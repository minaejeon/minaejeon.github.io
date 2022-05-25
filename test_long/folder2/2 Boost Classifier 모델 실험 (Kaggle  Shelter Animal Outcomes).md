# 2 Boost Classifier 모델 실험 (Kaggle  Shelter Animal Outcomes).md

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
/kaggle/input/shelter-animal-outcomes/sample_submission.csv.gz
/kaggle/input/shelter-animal-outcomes/train.csv.gz
/kaggle/input/shelter-animal-outcomes/test.csv.gz
</pre>

```python
train=pd.read_csv("/kaggle/input/shelter-animal-outcomes/train.csv.gz")
test=pd.read_csv("/kaggle/input/shelter-animal-outcomes/test.csv.gz")
pd.options.display.max_columns=99
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AnimalID</th>
      <th>Name</th>
      <th>DateTime</th>
      <th>OutcomeType</th>
      <th>OutcomeSubtype</th>
      <th>AnimalType</th>
      <th>SexuponOutcome</th>
      <th>AgeuponOutcome</th>
      <th>Breed</th>
      <th>Color</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A671945</td>
      <td>Hambone</td>
      <td>2014-02-12 18:22:00</td>
      <td>Return_to_owner</td>
      <td>NaN</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>1 year</td>
      <td>Shetland Sheepdog Mix</td>
      <td>Brown/White</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A656520</td>
      <td>Emily</td>
      <td>2013-10-13 12:44:00</td>
      <td>Euthanasia</td>
      <td>Suffering</td>
      <td>Cat</td>
      <td>Spayed Female</td>
      <td>1 year</td>
      <td>Domestic Shorthair Mix</td>
      <td>Cream Tabby</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A686464</td>
      <td>Pearce</td>
      <td>2015-01-31 12:28:00</td>
      <td>Adoption</td>
      <td>Foster</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>2 years</td>
      <td>Pit Bull Mix</td>
      <td>Blue/White</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A683430</td>
      <td>NaN</td>
      <td>2014-07-11 19:09:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>3 weeks</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue Cream</td>
    </tr>
    <tr>
      <th>4</th>
      <td>A667013</td>
      <td>NaN</td>
      <td>2013-11-15 12:52:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>2 years</td>
      <td>Lhasa Apso/Miniature Poodle</td>
      <td>Tan</td>
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
    </tr>
    <tr>
      <th>26724</th>
      <td>A702446</td>
      <td>NaN</td>
      <td>2015-05-14 11:56:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>1 month</td>
      <td>Domestic Shorthair Mix</td>
      <td>Brown Tabby/White</td>
    </tr>
    <tr>
      <th>26725</th>
      <td>A718934</td>
      <td>NaN</td>
      <td>2016-01-20 18:59:00</td>
      <td>Transfer</td>
      <td>SCRP</td>
      <td>Cat</td>
      <td>Spayed Female</td>
      <td>3 months</td>
      <td>Domestic Shorthair Mix</td>
      <td>Brown Tabby</td>
    </tr>
    <tr>
      <th>26726</th>
      <td>A698128</td>
      <td>Zeus</td>
      <td>2015-03-09 13:33:00</td>
      <td>Adoption</td>
      <td>NaN</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>4 years</td>
      <td>Old English Bulldog Mix</td>
      <td>White/Tan</td>
    </tr>
    <tr>
      <th>26727</th>
      <td>A677478</td>
      <td>NaN</td>
      <td>2014-04-27 12:22:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>4 weeks</td>
      <td>Domestic Shorthair Mix</td>
      <td>Black</td>
    </tr>
    <tr>
      <th>26728</th>
      <td>A706629</td>
      <td>NaN</td>
      <td>2015-07-02 09:00:00</td>
      <td>Transfer</td>
      <td>SCRP</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>1 year</td>
      <td>Domestic Shorthair Mix</td>
      <td>Brown Tabby/White</td>
    </tr>
  </tbody>
</table>
<p>26729 rows × 10 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Name</th>
      <th>DateTime</th>
      <th>AnimalType</th>
      <th>SexuponOutcome</th>
      <th>AgeuponOutcome</th>
      <th>Breed</th>
      <th>Color</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>Summer</td>
      <td>2015-10-12 12:15:00</td>
      <td>Dog</td>
      <td>Intact Female</td>
      <td>10 months</td>
      <td>Labrador Retriever Mix</td>
      <td>Red/White</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>Cheyenne</td>
      <td>2014-07-26 17:59:00</td>
      <td>Dog</td>
      <td>Spayed Female</td>
      <td>2 years</td>
      <td>German Shepherd/Siberian Husky</td>
      <td>Black/Tan</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>Gus</td>
      <td>2016-01-13 12:20:00</td>
      <td>Cat</td>
      <td>Neutered Male</td>
      <td>1 year</td>
      <td>Domestic Shorthair Mix</td>
      <td>Brown Tabby</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>Pongo</td>
      <td>2013-12-28 18:12:00</td>
      <td>Dog</td>
      <td>Intact Male</td>
      <td>4 months</td>
      <td>Collie Smooth Mix</td>
      <td>Tricolor</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>Skooter</td>
      <td>2015-09-24 17:59:00</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>2 years</td>
      <td>Miniature Poodle Mix</td>
      <td>White</td>
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
    </tr>
    <tr>
      <th>11451</th>
      <td>11452</td>
      <td>NaN</td>
      <td>2014-07-08 14:50:00</td>
      <td>Cat</td>
      <td>Neutered Male</td>
      <td>2 months</td>
      <td>Domestic Shorthair Mix</td>
      <td>Black</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>11453</td>
      <td>NaN</td>
      <td>2014-10-21 12:57:00</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>2 weeks</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>11454</td>
      <td>NaN</td>
      <td>2014-09-29 09:00:00</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>1 year</td>
      <td>Domestic Shorthair Mix</td>
      <td>Calico</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>11455</td>
      <td>Rambo</td>
      <td>2015-09-05 17:16:00</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>6 years</td>
      <td>German Shepherd Mix</td>
      <td>Black/Tan</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>11456</td>
      <td>Gusto</td>
      <td>2014-07-12 18:40:00</td>
      <td>Dog</td>
      <td>Intact Male</td>
      <td>4 years</td>
      <td>Labrador Retriever</td>
      <td>Cream</td>
    </tr>
  </tbody>
</table>
<p>11456 rows × 8 columns</p>
</div>


'AgeuponOutcome'연령의 단위가 다르게 있어 train과정에 어려움이 있을 것으로 보고, 모두 day로 변환한다.



```python
alldata=pd.concat([train,test])
alldata["DateTime"]=pd.to_datetime(alldata["DateTime"])
alldata["Year"]=alldata["DateTime"].dt.year
alldata["Month"]=alldata["DateTime"].dt.month
alldata["Day"]=alldata["DateTime"].dt.day
alldata["Hour"]=alldata["DateTime"].dt.hour
alldata["Weekday"]=alldata["DateTime"].dt.weekday
alldata["Minute"]=alldata["DateTime"].dt.minute

def agetransformation(x) :
    if pd.isnull(x):
        return -1
    num=int(x.split()[0])
    if 'year' in x:
        return num*365
    elif 'month' in x:
        return num*30
    elif 'week' in x:
        return num*7
    else :
        return num*1
    
alldata["AgeuponOutcome"]=alldata["AgeuponOutcome"].apply(agetransformation)
alldata
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>AnimalID</th>
      <th>Name</th>
      <th>DateTime</th>
      <th>OutcomeType</th>
      <th>OutcomeSubtype</th>
      <th>AnimalType</th>
      <th>SexuponOutcome</th>
      <th>AgeuponOutcome</th>
      <th>Breed</th>
      <th>Color</th>
      <th>ID</th>
      <th>Year</th>
      <th>Month</th>
      <th>Day</th>
      <th>Hour</th>
      <th>Weekday</th>
      <th>Minute</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A671945</td>
      <td>Hambone</td>
      <td>2014-02-12 18:22:00</td>
      <td>Return_to_owner</td>
      <td>NaN</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>365</td>
      <td>Shetland Sheepdog Mix</td>
      <td>Brown/White</td>
      <td>NaN</td>
      <td>2014</td>
      <td>2</td>
      <td>12</td>
      <td>18</td>
      <td>2</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>A656520</td>
      <td>Emily</td>
      <td>2013-10-13 12:44:00</td>
      <td>Euthanasia</td>
      <td>Suffering</td>
      <td>Cat</td>
      <td>Spayed Female</td>
      <td>365</td>
      <td>Domestic Shorthair Mix</td>
      <td>Cream Tabby</td>
      <td>NaN</td>
      <td>2013</td>
      <td>10</td>
      <td>13</td>
      <td>12</td>
      <td>6</td>
      <td>44</td>
    </tr>
    <tr>
      <th>2</th>
      <td>A686464</td>
      <td>Pearce</td>
      <td>2015-01-31 12:28:00</td>
      <td>Adoption</td>
      <td>Foster</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>730</td>
      <td>Pit Bull Mix</td>
      <td>Blue/White</td>
      <td>NaN</td>
      <td>2015</td>
      <td>1</td>
      <td>31</td>
      <td>12</td>
      <td>5</td>
      <td>28</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A683430</td>
      <td>NaN</td>
      <td>2014-07-11 19:09:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>21</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue Cream</td>
      <td>NaN</td>
      <td>2014</td>
      <td>7</td>
      <td>11</td>
      <td>19</td>
      <td>4</td>
      <td>9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>A667013</td>
      <td>NaN</td>
      <td>2013-11-15 12:52:00</td>
      <td>Transfer</td>
      <td>Partner</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>730</td>
      <td>Lhasa Apso/Miniature Poodle</td>
      <td>Tan</td>
      <td>NaN</td>
      <td>2013</td>
      <td>11</td>
      <td>15</td>
      <td>12</td>
      <td>4</td>
      <td>52</td>
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
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11451</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2014-07-08 14:50:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cat</td>
      <td>Neutered Male</td>
      <td>60</td>
      <td>Domestic Shorthair Mix</td>
      <td>Black</td>
      <td>11452.0</td>
      <td>2014</td>
      <td>7</td>
      <td>8</td>
      <td>14</td>
      <td>1</td>
      <td>50</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2014-10-21 12:57:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>14</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue</td>
      <td>11453.0</td>
      <td>2014</td>
      <td>10</td>
      <td>21</td>
      <td>12</td>
      <td>1</td>
      <td>57</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2014-09-29 09:00:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>365</td>
      <td>Domestic Shorthair Mix</td>
      <td>Calico</td>
      <td>11454.0</td>
      <td>2014</td>
      <td>9</td>
      <td>29</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>NaN</td>
      <td>Rambo</td>
      <td>2015-09-05 17:16:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>2190</td>
      <td>German Shepherd Mix</td>
      <td>Black/Tan</td>
      <td>11455.0</td>
      <td>2015</td>
      <td>9</td>
      <td>5</td>
      <td>17</td>
      <td>5</td>
      <td>16</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>NaN</td>
      <td>Gusto</td>
      <td>2014-07-12 18:40:00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Dog</td>
      <td>Intact Male</td>
      <td>1460</td>
      <td>Labrador Retriever</td>
      <td>Cream</td>
      <td>11456.0</td>
      <td>2014</td>
      <td>7</td>
      <td>12</td>
      <td>18</td>
      <td>5</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
