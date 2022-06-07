# 5 Stemming과 Lemmatization, stop words 실험 (Kaggle Spooky Author Identification)

![image](https://user-images.githubusercontent.com/69743938/172271470-c6312226-5e71-4585-ba64-ff1dcfd40332.png)
![image](https://user-images.githubusercontent.com/69743938/172271552-3c7c0611-49e7-4172-a30f-92bfd865b393.png)

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


/kaggle/input/spooky-author-identification/train.zip

/kaggle/input/spooky-author-identification/test.zip

/kaggle/input/spooky-author-identification/sample_submission.zip


```python
train=pd.read_csv('/kaggle/input/spooky-author-identification/train.zip')
test=pd.read_csv('/kaggle/input/spooky-author-identification/test.zip')
sub=pd.read_csv('/kaggle/input/spooky-author-identification/sample_submission.zip')
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>text</th>
      <th>author</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>id26305</td>
      <td>This process, however, afforded me no means of...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>1</th>
      <td>id17569</td>
      <td>It never once occurred to me that the fumbling...</td>
      <td>HPL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>id11008</td>
      <td>In his left hand was a gold snuff box, from wh...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>3</th>
      <td>id27763</td>
      <td>How lovely is spring As we looked from Windsor...</td>
      <td>MWS</td>
    </tr>
    <tr>
      <th>4</th>
      <td>id12958</td>
      <td>Finding nothing else, not even gold, the Super...</td>
      <td>HPL</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>19574</th>
      <td>id17718</td>
      <td>I could have fancied, while I looked at it, th...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>19575</th>
      <td>id08973</td>
      <td>The lids clenched themselves together as if in...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>19576</th>
      <td>id05267</td>
      <td>Mais il faut agir that is to say, a Frenchman ...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>19577</th>
      <td>id17513</td>
      <td>For an item of news like this, it strikes us i...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>19578</th>
      <td>id00393</td>
      <td>He laid a gnarled claw on my shoulder, and it ...</td>
      <td>HPL</td>
    </tr>
  </tbody>
</table>
<p>19579 rows × 3 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>id02310</td>
      <td>Still, as I urged our leaving Ireland with suc...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>id24541</td>
      <td>If a fire wanted fanning, it could readily be ...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>id00134</td>
      <td>And when they had broken down the frail door t...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>id27757</td>
      <td>While I was thinking how I should possibly man...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>id04081</td>
      <td>I am not sure to what limit his knowledge may ...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8387</th>
      <td>id11749</td>
      <td>All this is now the fitter for my purpose.</td>
    </tr>
    <tr>
      <th>8388</th>
      <td>id10526</td>
      <td>I fixed myself on a wide solitude.</td>
    </tr>
    <tr>
      <th>8389</th>
      <td>id13477</td>
      <td>It is easily understood that what might improv...</td>
    </tr>
    <tr>
      <th>8390</th>
      <td>id13761</td>
      <td>Be this as it may, I now began to feel the ins...</td>
    </tr>
    <tr>
      <th>8391</th>
      <td>id04282</td>
      <td>Long winded, statistical, and drearily genealo...</td>
    </tr>
  </tbody>
</table>
<p>8392 rows × 2 columns</p>
</div>



```python
train['text'][0]
```


'This process, however, afforded me no means of ascertaining the dimensions of my dungeon; as I might make its circuit, and return to the point whence I set out, without being aware of the fact; so perfectly uniform seemed the wall.'


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
      <th>text</th>
      <th>author</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>id26305</td>
      <td>This process, however, afforded me no means of...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>1</th>
      <td>id17569</td>
      <td>It never once occurred to me that the fumbling...</td>
      <td>HPL</td>
    </tr>
    <tr>
      <th>2</th>
      <td>id11008</td>
      <td>In his left hand was a gold snuff box, from wh...</td>
      <td>EAP</td>
    </tr>
    <tr>
      <th>3</th>
      <td>id27763</td>
      <td>How lovely is spring As we looked from Windsor...</td>
      <td>MWS</td>
    </tr>
    <tr>
      <th>4</th>
      <td>id12958</td>
      <td>Finding nothing else, not even gold, the Super...</td>
      <td>HPL</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8387</th>
      <td>id11749</td>
      <td>All this is now the fitter for my purpose.</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8388</th>
      <td>id10526</td>
      <td>I fixed myself on a wide solitude.</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8389</th>
      <td>id13477</td>
      <td>It is easily understood that what might improv...</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8390</th>
      <td>id13761</td>
      <td>Be this as it may, I now began to feel the ins...</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>8391</th>
      <td>id04282</td>
      <td>Long winded, statistical, and drearily genealo...</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>27971 rows × 3 columns</p>
</div>



```python
alldata['author'].unique()
```


array(['EAP', 'HPL', 'MWS', nan], dtype=object)


```python
alldata['text']
```

0       This process, however, afforded me no means of...


1       It never once occurred to me that the fumbling...

2       In his left hand was a gold snuff box, from wh...

3       How lovely is spring As we looked from Windsor...

4       Finding nothing else, not even gold, the Super...

...                        

8387           All this is now the fitter for my purpose.

8388                   I fixed myself on a wide solitude.

8389    It is easily understood that what might improv...

8390    Be this as it may, I now began to feel the ins...

8391    Long winded, statistical, and drearily genealo...

Name: text, Length: 27971, dtype: object


---------------
Lemmatization은 정확한 원형 단어 추출을 위해 단어의 '품사'를 입력해 주어야합니다.
alldata의 text는 sentence로 되어 있어 하나씩 품사를 지정하는 것이 어려우므로 Stemming을 이용하겠습니다.

---------


```python
from nltk.stem import LancasterStemmer
LS =  LancasterStemmer()
alldata['text'] = [LS.stem(w) for w in alldata['text']]
```


```python
alldata['text']
```


0       this process, however, afforded me no means of...

1       it never once occurred to me that the fumbling...

2       in his left hand was a gold snuff box, from wh...

3       how lovely is spring as we looked from windsor...

4       finding nothing else, not even gold, the super...

...                        

8387           all this is now the fitter for my purpose.

8388                   i fixed myself on a wide solitude.

8389    it is easily understood that what might improv...

8390    be this as it may, i now began to feel the ins...

8391    long winded, statistical, and drearily genealo...

Name: text, Length: 27971, dtype: object



```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
TK.fit_on_texts(alldata['text'])
TK.word_index
```


{'the': 1,
 'of': 2,
 'and': 3,
 'to': 4,
 'i': 5,
 ...
 'lead': 996,
 'proper': 997,
 'dying': 998,
 'mankind': 999,
 'bosom': 1000,
 ...}


```python
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
train['author']=le.fit_transform(train['author'])
train['author'][0]
```


0


```python
text=TK.texts_to_sequences(alldata['text'])
text
```

[[26,
  3334,
  139,
  ...
  87,
  1,
  1409],
 ...]

------
분석에 큰 의미가 없는 단어를 학습에 되면 텍스트에 빈번하게 나타나 중요한 단어로 인지되는 오류가 우려됩니다.

따라서 is, the, a, will등 문장을 구성하는 필수 문법 요소이나 문맥적으로 큰 의미가 없는 단어를 전처리하는 작업을 진행하겠습니다.

------

```python
 import nltk

 stopwords = nltk.corpus.stopwords.words('english')

 for sentence in TK.word_index:
     filtered_words=[]
    
     for word in sentence:
         word=word.lower()
     if word not in stopwords:
         filtered_words.append(word)
        
 text.append(filtered_words)
```


```python
pd.Series(text)
```


0        [26, 3334, 139, 1295, 22, 36, 285, 2, 6426, 1,...

1        [11, 90, 128, 725, 4, 22, 9, 1, 5966, 80, 28, ...

2        [7, 15, 154, 173, 8, 6, 694, 5967, 560, 24, 19...

3        [120, 568, 25, 766, 16, 34, 216, 24, 754, 4176...

4        [1229, 160, 735, 20, 75, 694, 1, 5214, 1464, 1...

...                        

27966              [32, 26, 25, 52, 1, 18603, 17, 10, 500]

27967                      [5, 1045, 110, 27, 6, 574, 817]

27968    [11, 25, 672, 1112, 9, 53, 80, 7208, 6, 1402, ...


27969    [28, 26, 16, 11, 123, 5, 52, 273, 4, 297, 1, 6...

27970    [109, 18563, 29450, 3, 29451, 6647, 16, 54, 2,...

Length: 27971, dtype: object


```python
len(TK.word_index)
```


29451


```python
pd.Series(text).apply(len).max()
```


861


```python
import seaborn as sns
sns.displot(pd.Series(text).apply(len))
```


<seaborn.axisgrid.FacetGrid at 0x7f915d775e50>

<img src="data:image/png;base64,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"/>


```python
pd.Series(text)
```


0        [26, 3334, 139, 1295, 22, 36, 285, 2, 6426, 1,...

1        [11, 90, 128, 725, 4, 22, 9, 1, 5966, 80, 28, ...

2        [7, 15, 154, 173, 8, 6, 694, 5967, 560, 24, 19...

3        [120, 568, 25, 766, 16, 34, 216, 24, 754, 4176...

4        [1229, 160, 735, 20, 75, 694, 1, 5214, 1464, 1...

...                        

27966              [32, 26, 25, 52, 1, 18603, 17, 10, 500]

27967                      [5, 1045, 110, 27, 6, 574, 817]

27968    [11, 25, 672, 1112, 9, 53, 80, 7208, 6, 1402, ...

27969    [28, 26, 16, 11, 123, 5, 52, 273, 4, 297, 1, 6...

27970    [109, 18563, 29450, 3, 29451, 6647, 16, 54, 2,...

Length: 27971, dtype: object



```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(text,maxlen=100)
pad_text
```


array([[    0,     0,     0, ...,    98,     1,   443],

[    0,     0,     0, ...,     6,   450,  2453],

[    0,     0,     0, ...,   353,   526,  3101],

...,

[    0,     0,     0, ..., 13787,   482,   541],

[    0,     0,     0, ...,     4,    28, 16748],

[    0,     0,     0, ...,     1,   189,  1581]], dtype=int32)



```python
train2=pad_text[:len(train)]
test2=pad_text[len(train):]
display(train2,test2)
```


array([[    0,     0,     0, ...,    98,     1,   443],

[    0,     0,     0, ...,     6,   450,  2453],

[    0,     0,     0, ...,   353,   526,  3101],

...,

[    0,     0,     0, ...,    90, 18101, 12055],

[    0,     0,     0, ...,    61,  8069,   523],

[    0,     0,     0, ...,     9,     2,  6011]], dtype=int32)


array([[    0,     0,     0, ...,   420,     4,  2315],

[    0,     0,     0, ...,     2,     6,  7023],

[    0,     0,     0, ...,     1,  2161,  4474],

...,

[    0,     0,     0, ..., 13787,   482,   541],

[    0,     0,     0, ...,     4,    28, 16748],

[    0,     0,     0, ...,     1,   189,  1581]], dtype=int32)



```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
```


```python
from sklearn.model_selection import train_test_split
x_train, x_valid, y_train, y_valid = train_test_split(train2,train["author"],test_size=0.2,random_state=42,stratify=train["author"])
```
---------------------------

# EarlyStopping의 patience를 3/5/8로 변경하고, Stopwords를 사용할 경우와 Stemming을 사용할 경우의 예측 정확도를 확인하겠습니다.

----------

```python
from sklearn.model_selection import StratifiedKFold
from tensorflow.keras.callbacks import EarlyStopping

skf=StratifiedKFold(n_splits=5, shuffle=True, random_state=24)
result=0
for train_index, valid_index in skf.split(train2,train['author']):
    x_train=train2[train_index]
    x_valid=train2[valid_index]
    y_train=train['author'].iloc[train_index]
    y_valid=train['author'].iloc[valid_index]
    es=EarlyStopping(patience=3)
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1, 3, input_length=100))
    model.add(LSTM(32))
    model.add(Dense(3,activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=1000, batch_size=128, validation_data=(x_valid,y_valid), callbacks=[es])
    result += model.predict(test2)/5
```

Epoch 1/1000

2022-04-11 07:46:25.520845: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005

Output exceeds the size limit. Open the full output data in a text editor

123/123 [==============================] - 5s 11ms/step - loss: 1.0559 - acc: 0.4442 - val_loss: 0.9613 - val_acc: 0.5493

Epoch 2/1000

123/123 [==============================] - 1s 8ms/step - loss: 0.8277 - acc: 0.6054 - val_loss: 0.7772 - val_acc: 0.6221

...

Epoch 7/1000

123/123 [==============================] - 1s 7ms/step - loss: 0.1508 - acc: 0.9540 - val_loss: 0.5172 - val_acc: 0.8209

Epoch 8/1000

123/123 [==============================] - 1s 8ms/step - loss: 0.1163 - acc: 0.9643 - val_loss: 0.5753 - val_acc: 0.8153



```python
from sklearn.model_selection import StratifiedKFold
from tensorflow.keras.callbacks import EarlyStopping

skf=StratifiedKFold(n_splits=5, shuffle=True, random_state=24)
result=0
for train_index, valid_index in skf.split(train2,train['author']):
    x_train=train2[train_index]
    x_valid=train2[valid_index]
    y_train=train['author'].iloc[train_index]
    y_valid=train['author'].iloc[valid_index]
    es=EarlyStopping(patience=5)
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1, 3, input_length=100))
    model.add(LSTM(32))
    model.add(Dense(3,activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=1000, batch_size=128, validation_data=(x_valid,y_valid), callbacks=[es])
    result += model.predict(test2)/5
```

Epoch 1/1000

123/123 [==============================] - 3s 10ms/step - loss: 1.0681 - acc: 0.4218 - val_loss: 1.0104 - val_acc: 0.5618

Epoch 2/1000

123/123 [==============================] - 1s 7ms/step - loss: 0.8526 - acc: 0.6190 - val_loss: 0.7807 - val_acc: 0.6614

...

Epoch 9/1000

123/123 [==============================] - 1s 7ms/step - loss: 0.3234 - acc: 0.8742 - val_loss: 0.8906 - val_acc: 0.6777

Epoch 10/1000

123/123 [==============================] - 1s 7ms/step - loss: 0.2731 - acc: 0.8949 - val_loss: 1.0300 - val_acc: 0.6705




```python
from sklearn.model_selection import StratifiedKFold
from tensorflow.keras.callbacks import EarlyStopping

skf=StratifiedKFold(n_splits=5, shuffle=True, random_state=24)
result=0
for train_index, valid_index in skf.split(train2,train['author']):
    x_train=train2[train_index]
    x_valid=train2[valid_index]
    y_train=train['author'].iloc[train_index]
    y_valid=train['author'].iloc[valid_index]
    es=EarlyStopping(patience=8)
    
    model=Sequential()
    model.add(Embedding(len(TK.word_index)+1, 3, input_length=100))
    model.add(LSTM(32))
    model.add(Dense(3,activation='softmax'))
    
    model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics='acc')
    model.fit(x_train,y_train,epochs=1000, batch_size=128, validation_data=(x_valid,y_valid), callbacks=[es])
    result += model.predict(test2)/5
