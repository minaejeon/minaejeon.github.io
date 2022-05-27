
# 7 training Image 전처리 기법 효과 분석 (Kaggle Plant Seedlings Classification)

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
/kaggle/input/plant-seedlings-classification/sample_submission.csv
/kaggle/input/plant-seedlings-classification/test/fd87b36ae.png
/kaggle/input/plant-seedlings-classification/test/0e8492cb1.png
/kaggle/input/plant-seedlings-classification/test/8d6acbe9b.png
/kaggle/input/plant-seedlings-classification/test/54b3afd58.png
/kaggle/input/plant-seedlings-classification/test/6049234e6.png
/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/4ae939d7d.png
/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/b8664f705.png
/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/628b08c82.png
/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/9ab3b61db.png
/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/086894274.png
/kaggle/input/plant-seedlings-classification/train/Common wheat/df584ca28.png
/kaggle/input/plant-seedlings-classification/train/Common wheat/9026da493.png
/kaggle/input/plant-seedlings-classification/train/Common wheat/1a9a859c9.png
/kaggle/input/plant-seedlings-classification/train/Common wheat/c48b788a4.png
/kaggle/input/plant-seedlings-classification/train/Common wheat/c643a424f.png
/kaggle/input/plant-seedlings-classification/train/Charlock/67e37de9b.png
/kaggle/input/plant-seedlings-classification/train/Charlock/8b35222d0.png
/kaggle/input/plant-seedlings-classification/train/Charlock/4e0cef11d.png
/kaggle/input/plant-seedlings-classification/train/Charlock/84281dd7c.png
/kaggle/input/plant-seedlings-classification/train/Charlock/d04eff450.png
/kaggle/input/plant-seedlings-classification/train/Black-grass/2aa60045d.png
/kaggle/input/plant-seedlings-classification/train/Black-grass/a47cfeec4.png
/kaggle/input/plant-seedlings-classification/train/Black-grass/c025e2886.png
/kaggle/input/plant-seedlings-classification/train/Black-grass/48141d6a7.png
/kaggle/input/plant-seedlings-classification/train/Black-grass/ed540beb6.png
/kaggle/input/plant-seedlings-classification/train/Sugar beet/4839e4577.png
/kaggle/input/plant-seedlings-classification/train/Sugar beet/3041d1470.png
/kaggle/input/plant-seedlings-classification/train/Sugar beet/fef5e7066.png
/kaggle/input/plant-seedlings-classification/train/Sugar beet/ed71987ae.png
/kaggle/input/plant-seedlings-classification/train/Sugar beet/6d63eb98f.png
/kaggle/input/plant-seedlings-classification/train/Loose Silky-bent/93d9858f0.png
/kaggle/input/plant-seedlings-classification/train/Loose Silky-bent/de82f96f1.png
/kaggle/input/plant-seedlings-classification/train/Loose Silky-bent/6d2f11b51.png
/kaggle/input/plant-seedlings-classification/train/Loose Silky-bent/17d3e7e2c.png
/kaggle/input/plant-seedlings-classification/train/Loose Silky-bent/f9d597956.png
/kaggle/input/plant-seedlings-classification/train/Maize/65ba0f497.png
/kaggle/input/plant-seedlings-classification/train/Maize/fc02b8466.png
/kaggle/input/plant-seedlings-classification/train/Maize/266211c3c.png
/kaggle/input/plant-seedlings-classification/train/Maize/988113525.png
/kaggle/input/plant-seedlings-classification/train/Maize/f2c22a1bf.png
/kaggle/input/plant-seedlings-classification/train/Cleavers/bd6681c02.png
/kaggle/input/plant-seedlings-classification/train/Cleavers/6bcc0c252.png
/kaggle/input/plant-seedlings-classification/train/Cleavers/3fc47de35.png
/kaggle/input/plant-seedlings-classification/train/Cleavers/d8597aa6a.png
/kaggle/input/plant-seedlings-classification/train/Cleavers/420f3654f.png
/kaggle/input/plant-seedlings-classification/train/Common Chickweed/57731eb29.png
/kaggle/input/plant-seedlings-classification/train/Common Chickweed/40c5757c0.png
/kaggle/input/plant-seedlings-classification/train/Common Chickweed/28285eb94.png
/kaggle/input/plant-seedlings-classification/train/Common Chickweed/1d00f7fab.png
/kaggle/input/plant-seedlings-classification/train/Common Chickweed/eddaf3d47.png
/kaggle/input/plant-seedlings-classification/train/Fat Hen/7f731311e.png
/kaggle/input/plant-seedlings-classification/train/Fat Hen/00268e97d.png
/kaggle/input/plant-seedlings-classification/train/Fat Hen/685091401.png
/kaggle/input/plant-seedlings-classification/train/Fat Hen/a86b9c0cd.png
/kaggle/input/plant-seedlings-classification/train/Fat Hen/ff9f29145.png
/kaggle/input/plant-seedlings-classification/train/Small-flowered Cranesbill/00d030ea0.png
/kaggle/input/plant-seedlings-classification/train/Small-flowered Cranesbill/85f33fcee.png
/kaggle/input/plant-seedlings-classification/train/Small-flowered Cranesbill/58e22d25a.png
/kaggle/input/plant-seedlings-classification/train/Small-flowered Cranesbill/7adff29ac.png
/kaggle/input/plant-seedlings-classification/train/Small-flowered Cranesbill/b8ac37dcd.png
/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/8056c3590.png
/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/896a23ea3.png
/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/97bfbdcf0.png
/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/da6621ac8.png
/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/d33d10a18.png
</pre>
train 폴더안에 이미지 파일로 데이터가 주어져 있습니다.



