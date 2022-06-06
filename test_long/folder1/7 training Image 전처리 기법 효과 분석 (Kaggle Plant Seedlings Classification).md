
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

----------
train 폴더안에 이미지 파일로 데이터가 주어져 있습니다.
각 파일의 특징을 추출한 dataframe을 만들고자 glob를 사용합니다.

-------


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

-----

데이터가 주어질 때, plant species별로 이미지가 분류되어 있습니다.
'path'의 정보로부터 plant species 정보를 분류할 수 있습니다.
/기호 역으로 2번째에 해당하므로 /기준으로 split하였을 때 -2 위치에 해당합니다. 이를 칼럼으로 만들어 보겠습니다.

-----


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


```python
train['species']=train['species'].astype(str)
```


```python
species=train['species'].value_counts()
species.index
```


Index(['Loose Silky-bent', 'Common Chickweed', 'Scentless Mayweed',

'Small-flowered Cranesbill', 'Fat Hen', 'Charlock', 'Sugar beet',

'Cleavers', 'Black-grass', 'Shepherds Purse', 'Common wheat', 'Maize'],

dtype='object')


------
image data 학습 model은 동일하게 적용하고, image 전처리 기법을 달리하여 점수의 변화를 살펴 보겠습니다.
자르기 / 투명도 처리 / 선명하게 하기 / 대비 높이기 / 색상 구분 / 이진화 / 경계선 감지를 적용하려합니다.
# 흥미로운 점은 각 전처리 방식에 따라 학습의 정확성을 높이는 효과가 다르고 때로는 방해되는 것을 확인할 수 있습니다.
전처리 기법을 하나씩 사용하여 예측 정확도를 비교하여 보고 그 이유를 고찰하겠습니다.

이미지 자르기 (score : 0.96221)
------



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


100%|██████████| 12/12 [01:38<00:00,  8.19s/it]

'/kaggle/working/362_train.zip'

-------
# 이미지 투명도 처리(score: 0.94710)

각 픽셀을 주변 픽셀의 평균값으로 변환하여 투명도를 처리합니다. 커널이 클수록 흐름의 정도가 커지며 이미지가 부드러워집니다

---------

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


100%|██████████| 12/12 [00:55<00:00,  4.64s/it]

'/kaggle/working/362_train.zip'

-------
# 이미지 투명도 처리2 (score : 0.94836)

blur 함수는 각 픽셀에 커널 개수의 역수를 곱하여 모두 더합니다.

-----------


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

100%|██████████| 12/12 [01:05<00:00,  5.43s/it]

'/kaggle/working/362_train.zip'

-----
# 이미지 선명하게 하기(score : 0.94206)
대상 픽셀을 강조하는 커널을 만들고 filter2D를 사용하여 이미지에 커널을 적용합니다.

-------

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

100%|██████████| 12/12 [00:56<00:00,  4.70s/it]

'/kaggle/working/362_train.zip'

------------
# 이미지 대비 높이기1 (Score : 0.95465)
흑백화 된 이미지에 히스토그램 평활화를 하여 객체의 형태가 두드러지도록 만들어 줍니다.

----

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

100%|██████████| 12/12 [00:52<00:00,  4.39s/it]

'/kaggle/working/362_train.zip'

---------
# 이미지 대비 높이기2 (score : 0.93954)
컬러 이미지에 히스토그램 평활하를 하여 객체의 형태가 두드러지도록 만들어 줍니다.

-----

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
100%|██████████| 12/12 [00:55<00:00,  4.62s/it]

'/kaggle/working/362_train.zip'


-----
# 색상 구분 (score : 0.94458)
이미지를 HSV(색상/채도/명도)로 변환한 다음에 격리시킬 값의 범위를 정의하고 이미지에 적용할 마스크를 만듭니다.

-------

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

100%|██████████| 12/12 [00:54<00:00,  4.53s/it]

'/kaggle/working/362_train.zip'

------------
# 이미지 이진화 (score : 0.96095)
기준 값을 바탕으로 이보다 큰 픽셀은 흰색, 이보다 작은 픽셀은 검은색으로 만듭니다.

-----

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

100%|██████████| 12/12 [00:00<00:00, 771.28it/s]

'/kaggle/working/362_train.zip'

-----
# 경계선 감지 (score:0.97103)

낮은 임계값과 높은 임곗값을 이미지 중간 픽셀 강도의 1표준편차 아래 값과 위값으로 설정해 보겠습니다.

----------




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


100%|██████████| 12/12 [00:00<00:00, 802.05it/s]

'/kaggle/working/362_train.zip'


-------------------
test의 데이터도 또한 폴더안에 이미지가 저장되어 있으나, species로 분류되어 있지 않습니다.

