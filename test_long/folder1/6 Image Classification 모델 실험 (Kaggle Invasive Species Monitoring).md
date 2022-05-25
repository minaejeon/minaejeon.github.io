
#6 Image Classification 모델 실험 (Kaggle Invasive Species Monitoring)


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
    for filename in filenames[:5]:
        print(os.path.join(dirname, filename))

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```

<pre>
/kaggle/input/invasivespecies/test/1269.jpg
/kaggle/input/invasivespecies/test/623.jpg
/kaggle/input/invasivespecies/test/764.jpg
/kaggle/input/invasivespecies/test/1075.jpg
/kaggle/input/invasivespecies/test/771.jpg
/kaggle/input/invasivespecies/train/1269.jpg
/kaggle/input/invasivespecies/train/623.jpg
/kaggle/input/invasivespecies/train/2193.jpg
/kaggle/input/invasivespecies/train/2008.jpg
/kaggle/input/invasivespecies/train/2081.jpg
/kaggle/input/invasive-species-monitoring/train_labels.csv.zip
/kaggle/input/invasive-species-monitoring/sample_submission.csv.zip
/kaggle/input/invasive-species-monitoring/test.7z
/kaggle/input/invasive-species-monitoring/train.7z
</pre>
train data가 zip 형식이므로 압축 되어 있어, 먼저 압축 풀기 이후 분석을 진행하겠습니다.



폴더는 output에(-O) 저장됩니다



```python
#unzip
!unzip -q -o /kaggle/input/invasive-species-monitoring/train_labels.csv.zip 
```


```python
train=pd.read_csv('train_labels.csv')
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2290</th>
      <td>2291</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2291</th>
      <td>2292</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2292</th>
      <td>2293</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2293</th>
      <td>2294</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2294</th>
      <td>2295</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>2295 rows × 2 columns</p>
</div>


train data에는 invasive species의 포함 여부가 0(불포함) 혹은 1(포함)로 표기 되어 있습니다.


train['path']의 상위 폴더는 고정 값으로 넣어주고, name column의 값에 따라 달라지므로 string 형식으로 넣어줍니다. 이후 '.jpg'로 동일한 확장자를 추가하였습니다.



```python
train['path']='../input/invasivespecies/train/'+train['name'].astype(str)+'.jpg'
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>../input/invasivespecies/train/1.jpg</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0</td>
      <td>../input/invasivespecies/train/2.jpg</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>../input/invasivespecies/train/3.jpg</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0</td>
      <td>../input/invasivespecies/train/4.jpg</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1</td>
      <td>../input/invasivespecies/train/5.jpg</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2290</th>
      <td>2291</td>
      <td>1</td>
      <td>../input/invasivespecies/train/2291.jpg</td>
    </tr>
    <tr>
      <th>2291</th>
      <td>2292</td>
      <td>1</td>
      <td>../input/invasivespecies/train/2292.jpg</td>
    </tr>
    <tr>
      <th>2292</th>
      <td>2293</td>
      <td>1</td>
      <td>../input/invasivespecies/train/2293.jpg</td>
    </tr>
    <tr>
      <th>2293</th>
      <td>2294</td>
      <td>1</td>
      <td>../input/invasivespecies/train/2294.jpg</td>
    </tr>
    <tr>
      <th>2294</th>
      <td>2295</td>
      <td>1</td>
      <td>../input/invasivespecies/train/2295.jpg</td>
    </tr>
  </tbody>
</table>
<p>2295 rows × 3 columns</p>
</div>



```python
train['invasive']=train['invasive'].astype(str)
```


```python
!unzip -q -o /kaggle/input/invasive-species-monitoring/sample_submission.csv.zip
```

test data가 제공 되어 있지 않아, 정답 값 ['invasive'] column이 없는 submission data를 이용해 test data로 활용하겠습니다.



```python
test=pd.read_csv('./sample_submission.csv')
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1526</th>
      <td>1527</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1527</th>
      <td>1528</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1528</th>
      <td>1529</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1529</th>
      <td>1530</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1530</th>
      <td>1531</td>
      <td>0.5</td>
    </tr>
  </tbody>