각 파일의 특징을 추출한 dataframe을 만들고자 glob를 사용합니다.



```python
import glob
train=pd.DataFrame({'path':glob.glob('/kaggle/input/plant-seedlings-classification/train/*/*')})
pd.options.display.max_colwidth=99
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/4ae939d7d.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/b8664f705.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/628b08c82.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/9ab3b61db.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/086894274.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>4745</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/f0127f70d.png</td>
    </tr>
    <tr>
      <th>4746</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/179cedc9e.png</td>
    </tr>
    <tr>
      <th>4747</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/a0ec33869.png</td>
    </tr>
    <tr>
      <th>4748</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/33010c8cb.png</td>
    </tr>
    <tr>
      <th>4749</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/aad81b27b.png</td>
    </tr>
  </tbody>
</table>
<p>4750 rows × 1 columns</p>
</div>


데이터가 주어질 때, plant species별로 이미지가 분류되어 있습니다.



'path'의 정보로부터 plant species 정보를 분류할 수 있습니다.



/기호 역으로 2번째에 해당하므로 /기준으로 split하였을 때 -2 위치에 해당합니다. 이를 칼럼으로 만들어 보겠습니다.



```python
train['species']=train['path'].apply(lambda x : x.split('/')[-2])
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/4ae939d7d.png</td>
      <td>Scentless Mayweed</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/b8664f705.png</td>
      <td>Scentless Mayweed</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/628b08c82.png</td>
      <td>Scentless Mayweed</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/9ab3b61db.png</td>
      <td>Scentless Mayweed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Scentless Mayweed/086894274.png</td>
      <td>Scentless Mayweed</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4745</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/f0127f70d.png</td>
      <td>Shepherds Purse</td>
    </tr>
    <tr>
      <th>4746</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/179cedc9e.png</td>
      <td>Shepherds Purse</td>
    </tr>
    <tr>
      <th>4747</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/a0ec33869.png</td>
      <td>Shepherds Purse</td>
    </tr>
    <tr>
      <th>4748</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/33010c8cb.png</td>
      <td>Shepherds Purse</td>
    </tr>
    <tr>
      <th>4749</th>
      <td>/kaggle/input/plant-seedlings-classification/train/Shepherds Purse/aad81b27b.png</td>
      <td>Shepherds Purse</td>
    </tr>
  </tbody>
