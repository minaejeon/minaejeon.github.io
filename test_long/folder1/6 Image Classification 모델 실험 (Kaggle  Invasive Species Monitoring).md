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
#
 
T
h
i
s
 
P
y
t
h
o
n
 
3
 
e
n
v
i
r
o
n
m
e
n
t
 
c
o
m
e
s
 
w
i
t
h
 
m
a
n
y
 
h
e
l
p
f
u
l
 
a
n
a
l
y
t
i
c
s
 
l
i
b
r
a
r
i
e
s
 
i
n
s
t
a
l
l
e
d

#
 
I
t
 
i
s
 
d
e
f
i
n
e
d
 
b
y
 
t
h
e
 
k
a
g
g
l
e
/
p
y
t
h
o
n
 
D
o
c
k
e
r
 
i
m
a
g
e
:
 
h
t
t
p
s
:
/
/
g
i
t
h
u
b
.
c
o
m
/
k
a
g
g
l
e
/
d
o
c
k
e
r
-
p
y
t
h
o
n

#
 
F
o
r
 
e
x
a
m
p
l
e
,
 
h
e
r
e
'
s
 
s
e
v
e
r
a
l
 
h
e
l
p
f
u
l
 
p
a
c
k
a
g
e
s
 
t
o
 
l
o
a
d


i
m
p
o
r
t
 
n
u
m
p
y
 
a
s
 
n
p
 
#
 
l
i
n
e
a
r
 
a
l
g
e
b
r
a

i
m
p
o
r
t
 
p
a
n
d
a
s
 
a
s
 
p
d
 
#
 
d
a
t
a
 
p
r
o
c
e
s
s
i
n
g
,
 
C
S
V
 
f
i
l
e
 
I
/
O
 
(
e
.
g
.
 
p
d
.
r
e
a
d
_
c
s
v
)


#
 
I
n
p
u
t
 
d
a
t
a
 
f
i
l
e
s
 
a
r
e
 
a
v
a
i
l
a
b
l
e
 
i
n
 
t
h
e
 
r
e
a
d
-
o
n
l
y
 
"
.
.
/
i
n
p
u
t
/
"
 
d
i
r
e
c
t
o
r
y

#
 
F
o
r
 
e
x
a
m
p
l
e
,
 
r
u
n
n
i
n
g
 
t
h
i
s
 
(
b
y
 
c
l
i
c
k
i
n
g
 
r
u
n
 
o
r
 
p
r
e
s
s
i
n
g
 
S
h
i
f
t
+
E
n
t
e
r
)
 
w
i
l
l
 
l
i
s
t
 
a
l
l
 
f
i
l
e
s
 
u
n
d
e
r
 
t
h
e
 
i
n
p
u
t
 
d
i
r
e
c
t
o
r
y


i
m
p
o
r
t
 
o
s

f
o
r
 
d
i
r
n
a
m
e
,
 
_
,
 
f
i
l
e
n
a
m
e
s
 
i
n
 
o
s
.
w
a
l
k
(
'
/
k
a
g
g
l
e
/
i
n
p
u
t
'
)
:

 
 
 
 
f
o
r
 
f
i
l
e
n
a
m
e
 
i
n
 
f
i
l
e
n
a
m
e
s
[
:
5
]
:

 
 
 
 
 
 
 
 
p
r
i
n
t
(
o
s
.
p
a
t
h
.
j
o
i
n
(
d
i
r
n
a
m
e
,
 
f
i
l
e
n
a
m
e
)
)


#
 
Y
o
u
 
c
a
n
 
w
r
i
t
e
 
u
p
 
t
o
 
2
0
G
B
 
t
o
 
t
h
e
 
c
u
r
r
e
n
t
 
d
i
r
e
c
t
o
r
y
 
(
/
k
a
g
g
l
e
/
w
o
r
k
i
n
g
/
)
 
t
h
a
t
 
g
e
t
s
 
p
r
e
s
e
r
v
e
d
 
a
s
 
o
u
t
p
u
t
 
w
h
e
n
 
y
o
u
 
c
r
e
a
t
e
 
a
 
v
e
r
s
i
o
n
 
u
s
i
n
g
 
"
S
a
v
e
 
&
 
R
u
n
 
A
l
l
"
 

#
 
Y
o
u
 
c
a
n
 
a
l
s
o
 
w
r
i
t
e
 
t
e
m
p
o
r
a
r
y
 
f
i
l
e
s
 
t
o
 
/
k
a
g
g
l
e
/
t
e
m
p
/
,
 
b
u
t
 
t
h
e
y
 
w
o
n
'
t
 
b
e
 
s
a
v
e
d
 
o
u
t
s
i
d
e
 
o
f
 
t
h
e
 
c
u
r
r
e
n
t
 
s
e
s
s
i
o
n
```

<pre>
/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
2
6
9
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
6
2
3
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
7
6
4
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
0
7
5
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
7
7
1
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
1
2
6
9
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
6
2
3
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
1
9
3
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
0
0
8
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
0
8
1
.
j
p
g

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
t
r
a
i
n
_
l
a
b
e
l
s
.
c
s
v
.
z
i
p

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
s
a
m
p
l
e
_
s
u
b
m
i
s
s
i
o
n
.
c
s
v
.
z
i
p

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
t
e
s
t
.
7
z

/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
t
r
a
i
n
.
7
z

</pre>
t
r
a
i
n
 
d
a
t
a
가
 
z
i
p
 
형
식
이
므
로
 
압
축
 
되
어
 
있
어
,
 
먼
저
 
압
축
 
풀
기
 
이
후
 
분
석
을
 
진
행
하
겠
습
니
다
.




폴
더
는
 
o
u
t
p
u
t
에
(
-
O
)
 
저
장
됩
니
다



```python
#
u
n
z
i
p

!
u
n
z
i
p
 
-
q
 
-
o
 
/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
t
r
a
i
n
_
l
a
b
e
l
s
.
c
s
v
.
z
i
p
 
```


```python
t
r
a
i
n
=
p
d
.
r
e
a
d
_
c
s
v
(
'
t
r
a
i
n
_
l
a
b
e
l
s
.
c
s
v
'
)

t
r
a
i
n
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
0

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
1

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
 
0

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
 
 
1

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

2
2
9
0
 
 
2
2
9
1
 
 
 
 
 
 
 
 
 