</table>
<p>1531 rows × 2 columns</p>
</div>



```python
test['path']='../input/invasivespecies/test/'+test['name'].astype(str)+'.jpg'
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1.jpg</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/2.jpg</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/3.jpg</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/4.jpg</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/5.jpg</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1526</th>
      <td>1527</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1527.jpg</td>
    </tr>
    <tr>
      <th>1527</th>
      <td>1528</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1528.jpg</td>
    </tr>
    <tr>
      <th>1528</th>
      <td>1529</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1529.jpg</td>
    </tr>
    <tr>
      <th>1529</th>
      <td>1530</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1530.jpg</td>
    </tr>
    <tr>
      <th>1530</th>
      <td>1531</td>
      <td>0.5</td>
      <td>../input/invasivespecies/test/1531.jpg</td>
    </tr>
  </tbody>
</table>
<p>1531 rows × 3 columns</p>
</div>


DataFrame 형식의 데이터에는 'path' column에 이미지 경로를 내포하고 있습니다.



train data로 부터 training/validation data로 나누고, training/validation/testing data를 모두 tensorflow의 ImageDataGenerator를 이용하여 Image Data를 불러오겠습니다.



```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
from sklearn.model_selection import train_test_split
x_train, x_valid = train_test_split(train,test_size=0.2,random_state=42,stratify=train['invasive'])
```


```python
train_generator=idg.flow_from_dataframe(x_train,x_col='path',y_col='invasive')
```

<pre>
Found 1836 validated image filenames belonging to 2 classes.
</pre>

```python
valid_generator=idg.flow_from_dataframe(x_valid,x_col='path',y_col='invasive')
```

<pre>
Found 459 validated image filenames belonging to 2 classes.
</pre>
invasive species의 존재 여부로 2가지 class를 가지고 train image는 1836개, validation image는 459로 나누어져 있습니다.



이는 4:1의 비율인데 test_size를 0.2로 20%의 데이터를 validation data로 분류하기 때문입니다.



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.applications.efficientnet import 
from tensorflow.keras.callbacks import *
```


```python
from tensorflow.keras.applications.vgg16 import *
from tensorflow.keras.applications.vgg19 import *
```

*점수개선*



동일 조건에서 실험하였을 때, 아래와 같은 순으로 점수가 개선 된 것을 확인하였습니다.



변형 Conv2D < 변형 Conv2D + BatchNormalization 추가  < VGG19 < VGG16 < ResNet50 < InceptionV3 < EfficientNetB1+ModelCheckpoint < EfficientNetB1 < MobileNet < EfficientNetB0 < Xception


여기에서 주목하게 되는 점은, VGG16이 VGG19보다 점수가 개선되고, EfficientNetB0가 EfficientNetB1보다 점수가 개선된 것을 확인할 수 있습니다.



VGG16에서 VGG19를 사용하게 될 때, 레이어층을 더 깊게 사용하나 반드시 정확도가 개선되는 것은 아닌 것으로 보입니다.



![image.png](attachment:147dcfc1-e89d-413a-929b-200be019d976.png)![image.png](attachment:b6122c13-bdf0-404f-b6c7-19fb44a4c955.png)


EfficientNetB0에서 EfficientNetB1보다 점수가 개선되지 않은 이유는 callback의 patience 인자 조절이 적합치 않아 최적화되지 않은 상태의 학습을 했을 것으로 보입니다.



parameter가 늘어났지만, 최적의 학습을 위해 적합한 인자값을 찾는 노력이 수반되어야 합니다.



InceptionV3가 V16과 V19보다 예측 정확도가 향상하였는데, 이는 매개변수 수는 줄었고 네트워크 성능은 좋아졌습니다. 위의 그래프를 볼 때, 파라미터의 수가 증가할 수록 정확도가 향상되는 경향을 보이지만 각 모델마다 향상되는 속도가 달라짐을 확인했습니다.