</table>
<p>4750 rows × 2 columns</p>
</div>



```python
train['species'].value_counts()
```

<pre>
Loose Silky-bent             654
Common Chickweed             611
Scentless Mayweed            516
Small-flowered Cranesbill    496
Fat Hen                      475
Charlock                     390
Sugar beet                   385
Cleavers                     287
Black-grass                  263
Shepherds Purse              231
Common wheat                 221
Maize                        221
Name: species, dtype: int64
</pre>

```python
train['species']=train['species'].astype(str)
```


```python
species=train['species'].value_counts()
species.index
```

<pre>
Index(['Loose Silky-bent', 'Common Chickweed', 'Scentless Mayweed',
       'Small-flowered Cranesbill', 'Fat Hen', 'Charlock', 'Sugar beet',
       'Cleavers', 'Black-grass', 'Shepherds Purse', 'Common wheat', 'Maize'],
      dtype='object')
</pre>

```python
image data 학습 model은 동일하게 적용하고, image 전처리 기법을 달리하여 점수의 변화를 살펴 보겠습니다.
```

이미지 자르기 (score : 0.96221)



• 이미지 주변을 제거하여 차원을 줄일 수 있습니다.



• 이미지는 2차원 넘파이 배열로 저장됩니다.



• 배열 슬라이싱을 사용해 간단하게 이미지를 자를 수 있습니다



