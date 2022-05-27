
# 9 Sequential Model Compile 실험 (Kaggle Toxic Comment Classification Challenge) 


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
/kaggle/input/jigsaw-toxic-comment-classification-challenge/train.csv.zip
/kaggle/input/jigsaw-toxic-comment-classification-challenge/sample_submission.csv.zip
/kaggle/input/jigsaw-toxic-comment-classification-challenge/test_labels.csv.zip
/kaggle/input/jigsaw-toxic-comment-classification-challenge/test.csv.zip
</pre>

```python
train=pd.read_csv("/kaggle/input/jigsaw-toxic-comment-classification-challenge/train.csv.zip")
test=pd.read_csv("/kaggle/input/jigsaw-toxic-comment-classification-challenge/test.csv.zip")
display(train,test)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>comment_text</th>
      <th>toxic</th>
      <th>severe_toxic</th>
      <th>obscene</th>
      <th>threat</th>
      <th>insult</th>
      <th>identity_hate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0000997932d777bf</td>
      <td>Explanation\nWhy the edits made under my usern...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>000103f0d9cfb60f</td>
      <td>D'aww! He matches this background colour I'm s...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>000113f07ec002fd</td>
      <td>Hey man, I'm really not trying to edit war. It...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0001b41b1c6bb37e</td>
      <td>"\nMore\nI can't make any real suggestions on ...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0001d958c54c6e35</td>
      <td>You, sir, are my hero. Any chance you remember...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
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
    </tr>
    <tr>
      <th>159566</th>
      <td>ffe987279560d7ff</td>
      <td>":::::And for the second time of asking, when ...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>159567</th>
      <td>ffea4adeee384e90</td>
      <td>You should be ashamed of yourself \n\nThat is ...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>159568</th>
      <td>ffee36eab5c267c9</td>
      <td>Spitzer \n\nUmm, theres no actual article for ...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>159569</th>
      <td>fff125370e4aaaf3</td>
      <td>And it looks like it was actually you who put ...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>159570</th>
      <td>fff46fc426af1f9a</td>
      <td>"\nAnd ... I really don't think you understand...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>159571 rows × 8 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>comment_text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>00001cee341fdb12</td>
      <td>Yo bitch Ja Rule is more succesful then you'll...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0000247867823ef7</td>
      <td>== From RfC == \n\n The title is fine as it is...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>00013b17ad220c46</td>
      <td>" \n\n == Sources == \n\n * Zawe Ashton on Lap...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>00017563c3f7919a</td>
      <td>:If you have a look back at the source, the in...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00017695ad8997eb</td>
      <td>I don't anonymously edit articles at all.</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>153159</th>
      <td>fffcd0960ee309b5</td>
      <td>. \n i totally agree, this stuff is nothing bu...</td>
    </tr>
    <tr>
      <th>153160</th>
      <td>fffd7a9a6eb32c16</td>
      <td>== Throw from out field to home plate. == \n\n...</td>
    </tr>
    <tr>
      <th>153161</th>
      <td>fffda9e8d6fafa9e</td>
      <td>" \n\n == Okinotorishima categories == \n\n I ...</td>
    </tr>
    <tr>
      <th>153162</th>
      <td>fffe8f1340a79fc2</td>
      <td>" \n\n == ""One of the founding nations of the...</td>
    </tr>
    <tr>
      <th>153163</th>
      <td>ffffce3fb183ee80</td>
      <td>" \n :::Stop already. Your bullshit is not wel...</td>
    </tr>
  </tbody>
</table>
<p>153164 rows × 2 columns</p>
</div>



```python
train["comment_text"][0]
```

<pre>
"Explanation\nWhy the edits made under my username Hardcore Metallica Fan were reverted? They weren't vandalisms, just closure on some GAs after I voted at New York Dolls FAC. And please don't remove the template from the talk page since I'm retired now.89.205.38.27"
</pre>

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
      <th>comment_text</th>
      <th>toxic</th>
      <th>severe_toxic</th>
      <th>obscene</th>
      <th>threat</th>
      <th>insult</th>
      <th>identity_hate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0000997932d777bf</td>
      <td>Explanation\nWhy the edits made under my usern...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>000103f0d9cfb60f</td>
      <td>D'aww! He matches this background colour I'm s...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>000113f07ec002fd</td>
      <td>Hey man, I'm really not trying to edit war. It...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0001b41b1c6bb37e</td>
      <td>"\nMore\nI can't make any real suggestions on ...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0001d958c54c6e35</td>
      <td>You, sir, are my hero. Any chance you remember...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
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
    </tr>
    <tr>
      <th>153159</th>
      <td>fffcd0960ee309b5</td>
      <td>. \n i totally agree, this stuff is nothing bu...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>153160</th>
      <td>fffd7a9a6eb32c16</td>
      <td>== Throw from out field to home plate. == \n\n...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>153161</th>
      <td>fffda9e8d6fafa9e</td>
      <td>" \n\n == Okinotorishima categories == \n\n I ...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>153162</th>
      <td>fffe8f1340a79fc2</td>
      <td>" \n\n == ""One of the founding nations of the...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>153163</th>
      <td>ffffce3fb183ee80</td>
      <td>" \n :::Stop already. Your bullshit is not wel...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>312735 rows × 8 columns</p>
</div>


alldata의 'comment_text' column은 text 형식으로 Keras에서 제공하는 Tokenizer를 이용하여 빈도수가 높은 순서대로 정렬하여 각 단어에 숫자를 부여합니다



```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
TK.fit_on_texts(alldata["comment_text"])
TK.word_index
```

<pre>
{'the': 1,
 'to': 2,
 'of': 3,
 'a': 4,
 'and': 5,
 'you': 6,
 'i': 7,
 'is': 8,
 'that': 9,
...
 'million': 997,
 'house': 998,
 'wait': 999,
 'bastard': 1000,
 ...}
</pre>

```python
TK.word_counts["toxic"]
```

<pre>
123
</pre>
alldata의 'comment_text' column만 따로 text로 정의하고, 숫자가 순서대로 matching 되어 들어갑니다.



```python
text=TK.texts_to_sequences(alldata["comment_text"])
text
```

<pre>
[[733,
  78,
  1,
  140,
  131,
  182,
  30,

  224,
  12,
  37,
  2,
  1625],
 ...]
</pre>

```python
len(TK.word_index)
```

<pre>
394787
</pre>

```python
print(text[0])
```

<pre>
[733, 78, 1, 140, 131, 182, 30, 712, 4438, 10284, 1252, 86, 368, 51, 2230, 14039, 49, 6744, 15, 60, 2624, 151, 7, 2832, 33, 115, 1246, 16129, 2517, 5, 50, 59, 256, 1, 370, 31, 1, 46, 29, 144, 72, 3931, 89, 4208, 6368, 2687, 1183]
</pre>

```python
pd.Series(text)
```

<pre>
0         [733, 78, 1, 140, 131, 182, 30, 712, 4438, 102...
1         [160366, 52, 2911, 13, 450, 3782, 72, 4871, 26...
2         [455, 400, 72, 126, 14, 268, 2, 79, 326, 71, 4...
3         [58, 7, 229, 97, 55, 325, 1408, 15, 2120, 7, 5...
4         [6, 1744, 18, 30, 3598, 55, 1105, 6, 584, 38, ...
                                ...                        
312730    [7, 1071, 263, 13, 536, 8, 241, 26, 155, 250, ...
312731    [2574, 31, 76, 995, 2, 1042, 6255, 100, 11, 94...
312732    [106460, 1207, 7, 63, 20, 422, 5, 263, 13, 8, ...
312733    [47, 3, 1, 5959, 2178, 3, 1, 2829, 1411, 42, 4...
312734    [171, 237, 20, 837, 8, 14, 196, 64, 72, 44, 15...
Length: 312735, dtype: object
</pre>

```python
pd.Series(text).apply(len).max()
```

<pre>
2142
</pre>

```python
import seaborn as sns
import matplotlib.pyplot as plt
sns.displot(pd.Series(text).apply(len))
plt.xlim(0,300)
```

<pre>
(0.0, 300.0)
</pre>
<img src="data:image/png;base64,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"/>

text의 숫자 갯수를 보았을때, 250 이상이 많지 않으므로 모든 행의 value 갯수를 250으로 변경합니다.



```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(text, maxlen=250)
pad_text
pad_text.shape
```

<pre>
(312735, 250)
</pre>

```python
train2=pad_text[:len(train)]
test2=pad_text[len(train):]
```


```python
from tensorflow.keras import *
from tensorflow.keras.layers import *
```

사이킷런의 train_test_split : 원본 데이터 세트에서 학습 및 테스트 데이터 세트를 쉽게 분리할 수 있습니다.



test size : 전체 데이터에서 테스트 데이터 세트 크기를 얼마로 샘플링할 것인가 결정 (20%로 설정)



train size : 전체 데이터에서 학습 데이터 세트 크기를 얼마로 샘플링할 것인가 결정, 대부분 test size만 사용



shuffle : 데이터 분리 전에 섞는 작업, default는 True



random_state : 호출할 때마다 동일한 학습/테스트용 데이터 세트를 생성하기 위해 주어지는 난수 값. 지정하지 않으면 train_test_split 호출 시 무작위로 데이터를 분리하므로 수행할 때마다 다른 학습/테스트용 데이터를 생성할 수 있습니다. (일정한 값 42로 설정)



stratify : default는 none, stratify 값을 target으로 지정해주면 각각의 class 비율(ratio)을 train / validation에 유지해 줍니다. 한 쪽에 쏠려서 분배되는 것을 방지합니다



```python
from sklearn.model_selection import train_test_split  #train["정답 column"]
x_train, x_valid, y_train, y_valid = train_test_split(train2,train["toxic"], test_size=0.2, random_state=42, stratify=train["toxic"])
```

model Sequential을 이용하여 순차 학습을 진행합니다



*Embedding(vocab_size, embedding_dim, input_length)



vocabsize : 총 단어의 갯수



embedding_dim : 결과로 출력되는 임베딩 벡터의 크기 



input_length : 입력 시퀀스의 길이





LSTM과 DENSE LAYER를 이용하여 순차적으로 학습합니다.





*LSTM

LSTM에서는 출력, 입력, 삭제 게이트라는 3개의 게이트가 존재



LSTM (Long Short Term Memory)는 기존의 RNN이 출력과 먼 위치에 있는 정보를 기억할 수 없다는 단점을 보완하여 장/단기 기억을 가능하게 설계한 신경망의 구조



*DENSE LAYER

입력과 출력을 모두 연결해 주며, 입력과 출력을 각각 연결해주는 가중치를 포함하고 있다.







verbose = 학습 중 출력되는 문구를 설정합니다.

- 0 : 아무 것도 출력하지 않습니다.

- 1 : 훈련의 진행도를 보여주는 진행 막대를 보여줍니다.

- 2 : 미니 배치마다 손실 정보를 출력합니다.


[rmsprop]



Adagrad는 실제로 무한히 계속 학습하다보면 어느 순간 갱신량이 0이 되는 문제를 해결.



과거의 기울기를 균일하게 더해가는 것이 아니라 먼 과거의 기울기는 서서히 잊고 새로운 기울기 정보를 크게 반영하는 방법이다. 이를 지수이동평균이라 한다. 



학습률이 크면 학습은 빠르나 최적의 가중치를 지나칠 수 있고, 학습률이 작으면 학습시간이 오래걸려 기울기에 따라 학습률을 조정하여 최적의 해 부근에서 학습률이 작아지도록 하는 방법



알엠에스프롭은 아다그라드의 G(i) 값이 무한히 커지는 것을 방지하고자 제안된 방법으로 아다그라드 함수에 감마 값을 추가하여 사용자가 감마값을 이용하여 학습률 크기를 비율로 조정할 수 있도록 했습니다.



​



알엠에스프롭은 일반적으로 순환 신경망(Recurrent Nerural Networks)의 옵티마이저로 많이 사용되며, 사용할 때는 학습률을 제외한 모든 인자의 기본값을 사용하는 것이 권장됩니다.



For a multi-class classification problem

model.compile(optimizer='rmsprop',

              loss='sparse_categorical_crossentropy',

              metrics=['accuracy'])



For a binary classification problem

model.compile(optimizer='rmsprop',

              loss='binary_crossentropy',

              metrics=['accuracy'])



For a mean squared error regression problem

model.compile(optimizer='rmsprop',

              loss='mse')



# 데이터가 multi-class classification problem에 해당 하므로, 손실 함수는 'sparse_categorical_crossentropy'를 사용하는 것이 적합합니다.



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer='rmsprop',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
2022-03-30 03:18:25.369316: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:25.443869: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:25.444593: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:25.445725: I tensorflow/core/platform/cpu_feature_guard.cc:142] This TensorFlow binary is optimized with oneAPI Deep Neural Network Library (oneDNN) to use the following CPU instructions in performance-critical operations:  AVX2 AVX512F FMA
To enable them in other operations, rebuild TensorFlow with the appropriate compiler flags.
2022-03-30 03:18:25.447310: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:25.447984: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:25.448584: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:27.373254: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:27.374173: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:27.374894: I tensorflow/stream_executor/cuda/cuda_gpu_executor.cc:937] successful NUMA node read from SysFS had negative value (-1), but there must be at least one NUMA node, so returning NUMA node zero
2022-03-30 03:18:27.375602: I tensorflow/core/common_runtime/gpu/gpu_device.cc:1510] Created device /job:localhost/replica:0/task:0/device:GPU:0 with 15403 MB memory:  -> device: 0, name: Tesla P100-PCIE-16GB, pci bus id: 0000:00:04.0, compute capability: 6.0
2022-03-30 03:18:28.120608: I tensorflow/compiler/mlir/mlir_graph_optimization_pass.cc:185] None of the MLIR Optimization Passes are enabled (registered 2)
</pre>
<pre>
Epoch 1/5
</pre>
<pre>
2022-03-30 03:18:30.523272: I tensorflow/stream_executor/cuda/cuda_dnn.cc:369] Loaded cuDNN version 8005
</pre>
<pre>
998/998 [==============================] - 16s 13ms/step - loss: nan - accuracy: 0.9033 - val_loss: nan - val_accuracy: 0.9042
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: nan - accuracy: 0.9042 - val_loss: nan - val_accuracy: 0.9042
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: nan - accuracy: 0.9042 - val_loss: nan - val_accuracy: 0.9042
Epoch 4/5
998/998 [==============================] - 13s 13ms/step - loss: nan - accuracy: 0.9042 - val_loss: nan - val_accuracy: 0.9042
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: nan - accuracy: 0.9042 - val_loss: nan - val_accuracy: 0.9042
</pre>
# multiple classification이므로 컴파일의 loss를 categorical_crossentropy로 지정하면 accuracy가 현저히 낮아지는 것을 볼 수 있습니다.



categorical_crossentropy는 이진분류에 적합하므로 데이터를 one-hot encoding 처리한 경우 사용 가능하다



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer='rmsprop',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 14s 13ms/step - loss: 0.0000e+00 - accuracy: 0.0958 - val_loss: 0.0000e+00 - val_accuracy: 0.0958
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: 0.0000e+00 - accuracy: 0.0958 - val_loss: 0.0000e+00 - val_accuracy: 0.0958
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: 0.0000e+00 - accuracy: 0.0958 - val_loss: 0.0000e+00 - val_accuracy: 0.0958
Epoch 4/5
998/998 [==============================] - 13s 14ms/step - loss: 0.0000e+00 - accuracy: 0.0958 - val_loss: 0.0000e+00 - val_accuracy: 0.0958
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: 0.0000e+00 - accuracy: 0.0958 - val_loss: 0.0000e+00 - val_accuracy: 0.0958
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer='rmsprop',
              loss='binary_crossentropy',
              metrics=['accuracy'])
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 16s 14ms/step - loss: 0.2041 - accuracy: 0.0958 - val_loss: 0.1445 - val_accuracy: 0.0958
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: 0.1269 - accuracy: 0.0958 - val_loss: 0.1176 - val_accuracy: 0.0958
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: 0.1103 - accuracy: 0.0958 - val_loss: 0.1120 - val_accuracy: 0.0958
Epoch 4/5
998/998 [==============================] - 14s 14ms/step - loss: 0.1044 - accuracy: 0.0958 - val_loss: 0.1131 - val_accuracy: 0.0958
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: 0.1031 - accuracy: 0.0958 - val_loss: 0.1276 - val_accuracy: 0.0958
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer='rmsprop', loss='mse',metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 14s 13ms/step - loss: 0.9042 - acc: 0.0958 - val_loss: 0.9042 - val_acc: 0.0958
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: 0.9042 - acc: 0.0958 - val_loss: 0.9042 - val_acc: 0.0958
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: 0.9042 - acc: 0.0958 - val_loss: 0.9042 - val_acc: 0.0958
Epoch 4/5
998/998 [==============================] - 13s 13ms/step - loss: 0.9042 - acc: 0.0958 - val_loss: 0.9042 - val_acc: 0.0958
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: 0.9042 - acc: 0.0958 - val_loss: 0.9042 - val_acc: 0.0958
</pre>
*activation

- sigmoid : 이진 분류 문제에서 출력층에 주로 사용되는 활성화 함수.

- linear : 디폴트 값으로 별도 활성화 함수 없이 입력 뉴런과 가중치의 계산 결과 그대로 출력.

- softmax : 셋 이상의 선택지 중 하나를 택하는 다중 클래스 분류 문제에서 출력층에 주로 사용되는 활성화 함수.

- relu : 은닉층에 주로 사용되는 활성화 함수.





# 데이터를 사용하여 예측 할 때,

# 초기 속도(linear>relu>softmax) 최종속도(softmax>relu>linear) 의 경향을 보여 학습이 복잡하고 데이터가 방대할 수록 softmax가 유리할 것으로 보입니다.





# 초기 ACCRACY(linear>relu>softmax) 이나, 학습을 진행하면서 accuracy의 차이는 줄어드는 것으로 보입니다.


[adam]



RMSProp과 모멘텀의 개념을 합친 것.

학습률은 기울기에 따라 조정하되 관성을 통해 지역 최솟값에 갇히지 않도록 하여 가장 많이 사용.



아담은 모멘텀과 알엠에스프롭의 장점을 결합한 경사 하강법입니다. 알엠에스프롭의 특징인 기울기 제곱을 지수 평균한 값과 모멘텀의 특징을 수식에 활용하는데 알엠에스프롭의 G함수와 모멘텀을 이용하여 가중치를 업데이트합니다.





​



아담은 두 개의 모멘텀을 활용하는데 m(First momentum)과 v(Second momentum)이 그것입니다. m은 기존의 모멘텀과 동일하게 Gradient 값을 좀 더 빠르게 계산할 수 있도록 돕는 역할을 하고 v는 데이터의 분포가 띄엄띄엄한 영역에서 영향력을 극대화시켜 해당 영역을 벗어날 수 있도록 돕는 역할을 합니다. 아담은 각기 다른 분야의 장점을 합쳐 우수한 성능으로 보편적으로 많이 사용되는 옵티마이저 중 하나입니다.



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="linear"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=20, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/20
998/998 [==============================] - 15s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 2/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 6/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 7/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 8/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 9/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 10/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 11/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 12/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 13/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 14/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 15/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 16/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 17/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 18/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 19/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 20/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=20, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/20
998/998 [==============================] - 15s 13ms/step - loss: nan - acc: 0.9033 - val_loss: nan - val_acc: 0.9042
Epoch 2/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 6/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 7/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 8/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 9/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 10/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 11/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 12/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 13/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 14/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 15/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 16/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 17/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 18/20
998/998 [==============================] - 12s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 19/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 20/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="relu"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=20, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/20
998/998 [==============================] - 14s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 2/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 6/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 7/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 8/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 9/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 10/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 11/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 12/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 13/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 14/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 15/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 16/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 17/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 18/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 19/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 20/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[GRU]



GRU는 LSTM의 장기 의존성 문제에 대한 해결책을 유지하면서, 은닉 상태를 업데이트하는 계산을 줄였습니다. 다시 말해서, GRU는 성능은 LSTM과 유사하면서 복잡했던 LSTM의 구조를 간단화 시켰습니다.



GRU와 LSTM 중 어떤 것이 모델의 성능면에서 더 낫다라고 단정지어 말할 수 없으며, 기존에 LSTM을 사용하면서 최적의 하이퍼파라미터를 찾아낸 상황이라면 굳이 GRU로 바꿔서 사용할 필요는 없습니다.



경험적으로 데이터 양이 적을 때는 매개 변수의 양이 적은 GRU가 조금 더 낫고, 데이터 양이 더 많으면 LSTM이 더 낫다고도 합니다. GRU보다 LSTM에 대한 연구나 사용량이 더 많은데, 이는 LSTM이 더 먼저 나온 구조이기 때문입니다.



# 데이터에 적용하였을 때, LSTM과 GRU의 ACCURACY와 학습 시간의 차이는 거의 없습니다.



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(GRU(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=20, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2) 
```