1

2
2
9
1
 
 
2
2
9
2
 
 
 
 
 
 
 
 
 
1

2
2
9
2
 
 
2
2
9
3
 
 
 
 
 
 
 
 
 
1

2
2
9
3
 
 
2
2
9
4
 
 
 
 
 
 
 
 
 
1

2
2
9
4
 
 
2
2
9
5
 
 
 
 
 
 
 
 
 
1


[
2
2
9
5
 
r
o
w
s
 
x
 
2
 
c
o
l
u
m
n
s
]
</pre>
t
r
a
i
n
 
d
a
t
a
에
는
 
i
n
v
a
s
i
v
e
 
s
p
e
c
i
e
s
의
 
포
함
 
여
부
가
 
0
(
불
포
함
)
 
혹
은
 
1
(
포
함
)
로
 
표
기
 
되
어
 
있
습
니
다
.


t
r
a
i
n
[
'
p
a
t
h
'
]
의
 
상
위
 
폴
더
는
 
고
정
 
값
으
로
 
넣
어
주
고
,
 
n
a
m
e
 
c
o
l
u
m
n
의
 
값
에
 
따
라
 
달
라
지
므
로
 
s
t
r
i
n
g
 
형
식
으
로
 
넣
어
줍
니
다
.
 
이
후
 
'
.
j
p
g
'
로
 
동
일
한
 
확
장
자
를
 
추
가
하
였
습
니
다
.



```python
t
r
a
i
n
[
'
p
a
t
h
'
]
=
'
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
'
+
t
r
a
i
n
[
'
n
a
m
e
'
]
.
a
s
t
y
p
e
(
s
t
r
)
+
'
.
j
p
g
'

t
r
a
i
n
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
1
.
j
p
g

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
.
j
p
g

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
3
.
j
p
g

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
4
.
j
p
g

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
5
.
j
p
g

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.

2
2
9
0
 
 
2
2
9
1
 
 
 
 
 
 
 
 
 
1
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
2
9
1
.
j
p
g

2
2
9
1
 
 
2
2
9
2
 
 
 
 
 
 
 
 
 
1
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
2
9
2
.
j
p
g

2
2
9
2
 
 
2
2
9
3
 
 
 
 
 
 
 
 
 
1
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
2
9
3
.
j
p
g

2
2
9
3
 
 
2
2
9
4
 
 
 
 
 
 
 
 
 
1
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
2
9
4
.
j
p
g

2
2
9
4
 
 
2
2
9
5
 
 
 
 
 
 
 
 
 
1
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
r
a
i
n
/
2
2
9
5
.
j
p
g


[
2
2
9
5
 
r
o
w
s
 
x
 
3
 
c
o
l
u
m
n
s
]
</pre>

```python
t
r
a
i
n
[
'
i
n
v
a
s
i
v
e
'
]
=
t
r
a
i
n
[
'
i
n
v
a
s
i
v
e
'
]
.
a
s
t
y
p
e
(
s
t
r
)
```


```python
!
u
n
z
i
p
 
-
q
 
-
o
 
/
k
a
g
g
l
e
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
-
s
p
e
c
i
e
s
-
m
o
n
i
t
o
r
i
n
g
/
s
a
m
p
l
e
_
s
u
b
m
i
s
s
i
o
n
.
c
s
v
.
z
i
p
```

t
e
s
t
 
d
a
t
a
가
 
제
공
 
되
어
 
있
지
 
않
아
,
 
정
답
 
값
 
[
'
i
n
v
a
s
i
v
e
'
]
 
c
o
l
u
m
n
이
 
없
는
 
s
u
b
m
i
s
s
i
o
n
 
d
a
t
a
를
 
이
용
해
 
t
e
s
t
 
d
a
t
a
로
 
활
용
하
겠
습
니
다
.



```python
t
e
s
t
=
p
d
.
r
e
a
d
_
c
s
v
(
'
.
/
s
a
m
p
l
e
_
s
u
b
m
i
s
s
i
o
n
.
c
s
v
'
)

t
e
s
t
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
.
5

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
0
.
5

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
0
.
5

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
0
.
5

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
.
5

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

1
5
2
6
 
 
1
5
2
7
 
 
 
 
 
 
 
0
.
5

1
5
2
7
 
 
1
5
2
8
 
 
 
 
 
 
 
0
.
5

1
5
2
8
 
 
1
5
2
9
 
 
 
 
 
 
 
0
.
5

1
5
2
9
 
 
1
5
3
0
 
 
 
 
 
 
 
0
.
5

1
5
3
0
 
 
1
5
3
1
 
 
 
 
 
 
 
0
.
5


[
1
5
3
1
 
r
o
w
s
 
x
 
2
 
c
o
l
u
m
n
s
]
</pre>

```python
t
e
s
t
[
'
p
a
t
h
'
]
=
'
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
'
+
t
e
s
t
[
'
n
a
m
e
'
]
.
a
s
t
y
p
e
(
s
t
r
)
+
'
.
j
p
g
'

t
e
s
t
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
.
j
p
g

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
2
.
j
p
g

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
3
.
j
p
g

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
4
.
j
p
g

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
5
.
j
p
g

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.

1
5
2
6
 
 
1
5
2
7
 
 
 
 
 
 
 
0
.
5
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
5
2
7
.
j
p
g

1
5
2
7
 
 
1
5
2
8
 
 
 
 
 
 
 
0
.
5
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
5
2
8
.
j
p
g

1
5
2
8
 
 
1
5
2
9
 
 
 
 
 
 
 
0
.
5
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
5
2
9
.
j
p
g

1
5
2
9
 
 
1
5
3
0
 
 
 
 
 
 
 
0
.
5
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
5
3
0
.
j
p
g

1
5
3
0
 
 
1
5
3
1
 
 
 
 
 
 
 
0
.
5
 
 
.
.
/
i
n
p
u
t
/
i
n
v
a
s
i
v
e
s
p
e
c
i
e
s
/
t
e
s
t
/
1
5
3
1
.
j
p
g


[
1
5
3
1
 
r
o
w
s
 
x
 
3
 
c
o
l
u
m
n
s
]
</pre>
D
a
t
a
F
r
a
m
e
 
형
식
의
 
데
이
터
에
는
 
'
p
a
t
h
'
 
c
o
l
u
m
n
에
 
이
미
지
 
경
로
를
 
내
포
하
고
 
있
습
니
다
.




t
r
a
i
n
 
d
a
t
a
로
 
부
터
 
t
r
a
i
n
i
n
g
/
v
a
l
i
d
a
t
i
o
n
 
d
a
t
a
로
 
나
누
고
,
 
t
r
a
i
n
i
n
g
/
v
a
l
i
d
a
t
i
o
n
/
t
e
s
t
i
n
g
 
d
a
t
a
를
 
모
두
 
t
e
n
s
o
r
f
l
o
w
의
 
I
m
a
g
e
D
a
t
a
G
e
n
e
r
a
t
o
r
를
 
이
용
하
여
 
I
m
a
g
e
 
D
a
t
a
를
 
불
러
오
겠
습
니
다
.



```python
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
p
r
e
p
r
o
c
e
s
s
i
n
g
.
i
m
a
g
e
 
