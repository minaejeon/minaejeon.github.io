# 2. tokenization experiment 2 : NLTK, Text tokenizer of Keras (Kaggle Fake and real news Dataset)

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


/kaggle/input/fake-and-real-news-dataset/True.csv
/kaggle/input/fake-and-real-news-dataset/Fake.csv


```python
true=pd.read_csv("/kaggle/input/fake-and-real-news-dataset/True.csv")
fake=pd.read_csv("/kaggle/input/fake-and-real-news-dataset/Fake.csv")
display(true,fake)
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>text</th>
      <th>subject</th>
      <th>date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>As U.S. budget fight looms, Republicans flip t...</td>
      <td>WASHINGTON (Reuters) - The head of a conservat...</td>
      <td>politicsNews</td>
      <td>December 31, 2017</td>
    </tr>
    <tr>
      <th>1</th>
      <td>U.S. military to accept transgender recruits o...</td>
      <td>WASHINGTON (Reuters) - Transgender people will...</td>
      <td>politicsNews</td>
      <td>December 29, 2017</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Senior U.S. Republican senator: 'Let Mr. Muell...</td>
      <td>WASHINGTON (Reuters) - The special counsel inv...</td>
      <td>politicsNews</td>
      <td>December 31, 2017</td>
    </tr>
    <tr>
      <th>3</th>
      <td>FBI Russia probe helped by Australian diplomat...</td>
      <td>WASHINGTON (Reuters) - Trump campaign adviser ...</td>
      <td>politicsNews</td>
      <td>December 30, 2017</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Trump wants Postal Service to charge 'much mor...</td>
      <td>SEATTLE/WASHINGTON (Reuters) - President Donal...</td>
      <td>politicsNews</td>
      <td>December 29, 2017</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>21412</th>
      <td>'Fully committed' NATO backs new U.S. approach...</td>
      <td>BRUSSELS (Reuters) - NATO allies on Tuesday we...</td>
      <td>worldnews</td>
      <td>August 22, 2017</td>
    </tr>
    <tr>
      <th>21413</th>
      <td>LexisNexis withdrew two products from Chinese ...</td>
      <td>LONDON (Reuters) - LexisNexis, a provider of l...</td>
      <td>worldnews</td>
      <td>August 22, 2017</td>
    </tr>
    <tr>
      <th>21414</th>
      <td>Minsk cultural hub becomes haven from authorities</td>
      <td>MINSK (Reuters) - In the shadow of disused Sov...</td>
      <td>worldnews</td>
      <td>August 22, 2017</td>
    </tr>
    <tr>
      <th>21415</th>
      <td>Vatican upbeat on possibility of Pope Francis ...</td>
      <td>MOSCOW (Reuters) - Vatican Secretary of State ...</td>
      <td>worldnews</td>
      <td>August 22, 2017</td>
    </tr>
    <tr>
      <th>21416</th>
      <td>Indonesia to buy $1.14 billion worth of Russia...</td>
      <td>JAKARTA (Reuters) - Indonesia will buy 11 Sukh...</td>
      <td>worldnews</td>
      <td>August 22, 2017</td>
    </tr>
  </tbody>
</table>
<p>21417 rows × 4 columns</p>
</div>


<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>text</th>
      <th>subject</th>
      <th>date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Donald Trump Sends Out Embarrassing New Year’...</td>
      <td>Donald Trump just couldn t wish all Americans ...</td>
      <td>News</td>
      <td>December 31, 2017</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Drunk Bragging Trump Staffer Started Russian ...</td>
      <td>House Intelligence Committee Chairman Devin Nu...</td>
      <td>News</td>
      <td>December 31, 2017</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Sheriff David Clarke Becomes An Internet Joke...</td>
      <td>On Friday, it was revealed that former Milwauk...</td>
      <td>News</td>
      <td>December 30, 2017</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Trump Is So Obsessed He Even Has Obama’s Name...</td>
      <td>On Christmas day, Donald Trump announced that ...</td>
      <td>News</td>
      <td>December 29, 2017</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Pope Francis Just Called Out Donald Trump Dur...</td>
      <td>Pope Francis used his annual Christmas Day mes...</td>
      <td>News</td>
      <td>December 25, 2017</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>23476</th>
      <td>McPain: John McCain Furious That Iran Treated ...</td>
      <td>21st Century Wire says As 21WIRE reported earl...</td>
      <td>Middle-east</td>
      <td>January 16, 2016</td>
    </tr>
    <tr>
      <th>23477</th>
      <td>JUSTICE? Yahoo Settles E-mail Privacy Class-ac...</td>
      <td>21st Century Wire says It s a familiar theme. ...</td>
      <td>Middle-east</td>
      <td>January 16, 2016</td>
    </tr>
    <tr>
      <th>23478</th>
      <td>Sunnistan: US and Allied ‘Safe Zone’ Plan to T...</td>
      <td>Patrick Henningsen  21st Century WireRemember ...</td>
      <td>Middle-east</td>
      <td>January 15, 2016</td>
    </tr>
    <tr>
      <th>23479</th>
      <td>How to Blow $700 Million: Al Jazeera America F...</td>
      <td>21st Century Wire says Al Jazeera America will...</td>
      <td>Middle-east</td>
      <td>January 14, 2016</td>
    </tr>
    <tr>
      <th>23480</th>
      <td>10 U.S. Navy Sailors Held by Iranian Military ...</td>
      <td>21st Century Wire says As 21WIRE predicted in ...</td>
      <td>Middle-east</td>
      <td>January 12, 2016</td>
    </tr>
  </tbody>
</table>
<p>23481 rows × 4 columns</p>
</div>



```python
true["target"]=1
fake["target"]=0
data=pd.concat([true,fake])
data
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>text</th>
      <th>subject</th>
      <th>date</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>As U.S. budget fight looms, Republicans flip t...</td>
      <td>WASHINGTON (Reuters) - The head of a conservat...</td>
      <td>politicsNews</td>
      <td>December 31, 2017</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>U.S. military to accept transgender recruits o...</td>
      <td>WASHINGTON (Reuters) - Transgender people will...</td>
      <td>politicsNews</td>
      <td>December 29, 2017</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Senior U.S. Republican senator: 'Let Mr. Muell...</td>
      <td>WASHINGTON (Reuters) - The special counsel inv...</td>
      <td>politicsNews</td>
      <td>December 31, 2017</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>FBI Russia probe helped by Australian diplomat...</td>
      <td>WASHINGTON (Reuters) - Trump campaign adviser ...</td>
      <td>politicsNews</td>
      <td>December 30, 2017</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Trump wants Postal Service to charge 'much mor...</td>
      <td>SEATTLE/WASHINGTON (Reuters) - President Donal...</td>
      <td>politicsNews</td>
      <td>December 29, 2017</td>
      <td>1</td>
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
      <th>23476</th>
      <td>McPain: John McCain Furious That Iran Treated ...</td>
      <td>21st Century Wire says As 21WIRE reported earl...</td>
      <td>Middle-east</td>
      <td>January 16, 2016</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23477</th>
      <td>JUSTICE? Yahoo Settles E-mail Privacy Class-ac...</td>
      <td>21st Century Wire says It s a familiar theme. ...</td>
      <td>Middle-east</td>
      <td>January 16, 2016</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23478</th>
      <td>Sunnistan: US and Allied ‘Safe Zone’ Plan to T...</td>
      <td>Patrick Henningsen  21st Century WireRemember ...</td>
      <td>Middle-east</td>
      <td>January 15, 2016</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23479</th>
      <td>How to Blow $700 Million: Al Jazeera America F...</td>
      <td>21st Century Wire says Al Jazeera America will...</td>
      <td>Middle-east</td>
      <td>January 14, 2016</td>
      <td>0</td>
    </tr>
    <tr>
      <th>23480</th>
      <td>10 U.S. Navy Sailors Held by Iranian Military ...</td>
      <td>21st Century Wire says As 21WIRE predicted in ...</td>
      <td>Middle-east</td>
      <td>January 12, 2016</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>44898 rows × 5 columns</p>
