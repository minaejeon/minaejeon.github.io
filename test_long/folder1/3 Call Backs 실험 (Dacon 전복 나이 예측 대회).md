
# 3 Call Backs 실험 (Dacon 전복 나이 예측 대회)



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
/kaggle/input/abalone-age-predict/sample_submission.csv
/kaggle/input/abalone-age-predict/train.csv
/kaggle/input/abalone-age-predict/test.csv
</pre>
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


[학습 스케줄링]



learning rate는 신경망 학습하는데 중요 요소



학습률이 충분치 못하면 Local Mininum에 빠질 수 있고 수렴이 어려움



학습률이 크면 Global Minimum을 지나칠 수 있고 수렴이 어려움



적절한 학습률이 중요 : 큰 학습률로 시작하고 신경망이 훈련하는 동안 학습률을 감소시키는 전략 필요.


![image.png](attachment:c0b21ff3-8a44-44d2-8fc6-e51728c42573.png)


1. 거듭 제곱 기반 스케줄링



학습률은 각 스텝마다 감소하며 s번 스텝 학습 이후 초기 학습률/2, s번 스텝 이후 초기학습률/3.. 처음에는 빠르게 감소하다가 점차 느리게 감소



t는 반복 횟수 (epoch)



s는 스텝 횟수



decay는 step(s)의 역수



optimizer=keras.optimizers.SGD(lr=1e-3,decay=1e-4)


![image.png](attachment:3a4ebad4-af68-4b34-a625-3a861b572fb5.png)


2. 지수 기반 스케줄링



s번 스텝마다 10배씩 감소



![image.png](attachment:c496c3f6-efb8-4b0a-ba9f-b8687c368e8a.png)


3. 구간 별 고정 스케줄링



일정 횟수의 에포크 동안 일정한 학습률을 사용하고, 또 다른 횟수의 에포크 동안 작은 학습률을 사용하는 방식



직접 구간별 학습률 지정 필요



![image.png](attachment:c80d0147-da06-47cb-b1ea-0a2e12cf7a47.png)


4. 성능 기반 학습 스케줄링



매 N 스텝마다 (조기 종료처럼) 검증 오차를 측정하고 오차가 줄어들지 않으면 람다배 만큼 학습률을 감소



(데이터의 패턴을 학습할 수 있도록)



![image.png](attachment:580c2070-085f-408a-89df-3fd786515186.png)


5.1 사이클 스케줄링



훈련 절반 동안 초기 학습률을 선형적으로 증가시킨 뒤, 나머지 절반 동안 선형적으로 학습률을 초기 학습률까지 다시 감소시키며 학습



보통 초기 학습률 * 10 = 증가시킨 학습률 



[l1 l2 규제]



신경망의 연결 가중치를 제한하기 위해 l2규제를 사용하거나, 희소 모델을 만들기 위해 l1 규제를 사용



규제항 l2 적용 심층신경망 생성



keras.regularizers.l1()

keras.regularizers.l2()

keras.regularizers.l1_l2()



![image.png](attachment:8404ebf1-9470-4b5b-ba58-4492ffe46368.png)


![image.png](attachment:4f3face4-7ebe-480c-b0b7-32c7d432147e.png)


각 훈련 반복에서 (출력 층 제외) 하나 이상의 층에 있는 모든 뉴런의 일부를 확률적으로 제거하고 훈련



매 훈련 스텝에서 각 뉴련(입력 뉴런 포함 가능, 출력 층 포함 불가)은 임시적으로 드롭아웃 될 확률 p를 가짐



일반적으로 0.1 ~ 0.5 지정(0.5 지정시 그 층의 반은 드롭아웃 되고 훈련진행)



- 장점



1) 드롭아웃으로 훈련된 뉴런은 이웃한 뉴런에 맞춰 적응될 수 없어 자기 자신이 유용해져야함



2) 몇 개의 입력 뉴런에만 지나치게 의존할 수 없어 모든 입력 뉴런에 주의를 기울여야 함



3) 입력값의 작은 변화에 덜 민감해져서 일반화 성능 좋아짐



4) 2**n개의 네트워크 생성이 가능해져, 여러번의 훈련을 통해 만들어진 신경망은 이 모든 신경망을 평균한 앙상블과 같은 모델이 됨(n은 드롭아웃이 가능한 뉴런 수)