• OpenCV는 이미지를 행렬로 표현하므로 이미지에서 남기고 싶은 특정 부분을 행과 열을 선택하여 이미지 자르기 기능을 사용합니다.



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image, (362,362))
        image=image[:,181]
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [01:38<00:00,  8.19s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
이미지 투명도 처리(score: 0.94710)



• 이미지를 흐리게 하려면 각 픽셀을 주변 픽셀의 평균값으로 변환합니다.



• 주변 픽셀에 수행되는 연산을 수학적으로 커널이라 표현합니다.



• 커널의 크기는 흐림의 정도를 결정합니다.



• 커널이 클수록 이미지가 더 부드러워집니다.



• 커널은 이미지를 선명하게 만드는 것부터 경계선 감지까지 이미지 처리 작업을 하는데 널리 사용됩니다.



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/', exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image, (362,362))
        image=cv2.blur(image, (5,5))
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:55<00:00,  4.64s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
이미지 투명도 처리 (score : 0.94836)



• 커널은 이미지를 선명하게 만드는 것부터 경계선 감지까지 이미지 처리 작업을 하는데 널리 사용됩니다.



• 커널 PCA와 서포트 벡터 머신이 사용하는 비선형 함수를 커널이라 부릅니다.



• Meanshift 알고리즘에서는 샘플의 영향 범위를 커널이라 부릅니다.



• 신경망의 가중치를 커널이라 부릅니다



• 커널 크기는 (너비, 높이)로 지정합니다.



• 주변 픽셀값의 평균을 계산하는 커널은 이미지를 흐리게 처리합니다.



• blur 함수는 각 픽셀에 커널 개수의 역수를 곱하여 모두 더합니다. ( 이 값이 중앙 픽셀의 값이 됩니다.)



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/', exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image,(362,362))
        kernel=np.ones((5,5)) / 25.0
        kernel
        image_kernel=cv2.filter2D(image, -1, kernel)
        image=cv2.GaussianBlur(image_kernel, (5,5), 0)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [01:05<00:00,  5.43s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
이미지 선명하게 하기(score : 0.94206)



• 대상 픽셀을 강조하는 커널을 만들고 filter2D를 사용하여 이미지에 커널을 적용합니다



• 중앙 픽셀을 부각하는 커널을 만들면 이미지의 경계선에서 대비가 더욱 두드러지는 효과가 생깁니다.



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image, (362,362))
        kernel = np.array([[0, -1, 0],
                          [-1, 5, -1],
                          [0, -1, 0]])
        image_kernel=cv2.filter2D(image, -1, kernel)
        image=cv2.GaussianBlur(image_kernel, (5,5), 0)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train', 'zip', '362_train')
```

<pre>
100%|██████████| 12/12 [00:56<00:00,  4.70s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
이미지 대비 높이기 (Score : 0.95465)



• 히스토그램 평활화는 객체의 형태가 두드러지도록 만들어주는 이미지 처리 도구입니다



• Y는 루마(luma) 또는 밝기이고 U와 V는 컬러를 나타냅니다..



• 흑백 이미지에는 OpenCV의 equalizeHist()를 바로 적용할 수 있습니다.



• 히스토그램 평활화는 픽셀값의 범위가 커지도록 이미지를 변환합니다.



• 히스토그램 평활화는 관심 대상을 다른 객체나 배경과 잘 구분되도록 만들어줍니다.



에러 발생



두가지 과정으로 쪼갬 흑백/컬러



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path,cv2.IMREAD_GRAYSCALE)
        image=cv2.resize(image,(362,362))
        image=cv2.equalizeHist(image)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:52<00:00,  4.39s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
score : 0.93954



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image_bgr=cv2.imread(path)
        image_bgr=cv2.resize(image_bgr,(362,362))
        image_yuv=cv2.cvtColor(image_bgr, cv2.COLOR_BGR2YUV)
        image_yuv[:, :, 0]=cv2.equalizeHist(image_yuv[:,:,0])
        image=cv2.cvtColor(image_yuv, cv2.COLOR_YUV2RGB)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:55<00:00,  4.62s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
색상 구분 (score : 0.94458)



• 이미지에서 한 색상을 구분하려면 색 범위를 정의하고 이미지에 마스크를 적용합니다.



• 이미지를 HSV(색상, 채도, 명도)로 변환 -> 격리시킬 값의 범위를 정의 -> 이미지에 적용할 마스크를 만듭니다.(마 스크의 흰색 영역만 유지)



• bitwise_and()는 마스크를 적용하고 원하는 포맷으로 변환



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species.index):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image,(362,362))
        image_hsv=cv2.cvtColor(image, cv2.COLOR_BGR2HSV) #BGR에서 HSV로 전환
        lower_blue=np.array([50,100,50]) #HSV에서 파랑 값의 범위를 정의
        upper_blue=np.array([130,255,255])
        mask=cv2.inRange(image_hsv, lower_blue, upper_blue) #마스크를 만듭니다
        image_bgr_masked=cv2.bitwise_and(image, image, mask=mask) #이미지에 마스크를 적용
        image=cv2.cvtColor(image_bgr_masked, cv2.COLOR_BGR2RGB) #BGR에서 RGB로 전환
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:54<00:00,  4.53s/it]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
이미지 이진화 (score : 0.96095)



• 이미지 이진화(임계처리)thresholding은 어떤 값보다 큰 값을 가진 픽셀을 흰색으로 만들고 작은 값을 가진 픽셀은 검은색으로 만드는 과정입니다.



• 적응적 이진화(임계처리)adaptive thresholding은 픽셀의 임계값이 주변 픽셀의 강도에 의해 결정됩니다.



• 이진화는 이미지 안의 영역 마다 빛 조건이 달라질 때 도움이 됩니다.



• adaptiveThreshold()의 max_output_value매개변수는 출력 픽셀 강도의 최대값을 결정



• cv2.ADAPTIVE_THRESH_GAUSSIAN_C는 픽셀의 임계값을 주변 픽셀 강도의 가중치 합으로 설정합니다



• cv2.ADAPTIVE_THRESH_MEAN_C는 픽셀의 임계값을 주변 픽셀의 평균으로 설정합니다



에러 발생



흑백화해서 사용



```python
import shutil
from tqdm import tqdm
for category in tqdm(species):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image_gray=cv2.imread(path,cv2.IMREAD_GRAYSCALE)
        image_gray=cv2.resize(image_gray, (362,362))
        max_output_value=255
        neighborhood_size=99
        subtract_from_mean=10
        image=cv2.adaptiveThreshold(image_gray, max_output_value, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, neighborhood_size, subtract_from_mean)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:00<00:00, 771.28it/s]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