score : 0.79712



```python
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)#Plateau 
# model=Sequential() 
# model.add(Convolution2D(32,3,3))
# model.add(MaxPooling2D(pool_size=(2,2)))
# model.add(Flatten())
# model.add(Dense(2,activation='softmax')) 

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.83298



```python
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential() 
# model.add(Convolution2D(32,3,3))
# model.add(MaxPooling2D(pool_size=(2,2)))
# model.add(Flatten())
# model.add(BatchNormalization(axis=-1))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.96698


# VGG



1. 규모가 큰 합성곱을 여러 작은 합성곱으로 대체



처음에는 3X3 커널을 갖는 두 합성곱 계층을 쌓은 스택이 5X5 커널을 갖는 하나의 합성곱 계층과 동일한 수용 영역을 갖는다.



이와 마찬가지로 3X3 합성곱 계층을 3개 연이어 배치하면 수용 영역은 7X7이 되고 5개의 3X3 합성곱의 수용 영역은 11X11이 된다.



VGG 네트워크는 이보다 작은 합성곱 계층을 더 많이 포함해 더 큰 ERF를 얻을 수 있다. 따라서 매개변수 개수를 줄이고, 비선형성을 증가시킬 수 있다는 장점이 있다.



2. 특정 맵 깊이를 증가



각 합성곱 블록에 대한 특징 맵의 깊이를 두 배로 늘렸다. 각 집합 다음에는 윈도우 크기가 2X2이고 보폭이 2인 최대 풀링 계층이 나오므로 깊이가 두 배로 늘고 공간 차원은 반으로 줄게 된다.



3. 척도 변경을 통한 데이터 보강



훈련이 반복될 때마다 이미지 배치를 적절한 입력 크기로 자르기 전에 그 척도를 무작위로 조정한다. 이렇게 무작위로 변환함으로써 네트워크는 다양한 척도의 샘플을 경험하게 되고 이러한 척도 변경에도 불구하고 이미지를 적절히 분류하는 방법을 학습하게 된다.



4. 완전 연결 계층을 합성곱 계층으로 대체



크기가 좀 더 큰 커널 (7X7과 3X3)을 적용한 첫 번째 합성곱 세트는 특징 맵의 공간 크기를 1X1로 줄이고 (그 전에 패딩을 적용하지 않았다면) 특징 맵의 깊이를 4,096으로 늘린다. 마지막으로 1X1 합성곱 계층이 예측해야 할 클래스 개수만큼의 필터와 함께 사용된다. 그 결과 얻게 된 1X1XN 벡터는 softmax 함수로 정규화된 다음 평면화되어 최종 클래스 예측으로 출력된다.