5) 시간이 오래 걸리지만 적절한 튜닝 시 좋은 성능을 갖는 모델을 생성할 수 있음



6) Test시 보존 확률 (1-p)를 각 입력의 연결 가중치에 곱해줘야 함



[맥스-노름 규제]



각각의 뉴런에 대해 입력의 연결 가중치 w가 ||w||2 <= r이 되도록 제한하는 것



전체 손실 함수에 규제 손실 항을 추가하지 않고, w의 스케일을 조정함 (w<-w*r/||w||2)



r의 값이 작을 수록 규제의 양이 증가하여 과대적합을 방지할 수 있음



불안정한 Gradient 문제를 완화하는데 도움



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


Gender column(categorical : M,F,I)을 제외한 column은 연속형 변수 data 입니다.



따라서 get_dummies를 사용하여 Gender column을 3가지의 column으로 나눠준 후 True, False의 형식으로 바꾸어 줍니다.



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

# *EarlyStopping*



모델을 더 이상 학습하지 못할 경우 (loss, metric 등의 개선이 없는 경우), 학습 도중 미리 학습을 종료시키는 콜백 함수



tf.keras.callbacks.EarlyStopping(monitor='val_loss', min_delta=0, patience=0, verbose=0, mode='auto', baseline=None, restore_best_weight=False)



1. monitor : EarlyStopping의 기준이 되는 값을 입력합니다.



만약 'val_loss'를 입력하면 val_loss가 더 이상 감소되지 않을 경우 EarlyStopping을 적용합니다. 이외에도 다양한 값을 입력할 수 있습니다.



2. min_delta : 개선된 것으로 간주하기 위한 최소한의 변화량 입니다. 



예를 들어, min_delta가 0.01이고 30 에폭에 정확도가 0.8532라고 할 때, 만약 31 에폭에 정확도가 0.8537이라고 하면 이는 0.0005의 개선이 있었지만 min_delta값 0.01에는 미치지 못했으므로 개선 된 것으로 보이지 않습니다.



3. patience : training이 진행됨에도 더 이상 monitor 되는 값의 개선이 없는 경우, 최적의 monitor 값을 기준으로 몇 번의 epoch를 할지 정하는 값.



예를 들어, patience가 3이고 30에폭에 정확도가 99%였을 때, 31번째에 정확도 98% 32번에 98.5% 33번에 98%라면 더 이상 training을 하지 않고 종료시킵니다.



4. verbose : 0 또는 1



1일 경우 EarlyStopping이 적용될 때 화면에 적용되었다고 나타납니다.  0일 경우 화면에 나타냄 없이 종료합니다.



5. mode : 'auto' 또는 'min' 또는 'max'



monitor되는 값이 최소가 되어야 하는지, 최대가 되어야 하는지 알려주는 인자입니다.



monitor하는 값이 val_acc 즉 정확도일 경우 값이 클 수록 좋기 때문에 'max'를 입력하고 val_loss일 경우 작을 수록 좋기 때문에 'min'을 입력합니다. 'auto'는 모델이 알아서 판단합니다.



6. baseline : 모델이 달성해야 하는 최소한의 기준 값을 설정합니다.



patience 이내에 모델이 baseline 보다 개선됨이 보이지 않으면 training을 중단 시킵니다.



patience가 3이고 baseline이 정확도 기준 0.98 이라면, 3번의 training안에 0.98의 정확도를 달성하지 못하면 training이 종료됩니다.



7. resotre_best_weights : True or False



true라면 training이 끝난 후 , model의 weight를 monitor하고 있던 값이 가장 좋았을 때의 weight로 복원합니다.



false라면, 마지막 training이 끝난 후의 weight로 놔둡니다.


# drop out을 0.1/0.3/0.5로 변경하여 result 변화를 알아보겠습니다.



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


# 같은 조건에서 Dropout의 크기가 클 수록 (0.5 > 0.4 > 0.3) val_loss의 평균이 낮아짐 확인하였습니다



# 드롭아웃으로 훈련된 뉴런은 이웃한 뉴런에 맞춰 적응될 수 없어 자기 자신이 유용해져야하기 때문으로 보입니다


# *ReduceLROnPlateau*



모델의 개선이 없을 경우 Learning Rate를 조절해 모델의 개선을 유도하는 콜백 함수



