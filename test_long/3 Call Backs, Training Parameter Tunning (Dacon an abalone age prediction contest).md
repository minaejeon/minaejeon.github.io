# 3. Call Backs, Training Parameter Tunning (Dacon an abalone age prediction contest)



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


/kaggle/input/abalone-age-predict/sample_submission.csv
/kaggle/input/abalone-age-predict/train.csv
/kaggle/input/abalone-age-predict/test.csv

1. train.csv : 학습 데이터
id : 샘플 아이디
Gender : 전복 성별
Lenght : 전복 길이
Diameter : 전복 둘레
Height : 전복 키 
Whole : Weight : 전복 전체 무게
Shucked Weight : 껍질을 제외한 무게
Viscra Weight : 내장 무게
Shell Weight : 껍질 무게
Target : 전복 나이

2. test.csv : 테스트 데이터
id : 샘플 아이디
Gender : 전복 성별
Lenght : 전복 길이
Diameter : 전복 둘레
Height : 전복 키 
Whole : Weight : 전복 전체 무게
Shucked Weight : 껍질을 제외한 무게
Viscra Weight : 내장 무게
Shell Weight : 껍질 무게

3. sample_submission.csv : 제출 양식
id : 샘플 아이디
Target : 전복 나이

```python
train=pd.read_csv('/kaggle/input/abalone-age-predict/train.csv')
test=pd.read_csv('/kaggle/input/abalone-age-predict/test.csv')
sub=pd.read_csv('/kaggle/input/abalone-age-predict/sample_submission.csv')
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>Gender</th>
      <th>Lenght</th>
      <th>Diameter</th>
      <th>Height</th>
      <th>Whole Weight</th>
      <th>Shucked Weight</th>
      <th>Viscra Weight</th>
      <th>Shell Weight</th>
      <th>Target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>M</td>
      <td>0.605</td>
      <td>0.470</td>
      <td>0.115</td>
      <td>1.1140</td>
      <td>0.3925</td>
      <td>0.2910</td>
      <td>0.3100</td>
      <td>15</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>I</td>
      <td>0.430</td>
      <td>0.315</td>
      <td>0.095</td>
      <td>0.3780</td>
      <td>0.1750</td>
      <td>0.0800</td>
      <td>0.1045</td>
      <td>8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>I</td>
      <td>0.580</td>
      <td>0.490</td>
      <td>0.195</td>
      <td>1.3165</td>
      <td>0.5305</td>
      <td>0.2540</td>
      <td>0.4100</td>
      <td>18</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>M</td>
      <td>0.535</td>
      <td>0.405</td>
      <td>0.175</td>
      <td>1.2705</td>
      <td>0.5480</td>
      <td>0.3265</td>
      <td>0.3370</td>
      <td>13</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>I</td>
      <td>0.310</td>
      <td>0.235</td>
      <td>0.090</td>
      <td>0.1270</td>
      <td>0.0480</td>
      <td>0.0310</td>
      <td>0.0400</td>
      <td>6</td>
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
      <th>1248</th>
      <td>1249</td>
      <td>I</td>
      <td>0.190</td>
      <td>0.145</td>
      <td>0.040</td>
      <td>0.0380</td>
      <td>0.0165</td>
      <td>0.0065</td>
      <td>0.0150</td>
      <td>4</td>
    </tr>
    <tr>
      <th>1249</th>
      <td>1250</td>
      <td>I</td>
      <td>0.395</td>
      <td>0.310</td>
      <td>0.085</td>
      <td>0.3170</td>
      <td>0.1530</td>
      <td>0.0505</td>
      <td>0.0935</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1250</th>
      <td>1251</td>
      <td>F</td>
      <td>0.525</td>
      <td>0.410</td>
      <td>0.115</td>
      <td>0.7745</td>
      <td>0.4160</td>
      <td>0.1630</td>
      <td>0.1800</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1251</th>
      <td>1252</td>
      <td>F</td>
      <td>0.445</td>
      <td>0.335</td>
      <td>0.110</td>
      <td>0.4355</td>
      <td>0.2025</td>
      <td>0.1095</td>
      <td>0.1195</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1252</th>
      <td>1253</td>
      <td>F</td>
      <td>0.750</td>
      <td>0.550</td>
      <td>0.195</td>
      <td>1.8325</td>
      <td>0.8300</td>
      <td>0.3660</td>
      <td>0.4400</td>
      <td>11</td>
    </tr>
  </tbody>
</table>
<p>1253 rows × 10 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>Gender</th>
      <th>Lenght</th>
      <th>Diameter</th>
      <th>Height</th>
      <th>Whole Weight</th>
      <th>Shucked Weight</th>
      <th>Viscra Weight</th>
      <th>Shell Weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>F</td>
      <td>0.595</td>
      <td>0.470</td>
      <td>0.155</td>
      <td>1.1210</td>
      <td>0.4515</td>
      <td>0.1780</td>
      <td>0.1550</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>M</td>
      <td>0.580</td>
      <td>0.450</td>
      <td>0.150</td>
      <td>0.9270</td>
      <td>0.2760</td>
      <td>0.1815</td>
      <td>0.3600</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>I</td>
      <td>0.260</td>
      <td>0.205</td>
      <td>0.070</td>
      <td>0.0970</td>
      <td>0.0415</td>
      <td>0.0190</td>
      <td>0.0305</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>M</td>
      <td>0.590</td>
      <td>0.460</td>
      <td>0.130</td>
      <td>1.1020</td>
      <td>0.4550</td>
      <td>0.2055</td>
      <td>0.3300</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>F</td>
      <td>0.595</td>
      <td>0.465</td>
      <td>0.140</td>
      <td>1.1130</td>
      <td>0.5175</td>
      <td>0.2440</td>
      <td>0.3050</td>
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
      <th>2919</th>
      <td>2920</td>
      <td>I</td>
      <td>0.170</td>
      <td>0.105</td>
      <td>0.035</td>
      <td>0.0340</td>
      <td>0.0120</td>
      <td>0.0085</td>
      <td>0.0050</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>2921</td>
      <td>I</td>
      <td>0.435</td>
      <td>0.345</td>
      <td>0.115</td>
      <td>0.4180</td>
      <td>0.2220</td>
      <td>0.0735</td>
      <td>0.1060</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>2922</td>
      <td>I</td>
      <td>0.570</td>
      <td>0.450</td>
      <td>0.135</td>
      <td>0.7940</td>
      <td>0.3815</td>
      <td>0.1415</td>
      <td>0.2450</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>2923</td>
      <td>I</td>
      <td>0.460</td>
      <td>0.350</td>
      <td>0.120</td>
      <td>0.4885</td>
      <td>0.1930</td>
      <td>0.1050</td>
      <td>0.1550</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>2924</td>
      <td>F</td>
      <td>0.565</td>
      <td>0.440</td>
      <td>0.160</td>
      <td>0.9150</td>
      <td>0.3540</td>
      <td>0.1935</td>
      <td>0.3200</td>
    </tr>
  </tbody>
</table>
<p>2924 rows × 9 columns</p>
</div>



```python
alldata=pd.concat([train,test])
alldata
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>Gender</th>
      <th>Lenght</th>
      <th>Diameter</th>
      <th>Height</th>
      <th>Whole Weight</th>
      <th>Shucked Weight</th>
      <th>Viscra Weight</th>
      <th>Shell Weight</th>
      <th>Target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>M</td>
      <td>0.605</td>
      <td>0.470</td>
      <td>0.115</td>
      <td>1.1140</td>
      <td>0.3925</td>
      <td>0.2910</td>
      <td>0.3100</td>
      <td>15.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>I</td>
      <td>0.430</td>
      <td>0.315</td>
      <td>0.095</td>
      <td>0.3780</td>
      <td>0.1750</td>
      <td>0.0800</td>
      <td>0.1045</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>I</td>
      <td>0.580</td>
      <td>0.490</td>
      <td>0.195</td>
      <td>1.3165</td>
      <td>0.5305</td>
      <td>0.2540</td>
      <td>0.4100</td>
      <td>18.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>M</td>
      <td>0.535</td>
      <td>0.405</td>
      <td>0.175</td>
      <td>1.2705</td>
      <td>0.5480</td>
      <td>0.3265</td>
      <td>0.3370</td>
      <td>13.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>I</td>
      <td>0.310</td>
      <td>0.235</td>
      <td>0.090</td>
      <td>0.1270</td>
      <td>0.0480</td>
      <td>0.0310</td>
      <td>0.0400</td>
      <td>6.0</td>
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
      <th>2919</th>
      <td>2920</td>
      <td>I</td>
      <td>0.170</td>
      <td>0.105</td>
      <td>0.035</td>
      <td>0.0340</td>
      <td>0.0120</td>
      <td>0.0085</td>
      <td>0.0050</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>2921</td>
      <td>I</td>
      <td>0.435</td>
      <td>0.345</td>
      <td>0.115</td>
      <td>0.4180</td>
      <td>0.2220</td>
      <td>0.0735</td>
      <td>0.1060</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>2922</td>
      <td>I</td>
      <td>0.570</td>
      <td>0.450</td>
      <td>0.135</td>
      <td>0.7940</td>
      <td>0.3815</td>
      <td>0.1415</td>
      <td>0.2450</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>2923</td>
      <td>I</td>
      <td>0.460</td>
      <td>0.350</td>
      <td>0.120</td>
      <td>0.4885</td>
      <td>0.1930</td>
      <td>0.1050</td>
      <td>0.1550</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>2924</td>
      <td>F</td>
      <td>0.565</td>
      <td>0.440</td>
      <td>0.160</td>
      <td>0.9150</td>
      <td>0.3540</td>
      <td>0.1935</td>
      <td>0.3200</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>4177 rows × 10 columns</p>
