# 8 NLTK와 Keras의 Text 토큰화 실험 (Kaggle Spam Mails Dataset)


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
/kaggle/input/spam-mails-dataset/spam_ham_dataset.csv
</pre>

```python
data=pd.read_csv("/kaggle/input/spam-mails-dataset/spam_ham_dataset.csv")
data
```

<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Unnamed: 0</th>
      <th>label</th>
      <th>text</th>
      <th>label_num</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>605</td>
      <td>ham</td>
      <td>Subject: enron methanol ; meter # : 988291\r\n...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2349</td>
      <td>ham</td>
      <td>Subject: hpl nom for january 9 , 2001\r\n( see...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3624</td>
      <td>ham</td>
      <td>Subject: neon retreat\r\nho ho ho , we ' re ar...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4685</td>
      <td>spam</td>
      <td>Subject: photoshop , windows , office . cheap ...</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2030</td>
      <td>ham</td>
      <td>Subject: re : indian springs\r\nthis deal is t...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>5166</th>
      <td>1518</td>
      <td>ham</td>
      <td>Subject: put the 10 on the ft\r\nthe transport...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5167</th>
      <td>404</td>
      <td>ham</td>
      <td>Subject: 3 / 4 / 2000 and following noms\r\nhp...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5168</th>
      <td>2933</td>
      <td>ham</td>
      <td>Subject: calpine daily gas nomination\r\n&gt;\r\n...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5169</th>
      <td>1409</td>
      <td>ham</td>
      <td>Subject: industrial worksheets for august 2000...</td>
      <td>0</td>
    </tr>
    <tr>
      <th>5170</th>
      <td>4807</td>
      <td>spam</td>
      <td>Subject: important online banking alert\r\ndea...</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>5171 rows × 4 columns</p>
</div>


word_tokenize



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 지우고 띄어쓰기 기준으로 잘라내는 특징



```python
from nltk.tokenize import word_tokenize
tk=word_tokenize
text=data["text"]
tk_result=word_tokenize(str(text))
tk_result
```

<pre>
['0',
 'Subject',
 ':',
 'enron',
 'methanol',
 ';',
 'meter',
 '#',
 ':',
 '988291\\r\\n',
 '...',
 '1',
 'Subject',
 ':',
 'hpl',
 'nom',
 ...
 'Length',
 ':',
 '5171',
 ',',
 'dtype',
 ':',
 'object']
</pre>
TreebankWordTokenizer(다른 tokenizer에 비해 시간이 오래 걸렸다)



hyphen(-)으로 구성된 단어를 유지



doesn't와 같이 접어(줄임말을 쓸때 생기는 형태)가 있을 경우 분리



0 [WASHINGTON, (, Reuters, ), -, The, head, of, ...



1 [WASHINGTON, (, Reuters, ), -, Transgender, pe...



2 [WASHINGTON, (, Reuters, ), -, The, special, c...



3 [WASHINGTON, (, Reuters, ), -, Trump, campaign...



4 [SEATTLE/WASHINGTON, (, Reuters, ), -, Preside...



```python
from nltk.tokenize import TreebankWordTokenizer
tk=TreebankWordTokenizer()
text=data["text"]
tk_result=data["text"].apply(tk.tokenize)
tk_result
```

<pre>
0       [Subject, :, enron, methanol, ;, meter, #, :, ...
1       [Subject, :, hpl, nom, for, january, 9, ,, 200...
2       [Subject, :, neon, retreat, ho, ho, ho, ,, we,...
3       [Subject, :, photoshop, ,, windows, ,, office,...
4       [Subject, :, re, :, indian, springs, this, dea...
                              ...                        
5166    [Subject, :, put, the, 10, on, the, ft, the, t...
5167    [Subject, :, 3, /, 4, /, 2000, and, following,...
5168    [Subject, :, calpine, daily, gas, nomination, ...
5169    [Subject, :, industrial, worksheets, for, augu...
5170    [Subject, :, important, online, banking, alert...
Name: text, Length: 5171, dtype: object
</pre>
sent_tokenize



문장 단위로 구분



단순 마침표(.)기준으로 문장을 분리하지 않고 영어 문장에 적합.


TURE 뉴스와 FAKE 뉴스의 'text' column을 보았을 때, 문장 단위의 토큰화는 세밀하게 학습하는 것이 어려워 단어 단위의 토큰화가 적합해 보인다.



```python
from nltk.tokenize import sent_tokenize
tk=sent_tokenize
text=data["text"]
tk_result=tk(str(text))
tk_result
```

<pre>
["0       Subject: enron methanol ; meter # : 988291\\r\\n...\n1       Subject: hpl nom for january 9 , 2001\\r\\n( see...\n2       Subject: neon retreat\\r\\nho ho ho , we ' re ar...\n3       Subject: photoshop , windows , office .",
 'cheap ...\n4       Subject: re : indian springs\\r\\nthis deal is t...\n                              ...                        \n5166    Subject: put the 10 on the ft\\r\\nthe transport...\n5167    Subject: 3 / 4 / 2000 and following noms\\r\\nhp...\n5168    Subject: calpine daily gas nomination\\r\\n>\\r\\n...\n5169    Subject: industrial worksheets for august 2000...\n5170    Subject: important online banking alert\\r\\ndea...\nName: text, Length: 5171, dtype: object']
</pre>
WordPunctTokenizer



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 별도로 분류하는 특징.



word_tokenizer를 사용했을 때보다 정확하게 예측 가능



```python
from nltk.tokenize import WordPunctTokenizer
tk=WordPunctTokenizer()
text=data["text"]
tk_result=data["text"].apply(tk.tokenize)
tk_result
```

<pre>
0       [Subject, :, enron, methanol, ;, meter, #, :, ...
1       [Subject, :, hpl, nom, for, january, 9, ,, 200...
2       [Subject, :, neon, retreat, ho, ho, ho, ,, we,...
3       [Subject, :, photoshop, ,, windows, ,, office,...
4       [Subject, :, re, :, indian, springs, this, dea...
                              ...                        
5166    [Subject, :, put, the, 10, on, the, ft, the, t...
5167    [Subject, :, 3, /, 4, /, 2000, and, following,...
5168    [Subject, :, calpine, daily, gas, nomination, ...
5169    [Subject, :, industrial, worksheets, for, augu...
5170    [Subject, :, important, online, banking, alert...
Name: text, Length: 5171, dtype: object
</pre>
text_to_word_sequence



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



모든 알파벳을 소문자로 변경하고 마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 제거.



아포스트로피(')는 보존하는 특징.



tokenizer와 text_to_word_sequence 모두 keras에서 제공하고, 단어 토큰화에 사용된다.



빈도수를 감안하여 순서대로 배열하는 tokenizer가 러닝에 더 정확하게 사용 될 것으로 보인다.



```python
from tensorflow.keras.preprocessing.text import text_to_word_sequence
tk=text_to_word_sequence
text=data["text"]
tk_result=tk(str(text))
tk_result
```

<pre>
['0',
 'subject',
 'enron',
 'methanol',
 'meter',
 '988291',
 ...
 'name',
 'text',
 'length',
 '5171',
 'dtype',
 'object']
</pre>
Tokenizer



Keras에서 제공하는 Tokenizer를 이용하면



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 단어에 포함시키지 않고 분류



빈도수가 높은 순서대로 정렬하여 각 단어에 숫자를 부여



```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
text=data["text"]
TK.fit_on_texts(text)
TK.word_index
```

<pre>
{'\r': 1,
 'the': 2,
 'to': 3,
 'and': 4,
 'ect': 5,
 'for': 6,
 'of': 7,
 'a': 8,
 'subject': 9,
 ...
 'mg': 994,
 'country': 995,
 'loss': 996,
 'voip': 997,
 'registered': 998,
 'hesse': 999,
 'bryan': 1000,
 ...}
</pre>
# true/fake data를 보았을때, sentence 단위 보다 word 단위로 분류하는 것이 필요해 보인다.

# 

# 또한, tokenizer는 nltk와 keras에서 제공하고 있는데 같은 keras 에서도 tokenizer만 단어의 빈도수를 반영하고 있어 text_to_word_sequence 보다 정확할 것으로 보인다


texts_to_sequences의 이용 : data의 'text' column에 숫자가 순서대로 matching되어 들어간다.



```python
sequence=TK.texts_to_sequences(data["text"])
sequence
```

<pre>
[[9,
  18,
  1043,
  44,
  13702,
  ...
   33694,
  15329,
  7743,
  9348],
 ...]
 </pre>

```python
pd.Series(sequence)
```

<pre>
0       [9, 18, 1043, 44, 13702, 16, 15, 8, 679, 82, 3...
1       [9, 48, 148, 6, 267, 119, 276, 93, 98, 169, 20...
2       [9, 1440, 27147, 9841, 9841, 9841, 21, 11, 51,...
3       [9, 1367, 521, 294, 1425, 2485, 27152, 27153, ...
4       [9, 51, 5644, 11291, 16, 41, 15, 3, 714, 2, 24...
                              ...                        
5166    [9, 504, 2, 49, 14, 2, 27146, 2, 290, 157, 731...
5167    [9, 36, 69, 30, 4, 177, 1517, 48, 53, 11, 77, ...
5168    [9, 704, 241, 37, 1072, 1, 1, 335, 34, 17, 439...
5169    [9, 1064, 9434, 6, 345, 30, 2483, 98, 29, 2, 9...
5170    [9, 907, 330, 2686, 5813, 1136, 3334, 7268, 10...
Length: 5171, dtype: object
</pre>
각 행의 'data'column의 숫자 갯수가 다르므로 하나로 통일해 주어야 한다.



displot을 이용하여 찾을 수 있다.



```python
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(16,8))
sns.displot(pd.Series(sequence).apply(len))
plt.xlim(0,1000)
```

<pre>
(0.0, 1000.0)
</pre>
<pre>
<Figure size 1152x576 with 0 Axes>
</pre>
<img src="data:image/png;base64,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"/>

각 'text' column의 모든 행에 앞에서 800개의 숫자만 남겨서 데이터를 정제한다



keras의 pad_sequences 를 이용하여 갯수를 맞출 수 있다.



```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(sequence)
pad_text
```

<pre>
array([[   0,    0,    0, ...,    6, 4370, 1975],
       [   0,    0,    0, ..., 2014,  134,  121],
       [   0,    0,    0, ..., 1285,    1, 4554],
       ...,
       [   0,    0,    0, ...,  224,   42,  639],
       [   0,    0,    0, ...,  333,   16,  479],
       [   0,    0,    0, ...,  611,  309,    1]], dtype=int32)
</pre>