```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(VGG19(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.96876



```python
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(VGG16(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

# ResNet - 잔차 네트워크



1. 매핑 대신 잔차 함수 추정하기

네트워크 계층이 항등 매핑을 쉽게 학습할 수 있다면 (즉 계층이 가중치를 학습해 계층에서의 일련의 연산이 최종적으로 입력 텐서와 동일한 텐서를 반환한다면) 성능 저하 현상은 발생하지 않을 것이다.



일부 추가적인 합성곱 계층을 사용해 데이터를 추가로 처리하는 경로



항등 매핑(즉, 데이터에 어떤 변경도 가하지 않고 전달)을 수행하는 경로



2. 극단적으로 깊이 들어가기



잔차 블록은 전통 블록보다 매개변수가 많지 않은데, 스킵과 덧셈 연산에는 어떤 매개변수도 필요 없기 때문이다. 따라서 잔차블록은 '상당히 깊은' 네트워크를 구성할 때 효율적이다.


score : 0.98666



```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential() #B 숫자 증가~성능 향상 
# model.add(ResNet50(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax')) 
# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

# Inception 모듈



1. 다양한 세부 특징 잡아내기



기본 인셉션 모듈은 4개의 병렬 계층 즉, 3개의 합성곱 계층(필터 크기는 각각 1x1, 3x3, 5x5)과 하나의 최대-풀링 계측으로 구성된다. 계층의 결과를 하나로 연결해 최종 결과를 만드는 이 병렬 처리는 이점을 갖고 있다. 척도가 다양한 데이터 처리를 가능하게 해준다. 각 인셉션 모듈의 결과는 다양한 척도의 특징을 결합해 더 광범위한 정보를 잡아낸다. 이 경우 최선의 커널 크기를 선택할 필요가 없다. 즉 네트워크가 스스스로 각 모듈에 대해 어느 합성곱 계층에 더 의존하는지 학습한다.



서로 다른 계층에서 매핑된 특징을 연결하는 것으로 CNN에 비선형성이 추가된다.



2. 병목 계층으로 1x1 합성곱 계층을 사용



3. 완전 연결 계층 대신 풀링 계층 사용

매개변수 개수를 줄이기 위해 마지막 합성곱 블록 다음에 완전 연결 계층 대신 평균-풀링 계층을 사용할 수 있다. 윈도우 크기로 7x7, 보폭으로 1을 설정하면 이 계층은 훈련시킬 배개변수 하나 없이 특징 볼륨을 7x7x1024에서 1x1x1024로 줄인다. 밀집 계층이 오면 (7x7x1024)x1024 개의 매개변수가 추가 될 것이다. 물론 풀링 계층으로 대체하면 네트워크가 표현력을 약간 잃게 되지만, 계산상으로 얻는 이익이 막대하다.



4. 중간 손실로 경사 소실 문제 해결하기

CNN이 깊어질수록 경사가 소실되어 문제가 되는 경우가 많다. 많은 CNN연산(예를 들어 시그모이드)에는 진폭이 작은(1보다 작은) 도함수가 있다. 따라서 계층 수가 많을 수록 역전파할 때 도함수의 곱은 작아진다(1보다 작은 값을 여러 번 곱하면 그 결과는 0에 가까워지기 때문에) 이렇게 첫번째 계층에 도착했을 때 대체로 경사는 소실되거나 0에 가까워진다. 경삿값이 매개변수 업데이트에 직접 사용되기 때문에 경사가 너무 작으면 이 계층들은 효과적으로 학습할 수 없다. 솔루션은 다양한 네트워크 깊이에서 추가적인 분류 손실을 도입함으로써 첫번째 계층과 예측 사이의 거리를 줄이는 것이다. 마지막 손실에서의 경사가 적절하게 첫번째 계층까지 흐를 수 없더라도 그보다 더 가까운 중간 손실 덕에 분류작업에 도움이 되게 훈련될 수 있다.



score : 0.98724



```python
# from tensorflow.keras.applications import *
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential() 
# model.add(InceptionV3(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.98873



```python
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# mc=ModelCheckpoint(patience=2,verbose=1,filepath='./_ModelCheckPoint/keras.hdf5')
# model=Sequential() 
# model.add(EfficientNetB1(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl,mc])
```

score : 0.99095



```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(EfficientNetB1(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax')) 

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.99113



```python
# from tensorflow.keras.applications.mobilenet import MobileNet
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(MobileNet(weights='imagenet',include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))
# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

score : 0.99233



```python
es=EarlyStopping(patience=4,restore_best_weights=True)
rl=ReduceLROnPlateau(patience=3,verbose=1)
model=Sequential() #B 숫자 증가~성능 향상 
model.add(EfficientNetB0(include_top=False,pooling='avg'))
model.add(Dense(2,activation='softmax')) 
model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

<pre>
Downloading data from https://storage.googleapis.com/keras-applications/efficientnetb0_notop.h5
16711680/16705208 [==============================] - 0s 0us/step
16719872/16705208 [==============================] - 0s 0us/step
Epoch 1/1000
58/58 [==============================] - 112s 2s/step - loss: 0.2050 - acc: 0.9216 - val_loss: 1.0076 - val_acc: 0.8584
Epoch 2/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0893 - acc: 0.9711 - val_loss: 0.0725 - val_acc: 0.9782
Epoch 3/1000
58/58 [==============================] - 69s 1s/step - loss: 0.0207 - acc: 0.9924 - val_loss: 0.1756 - val_acc: 0.9586
Epoch 4/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0453 - acc: 0.9842 - val_loss: 0.0518 - val_acc: 0.9869
Epoch 5/1000
58/58 [==============================] - 71s 1s/step - loss: 0.0604 - acc: 0.9788 - val_loss: 0.1122 - val_acc: 0.9695
Epoch 6/1000
58/58 [==============================] - 71s 1s/step - loss: 0.0230 - acc: 0.9929 - val_loss: 0.0357 - val_acc: 0.9869
Epoch 7/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0180 - acc: 0.9935 - val_loss: 0.1061 - val_acc: 0.9651
Epoch 8/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0195 - acc: 0.9929 - val_loss: 0.0289 - val_acc: 0.9935
Epoch 9/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0135 - acc: 0.9956 - val_loss: 0.1819 - val_acc: 0.9499
Epoch 10/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0260 - acc: 0.9891 - val_loss: 0.1935 - val_acc: 0.9739
Epoch 11/1000
58/58 [==============================] - 70s 1s/step - loss: 0.0063 - acc: 0.9989 - val_loss: 0.0676 - val_acc: 0.9891

Epoch 00011: ReduceLROnPlateau reducing learning rate to 0.00010000000474974513.
Epoch 12/1000
58/58 [==============================] - 69s 1s/step - loss: 0.0019 - acc: 0.9995 - val_loss: 0.0587 - val_acc: 0.9891
</pre>
<pre>
<keras.callbacks.History at 0x7fade406cf10>
</pre>
score : 0.99315



```python
# from tensorflow.keras.applications.xception import Xception
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential() 
# model.add(Xception(weights='imagenet',include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax')) 

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```


```python
from tensorflow.keras.applications import *
```


```python
test_generator=idg.flow_from_dataframe(test,x_col='path',y_col=None,shuffle=False,class_mode=None) 
```

<pre>
Found 1531 validated image filenames.
</pre>

```python
result=model.predict(test_generator,verbose=1,workers=2) 
```

<pre>
48/48 [==============================] - 41s 806ms/step
</pre>

```python
result
```

<pre>
array([[2.7186363e-03, 9.9728131e-01],
       [9.9734539e-01, 2.6546121e-03],
       [9.9898201e-01, 1.0179272e-03],
       ...,
       [9.9999774e-01, 2.2147251e-06],
       [1.1051272e-07, 9.9999988e-01],
       [1.6658715e-06, 9.9999833e-01]], dtype=float32)
</pre>

```python
sub=pd.read_csv('./sample_submission.csv')
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1526</th>
      <td>1527</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1527</th>
      <td>1528</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1528</th>
      <td>1529</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1529</th>
      <td>1530</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1530</th>
      <td>1531</td>
      <td>0.5</td>
    </tr>
  </tbody>
</table>
<p>1531 rows × 2 columns</p>
</div>


invasive가 1일 확률을 제출하므로 각 행의 result 값에서 2번째 값을 반환해야합니다.



따라서 result[모든행,2번째 값]을 기준으로 sub['invasive']값에 적용하였습니다.



```python
sub['invasive']=result[:,1]
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>name</th>
      <th>invasive</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0.997281</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>0.002655</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>0.001018</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>0.061969</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>0.999998</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1526</th>
      <td>1527</td>
      <td>0.000117</td>
    </tr>
    <tr>
      <th>1527</th>
      <td>1528</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1528</th>
      <td>1529</td>
      <td>0.000002</td>
    </tr>
    <tr>
      <th>1529</th>
      <td>1530</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>1530</th>
      <td>1531</td>
      <td>0.999998</td>
    </tr>
  </tbody>
</table>
<p>1531 rows × 2 columns</p>
</div>



```python
sub.to_csv('submission.csv',index=False)
```
