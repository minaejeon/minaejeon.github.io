# 5 회귀분석 모델 실험 (Kaggle  Bike Sharing Demand).md

```python
# This Python 3 environment comes with many helpful analytics libraries installed
# It is defined by the kaggle/python Docker image: https://github.com/kaggle/docker-python
# For example, here's several helpful packages to load

import numpy as np # linear algebra
import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv)

# Input data files are available in the read-only "../input/" directory
# For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory

import os
for dirname, _, filenames in os.walk('/kaggle/input'):
    for filename in filenames:
        print(os.path.join(dirname, filename))

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```

<pre>
/kaggle/input/bike-sharing-demand/sampleSubmission.csv
/kaggle/input/bike-sharing-demand/train.csv
/kaggle/input/bike-sharing-demand/test.csv
</pre>

```python
train=pd.read_csv("/kaggle/input/bike-sharing-demand/train.csv")
test=pd.read_csv("/kaggle/input/bike-sharing-demand/test.csv")
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-01 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0000</td>
      <td>3</td>
      <td>13</td>
      <td>16</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-01 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>8</td>
      <td>32</td>
      <td>40</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-01 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>5</td>
      <td>27</td>
      <td>32</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-01 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>3</td>
      <td>10</td>
      <td>13</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-01 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>10881</th>
      <td>2012-12-19 19:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>15.58</td>
      <td>19.695</td>
      <td>50</td>
      <td>26.0027</td>
      <td>7</td>
      <td>329</td>
      <td>336</td>
    </tr>
    <tr>
      <th>10882</th>
      <td>2012-12-19 20:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>14.76</td>
      <td>17.425</td>
      <td>57</td>
      <td>15.0013</td>
      <td>10</td>
      <td>231</td>
      <td>241</td>
    </tr>
    <tr>
      <th>10883</th>
      <td>2012-12-19 21:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>15.910</td>
      <td>61</td>
      <td>15.0013</td>
      <td>4</td>
      <td>164</td>
      <td>168</td>
    </tr>
    <tr>
      <th>10884</th>
      <td>2012-12-19 22:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>17.425</td>
      <td>61</td>
      <td>6.0032</td>
      <td>12</td>
      <td>117</td>
      <td>129</td>
    </tr>
    <tr>
      <th>10885</th>
      <td>2012-12-19 23:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.12</td>
      <td>16.665</td>
      <td>66</td>
      <td>8.9981</td>
      <td>4</td>
      <td>84</td>
      <td>88</td>
    </tr>
  </tbody>
</table>
<p>10886 rows × 12 columns</p>
</div>


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>11.365</td>
      <td>56</td>
      <td>26.0027</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>2012-12-31 19:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>2012-12-31 20:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>2012-12-31 21:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>2012-12-31 22:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>8.9981</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>2012-12-31 23:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>65</td>
      <td>8.9981</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 9 columns</p>
</div>



```python
sub=pd.read_csv("/kaggle/input/bike-sharing-demand/sampleSubmission.csv")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>2012-12-31 19:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>2012-12-31 20:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>2012-12-31 21:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>2012-12-31 22:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>2012-12-31 23:00:00</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 2 columns</p>
</div>


datetime의 칼럼에서 train에 필요한 데이터만 가져오려고 한다.



```python
train["datetime"]=pd.to_datetime(train["datetime"])
train["Year"]=train["datetime"].dt.year
# train["Month"]=train["datetime"].dt.month
# train["Day"]=train["datetime"].dt.day
train["Hour"]=train["datetime"].dt.hour
# train["Minute"]=train["datetime"].dt.minute
train["Weekday"]=train["datetime"].dt.weekday

test["datetime"]=pd.to_datetime(test["datetime"])
test["Year"]=test["datetime"].dt.year
# test["Month"]=test["datetime"].dt.month
# # test["Day"]=test["datetime"].dt.day
test["Hour"]=test["datetime"].dt.hour
# test["Minute"]=test["datetime"].dt.minute
test["Weekday"]=test["datetime"].dt.weekday

display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>casual</th>
      <th>registered</th>
      <th>count</th>
      <th>Year</th>
      <th>Hour</th>
      <th>Weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-01 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0000</td>
      <td>3</td>
      <td>13</td>
      <td>16</td>
      <td>2011</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-01 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>8</td>
      <td>32</td>
      <td>40</td>
      <td>2011</td>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-01 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>5</td>
      <td>27</td>
      <td>32</td>
      <td>2011</td>
      <td>2</td>
      <td>5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-01 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>3</td>
      <td>10</td>
      <td>13</td>
      <td>2011</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-01 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>2011</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>10881</th>
      <td>2012-12-19 19:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>15.58</td>
      <td>19.695</td>
      <td>50</td>
      <td>26.0027</td>
      <td>7</td>
      <td>329</td>
      <td>336</td>
      <td>2012</td>
      <td>19</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10882</th>
      <td>2012-12-19 20:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>14.76</td>
      <td>17.425</td>
      <td>57</td>
      <td>15.0013</td>
      <td>10</td>
      <td>231</td>
      <td>241</td>
      <td>2012</td>
      <td>20</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10883</th>
      <td>2012-12-19 21:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>15.910</td>
      <td>61</td>
      <td>15.0013</td>
      <td>4</td>
      <td>164</td>
      <td>168</td>
      <td>2012</td>
      <td>21</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10884</th>
      <td>2012-12-19 22:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>17.425</td>
      <td>61</td>
      <td>6.0032</td>
      <td>12</td>
      <td>117</td>
      <td>129</td>
      <td>2012</td>
      <td>22</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10885</th>
      <td>2012-12-19 23:00:00</td>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.12</td>
      <td>16.665</td>
      <td>66</td>
      <td>8.9981</td>
      <td>4</td>
      <td>84</td>
      <td>88</td>
      <td>2012</td>
      <td>23</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>10886 rows × 15 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>Year</th>
      <th>Hour</th>
      <th>Weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>11.365</td>
      <td>56</td>
      <td>26.0027</td>
      <td>2011</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>2012-12-31 19:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>19</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>2012-12-31 20:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>20</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>2012-12-31 21:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>21</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>2012-12-31 22:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>8.9981</td>
      <td>2012</td>
      <td>22</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>2012-12-31 23:00:00</td>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>65</td>
      <td>8.9981</td>
      <td>2012</td>
      <td>23</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 12 columns</p>
</div>



```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.boxplot(test["Hour"],train["count"],showfliers=False)
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Hour', ylabel='count'>
</pre>
<img src="data:image/png;base64,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"/>

working day여부에 따른 대여수가 다를 것으로 보고 나누어 box plot으로 그려보겠다.