경계선 감지 (score:0.97103)



• 캐니(Canny) 경계선 감지기와 같은 경계선 감지 기술 사용



• 경계선 감지는 컴퓨터 비전의 주요 관심 대상이며 경계선은 많은 정보가 담긴 영역입니다.



• 경계선 감지를 사용하여 정보가 적은 영역을 제거하고 대부분의 정보가 담긴 이미지 영역을 구분할 수 있습니다.



• 캐니 감지기는 그레이디언트 임계값의 저점과 고점을 나타내는 두 매개변수가 필요합니다.



• 낮은 임계값과 높은 임계값 사이의 가능성 있는 경계선 픽셀은 약한 경계선 픽셀로 간주됩니다



• OpenCV의 Canny 함수는 낮은 임곗값과 높은 임곗값이 필수 매개변수입니다.



• Canny를 전체 이미지 모음에 적용하기 전에 몇 개의 이미지를 테스트하여 낮은 임계값과 높은 임곗값의 적절한 쌍 을 찾는 것이 좋은 결과를 만듭니다.



• 예제 실습은 낮은 임곗값과 높은 임곗값을 이미지 중간 픽셀 강도의 1표준편차 아래 값과 위 값으로 설정



```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(species):
    os.makedirs('362_train/',exist_ok=True)
    for path in train[train['species']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image,(362,362))
        median_intensity=np.median(image) #픽셀 강도의 중간 값을 계산
        #중간 픽셀 강도에서 위 아래 1 표준 편차 떨어진 값을 임계값으로 지정
        lower_threshold=int(max(0, (1.0 - 0.33)*median_intensity))
        upper_threshold=int(min(255, (1.0 + 0.33)*median_intensity))
        #캐니 경계선 감지기를 이용합니다
        image=cv2.Canny(image, lower_threshold, upper_threshold)
        path_split=path.split('/')[-1]
        cv2.imwrite('/kaggle/input/plant-seedlings-classification/train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```

<pre>
100%|██████████| 12/12 [00:00<00:00, 802.05it/s]
</pre>
<pre>
'/kaggle/working/362_train.zip'
</pre>
test의 데이터도 또한 폴더안에 이미지가 저장되어 있으나, species로 분류되어 있지 않습니다.



glob로 path column을 가져와서 dataframe의 형식으로 특징을 추출할 수 있으나, glob로는 순서가 뒤엉킨다는 단점이 있습니다.



train data와 test data를 모두 glob사용하는 경우, test data는 순서를 fix하는 index reset작업을 추가로 진행 해주어야 합니다.



submission data를 이용해서 test data를 가져오는 것으로 먼저 생각했습니다.



