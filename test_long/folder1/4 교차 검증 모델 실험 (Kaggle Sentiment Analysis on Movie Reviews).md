
# 6 교차 검증 모델 실험 (Kaggle Sentiment Analysis on Movie Reviews)



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
/kaggle/input/fasttext-crawl-300d-2m/crawl-300d-2M.vec
/kaggle/input/sentiment-analysis-on-movie-reviews/sampleSubmission.csv
/kaggle/input/sentiment-analysis-on-movie-reviews/train.tsv.zip
/kaggle/input/sentiment-analysis-on-movie-reviews/test.tsv.zip
</pre>

```python
train=pd.read_table('/kaggle/input/sentiment-analysis-on-movie-reviews/train.tsv.zip')
test=pd.read_table('/kaggle/input/sentiment-analysis-on-movie-reviews/test.tsv.zip')
sub=pd.read_csv('/kaggle/input/sentiment-analysis-on-movie-reviews/sampleSubmission.csv')
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PhraseId</th>
      <th>SentenceId</th>
      <th>Phrase</th>
      <th>Sentiment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>A series of escapades demonstrating the adage ...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>A series of escapades demonstrating the adage ...</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>A series</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>A</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1</td>
      <td>series</td>
      <td>2</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>156055</th>
      <td>156056</td>
      <td>8544</td>
      <td>Hearst 's</td>
      <td>2</td>
    </tr>
    <tr>
      <th>156056</th>
      <td>156057</td>
      <td>8544</td>
      <td>forced avuncular chortles</td>
      <td>1</td>
    </tr>
    <tr>
      <th>156057</th>
      <td>156058</td>
      <td>8544</td>
      <td>avuncular chortles</td>
      <td>3</td>
    </tr>
    <tr>
      <th>156058</th>
      <td>156059</td>
      <td>8544</td>
      <td>avuncular</td>
      <td>2</td>
    </tr>
    <tr>
      <th>156059</th>
      <td>156060</td>
      <td>8544</td>
      <td>chortles</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
<p>156060 rows × 4 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>PhraseId</th>
      <th>SentenceId</th>
      <th>Phrase</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>156061</td>
      <td>8545</td>
      <td>An intermittently pleasing but mostly routine ...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>156062</td>
      <td>8545</td>
      <td>An intermittently pleasing but mostly routine ...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>156063</td>
      <td>8545</td>
      <td>An</td>
    </tr>
    <tr>
      <th>3</th>
      <td>156064</td>
      <td>8545</td>
      <td>intermittently pleasing but mostly routine effort</td>
    </tr>
    <tr>
      <th>4</th>
      <td>156065</td>
      <td>8545</td>
      <td>intermittently pleasing but mostly routine</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>66287</th>
      <td>222348</td>
      <td>11855</td>
      <td>A long-winded , predictable scenario .</td>
    </tr>
    <tr>
      <th>66288</th>
      <td>222349</td>
      <td>11855</td>
      <td>A long-winded , predictable scenario</td>
    </tr>
    <tr>
      <th>66289</th>
      <td>222350</td>
      <td>11855</td>
      <td>A long-winded ,</td>
    </tr>
    <tr>
      <th>66290</th>
      <td>222351</td>
      <td>11855</td>
      <td>A long-winded</td>
    </tr>
    <tr>
      <th>66291</th>
      <td>222352</td>
      <td>11855</td>
      <td>predictable scenario</td>
    </tr>
  </tbody>
</table>
<p>66292 rows × 3 columns</p>
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
      <th>PhraseId</th>
      <th>SentenceId</th>
      <th>Phrase</th>
      <th>Sentiment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>1</td>
      <td>A series of escapades demonstrating the adage ...</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>A series of escapades demonstrating the adage ...</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>1</td>
      <td>A series</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>1</td>
      <td>A</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>1</td>
      <td>series</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>66287</th>
      <td>222348</td>
      <td>11855</td>
      <td>A long-winded , predictable scenario .</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>66288</th>
      <td>222349</td>
      <td>11855</td>
      <td>A long-winded , predictable scenario</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>66289</th>
      <td>222350</td>
      <td>11855</td>
      <td>A long-winded ,</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>66290</th>
      <td>222351</td>
      <td>11855</td>
      <td>A long-winded</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>66291</th>
      <td>222352</td>
      <td>11855</td>
      <td>predictable scenario</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>222352 rows × 4 columns</p>
</div>



```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
TK.fit_on_texts(alldata['Phrase'])
TK.word_index
```

<pre>
{'the': 1,
 'a': 2,
 'of': 3,
 'and': 4,
 'to': 5,
 "'s": 6,
 'in': 7,
 'is': 8,
 'that': 9,
 'it': 10,
 'as': 11,
 [286, 88],
 [286],
 [719, 5, 1078],
 ...]
</pre>

```python
pd.Series(text)
```

<pre>
0         [2, 315, 3, 16573, 7660, 1, 8313, 9, 53, 8, 47...
1         [2, 315, 3, 16573, 7660, 1, 8313, 9, 53, 8, 47...
2                                                  [2, 315]
3                                                       [2]
4                                                     [315]
                                ...                        
222347                            [2, 118, 4456, 343, 1623]
222348                            [2, 118, 4456, 343, 1623]
222349                                       [2, 118, 4456]
222350                                       [2, 118, 4456]
222351                                          [343, 1623]
Length: 222352, dtype: object
</pre>

```python
pd.Series(text).apply(len).max
```

<pre>
<bound method NDFrame._add_numeric_operations.<locals>.max of 0         35
1         14
2          2
3          1
4          1
          ..
222347     5
222348     5
222349     3
222350     3
222351     2
Length: 222352, dtype: int64>
</pre>

```python
import seaborn as sns
import matplotlib.pyplot as plt
plt.figure(figsize=(16,8))
sns.displot(pd.Series(text).apply(len))
plt.xlim(0,30)
```

<pre>
(0.0, 30.0)
</pre>
<pre>
<Figure size 1152x576 with 0 Axes>
</pre>
<img src="data:image/png;base64,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"/>


```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(text,maxlen=30)
pad_text
```

<pre>
array([[   1, 8313,    9, ...,    3,    2,   42],
       [   0,    0,    0, ...,   13,    1, 3940],
       [   0,    0,    0, ...,    0,    2,  315],
       ...,
       [   0,    0,    0, ...,    2,  118, 4456],
       [   0,    0,    0, ...,    2,  118, 4456],
       [   0,    0,    0, ...,    0,  343, 1623]], dtype=int32)
</pre>

```python
train2=pad_text[:len(train)]
test2=pad_text[len(train):]
```


```python
from sklearn.model_selection import train_test_split
x_train, x_valid, y_train, y_valid = train_test_split(train2,train['Sentiment'],test_size=0.2,random_state=42,stratify=train['Sentiment'])
```

*pretrained embedding



방대한 양의 데이터로 미리 학습 된 것을 이용하여 다른 데이터의 embedding에 적용하는 것을 의미합니다.



facebook에서 제공하는 300차원의 vector를 이용하여 pretrain 하기 위해 먼저 load하여 embedding 값으로 넣어줍니다.



embeddings의 값을 {}로 먼저 비워 준 뒤, 각 line의 value 값을 학습할 예정입니다.



해당 데이터를 보면 line 마지막에 여백이 많이 있어, rstrip().split()처리하여 줍니다.




```python
def load_embedding(filepath):
    embeddings = {}
    with open(filepath) as f:
        for line in f:
            values=line.rstrip().split()
            word=values[0]
            vector=np.asarray(values[1:],dtype=np.float32)
            embeddings[word]=vector
    return embeddings
