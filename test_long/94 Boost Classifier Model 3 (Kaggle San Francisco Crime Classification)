# 4 Boost Classifier Model 3 (Kaggle San Francisco Crime Classification)
![image](https://user-images.githubusercontent.com/69743938/172272203-69a79c9c-36ed-49ea-8e34-e4f92012bec3.png)
![image](https://user-images.githubusercontent.com/69743938/172272257-bf671298-c910-4e1c-adec-944b612b594a.png)

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

/kaggle/input/sf-crime/train.csv.zip

/kaggle/input/sf-crime/sampleSubmission.csv.zip

/kaggle/input/sf-crime/test.csv.zip


```python
train=pd.read_csv("/kaggle/input/sf-crime/train.csv.zip")
test=pd.read_csv("/kaggle/input/sf-crime/test.csv.zip")
pd.options.display.max_columns=99
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Dates</th>
      <th>Category</th>
      <th>Descript</th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Resolution</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2015-05-13 23:53:00</td>
      <td>WARRANTS</td>
      <td>WARRANT ARREST</td>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>ARREST, BOOKED</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2015-05-13 23:53:00</td>
      <td>OTHER OFFENSES</td>
      <td>TRAFFIC VIOLATION ARREST</td>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>ARREST, BOOKED</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2015-05-13 23:33:00</td>
      <td>OTHER OFFENSES</td>
      <td>TRAFFIC VIOLATION ARREST</td>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>ARREST, BOOKED</td>
      <td>VANNESS AV / GREENWICH ST</td>
      <td>-122.424363</td>
      <td>37.800414</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2015-05-13 23:30:00</td>
      <td>LARCENY/THEFT</td>
      <td>GRAND THEFT FROM LOCKED AUTO</td>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>NONE</td>
      <td>1500 Block of LOMBARD ST</td>
      <td>-122.426995</td>
      <td>37.800873</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2015-05-13 23:30:00</td>
      <td>LARCENY/THEFT</td>
      <td>GRAND THEFT FROM LOCKED AUTO</td>
      <td>Wednesday</td>
      <td>PARK</td>
      <td>NONE</td>
      <td>100 Block of BRODERICK ST</td>
      <td>-122.438738</td>
      <td>37.771541</td>
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
      <th>878044</th>
      <td>2003-01-06 00:15:00</td>
      <td>ROBBERY</td>
      <td>ROBBERY ON THE STREET WITH A GUN</td>
      <td>Monday</td>
      <td>TARAVAL</td>
      <td>NONE</td>
      <td>FARALLONES ST / CAPITOL AV</td>
      <td>-122.459033</td>
      <td>37.714056</td>
    </tr>
    <tr>
      <th>878045</th>
      <td>2003-01-06 00:01:00</td>
      <td>LARCENY/THEFT</td>
      <td>GRAND THEFT FROM LOCKED AUTO</td>
      <td>Monday</td>
      <td>INGLESIDE</td>
      <td>NONE</td>
      <td>600 Block of EDNA ST</td>
      <td>-122.447364</td>
      <td>37.731948</td>
    </tr>
    <tr>
      <th>878046</th>
      <td>2003-01-06 00:01:00</td>
      <td>LARCENY/THEFT</td>
      <td>GRAND THEFT FROM LOCKED AUTO</td>
      <td>Monday</td>
      <td>SOUTHERN</td>
      <td>NONE</td>
      <td>5TH ST / FOLSOM ST</td>
      <td>-122.403390</td>
      <td>37.780266</td>
    </tr>
    <tr>
      <th>878047</th>
      <td>2003-01-06 00:01:00</td>
      <td>VANDALISM</td>
      <td>MALICIOUS MISCHIEF, VANDALISM OF VEHICLES</td>
      <td>Monday</td>
      <td>SOUTHERN</td>
      <td>NONE</td>
      <td>TOWNSEND ST / 2ND ST</td>
      <td>-122.390531</td>
      <td>37.780607</td>
    </tr>
    <tr>
      <th>878048</th>
      <td>2003-01-06 00:01:00</td>
      <td>FORGERY/COUNTERFEITING</td>
      <td>CHECKS, FORGERY (FELONY)</td>
      <td>Monday</td>
      <td>BAYVIEW</td>
      <td>NONE</td>
      <td>1800 Block of NEWCOMB AV</td>
      <td>-122.394926</td>
      <td>37.738212</td>
    </tr>
  </tbody>
</table>
<p>878049 rows × 9 columns</p>
</div>


<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Id</th>
      <th>Dates</th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>2015-05-10 23:59:00</td>
      <td>Sunday</td>
      <td>BAYVIEW</td>
      <td>2000 Block of THOMAS AV</td>
      <td>-122.399588</td>
      <td>37.735051</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>2015-05-10 23:51:00</td>
      <td>Sunday</td>
      <td>BAYVIEW</td>
      <td>3RD ST / REVERE AV</td>
      <td>-122.391523</td>
      <td>37.732432</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>2015-05-10 23:50:00</td>
      <td>Sunday</td>
      <td>NORTHERN</td>
      <td>2000 Block of GOUGH ST</td>
      <td>-122.426002</td>
      <td>37.792212</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>2015-05-10 23:45:00</td>
      <td>Sunday</td>
      <td>INGLESIDE</td>
      <td>4700 Block of MISSION ST</td>
      <td>-122.437394</td>
      <td>37.721412</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>2015-05-10 23:45:00</td>
      <td>Sunday</td>
      <td>INGLESIDE</td>
      <td>4700 Block of MISSION ST</td>
      <td>-122.437394</td>
      <td>37.721412</td>
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
    </tr>
    <tr>
      <th>884257</th>
      <td>884257</td>
      <td>2003-01-01 00:01:00</td>
      <td>Wednesday</td>
      <td>MISSION</td>
      <td>2600 Block of BRYANT ST</td>
      <td>-122.408983</td>
      <td>37.751987</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>884258</td>
      <td>2003-01-01 00:01:00</td>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>1900 Block of WASHINGTON ST</td>
      <td>-122.425342</td>
      <td>37.792681</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>884259</td>
      <td>2003-01-01 00:01:00</td>
      <td>Wednesday</td>
      <td>INGLESIDE</td>
      <td>5500 Block of MISSION ST</td>
      <td>-122.445418</td>
      <td>37.712075</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>884260</td>
      <td>2003-01-01 00:01:00</td>
      <td>Wednesday</td>
      <td>BAYVIEW</td>
      <td>1500 Block of HUDSON AV</td>
      <td>-122.387394</td>
      <td>37.739479</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>884261</td>
      <td>2003-01-01 00:01:00</td>
      <td>Wednesday</td>
      <td>TARAVAL</td>
      <td>1500 Block of SLOAT BL</td>
      <td>-122.489714</td>
      <td>37.733950</td>
    </tr>
  </tbody>
</table>
<p>884262 rows × 7 columns</p>
</div>

----
train,test 각 데이터에서 겹치지 않는 값과 정답 값을 drop하여 정제합니다

----

```python
alldata=pd.concat([train,test],axis=0)
alldata2=alldata.drop(columns=["Category","Descript","Resolution","Dates"])
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
      <th>Id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>VANNESS AV / GREENWICH ST</td>
      <td>-122.424363</td>
      <td>37.800414</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>1500 Block of LOMBARD ST</td>
      <td>-122.426995</td>
      <td>37.800873</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Wednesday</td>
      <td>PARK</td>
      <td>100 Block of BRODERICK ST</td>
      <td>-122.438738</td>
      <td>37.771541</td>
      <td>NaN</td>
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
      <th>884257</th>
      <td>Wednesday</td>
      <td>MISSION</td>
      <td>2600 Block of BRYANT ST</td>
      <td>-122.408983</td>
      <td>37.751987</td>
      <td>884257.0</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>Wednesday</td>
      <td>NORTHERN</td>
      <td>1900 Block of WASHINGTON ST</td>
      <td>-122.425342</td>
      <td>37.792681</td>
      <td>884258.0</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>Wednesday</td>
      <td>INGLESIDE</td>
      <td>5500 Block of MISSION ST</td>
      <td>-122.445418</td>
      <td>37.712075</td>
      <td>884259.0</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>Wednesday</td>
      <td>BAYVIEW</td>
      <td>1500 Block of HUDSON AV</td>
      <td>-122.387394</td>
      <td>37.739479</td>
      <td>884260.0</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>Wednesday</td>
      <td>TARAVAL</td>
      <td>1500 Block of SLOAT BL</td>
      <td>-122.489714</td>
      <td>37.733950</td>
      <td>884261.0</td>
    </tr>
  </tbody>
</table>
<p>1762311 rows × 6 columns</p>
</div>

------
날짜를 숫자로 변경하여 러닝에 용이합니다

------

```python
alldata2["DayOfWeek"].unique()
alldata2["DayOfWeek"]=alldata2["DayOfWeek"].replace({"Wednesday":0, "Tuesday":1, "Monday":2, "Sunday":3, "Saturday":4, "Friday":5, "Thursday":6})
alldata2["DayOfWeek"]
```

0         0

1         0

2         0

3         0

4         0

..

884257    0

884258    0

884259    0

884260    0

884261    0

Name: DayOfWeek, Length: 1762311, dtype: int64

-----------
LabelEncoder를 이용하면 해당 칼럼의 값을 임의의 숫자로 지정해줍니다

-----

```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
alldata2["PdDistrict"]=le.fit_transform(alldata2["PdDistrict"])
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
      <th>Id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>4</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>4</td>
      <td>OAK ST / LAGUNA ST</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>4</td>
      <td>VANNESS AV / GREENWICH ST</td>
      <td>-122.424363</td>
      <td>37.800414</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>4</td>
      <td>1500 Block of LOMBARD ST</td>
      <td>-122.426995</td>
      <td>37.800873</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>5</td>
      <td>100 Block of BRODERICK ST</td>
      <td>-122.438738</td>
      <td>37.771541</td>
      <td>NaN</td>
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
      <th>884257</th>
      <td>0</td>
      <td>3</td>
      <td>2600 Block of BRYANT ST</td>
      <td>-122.408983</td>
      <td>37.751987</td>
      <td>884257.0</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>0</td>
      <td>4</td>
      <td>1900 Block of WASHINGTON ST</td>
      <td>-122.425342</td>
      <td>37.792681</td>
      <td>884258.0</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>0</td>
      <td>2</td>
      <td>5500 Block of MISSION ST</td>
      <td>-122.445418</td>
      <td>37.712075</td>
      <td>884259.0</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>0</td>
      <td>0</td>
      <td>1500 Block of HUDSON AV</td>
      <td>-122.387394</td>
      <td>37.739479</td>
      <td>884260.0</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>0</td>
      <td>8</td>
      <td>1500 Block of SLOAT BL</td>
      <td>-122.489714</td>
      <td>37.733950</td>
      <td>884261.0</td>
    </tr>
  </tbody>
</table>
<p>1762311 rows × 6 columns</p>
</div>

------------
PdDistrict의 각 칼럼 고유값에 해당하는 숫자 값을 dictionary로 만들어 줍니다

-------------

```python
len(le.classes_) #10개
dict(zip(le.classes_,range(10)))
```

{'BAYVIEW': 0,
 'CENTRAL': 1,
 'INGLESIDE': 2,
 'MISSION': 3,
 'NORTHERN': 4,
 'PARK': 5,
 'RICHMOND': 6,
 'SOUTHERN': 7,
 'TARAVAL': 8,
 'TENDERLOIN': 9}

--------------
칼럼 값이 object인 것이 있는지 추가로 확인합니다.

-----------------

```python
category=alldata2.columns[alldata2.dtypes == object]
category
```


Index(['Address'], dtype='object')

------------
Address column에서 레이블 인코딩 처리, 숫자로 변경해 줍니다

------------

```python
for col in category:
    alldata2[col]=le.fit_transform(alldata2["Address"])
```


```python
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
      <th>Id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>4</td>
      <td>20895</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>4</td>
      <td>20895</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>4</td>
      <td>24169</td>
      <td>-122.424363</td>
      <td>37.800414</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>4</td>
      <td>4418</td>
      <td>-122.426995</td>
      <td>37.800873</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>5</td>
      <td>1923</td>
      <td>-122.438738</td>
      <td>37.771541</td>
      <td>NaN</td>
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
      <th>884257</th>
      <td>0</td>
      <td>3</td>
      <td>7919</td>
      <td>-122.408983</td>
      <td>37.751987</td>
      <td>884257.0</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>0</td>
      <td>4</td>
      <td>5596</td>
      <td>-122.425342</td>
      <td>37.792681</td>
      <td>884258.0</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>0</td>
      <td>2</td>
      <td>11612</td>
      <td>-122.445418</td>
      <td>37.712075</td>
      <td>884259.0</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>0</td>
      <td>0</td>
      <td>4393</td>
      <td>-122.387394</td>
      <td>37.739479</td>
      <td>884260.0</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>0</td>
      <td>8</td>
      <td>4476</td>
      <td>-122.489714</td>
      <td>37.733950</td>
      <td>884261.0</td>
    </tr>
  </tbody>
</table>
<p>1762311 rows × 6 columns</p>
</div>



```python
alldata2=alldata2.fillna(-1) # nan값 있을 경우 러닝 과정에서 오류발생
alldata2
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DayOfWeek</th>
      <th>PdDistrict</th>
      <th>Address</th>
      <th>X</th>
      <th>Y</th>
      <th>Id</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>4</td>
      <td>20895</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>4</td>
      <td>20895</td>
      <td>-122.425892</td>
      <td>37.774599</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>4</td>
      <td>24169</td>
      <td>-122.424363</td>
      <td>37.800414</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>4</td>
      <td>4418</td>
      <td>-122.426995</td>
      <td>37.800873</td>
      <td>-1.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>5</td>
      <td>1923</td>
      <td>-122.438738</td>
      <td>37.771541</td>
      <td>-1.0</td>
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
      <th>884257</th>
      <td>0</td>
      <td>3</td>
      <td>7919</td>
      <td>-122.408983</td>
      <td>37.751987</td>
      <td>884257.0</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>0</td>
      <td>4</td>
      <td>5596</td>
      <td>-122.425342</td>
      <td>37.792681</td>
      <td>884258.0</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>0</td>
      <td>2</td>
      <td>11612</td>
      <td>-122.445418</td>
      <td>37.712075</td>
      <td>884259.0</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>0</td>
      <td>0</td>
      <td>4393</td>
      <td>-122.387394</td>
      <td>37.739479</td>
      <td>884260.0</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>0</td>
      <td>8</td>
      <td>4476</td>
      <td>-122.489714</td>
      <td>37.733950</td>
      <td>884261.0</td>
    </tr>
  </tbody>
</table>
<p>1762311 rows × 6 columns</p>
</div>



```python
train2=alldata2[:len(train)]
test2=alldata2[len(train):]
```
----
분류 Model중 RandomForestClassifier/ CatBoostClassifier / GradientBoostingClassifier 를 적용하여 데이터와의 적합성을 확인해보았습니다.

SCORE가 낮을수록 순위가 개선되는데, CatBoostClassifier(score 2.41086) > RandomForestClassifier(score 9.53751) 순으로 큰 차이를 보였습니다.

또한, GradientBoostingClassifier는 방대한 데이터를 처리하기에 적합치 않아 5시간 이상 소요되어 학습을 중지하였습니다.

CatBoostingClassifier의 경우, 성능도 월등히 높고 GBM에 비해 시간은 적게 걸리기 때문에 가장 적합한 모델입니다.

약한 학습기를 순차적으로 학습-예측하면서 잘못 예측한 데이터에 가중치 부여를 통해 오류를 개선해 나가면서 학습하는 방식이기 때문으로 보입니다.

적용 code는 아래와 같습니다.

1) RandomForestClassifier

----

```python
from sklearn.ensemble import RandomForestClassifier 
rfc=RandomForestClassifier(n_jobs=-1)
rfc.fit(train2,train["Category"])
```


```python
result=rfc.predict_proba(test2)
```
----
2) CatBoostClassifier

---


```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier (task_type="GPU")
cbc.fit(train2,train["Category"])

result=cbc.predict_proba(test2)
result
```

Learning rate set to 0.258679

0:	learn: 2.9675235	total: 86.6ms	remaining: 1m 26s

1:	learn: 2.8087564	total: 167ms	remaining: 1m 23s

2:	learn: 2.7177632	total: 246ms	remaining: 1m 21s

3:	learn: 2.6591386	total: 323ms	remaining: 1m 20s

4:	learn: 2.6195879	total: 405ms	remaining: 1m 20s

5:	learn: 2.5929342	total: 481ms	remaining: 1m 19s

6:	learn: 2.5713568	total: 559ms	remaining: 1m 19s

7:	learn: 2.5560285	total: 637ms	remaining: 1m 18s

8:	learn: 2.5391151	total: 713ms	remaining: 1m 18s

9:	learn: 2.5296752	total: 791ms	remaining: 1m 18s

10:	learn: 2.5216833	total: 866ms	remaining: 1m 17s

11:	learn: 2.5168089	total: 941ms	remaining: 1m 17s

12:	learn: 2.5130235	total: 1.02s	remaining: 1m 17s

13:	learn: 2.5082091	total: 1.09s	remaining: 1m 17s

14:	learn: 2.5058305	total: 1.17s	remaining: 1m 16s

15:	learn: 2.5025722	total: 1.25s	remaining: 1m 16s

16:	learn: 2.4997859	total: 1.32s	remaining: 1m 16s

17:	learn: 2.4958220	total: 1.4s	remaining: 1m 16s

18:	learn: 2.4941350	total: 1.48s	remaining: 1m 16s

19:	learn: 2.4920508	total: 1.55s	remaining: 1m 16s

20:	learn: 2.4905757	total: 1.63s	remaining: 1m 15s

21:	learn: 2.4890146	total: 1.71s	remaining: 1m 15s

22:	learn: 2.4872111	total: 1.78s	remaining: 1m 15s

23:	learn: 2.4851523	total: 1.87s	remaining: 1m 16s

24:	learn: 2.4835806	total: 1.95s	remaining: 1m 16s

25:	learn: 2.4821135	total: 2.03s	remaining: 1m 16s

26:	learn: 2.4805743	total: 2.1s	remaining: 1m 15s

27:	learn: 2.4789716	total: 2.18s	remaining: 1m 15s

28:	learn: 2.4782270	total: 2.26s	remaining: 1m 15s

29:	learn: 2.4764247	total: 2.33s	remaining: 1m 15s

30:	learn: 2.4748778	total: 2.41s	remaining: 1m 15s

31:	learn: 2.4737705	total: 2.48s	remaining: 1m 15s

...

994:	learn: 2.3135787	total: 1m 20s	remaining: 403ms

995:	learn: 2.3134935	total: 1m 20s	remaining: 322ms

996:	learn: 2.3134485	total: 1m 20s	remaining: 242ms

997:	learn: 2.3133665	total: 1m 20s	remaining: 161ms

998:	learn: 2.3132940	total: 1m 20s	remaining: 80.6ms

999:	learn: 2.3132355	total: 1m 20s	remaining: 0us

array([[5.13981685e-03, 1.33836675e-01, 2.60218668e-04, ...,
        1.04583196e-01, 2.96222535e-02, 2.08501741e-02],
       [6.52594062e-04, 1.23925386e-01, 5.93575446e-05, ...,
        3.48495807e-02, 7.82117240e-02, 2.25429659e-02],
       [9.81822206e-04, 6.29439575e-02, 2.54633670e-04, ...,
        9.27102233e-02, 2.20450354e-02, 2.17404799e-03],
       ...,
       [1.18982462e-03, 1.17355734e-01, 1.01393952e-03, ...,
        5.37868271e-02, 5.80140400e-02, 6.98672479e-03],
       [1.03975181e-02, 1.11149458e-01, 6.58686976e-05, ...,
        1.03926996e-01, 5.75476796e-02, 2.37595173e-02],
       [1.62208050e-03, 4.06436602e-02, 3.91631858e-03, ...,
        2.97695394e-02, 6.53736414e-02, 2.59673197e-03]])

-----
3) GradientBoostingClassifier

-----

```python
# from sklearn.ensemble import GradientBoostingClassifier
# gbc=GradientBoostingClassifier(random_state=0)
# gbc.fit(train2,train["Category"])
# result=gbc.predict_proba(test2)
```


```python
sub=pd.read_csv("/kaggle/input/sf-crime/sampleSubmission.csv.zip")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Id</th>
      <th>ARSON</th>
      <th>ASSAULT</th>
      <th>BAD CHECKS</th>
      <th>BRIBERY</th>
      <th>BURGLARY</th>
      <th>DISORDERLY CONDUCT</th>
      <th>DRIVING UNDER THE INFLUENCE</th>
      <th>DRUG/NARCOTIC</th>
      <th>DRUNKENNESS</th>
      <th>EMBEZZLEMENT</th>
      <th>EXTORTION</th>
      <th>FAMILY OFFENSES</th>
      <th>FORGERY/COUNTERFEITING</th>
      <th>FRAUD</th>
      <th>GAMBLING</th>
      <th>KIDNAPPING</th>
      <th>LARCENY/THEFT</th>
      <th>LIQUOR LAWS</th>
      <th>LOITERING</th>
      <th>MISSING PERSON</th>
      <th>NON-CRIMINAL</th>
      <th>OTHER OFFENSES</th>
      <th>PORNOGRAPHY/OBSCENE MAT</th>
      <th>PROSTITUTION</th>
      <th>RECOVERED VEHICLE</th>
      <th>ROBBERY</th>
      <th>RUNAWAY</th>
      <th>SECONDARY CODES</th>
      <th>SEX OFFENSES FORCIBLE</th>
      <th>SEX OFFENSES NON FORCIBLE</th>
      <th>STOLEN PROPERTY</th>
      <th>SUICIDE</th>
      <th>SUSPICIOUS OCC</th>
      <th>TREA</th>
      <th>TRESPASS</th>
      <th>VANDALISM</th>
      <th>VEHICLE THEFT</th>
      <th>WARRANTS</th>
      <th>WEAPON LAWS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
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
      <th>884257</th>
      <td>884257</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>884258</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>884259</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>884260</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>884261</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>884262 rows × 40 columns</p>
</div>



```python
sub.iloc[:,1:]=result
sub
```

<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Id</th>
      <th>ARSON</th>
      <th>ASSAULT</th>
      <th>BAD CHECKS</th>
      <th>BRIBERY</th>
      <th>BURGLARY</th>
      <th>DISORDERLY CONDUCT</th>
      <th>DRIVING UNDER THE INFLUENCE</th>
      <th>DRUG/NARCOTIC</th>
      <th>DRUNKENNESS</th>
      <th>EMBEZZLEMENT</th>
      <th>EXTORTION</th>
      <th>FAMILY OFFENSES</th>
      <th>FORGERY/COUNTERFEITING</th>
      <th>FRAUD</th>
      <th>GAMBLING</th>
      <th>KIDNAPPING</th>
      <th>LARCENY/THEFT</th>
      <th>LIQUOR LAWS</th>
      <th>LOITERING</th>
      <th>MISSING PERSON</th>
      <th>NON-CRIMINAL</th>
      <th>OTHER OFFENSES</th>
      <th>PORNOGRAPHY/OBSCENE MAT</th>
      <th>PROSTITUTION</th>
      <th>RECOVERED VEHICLE</th>
      <th>ROBBERY</th>
      <th>RUNAWAY</th>
      <th>SECONDARY CODES</th>
      <th>SEX OFFENSES FORCIBLE</th>
      <th>SEX OFFENSES NON FORCIBLE</th>
      <th>STOLEN PROPERTY</th>
      <th>SUICIDE</th>
      <th>SUSPICIOUS OCC</th>
      <th>TREA</th>
      <th>TRESPASS</th>
      <th>VANDALISM</th>
      <th>VEHICLE THEFT</th>
      <th>WARRANTS</th>
      <th>WEAPON LAWS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>0.005140</td>
      <td>0.133837</td>
      <td>0.000260</td>
      <td>0.001001</td>
      <td>0.044844</td>
      <td>0.003067</td>
      <td>0.004333</td>
      <td>0.020894</td>
      <td>0.002635</td>
      <td>0.000643</td>
      <td>0.000079</td>
      <td>0.002361</td>
      <td>0.005553</td>
      <td>0.017387</td>
      <td>0.000271</td>
      <td>0.003643</td>
      <td>0.135135</td>
      <td>0.000814</td>
      <td>0.000389</td>
      <td>0.062013</td>
      <td>0.083156</td>
      <td>0.107755</td>
      <td>1.273716e-07</td>
      <td>0.000067</td>
      <td>0.007433</td>
      <td>0.026381</td>
      <td>0.001052</td>
      <td>0.013480</td>
      <td>0.004029</td>
      <td>0.000080</td>
      <td>0.007954</td>
      <td>0.001029</td>
      <td>0.064134</td>
      <td>8.504400e-08</td>
      <td>0.007716</td>
      <td>0.076377</td>
      <td>0.104583</td>
      <td>0.029622</td>
      <td>0.020850</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>0.000653</td>
      <td>0.123925</td>
      <td>0.000059</td>
      <td>0.000616</td>
      <td>0.004988</td>
      <td>0.001679</td>
      <td>0.007780</td>
      <td>0.087791</td>
      <td>0.003859</td>
      <td>0.000084</td>
      <td>0.000014</td>
      <td>0.000175</td>
      <td>0.005371</td>
      <td>0.005762</td>
      <td>0.000556</td>
      <td>0.002574</td>
      <td>0.049147</td>
      <td>0.005175</td>
      <td>0.001617</td>
      <td>0.006260</td>
      <td>0.071285</td>
      <td>0.341952</td>
      <td>8.329714e-08</td>
      <td>0.000011</td>
      <td>0.000950</td>
      <td>0.067321</td>
      <td>0.000156</td>
      <td>0.014347</td>
      <td>0.002246</td>
      <td>0.000087</td>
      <td>0.003859</td>
      <td>0.000086</td>
      <td>0.036048</td>
      <td>2.437253e-07</td>
      <td>0.001423</td>
      <td>0.016542</td>
      <td>0.034850</td>
      <td>0.078212</td>
      <td>0.022543</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>0.000982</td>
      <td>0.062944</td>
      <td>0.000255</td>
      <td>0.000009</td>
      <td>0.131975</td>
      <td>0.001753</td>
      <td>0.001083</td>
      <td>0.010244</td>
      <td>0.003373</td>
      <td>0.001551</td>
      <td>0.000155</td>
      <td>0.000069</td>
      <td>0.011248</td>
      <td>0.021056</td>
      <td>0.000043</td>
      <td>0.004799</td>
      <td>0.259024</td>
      <td>0.000378</td>
      <td>0.000633</td>
      <td>0.032383</td>
      <td>0.107672</td>
      <td>0.064634</td>
      <td>5.183362e-07</td>
      <td>0.001288</td>
      <td>0.000755</td>
      <td>0.009190</td>
      <td>0.000216</td>
      <td>0.014339</td>
      <td>0.004860</td>
      <td>0.000011</td>
      <td>0.009470</td>
      <td>0.000858</td>
      <td>0.041393</td>
      <td>1.355137e-07</td>
      <td>0.018212</td>
      <td>0.066216</td>
      <td>0.092710</td>
      <td>0.022045</td>
      <td>0.002174</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>0.000586</td>
      <td>0.220010</td>
      <td>0.000201</td>
      <td>0.000863</td>
      <td>0.034339</td>
      <td>0.007504</td>
      <td>0.001464</td>
      <td>0.035376</td>
      <td>0.014801</td>
      <td>0.000444</td>
      <td>0.003228</td>
      <td>0.001812</td>
      <td>0.015559</td>
      <td>0.009601</td>
      <td>0.000123</td>
      <td>0.004651</td>
      <td>0.086960</td>
      <td>0.005905</td>
      <td>0.002438</td>
      <td>0.021292</td>
      <td>0.079723</td>
      <td>0.147098</td>
      <td>2.846644e-08</td>
      <td>0.000360</td>
      <td>0.002244</td>
      <td>0.032413</td>
      <td>0.002664</td>
      <td>0.023494</td>
      <td>0.007427</td>
      <td>0.000546</td>
      <td>0.007885</td>
      <td>0.001211</td>
      <td>0.040226</td>
      <td>2.119791e-06</td>
      <td>0.005119</td>
      <td>0.074884</td>
      <td>0.040058</td>
      <td>0.046039</td>
      <td>0.021450</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>0.000586</td>
      <td>0.220010</td>
      <td>0.000201</td>
      <td>0.000863</td>
      <td>0.034339</td>
      <td>0.007504</td>
      <td>0.001464</td>
      <td>0.035376</td>
      <td>0.014801</td>
      <td>0.000444</td>
      <td>0.003228</td>
      <td>0.001812</td>
      <td>0.015559</td>
      <td>0.009601</td>
      <td>0.000123</td>
      <td>0.004651</td>
      <td>0.086960</td>
      <td>0.005905</td>
      <td>0.002438</td>
      <td>0.021292</td>
      <td>0.079723</td>
      <td>0.147098</td>
      <td>2.846644e-08</td>
      <td>0.000360</td>
      <td>0.002244</td>
      <td>0.032413</td>
      <td>0.002664</td>
      <td>0.023494</td>
      <td>0.007427</td>
      <td>0.000546</td>
      <td>0.007885</td>
      <td>0.001211</td>
      <td>0.040226</td>
      <td>2.119791e-06</td>
      <td>0.005119</td>
      <td>0.074884</td>
      <td>0.040058</td>
      <td>0.046039</td>
      <td>0.021450</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>884257</th>
      <td>884257</td>
      <td>0.001149</td>
      <td>0.107800</td>
      <td>0.002124</td>
      <td>0.000427</td>
      <td>0.030485</td>
      <td>0.001700</td>
      <td>0.002842</td>
      <td>0.054250</td>
      <td>0.011411</td>
      <td>0.000234</td>
      <td>0.000088</td>
      <td>0.000888</td>
      <td>0.008121</td>
      <td>0.017036</td>
      <td>0.000072</td>
      <td>0.002741</td>
      <td>0.132239</td>
      <td>0.016218</td>
      <td>0.000051</td>
      <td>0.023003</td>
      <td>0.091262</td>
      <td>0.181880</td>
      <td>3.291479e-06</td>
      <td>0.001299</td>
      <td>0.002786</td>
      <td>0.043498</td>
      <td>0.001382</td>
      <td>0.020941</td>
      <td>0.008870</td>
      <td>0.000287</td>
      <td>0.005811</td>
      <td>0.000497</td>
      <td>0.037544</td>
      <td>6.260359e-08</td>
      <td>0.005925</td>
      <td>0.066932</td>
      <td>0.060994</td>
      <td>0.039087</td>
      <td>0.018121</td>
    </tr>
    <tr>
      <th>884258</th>
      <td>884258</td>
      <td>0.000565</td>
      <td>0.038851</td>
      <td>0.001017</td>
      <td>0.000009</td>
      <td>0.160727</td>
      <td>0.003577</td>
      <td>0.000863</td>
      <td>0.013937</td>
      <td>0.001015</td>
      <td>0.001172</td>
      <td>0.000246</td>
      <td>0.000025</td>
      <td>0.022178</td>
      <td>0.018173</td>
      <td>0.000475</td>
      <td>0.000784</td>
      <td>0.230403</td>
      <td>0.001661</td>
      <td>0.000360</td>
      <td>0.020659</td>
      <td>0.084616</td>
      <td>0.098528</td>
      <td>1.378101e-06</td>
      <td>0.013475</td>
      <td>0.005369</td>
      <td>0.010647</td>
      <td>0.000861</td>
      <td>0.004214</td>
      <td>0.002380</td>
      <td>0.000009</td>
      <td>0.008016</td>
      <td>0.000461</td>
      <td>0.035762</td>
      <td>1.865911e-08</td>
      <td>0.007859</td>
      <td>0.063806</td>
      <td>0.126528</td>
      <td>0.017916</td>
      <td>0.002855</td>
    </tr>
    <tr>
      <th>884259</th>
      <td>884259</td>
      <td>0.001190</td>
      <td>0.117356</td>
      <td>0.001014</td>
      <td>0.000320</td>
      <td>0.042540</td>
      <td>0.000897</td>
      <td>0.000736</td>
      <td>0.049310</td>
      <td>0.002352</td>
      <td>0.011201</td>
      <td>0.003967</td>
      <td>0.000116</td>
      <td>0.031840</td>
      <td>0.014138</td>
      <td>0.000137</td>
      <td>0.010043</td>
      <td>0.111441</td>
      <td>0.009511</td>
      <td>0.000084</td>
      <td>0.032177</td>
      <td>0.139816</td>
      <td>0.113581</td>
      <td>4.000877e-08</td>
      <td>0.000619</td>
      <td>0.009697</td>
      <td>0.043316</td>
      <td>0.001579</td>
      <td>0.006415</td>
      <td>0.004489</td>
      <td>0.000363</td>
      <td>0.001553</td>
      <td>0.000106</td>
      <td>0.038470</td>
      <td>1.009188e-06</td>
      <td>0.005794</td>
      <td>0.075043</td>
      <td>0.053787</td>
      <td>0.058014</td>
      <td>0.006987</td>
    </tr>
    <tr>
      <th>884260</th>
      <td>884260</td>
      <td>0.010398</td>
      <td>0.111149</td>
      <td>0.000066</td>
      <td>0.000522</td>
      <td>0.064157</td>
      <td>0.001485</td>
      <td>0.001806</td>
      <td>0.042956</td>
      <td>0.001302</td>
      <td>0.007940</td>
      <td>0.000040</td>
      <td>0.000540</td>
      <td>0.016415</td>
      <td>0.008389</td>
      <td>0.000100</td>
      <td>0.001455</td>
      <td>0.144280</td>
      <td>0.000771</td>
      <td>0.000273</td>
      <td>0.020382</td>
      <td>0.075537</td>
      <td>0.145082</td>
      <td>3.482791e-06</td>
      <td>0.000087</td>
      <td>0.015896</td>
      <td>0.023526</td>
      <td>0.001566</td>
      <td>0.016419</td>
      <td>0.002136</td>
      <td>0.000553</td>
      <td>0.005911</td>
      <td>0.000127</td>
      <td>0.044850</td>
      <td>1.818928e-06</td>
      <td>0.005227</td>
      <td>0.043417</td>
      <td>0.103927</td>
      <td>0.057548</td>
      <td>0.023760</td>
    </tr>
    <tr>
      <th>884261</th>
      <td>884261</td>
      <td>0.001622</td>
      <td>0.040644</td>
      <td>0.003916</td>
      <td>0.000034</td>
      <td>0.074317</td>
      <td>0.000270</td>
      <td>0.000947</td>
      <td>0.023961</td>
      <td>0.000794</td>
      <td>0.000120</td>
      <td>0.000448</td>
      <td>0.000056</td>
      <td>0.060744</td>
      <td>0.050868</td>
      <td>0.000170</td>
      <td>0.000791</td>
      <td>0.316918</td>
      <td>0.000873</td>
      <td>0.000038</td>
      <td>0.004241</td>
      <td>0.075005</td>
      <td>0.114943</td>
      <td>1.044892e-06</td>
      <td>0.000536</td>
      <td>0.001291</td>
      <td>0.027433</td>
      <td>0.000091</td>
      <td>0.006139</td>
      <td>0.003789</td>
      <td>0.000020</td>
      <td>0.007178</td>
      <td>0.000717</td>
      <td>0.038307</td>
      <td>2.792012e-08</td>
      <td>0.004346</td>
      <td>0.040691</td>
      <td>0.029770</td>
      <td>0.065374</td>
      <td>0.002597</td>
    </tr>
  </tbody>
</table>
<p>884262 rows × 40 columns</p>
</div>

---------


```python
sub.to_csv("cbc.csv",index=False)
```