</div>



```python
alldata['weight']=alldata['Whole Weight']-alldata['Shucked Weight']-alldata['Viscra Weight']-alldata['Shell Weight']
alldata['ratio']=alldata['Diameter']/alldata['Height']
alldata['ratio2']=(alldata['Lenght']*alldata['Height'])/alldata['Diameter']
```


```python
alldata2=alldata.drop(columns=['id','Target'])
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Gender</th>
      <th>Lenght</th>
      <th>Diameter</th>
      <th>Height</th>
      <th>Whole Weight</th>
      <th>Shucked Weight</th>
      <th>Viscra Weight</th>
      <th>Shell Weight</th>
      <th>weight</th>
      <th>ratio</th>
      <th>ratio2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>M</td>
      <td>0.605</td>
      <td>0.470</td>
      <td>0.115</td>
      <td>1.1140</td>
      <td>0.3925</td>
      <td>0.2910</td>
      <td>0.3100</td>
      <td>0.1205</td>
      <td>4.086957</td>
      <td>0.148032</td>
    </tr>
    <tr>
      <th>1</th>
      <td>I</td>
      <td>0.430</td>
      <td>0.315</td>
      <td>0.095</td>
      <td>0.3780</td>
      <td>0.1750</td>
      <td>0.0800</td>
      <td>0.1045</td>
      <td>0.0185</td>
      <td>3.315789</td>
      <td>0.129683</td>
    </tr>
    <tr>
      <th>2</th>
      <td>I</td>
      <td>0.580</td>
      <td>0.490</td>
      <td>0.195</td>
      <td>1.3165</td>
      <td>0.5305</td>
      <td>0.2540</td>
      <td>0.4100</td>
      <td>0.1220</td>
      <td>2.512821</td>
      <td>0.230816</td>
    </tr>
    <tr>
      <th>3</th>
      <td>M</td>
      <td>0.535</td>
      <td>0.405</td>
      <td>0.175</td>
      <td>1.2705</td>
      <td>0.5480</td>
      <td>0.3265</td>
      <td>0.3370</td>
      <td>0.0590</td>
      <td>2.314286</td>
      <td>0.231173</td>
    </tr>
    <tr>
      <th>4</th>
      <td>I</td>
      <td>0.310</td>
      <td>0.235</td>
      <td>0.090</td>
      <td>0.1270</td>
      <td>0.0480</td>
      <td>0.0310</td>
      <td>0.0400</td>
      <td>0.0080</td>
      <td>2.611111</td>
      <td>0.118723</td>
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
      <th>2919</th>
      <td>I</td>
      <td>0.170</td>
      <td>0.105</td>
      <td>0.035</td>
      <td>0.0340</td>
      <td>0.0120</td>
      <td>0.0085</td>
      <td>0.0050</td>
      <td>0.0085</td>
      <td>3.000000</td>
      <td>0.056667</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>I</td>
      <td>0.435</td>
      <td>0.345</td>
      <td>0.115</td>
      <td>0.4180</td>
      <td>0.2220</td>
      <td>0.0735</td>
      <td>0.1060</td>
      <td>0.0165</td>
      <td>3.000000</td>
      <td>0.145000</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>I</td>
      <td>0.570</td>
      <td>0.450</td>
      <td>0.135</td>
      <td>0.7940</td>
      <td>0.3815</td>
      <td>0.1415</td>
      <td>0.2450</td>
      <td>0.0260</td>
      <td>3.333333</td>
      <td>0.171000</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>I</td>
      <td>0.460</td>
      <td>0.350</td>
      <td>0.120</td>
      <td>0.4885</td>
      <td>0.1930</td>
      <td>0.1050</td>
      <td>0.1550</td>
      <td>0.0355</td>
      <td>2.916667</td>
      <td>0.157714</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>F</td>
      <td>0.565</td>
      <td>0.440</td>
      <td>0.160</td>
      <td>0.9150</td>
      <td>0.3540</td>
      <td>0.1935</td>
      <td>0.3200</td>
      <td>0.0475</td>
      <td>2.750000</td>
      <td>0.205455</td>
    </tr>
  </tbody>
</table>
<p>4177 rows × 11 columns</p>
</div>

-----------------------
Gender column(categorical : M,F,I)을 제외한 column은 연속형 변수 data 입니다.
따라서 get_dummies를 사용하여 Gender column을 3가지의 column으로 나눠준 후 True, False의 형식으로 바꾸어 줍니다.

---------------------------

```python
alldata2=pd.get_dummies(alldata2)
alldata2
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Lenght</th>
      <th>Diameter</th>
      <th>Height</th>
      <th>Whole Weight</th>
      <th>Shucked Weight</th>
      <th>Viscra Weight</th>
      <th>Shell Weight</th>
      <th>weight</th>
      <th>ratio</th>
      <th>ratio2</th>
      <th>Gender_F</th>
      <th>Gender_I</th>
      <th>Gender_M</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.605</td>
      <td>0.470</td>
      <td>0.115</td>
      <td>1.1140</td>
      <td>0.3925</td>
      <td>0.2910</td>
      <td>0.3100</td>
      <td>0.1205</td>
      <td>4.086957</td>
      <td>0.148032</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.430</td>
      <td>0.315</td>
      <td>0.095</td>
      <td>0.3780</td>
      <td>0.1750</td>
      <td>0.0800</td>
      <td>0.1045</td>
      <td>0.0185</td>
      <td>3.315789</td>
      <td>0.129683</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.580</td>
      <td>0.490</td>
      <td>0.195</td>
      <td>1.3165</td>
      <td>0.5305</td>
      <td>0.2540</td>
      <td>0.4100</td>
      <td>0.1220</td>
      <td>2.512821</td>
      <td>0.230816</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.535</td>
      <td>0.405</td>
      <td>0.175</td>
      <td>1.2705</td>
      <td>0.5480</td>
      <td>0.3265</td>
      <td>0.3370</td>
      <td>0.0590</td>
      <td>2.314286</td>
      <td>0.231173</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.310</td>
      <td>0.235</td>
      <td>0.090</td>
      <td>0.1270</td>
      <td>0.0480</td>
      <td>0.0310</td>
      <td>0.0400</td>
      <td>0.0080</td>
      <td>2.611111</td>
      <td>0.118723</td>
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
    </tr>
    <tr>
      <th>2919</th>
      <td>0.170</td>
      <td>0.105</td>
      <td>0.035</td>
      <td>0.0340</td>
      <td>0.0120</td>
      <td>0.0085</td>
      <td>0.0050</td>
      <td>0.0085</td>
      <td>3.000000</td>
      <td>0.056667</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>0.435</td>
      <td>0.345</td>
      <td>0.115</td>
      <td>0.4180</td>
      <td>0.2220</td>
      <td>0.0735</td>
      <td>0.1060</td>
      <td>0.0165</td>
      <td>3.000000</td>
      <td>0.145000</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>0.570</td>
      <td>0.450</td>
      <td>0.135</td>
      <td>0.7940</td>
      <td>0.3815</td>
      <td>0.1415</td>
      <td>0.2450</td>
      <td>0.0260</td>
      <td>3.333333</td>
      <td>0.171000</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>0.460</td>
      <td>0.350</td>
      <td>0.120</td>
      <td>0.4885</td>
      <td>0.1930</td>
      <td>0.1050</td>
      <td>0.1550</td>
      <td>0.0355</td>
      <td>2.916667</td>
      <td>0.157714</td>
      <td>0</td>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>0.565</td>
      <td>0.440</td>
      <td>0.160</td>
      <td>0.9150</td>
      <td>0.3540</td>
      <td>0.1935</td>
      <td>0.3200</td>
      <td>0.0475</td>
      <td>2.750000</td>
      <td>0.205455</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>4177 rows × 13 columns</p>
