
# 8 Image Classification 모델 실험 (Kaggle Invasive Species Monitoring)

![image](https://user-images.githubusercontent.com/69743938/172272601-a2da78e5-1826-4563-adef-61adf6746e3a.png)
![image](https://user-images.githubusercontent.com/69743938/172272635-8e235996-9f66-424d-a6cd-39999f79a990.png)

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

--------
train data가 zip 형식이므로 압축 되어 있어, 먼저 압축 풀기 이후 분석을 진행하겠습니다.
폴더는 output에(-O) 저장됩니다

------

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

--------
train data에는 invasive species의 포함 여부가 0(불포함) 혹은 1(포함)로 표기 되어 있습니다.

train['path']의 상위 폴더는 고정 값으로 넣어주고, name column의 값에 따라 달라지므로 string 형식으로 넣어줍니다. 이후 '.jpg'로 동일한 확장자를 추가하였습니다.

-------


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
------
test data가 제공 되어 있지 않아, 정답 값 ['invasive'] column이 없는 submission data를 이용해 test data로 활용하겠습니다.

--------

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

-------
DataFrame 형식의 데이터에는 'path' column에 이미지 경로를 내포하고 있습니다.

train data로 부터 training/validation data로 나누고, training/validation/testing data를 모두 tensorflow의 ImageDataGenerator를 이용하여 Image Data를 불러오겠습니다.

-------

```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
from sklearn.model_selection import train_test_split
x_train, x_valid = train_test_split(train,test_size=0.2,random_state=42,stratify=train['invasive'])
```


```python
train_generator=idg.flow_from_dataframe(x_train,x_col='path',y_col='invasive')
```

Found 1836 validated image filenames belonging to 2 classes.

```python
valid_generator=idg.flow_from_dataframe(x_valid,x_col='path',y_col='invasive')
```

Found 459 validated image filenames belonging to 2 classes.

--------------
invasive species의 존재 여부로 2가지 class를 가지고 train image는 1836개, validation image는 459로 나누어져 있습니다.

이는 4:1의 비율인데 test_size를 0.2로 20%의 데이터를 validation data로 분류하기 때문입니다.

------------

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
-------

# 동일 조건에서 실험하였을 때, 아래와 같은 순으로 점수가 개선 된 것을 확인하였습니다.

# VGG19 < VGG16 < ResNet50 < InceptionV3 < EfficientNetB1+ModelCheckpoint < EfficientNetB1 < MobileNet < EfficientNetB0 < Xception

# 여기에서 주목하게 되는 점은, VGG16이 VGG19보다 점수가 개선되고, EfficientNetB0가 EfficientNetB1보다 점수가 개선된 것을 확인할 수 있습니다.

# VGG16에서 VGG19를 사용하게 될 때, 레이어층을 더 깊게 사용하나 반드시 정확도가 개선되는 것은 아닌 것으로 보입니다.

![image](https://user-images.githubusercontent.com/69743938/172105394-b64fe538-e0a5-4a19-8ea7-f82a1a5366e2.png)

# EfficientNetB0에서 EfficientNetB1보다 점수가 개선되지 않은 이유는 callback의 patience 인자 조절이 적합치 않아 최적화되지 않은 상태의 학습을 했을 것으로 보입니다.

# parameter가 늘어났지만, 최적의 학습을 위해 적합한 인자값을 찾는 노력이 수반되어야 합니다.
 
#  InceptionV3가 V16과 V19보다 예측 정확도가 향상하였는데, 이는 매개변수 수는 줄었고 네트워크 성능은 좋아졌습니다. 위의 그래프를 볼 때, 파라미터의 수가 증가할 수록 정확도가 향상되는 경향을 보이지만 각 모델마다 향상되는 속도가 달라짐을 확인했습니다.

각 모델의 적용 code 및 예측 결과 score는 다음과 같습니다.

VGG 19(score : 0.96698)

-------------
```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(VGG19(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```
----------
VGG 16(score : 0.96876)

--------


```python
# es=EarlyStopping(patience=4,restore_best_weights=True) 
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(VGG16(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax'))

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```
-------
ResNet (score : 0.98666)

-------
```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential() #B 숫자 증가~성능 향상 
# model.add(ResNet50(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax')) 
# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```
------
InceptionV3(score : 0.98724)

-----

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
-------
EfficientNetB1 + ModelCheckPoint (score : 0.98873)

---------


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
------------
EfficientNetB1 (score : 0.99095)

-----------


```python
# es=EarlyStopping(patience=4,restore_best_weights=True)
# rl=ReduceLROnPlateau(patience=3,verbose=1)
# model=Sequential()
# model.add(EfficientNetB1(include_top=False,pooling='avg'))
# model.add(Dense(2,activation='softmax')) 

# model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy') 
# model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```
-------
MobileNet(score : 0.99113)

----------

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
----------
EfficientNetB0(score : 0.99233)

--------


```python
es=EarlyStopping(patience=4,restore_best_weights=True)
rl=ReduceLROnPlateau(patience=3,verbose=1)
model=Sequential() #B 숫자 증가~성능 향상 
model.add(EfficientNetB0(include_top=False,pooling='avg'))
model.add(Dense(2,activation='softmax')) 
model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[es,rl])
```

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

<keras.callbacks.History at 0x7fade406cf10>

-----------
Xception(score : 0.99315)

---------


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

Found 1531 validated image filenames.

```python
result=model.predict(test_generator,verbose=1,workers=2) 
```

48/48 [==============================] - 41s 806ms/step


```python
result
```


array([[2.7186363e-03, 9.9728131e-01],

[9.9734539e-01, 2.6546121e-03],

[9.9898201e-01, 1.0179272e-03],

...,

[9.9999774e-01, 2.2147251e-06],

[1.1051272e-07, 9.9999988e-01],

[1.6658715e-06, 9.9999833e-01]], dtype=float32)


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

---------------
invasive가 1일 확률을 제출하므로 각 행의 result 값에서 2번째 값을 반환해야합니다.

따라서 result[모든행,2번째 값]을 기준으로 sub['invasive']값에 적용하였습니다.

------------


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
