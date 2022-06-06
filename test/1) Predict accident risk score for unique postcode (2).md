---
layout: single
title:  "jupyter notebook 변환하기!"
categories: coding
tag: [python, blog, jekyll]
toc: true
author_profile: false
---

<head>
  <style>
    table.dataframe {
      white-space: normal;
      width: 100%;
      height: 240px;
      display: block;
      overflow: auto;
      font-family: Arial, sans-serif;
      font-size: 0.9rem;
      line-height: 20px;
      text-align: center;
      border: 0px !important;
    }

    table.dataframe th {
      text-align: center;
      font-weight: bold;
      padding: 8px;
    }

    table.dataframe td {
      text-align: center;
      padding: 8px;
    }

    table.dataframe tr:hover {
      background: #b8d1f3; 
    }

    .output_prompt {
      overflow: auto;
      font-size: 0.9rem;
      line-height: 1.45;
      border-radius: 0.3rem;
      -webkit-overflow-scrolling: touch;
      padding: 0.8rem;
      margin-top: 0;
      margin-bottom: 15px;
      font: 1rem Consolas, "Liberation Mono", Menlo, Courier, monospace;
      color: $code-text-color;
      border: solid 1px $border-color;
      border-radius: 0.3rem;
      word-break: normal;
      white-space: pre;
    }

  .dataframe tbody tr th:only-of-type {
      vertical-align: middle;
  }

  .dataframe tbody tr th {
      vertical-align: top;
  }

  .dataframe thead th {
      text-align: center !important;
      padding: 8px;
  }

  .page__content p {
      margin: 0 0 0px !important;
  }

  .page__content p > strong {
    font-size: 0.8rem !important;
  }

  </style>
</head>



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
/kaggle/input/image-classification/sample_submission.csv
/kaggle/input/image-classification/train.csv
/kaggle/input/image-classification/test.csv
/kaggle/input/image-classification/test/173.png
/kaggle/input/image-classification/test/043.png
/kaggle/input/image-classification/test/038.png
/kaggle/input/image-classification/test/069.png
/kaggle/input/image-classification/test/083.png
/kaggle/input/image-classification/train/641.png
/kaggle/input/image-classification/train/173.png
/kaggle/input/image-classification/train/815.png
/kaggle/input/image-classification/train/491.png
/kaggle/input/image-classification/train/718.png
</pre>

```python
train=pd.read_csv('/kaggle/input/image-classification/train.csv')
train
```

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
      <th>file_name</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>10-2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>10-1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>8</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>9</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>853</th>
      <td>854.png</td>
      <td>9</td>
    </tr>
    <tr>
      <th>854</th>
      <td>855.png</td>
      <td>1</td>
    </tr>
    <tr>
      <th>855</th>
      <td>856.png</td>
      <td>4</td>
    </tr>
    <tr>
      <th>856</th>
      <td>857.png</td>
      <td>10-1</td>
    </tr>
    <tr>
      <th>857</th>
      <td>858.png</td>
      <td>7</td>
    </tr>
  </tbody>
</table>
<p>858 rows × 2 columns</p>
</div>


public : private = 1 : 1 

test_data 200개



```python
train['label'].value_counts()
```

<pre>
2       83
4       83
10-1    82
7       82
8       79
9       79
5       79
6       79
1       79
3       77
10-2    56
Name: label, dtype: int64
</pre>

```python
train['path']='/kaggle/input/image-classification/train/'+train['file_name']
train
```

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
      <th>file_name</th>
      <th>label</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>10-2</td>
      <td>/kaggle/input/image-classification/train/001.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>10-1</td>
      <td>/kaggle/input/image-classification/train/002.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>3</td>
      <td>/kaggle/input/image-classification/train/003.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>8</td>
      <td>/kaggle/input/image-classification/train/004.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>9</td>
      <td>/kaggle/input/image-classification/train/005.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>853</th>
      <td>854.png</td>
      <td>9</td>
      <td>/kaggle/input/image-classification/train/854.png</td>
    </tr>
    <tr>
      <th>854</th>
      <td>855.png</td>
      <td>1</td>
      <td>/kaggle/input/image-classification/train/855.png</td>
    </tr>
    <tr>
      <th>855</th>
      <td>856.png</td>
      <td>4</td>
      <td>/kaggle/input/image-classification/train/856.png</td>
    </tr>
    <tr>
      <th>856</th>
      <td>857.png</td>
      <td>10-1</td>
      <td>/kaggle/input/image-classification/train/857.png</td>
    </tr>
    <tr>
      <th>857</th>
      <td>858.png</td>
      <td>7</td>
      <td>/kaggle/input/image-classification/train/858.png</td>
    </tr>
  </tbody>
