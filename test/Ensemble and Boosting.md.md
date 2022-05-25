
<head>




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
/kaggle/input/sf-crime/train.csv.zip
/kaggle/input/sf-crime/sampleSubmission.csv.zip
/kaggle/input/sf-crime/test.csv.zip
</pre>

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


train,test 각 데이터에서 겹치지 않는 값과 정답 값을 drop하여 정제합니다



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


날짜를 숫자로 변경하여 러닝에 용이합니다



```python
alldata2["DayOfWeek"].unique()
alldata2["DayOfWeek"]=alldata2["DayOfWeek"].replace({"Wednesday":0, "Tuesday":1, "Monday":2, "Sunday":3, "Saturday":4, "Friday":5, "Thursday":6})
alldata2["DayOfWeek"]
```

<pre>
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
</pre>
LabelEncoder를 이용하면 해당 칼럼의 값을 임의의 숫자로 지정해줍니다



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


PdDistrict의 각 칼럼 고유값에 해당하는 숫자 값을 dictionary로 만들어 줍니다



```python
len(le.classes_) #10개
dict(zip(le.classes_,range(10)))
```

<pre>
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
</pre>
칼럼 값이 object인 것이 있는지 추가로 확인합니다.



```python
category=alldata2.columns[alldata2.dtypes == object]
category
```

<pre>
Index(['Address'], dtype='object')
</pre>
Address column에서 레이블 인코딩 처리, 숫자로 변경해 줍니다



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

RandomForestClassifier 에서 score 9.53751

GBDT와 달리 병렬로 트리를 작성. 각 결정 트리의 학습에서 행 데이터나 특징을 샘플링해 전달함으로써 다양한 결정 트리를 작성하고, 앙상블하여 일반화 성능이 높은 예측을 실시. 모델 구축 순서

1) 학습 데이터에서 행 데이터를 샘플링하여 추출

2) 1)을 학습하고 결정트리를 작성, 분기를 작성할 때는 특징의 일부만을 샘플링하여 추출하고 특징의 후보로 삼음. 그 후보들로 부터 데이터를 가장 잘 분할하는 특징과 임곗값을 선택해 분기로 삼음

3) 1)과 2)의 과정을 결정트리의 개수만큼 병렬로 수행



-회귀문제일때는 제곱오차, 분류문제일때는 지니 불순도가 가장 감소하도록 분기를 시행

-결정트리마다 원래 개수와 같은 수만큼 행 데이터를 복원 추출하는 부트스트랩 샘플링을 실시.

부트스트랩 샘플링에서는 중복 추출되는 행 데이터가 있는 한편, 평균적으로 행데이터의 1/3 정도는 추출되지 않음

-분기마다 특징의 일부를 샘플링한 것을 후보로 삼고 그중 분기의 특징을 선택. 회귀 문제에서는 샘플링하지 않고 모든 특징을 후보로 삼음. 분류문제에서는 특징개수의 제곱근 개수만큼 추출하여 후보로 삼음



*결정 트리의 개수와 모델 성능의 관계

결정 트리를 병렬로 작성하므로, GBDT와는 달리 결정 트리의 개수가 지나치게 증가하여 모델 성능이 낮아지는 일은 없음.

어느 정도 증가한 후에는 성능이 더 이상 올라가지 않음. 결정 트리의 개수는 계산 시간과 성능의 트레이드 오프로 결정



*예측 확률 타당성

> 분류 작업시 GBDT에서는 가중치에 기반을 둔 예측 확률의 로그 손실을 최소화하려는 반면, 랜덤 포레스트에서는 지니 불순도를 최소화하려는 각 결정 트리의 예측값의 평균을 구함.



*랜덤 포레스트 방법의 예측 확률 타당성 보증이 되지 않음

1) 데이터가 충분하지 않을 경우, 0이나 1에 가까운 확률을 예측하기 어려움

2) 모델이 로그 손실을 최소화 하도록 학습할 경우, 충분한 데이터가 있으면 타당한 확률을 예측하나 그렇지 않으면 왜곡

> GBDT,신경망, 로지스틱 회귀일때 분류문제에서는 통상적인 설정으로 로그 손실을 목적함수로 삼아 학습하지만 랜덤포레스트에서는 다른 알고리즘으로 분류하므로 확률이 왜곡됨




```python
# from sklearn.ensemble import RandomForestClassifier 
# rfc=RandomForestClassifier(n_jobs=-1)
# rfc.fit(train2,train["Category"])
```


```python
# result=rfc.predict_proba(test2)
# result
```

# CatBoostClassifier에서 score 2.41086으로 상승 (score 낮을 수록 순위 높아짐)

GBDT의 라이브러리인 CATBOOST는 범주형 변수 지원, 과적합 해소를 위한 정렬된 부스팅, GPU를 활용한 트리모델에서의 부스팅 성능 향상과 같은 기능을 지원

범주형 변수로서 지정한 특징을 자동으로 타깃 인코딩하여 수치로 변환. 타깃 인코딩을 잘못 사용하면 목적변수의 정보를 부적절하게 사용. 랜덤하게 데이터를 정렬하면서 적용하는 식의 연구 진행. 결정 트리를 작성하는 과정에서 동적으로 범주형 변수의 조합에 대해 타깃 인코딩이 이루어짐. 즉 어떤 분기에서 범주형 변수가 사용되었을 때 그 범주형 변수와 다른 범주형 변수와의 조합에 대해 타깃 인코딩 연산이 이루어지며 급다 깊은 분기에서 그 결과가 사용



데이터 수가 적을 때는 정렬부스팅이라는 알고리즘 사용. 속도는 느리지만 데이터 수가 적을 때 모델 성능이 높음.



```python
from catboost import CatBoostClassifier
cbc=CatBoostClassifier (task_type="GPU")
cbc.fit(train2,train["Category"])

result=cbc.predict_proba(test2)
result
```