```python
test=pd.read_csv('/kaggle/input/plant-seedlings-classification/sample_submission.csv')
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>file</th>
      <th>species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0021e90e4.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>1</th>
      <td>003d61042.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>2</th>
      <td>007b3da8b.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0086a6340.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00c47e980.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>789</th>
      <td>fea355851.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>790</th>
      <td>fea3da57c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>791</th>
      <td>fef2ade8c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>792</th>
      <td>ff65bc002.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>793</th>
      <td>ffc6f8527.png</td>
      <td>Sugar beet</td>
    </tr>
  </tbody>
</table>
<p>794 rows × 2 columns</p>
</div>



```python
test['path']='/kaggle/input/plant-seedlings-classification/test/'+test['file']
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>file</th>
      <th>species</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0021e90e4.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/0021e90e4.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>003d61042.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/003d61042.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>007b3da8b.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/007b3da8b.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0086a6340.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/0086a6340.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00c47e980.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/00c47e980.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>789</th>
      <td>fea355851.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/fea355851.png</td>
    </tr>
    <tr>
      <th>790</th>
      <td>fea3da57c.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/fea3da57c.png</td>
    </tr>
    <tr>
      <th>791</th>
      <td>fef2ade8c.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/fef2ade8c.png</td>
    </tr>
    <tr>
      <th>792</th>
      <td>ff65bc002.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/ff65bc002.png</td>
    </tr>
    <tr>
      <th>793</th>
      <td>ffc6f8527.png</td>
      <td>Sugar beet</td>
      <td>/kaggle/input/plant-seedlings-classification/test/ffc6f8527.png</td>
    </tr>
  </tbody>
</table>
<p>794 rows × 3 columns</p>
</div>


이미지 분류 학습에 사용할 데이터를 x_train, x_valid 로 나누어 학습을 진행하겠습니다.



```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
from sklearn.model_selection import train_test_split
x_train, x_valid = train_test_split(train, test_size=0.2, random_state=42, stratify=train['species'])
```

image 데이터를 처리해야 하므로, ImageDataGenerator를 이용하여 변환하여 줍니다.



```python
train_generator=idg.flow_from_dataframe(x_train,x_col='path',y_col='species')
```

<pre>
Found 3800 validated image filenames belonging to 12 classes.
</pre>

```python
valid_generator=idg.flow_from_dataframe(x_valid, x_col='path', y_col='species')
```

<pre>
Found 950 validated image filenames belonging to 12 classes.
</pre>

```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.applications.efficientnet import *
from tensorflow.keras.callbacks import *
```

성능이 비교적 우수한 것으로 알려져있는 EfficientNetB0를 이용하여 학습에 사용합니다.



```python
es=EarlyStopping(patience=4, restore_best_weights=True)
rl=ReduceLROnPlateau(patience=4, verbose=1)
model=Sequential()
model.add(EfficientNetB0(include_top=False,pooling='avg'))
model.add(Dense(12, activation='softmax'))
model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
model.fit(train_generator, validation_data=valid_generator, epochs=1000, callbacks=[es,rl])
```


<pre>
Downloading data from https://storage.googleapis.com/keras-applications/efficientnetb0_notop.h5
16711680/16705208 [==============================] - 0s 0us/step
16719872/16705208 [==============================] - 0s 0us/step
</pre>
<pre>
2022-05-22 04:12:08.954289: I tensorflow/compiler/mlir/mlir_graph_optimization_pass.cc:185] None of the MLIR Optimization Passes are enabled (registered 2)
</pre>
<pre>
Epoch 1/1000
</pre>
<pre>
2022-05-22 04:12:17.634328: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005
</pre>
<pre>
119/119 [==============================] - 79s 541ms/step - loss: 0.5781 - acc: 0.8076 - val_loss: 1.2555 - val_acc: 0.6779
Epoch 2/1000
119/119 [==============================] - 63s 528ms/step - loss: 0.1903 - acc: 0.9371 - val_loss: 0.8262 - val_acc: 0.7916
Epoch 3/1000
119/119 [==============================] - 63s 526ms/step - loss: 0.1110 - acc: 0.9634 - val_loss: 0.2916 - val_acc: 0.9242
Epoch 4/1000
119/119 [==============================] - 65s 545ms/step - loss: 0.0894 - acc: 0.9697 - val_loss: 0.2442 - val_acc: 0.9263
Epoch 5/1000
119/119 [==============================] - 63s 526ms/step - loss: 0.1162 - acc: 0.9626 - val_loss: 0.4435 - val_acc: 0.8600
Epoch 6/1000
119/119 [==============================] - 62s 520ms/step - loss: 0.0782 - acc: 0.9734 - val_loss: 0.2518 - val_acc: 0.9147
Epoch 7/1000
119/119 [==============================] - 63s 527ms/step - loss: 0.0517 - acc: 0.9853 - val_loss: 0.2538 - val_acc: 0.9474
Epoch 8/1000
119/119 [==============================] - 62s 523ms/step - loss: 0.0506 - acc: 0.9829 - val_loss: 0.3482 - val_acc: 0.9074

