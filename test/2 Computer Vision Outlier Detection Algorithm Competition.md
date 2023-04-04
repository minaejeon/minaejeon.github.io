# 2. Computer Vision Outlier Detection Algorithm Competition

![image](https://user-images.githubusercontent.com/69743938/172152981-c7814f6c-6e64-4ffa-9b12-5f2ae491dff9.png)


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
    for filename in filenames[:1]:
        print(os.path.join(dirname, filename))

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```

/kaggle/input/dacon-cv-data/open/sample_submission.csv

/kaggle/input/dacon-cv-data/open/test/test/21130.png

/kaggle/input/dacon-cv-data/open/train/train/14127.png

/kaggle/input/362-trainzip/bottle-broken_large/2010839.png

/kaggle/input/362-trainzip/cable-good/12743.png 

/kaggle/input/362-trainzip/zipper-rough/2013782.png

/kaggle/input/362-trainzip/bottle-broken_small/1113436.png

/kaggle/input/362-trainzip/metal_nut-color/612101.png

/kaggle/input/362-trainzip/cable-missing_wire/614192.png

/kaggle/input/362-trainzip/hazelnut-crack/612864.png

/kaggle/input/362-trainzip/pill-scratch/1311620.png

/kaggle/input/362-trainzip/zipper-squeezed_teeth/1213187.png

/kaggle/input/362-trainzip/metal_nut-scratch/210220.png

/kaggle/input/362-trainzip/capsule-faulty_imprint/1913221.png

/kaggle/input/362-trainzip/cable-combined/1911993.png

/kaggle/input/362-trainzip/cable-poke_insulation/1811438.png

/kaggle/input/362-trainzip/transistor-good/10760.png

/kaggle/input/362-trainzip/zipper-split_teeth/1112587.png

/kaggle/input/362-trainzip/transistor-misplaced/1012471.png

/kaggle/input/362-trainzip/hazelnut-cut/212809.png

/kaggle/input/362-trainzip/grid-glue/610509.png

/kaggle/input/362-trainzip/wood-scratch/614208.png

/kaggle/input/362-trainzip/tile-oil/413350.png

/kaggle/input/362-trainzip/carpet-good/12329.png

/kaggle/input/362-trainzip/screw-good/14127.png

/kaggle/input/362-trainzip/pill-pill_type/2512103.png

/kaggle/input/362-trainzip/leather-cut/1511125.png

/kaggle/input/362-trainzip/carpet-hole/1010711.png

/kaggle/input/362-trainzip/carpet-cut/2211382.png

/kaggle/input/362-trainzip/tile-good/14202.png

/kaggle/input/362-trainzip/transistor-damaged_case/012384.png

/kaggle/input/362-trainzip/grid-broken/813067.png

/kaggle/input/362-trainzip/carpet-metal_contamination/1111180.png

/kaggle/input/362-trainzip/grid-metal_contamination/012827.png

/kaggle/input/362-trainzip/tile-crack/612876.png

/kaggle/input/362-trainzip/hazelnut-print/410599.png

/kaggle/input/362-trainzip/capsule-poke/813009.png

/kaggle/input/362-trainzip/cable-cable_swap/1712853.png


/kaggle/input/362-trainzip/zipper-combined/1310802.png

/kaggle/input/362-trainzip/transistor-bent_lead/714248.png

/kaggle/input/362-trainzip/leather-good/12867.png

/kaggle/input/362-trainzip/screw-scratch_neck/1313182.png

/kaggle/input/362-trainzip/cable-bent_wire/3013211.png

/kaggle/input/362-trainzip/carpet-color/810866.png

--------------------
label column은 train data에 포함되어 있으나 test data에는 제외, submission data에는 한가지 값(오답)만 포함되어 있습니다. 

-------------------

```python
train=pd.read_csv('/kaggle/input/dacon-cv-data/open/train_df.csv')
test=pd.read_csv('/kaggle/input/dacon-cv-data/open/test_df.csv')
sub=pd.read_csv('/kaggle/input/dacon-cv-data/open/sample_submission.csv')
display(train,test,sub)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>file_name</th>
      <th>class</th>
      <th>state</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>10000.png</td>
      <td>transistor</td>
      <td>good</td>
      <td>transistor-good</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>10001.png</td>
      <td>capsule</td>
      <td>good</td>
      <td>capsule-good</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>10002.png</td>
      <td>transistor</td>
      <td>good</td>
      <td>transistor-good</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>10003.png</td>
      <td>wood</td>
      <td>good</td>
      <td>wood-good</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>10004.png</td>
      <td>bottle</td>
      <td>good</td>
      <td>bottle-good</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>4272</th>
      <td>4272</td>
      <td>14272.png</td>
      <td>transistor</td>
      <td>good</td>
      <td>transistor-good</td>
    </tr>
    <tr>
      <th>4273</th>
      <td>4273</td>
      <td>14273.png</td>
      <td>transistor</td>
      <td>good</td>
      <td>transistor-good</td>
    </tr>
    <tr>
      <th>4274</th>
      <td>4274</td>
      <td>14274.png</td>
      <td>grid</td>
      <td>good</td>
      <td>grid-good</td>
    </tr>
    <tr>
      <th>4275</th>
      <td>4275</td>
      <td>14275.png</td>
      <td>zipper</td>
      <td>good</td>
      <td>zipper-good</td>
    </tr>
    <tr>
      <th>4276</th>
      <td>4276</td>
      <td>14276.png</td>
      <td>screw</td>
      <td>good</td>
      <td>screw-good</td>
    </tr>
  </tbody>
</table>
<p>4277 rows × 5 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>file_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>20000.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>20001.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20002.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>20003.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>20004.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>22149.png</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>22150.png</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>22151.png</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>22152.png</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>22153.png</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 2 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>tile-good</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 2 columns</p>
</div>

-----------
train data에는 각 label을 포함한 데이터의 분포가 최대 391개 최소 4개로 불균형하게 이루어져있습니다.
특정 label에 대한 학습이 부족하여 예측에 부정확성을 초래할 수 있어 해결 방안이 필요했습니다.
이미지를 상하좌우 대칭하거나 회전을 통해 부족한 데이터를 늘리는 방식을 생각하게 되었습니다.

-------------

```python
train['label'].nunique()
train['label'].value_counts()
```


hazelnut-good                 391

screw-good                    320

carpet-good                   280

pill-good                     267

grid-good                     264

... 


transistor-bent_lead            5

transistor-damaged_case         5

cable-cut_outer_insulation      5

wood-liquid                     5

wood-color                      4

Name: label, Length: 88, dtype: int64


```python
train['state'].nunique()
```


49

--------
이미지의 크기가 클 경우 처리에 시간이 많이 소요되어 줄이는 작업이 필요합니다.
원본 image size를 조회하였을 때, 1024x1024로 큰 값이 나왔고 이를 줄여서 학습하겠습니다.

--------
```python
from PIL import Image
Image.open('/kaggle/input/dacon-cv-data/open/train/train/14127.png').size
```


(1024, 1024)

------
albumentation 라이브러리를 이용하여 상하좌우 대칭 및 회전, 사이즈 변경을 진행할 수 있습니다.
이 때, size는 362x362로 줄이는 것을 채택하였습니다.

--------

```python
import albumentations as al
aug=al.Compose([al.HorizontalFlip(p=0.5),al.VerticalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(362,362)])
```


```python
import cv2
image=cv2.imread('/kaggle/input/dacon-cv-data/open/train/train/14127.png')
image.shape
```

(1024, 1024, 3)

----------
albumentation이 진행되자 1024x1024 size의 image가 362x362 size로 변경된 것을 알 수 있습니다.

----------

```python
aug_dict=aug(image=image)
augmented_image=aug_dict['image']
augmented_image.shape
```


(362, 362, 3)

```python
cv2.imwrite('sample.png',augmented_image)
```


True


```python
Image.open('./sample.png')
```

<img src="data:image/png;base64,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"/>

------
주어진 data의 file path를 보면 file name 앞에 label을 포함하고 있는 것을 알 수 있습니다.
이를 분류에 활용하고자 합니다. 먼저, train의 path를 column값으로 만들겠습니다.

------
```python
train['path']='../input/dacon-cv-data/open/train/train/'+train['file_name']
train['path']
```

0       ../input/dacon-cv-data/open/train/train/10000.png

1       ../input/dacon-cv-data/open/train/train/10001.png

2       ../input/dacon-cv-data/open/train/train/10002.png

3       ../input/dacon-cv-data/open/train/train/10003.png

4       ../input/dacon-cv-data/open/train/train/10004.png

...

4272    ../input/dacon-cv-data/open/train/train/14272.png

4273    ../input/dacon-cv-data/open/train/train/14273.png

4274    ../input/dacon-cv-data/open/train/train/14274.png

4275    ../input/dacon-cv-data/open/train/train/14275.png

4276    ../input/dacon-cv-data/open/train/train/14276.png

Name: path, Length: 4277, dtype: object



```python
test['path']='../input/dacon-cv-data/open/test/test/'+test['file_name']
test['path']
```

0       ../input/dacon-cv-data/open/test/test/20000.png

1       ../input/dacon-cv-data/open/test/test/20001.png

2       ../input/dacon-cv-data/open/test/test/20002.png

3       ../input/dacon-cv-data/open/test/test/20003.png

4       ../input/dacon-cv-data/open/test/test/20004.png

...                   

2149    ../input/dacon-cv-data/open/test/test/22149.png

2150    ../input/dacon-cv-data/open/test/test/22150.png

2151    ../input/dacon-cv-data/open/test/test/22151.png

2152    ../input/dacon-cv-data/open/test/test/22152.png

2153    ../input/dacon-cv-data/open/test/test/22153.png

Name: path, Length: 2154, dtype: object


--------
train data의 각 label은 4개 ~ 391개의 데이터를 갖고 있습니다.
데이터 갯수로 구간을 나누어 image 증식을 진행하면 각 label의 데이터 갯수를 비슷한 수준으로 맞출 수 있습니다.
데이터의 갯수가 7개 이하, 8개 이상 11개 이하, 12개 이상 15개 이하, 15개 초과로 총 4가지 그룹으로 나누었습니다.

-------

```python
outlier1=train['label'].value_counts()[train['label'].value_counts()<=7]
outlier1
```


cable-cut_inner_insulation    7

cable-bent_wire               7

grid-metal_contamination      6

grid-thread                   6

grid-broken                   6

cable-combined                6

wood-combined                 6

cable-missing_cable           6

grid-bent                     6

cable-cable_swap              6

grid-glue                     6

cable-poke_insulation         5

transistor-cut_lead           5

wood-hole                     5

cable-missing_wire            5

pill-pill_type                5

transistor-misplaced          5

transistor-bent_lead          5

transistor-damaged_case       5

cable-cut_outer_insulation    5

wood-liquid                   5

wood-color                    4

Name: label, dtype: int64


```python
outlier2=train['label'].value_counts()[(train['label'].value_counts()<=11) & (train['label'].value_counts()>=8)]
outlier2.index
```


Index(['pill-contamination', 'bottle-broken_small', 'bottle-contamination',

'capsule-poke', 'metal_nut-color', 'capsule-faulty_imprint',

'wood-scratch', 'leather-color', 'leather-glue', 'leather-cut',

'bottle-broken_large', 'pill-faulty_imprint', 'carpet-color',

'zipper-broken_teeth', 'capsule-squeeze', 'carpet-thread', 'carpet-cut',

'leather-poke', 'tile-crack', 'pill-combined', 'hazelnut-hole',

'hazelnut-print', 'tile-oil', 'hazelnut-cut',

'carpet-metal_contamination', 'leather-fold', 'zipper-fabric_border',

'hazelnut-crack', 'zipper-split_teeth', 'zipper-rough', 'carpet-hole',

'tile-glue_strip', 'tile-rough', 'tile-gray_stroke', 'zipper-combined',

'zipper-squeezed_teeth', 'zipper-fabric_interior'],

dtype='object')


```python
outlier3=train['label'].value_counts()[(train['label'].value_counts()<=15) & (train['label'].value_counts()>=12)]
outlier3.index
```


Index(['toothbrush-defective', 'pill-color', 'screw-scratch_neck',

'metal_nut-bent', 'pill-crack', 'screw-manipulated_front',

'capsule-scratch', 'metal_nut-flip', 'capsule-crack',

'screw-thread_top', 'metal_nut-scratch', 'screw-scratch_head',

'screw-thread_side', 'pill-scratch'],

dtype='object')




```python
good=train['label'].value_counts()[train['label'].value_counts()>15]
good.index
```

Index(['hazelnut-good', 'screw-good', 'carpet-good', 'pill-good', 'grid-good',

'wood-good', 'leather-good', 'zipper-good', 'tile-good', 'cable-good',

'metal_nut-good', 'capsule-good', 'transistor-good', 'bottle-good',

'toothbrush-good'],

dtype='object')


```python
outlier1.index
```


Index(['cable-cut_inner_insulation', 'cable-bent_wire',

'grid-metal_contamination', 'grid-thread', 'grid-broken',

'cable-combined', 'wood-combined', 'cable-missing_cable', 'grid-bent',

'cable-cable_swap', 'grid-glue', 'cable-poke_insulation',

'transistor-cut_lead', 'wood-hole', 'cable-missing_wire',

'pill-pill_type', 'transistor-misplaced', 'transistor-bent_lead',

'transistor-damaged_case', 'cable-cut_outer_insulation', 'wood-liquid',

'wood-color'],

dtype='object')

----------
먼저 데이터의 갯수가 7개 이하인 label의 경우 각 이미지를 변형을 통해 35배 (140개~245개)로 증식하겠습니다.
변형한 데이터는 압축하여 저장해두고, 코드 실험을 진행할 때 저장된 값으로 소요시간을 줄일 수 있습니다.
상하좌우 대칭, 회전, 362x362로 size 축소를 진행하였고, file path는 초기 data가 주어질 때처럼 label이 file name 안에 들어갈 수 있도록 지정했습니다.

----------

```python
import shutil
from tqdm import tqdm

for category in tqdm(outlier1.index):
    os.makedirs('362_train/'+category, exist_ok=True)
    for i in range(35): #각 class에 해당하는 path
        for path in train[train['label']==category]['path']:
            image=cv2.imread(path)
            aug=al.Compose([al.HorizontalFlip(p=0.5),al.VerticalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(362,362)]) # for 문 밖에서도 가능
            aug_dict=aug(image=image)
            augmented_image=aug_dict['image']
            path_split=path.split('/')[-1]
            cv2.imwrite('362_train/'+category+'/'+str(i)+path_split,augmented_image) #cv2.imwrite('362_train/'+category+'/'+path_split) 
shutil.make_archive('362_train','zip','362_train')

            
```


100%|██████████| 22/22 [03:35<00:00,  9.79s/it]

'/kaggle/working/362_train.zip'

----
마찬가지로 데이터의 갯수가 8개 이상 11개 이하일 경우 25배 증식 (200개~275개), 12개 이상 15개 이하일 경우 15배 증식(180개~225개), 15개 초과일 경우 증식없이 사이즈 축소만 진행하겠습니다. 

-----

```python
for category in tqdm(outlier2.index):
    os.makedirs('362_train/'+category, exist_ok=True)
    for i in range(25): 
        for path in train[train['label']==category]['path']:
            image=cv2.imread(path)
            aug=al.Compose([al.HorizontalFlip(p=0.5),al.VerticalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(362,362)])
            aug_dict=aug(image=image)
            augmented_image=aug_dict['image'] 
            path_split=path.split('/')[-1] 
            cv2.imwrite('362_train/'+category+'/'+str(i)+path_split,augmented_image) #cv2.imwrite('362_train/'+category+'/'+path_split)
shutil.make_archive('362_train','zip','362_train')

for category in tqdm(outlier3.index):
    os.makedirs('362_train/'+category, exist_ok=True)
    for i in range(15):
        for path in train[train['label']==category]['path']:
            image=cv2.imread(path)
            aug=al.Compose([al.HorizontalFlip(p=0.5),al.VerticalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(362,362)])
            aug_dict=aug(image=image)
            augmented_image=aug_dict['image'] 
            path_split=path.split('/')[-1] 
            cv2.imwrite('362_train/'+category+'/'+str(i)+path_split,augmented_image) #cv2.imwrite('362_train/'+category+'/'+path_split)
shutil.make_archive('362_train','zip','362_train')

for category in tqdm(good.index):
    os.makedirs('362_train/'+category, exist_ok=True)
    for path in train[train['label']==category]['path']:
        image=cv2.imread(path)
        image=cv2.resize(image,(362,362))
        path_split=path.split('/')[-1] 
        cv2.imwrite('362_train/'+category+'/'+path_split,image)
shutil.make_archive('362_train','zip','362_train')
```


100%|██████████| 37/37 [06:23<00:00, 10.36s/it]
100%|██████████| 14/14 [01:35<00:00,  6.80s/it]
100%|██████████| 15/15 [02:45<00:00, 11.02s/it]

-------
마찬가지로 test file의 경우 아직 label을 알 수 없으므로 증식없이 362x362 size로 사이즈 축소만 진행하겠습니다.

------

```python
os.makedirs('362_test/', exist_ok=True)
for path in tqdm(test['path']):
    image=cv2.imread(path)
    image=cv2.resize(image,(362,362))
    path_split=path.split('/')[-1] #path가 문자열이므로 split 적용 // 파일 이름만 나올 수 있게
    cv2.imwrite('362_test/'+path_split,image)
shutil.make_archive('362_test','zip','362_test')
```

100%|██████████| 2154/2154 [01:32<00:00, 23.32it/s]

'/kaggle/working/362_test.zip'



----
위에 압축 파일을 notebook의 input data로 넣어준 후 , glob를 이용하여 바뀐 path를 적용합니다.

---

```python
import glob
train=pd.DataFrame({'path':glob.glob('/kaggle/input/362-trainzip/*/*')})
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
      <td>/kaggle/input/362-trainzip/bottle-broken_large/2010839.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/362-trainzip/bottle-broken_large/610912.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/362-trainzip/bottle-broken_large/2413456.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/362-trainzip/bottle-broken_large/312006.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/362-trainzip/bottle-broken_large/613456.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>19294</th>
      <td>/kaggle/input/362-trainzip/pill-contamination/1012806.png</td>
    </tr>
    <tr>
      <th>19295</th>
      <td>/kaggle/input/362-trainzip/pill-contamination/113553.png</td>
    </tr>
    <tr>
      <th>19296</th>
      <td>/kaggle/input/362-trainzip/pill-contamination/2111251.png</td>
    </tr>
    <tr>
      <th>19297</th>
      <td>/kaggle/input/362-trainzip/pill-contamination/213553.png</td>
    </tr>
    <tr>
      <th>19298</th>
      <td>/kaggle/input/362-trainzip/pill-contamination/1410764.png</td>
    </tr>
  </tbody>
</table>
<p>19299 rows × 1 columns</p>
</div>

------
file name 직전 폴더에 label이 표기되어 있으므로 path에서 '/'을 기준으로 오른쪽에서 두번째 값을 label column 값으로 지정해줍니다.
이후 데이터 갯수의 balance를 맞추기 위해 증식된 데이터 갯수를 볼 수 있습니다. 이전에 비해 데이터가 부족한 label의 데이터 갯수가 증가한 것을 확인할 수 있습니다.

------

```python
train['label']=train['path'].apply(lambda x : x.split('/')[-2])
train['label'].value_counts() # 증식 된 데이터 나타남, f1점수 평가 (데이터가 많이 없는 class를 학습 필요)
```

screw-good                 320

carpet-good                280

wood-scratch               275

capsule-poke               275

... 

transistor-bent_lead       175

transistor-damaged_case    175

transistor-cut_lead        175

wood-color                 140

toothbrush-good             60

Name: label, Length: 88, dtype: int64



-----
train 데이터를 train 및 valid로 나누어 학습하기 위해 train_test_split을 이용합니다.

-----

```python
from sklearn.model_selection import train_test_split
x_train, x_valid = train_test_split(train,test_size=0.2,random_state=42,stratify=train['label'])
```
----
이미지 픽셀 용량이 크기 때문에 램소모량 줄이고자 batch size 지정하여 진행할 수 있는 image_data_generator를 이용하여 train_generator와 valid_generator를 만듭니다.

-----

```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()

train_generator=idg.flow_from_dataframe(x_train,x_col='path',y_col='label',target_size=(362,362),batch_size=16)#batch_size 지정하지 않을 경우 램 소모량 크게 증가
```


Found 15439 validated image filenames belonging to 88 classes.


```python
valid_generator=idg.flow_from_dataframe(x_valid,x_col='path',y_col='label',target_size=(362,362),batch_size=16)
```


Found 3860 validated image filenames belonging to 88 classes.

--------
test data의 겨우 train data처럼 glob를 이용하지 않는데, 이는 순서가 뒤섞이면서 id matching이 안되는 문제가 발생할 수 있기 때문입니다.

------

```python
test=pd.read_csv('/kaggle/input/dacon-cv-data/open/test_df.csv')
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>file_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>20000.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>20001.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20002.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>20003.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>20004.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>22149.png</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>22150.png</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>22151.png</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>22152.png</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>22153.png</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 2 columns</p>
</div>





```python
test['path']='../input/362-test/'+test['file_name']
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>file_name</th>
      <th>path</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>20000.png</td>
      <td>../input/362-test/20000.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>20001.png</td>
      <td>../input/362-test/20001.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20002.png</td>
      <td>../input/362-test/20002.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>20003.png</td>
      <td>../input/362-test/20003.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>20004.png</td>
      <td>../input/362-test/20004.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>22149.png</td>
      <td>../input/362-test/22149.png</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>22150.png</td>
      <td>../input/362-test/22150.png</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>22151.png</td>
      <td>../input/362-test/22151.png</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>22152.png</td>
      <td>../input/362-test/22152.png</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>22153.png</td>
      <td>../input/362-test/22153.png</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 3 columns</p>
</div>



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
from tensorflow.keras.applications.efficientnet import * #성능이 가장 좋은 pretrain 모델 이용
from tensorflow.keras.optimizers import * 
```

-------
ImageNet에서 성능은 우수하나 처리 용량이 크지 않은 EfficientNetB1을 이용하여 Sequential 층을 쌓겠습니다.
또한 학습 개선이 없을 경우 중단하는 EarlyStopping과 learning rate를 조정함으로써 최적점을 찾는데 용이한 ReduceLROnPlateau를 callback함수로 이용하겠습니다.

-------


```python
es=EarlyStopping(patience=4,restore_best_weights=True)
rl=ReduceLROnPlateau(patience=4,verbose=1)
model=Sequential()
model.add(EfficientNetB1(include_top=False,pooling='avg')) #출력층 top을 가져오면 안됨 다른 곳에서 1000개 넘게 학습한 것 가져오면 비효율적 // pooling 이미지 분류시 층을 따로 쌓아주지 않고 global avg 바로 넣기
model.add(Dense(88,activation='softmax')) #softmax : 확률값으로 변경
#lr=learningrate
model.compile(optimizer=Adam(lr=0.0001), metrics='acc', loss='categorical_crossentropy') #sparse하지 않는 이유 : train_generator를 사용할 때 분류문제인 것을 인식하여 미리 setting, sparse적는 경우 오류
model.fit(train_generator,validation_data=valid_generator,epochs=1000,callbacks=[rl,es])
```

Epoch 1/1000

2022-06-06 13:15:52.661427: W tensorflow/core/framework/cpu_allocator_impl.cc:80] Allocation of 25160448 exceeds 10% of free system memory.