```

Epoch 1/1000

123/123 [==============================] - 3s 10ms/step - loss: 1.0675 - acc: 0.4213 - val_loss: 0.9893 - val_acc: 0.5281

Epoch 2/1000

123/123 [==============================] - 1s 7ms/step - loss: 0.8423 - acc: 0.5798 - val_loss: 0.7999 - val_acc: 0.5896

...

Epoch 19/1000

123/123 [==============================] - 1s 8ms/step - loss: 0.0222 - acc: 0.9946 - val_loss: 0.9370 - val_acc: 0.7900

Epoch 20/1000

123/123 [==============================] - 1s 8ms/step - loss: 0.0271 - acc: 0.9933 - val_loss: 0.8450 - val_acc: 0.8018

-------
STOP WORD를 사용하는 경우 결과를 result의 row수가 증가하는 것을 감안하여 
'a = np.delete(result, 8392, 0)
sub.iloc[:, 1:] = a' 로 바꾸어 주어야 합니다.

----------------


```python
sub=pd.read_csv('/kaggle/input/spooky-author-identification/sample_submission.zip')
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>EAP</th>
      <th>HPL</th>
      <th>MWS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>id02310</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>1</th>
      <td>id24541</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>2</th>
      <td>id00134</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>3</th>
      <td>id27757</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>4</th>
      <td>id04081</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8387</th>
      <td>id11749</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>8388</th>
      <td>id10526</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>8389</th>
      <td>id13477</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>8390</th>
      <td>id13761</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
    <tr>
      <th>8391</th>
      <td>id04282</td>
      <td>0.403494</td>
      <td>0.287808</td>
      <td>0.308698</td>
    </tr>
  </tbody>
