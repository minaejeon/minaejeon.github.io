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
    for filename in filenames:
        print(os.path.join(dirname, filename))

# You can write up to 20GB to the current directory (/kaggle/working/) that gets preserved as output when you create a version using "Save & Run All" 
# You can also write temporary files to /kaggle/temp/, but they won't be saved outside of the current session
```

<pre>
/kaggle/input/fake-and-real-news-dataset/True.csv
/kaggle/input/fake-and-real-news-dataset/Fake.csv
</pre>

```python
true=pd.read_csv("/kaggle/input/fake-and-real-news-dataset/True.csv")
fake=pd.read_csv("/kaggle/input/fake-and-real-news-dataset/Fake.csv")
display(true,fake)
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

<pre>
3    WASHINGTON (Reuters) - Trump campaign adviser ...
3    On Christmas day, Donald Trump announced that ...
Name: text, dtype: object
</pre>
word_tokenize



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 지우고 띄어쓰기 기준으로 잘라내는 특징



['0','WASHINGTON','(','Reuters',')','-','The','head','of','a','conservat','...','1','WASHINGTON','(','Reuters',')','-



','Transgender','people','will','...','2','WASHINGTON','(','Reuters',')','-



','The','special','counsel','inv','...','3','WASHINGTON','(','Reuters', ')','-



','Trump','campaign','adviser','...','4','SEATTLE/WASHINGTON','(','Reuters',')','-



','President','Donal','...','...','23476','21st','Century','Wire','says','As','21WIRE','reported','earl','...','23477','21st','Century','Wire



','says','It',...':',



 'object']




```python
import nltk
from nltk.tokenize import word_tokenize
TK=word_tokenize
text=data["text"]
tk_result=TK(str(text))
tk_result
```

<pre>
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
</pre>
TreebankWordTokenizer(다른 tokenizer에 비해 시간이 오래 걸렸다)



hyphen(-)으로 구성된 단어를 유지



doesn't와 같이 접어(줄임말을 쓸때 생기는 형태)가 있을 경우 분리