2022-06-06 13:15:52.975790: W tensorflow/core/framework/cpu_allocator_impl.cc:80] Allocation of 25160448 exceeds 10% of free system memory.

2022-06-06 13:15:53.553874: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005

  2/965 [..............................] - ETA: 6:48 - loss: 4.5513 - acc: 0.0000e+00   2022-06-06 13:16:00.830182: W tensorflow/core/framework/cpu_allocator_impl.cc:80] Allocation of 25160448 exceeds 10% of free system memory.

  3/965 [..............................] - ETA: 6:52 - loss: 4.5592 - acc: 0.0000e+002022-06-06 13:16:01.238892: W tensorflow/core/framework/cpu_allocator_impl.cc:80] Allocation of 25160448 exceeds 10% of free system memory.

965/965 [==============================] - ETA: 0s - loss: 1.3265 - acc: 0.6274



```python
test_generator=idg.flow_from_dataframe(test,x_col='path',y_col=None,target_size=(362,362),batch_size=16,shuffle=False,class_mode=None)

```


Found 2154 validated image filenames.

-----------
학습한 내용을 바탕으로 test_generator로 label column 값을 예측하여 제출 data에 적용하겠습니다.

----------

```python
result=model.predict(test_generator,verbose=1,workers=2) 
```

135/135 [==============================] - 17s 111ms/step