<pre>
Epoch 1/20
998/998 [==============================] - 15s 13ms/step - loss: nan - acc: 0.9034 - val_loss: nan - val_acc: 0.9042
Epoch 2/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/20
998/998 [==============================] - 12s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 6/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 7/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 8/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 9/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 10/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 11/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 12/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 13/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 14/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 15/20
998/998 [==============================] - 12s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 16/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 17/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 18/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 19/20
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 20/20
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[SGD]

일부의 데이터 샘플만 무작위로 추출하여 경사 하강법에 사용, 학습 속도 개선



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="SGD", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 14s 13ms/step - loss: nan - acc: 0.9034 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[Adadelta]



훈련 전반에 걸쳐 학습률이 지속적으로 감소.



과거의 모든 그래디언트를 누적하는 대신 그래디언트 업데이트의 이동 창을 기반으로 학습률을 조정. 많은 업데이트가 수행된 경우에도 계속 학습.



Adagrad에 비해 Adadelta는 초기 학습률을 설정할 필요가 없음



아다델타는 학습률이 0에 가까워지는 문제를 해결하기 위해 모든 그래디언트의 제곱합인 G값 대신에 이전 개수 만큼을 제곱하여 더한 값의 평균을 사용하여 학습을 진행합니다. 아다델타는 아다그라드의 수식에서 학습률을 가중치의 변화량 크기를 누적한 값으로 변환했기 때문에 학습률에 대한 하이퍼 파라미터가 필요하지 않습니다.



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))
model.compile(optimizer="Adadelta", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 14s 13ms/step - loss: nan - acc: 0.9033 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[Adagrad]



Adaptive Gradient의 합성 단어로 이 optimizer에서는 학습률이 매우 중요한 역할을 한다. 기존의 optimizer들에서는 학습률은 따로 건드리지 않았었는데 adagrad는 학습을 진행하면서 학습률을 점차 줄여가는 방법을 사용한다. 처음에는 크게 학습하다가 조금씩 작게 학습한다는 얘기로, 실제 신경망에서 많이 쓰이는 방식이다. 



​



많이 변화하지 않은 변수들은 학습률(step size)를 크게하고, 반대로 많이 변화한 변수들에 대해서는 학습률을 적게합니다. 이는 많이 변화한 변수는 최적값에 근접했을 것이라는 가정하에 작은 크기로 이동하면서 세밀한 값을 조정하고, 반대로 적게 변화한 변수들은 학습률을 크게하여 빠르게 loss값을 줄입니다.





‘Ada’ptive와 ‘Grad’ient의 합성어인 아다그라드는 적응형 경사하강법으로 업데이트 횟수에 따라 학습률을 조정하는 옵티마이저입니다. 아다그라드는 많이 변화하지 않는 변수들의 학습률은 크게 하고, 많이 변화하는 변수들의 학습률은 작게 합니다. 자세하게 살펴보면 기울기 크기가 누적되는 변수값 G(i)에 따라 파라미터가 변하는데 파라미터가 많이 학습되었으면 작은 학습률로 업데이터하고, 학습이 덜 되었으면 개선이 더 필요하기 때문에 높은 학습률로 업데이트되는 원리입니다.





​



아다그라드는 학습률을 조정해주지 않아도 적절한 학습률을 적용한다는 장점이 있지만 학습률이 점점 줄어들다가 반복 학습 이후에는 파라미터가 갱신되지 않는 문제가 있습니다.



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="Adagrad", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 14s 13ms/step - loss: nan - acc: 0.9034 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 12s 12ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[Adamax]



adam 모델에서 무한대로 진행하는 것을 기반.



임베딩 모델에서 adam보다 성능이 우수한 경우 빈번



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="Adamax", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 15s 14ms/step - loss: nan - acc: 0.9033 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
[Nadam]

nadam은 아담의 두 결합 요소중 하나인 모멘텀 대신에 네스테로프 모멘텀을 결합한 옵티마이저입니다. 아담과 다르게 Nadam은 현재 위치에서 Gradient 값을 계산하는 것이 아닌 모멘텀 방향으로 이동한 뒤 새로운 위치에서 Gradient 값을 계산하게 됩니다. (Nadam을 사용할 때는 모든 인자의 기본값 사용이 권장됩니다.)






```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="Nadam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2)
```

<pre>
Epoch 1/5
998/998 [==============================] - 16s 14ms/step - loss: nan - acc: 0.9033 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
# 초기 속도

# SGD>ADADELTA=ADAM>ADAGRAD>ADAMAX>NADAM

# 

# 초기 ACCURACY

# NADAM=SGD>ADADELTA=ADAGRAD=ADAMAX=ADAM

# 

# 전체 속도

# SGD>ADADELTA=ADAGRAD>ADAM>ADAMAX>NADAM

# 

# 속도에서는 SGD가 우수한 것으로 보이는데, 방대한 데이터를 빠르게 처리할 경우 SGD가 필요할 것 같습니다.

# 

# ACCURACY 면에서 초기에는 SGD와 NADAM이 우수해 보이나, 학습이 반복되면서 차이가 작아집니다.


[BatchNormalization]



정규화 하여 오차 적게 나올 수 있도록 사용



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(BatchNormalization())
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2) 
```

<pre>
Epoch 1/5
998/998 [==============================] - 15s 14ms/step - loss: nan - acc: 0.9034 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(BatchNormalization())
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2) 
```