</table>
<p>858 rows × 3 columns</p>
</div>



```python
import cv2
import shutil
from tqdm import tqdm
os.makedirs('384_train/',exist_ok=True)
for path in tqdm(train['path']):
    image=cv2.imread(path)
    image=cv2.blur(image, (5,5))
    image_hsv=cv2.cvtColor(image, cv2.COLOR_BGR2HSV) #BGR에서 HSV로 전환
    lower_blue=np.array([50,100,50]) #HSV에서 파랑 값의 범위를 정의
    upper_blue=np.array([130,255,255])
    mask=cv2.inRange(image_hsv, lower_blue, upper_blue) #마스크를 만듭니다
    image_bgr_masked=cv2.bitwise_and(image, image, mask=mask) #이미지에 마스크를 적용
    image=cv2.cvtColor(image_bgr_masked, cv2.COLOR_BGR2RGB) #BGR에서 RGB로 전환
    image=cv2.resize(image, (384,384))
    image=image[:,181]
    max_output_value=255
    neighborhood_size=99
    subtract_from_mean=10
    image=cv2.adaptiveThreshold(image, max_output_value, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, neighborhood_size, subtract_from_mean)
    median_intensity=np.median(image) #픽셀 강도의 중간 값을 계산
    #중간 픽셀 강도에서 위 아래 1 표준 편차 떨어진 값을 임계값으로 지정
    lower_threshold=int(max(0, (1.0 - 0.33)*median_intensity))
    upper_threshold=int(min(255, (1.0 + 0.33)*median_intensity))
    #캐니 경계선 감지기를 이용합니다
    image=cv2.Canny(image, lower_threshold, upper_threshold)
    path_split=path.split('/')[-1]
    cv2.imwrite('/kaggle/input/image-classification/train/'+path_split,image)
shutil.make_archive('384_train','zip','384_train')
```

<pre>
100%|██████████| 858/858 [00:04<00:00, 185.59it/s]
</pre>
<pre>
'/kaggle/working/384_train.zip'
</pre>

```python
test=pd.read_csv('/kaggle/input/image-classification/test.csv')
test
```

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
      <th>file_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>210</th>
      <td>211.png</td>
    </tr>
    <tr>
      <th>211</th>
      <td>212.png</td>
    </tr>
    <tr>
      <th>212</th>
      <td>213.png</td>
    </tr>
    <tr>
      <th>213</th>
      <td>214.png</td>
    </tr>
    <tr>
      <th>214</th>
      <td>215.png</td>
    </tr>
  </tbody>
</table>
<p>215 rows × 1 columns</p>
</div>



```python
test['path']='/kaggle/input/image-classification/test/'+test['file_name']
test
```

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
      <th>file_name</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>/kaggle/input/image-classification/test/001.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>/kaggle/input/image-classification/test/002.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>/kaggle/input/image-classification/test/003.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>/kaggle/input/image-classification/test/004.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>/kaggle/input/image-classification/test/005.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>210</th>
      <td>211.png</td>
      <td>/kaggle/input/image-classification/test/211.png</td>
    </tr>
    <tr>
      <th>211</th>
      <td>212.png</td>
      <td>/kaggle/input/image-classification/test/212.png</td>
    </tr>
    <tr>
      <th>212</th>
      <td>213.png</td>
      <td>/kaggle/input/image-classification/test/213.png</td>
    </tr>
    <tr>
      <th>213</th>
      <td>214.png</td>
      <td>/kaggle/input/image-classification/test/214.png</td>
    </tr>
    <tr>
      <th>214</th>
      <td>215.png</td>
      <td>/kaggle/input/image-classification/test/215.png</td>
    </tr>
  </tbody>
</table>
<p>215 rows × 2 columns</p>
</div>



```python
from PIL import Image
Image.open('/kaggle/input/image-classification/train/641.png')
```

<img src="data:image/png;base64,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"/>


```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
```