embeddings=load_embedding('../input/fasttext-crawl-300d-2m/crawl-300d-2M.vec')
embeddings
```

<pre>
{'2000000': array([ 2.0600e-02,  1.9530e-01, -9.0400e-02, -3.5390e-01, -6.2700e-02,
        -1.4600e-02, -1.3150e-01,  5.8600e-02,  5.9930e-01,  6.3100e-02,
        -9.3200e-02,  7.1720e-01, -3.4950e-01, -6.1100e-02, -3.0790e-01,
        ...
                1.681e-01, -4.000e-04,  2.214e-01,  1.369e-01,  1.029e-01,
         1.317e-01,  6.520e-02, -1.035e-01,  1.597e-01,  9.220e-02,
         4.165e-01,  9.100e-02, -3.026e-01,  3.280e-02, -2.860e-02,
         1.461e-01, -2.332e-01,  2.790e-02,  1.100e-03, -9.940e-02],
       dtype=float32),
 ...}
</pre>

```python
np.zeros([4,3])
```

<pre>
array([[0., 0., 0.],
       [0., 0., 0.],
       [0., 0., 0.],
       [0., 0., 0.]])
</pre>

```python
TK.word_index.items()
```

dict_items([('the', 1), ('a', 2), ('of', 3), ('and', 4), ('to', 5), ("'s", 6), ('in', 7), ('is', 8), ('that', 9), ('it', 10), ('as', 11), ('with', 12), ('for', 13), ('its', 14), ('film', 15), ('an', 16), ('movie', 17), ('this', 18), ('but', 19), ('be', 20), ('on', 21), ('you', 22), ('by', 23), ("n't", 24), ('more', 25), ('his', 26), ('not', 27), ('one', 28), ('than', 29), ('about', 30), ('at', 31), ('from', 32), ('or', 33), ('all', 34), ('like', 35), ('are', 36), ('have', 37), ('has', 38), ('so', 39), ("'", 40), ('out', 41), ('story', 42), ('who', 43), ('rrb', 44), ('up', 45), ('too', 46), ('good', 47), ('most', 48), ('into', 49), ('lrb', 50), ('time', 51), ('much', 52), ('what', 53), ('if', 54), ('characters', 55), ('no', 56), ('comedy', 57), ('their', 58), ('just', 59), ('i', 60), ('some', 61), ('can', 62), ('even', 63), ('life', 64), ('your', 65), ('little', 66), ('does', 67), ("''", 68),...('harmlessly', 17778), ('christophe', 17779), ('deriding', 17780)])


분석 대상 데이터의 word는Tokenizer를 이용하여 빈도순으로 숫자가 부여되었습니다.



pretrained embedding 중에서도 분석 대상 데이터의 word만 추출해 줍니다.



```python
def filter_embedding(embeddings, word_index, vocab_size, dim=300):
    embedding_matrix=np.zeros([vocab_size,dim])
    for word, i in word_index.items():
        vector=embeddings.get(word)
        if vector is not None:
            embedding_matrix[i]=vector
    return embedding_matrix