</div>



```python
data["text"][3]
```


3    WASHINGTON (Reuters) - Trump campaign adviser ...
3    On Christmas day, Donald Trump announced that ...
Name: text, dtype: object

---------------
Kaggle Spam Mails Dataset에서는 NLTK와 Keras에서 제공하는 Text 토큰화 실험을 진행하였습니다.

이번에는 다른 Kaggle Fake and real news Dataset에 동일하게 적용하고, 각 모델의 장단점을 추가로 분석하겠습니다.

또한, Pretrain 방식을 이용하여 단어별 학습된 의미를 상황에 맞게 적절히 적용하는 방식을 실험해 보겠습니다.

첫째, NLTK의 word_tokenize를 적용하였습니다.

----------------


```python
import nltk
from nltk.tokenize import word_tokenize
TK=word_tokenize
text=data["text"]
tk_result=TK(str(text))
tk_result
```

['0',
 'WASHINGTON',
 '(',
 'Reuters',
 ')',
 '-',
 'The',
 'head',
 'of',
 'a',
 'conservat',
 '...',
 '1',
 'WASHINGTON',
 '(',
 'Reuters',
 ')',
 '-',
 'Transgender',
 'people',
 'will',
 '...',
 '2',
 'WASHINGTON',
 '(',
 'Reuters',
 ')',
 '-',
 'The',
 'special',
 'counsel',
 'inv',
 '...',
 '3',
 'WASHINGTON',
 '(',
 'Reuters',
 ')',
 '-',
 'Trump',
 'campaign',
 'adviser',
 '...',
 '4',
 'SEATTLE/WASHINGTON',
 '(',
 'Reuters',
 ')',
 '-',
 'President',
 'Donal',
 '...',
 '...',
 '23476',
 '21st',
 'Century',
 'Wire',
 'says',
 'As',
 '21WIRE',
 'reported',
 'earl',
 '...',
 '23477',
 '21st',
 'Century',
 'Wire',
 'says',
 'It',
 's',
 'a',
 'familiar',
 'theme',
 '.',
 '...',
 '23478',
 'Patrick',
 'Henningsen',
 '21st',
 'Century',
 'WireRemember',
 '...',
 '23479',
 '21st',
 'Century',
 'Wire',
 'says',
 'Al',
 'Jazeera',
 'America',
 'will',
 '...',
 '23480',
 '21st',
 'Century',
 'Wire',
 'says',
 'As',
 '21WIRE',
 'predicted',
 'in',
 '...',
 'Name',
 ':',
 'text',
 ',',
 'Length',
 ':',
 '44898',
 ',',
 'dtype',
 ':',
 'object']