Epoch 00008: ReduceLROnPlateau reducing learning rate to 0.00010000000474974513.
</pre>
<pre>
<keras.callbacks.History at 0x7f5c90156590>
</pre>
predict할 test값을 ImageDataGenerator를 이용하여 변환해 줍니다.



```python
test_generator=idg.flow_from_dataframe(test, x_col='path', y_col=None, shuffle=False, class_mode=None)
```

<pre>
Found 794 validated image filenames.
</pre>

```python
result=model.predict(test_generator, verbose=1, workers=2)
```

<pre>
25/25 [==============================] - 6s 210ms/step
</pre>

```python
sub=pd.read_csv('/kaggle/input/plant-seedlings-classification/sample_submission.csv')
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>file</th>
      <th>species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0021e90e4.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>1</th>
      <td>003d61042.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>2</th>
      <td>007b3da8b.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0086a6340.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00c47e980.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>789</th>
      <td>fea355851.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>790</th>
      <td>fea3da57c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>791</th>
      <td>fef2ade8c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>792</th>
      <td>ff65bc002.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>793</th>
      <td>ffc6f8527.png</td>
      <td>Sugar beet</td>
    </tr>
  </tbody>
</table>
<p>794 rows × 2 columns</p>
</div>


result의 값을 살펴보면, 모든 가능한 species별 일치할 확률이 나타나 있습니다.



따라서 가장 높은 값을 가져오는 argmax(1)를 이용하여 sub dataframe의 species column으로 추가할 수 있습니다.



그러나 결과에는 각 species에 해당하는 숫자로 표기되어 있습니다.



따라서 이를 species 명 (문자)로 변환하는 작업이 필요합니다.



먼저 train_generator에서 존재하는 class의 명칭 list를 가져와 class_list로 지정해 주겠습니다.



```python
sub['species']=result.argmax(1)
class_list=list(train_generator.class_indices)
class_list
```

<pre>
['Black-grass',
 'Charlock',
 'Cleavers',
 'Common Chickweed',
 'Common wheat',
 'Fat Hen',
 'Loose Silky-bent',
 'Maize',
 'Scentless Mayweed',
 'Shepherds Purse',
 'Small-flowered Cranesbill',
 'Sugar beet']
</pre>

```python
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>file</th>
      <th>species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0021e90e4.png</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>003d61042.png</td>
      <td>5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>007b3da8b.png</td>
      <td>11</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0086a6340.png</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00c47e980.png</td>
      <td>11</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>789</th>
      <td>fea355851.png</td>
      <td>6</td>
    </tr>
    <tr>
      <th>790</th>
      <td>fea3da57c.png</td>
      <td>11</td>
    </tr>
    <tr>
      <th>791</th>
      <td>fef2ade8c.png</td>
      <td>11</td>
    </tr>
    <tr>
      <th>792</th>
      <td>ff65bc002.png</td>
      <td>1</td>
    </tr>
    <tr>
      <th>793</th>
      <td>ffc6f8527.png</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>794 rows × 2 columns</p>
</div>


class list에 각 해당하는 숫자 값을 부여하고 class_dict로 지정해 주겠습니다.



```python
class_dict=dict(zip(range(12),class_list))
class_dict
```

<pre>
{0: 'Black-grass',
 1: 'Charlock',
 2: 'Cleavers',
 3: 'Common Chickweed',
 4: 'Common wheat',
 5: 'Fat Hen',
 6: 'Loose Silky-bent',
 7: 'Maize',
 8: 'Scentless Mayweed',
 9: 'Shepherds Purse',
 10: 'Small-flowered Cranesbill',
 11: 'Sugar beet'}