</div>



```python
train2=alldata2[:len(train)]
test2=alldata2[len(train):]
```
-----------------------------
train,test data를 나누었는데 학습을 무한히 하게 될 경우 과적합이 발생하거나 데이터양에 따라 방대한 시간이 소요됩니다.
해결하고자 적정한 시점에 학습을 종료시켜줌으로써 정확성과 효율성을 동시에 높일 수 있는 call back 함수를 적용하고 인자의 변화를 적용/실험하겠습니다.
또한 Sequential model을 사용하여 학습 모델의 각 층을 쌓아주되 Dropout값을 조정하여 학습의 정확도 변화를 확인하고 학습 split 비율을 달리하여 실험하겠습니다.
내용은 아래와 같습니다.

첫째, call back함수로 EarlyStopping을 사용하고 drop out을 0.1/0.3/0.5로 변경하여 실험해 보겠습니다.
-----------------------------

```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.1)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")

es = EarlyStopping(patience = 55, restore_best_weights = True)
model.fit(train2,np.log(train["Target"]),validation_split = 0.2,callbacks = [es], epochs = 1000) 
result = model.predict(test2)
result
```

Output exceeds the size limit. Open the full output data in a text editor

Epoch 1/1000

32/32 [==============================] - 2s 11ms/step - loss: 0.4796 - val_loss: 0.2531