glob로 path column을 가져와서 dataframe의 형식으로 특징을 추출할 수 있으나, glob로는 순서가 뒤엉킨다는 단점이 있습니다.

train data와 test data를 모두 glob사용하는 경우, test data는 순서를 fix하는 index reset작업을 추가로 진행 해주어야 합니다.

submission data를 이용해서 test data를 가져오는 것으로 먼저 생각했습니다.

---------

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

---------------
이미지 분류 학습에 사용할 데이터를 x_train, x_valid 로 나누어 학습을 진행하겠습니다.

------------


```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
from sklearn.model_selection import train_test_split
x_train, x_valid = train_test_split(train, test_size=0.2, random_state=42, stratify=train['species'])
```
------------
image 데이터를 처리해야 하므로, ImageDataGenerator를 이용하여 변환하여 줍니다.

----------


```python
train_generator=idg.flow_from_dataframe(x_train,x_col='path',y_col='species')
```

Found 3800 validated image filenames belonging to 12 classes.


```python
valid_generator=idg.flow_from_dataframe(x_valid, x_col='path', y_col='species')
```


Found 950 validated image filenames belonging to 12 classes.


```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.applications.efficientnet import *
from tensorflow.keras.callbacks import *
```
------
성능이 비교적 우수한 것으로 알려져있는 EfficientNetB0를 이용하여 학습에 사용합니다.

--------


```python
es=EarlyStopping(patience=4, restore_best_weights=True)
rl=ReduceLROnPlateau(patience=4, verbose=1)
model=Sequential()
model.add(EfficientNetB0(include_top=False,pooling='avg'))
model.add(Dense(12, activation='softmax'))
model.compile(optimizer='adam', metrics='acc', loss='categorical_crossentropy')
model.fit(train_generator, validation_data=valid_generator, epochs=1000, callbacks=[es,rl])
```

Downloading data from https://storage.googleapis.com/keras-applications/efficientnetb0_notop.h5

16711680/16705208 [==============================] - 0s 0us/step

16719872/16705208 [==============================] - 0s 0us/step

2022-05-22 04:12:08.954289: I tensorflow/compiler/mlir/mlir_graph_optimization_pass.cc:185] None of the MLIR Optimization Passes are enabled (registered 2)

Epoch 1/1000

2022-05-22 04:12:17.634328: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005

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

<keras.callbacks.History at 0x7f5c90156590>

---------
predict할 test값을 ImageDataGenerator를 이용하여 변환해 줍니다.

--------


```python
test_generator=idg.flow_from_dataframe(test, x_col='path', y_col=None, shuffle=False, class_mode=None)
```

Found 794 validated image filenames.


```python
result=model.predict(test_generator, verbose=1, workers=2)
```

25/25 [==============================] - 6s 210ms/step


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

-------------------
result의 값을 살펴보면, 모든 가능한 species별 일치할 확률이 나타나 있습니다.

따라서 가장 높은 값을 가져오는 argmax(1)를 이용하여 sub dataframe의 species column으로 추가할 수 있습니다.

그러나 결과에는 각 species에 해당하는 숫자로 표기되어 있습니다. 따라서 이를 species 명 (문자)로 변환하는 작업이 필요합니다.

먼저 train_generator에서 존재하는 class의 명칭 list를 가져와 class_list로 지정해 주겠습니다.

---------------


```python
sub['species']=result.argmax(1)
class_list=list(train_generator.class_indices)
class_list
```


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

---------
class list에 각 해당하는 숫자 값을 부여하고 class_dict로 지정해 주겠습니다.

-----------


```python
class_dict=dict(zip(range(12),class_list))
class_dict
```


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

--------
기존 sub dataframe의 species column값을 class_dict로 대체하면 해당하는 species 명으로 대체가 됩니다.


--------


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

-------
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

# 각 plants의 가장 두드러진 차이점은 모서리 부분 입니다. 따라서 캐니 경계선 감지 전처리가 가장 효과적이었고, 이미지를 자르게 되면 학습 효과가 세분화됩니다

# 이미지 이진화를 하게 되면 어두운 곳에서 촬영된 경우 보정하여 학습하므로 정확도를 높인다는 장점이 있습니다. 또한 이미지 대비를 높일 때 컬러보다 흑백일 경우 모양이 두드러지지 않아 더욱 세밀하게 학습 훈련할 수 있습니다.

# species간 색상 차이는 크지 않아서 선명하게 혹은 색상 구분을 극대화하는 것보다 흑백처리하여 학습하는 것이 더욱 효과가 높았습니다.

# 주어진 데이터의 두드러진 차이점을 감안하여 데이터 전처리가 필요함을 느꼈습니다.