</pre>
기존 sub dataframe의 species column값을 class_dict로 대체하면 해당하는 species 명으로 대체가 됩니다.



```python
sub['species']=sub['species'].replace(class_dict)
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>file</th>
      <th>species</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0021e90e4.png</td>
      <td>Small-flowered Cranesbill</td>
    </tr>
    <tr>
      <th>1</th>
      <td>003d61042.png</td>
      <td>Fat Hen</td>
    </tr>
    <tr>
      <th>2</th>
      <td>007b3da8b.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0086a6340.png</td>
      <td>Common Chickweed</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00c47e980.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>789</th>
      <td>fea355851.png</td>
      <td>Loose Silky-bent</td>
    </tr>
    <tr>
      <th>790</th>
      <td>fea3da57c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>791</th>
      <td>fef2ade8c.png</td>
      <td>Sugar beet</td>
    </tr>
    <tr>
      <th>792</th>
      <td>ff65bc002.png</td>
      <td>Charlock</td>
    </tr>
    <tr>
      <th>793</th>
      <td>ffc6f8527.png</td>
      <td>Black-grass</td>
    </tr>
  </tbody>
</table>
<p>794 rows × 2 columns</p>
</div>



```python
sub.to_csv('cutting.csv',index=False)
```

제출하였을 때, score가 높을 수록 대회 순위가 개선되었습니다.



캐니 경계선 감지 > 자르기 > 이진화 > 대비 높이기 1번째 > 투명도 처리 2번째 > 투명도 처리 1번째 > 색상 구분 > 선명하게 하기 > 대비 높이기 2번째



순으로 score가 높았습니다.



각 species 별 이미지를 한개씩 불러와 보겠습니다.

![image](https://user-images.githubusercontent.com/69743938/170181948-7494ad51-9af6-4cc5-8683-eed786e89e0b.png)
![image](https://user-images.githubusercontent.com/69743938/170181967-5ec29e8a-5016-4d11-b7ef-7172ed5fb733.png)
![image](https://user-images.githubusercontent.com/69743938/170181981-b46d6314-2b35-4288-83ef-61cd3b023a66.png)
![image](https://user-images.githubusercontent.com/69743938/170181991-bd2353ad-9e17-4c8d-ab27-82f713157563.png)
![image](https://user-images.githubusercontent.com/69743938/170182001-ada66401-2db4-4004-989c-684ce0ab5ef9.png)
![image](https://user-images.githubusercontent.com/69743938/170182009-398dd227-be7a-429b-aa63-19f547abf50a.png)



캐니 경계선 감지 > 자르기 > 이진화 > 대비 높이기 1번째 > 투명도 처리 2번째 > 투명도 처리 1번째 > 색상 구분 > 선명하게 하기 > 대비 높이기 2번째



각 plants의 가장 두드러진 차이점은 모서리 부분 입니다. 따라서 캐니 경계선 감지 전처리가 가장 효과적이었고, 이미지를 자르게 되면 학습 효과가 세분화됩니다



이미지 이진화를 하게 되면 어두운 곳에서 촬영된 경우 보정하여 학습하므로 정확도를 높인다는 장점이 있습니다. 또한 이미지 대비를 높일 때 컬러보다 흑백일 경우 모양이 두드러지지 않아 더욱 세밀하게 학습 훈련할 수 있습니다.



이미지 투명도 처리의 경우도 단순히 blur 처리를 하는 것보다, filter2D이후 GaussianBlur를 이용할 때 학습효과가 높았습니다.



species간 색상 차이는 크지 않아서 선명하게 혹은 색상 구분을 극대화하는 것보다 흑백처리하여 학습하는 것이 더욱 효과가 높았습니다.



주어진 데이터의 두드러진 차이점을 감안하여 데이터 전처리가 필요함을 느꼈습니다.