i
m
p
o
r
t
 
I
m
a
g
e
D
a
t
a
G
e
n
e
r
a
t
o
r

i
d
g
=
I
m
a
g
e
D
a
t
a
G
e
n
e
r
a
t
o
r
(
)

f
r
o
m
 
s
k
l
e
a
r
n
.
m
o
d
e
l
_
s
e
l
e
c
t
i
o
n
 
i
m
p
o
r
t
 
t
r
a
i
n
_
t
e
s
t
_
s
p
l
i
t

x
_
t
r
a
i
n
,
 
x
_
v
a
l
i
d
 
=
 
t
r
a
i
n
_
t
e
s
t
_
s
p
l
i
t
(
t
r
a
i
n
,
t
e
s
t
_
s
i
z
e
=
0
.
2
,
r
a
n
d
o
m
_
s
t
a
t
e
=
4
2
,
s
t
r
a
t
i
f
y
=
t
r
a
i
n
[
'
i
n
v
a
s
i
v
e
'
]
)
```


```python
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
=
i
d
g
.
f
l
o
w
_
f
r
o
m
_
d
a
t
a
f
r
a
m
e
(
x
_
t
r
a
i
n
,
x
_
c
o
l
=
'
p
a
t
h
'
,
y
_
c
o
l
=
'
i
n
v
a
s
i
v
e
'
)
```

<pre>
F
o
u
n
d
 
1
8
3
6
 
v
a
l
i
d
a
t
e
d
 
i
m
a
g
e
 
f
i
l
e
n
a
m
e
s
 
b
e
l
o
n
g
i
n
g
 
t
o
 
2
 
c
l
a
s
s
e
s
.

</pre>

```python
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
=
i
d
g
.
f
l
o
w
_
f
r
o
m
_
d
a
t
a
f
r
a
m
e
(
x
_
v
a
l
i
d
,
x
_
c
o
l
=
'
p
a
t
h
'
,
y
_
c
o
l
=
'
i
n
v
a
s
i
v
e
'
)
```

<pre>
F
o
u
n
d
 
4
5
9
 
v
a
l
i
d
a
t
e
d
 
i
m
a
g
e
 
f
i
l
e
n
a
m
e
s
 
b
e
l
o
n
g
i
n
g
 
t
o
 
2
 
c
l
a
s
s
e
s
.

</pre>
i
n
v
a
s
i
v
e
 
s
p
e
c
i
e
s
의
 
존
재
 
여
부
로
 
2
가
지
 
c
l
a
s
s
를
 
가
지
고
 
t
r
a
i
n
 
i
m
a
g
e
는
 
1
8
3
6
개
,
 
v
a
l
i
d
a
t
i
o
n
 
i
m
a
g
e
는
 
4
5
9
로
 
나
누
어
져
 
있
습
니
다
.




이
는
 
4
:
1
의
 
비
율
인
데
 
t
e
s
t
_
s
i
z
e
를
 
0
.
2
로
 
2
0
%
의
 
데
이
터
를
 
v
a
l
i
d
a
t
i
o
n
 
d
a
t
a
로
 
분
류
하
기
 
때
문
입
니
다
.



```python
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
 
i
m
p
o
r
t
 
*

f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
l
a
y
e
r
s
 
i
m
p
o
r
t
 
*

f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
.
e
f
f
i
c
i
e
n
t
n
e
t
 
i
m
p
o
r
t
 
*
 
#
층
이
 
많
은
 
모
델
을
 
가
져
와
서
 
학
습
,
 
p
r
e
t
r
a
i
n
e
d

f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
c
a
l
l
b
a
c
k
s
 
i
m
p
o
r
t
 
*
```


```python
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
.
v
g
g
1
6
 
i
m
p
o
r
t
 
*

f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
.
v
g
g
1
9
 
i
m
p
o
r
t
 