```python
from sklearn.model_selection import StratifiedKFold
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
from tensorflow.keras.applications.efficientnet import *
skf=StratifiedKFold(n_splits=5,shuffle=True,random_state=88) # 10 15 20 #random_state 변경
result=0
for train_index, valid_index in skf.split(train,train['label']):
    x_train = train.iloc[train_index]
    x_valid = train.iloc[valid_index]
    train_generator=idg.flow_from_dataframe(x_train, x_col='path', y_col='label', target_size=(384,384), batch_size=16) #224/32,
    valid_generator=idg.flow_from_dataframe(x_valid, x_col='path', y_col='label', target_size=(384,384), batch_size=16) #224/32,
    
    model=Sequential()
    model.add(EfficientNetB1(include_top=False,pooling='avg'))
    model.add(Dense(11, activation='softmax'))
    model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
    es=EarlyStopping(patience=6, restore_best_weights=True)
    rl=ReduceLROnPlateau(patience=4, verbose=1) #최적 주변에서 미세 조정, learning rate 줄이는 방법 
    model.fit(train_generator, validation_data=valid_generator, epochs=1000,callbacks=[es,rl])
    test_generator=idg.flow_from_dataframe(test, x_col='path', y_col=None, shuffle=False, class_mode=None)
    result+=model.predict(test_generator, workers=2, verbose=1)/5
```



Epoch 1/1000

43/43 [==============================] - 36s 596ms/step - loss: 1.1160 - acc: 0.6341 - val_loss: 0.9324 - val_acc: 0.7209

Epoch 2/1000

43/43 [==============================] - 22s 520ms/step - loss: 0.3075 - acc: 0.9096 - val_loss: 1.0607 - val_acc: 0.7384

Epoch 3/1000

43/43 [==============================] - 23s 524ms/step - loss: 0.2541 - acc: 0.9067 - val_loss: 1.9010 - val_acc: 0.7616

...

Epoch 21/1000

43/43 [==============================] - 22s 518ms/step - loss: 0.0210 - acc: 0.9927 - val_loss: 0.2201 - val_acc: 0.9474

Found 215 validated image filenames.

7/7 [==============================] - 2s 71ms/step



```python
sub=pd.read_csv('/kaggle/input/image-classification/sample_submission.csv')
sub
```

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
      <th>file_name</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>210</th>
      <td>211.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>211</th>
      <td>212.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>212</th>
      <td>213.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>213</th>
      <td>214.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>214</th>
      <td>215.png</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>215 rows × 2 columns</p>
</div>



```python
sub['label']=result.argmax(1)
sub
```

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
      <th>file_name</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>7</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>9</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>210</th>
      <td>211.png</td>
      <td>6</td>
    </tr>
    <tr>
      <th>211</th>
      <td>212.png</td>
      <td>9</td>
    </tr>
    <tr>
      <th>212</th>
      <td>213.png</td>
      <td>4</td>
    </tr>
    <tr>
      <th>213</th>
      <td>214.png</td>
      <td>7</td>
    </tr>
    <tr>
      <th>214</th>
      <td>215.png</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>215 rows × 2 columns</p>
</div>



```python
class_list=list(train_generator.class_indices)
class_list
```

<pre>
['1', '10-1', '10-2', '2', '3', '4', '5', '6', '7', '8', '9']
</pre>

```python
class_dict=dict(zip(range(11),class_list))
class_dict
```

<pre>
{0: '1',
 1: '10-1',
 2: '10-2',
 3: '2',
 4: '3',
 5: '4',
 6: '5',
 7: '6',
 8: '7',
 9: '8',
 10: '9'}
</pre>

```python
sub['label']=sub['label'].replace(class_dict)
sub
```

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
      <th>file_name</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>8</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>210</th>
      <td>211.png</td>
      <td>5</td>
    </tr>
    <tr>
      <th>211</th>
      <td>212.png</td>
      <td>8</td>
    </tr>
    <tr>
      <th>212</th>
      <td>213.png</td>
      <td>3</td>
    </tr>
    <tr>
      <th>213</th>
      <td>214.png</td>
      <td>6</td>
    </tr>
    <tr>
      <th>214</th>
      <td>215.png</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>215 rows × 2 columns</p>
</div>



```python
sub.to_csv('es6_rl4_88.csv',index=False)
```


```python
pd.DataFrame(result).to_csv('cutting_canny_result.csv',index=False) #Ensemble에 활
```