```python
sub=pd.read_csv('/kaggle/input/dacon-cv-data/open/sample_submission.csv')
sub['label']=result.argmax(1)
```


```python
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>62</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>70</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>64</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>63</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>64</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>55</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>12</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 2 columns</p>
</div>

-------
label 값이 숫자로 표기되어 있으나, 이에 대응하는 label name(문자)로 변환하겠습니다.

-----

```python
class_list=list(train_generator.class_indices)
class_list
```

Output exceeds the size limit. Open the full output data in a text editor

['bottle-broken_large',

 'bottle-broken_small',

 'bottle-contamination',

 'bottle-good',

 'cable-bent_wire',

 'cable-cable_swap',

 'cable-combined',

 'cable-cut_inner_insulation',

 'cable-cut_outer_insulation',

 'cable-good',

 'cable-missing_cable',

 'cable-missing_wire',

 'cable-poke_insulation',

 'capsule-crack',

 'capsule-faulty_imprint',

 'capsule-good',

 'capsule-poke',

 'capsule-scratch',

 'capsule-squeeze',

 'carpet-color',

 'carpet-cut',

 'carpet-good',

 'carpet-hole',

 'carpet-metal_contamination',

 'carpet-thread',

...

 'zipper-fabric_interior',

 'zipper-good',

 'zipper-rough',

 'zipper-split_teeth',

 'zipper-squeezed_teeth']



```python
class_dict=dict(zip(range(88),class_list))
class_dict
```

{0: 'bottle-broken_large',

 1: 'bottle-broken_small',

 2: 'bottle-contamination',

 3: 'bottle-good',

 4: 'cable-bent_wire',

 5: 'cable-cable_swap',

 6: 'cable-combined',

 7: 'cable-cut_inner_insulation',

 8: 'cable-cut_outer_insulation',

 9: 'cable-good',

 10: 'cable-missing_cable',

 11: 'cable-missing_wire',

 12: 'cable-poke_insulation',

 13: 'capsule-crack',

 14: 'capsule-faulty_imprint',

 15: 'capsule-good',

 16: 'capsule-poke',

 17: 'capsule-scratch',

 18: 'capsule-squeeze',

 19: 'carpet-color',

 20: 'carpet-cut',

 21: 'carpet-good',

 22: 'carpet-hole',

 23: 'carpet-metal_contamination',

 24: 'carpet-thread',

...

 83: 'zipper-fabric_interior',

 84: 'zipper-good',

 85: 'zipper-rough',

 86: 'zipper-split_teeth',

 87: 'zipper-squeezed_teeth'}

-------
label column의 값이 이름으로 표기된 것을 확인할 수 있습니다.

------


```python
sub['label']=sub['label'].replace(class_dict)
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>index</th>
      <th>label</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>tile-glue_strip</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>grid-good</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>transistor-cut_lead</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>tile-gray_stroke</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>tile-good</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2149</th>
      <td>2149</td>
      <td>tile-gray_stroke</td>
    </tr>
    <tr>
      <th>2150</th>
      <td>2150</td>
      <td>screw-good</td>
    </tr>
    <tr>
      <th>2151</th>
      <td>2151</td>
      <td>grid-good</td>
    </tr>
    <tr>
      <th>2152</th>
      <td>2152</td>
      <td>cable-poke_insulation</td>
    </tr>
    <tr>
      <th>2153</th>
      <td>2153</td>
      <td>zipper-good</td>
    </tr>
  </tbody>
</table>
<p>2154 rows × 2 columns</p>
</div>



```python
sub.to_csv('submission.csv',index=False)
```