```python
weekday_df=train[train['workingday']==1]
weekday_df
weekend_df=train[train['workingday']==0]
weekend_df
plt.figure(figsize=(16,8))
sns.boxplot(weekday_df["Hour"],weekday_df["count"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Hour', ylabel='count'>
</pre>
<img src="data:image/png;base64,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"/>


```python
plt.figure(figsize=(16,8))
sns.boxplot(weekend_df["Hour"],weekend_df["count"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Hour', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA7MAAAHgCAYAAAB3mzofAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAABC2klEQVR4nO3de3xcd33n/9dHkZ1ALk48URxLiQlKst3dB78tBS9QemMVKi6lmO0WCtJ2uaSP7M8/6i2lMQ2mj/11dwmm2CxL6e+nNsuloSvRAm3XIUkTpRFQfo+Wi2HBmCQt1hQlkXJxxrGdyzr2WN/fH3NMlCDJGkkz5xzp9Xw89JiZc+Y7308U+cy85/s93xMpJSRJkiRJKpOOvAuQJEmSJKlZhllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUul05l3AUlx44YXpsssuy7sMSZIkSVILfPOb33wkpdQ1275Sh9nLLruMvXv35l2GJEmSJKkFImJirn1OM5YkSZIklY5hVpIkSZJUOoZZSZIkSVLpGGYlSZIkSaVjmJUkSZIklU5Lw2xE/GZEfC8i9kfEZyLirIh4fkR8LSIORMSfRcTa7LlnZo8PZPsva2VtkiRJkqTyalmYjYge4D8Am1NKLwDOAN4M/B7wkZTSFcCjwNVZk6uBR7PtH8meJ0mSJEnSj2j1NONO4DkR0Qk8F3gA6AM+n+2/EXhDdn9L9phs/1URES2uT5IkSZJUQi0LsymlSWA3cC+NEHsE+CZwOKVUz552P9CT3e8B7sva1rPnV1pVnyRJkiSpvFo5zfgCGqOtzwe6gbOBVy/D614TEXsjYu/BgweX+nKSJEmSpBJq5TTjVwL/mFI6mFI6AfwF8FPA+dm0Y4BLgMns/iRwKUC2fx1Qe/aLppRuSCltTilt7urqamH5kiRJkqSiamWYvRd4WUQ8Nzv39SrgLuCLwC9nz3krsCe7f1P2mGz/WEoptbA+SZIkSVJJtfKc2a/RWMjpW8B3s75uAH4beHdEHKBxTuwnsiafACrZ9ncD17WqNkmSJElSuUWZBz83b96c9u7dm3cZkiRJkqQWiIhvppQ2z7av1ZfmkSRJkiRp2RlmJUmSJEmlY5iVJEmSJJVO5+mfIkmSpNVsaGiIarU65/7JycaVFnt6embd39vby9atW1tSm6TVyzArSZKkJTl27FjeJUhahQyzkiRJmtfpRlW3b98OwK5du9pRjiQBnjMrSZIkSSohw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQ68y5AkiQtv6GhIarV6qz7JicnAejp6ZmzfW9vL1u3bm1JbZIkLQfDrCRJq8yxY8fyLkGSpCUzzEqStALNN6q6fft2AHbt2tWuciRJWnaeMytJkiRJKh3DrCRJkiSpdAyzkiRJkqTSMcxKkiRJkkrHMCtJkiRJKh3DrCRJkiSpdAyzkiRJkqTSMcxKkiRJkkrHMCtJkiRJKh3DrCRJkiSpdDrzLkCSJCkvQ0NDVKvVWfdNTk4C0NPTM2f73t5etm7d2pLaJEnzM8xKkqS2KFtwPHbsWNv60uKU7W9K0vIyzEqSpNzlFRznCzLbt28HYNeuXe0qR8vILyOklc8wK0mS2sLgqOXm35S0uhlmJUmSCmS+qbNw+umzTp2VtFoYZiVJkkrE6bOS1GCYlSRJKpDTjao6fVaSGrzOrCRJkiSpdAyzkiRJkqTSMcxKkiRJkkrHMCtJkiRJKh3DrCRJkiSpdAyzkiRJkqTSaVmYjYgfi4hvz/g5GhHvioj1EXFHRHw/u70ge35ExO9HxIGI2BcRL2pVbZIkSZKkcmtZmE0p/X1K6YUppRcCLwaeBP4SuA64M6V0JXBn9hjgNcCV2c81wFCrapMkSZIklVu7phlfBYynlCaALcCN2fYbgTdk97cAn04NXwXOj4iNbapPkiRJklQi7QqzbwY+k93fkFJ6ILv/ILAhu98D3Dejzf3ZNkmSJEmSnqHlYTYi1gKvBz737H0ppQSkJl/vmojYGxF7Dx48uExVSpIkSZLKpB0js68BvpVSeih7/NCp6cPZ7cPZ9kng0hntLsm2PUNK6YaU0uaU0uaurq4Wli1JkiRJKqp2hNm38PQUY4CbgLdm998K7Jmx/d9lqxq/DDgyYzqyJEmSJEk/1NnKF4+Is4GfB/79jM0fBD4bEVcDE8Cbsu23Aq8FDtBY+fjtraxNkiRJklReLQ2zKaUngMqzttVorG787Ocm4J2trEeSJEmStDK0azVjSZIkSZKWjWFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6Lb00jyRJkrSaDA0NUa1WZ903OTkJQE9Pz5zte3t72bp1a0tqk1Yaw6wkSZLUBseOHcu7BGlFMcxKkiRJy2S+UdXt27cDsGvXrnaVI61onjMrSZIkSSodw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0unMuwBJkspsaGiIarU65/7JyUkAenp6Zt3f29vL1q1bW1KbJEkrmWFWkqQWOnbsWN4lSJK0IhlmJUlagtONqm7fvh2AXbt2taMcSZJWDc+ZlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6LQ2zEXF+RHw+Iu6JiLsj4icjYn1E3BER389uL8ieGxHx+xFxICL2RcSLWlmbJEmSJKm8Wj0y+1HgtpTSPwV+HLgbuA64M6V0JXBn9hjgNcCV2c81wFCLa5MkSZIklVTLwmxErAN+FvgEQErpeErpMLAFuDF72o3AG7L7W4BPp4avAudHxMZW1SdJZVGr1bj22ms5dOhQ3qVIkiQVRitHZp8PHAQ+FRH/KyI+HhFnAxtSSg9kz3kQ2JDd7wHum9H+/mybJK1qIyMj7N+/n+Hh4bxLkSRJKoxWhtlO4EXAUErpJ4AneHpKMQAppQSkZl40Iq6JiL0RsffgwYPLVqwkFVGtVmN0dJSUEqOjo47OSpIkZVoZZu8H7k8pfS17/Hka4fahU9OHs9uHs/2TwKUz2l+SbXuGlNINKaXNKaXNXV1dLStekopgZGSE6elpAKanpx2dlSRJyrQszKaUHgTui4gfyzZdBdwF3AS8Ndv2VmBPdv8m4N9lqxq/DDgyYzqyJK1KY2Nj1Ot1AOr1OmNjYzlXJEmSVAydLX79bcBwRKwFqsDbaQToz0bE1cAE8KbsubcCrwUOAE9mz5WkVa2vr4/bbruNer1OZ2cnfX19eZckSZJUCC29NE9K6dvZlOB/kVJ6Q0rp0ZRSLaV0VUrpypTSK1NKh7LnppTSO1NKl6eU/o+U0t5W1iZJZTAwMEBHR+NQ3dHRweDgYM4VSZK0Onl1geJp9XVmJUlLUKlU6O/vJyLo7+9n/fr1eZckSdKq5NUFiscwK0kFNzAwwAte8AJHZSVJyolXFygmw6wkFVylUmH37t2OykqSlBOvLlBMhllJkiRJmodXFygmw6wkSZIkzaOvr4/OzsaFYLy6QHEYZiVJkiRpHl5doJgMs5IkSZI0D68uUEydeRcgSZIkSUU3MDDAxMSEo7IFYpiVJEmSpNM4dXUBFYfTjCVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJhVKr1bj22ms5dOhQ3qWowDrzLkCSJElS6wwNDVGtVmfdNzk5CUBPT8+c7Xt7e9m6dWtLapvLyMgI+/fvZ3h4mG3btrW1b5WHI7OSJEnSKnXs2DGOHTuWdxnPUKvVGB0dJaXE6Oioo7OakyOzkiRJ0go236jq9u3bAdi1a1e7yjmtkZERpqenAZiennZ0VnNyZFaSJElSYYyNjVGv1wGo1+uMjY3lXJGKyjArSZIkqTD6+vro7GxMIO3s7KSvry/nilRUhllJKjhXdJQkrSYDAwN0dDRiSkdHB4ODgzlXpKIyzEpSwc1c0VGSpJWuUqnQ399PRNDf38/69evzLkkFZZiVpAJzRUdJ0mo0MDDAC17wAkdlNS9XM5akAnNFx2ea71qJcPrrJeZxrURJUvMqlQq7d+/OuwwVnCOzklRgrujYnCJeL1GSJLWGI7OSVGB9fX3cdttt1Ot1V3Rk/mslQjGvlyhJklrDkVlJKjBXdJQkSZqdYVaSCswVHSVJkmbnNGNJKriBgQEmJiYclZUkSZrBMCtJBeeKjpIkST/KacaSJEmSpNIxzEqSJEmSSscwK0mSJEkqHcOsJEmSJKl0DLOSJEmSpNIxzEqSJEmSSscwK0mSJEkqHcOsJEmSJKl0DLOSJEmSpNIxzEqSJElSCdVqNa699loOHTqUdym5aGmYjYgfRMR3I+LbEbE327Y+Iu6IiO9ntxdk2yMifj8iDkTEvoh4UStrkyRJkqQyGxkZYf/+/QwPD+ddSi4629DHv0opPTLj8XXAnSmlD0bEddnj3wZeA1yZ/bwUGMpuJUmSFm1oaIhqtdp0u/HxcQC2b9++qH57e3vZunXrotpK0unUajVGR0dJKTE6Osrg4CDr16/Pu6y2akeYfbYtwCuy+zcCX6IRZrcAn04pJeCrEXF+RGxMKT2QQ42SJGmFqFar7Lvn7+moXNRUu+kUAOw/+GjTfU7XHm66jSQ1Y2RkhOnpaQCmp6cZHh5m27ZtOVfVXq0OswkYjYgE/FFK6QZgw4yA+iCwIbvfA9w3o+392TbDrCRJWpKOykWc+bq3tK2/p27+TNv6krQ6jY2NUa/XAajX64yNjRlml9lPp5QmI+Ii4I6IuGfmzpRSyoLugkXENcA1AJs2bVq+SiVJ0pIsdjovOKVXkprV19fHbbfdRr1ep7Ozk76+vrxLaruWhtmU0mR2+3BE/CXwEuChU9OHI2IjcGoeziRw6Yzml2Tbnv2aNwA3AGzevLmpICxJklqnMZ33HqJyYdNtU/aO/t2Dj8z/xNna1ppvI0llNzAwwOjoKAAdHR0MDg7mXFH7tSzMRsTZQEdK6bHsfj/wn4GbgLcCH8xu92RNbgJ+PSL+lMbCT0c8X1aSpHKJyoWsed2WtvZ54uY9p3+SJK0wlUqF/v5+brnlFvr7+1fd4k/Q2pHZDcBfRsSpfkZSSrdFxDeAz0bE1cAE8Kbs+bcCrwUOAE8Cb29hbZIkSZJUagMDA0xMTKzKUVloYZhNKVWBH59lew24apbtCXhnq+qRJGkl8fxUSVKlUmH37t15l5GbPC7NI0mSlqhxfurdRKX5aWUpO0H1uwcfar5t7VDTbSRJagXDrCRJJRWV9XS+7lVt7bN+8+1t7W+lcmRdkpbOMCtJktRmjZH1f+CMysam206nMwD43sHHmm57subampJWDsOsJElSDs6obOS5v3hNW/t88gs3tLU/SWqljrwLkCRJkiSpWYZZSZIkSVLpGGYlSZIkSaVjmJUkSZIklY5hVpIkSZJUOq5mLEmSJK99K6l0DLOSJEmiWq2y/57vc2bl0qbbHk9rAPj+wWNNt32qdl/TbSQJDLOSJEnKnFm5lE1b3tPWPu/d86G29idp5TDMSpIkqZCc+qwiqdVq7Ny5kx07drB+/fq8yxGGWUmSJBVUtVrl7nsOcH5lU9Ntp9NaAB44eLzptodr9zbdRivfyMgI+/fvZ3h4mG3btuVdjjDMSpIkqcDOr2ziFa9/X1v7/NJN17e1PxVfrVZjdHSUlBKjo6MMDg46OlsAXppHkiRJkuYxMjLC9PQ0ANPT0wwPD+dckcAwK0mSJEnzGhsbo16vA1Cv1xkbG8u5IoFhVpIkSZLm1dfXR2dn4wzNzs5O+vr6cq5IYJiVJEmSpHkNDAzQ0dGITh0dHQwODuZckcAwK0mSJEnzqlQq9Pf3ExH09/e7+FNBuJqxJEmSJJ3GwMAAExMTjsoWiGFWkiRJkk6jUqmwe/fuvMvQDE4zliRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUukYZiVJkiRJpWOYlSRJkiSVjmFWkiRJklQ6hllJkiRJUul05l2AJElFNzQ0RLVaXVTb8fFxALZv376o9r29vWzdunVRbSVJWskMs5IknUa1WmXfPXdDZV3zjdNJAPYdnGq+be1I820kSVolDLOSJC1EZR2dv/hzbe2y/oUvt7U/SZLKxHNmJUmSJEmlY5iVJEmSJJXOgsJsRNy5kG2SJEmSJLXDvOfMRsRZwHOBCyPiAiCyXecBPS2uTZIkSZKkWZ1uAah/D7wL6Aa+ydNh9ijwB60rS5IkSZKkuc0bZlNKHwU+GhHbUkofa1NNkiRJkiTNa0GX5kkpfSwiXg5cNrNNSunTp2sbEWcAe4HJlNLrIuL5wJ8CFRqjvb+aUjoeEWcCnwZeDNSAX0kp/aC5/xxJkiSpdYaGhqhWq4tqOz4+DsD27dsX1b63t5etW7cuqq20Ei0ozEbEnwCXA98GTmabE43weTq/AdxN4zxbgN8DPpJS+tOI+EPgamAou300pXRFRLw5e96vLPC/Q5JWrFqtxs6dO9mxYwfr16/PuxxJWtWq1Sr33HOArvXPa75xWgtA7eETTTc9eGii+f6kFW5BYRbYDPzzlFJq5sUj4hLgF4DrgXdHRAB9wED2lBuB36URZrdk9wE+D/xBRESzfUrSSjMyMsL+/fsZHh5m27ZteZcjSate1/rn8cbX/k5b+/zcre9va39SGSw0zO4HLgYeaPL1/xvwHuDc7HEFOJxSqmeP7+fpVZF7gPsAUkr1iDiSPf+RmS8YEdcA1wBs2rSpyXIkqVxqtRqjo6OklBgdHWVwcNDRWUlS6Z1uuvbk5CQAPT2zX0DFKdeChYfZC4G7IuLrwFOnNqaUXj9Xg4h4HfBwSumbEfGKpRQ5U0rpBuAGgM2bNztqK2lFGxkZYXp6GoDp6em2js7O90HjdB8ywA8akqTFO3bsWN4lqAQWGmZ/dxGv/VPA6yPitcBZNM6Z/ShwfkR0ZqOzlwCT2fMngUuB+yOiE1hHYyEoSVq1xsbGqNcbk1nq9TpjY2OFmGrshwxJ0lKc7svOU4tk7dq1qx3lqKQWuprxl5t94ZTSe4H3AmQjs9emlAYj4nPAL9NY0fitwJ6syU3Z47/L9o95vqykdivaYkt9fX3cdttt1Ot1Ojs76evra1vf833Q8EOGJEnKW8dCnhQRj0XE0eznWEScjIiji+zzt2ksBnWAxjmxn8i2fwKoZNvfDVy3yNeXpEWbudhSEQwMDNDR0ThUd3R0MDg4mHNFkiRJxbCgMJtSOjeldF5K6TzgOcC/Af7fhXaSUvpSSul12f1qSuklKaUrUkpvTCk9lW0/lj2+Itu/uAt4SdIiPXuxpUOHDuVdEpVKhf7+fiKC/v7+QowWS5IkFcGCwuxMqeF/Aq9a/nIkKT+zLbZUBAMDA7zgBS9wVFaSJGmGBZ0zGxG/NONhB43rzrr6h6QVpaiLLVUqFXbv3p13GZIkSYWy0JHZX5zx8yrgMWBLq4qSpDz09fXR2dn4jq/diy1JkiSpOQtdzfjtrS5EkvI2MDDA6Ogo4GJLkiRJRbfQ1YwviYi/jIiHs58/j4hLWl2cJLWTiy1JkiSVx0KnGX+KxnVgu7OfL2TbJGlFcbElSZKkcljQNGOgK6U0M7z+cUS8qwX1SFKuXGxJZTE1NUU6eoT6zbe3td9UO8TUiZNt7VOSpNksNMzWIuLfAp/JHr8FqLWmJEmSVEaNgH2UEzfvaWu/qfYIUyeOz7l/amqK6aOP8dTNn5nzOcttuvYwUyf+d9v6Ww5TU1M8dfQJ7t3zobb2+1TtPqZOnN3WPiWtDAsNs+8APgZ8BEjA3wJva1FNkiTpNLq7u6mtOYPO17X3su/1m2+nu2tDW/tciaampjh59HGe/MINbe33ZO0Bpk481tY+JalVFhpm/zPw1pTSowARsR7YTSPkSpIkZQF7LWte196r9524eQ/dXRfOub+7u5tDax7lzNe9pW01PXXzZ+juuqBt/S2H7u5unlhzjE1b3tPWfu/d8yG6u85qa5+SVoaFhtl/cSrIAqSUDkXET7SoJkmSpBWtu7ubR9c8xnN/8Zq29vvkF26gu+vctvYpSa2y0NWMOyLih18vZiOzCw3CkiRJkiQtq4UG0g8DfxcRn8sevxG4vjUlSZIkSZI0vwWF2ZTSpyNiL9CXbfqllNJdrStLkiRJkqS5LXiqcBZeDbCSJEmSpNwt9JxZSZIkSZIKwzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0vFasZKkQhkaGqJarS6q7fj4OADbt29fVPve3l62bt26qLaSJKm9DLOSpEKpVqvsu+cuqJzTfON0AoB9B+9tvm3t8ebbSJKk3BhmJUnFUzmHzi2b29plfc/etvYnSZKWxjArSZKkQpqamuLI0Sf40k3Xt7Xfw7UJ0omz29qntBi1Wo2dO3eyY8cO1q9fn3c5becCUJIkSZJUQiMjI+zfv5/h4eG8S8mFI7OSJEkqpO7ubmLNcV7x+ve1td8v3XQ9G7vWtrXPpVrs4nkunFdetVqN0dFRUkqMjo4yODi46kZnDbOSJElSyVWrVf7h7gNcfP6mptp1TDdC+9EHjjfd54OHF7HYXoGd7guByclJAHp6embd3+5gPzIywvT0NADT09MMDw+zbdu2tvVfBIZZSZIkaQW4+PxN/NpV7RvF/vid7T2XOW/Hjh3Lu4RnGBsbo16vA1Cv1xkbGzPMSpIkSdJqc7pR1VNTsXft2tWOck6rr6+P2267jXq9TmdnJ319fXmX1HYuACVJkiRJJTMwMEBEANDR0cHg4GDOFbWfYVaSJEmSSqZSqdDd3Q3Axo0bV93iT2CYlSRJkqTSqdVqTE1NAY1rMh86dCjnitrPc2YlSTqNqakpOHqY+he+3N6Oa4eZOtHeLiVJ5TAyMkJKCYCU0qpczdiRWUmSJEkqmdlWM15tHJmVJOk0uru7eWQNdP7iz7W13/oXvkx3V3db+5QklYOrGTsyK0mSJEmlMzAwQEdHI865mrEkSZIkqRQqlQr9/f1EBP39/atyNWOnGUuSJElSCQ0MDDAxMbEqR2XBMCtJkiRJpVSpVNi9e3feZeTGacaSJEmSpNIxzEqSJEmSSscwK0mSJEkqnZaF2Yg4KyK+HhHfiYjvRcR/yrY/PyK+FhEHIuLPImJttv3M7PGBbP9lrapNksqkVqtx7bXXcujQobxLkSRJKoxWjsw+BfSllH4ceCHw6oh4GfB7wEdSSlcAjwJXZ8+/Gng02/6R7HmStOqNjIywf/9+hoeH8y5FkiSpMFoWZlPD49nDNdlPAvqAz2fbbwTekN3fkj0m239VRESr6pOkMqjVaoyOjpJSYnR01NFZSZKkTEvPmY2IMyLi28DDwB3AOHA4pVTPnnI/0JPd7wHuA8j2HwEqraxPkopuZGSE6elpAKanpx2dlSRJyrQ0zKaUTqaUXghcArwE+KdLfc2IuCYi9kbE3oMHDy715SSp0MbGxqjXG9//1et1xsbGcq5IkiSpGNqymnFK6TDwReAngfMjojPbdQkwmd2fBC4FyPavA2qzvNYNKaXNKaXNXV1drS5dknLV19dHZ2fjkNnZ2UlfX1/OFUmSJBVDK1cz7oqI87P7zwF+HribRqj95expbwX2ZPdvyh6T7R9LKaVW1SdJZTAwMEBHR+NQ3dHRweDgYM4VSZIkFUMrR2Y3Al+MiH3AN4A7Uko3A78NvDsiDtA4J/YT2fM/AVSy7e8GrmthbZJUCpVKhf7+fiKC/v5+1q9fn3dJkiRJhdB5+qcsTkppH/ATs2yv0jh/9tnbjwFvbFU9klRWAwMDTExMOCorSQUwNTXF0SNP8rlb39/Wfg/WJniq/ty29ikVXcvCrCRpeVQqFXbv3p13GZIkSYVimJUkSZIWqLu7mzM7T/DG1/5OW/v93K3vp3LRmrb2KRVdW1YzliRJkiRpORlmJUmSJEml4zRjSZIkSSqooaEhqtXqrPsmJycB6OnpmbN9b28vW7dubUlteTPMSpIkSVIJHTt2LO8ScmWYlSRJkqSCmm9Udfv27QDs2rWrXeUUiufMSpIkSZJKx5FZSZKkHJysPcCTX7ih6XbTR2oAdKyrLKpPus5tup0kFZFhVpJmqNVq7Ny5kx07drB+/fq8y5HmlWqHqN98e/PtjjwGQKxrPtSk2iHo2tB0Oz1Tb2/votuOH30YgMsXE0q7zl1S35JUJIZZSZphZGSE/fv3Mzw8zLZt2/IuR5rT0sLQ4wBcvphQ2rXBMLQMlrKy6Go/R06STjHMSlKmVqsxOjpKSonR0VEGBwcdnVVhGYYkSaudYVaSMiMjI0xPTwMwPT1dmNHZ1Tb1eWpqCo4+Rn3P3vZ2XHuMqRNT7e1TkiQtmmFWkjJjY2PU63UA6vU6Y2NjhQizTn1WmaTaI5y4eU/z7Y4cASDWrVtUn3Rd2HQ7SVK5GWYlKdPX18dtt91GvV6ns7OTvr6+vEtalVOfu7u7eWRNnc4tm9vab33PXrq7utva50qztPN4G2H28sWE0q4LPY9XKqChoSGq1eqi2o6PjwNPnxbRrN7e3iWdjqFyMMxKUmZgYIDR0VEAOjo6GBwczLmi4k59lmbjebySZqpWq3z/rgNcet6mptuuqa8F4Nj9x5tue9/Re5tuo3IyzEpSplKp0N/fzy233EJ/f38hRkCLOvVZkqSFuPS8TfzWS9/b1j4//LWdbe1P+THMsvoWV5E0t4GBASYmJto+KjvXVKyzzjqLJ5988oePn/Oc58w65crpVJIkabXpyLuAIpi5uIqk1a1SqbB79+7CfLG1YcPT1wGNCC666KIcq5EkSSqOVT8yuxoXV5FUPPONqr7lLW/h0KFD/MIv/IJTjKVFmq49zFM3f6a5NkceBaBj3QWL6o+u5ttJkhZu1YdZF1eRVHQbNmzgqaeeKsSCVFIZLXal4/GjhwC4fDGhtOsCV1iWpBZb9WHWxVUkFd2aNWu4/PLLnTUiLdJizyd3hWVJKrZVf85sX18fnZ2NTF+U60pKkiRJkua36kdmi3hdSUmSpDw8VbuPe/d8qOl2x488DMDadc0vUvdU7T7ourLpdpK06sNsEa8rKUmS1G5LOcd3/OgJAC7vOqv5xl1Xen6xpEVZ9WEW8ruupCRJUlEs5VrVnl+cv6mpKR478gQfv/P6tvX5wOEJHk9nt60/FcfQ0BDVanXWfZOTkwD09PTM2b63t3dJx5xTDLM8fV1JSVpt5nszms/4+Djw9AfYZi3Xm5gkSSqWY8eOta0vw6wkrWLVapV99+yHC5udGngcgH2PHGi+00fa9yYnSatFd3c3R+M4v3bV+9rW58fvvJ7zNq5tW38qjvm+kG7nTA3DrCStdheexRlb2ne+2sk9zY8ES5IkPduqvzSPJEmSJKl8DLOSJEmSpNIxzEqSJEmSSscwK0mSJEkqHcOsJEmSJKl0DLOSJEmSpNIxzEqSJEmSSscwK0mSJEkqHcOsJEmSJKl0OvMuQJIkSZrL4dq9fOmm65tu9/iRhwA4Z92GRfW5seuKpttJai/DrCRJkgqpt7d30W3Hjx4HYGPX2qbbbuy6Ykl9S2oPw6wkSQtRO0L9C19uvt2Rxxu3685ZVJ90dTffTlohtm7duui227dvB2DXrl3LVY6kglkVYXZoaIhqtTrn/snJSQB6enpm3d/b27ukg6kkqdyWNjo0DsDliwmlXd2ODknSMjpdLpjP+HjjeH7qi5JmmSmWX8vCbERcCnwa2AAk4IaU0kcjYj3wZ8BlwA+AN6WUHo2IAD4KvBZ4EnhbSulbrapvpmPHjrWjG0lSSTk6JEkrQ7Va5cBd32fTubMPYs1nbb0RnY7f92TTbe99bLLpNjq9Vo7M1oHfSil9KyLOBb4ZEXcAbwPuTCl9MCKuA64Dfht4DXBl9vNSYCi7XbLTfQjxg4YkSZK0Omw6t4f3/sttbe1z5zc+1tb+VouWXZonpfTAqZHVlNJjwN1AD7AFuDF72o3AG7L7W4BPp4avAudHxMZW1SdJkiRJKq+2XGc2Ii4DfgL4GrAhpfRAtutBGtOQoRF075vR7P5s27Nf65qI2BsRew8ePNi6oiVJkiRJhdXyMBsR5wB/DrwrpXR05r6UUqJxPu2CpZRuSCltTilt7urqWsZKJUmSJEll0dIwGxFraATZ4ZTSX2SbHzo1fTi7fTjbPglcOqP5Jdk2SZIkSZKeoWVhNlud+BPA3Sml/zpj103AW7P7bwX2zNj+76LhZcCRGdORJUmSJEn6oVauZvxTwK8C342Ib2fbdgAfBD4bEVcDE8Cbsn230rgszwEal+Z5ewtrkyRJkiSVWMvCbErp/wNijt1XzfL8BLyzVfVIkiRJklaOtqxmLEmSJEnScmrlNGNJkhan9jj1PXubb3fkycbtuucuqk9cJF+SpNIwzEqSCqW3t3fRbcePjgNwedem5ht3La1vSZLUXoZZSVKhbN26ddFtt2/fDsCuXbuWqxxJklRQhllJWsWmpqbg6DFO7qm2r9NHjjF1fKp9/UmScjE1NcUTR5/gw1/b2dZ+7zs6wdlTZ7e1T+XDBaAkSZIkSaXjyKwkrWLd3d08svZJztjSvnNFT+6p0n1hd9v6kyTlo7u7m2PTx/mtl763rf1++Gs7Oat7bVv7VD4cmZUkSZIklY4js5IkSVITDh6a4HO3vr/pdoePPgjA+eddvKg+Kxdd0XQ7aSUzzEqSJEkLtJRLeB1+7DgAlYvWNN22ctEVXj5MehbDbE6GhoaoVudePXRychKAnp6eWff39vYu6fIVkiRJap6XD5OKwzBbUMeOHcu7BEmSJEkqLMNsTk73rZ7f3EmSJEnS3AyzkiRJkpST051+OJ/x8XHg6YGwZpX91EXDrCTNUKvV2LlzJzt27GD9+vV5lyNJkla4arXKgbv+nk2LWOV6bb1xpdXj9x9puu292eraZWaYlaQZRkZG2L9/P8PDw2zbti3vciRJ0iqw6byL2fGyt7e1zw989VNt7a8VOvIuQJKKolarcfvtt5NSYnR0lEOHDuVdkiRJkuZgmJWkzMjICPV6HYATJ04wPDycc0WSJEmai2FWkjJ33nknKSUAUkrceeedOVckSZKkuRhmJSlz0UUXzftYkiRJxeECUJKUefjhh+d9LEmSym1qaoonHnucnd/4WFv7nXjsfs6eOqetfa4GjsxKUuaqq64iIgCICK666qqcK5IkSdJcHJmVpMzAwAC33347J06coLOzk8HBwbxLkiRJy6i7u5vjJ5/kvf+yvZff2/mNj7G2+7lt7XM1cGRWkjKVSoVXvepVRASvetWrWL9+fd4lSZIkaQ6OzErKTa1WY+fOnezYsaMwwXFgYICJiYllH5UdGhqiWq0uqu34+DgA27dvX1T73t5etm7duqi2kiRJRWWYlZSbkZER9u/fz/DwMNu2tXe6z1wqlQq7d+9e9tetVqt89559rKk037beuFoQ9xzc13TbE7Xm+5MkSSoDw6ykXNRqNUZHR0kpMTo6yuDgYGFGZ1tlTQUu3BJt7fORPamt/UmS8vPg4Xv5+J3XN9Wm9vhDAFTO2bCo/s7beEXT7aTlYpiVlIuRkRGmp6cBmJ6eLtTorCRJZdPb27uodgfHjwNw3sa1Tbc9b+MVi+5XWg6GWUm5GBsbo16vA1Cv1xkbGzPMSpK0SItdG+HUegy7du1aznKktnA1Y0m56Ovro7Oz8X1aZ2cnfX19OVckSZKkMjHMSsrFwMAAHR2NQ1BHR4fXdJUkSVJTnGYsKReVSoX+/n5uueUW+vv7V/ziT5IkSWVRlksKrpgwW5ZfuKSnteqarpIkSVq8arXKgbvuYdO6rqbbrj3ZuD0+2fz1Ae89crCp56+YMNv4hd/NpnXNj+6sPdm4dMXxyYeabnvvkUNNt5HU0Kprup7OfF9+TU5OAtDT0zNne7/AkiRJK92mdV287+VvbGuf1//t55p6/ooJswCb1q3nd36mv619vv8ro23tr9X8kK/V7tixY3mXIEmSpAVYUWFWreWHfK0U833h4iUKJElSO01NTfHE0cf4wFc/1dZ+J44+yNlTT7S1z+VmmNUz+CFfkiRJUhkYZiVJkiQpJ93d3RyfPsKOl729rf1+4KufYm33urb2udy8zqwkSZIkqXQMs5IkSZKk0jHMSpIkSZJKp2VhNiI+GREPR8T+GdvWR8QdEfH97PaCbHtExO9HxIGI2BcRL2pVXZIkSZKk8mvlAlB/DPwB8OkZ264D7kwpfTAirsse/zbwGuDK7OelwFB2K2kFq9Vq7Ny5kx07drB+/fq8y5EkScvsvqP38uGv7Wy63cNPPATARWdvWFSfV3JF0+1UPi0Lsymlv4mIy561eQvwiuz+jcCXaITZLcCnU0oJ+GpEnB8RG1NKD7SqPkn5GxkZYf/+/QwPD7Nt27a8y1m9HjnGyT3V5tocOd64Xbd2Uf1xYfPNJEnl0tvbu+i2J8Yb7zNnXdL8+8yVXLGkvlUe7b40z4YZAfVB4NRXLT3AfTOed3+2zTArrVC1Wo3R0VFSSoyOjjI4OOjobA4W+2Y/fmQcgMsvvLz5xhcu7QOOJKkctm7duui227dvB2DXrl3LVY5WoNyuM5tSShGRmm0XEdcA1wBs2rRp2euS1B4jIyNMT08DMD09veJHZ6empjhxFB7Z0/Rhb0lO1GDqxNSc+xf7QcMPGZIkKW/tDrMPnZo+HBEbgYez7ZPApTOed0m27UeklG4AbgDYvHnzDz8VTk1N8cSRI7z/K6OtqXwOE0cOcXacbGuf0kowNjZGvV4HoF6vMzY2tqLDrCRJkpZXu8PsTcBbgQ9mt3tmbP/1iPhTGgs/HVkJ58sODQ1RrTZ5HlpmfLwxhe/U6Eezent7lzS1Q2q1vr4+brvtNur1Op2dnfT19eVdUkt1d3dzdM0jXLgl2trvI3sS3V3dbe1TkiSpHVoWZiPiMzQWe7owIu4H/m8aIfazEXE1MAG8KXv6rcBrgQPAk8Dbm+2vu7ub4+kMfudn+peh+oV7/1dGWds9+ypr1WqVA3fdxaZ15zT9umtPngDg+OS9Tbe998jjTbeR2m1gYIDR0cZMio6ODgYHB3OuSJIkSWXSytWM3zLHrqtmeW4C3tmqWvK0ad057PiZzW3t8wNf2dvW/qTFqFQq9Pf3c8stt9Df3+/iT5IkSWpKbgtASdLAwAATExOOykqSJKlpHXkXIEmSJElSswyzknIzMjLC/v37GR4ezrsUSZIklYzTjCXlolarMTo6SkqJ0dFRBgcHPW9WkiS13L2PTbLzGx9rut1DTx4EYMNzuxbV5xVc2XQ7zc8wKykXIyMjTE9PAzA9Pc3w8LDXmZUkSS3V29u76LbHx+sArL30uU23vYIrl9R3u01NTfHEkaNc/7efa2u/E0cOcnY8teDnG2Yl5WJsbIx6vfGmUK/XGRsbM8xKkqSW2rp166Lbbt++HYBdu3YtVzlaIsOspFz09fXxV3/1V5w8eZIzzjiDvr6+vEuSJEkS0N3dzfF0Ju97+Rvb2u/1f/s51nZXFvx8F4CSlIuBgQEal5iGlJKX55EkSVJTHJltocZc88f4wFf2trXfiSOPcXZMzbpvaGiIarW6qNcdHx8Hnp5i0aze3t4lTe2YTa1WY+fOnezYscPFgyRJkqRVxDC7ylSrVb5/1z4uPe+MptuuqTcW6zl2//eabnvf0ZNNt1mImZd28XzLchkZGaGjo4Pp6Wk6Ojr8fyhJkqSmGGZbqDHXvM6On9nc1n4/8JW9rO3unnP/peedwfafbH4VtqXY9XdPLvtremmXcnMBKEmSJC2F58yqtGa7tIvKo6+vj87OxvdpnZ2dLgAlSZKkpjgyq9JyZK/cBgYGuP322wHo6OhwAShJkrRq3Xv0QT7w1U813e6hJw4BsOHs5mcn3nv0Qa5gXdPtisQwq9Lq6+vjtttuo16vO7JXQpVKhe7ubiYmJti4ceOyThEv6kJnJ2rwyJ7U9GvWjzRuOxfxfnOiBnQ1306SJLVHb2/votseH38EgLWXNP8h4QrWLanvIjDMqrQGBgYYHR0FHNlbiKKt/Fyr1Ziaaqy6PTU1xaFDh5atrmq1yvfu2cc5i3i5E1nWnHh4X9NtHz80976lvFmMH20E7Mu7Lm++cdfS+pYkSa21lKt9nPryfdeuXctVTqkYZlValUqF/v5+brnlFvr7+wsR0IqsaCs/j4yMPOM6s8td1znr4cdfu2wvtyDfuXXufb5RSfPPmljIrIhWXOJNklRehtlVZmpqiieOnmzJ6sLzue/oSc6emv3at6cz34ef++67jzPOOIPx8fE5PwD54aeYKz97zrOkmc4666y8S5AklYxhVqV2/PhxzjzzTNasWZN3KYU228rPeQdHz3mWVp/V/sWiJGl5ragwe++RQ7z/K6NNt3voiccA2HD2uYvq84qeDU23y0t3dzfHph/N5TqzZ81z7dv5zPfhx+mXC1PEUVDPeZYkSdJSrJgwu7RVwB4HYO0iQukVPRtcXEWFl9co6OlWFY4IAM4991x27tz5I/udIi5JkqS5rJgw6+Iq0tyKOgra0dFBR0cHF110Ud6lSJIkqWRWTJiVNLe8Vn4+3ZdMfpEkSZJUTPceOcj1f/u5pts99MRhADacff6i+ryip7Lg5xtmW+zeI4/zga/sbbrdQ080VhvecHbz57bee+RxruhpuplWuJe//OXceuut/PRP/3TepUiSJKnAlnYK52EA1jYRSk+5oqfSVN+G2RZa2h9B43p7a3s2Nd32ip6l9a2V6Y/+6I+Ynp5maGiIG264Ie9yJEmSVFBlOYXTMNtCZfkj0Mp34MABJiYmAJiYmKBara7oLzympqZ4/Ah859b29vt4Dabqi7uesiRJkppjmJVWgQ996EPPePzBD37Q0VlJYv5V18ezWVKnvmCejauuS1J+DLOr0H1HT7Lr755sut3DT0wDcNHZHYvq88qmW2m5nBqVnevxStPd3c2Jzkf48de2t9/v3ArdFy3uesqSiuess87KuwRJ0jwMs6vMUqaWnsi+oT7rksubbnvlEvsuk1qtxs6dO9mxY0fbVg0+nec973nPCLDPe97zcqxGkorDUVVJKi/D7CpTxPN455vidToLmQI2n1ZMD/vkJz/Jd7/7XT75yU9y7bXXLutrL9Z73vMe3vnOd/7w8XXXXZdjNZLawemzkqSVzjCr3FWrVf7h7n1cvC6abttxMgFwdOq7Tbd98Ehqus3p1Go1xsbGALjzzjt5xzveUYjR2SuuuIKenh4mJye55JJLVs0oudQOp/tC7nTBMY/Q6PRZSdJKYJhVIVy8Lvi1n13T1j4//jcnlv01P/nJTzI93Ti3eHp6ulCjs5dccskPw6yk9skrODqqKkla6Qyzyt3U1BSPHU4tCZfzeeBw4nGW9zIqX/rSl57x+Itf/GIhwmytVuMb3/gGAF//+tc5dOjQso0Yr7Rp4lKz/BuUJCkfhllpGaWU5n2cl1aOGFerVe6+ex/rLmi+7clGSUw9uK/ptkcebb4/SZIkrRyGWeWuu7ubo9RymWZ8XvfiLqMy12jkueeey+HDh3/4+Lzzzpt11LEVI4rzjZDu2/fMsHjHHXfw0EMPLVtN6y6An+1fVNNF+5vR+fc/fqhxqZxm/e+jjdvnnNd828cPARc1304LV8bzUyWtLi6+JrWPYVZaRhs3bnxGmL344ovzK2YVW8oCV+OPNT5oPO+i5i9BxUWr5xJUReXCRpKKzGOUtLwMs9IizPeN6a/8yq9w+PBhXvnKVy76XNDlrmnXrl389V//9Q8ft7u2diviJai0PBytkFR0Hqek9lkVYdZpaWqnjRs3cuLECa6++uq8S/mhd7zjHT8Msx0dHcta29TUFIePnH7a73I7/CgwvbwLeEmSJKk8VkWYPR2nfOTvwSOLW8249nhjgaXKOc1fo/bBI4nzFnfK7LzWrFnD5ZdfXojry55SqVQ4//zzOXz4MH19fYWqTcXleV+Sis7jlLS6rYowW8SDlKPFT1vKOYYHs9/Ted3Nn994Xvf8fS/2kjOtvNzMUi6D89RTT9HR0cHk5OSiapurru7ubuh4JJcFoLovbsG3EVoQvwSUVHQep6SVb1WE2TJaTQfgop7fWK1W+fu799F1fnPtIrvczKEHmr/czMHDp6/pnrv3sb7JmgACOOtMePSRu5tue+g0dWllWilfmElauqJ+Ce9xamGKOIJd1L8plYthNif+4yu+qakpFnOV2PPPWXyfKet3LoutCeC8FtalpSviBw1JWqjV9CX8SlPU/3dFrSsPfkaYm2FWz+A/Fi3GkUcXtwDU4481bs85d3F9dq+SKx/5hi6tLkUcsfK9vdyK+P+viDUV8d/e6az2zwiFCrMR8Wrgo8AZwMdTSh/MuSTNsNr+sXR3d/PYkUeabnf48cbtYkZoI+t3vpqOLqImgKNZXYsZoZ2vriVd0/WJxptC98XNn/PcffHKuqZrEd/UJRXTans/looir397fkaYW2HCbEScAfw/wM8D9wPfiIibUkp35VvZ6uI/lqctNig9mn1rt35j8wFt/cb5+11KeHssq+uiRdR10Tx1FfWcZ0kqK9+LpXz4b2/hijKbszBhFngJcCClVAWIiD8FtgCG2VUur38s87VZyqrCK62m+RR1uk5RDsCSJEkrTTtHsIsUZnuA+2Y8vh94aU61qCSKONWqiDVBMeuyJkmSpPIpypf6kdJi10ZdXhHxy8CrU0q/lj3+VeClKaVff9bzrgGuAdi0adOLJyYm2l6rJEmSJKn1IuKbKaXNs+3raHcx85gELp3x+JJs2zOklG5IKW1OKW3u6upqW3GSJEmSpOIoUpj9BnBlRDw/ItYCbwZuyrkmSZIkSVIBFeac2ZRSPSJ+HbidxqV5PplS+l7OZUmSJEmSCqgwYRYgpXQrcGvedUiSJEmSiq1I04wlSZIkSVoQw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQMs5IkSZKk0jHMSpIkSZJKxzArSZIkSSodw6wkSZIkqXQipZR3DYsWEQeBiWV6uQuBR5bptZaLNS2MNS1cEeuypoWxpoUrYl3WtDDWtHBFrMuaFsaaFq6IdVnTwixnTc9LKXXNtqPUYXY5RcTelNLmvOuYyZoWxpoWroh1WdPCWNPCFbEua1oYa1q4ItZlTQtjTQtXxLqsaWHaVZPTjCVJkiRJpWOYlSRJkiSVjmH2aTfkXcAsrGlhrGnhiliXNS2MNS1cEeuypoWxpoUrYl3WtDDWtHBFrMuaFqYtNXnOrCRJkiSpdByZlSRJkiSVzqoPsxHx6oj4+4g4EBHX5V0PQER8MiIejoj9eddySkRcGhFfjIi7IuJ7EfEbBajprIj4ekR8J6vpP+Vd0ykRcUZE/K+IuDnvWgAi4gcR8d2I+HZE7M27HoCIOD8iPh8R90TE3RHxkwWo6cey39Gpn6MR8a4C1PWb2d/4/oj4TEScVYCafiOr53t5/Y5mO1ZGxPqIuCMivp/dXlCQut6Y/a6mI6LtK07OUdOu7N/fvoj4y4g4vwA1/Zesnm9HxGhEdOdd04x9vxURKSIuzLumiPjdiJiccax6bTtrmquubPu27O/qexHxobxriog/m/F7+kFEfLsANb0wIr566j05Il5SgJp+PCL+Lvus8IWIOK/NNc36OTPPY/o8NeV2PJ+npryP53PV1fpjekpp1f4AZwDjQC+wFvgO8M8LUNfPAi8C9uddy4yaNgIvyu6fC/xD3r8rIIBzsvtrgK8BL8v7d5XV825gBLg571qyen4AXJh3Hc+q6Ubg17L7a4Hz867pWfWdATxI49pmedbRA/wj8Jzs8WeBt+Vc0wuA/cBzgU7gr4ErcqjjR46VwIeA67L71wG/V5C6/hnwY8CXgM0Fqakf6Mzu/167f1dz1HTejPv/AfjDvGvKtl8K3E7j2vZtPZbO8Xv6XeDadv8dLaCuf5UdD87MHl+Ud03P2v9h4D/mXRMwCrwmu/9a4EsFqOkbwM9l998B/Jc21zTr58w8j+nz1JTb8XyemvI+ns9VV8uP6at9ZPYlwIGUUjWldBz4U2BLzjWRUvob4FDedcyUUnogpfSt7P5jwN00PmTnWVNKKT2ePVyT/eR+EnhEXAL8AvDxvGspqohYR+PN9BMAKaXjKaXDuRb1o64CxlNKE3kXQiMwPiciOmkEyKmc6/lnwNdSSk+mlOrAl4FfancRcxwrt9D4ooTs9g3trAlmryuldHdK6e/bXcuM/meraTT7/wfwVeCSAtR0dMbDs2nzMX2e99+PAO9pdz1QzM8EMGddW4EPppSeyp7zcAFqAiAiAngT8JkC1JSAUyOf62jzMX2Omv4J8DfZ/TuAf9Pmmub6nJnbMX2umvI8ns9TU97H87nqavkxfbWH2R7gvhmP7yfngFYGEXEZ8BM0RkJzFY3pvN8GHgbuSCnlXhPw32h86JnOuY6ZEjAaEd+MiGvyLgZ4PnAQ+FQ0pmN/PCLOzruoZ3kzbf7QM5uU0iSwG7gXeAA4klIazbcq9gM/ExGViHgujZGFS3Ou6ZQNKaUHsvsPAhvyLKZE3gH8Vd5FAETE9RFxHzAI/McC1LMFmEwpfSfvWp7l17Ppe5/MYzr9HP4JjWPD1yLiyxHxL/MuaIafAR5KKX0/70KAdwG7sr/z3cB78y0HgO/x9IDOG8nxmP6sz5mFOKYX6bPvKfPUlOvx/Nl1tfqYvtrDrJoUEecAfw6861nftuQipXQypfRCGt9AvSQiXpBnPRHxOuDhlNI386xjFj+dUnoR8BrgnRHxsznX00ljitNQSukngCdoTB8qhIhYC7we+FwBarmAxgeM5wPdwNkR8W/zrCmldDeNaUyjwG3At4GTedY0m9SY15T7bI2ii4j3AXVgOO9aAFJK70spXUqjnl/Ps5bsy5odFCBUP8sQcDnwQhpfcn0412qe1gmsB14GbAc+m42IFsFbKMAXlJmtwG9mf+e/STZLKWfvAP6viPgmjWmix/MoYr7PmXkd04v22Rfmrinv4/lsdbX6mL7aw+wkz/zm6ZJsm2YREWto/IEOp5T+Iu96ZsqmqH4ReHXOpfwU8PqI+AGNaet9EfE/8i3ph6N7p6Z8/SWNKfZ5uh+4f8ZI+udphNuieA3wrZTSQ3kXArwS+MeU0sGU0gngL4CX51wTKaVPpJRenFL6WeBRGufHFMFDEbERILtt6zTHsomItwGvAwazD4pFMkybpzrO4nIaXyR9JzuuXwJ8KyIuzrOolNJD2Ze508B/J/9j+in3A3+RnQb0dRozlNq6YNZsslM0fgn4s7xrybyVxrEcGl+a5v7/L6V0T0qpP6X0Yhqhf7zdNczxOTPXY3oRP/vOVVPex/MF/K5ackxf7WH2G8CVEfH8bCTmzcBNOddUSNk3q58A7k4p/de86wGIiK5Tq7VFxHOAnwfuybOmlNJ7U0qXpJQuo/H3NJZSynUULSLOjohzT92nsUhAritlp5QeBO6LiB/LNl0F3JVjSc9WpG/w7wVeFhHPzf4dXkXjXJRcRcRF2e0mGh8SR/Kt6IduovFBkex2T461FFpEvJrGKRGvTyk9mXc9ABFx5YyHW8j/mP7dlNJFKaXLsuP6/TQWOXkwz7pOfbjP/GtyPqbP8D9pLAJFRPwTGov7PZJnQZlXAveklO7Pu5DMFPBz2f0+IPepzzOO6R3A7wB/2Ob+5/qcmdsxvaCffWetKe/j+Tx1tf6YnpZ5Ramy/dA41+sfaHwD9b6868lq+gyNaUMnaLxxXl2Amn6axtSOfTSmFH4beG3ONf0L4H9lNe2nzSsULqC+V1CA1YxprNb9neznewX6O38hsDf7//c/gQvyrimr62ygBqzLu5YZNf0nGm8A+4E/IVspNOeavkLjC4jvAFflVMOPHCuBCnAnjQ+Hfw2sL0hd/zq7/xTwEHB7AWo6QGPdiFPH9HavHDxbTX+e/Z3vA75AYwGRXGt61v4f0P7VjGf7Pf0J8N3s93QTsLGdNc1T11rgf2T/D78F9OVdU7b9j4H/s92/o3l+Tz8NfDM7fn4NeHEBavoNGp+H/wH4IBBtrmnWz5l5HtPnqSm34/k8NeV9PJ+rrpYf0yMrQJIkSZKk0ljt04wlSZIkSSVkmJUkSZIklY5hVpIkSZJUOoZZSZIkSVLpGGYlSZIkSaVjmJUkKUcR8fizHr8tIv4gr3okSSoLw6wkSStQRHTmXYMkSa1kmJUkqaAi4rKIGIuIfRFxZ0Rsyrb/cUT88oznPZ7dviIivhIRNwF35VS2JElt4be2kiTl6zkR8e0Zj9cDN2X3PwbcmFK6MSLeAfw+8IbTvN6LgBeklP5xuQuVJKlIDLOSJOXrf6eUXnjqQUS8DdicPfxJ4Jey+38CfGgBr/d1g6wkaTVwmrEkSeVTJ3sPj4gOYO2MfU/kUpEkSW1mmJUkqbj+Fnhzdn8Q+Ep2/wfAi7P7rwfWtLcsSZLyZ5iVJKm4tgFvj4h9wK8Cv5Ft/+/Az0XEd2hMRXY0VpK06kRKKe8aJEmSJElqiiOzkiRJkqTSMcxKkiRJkkrHMCtJkiRJKh3DrCRJkiSpdAyzkiRJkqTSMcxKkiRJkkrHMCtJkiRJKh3DrCRJkiSpdP5/Uzb6KjJj9bEAAAAASUVORK5CYII="/>

working day에는 출/퇴근 시간에, non working day에는 낮 시간대에 대여수가 증가함을 확인하였다. working day는 자전거 대여수 예측하는데 중요한 column이다.


또한, count의 값이 크기 때문에 log 형식으로 바꾸어주면 정규성을 확보하여 예측 정확도를 높일 수 있다.



```python
sns.displot(np.log(train["count"]))
```

<pre>
<seaborn.axisgrid.FacetGrid at 0x7fd92b4ccc90>
</pre>
<img src="data:image/png;base64,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"/>


```python
train2=train.drop(columns=["datetime","casual","registered","count"])
train2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>Year</th>
      <th>Hour</th>
      <th>Weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>81</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>0</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>1</td>
      <td>5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.02</td>
      <td>13.635</td>
      <td>80</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>2</td>
      <td>5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>3</td>
      <td>5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>9.84</td>
      <td>14.395</td>
      <td>75</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>4</td>
      <td>5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>10881</th>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>15.58</td>
      <td>19.695</td>
      <td>50</td>
      <td>26.0027</td>
      <td>2012</td>
      <td>19</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10882</th>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>14.76</td>
      <td>17.425</td>
      <td>57</td>
      <td>15.0013</td>
      <td>2012</td>
      <td>20</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10883</th>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>15.910</td>
      <td>61</td>
      <td>15.0013</td>
      <td>2012</td>
      <td>21</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10884</th>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.94</td>
      <td>17.425</td>
      <td>61</td>
      <td>6.0032</td>
      <td>2012</td>
      <td>22</td>
      <td>2</td>
    </tr>
    <tr>
      <th>10885</th>
      <td>4</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>13.12</td>
      <td>16.665</td>
      <td>66</td>
      <td>8.9981</td>
      <td>2012</td>
      <td>23</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>10886 rows × 11 columns</p>
</div>



```python
test2=test.drop(columns="datetime")
test2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>season</th>
      <th>holiday</th>
      <th>workingday</th>
      <th>weather</th>
      <th>temp</th>
      <th>atemp</th>
      <th>humidity</th>
      <th>windspeed</th>
      <th>Year</th>
      <th>Hour</th>
      <th>Weekday</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>11.365</td>
      <td>56</td>
      <td>26.0027</td>
      <td>2011</td>
      <td>0</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>1</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>0.0000</td>
      <td>2011</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>3</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>56</td>
      <td>11.0014</td>
      <td>2011</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>19</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>2</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>20</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>12.880</td>
      <td>60</td>
      <td>11.0014</td>
      <td>2012</td>
      <td>21</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>56</td>
      <td>8.9981</td>
      <td>2012</td>
      <td>22</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>1</td>
      <td>0</td>
      <td>1</td>
      <td>1</td>
      <td>10.66</td>
      <td>13.635</td>
      <td>65</td>
      <td>8.9981</td>
      <td>2012</td>
      <td>23</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 11 columns</p>
</div>


GradientBoostingRegressor을 사용하니 predict에 -값이 출력되어 err가 발생하고 출력이 불가능하다.

predict값을 절댓값으로 변환하여 제출하자 score는 0.70437로 동일 조건의 RandomForestRegressor score : 0.42058에 비해 나빠졌음을 알 수 있다.



```python
from sklearn.ensemble import GradientBoostingRegressor
gbr=GradientBoostingRegressor()
gbr.fit(train2,train["count"])
result=gbr.predict(test2)
result=np.absolute(list(result))
result
```

<pre>
array([ 15.65101246,   7.32384145,   2.21763301, ..., 111.68123036,
        82.18822316,  53.21244721])
</pre>
CatBoostRegressor predict값에 -값이 출력되어 err가 발생하고 제출이 되지 않는다.

절댓값을 구하자 score : 0.49252로 동일 조건의 RandomForestRegressor score:0.42058 보다 점수가 나빠짐을 확인하였다.



```python
from catboost import CatBoostRegressor
cbr=CatBoostRegressor()
cbr.fit(train2,train["count"])
result=cbr.predict(test2)
result=np.absolute(list(result))
result
```

<pre>
Learning rate set to 0.059704
0:	learn: 174.3421739	total: 54ms	remaining: 53.9s
1:	learn: 167.9605817	total: 56.5ms	remaining: 28.2s
2:	learn: 162.5859310	total: 59ms	remaining: 19.6s
3:	learn: 156.9690948	total: 61.5ms	remaining: 15.3s
4:	learn: 152.0179996	total: 63.8ms	remaining: 12.7s
5:	learn: 147.2317303	total: 66.5ms	remaining: 11s
6:	learn: 143.1159824	total: 71.6ms	remaining: 10.2s
7:	learn: 139.3371421	total: 74.5ms	remaining: 9.24s
8:	learn: 135.6340091	total: 77ms	remaining: 8.48s
9:	learn: 132.3329481	total: 80ms	remaining: 7.92s
10:	learn: 129.0109257	total: 83ms	remaining: 7.46s
11:	learn: 126.2031835	total: 85.1ms	remaining: 7.01s
12:	learn: 123.8644806	total: 87.1ms	remaining: 6.62s
13:	learn: 121.0820471	total: 89ms	remaining: 6.27s
14:	learn: 118.3263197	total: 90.8ms	remaining: 5.96s
15:	learn: 116.4257971	total: 92.6ms	remaining: 5.69s
16:	learn: 114.2719587	total: 95.4ms	remaining: 5.51s
17:	learn: 112.2549934	total: 97.7ms	remaining: 5.33s
18:	learn: 110.7459312	total: 100ms	remaining: 5.17s
19:	learn: 109.0516095	total: 102ms	remaining: 5.02s
20:	learn: 107.5878098	total: 105ms	remaining: 4.88s
21:	learn: 106.1472604	total: 107ms	remaining: 4.76s
22:	learn: 104.3181280	total: 110ms	remaining: 4.65s
23:	learn: 101.4206618	total: 112ms	remaining: 4.55s
24:	learn: 100.4184633	total: 114ms	remaining: 4.46s
25:	learn: 97.7602534	total: 117ms	remaining: 4.37s
26:	learn: 95.3367669	total: 119ms	remaining: 4.29s
27:	learn: 93.4154542	total: 122ms	remaining: 4.23s
28:	learn: 90.8899394	total: 124ms	remaining: 4.16s
29:	learn: 88.7127694	total: 127ms	remaining: 4.1s
30:	learn: 87.8928152	total: 129ms	remaining: 4.04s
31:	learn: 85.9973572	total: 132ms	remaining: 3.98s
32:	learn: 84.9534122	total: 134ms	remaining: 3.92s
33:	learn: 83.5582102	total: 136ms	remaining: 3.88s
34:	learn: 82.9487776	total: 139ms	remaining: 3.83s
35:	learn: 81.8549586	total: 142ms	remaining: 3.79s
36:	learn: 81.1652732	total: 144ms	remaining: 3.74s
37:	learn: 80.5396414	total: 146ms	remaining: 3.69s
38:	learn: 79.2807449	total: 148ms	remaining: 3.64s
39:	learn: 77.7200649	total: 151ms	remaining: 3.62s
40:	learn: 76.1262127	total: 153ms	remaining: 3.57s
41:	learn: 74.8665515	total: 154ms	remaining: 3.52s
42:	learn: 74.4498257	total: 156ms	remaining: 3.48s
43:	learn: 74.0122704	total: 158ms	remaining: 3.44s
44:	learn: 72.7861639	total: 160ms	remaining: 3.4s
45:	learn: 72.4133948	total: 162ms	remaining: 3.36s
46:	learn: 71.6946197	total: 164ms	remaining: 3.33s
47:	learn: 71.1217956	total: 166ms	remaining: 3.3s
48:	learn: 70.2376547	total: 168ms	remaining: 3.26s
49:	learn: 69.3296119	total: 170ms	remaining: 3.23s
50:	learn: 68.9946743	total: 172ms	remaining: 3.19s
51:	learn: 68.0373640	total: 174ms	remaining: 3.17s
52:	learn: 67.2195356	total: 177ms	remaining: 3.15s
53:	learn: 66.3519970	total: 179ms	remaining: 3.14s
54:	learn: 65.9259663	total: 182ms	remaining: 3.13s
55:	learn: 65.5729299	total: 184ms	remaining: 3.11s
56:	learn: 64.9499531	total: 187ms	remaining: 3.09s
57:	learn: 64.2614540	total: 190ms	remaining: 3.08s
58:	learn: 63.9976034	total: 193ms	remaining: 3.08s
59:	learn: 63.4876860	total: 196ms	remaining: 3.07s
60:	learn: 63.1038785	total: 199ms	remaining: 3.06s
61:	learn: 62.7795440	total: 201ms	remaining: 3.04s
62:	learn: 62.5500839	total: 203ms	remaining: 3.02s
63:	learn: 62.0792900	total: 206ms	remaining: 3.01s
64:	learn: 61.4754967	total: 208ms	remaining: 3s
65:	learn: 61.0872646	total: 212ms	remaining: 3s
66:	learn: 60.9004093	total: 214ms	remaining: 2.98s
67:	learn: 60.4765575	total: 217ms	remaining: 2.97s
68:	learn: 60.3218949	total: 220ms	remaining: 2.96s
69:	learn: 59.8721613	total: 222ms	remaining: 2.95s
70:	learn: 59.4030742	total: 225ms	remaining: 2.94s
71:	learn: 59.2537217	total: 228ms	remaining: 2.93s
72:	learn: 59.0847254	total: 230ms	remaining: 2.92s
73:	learn: 58.9237788	total: 233ms	remaining: 2.91s
74:	learn: 58.7694644	total: 235ms	remaining: 2.9s
75:	learn: 58.5906315	total: 237ms	remaining: 2.89s
76:	learn: 58.3718424	total: 240ms	remaining: 2.88s
77:	learn: 58.0212107	total: 243ms	remaining: 2.87s
78:	learn: 57.4762531	total: 245ms	remaining: 2.85s
79:	learn: 57.3178812	total: 247ms	remaining: 2.85s
80:	learn: 57.0502414	total: 250ms	remaining: 2.83s
81:	learn: 56.8836080	total: 252ms	remaining: 2.82s
82:	learn: 56.3892516	total: 255ms	remaining: 2.81s
83:	learn: 56.1160189	total: 257ms	remaining: 2.8s
84:	learn: 55.9742330	total: 260ms	remaining: 2.8s
85:	learn: 55.6654176	total: 263ms	remaining: 2.79s
86:	learn: 55.1529511	total: 266ms	remaining: 2.79s
87:	learn: 55.0001713	total: 268ms	remaining: 2.78s
88:	learn: 54.7764084	total: 271ms	remaining: 2.77s
89:	learn: 54.7053719	total: 273ms	remaining: 2.76s
90:	learn: 54.5421585	total: 276ms	remaining: 2.75s
91:	learn: 54.1479831	total: 278ms	remaining: 2.75s
92:	learn: 54.0604625	total: 282ms	remaining: 2.75s
93:	learn: 53.7707171	total: 284ms	remaining: 2.74s
94:	learn: 53.4974528	total: 287ms	remaining: 2.74s
95:	learn: 53.3316046	total: 290ms	remaining: 2.73s
96:	learn: 53.0741827	total: 292ms	remaining: 2.72s
97:	learn: 52.9940915	total: 295ms	remaining: 2.71s
98:	learn: 52.6913249	total: 297ms	remaining: 2.7s
99:	learn: 52.5934570	total: 299ms	remaining: 2.69s
100:	learn: 52.4666273	total: 302ms	remaining: 2.69s
101:	learn: 52.3485008	total: 304ms	remaining: 2.68s
102:	learn: 52.2665010	total: 307ms	remaining: 2.67s
103:	learn: 52.0930513	total: 309ms	remaining: 2.66s
104:	learn: 52.0283074	total: 311ms	remaining: 2.65s
105:	learn: 51.8981977	total: 313ms	remaining: 2.64s
106:	learn: 51.7630962	total: 316ms	remaining: 2.63s
107:	learn: 51.6490207	total: 318ms	remaining: 2.62s
108:	learn: 51.4038608	total: 320ms	remaining: 2.62s
109:	learn: 51.3221446	total: 322ms	remaining: 2.61s
110:	learn: 51.2568399	total: 324ms	remaining: 2.6s
111:	learn: 51.1838275	total: 326ms	remaining: 2.59s
112:	learn: 51.0923815	total: 329ms	remaining: 2.58s
113:	learn: 50.8400534	total: 331ms	remaining: 2.58s
114:	learn: 50.7645741	total: 334ms	remaining: 2.57s
115:	learn: 50.6949611	total: 336ms	remaining: 2.56s
116:	learn: 50.4855762	total: 339ms	remaining: 2.56s
117:	learn: 50.2717371	total: 341ms	remaining: 2.55s
118:	learn: 50.1793106	total: 344ms	remaining: 2.54s
119:	learn: 50.1199916	total: 346ms	remaining: 2.54s
120:	learn: 49.9933156	total: 349ms	remaining: 2.53s
121:	learn: 49.9241454	total: 351ms	remaining: 2.53s
122:	learn: 49.8770621	total: 354ms	remaining: 2.52s
123:	learn: 49.7357295	total: 356ms	remaining: 2.52s
124:	learn: 49.6567850	total: 358ms	remaining: 2.51s
125:	learn: 49.5865630	total: 361ms	remaining: 2.5s
126:	learn: 49.4040816	total: 364ms	remaining: 2.5s
127:	learn: 49.2228045	total: 366ms	remaining: 2.49s
128:	learn: 49.0387904	total: 368ms	remaining: 2.49s
129:	learn: 48.9811866	total: 371ms	remaining: 2.48s
130:	learn: 48.8416681	total: 373ms	remaining: 2.47s
131:	learn: 48.7834331	total: 375ms	remaining: 2.46s
132:	learn: 48.7310712	total: 377ms	remaining: 2.46s
133:	learn: 48.6270962	total: 380ms	remaining: 2.45s
134:	learn: 48.5462759	total: 383ms	remaining: 2.45s
135:	learn: 48.3112661	total: 385ms	remaining: 2.45s
136:	learn: 48.2671776	total: 388ms	remaining: 2.44s
137:	learn: 48.2160611	total: 391ms	remaining: 2.44s
138:	learn: 48.0820062	total: 393ms	remaining: 2.44s
139:	learn: 47.9671588	total: 396ms	remaining: 2.43s
140:	learn: 47.9069591	total: 399ms	remaining: 2.43s
141:	learn: 47.8276933	total: 401ms	remaining: 2.42s
142:	learn: 47.7357438	total: 404ms	remaining: 2.42s
143:	learn: 47.6548326	total: 407ms	remaining: 2.42s
144:	learn: 47.5245677	total: 409ms	remaining: 2.41s
145:	learn: 47.4205601	total: 412ms	remaining: 2.41s
146:	learn: 47.2572226	total: 414ms	remaining: 2.4s
147:	learn: 47.1931146	total: 417ms	remaining: 2.4s
148:	learn: 47.1455959	total: 419ms	remaining: 2.39s
149:	learn: 47.0948812	total: 422ms	remaining: 2.39s
150:	learn: 46.9745609	total: 424ms	remaining: 2.39s
151:	learn: 46.9169332	total: 427ms	remaining: 2.38s
152:	learn: 46.8435859	total: 430ms	remaining: 2.38s
153:	learn: 46.7204285	total: 432ms	remaining: 2.37s
154:	learn: 46.6356621	total: 435ms	remaining: 2.37s
155:	learn: 46.5592830	total: 437ms	remaining: 2.37s
156:	learn: 46.4272985	total: 440ms	remaining: 2.36s
157:	learn: 46.3352454	total: 442ms	remaining: 2.36s
158:	learn: 46.2354312	total: 445ms	remaining: 2.35s
159:	learn: 46.1950627	total: 447ms	remaining: 2.35s
160:	learn: 46.1104880	total: 450ms	remaining: 2.34s
161:	learn: 46.0785784	total: 452ms	remaining: 2.34s
162:	learn: 46.0156013	total: 454ms	remaining: 2.33s
163:	learn: 45.9408905	total: 457ms	remaining: 2.33s
164:	learn: 45.9070078	total: 459ms	remaining: 2.32s
165:	learn: 45.7829278	total: 462ms	remaining: 2.32s
166:	learn: 45.6681695	total: 464ms	remaining: 2.32s
167:	learn: 45.5890835	total: 467ms	remaining: 2.31s
168:	learn: 45.5328857	total: 469ms	remaining: 2.31s
169:	learn: 45.4608609	total: 472ms	remaining: 2.3s
170:	learn: 45.3661180	total: 474ms	remaining: 2.3s
171:	learn: 45.2695674	total: 476ms	remaining: 2.29s
172:	learn: 45.1781473	total: 479ms	remaining: 2.29s
173:	learn: 45.1048539	total: 482ms	remaining: 2.29s
174:	learn: 45.0379145	total: 484ms	remaining: 2.28s
175:	learn: 44.9432035	total: 487ms	remaining: 2.28s
176:	learn: 44.8861513	total: 489ms	remaining: 2.27s
177:	learn: 44.7830570	total: 492ms	remaining: 2.27s
178:	learn: 44.6880873	total: 494ms	remaining: 2.27s
179:	learn: 44.6554034	total: 497ms	remaining: 2.26s
180:	learn: 44.6157556	total: 499ms	remaining: 2.26s
181:	learn: 44.5537843	total: 502ms	remaining: 2.25s
182:	learn: 44.5069341	total: 504ms	remaining: 2.25s
183:	learn: 44.4627516	total: 506ms	remaining: 2.25s
184:	learn: 44.4234173	total: 509ms	remaining: 2.24s
185:	learn: 44.2908721	total: 512ms	remaining: 2.24s
186:	learn: 44.2539349	total: 514ms	remaining: 2.23s
187:	learn: 44.1748325	total: 516ms	remaining: 2.23s
188:	learn: 44.1240428	total: 519ms	remaining: 2.23s
189:	learn: 44.0975962	total: 521ms	remaining: 2.22s
190:	learn: 44.0098107	total: 524ms	remaining: 2.22s
191:	learn: 43.9454061	total: 526ms	remaining: 2.21s
192:	learn: 43.8562347	total: 529ms	remaining: 2.21s
193:	learn: 43.7698386	total: 532ms	remaining: 2.21s
194:	learn: 43.7251325	total: 534ms	remaining: 2.2s
195:	learn: 43.6535692	total: 537ms	remaining: 2.2s
196:	learn: 43.5917168	total: 539ms	remaining: 2.2s
197:	learn: 43.5489734	total: 542ms	remaining: 2.19s
198:	learn: 43.5077094	total: 544ms	remaining: 2.19s
199:	learn: 43.4422436	total: 547ms	remaining: 2.19s
200:	learn: 43.3609264	total: 549ms	remaining: 2.18s
201:	learn: 43.2767181	total: 552ms	remaining: 2.18s
202:	learn: 43.2345822	total: 555ms	remaining: 2.18s
203:	learn: 43.1658663	total: 557ms	remaining: 2.17s
204:	learn: 43.1200302	total: 559ms	remaining: 2.17s
205:	learn: 43.0450084	total: 562ms	remaining: 2.17s
206:	learn: 43.0219706	total: 564ms	remaining: 2.16s
207:	learn: 42.9583341	total: 567ms	remaining: 2.16s
208:	learn: 42.9172905	total: 569ms	remaining: 2.15s
209:	learn: 42.8789265	total: 572ms	remaining: 2.15s
210:	learn: 42.8522614	total: 575ms	remaining: 2.15s
211:	learn: 42.8086893	total: 579ms	remaining: 2.15s
212:	learn: 42.7629431	total: 581ms	remaining: 2.15s
213:	learn: 42.7184977	total: 583ms	remaining: 2.14s
214:	learn: 42.6787318	total: 586ms	remaining: 2.14s
215:	learn: 42.6377593	total: 588ms	remaining: 2.13s
216:	learn: 42.5818978	total: 591ms	remaining: 2.13s
217:	learn: 42.5411824	total: 593ms	remaining: 2.13s
218:	learn: 42.4886937	total: 595ms	remaining: 2.12s
219:	learn: 42.4492608	total: 597ms	remaining: 2.12s
220:	learn: 42.3978449	total: 600ms	remaining: 2.11s
221:	learn: 42.3583890	total: 602ms	remaining: 2.11s
222:	learn: 42.3282915	total: 605ms	remaining: 2.11s
223:	learn: 42.2981947	total: 608ms	remaining: 2.1s
224:	learn: 42.2325679	total: 610ms	remaining: 2.1s
225:	learn: 42.1728346	total: 613ms	remaining: 2.1s
226:	learn: 42.1380515	total: 615ms	remaining: 2.09s
227:	learn: 42.1030195	total: 618ms	remaining: 2.09s
228:	learn: 42.0737936	total: 620ms	remaining: 2.09s
229:	learn: 42.0362801	total: 622ms	remaining: 2.08s
230:	learn: 42.0053306	total: 625ms	remaining: 2.08s
231:	learn: 41.9838047	total: 628ms	remaining: 2.08s
232:	learn: 41.8994401	total: 630ms	remaining: 2.07s
233:	learn: 41.8639750	total: 632ms	remaining: 2.07s
234:	learn: 41.8480149	total: 635ms	remaining: 2.06s
235:	learn: 41.8037655	total: 637ms	remaining: 2.06s
236:	learn: 41.7748084	total: 639ms	remaining: 2.06s
237:	learn: 41.7270506	total: 641ms	remaining: 2.05s
238:	learn: 41.6926289	total: 644ms	remaining: 2.05s
239:	learn: 41.6713644	total: 647ms	remaining: 2.05s
240:	learn: 41.6407441	total: 649ms	remaining: 2.04s
241:	learn: 41.5721768	total: 651ms	remaining: 2.04s
242:	learn: 41.5561597	total: 654ms	remaining: 2.04s
243:	learn: 41.5002000	total: 656ms	remaining: 2.03s
244:	learn: 41.4776598	total: 659ms	remaining: 2.03s
245:	learn: 41.4265086	total: 661ms	remaining: 2.03s
246:	learn: 41.4052566	total: 664ms	remaining: 2.02s
247:	learn: 41.3815652	total: 666ms	remaining: 2.02s
248:	learn: 41.3071521	total: 668ms	remaining: 2.02s
249:	learn: 41.2610545	total: 671ms	remaining: 2.01s
250:	learn: 41.2361298	total: 673ms	remaining: 2.01s
251:	learn: 41.2118099	total: 676ms	remaining: 2.01s
252:	learn: 41.1634834	total: 679ms	remaining: 2s
253:	learn: 41.1129739	total: 682ms	remaining: 2s
254:	learn: 41.0705325	total: 684ms	remaining: 2s
255:	learn: 41.0337595	total: 687ms	remaining: 2s
256:	learn: 41.0140248	total: 689ms	remaining: 1.99s
257:	learn: 40.9837504	total: 692ms	remaining: 1.99s
258:	learn: 40.9259833	total: 695ms	remaining: 1.99s
259:	learn: 40.9009125	total: 697ms	remaining: 1.98s
260:	learn: 40.8658965	total: 700ms	remaining: 1.98s
261:	learn: 40.8399136	total: 702ms	remaining: 1.98s
262:	learn: 40.7810561	total: 705ms	remaining: 1.98s
263:	learn: 40.7326070	total: 708ms	remaining: 1.97s
264:	learn: 40.7023473	total: 710ms	remaining: 1.97s
265:	learn: 40.6714086	total: 713ms	remaining: 1.97s
266:	learn: 40.6370562	total: 715ms	remaining: 1.96s
267:	learn: 40.5974886	total: 718ms	remaining: 1.96s
268:	learn: 40.5808735	total: 720ms	remaining: 1.96s
269:	learn: 40.5509996	total: 723ms	remaining: 1.95s
270:	learn: 40.5298588	total: 725ms	remaining: 1.95s
271:	learn: 40.5095339	total: 728ms	remaining: 1.95s
272:	learn: 40.4857348	total: 730ms	remaining: 1.94s
273:	learn: 40.4631354	total: 733ms	remaining: 1.94s
274:	learn: 40.4355668	total: 735ms	remaining: 1.94s
275:	learn: 40.3882960	total: 738ms	remaining: 1.94s
276:	learn: 40.3583405	total: 740ms	remaining: 1.93s
277:	learn: 40.3286484	total: 743ms	remaining: 1.93s
278:	learn: 40.2874262	total: 746ms	remaining: 1.93s
279:	learn: 40.2541318	total: 748ms	remaining: 1.92s
280:	learn: 40.2216128	total: 750ms	remaining: 1.92s
281:	learn: 40.1738362	total: 753ms	remaining: 1.92s
282:	learn: 40.1143740	total: 756ms	remaining: 1.91s
283:	learn: 40.0834560	total: 758ms	remaining: 1.91s
284:	learn: 40.0618616	total: 760ms	remaining: 1.91s
285:	learn: 40.0344995	total: 763ms	remaining: 1.91s
286:	learn: 40.0022773	total: 767ms	remaining: 1.91s
287:	learn: 39.9681430	total: 770ms	remaining: 1.9s
288:	learn: 39.9130239	total: 773ms	remaining: 1.9s
289:	learn: 39.8913485	total: 775ms	remaining: 1.9s
290:	learn: 39.8611509	total: 778ms	remaining: 1.9s
291:	learn: 39.8321109	total: 781ms	remaining: 1.89s
292:	learn: 39.8080258	total: 783ms	remaining: 1.89s
293:	learn: 39.7797034	total: 786ms	remaining: 1.89s
294:	learn: 39.7507708	total: 789ms	remaining: 1.89s
295:	learn: 39.7264385	total: 792ms	remaining: 1.88s
296:	learn: 39.6681395	total: 794ms	remaining: 1.88s
297:	learn: 39.6332546	total: 797ms	remaining: 1.88s
298:	learn: 39.5991548	total: 800ms	remaining: 1.87s
299:	learn: 39.5770635	total: 802ms	remaining: 1.87s
300:	learn: 39.5613471	total: 805ms	remaining: 1.87s
301:	learn: 39.5118340	total: 807ms	remaining: 1.86s
302:	learn: 39.4891429	total: 810ms	remaining: 1.86s
303:	learn: 39.4659550	total: 812ms	remaining: 1.86s
304:	learn: 39.4310798	total: 815ms	remaining: 1.86s
305:	learn: 39.3877905	total: 817ms	remaining: 1.85s
306:	learn: 39.3610975	total: 820ms	remaining: 1.85s
307:	learn: 39.3077652	total: 822ms	remaining: 1.85s
308:	learn: 39.2833555	total: 826ms	remaining: 1.85s
309:	learn: 39.2648442	total: 828ms	remaining: 1.84s
310:	learn: 39.2402000	total: 831ms	remaining: 1.84s
311:	learn: 39.2011794	total: 833ms	remaining: 1.84s
312:	learn: 39.1799674	total: 836ms	remaining: 1.83s
313:	learn: 39.1622564	total: 837ms	remaining: 1.83s
314:	learn: 39.1236637	total: 840ms	remaining: 1.83s
315:	learn: 39.1140097	total: 843ms	remaining: 1.82s
316:	learn: 39.0974940	total: 845ms	remaining: 1.82s
317:	learn: 39.0655505	total: 847ms	remaining: 1.82s
318:	learn: 39.0351762	total: 850ms	remaining: 1.81s
319:	learn: 39.0010473	total: 852ms	remaining: 1.81s
320:	learn: 38.9854193	total: 855ms	remaining: 1.81s
321:	learn: 38.9679814	total: 857ms	remaining: 1.8s
322:	learn: 38.9477349	total: 860ms	remaining: 1.8s
323:	learn: 38.9305927	total: 863ms	remaining: 1.8s
324:	learn: 38.8872875	total: 865ms	remaining: 1.8s
325:	learn: 38.8581123	total: 867ms	remaining: 1.79s
326:	learn: 38.8445837	total: 870ms	remaining: 1.79s
327:	learn: 38.8165503	total: 872ms	remaining: 1.79s
328:	learn: 38.7895058	total: 875ms	remaining: 1.78s
329:	learn: 38.7547187	total: 877ms	remaining: 1.78s
330:	learn: 38.7341697	total: 880ms	remaining: 1.78s
331:	learn: 38.7135019	total: 882ms	remaining: 1.77s
332:	learn: 38.6813813	total: 885ms	remaining: 1.77s
333:	learn: 38.6541331	total: 888ms	remaining: 1.77s
334:	learn: 38.6315274	total: 890ms	remaining: 1.77s
335:	learn: 38.6205266	total: 893ms	remaining: 1.76s
336:	learn: 38.5887336	total: 895ms	remaining: 1.76s
337:	learn: 38.5650211	total: 897ms	remaining: 1.76s
338:	learn: 38.5429965	total: 900ms	remaining: 1.75s
339:	learn: 38.5079110	total: 903ms	remaining: 1.75s
340:	learn: 38.4780915	total: 905ms	remaining: 1.75s
341:	learn: 38.4477957	total: 908ms	remaining: 1.75s
342:	learn: 38.4149784	total: 910ms	remaining: 1.74s
343:	learn: 38.3921450	total: 913ms	remaining: 1.74s
344:	learn: 38.3749830	total: 915ms	remaining: 1.74s
345:	learn: 38.3603210	total: 917ms	remaining: 1.73s
346:	learn: 38.3348078	total: 920ms	remaining: 1.73s
347:	learn: 38.3188732	total: 922ms	remaining: 1.73s
348:	learn: 38.2718692	total: 925ms	remaining: 1.73s
349:	learn: 38.2512986	total: 927ms	remaining: 1.72s
350:	learn: 38.2312705	total: 930ms	remaining: 1.72s
351:	learn: 38.2156655	total: 932ms	remaining: 1.72s
352:	learn: 38.1821667	total: 934ms	remaining: 1.71s
353:	learn: 38.1357596	total: 937ms	remaining: 1.71s
354:	learn: 38.1150390	total: 939ms	remaining: 1.71s
355:	learn: 38.0920243	total: 942ms	remaining: 1.7s
356:	learn: 38.0701988	total: 944ms	remaining: 1.7s
357:	learn: 38.0275987	total: 947ms	remaining: 1.7s
358:	learn: 37.9853742	total: 949ms	remaining: 1.7s
359:	learn: 37.9627841	total: 952ms	remaining: 1.69s
360:	learn: 37.9455826	total: 956ms	remaining: 1.69s
361:	learn: 37.9135476	total: 959ms	remaining: 1.69s
362:	learn: 37.8955017	total: 962ms	remaining: 1.69s
363:	learn: 37.8784017	total: 964ms	remaining: 1.68s
364:	learn: 37.8541633	total: 967ms	remaining: 1.68s
365:	learn: 37.8197428	total: 970ms	remaining: 1.68s
366:	learn: 37.8039385	total: 972ms	remaining: 1.68s
367:	learn: 37.7886157	total: 975ms	remaining: 1.67s
368:	learn: 37.7771108	total: 977ms	remaining: 1.67s
369:	learn: 37.7516780	total: 979ms	remaining: 1.67s
370:	learn: 37.7361632	total: 982ms	remaining: 1.66s
371:	learn: 37.7115584	total: 985ms	remaining: 1.66s
372:	learn: 37.6929868	total: 987ms	remaining: 1.66s
373:	learn: 37.6789585	total: 990ms	remaining: 1.66s
374:	learn: 37.6579425	total: 992ms	remaining: 1.65s
375:	learn: 37.6370943	total: 995ms	remaining: 1.65s
376:	learn: 37.6044204	total: 997ms	remaining: 1.65s
377:	learn: 37.5824054	total: 1000ms	remaining: 1.64s
378:	learn: 37.5653336	total: 1s	remaining: 1.64s
379:	learn: 37.5494345	total: 1s	remaining: 1.64s
380:	learn: 37.5370757	total: 1.01s	remaining: 1.64s
381:	learn: 37.5137906	total: 1.01s	remaining: 1.63s
382:	learn: 37.4907904	total: 1.01s	remaining: 1.63s
383:	learn: 37.4517392	total: 1.01s	remaining: 1.63s
384:	learn: 37.4365897	total: 1.01s	remaining: 1.62s
385:	learn: 37.4222542	total: 1.02s	remaining: 1.62s
386:	learn: 37.3991897	total: 1.02s	remaining: 1.62s
387:	learn: 37.3735010	total: 1.02s	remaining: 1.61s
388:	learn: 37.3438633	total: 1.02s	remaining: 1.61s
389:	learn: 37.3298981	total: 1.03s	remaining: 1.61s
390:	learn: 37.3062649	total: 1.03s	remaining: 1.6s
391:	learn: 37.2800866	total: 1.03s	remaining: 1.6s
392:	learn: 37.2654086	total: 1.03s	remaining: 1.6s
393:	learn: 37.2561476	total: 1.04s	remaining: 1.6s
394:	learn: 37.2425767	total: 1.04s	remaining: 1.59s
395:	learn: 37.2228948	total: 1.04s	remaining: 1.59s
396:	learn: 37.1879177	total: 1.04s	remaining: 1.59s
397:	learn: 37.1711301	total: 1.05s	remaining: 1.58s
398:	learn: 37.1580796	total: 1.05s	remaining: 1.58s
399:	learn: 37.1386039	total: 1.05s	remaining: 1.58s
400:	learn: 37.1137850	total: 1.05s	remaining: 1.58s
401:	learn: 37.0974772	total: 1.06s	remaining: 1.57s
402:	learn: 37.0831008	total: 1.06s	remaining: 1.57s
403:	learn: 37.0618699	total: 1.06s	remaining: 1.57s
404:	learn: 37.0472032	total: 1.06s	remaining: 1.56s
405:	learn: 37.0255606	total: 1.07s	remaining: 1.56s
406:	learn: 37.0074740	total: 1.07s	remaining: 1.56s
407:	learn: 36.9885843	total: 1.07s	remaining: 1.56s
408:	learn: 36.9766391	total: 1.07s	remaining: 1.55s
409:	learn: 36.9549453	total: 1.08s	remaining: 1.55s
410:	learn: 36.9359867	total: 1.08s	remaining: 1.55s
411:	learn: 36.9203447	total: 1.08s	remaining: 1.54s
412:	learn: 36.9074434	total: 1.08s	remaining: 1.54s
413:	learn: 36.8836718	total: 1.09s	remaining: 1.54s
414:	learn: 36.8642444	total: 1.09s	remaining: 1.54s
415:	learn: 36.8514231	total: 1.09s	remaining: 1.53s
416:	learn: 36.7999608	total: 1.09s	remaining: 1.53s
417:	learn: 36.7735944	total: 1.1s	remaining: 1.53s
418:	learn: 36.7598345	total: 1.1s	remaining: 1.52s
419:	learn: 36.7364967	total: 1.1s	remaining: 1.52s
420:	learn: 36.7103995	total: 1.1s	remaining: 1.52s
421:	learn: 36.6613127	total: 1.11s	remaining: 1.52s
422:	learn: 36.6527219	total: 1.11s	remaining: 1.51s
423:	learn: 36.6284055	total: 1.11s	remaining: 1.51s
424:	learn: 36.6086553	total: 1.11s	remaining: 1.51s
425:	learn: 36.5833794	total: 1.12s	remaining: 1.5s
426:	learn: 36.5700711	total: 1.12s	remaining: 1.5s
427:	learn: 36.5530839	total: 1.12s	remaining: 1.5s
428:	learn: 36.5408273	total: 1.12s	remaining: 1.5s
429:	learn: 36.5326558	total: 1.13s	remaining: 1.49s
430:	learn: 36.5167609	total: 1.13s	remaining: 1.49s
431:	learn: 36.4988524	total: 1.13s	remaining: 1.49s
432:	learn: 36.4762393	total: 1.13s	remaining: 1.48s
433:	learn: 36.4423929	total: 1.14s	remaining: 1.48s
434:	learn: 36.4191744	total: 1.14s	remaining: 1.48s
435:	learn: 36.4040353	total: 1.14s	remaining: 1.48s
436:	learn: 36.3910287	total: 1.14s	remaining: 1.47s
437:	learn: 36.3608250	total: 1.15s	remaining: 1.47s
438:	learn: 36.3392498	total: 1.15s	remaining: 1.47s
439:	learn: 36.3290231	total: 1.15s	remaining: 1.47s
440:	learn: 36.3201108	total: 1.16s	remaining: 1.47s
441:	learn: 36.3007180	total: 1.16s	remaining: 1.46s
442:	learn: 36.2785617	total: 1.16s	remaining: 1.46s
443:	learn: 36.2610386	total: 1.16s	remaining: 1.46s
444:	learn: 36.2405690	total: 1.17s	remaining: 1.46s
445:	learn: 36.2171957	total: 1.17s	remaining: 1.45s
446:	learn: 36.1936219	total: 1.17s	remaining: 1.45s
447:	learn: 36.1762932	total: 1.18s	remaining: 1.45s
448:	learn: 36.1569014	total: 1.18s	remaining: 1.45s
449:	learn: 36.1483729	total: 1.18s	remaining: 1.44s
450:	learn: 36.1279230	total: 1.18s	remaining: 1.44s
451:	learn: 36.1152930	total: 1.19s	remaining: 1.44s
452:	learn: 36.0971186	total: 1.19s	remaining: 1.44s
453:	learn: 36.0764943	total: 1.19s	remaining: 1.43s
454:	learn: 36.0439275	total: 1.19s	remaining: 1.43s
455:	learn: 36.0297108	total: 1.2s	remaining: 1.43s
456:	learn: 36.0061081	total: 1.2s	remaining: 1.43s
457:	learn: 35.9964252	total: 1.2s	remaining: 1.42s
458:	learn: 35.9837191	total: 1.2s	remaining: 1.42s
459:	learn: 35.9730176	total: 1.21s	remaining: 1.42s
460:	learn: 35.9457647	total: 1.21s	remaining: 1.42s
461:	learn: 35.9236252	total: 1.21s	remaining: 1.41s
462:	learn: 35.9150603	total: 1.22s	remaining: 1.41s
463:	learn: 35.8983486	total: 1.22s	remaining: 1.41s
464:	learn: 35.8783254	total: 1.22s	remaining: 1.41s
465:	learn: 35.8654882	total: 1.22s	remaining: 1.4s
466:	learn: 35.8516038	total: 1.23s	remaining: 1.4s
467:	learn: 35.8392216	total: 1.23s	remaining: 1.4s
468:	learn: 35.8216070	total: 1.23s	remaining: 1.4s
469:	learn: 35.8165681	total: 1.23s	remaining: 1.39s
470:	learn: 35.8077272	total: 1.24s	remaining: 1.39s
471:	learn: 35.7939293	total: 1.24s	remaining: 1.39s
472:	learn: 35.7690320	total: 1.24s	remaining: 1.38s
473:	learn: 35.7556038	total: 1.24s	remaining: 1.38s
474:	learn: 35.7400883	total: 1.25s	remaining: 1.38s
475:	learn: 35.7238783	total: 1.25s	remaining: 1.38s
476:	learn: 35.6984264	total: 1.25s	remaining: 1.37s
477:	learn: 35.6878096	total: 1.25s	remaining: 1.37s
478:	learn: 35.6874336	total: 1.26s	remaining: 1.37s
479:	learn: 35.6758459	total: 1.26s	remaining: 1.36s
480:	learn: 35.6675804	total: 1.26s	remaining: 1.36s
481:	learn: 35.6493962	total: 1.26s	remaining: 1.36s
482:	learn: 35.6377837	total: 1.27s	remaining: 1.35s
483:	learn: 35.6200633	total: 1.27s	remaining: 1.35s
484:	learn: 35.6114975	total: 1.27s	remaining: 1.35s
485:	learn: 35.5941159	total: 1.27s	remaining: 1.35s
486:	learn: 35.5717082	total: 1.28s	remaining: 1.34s
487:	learn: 35.5595316	total: 1.28s	remaining: 1.34s
488:	learn: 35.5399459	total: 1.28s	remaining: 1.34s
489:	learn: 35.5329643	total: 1.28s	remaining: 1.34s
490:	learn: 35.5161584	total: 1.29s	remaining: 1.33s
491:	learn: 35.5003294	total: 1.29s	remaining: 1.33s
492:	learn: 35.4792372	total: 1.29s	remaining: 1.33s
493:	learn: 35.4634237	total: 1.29s	remaining: 1.33s
494:	learn: 35.4480975	total: 1.3s	remaining: 1.32s
495:	learn: 35.4313619	total: 1.3s	remaining: 1.32s
496:	learn: 35.4093122	total: 1.3s	remaining: 1.32s
497:	learn: 35.3926106	total: 1.3s	remaining: 1.31s
498:	learn: 35.3831047	total: 1.31s	remaining: 1.31s
499:	learn: 35.3676184	total: 1.31s	remaining: 1.31s
500:	learn: 35.3546592	total: 1.31s	remaining: 1.31s
501:	learn: 35.3543165	total: 1.31s	remaining: 1.3s
502:	learn: 35.3381849	total: 1.32s	remaining: 1.3s
503:	learn: 35.3238984	total: 1.32s	remaining: 1.3s
504:	learn: 35.3087185	total: 1.32s	remaining: 1.3s
505:	learn: 35.2984837	total: 1.33s	remaining: 1.29s
506:	learn: 35.2886679	total: 1.33s	remaining: 1.29s
507:	learn: 35.2736777	total: 1.33s	remaining: 1.29s
508:	learn: 35.2525069	total: 1.34s	remaining: 1.29s
509:	learn: 35.2291990	total: 1.34s	remaining: 1.29s
510:	learn: 35.2094022	total: 1.34s	remaining: 1.28s
511:	learn: 35.1993064	total: 1.34s	remaining: 1.28s
512:	learn: 35.1799128	total: 1.35s	remaining: 1.28s
513:	learn: 35.1609368	total: 1.35s	remaining: 1.28s
514:	learn: 35.1353929	total: 1.35s	remaining: 1.27s
515:	learn: 35.1215955	total: 1.35s	remaining: 1.27s
516:	learn: 35.1154491	total: 1.36s	remaining: 1.27s
517:	learn: 35.0979666	total: 1.36s	remaining: 1.26s
518:	learn: 35.0850909	total: 1.36s	remaining: 1.26s
519:	learn: 35.0603282	total: 1.36s	remaining: 1.26s
520:	learn: 35.0478506	total: 1.37s	remaining: 1.26s
521:	learn: 35.0366809	total: 1.37s	remaining: 1.25s
522:	learn: 35.0207311	total: 1.37s	remaining: 1.25s
523:	learn: 35.0107146	total: 1.38s	remaining: 1.25s
524:	learn: 34.9992185	total: 1.38s	remaining: 1.25s
525:	learn: 34.9844082	total: 1.38s	remaining: 1.24s
526:	learn: 34.9673076	total: 1.38s	remaining: 1.24s
527:	learn: 34.9449839	total: 1.39s	remaining: 1.24s
528:	learn: 34.9337450	total: 1.39s	remaining: 1.24s
529:	learn: 34.9109249	total: 1.39s	remaining: 1.23s
530:	learn: 34.9106212	total: 1.39s	remaining: 1.23s
531:	learn: 34.8925946	total: 1.4s	remaining: 1.23s
532:	learn: 34.8842077	total: 1.4s	remaining: 1.22s
533:	learn: 34.8694270	total: 1.4s	remaining: 1.22s
534:	learn: 34.8555774	total: 1.4s	remaining: 1.22s
535:	learn: 34.8473792	total: 1.4s	remaining: 1.22s
536:	learn: 34.8328655	total: 1.41s	remaining: 1.21s
537:	learn: 34.8234701	total: 1.41s	remaining: 1.21s
538:	learn: 34.8088777	total: 1.41s	remaining: 1.21s
539:	learn: 34.7971226	total: 1.41s	remaining: 1.2s
540:	learn: 34.7838020	total: 1.42s	remaining: 1.2s
541:	learn: 34.7709084	total: 1.42s	remaining: 1.2s
542:	learn: 34.7524674	total: 1.42s	remaining: 1.2s
543:	learn: 34.7460790	total: 1.42s	remaining: 1.19s
544:	learn: 34.7401342	total: 1.43s	remaining: 1.19s
545:	learn: 34.7185199	total: 1.43s	remaining: 1.19s
546:	learn: 34.7103871	total: 1.43s	remaining: 1.19s
547:	learn: 34.6937918	total: 1.43s	remaining: 1.18s
548:	learn: 34.6784300	total: 1.44s	remaining: 1.18s
549:	learn: 34.6745631	total: 1.44s	remaining: 1.18s
550:	learn: 34.6639148	total: 1.44s	remaining: 1.17s
551:	learn: 34.6585786	total: 1.44s	remaining: 1.17s
552:	learn: 34.6485753	total: 1.45s	remaining: 1.17s
553:	learn: 34.6356509	total: 1.45s	remaining: 1.17s
554:	learn: 34.6259358	total: 1.45s	remaining: 1.16s
555:	learn: 34.6215839	total: 1.45s	remaining: 1.16s
556:	learn: 34.6108578	total: 1.46s	remaining: 1.16s
557:	learn: 34.5970643	total: 1.46s	remaining: 1.16s
558:	learn: 34.5781794	total: 1.46s	remaining: 1.15s
559:	learn: 34.5742874	total: 1.46s	remaining: 1.15s
560:	learn: 34.5572298	total: 1.47s	remaining: 1.15s
561:	learn: 34.5505242	total: 1.47s	remaining: 1.14s
562:	learn: 34.5383740	total: 1.47s	remaining: 1.14s
563:	learn: 34.5197173	total: 1.47s	remaining: 1.14s
564:	learn: 34.4909358	total: 1.48s	remaining: 1.14s
565:	learn: 34.4832509	total: 1.48s	remaining: 1.13s
566:	learn: 34.4621332	total: 1.48s	remaining: 1.13s
567:	learn: 34.4525779	total: 1.48s	remaining: 1.13s
568:	learn: 34.4438336	total: 1.49s	remaining: 1.13s
569:	learn: 34.4290627	total: 1.49s	remaining: 1.12s
570:	learn: 34.4130899	total: 1.49s	remaining: 1.12s
571:	learn: 34.4017102	total: 1.49s	remaining: 1.12s
572:	learn: 34.3938299	total: 1.5s	remaining: 1.11s
573:	learn: 34.3792118	total: 1.5s	remaining: 1.11s
574:	learn: 34.3629373	total: 1.5s	remaining: 1.11s
575:	learn: 34.3436293	total: 1.5s	remaining: 1.1s
576:	learn: 34.3378178	total: 1.5s	remaining: 1.1s
577:	learn: 34.3290507	total: 1.51s	remaining: 1.1s
578:	learn: 34.3200021	total: 1.51s	remaining: 1.1s
579:	learn: 34.3054007	total: 1.51s	remaining: 1.09s
580:	learn: 34.2969724	total: 1.51s	remaining: 1.09s
581:	learn: 34.2884391	total: 1.52s	remaining: 1.09s
582:	learn: 34.2746076	total: 1.52s	remaining: 1.09s
583:	learn: 34.2582571	total: 1.52s	remaining: 1.08s
584:	learn: 34.2385542	total: 1.52s	remaining: 1.08s
585:	learn: 34.2377040	total: 1.52s	remaining: 1.08s
586:	learn: 34.2282073	total: 1.53s	remaining: 1.07s
587:	learn: 34.2189744	total: 1.53s	remaining: 1.07s
588:	learn: 34.2061698	total: 1.53s	remaining: 1.07s
589:	learn: 34.2004105	total: 1.54s	remaining: 1.07s
590:	learn: 34.1868656	total: 1.54s	remaining: 1.06s
591:	learn: 34.1742569	total: 1.54s	remaining: 1.06s
592:	learn: 34.1583900	total: 1.54s	remaining: 1.06s
593:	learn: 34.1510775	total: 1.55s	remaining: 1.06s
594:	learn: 34.1508484	total: 1.55s	remaining: 1.05s
595:	learn: 34.1410967	total: 1.55s	remaining: 1.05s
596:	learn: 34.1294376	total: 1.55s	remaining: 1.05s
597:	learn: 34.1244658	total: 1.55s	remaining: 1.04s
598:	learn: 34.1139530	total: 1.56s	remaining: 1.04s
599:	learn: 34.1005026	total: 1.56s	remaining: 1.04s
600:	learn: 34.0842126	total: 1.56s	remaining: 1.04s
601:	learn: 34.0627495	total: 1.56s	remaining: 1.03s
602:	learn: 34.0449369	total: 1.57s	remaining: 1.03s
603:	learn: 34.0344625	total: 1.57s	remaining: 1.03s
604:	learn: 34.0257913	total: 1.57s	remaining: 1.03s
605:	learn: 34.0106700	total: 1.57s	remaining: 1.02s
606:	learn: 33.9943200	total: 1.58s	remaining: 1.02s
607:	learn: 33.9823819	total: 1.58s	remaining: 1.02s
608:	learn: 33.9783045	total: 1.58s	remaining: 1.02s
609:	learn: 33.9651644	total: 1.58s	remaining: 1.01s
610:	learn: 33.9501994	total: 1.59s	remaining: 1.01s
611:	learn: 33.9413750	total: 1.59s	remaining: 1.01s
612:	learn: 33.9229056	total: 1.59s	remaining: 1.01s
613:	learn: 33.9151489	total: 1.6s	remaining: 1s
614:	learn: 33.9077713	total: 1.6s	remaining: 1s
615:	learn: 33.8894510	total: 1.6s	remaining: 998ms
616:	learn: 33.8758547	total: 1.6s	remaining: 996ms
617:	learn: 33.8702635	total: 1.61s	remaining: 993ms
618:	learn: 33.8637970	total: 1.61s	remaining: 990ms
619:	learn: 33.8430391	total: 1.61s	remaining: 987ms
620:	learn: 33.8260145	total: 1.61s	remaining: 985ms
621:	learn: 33.8134566	total: 1.62s	remaining: 982ms
622:	learn: 33.7970410	total: 1.62s	remaining: 980ms
623:	learn: 33.7909762	total: 1.62s	remaining: 977ms
624:	learn: 33.7754601	total: 1.62s	remaining: 975ms
625:	learn: 33.7606656	total: 1.63s	remaining: 972ms
626:	learn: 33.7499197	total: 1.63s	remaining: 969ms
627:	learn: 33.7384201	total: 1.63s	remaining: 967ms
628:	learn: 33.7319165	total: 1.63s	remaining: 964ms
629:	learn: 33.7192383	total: 1.64s	remaining: 962ms
630:	learn: 33.7041018	total: 1.64s	remaining: 959ms
631:	learn: 33.6977264	total: 1.64s	remaining: 956ms
632:	learn: 33.6864752	total: 1.64s	remaining: 954ms
633:	learn: 33.6761094	total: 1.65s	remaining: 951ms
634:	learn: 33.6704074	total: 1.65s	remaining: 948ms
635:	learn: 33.6611965	total: 1.65s	remaining: 946ms
636:	learn: 33.6413997	total: 1.65s	remaining: 943ms
637:	learn: 33.6342495	total: 1.66s	remaining: 941ms
638:	learn: 33.6209797	total: 1.66s	remaining: 938ms
639:	learn: 33.6155005	total: 1.66s	remaining: 935ms
640:	learn: 33.6043701	total: 1.67s	remaining: 933ms
641:	learn: 33.5975912	total: 1.67s	remaining: 930ms
642:	learn: 33.5923472	total: 1.67s	remaining: 927ms
643:	learn: 33.5731317	total: 1.67s	remaining: 925ms
644:	learn: 33.5532860	total: 1.68s	remaining: 922ms
645:	learn: 33.5496907	total: 1.68s	remaining: 919ms
646:	learn: 33.5398728	total: 1.68s	remaining: 917ms
647:	learn: 33.5327223	total: 1.68s	remaining: 914ms
648:	learn: 33.5325203	total: 1.69s	remaining: 911ms
649:	learn: 33.5214701	total: 1.69s	remaining: 909ms
650:	learn: 33.5073387	total: 1.69s	remaining: 906ms
651:	learn: 33.4837816	total: 1.69s	remaining: 904ms
652:	learn: 33.4683365	total: 1.7s	remaining: 901ms
653:	learn: 33.4575954	total: 1.7s	remaining: 898ms
654:	learn: 33.4498384	total: 1.7s	remaining: 896ms
655:	learn: 33.4408530	total: 1.7s	remaining: 893ms
656:	learn: 33.4289708	total: 1.71s	remaining: 890ms
...
999:	learn: 30.4092078	total: 2.56s	remaining: 0us
</pre>
<pre>
array([ 20.10567644,   0.83930807,   3.77110868, ..., 112.30901916,
        78.70384289,  30.1806374 ])
</pre>
LinearRegression 적용하자 -값이 반환되어 제출이 불가능하다.

절댓값으로 적용하였다. score 1.21132로 가장 낮은 score가 되었다. 

선형 모델은 다른 GBDT나 CATBOOST 모델에 비해 성능이 낮다.

특징값의 범위가 균일하지 않으면 정규화의 효과가 특징에 따라 달라지믈 학습이 진행되지 않을 수 있음==>count값이 균일하지 않으므로 적합하지 않은 모델

상호작용을 나타내는 특징을 일부러 만들거나 최댓값/최솟값을 제한하거나 구간분할을 하거나 그들을 조합하는 등 다양한 변환이나 처리.



```python
from sklearn.linear_model import LinearRegression
lr=LinearRegression()
lr.fit(train2,train["count"])
result=lr.predict(test2)
result=np.absolute(list(result))
result
```

<pre>
array([ 23.27179232,  20.84936197,  13.04580719, ..., 209.84495832,
       227.95174821, 217.86201958])
</pre>
LogisticRegression을 이용하자 -값은 없으나 predict값이 모두 1로 나오며 score  2.46839를 기록하였다.

선형 모델은 다른 GBDT나 CATBOOST 모델에 비해 성능이 낮다.

특징값의 범위가 균일하지 않으면 정규화의 효과가 특징에 따라 달라지믈 학습이 진행되지 않을 수 있음==>count값이 균일하지 않으므로 적합하지 않은 모델

상호작용을 나타내는 특징을 일부러 만들거나 최댓값/최솟값을 제한하거나 구간분할을 하거나 그들을 조합하는 등 다양한 변환이나 처리.




```python
from sklearn.linear_model import LogisticRegression
LR=LogisticRegression()
LR.fit(train2,train["count"])
result=LR.predict(test2)
result
```

<pre>
/opt/conda/lib/python3.7/site-packages/sklearn/linear_model/_logistic.py:818: ConvergenceWarning: lbfgs failed to converge (status=1):
STOP: TOTAL NO. of ITERATIONS REACHED LIMIT.

Increase the number of iterations (max_iter) or scale the data as shown in:
    https://scikit-learn.org/stable/modules/preprocessing.html
Please also refer to the documentation for alternative solver options:
    https://scikit-learn.org/stable/modules/linear_model.html#logistic-regression
  extra_warning_msg=_LOGISTIC_SOLVER_CONVERGENCE_MSG,
</pre>
<pre>
array([1, 1, 1, ..., 1, 1, 1])
</pre>
Lasso 모델 score 1.20873



```python
from sklearn.linear_model import Lasso
ls=Lasso()
ls.fit(train2,train["count"])
result=ls.predict(test2)
result=np.absolute(list(result))
result
```

<pre>
array([ 22.83753911,  18.77172599,  11.02199679, ..., 208.03925463,
       226.31880201, 215.67397738])
</pre>
Ridge model -값으로 반환되어 절댓값으로 계산하자 score : 1.21130



```python
from sklearn.linear_model import Ridge
rg=Ridge()
rg.fit(train2,train["count"])
result=rg.predict(test2)
result=np.absolute(list(result))
result
```

<pre>
array([ 23.2558968 ,  20.83040042,  13.02694849, ..., 209.82681124,
       227.93407623, 217.84343227])
</pre>
랜덤 포레스트의 가장 큰 특징은 랜덤성(randomness)에 의해 트리들이 서로 조금씩 다른 특성을 갖는다는 점이다. 

랜덤화(randomization)는 포레스트가 노이즈가 포함된 데이터에 대해서도 강인하게 만들어 준다.

각 트리들의 예측(prediction)들이 비상관화(decorrelation) 되게하며, 결과적으로 일반화(generalization) 성능을 향상시킨다. 

랜덤화는 각 트리들의 훈련 과정에서 진행된다. 

랜덤 학습 데이터 추출 방법을 이용한 앙상블 학습법인 배깅(bagging)과 랜덤 노드 최적화(randomized node optimization)가 자주 사용된다. 

이 두 가지 방법은 서로 동시에 사용되어 랜덤화 특성을 더욱 증진 시킬 수 있다.



```python
from sklearn.ensemble import RandomForestRegressor
rfr=RandomForestRegressor(n_jobs=-1)
rfr.fit(train2,train["count"])
result=rfr.predict(test2)
result
```

<pre>
array([ 11.78 ,   4.62 ,   3.95 , ...,  98.425, 102.26 ,  47.31 ])
</pre>
결론적으로 count값이 균일하지 않으므로 linear_model은 사용이 부적합하며, 절댓값을 제출하면 CatBoostRegressor > GradientBoostingRegressor 순으로 score가 높다.

RandomForestRegressor를 이용하면 예측 값에 음수가 존재하지 않으며 가장 정확한 예측이 가능하다.(score:0.42058)

box plot의 count값을 보면 outlier들이 있는데 RandomForestRegressor의 랜덤화와 예측 값 간의 비상관화가 노이즈에 대해서도 강인하게 만들어 주기 때문이다.

또한, Month column은 주어진 train,test 데이터에서 학습과정에 부정확도를 상승시키므로 제외하는 것이 적합하다.



```python
sub=pd.read_csv("/kaggle/input/bike-sharing-demand/sampleSubmission.csv")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>2012-12-31 19:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>2012-12-31 20:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>2012-12-31 21:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>2012-12-31 22:00:00</td>
      <td>0</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>2012-12-31 23:00:00</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 2 columns</p>
</div>



```python
sub["count"]=result
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>datetime</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2011-01-20 00:00:00</td>
      <td>11.780</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2011-01-20 01:00:00</td>
      <td>4.620</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2011-01-20 02:00:00</td>
      <td>3.950</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011-01-20 03:00:00</td>
      <td>3.890</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2011-01-20 04:00:00</td>
      <td>3.280</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6488</th>
      <td>2012-12-31 19:00:00</td>
      <td>203.390</td>
    </tr>
    <tr>
      <th>6489</th>
      <td>2012-12-31 20:00:00</td>
      <td>161.780</td>
    </tr>
    <tr>
      <th>6490</th>
      <td>2012-12-31 21:00:00</td>
      <td>98.425</td>
    </tr>
    <tr>
      <th>6491</th>
      <td>2012-12-31 22:00:00</td>
      <td>102.260</td>
    </tr>
    <tr>
      <th>6492</th>
      <td>2012-12-31 23:00:00</td>
      <td>47.310</td>
    </tr>
  </tbody>
</table>
<p>6493 rows × 2 columns</p>
</div>



```python
rfr.feature_importances_
```

<pre>
array([0.03830382, 0.00221091, 0.04384866, 0.01524303, 0.07955084,
       0.03912681, 0.03122117, 0.01046415, 0.08769251, 0.60976475,
       0.04257334])
</pre>
모델을 사용하여 train할때 정확성을 높이는데 기여도가 높은 columns을 확인하면 다음과 같다.



```python
pd.Series(rfr.feature_importances_,index=train2.columns).sort_values(ascending=False)
```

<pre>
Hour          0.609765
Year          0.087693
temp          0.079551
workingday    0.043849
Weekday       0.042573
atemp         0.039127
season        0.038304
humidity      0.031221
weather       0.015243
windspeed     0.010464
holiday       0.002211
dtype: float64
</pre>

```python
sub.to_csv("rfr_without_month",index=False)
```