<pre>
Epoch 1/5
998/998 [==============================] - 16s 14ms/step - loss: nan - acc: 0.9034 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 13s 13ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>

```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(LSTM(32))
model.add(Dense(1,input_dim=6,activation="softmax"))
model.add(BatchNormalization())

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2) 
```

<pre>
Epoch 1/5
998/998 [==============================] - 16s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 2/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 3/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 4/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
Epoch 5/5
998/998 [==============================] - 14s 14ms/step - loss: nan - acc: 0.9042 - val_loss: nan - val_acc: 0.9042
</pre>
# embedding layer, LSTM layer, Dense layer 에서 정규화의 시기는 이 데이터에서 accuracy에 크게 영향을 주지 않아 시간이 비교적 유리한 embedding 직후가 적합할 것으로 보입니다



```python
model=Sequential()
model.add(Embedding(len(TK.word_index)+1,3,input_length=250))
model.add(Dense(1,input_dim=6,activation="softmax"))

model.compile(optimizer="adam", loss="sparse_categorical_crossentropy", metrics='acc')
model.fit(x_train, y_train, epochs=5, batch_size=128, validation_data=(x_valid,y_valid))
result=model.predict(test2) 
```

<pre>
Epoch 1/5
998/998 [==============================] - 4s 4ms/step - loss: 5.5215 - acc: 0.0958 - val_loss: 5.5215 - val_acc: 0.0958
Epoch 2/5
998/998 [==============================] - 4s 4ms/step - loss: 5.5215 - acc: 0.0958 - val_loss: 5.5215 - val_acc: 0.0958
Epoch 3/5
998/998 [==============================] - 4s 4ms/step - loss: 5.5215 - acc: 0.0958 - val_loss: 5.5215 - val_acc: 0.0958
Epoch 4/5
998/998 [==============================] - 4s 4ms/step - loss: 5.5215 - acc: 0.0958 - val_loss: 5.5215 - val_acc: 0.0958
Epoch 5/5
998/998 [==============================] - 4s 4ms/step - loss: 5.5215 - acc: 0.0958 - val_loss: 5.5215 - val_acc: 0.0958
</pre>
위 case를 적용하였을 때, 2번 case에서 score 0.57450 나머지 case는 score 0.5000으로 동일하였습니다