tf.keras.callbacks.ReduceLROnPlateau(monitor='val_loss', factor=0.1, patience=10, verbose=0, mode='auto', min_delta=0.0001, cooldown=0, min_lr=0, **kwargs)



1. monitor



ReduceLROnPlateau의 기준이 되는 값, 'val_loss'를 입력하면 val_loss가 더 이상 감소 되지 않을 경우 ReduceLROnPlateau을 적용. 이외에도 다양한 값 입력 가능



2. factor



Learning rate를 얼마나 감소시킬지 정하는 인자값



새로운 learning rate는 기존 learning rate*factor 입니다



현재 lr이 0.01이고 factor가 0.8 일 때 콜백함수가 실행된다면 그 다음 lr은 0.008이 됩니다.



lr이 0.3이고 factor가 0.1일때 콜백함수가 실행된다면 그 다음 lr은 0.03이 됩니다.



3. patience



training이 진행됨에도 더 이상 monitor 되는 값의 개선이 없을 경우, 



4. verbose



0 또는 1



1일 경우, EarlyStopping이 적용될 때, 화면에 적용되었다고 나타냅니다.



0일 경우, 화면에 나타냄 없이 종료합니다.



5. mode



"auto" 또는 "min" 또는 "max"



monitor되는 값이 최소가 되어야 하는지, 최대가 되어야 하는지 알려주는 인자입니다.



예를 들어, monitor하는 값이 val_acc 즉 정확도일 경우, 값이 클수록 좋기때문에 "max"를 입력하고, val_loss일 경우 작을수록 좋기 때문에 "min"을 입력합니다.



"auto"는 모델이 알아서 판단합니다



6. min_delta



개선된 것으로 간주하기 위한 최소한의 변화량입니다. 예시로 이해하는 게 좋을 것 같습니다.



예를 들어, min_delta가 0.01이고, 30에폭에 정확도가 0.8532라고 할 때,



만약 31에폭에 정확도가 0.8537라고 하면 이는 0.005의 개선이 있었지만 min_delta 값 0.01에는 미치지 못했으므로 개선된 것으로 보지 않습니다.



7. cooldown



Learning rate가 감소한 후, ReduceLROnPlateau 콜백함수를 다시 실행하기 전에 대기 할 Epoch 수 입니다.



factor가 3이고 cooldown이 5 일 때, ReduceLROnPlateau이 적용되어 learning rate가 감소 되었다고 가정.



감소 된 이후에도 3 에폭 연속 monitor 값의 개선이 없었다고 하더라도 ReduceLROnPlateau는 실행되지 않습니다.



cooldown이 적용되고 있기 때문입니다. cool down 값인 5 에폭 실행 후, 3번 연속 monitor값의 개선이 없을 시, ReduceLROnPlateau이 다시 적용됩니다.



8. min_lr



Learning rate의 하한선을 지정합니다.



현재 lr이 0.1, factor가 5, min_lr이 0.03일 때



첫 번째 콜백 함수가 적용될 시 lr은 0.05(0.1*0.5)이 됩니다.



두 번째로 콜백 함수가 적용되면 0.025(0.1*0.5*0.5)이지만 min_lr이 0.03이기 때문에 새로운 learning rate는 0.025가 아닌 0.03이 됩니다.


# validation_split의 값을 0.2 / 0.3 / 0.4 로 나누어 적용하고, 결과를 확인하겠습니다.



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


# 같은 조건에서 validation_split의 값이 높을 수록 (0.4 > 0.3 > 0.2) val_loss 평균이 낮아짐 확인하였습니다.



# drop out과 마찬가지로 이웃한 뉴런에 맞춰 적응될 수 없어 자기 자신이 유용해져야하기 때문으로 보입니다



# 이번에는 같은 조건에서 콜백함수의 patience 값을 55 / 80 / 100으로 나누어 val_loss의 변화를 확인하겠습니다.



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



# Patience 55일 때 > 100일 때 > 80일 때 순으로 val_loss 평균이 낮아짐을 확인하였습니다.



# epcohs는 절대 적으로 Patience값이 올라감에 따라 증가하므로 val_loss 평균이 높아질 수 밖에 없습니다.



# 그러나 Patience가 100일 때 Patience가 80일 때보다 val_loss 평균이 낮은 이유는 Patience 80 ~ 100 사이에서 가장 적합한 학습이 추가로 나왔을 것으로 예상됩니다.


# *ModelCheckpoint*