<p>38185 rows × 17 columns</p>
</div>



```python
alldata2=alldata.drop(columns=["AnimalID","OutcomeType","OutcomeSubtype","DateTime","ID"])
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>AnimalType</th>
      <th>SexuponOutcome</th>
      <th>AgeuponOutcome</th>
      <th>Breed</th>
      <th>Color</th>
      <th>Year</th>
      <th>Month</th>
      <th>Day</th>
      <th>Hour</th>
      <th>Weekday</th>
      <th>Minute</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Hambone</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>365</td>
      <td>Shetland Sheepdog Mix</td>
      <td>Brown/White</td>
      <td>2014</td>
      <td>2</td>
      <td>12</td>
      <td>18</td>
      <td>2</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Emily</td>
      <td>Cat</td>
      <td>Spayed Female</td>
      <td>365</td>
      <td>Domestic Shorthair Mix</td>
      <td>Cream Tabby</td>
      <td>2013</td>
      <td>10</td>
      <td>13</td>
      <td>12</td>
      <td>6</td>
      <td>44</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Pearce</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>730</td>
      <td>Pit Bull Mix</td>
      <td>Blue/White</td>
      <td>2015</td>
      <td>1</td>
      <td>31</td>
      <td>12</td>
      <td>5</td>
      <td>28</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>Cat</td>
      <td>Intact Male</td>
      <td>21</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue Cream</td>
      <td>2014</td>
      <td>7</td>
      <td>11</td>
      <td>19</td>
      <td>4</td>
      <td>9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>730</td>
      <td>Lhasa Apso/Miniature Poodle</td>
      <td>Tan</td>
      <td>2013</td>
      <td>11</td>
      <td>15</td>
      <td>12</td>
      <td>4</td>
      <td>52</td>
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
      <th>11451</th>
      <td>NaN</td>
      <td>Cat</td>
      <td>Neutered Male</td>
      <td>60</td>
      <td>Domestic Shorthair Mix</td>
      <td>Black</td>
      <td>2014</td>
      <td>7</td>
      <td>8</td>
      <td>14</td>
      <td>1</td>
      <td>50</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>NaN</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>14</td>
      <td>Domestic Shorthair Mix</td>
      <td>Blue</td>
      <td>2014</td>
      <td>10</td>
      <td>21</td>
      <td>12</td>
      <td>1</td>
      <td>57</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>NaN</td>
      <td>Cat</td>
      <td>Intact Female</td>
      <td>365</td>
      <td>Domestic Shorthair Mix</td>
      <td>Calico</td>
      <td>2014</td>
      <td>9</td>
      <td>29</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>Rambo</td>
      <td>Dog</td>
      <td>Neutered Male</td>
      <td>2190</td>
      <td>German Shepherd Mix</td>
      <td>Black/Tan</td>
      <td>2015</td>
      <td>9</td>
      <td>5</td>
      <td>17</td>
      <td>5</td>
      <td>16</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>Gusto</td>
      <td>Dog</td>
      <td>Intact Male</td>
      <td>1460</td>
      <td>Labrador Retriever</td>
      <td>Cream</td>
      <td>2014</td>
      <td>7</td>
      <td>12</td>
      <td>18</td>
      <td>5</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
<p>38185 rows × 12 columns</p>
</div>


cat boost classifier에서 가장 정확도가 높은 alldata2 set// 다른 model 사용의 경우 "DateTime" column이 drop되어야 오류가 발생하지 않음



```python
# alldata2=alldata.drop(columns=["AnimalID","OutcomeType","OutcomeSubtype","ID"])
# alldata2
```


```python
# alldata2=alldata.drop(columns=["AnimalID","OutcomeType","OutcomeSubtype","ID","SexuponOutcome"])
# alldata2
```


```python
alldata["AgeuponOutcome"].unique()
```

<pre>
array([ 365,  730,   21,   30,  150, 1460,   90,   14,   60,  300,  180,
       1825, 2555, 1095,  120, 4380, 3285, 2190,    7, 4015,   28,  210,
       2920,  330,    4,  270,  240, 5475, 3650,    0, 5110,    3,    6,
          5,   35,    2, 5840,    1, 4745,   -1, 6205, 6570, 6935, 7300,
       8030])
</pre>
도표를 통해, adoption이 17~18시에 많기 때문에 출 퇴근 시간의 영향이 있음을 알 수 있다.

0~9, 19~24 구간에서 count의 갯수가 현저히 낮아지므로 사람의 여가 및 수면 시간과도 관계있음을 알 수 있다.

catboostclassifier를 이용하고, DateTime column을 삭제하였을때 score는 0.74015였으나 DateTime Column을 추가하니 score는 0.73824로 개선되었다(score 낮을 수록 순위 개선) DateTime의 날짜형식을 인식할 수 있는 것이 CatBoostClassifier가 가지는 장점 중 하나이다.



```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.countplot(alldata["Hour"],hue=alldata["OutcomeType"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='Hour', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA7kAAAHgCAYAAABguarWAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAA51ElEQVR4nO3deZRdZYEu/OclCRAGZRBoBf0SbbTDkJnZDBBBWhEExIsXkTg0ooI2S6UR2wYRuNyLaAva0qIYsWNEoRm8y+8TBUmYFBKoMAUF7SCJNGMLBIKS5P3+qJPqAFWVAFV1qja/31q1cs679znnqVNQu57z7qHUWgMAAABNsF67AwAAAEBfUXIBAABoDCUXAACAxlByAQAAaAwlFwAAgMZQcgEAAGiM4e0O0B9e85rX1FGjRrU7BgAAAP1gwYIFj9Rat+puWSNL7qhRozJ//vx2xwAAAKAflFLu62mZ3ZUBAABoDCUXAACAxlByAQAAaIxGHpMLAM8++2yWLFmSZ555pt1R6GMbbrhhtttuu4wYMaLdUQAYhPqt5JZSXp/kwiTbJKlJvlVr/Vop5ZQkf5fk4daqJ9Vaf9p6zOeSfDjJyiSfrLX+rDW+f5KvJRmW5Nu11jP7KzcAzbBkyZJsuummGTVqVEop7Y5DH6m15tFHH82SJUsyevTodscBYBDqz5ncFUk+XWu9pZSyaZIFpZSft5Z9tdb65TVXLqXskOTwJDsmeV2SX5RS3txa/I0k+yZZkuTmUsoVtda7+jE7AEPcM888o+A2UCklW265ZR5++OG1rwzAK1K/ldxa6wNJHmjdfrKUsijJtr085KAkP6y1/jnJf5RS7k2ya2vZvbXW3ydJKeWHrXWVXAB6peA2k58rAL0ZkBNPlVJGJZmQ5NetoWNLKbeVUi4opWzeGts2yf1rPGxJa6yncQAYFJYsWZKDDjoo22+/fd70pjflU5/6VP7yl7/0+pgzzjhjgNI918EHH5zx48fnr//6r/PqV78648ePz/jx43PDDTe0JQ8A9LV+L7mllE2SXJLk72utTyT5ZpI3JRmfzpnes/vodY4upcwvpcy3CxMAA6XWmkMOOSTvfve7c8899+S3v/1tli1bls9//vO9Pq5dJffSSy9NR0dHvv3tb2fKlCnp6OhIR0dH9txzz7bkAYC+1q8lt5QyIp0Fd3at9d+TpNb6YK11Za11VZLz89+7JC9N8vo1Hr5da6yn8eeotX6r1jq51jp5q6226vtvBgC6cfXVV2fDDTfMBz/4wSTJsGHD8tWvfjUXXHBB/uVf/iXHHnts17oHHHBArrnmmpx44olZvnx5xo8fnyOOOCJJcuGFF2bs2LEZN25cjjzyyCTJ4sWLs88++2Ts2LGZMWNG/vCHPyRJZs6cmY997GPZfffd88Y3vjHXXHNNPvShD2XMmDGZOXNm1+tdeeWV2WOPPTJx4sQcdthhWbZsWbffw9SpU9PR0dF1/61vfWsWLlyYU045JUceeWT22GOPbL/99jn//PO71jnrrLOyyy67ZOzYsTn55JP75L0EgL7QbyW3dB4w850ki2qtX1lj/LVrrHZwkjtat69IcngpZYNSyugk2ye5KcnNSbYvpYwupayfzpNTXdFfuQHgxbjzzjszadKk54y96lWvyhve8IasWLGi28eceeaZGTlyZDo6OjJ79uzceeedOe2003L11Vdn4cKF+drXvpYkOe6443LUUUfltttuyxFHHJFPfvKTXc/xX//1X7nxxhvz1a9+NQceeGCOP/743Hnnnbn99tvT0dGRRx55JKeddlp+8Ytf5JZbbsnkyZPzla98pds8H/7whzNr1qwkyW9/+9s888wzGTduXJLktttuy9VXX50bb7wxp556av74xz/myiuvzD333JObbropHR0dWbBgQebNm/dy30oA6BP9eXblvZIcmeT2UkpHa+ykJO8rpYxP52WFFif5aJLUWu8spfwonSeUWpHkE7XWlUlSSjk2yc/SeQmhC2qtd/ZjbgAYUFdffXUOO+ywvOY1r0mSbLHFFkmSG2+8Mf/+7/+eJDnyyCNzwgkndD3mXe96V0op2XnnnbPNNttk5513TpLsuOOOWbx4cZYsWZK77rore+21V5LkL3/5S/bYY49uX/+www7Ll770pZx11lm54IILnjMbfNBBB2XkyJEZOXJk9t5779x000257rrrcuWVV2bChAlJkmXLluWee+7J1KlT+/aNAYCXoD/Prnxdku5Of/jTXh5zepLTuxn/aW+PA4B22WGHHXLxxRc/Z+yJJ57IH/7wh2y22WZZtWpV1/gzzzzTZ6+7wQYbJEnWW2+9rtur769YsSLDhg3Lvvvumzlz5qz1uTbaaKPsu+++ufzyy/OjH/0oCxYs6Fr2/DMZl1JSa83nPve5fPSjH+2j7wYA+s6AnF0ZAJpqxowZefrpp3PhhRcmSVauXJlPf/rTmTlzZt74xjemo6Mjq1atyv3335+bbrqp63EjRozIs88+myTZZ5998uMf/ziPPvpokuSxxx5Lkuy555754Q9/mCSZPXt2pkyZss65dt9991x//fW59957kyRPPfVUfvvb3/a4/kc+8pF88pOfzC677JLNN9+8a/zyyy/PM888k0cffTTXXHNNdtlll7z97W/PBRdc0HWM79KlS/PQQw+tczYA6E/9ubsyADReKSWXXnppPv7xj+dLX/pSVq1alXe84x0544wzsv7662f06NHZYYcdMmbMmEycOLHrcUcffXTGjh2biRMnZvbs2fn85z+fadOmZdiwYZkwYUJmzZqVc889Nx/84Adz1llnZauttsp3v/vddc611VZbZdasWXnf+96XP//5z0mS0047LW9+85u7XX/SpEl51ate1XUCrdXGjh2bvffeO4888ki+8IUv5HWve11e97rXZdGiRV27P2+yySb5t3/7t2y99dYv9u0DgD5Xaq3tztDnJk+eXOfPn9/uGAC00aJFizJmzJh2xxgy/vjHP2b69Om5++67s956nTt6nXLKKdlkk03ymc98ps3pXsjPF+CVrZSyoNY6ubtldlcGgFe4Cy+8MLvttltOP/30roILAEOVmVwAGslMX7P5+QK8spnJBQAA4BXBiacAAOg3e527V7fj1x93/QAnAV4pzOQCAADQGEouAAAAjaHkAgAA0BiOyQXgFWHSZy/s0+dbcNYH1rrOsGHDsvPOO2fFihUZPXp0vv/972ezzTbrcf3LLrssb37zm7PDDjv0YdIXOuOMM3LSSSf162sAQLuYyQWAfjJy5Mh0dHTkjjvuyBZbbJFvfOMbva5/2WWX5a677npRr7FixYoXneuMM8540Y9pp5fyPQLwyqXkAsAA2GOPPbJ06dIkye9+97vsv//+mTRpUqZMmZK77747N9xwQ6644op89rOfzfjx4/O73/0u06dPz+rrvj/yyCMZNWpUkmTWrFk58MADs88++2TGjBmZNWtWDjnkkOy///7Zfvvtc8IJJ/SY48QTT8zy5cszfvz4HHHEEUmSr3zlK9lpp52y00475Z//+Z97/T66W/ess87KOeeckyQ5/vjjs88++yRJrr766q7X2GSTTfL5z38+48aNy+67754HH3wwSfLwww/n0EMPzS677JJddtkl11/fecbdU045JUceeWT22muvHHnkkS/y3QbglUzJBYB+tnLlylx11VU58MADkyRHH310zj333CxYsCBf/vKX8/GPfzx77rlnDjzwwJx11lnp6OjIm970pl6f85ZbbsnFF1+cuXPnJkk6Ojpy0UUX5fbbb89FF12U+++/v9vHnXnmmV0zzLNnz86CBQvy3e9+N7/+9a/zq1/9Kueff35uvfXWbh/b07pTpkzJtddemySZP39+li1blmeffTbXXnttpk6dmiR56qmnsvvuu2fhwoWZOnVqzj///CTJpz71qRx//PG5+eabc8kll+QjH/lI1+vddddd+cUvfpE5c+a8iHcbgFc6x+QCQD9ZPWO6dOnSjBkzJvvuu2+WLVuWG264IYcddljXen/+859f9HPvu+++2WKLLbruz5gxI69+9auTJDvssEPuu+++vP71r1/r81x33XU5+OCDs/HGGydJDjnkkFx77bWZMGHCOq/7sY99LAsWLMgTTzyRDTbYIBMnTsz8+fNz7bXXds3wrr/++jnggAOSJJMmTcrPf/7zJMkvfvGL5+yi/cQTT2TZsmVJkgMPPDAjR4580e8NAK9sSi4A9JPVM6ZPP/103v72t+cb3/hGZs6cmc022ywdHR1rffzw4cOzatWqJMkzzzzznGWri+ZqG2ywQdftYcOGDehxrCNGjMjo0aMza9as7Lnnnhk7dmx++ctf5t57782YMWO61imlvCDfqlWr8qtf/SobbrjhC573+d8jAKwLuysDQD/baKONcs455+Tss8/ORhttlNGjR+fHP/5xkqTWmoULFyZJNt100zz55JNdjxs1alQWLFiQJLn44ov7LM+IESPy7LPPJkmmTJmSyy67LE8//XSeeuqpXHrppZkyZUq3j+tt3SlTpuTLX/5ypk6dmilTpuS8887LhAkTuoptT/bbb7+ce+65XffXpfwDQG/M5ALwirAul/zpTxMmTMjYsWMzZ86czJ49Ox/72Mdy2mmn5dlnn83hhx+ecePG5fDDD8/f/d3f5ZxzzsnFF1+cz3zmM3nve9+bb33rW3nnO9/ZZ1mOPvrojB07NhMnTszs2bMzc+bM7LrrrkmSj3zkI93uqpwkEydO7HHdKVOm5PTTT88ee+yRjTfeOBtuuGGPZXlN55xzTj7xiU9k7NixWbFiRaZOnZrzzjuvj75TAF6JSq213Rn63OTJk+vqs1EC8Mq0aNGirl1laR4/36Fjr3P36nb8+uOuH+AkQJOUUhbUWid3t8zuygAAADSG3ZUBoKF22223F5y5+fvf/3523nnnXh/36KOPZsaMGS8Yv+qqq7Llllv2aUYA6GtKLgA01K9//euX9Lgtt9zSCaAAGLLsrgwAAEBjKLkAAAA0hpILAABAYyi5ANBPhg0blvHjx3d9nXnmmb2uf8011+SGG27ouj9z5sxcfPHF/R3zBebPn59PfvKTA/66ANAXnHgKgFeEP5za+xmFX6w3/NPta11n5MiRL+oETtdcc0022WST7Lnnni8j2cs3efLkTJ7c7aUHAWDQM5MLAANs1KhReeSRR5J0zppOnz49ixcvznnnnZevfvWrGT9+fK699tokybx587LnnnvmjW98Y9es7rJlyzJjxoxMnDgxO++8cy6//PIkyeLFizNmzJj83d/9XXbcccfst99+Wb58eZLk/PPPzy677JJx48bl0EMPzdNPP50k+fGPf5yddtop48aNy9SpU5N0lu0DDjggSXLTTTdljz32yIQJE7LnnnvmN7/5zcC9UQDwEii5ANBPli9f/pzdlS+66KIe1x01alSOOeaYHH/88eno6MiUKVOSJA888ECuu+66/N//+39z4oknJkk23HDDXHrppbnlllvyy1/+Mp/+9KdTa02S3HPPPfnEJz6RO++8M5tttlkuueSSJMkhhxySm2++OQsXLsyYMWPyne98J0ly6qmn5mc/+1kWLlyYK6644gW5/uZv/ibXXnttbr311px66qk56aST+vQ9AoC+ZndlAOgnL3Z35e68+93vznrrrZcddtghDz74YJKk1pqTTjop8+bNy3rrrZelS5d2LRs9enTGjx+fJJk0aVIWL16cJLnjjjvyj//4j/nTn/6UZcuW5e1vf3uSZK+99srMmTPz3ve+N4cccsgLXv/xxx/PUUcdlXvuuSellDz77LMv6/sBgP5mJhcABtjw4cOzatWqJMkzzzzT67obbLBB1+3Vs7WzZ8/Oww8/nAULFqSjoyPbbLNN1/Osuf6wYcOyYsWKJJ0nsfr617+e22+/PSeffHLX+uedd15OO+203H///Zk0aVIeffTR57z+F77whey9996544478pOf/GSteQGg3ZRc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"/>

도표를 통해 adoption(입양)은 대부분 연령이 낮은 동물에게서 나타남을 알 수 있다(연령과 분석의 target인  outcometype은 상관관계가 있다)



```python
plt.figure(figsize=(16,8))
sns.boxplot(alldata["OutcomeType"],alldata["AgeuponOutcome"],showfliers=False,hue=alldata["SexuponOutcome"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variables as keyword args: x, y. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='OutcomeType', ylabel='AgeuponOutcome'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA7kAAAHhCAYAAACr5XlzAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAABWUElEQVR4nO3deZhU1Zn48e/bgCwiooJobLfYbiCLiltcgjouyThqjEpMMooxYaLGjplMMjpx3IIzJnEiac3yM8GoiYm70RBNRIW4K6CICipNRG2DiCCbNGuf3x91u9NAN3Q1XdV08f08Tz9d99xz7nmruFTXW+fccyOlhCRJkiRJpaCsvQOQJEmSJKmtmORKkiRJkkqGSa4kSZIkqWSY5EqSJEmSSoZJriRJkiSpZJjkSpIkSZJKRuf2DqAQ+vTpk3bbbbf2DkOSJEmSVACTJ0/+MKXUt6l9JZnk7rbbbkyaNKm9w5AkSZIkFUBEvN3cPqcrS5IkSZJKhkmuJEmSJKlkmORKkiRJkkpGSV6TK0mSJEn1Vq5cSU1NDcuWLWvvUJSnbt26UV5eTpcuXVrcxiRXkiRJUkmrqalhq622YrfddiMi2jsctVBKiXnz5lFTU8Puu+/e4nZOV5YkSZJU0pYtW8Z2221ngtvBRATbbbdd3iPwJrmSJEmSSp4JbsfUmn83k1xJkiRJWss111zDgAEDGDRoEEOGDOH5559v75CatHDhQs4++2wqKirYY489OPvss1m4cOEG240ePZqlS5cWIcLiM8mVJEmSpEaeffZZxo4dy4svvsjUqVN59NFH2Xnnnds7rCadd955fPKTn6S6upqZM2ey++6789WvfnWD7UxyJUmSJGkzMXv2bPr06UPXrl0B6NOnD5/4xCeYPHkyn/70pznwwAM54YQTmD17NgsXLmTvvffmjTfeAOCss87il7/8JQA9e/ZsOOY999zDiBEjABgxYgRf//rXGTp0KHvttRdjx44FctcOn3vuuQwcOJD999+f8ePHA3DLLbdw2mmnceKJJ7Lnnnvy3e9+F4Dq6momT57Mf//3fzf0c/nllzNp0iRmzpzJhAkTOOmkkxr2feMb3+CWW26hqqqKv//97xx99NEcffTRAPz5z3/mgAMOYPDgwRx77LEAzJ8/n1NPPZVBgwZx6KGHMnXqVACuvPJKzjnnHI488kh23XVX7rvvPr773e8ycOBATjzxRFauXAnQ5OtVDAVLciNi74iY0uhnUURcHBHbRsS4iJiR/d4mqx8RURUR1RExNSIOaHSsc7L6MyLinELFLEmSJEnHH3887777LnvttRcXXHABf/3rX1m5ciUXXXQR99xzD5MnT+YrX/kK3/ve99h666258cYbGTFiBHfccQcfffQRX/va1zbYx6xZs3jhhRf405/+xNe//nWWLVvGT3/6UyKCV155hd///vecc845DYsuTZkyhTvvvJNXXnmFO++8k3fffZdp06YxZMgQOnXq1HDcTp06MWTIEF577bVm+66srOQTn/gE48ePZ/z48cydO5evfe1r3Hvvvbz88svcfffdAFxxxRXsv//+TJ06lf/5n//h7LPPbjjGzJkzefzxx3nwwQf58pe/zNFHH80rr7xC9+7d+dOf/tTs61UMBbuFUErpDWAIQER0At4D7gcuAR5LKV0bEZdk2/8JfAbYM/s5BPg5cEhEbAtcAQwFEjA5Ih5MKX1UqNglSZIkbb569uzJ5MmTefLJJxk/fjzDhw/nsssu49VXX+W4444DYPXq1ey4444AHHfccdx9991ceOGFvPzyyy3q48wzz6SsrIw999yTT37yk7z++us89dRTXHTRRQDss88+7Lrrrrz55psAHHvssWy99dYA9O/fn7fffrvNnu9zzz3HUUcd1XCbnm233RaAp556invvvReAY445hnnz5rFo0SIAPvOZz9ClSxcGDhzI6tWrOfHEEwEYOHAgs2bN4o033mj29Sq0Yt0n91hgZkrp7Yg4BRiWld8KTCCX5J4C3JZSSsBzEdE7InbM6o5LKc0HiIhxwInA74sUuyRJkqTNTKdOnRg2bBjDhg1j4MCB/PSnP2XAgAE8++yz69Stq6tj+vTp9OjRg48++ojy8nJgzZWB174NztqrBm9oFeH6qdP1sa1atYr+/fszZcoU6urqKCsra4hlypQp9O/fn/fff5+6urpmY9gY9fGUlZXRpUuXhvjLyspYtWoVKaVmX69CK9Y1uV/gH0lpv5RS/WTs94F+2eOdgHcbtanJyporlyRJkqQ298YbbzBjxoyG7SlTprDvvvsyd+7chqRt5cqVDVOCr7/+evbdd19+97vfce655zZck9qvXz+mT59OXV0d999//xp93H333dTV1TFz5kz+9re/sffee3PkkUdy++23A/Dmm2/yzjvvsPfeezcbZ0VFBfvvvz+jRo1qKBs1ahQHHHAAFRUV7LrrrkybNo3ly5ezYMECHnvssYZ6W221FYsXLwbg0EMP5YknnuCtt94CctfiAmvEM2HCBPr06UOvXr1a9Bruvffezb5ehVbwkdyI2AI4Gbh07X0ppRQRqY36GQmMBNhll13a4pCSJEmSNkNLlizhoosuYsGCBXTu3JmKigpuuukmRo4cSWVlJQsXLmTVqlVcfPHFdO7cmV/96le88MILbLXVVhx11FGMGjWKq666imuvvZaTTjqJvn37MnToUJYsWdLQxy677MLBBx/MokWL+MUvfkG3bt244IILOP/88xk4cCCdO3fmlltuWWMEtyljxozhoosuYo899gDgsMMOY8yYMQDsvPPOnHnmmey3337svvvu7L///g3tRo4cyYknnthwbe5NN93EaaedRl1dHdtvvz3jxo3jyiuv5Ctf+QqDBg2iR48e3HrrrS1+DbfYYgvuueeedV6vAQMG5PNP0SqRmx1cwA5y05MvTCkdn22/AQxLKc3OpiNPSCntHRH/L3v8+8b16n9SSv+Wla9RrylDhw5NkyZNKuTTkiRJktRBTJ8+nX333be9w2gwYsQITjrpJE4//fT2DqVDaOrfLyImp5SGNlW/GNOVz2LN62cfBOpXSD4HeKBR+dnZKsuHAguzac1/AY6PiG2ylZiPz8okSZIkSVpDQacrR8SWwHHAvzUqvha4KyLOA94GzszKHwI+C1QDS4FzAVJK8yPi+8DErN7V9YtQSep4qqqqqK6ubnJfTU0NQMNiDWurqKigsrKyYLFJkiQVwy233NLeIZS0gia5KaWPge3WKptHbrXltesm4MJmjnMzcHMhYpS06aitrW3vECRJktTBFesWQpIEsN6R2Pp9VVVVxQpHkiRJJaZYtxCSJEmSJKngTHIlSZIkSSXDJFeSJEmSCiwi+Pa3v92wfd1113HllVe26lgLFizgZz/7WRtFtq4rr7yS6667rsnyiFhjEdHRo0cTEWzoFq7Dhg3bYJ224jW5kiRJkjYrF178H8z5sO1u2NKvz7b8dPS6SWFjXbt25b777uPSSy+lT58+G9VffZJ7wQUXtLhNSomUEmVlGzfOOXDgQO644w4uu+wyAO6++24GDBiwUcdsa47kSpIkSdqszPlwPm/tOKzNflqSMHfu3JmRI0dy/fXXr7Nv7ty5fP7zn+eggw7ioIMO4umnnwbWHVHdb7/9mDVrFpdccgkzZ85kyJAhfOc73wHgRz/6EQcddBCDBg3iiiuuAGDWrFnsvffenH322ey33368++67TdYDuOaaa9hrr7044ogjeOONN5p9HqeeeioPPPAAADNnzmTrrbdeI2k///zzGTp0KAMGDFjj+I098sgjHHbYYRxwwAGcccYZLFmyZIOvXz5MciVJkiSpCC688EJuv/12Fi5cuEb5N7/5Tb71rW8xceJE7r33Xr761a+u9zjXXnste+yxB1OmTOFHP/oRjzzyCDNmzOCFF15gypQpTJ48mSeeeAKAGTNmcMEFF/Daa6/xxhtvNFlv8uTJ3HHHHUyZMoWHHnqIiRMnNtt3r1692HnnnXn11Ve54447GD58+Br7r7nmGiZNmsTUqVP561//ytSpU9fY/+GHHzJq1CgeffRRXnzxRYYOHcqPf/zjfF7GDXK6siRJkiQVQa9evTj77LOpqqqie/fuDeWPPvoo06ZNa9hetGhRXqObjzzyCI888gj7778/AEuWLGHGjBnssssu7Lrrrhx66KHrrbd48WI+97nP0aNHDwBOPvnk9fb3hS98gTvuuIO//OUvPPbYY/z6179u2HfXXXdx0003sWrVKmbPns20adMYNGhQw/7nnnuOadOmcfjhhwOwYsUKDjvssBY/15YwyZUkSZKkIrn44os54IADOPfccxvK6urqeO655+jWrdsadTt37kxdXV3D9rJly5o8ZkqJSy+9lH/7t39bo3zWrFlsueWWG6w3evTovJ7DSSedxHe+8x2GDh1Kr169GsrfeustrrvuOiZOnMg222zDiBEj1ok5pcRxxx3H73//+7z6zIfTlSVJkiSpSLbddlvOPPNMxowZ01B2/PHHc8MNNzRsT5kyBYDddtuNF198EYAXX3yRt956C4CtttqKxYsXN9Q/4YQTuPnmmxtGf9977z0++OCDdfpurt5RRx3FH/7wB2pra1m8eDF//OMf1/scevTowQ9+8AO+973vrVG+aNEittxyS7beemvmzJnDww8/vE7bQw89lKeffrphheaPP/6YN998c7395cuRXEmSJEkqom9/+9vceOONDdtVVVVceOGFDBo0iFWrVnHUUUfxi1/8gs9//vPcdtttDBgwgEMOOYS99toLgO22247DDz+c/fbbj8985jP86Ec/Yvr06Q3Tfnv27Mlvf/tbOnXqtEa/xx9/fJP1DjjgAIYPH87gwYPZfvvtOeiggzb4HL7whS+sUzZ48GD2339/9tlnH3beeeeGKcmN9e3bl1tuuYWzzjqL5cuXAzBq1KiG59YWIqXUZgfbVAwdOjQV6x5MktpOZWUlkHujlyRJaivTp09n3333bdhuj1sIqfXW/vcDiIjJKaWhTdV3JFeSJEnSZsWEtLR5Ta4kSZIkqWSY5EqSJEmSSoZJriRJkiSpZJjkSpIkSZJKhkmuJEmSJKlkmORKkiRJUoFdc801DBgwgEGDBjFkyBCef/75doljt91248MPP2yyfODAgQwZMoQhQ4bwzDPPFCyGYcOGUchbvnoLIWkzVlVVRXV1dZP7ampqACgvL29yf0VFRcN9bSVJkjqSS791IQvnvd9mx9t6ux343+t/2uz+Z599lrFjx/Liiy/StWtXPvzwQ1asWNFm/beV8ePH06dPn/YOY6OZ5EpqUm1tbXuHIEmSVBAL573PJRVvttnxrm16zKDB7Nmz6dOnD127dgVYI5HcbbfdOPPMM3n44Yfp3r07v/vd76ioqOCPf/wjo0aNYsWKFWy33Xbcfvvt9O3bl7333ptnnnmGvn37UldXx1577cWzzz4LwNe//nXeeecdAEaPHs3hhx/OvHnzOOuss3jvvfc47LDDSCm1+HnNnDmTCy+8kLlz59KjRw9++ctfss8++zBixAi6d+/OSy+9xAcffMDNN9/MbbfdxrPPPsshhxzCLbfcAsD555/PxIkTqa2t5fTTT+eqq65ap49HHnmEK664guXLl7PHHnvw61//mp49e7Y4xqaY5EqbsfWNxNbvq6qqKlY4kiRJJen444/n6quvZq+99uKf/umfGD58OJ/+9Kcb9m+99da88sor3HbbbVx88cWMHTuWI444gueee46I4Fe/+hU//OEP+b//+z++/OUvc/vtt3PxxRfz6KOPMnjwYPr27csXv/hFvvWtb3HEEUfwzjvvcMIJJzB9+nSuuuoqjjjiCC6//HL+9Kc/MWbMmGbjPProo+nUqRNdu3bl+eefZ+TIkfziF79gzz335Pnnn+eCCy7g8ccfB+Cjjz7i2Wef5cEHH+Tkk0/m6aef5le/+hUHHXQQU6ZMYciQIVxzzTVsu+22rF69mmOPPZapU6cyaNCghv4+/PBDRo0axaOPPsqWW27JD37wA3784x9z+eWXb9TrbZIrSZIkSQXUs2dPJk+ezJNPPsn48eMZPnw41157LSNGjADgrLPOavj9rW99C8hdOjZ8+HBmz57NihUr2H333QH4yle+wimnnMLFF1/MzTffzLnnngvAo48+yrRp0xr6XLRoEUuWLOGJJ57gvvvuA+Cf//mf2WabbZqNs/F05SVLlvDMM89wxhlnNOxfvnx5w+N/+Zd/ISIYOHAg/fr1Y+DAgQAMGDCAWbNmMWTIEO666y5uuukmVq1axezZs5k2bdoaSe5zzz3HtGnTOPzwwwFYsWIFhx12WCte4TWZ5EqSJElSgXXq1Ilhw4YxbNgwBg4cyK233tqQ5EZEQ736xxdddBH//u//zsknn8yECRO48sorAdh5553p168fjz/+OC+88AK33347AHV1dTz33HN069atTeKtq6ujd+/eTJkypcn99VOvy8rKGh7Xb69atYq33nqL6667jokTJ7LNNtswYsQIli1btsYxUkocd9xx/P73v2+TmBtiaNOjSZIkSZLW8MYbbzBjxoyG7SlTprDrrrs2bN95550Nv+tHMhcuXMhOO+0EwK233rrG8b761a/y5S9/mTPOOINOnToBuSnRN9xwwxp9ABx11FH87ne/A+Dhhx/mo48+alHMvXr1Yvfdd+fuu+8Gcgnpyy+/3OLnvGjRIrbccku23npr5syZw8MPP7xOnUMPPZSnn366YSHUjz/+mDff3PhrpU1yJUmSJKmAlixZwjnnnEP//v0ZNGgQ06ZNaxiZhdz1rYMGDeInP/kJ119/PQBXXnklZ5xxBgceeOA6Kx6ffPLJLFmypGGqMuTWUZk0aRKDBg2if//+/OIXvwDgiiuu4IknnmDAgAHcd9997LLLLi2O+/bbb2fMmDEMHjyYAQMG8MADD7S47eDBg9l///3ZZ599+OIXv9gwJbmxvn37csstt3DWWWcxaNAgDjvsMF5//fUW99GcyGd1rY5i6NChqZD3XZI2B+2x8JSLXUmSpEKYPn06++67b8N2sW8htD677bYbkyZNyuvWPZMmTeJb3/oWTz75ZKv67GjW/vcDiIjJKaWhTdX3mlxJkiRJm5XWJqSbgmuvvZaf//znDdfial1OV5YkSZKkdjJr1qy8RnEvueQS3n77bY444ogCRtWxmeRKkiRJkkqGSa4kSZIkqWSY5EqSJEmSSoZJriRJkiSpZJjkSpIkSVKB9ezZc4N1Ro8ezdKlS1t1/ClTpvDQQw81uW/ChAlEBL/61a/WqB8RXHfddes97pVXXrnBOpsabyEkSZIkabPyjW9/gznz5rTZ8fpt148b/+/GjT7O6NGj+fKXv0yPHj3ybjtlyhQmTZrEZz/72Sb377ffftx111189atfBeD3v/89gwcP3qh4N1UmuZIkSZI2K3PmzeHvB/697Q44ueVVJ0yYwJVXXkmfPn149dVXOfDAA/ntb3/LDTfcwN///neOPvpo+vTpw/jx4zn//POZOHEitbW1nH766Vx11VUATJw4kW9+85t8/PHHdO3alXHjxnH55ZdTW1vLU089xaWXXsrw4cPX6HfXXXdl0aJFzJkzh+23354///nPayTEv/zlL7nppptYsWIFFRUV/OY3v1kn2Z45cyYXXnghc+fOpUePHvzyl79kn332af3rViAmuZIkSZJURC+99BKvvfYan/jEJzj88MN5+umnqays5Mc//jHjx49vuG/uNddcw7bbbsvq1as59thjmTp1Kvvssw/Dhw/nzjvv5KCDDmLRokX06NGDq6++mkmTJnHjjc2PKJ9++uncfffd7L///hxwwAF07dq1Yd9pp53G1772NQAuu+wyxowZw0UXXbRG+5EjR/KLX/yCPffck+eff54LLriAxx9/vACv0MYxyZUkSZKkIjr44IMpLy8HYMiQIcyaNYsjjjhinXp33XUXN910E6tWrWL27NlMmzaNiGDHHXfkoIMOAqBXr14t7vfMM89k+PDhvP7665x11lk888wzDfteffVVLrvsMhYsWMCSJUs44YQT1mi7ZMkSnnnmGc4444yGsuXLl+f1vIvFJFeSJEmSiqjxCGqnTp1YtWrVOnXeeustrrvuOiZOnMg222zDiBEjWLZs2Ub1u8MOO9ClSxfGjRvHT37ykzWS3BEjRvCHP/yBwYMHc8sttzBhwoQ12tbV1dG7d2+mTJmyUTEUg6srS5IkSdImYKuttmLx4sUALFq0iC233JKtt96aOXPm8PDDDwOw9957M3v2bCZOnAjA4sWLWbVq1Rpt1+fqq6/mBz/4AZ06dVqjfPHixey4446sXLmS22+/fZ12vXr1Yvfdd+fuu+8GIKXEyy+/vFHPt1BMciVJkiRpEzBy5EhOPPFEjj76aAYPHsz+++/PPvvswxe/+EUOP/xwALbYYgvuvPNOLrroIgYPHsxxxx3HsmXLOProo5k2bRpDhgzhzjvvbLaPT33qU5x66qnrlH//+9/nkEMO4fDDD292Manbb7+dMWPGMHjwYAYMGMADDzzQJs+7rUVKqb1jaHNDhw5NkyZNau8wpA6tsrISgKqqqpLuU5Iklb7p06ez7777NmxvqrcQUtPW/vcDiIjJKaWhTdX3mlxJkiRJmxUT0tLmdGVJkiRJUskwyZUkSZIklQyTXEmSJElSyTDJlSRJkiSVDJNcSZIkSVLJKGiSGxG9I+KeiHg9IqZHxGERsW1EjIuIGdnvbbK6ERFVEVEdEVMj4oBGxzknqz8jIs4pZMySJEmS1NZ69uy5wTqjR49m6dKlrTr+lClTeOihh5rcN2HCBLbeemuGDBnCkCFD+Kd/+qdW9dESs2bNYr/99ivY8Vui0LcQ+gnw55TS6RGxBdAD+C/gsZTStRFxCXAJ8J/AZ4A9s59DgJ8Dh0TEtsAVwFAgAZMj4sGU0kcFjl2SJElSCfruN77BgjkftNnxevfbnh/euPG3JRo9ejRf/vKX6dGjR95tp0yZwqRJk/jsZz/b5P4jjzySsWPHbmyIHULBktyI2Bo4ChgBkFJaAayIiFOAYVm1W4EJ5JLcU4DbUkoJeC4bBd4xqzsupTQ/O+444ETg94WKXZIkSVLpWjDnA740Z06bHe/2POpOmDCBK6+8kj59+vDqq69y4IEH8tvf/pYbbriBv//97xx99NH06dOH8ePHc/755zNx4kRqa2s5/fTTueqqqwCYOHEi3/zmN/n444/p2rUr48aN4/LLL6e2tpannnqKSy+9lOHDh28wlt/+9rdUVVWxYsUKDjnkEH72s5/RqVMnevbsyfnnn89DDz3EjjvuyP/8z//w3e9+l3feeYfRo0dz8sknM2vWLP71X/+Vjz/+GIAbb7yRT33qU2scf/Xq1VxyySVMmDCB5cuXc+GFF/Jv//ZvebxarVPI6cq7A3OBX0fESxHxq4jYEuiXUpqd1Xkf6Jc93gl4t1H7mqysuXJJkiRJ6nBeeuklRo8ezbRp0/jb3/7G008/TWVlJZ/4xCcYP34848ePB+Caa65h0qRJTJ06lb/+9a9MnTqVFStWMHz4cH7yk5/w8ssv8+ijj7Llllty9dVXM3z4cKZMmdJkgvvkk082TFe+5pprmD59OnfeeSdPP/00U6ZMoVOnTtx+ey5d//jjjznmmGN47bXX2GqrrbjssssYN24c999/P5dffjkA22+/PePGjePFF1/kzjvvpLKycp0+x4wZw9Zbb83EiROZOHEiv/zlL3nrrbcK+MrmFHK6cmfgAOCilNLzEfETclOTG6SUUkSktugsIkYCIwF22WWXtjikJEmSJLW5gw8+mPLycgCGDBnCrFmzOOKII9apd9ddd3HTTTexatUqZs+ezbRp04gIdtxxRw466CAAevXq1aI+156ufOONNzJ58uSG49TW1rL99tsDsMUWW3DiiScCMHDgQLp27UqXLl0YOHAgs2bNAmDlypV84xvfaEiQ33zzzXX6fOSRR5g6dSr33HMPAAsXLmTGjBnsvvvuLYq5tQqZ5NYANSml57Pte8gluXMiYseU0uxsOnL9ZPj3gJ0btS/Pyt7jH9Ob68snrN1ZSukm4CaAoUOHtkniLEmSJEltrWvXrg2PO3XqxKpVq9ap89Zbb3HdddcxceJEttlmG0aMGMGyZcvaLIaUEueccw7/+7//u86+Ll26EBEAlJWVNcRbVlbWEOv1119Pv379ePnll6mrq6Nbt25N9nHDDTdwwgkntFncLVGw6coppfeBdyNi76zoWGAa8CBQv0LyOcAD2eMHgbOzVZYPBRZm05r/AhwfEdtkKzEfn5VJkiRJUsnYaqutWLx4MQCLFi1iyy23ZOutt2bOnDk8/PDDAOy9997Mnj2biRMnArB48WJWrVq1RtuWOPbYY7nnnnv44IPcmOP8+fN5++23W9x+4cKF7LjjjpSVlfGb3/yG1atXr1PnhBNO4Oc//zkrV64E4M0332y4hreQCr268kXA7dnKyn8DziWXWN8VEecBbwNnZnUfAj4LVANLs7qklOZHxPeBiVm9q+sXoZIkSZKkUjFy5EhOPPHEhmtz999/f/bZZx923nlnDj/8cCA3lfjOO+/koosuora2lu7du/Poo49y9NFHc+211zJkyJAWLTzVv39/Ro0axfHHH09dXR1dunThpz/9KbvuumuLYr3gggv4/Oc/z2233caJJ57IlltuuU6dr371q8yaNYsDDjiAlBJ9+/blD3/4Q96vS74it5hxaRk6dGiaNGlSe4chdWj1iwdUVVWVdJ+SJKn0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"/>

중성화 되었을 때, 다른 OutcomeType에 비해 입양비율이 현저히 높음을 알 수 있다.

따라서 train과정에 SexuponOutcome  column을 포함 시켜야 하며, column을 포함하지 않았을때 score가 개선되지 않고 더 나빠짐을 알수있다.

CatBoostModel에서 score 0.73824였던 조건에 SexuponOutcome 컬럼만 삭제하였더니 score 0.81490으로 변경되었다.



```python
plt.figure(figsize=(16,8))
sns.countplot(alldata["SexuponOutcome"],hue=alldata["OutcomeType"])
```

<pre>
/opt/conda/lib/python3.7/site-packages/seaborn/_decorators.py:43: FutureWarning: Pass the following variable as a keyword arg: x. From version 0.12, the only valid positional argument will be `data`, and passing other arguments without an explicit keyword will result in an error or misinterpretation.
  FutureWarning
</pre>
<pre>
<AxesSubplot:xlabel='SexuponOutcome', ylabel='count'>
</pre>
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA7kAAAHgCAYAAABguarWAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjUuMSwgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/YYfK9AAAACXBIWXMAAAsTAAALEwEAmpwYAAA9wklEQVR4nO3deXxV1b3//9eHgILiLHqd+gUttkGBAEEmQZA6tFpnra1asLVW6/ytWod6HYpev19rbdW2VltEWooDXtT67a9OiOBUTDQoggpaUNCriCMKlmH9/jg7MUACAXISsnk9H4/zyN5rr73XOif7JOd91h4ipYQkSZIkSXnQqrk7IEmSJElSYzHkSpIkSZJyw5ArSZIkScoNQ64kSZIkKTcMuZIkSZKk3DDkSpIkSZJyo3Vzd6AYtt9++9SxY8fm7oYkSZIkqQgqKyvfTyl1qGtZLkNux44dqaioaO5uSJIkSZKKICLm1LfMw5UlSZIkSblhyJUkSZIk5YYhV5IkSZKUG7k8J1eSpCVLljB37lwWL17c3F1RI2vbti277rorbdq0ae6uSJI2QIZcSVIuzZ07ly222IKOHTsSEc3dHTWSlBILFixg7ty5dOrUqbm7I0naAHm4siQplxYvXsx2221nwM2ZiGC77bZzhF6SVC9DriQptwy4+eTvVZK0OoZcSZLW09y5czn88MPp3Lkze+yxB+eccw7//ve/V7vONddc00S9W9GRRx5JWVkZX/3qV9lqq60oKyujrKyMp59+uln6I0lSYzPkSpK0HlJKHHXUURxxxBHMnDmT1157jYULF3LppZeudr3mCrnjx4+nqqqKP/7xjwwcOJCqqiqqqqro379/s/RHkqTGZsiVJGk9TJgwgbZt23LyyScDUFJSwg033MDIkSP53e9+x5lnnllT99BDD2XixIlcdNFFLFq0iLKyMk444QQARo8eTbdu3ejevTsnnXQSALNnz2b//fenW7duDB06lDfffBOA4cOHc/rpp9O3b1923313Jk6cyA9+8ANKS0sZPnx4TXsPP/ww/fr1o2fPnhx77LEsXLiwzucwaNAgqqqqaub33Xdfpk6dyhVXXMFJJ51Ev3796Ny5M7fddltNneuuu47evXvTrVs3Lr/88kZ5LSVJagyGXEmS1sPLL79Mr169Vijbcsst+cpXvsLSpUvrXOfaa6+lXbt2VFVVMWbMGF5++WVGjBjBhAkTmDp1Kr/5zW8AOOussxg2bBgvvvgiJ5xwAmeffXbNNj788EOeeeYZbrjhBg477DDOO+88Xn75ZV566SWqqqp4//33GTFiBI8++ijPP/885eXl/OpXv6qzPz/84Q8ZNWoUAK+99hqLFy+me/fuALz44otMmDCBZ555hquuuoq3336bhx9+mJkzZzJlyhSqqqqorKxk0qRJ6/tSSpLUKAy5kiQ1swkTJnDsscey/fbbA7DtttsC8Mwzz/C9730PgJNOOoknn3yyZp1vf/vbRARdu3Zlxx13pGvXrrRq1Yq99tqL2bNn8+yzzzJ9+nQGDBhAWVkZd9xxB3PmzKmz/WOPPZYHH3yQJUuWMHLkyBVGgw8//HDatWvH9ttvz5AhQ5gyZQoPP/wwDz/8MD169KBnz5688sorzJw5s0ivjiRJa8f75EqStB66dOnCuHHjVij75JNPePPNN9l6661Zvnx5TXlj3vZm0003BaBVq1Y109XzS5cupaSkhAMOOICxY8eucVubbbYZBxxwAPfffz933303lZWVNctWvpJxRJBS4uKLL+bHP/5xIz0bSZIajyO5kiSth6FDh/L5558zevRoAJYtW8ZPf/pThg8fzu67705VVRXLly/nrbfeYsqUKTXrtWnThiVLlgCw//77c88997BgwQIAPvjgAwD69+/PnXfeCcCYMWMYOHBgg/vVt29fnnrqKWbNmgXAZ599xmuvvVZv/VNOOYWzzz6b3r17s80229SU33///SxevJgFCxYwceJEevfuzUEHHcTIkSNrzvGdN28e7733XoP7JklSMTmSK0nSeogIxo8fz09+8hN+8YtfsHz5cr71rW9xzTXXsMkmm9CpUye6dOlCaWkpPXv2rFnv1FNPpVu3bvTs2ZMxY8Zw6aWXst9++1FSUkKPHj0YNWoUN910EyeffDLXXXcdHTp04Pbbb29wvzp06MCoUaP47ne/yxdffAHAiBEj2HPPPeus36tXL7bccsuaC2hV69atG0OGDOH999/nsssuY+edd2bnnXdmxowZ9OvXD4D27dvzl7/8hR122GFtXz5JkhpdpJSauw+Nrry8PFVUVDR3NyRJzWjGjBmUlpY2dzdajLfffpvBgwfzyiuv0KpV4UCvK664gvbt23P++ec3c+9W5e9XkjZuEVGZUiqva5mHK0uStJEbPXo0ffr04eqrr64JuJIktVSO5EqScsmRvnzz9ytJGzdHciVJkiRJGwUvPLWRG3DTgCZv86mznmryNiVJkiRtHBzJlSRJkiTlhiO5knKhqY9K8IgESZKkDZMjuZIkSZKk3HAkV5K0Ueh1wehG3V7ldd9fY52SkhK6du3K0qVL6dSpE3/+85/Zeuut661/3333seeee9KlS5dG7OmqrrnmGi655JKitiFJUnNxJFeSpCJp164dVVVVTJs2jW233Zbf/va3q61/3333MX369LVqY+nSpWvdr2uuuWat12lO6/IcJUkbL0OuJElNoF+/fsybNw+A119/nYMPPphevXoxcOBAXnnlFZ5++mkeeOABLrjgAsrKynj99dcZPHgw1fd9f//99+nYsSMAo0aN4rDDDmP//fdn6NChjBo1iqOOOoqDDz6Yzp07c+GFF9bbj4suuohFixZRVlbGCSecAMCvfvUr9t57b/bee29+/etfr/Z51FX3uuuu48YbbwTgvPPOY//99wdgwoQJNW20b9+eSy+9lO7du9O3b1/effddAObPn8/RRx9N79696d27N089VTjf/YorruCkk05iwIABnHTSSWv5akuSNmaGXEmSimzZsmU89thjHHbYYQCceuqp3HTTTVRWVvLLX/6Sn/zkJ/Tv35/DDjuM6667jqqqKvbYY4/VbvP5559n3LhxPPHEEwBUVVVx11138dJLL3HXXXfx1ltv1bnetddeWzPCPGbMGCorK7n99tv55z//ybPPPsttt93GCy+8UOe69dUdOHAgkydPBqCiooKFCxeyZMkSJk+ezKBBgwD47LPP6Nu3L1OnTmXQoEHcdtttAJxzzjmcd955PPfcc9x7772ccsopNe1Nnz6dRx99lLFjx67Fqy1J2th5Tq4kSUVSPWI6b948SktLOeCAA1i4cCFPP/00xx57bE29L774Yq23fcABB7DtttvWzA8dOpStttoKgC5dujBnzhx22223NW7nySef5Mgjj2TzzTcH4KijjmLy5Mn06NGjwXVPP/10Kisr+eSTT9h0003p2bMnFRUVTJ48uWaEd5NNNuHQQw8FoFevXjzyyCMAPProoyscov3JJ5+wcOFCAA477DDatWu31q+NJGnjZsiVJKlIqkdMP//8cw466CB++9vfMnz4cLbeemuqqqrWuH7r1q1Zvnw5AIsXL15hWXXQrLbpppvWTJeUlDTpeaxt2rShU6dOjBo1iv79+9OtWzcef/xxZs2aRWlpaU2diFilf8uXL+fZZ5+lbdu2q2x35ecoSVJDeLiyJElFttlmm3HjjTdy/fXXs9lmm9GpUyfuueceAFJKTJ06FYAtttiCTz/9tGa9jh07UllZCcC4ceMarT9t2rRhyZIlAAwcOJD77ruPzz//nM8++4zx48czcODAOtdbXd2BAwfyy1/+kkGDBjFw4EBuueUWevToURNs63PggQdy00031cw3JPxLkrQ6juRKkjYKDbnlTzH16NGDbt26MXbsWMaMGcPpp5/OiBEjWLJkCccffzzdu3fn+OOP50c/+hE33ngj48aN4/zzz+e4447j1ltv5ZBDDmm0vpx66ql069aNnj17MmbMGIYPH84+++wDwCmnnFLnocoAPXv2rLfuwIEDufrqq+nXrx+bb745bdu2rTcs13bjjTdyxhln0K1bN5YuXcqgQYO45ZZbGumZSpI2RpFSau4+NLry8vJUfTVKrd6AmwY0eZtPnfVUk7ep/Gvqfdn9eMM3Y8aMmkNllT/+fiVp4xYRlSml8rqWebiyJEmSJCk3inq4ckTMBj4FlgFLU0rlEbEtcBfQEZgNHJdS+jAKJ+38BvgW8DkwPKX0fLadYcDPs82OSCndUcx+S5KUB3369Fnlys1//vOf6dq162rXW7BgAUOHDl2l/LHHHmO77bZr1D5KktTYmuKc3CEppfdrzV8EPJZSujYiLsrmfwZ8E+icPfoAvwf6ZKH4cqAcSEBlRDyQUvqwCfouSVKL9c9//nOd1ttuu+28AJQkqcVqjsOVDweqR2LvAI6oVT46FTwLbB0ROwEHAY+klD7Igu0jwMFN3GdJkiRJUgtQ7JCbgIcjojIiTs3KdkwpvZNN/w+wYza9C/BWrXXnZmX1la8gIk6NiIqIqJg/f35jPgdJkiRJUgtR7MOV900pzYuIHYBHIuKV2gtTSikiGuXyzimlW4FboXB15cbYpiRJkiSpZSnqSG5KaV728z1gPLAP8G52GDLZz/ey6vOA3WqtvmtWVl+5JEkbtJKSEsrKymoe11577WrrT5w4kaeffrpmfvjw4YwbN67Y3VxFRUUFZ599dpO3K0lSYyjaSG5EbA60Sil9mk0fCFwFPAAMA67Nft6frfIAcGZE3EnhwlMfp5TeiYiHgGsiYpus3oHAxcXqtyQpn968avVXFF5bX/nPl9ZYp127dmt1AaeJEyfSvn17+vfvvx49W3/l5eWUl9d560FJkjZ4xRzJ3RF4MiKmAlOA/5dS+geFcHtARMwEvpHNA/wdeAOYBdwG/AQgpfQB8AvguexxVVYmSVKL1LFjR95/v3DjgYqKCgYPHszs2bO55ZZbuOGGGygrK2Py5MkATJo0if79+7P77rvXjOouXLiQoUOH0rNnT7p27cr99xe+L549ezalpaX86Ec/Yq+99uLAAw9k0aJFANx222307t2b7t27c/TRR/P5558DcM8997D33nvTvXt3Bg0aBBTC9qGHHgrAlClT6NevHz169KB///68+uqrTfdCSZK0DooWclNKb6SUumePvVJKV2flC1JKQ1NKnVNK36gOrNlVlc9IKe2RUuqaUqqota2RKaWvZo/bi9VnSZIa06JFi1Y4XPmuu+6qt27Hjh057bTTOO+886iqqmLgwIEAvPPOOzz55JM8+OCDXHTRRQC0bduW8ePH8/zzz/P444/z05/+lJQKl6OYOXMmZ5xxBi+//DJbb7019957LwBHHXUUzz33HFOnTqW0tJQ//elPAFx11VU89NBDTJ06lQceeGCVfn39619n8uTJvPDCC1x11VVccskljfoaSZLU2JriPrmSJG2U1vZw5bocccQRtGrVii5duvDuu+8CkFLikksuYdKkSbRq1Yp58+bVLOvUqRNlZWUA9OrVi9mzZwMwbdo0fv7zn/PRRx+xcOFCDjroIAAGDBjA8OHDOe644zjqqKNWaf/jjz9m2LBhzJw5k4hgyZIl6/V8JEkqtua4T64kSRu11q1bs3z5cgAWL1682rqbbrppzXT1aO2YMWOYP38+lZWVVFVVseOOO9Zsp3b9kpISli5dChQuYnXzzTfz0ksvcfnll9fUv+WWWxgxYgRvvfUWvXr1YsGCBSu0f9lllzFkyBCmTZvG3/72tzX2V5Kk5mbIlSSpiXXs2JHKykqAmsOJAbbYYgs+/fTTNa7/8ccfs8MOO9CmTRsef/xx5syZs8Z1Pv30U3baaSeWLFnCmDFjaspff/11+vTpw1VXXUWHDh146623Vljv448/ZpddCrenHzVqVEOeniRJzcqQK0lSkax8Tm71ObWXX34555xzDuXl5ZSUlNTU//a3v8348eNXuPBUXU444QQqKiro2rUro0eP5utf//oa+/KLX/yCPn36MGDAgBXqX3DBBXTt2pW9996b/v3707179xXWu/DCC7n44ovp0aNHzaiwJEkbsqg+9ClPysvLU0VFxZorigE3DWjyNp8666kmb1P519T7svvxhm/GjBmUlpY2dzdUJP5+JWnjFhGVKaU673fnSK4kSZIkKTcMuZIkSZKk3DDkSpIkSZJyw5ArSZIkScoNQ64kSZIkKTcMuZIkSZKk3DDkSpJURPfddx8RwSuvvFLn8sGDB7Out70bNWoUb7/9ds38KaecwvTp09dpW5Ik5UXr5u6AJElNobHvpdzQeyWPHTuWfffdl7Fjx3LllVc2ah9GjRrF3nvvzc477wzAH//4x0bdviRJLZEjuZIkFcnChQt58skn+dOf/sSdd94JwKJFizj++OMpLS3lyCOPZNGiRTX1x44dS9euXdl777352c9+VlPevn17zjvvPPbaay+GDh3K/PnzGTduHBUVFZxwwgmUlZWxaNGiFUaFV7etSy+9lO7du9O3b1/efffdJno1JElqGoZcSZKK5P777+fggw9mzz33ZLvttqOyspLf//73bLbZZsyYMYMrr7ySyspKAN5++21+9rOfMWHCBKqqqnjuuee47777APjss88oLy/n5ZdfZr/99uPKK6/kmGOOoby8nDFjxlBVVUW7du1q2l3Ttvr27cvUqVMZNGgQt912W1O/LJIkFZUhV5KkIhk7dizHH388AMcffzxjx45l0qRJnHjiiQB069aNbt26AfDcc88xePBgOnToQOvWrTnhhBOYNGkSAK1ateI73/kOACeeeCJPPvnkattd3bY22WQTDj30UAB69erF7NmzG/15S5LUnDwnV5KkIvjggw+YMGECL730EhHBsmXLiAh69Oix3tuOiHVet02bNjXrl5SUsHTp0vXujyRJGxJHciVJKoJx48Zx0kknMWfOHGbPns1bb71Fp06d6NWrF3/9618BmDZtGi+++CIA++yzD0888QTvv/8+y5YtY+zYsey3334ALF++nHHjxgHw17/+lX333ReALbbYgk8//XSVtle3LUmS8s6RXEmSimDs2LErXPAJ4Oijj+aFF15g0aJFlJaWUlpaSq9evQDYaaeduPbaaxkyZAgpJQ455BAOP/xwADbffHOmTJnCiBEj2GGHHbjrrrsAGD58OKeddhrt2rXjmWeeqWlndduSJCnvIqXU3H1odOXl5Wld7zm4sWnsW2o0RENvuyGtjabel92PN3wzZsygtLS0ubvRKNq3b8/ChQubuxsblDz9fiVJay8iKlNK5XUt83BlSZIkSVJuGHIlSdrAOYorSVLDGXIlSZIkSblhyJUkSZIk5YYhV5IkSZKUG4ZcSZIkSVJuGHIlSSqCBQsWUFZWRllZGf/xH//BLrvsUjP/73//u1HbeuWVVygrK6NHjx68/vrrjbptSZJamtbN3QFJkprCE4P2a9Tt7TfpidUu32677aiqqgLgiiuuoH379px//vk1y5cuXUrr1o3zb/i+++7jmGOO4ec//3mD11m2bBklJSWN0r4kSRsSR3IlSWoiw4cP57TTTqNPnz5ceOGFTJkyhX79+tGjRw/69+/Pq6++CsCoUaM46qijOPjgg+ncuTMXXnghUAimw4cPZ++996Zr167ccMMN/P3vf+fXv/41v//97xkyZAgAf/nLX9hnn30oKyvjxz/+McuWLQOgffv2/PSnP6V79+4888wzzfMiSJJUZI7kSpLUhObOncvTTz9NSUkJn3zyCZMnT6Z169Y8+uijXHLJJdx7770AVFVV8cILL7Dpppvyta99jbPOOov33nuPefPmMW3aNAA++ugjtt56a0477bSakeIZM2Zw11138dRTT9GmTRt+8pOfMGbMGL7//e/z2Wef0adPH66//vrmfAkkSSoqQ64kSU3o2GOPrTlM+OOPP2bYsGHMnDmTiGDJkiU19YYOHcpWW20FQJcuXZgzZw577bUXb7zxBmeddRaHHHIIBx544Crbf+yxx6isrKR3794ALFq0iB122AGAkpISjj766GI/RUmSmpUhV5KkJrT55pvXTF922WUMGTKE8ePHM3v2bAYPHlyzbNNNN62ZLikpYenSpWyzzTZMnTqVhx56iFtuuYW7776bkSNHrrD9lBLDhg3jv/7rv1Zpu23btp6HK0nKPc/JlSSpmXz88cfssssuQOE83DV5//33Wb58OUcffTQjRozg+eefX6XO0KFDGTduHO+99x4AH3zwAXPmzGnUfkuStCEz5EqS1EwuvPBCLr74Ynr06MHSpUvXWH/evHkMHjyYsrIyTjzxxDpHa7t06cKIESM48MAD6datGwcccADvvPNOMbovSdIGKVJKzd2HRlde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"/>


```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()

category=alldata2.columns[alldata2.dtypes=='object']
for col in category:
    alldata2[col]=le.fit_transform(list(alldata2[col]))
    
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>AnimalType</th>
      <th>SexuponOutcome</th>
      <th>AgeuponOutcome</th>
      <th>Breed</th>
      <th>Color</th>
      <th>Year</th>
      <th>Month</th>
      <th>Day</th>
      <th>Hour</th>
      <th>Weekday</th>
      <th>Minute</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2910</td>
      <td>1</td>
      <td>2</td>
      <td>365</td>
      <td>1482</td>
      <td>146</td>
      <td>2014</td>
      <td>2</td>
      <td>12</td>
      <td>18</td>
      <td>2</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2265</td>
      <td>0</td>
      <td>3</td>
      <td>365</td>
      <td>775</td>
      <td>184</td>
      <td>2013</td>
      <td>10</td>
      <td>13</td>
      <td>12</td>
      <td>6</td>
      <td>44</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5500</td>
      <td>1</td>
      <td>2</td>
      <td>730</td>
      <td>1293</td>
      <td>97</td>
      <td>2015</td>
      <td>1</td>
      <td>31</td>
      <td>12</td>
      <td>5</td>
      <td>28</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7968</td>
      <td>0</td>
      <td>1</td>
      <td>21</td>
      <td>775</td>
      <td>47</td>
      <td>2014</td>
      <td>7</td>
      <td>11</td>
      <td>19</td>
      <td>4</td>
      <td>9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7968</td>
      <td>1</td>
      <td>2</td>
      <td>730</td>
      <td>1101</td>
      <td>311</td>
      <td>2013</td>
      <td>11</td>
      <td>15</td>
      <td>12</td>
      <td>4</td>
      <td>52</td>
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
      <th>11451</th>
      <td>7968</td>
      <td>0</td>
      <td>2</td>
      <td>60</td>
      <td>775</td>
      <td>6</td>
      <td>2014</td>
      <td>7</td>
      <td>8</td>
      <td>14</td>
      <td>1</td>
      <td>50</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>7968</td>
      <td>0</td>
      <td>0</td>
      <td>14</td>
      <td>775</td>
      <td>46</td>
      <td>2014</td>
      <td>10</td>
      <td>21</td>
      <td>12</td>
      <td>1</td>
      <td>57</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>7968</td>
      <td>0</td>
      <td>0</td>
      <td>365</td>
      <td>775</td>
      <td>156</td>
      <td>2014</td>
      <td>9</td>
      <td>29</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>5964</td>
      <td>1</td>
      <td>2</td>
      <td>2190</td>
      <td>841</td>
      <td>40</td>
      <td>2015</td>
      <td>9</td>
      <td>5</td>
      <td>17</td>
      <td>5</td>
      <td>16</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>2876</td>
      <td>1</td>
      <td>1</td>
      <td>1460</td>
      <td>1022</td>
      <td>183</td>
      <td>2014</td>
      <td>7</td>
      <td>12</td>
      <td>18</td>
      <td>5</td>
      <td>40</td>
    </tr>
  </tbody>
</table>
<p>38185 rows × 12 columns</p>
</div>



```python
train2=alldata2[:len(train)]
test2=alldata2[len(train):]
```

CatBoostClassifier score:0.74015 (score가 낮을수록 순위 향상, rfc보다는 cbc가 더 정확한 예측 모델 (오류가 발생할 경우 지속해서 보정하기 때문이다 / cbc 사용에서 분석 시간이 너무 길지 않았기 때문에 더 적합)

-범주형 변수를 처리하는데 유용

-level-wise방식

-과대적합을 방지하기 위한 기법들이 다수 포함

-데이터를 랜덤하게 셔플링하여 사용

-다른 부스팅에 비해 비교적 하이퍼파라미터 최적화가 잘 되어 있



```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier(verbose=100)
cbc.fit(train2,train["OutcomeType"])

result=cbc.predict_proba(test2)
result
```

<pre>
Learning rate set to 0.093562
0:	learn: 1.4703223	total: 71.4ms	remaining: 1m 11s
100:	learn: 0.7474971	total: 1.61s	remaining: 14.4s
200:	learn: 0.7070210	total: 3.11s	remaining: 12.4s
300:	learn: 0.6746519	total: 4.65s	remaining: 10.8s
400:	learn: 0.6461705	total: 6.18s	remaining: 9.23s
500:	learn: 0.6212625	total: 7.72s	remaining: 7.69s
600:	learn: 0.5979028	total: 9.27s	remaining: 6.16s
700:	learn: 0.5765164	total: 10.8s	remaining: 4.6s
800:	learn: 0.5570537	total: 12.3s	remaining: 3.05s
900:	learn: 0.5387021	total: 13.9s	remaining: 1.53s
999:	learn: 0.5208813	total: 15.4s	remaining: 0us
</pre>
<pre>
array([[2.81584957e-02, 2.21831975e-03, 7.79193979e-02, 2.54228354e-01,
        6.37475433e-01],
       [6.53466915e-01, 1.60713027e-04, 8.01670255e-03, 3.15979530e-01,
        2.23761391e-02],
       [4.67422684e-01, 1.03428028e-03, 1.10383341e-02, 1.11178304e-01,
        4.09326398e-01],
       ...,
       [7.02888856e-04, 6.02495713e-03, 5.35806192e-03, 9.44919865e-04,
        9.86969172e-01],
       [5.09586666e-01, 1.37543477e-03, 9.87739265e-03, 4.27844202e-01,
        5.13163049e-02],
       [8.17291724e-02, 1.49440796e-03, 1.20334687e-01, 6.12336480e-01,
        1.84105253e-01]])
</pre>
RandomForestClassifier score 0.83696

-결정트리 모델의 과대적합을 통계적으로 해소

-결정트리모델처럼 직관적

-앙상블 모델중 비교적 빠른 속도

-모델 튜닝을 위한 시간이 많이 필요

-큰데이터 세트에도 잘 작동하지만 시간이 오래걸림

-트리의 개수가 많아져서

-training과정의 오류를 보정하지 않아 GRADIENT/CAT BOOST보다 정확도가 낮다.



```python
from sklearn.ensemble import RandomForestClassifier
rfc=RandomForestClassifier()
rfc.fit(train2,train["OutcomeType"])
result=rfc.predict_proba(test2)
```

GradientBoostingClassifier를 사용했을 때 score 0.76171로 RandomForestClassifier보다 개선되었다. 그러나 Cat Boost Classifier가 더 높다. 

GradientBoostingClassifier

-ada 부스팅과 기본 개념 동일

-가중치를 계산하는 방식에서 경시하강법을 사용

-학습속도가 느림

-특성 스케일을 조절할 필요가 없음(트리기반 모델)

SanFranciscoCrimeClassifier는  1762311 rows × 6 columns, 이번 데이터는 38185 rows × 12 columns로 약 23배 데이터의 크기가 작아 train및 predict에 시간이 더 적게 들었고, 빠른 시간 안에 적용할 수 있었다.



```python
from sklearn.ensemble import GradientBoostingClassifier
gbc=GradientBoostingClassifier(random_state=0)
gbc.fit(train2,train["OutcomeType"])
result=gbc.predict_proba(test2)
result
```

<pre>
array([[4.27993417e-02, 4.79213173e-03, 4.20526611e-02, 2.38160059e-01,
        6.72195807e-01],
       [6.87368648e-01, 6.17870538e-04, 1.02365106e-02, 2.44929386e-01,
        5.68475845e-02],
       [4.13345131e-01, 4.83263364e-03, 1.33157311e-02, 1.18887221e-01,
        4.49619283e-01],
       ...,
       [3.26446508e-03, 2.73996157e-03, 1.46132117e-02, 4.29836743e-03,
        9.75083994e-01],
       [5.05370820e-01, 1.06387942e-03, 1.83918940e-02, 4.19116761e-01,
        5.60566455e-02],
       [8.95909940e-02, 3.92833646e-03, 1.11641507e-01, 6.61491074e-01,
        1.33348088e-01]])
</pre>
xgboost classifier: 0.76171로 gradientboostinc과 동일

1. 뛰어난 예측 성능 : 일반적으로 분류와 회귀 영역에서 뛰어난 예측 성능을 발휘

2. GBM 대비 빠른 수행시간 : 일반적인 GBM은 순차적으로 weak learner가 가중치를 증감하는 방법으로 학습하기 때문에 전반적으로 속도가 느림. XGBOOST는 병렬 수행 및 다양한 기능으로 GBM에 비해 빠른 수행 성능 보장. 

3. 과적합 규제 : 표준 GBM의 경우 과적합 규제 기능이 없으나 XGBOOST는 자체에 과적합 규제 기능으로 과적합에 좀 더 강한 내구성

4. 나무 가지치기 : 일반적으로 GBM은 분할 시 부정 손실이 발생하면 분ㄴ할을 더 이상 수행하지 않지만 이러한 방식도 자칫 지나치게 많은 분할을 발생할 수 있음. 다른 GBM과 마찬가지로 XGBOOST도 max_depth 파라미터로 분할 깊이를 조정하기도 하지만 tree pruning으로 더이상 긍정 이득이 없는 분할을 가지치기해서 분할 수를 더 줄이는 장점이 있음.

5. 자체 내장된 교차 검증 : xgboost는 반복 수행 시마다 내부적으로 학습 데이터 세트와 평가 데이터 세트에 대한 교차 검증을 수행해 최적화된 반복 수행 횟수를 가질 수 있음. 지정된 반복 횟수가 아니라 교차 검증을 통해 평가 데이터 세트의 평가 값이 최적화 되면 반복을 중간에 멈출 수 있는 조기 중단 기능이 있음

6. 결손값 자체 처리 XGBoost는 결손값을 자체 처리할 수 있는 기능을 가지고 있음



```python
from xgboost import XGBClassifier
xgbc=XGBClassifier(random_state=0)
xgbc.fit(train2,train["OutcomeType"])
result=gbc.predict_proba(test2)
result
```

<pre>
/opt/conda/lib/python3.7/site-packages/xgboost/sklearn.py:1224: UserWarning: The use of label encoder in XGBClassifier is deprecated and will be removed in a future release. To remove this warning, do the following: 1) Pass option use_label_encoder=False when constructing XGBClassifier object; and 2) Encode your labels (y) as integers starting with 0, i.e. 0, 1, 2, ..., [num_class - 1].
  warnings.warn(label_encoder_deprecation_msg, UserWarning)
</pre>
<pre>
[08:40:59] WARNING: ../src/learner.cc:1115: Starting in XGBoost 1.3.0, the default evaluation metric used with the objective 'multi:softprob' was changed from 'merror' to 'mlogloss'. Explicitly set eval_metric if you'd like to restore the old behavior.
</pre>
<pre>
array([[4.27993417e-02, 4.79213173e-03, 4.20526611e-02, 2.38160059e-01,
        6.72195807e-01],
       [6.87368648e-01, 6.17870538e-04, 1.02365106e-02, 2.44929386e-01,
        5.68475845e-02],
       [4.13345131e-01, 4.83263364e-03, 1.33157311e-02, 1.18887221e-01,
        4.49619283e-01],
       ...,
       [3.26446508e-03, 2.73996157e-03, 1.46132117e-02, 4.29836743e-03,
        9.75083994e-01],
       [5.05370820e-01, 1.06387942e-03, 1.83918940e-02, 4.19116761e-01,
        5.60566455e-02],
       [8.95909940e-02, 3.92833646e-03, 1.11641507e-01, 6.61491074e-01,
        1.33348088e-01]])
</pre>
lgbmclassifier score 0.73234로 cat boost보다 높음

그러나 cat boost 쓸때와 달리 datetime을 learning으로 사용하지 못하는 문제가 있고, 대신 hour 러닝 하는 것으로 대체해야한다.

LightGBM

1. XGBOOST보다 학습에 걸리는 시간이 훨씬 적고 메모리 사용량이 상대적으로 낮음

2. 적은 데이터 세트에 적용할 경우 과적합이 발생하기 쉬움(10,000건 이하의 데이터)

3. 리프중심 트리 분할 방식 사용. 트리의 균형을 맞추지않고 최대 손실 값을 가지는 리프 노드를 지속적으로 분할하면서 트리의 깊이가 깊어지고 비대칭적 트리. 균형트리 분할 방식보다 예측 오류 손실을 최소화 할 수 있음 => CAT BOOST(대칭 트리)보다 높은 이유!



```python
from lightgbm import LGBMClassifier
lgbmc= LGBMClassifier(random_state=0)
lgbmc.fit(train2,train["OutcomeType"])
result=lgbmc.predict_proba(test2)
result
```

<style type='text/css'>
.datatable table.frame { margin-bottom: 0; }
.datatable table.frame thead { border-bottom: none; }
.datatable table.frame tr.coltypes td {  color: #FFFFFF;  line-height: 6px;  padding: 0 0.5em;}
.datatable .bool    { background: #DDDD99; }
.datatable .object  { background: #565656; }
.datatable .int     { background: #5D9E5D; }
.datatable .float   { background: #4040CC; }
.datatable .str     { background: #CC4040; }
.datatable .time    { background: #40CC40; }
.datatable .row_index {  background: var(--jp-border-color3);  border-right: 1px solid var(--jp-border-color0);  color: var(--jp-ui-font-color3);  font-size: 9px;}
.datatable .frame tbody td { text-align: left; }
.datatable .frame tr.coltypes .row_index {  background: var(--jp-border-color0);}
.datatable th:nth-child(2) { padding-left: 12px; }
.datatable .hellipsis {  color: var(--jp-cell-editor-border-color);}
.datatable .vellipsis {  background: var(--jp-layout-color0);  color: var(--jp-cell-editor-border-color);}
.datatable .na {  color: var(--jp-cell-editor-border-color);  font-size: 80%;}
.datatable .sp {  opacity: 0.25;}
.datatable .footer { font-size: 9px; }
.datatable .frame_dimensions {  background: var(--jp-border-color3);  border-top: 1px solid var(--jp-border-color0);  color: var(--jp-ui-font-color3);  display: inline-block;  opacity: 0.6;  padding: 1px 10px 1px 5px;}
</style>


<pre>
array([[2.61645417e-02, 5.23760785e-04, 4.80559073e-02, 1.75447674e-01,
        7.49808116e-01],
       [6.53465451e-01, 4.74909051e-04, 7.15232870e-03, 2.89924996e-01,
        4.89823151e-02],
       [3.79987191e-01, 3.87778767e-04, 9.61818643e-03, 1.37899925e-01,
        4.72106918e-01],
       ...,
       [8.15974259e-04, 4.17487959e-04, 1.76290435e-03, 7.83229394e-04,
        9.96220404e-01],
       [4.34432896e-01, 4.94487238e-04, 9.63687466e-03, 4.83548450e-01,
        7.18872922e-02],
       [6.99377657e-02, 9.67498212e-04, 1.54693550e-01, 5.79142914e-01,
        1.95258272e-01]])
</pre>

```python
sub=pd.read_csv("/kaggle/input/shelter-animal-outcomes/sample_submission.csv.gz")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Adoption</th>
      <th>Died</th>
      <th>Euthanasia</th>
      <th>Return_to_owner</th>
      <th>Transfer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11451</th>
      <td>11452</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>11453</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>11454</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>11455</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>11456</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>11456 rows × 6 columns</p>
</div>



```python
lgbmc.classes_
```

<pre>
array(['Adoption', 'Died', 'Euthanasia', 'Return_to_owner', 'Transfer'],
      dtype=object)
</pre>

```python
sub.iloc[:,1:]=result
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Adoption</th>
      <th>Died</th>
      <th>Euthanasia</th>
      <th>Return_to_owner</th>
      <th>Transfer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0.026165</td>
      <td>0.000524</td>
      <td>0.048056</td>
      <td>0.175448</td>
      <td>0.749808</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0.653465</td>
      <td>0.000475</td>
      <td>0.007152</td>
      <td>0.289925</td>
      <td>0.048982</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0.379987</td>
      <td>0.000388</td>
      <td>0.009618</td>
      <td>0.137900</td>
      <td>0.472107</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0.205234</td>
      <td>0.001639</td>
      <td>0.033865</td>
      <td>0.134480</td>
      <td>0.624783</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0.502942</td>
      <td>0.000086</td>
      <td>0.005115</td>
      <td>0.429320</td>
      <td>0.062537</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>11451</th>
      <td>11452</td>
      <td>0.511812</td>
      <td>0.000329</td>
      <td>0.008214</td>
      <td>0.013134</td>
      <td>0.466511</td>
    </tr>
    <tr>
      <th>11452</th>
      <td>11453</td>
      <td>0.000521</td>
      <td>0.022359</td>
      <td>0.075606</td>
      <td>0.002000</td>
      <td>0.899515</td>
    </tr>
    <tr>
      <th>11453</th>
      <td>11454</td>
      <td>0.000816</td>
      <td>0.000417</td>
      <td>0.001763</td>
      <td>0.000783</td>
      <td>0.996220</td>
    </tr>
    <tr>
      <th>11454</th>
      <td>11455</td>
      <td>0.434433</td>
      <td>0.000494</td>
      <td>0.009637</td>
      <td>0.483548</td>
      <td>0.071887</td>
    </tr>
    <tr>
      <th>11455</th>
      <td>11456</td>
      <td>0.069938</td>
      <td>0.000967</td>
      <td>0.154694</td>
      <td>0.579143</td>
      <td>0.195258</td>
    </tr>
  </tbody>
</table>
<p>11456 rows × 6 columns</p>
</div>



```python
sub.to_csv("lgbmc.csv",index=False)
```