*
```

*
점
수
개
선
*




동
일
 
조
건
에
서
 
실
험
하
였
을
 
때
,
 
아
래
와
 
같
은
 
순
으
로
 
점
수
가
 
개
선
 
된
 
것
을
 
확
인
하
였
습
니
다
.




변
형
 
C
o
n
v
2
D
 
<
 
변
형
 
C
o
n
v
2
D
 
+
 
B
a
t
c
h
N
o
r
m
a
l
i
z
a
t
i
o
n
 
추
가
 
 
<
 
V
G
G
1
9
 
<
 
V
G
G
1
6
 
<
 
R
e
s
N
e
t
5
0
 
<
 
I
n
c
e
p
t
i
o
n
V
3
 
<
 
E
f
f
i
c
i
e
n
t
N
e
t
B
1
+
M
o
d
e
l
C
h
e
c
k
p
o
i
n
t
 
<
 
E
f
f
i
c
i
e
n
t
N
e
t
B
1
 
<
 
M
o
b
i
l
e
N
e
t
 
<
 
E
f
f
i
c
i
e
n
t
N
e
t
B
0
 
<
 
X
c
e
p
t
i
o
n


여
기
에
서
 
주
목
하
게
 
되
는
 
점
은
,
 
V
G
G
1
6
이
 
V
G
G
1
9
보
다
 
점
수
가
 
개
선
되
고
,
 
E
f
f
i
c
i
e
n
t
N
e
t
B
0
가
 
E
f
f
i
c
i
e
n
t
N
e
t
B
1
보
다
 
점
수
가
 
개
선
된
 
것
을
 
확
인
할
 
수
 
있
습
니
다
.




V
G
G
1
6
에
서
 
V
G
G
1
9
를
 
사
용
하
게
 
될
 
때
,
 
레
이
어
층
을
 
더
 
깊
게
 
사
용
하
나
 
반
드
시
 
정
확
도
가
 
개
선
되
는
 
것
은
 
아
닌
 
것
으
로
 
보
입
니
다
.




!
[
i
m
a
g
e
.
p
n
g
]
(
a
t
t
a
c
h
m
e
n
t
:
1
4
7
d
c
f
c
1
-
e
8
9
d
-
4
1
3
a
-
9
2
9
b
-
2
0
0
b
e
0
1
9
d
9
7
6
.
p
n
g
)
!
[
i
m
a
g
e
.
p
n
g
]
(
a
t
t
a
c
h
m
e
n
t
:
b
6
1
2
2
c
1
3
-
b
d
f
0
-
4
0
4
f
-
b
6
c
7
-
1
9
f
b
4
4
a
4
c
9
5
5
.
p
n
g
)


E
f
f
i
c
i
e
n
t
N
e
t
B
0
에
서
 
E
f
f
i
c
i
e
n
t
N
e
t
B
1
보
다
 
점
수
가
 
개
선
되
지
 
않
은
 
이
유
는
 
c
a
l
l
b
a
c
k
의
 
p
a
t
i
e
n
c
e
 
인
자
 
조
절
이
 
적
합
치
 
않
아
 
최
적
화
되
지
 
않
은
 
상
태
의
 
학
습
을
 
했
을
 
것
으
로
 
보
입
니
다
.




p
a
r
a
m
e
t
e
r
가
 
늘
어
났
지
만
,
 
최
적
의
 
학
습
을
 
위
해
 
적
합
한
 
인
자
값
을
 
찾
는
 
노
력
이
 
수
반
되
어
야
 
합
니
다
.




I
n
c
e
p
t
i
o
n
V
3
가
 
V
1
6
과
 
V
1
9
보
다
 
예
측
 
정
확
도
가
 
향
상
하
였
는
데
,
 
이
는
 
매
개
변
수
 
수
는
 
줄
었
고
 
네
트
워
크
 
성
능
은
 
좋
아
졌
습
니
다
.
 
위
의
 
그
래
프
를
 
볼
 
때
,
 
파
라
미
터
의
 
수
가
 
증
가
할
 
수
록
 
정
확
도
가
 
향
상
되
는
 
경
향
을
 
보
이
지
만
 
각
 
모
델
마
다
 
향
상
되
는
 
속
도
가
 
달
라
짐
을
 
확
인
했
습
니
다
.


s
c
o
r
e
 
:
 
0
.
7
9
7
1
2



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
C
o
n
v
o
l
u
t
i
o
n
2
D
(
3
2
,
3
,
3
)
)

#
 
m
o
d
e
l
.
a
d
d
(
M
a
x
P
o
o
l
i
n
g
2
D
(
p
o
o
l
_
s
i
z
e
=
(
2
,
2
)
)
)

#
 
m
o
d
e
l
.
a
d
d
(
F
l
a
t
t
e
n
(
)
)

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
8
3
2
9
8



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
C
o
n
v
o
l
u
t
i
o
n
2
D
(
3
2
,
3
,
3
)
)

#
 
m
o
d
e
l
.
a
d
d
(
M
a
x
P
o
o
l
i
n
g
2
D
(
p
o
o
l
_
s
i
z
e
=
(
2
,
2
)
)
)

#
 
m
o
d
e
l
.
a
d
d
(
F
l
a
t
t
e
n
(
)
)

#
 
m
o
d
e
l
.
a
d
d
(
B
a
t
c
h
N
o
r
m
a
l
i
z
a
t
i
o
n
(
a
x
i
s
=
-
1
)
)

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
9
6
6
9
8


#
 
V
G
G




1
.
 
규
모
가
 
큰
 
합
성
곱
을
 
여
러
 
작
은
 
합
성
곱
으
로
 
대
체




처
음
에
는
 
3
X
3
 
커
널
을
 
갖
는
 
두
 
합
성
곱
 
계
층
을
 
쌓
은
 
스
택
이
 
5
X
5
 
커
널
을
 
갖
는
 
하
나
의
 
합
성
곱
 
계
층
과
 
동
일
한
 
수
용
 
영
역
을
 
갖
는
다
.




이
와
 
마
찬
가
지
로
 
3
X
3
 
합
성
곱
 
계
층
을
 
3
개
 
연
이
어
 
배
치
하
면
 
수
용
 
영
역
은
 
7
X
7
이
 
되
고
 
5
개
의
 
3
X
3
 
합
성
곱
의
 
수
용
 
영
역
은
 
1
1
X
1
1
이
 
된
다
.




V
G
G
 
네
트
워
크
는
 
이
보
다
 
작
은
 
합
성
곱
 
계
층
을
 
더
 
많
이
 
포
함
해
 
더
 
큰
 
E
R
F
를
 
얻
을
 
수
 
있
다
.
 
따
라
서
 
매
개
변
수
 
개
수
를
 
줄
이
고
,
 
비
선
형
성
을
 
증
가
시
킬
 
수
 
있
다
는
 
장
점
이
 
있
다
.




2
.
 
특
정
 
맵
 
깊
이
를
 
증
가




각
 
합
성
곱
 
블
록
에
 
대
한
 
특
징
 
맵
의
 
깊
이
를
 
두
 
배
로
 
늘
렸
다
.
 
각
 
집
합
 
다
음
에
는
 
윈
도
우
 
크
기
가
 
2
X
2
이
고
 
보
폭
이
 
2
인
 
최
대
 
풀
링
 
계
층
이
 
나
오
므
로
 
깊
이
가
 
두
 
배
로
 
늘
고
 
공
간
 
차
원
은
 
반
으
로
 
줄
게
 
된
다
.




3
.
 
척
도
 
변
경
을
 
통
한
 
데
이
터
 
보
강




훈
련
이
 
반
복
될
 
때
마
다
 
이
미
지
 
배
치
를
 
적
절
한
 
입
력
 
크
기
로
 
자
르
기
 
전
에
 
그
 
척
도
를
 
무
작
위
로
 
조
정
한
다
.
 
이
렇
게
 
무
작
위
로
 
변
환
함
으
로
써
 
네
트
워
크
는
 
다
양
한
 
척
도
의
 
샘
플
을
 
경
험
하
게
 
되
고
 
이
러
한
 
척
도
 
변
경
에
도
 
불
구
하
고
 
이
미
지
를
 
적
절
히
 
분
류
하
는
 
방
법
을
 
학
습
하
게
 
된
다
.




4
.
 
완
전
 
연
결
 
계
층
을
 
합
성
곱
 
계
층
으
로
 
대
체




크
기
가
 
좀
 
더
 
큰
 
커
널
 
(
7
X
7
과
 
3
X
3
)
을
 
적
용
한
 
첫
 
번
째
 
합
성
곱
 
세
트
는
 
특
징
 
맵
의
 
공
간
 
크
기
를
 
1
X
1
로
 
줄
이
고
 
(
그
 
전
에
 
패
딩
을
 
적
용
하
지
 
않
았
다
면
)
 
특
징
 
맵
의
 
깊
이
를
 
4
,
0
9
6
으
로
 
늘
린
다
.
 
마
지
막
으
로
 
1
X
1
 
합
성
곱
 
계
층
이
 
예
측
해
야
 
할
 
클
래
스
 
개
수
만
큼
의
 
필
터
와
 
함
께
 
사
용
된
다
.
 
그
 
결
과
 
얻
게
 
된
 
1
X
1
X
N
 
벡
터
는
 
s
o
f
t
m
a
x
 
함
수
로
 
정
규
화
된
 
다
음
 
평
면
화
되
어
 
최
종
 
클
래
스
 
예
측
으
로
 
출
력
된
다
.



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
V
G
G
1
9
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
9
6
8
7
6



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
V
G
G
1
6
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

#
 
R
e
s
N
e
t
 
-
 
잔
차
 
네
트
워
크




1
.
 
매
핑
 
대
신
 
잔
차
 
함
수
 
추
정
하
기


네
트
워
크
 
계
층
이
 
항
등
 
매
핑
을
 
쉽
게
 
학
습
할
 
수
 
있
다
면
 
(
즉
 
계
층
이
 
가
중
치
를
 
학
습
해
 
계
층
에
서
의
 
일
련
의
 
연
산
이
 
최
종
적
으
로
 
입
력
 
텐
서
와
 
동
일
한
 
텐
서
를
 
반
환
한
다
면
)
 
성
능
 
저
하
 
현
상
은
 
발
생
하
지
 
않
을
 
것
이
다
.




일
부
 
추
가
적
인
 
합
성
곱
 
계
층
을
 
사
용
해
 
데
이
터
를
 
추
가
로
 
처
리
하
는
 
경
로




항
등
 
매
핑
(
즉
,
 
데
이
터
에
 
어
떤
 
변
경
도
 
가
하
지
 
않
고
 
전
달
)
을
 
수
행
하
는
 
경
로




2
.
 
극
단
적
으
로
 
깊
이
 
들
어
가
기




잔
차
 
블
록
은
 
전
통
 
블
록
보
다
 
매
개
변
수
가
 
많
지
 
않
은
데
,
 
스
킵
과
 
덧
셈
 
연
산
에
는
 
어
떤
 
매
개
변
수
도
 
필
요
 
없
기
 
때
문
이
다
.
 
따
라
서
 
잔
차
블
록
은
 
'
상
당
히
 
깊
은
'
 
네
트
워
크
를
 
구
성
할
 
때
 
효
율
적
이
다
.


s
c
o
r
e
 
:
 
0
.
9
8
6
6
6



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
R
e
s
N
e
t
5
0
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

#
 
I
n
c
e
p
t
i
o
n
 
모
듈




1
.
 
다
양
한
 
세
부
 
특
징
 
잡
아
내
기




기
본
 
인
셉
션
 
모
듈
은
 
4
개
의
 
병
렬
 
계
층
 
즉
,
 
3
개
의
 
합
성
곱
 
계
층
(
필
터
 
크
기
는
 
각
각
 
1
x
1
,
 
3
x
3
,
 
5
x
5
)
과
 
하
나
의
 
최
대
-
풀
링
 
계
측
으
로
 
구
성
된
다
.
 
계
층
의
 
결
과
를
 
하
나
로
 
연
결
해
 
최
종
 
결
과
를
 
만
드
는
 
이
 
병
렬
 
처
리
는
 
이
점
을
 
갖
고
 
있
다
.
 
척
도
가
 
다
양
한
 
데
이
터
 
처
리
를
 
가
능
하
게
 
해
준
다
.
 
각
 
인
셉
션
 
모
듈
의
 
결
과
는
 
다
양
한
 
척
도
의
 
특
징
을
 
결
합
해
 
더
 
광
범
위
한
 
정
보
를
 
잡
아
낸
다
.
 
이
 
경
우
 
최
선
의
 
커
널
 
크
기
를
 
선
택
할
 
필
요
가
 
없
다
.
 
즉
 
네
트
워
크
가
 
스
스
스
로
 
각
 
모
듈
에
 
대
해
 
어
느
 
합
성
곱
 
계
층
에
 
더
 
의
존
하
는
지
 
학
습
한
다
.




서
로
 
다
른
 
계
층
에
서
 
매
핑
된
 
특
징
을
 
연
결
하
는
 
것
으
로
 
C
N
N
에
 
비
선
형
성
이
 
추
가
된
다
.




2
.
 
병
목
 
계
층
으
로
 
1
x
1
 
합
성
곱
 
계
층
을
 
사
용




3
.
 
완
전
 
연
결
 
계
층
 
대
신
 
풀
링
 
계
층
 
사
용


매
개
변
수
 
개
수
를
 
줄
이
기
 
위
해
 
마
지
막
 
합
성
곱
 
블
록
 
다
음
에
 
완
전
 
연
결
 
계
층
 
대
신
 
평
균
-
풀
링
 
계
층
을
 
사
용
할
 
수
 
있
다
.
 
윈
도
우
 
크
기
로
 
7
x
7
,
 
보
폭
으
로
 
1
을
 
설
정
하
면
 
이
 
계
층
은
 
훈
련
시
킬
 
배
개
변
수
 
하
나
 
없
이
 
특
징
 
볼
륨
을
 
7
x
7
x
1
0
2
4
에
서
 
1
x
1
x
1
0
2
4
로
 
줄
인
다
.
 
밀
집
 
계
층
이
 
오
면
 
(
7
x
7
x
1
0
2
4
)
x
1
0
2
4
 
개
의
 
매
개
변
수
가
 
추
가
 
될
 
것
이
다
.
 
물
론
 
풀
링
 
계
층
으
로
 
대
체
하
면
 
네
트
워
크
가
 
표
현
력
을
 
약
간
 
잃
게
 
되
지
만
,
 
계
산
상
으
로
 
얻
는
 
이
익
이
 
막
대
하
다
.




4
.
 
중
간
 
손
실
로
 
경
사
 
소
실
 
문
제
 
해
결
하
기


C
N
N
이
 
깊
어
질
수
록
 
경
사
가
 
소
실
되
어
 
문
제
가
 
되
는
 
경
우
가
 
많
다
.
 
많
은
 
C
N
N
연
산
(
예
를
 
들
어
 
시
그
모
이
드
)
에
는
 
진
폭
이
 
작
은
(
1
보
다
 
작
은
)
 
도
함
수
가
 
있
다
.
 
따
라
서
 
계
층
 
수
가
 
많
을
 
수
록
 
역
전
파
할
 
때
 
도
함
수
의
 
곱
은
 
작
아
진
다
(
1
보
다
 
작
은
 
값
을
 
여
러
 
번
 
곱
하
면
 
그
 
결
과
는
 
0
에
 
가
까
워
지
기
 
때
문
에
)
 
이
렇
게
 
첫
번
째
 
계
층
에
 
도
착
했
을
 
때
 
대
체
로
 
경
사
는
 
소
실
되
거
나
 
0
에
 
가
까
워
진
다
.
 
경
삿
값
이
 
매
개
변
수
 
업
데
이
트
에
 
직
접
 
사
용
되
기
 
때
문
에
 
경
사
가
 
너
무
 
작
으
면
 
이
 
계
층
들
은
 
효
과
적
으
로
 
학
습
할
 
수
 
없
다
.
 
솔
루
션
은
 
다
양
한
 
네
트
워
크
 
깊
이
에
서
 
추
가
적
인
 
분
류
 
손
실
을
 
도
입
함
으
로
써
 
첫
번
째
 
계
층
과
 
예
측
 
사
이
의
 
거
리
를
 
줄
이
는
 
것
이
다
.
 
마
지
막
 
손
실
에
서
의
 
경
사
가
 
적
절
하
게
 
첫
번
째
 
계
층
까
지
 
흐
를
 
수
 
없
더
라
도
 
그
보
다
 
더
 
가
까
운
 
중
간
 
손
실
 
덕
에
 
분
류
작
업
에
 
도
움
이
 
되
게
 
훈
련
될
 
수
 
있
다
.




s
c
o
r
e
 
:
 
0
.
9
8
7
2
4



```python
#
 
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
 