모델을 저장할 때 사용하는 콜백 함수



tf.keras.callbacks.ModelCheckPoint(filepath, monitor='val_loss', verbose=0, save_best_only=False, save_weights_only=False, mode='auto', save_freq='epoch, options=None, *kwargs



1. filepath



모델을 저장할 경로를 입력합니다.



만약 monitor가 val_loss 일 때, 모델 경로를 '{epoch:02d}-{val_loss:.5f}.h5'라고 입력하면 에폭-해당에폭에서의 val_loss.h5로 모델이 저장됩니다.



2. monitor



모델을 저장할 때, 기준이 되는 값을 지정합니다.



validation set의 loss가 가장 작을 때를 저장하고 싶으면 'val_loss'를 입력하고 train set의 loss가 가장 적을 때를 저장하고 싶으면 'loss'를 입력합니다. 이 외에도 다양한 값을 기준으로 삼을 수 있습니다.



3. verbose



1일 경우 모델이 저장될 때, '저장되었습니다'라고 화면에 표시되고, 0일 경우 화면에 표시 되는 것 없이 바로 모델이 저장됩니다.



4. save_best_only



True인 경우 monitor 되고 있는 값을 기준으로 가장 좋은 값으로 모델이 저장됩니다.



False인 경우 매 에폭마다 모델이 filepath{epoch}으로 저장됩니다.(model0, model1, model2....)



5. save_weights_only



True인 경우 모델의 weights만 저장됩니다.



False인 경우 모델 레이어 및 weights 모두 저장됩니다.



6. mode



'auto', 'min', 'max'



val_acc인 경우 정확도가 클수록 좋습니다. 이때는 max값을 입력해 줘야 하고 , val_loss 인 경우 작을수록 좋으므로 min을 입력해야 합니다.



auto로 할 경우 모델이 min,max 모델을 판단하여 저장합니다.



7. save_freq



'epoch' 혹은 intiger(정수형 숫자)



'epoch'을 사용할 경우 매 에폭마다 모델이 저장됩니다. integer를 입력한 경우 숫자만큼의 배치를 진행하면 모델이 저장됩니다.



숫자 8을 입력하면, 8번째 배치가 train된 이후 16번째 배치가 train된 이후 모델이 저장됩니다.



8. options



tf.train.CheckpointOptions를 옵션으로 줄 수 있습니다. 분산환경에서 다른 디렉토리에 모델을 저장하고 싶을 경우 사용합니다.





# 같은 조건에서 validation_split 값을 0.2 / 0.6 / 0.8 로 나누어 결과를 확인하겠습니다.




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


# 같은 조건에서 val_loss 값은 (validation_split 기준) 0.6 > 0.2 > 0.8 순으로 낮아졌습니다.



# validation_split 값을 높이게 되면 test 과정에서 자기 자신의 유용성을 높여야 하지만 0.8까지 높이게 되면 오히려 train과 valid data간의 불균형이 심화되기 때문으로 보입니다.


# 에폭 저장 회차를 2 / 4 / 8로 변경하여 확인하겠습니다.



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


# ModelCheckpoint의 에폭 저장 회차를 달리하고, 이외 같은 조건을 사용하였을 때

# 에폭 저장 회차 2 > 4 > 8 순으로 val_loss 평균이 낮아졌습니다.

# 이는 에폭 저장 회차를 적게 할 수록, 저장되는 데이터 값이 많아지므로 val_loss의 값이 줄어드는 것으로 보입니다.


# 또한 같은 조건을 사용하였을 때, 콜백함수는  ReduceLROnPlateau(factor=0.1추가, 0.161334783)> EarlyStopping(0.165567154) 순으로 val_loss 가 작아졌습니다.



# ReduceLROnPlateau는 EarlyStopping과 달리 factor=0.1을 적용하여 Learning rate를 지속 줄여나갔기 때문으로 보입니다.



# ModelCheckpoint의 저장 회차를 적게하여 저장 주기를 빨리하는 것도 val_loss 향상에 도움이 될 수 있으나, 이는 처리 시간을 늘리게 되는 단점이 있습니다. 



```python
train2.shape
```

<pre>
(1253, 13)
</pre>
train['target']의 log값으로 학습을 진행했으므로 result값에 exp으로 반환하고, 소수점 첫째자리까지 반환하기 위하여 np.round를 사용하였습니다.



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