-------------
index의 number와 '-'하이픈까지 모두 하나의 독립된 의미단위로 분류하였습니다.

text의 정확한 분류에는 기여될 수 있으나 분석 속도가 느리기 때문에 비효율적으로 보입니다.

둘째, TreebankWordTokenizer를 적용하겠습니다. 


--------------

```python
from nltk.tokenize import TreebankWordTokenizer
TK = TreebankWordTokenizer()
tk_result = data['text'].apply(TK.tokenize)
tk_result
```


['0        WASHINGTON (Reuters) - The head of a conservat...



\n1        WASHINGTON (Reuters) - Transgender people will...



\n2        WASHINGTON (Reuters) - The special counsel inv...



\n3        WASHINGTON (Reuters) - Trump campaign adviser ...



\n4        SEATTLE/WASHINGTON (Reuters) - President Donal...



\n                               ...                        



\n23476    21st Century Wire says As 21WIRE reported earl...



\n23477    21st Century Wire says It s a familiar theme.',

 '...

 

 \n23478    Patrick Henningsen  21st Century WireRemember ...

 

 \n23479    21st Century Wire says Al Jazeera America will...

 

 \n23480    21st Century Wire says As 21WIRE predicted in ...

 

 \nName: text, Length: 44898, dtype: object']
 

-------------------
word_tokenize에 비해 의미가 없는 기호를 독립적인 의미 단위로 구분하지 않음으로써 Text 분석의 효율성은 높일 수 있을 것으로 보입니다.

그러나 이는 같은 의미의 단어이나 기호의 추가 여부에 따라 다른 단위로 구분하는 문제가 생기지 않을까 고민하게 되었습니다.

따라서 세번째, 문장단위로 text를 토큰화하면 문맥이 중요한 요소로 작용하기 때문에, 분석에 보다 정확성을 높일 수 있을지 확인해 보겠습니다.

----------------------


```python
from nltk.tokenize import sent_tokenize
text=data["text"]
TK=sent_tokenize
tk_result=TK(str(data['text']))
tk_result
```


['0        WASHINGTON (Reuters) - The head of a conservat...\n1        WASHINGTON (Reuters) - Transgender people will...\n2        WASHINGTON (Reuters) - The special counsel inv...\n3        WASHINGTON (Reuters) - Trump campaign adviser ...\n4        SEATTLE/WASHINGTON (Reuters) - President Donal...\n                               ...                        \n23476    21st Century Wire says As 21WIRE reported earl...\n23477    21st Century Wire says It s a familiar theme.',
 '...\n23478    Patrick Henningsen  21st Century WireRemember ...\n23479    21st Century Wire says Al Jazeera America will...\n23480    21st Century Wire says As 21WIRE predicted in ...\nName: text, Length: 44898, dtype: object']

--------------------
단순히 '-','.'와 같은 기호로 분류하지 않은 점에서 토큰화의 완성도가 높아보입니다.

토큰화 단위를 '문장'으로 설정할 경우, '단어' 단위보다 학습시 문맥에 맞는 정확도로 토큰화 할 수 있다는 장점이 보입니다.

그러나 학습에 사용되지 않은 문장을 이용하여 NEWS의 FAKE OR TRUTH 여부를 판별하려면 학습 빈도가 낮아 유연성이 낮아질 우려가 있습니다.

작은 단어 단위로 토큰화하면 문맥상의 정확한 의미를 학습/예측하기가 어렵고 문장 단위로 토큰화하면 정확히 예측할 수 있는 데이터에 한계를 갖게 됩니다.

# 이를 모두 보완할 수 있는 방법에 고민하게 되었고, 단어 단위로 토큰화하되 문맥 파악 학습이 추가되면 좋겠다는 생각이 들었습니다.

넷째, Keras의 Tokenizer를 이용하여 단어 단위의 토큰화를 진행하고 빈도순으로 정렬해 보겠습니다.

-----------------------


```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
tk_result=TK.fit_on_texts(data["text"])
TK.word_index
```


{'the': 1,
 'to': 2,
 'of': 3,
 'a': 4,
 'and': 5,
 'in': 6,
 'that': 7,
 's': 8,
 'on': 9,
 'for': 10,
 'is': 11,
 'said': 12,
 ...
 'debt': 984,
 'convention': 985,
 'giving': 986,
 '14': 987,
 'secret': 988,
 '16': 989,
 'speak': 990,
 'forced': 991,
 'relationship': 992,
 'fear': 993,
 'push': 994,
 'proposed': 995,
 'created': 996,
 'helped': 997,
 'phone': 998,
 'incident': 999,
 'repeatedly': 1000,
 ...}

---------


```python
sequence=TK.texts_to_sequences(data["text"])
print(text[3])
```

3    WASHINGTON (Reuters) - Trump campaign adviser ...
3    On Christmas day, Donald Trump announced that ...
Name: text, dtype: object

```python
pd.Series(sequence)
```

0        [107, 67, 1, 441, 3, 4, 317, 79, 6288, 6, 1, 3...
1        [107, 67, 1549, 45, 39, 22, 752, 10, 1, 104, 9...
2        [107, 67, 1, 524, 1366, 275, 3, 2102, 164, 152...
3        [107, 67, 15, 96, 878, 743, 6493, 87, 30, 3283...
4        [3927, 107, 67, 36, 70, 15, 156, 9, 1, 37, 8, ...
                               ...                        
44893    [1013, 754, 1005, 199, 18, 1102, 283, 383, 26,...
44894    [1013, 754, 1005, 199, 14, 8, 4, 1597, 4478, 5...
44895    [2384, 4378, 1013, 754, 87842, 60, 1, 77, 155,...
44896    [1013, 754, 1005, 199, 343, 11426, 160, 39, 20...
44897    [1013, 754, 1005, 199, 18, 1102, 4014, 6, 64, ...
Length: 44898, dtype: object

pd.Series(text).apply(len).max

```python
import seaborn as sns
import matplotlib.pyplot as plt
plt.figure(figsize=(16,8))
sns.displot(pd.Series(sequence).apply(len))
plt.xlim(0,20000)
```

(0.0, 20000.0)
<Figure size 1152x576 with 0 Axes>
![image](https://user-images.githubusercontent.com/69743938/172044885-5cf35e2f-4b06-4d23-978f-04bf025e992a.png)

```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(text,maxlen=1750)
pad_text
```

--------------
# 단어 단위의 토큰화를 진행하고, 예측의 유연성을 확보하고자 pretrain을 추가하겠습니다.

facebook에서 제공하는 300차원의 vector를 이용하여 pretrain 하기 위해 먼저 load하여 embedding 값으로 넣어줍니다.

embeddings의 값을 {}로 먼저 비워 준 뒤, 각 line의 value 값을 학습할 예정입니다.

해당 데이터를 보면 line 마지막에 여백이 많이 있어, rstrip().split()처리하여 줍니다.

-----------------------
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
{'2000000': array([ 2.0600e-02,  1.9530e-01, -9.0400e-02, -3.5390e-01, -6.2700e-02,
        -1.4600e-02, -1.3150e-01,  5.8600e-02,  5.9930e-01,  6.3100e-02,
        -9.3200e-02,  7.1720e-01, -3.4950e-01, -6.1100e-02, -3.0790e-01,
         3.6940e-01, -2.5880e-01, -3.0210e-01, -1.2800e-02,  3.2680e-01,
         6.9900e-02,  8.9400e-02, -1.1910e-01, -1.1900e-01, -1.2200e-01,
        -4.5400e-02, -2.5100e-02, -1.7630e-01,  7.6370e-01, -8.4900e-02,
        -4.1930e-01,  3.0050e-01, -9.8500e-02,  1.6770e-01, -2.0570e-01,
        -1.8150e-01, -2.7360e-01,  3.7540e-01, -6.6400e-02,  1.7150e-01,
         4.6900e-01,  3.0410e-01,  1.8830e-01,  1.0950e-01,  4.7590e-01,
         1.1540e-01, -2.9670e-01, -3.4600e-02,  1.4270e-01,  4.1870e-01,
         1.2770e-01,  1.7650e-01,  7.1670e-01,  5.0060e-01, -5.6000e-03,
        -1.0700e-01, -3.6280e-01,  5.4290e-01,  1.0060e-01, -4.4410e-01,
        -6.2800e-02, -3.6000e-03,  8.1900e-02, -4.5830e-01,  8.3400e-02,
        -9.4100e-02,  7.5100e-02,  3.7370e-01, -1.0820e-01, -1.5300e-02,
        -1.3900e-02, -5.9000e-02, -1.1600e-02, -8.0970e-01, -1.6890e-01,
         6.1260e-01,  1.5200e-02, -1.7120e-01, -2.8400e-01,  3.7140e-01,
         9.0600e-02,  2.4040e-01, -1.2440e-01, -3.8910e-01,  4.1730e-01,
        -9.1600e-02,  6.1100e-02,  5.9410e-01, -6.5990e-01, -1.0140e-01,
         2.5740e-01,  5.5680e-01, -1.1930e-01, -3.3940e-01, -3.7260e-01,
         2.3520e-01,  8.0200e-02, -2.4910e-01,  9.8300e-02, -1.0260e-01,
        -3.4620e-01,  2.9500e-02, -1.8830e-01,  1.1920e-01, -2.3710e-01,
         1.2340e-01, -1.1770e-01, -6.8190e-01,  4.2390e-01,  2.9710e-01,
         3.3000e-03,  7.3810e-01,  2.5250e-01, -2.3500e-02, -1.1836e+00,
         2.6000e-01,  3.4200e-02, -3.9810e-01, -1.6400e-02,  5.1290e-01,
        -3.8360e-01,  1.9830e-01, -1.1460e-01,  6.3550e-01, -2.4790e-01,
        -3.6190e-01,  2.9730e-01,  2.0180e-01,  3.4330e-01, -1.4460e-01,
        -4.3870e-01, -5.8100e-02, -5.0000e-04, -3.7000e-03, -2.1090e-01,
         4.8070e-01, -1.0980e-01, -5.1590e-01,  4.5390e-01, -4.3330e-01,
        -3.4400e-02, -5.1200e-02, -5.4900e-02, -1.2420e-01, -4.4240e-01,
         3.4240e-01,  2.6360e-01, -1.6450e-01, -2.0510e-01,  7.4400e-02,
        -1.0000e-02, -1.3730e-01,  1.5960e-01,  1.7360e-01,  1.6860e-01,
         1.7930e-01,  1.4980e-01, -6.2220e-01, -1.0770e-01,  1.0280e-01,
         1.9820e-01, -4.5300e-02,  4.6940e-01, -6.5300e-02,  1.5870e-01,
        -1.6720e-01,  1.2900e-01,  1.4300e-02, -3.1500e-01,  2.2580e-01,
        -1.0060e-01,  1.8500e-01, -1.1890e-01, -5.5900e-02, -5.3770e-01,
         1.4140e-01,  1.0650e-01, -4.0230e-01,  1.2630e-01, -4.7200e-01,
        -3.2660e-01, -3.9080e-01,  9.8900e-02,  3.2510e-01, -1.4740e-01,
        -3.4340e-01, -1.5780e-01, -1.8930e-01,  3.0170e-01, -3.4050e-01,
         5.4000e-02,  2.8060e-01, -1.2340e-01,  2.7000e-03,  3.2030e-01,
        -9.6500e-02, -6.0200e-02, -6.2000e-02, -1.7620e-01,  6.4070e-01,
         3.7880e-01, -4.9060e-01,  3.8680e-01,  8.6400e-02, -3.3680e-01,
         1.1080e-01,  2.8830e-01,  1.3520e-01, -5.7200e-01,  1.9780e-01,
         2.3600e-02,  7.1200e-01, -3.9950e-01,  4.6000e-03,  4.3200e-02,
        -4.8900e-02, -2.9160e-01, -2.0000e-04,  1.1090e-01, -1.5390e-01,
        -1.2050e-01, -1.2800e-01, -7.8000e-03, -1.8050e-01, -2.0700e-02,
        -9.9000e-03, -3.7150e-01,  2.7100e-02, -2.2270e-01, -8.9000e-03,
        -8.9000e-02, -5.5720e-01, -2.4770e-01, -4.4550e-01, -8.7900e-02,
        -6.7630e-01, -2.3920e-01, -1.7040e-01,  1.1927e+00, -1.3530e-01,
        -3.0590e-01, -2.5380e-01,  1.7630e-01, -4.0400e-02,  2.4220e-01,
         3.2290e-01,  1.6560e-01,  3.5260e-01, -2.6600e-02,  3.1970e-01,
        -3.2930e-01, -6.9840e-01,  3.7960e-01, -5.2400e-02, -1.6880e-01,
         1.7040e-01,  6.2400e-02, -2.0740e-01,  4.8760e-01,  2.0620e-01,
         6.4120e-01, -3.0160e-01, -1.2510e-01, -4.5100e-02,  8.5560e-01,
         1.5600e-02,  3.5630e-01,  2.1720e-01, -5.8000e-03,  4.1010e-01,
        -1.7880e-01, -3.2000e-02, -3.3430e-01,  1.2940e-01, -3.1430e-01,
         3.2600e-01,  2.4230e-01,  2.8470e-01, -2.1530e-01,  5.3850e-01,
         1.6840e-01, -4.1220e-01, -7.6000e-03,  3.7700e-02, -6.5370e-01,
         3.2410e-01, -9.1000e-02,  2.6290e-01, -1.7060e-01,  1.6000e-03,
         2.4310e-01,  5.3520e-01, -3.7310e-01,  2.5800e-01,  2.6100e-01,
        -4.5380e-01, -2.9440e-01,  5.2330e-01, -3.7930e-01, -1.9200e-02],
       dtype=float32),
 ',': array([-2.820e-02, -5.570e-02, -4.510e-02, -4.340e-02,  7.120e-02,
        -8.550e-02, -1.085e-01, -5.610e-02, -4.523e-01, -2.020e-02,
         9.750e-02,  1.047e-01,  1.962e-01, -6.930e-02,  2.130e-02,
        -2.350e-02,  1.336e-01, -4.200e-02, -5.640e-02, -7.980e-02,
         4.240e-02, -4.090e-02, -5.360e-02, -2.520e-02,  1.350e-02,
         6.400e-03,  1.235e-01,  4.610e-02,  1.200e-02, -3.720e-02,
         6.500e-02,  4.100e-03, -1.074e-01, -2.630e-02,  1.133e-01,
        -2.900e-03,  6.710e-02,  1.065e-01,  2.340e-02, -1.600e-02,
         7.000e-03,  4.355e-01, -7.520e-02, -4.328e-01,  4.570e-02,
         6.040e-02, -7.400e-02, -5.500e-03, -8.900e-03, -2.926e-01,
        -5.450e-02, -1.519e-01,  9.900e-02, -1.930e-02, -5.000e-03,
         5.110e-02,  4.040e-02,  1.023e-01, -1.280e-02,  4.880e-02,
        -1.567e-01, -7.590e-02, -1.900e-02,  1.442e-01,  4.700e-03,
        -1.860e-02,  1.400e-02, -3.850e-02, -8.530e-02,  1.572e-01,
         1.770e-01,  8.400e-03, -2.500e-02, -1.145e-01, -6.630e-02,
        -1.244e-01, -3.977e-01, -1.240e-02, -4.586e-01, -2.200e-02,
         5.746e-01,  2.180e-02, -7.540e-02,  9.900e-03,  3.970e-02,
         {'2000000': array([ 2.0600e-02,  1.9530e-01, -9.0400e-02, -3.5390e-01, -6.2700e-02,
        -1.4600e-02, -1.3150e-01,  5.8600e-02,  5.9930e-01,  6.3100e-02,
        -9.3200e-02,  7.1720e-01, -3.4950e-01, -6.1100e-02, -3.0790e-01,
         3.6940e-01, -2.5880e-01, -3.0210e-01, -1.2800e-02,  3.2680e-01,
         6.9900e-02,  8.9400e-02, -1.1910e-01, -1.1900e-01, -1.2200e-01,
        -4.5400e-02, -2.5100e-02, -1.7630e-01,  7.6370e-01, -8.4900e-02,
        -4.1930e-01,  3.0050e-01, -9.8500e-02,  1.6770e-01, -2.0570e-01,
        -1.8150e-01, -2.7360e-01,  3.7540e-01, -6.6400e-02,  1.7150e-01,
         4.6900e-01,  3.0410e-01,  1.8830e-01,  1.0950e-01,  4.7590e-01,
         1.1540e-01, -2.9670e-01, -3.4600e-02,  1.4270e-01,  4.1870e-01,
         1.2770e-01,  1.7650e-01,  7.1670e-01,  5.0060e-01, -5.6000e-03,
        -1.0700e-01, -3.6280e-01,  5.4290e-01,  1.0060e-01, -4.4410e-01,
        -6.2800e-02, -3.6000e-03,  8.1900e-02, -4.5830e-01,  8.3400e-02,
        -9.4100e-02,  7.5100e-02,  3.7370e-01, -1.0820e-01, -1.5300e-02,
        -1.3900e-02, -5.9000e-02, -1.1600e-02, -8.0970e-01, -1.6890e-01,
         6.1260e-01,  1.5200e-02, -1.7120e-01, -2.8400e-01,  3.7140e-01,
         9.0600e-02,  2.4040e-01, -1.2440e-01, -3.8910e-01,  4.1730e-01,
        -9.1600e-02,  6.1100e-02,  5.9410e-01, -6.5990e-01, -1.0140e-01,
         2.5740e-01,  5.5680e-01, -1.1930e-01, -3.3940e-01, -3.7260e-01,
         2.3520e-01,  8.0200e-02, -2.4910e-01,  9.8300e-02, -1.0260e-01,
        -3.4620e-01,  2.9500e-02, -1.8830e-01,  1.1920e-01, -2.3710e-01,
         1.2340e-01, -1.1770e-01, -6.8190e-01,  4.2390e-01,  2.9710e-01,
         3.3000e-03,  7.3810e-01,  2.5250e-01, -2.3500e-02, -1.1836e+00,
         2.6000e-01,  3.4200e-02, -3.9810e-01, -1.6400e-02,  5.1290e-01,
        -3.8360e-01,  1.9830e-01, -1.1460e-01,  6.3550e-01, -2.4790e-01,
        -3.6190e-01,  2.9730e-01,  2.0180e-01,  3.4330e-01, -1.4460e-01,
        -4.3870e-01, -5.8100e-02, -5.0000e-04, -3.7000e-03, -2.1090e-01,
         4.8070e-01, -1.0980e-01, -5.1590e-01,  4.5390e-01, -4.3330e-01,
        -3.4400e-02, -5.1200e-02, -5.4900e-02, -1.2420e-01, -4.4240e-01,
         3.4240e-01,  2.6360e-01, -1.6450e-01, -2.0510e-01,  7.4400e-02,
        -1.0000e-02, -1.3730e-01,  1.5960e-01,  1.7360e-01,  1.6860e-01,
         1.7930e-01,  1.4980e-01, -6.2220e-01, -1.0770e-01,  1.0280e-01,
         1.9820e-01, -4.5300e-02,  4.6940e-01, -6.5300e-02,  1.5870e-01,
        -1.6720e-01,  1.2900e-01,  1.4300e-02, -3.1500e-01,  2.2580e-01,
        -1.0060e-01,  1.8500e-01, -1.1890e-01, -5.5900e-02, -5.3770e-01,
         1.4140e-01,  1.0650e-01, -4.0230e-01,  1.2630e-01, -4.7200e-01,
        -3.2660e-01, -3.9080e-01,  9.8900e-02,  3.2510e-01, -1.4740e-01,
        -3.4340e-01, -1.5780e-01, -1.8930e-01,  3.0170e-01, -3.4050e-01,
         5.4000e-02,  2.8060e-01, -1.2340e-01,  2.7000e-03,  3.2030e-01,
        -9.6500e-02, -6.0200e-02, -6.2000e-02, -1.7620e-01,  6.4070e-01,
         3.7880e-01, -4.9060e-01,  3.8680e-01,  8.6400e-02, -3.3680e-01,
         1.1080e-01,  2.8830e-01,  1.3520e-01, -5.7200e-01,  1.9780e-01,
         2.3600e-02,  7.1200e-01, -3.9950e-01,  4.6000e-03,  4.3200e-02,
        -4.8900e-02, -2.9160e-01, -2.0000e-04,  1.1090e-01, -1.5390e-01,
        -1.2050e-01, -1.2800e-01, -7.8000e-03, -1.8050e-01, -2.0700e-02,
        -9.9000e-03, -3.7150e-01,  2.7100e-02, -2.2270e-01, -8.9000e-03,
        -8.9000e-02, -5.5720e-01, -2.4770e-01, -4.4550e-01, -8.7900e-02,
        -6.7630e-01, -2.3920e-01, -1.7040e-01,  1.1927e+00, -1.3530e-01,
        -3.0590e-01, -2.5380e-01,  1.7630e-01, -4.0400e-02,  2.4220e-01,
         3.2290e-01,  1.6560e-01,  3.5260e-01, -2.6600e-02,  3.1970e-01,
        -3.2930e-01, -6.9840e-01,  3.7960e-01, -5.2400e-02, -1.6880e-01,
         1.7040e-01,  6.2400e-02, -2.0740e-01,  4.8760e-01,  2.0620e-01,
         6.4120e-01, -3.0160e-01, -1.2510e-01, -4.5100e-02,  8.5560e-01,
         1.5600e-02,  3.5630e-01,  2.1720e-01, -5.8000e-03,  4.1010e-01,
        -1.7880e-01, -3.2000e-02, -3.3430e-01,  1.2940e-01, -3.1430e-01,
         3.2600e-01,  2.4230e-01,  2.8470e-01, -2.1530e-01,  5.3850e-01,
         1.6840e-01, -4.1220e-01, -7.6000e-03,  3.7700e-02, -6.5370e-01,
         3.2410e-01, -9.1000e-02,  2.6290e-01, -1.7060e-01,  1.6000e-03,
         2.4310e-01,  5.3520e-01, -3.7310e-01,  2.5800e-01,  2.6100e-01,
        -4.5380e-01, -2.9440e-01,  5.2330e-01, -3.7930e-01, -1.9200e-02],
       dtype=float32),
 ',': array([-2.820e-02, -5.570e-02, -4.510e-02, -4.340e-02,  7.120e-02,
        -8.550e-02, -1.085e-01, -5.610e-02, -4.523e-01, -2.020e-02,
         9.750e-02,  1.047e-01,  1.962e-01, -6.930e-02,  2.130e-02,
        -2.350e-02,  1.336e-01, -4.200e-02, -5.640e-02, -7.980e-02,
         4.240e-02, -4.090e-02, -5.360e-02, -2.520e-02,  1.350e-02,
         6.400e-03,  1.235e-01,  4.610e-02,  1.200e-02, -3.720e-02,
         6.500e-02,  4.100e-03, -1.074e-01, -2.630e-02,  1.133e-01,
        -2.900e-03,  6.710e-02,  1.065e-01,  2.340e-02, -1.600e-02,
         7.000e-03,  4.355e-01, -7.520e-02, -4.328e-01,  4.570e-02,
         6.040e-02, -7.400e-02, -5.500e-03, -8.900e-03, -2.926e-01,
        -5.450e-02, -1.519e-01,  9.900e-02, -1.930e-02, -5.000e-03,
         5.110e-02,  4.040e-02,  1.023e-01, -1.280e-02,  4.880e-02,
        -1.567e-01, -7.590e-02, -1.900e-02,  1.442e-01,  4.700e-03,
        -1.860e-02,  1.400e-02, -3.850e-02, -8.530e-02,  1.572e-01,
         1.770e-01,  8.400e-03, -2.500e-02, -1.145e-01, -6.630e-02,
        -1.244e-01, -3.977e-01, -1.240e-02, -4.586e-01, -2.200e-02,
         5.746e-01,  2.180e-02, -7.540e-02,  9.900e-03,  3.970e-02,


```python
TK.word_index.items()
```

dict_items([('the', 1), ('to', 2), ('of', 3), ('a', 4), ('and', 5), ('in', 6), ('that', 7), ('s', 8), ('on', 9), ('for', 10), ('is', 11), ('said', 12), ('he', 13), ('it', 14), ('trump', 15), ('with', 16), ('was', 17), ('as', 18), ('his', 19), ('by', 20), ('has', 21), ('be', 22), ('have', 23), ('not', 24), ('from', 25), ('this', 26), ('at', 27), ('are', 28), ('who', 29), ('an', 30), ('they', 31), ('but', 32), ('i', 33), ('we', 34), ('would', 35), ('president', 36), ('u', 37), ('about', 38), ('will', 39), ('t', 40), ('their', 41), ('had', 42), ('you', 43), ('been', 44), ('people', 45), ('were', 46), ('”', 47), ('or', 48), ('more', 49), ('which', 50), ('she', 51), ('one', 52), ('after', 53), ('her', 54), ('all', 55), ('if', 56), ('out', 57), ('state', 58), ('what', 59), ('when', 60), ('also', 61), ('up', 62), ('new', 63), ('its', 64), ('there', 65), ('no', 66), ('reuters', 67), ('over', 68), ('so', 69), ('donald', 70), ('government', 71), ('house', 72), ('our', 73), ('clinton', 74), ('states', 75), ('can', 76), ('obama', 77), ('him', 78), ('republican', 79), ('than', 80), ('other', 81), ('just', 82), ('some', 83), ('year', 84), ('could', 85), ('united', 86), ('told', 87), ('into', 88), ('like', 89), ('white', 90), ('do', 91), ('against', 92), ('them', 93), ('two', 94), ('because', 95), ('campaign', 96), ('time', 97), ('election', 98), ('last', 99), ('now', 100), ('news', 101), ('any', 102), ('party', 103), ('first', 104), ('how', 105), ('only', 106), ('washington', 107), ('former', 108), ('while', 109), ('even', 110), ('country', 111), ('being', 112), ('should', 113), ('us', 114), ('during', 115), ('did', 116), ('hillary', 117), ('before', 118), ('years', 119), ('many', 120), ('american', 121), ('media', 122), ('most', 123), ('security', 124), ('law', 125), ('made', 126), ('may', 127), ('national', 128), ('say', 129), ('political', 130), ('police', 131), ('those', 132), ('get', 133), ('right', 134), ('since', 135), ('make', 136), ('court', 137), ('percent', 138), ('where', 139), ('twitter', 140), ('according', 141), ('going', 142), ('republicans', 143), ('under', 144), ('back', 145), ('these', 146), ('here', 147), ('presidential', 148), ('then', 149), ('re', 150), ('very', 151), ('russia', 152), ('via', 153), ('democratic', 154), ('administration', 155), ('called', 156), ('bill', 157), ('week', 158), ('support', 159), ('america', 160), ('down', 161), ('vote', 162), ('senate', 163), ('between', 164), ('way', 165), ('including', 166), ('know', 167), ('think', 168), ('group', 169), ('north', 170), ('officials', 171), ('office', 172), ('well', 173), ('public', 174), ('take', 175), ('such', 176), ('federal', 177), ('world', 178), ('military', 179), ('foreign', 180), ('my', 181), ('statement', 182), ('million', 183), ('trump’s', 184), ('000', 185), ('day', 186), ('department', 187), ('saying', 188), ('don', 189), ('want', 190), ('1', 191), ('tax', 192), ('see', 193), ('russian', 194), ('tuesday', 195), ('still', 196), ('both', 197), ('much', 198), ('says', 199), ('image', 200), ('2016', 201), ('another', 202), ('congress', 203), ('part', 204), ('wednesday', 205), ('women', 206), ('your', 207), ('work', 208), ('go', 209), ('through', 210), ('friday', 211), ('thursday', 212), ('off', 213), ('three', 214), ('minister', 215), ('war', 216), ('city', 217), ('asked', 218), ('democrats', 219), ('policy', 220), ('own', 221), ('secretary', 222), ('monday', 223), ('americans', 224), ('long', 225), ('video', 226), ('rights', 227), ('china', 2('fult', 137988), ('misrule', 137989), ('distractive', 137990), ('refugearmed', 137991), ('oregonoregon', 137992), ('buildingthe', 137993), ('saturating', 137994), ('vanillaisis', 137995), ('behoove', 137996), ('1114', 137997), ('fs', 137998), ('owyhee', 137999), ('canyonlands', 138000), ('misapplies', 138001), ('subterfugeto', 138002), ('manuever', 138003), ('bundyranch', 138004), ('2014if', 138005), ('souloftheeast', 138006), ('ec6tmdetik', 138007), ('familyhistory', 138008), ('irrigated', 138009), ('a1', 138010), ('blitzen', 138011), ('meadowlands', 138012), ('a4', 138013), ('barricading', 138014), ('j1', 138015), ('frenchglen', 138016), ('glerup', 138017), ('exemplifying', 138018), ('treehousehere', 138019), ('betti', 138020), ('mondoweiss', 138021)])

---------------------------------

분석 대상 데이터의 word는Tokenizer를 이용하여 빈도순으로 숫자가 부여되었습니다.

pretrained embedding 중에서도 분석 대상 데이터의 word만 추출해 줍니다.

---------------------------


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

(138022, 300)


--------------------
# 처음 토큰화 방식을 실험하였을 때, text의 의미를 정확히 학습하는 것은 어려워 보였습니다.
# 그러나 pretrain방식을 이용하고 단어 단위로 세분화하는 방식을 이용한다면 이전에 접하지 못한 text의 의미를 분석하여 예측함에도 정확성을 향상할 수 있다는 것을 알게되었습니다. 중요한 것은 pretrain하는 data의 적절성인데, 분석 대상의 데이터 종류에 따라 전문용어/일상용어 등 의미 활용방식이 천차만별이기 때문입니다. 이 실험에서 Facebook에서 사용된 단어 데이터를 이용한 것은 실제 news나 issue가 facebook에 활용하고 있는 경우가 많고 real or fake news 여부를 많이 다루고 있기 때문이었습니다.
# 6.교차 검증 모델 실험 (Kaggle : Sentiment Analysis on Movie Reviews)을 통해 주어진 데이터를 임의의 train/test data로 나누고 data손실과 정확성을 직접 확인하는 실험을 진행하겠습니다.
