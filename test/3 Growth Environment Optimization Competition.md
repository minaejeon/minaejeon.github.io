# 3. Growth Environment Optimization Competition

![image](https://user-images.githubusercontent.com/69743938/172153090-98a6e77e-bdc6-4218-9bb4-f75cd490c173.png)

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


/kaggle/input/dataset/sample_submission.csv

/kaggle/input/dataset/test/meta/142.csv

/kaggle/input/dataset/test/image/173.png

/kaggle/input/dataset/train/CASE12/label.csv

/kaggle/input/dataset/train/CASE12/meta/CASE12_25.csv

/kaggle/input/dataset/train/CASE12/image/CASE12_32.png

/kaggle/input/dataset/train/CASE36/label.csv

/kaggle/input/dataset/train/CASE36/meta/CASE36_14.csv

/kaggle/input/dataset/train/CASE36/image/CASE36_06.png

/kaggle/input/dataset/train/CASE69/label.csv

/kaggle/input/dataset/train/CASE69/meta/CASE69_19.csv

/kaggle/input/dataset/train/CASE69/image/CASE69_17.png

/kaggle/input/dataset/train/CASE05/label.csv

/kaggle/input/dataset/train/CASE05/meta/CASE05_16.csv

/kaggle/input/dataset/train/CASE05/image/CASE05_14.png

/kaggle/input/dataset/train/CASE22/label.csv

/kaggle/input/dataset/train/CASE22/meta/CASE22_02.csv

/kaggle/input/dataset/train/CASE22/image/CASE22_06.jpg

/kaggle/input/dataset/train/CASE20/label.csv

/kaggle/input/dataset/train/CASE20/meta/CASE20_05.csv

...

/kaggle/input/dataset/train/CASE15/label.csv

/kaggle/input/dataset/train/CASE15/meta/CASE15_04.csv

/kaggle/input/dataset/train/CASE15/image/CASE15_01.jpg

/kaggle/input/dataset/train/CASE58/label.csv

/kaggle/input/dataset/train/CASE58/meta/CASE58_19.csv

/kaggle/input/dataset/train/CASE58/image/CASE58_04.png

/kaggle/input/dataset/train/CASE17/label.csv

/kaggle/input/dataset/train/CASE17/meta/CASE17_02.csv

/kaggle/input/dataset/train/CASE17/image/CASE17_03.jpg

/kaggle/input/dataset/train/CASE33/label.csv

/kaggle/input/dataset/train/CASE33/meta/CASE33_08.csv

/kaggle/input/dataset/train/CASE33/image/CASE33_17.png

/kaggle/input/dataset/train/CASE56/label.csv

/kaggle/input/dataset/train/CASE56/meta/CASE56_11.csv

/kaggle/input/dataset/train/CASE56/image/CASE56_22.png

----
주어진 data에는 train 폴더에 CASE별로 나누어 IMAGE가 포함되어 있습니다.
따라서 train은 file path의 규칙을 기반으로 column을 생성, dataframe 형식을 가져왔습니다.

-----

```python
import glob
train=pd.DataFrame({'path':glob.glob('/kaggle/input/dataset/train/*/image/*')})
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
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 1 columns</p>
</div>

------
label file의 경우 img_name과 leaf_weight(정답값)으로 구성된 것을 알 수 있습니다.

------

```python
label=pd.read_csv('/kaggle/input/dataset/train/CASE35/label.csv')
label
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>img_name</th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CASE35_01.png</td>
      <td>0.348</td>
    </tr>
    <tr>
      <th>1</th>
      <td>CASE35_02.png</td>
      <td>1.157</td>
    </tr>
    <tr>
      <th>2</th>
      <td>CASE35_03.png</td>
      <td>1.974</td>
    </tr>
    <tr>
      <th>3</th>
      <td>CASE35_04.png</td>
      <td>2.575</td>
    </tr>
    <tr>
      <th>4</th>
      <td>CASE35_05.png</td>
      <td>3.119</td>
    </tr>
    <tr>
      <th>5</th>
      <td>CASE35_06.png</td>
      <td>4.434</td>
    </tr>
    <tr>
      <th>6</th>
      <td>CASE35_07.png</td>
      <td>6.013</td>
    </tr>
    <tr>
      <th>7</th>
      <td>CASE35_08.png</td>
      <td>8.432</td>
    </tr>
    <tr>
      <th>8</th>
      <td>CASE35_09.png</td>
      <td>11.703</td>
    </tr>
    <tr>
      <th>9</th>
      <td>CASE35_10.png</td>
      <td>15.088</td>
    </tr>
    <tr>
      <th>10</th>
      <td>CASE35_11.png</td>
      <td>20.885</td>
    </tr>
    <tr>
      <th>11</th>
      <td>CASE35_12.png</td>
      <td>28.298</td>
    </tr>
    <tr>
      <th>12</th>
      <td>CASE35_13.png</td>
      <td>38.251</td>
    </tr>
    <tr>
      <th>13</th>
      <td>CASE35_14.png</td>
      <td>49.132</td>
    </tr>
    <tr>
      <th>14</th>
      <td>CASE35_15.png</td>
      <td>63.277</td>
    </tr>
    <tr>
      <th>15</th>
      <td>CASE35_16.png</td>
      <td>83.856</td>
    </tr>
    <tr>
      <th>16</th>
      <td>CASE35_17.png</td>
      <td>106.120</td>
    </tr>
    <tr>
      <th>17</th>
      <td>CASE35_18.png</td>
      <td>133.164</td>
    </tr>
    <tr>
      <th>18</th>
      <td>CASE35_19.png</td>
      <td>160.963</td>
    </tr>
    <tr>
      <th>19</th>
      <td>CASE35_20.png</td>
      <td>190.768</td>
    </tr>
    <tr>
      <th>20</th>
      <td>CASE35_21.png</td>
      <td>230.770</td>
    </tr>
    <tr>
      <th>21</th>
      <td>CASE35_22.png</td>
      <td>277.233</td>
    </tr>
    <tr>
      <th>22</th>
      <td>CASE35_23.png</td>
      <td>327.570</td>
    </tr>
    <tr>
      <th>23</th>
      <td>CASE35_24.png</td>
      <td>376.460</td>
    </tr>
    <tr>
      <th>24</th>
      <td>CASE35_25.png</td>
      <td>393.269</td>
    </tr>
    <tr>
      <th>25</th>
      <td>CASE35_26.png</td>
      <td>433.624</td>
    </tr>
    <tr>
      <th>26</th>
      <td>CASE35_27.png</td>
      <td>469.019</td>
    </tr>
  </tbody>
</table>
</div>

------
위에서 만들어준 train의 path를 이용하여 label 파일을 만들 수 있습니다

------


```python
label_list=[]
for path in glob.glob('/kaggle/input/dataset/train/*/label.csv'):
    label=pd.read_csv(path)
    label_list.append(label)
label_csv=pd.concat(label_list)
label_csv
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>img_name</th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CASE12_01.png</td>
      <td>0.025</td>
    </tr>
    <tr>
      <th>1</th>
      <td>CASE12_02.png</td>
      <td>0.085</td>
    </tr>
    <tr>
      <th>2</th>
      <td>CASE12_03.png</td>
      <td>0.118</td>
    </tr>
    <tr>
      <th>3</th>
      <td>CASE12_04.png</td>
      <td>0.184</td>
    </tr>
    <tr>
      <th>4</th>
      <td>CASE12_05.png</td>
      <td>0.345</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>22</th>
      <td>CASE56_23.png</td>
      <td>131.028</td>
    </tr>
    <tr>
      <th>23</th>
      <td>CASE56_24.png</td>
      <td>160.933</td>
    </tr>
    <tr>
      <th>24</th>
      <td>CASE56_25.png</td>
      <td>179.876</td>
    </tr>
    <tr>
      <th>25</th>
      <td>CASE56_26.png</td>
      <td>219.150</td>
    </tr>
    <tr>
      <th>26</th>
      <td>CASE56_27.png</td>
      <td>227.165</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 2 columns</p>
</div>

------
img_name은 file path에서 '/'기준 가장 오른쪽에 존재하므로 split하여 해당 column을 생성합니다.

----

```python
train['img_name']=train['path'].apply(lambda x : x.split('/')[-1])
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>img_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
      <td>CASE12_32.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
      <td>CASE12_20.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
      <td>CASE12_39.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
      <td>CASE12_23.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
      <td>CASE12_17.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
      <td>CASE56_24.png</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
      <td>CASE56_18.png</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
      <td>CASE56_06.png</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
      <td>CASE56_01.png</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
      <td>CASE56_07.png</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 2 columns</p>
</div>

------
train dataframe에 leaf_weight column(정답값) 포함이 필요하므로 label_csv와 merge하여 줍니다.

--------

```python
train=pd.merge(train,label_csv,how='left',on='img_name')
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>img_name</th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
      <td>CASE12_32.png</td>
      <td>40.688</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
      <td>CASE12_20.png</td>
      <td>31.108</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
      <td>CASE12_39.png</td>
      <td>43.051</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
      <td>CASE12_23.png</td>
      <td>34.620</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
      <td>CASE12_17.png</td>
      <td>20.122</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
      <td>CASE56_24.png</td>
      <td>160.933</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
      <td>CASE56_18.png</td>
      <td>53.014</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
      <td>CASE56_06.png</td>
      <td>1.472</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
      <td>CASE56_01.png</td>
      <td>0.149</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
      <td>CASE56_07.png</td>
      <td>1.894</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 3 columns</p>
</div>

------
leaf_wieght의 경우 200배 이상 차이나는 경우가 있는데, log를 취함으로써 학습의 정확성을 높일 수 있습니다.

------

```python
train['leaf_weight']=np.log(train['leaf_weight'])
train
```


/opt/conda/lib/python3.7/site-packages/pandas/core/arraylike.py:364: RuntimeWarning: divide by zero encountered in log
  result = getattr(ufunc, method)(*inputs, **kwargs)

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>img_name</th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
      <td>CASE12_32.png</td>
      <td>3.705933</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
      <td>CASE12_20.png</td>
      <td>3.437465</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
      <td>CASE12_39.png</td>
      <td>3.762385</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
      <td>CASE12_23.png</td>
      <td>3.544432</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
      <td>CASE12_17.png</td>
      <td>3.001814</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
      <td>CASE56_24.png</td>
      <td>5.080988</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
      <td>CASE56_18.png</td>
      <td>3.970556</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
      <td>CASE56_06.png</td>
      <td>0.386622</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
      <td>CASE56_01.png</td>
      <td>-1.903809</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
      <td>CASE56_07.png</td>
      <td>0.638691</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 3 columns</p>
</div>

------
case의 이름은 img_name column에서 '_'  를 기준으로 오른쪽에서 두번째 위치합니다.
split 함수를 적용하여 case column을 취할 수 있습니다.

--------

```python
train['case']=train['img_name'].apply(lambda x : x.split('_')[-2])
case=train['case'].astype(str)
case
```


0       CASE12

1       CASE12

2       CASE12

3       CASE12

4       CASE12

...  

1587    CASE56

1588    CASE56

1589    CASE56

1590    CASE56

1591    CASE56

Name: case, Length: 1592, dtype: object


```python
img_name=train['img_name'].astype(str)
img_name
```


0       CASE12_32.png

1       CASE12_20.png

2       CASE12_39.png

3       CASE12_23.png

4       CASE12_17.png

...      

1587    CASE56_24.png

1588    CASE56_18.png

1589    CASE56_06.png

1590    CASE56_01.png

1591    CASE56_07.png

Name: img_name, Length: 1592, dtype: object


```python
import albumentations as al
aug=al.Compose([al.HorizontalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(256,256)])
```

/kaggle/input/dataset/train/CASE12/image/CASE12_32.png


-------
train의 이미지를 좌우대칭 및 회전, 사이즈 축소로 변형하여 압축파일로 저장하겠습니다.

------

```python
import cv2
import shutil
from tqdm import tqdm
for category in tqdm(img_name):
    os.makedirs('256_train/'+category, exist_ok=True)
    for path in train[train['img_name']==category]['path']:
        image=cv2.imread(path)
        aug=al.Compose([al.HorizontalFlip(p=0.5),al.Rotate(limit=360,p=0.5),al.Resize(256,256)])
        aug_dict=aug(image=image)
        augmented_image=aug_dict['image'] 
        category_split=category.split('_')[-2]
        path_split=path.split('/')[-1] #path가 문자열이므로 split 적용 // 파일 이름만 나올 수 있게
        cv2.imwrite('/kaggle/input/dataset/train/'+category_split+'/image/'+path_split,augmented_image)
shutil.make_archive('256_train','zip','256_train')
```


100%|██████████| 1592/1592 [05:26<00:00,  4.88it/s]

'/kaggle/working/256_train.zip'


```python
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>img_name</th>
      <th>leaf_weight</th>
      <th>case</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
      <td>CASE12_32.png</td>
      <td>3.705933</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
      <td>CASE12_20.png</td>
      <td>3.437465</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
      <td>CASE12_39.png</td>
      <td>3.762385</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
      <td>CASE12_23.png</td>
      <td>3.544432</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
      <td>CASE12_17.png</td>
      <td>3.001814</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
      <td>CASE56_24.png</td>
      <td>5.080988</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
      <td>CASE56_18.png</td>
      <td>3.970556</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
      <td>CASE56_06.png</td>
      <td>0.386622</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
      <td>CASE56_01.png</td>
      <td>-1.903809</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
      <td>CASE56_07.png</td>
      <td>0.638691</td>
      <td>CASE56</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 4 columns</p>
</div>

---------
log값이 -인 경우 0에 가까우므로 0으로 변경하겠습니다.

--------

```python
train['leaf_weight'] = [0 if i < 0 else i for i in train['leaf_weight']]
train
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>path</th>
      <th>img_name</th>
      <th>leaf_weight</th>
      <th>case</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_32.png</td>
      <td>CASE12_32.png</td>
      <td>3.705933</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_20.png</td>
      <td>CASE12_20.png</td>
      <td>3.437465</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_39.png</td>
      <td>CASE12_39.png</td>
      <td>3.762385</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_23.png</td>
      <td>CASE12_23.png</td>
      <td>3.544432</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/train/CASE12/image/CASE12_17.png</td>
      <td>CASE12_17.png</td>
      <td>3.001814</td>
      <td>CASE12</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1587</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_24.png</td>
      <td>CASE56_24.png</td>
      <td>5.080988</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1588</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_18.png</td>
      <td>CASE56_18.png</td>
      <td>3.970556</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1589</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_06.png</td>
      <td>CASE56_06.png</td>
      <td>0.386622</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1590</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_01.png</td>
      <td>CASE56_01.png</td>
      <td>0.000000</td>
      <td>CASE56</td>
    </tr>
    <tr>
      <th>1591</th>
      <td>/kaggle/input/dataset/train/CASE56/image/CASE56_07.png</td>
      <td>CASE56_07.png</td>
      <td>0.638691</td>
      <td>CASE56</td>
    </tr>
  </tbody>
</table>
<p>1592 rows × 4 columns</p>
</div>


-------
이미지 픽셀 용량이 크기 때문에 램소모량 줄이고자 batch size 지정하여 진행할 수 있는 image_data_generator를 이용하여 train_generator를 만듭니다. 

-------


```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg=ImageDataGenerator()
```


```python
train_generator=idg.flow_from_dataframe(train,x_col='path',y_col='leaf_weight',class_mode='raw')

```


Found 1592 validated image filenames.



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
from tensorflow.keras.callbacks import *
from tensorflow.keras.applications.efficientnet import *
```
-------------
ImageNet에서 성능은 우수하나 처리 용량이 크지 않은 EfficientNetB1을 이용하여 Sequential 층을 쌓겠습니다. 또한 학습 개선이 없을 경우 중단하는 EarlyStopping과 learning rate를 조정함으로써 최적점을 찾는데 용이한 ReduceLROnPlateau를 callback함수로 이용하겠습니다.

--------------



```python
es=EarlyStopping(patience=4, restore_best_weights=True)
rl=ReduceLROnPlateau(patience=3, verbose=1)
model=Sequential()
model.add(EfficientNetB1(include_top=False,pooling='avg'))
model.add(Dense(1, activation='linear')) #회귀 input 1
model.compile(optimizer='adam', metrics='mae', loss='mse')

model.fit(train_generator,epochs=13, callbacks=[es,rl])
```

Epoch 1/13
50/50 [==============================] - 271s 5s/step - loss: 1.4170 - mae: 0.8256

Epoch 2/13
50/50 [==============================] - 268s 5s/step - loss: 0.1416 - mae: 0.2909

Epoch 3/13
50/50 [==============================] - 266s 5s/step - loss: 0.0722 - mae: 0.2087

Epoch 4/13
50/50 [==============================] - 265s 5s/step - loss: 0.0446 - mae: 0.1610

Epoch 5/13
50/50 [==============================] - 264s 5s/step - loss: 0.0365 - mae: 0.1520

Epoch 6/13
50/50 [==============================] - 264s 5s/step - loss: 0.0599 - mae: 0.1921

Epoch 7/13
50/50 [==============================] - 264s 5s/step - loss: 0.0463 - mae: 0.1687

Epoch 8/13
50/50 [==============================] - 263s 5s/step - loss: 0.0262 - mae: 0.1255

Epoch 9/13
50/50 [==============================] - 261s 5s/step - loss: 0.0204 - mae: 0.1092

Epoch 10/13
50/50 [==============================] - 264s 5s/step - loss: 0.0242 - mae: 0.1208

Epoch 11/13
50/50 [==============================] - 266s 5s/step - loss: 0.0173 - mae: 0.1012

Epoch 12/13
50/50 [==============================] - 264s 5s/step - loss: 0.0255 - mae: 0.1239

Epoch 13/13
50/50 [==============================] - 264s 5s/step - loss: 0.0328 - mae: 0.1434


<keras.callbacks.History at 0x7fa6d83d1250>

Epoch 13/1000



50/50 [==============================] - 291s 6s/step - loss: 0.0145 - mae: 0.0930



```python
test=pd.read_csv('/kaggle/input/dataset/sample_submission.csv')
test
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>img_name</th>
      <th>leaf_weight</th>
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
      <th>455</th>
      <td>456.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>456</th>
      <td>457.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>457</th>
      <td>458.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>458</th>
      <td>459.png</td>
      <td>0</td>
    </tr>
    <tr>
      <th>459</th>
      <td>460.png</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>460 rows × 2 columns</p>
</div>

---
test의 path column을 glob를 이용해 만들되 glob 과정에서 순서가 뒤엉키므로 정렬합니다.

------

```python
import glob
test=pd.DataFrame({'path':glob.glob('/kaggle/input/dataset/test/image/*')})
test
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
      <td>/kaggle/input/dataset/test/image/173.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/test/image/043.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/test/image/248.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/test/image/333.jpg</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/test/image/038.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>455</th>
      <td>/kaggle/input/dataset/test/image/428.png</td>
    </tr>
    <tr>
      <th>456</th>
      <td>/kaggle/input/dataset/test/image/217.png</td>
    </tr>
    <tr>
      <th>457</th>
      <td>/kaggle/input/dataset/test/image/418.png</td>
    </tr>
    <tr>
      <th>458</th>
      <td>/kaggle/input/dataset/test/image/452.png</td>
    </tr>
    <tr>
      <th>459</th>
      <td>/kaggle/input/dataset/test/image/306.png</td>
    </tr>
  </tbody>
</table>
<p>460 rows × 1 columns</p>
</div>


```python
test=test.sort_values('path').reset_index(drop=True) #drop : index가 column으로 만들어지지 않게
test
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
      <td>/kaggle/input/dataset/test/image/001.png</td>
    </tr>
    <tr>
      <th>1</th>
      <td>/kaggle/input/dataset/test/image/002.png</td>
    </tr>
    <tr>
      <th>2</th>
      <td>/kaggle/input/dataset/test/image/003.png</td>
    </tr>
    <tr>
      <th>3</th>
      <td>/kaggle/input/dataset/test/image/004.png</td>
    </tr>
    <tr>
      <th>4</th>
      <td>/kaggle/input/dataset/test/image/005.png</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>455</th>
      <td>/kaggle/input/dataset/test/image/456.png</td>
    </tr>
    <tr>
      <th>456</th>
      <td>/kaggle/input/dataset/test/image/457.png</td>
    </tr>
    <tr>
      <th>457</th>
      <td>/kaggle/input/dataset/test/image/458.png</td>
    </tr>
    <tr>
      <th>458</th>
      <td>/kaggle/input/dataset/test/image/459.png</td>
    </tr>
    <tr>
      <th>459</th>
      <td>/kaggle/input/dataset/test/image/460.png</td>
    </tr>
  </tbody>
</table>
<p>460 rows × 1 columns</p>
</div>



```python
from tensorflow.keras.preprocessing.image import ImageDataGenerator
idg_test=ImageDataGenerator()
```


```python
test_generator=idg_test.flow_from_dataframe(test, x_col='path', y_col=None, shuffle=False, class_mode=None)
```


Found 460 validated image filenames.


```python
result=model.predict(test_generator,verbose=1,workers=2)
```


15/15 [==============================] - 88s 5s/step

-----
정답값(leaf_weight)를 log로 학습하여 예측했으므로 다시 exponential 처리해줍니다.

----


```python
result=np.exp(result)
```


```python
result.shape
```


(460, 1)


```python
sub=pd.read_csv('/kaggle/input/dataset/sample_submission.csv')
```


```python
train.describe() # 0~481 
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1592.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>3.231351</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.824278</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.764131</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.557873</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>4.777877</td>
    </tr>
    <tr>
      <th>max</th>
      <td>6.176647</td>
    </tr>
  </tbody>
</table>
</div>


-----
result가 음수인 경우 0에 가까우므로 0으로 변환해줍니다.

------



```python
result = [0 if i < 0 else i for i in result]
result
```

[array([67.874146], dtype=float32),

 array([312.3977], dtype=float32),

 array([5.737878], dtype=float32),

 array([85.7598], dtype=float32),

 array([89.80581], dtype=float32),

 array([89.20752], dtype=float32),

 array([1.2003134], dtype=float32),

 array([85.48924], dtype=float32),

 array([1.0934514], dtype=float32),

 array([87.02903], dtype=float32),

 
...

 array([65.20689], dtype=float32),

 array([89.601395], dtype=float32),

 array([39.58943], dtype=float32),

 array([61.912693], dtype=float32),

 array([253.98407], dtype=float32)]



```python
result
```

Output exceeds the size limit. Open the full output data in a text editor

[array([67.874146], dtype=float32),

 array([312.3977], dtype=float32),

 array([5.737878], dtype=float32),

 array([85.7598], dtype=float32),

 array([89.80581], dtype=float32),

 array([89.20752], dtype=float32),

 array([1.2003134], dtype=float32),

 array([85.48924], dtype=float32),

 array([1.0934514], dtype=float32),

 array([87.02903], dtype=float32),

 array([1.0166383], dtype=float32),

 
...

 array([65.20689], dtype=float32),

 array([89.601395], dtype=float32),

 array([39.58943], dtype=float32),

 array([61.912693], dtype=float32),

 array([253.98407], dtype=float32)]

------
예측한 값을 제출 dataframe의 column에 대응하도록 넣어줍니다.

-----

```python
sub['leaf_weight']=result
```


```python
sub['leaf_weight']=sub['leaf_weight'].astype(float)
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>img_name</th>
      <th>leaf_weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001.png</td>
      <td>67.874146</td>
    </tr>
    <tr>
      <th>1</th>
      <td>002.png</td>
      <td>312.397705</td>
    </tr>
    <tr>
      <th>2</th>
      <td>003.png</td>
      <td>5.737878</td>
    </tr>
    <tr>
      <th>3</th>
      <td>004.png</td>
      <td>85.759804</td>
    </tr>
    <tr>
      <th>4</th>
      <td>005.png</td>
      <td>89.805809</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>455</th>
      <td>456.png</td>
      <td>65.206886</td>
    </tr>
    <tr>
      <th>456</th>
      <td>457.png</td>
      <td>89.601395</td>
    </tr>
    <tr>
      <th>457</th>
      <td>458.png</td>
      <td>39.589432</td>
    </tr>
    <tr>
      <th>458</th>
      <td>459.png</td>
      <td>61.912693</td>
    </tr>
    <tr>
      <th>459</th>
      <td>460.png</td>
      <td>253.984070</td>
    </tr>
  </tbody>
</table>
<p>460 rows × 2 columns</p>
</div>



```python
sub.to_csv('origin_epoch13.csv',index=False)
```