embedding_matrix=filter_embedding(embeddings, TK.word_index, len(TK.word_index)+1, 300)
embedding_matrix.shape
```

<pre>
(17781, 300)
</pre>

```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
```

[KFold]



학습 데이터를 분할하고 홀드아웃 검증 절차를 여러 번 반복함으로써 매회 검증 학습에 이용할 데이터의 양을 유지하면서도 검증 평가에 필요한 데이터를 학습 데이터 전체로 할 수 있습니다.



교차 검증의 폴드 수는 n_splits 인수로 지정합니다. 폴드 수를 늘릴수록 학습 데이터의 양을 더 확보할 수 있으므로 데이터 전체로 학습시켰을 때와 유사한 모델 성능으로 평가할 수 있습니다.



한편 연산 시간이 늘어나므로 트레이드 오프가 됩니다.



연산 시간과 학습 데이터의 비율, 검증 점수의 관계를 살펴보고 폴드 수를 바꾸는 것이 필요합니다.



모델의 일반화 성능을 평가할 때는 보통 각 폴드의 점수를 평균내지만, 각 폴드의 목적변수와 예측값을 모아 데이터 전체로 연산하는 방법도 있습니다.



train2는 numpy의 array형식 / train은 pandas의 Series 형식이기 때문에 'iloc' 데이터에 접근하는 함수 사용 필요.



model=Sequential()선언을 for문에 넣고 초기화 합니다. (이전 split에서 저장된 값이 영향을 줄 수 있기 때문)



model embedding 층의 trainable의 default값은 True이나 이미 pretrained embedding으로 가중치를 가져 왔으므로 과대적합이 발생합니다. 따라서 False 처리하였습니다.



result 값은 총 5번의 split에 해당하는 값이므로 모두 저장하여 횟수(5)로 나누어 줌으로써 확률값을 저장합니다.



```python
from sklearn.model_selection import KFold
kf=KFold(n_splits=5, shuffle=True, random_state=26)
result=0
for train_index, valid_index in kf.split(train2):
    x_train = train2[train_index]
    x_valid = train2[valid_index]
    y_train = train['Sentiment'].iloc[train_index]
    y_valid = train['Sentiment'].iloc[valid_index]
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
    model.add(LSTM(32))
    model.add(Dense(5, activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
    result+=model.predict(test2)/5
```

</pre>
<pre>
Epoch 1/10
</pre>
<pre>
2022-04-07 13:10:37.733123: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005
</pre>
<pre>
976/976 [==============================] - 12s 8ms/step - loss: 0.9415 - acc: 0.6123 - val_loss: 0.8859 - val_acc: 0.6321
Epoch 2/10
976/976 [==============================] - 6s 7ms/step - loss: 0.8511 - acc: 0.6454 - val_loss: 0.8530 - val_acc: 0.6434
Epoch 3/10
976/976 [==============================] - 7s 7ms/step - loss: 0.8223 - acc: 0.6581 - val_loss: 0.8498 - val_acc: 0.6478
....
Epoch 9/10
976/976 [==============================] - 6s 7ms/step - loss: 0.7213 - acc: 0.7040 - val_loss: 0.7932 - val_acc: 0.6710
Epoch 10/10
976/976 [==============================] - 6s 6ms/step - loss: 0.7098 - acc: 0.7083 - val_loss: 0.7914 - val_acc: 0.6720
</pre>
[StratifiedKFold]



층화 추출 : 분류 문제에서 폴드마다 포함되는 클래스의 비율을 서로 맞추는 것.



테스트 데이터에 포함되는 각 클래스의 비율은 학습 데이터에 포함되는 각 클래스의 비율과 거의 같을 것이라는 가정에 근거하여 검증의 평가를 안정화 하는 방법



다중 클래스 분류에서 극단적으로 빈도가 적은 클래스가 있을 때, 랜덤으로 분할했을 때는 각 클래스의 비율이 달라져 평가의 불균형이 커질 가능성이 있으므로 층화 추출이 중요.



이진 분류에서 양성과 음성 중 어느 하나에 치우치지 않을 때는 클래스의 비율에 영향이 크지 않아 층화 추출을 사용하지 않아도 됨.



기존 KFold 클래스와 달리 층화추출을 위해 split 메서드의 인수에 목적변수를 입력해야함.









```python
from sklearn.model_selection import StratifiedKFold
skf=StratifiedKFold(n_splits=5, shuffle=True, random_state=26)
result=0
for train_index, valid_index in skf.split(train2,train['Sentiment']):
    x_train = train2[train_index]
    x_valid = train2[valid_index]
    y_train = train['Sentiment'].iloc[train_index]
    y_valid = train['Sentiment'].iloc[valid_index]
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
    model.add(LSTM(32))
    model.add(Dense(5, activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
    result+=model.predict(test2)/5
```

<pre>
Epoch 1/10
976/976 [==============================] - 8s 7ms/step - loss: 0.9425 - acc: 0.6114 - val_loss: 0.8675 - val_acc: 0.6383
Epoch 2/10
976/976 [==============================] - 7s 7ms/step - loss: 0.8506 - acc: 0.6442 - val_loss: 0.8447 - val_acc: 0.6494
...
</pre>
[GroupKFold]



학습 데이터와 테스트 데이터가 랜덤으로 분할되지 않을 때 사용 (단순히 랜덤하게 데이터를 분할하여 검증하면 본래의 성능보다 과대 평가될 우려가 있음)



group으로 지정한 데이터는 학습 데이터와 테스트 데이터에 동일한 값이 포함되지 않도록 분할.



```python
from sklearn.model_selection import KFold, GroupKFold
gkf=GroupKFold(n_splits=5)
result=0
for train_index, valid_index in gkf.split(train2,train['Sentiment'],train['SentenceId']):
    x_train = train2[train_index]
    x_valid = train2[valid_index]
    y_train = train['Sentiment'].iloc[train_index]
    y_valid = train['Sentiment'].iloc[valid_index]
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
    model.add(LSTM(32))
    model.add(Dense(5, activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
    result+=model.predict(test2)/5
```

<pre>
Epoch 1/10
976/976 [==============================] - 9s 7ms/step - loss: 0.9476 - acc: 0.6104 - val_loss: 0.8879 - val_acc: 0.6290
Epoch 2/10
976/976 [==============================] - 6s 6ms/step - loss: 0.8510 - acc: 0.6457 - val_loss: 0.8696 - val_acc: 0.6373
Epoch 3/10
...
976/976 [==============================] - 7s 7ms/step - loss: 0.7107 - acc: 0.7063 - val_loss: 0.8895 - val_acc: 0.6373
Epoch 10/10
976/976 [==============================] - 7s 7ms/step - loss: 0.6993 - acc: 0.7119 - val_loss: 0.8951 - val_acc: 0.6363
</pre>
[LeaveOneOut]



학습 데이터의 데이터 수가 극히 적을 때 사용



데이터가 적으면 가능한 한 많은 데이터를 사용하려 하고 학습에 걸리는 연산 시간도 짧으므로 폴드 수를 늘리 방법을 고려할 수 있으나, 폴드 수가 학습 데이터의 행의 수와 동일하며 검증 데이터는 각각 1건으로 검증하는 방법.



```python
# from sklearn.model_selection import LeaveOneOut
# loo=LeaveOneOut()
# result=0
# for train_index, valid_index in loo.split(train2):
#     x_train = train2[train_index]
#     x_valid = train2[valid_index]
#     y_train = train['Sentiment'].iloc[train_index]
#     y_valid = train['Sentiment'].iloc[valid_index]
    
#     model=Sequential()
#     model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
#     model.add(LSTM(32))
#     model.add(Dense(5, activation='softmax'))
    
#     model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
#     model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
#     result=model.predict(test2).mean
```

# 데이터가 극히 적은 경우가 아니므로 LeaveOneOut 교차 검증을 제외하고, 동일 조건에서 교차 검증을 비교하였을 때

# 

# 속도는 StratifiedKFold > GroupKFold > KFold 순으로 빠르고

# 

# 정확성은 GroupKFold > KFold > StratifiedKFold 순으로 높은 것으로 확인되었다.

# 

# 또한, 손실은 GroupKFold > KFold > StratifiedKFold 순으로 적었다.

# 

# 속도 측면에서는 StratifiedKFold가 빠르지만, accurcy와 loss 측면에서 GroupKFold가 유리한 결과를 얻었다.



```python
from sklearn.model_selection import StratifiedKFold
skf=StratifiedKFold(n_splits=7, shuffle=True, random_state=26)
result=0
for train_index, valid_index in skf.split(train2,train['Sentiment']):
    x_train = train2[train_index]
    x_valid = train2[valid_index]
    y_train = train['Sentiment'].iloc[train_index]
    y_valid = train['Sentiment'].iloc[valid_index]
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
    model.add(LSTM(32))
    model.add(Dense(5, activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
    result+=model.predict(test2)/7
```

<pre>
Epoch 1/10
1046/1046 [==============================] - 9s 7ms/step - loss: 0.9419 - acc: 0.6098 - val_loss: 0.8728 - val_acc: 0.6358
Epoch 2/10
1046/1046 [==============================] - 6s 6ms/step - loss: 0.8515 - acc: 0.6438 - val_loss: 0.8540 - val_acc: 0.6463
...
Epoch 9/10
1046/1046 [==============================] - 6s 6ms/step - loss: 0.7201 - acc: 0.7018 - val_loss: 0.7830 - val_acc: 0.6755
Epoch 10/10
1046/1046 [==============================] - 6s 6ms/step - loss: 0.7087 - acc: 0.7063 - val_loss: 0.7780 - val_acc: 0.6789
</pre>

```python
from sklearn.model_selection import StratifiedKFold
skf=StratifiedKFold(n_splits=9, shuffle=True, random_state=26)
result=0
for train_index, valid_index in skf.split(train2,train['Sentiment']):
    x_train = train2[train_index]
    x_valid = train2[valid_index]
    y_train = train['Sentiment'].iloc[train_index]
    y_valid = train['Sentiment'].iloc[valid_index]
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1,300,input_length=30, weights=[embedding_matrix], trainable=False))
    model.add(LSTM(32))
    model.add(Dense(5, activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=10,batch_size=128,validation_data=(x_valid,y_valid))
    result+=model.predict(test2)/9
```

<pre>
Epoch 1/10
1084/1084 [==============================] - 10s 6ms/step - loss: 0.9376 - acc: 0.6127 - val_loss: 0.8689 - val_acc: 0.6409
Epoch 2/10
1084/1084 [==============================] - 6s 6ms/step - loss: 0.8485 - acc: 0.6450 - val_loss: 0.8418 - val_acc: 0.6479
...
Epoch 9/10
1084/1084 [==============================] - 7s 7ms/step - loss: 0.7177 - acc: 0.7028 - val_loss: 0.7826 - val_acc: 0.6769
Epoch 10/10
1084/1084 [==============================] - 6s 6ms/step - loss: 0.7073 - acc: 0.7079 - val_loss: 0.7700 - val_acc: 0.6809
</pre>
StratifiedKFold를 기준으로 split 수를 5,7,9로 나누어 비교하였다.



# split을 많이 할 수록 전체 교차 검증의 횟수가 증가하므로 많은 시간이 소요되나, loss는 적게 나왔다.

# 

# 그러나 정확도 측면에서는 split수가 5>7>9 순으로 높았는데, 5보다 많이 split 갯수를 추가하면 과대적합이 일어나기 때문으로 보인다.



```python
sub['Sentiment']=result
sub.to_csv('submission.csv',index=False)
```

# 동일 조건일 때, score는 StratifiedKfold > GroupKFold > KFold 순으로 높았다.

# (score가 향상 될 수록 순위가 개선된다.)

# KFold : 0.66557

# StratifiedKFold : 0.66756

# GroupKFold : 0.66689

# 

# 따라서 StraitifedKFold 모델을 사용하여 5개로 split, 교차 검증하는 것이 가장 적합한 것으로 보았다.
