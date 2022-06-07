# 5 회귀분석 모델 실험 (Kaggle  Bike Sharing Demand)

![image](https://user-images.githubusercontent.com/69743938/172272305-9e152b38-376a-43b8-8a58-5089b4f0eef7.png)
![image](https://user-images.githubusercontent.com/69743938/172272334-e4866091-0e95-4a38-92a9-95ae8bd93786.png)

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

/kaggle/input/bike-sharing-demand/sampleSubmission.csv

/kaggle/input/bike-sharing-demand/train.csv

/kaggle/input/bike-sharing-demand/test.csv


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

-------
datetime의 칼럼에서 train에 필요한 데이터만 추출하려합니다.

------



```python
train["datetime"]=pd.to_datetime(train["datetime"])
train["Year"]=train["datetime"].dt.year
train["Hour"]=train["datetime"].dt.hour
train["Weekday"]=train["datetime"].dt.weekday

test["datetime"]=pd.to_datetime(test["datetime"])
test["Year"]=test["datetime"].dt.year
test["Hour"]=test["datetime"].dt.hour
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


![image](https://user-images.githubusercontent.com/69743938/172124761-828bbc7e-07e9-4c24-b378-e2c6f8ad6061.png)

----------------------------
working day 여부에 따라 대여수가 다를 것으로 보고 box plot으로 확인하겠습니다.

----



```python
weekday_df=train[train['workingday']==1]
weekday_df
weekend_df=train[train['workingday']==0]
weekend_df
plt.figure(figsize=(16,8))
sns.boxplot(weekday_df["Hour"],weekday_df["count"])
```

![image](https://user-images.githubusercontent.com/69743938/172124791-0bea0d09-70b1-4748-a0f1-68278fe858f3.png)
```python
plt.figure(figsize=(16,8))
sns.boxplot(weekend_df["Hour"],weekend_df["count"])
```


![image](https://user-images.githubusercontent.com/69743938/172124828-782aa004-b026-42c1-98a3-a0d4bddab252.png)

-----------
working day에는 출/퇴근 시간에, non working day에는 낮 시간대에 대여수가 증가함을 확인했습니다. 

또한, count의 값이 크기 때문에 log 형식으로 바꾸어주면 정규성을 확보하여 예측 정확도를 높일 수 있음을 고려했습니다.

-------



```python
sns.displot(np.log(train["count"]))
```

![image](https://user-images.githubusercontent.com/69743938/172124864-6b2e5e59-144e-4385-987e-0a4338e53389.png)

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

-----------------
GradientBoostingRegressor을 사용하니 predict에 -값이 출력되어 err가 발생하고 출력이 불가능합니다.

predict값을 절댓값으로 변환하여 제출하자 score는 0.70437로 동일 조건의 RandomForestRegressor score : 0.42058에 비해 미개선 확인됩니다.
(score는 낮을수록 순위 향상됩니다.)

------------

```python
from sklearn.ensemble import GradientBoostingRegressor
gbr=GradientBoostingRegressor()
gbr.fit(train2,train["count"])
result=gbr.predict(test2)
result=np.absolute(list(result))
result
```

array([ 15.65101246,   7.32384145,   2.21763301, ..., 111.68123036,
        82.18822316,  53.21244721])

-----
CatBoostRegressor의 경우 predict값에 -값이 출력되어 err가 발생하고 제출이 되지 않습니다.

절댓값을 구하자 score : 0.49252로 동일 조건의 RandomForestRegressor score:0.42058 보다 미개선 확인됩니다.

------------

```python
from catboost import CatBoostRegressor
cbr=CatBoostRegressor()
cbr.fit(train2,train["count"])
result=cbr.predict(test2)
result=np.absolute(list(result))
result
```

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

...
999:	learn: 30.4092078	total: 2.56s	remaining: 0us

array([ 20.10567644,   0.83930807,   3.77110868, ..., 112.30901916,
        78.70384289,  30.1806374 ])

------------
LinearRegression 적용하자 -값이 반환되어 제출이 불가능하고, 절댓값을 적용하자 score 1.21132로 가장 예측이 부정확합니다.

LinearRegression은 다른 모델에 비해 성능이 낮은데, 특징값의 범위가 균일하지 않으면 정규화의 효과가 특징에 따라 달라지므로 학습이 진행되지 않을 수 있기 때문입니다.

Count값을 확인하였을 때, 균일하지 않으므로 부정확한 예측을 초래한 것은 당연한 결과였습니다.

------

```python
from sklearn.linear_model import LinearRegression
lr=LinearRegression()
lr.fit(train2,train["count"])
result=lr.predict(test2)
result=np.absolute(list(result))
result
```

array([ 23.27179232,  20.84936197,  13.04580719, ..., 209.84495832,
       227.95174821, 217.86201958])

------------
LogisticRegression을 이용하자 -값은 없으나 predict값이 모두 1로 나오며 score  2.46839를 기록했습니다.

이는 LinearRegression과 같이 특징값의 범위가 균일하지 않으면 정규화의 효과가 특징에 따라 달라지므로 학습이 진행되지 않을 수 있기 때문입니다.

----------------

```python
from sklearn.linear_model import LogisticRegression
LR=LogisticRegression()
LR.fit(train2,train["count"])
result=LR.predict(test2)
result
```


array([1, 1, 1, ..., 1, 1, 1])

-------
linear model중 Lasso model과 Ridge model이 있습니다.

이들 역시 -값이 반환되어 절댓값으로 바꾸어 result에 적용했습니다.

Lasso model (score : 1.20873) 과 Ridge model (score : 1.21130) 의 적용 code는 아래와 같습니다.

Lasso model

----------


```python
from sklearn.linear_model import Lasso
ls=Lasso()
ls.fit(train2,train["count"])
result=ls.predict(test2)
result=np.absolute(list(result))
result
```


array([ 22.83753911,  18.77172599,  11.02199679, ..., 208.03925463,
       226.31880201, 215.67397738])

--------------
Ridge model 

------------

```python
from sklearn.linear_model import Ridge
rg=Ridge()
rg.fit(train2,train["count"])
result=rg.predict(test2)
result=np.absolute(list(result))
result
```

array([ 23.2558968 ,  20.83040042,  13.02694849, ..., 209.82681124,
       227.93407623, 217.84343227])




```python
from sklearn.ensemble import RandomForestRegressor
rfr=RandomForestRegressor(n_jobs=-1)
rfr.fit(train2,train["count"])
result=rfr.predict(test2)
result
```


array([ 11.78 ,   4.62 ,   3.95 , ...,  98.425, 102.26 ,  47.31 ])

--------------

결론적으로 count값이 균일하지 않으므로 linear_model은 사용이 부적합하며, 절댓값 제출한 것을 포함하면

RandomForestRegressor score : 0.42058 > CatBoostRegressor 절댓값  score : 0.49252 > GradientBoostingRegressor 절댓값 score : 0.70437 > Lasso model 절댓값 score : 1.20873 > Ridge model  절댓값  score : 1.21130 >LinearRegression 절댓값 score : 1.21132 > LogisticRegression score : 2.46839 순으로 점수가 개선됩니다.

그러나 주의해야할 점은 -값은 0에 가깝기 때문에 절댓값으로 예측하는 것은 무리가 있어 보입니다.

흥미로운 점은 절댓값으로 적용된 경우 LogisticRegressor보다 정확히 예측한 것으로 score가 나타났다는 것입니다.

이는 양수로 나타난 count값만 두고 볼 때, Logistic Regression보다 정확히 맞추었음을 생각할 수 있습니다.

단순히 -값을 예측했으므로 부적합한 모델로 제외하는 것보다 다른 모델 결과값과 비교하여 예측하는 것이 효과적임을 생각했습니다.

RandomForestRegressor가 특히 정확도가 높은 것에 의구심을 품게 되었는데, box plot의 count값의 outlier를 보며 이유를 유추할 수 있습니다.

RandomForestRegressor는 랜덤화와 예측 값 간의 비상관화가 노이즈에 대해서도 강인하게 만들 장점을 갖고 있어 이 데이터에 적용이 유리합니다.

또한, Month column은 주어진 train,test 데이터에서 학습과정에 부정확도를 상승시키므로 제외하는 것이 적합할 것으로 보입니다.

------------


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

array([0.03830382, 0.00221091, 0.04384866, 0.01524303, 0.07955084,
       0.03912681, 0.03122117, 0.01046415, 0.08769251, 0.60976475,
       0.04257334])

------------
모델을 사용하여 train할때 정확성을 높이는데 기여도가 높은 columns을 확인하면 다음과 같습니다.

-----------


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