# LSTM layer를 삭제할 경우, 이외의 조건이 동일할 때 보다 accuracy가 크게 저하되는데 이는 앞서 학습한 것에 대한 기억을 잃었기 때문입니다.

# 따라서 LSTM layer를 사용하는 것이 적합합니다.



```python
sub=pd.read_csv("/kaggle/input/jigsaw-toxic-comment-classification-challenge/sample_submission.csv.zip")
sub
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>toxic</th>
      <th>severe_toxic</th>
      <th>obscene</th>
      <th>threat</th>
      <th>insult</th>
      <th>identity_hate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>00001cee341fdb12</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0000247867823ef7</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>2</th>
      <td>00013b17ad220c46</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>3</th>
      <td>00017563c3f7919a</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>4</th>
      <td>00017695ad8997eb</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
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
    </tr>
    <tr>
      <th>153159</th>
      <td>fffcd0960ee309b5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>153160</th>
      <td>fffd7a9a6eb32c16</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>153161</th>
      <td>fffda9e8d6fafa9e</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>153162</th>
      <td>fffe8f1340a79fc2</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
    <tr>
      <th>153163</th>
      <td>ffffce3fb183ee80</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
      <td>0.5</td>
    </tr>
  </tbody>
</table>
<p>153164 rows × 7 columns</p>
</div>



```python
result.argmax(1)
```

<pre>
array([[0],
       [0],
       [0],
       ...,
       [0],
       [0],
       [0]])
</pre>

```python
sub["Toxic"]=result.argmax(1)
sub
sub.to_csv('submission.csv',index=0)
```

ERROR: Could not parse '' into expected type of Double (Line 2, Column 18)

와 같은 ERR를 해결 하고자 sub['toxic']=result.argmax로 수정하였습니다.