</table>
<p>8392 rows × 4 columns</p>
</div>



```python
sub.iloc[:, 1:] = result
```


```python
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>EAP</th>
      <th>HPL</th>
      <th>MWS</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>id02310</td>
      <td>0.008728</td>
      <td>0.118500</td>
      <td>0.872772</td>
    </tr>
    <tr>
      <th>1</th>
      <td>id24541</td>
      <td>0.996614</td>
      <td>0.001209</td>
      <td>0.002178</td>
    </tr>
    <tr>
      <th>2</th>
      <td>id00134</td>
      <td>0.015583</td>
      <td>0.961564</td>
      <td>0.022853</td>
    </tr>
    <tr>
      <th>3</th>
      <td>id27757</td>
      <td>0.947694</td>
      <td>0.033086</td>
      <td>0.019219</td>
    </tr>
    <tr>
      <th>4</th>
      <td>id04081</td>
      <td>0.981254</td>
      <td>0.003714</td>
      <td>0.015032</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>8387</th>
      <td>id11749</td>
      <td>0.739260</td>
      <td>0.025434</td>
      <td>0.235306</td>
    </tr>
    <tr>
      <th>8388</th>
      <td>id10526</td>
      <td>0.002920</td>
      <td>0.027663</td>
      <td>0.969417</td>
    </tr>
    <tr>
      <th>8389</th>
      <td>id13477</td>
      <td>0.273617</td>
      <td>0.054506</td>
      <td>0.671877</td>
    </tr>
    <tr>
      <th>8390</th>
      <td>id13761</td>
      <td>0.097436</td>
      <td>0.012237</td>
      <td>0.890327</td>
    </tr>
    <tr>
      <th>8391</th>
      <td>id04282</td>
      <td>0.009043</td>
      <td>0.981518</td>
      <td>0.009439</td>
    </tr>
  </tbody>
</table>
<p>8392 rows × 4 columns</p>
</div>



```python
sub.to_csv("submission.csv",index=0)
```

------------------
총 5가지의 조건에서 실험하였을 때, score 개선 순위는 다음과 같습니다.(score가 낮을 수록 순위가 개선됩니다.)

동일 조건의 EarlyStopping(patience=5) : 0.41446  >  EarlyStopping(patience=3) : 0.44439  >  EarlyStopping(patience=8) : 0.49869

# patience의 횟수를 늘리면 교차 검증의 정확도가 높아지나, 일정 기준을 넘으면 score가 미개선 되는 것으로 보아 과대 적합이 발생했음을 예상할 수 있습니다.

동일 조건, EarlyStopping의 patience를 5로 고정하였을 때, STOP WORDS : 0.54565 > Stemming : 0.57502  의 결과를 얻었습니다.

그러나 모두 적용하지 않았을 때 보다 SCORE가 미개선 되었습니다.

# STOP WORDS의 경우 미개선 이유는 is, the, a, will등 문장을 구성하는 문법 등이 train data의 text column의 의미를 조금씩 변화시켜 정확도를 향상하는데 도움이 되었던 것으로 보입니다.

# Stemming의 경우 미개선 이유는 역시 단어의 원형을 찾는 과정에서 train data의 text column의 의미를 조금씩 변화시켜 정확도를 향상하는데 도움이 되지 않았던 것으로 보입니다.

# Text의 문맥상 미세한 차이가 정확성에 큰 영향을 주는 경우 STOP WORDS와 Stemming을 사용하는 것은 부적합함을 느꼈습니다. 따라서 Data 특성을 먼저 파악하여 적합한 기법을 사용하는 것이 필요할 것입니다.