<pre>
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
32:	learn: 2.4728389	total: 2.56s	remaining: 1m 15s
33:	learn: 2.4719506	total: 2.64s	remaining: 1m 14s
34:	learn: 2.4711067	total: 2.71s	remaining: 1m 14s
35:	learn: 2.4705145	total: 2.79s	remaining: 1m 14s
36:	learn: 2.4695325	total: 2.86s	remaining: 1m 14s
37:	learn: 2.4687509	total: 2.94s	remaining: 1m 14s
38:	learn: 2.4680180	total: 3.02s	remaining: 1m 14s
39:	learn: 2.4670448	total: 3.1s	remaining: 1m 14s
40:	learn: 2.4665842	total: 3.17s	remaining: 1m 14s
41:	learn: 2.4653100	total: 3.25s	remaining: 1m 14s
42:	learn: 2.4641256	total: 3.33s	remaining: 1m 14s
43:	learn: 2.4633232	total: 3.4s	remaining: 1m 13s
44:	learn: 2.4626624	total: 3.48s	remaining: 1m 13s
45:	learn: 2.4619660	total: 3.56s	remaining: 1m 13s
46:	learn: 2.4614611	total: 3.63s	remaining: 1m 13s
47:	learn: 2.4604424	total: 3.71s	remaining: 1m 13s
48:	learn: 2.4595720	total: 3.78s	remaining: 1m 13s
49:	learn: 2.4589892	total: 3.86s	remaining: 1m 13s
50:	learn: 2.4582159	total: 3.94s	remaining: 1m 13s
51:	learn: 2.4571063	total: 4.01s	remaining: 1m 13s
52:	learn: 2.4563760	total: 4.09s	remaining: 1m 13s
53:	learn: 2.4552041	total: 4.17s	remaining: 1m 12s
54:	learn: 2.4546352	total: 4.24s	remaining: 1m 12s
55:	learn: 2.4539741	total: 4.32s	remaining: 1m 12s
56:	learn: 2.4533098	total: 4.39s	remaining: 1m 12s
57:	learn: 2.4526644	total: 4.47s	remaining: 1m 12s
58:	learn: 2.4521188	total: 4.55s	remaining: 1m 12s
59:	learn: 2.4513023	total: 4.62s	remaining: 1m 12s
60:	learn: 2.4506016	total: 4.7s	remaining: 1m 12s
61:	learn: 2.4500592	total: 4.78s	remaining: 1m 12s
62:	learn: 2.4495751	total: 4.86s	remaining: 1m 12s
63:	learn: 2.4490302	total: 4.94s	remaining: 1m 12s
64:	learn: 2.4481287	total: 5.01s	remaining: 1m 12s
65:	learn: 2.4471875	total: 5.09s	remaining: 1m 12s
66:	learn: 2.4467191	total: 5.17s	remaining: 1m 12s
67:	learn: 2.4459882	total: 5.29s	remaining: 1m 12s
68:	learn: 2.4454245	total: 5.41s	remaining: 1m 12s
69:	learn: 2.4449043	total: 5.52s	remaining: 1m 13s
70:	learn: 2.4443838	total: 5.64s	remaining: 1m 13s
71:	learn: 2.4437930	total: 5.76s	remaining: 1m 14s
72:	learn: 2.4433850	total: 5.85s	remaining: 1m 14s
73:	learn: 2.4429451	total: 5.96s	remaining: 1m 14s
74:	learn: 2.4427202	total: 6.12s	remaining: 1m 15s
75:	learn: 2.4421359	total: 6.28s	remaining: 1m 16s
76:	learn: 2.4414048	total: 6.43s	remaining: 1m 17s
77:	learn: 2.4408458	total: 6.56s	remaining: 1m 17s
78:	learn: 2.4402992	total: 6.64s	remaining: 1m 17s
79:	learn: 2.4398655	total: 6.71s	remaining: 1m 17s
80:	learn: 2.4394977	total: 6.79s	remaining: 1m 17s
81:	learn: 2.4388158	total: 6.87s	remaining: 1m 16s
82:	learn: 2.4384311	total: 6.94s	remaining: 1m 16s
83:	learn: 2.4379092	total: 7.02s	remaining: 1m 16s
84:	learn: 2.4374406	total: 7.09s	remaining: 1m 16s
85:	learn: 2.4371897	total: 7.17s	remaining: 1m 16s
86:	learn: 2.4366880	total: 7.24s	remaining: 1m 16s
87:	learn: 2.4360488	total: 7.32s	remaining: 1m 15s
88:	learn: 2.4356366	total: 7.4s	remaining: 1m 15s
89:	learn: 2.4352735	total: 7.47s	remaining: 1m 15s
90:	learn: 2.4349225	total: 7.55s	remaining: 1m 15s
91:	learn: 2.4343994	total: 7.63s	remaining: 1m 15s
92:	learn: 2.4338485	total: 7.7s	remaining: 1m 15s
93:	learn: 2.4333164	total: 7.78s	remaining: 1m 14s
94:	learn: 2.4327518	total: 7.86s	remaining: 1m 14s
95:	learn: 2.4319258	total: 7.93s	remaining: 1m 14s
96:	learn: 2.4312219	total: 8.01s	remaining: 1m 14s
97:	learn: 2.4309062	total: 8.08s	remaining: 1m 14s
98:	learn: 2.4301522	total: 8.16s	remaining: 1m 14s
99:	learn: 2.4297824	total: 8.24s	remaining: 1m 14s
100:	learn: 2.4290620	total: 8.32s	remaining: 1m 14s
101:	learn: 2.4288576	total: 8.39s	remaining: 1m 13s
102:	learn: 2.4282338	total: 8.47s	remaining: 1m 13s
103:	learn: 2.4278184	total: 8.55s	remaining: 1m 13s
104:	learn: 2.4275473	total: 8.63s	remaining: 1m 13s
105:	learn: 2.4271883	total: 8.7s	remaining: 1m 13s
106:	learn: 2.4269446	total: 8.78s	remaining: 1m 13s
107:	learn: 2.4264514	total: 8.85s	remaining: 1m 13s
108:	learn: 2.4260762	total: 8.93s	remaining: 1m 13s
109:	learn: 2.4256761	total: 9.01s	remaining: 1m 12s
110:	learn: 2.4253211	total: 9.08s	remaining: 1m 12s
111:	learn: 2.4249430	total: 9.16s	remaining: 1m 12s
112:	learn: 2.4245888	total: 9.24s	remaining: 1m 12s
113:	learn: 2.4243419	total: 9.31s	remaining: 1m 12s
114:	learn: 2.4238818	total: 9.4s	remaining: 1m 12s
115:	learn: 2.4235925	total: 9.51s	remaining: 1m 12s
116:	learn: 2.4231575	total: 9.61s	remaining: 1m 12s
117:	learn: 2.4228457	total: 9.72s	remaining: 1m 12s
118:	learn: 2.4225695	total: 9.86s	remaining: 1m 13s
119:	learn: 2.4219696	total: 9.95s	remaining: 1m 12s
120:	learn: 2.4216080	total: 10.1s	remaining: 1m 13s
121:	learn: 2.4211203	total: 10.2s	remaining: 1m 13s
122:	learn: 2.4205870	total: 10.3s	remaining: 1m 13s
123:	learn: 2.4199250	total: 10.4s	remaining: 1m 13s
124:	learn: 2.4195378	total: 10.4s	remaining: 1m 13s
125:	learn: 2.4192975	total: 10.5s	remaining: 1m 12s
126:	learn: 2.4190800	total: 10.6s	remaining: 1m 12s
127:	learn: 2.4187110	total: 10.7s	remaining: 1m 12s
128:	learn: 2.4184317	total: 10.7s	remaining: 1m 12s
129:	learn: 2.4179898	total: 10.8s	remaining: 1m 12s
130:	learn: 2.4175194	total: 10.9s	remaining: 1m 12s
131:	learn: 2.4172535	total: 11s	remaining: 1m 12s
132:	learn: 2.4169013	total: 11.1s	remaining: 1m 12s
133:	learn: 2.4166664	total: 11.1s	remaining: 1m 11s
134:	learn: 2.4163891	total: 11.2s	remaining: 1m 11s
135:	learn: 2.4160605	total: 11.3s	remaining: 1m 11s
136:	learn: 2.4157966	total: 11.4s	remaining: 1m 11s
137:	learn: 2.4155326	total: 11.4s	remaining: 1m 11s
138:	learn: 2.4152957	total: 11.5s	remaining: 1m 11s
139:	learn: 2.4148234	total: 11.6s	remaining: 1m 11s
140:	learn: 2.4143368	total: 11.7s	remaining: 1m 11s
141:	learn: 2.4139715	total: 11.7s	remaining: 1m 10s
142:	learn: 2.4138072	total: 11.8s	remaining: 1m 10s
143:	learn: 2.4136381	total: 11.9s	remaining: 1m 10s
144:	learn: 2.4134260	total: 12s	remaining: 1m 10s
145:	learn: 2.4130197	total: 12s	remaining: 1m 10s
146:	learn: 2.4128038	total: 12.1s	remaining: 1m 10s
147:	learn: 2.4125322	total: 12.2s	remaining: 1m 10s
148:	learn: 2.4121894	total: 12.3s	remaining: 1m 10s
149:	learn: 2.4119673	total: 12.3s	remaining: 1m 9s
150:	learn: 2.4118341	total: 12.4s	remaining: 1m 9s
151:	learn: 2.4114898	total: 12.5s	remaining: 1m 9s
152:	learn: 2.4111940	total: 12.6s	remaining: 1m 9s
153:	learn: 2.4108390	total: 12.7s	remaining: 1m 9s
154:	learn: 2.4105437	total: 12.7s	remaining: 1m 9s
155:	learn: 2.4102510	total: 12.8s	remaining: 1m 9s
156:	learn: 2.4099065	total: 12.9s	remaining: 1m 9s
157:	learn: 2.4096901	total: 13s	remaining: 1m 9s
158:	learn: 2.4095293	total: 13s	remaining: 1m 8s
159:	learn: 2.4092889	total: 13.1s	remaining: 1m 8s
160:	learn: 2.4090364	total: 13.2s	remaining: 1m 8s
161:	learn: 2.4087292	total: 13.3s	remaining: 1m 8s
162:	learn: 2.4085401	total: 13.3s	remaining: 1m 8s
163:	learn: 2.4082907	total: 13.4s	remaining: 1m 8s
164:	learn: 2.4080521	total: 13.5s	remaining: 1m 8s
165:	learn: 2.4077905	total: 13.6s	remaining: 1m 8s
166:	learn: 2.4074383	total: 13.6s	remaining: 1m 8s
167:	learn: 2.4070912	total: 13.7s	remaining: 1m 7s
168:	learn: 2.4067905	total: 13.8s	remaining: 1m 7s
169:	learn: 2.4064184	total: 13.9s	remaining: 1m 7s
170:	learn: 2.4061997	total: 13.9s	remaining: 1m 7s
171:	learn: 2.4058800	total: 14s	remaining: 1m 7s
172:	learn: 2.4054073	total: 14.1s	remaining: 1m 7s
173:	learn: 2.4050961	total: 14.2s	remaining: 1m 7s
174:	learn: 2.4048305	total: 14.3s	remaining: 1m 7s
175:	learn: 2.4045275	total: 14.3s	remaining: 1m 7s
176:	learn: 2.4043408	total: 14.4s	remaining: 1m 7s
177:	learn: 2.4040774	total: 14.5s	remaining: 1m 6s
178:	learn: 2.4038707	total: 14.6s	remaining: 1m 6s
179:	learn: 2.4036378	total: 14.6s	remaining: 1m 6s
180:	learn: 2.4033049	total: 14.7s	remaining: 1m 6s
181:	learn: 2.4030350	total: 14.8s	remaining: 1m 6s
182:	learn: 2.4028895	total: 14.9s	remaining: 1m 6s
183:	learn: 2.4027386	total: 14.9s	remaining: 1m 6s
184:	learn: 2.4025447	total: 15s	remaining: 1m 6s
185:	learn: 2.4022609	total: 15.1s	remaining: 1m 6s
186:	learn: 2.4019588	total: 15.2s	remaining: 1m 5s
187:	learn: 2.4017558	total: 15.3s	remaining: 1m 5s
188:	learn: 2.4016370	total: 15.3s	remaining: 1m 5s
189:	learn: 2.4014289	total: 15.4s	remaining: 1m 5s
190:	learn: 2.4010585	total: 15.5s	remaining: 1m 5s
191:	learn: 2.4008814	total: 15.6s	remaining: 1m 5s
192:	learn: 2.4007063	total: 15.6s	remaining: 1m 5s
193:	learn: 2.4004819	total: 15.7s	remaining: 1m 5s
194:	learn: 2.4003211	total: 15.8s	remaining: 1m 5s
195:	learn: 2.4000728	total: 15.9s	remaining: 1m 5s
196:	learn: 2.3997752	total: 15.9s	remaining: 1m 4s
197:	learn: 2.3995241	total: 16s	remaining: 1m 4s
198:	learn: 2.3991918	total: 16.1s	remaining: 1m 4s
199:	learn: 2.3988641	total: 16.2s	remaining: 1m 4s
200:	learn: 2.3986349	total: 16.2s	remaining: 1m 4s
201:	learn: 2.3984786	total: 16.3s	remaining: 1m 4s
202:	learn: 2.3981461	total: 16.4s	remaining: 1m 4s
203:	learn: 2.3979001	total: 16.5s	remaining: 1m 4s
204:	learn: 2.3977110	total: 16.5s	remaining: 1m 4s
205:	learn: 2.3974747	total: 16.6s	remaining: 1m 4s
206:	learn: 2.3972196	total: 16.7s	remaining: 1m 3s
207:	learn: 2.3969055	total: 16.8s	remaining: 1m 3s
208:	learn: 2.3967105	total: 16.9s	remaining: 1m 3s
209:	learn: 2.3965146	total: 16.9s	remaining: 1m 3s
210:	learn: 2.3963025	total: 17s	remaining: 1m 3s
211:	learn: 2.3961661	total: 17.1s	remaining: 1m 3s
212:	learn: 2.3960027	total: 17.2s	remaining: 1m 3s
213:	learn: 2.3958111	total: 17.2s	remaining: 1m 3s
214:	learn: 2.3956844	total: 17.3s	remaining: 1m 3s
215:	learn: 2.3954637	total: 17.4s	remaining: 1m 3s
216:	learn: 2.3952806	total: 17.5s	remaining: 1m 2s
217:	learn: 2.3950537	total: 17.5s	remaining: 1m 2s
218:	learn: 2.3946508	total: 17.6s	remaining: 1m 2s
219:	learn: 2.3944831	total: 17.7s	remaining: 1m 2s
220:	learn: 2.3942092	total: 17.8s	remaining: 1m 2s
221:	learn: 2.3940518	total: 17.9s	remaining: 1m 2s
222:	learn: 2.3938413	total: 17.9s	remaining: 1m 2s
223:	learn: 2.3936623	total: 18s	remaining: 1m 2s
224:	learn: 2.3935031	total: 18.1s	remaining: 1m 2s
225:	learn: 2.3932685	total: 18.2s	remaining: 1m 2s
226:	learn: 2.3930774	total: 18.2s	remaining: 1m 2s
227:	learn: 2.3928730	total: 18.3s	remaining: 1m 2s
228:	learn: 2.3926526	total: 18.4s	remaining: 1m 1s
229:	learn: 2.3924004	total: 18.5s	remaining: 1m 1s
230:	learn: 2.3922361	total: 18.5s	remaining: 1m 1s
231:	learn: 2.3920584	total: 18.6s	remaining: 1m 1s
232:	learn: 2.3917583	total: 18.7s	remaining: 1m 1s
233:	learn: 2.3915468	total: 18.8s	remaining: 1m 1s
234:	learn: 2.3913008	total: 18.9s	remaining: 1m 1s
235:	learn: 2.3910719	total: 18.9s	remaining: 1m 1s
236:	learn: 2.3909309	total: 19s	remaining: 1m 1s
237:	learn: 2.3908039	total: 19.1s	remaining: 1m 1s
238:	learn: 2.3905762	total: 19.2s	remaining: 1m 1s
239:	learn: 2.3903398	total: 19.2s	remaining: 1m
240:	learn: 2.3901496	total: 19.3s	remaining: 1m
241:	learn: 2.3899298	total: 19.4s	remaining: 1m
242:	learn: 2.3897003	total: 19.5s	remaining: 1m
243:	learn: 2.3894882	total: 19.5s	remaining: 1m
244:	learn: 2.3893097	total: 19.6s	remaining: 1m
245:	learn: 2.3891898	total: 19.7s	remaining: 1m
246:	learn: 2.3890187	total: 19.8s	remaining: 1m
247:	learn: 2.3888228	total: 19.9s	remaining: 1m
248:	learn: 2.3886469	total: 19.9s	remaining: 1m
249:	learn: 2.3885210	total: 20s	remaining: 1m
250:	learn: 2.3882572	total: 20.1s	remaining: 59.9s
251:	learn: 2.3880571	total: 20.2s	remaining: 59.8s
252:	learn: 2.3878417	total: 20.2s	remaining: 59.8s
253:	learn: 2.3876886	total: 20.3s	remaining: 59.7s
254:	learn: 2.3874963	total: 20.4s	remaining: 59.7s
255:	learn: 2.3872769	total: 20.5s	remaining: 59.7s
256:	learn: 2.3871492	total: 20.6s	remaining: 59.7s
257:	learn: 2.3870129	total: 20.8s	remaining: 59.7s
258:	learn: 2.3868998	total: 20.9s	remaining: 59.7s
259:	learn: 2.3867227	total: 21s	remaining: 59.7s
260:	learn: 2.3865378	total: 21.1s	remaining: 59.7s
261:	learn: 2.3864501	total: 21.2s	remaining: 59.6s
262:	learn: 2.3862488	total: 21.2s	remaining: 59.5s
263:	learn: 2.3859931	total: 21.3s	remaining: 59.4s
264:	learn: 2.3857403	total: 21.4s	remaining: 59.4s
265:	learn: 2.3855569	total: 21.5s	remaining: 59.3s
266:	learn: 2.3853861	total: 21.6s	remaining: 59.2s
267:	learn: 2.3852507	total: 21.6s	remaining: 59.1s
268:	learn: 2.3851009	total: 21.7s	remaining: 59s
269:	learn: 2.3848911	total: 21.8s	remaining: 58.9s
270:	learn: 2.3846657	total: 21.9s	remaining: 58.8s
271:	learn: 2.3844323	total: 21.9s	remaining: 58.7s
272:	learn: 2.3843311	total: 22s	remaining: 58.6s
273:	learn: 2.3842381	total: 22.1s	remaining: 58.5s
274:	learn: 2.3840520	total: 22.2s	remaining: 58.4s
275:	learn: 2.3838139	total: 22.2s	remaining: 58.3s
276:	learn: 2.3837171	total: 22.3s	remaining: 58.3s
277:	learn: 2.3836006	total: 22.4s	remaining: 58.2s
278:	learn: 2.3834809	total: 22.5s	remaining: 58.1s
279:	learn: 2.3832965	total: 22.5s	remaining: 58s
280:	learn: 2.3831022	total: 22.6s	remaining: 57.9s
281:	learn: 2.3828363	total: 22.7s	remaining: 57.8s
282:	learn: 2.3826936	total: 22.8s	remaining: 57.7s
283:	learn: 2.3824994	total: 22.9s	remaining: 57.6s
284:	learn: 2.3823639	total: 22.9s	remaining: 57.5s
285:	learn: 2.3822561	total: 23s	remaining: 57.4s
286:	learn: 2.3821168	total: 23.1s	remaining: 57.3s
287:	learn: 2.3820241	total: 23.2s	remaining: 57.2s
288:	learn: 2.3818350	total: 23.2s	remaining: 57.1s
289:	learn: 2.3816060	total: 23.3s	remaining: 57.1s
290:	learn: 2.3813712	total: 23.4s	remaining: 57s
291:	learn: 2.3811564	total: 23.5s	remaining: 56.9s
292:	learn: 2.3810502	total: 23.5s	remaining: 56.8s
293:	learn: 2.3809406	total: 23.6s	remaining: 56.7s
294:	learn: 2.3807978	total: 23.7s	remaining: 56.6s
295:	learn: 2.3805888	total: 23.8s	remaining: 56.5s
296:	learn: 2.3802827	total: 23.8s	remaining: 56.4s
297:	learn: 2.3800783	total: 23.9s	remaining: 56.3s
298:	learn: 2.3799909	total: 24s	remaining: 56.3s
299:	learn: 2.3798645	total: 24.1s	remaining: 56.2s
300:	learn: 2.3796470	total: 24.1s	remaining: 56.1s
301:	learn: 2.3794758	total: 24.2s	remaining: 56s
302:	learn: 2.3793283	total: 24.3s	remaining: 55.9s
303:	learn: 2.3790888	total: 24.4s	remaining: 55.8s
304:	learn: 2.3789635	total: 24.5s	remaining: 55.7s
305:	learn: 2.3788594	total: 24.5s	remaining: 55.6s
306:	learn: 2.3787374	total: 24.6s	remaining: 55.5s
307:	learn: 2.3786237	total: 24.7s	remaining: 55.5s
308:	learn: 2.3785045	total: 24.8s	remaining: 55.4s
309:	learn: 2.3783594	total: 24.8s	remaining: 55.3s
310:	learn: 2.3780528	total: 24.9s	remaining: 55.2s
311:	learn: 2.3778844	total: 25s	remaining: 55.1s
312:	learn: 2.3777866	total: 25.1s	remaining: 55s
313:	learn: 2.3775686	total: 25.1s	remaining: 54.9s
314:	learn: 2.3774169	total: 25.2s	remaining: 54.8s
315:	learn: 2.3772886	total: 25.3s	remaining: 54.8s
316:	learn: 2.3771576	total: 25.4s	remaining: 54.7s
317:	learn: 2.3769844	total: 25.4s	remaining: 54.6s
318:	learn: 2.3768773	total: 25.5s	remaining: 54.5s
319:	learn: 2.3767293	total: 25.6s	remaining: 54.4s
320:	learn: 2.3765724	total: 25.7s	remaining: 54.3s
321:	learn: 2.3764092	total: 25.8s	remaining: 54.2s
322:	learn: 2.3762744	total: 25.8s	remaining: 54.1s
323:	learn: 2.3761793	total: 25.9s	remaining: 54.1s
324:	learn: 2.3760388	total: 26s	remaining: 54s
325:	learn: 2.3759187	total: 26.1s	remaining: 53.9s
326:	learn: 2.3757712	total: 26.1s	remaining: 53.8s
327:	learn: 2.3754836	total: 26.2s	remaining: 53.7s
328:	learn: 2.3753321	total: 26.3s	remaining: 53.6s
329:	learn: 2.3751775	total: 26.4s	remaining: 53.5s
330:	learn: 2.3749428	total: 26.4s	remaining: 53.4s
331:	learn: 2.3748359	total: 26.5s	remaining: 53.4s
332:	learn: 2.3747012	total: 26.6s	remaining: 53.3s
333:	learn: 2.3745406	total: 26.7s	remaining: 53.2s
334:	learn: 2.3743829	total: 26.8s	remaining: 53.1s
335:	learn: 2.3742794	total: 26.8s	remaining: 53s
336:	learn: 2.3742167	total: 26.9s	remaining: 52.9s
337:	learn: 2.3740601	total: 27s	remaining: 52.8s
338:	learn: 2.3739265	total: 27.1s	remaining: 52.7s
339:	learn: 2.3735831	total: 27.1s	remaining: 52.7s
340:	learn: 2.3734608	total: 27.2s	remaining: 52.6s
341:	learn: 2.3733125	total: 27.3s	remaining: 52.5s
342:	learn: 2.3731941	total: 27.4s	remaining: 52.4s
343:	learn: 2.3730158	total: 27.4s	remaining: 52.3s
344:	learn: 2.3728968	total: 27.5s	remaining: 52.2s
345:	learn: 2.3727553	total: 27.6s	remaining: 52.2s
346:	learn: 2.3726266	total: 27.7s	remaining: 52.1s
347:	learn: 2.3724607	total: 27.7s	remaining: 52s
348:	learn: 2.3723564	total: 27.8s	remaining: 51.9s
349:	learn: 2.3722420	total: 27.9s	remaining: 51.8s
350:	learn: 2.3721774	total: 28s	remaining: 51.7s
351:	learn: 2.3720208	total: 28.1s	remaining: 51.6s
352:	learn: 2.3718033	total: 28.1s	remaining: 51.6s
353:	learn: 2.3717107	total: 28.2s	remaining: 51.5s
354:	learn: 2.3716001	total: 28.3s	remaining: 51.4s
355:	learn: 2.3715110	total: 28.4s	remaining: 51.3s
356:	learn: 2.3713921	total: 28.4s	remaining: 51.2s
357:	learn: 2.3712790	total: 28.5s	remaining: 51.1s
358:	learn: 2.3711783	total: 28.6s	remaining: 51s
359:	learn: 2.3710318	total: 28.7s	remaining: 51s
360:	learn: 2.3708328	total: 28.7s	remaining: 50.9s
361:	learn: 2.3706685	total: 28.8s	remaining: 50.8s
362:	learn: 2.3705253	total: 28.9s	remaining: 50.7s
363:	learn: 2.3703501	total: 29s	remaining: 50.6s
364:	learn: 2.3702551	total: 29s	remaining: 50.5s
365:	learn: 2.3700782	total: 29.1s	remaining: 50.5s
366:	learn: 2.3699959	total: 29.2s	remaining: 50.4s
367:	learn: 2.3698585	total: 29.3s	remaining: 50.3s
368:	learn: 2.3697651	total: 29.4s	remaining: 50.2s
369:	learn: 2.3696926	total: 29.5s	remaining: 50.2s
370:	learn: 2.3695793	total: 29.5s	remaining: 50.1s
371:	learn: 2.3694271	total: 29.6s	remaining: 50s
372:	learn: 2.3693114	total: 29.7s	remaining: 49.9s
373:	learn: 2.3692470	total: 29.8s	remaining: 49.8s
374:	learn: 2.3691181	total: 29.8s	remaining: 49.7s
375:	learn: 2.3690002	total: 29.9s	remaining: 49.6s
376:	learn: 2.3689232	total: 30s	remaining: 49.6s
377:	learn: 2.3687580	total: 30.1s	remaining: 49.5s
378:	learn: 2.3686228	total: 30.1s	remaining: 49.4s
379:	learn: 2.3684100	total: 30.2s	remaining: 49.3s
380:	learn: 2.3682588	total: 30.3s	remaining: 49.2s
381:	learn: 2.3681392	total: 30.4s	remaining: 49.1s
382:	learn: 2.3680146	total: 30.5s	remaining: 49.1s
383:	learn: 2.3678200	total: 30.6s	remaining: 49.1s
384:	learn: 2.3676994	total: 30.7s	remaining: 49s
385:	learn: 2.3676059	total: 30.7s	remaining: 48.9s
386:	learn: 2.3674616	total: 30.8s	remaining: 48.8s
387:	learn: 2.3673058	total: 30.9s	remaining: 48.7s
388:	learn: 2.3672070	total: 31s	remaining: 48.6s
389:	learn: 2.3671123	total: 31s	remaining: 48.6s
390:	learn: 2.3670340	total: 31.1s	remaining: 48.5s
391:	learn: 2.3669560	total: 31.2s	remaining: 48.4s
392:	learn: 2.3668195	total: 31.3s	remaining: 48.3s
393:	learn: 2.3667107	total: 31.4s	remaining: 48.2s
394:	learn: 2.3665675	total: 31.5s	remaining: 48.2s
395:	learn: 2.3664374	total: 31.6s	remaining: 48.2s
396:	learn: 2.3662925	total: 31.7s	remaining: 48.1s
397:	learn: 2.3661846	total: 31.8s	remaining: 48.1s
398:	learn: 2.3659974	total: 31.9s	remaining: 48.1s
399:	learn: 2.3658298	total: 32.1s	remaining: 48.1s
400:	learn: 2.3657438	total: 32.2s	remaining: 48s
401:	learn: 2.3656157	total: 32.2s	remaining: 48s
402:	learn: 2.3654681	total: 32.3s	remaining: 47.9s
403:	learn: 2.3653268	total: 32.4s	remaining: 47.8s
404:	learn: 2.3651540	total: 32.5s	remaining: 47.7s
405:	learn: 2.3650105	total: 32.5s	remaining: 47.6s
406:	learn: 2.3648932	total: 32.6s	remaining: 47.5s
407:	learn: 2.3648015	total: 32.7s	remaining: 47.4s
408:	learn: 2.3646538	total: 32.8s	remaining: 47.4s
409:	learn: 2.3645685	total: 32.8s	remaining: 47.3s
410:	learn: 2.3644765	total: 32.9s	remaining: 47.2s
411:	learn: 2.3643671	total: 33s	remaining: 47.1s
412:	learn: 2.3643017	total: 33.1s	remaining: 47s
413:	learn: 2.3641964	total: 33.2s	remaining: 46.9s
414:	learn: 2.3641033	total: 33.2s	remaining: 46.8s
415:	learn: 2.3639153	total: 33.3s	remaining: 46.8s
416:	learn: 2.3636160	total: 33.4s	remaining: 46.7s
417:	learn: 2.3635130	total: 33.5s	remaining: 46.6s
418:	learn: 2.3633576	total: 33.5s	remaining: 46.5s
419:	learn: 2.3632737	total: 33.6s	remaining: 46.4s
420:	learn: 2.3631474	total: 33.7s	remaining: 46.3s
421:	learn: 2.3630657	total: 33.8s	remaining: 46.2s
422:	learn: 2.3629869	total: 33.8s	remaining: 46.2s
423:	learn: 2.3628486	total: 33.9s	remaining: 46.1s
424:	learn: 2.3627128	total: 34s	remaining: 46s
425:	learn: 2.3625939	total: 34.1s	remaining: 45.9s
426:	learn: 2.3624961	total: 34.1s	remaining: 45.8s
427:	learn: 2.3623437	total: 34.2s	remaining: 45.7s
428:	learn: 2.3622136	total: 34.3s	remaining: 45.7s
429:	learn: 2.3621005	total: 34.4s	remaining: 45.6s
430:	learn: 2.3619744	total: 34.5s	remaining: 45.5s
431:	learn: 2.3618800	total: 34.5s	remaining: 45.4s
432:	learn: 2.3617032	total: 34.6s	remaining: 45.3s
433:	learn: 2.3615759	total: 34.7s	remaining: 45.2s
434:	learn: 2.3614713	total: 34.8s	remaining: 45.2s
435:	learn: 2.3612737	total: 34.8s	remaining: 45.1s
436:	learn: 2.3610796	total: 34.9s	remaining: 45s
437:	learn: 2.3608989	total: 35s	remaining: 44.9s
438:	learn: 2.3607843	total: 35.1s	remaining: 44.8s
439:	learn: 2.3606415	total: 35.2s	remaining: 44.7s
440:	learn: 2.3605237	total: 35.2s	remaining: 44.7s
441:	learn: 2.3604409	total: 35.3s	remaining: 44.6s
442:	learn: 2.3603270	total: 35.4s	remaining: 44.5s
443:	learn: 2.3601960	total: 35.5s	remaining: 44.4s
444:	learn: 2.3600571	total: 35.5s	remaining: 44.3s
445:	learn: 2.3599311	total: 35.6s	remaining: 44.2s
446:	learn: 2.3597948	total: 35.7s	remaining: 44.2s
447:	learn: 2.3597154	total: 35.8s	remaining: 44.1s
448:	learn: 2.3596219	total: 35.9s	remaining: 44s
449:	learn: 2.3594792	total: 35.9s	remaining: 43.9s
450:	learn: 2.3593436	total: 36s	remaining: 43.8s
451:	learn: 2.3591959	total: 36.1s	remaining: 43.7s
452:	learn: 2.3590798	total: 36.2s	remaining: 43.7s
453:	learn: 2.3589719	total: 36.2s	remaining: 43.6s
454:	learn: 2.3589010	total: 36.3s	remaining: 43.5s
455:	learn: 2.3587277	total: 36.4s	remaining: 43.4s
456:	learn: 2.3585349	total: 36.5s	remaining: 43.3s
457:	learn: 2.3583852	total: 36.5s	remaining: 43.2s
458:	learn: 2.3582511	total: 36.6s	remaining: 43.2s
459:	learn: 2.3581405	total: 36.7s	remaining: 43.1s
460:	learn: 2.3580723	total: 36.8s	remaining: 43s
461:	learn: 2.3579036	total: 36.9s	remaining: 42.9s
462:	learn: 2.3578519	total: 36.9s	remaining: 42.8s
463:	learn: 2.3577508	total: 37s	remaining: 42.7s
464:	learn: 2.3576510	total: 37.1s	remaining: 42.7s
465:	learn: 2.3575518	total: 37.2s	remaining: 42.6s
466:	learn: 2.3574487	total: 37.2s	remaining: 42.5s
467:	learn: 2.3572995	total: 37.3s	remaining: 42.4s
468:	learn: 2.3572338	total: 37.4s	remaining: 42.3s
469:	learn: 2.3571667	total: 37.5s	remaining: 42.2s
470:	learn: 2.3570685	total: 37.5s	remaining: 42.2s
471:	learn: 2.3569516	total: 37.6s	remaining: 42.1s
472:	learn: 2.3568528	total: 37.7s	remaining: 42s
473:	learn: 2.3567537	total: 37.8s	remaining: 41.9s
474:	learn: 2.3566108	total: 37.8s	remaining: 41.8s
475:	learn: 2.3565039	total: 37.9s	remaining: 41.7s
476:	learn: 2.3563735	total: 38s	remaining: 41.7s
477:	learn: 2.3562536	total: 38.1s	remaining: 41.6s
478:	learn: 2.3561501	total: 38.2s	remaining: 41.6s
479:	learn: 2.3560815	total: 38.3s	remaining: 41.5s
480:	learn: 2.3560183	total: 38.4s	remaining: 41.5s
481:	learn: 2.3558930	total: 38.6s	remaining: 41.5s
482:	learn: 2.3558080	total: 38.7s	remaining: 41.4s
483:	learn: 2.3556843	total: 38.8s	remaining: 41.4s
484:	learn: 2.3556030	total: 39s	remaining: 41.4s
485:	learn: 2.3554595	total: 39.1s	remaining: 41.4s
486:	learn: 2.3553311	total: 39.3s	remaining: 41.4s
487:	learn: 2.3552296	total: 39.4s	remaining: 41.3s
488:	learn: 2.3551307	total: 39.5s	remaining: 41.3s
489:	learn: 2.3550309	total: 39.6s	remaining: 41.2s
490:	learn: 2.3549408	total: 39.6s	remaining: 41.1s
491:	learn: 2.3548599	total: 39.7s	remaining: 41s
492:	learn: 2.3547538	total: 39.8s	remaining: 40.9s
493:	learn: 2.3545843	total: 39.9s	remaining: 40.8s
494:	learn: 2.3545054	total: 39.9s	remaining: 40.7s
495:	learn: 2.3544358	total: 40s	remaining: 40.7s
496:	learn: 2.3543569	total: 40.1s	remaining: 40.6s
497:	learn: 2.3542389	total: 40.2s	remaining: 40.5s
498:	learn: 2.3541615	total: 40.2s	remaining: 40.4s
499:	learn: 2.3540274	total: 40.3s	remaining: 40.3s
500:	learn: 2.3539065	total: 40.4s	remaining: 40.2s
501:	learn: 2.3538235	total: 40.5s	remaining: 40.2s
502:	learn: 2.3537115	total: 40.6s	remaining: 40.1s
503:	learn: 2.3536144	total: 40.6s	remaining: 40s
504:	learn: 2.3534890	total: 40.7s	remaining: 39.9s
505:	learn: 2.3533806	total: 40.8s	remaining: 39.8s
506:	learn: 2.3532828	total: 40.9s	remaining: 39.7s
507:	learn: 2.3531987	total: 40.9s	remaining: 39.6s
508:	learn: 2.3530609	total: 41s	remaining: 39.6s
509:	learn: 2.3529685	total: 41.1s	remaining: 39.5s
510:	learn: 2.3528340	total: 41.2s	remaining: 39.4s
511:	learn: 2.3527682	total: 41.2s	remaining: 39.3s
512:	learn: 2.3526298	total: 41.3s	remaining: 39.3s
513:	learn: 2.3525360	total: 41.4s	remaining: 39.2s
514:	learn: 2.3524900	total: 41.5s	remaining: 39.1s
515:	learn: 2.3523969	total: 41.6s	remaining: 39s
516:	learn: 2.3523404	total: 41.7s	remaining: 38.9s
517:	learn: 2.3522235	total: 41.7s	remaining: 38.8s
518:	learn: 2.3521068	total: 41.8s	remaining: 38.8s
519:	learn: 2.3520557	total: 41.9s	remaining: 38.7s
520:	learn: 2.3520104	total: 42s	remaining: 38.6s
521:	learn: 2.3518840	total: 42s	remaining: 38.5s
522:	learn: 2.3517198	total: 42.1s	remaining: 38.4s
523:	learn: 2.3516521	total: 42.2s	remaining: 38.3s
524:	learn: 2.3515860	total: 42.3s	remaining: 38.3s
525:	learn: 2.3514866	total: 42.4s	remaining: 38.2s
526:	learn: 2.3513814	total: 42.5s	remaining: 38.2s
527:	learn: 2.3512768	total: 42.6s	remaining: 38.1s
528:	learn: 2.3511532	total: 42.7s	remaining: 38s
529:	learn: 2.3510493	total: 42.8s	remaining: 38s
530:	learn: 2.3508968	total: 42.9s	remaining: 37.9s
531:	learn: 2.3508361	total: 43s	remaining: 37.9s
532:	learn: 2.3507327	total: 43.2s	remaining: 37.8s
533:	learn: 2.3506486	total: 43.3s	remaining: 37.8s
534:	learn: 2.3505593	total: 43.4s	remaining: 37.7s
535:	learn: 2.3504648	total: 43.4s	remaining: 37.6s
536:	learn: 2.3503718	total: 43.5s	remaining: 37.5s
537:	learn: 2.3502867	total: 43.6s	remaining: 37.4s
538:	learn: 2.3501036	total: 43.7s	remaining: 37.3s
539:	learn: 2.3500420	total: 43.7s	remaining: 37.3s
540:	learn: 2.3499817	total: 43.8s	remaining: 37.2s
541:	learn: 2.3498758	total: 43.9s	remaining: 37.1s
542:	learn: 2.3497578	total: 44s	remaining: 37s
543:	learn: 2.3495913	total: 44s	remaining: 36.9s
544:	learn: 2.3494680	total: 44.1s	remaining: 36.8s
545:	learn: 2.3493568	total: 44.2s	remaining: 36.8s
546:	learn: 2.3492618	total: 44.3s	remaining: 36.7s
547:	learn: 2.3490422	total: 44.4s	remaining: 36.6s
548:	learn: 2.3489698	total: 44.4s	remaining: 36.5s
549:	learn: 2.3488562	total: 44.5s	remaining: 36.4s
550:	learn: 2.3487399	total: 44.6s	remaining: 36.3s
551:	learn: 2.3486609	total: 44.7s	remaining: 36.2s
552:	learn: 2.3485613	total: 44.7s	remaining: 36.2s
553:	learn: 2.3484818	total: 44.8s	remaining: 36.1s
554:	learn: 2.3483096	total: 44.9s	remaining: 36s
555:	learn: 2.3482169	total: 45s	remaining: 35.9s
556:	learn: 2.3481356	total: 45s	remaining: 35.8s
557:	learn: 2.3480560	total: 45.1s	remaining: 35.7s
558:	learn: 2.3479730	total: 45.2s	remaining: 35.7s
559:	learn: 2.3479272	total: 45.3s	remaining: 35.6s
560:	learn: 2.3477914	total: 45.4s	remaining: 35.5s
561:	learn: 2.3476513	total: 45.4s	remaining: 35.4s
562:	learn: 2.3475704	total: 45.5s	remaining: 35.3s
563:	learn: 2.3474877	total: 45.6s	remaining: 35.2s
564:	learn: 2.3474005	total: 45.7s	remaining: 35.2s
565:	learn: 2.3473029	total: 45.7s	remaining: 35.1s
566:	learn: 2.3472162	total: 45.8s	remaining: 35s
567:	learn: 2.3471278	total: 45.9s	remaining: 34.9s
568:	learn: 2.3470448	total: 46s	remaining: 34.8s
569:	learn: 2.3469566	total: 46s	remaining: 34.7s
570:	learn: 2.3468764	total: 46.1s	remaining: 34.7s
571:	learn: 2.3467627	total: 46.2s	remaining: 34.6s
572:	learn: 2.3467013	total: 46.3s	remaining: 34.5s
573:	learn: 2.3465993	total: 46.4s	remaining: 34.4s
574:	learn: 2.3465340	total: 46.4s	remaining: 34.3s
575:	learn: 2.3464943	total: 46.5s	remaining: 34.2s
576:	learn: 2.3463755	total: 46.6s	remaining: 34.1s
577:	learn: 2.3462563	total: 46.7s	remaining: 34.1s
578:	learn: 2.3461622	total: 46.7s	remaining: 34s
579:	learn: 2.3460754	total: 46.8s	remaining: 33.9s
580:	learn: 2.3459827	total: 46.9s	remaining: 33.8s
581:	learn: 2.3459041	total: 47s	remaining: 33.7s
582:	learn: 2.3457667	total: 47s	remaining: 33.6s
583:	learn: 2.3456330	total: 47.1s	remaining: 33.6s
584:	learn: 2.3455577	total: 47.2s	remaining: 33.5s
585:	learn: 2.3454478	total: 47.3s	remaining: 33.4s
586:	learn: 2.3453510	total: 47.3s	remaining: 33.3s
587:	learn: 2.3452215	total: 47.4s	remaining: 33.2s
588:	learn: 2.3451610	total: 47.5s	remaining: 33.1s
589:	learn: 2.3450534	total: 47.6s	remaining: 33.1s
590:	learn: 2.3449735	total: 47.7s	remaining: 33s
591:	learn: 2.3448928	total: 47.7s	remaining: 32.9s
592:	learn: 2.3448055	total: 47.8s	remaining: 32.8s
593:	learn: 2.3446556	total: 47.9s	remaining: 32.7s
594:	learn: 2.3445717	total: 48s	remaining: 32.6s
595:	learn: 2.3444551	total: 48s	remaining: 32.6s
596:	learn: 2.3443501	total: 48.1s	remaining: 32.5s
597:	learn: 2.3442479	total: 48.2s	remaining: 32.4s
598:	learn: 2.3441623	total: 48.3s	remaining: 32.3s
599:	learn: 2.3440988	total: 48.3s	remaining: 32.2s
600:	learn: 2.3439936	total: 48.4s	remaining: 32.1s
601:	learn: 2.3439596	total: 48.5s	remaining: 32.1s
602:	learn: 2.3438763	total: 48.6s	remaining: 32s
603:	learn: 2.3437643	total: 48.6s	remaining: 31.9s
604:	learn: 2.3436414	total: 48.7s	remaining: 31.8s
605:	learn: 2.3435604	total: 48.8s	remaining: 31.7s
606:	learn: 2.3434672	total: 48.9s	remaining: 31.6s
607:	learn: 2.3434011	total: 48.9s	remaining: 31.6s
608:	learn: 2.3433351	total: 49s	remaining: 31.5s
609:	learn: 2.3432176	total: 49.1s	remaining: 31.4s
610:	learn: 2.3431330	total: 49.2s	remaining: 31.3s
611:	learn: 2.3430916	total: 49.3s	remaining: 31.2s
612:	learn: 2.3430204	total: 49.3s	remaining: 31.2s
613:	learn: 2.3429186	total: 49.4s	remaining: 31.1s
614:	learn: 2.3428503	total: 49.5s	remaining: 31s
615:	learn: 2.3427901	total: 49.6s	remaining: 30.9s
616:	learn: 2.3427276	total: 49.6s	remaining: 30.8s
617:	learn: 2.3426188	total: 49.7s	remaining: 30.7s
618:	learn: 2.3425444	total: 49.8s	remaining: 30.7s
619:	learn: 2.3424602	total: 49.9s	remaining: 30.6s
620:	learn: 2.3422938	total: 50s	remaining: 30.5s
621:	learn: 2.3422090	total: 50s	remaining: 30.4s
622:	learn: 2.3421364	total: 50.1s	remaining: 30.3s
623:	learn: 2.3420539	total: 50.2s	remaining: 30.2s
624:	learn: 2.3419566	total: 50.3s	remaining: 30.2s
625:	learn: 2.3418243	total: 50.3s	remaining: 30.1s
626:	learn: 2.3417158	total: 50.4s	remaining: 30s
627:	learn: 2.3416095	total: 50.5s	remaining: 29.9s
628:	learn: 2.3415457	total: 50.6s	remaining: 29.8s
629:	learn: 2.3414864	total: 50.6s	remaining: 29.7s
630:	learn: 2.3414163	total: 50.7s	remaining: 29.7s
631:	learn: 2.3413357	total: 50.8s	remaining: 29.6s
632:	learn: 2.3412442	total: 50.9s	remaining: 29.5s
633:	learn: 2.3410978	total: 50.9s	remaining: 29.4s
634:	learn: 2.3410129	total: 51s	remaining: 29.3s
635:	learn: 2.3409358	total: 51.1s	remaining: 29.2s
636:	learn: 2.3408481	total: 51.2s	remaining: 29.2s
637:	learn: 2.3407522	total: 51.3s	remaining: 29.1s
638:	learn: 2.3406686	total: 51.3s	remaining: 29s
639:	learn: 2.3405937	total: 51.4s	remaining: 28.9s
640:	learn: 2.3405059	total: 51.5s	remaining: 28.8s
641:	learn: 2.3404266	total: 51.6s	remaining: 28.8s
642:	learn: 2.3402807	total: 51.6s	remaining: 28.7s
643:	learn: 2.3401660	total: 51.7s	remaining: 28.6s
644:	learn: 2.3401140	total: 51.8s	remaining: 28.5s
645:	learn: 2.3400102	total: 51.9s	remaining: 28.4s
646:	learn: 2.3399319	total: 51.9s	remaining: 28.3s
647:	learn: 2.3398644	total: 52s	remaining: 28.3s
648:	learn: 2.3397558	total: 52.1s	remaining: 28.2s
649:	learn: 2.3397098	total: 52.2s	remaining: 28.1s
650:	learn: 2.3395992	total: 52.3s	remaining: 28s
651:	learn: 2.3395031	total: 52.3s	remaining: 27.9s
652:	learn: 2.3394089	total: 52.4s	remaining: 27.8s
653:	learn: 2.3393108	total: 52.5s	remaining: 27.8s
654:	learn: 2.3392151	total: 52.6s	remaining: 27.7s
655:	learn: 2.3391464	total: 52.6s	remaining: 27.6s
656:	learn: 2.3390632	total: 52.7s	remaining: 27.5s
657:	learn: 2.3389658	total: 52.8s	remaining: 27.4s
658:	learn: 2.3388856	total: 52.9s	remaining: 27.4s
659:	learn: 2.3387839	total: 52.9s	remaining: 27.3s
660:	learn: 2.3386760	total: 53s	remaining: 27.2s
661:	learn: 2.3386189	total: 53.1s	remaining: 27.1s
662:	learn: 2.3384965	total: 53.2s	remaining: 27s
663:	learn: 2.3384269	total: 53.3s	remaining: 26.9s
664:	learn: 2.3383073	total: 53.4s	remaining: 26.9s
665:	learn: 2.3382328	total: 53.5s	remaining: 26.8s
666:	learn: 2.3381413	total: 53.6s	remaining: 26.8s
667:	learn: 2.3380512	total: 53.7s	remaining: 26.7s
668:	learn: 2.3379959	total: 53.8s	remaining: 26.6s
669:	learn: 2.3379313	total: 53.9s	remaining: 26.5s
670:	learn: 2.3378505	total: 54s	remaining: 26.5s
671:	learn: 2.3377871	total: 54.1s	remaining: 26.4s
672:	learn: 2.3377183	total: 54.2s	remaining: 26.3s
673:	learn: 2.3376251	total: 54.3s	remaining: 26.2s
674:	learn: 2.3375635	total: 54.3s	remaining: 26.2s
675:	learn: 2.3374151	total: 54.4s	remaining: 26.1s
676:	learn: 2.3373599	total: 54.5s	remaining: 26s
677:	learn: 2.3372819	total: 54.6s	remaining: 25.9s
678:	learn: 2.3372424	total: 54.6s	remaining: 25.8s
679:	learn: 2.3371581	total: 54.7s	remaining: 25.8s
680:	learn: 2.3370435	total: 54.8s	remaining: 25.7s
681:	learn: 2.3369845	total: 54.9s	remaining: 25.6s
682:	learn: 2.3369170	total: 55s	remaining: 25.5s
683:	learn: 2.3368329	total: 55s	remaining: 25.4s
684:	learn: 2.3367597	total: 55.1s	remaining: 25.3s
685:	learn: 2.3366294	total: 55.2s	remaining: 25.3s
686:	learn: 2.3365459	total: 55.3s	remaining: 25.2s
687:	learn: 2.3364670	total: 55.3s	remaining: 25.1s
688:	learn: 2.3363974	total: 55.4s	remaining: 25s
689:	learn: 2.3363171	total: 55.5s	remaining: 24.9s
690:	learn: 2.3362621	total: 55.6s	remaining: 24.8s
691:	learn: 2.3361918	total: 55.6s	remaining: 24.8s
692:	learn: 2.3361027	total: 55.7s	remaining: 24.7s
693:	learn: 2.3360257	total: 55.8s	remaining: 24.6s
694:	learn: 2.3359020	total: 55.9s	remaining: 24.5s
695:	learn: 2.3358469	total: 56s	remaining: 24.4s
696:	learn: 2.3357706	total: 56s	remaining: 24.4s
697:	learn: 2.3356713	total: 56.1s	remaining: 24.3s
698:	learn: 2.3355184	total: 56.2s	remaining: 24.2s
699:	learn: 2.3354551	total: 56.3s	remaining: 24.1s
700:	learn: 2.3354063	total: 56.3s	remaining: 24s
701:	learn: 2.3353596	total: 56.4s	remaining: 23.9s
702:	learn: 2.3353109	total: 56.5s	remaining: 23.9s
703:	learn: 2.3352554	total: 56.6s	remaining: 23.8s
704:	learn: 2.3352047	total: 56.6s	remaining: 23.7s
705:	learn: 2.3351188	total: 56.7s	remaining: 23.6s
706:	learn: 2.3350630	total: 56.8s	remaining: 23.5s
707:	learn: 2.3349992	total: 56.9s	remaining: 23.5s
708:	learn: 2.3349222	total: 56.9s	remaining: 23.4s
709:	learn: 2.3348543	total: 57s	remaining: 23.3s
710:	learn: 2.3347299	total: 57.1s	remaining: 23.2s
711:	learn: 2.3346365	total: 57.2s	remaining: 23.1s
712:	learn: 2.3345713	total: 57.3s	remaining: 23s
713:	learn: 2.3344914	total: 57.3s	remaining: 23s
714:	learn: 2.3344107	total: 57.4s	remaining: 22.9s
715:	learn: 2.3343331	total: 57.5s	remaining: 22.8s
716:	learn: 2.3342282	total: 57.6s	remaining: 22.7s
717:	learn: 2.3341600	total: 57.6s	remaining: 22.6s
718:	learn: 2.3340948	total: 57.7s	remaining: 22.6s
719:	learn: 2.3339787	total: 57.8s	remaining: 22.5s
720:	learn: 2.3339092	total: 57.9s	remaining: 22.4s
721:	learn: 2.3338171	total: 58s	remaining: 22.3s
722:	learn: 2.3337317	total: 58s	remaining: 22.2s
723:	learn: 2.3336586	total: 58.1s	remaining: 22.2s
724:	learn: 2.3335587	total: 58.2s	remaining: 22.1s
725:	learn: 2.3334935	total: 58.3s	remaining: 22s
726:	learn: 2.3334200	total: 58.3s	remaining: 21.9s
727:	learn: 2.3333292	total: 58.4s	remaining: 21.8s
728:	learn: 2.3332375	total: 58.5s	remaining: 21.7s
729:	learn: 2.3330989	total: 58.6s	remaining: 21.7s
730:	learn: 2.3330241	total: 58.6s	remaining: 21.6s
731:	learn: 2.3329129	total: 58.7s	remaining: 21.5s
732:	learn: 2.3328013	total: 58.8s	remaining: 21.4s
733:	learn: 2.3327390	total: 58.9s	remaining: 21.3s
734:	learn: 2.3326339	total: 59s	remaining: 21.3s
735:	learn: 2.3325928	total: 59s	remaining: 21.2s
736:	learn: 2.3325158	total: 59.1s	remaining: 21.1s
737:	learn: 2.3324031	total: 59.2s	remaining: 21s
738:	learn: 2.3323535	total: 59.3s	remaining: 20.9s
739:	learn: 2.3322596	total: 59.4s	remaining: 20.9s
740:	learn: 2.3321943	total: 59.4s	remaining: 20.8s
741:	learn: 2.3321358	total: 59.5s	remaining: 20.7s
742:	learn: 2.3320509	total: 59.6s	remaining: 20.6s
743:	learn: 2.3319642	total: 59.7s	remaining: 20.5s
744:	learn: 2.3318529	total: 59.7s	remaining: 20.4s
745:	learn: 2.3317195	total: 59.8s	remaining: 20.4s
746:	learn: 2.3316165	total: 59.9s	remaining: 20.3s
747:	learn: 2.3315725	total: 60s	remaining: 20.2s
748:	learn: 2.3314996	total: 1m	remaining: 20.1s
749:	learn: 2.3314584	total: 1m	remaining: 20s
750:	learn: 2.3313473	total: 1m	remaining: 20s
751:	learn: 2.3312455	total: 1m	remaining: 19.9s
752:	learn: 2.3311862	total: 1m	remaining: 19.8s
753:	learn: 2.3310870	total: 1m	remaining: 19.7s
754:	learn: 2.3310240	total: 1m	remaining: 19.6s
755:	learn: 2.3309343	total: 1m	remaining: 19.6s
756:	learn: 2.3307945	total: 1m	remaining: 19.5s
757:	learn: 2.3306712	total: 1m	remaining: 19.4s
758:	learn: 2.3305882	total: 1m	remaining: 19.3s
759:	learn: 2.3305087	total: 1m	remaining: 19.2s
760:	learn: 2.3304387	total: 1m 1s	remaining: 19.2s
761:	learn: 2.3303597	total: 1m 1s	remaining: 19.1s
762:	learn: 2.3302857	total: 1m 1s	remaining: 19s
763:	learn: 2.3302317	total: 1m 1s	remaining: 18.9s
764:	learn: 2.3301530	total: 1m 1s	remaining: 18.8s
765:	learn: 2.3300737	total: 1m 1s	remaining: 18.8s
766:	learn: 2.3300005	total: 1m 1s	remaining: 18.7s
767:	learn: 2.3298818	total: 1m 1s	remaining: 18.6s
768:	learn: 2.3298409	total: 1m 1s	remaining: 18.5s
769:	learn: 2.3297534	total: 1m 1s	remaining: 18.4s
770:	learn: 2.3296446	total: 1m 1s	remaining: 18.4s
771:	learn: 2.3295811	total: 1m 1s	remaining: 18.3s
772:	learn: 2.3295203	total: 1m 1s	remaining: 18.2s
773:	learn: 2.3294587	total: 1m 2s	remaining: 18.1s
774:	learn: 2.3293901	total: 1m 2s	remaining: 18s
775:	learn: 2.3293112	total: 1m 2s	remaining: 17.9s
776:	learn: 2.3292303	total: 1m 2s	remaining: 17.9s
777:	learn: 2.3291600	total: 1m 2s	remaining: 17.8s
778:	learn: 2.3290626	total: 1m 2s	remaining: 17.7s
779:	learn: 2.3290003	total: 1m 2s	remaining: 17.6s
780:	learn: 2.3289231	total: 1m 2s	remaining: 17.5s
781:	learn: 2.3287967	total: 1m 2s	remaining: 17.5s
782:	learn: 2.3287245	total: 1m 2s	remaining: 17.4s
783:	learn: 2.3286518	total: 1m 2s	remaining: 17.3s
784:	learn: 2.3285526	total: 1m 2s	remaining: 17.2s
785:	learn: 2.3284457	total: 1m 2s	remaining: 17.1s
786:	learn: 2.3283918	total: 1m 3s	remaining: 17.1s
787:	learn: 2.3283236	total: 1m 3s	remaining: 17s
788:	learn: 2.3282553	total: 1m 3s	remaining: 16.9s
789:	learn: 2.3281743	total: 1m 3s	remaining: 16.8s
790:	learn: 2.3280953	total: 1m 3s	remaining: 16.7s
791:	learn: 2.3280193	total: 1m 3s	remaining: 16.7s
792:	learn: 2.3279499	total: 1m 3s	remaining: 16.6s
793:	learn: 2.3278728	total: 1m 3s	remaining: 16.5s
794:	learn: 2.3278119	total: 1m 3s	remaining: 16.4s
795:	learn: 2.3277267	total: 1m 3s	remaining: 16.3s
796:	learn: 2.3276039	total: 1m 3s	remaining: 16.2s
797:	learn: 2.3275394	total: 1m 3s	remaining: 16.2s
798:	learn: 2.3274883	total: 1m 3s	remaining: 16.1s
799:	learn: 2.3274037	total: 1m 4s	remaining: 16s
800:	learn: 2.3273624	total: 1m 4s	remaining: 15.9s
801:	learn: 2.3272524	total: 1m 4s	remaining: 15.8s
802:	learn: 2.3271328	total: 1m 4s	remaining: 15.8s
803:	learn: 2.3270495	total: 1m 4s	remaining: 15.7s
804:	learn: 2.3270057	total: 1m 4s	remaining: 15.6s
805:	learn: 2.3269151	total: 1m 4s	remaining: 15.6s
806:	learn: 2.3268790	total: 1m 4s	remaining: 15.5s
807:	learn: 2.3268079	total: 1m 4s	remaining: 15.4s
808:	learn: 2.3267588	total: 1m 5s	remaining: 15.4s
809:	learn: 2.3267148	total: 1m 5s	remaining: 15.3s
810:	learn: 2.3266620	total: 1m 5s	remaining: 15.2s
811:	learn: 2.3265930	total: 1m 5s	remaining: 15.1s
812:	learn: 2.3264876	total: 1m 5s	remaining: 15s
813:	learn: 2.3264221	total: 1m 5s	remaining: 15s
814:	learn: 2.3263407	total: 1m 5s	remaining: 14.9s
815:	learn: 2.3262248	total: 1m 5s	remaining: 14.8s
816:	learn: 2.3261388	total: 1m 5s	remaining: 14.7s
817:	learn: 2.3260755	total: 1m 5s	remaining: 14.6s
818:	learn: 2.3259489	total: 1m 5s	remaining: 14.5s
819:	learn: 2.3258722	total: 1m 5s	remaining: 14.5s
820:	learn: 2.3258123	total: 1m 5s	remaining: 14.4s
821:	learn: 2.3257674	total: 1m 6s	remaining: 14.3s
822:	learn: 2.3257015	total: 1m 6s	remaining: 14.2s
823:	learn: 2.3256194	total: 1m 6s	remaining: 14.1s
824:	learn: 2.3255722	total: 1m 6s	remaining: 14.1s
825:	learn: 2.3255049	total: 1m 6s	remaining: 14s
826:	learn: 2.3254374	total: 1m 6s	remaining: 13.9s
827:	learn: 2.3253560	total: 1m 6s	remaining: 13.8s
828:	learn: 2.3253143	total: 1m 6s	remaining: 13.7s
829:	learn: 2.3251950	total: 1m 6s	remaining: 13.7s
830:	learn: 2.3251457	total: 1m 6s	remaining: 13.6s
831:	learn: 2.3250856	total: 1m 6s	remaining: 13.5s
832:	learn: 2.3249942	total: 1m 6s	remaining: 13.4s
833:	learn: 2.3249263	total: 1m 6s	remaining: 13.3s
834:	learn: 2.3248747	total: 1m 7s	remaining: 13.2s
835:	learn: 2.3248220	total: 1m 7s	remaining: 13.2s
836:	learn: 2.3247346	total: 1m 7s	remaining: 13.1s
837:	learn: 2.3246719	total: 1m 7s	remaining: 13s
838:	learn: 2.3245599	total: 1m 7s	remaining: 12.9s
839:	learn: 2.3244815	total: 1m 7s	remaining: 12.8s
840:	learn: 2.3243650	total: 1m 7s	remaining: 12.8s
841:	learn: 2.3242851	total: 1m 7s	remaining: 12.7s
842:	learn: 2.3242171	total: 1m 7s	remaining: 12.6s
843:	learn: 2.3241345	total: 1m 7s	remaining: 12.5s
844:	learn: 2.3240631	total: 1m 7s	remaining: 12.4s
845:	learn: 2.3240075	total: 1m 7s	remaining: 12.4s
846:	learn: 2.3239072	total: 1m 7s	remaining: 12.3s
847:	learn: 2.3238632	total: 1m 8s	remaining: 12.2s
848:	learn: 2.3237856	total: 1m 8s	remaining: 12.1s
849:	learn: 2.3237027	total: 1m 8s	remaining: 12s
850:	learn: 2.3236543	total: 1m 8s	remaining: 12s
851:	learn: 2.3235667	total: 1m 8s	remaining: 11.9s
852:	learn: 2.3235016	total: 1m 8s	remaining: 11.8s
853:	learn: 2.3234521	total: 1m 8s	remaining: 11.7s
854:	learn: 2.3233467	total: 1m 8s	remaining: 11.6s
855:	learn: 2.3232855	total: 1m 8s	remaining: 11.6s
856:	learn: 2.3232089	total: 1m 8s	remaining: 11.5s
857:	learn: 2.3231135	total: 1m 8s	remaining: 11.4s
858:	learn: 2.3230241	total: 1m 8s	remaining: 11.3s
859:	learn: 2.3229195	total: 1m 8s	remaining: 11.2s
860:	learn: 2.3228315	total: 1m 9s	remaining: 11.1s
861:	learn: 2.3227646	total: 1m 9s	remaining: 11.1s
862:	learn: 2.3226908	total: 1m 9s	remaining: 11s
863:	learn: 2.3226100	total: 1m 9s	remaining: 10.9s
864:	learn: 2.3225089	total: 1m 9s	remaining: 10.8s
865:	learn: 2.3224661	total: 1m 9s	remaining: 10.7s
866:	learn: 2.3223926	total: 1m 9s	remaining: 10.7s
867:	learn: 2.3223469	total: 1m 9s	remaining: 10.6s
868:	learn: 2.3222168	total: 1m 9s	remaining: 10.5s
869:	learn: 2.3221063	total: 1m 9s	remaining: 10.4s
870:	learn: 2.3220518	total: 1m 9s	remaining: 10.3s
871:	learn: 2.3220116	total: 1m 9s	remaining: 10.3s
872:	learn: 2.3219541	total: 1m 9s	remaining: 10.2s
873:	learn: 2.3218627	total: 1m 10s	remaining: 10.1s
874:	learn: 2.3218102	total: 1m 10s	remaining: 10s
875:	learn: 2.3217669	total: 1m 10s	remaining: 9.95s
876:	learn: 2.3216861	total: 1m 10s	remaining: 9.88s
877:	learn: 2.3215955	total: 1m 10s	remaining: 9.81s
878:	learn: 2.3215013	total: 1m 10s	remaining: 9.73s
879:	learn: 2.3214325	total: 1m 10s	remaining: 9.66s
880:	learn: 2.3213821	total: 1m 10s	remaining: 9.58s
881:	learn: 2.3213216	total: 1m 11s	remaining: 9.51s
882:	learn: 2.3212511	total: 1m 11s	remaining: 9.43s
883:	learn: 2.3211790	total: 1m 11s	remaining: 9.36s
884:	learn: 2.3211370	total: 1m 11s	remaining: 9.28s
885:	learn: 2.3210876	total: 1m 11s	remaining: 9.2s
886:	learn: 2.3210181	total: 1m 11s	remaining: 9.12s
887:	learn: 2.3208920	total: 1m 11s	remaining: 9.04s
888:	learn: 2.3208141	total: 1m 11s	remaining: 8.96s
889:	learn: 2.3207566	total: 1m 11s	remaining: 8.87s
890:	learn: 2.3206764	total: 1m 11s	remaining: 8.79s
891:	learn: 2.3206332	total: 1m 11s	remaining: 8.71s
892:	learn: 2.3205645	total: 1m 12s	remaining: 8.63s
893:	learn: 2.3205396	total: 1m 12s	remaining: 8.55s
894:	learn: 2.3204064	total: 1m 12s	remaining: 8.47s
895:	learn: 2.3203305	total: 1m 12s	remaining: 8.39s
896:	learn: 2.3202280	total: 1m 12s	remaining: 8.31s
897:	learn: 2.3200996	total: 1m 12s	remaining: 8.22s
898:	learn: 2.3200156	total: 1m 12s	remaining: 8.14s
899:	learn: 2.3199518	total: 1m 12s	remaining: 8.06s
900:	learn: 2.3198957	total: 1m 12s	remaining: 7.98s
901:	learn: 2.3197820	total: 1m 12s	remaining: 7.9s
902:	learn: 2.3196996	total: 1m 12s	remaining: 7.82s
903:	learn: 2.3196057	total: 1m 12s	remaining: 7.74s
904:	learn: 2.3195209	total: 1m 12s	remaining: 7.66s
905:	learn: 2.3194628	total: 1m 13s	remaining: 7.58s
906:	learn: 2.3193906	total: 1m 13s	remaining: 7.5s
907:	learn: 2.3193111	total: 1m 13s	remaining: 7.42s
908:	learn: 2.3192720	total: 1m 13s	remaining: 7.33s
909:	learn: 2.3192232	total: 1m 13s	remaining: 7.25s
910:	learn: 2.3191836	total: 1m 13s	remaining: 7.17s
911:	learn: 2.3190988	total: 1m 13s	remaining: 7.09s
912:	learn: 2.3190285	total: 1m 13s	remaining: 7.01s
913:	learn: 2.3189653	total: 1m 13s	remaining: 6.93s
914:	learn: 2.3189092	total: 1m 13s	remaining: 6.85s
915:	learn: 2.3188228	total: 1m 13s	remaining: 6.77s
916:	learn: 2.3187698	total: 1m 13s	remaining: 6.69s
917:	learn: 2.3187052	total: 1m 13s	remaining: 6.61s
918:	learn: 2.3186465	total: 1m 14s	remaining: 6.52s
919:	learn: 2.3185994	total: 1m 14s	remaining: 6.44s
920:	learn: 2.3185104	total: 1m 14s	remaining: 6.36s
921:	learn: 2.3184209	total: 1m 14s	remaining: 6.28s
922:	learn: 2.3183747	total: 1m 14s	remaining: 6.2s
923:	learn: 2.3183326	total: 1m 14s	remaining: 6.12s
924:	learn: 2.3182927	total: 1m 14s	remaining: 6.04s
925:	learn: 2.3182263	total: 1m 14s	remaining: 5.96s
926:	learn: 2.3181823	total: 1m 14s	remaining: 5.88s
927:	learn: 2.3180980	total: 1m 14s	remaining: 5.8s
928:	learn: 2.3179909	total: 1m 14s	remaining: 5.72s
929:	learn: 2.3179052	total: 1m 14s	remaining: 5.63s
930:	learn: 2.3178557	total: 1m 14s	remaining: 5.55s
931:	learn: 2.3177529	total: 1m 15s	remaining: 5.47s
932:	learn: 2.3176897	total: 1m 15s	remaining: 5.39s
933:	learn: 2.3176168	total: 1m 15s	remaining: 5.31s
934:	learn: 2.3174979	total: 1m 15s	remaining: 5.24s
935:	learn: 2.3174646	total: 1m 15s	remaining: 5.16s
936:	learn: 2.3173960	total: 1m 15s	remaining: 5.08s
937:	learn: 2.3173524	total: 1m 15s	remaining: 5.01s
938:	learn: 2.3172833	total: 1m 15s	remaining: 4.93s
939:	learn: 2.3171997	total: 1m 15s	remaining: 4.84s
940:	learn: 2.3171523	total: 1m 15s	remaining: 4.76s
941:	learn: 2.3171157	total: 1m 16s	remaining: 4.68s
942:	learn: 2.3170069	total: 1m 16s	remaining: 4.6s
943:	learn: 2.3169480	total: 1m 16s	remaining: 4.52s
944:	learn: 2.3168852	total: 1m 16s	remaining: 4.44s
945:	learn: 2.3168474	total: 1m 16s	remaining: 4.36s
946:	learn: 2.3167760	total: 1m 16s	remaining: 4.28s
947:	learn: 2.3166852	total: 1m 16s	remaining: 4.2s
948:	learn: 2.3166174	total: 1m 16s	remaining: 4.12s
949:	learn: 2.3165481	total: 1m 16s	remaining: 4.04s
950:	learn: 2.3164559	total: 1m 16s	remaining: 3.96s
951:	learn: 2.3163982	total: 1m 16s	remaining: 3.88s
952:	learn: 2.3163437	total: 1m 16s	remaining: 3.79s
953:	learn: 2.3162815	total: 1m 17s	remaining: 3.71s
954:	learn: 2.3162267	total: 1m 17s	remaining: 3.63s
955:	learn: 2.3161812	total: 1m 17s	remaining: 3.55s
956:	learn: 2.3161121	total: 1m 17s	remaining: 3.47s
957:	learn: 2.3160618	total: 1m 17s	remaining: 3.39s
958:	learn: 2.3160261	total: 1m 17s	remaining: 3.31s
959:	learn: 2.3159364	total: 1m 17s	remaining: 3.23s
960:	learn: 2.3158826	total: 1m 17s	remaining: 3.15s
961:	learn: 2.3158224	total: 1m 17s	remaining: 3.07s
962:	learn: 2.3157275	total: 1m 17s	remaining: 2.98s
963:	learn: 2.3156270	total: 1m 17s	remaining: 2.9s
964:	learn: 2.3155769	total: 1m 17s	remaining: 2.82s
965:	learn: 2.3155288	total: 1m 17s	remaining: 2.74s
966:	learn: 2.3154669	total: 1m 18s	remaining: 2.66s
967:	learn: 2.3153872	total: 1m 18s	remaining: 2.58s
968:	learn: 2.3153242	total: 1m 18s	remaining: 2.5s
969:	learn: 2.3152451	total: 1m 18s	remaining: 2.42s
970:	learn: 2.3151518	total: 1m 18s	remaining: 2.34s
971:	learn: 2.3151026	total: 1m 18s	remaining: 2.26s
972:	learn: 2.3150562	total: 1m 18s	remaining: 2.18s
973:	learn: 2.3149706	total: 1m 18s	remaining: 2.1s
974:	learn: 2.3149087	total: 1m 18s	remaining: 2.02s
975:	learn: 2.3148692	total: 1m 18s	remaining: 1.94s
976:	learn: 2.3147835	total: 1m 18s	remaining: 1.85s
977:	learn: 2.3147210	total: 1m 18s	remaining: 1.77s
978:	learn: 2.3146547	total: 1m 18s	remaining: 1.69s
979:	learn: 2.3145790	total: 1m 19s	remaining: 1.61s
980:	learn: 2.3145213	total: 1m 19s	remaining: 1.53s
981:	learn: 2.3144440	total: 1m 19s	remaining: 1.45s
982:	learn: 2.3144113	total: 1m 19s	remaining: 1.37s
983:	learn: 2.3143122	total: 1m 19s	remaining: 1.29s
984:	learn: 2.3142448	total: 1m 19s	remaining: 1.21s
985:	learn: 2.3141806	total: 1m 19s	remaining: 1.13s
986:	learn: 2.3140760	total: 1m 19s	remaining: 1.05s
987:	learn: 2.3140169	total: 1m 19s	remaining: 967ms
988:	learn: 2.3139805	total: 1m 19s	remaining: 887ms
989:	learn: 2.3139324	total: 1m 19s	remaining: 806ms
990:	learn: 2.3138696	total: 1m 19s	remaining: 725ms
991:	learn: 2.3137819	total: 1m 19s	remaining: 645ms
992:	learn: 2.3136970	total: 1m 20s	remaining: 564ms
993:	learn: 2.3136368	total: 1m 20s	remaining: 484ms
994:	learn: 2.3135787	total: 1m 20s	remaining: 403ms
995:	learn: 2.3134935	total: 1m 20s	remaining: 322ms
996:	learn: 2.3134485	total: 1m 20s	remaining: 242ms
997:	learn: 2.3133665	total: 1m 20s	remaining: 161ms
998:	learn: 2.3132940	total: 1m 20s	remaining: 80.6ms
999:	learn: 2.3132355	total: 1m 20s	remaining: 0us
</pre>
<pre>
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
</pre>
**GBM에 비해 시간은 적게 걸리고, RANDOM FOREST에 비해 성능이 좋다.

약한 학습기를 순차적으로 학습-예측하면서 잘못 예측한 데이터에 가중치 부여를 통해 오류를 개선해 나가면서 학습하는 방식이기 때문에**


GBM(Gradient Boosting Machine)

부스팅 알고리즘은 여러개의 약한 학습기를 순차적으로 학습-예측하면서 잘못 예측한 데이터에 가중치 부여를 통해 오류를 개선해 나가면서 학습하는 방식. 랜덤 포레스트보다는 예측성능이 조금 뛰어난 경우가 많음. 그러나 수행시간이 오래 걸리고, 하이퍼 파라미터 튜닝 노력도 더 필요. 약한 학습기의 순차적인 예측 오류 보정을 통해 학습을 수행하므로 멀티 cpu코어 시스템을 사용하더라도 병렬 처리가 되지않아서 대용량 데이터의 경우 학습에 매우 많은 시간이 필요. => 5시간 이상 소요되어 pause



```python
# from sklearn.ensemble import GradientBoostingClassifier
# gbc=GradientBoostingClassifier(random_state=0)
# gbc.fit(train2,train["Category"])
# result=gbc.predict_proba(test2)
# result
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



```python
sub.to_csv("cbc.csv",index=False)
```