0        [WASHINGTON, (, Reuters, ), -, The, head, of, ...



1        [WASHINGTON, (, Reuters, ), -, Transgender, pe...



2        [WASHINGTON, (, Reuters, ), -, The, special, c...



3        [WASHINGTON, (, Reuters, ), -, Trump, campaign...



4        [SEATTLE/WASHINGTON, (, Reuters, ), -, Preside...



                               ...                        

23476    [21st, Century, Wire, says, As, 21WIRE, report...



23477    [21st, Century, Wire, says, It, s, a, familiar...



23478    [Patrick, Henningsen, 21st, Century, WireRemem...



23479    [21st, Century, Wire, says, Al, Jazeera, Ameri...



23480    [21st, Century, Wire, says, As, 21WIRE, predic...



Name: text, Length: 44898, dtype: object



```python
from nltk.tokenize import TreebankWordTokenizer
TK = TreebankWordTokenizer()
tk_result = data['text'].apply(TK.tokenize)
tk_result
```

<pre>
0        [WASHINGTON, (, Reuters, ), -, The, head, of, ...
1        [WASHINGTON, (, Reuters, ), -, Transgender, pe...
2        [WASHINGTON, (, Reuters, ), -, The, special, c...
3        [WASHINGTON, (, Reuters, ), -, Trump, campaign...
4        [SEATTLE/WASHINGTON, (, Reuters, ), -, Preside...
                               ...                        
23476    [21st, Century, Wire, says, As, 21WIRE, report...
23477    [21st, Century, Wire, says, It, s, a, familiar...
23478    [Patrick, Henningsen, 21st, Century, WireRemem...
23479    [21st, Century, Wire, says, Al, Jazeera, Ameri...
23480    [21st, Century, Wire, says, As, 21WIRE, predic...
Name: text, Length: 44898, dtype: object
</pre>
sent_tokenize



문장 단위로 구분



단순 마침표(.)기준으로 문장을 분리하지 않고 영어 문장에 적합.



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



**TURE 뉴스와 FAKE 뉴스의 'text' column을 보았을 때, 문장 단위의 토큰화는 세밀하게 학습하는 것이 어려워 단어 단위의 토큰화가 적합해 보인다.**



```python
from nltk.tokenize import sent_tokenize
text=data["text"]
TK=sent_tokenize
tk_result=TK(str(data['text']))
tk_result
```

<pre>
['0        WASHINGTON (Reuters) - The head of a conservat...\n1        WASHINGTON (Reuters) - Transgender people will...\n2        WASHINGTON (Reuters) - The special counsel inv...\n3        WASHINGTON (Reuters) - Trump campaign adviser ...\n4        SEATTLE/WASHINGTON (Reuters) - President Donal...\n                               ...                        \n23476    21st Century Wire says As 21WIRE reported earl...\n23477    21st Century Wire says It s a familiar theme.',
 '...\n23478    Patrick Henningsen  21st Century WireRemember ...\n23479    21st Century Wire says Al Jazeera America will...\n23480    21st Century Wire says As 21WIRE predicted in ...\nName: text, Length: 44898, dtype: object']
</pre>
WordPunctTokenizer



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 별도로 분류하는 특징.



word_tokenizer를 사용했을 때보다 정확하게 예측 가능





0        [WASHINGTON, (, Reuters, ), -, The, head, of, ...



1        [WASHINGTON, (, Reuters, ), -, Transgender, pe...



2        [WASHINGTON, (, Reuters, ), -, The, special, c...



3        [WASHINGTON, (, Reuters, ), -, Trump, campaign...



4        [SEATTLE, /, WASHINGTON, (, Reuters, ), -, Pre...



                               ...                        

23476    [21st, Century, Wire, says, As, 21WIRE, report...



23477    [21st, Century, Wire, says, It, s, a, familiar...



23478    [Patrick, Henningsen, 21st, Century, WireRemem...



23479    [21st, Century, Wire, says, Al, Jazeera, Ameri...



23480    [21st, Century, Wire, says, As, 21WIRE, predic...



Name: text, Length: 44898, dtype: object






```python
import tokenize
from nltk.tokenize import WordPunctTokenizer
text=data['text']
TK=WordPunctTokenizer()
tk_result = text.apply(TK.tokenize)
tk_result
```

<pre>
0        [WASHINGTON, (, Reuters, ), -, The, head, of, ...
1        [WASHINGTON, (, Reuters, ), -, Transgender, pe...
2        [WASHINGTON, (, Reuters, ), -, The, special, c...
3        [WASHINGTON, (, Reuters, ), -, Trump, campaign...
4        [SEATTLE, /, WASHINGTON, (, Reuters, ), -, Pre...
                               ...                        
23476    [21st, Century, Wire, says, As, 21WIRE, report...
23477    [21st, Century, Wire, says, It, s, a, familiar...
23478    [Patrick, Henningsen, 21st, Century, WireRemem...
23479    [21st, Century, Wire, says, Al, Jazeera, Ameri...
23480    [21st, Century, Wire, says, As, 21WIRE, predic...
Name: text, Length: 44898, dtype: object
</pre>
text_to_word_sequence



단어 토큰화 : 토큰의 기준을 단어로 하는 경우. 단어 단위, 단어 구, 의미를 갖는 문자 열로 구분



모든 알파벳을 소문자로 변경하고 마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 제거.



아포스트로피(')는 보존하는 특징.



tokenizer와 text_to_word_sequence 모두 keras에서 제공하고, 단어 토큰화에 사용된다.



빈도수를 감안하여 순서대로 배열하는 tokenizer가 러닝에 더 정확하게 사용 될 것으로 보인다.



['0',

 'washington',

 'reuters',

 'the',

 'head',

 'of',

 'a',

 'conservat',

 '1',

 'washington',

 'reuters',

 'transgender',

 'people',

 'will',

 '2',

 'washington',

 'reuters',

 'the',

 'special',

 'counsel',

 'inv',

 '3',

 'washington',

 'reuters',

 'trump',

 'campaign',

 'adviser',

 '4',

 'seattle',

 'washington',

 'reuters',

 'president',

 'donal',

 '23476',

 '21st',

 'century',

 'wire',

 'says',

 'as',

 '21wire',

 'reported',

 'earl',

 '23477',

 '21st',

 'century',

 'wire',

 'says',

 'it',

 's',

 'a',

 'familiar',

 'theme',

 '23478',

 'patrick',

 'henningsen',

 '21st',

 'century',

 'wireremember',

 '23479',

 '21st',

 'century',

 'wire',

 'says',

 'al',

 'jazeera',

 'america',

 'will',

 '23480',

 '21st',

 'century',

 'wire',

 'says',

 'as',

 '21wire',

 'predicted',

 'in',

 'name',

 'text',

 'length',

 '44898',

 'dtype',

 'object']



```python
import tokenize
from tensorflow.keras.preprocessing.text import text_to_word_sequence
tw=text_to_word_sequence
text=data["text"]
tk_result=tw(str(text))
tk_result
```

<pre>
['0',
 'washington',
 'reuters',
 'the',
 'head',
 'of',
 'a',
 'conservat',
 '1',
 'washington',
 'reuters',
 'transgender',
 'people',
 'will',
 '2',
 'washington',
 'reuters',
 'the',
 'special',
 'counsel',
 'inv',
 '3',
 'washington',
 'reuters',
 'trump',
 'campaign',
 'adviser',
 '4',
 'seattle',
 'washington',
 'reuters',
 'president',
 'donal',
 '23476',
 '21st',
 'century',
 'wire',
 'says',
 'as',
 '21wire',
 'reported',
 'earl',
 '23477',
 '21st',
 'century',
 'wire',
 'says',
 'it',
 's',
 'a',
 'familiar',
 'theme',
 '23478',
 'patrick',
 'henningsen',
 '21st',
 'century',
 'wireremember',
 '23479',
 '21st',
 'century',
 'wire',
 'says',
 'al',
 'jazeera',
 'america',
 'will',
 '23480',
 '21st',
 'century',
 'wire',
 'says',
 'as',
 '21wire',
 'predicted',
 'in',
 'name',
 'text',
 'length',
 '44898',
 'dtype',
 'object']
</pre>
Tokenizer



Keras에서 제공하는 Tokenizer를 이용하면 



마침표(.) 컴마(,) 물음표(?) 세미콜론(;) 느낌표(!)와 같은 구두점을 단어에 포함시키지 않고 분류



빈도수가 높은 순서대로 정렬하여 각 단어에 숫자를 부여





{'the': 1,'to': 2,'of': 3,'a': 4,'and': 5,'in': 6,'that': 7,'s': 8,'on': 9,'for': 10,

...'14': 987,'secret': 988,'16': 989,'speak': 990,'forced': 991,'relationship': 992,'fear': 993,'push': 994,'proposed': 995,'created': 996,'helped': 997,'phone': 998,'incident': 999,'repeatedly': 1000,...}



```python
from tensorflow.keras.preprocessing.text import Tokenizer
TK=Tokenizer()
tk_result=TK.fit_on_texts(data["text"])
TK.word_index
```

<pre>
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
 'he': 13,
 'it': 14,
 'trump': 15,
 'with': 16,
 'was': 17,
 'as': 18,
 'his': 19,
 'by': 20,
 'has': 21,
 'be': 22,
 'have': 23,
 'not': 24,
 'from': 25,
 'this': 26,
 'at': 27,
 'are': 28,
 'who': 29,
 'an': 30,
 'they': 31,
 'but': 32,
 'i': 33,
 'we': 34,
 'would': 35,
 'president': 36,
 'u': 37,
 'about': 38,
 'will': 39,
 't': 40,
 'their': 41,
 'had': 42,
 'you': 43,
 'been': 44,
 'people': 45,
 'were': 46,
 '”': 47,
 'or': 48,
 'more': 49,
 'which': 50,
 'she': 51,
 'one': 52,
 'after': 53,
 'her': 54,
 'all': 55,
 'if': 56,
 'out': 57,
 'state': 58,
 'what': 59,
 'when': 60,
 'also': 61,
 'up': 62,
 'new': 63,
 'its': 64,
 'there': 65,
 'no': 66,
 'reuters': 67,
 'over': 68,
 'so': 69,
 'donald': 70,
 'government': 71,
 'house': 72,
 'our': 73,
 'clinton': 74,
 'states': 75,
 'can': 76,
 'obama': 77,
 'him': 78,
 'republican': 79,
 'than': 80,
 'other': 81,
 'just': 82,
 'some': 83,
 'year': 84,
 'could': 85,
 'united': 86,
 'told': 87,
 'into': 88,
 'like': 89,
 'white': 90,
 'do': 91,
 'against': 92,
 'them': 93,
 'two': 94,
 'because': 95,
 'campaign': 96,
 'time': 97,
 'election': 98,
 'last': 99,
 'now': 100,
 'news': 101,
 'any': 102,
 'party': 103,
 'first': 104,
 'how': 105,
 'only': 106,
 'washington': 107,
 'former': 108,
 'while': 109,
 'even': 110,
 'country': 111,
 'being': 112,
 'should': 113,
 'us': 114,
 'during': 115,
 'did': 116,
 'hillary': 117,
 'before': 118,
 'years': 119,
 'many': 120,
 'american': 121,
 'media': 122,
 'most': 123,
 'security': 124,
 'law': 125,
 'made': 126,
 'may': 127,
 'national': 128,
 'say': 129,
 'political': 130,
 'police': 131,
 'those': 132,
 'get': 133,
 'right': 134,
 'since': 135,
 'make': 136,
 'court': 137,
 'percent': 138,
 'where': 139,
 'twitter': 140,
 'according': 141,
 'going': 142,
 'republicans': 143,
 'under': 144,
 'back': 145,
 'these': 146,
 'here': 147,
 'presidential': 148,
 'then': 149,
 're': 150,
 'very': 151,
 'russia': 152,
 'via': 153,
 'democratic': 154,
 'administration': 155,
 'called': 156,
 'bill': 157,
 'week': 158,
 'support': 159,
 'america': 160,
 'down': 161,
 'vote': 162,
 'senate': 163,
 'between': 164,
 'way': 165,
 'including': 166,
 'know': 167,
 'think': 168,
 'group': 169,
 'north': 170,
 'officials': 171,
 'office': 172,
 'well': 173,
 'public': 174,
 'take': 175,
 'such': 176,
 'federal': 177,
 'world': 178,
 'military': 179,
 'foreign': 180,
 'my': 181,
 'statement': 182,
 'million': 183,
 'trump’s': 184,
 '000': 185,
 'day': 186,
 'department': 187,
 'saying': 188,
 'don': 189,
 'want': 190,
 '1': 191,
 'tax': 192,
 'see': 193,
 'russian': 194,
 'tuesday': 195,
 'still': 196,
 'both': 197,
 'much': 198,
 'says': 199,
 'image': 200,
 '2016': 201,
 'another': 202,
 'congress': 203,
 'part': 204,
 'wednesday': 205,
 'women': 206,
 'your': 207,
 'work': 208,
 'go': 209,
 'through': 210,
 'friday': 211,
 'thursday': 212,
 'off': 213,
 'three': 214,
 'minister': 215,
 'war': 216,
 'city': 217,
 'asked': 218,
 'democrats': 219,
 'policy': 220,
 'own': 221,
 'secretary': 222,
 'monday': 223,
 'americans': 224,
 'long': 225,
 'video': 226,
 'rights': 227,
 'china': 228,
 'general': 229,
 'york': 230,
 'me': 231,
 'committee': 232,
 'black': 233,
 'official': 234,
 'deal': 235,
 'next': 236,
 'left': 237,
 'com': 238,
 'case': 239,
 'help': 240,
 'need': 241,
 'why': 242,
 'whether': 243,
 'show': 244,
 'same': 245,
 'featured': 246,
 'never': 247,
 'around': 248,
 'man': 249,
 'leader': 250,
 'senator': 251,
 'korea': 252,
 'does': 253,
 'order': 254,
 'members': 255,
 'candidate': 256,
 'month': 257,
 'use': 258,
 'old': 259,
 'power': 260,
 'report': 261,
 'good': 262,
 'took': 263,
 'end': 264,
 'come': 265,
 'every': 266,
 '2': 267,
 'fbi': 268,
 'times': 269,
 'meeting': 270,
 'iran': 271,
 'intelligence': 272,
 'without': 273,
 'used': 274,
 'investigation': 275,
 'far': 276,
 'countries': 277,
 'money': 278,
 'really': 279,
 'put': 280,
 'top': 281,
 'justice': 282,
 'reported': 283,
 'post': 284,
 'information': 285,
 'nuclear': 286,
 'change': 287,
 'business': 288,
 'anti': 289,
 'attack': 290,
 'm': 291,
 'watch': 292,
 'fact': 293,
 'trade': 294,
 'voters': 295,
 'syria': 296,
 'decision': 297,
 'family': 298,
 'story': 299,
 'international': 300,
 'leaders': 301,
 'again': 302,
 'however': 303,
 'south': 304,
 'days': 305,
 'already': 306,
 'plan': 307,
 'several': 308,
 'speech': 309,
 'high': 310,
 'interview': 311,
 'too': 312,
 'groups': 313,
 'director': 314,
 'place': 315,
 'chief': 316,
 'conservative': 317,
 'd': 318,
 '5': 319,
 'months': 320,
 '3': 321,
 'home': 322,
 'health': 323,
 'immigration': 324,
 'something': 325,
 '10': 326,
 'clear': 327,
 'pic': 328,
 'muslim': 329,
 'likely': 330,
 'among': 331,
 'agency': 332,
 'john': 333,
 'must': 334,
 'fox': 335,
 'call': 336,
 'border': 337,
 'program': 338,
 'social': 339,
 'issue': 340,
 'billion': 341,
 'barack': 342,
 'al': 343,
 'children': 344,
 'today': 345,
 'press': 346,
 'islamic': 347,
 'act': 348,
 'believe': 349,
 'four': 350,
 'won': 351,
 'supporters': 352,
 'recent': 353,
 'free': 354,
 'move': 355,
 'sunday': 356,
 'came': 357,
 'based': 358,
 'might': 359,
 'control': 360,
 'later': 361,
 'things': 362,
 'least': 363,
 'though': 364,
 'nation': 365,
 'seen': 366,
 'yet': 367,
 'co': 368,
 'got': 369,
 'number': 370,
 'making': 371,
 'found': 372,
 've': 373,
 'member': 374,
 'major': 375,
 'sanders': 376,
 'n': 377,
 'matter': 378,
 'didn': 379,
 'added': 380,
 'point': 381,
 'working': 382,
 'earlier': 383,
 'great': 384,
 'reporters': 385,
 'defense': 386,
 'killed': 387,
 'trying': 388,
 'win': 389,
 '2017': 390,
 '8': 391,
 'system': 392,
 'school': 393,
 'economic': 394,
 'known': 395,
 'march': 396,
 'went': 397,
 'real': 398,
 '4': 399,
 'become': 400,
 'spokesman': 401,
 'past': 402,
 'actually': 403,
 'little': 404,
 'cnn': 405,
 'attacks': 406,
 'executive': 407,
 'let': 408,
 'himself': 409,
 'violence': 410,
 'look': 411,
 'democrat': 412,
 'set': 413,
 'doesn': 414,
 'led': 415,
 'held': 416,
 'run': 417,
 'eu': 418,
 'ever': 419,
 'until': 420,
 'keep': 421,
 'away': 422,
 'stop': 423,
 'thing': 424,
 'january': 425,
 'senior': 426,
 'give': 427,
 'comment': 428,
 'legal': 429,
 'big': 430,
 'doing': 431,
 'forces': 432,
 'life': 433,
 'cruz': 434,
 'nothing': 435,
 '20': 436,
 '2015': 437,
 'following': 438,
 'majority': 439,
 'european': 440,
 'head': 441,
 'few': 442,
 'july': 443,
 'gun': 444,
 'local': 445,
 'human': 446,
 'wall': 447,
 'taking': 448,
 'prime': 449,
 'care': 450,
 'action': 451,
 'night': 452,
 'issues': 453,
 'reports': 454,
 'person': 455,
 'governor': 456,
 'second': 457,
 'opposition': 458,
 'once': 459,
 'nominee': 460,
 'force': 461,
 'community': 462,
 'woman': 463,
 'lawmakers': 464,
 'possible': 465,
 'job': 466,
 'across': 467,
 'expected': 468,
 'illegal': 469,
 'companies': 470,
 'attorney': 471,
 'union': 472,
 'continue': 473,
 'pay': 474,
 'released': 475,
 'source': 476,
 'wrote': 477,
 'men': 478,
 'sanctions': 479,
 'others': 480,
 'company': 481,
 'team': 482,
 'better': 483,
 'face': 484,
 'talks': 485,
 'nations': 486,
 'enough': 487,
 'history': 488,
 'given': 489,
 'legislation': 490,
 'process': 491,
 'read': 492,
 'judge': 493,
 'open': 494,
 'question': 495,
 'done': 496,
 'five': 497,
 'evidence': 498,
 'financial': 499,
 'taken': 500,
 'images': 501,
 'june': 502,
 'course': 503,
 'realdonaldtrump': 504,
 'wants': 505,
 'full': 506,
 'despite': 507,
 'november': 508,
 'supreme': 509,
 'university': 510,
 'close': 511,
 'center': 512,
 'important': 513,
 'having': 514,
 'mexico': 515,
 'private': 516,
 'lot': 517,
 'response': 518,
 'anyone': 519,
 'gop': 520,
 'https': 521,
 'race': 522,
 'air': 523,
 'special': 524,
 'iraq': 525,
 'staff': 526,
 'mr': 527,
 'budget': 528,
 'saturday': 529,
 'hard': 530,
 'ago': 531,
 'debate': 532,
 'saudi': 533,
 'further': 534,
 'instead': 535,
 'along': 536,
 'using': 537,
 'anything': 538,
 'syrian': 539,
 'plans': 540,
 'conference': 541,
 'refugees': 542,
 'comments': 543,
 'fight': 544,
 'death': 545,
 'ban': 546,
 'able': 547,
 'efforts': 548,
 'crisis': 549,
 'behind': 550,
 'facebook': 551,
 '9': 552,
 'agreement': 553,
 'less': 554,
 'accused': 555,
 'best': 556,
 'putin': 557,
 'future': 558,
 '6': 559,
 'early': 560,
 '30': 561,
 '15': 562,
 'term': 563,
 'region': 564,
 'email': 565,
 'lives': 566,
 'getty': 567,
 'find': 568,
 'role': 569,
 'lead': 570,
 'ryan': 571,
 'letter': 572,
 'council': 573,
 'current': 574,
 'within': 575,
 '7': 576,
 'sure': 577,
 'someone': 578,
 'comes': 579,
 '11': 580,
 'israel': 581,
 '2014': 582,
 'jobs': 583,
 'line': 584,
 'due': 585,
 'name': 586,
 'texas': 587,
 'civil': 588,
 '“i': 589,
 'service': 590,
 'calling': 591,
 'weeks': 592,
 'below': 593,
 'running': 594,
 'citizens': 595,
 'middle': 596,
 'event': 597,
 '“the': 598,
 'getting': 599,
 'comey': 600,
 'economy': 601,
 'coming': 602,
 'live': 603,
 'll': 604,
 'young': 605,
 'coalition': 606,
 'weapons': 607,
 'congressional': 608,
 'announced': 609,
 'muslims': 610,
 'elections': 611,
 'sources': 612,
 'effort': 613,
 'votes': 614,
 'students': 615,
 'visit': 616,
 'britain': 617,
 'chairman': 618,
 'nearly': 619,
 'late': 620,
 'six': 621,
 'rules': 622,
 'speaking': 623,
 'daily': 624,
 'thousands': 625,
 'sent': 626,
 'october': 627,
 'talk': 628,
 'authorities': 629,
 'street': 630,
 'front': 631,
 'global': 632,
 'each': 633,
 'december': 634,
 'paul': 635,
 'position': 636,
 'army': 637,
 'capital': 638,
 '12': 639,
 'rule': 640,
 'allow': 641,
 'candidates': 642,
 'problem': 643,
 'began': 644,
 'am': 645,
 'april': 646,
 'whose': 647,
 'east': 648,
 'politics': 649,
 'september': 650,
 'officers': 651,
 'wanted': 652,
 'everyone': 653,
 'august': 654,
 'workers': 655,
 'outside': 656,
 'ties': 657,
 'organization': 658,
 'bush': 659,
 'climate': 660,
 'florida': 661,
 'claims': 662,
 'showed': 663,
 'backed': 664,
 'tell': 665,
 'isn': 666,
 'ruling': 667,
 'means': 668,
 'immigrants': 669,
 'hold': 670,
 'emails': 671,
 'immediately': 672,
 'message': 673,
 'obamacare': 674,
 'needs': 675,
 'together': 676,
 'failed': 677,
 'policies': 678,
 'gave': 679,
 'stand': 680,
 'criminal': 681,
 'bad': 682,
 'start': 683,
 'questions': 684,
 'leave': 685,
 'relations': 686,
 'threat': 687,
 'healthcare': 688,
 'reform': 689,
 'services': 690,
 'oil': 691,
 'voting': 692,
 'latest': 693,
 'lost': 694,
 'february': 695,
 'elected': 696,
 'morning': 697,
 'list': 698,
 'rather': 699,
 'poll': 700,
 'racist': 701,
 'words': 702,
 'strong': 703,
 'cut': 704,
 'representatives': 705,
 'recently': 706,
 'different': 707,
 'reason': 708,
 'moscow': 709,
 'pro': 710,
 'access': 711,
 'hope': 712,
 'turkey': 713,
 'peace': 714,
 'central': 715,
 'liberal': 716,
 'fake': 717,
 'enforcement': 718,
 'almost': 719,
 'received': 720,
 'release': 721,
 'funding': 722,
 'rally': 723,
 'thought': 724,
 'parliament': 725,
 'involved': 726,
 'allies': 727,
 'germany': 728,
 'planned': 729,
 'try': 730,
 'vice': 731,
 'ministry': 732,
 'spending': 733,
 'laws': 734,
 'tried': 735,
 'agencies': 736,
 'cannot': 737,
 'large': 738,
 'conservatives': 739,
 'idea': 740,
 '100': 741,
 'non': 742,
 'george': 743,
 'millions': 744,
 'europe': 745,
 'side': 746,
 'happened': 747,
 'decided': 748,
 'ahead': 749,
 'shooting': 750,
 'often': 751,
 'allowed': 752,
 'situation': 753,
 'century': 754,
 'level': 755,
 'tv': 756,
 'missile': 757,
 'hate': 758,
 'near': 759,
 'always': 760,
 'chinese': 761,
 'small': 762,
 'sexual': 763,
 'provide': 764,
 'charges': 765,
 'district': 766,
 'talking': 767,
 'makes': 768,
 'bring': 769,
 'concerns': 770,
 'j': 771,
 'officer': 772,
 'host': 773,
 'kind': 774,
 'entire': 775,
 'protect': 776,
 'fire': 777,
 'although': 778,
 'met': 779,
 'key': 780,
 'parties': 781,
 'crime': 782,
 'needed': 783,
 'western': 784,
 'decades': 785,
 'looking': 786,
 'movement': 787,
 'meet': 788,
 'presidency': 789,
 'california': 790,
 'denied': 791,
 'energy': 792,
 'room': 793,
 'bank': 794,
 'shot': 795,
 'everything': 796,
 'calls': 797,
 'area': 798,
 'return': 799,
 'themselves': 800,
 'allegations': 801,
 '2012': 802,
 'nomination': 803,
 'data': 804,
 'market': 805,
 'james': 806,
 'industry': 807,
 'freedom': 808,
 'water': 809,
 'true': 810,
 'agreed': 811,
 'west': 812,
 'especially': 813,
 'include': 814,
 'hours': 815,
 'tweet': 816,
 'either': 817,
 'terrorism': 818,
 'documents': 819,
 'terrorist': 820,
 '25': 821,
 'british': 822,
 '“we': 823,
 'county': 824,
 'son': 825,
 'seems': 826,
 'half': 827,
 'fired': 828,
 'voted': 829,
 'third': 830,
 'wife': 831,
 'interest': 832,
 'representative': 833,
 'request': 834,
 'actions': 835,
 'adding': 836,
 'building': 837,
 'fighting': 838,
 'foundation': 839,
 'protesters': 840,
 'potential': 841,
 'hit': 842,
 'confirmed': 843,
 'personal': 844,
 'cases': 845,
 'short': 846,
 'polls': 847,
 'wrong': 848,
 'hearing': 849,
 'shows': 850,
 'continued': 851,
 'forward': 852,
 'elect': 853,
 'arrested': 854,
 'claim': 855,
 'insurance': 856,
 'step': 857,
 'korean': 858,
 'worked': 859,
 'clearly': 860,
 'myanmar': 861,
 'claimed': 862,
 'paid': 863,
 'biggest': 864,
 'commission': 865,
 'passed': 866,
 '50': 867,
 'nov': 868,
 'travel': 869,
 'address': 870,
 'low': 871,
 'alleged': 872,
 'hand': 873,
 'leading': 874,
 'record': 875,
 'spoke': 876,
 'board': 877,
 'adviser': 878,
 'serious': 879,
 'soon': 880,
 '2013': 881,
 'bernie': 882,
 'father': 883,
 'appeared': 884,
 'network': 885,
 'pressure': 886,
 'probably': 887,
 'families': 888,
 'primary': 889,
 'truth': 890,
 'feel': 891,
 'main': 892,
 'independence': 893,
 'mean': 894,
 'cost': 895,
 'love': 896,
 'turned': 897,
 'page': 898,
 'largest': 899,
 'posted': 900,
 'mike': 901,
 'college': 902,
 'issued': 903,
 'michael': 904,
 'taxes': 905,
 'result': 906,
 'declined': 907,
 'o': 908,
 'wasn': 909,
 'turn': 910,
 'leadership': 911,
 'review': 912,
 'dollars': 913,
 'agenda': 914,
 'simply': 915,
 'mark': 916,
 'pass': 917,
 'brought': 918,
 'victory': 919,
 'points': 920,
 'david': 921,
 'cia': 922,
 'lawyer': 923,
 'included': 924,
 'described': 925,
 'started': 926,
 'became': 927,
 'london': 928,
 'tillerson': 929,
 'article': 930,
 'final': 931,
 'signed': 932,
 'isis': 933,
 'remarks': 934,
 'related': 935,
 'toward': 936,
 'spent': 937,
 'previously': 938,
 '18': 939,
 'fund': 940,
 'african': 941,
 'deputy': 942,
 'religious': 943,
 'protest': 944,
 'influence': 945,
 'details': 946,
 'website': 947,
 'wing': 948,
 'class': 949,
 'pence': 950,
 'single': 951,
 'account': 952,
 '13': 953,
 'arabia': 954,
 'food': 955,
 'seven': 956,
 'view': 957,
 'sign': 958,
 '24': 959,
 'child': 960,
 'armed': 961,
 'longer': 962,
 'raised': 963,
 'flynn': 964,
 'mccain': 965,
 'town': 966,
 'reality': 967,
 'conflict': 968,
 'popular': 969,
 'protests': 970,
 'seeking': 971,
 'rubio': 972,
 'guy': 973,
 'pretty': 974,
 'attempt': 975,
 'aid': 976,
 'friends': 977,
 'saw': 978,
 'constitution': 979,
 'income': 980,
 'ted': 981,
 'sessions': 982,
 'else': 983,
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
</pre>
*true/fake data를 보았을때, sentence 단위 보다 word 단위로 분류하는 것이 필요해 보인다.*



*또한, tokenizer는 nltk와 keras에서 제공하고 있는데 같은 keras 에서도 tokenizer만 단어의 빈도수를 반영하고 있어 text_to_word_sequence 보다 정확할 것으로 보인다*



```python
sequence=TK.texts_to_sequences(data["text"])
print(text[3])
```

<pre>
3    WASHINGTON (Reuters) - Trump campaign adviser ...
3    On Christmas day, Donald Trump announced that ...
Name: text, dtype: object
</pre>

```python
pd.Series(sequence)
```

<pre>
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
</pre>

```python
import seaborn as sns
import matplotlib.pyplot as plt
plt.figure(figsize=(16,8))
sns.displot(pd.Series(sequence).apply(len))
plt.xlim(0,20000)
```

<pre>
(0.0, 20000.0)
</pre>
<pre>
<Figure size 1152x576 with 0 Axes>
</pre>
<img src="data:image/png;base64,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"/>


```python
from tensorflow.keras.preprocessing.sequence import pad_sequences
pad_text=pad_sequences(sequence,maxlen=1750)
pad_text
pad_text.shape
```

<pre>
(44898, 1750)
</pre>