i
m
p
o
r
t
 
*

#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
I
n
c
e
p
t
i
o
n
V
3
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
9
8
8
7
3



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
c
=
M
o
d
e
l
C
h
e
c
k
p
o
i
n
t
(
p
a
t
i
e
n
c
e
=
2
,
v
e
r
b
o
s
e
=
1
,
f
i
l
e
p
a
t
h
=
'
.
/
_
M
o
d
e
l
C
h
e
c
k
P
o
i
n
t
/
k
e
r
a
s
.
h
d
f
5
'
)

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
E
f
f
i
c
i
e
n
t
N
e
t
B
1
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
,
m
c
]
)
```

s
c
o
r
e
 
:
 
0
.
9
9
0
9
5



```python
#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
E
f
f
i
c
i
e
n
t
N
e
t
B
1
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
9
9
1
1
3



```python
#
 
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
.
m
o
b
i
l
e
n
e
t
 
i
m
p
o
r
t
 
M
o
b
i
l
e
N
e
t

#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
M
o
b
i
l
e
N
e
t
(
w
e
i
g
h
t
s
=
'
i
m
a
g
e
n
e
t
'
,
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

s
c
o
r
e
 
:
 
0
.
9
9
2
3
3



```python
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

m
o
d
e
l
.
a
d
d
(
E
f
f
i
c
i
e
n
t
N
e
t
B
0
(
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```

<pre>
D
o
w
n
l
o
a
d
i
n
g
 
d
a
t
a
 
f
r
o
m
 
h
t
t
p
s
:
/
/
s
t
o
r
a
g
e
.
g
o
o
g
l
e
a
p
i
s
.
c
o
m
/
k
e
r
a
s
-
a
p
p
l
i
c
a
t
i
o
n
s
/
e
f
f
i
c
i
e
n
t
n
e
t
b
0
_
n
o
t
o
p
.
h
5

1
6
7
1
1
6
8
0
/
1
6
7
0
5
2
0
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
0
s
 
0
u
s
/
s
t
e
p

1
6
7
1
9
8
7
2
/
1
6
7
0
5
2
0
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
0
s
 
0
u
s
/
s
t
e
p

E
p
o
c
h
 
1
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
1
1
2
s
 
2
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
2
0
5
0
 
-
 
a
c
c
:
 
0
.
9
2
1
6
 
-
 
v
a
l
_
l
o
s
s
:
 
1
.
0
0
7
6
 
-
 
v
a
l
_
a
c
c
:
 
0
.
8
5
8
4

E
p
o
c
h
 
2
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
8
9
3
 
-
 
a
c
c
:
 
0
.
9
7
1
1
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
7
2
5
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
7
8
2

E
p
o
c
h
 
3
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
6
9
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
2
0
7
 
-
 
a
c
c
:
 
0
.
9
9
2
4
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
1
7
5
6
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
5
8
6

E
p
o
c
h
 
4
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
4
5
3
 
-
 
a
c
c
:
 
0
.
9
8
4
2
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
5
1
8
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
8
6
9

E
p
o
c
h
 
5
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
1
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
6
0
4
 
-
 
a
c
c
:
 
0
.
9
7
8
8
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
1
1
2
2
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
6
9
5

E
p
o
c
h
 
6
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
1
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
2
3
0
 
-
 
a
c
c
:
 
0
.
9
9
2
9
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
3
5
7
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
8
6
9

E
p
o
c
h
 
7
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
1
8
0
 
-
 
a
c
c
:
 
0
.
9
9
3
5
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
1
0
6
1
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
6
5
1

E
p
o
c
h
 
8
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
1
9
5
 
-
 
a
c
c
:
 
0
.
9
9
2
9
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
2
8
9
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
9
3
5

E
p
o
c
h
 
9
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
1
3
5
 
-
 
a
c
c
:
 
0
.
9
9
5
6
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
1
8
1
9
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
4
9
9

E
p
o
c
h
 
1
0
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
2
6
0
 
-
 
a
c
c
:
 
0
.
9
8
9
1
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
1
9
3
5
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
7
3
9

E
p
o
c
h
 
1
1
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
7
0
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
0
6
3
 
-
 
a
c
c
:
 
0
.
9
9
8
9
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
6
7
6
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
8
9
1


E
p
o
c
h
 
0
0
0
1
1
:
 
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
 
r
e
d
u
c
i
n
g
 
l
e
a
r
n
i
n
g
 
r
a
t
e
 
t
o
 
0
.
0
0
0
1
0
0
0
0
0
0
0
4
7
4
9
7
4
5
1
3
.

E
p
o
c
h
 
1
2
/
1
0
0
0

5
8
/
5
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
6
9
s
 
1
s
/
s
t
e
p
 
-
 
l
o
s
s
:
 
0
.
0
0
1
9
 
-
 
a
c
c
:
 
0
.
9
9
9
5
 
-
 
v
a
l
_
l
o
s
s
:
 
0
.
0
5
8
7
 
-
 
v
a
l
_
a
c
c
:
 
0
.
9
8
9
1

</pre>
<pre>
<
k
e
r
a
s
.
c
a
l
l
b
a
c
k
s
.
H
i
s
t
o
r
y
 
a
t
 
0
x
7
f
a
d
e
4
0
6
c
f
1
0
>
</pre>
s
c
o
r
e
 
:
 
0
.
9
9
3
1
5



```python
#
 
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
.
x
c
e
p
t
i
o
n
 
i
m
p
o
r
t
 
X
c
e
p
t
i
o
n

#
 
e
s
=
E
a
r
l
y
S
t
o
p
p
i
n
g
(
p
a
t
i
e
n
c
e
=
4
,
r
e
s
t
o
r
e
_
b
e
s
t
_
w
e
i
g
h
t
s
=
T
r
u
e
)
 
#
 
3
~
4
 
적
정
,
 
점
수
개
선

#
 
r
l
=
R
e
d
u
c
e
L
R
O
n
P
l
a
t
e
a
u
(
p
a
t
i
e
n
c
e
=
3
,
v
e
r
b
o
s
e
=
1
)
#
P
l
a
t
e
a
u
 
개
선
이
 
안
 
될
때
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
이
겠
다
 
y
=
x
^
2
에
서
 
0
이
 
최
적
이
나
 
2
0
으
로
 
시
작
했
을
 
때
 
줄
어
드
는
데
,
 
얼
마
나
 
빨
리
 
줄
어
들
지
,
지
나
치
지
 
않
게
 
l
e
a
r
n
i
n
g
 
r
a
t
e
를
 
줄
임

#
 
m
o
d
e
l
=
S
e
q
u
e
n
t
i
a
l
(
)
 
#
B
 
숫
자
 
증
가
~
성
능
 
향
상
 

#
 
m
o
d
e
l
.
a
d
d
(
X
c
e
p
t
i
o
n
(
w
e
i
g
h
t
s
=
'
i
m
a
g
e
n
e
t
'
,
i
n
c
l
u
d
e
_
t
o
p
=
F
a
l
s
e
,
p
o
o
l
i
n
g
=
'
a
v
g
'
)
)
#
0
과
 
1
 
구
분
,
 
클
래
스
 
1
0
0
0
개
 
나
눈
 
모
델
 
가
져
옴
 
출
력
층
은
 
t
o
p
이
라
고
 
하
는
데
 
가
져
오
지
 
않
겠
다
/
직
접
선
언
필
요
,
 
f
l
a
t
t
e
n
처
럼
 
자
동
으
로
 
쌓
이
게

#
 
m
o
d
e
l
.
a
d
d
(
D
e
n
s
e
(
2
,
a
c
t
i
v
a
t
i
o
n
=
'
s
o
f
t
m
a
x
'
)
)
 
#
출
력
층
 
클
래
스
 
2
개


#
 
m
o
d
e
l
.
c
o
m
p
i
l
e
(
o
p
t
i
m
i
z
e
r
=
'
a
d
a
m
'
,
 
m
e
t
r
i
c
s
=
'
a
c
c
'
,
 
l
o
s
s
=
'
c
a
t
e
g
o
r
i
c
a
l
_
c
r
o
s
s
e
n
t
r
o
p
y
'
)
 
#
 
s
p
a
r
s
e
하
지
 
않
는
 
경
우
:
 
정
답
값
이
 
문
자
로
 
들
어
와
서
 
오
류
발
생

#
 
m
o
d
e
l
.
f
i
t
(
t
r
a
i
n
_
g
e
n
e
r
a
t
o
r
,
v
a
l
i
d
a
t
i
o
n
_
d
a
t
a
=
v
a
l
i
d
_
g
e
n
e
r
a
t
o
r
,
e
p
o
c
h
s
=
1
0
0
0
,
c
a
l
l
b
a
c
k
s
=
[
e
s
,
r
l
]
)
```


```python
f
r
o
m
 
t
e
n
s
o
r
f
l
o
w
.
k
e
r
a
s
.
a
p
p
l
i
c
a
t
i
o
n
s
 
i
m
p
o
r
t
 
*
```


```python
t
e
s
t
_
g
e
n
e
r
a
t
o
r
=
i
d
g
.
f
l
o
w
_
f
r
o
m
_
d
a
t
a
f
r
a
m
e
(
t
e
s
t
,
x
_
c
o
l
=
'
p
a
t
h
'
,
y
_
c
o
l
=
N
o
n
e
,
s
h
u
f
f
l
e
=
F
a
l
s
e
,
c
l
a
s
s
_
m
o
d
e
=
N
o
n
e
)
 
#
 
s
h
u
f
f
l
e
 
d
e
f
a
u
l
t
 
t
r
u
e
 
일
 
경
우
 
:
 
딥
러
닝
 
(
b
a
t
c
h
_
s
i
z
e
로
 
학
습
 
나
눠
서
)
,
 
i
m
a
g
e
 
사
이
즈
가
 
작
아
도
 
칼
럼
이
 
많
아
 
(
r
g
b
등
)
 
램
 
소
모
량
 
많
음
 
순
서
를
 
바
뀌
어
줘
야
 
b
a
t
c
h
내
의
 
구
성
이
 
다
양
하
게

#
c
l
a
s
s
_
m
o
d
e
=
c
a
t
e
g
o
r
i
c
a
l
이
 
d
e
f
a
u
l
t
 
t
r
a
i
n
에
 
정
답
값
이
 
들
어
왔
으
나
 
t
e
s
t
에
는
 
아
직
 
정
답
값
이
 
없
으
므
로
 
오
류
 
발
생
 
c
l
a
s
s
_
m
o
d
e
 
N
o
n
e
으
로
 
설
정
```

<pre>
F
o
u
n
d
 
1
5
3
1
 
v
a
l
i
d
a
t
e
d
 
i
m
a
g
e
 
f
i
l
e
n
a
m
e
s
.

</pre>

```python
r
e
s
u
l
t
=
m
o
d
e
l
.
p
r
e
d
i
c
t
(
t
e
s
t
_
g
e
n
e
r
a
t
o
r
,
v
e
r
b
o
s
e
=
1
,
w
o
r
k
e
r
s
=
2
)
 
#
w
o
r
k
e
r
s
 
속
도
 
2
 
m
u
l
t
i
 
p
r
o
c
e
s
s
i
n
g
```

<pre>
4
8
/
4
8
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
]
 
-
 
4
1
s
 
8
0
6
m
s
/
s
t
e
p

</pre>

```python
r
e
s
u
l
t
 
#
r
o
c
 
a
u
c
 
얼
마
나
 
1
 
o
r
 
0
인
지
 
확
률
값
 
제
출
 
c
l
a
s
s
0
번
일
 
확
률
 
/
 
c
l
a
s
s
1
일
 
확
률
 
(
고
정
 
*
*
)
```

<pre>
a
r
r
a
y
(
[
[
2
.
7
1
8
6
3
6
3
e
-
0
3
,
 
9
.
9
7
2
8
1
3
1
e
-
0
1
]
,

 
 
 
 
 
 
 
[
9
.
9
7
3
4
5
3
9
e
-
0
1
,
 
2
.
6
5
4
6
1
2
1
e
-
0
3
]
,

 
 
 
 
 
 
 
[
9
.
9
8
9
8
2
0
1
e
-
0
1
,
 
1
.
0
1
7
9
2
7
2
e
-
0
3
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
9
.
9
9
9
9
7
7
4
e
-
0
1
,
 
2
.
2
1
4
7
2
5
1
e
-
0
6
]
,

 
 
 
 
 
 
 
[
1
.
1
0
5
1
2
7
2
e
-
0
7
,
 
9
.
9
9
9
9
9
8
8
e
-
0
1
]
,

 
 
 
 
 
 
 
[
1
.
6
6
5
8
7
1
5
e
-
0
6
,
 
9
.
9
9
9
9
8
3
3
e
-
0
1
]
]
,
 
d
t
y
p
e
=
f
l
o
a
t
3
2
)
</pre>

```python
s
u
b
=
p
d
.
r
e
a
d
_
c
s
v
(
'
.
/
s
a
m
p
l
e
_
s
u
b
m
i
s
s
i
o
n
.
c
s
v
'
)

s
u
b
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
.
5

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
0
.
5

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
0
.
5

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
0
.
5

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
.
5

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

1
5
2
6
 
 
1
5
2
7
 
 
 
 
 
 
 
0
.
5

1
5
2
7
 
 
1
5
2
8
 
 
 
 
 
 
 
0
.
5

1
5
2
8
 
 
1
5
2
9
 
 
 
 
 
 
 
0
.
5

1
5
2
9
 
 
1
5
3
0
 
 
 
 
 
 
 
0
.
5

1
5
3
0
 
 
1
5
3
1
 
 
 
 
 
 
 
0
.
5


[
1
5
3
1
 
r
o
w
s
 
x
 
2
 
c
o
l
u
m
n
s
]
</pre>
i
n
v
a
s
i
v
e
가
 
1
일
 
확
률
을
 
제
출
하
므
로
 
각
 
행
의
 
r
e
s
u
l
t
 
값
에
서
 
2
번
째
 
값
을
 
반
환
해
야
합
니
다
.




따
라
서
 
r
e
s
u
l
t
[
모
든
행
,
2
번
째
 
값
]
을
 
기
준
으
로
 
s
u
b
[
'
i
n
v
a
s
i
v
e
'
]
값
에
 
적
용
하
였
습
니
다
.



```python
s
u
b
[
'
i
n
v
a
s
i
v
e
'
]
=
r
e
s
u
l
t
[
:
,
1
]

s
u
b
```

<pre>
 
 
 
 
 
 
n
a
m
e
 
 
i
n
v
a
s
i
v
e

0
 
 
 
 
 
 
 
 
1
 
 
0
.
9
9
7
2
8
1

1
 
 
 
 
 
 
 
 
2
 
 
0
.
0
0
2
6
5
5

2
 
 
 
 
 
 
 
 
3
 
 
0
.
0
0
1
0
1
8

3
 
 
 
 
 
 
 
 
4
 
 
0
.
0
6
1
9
6
9

4
 
 
 
 
 
 
 
 
5
 
 
0
.
9
9
9
9
9
8

.
.
.
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

1
5
2
6
 
 
1
5
2
7
 
 
0
.
0
0
0
1
1
7

1
5
2
7
 
 
1
5
2
8
 
 
1
.
0
0
0
0
0
0

1
5
2
8
 
 
1
5
2
9
 
 
0
.
0
0
0
0
0
2

1
5
2
9
 
 
1
5
3
0
 
 
1
.
0
0
0
0
0
0

1
5
3
0
 
 
1
5
3
1
 
 
0
.
9
9
9
9
9
8


[
1
5
3
1
 
r
o
w
s
 
x
 
2
 
c
o
l
u
m
n
s
]
</pre>

```python
s
u
b
.
t
o
_
c
s
v
(
'
s
u
b
m
i
s
s
i
o
n
.
c
s
v
'
,
i
n
d
e
x
=
F
a
l
s
e
)
```