Epoch 2/1000

32/32 [==============================] - 0s 4ms/step - loss: 0.2691 - val_loss: 0.2179

...

Epoch 329/1000

32/32 [==============================] - 0s 4ms/step - loss: 0.1368 - val_loss: 0.1630

Epoch 330/1000

32/32 [==============================] - 0s 4ms/step - loss: 0.1386 - val_loss: 0.1599

array([[2.2627108],

       [2.7198985],

       [1.7135146],

       ...,

       [2.196479 ],

       [2.1187353],

       [2.4432218]], dtype=float32)


val_loss 평균 : 0.169450138



array([[2.2136772],		

       [2.7583036],		

       [1.6957715],		

       ...,		

       [2.2163637],		

       [2.1247556],		

       [2.432406 ]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.3)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")

es = EarlyStopping(patience = 55, restore_best_weights = True)
model.fit(train2,np.log(train["Target"]),validation_split = 0.2,callbacks = [es], epochs = 1000) 
result = model.predict(test2)
result
```

val_loss 평균 : 0.166555276



array([[2.2273293],		

       [2.6902924],		

       [1.689068 ],		

       ...,		

       [2.1953666],		

       [2.1278155],		

       [2.4698129]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")

es = EarlyStopping(patience = 55, restore_best_weights = True)
model.fit(train2,np.log(train["Target"]),validation_split = 0.2,callbacks = [es], epochs = 1000) 
result = model.predict(test2)
result
```

val_loss 평균 : 0.165567154



array([[2.222119 ],		

       [2.7356184],		

       [1.7026181],		

       ...,		

       [2.1970065],		

       [2.12998  ],		

       [2.49071  ]], dtype=float32)


-----------
# 같은 조건에서 Dropout의 크기가 클 수록 (0.5 > 0.4 > 0.3) val_loss의 평균이 낮아짐 확인하였습니다
# 드롭아웃으로 훈련된 뉴런은 이웃한 뉴런에 맞춰 적응될 수 없어 자기 자신이 유용해져야하기 때문으로 보입니다
학습에 따른 개선이 부족하여 중단하는 것도 필요하나 아직 최적점을 발견하지 못한 상태에서 조기 stop될 경우가 우려되었습니다.
다행히 Learning Rate를 조절하는 call back함수가 있음을 확인하였고 이를 적용해 보겠습니다. 

셋째, 콜백함수로 ReduceLROnPlateau를 이용하고 validation_split의 값을 0.2 / 0.3 / 0.4 로 달리하여 실험하겠습니다.
----------

```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 55, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.2,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.161334783



array([[2.2416005],		

       [2.7447584],		

       [1.6821461],		

       ...,		

       [2.202456 ],		

       [2.1456022],		

       [2.4705086]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 55, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.3,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.154350895



array([[2.3059907],		

       [2.7096336],		

       [1.6718717],		

       ...,		

       [2.2180395],		

       [2.1521516],		

       [2.4741108]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 55, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.4,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.151001388



array([[2.2596931],		

       [2.7630682],		

       [1.6744958],		

       ...,		

       [2.2046976],		

       [2.1497662],		

       [2.453535 ]], dtype=float32)

---------------------
# 같은 조건에서 validation_split의 값이 높을 수록 (0.4 > 0.3 > 0.2) val_loss 평균이 낮아짐 확인하였습니다.
# drop out과 마찬가지로 이웃한 뉴런에 맞춰 적응될 수 없어 자기 자신이 유용해져야하기 때문으로 보입니다

넷째, 같은 조건에서 콜백함수의 patience 값을 55 / 80 / 100으로 나누어 val_loss의 변화를 확인하겠습니다.
------------
```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 55, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.4,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.151001388



array([[2.2596931],		

       [2.7630682],		

       [1.6744958],		

       ...,		

       [2.2046976],		

       [2.1497662],		

       [2.453535 ]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 80, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.4,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.152729254



array([[2.2948117],		

       [2.7154992],		

       [1.6728886],		

       ...,		

       [2.209257 ],		

       [2.1482503],		

       [2.4616075]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model = Sequential()
model.add(Dense(32, activation = 'elu', input_dim = train2.shape[1])) 
model.add(Dense(64, activation = 'elu')) 
model.add(Dropout(0.5)) 
model.add(Dense(32, activation = 'elu')) 
model.add(Dense(1)) 
model.compile(loss = "mae", optimizer = "nadam")


rl = ReduceLROnPlateau(patience = 100, factor = 0.1, verbose = 1)
model.fit(train2,np.log(train["Target"]),validation_split = 0.4,callbacks = [rl], epochs = 1000)
result = model.predict(test2)
result
```

val_loss 평균 : 0.152452096



array([[2.3107636],		

       [2.6987696],		

       [1.6954834],		

       ...,		

       [2.2094963],		

       [2.1340725],		

       [2.4649158]], dtype=float32)


-------------------
# Patience 55일 때 > 100일 때 > 80일 때 순으로 val_loss 평균이 낮아짐을 확인하였습니다.
# epcohs는 절대 적으로 Patience값이 올라감에 따라 증가하므로 val_loss 평균이 높아질 수 밖에 없습니다.
# 그러나 Patience가 100일 때 Patience가 80일 때보다 val_loss 평균이 낮은 이유는 Patience 80 ~ 100 사이에서 가장 적합한 학습이 추가로 나왔을 것으로 예상됩니다.

다섯째, 모델을 저장하는 콜백 함수 'ModelCheckpoin'를 적용하고 validation_split 값을 0.2 / 0.6 / 0.8 로 나누어 영향을 확인하겠습니다.
--------------------

```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.compile(optimizer='nadam', loss='mae')

filename='{epoch:02d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.2,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val_loss 평균 : 0.16968



array([[2.2663643, 2.264844 , 2.266024 , ..., 2.2650528, 2.2655187,



        2.2660198],

        

       [2.6442165, 2.6413276, 2.6443307, ..., 2.6416419, 2.6450284,

       

        2.6424193],

        

       [1.6988082, 1.7005508, 1.6973547, ..., 1.7015595, 1.6981194,

       

        1.7005796],

        

       ...,

       

       [2.2224991, 2.2217686, 2.2220447, ..., 2.2231448, 2.222627 ,

       

        2.2231038],

        

       [2.1464343, 2.146068 , 2.145969 , ..., 2.147265 , 2.1465645,

       

        2.1468613],

        

       [2.4238234, 2.4215486, 2.4233   , ..., 2.4225008, 2.4234416,

       

        2.4227142]], dtype=float32)




```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.compile(optimizer='nadam', loss='mae')

filename='{epoch:02d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.6,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val_loss 평균 : 0.1631971



array([[2.1754274, 2.1749456, 2.1755013, ..., 2.175321 , 2.1765492,



        2.1757126],

        

       [2.636394 , 2.6364853, 2.635841 , ..., 2.636465 , 2.6367075,

       

        2.636484 ],

        

       [1.6615014, 1.6620765, 1.6631621, ..., 1.6615144, 1.6630495,

       

        1.6620612],

        

       ...,

       

       [2.223041 , 2.2232974, 2.2233667, ..., 2.2227228, 2.2231922,

       

        2.2233453],

        

       [2.135646 , 2.136025 , 2.136189 , ..., 2.1354558, 2.1361368,

       

        2.1360142],

        

       [2.4100912, 2.4099514, 2.410209 , ..., 2.4102135, 2.4105268,

       

        2.410482 ]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.compile(optimizer='nadam', loss='mae')

filename='{epoch:02d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.8,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val loss 평균 : 0.1705457



array([[2.2388606, 2.2386045, 2.2394295, ..., 2.2396245, 2.2396524,



        2.2399938],

        

       [2.6036773, 2.6034594, 2.6039114, ..., 2.6058235, 2.6042902,

       

        2.604933 ],

        

       [1.6476009, 1.6482158, 1.6481934, ..., 1.6471771, 1.6485901,

       

        1.648053 ],

        

       ...,

       

       [2.1750462, 2.174553 , 2.1749265, ..., 2.175615 , 2.1749544,

       

        2.1754265],

        

       [2.0979395, 2.0977328, 2.098071 , ..., 2.0984697, 2.0982108,

       

        2.0984383],

        

       [2.3782737, 2.3776345, 2.378264 , ..., 2.3794928, 2.378156 ,

       

        2.3790903]], dtype=float32)

-------------------------
# 같은 조건에서 val_loss 값은 (validation_split 기준) 0.6 > 0.2 > 0.8 순으로 낮아졌습니다.
# validation_split 값을 높이게 되면 test 과정에서 자기 자신의 유용성을 높여야 하지만 0.8까지 높이게 되면 오히려 train과 valid data간의 불균형이 심화되기 때문으로 보입니다.
여섯째, epochs 저장 회차를 2 / 4 / 8로 변경하여 확인하겠습니다.
-------------------------


```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.add(Dense(1))
model.compile(optimizer='nadam', loss='mae')

filename= '{epoch:02d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.2,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val_loss 평균 : 0.1614164



array([[2.200793 ],		

       [2.5643947],		

       [1.7740062],		

       ...,		

       [2.2406104],		

       [2.1467557],		

       [2.4393594]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.add(Dense(1))
model.compile(optimizer='nadam', loss='mae')

filename= '{epoch:04d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.2,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val_loss 평균 : 0.1621975



array([[2.2824113],		

       [2.634952 ],		

       [1.7223554],		

       ...,		

       [2.2877655],		

       [2.1715932],		

       [2.523498 ]], dtype=float32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
model=Sequential()
model.add(Dense(32, activation='elu', input_dim=alldata2.shape[1]))
model.add(Dense(64, activation='elu'))
model.add(Dropout(0.5))
model.add(Dense(32, activation='elu'))
model.add(Dense(1))
model.compile(optimizer='nadam', loss='mae')

filename= '{epoch:08d}-{val_loss:.5f}.h5'
mc=ModelCheckpoint(filename, monitor='val_loss', verbose=1, save_best_only=True, mode='auto')
model.fit(train2,np.log(train['Target']),validation_split=0.2,callbacks=mc,epochs=1000)
result=model.predict(test2)
result
```

val_loss 평균 : 0.1639972



array([[2.2479684],		

       [2.7111971],		

       [1.6521204],		

       ...,		

       [2.2215517],		

       [2.1347444],		

       [2.5157259]], dtype=float32)		

--------------------------------------
# ModelCheckpoint의 에폭 저장 회차를 달리하고, 이외 같은 조건을 사용하였을 때
# 에폭 저장 회차 2 > 4 > 8 순으로 val_loss 평균이 낮아졌습니다.
# 이는 에폭 저장 회차를 적게 할 수록, 저장되는 데이터 값이 많아지므로 val_loss의 값이 줄어드는 것으로 보입니다.
# 또한 같은 조건을 사용하였을 때, 콜백함수는  ReduceLROnPlateau(factor=0.1추가, 0.161334783)> EarlyStopping(0.165567154) 순으로 val_loss 가 작아졌습니다.
# ReduceLROnPlateau는 EarlyStopping과 달리 factor=0.1을 적용하여 Learning rate를 지속 줄여나갔기 때문으로 보입니다.
# ModelCheckpoint의 저장 회차를 적게하여 저장 주기를 빨리하는 것도 val_loss 향상에 도움이 될 수 있으나, 이는 처리 시간을 늘리게 되는 단점이 있습니다. 

```python
train2.shape
```


(1253, 13)

-----------
train['target']의 log값으로 학습을 진행했으므로 result값에 exp으로 반환하고, 소수점 첫째자리까지 반환하기 위하여 np.round를 사용하였습니다.
---------------


```python
sub['Target']=np.round(np.exp(result))
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>Target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>15.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2919</th>
      <td>2920</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>2920</th>
      <td>2921</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>2921</th>
      <td>2922</td>
      <td>9.0</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>2923</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>2924</td>
      <td>12.0</td>
    </tr>
  </tbody>
</table>
<p>2924 rows × 2 columns</p>
</div>



```python
sub.to_csv('submission.csv',index=False)
```
