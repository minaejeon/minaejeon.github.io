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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
.
c
s
v

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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
.
c
s
v

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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
1
7
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
4
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
3
8
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
6
9
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
8
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
6
4
1
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
1
7
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
1
5
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
4
9
1
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
7
1
8
.
p
n
g

</pre>

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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
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
 
 
 
 
f
i
l
e
_
n
a
m
e
 
l
a
b
e
l

0
 
 
 
 
 
0
0
1
.
p
n
g
 
 
1
0
-
2

1
 
 
 
 
 
0
0
2
.
p
n
g
 
 
1
0
-
1

2
 
 
 
 
 
0
0
3
.
p
n
g
 
 
 
 
 
3

3
 
 
 
 
 
0
0
4
.
p
n
g
 
 
 
 
 
8

4
 
 
 
 
 
0
0
5
.
p
n
g
 
 
 
 
 
9

.
.
 
 
 
 
 
 
 
 
.
.
.
 
 
 
.
.
.

8
5
3
 
 
 
8
5
4
.
p
n
g
 
 
 
 
 
9

8
5
4
 
 
 
8
5
5
.
p
n
g
 
 
 
 
 
1

8
5
5
 
 
 
8
5
6
.
p
n
g
 
 
 
 
 
4

8
5
6
 
 
 
8
5
7
.
p
n
g
 
 
1
0
-
1

8
5
7
 
 
 
8
5
8
.
p
n
g
 
 
 
 
 
7


[
8
5
8
 
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
p
u
b
l
i
c
 
:
 
p
r
i
v
a
t
e
 
=
 
1
 
:
 
1
 


t
e
s
t
_
d
a
t
a
 
2
0
0
개



```python
t
r
a
i
n
[
'
l
a
b
e
l
'
]
.
v
a
l
u
e
_
c
o
u
n
t
s
(
)
```

<pre>
2
 
 
 
 
 
 
 
8
3

4
 
 
 
 
 
 
 
8
3

1
0
-
1
 
 
 
 
8
2

7
 
 
 
 
 
 
 
8
2

8
 
 
 
 
 
 
 
7
9

9
 
 
 
 
 
 
 
7
9

5
 
 
 
 
 
 
 
7
9

6
 
 
 
 
 
 
 
7
9

1
 
 
 
 
 
 
 
7
9

3
 
 
 
 
 
 
 
7
7

1
0
-
2
 
 
 
 
5
6

N
a
m
e
:
 
l
a
b
e
l
,
 
d
t
y
p
e
:
 
i
n
t
6
4
</pre>

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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
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
f
i
l
e
_
n
a
m
e
'
]

t
r
a
i
n
```

<pre>
 
 
 
 
f
i
l
e
_
n
a
m
e
 
l
a
b
e
l
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h

0
 
 
 
 
 
0
0
1
.
p
n
g
 
 
1
0
-
2
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
0
0
1
.
p
n
g

1
 
 
 
 
 
0
0
2
.
p
n
g
 
 
1
0
-
1
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
0
0
2
.
p
n
g

2
 
 
 
 
 
0
0
3
.
p
n
g
 
 
 
 
 
3
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
0
0
3
.
p
n
g

3
 
 
 
 
 
0
0
4
.
p
n
g
 
 
 
 
 
8
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
0
0
4
.
p
n
g

4
 
 
 
 
 
0
0
5
.
p
n
g
 
 
 
 
 
9
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
0
0
5
.
p
n
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

8
5
3
 
 
 
8
5
4
.
p
n
g
 
 
 
 
 
9
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
5
4
.
p
n
g

8
5
4
 
 
 
8
5
5
.
p
n
g
 
 
 
 
 
1
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
5
5
.
p
n
g

8
5
5
 
 
 
8
5
6
.
p
n
g
 
 
 
 
 
4
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
5
6
.
p
n
g

8
5
6
 
 
 
8
5
7
.
p
n
g
 
 
1
0
-
1
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
5
7
.
p
n
g

8
5
7
 
 
 
8
5
8
.
p
n
g
 
 
 
 
 
7
 
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
8
5
8
.
p
n
g


[
8
5
8
 
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
i
m
p
o
r
t
 
c
v
2

i
m
p
o
r
t
 
s
h
u
t
i
l

f
r
o
m
 
t
q
d
m
 
i
m
p
o
r
t
 
t
q
d
m

o
s
.
m
a
k
e
d
i
r
s
(
'
3
8
4
_
t
r
a
i
n
/
'
,
e
x
i
s
t
_
o
k
=
T
r
u
e
)

f
o
r
 
p
a
t
h
 
i
n
 
t
q
d
m
(
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
)
:

 
 
 
 
i
m
a
g
e
=
c
v
2
.
i
m
r
e
a
d
(
p
a
t
h
)

 
 
 
 
i
m
a
g
e
=
c
v
2
.
b
l
u
r
(
i
m
a
g
e
,
 
(
5
,
5
)
)

 
 
 
 
i
m
a
g
e
_
h
s
v
=
c
v
2
.
c
v
t
C
o
l
o
r
(
i
m
a
g
e
,
 
c
v
2
.
C
O
L
O
R
_
B
G
R
2
H
S
V
)
 
#
B
G
R
에
서
 
H
S
V
로
 
전
환

 
 
 
 
l
o
w
e
r
_
b
l
u
e
=
n
p
.
a
r
r
a
y
(
[
5
0
,
1
0
0
,
5
0
]
)
 
#
H
S
V
에
서
 
파
랑
 
값
의
 
범
위
를
 
정
의

 
 
 
 
u
p
p
e
r
_
b
l
u
e
=
n
p
.
a
r
r
a
y
(
[
1
3
0
,
2
5
5
,
2
5
5
]
)

 
 
 
 
m
a
s
k
=
c
v
2
.
i
n
R
a
n
g
e
(
i
m
a
g
e
_
h
s
v
,
 
l
o
w
e
r
_
b
l
u
e
,
 
u
p
p
e
r
_
b
l
u
e
)
 
#
마
스
크
를
 
만
듭
니
다

 
 
 
 
i
m
a
g
e
_
b
g
r
_
m
a
s
k
e
d
=
c
v
2
.
b
i
t
w
i
s
e
_
a
n
d
(
i
m
a
g
e
,
 
i
m
a
g
e
,
 
m
a
s
k
=
m
a
s
k
)
 
#
이
미
지
에
 
마
스
크
를
 
적
용

 
 
 
 
i
m
a
g
e
=
c
v
2
.
c
v
t
C
o
l
o
r
(
i
m
a
g
e
_
b
g
r
_
m
a
s
k
e
d
,
 
c
v
2
.
C
O
L
O
R
_
B
G
R
2
R
G
B
)
 
#
B
G
R
에
서
 
R
G
B
로
 
전
환

 
 
 
 
i
m
a
g
e
=
c
v
2
.
r
e
s
i
z
e
(
i
m
a
g
e
,
 
(
3
8
4
,
3
8
4
)
)

 
 
 
 
i
m
a
g
e
=
i
m
a
g
e
[
:
,
1
8
1
]

 
 
 
 
m
a
x
_
o
u
t
p
u
t
_
v
a
l
u
e
=
2
5
5

 
 
 
 
n
e
i
g
h
b
o
r
h
o
o
d
_
s
i
z
e
=
9
9

 
 
 
 
s
u
b
t
r
a
c
t
_
f
r
o
m
_
m
e
a
n
=
1
0

 
 
 
 
i
m
a
g
e
=
c
v
2
.
a
d
a
p
t
i
v
e
T
h
r
e
s
h
o
l
d
(
i
m
a
g
e
,
 
m
a
x
_
o
u
t
p
u
t
_
v
a
l
u
e
,
 
c
v
2
.
A
D
A
P
T
I
V
E
_
T
H
R
E
S
H
_
G
A
U
S
S
I
A
N
_
C
,
 
c
v
2
.
T
H
R
E
S
H
_
B
I
N
A
R
Y
,
 
n
e
i
g
h
b
o
r
h
o
o
d
_
s
i
z
e
,
 
s
u
b
t
r
a
c
t
_
f
r
o
m
_
m
e
a
n
)

 
 
 
 
m
e
d
i
a
n
_
i
n
t
e
n
s
i
t
y
=
n
p
.
m
e
d
i
a
n
(
i
m
a
g
e
)
 
#
픽
셀
 
강
도
의
 
중
간
 
값
을
 
계
산

 
 
 
 
#
중
간
 
픽
셀
 
강
도
에
서
 
위
 
아
래
 
1
 
표
준
 
편
차
 
떨
어
진
 
값
을
 
임
계
값
으
로
 
지
정

 
 
 
 
l
o
w
e
r
_
t
h
r
e
s
h
o
l
d
=
i
n
t
(
m
a
x
(
0
,
 
(
1
.
0
 
-
 
0
.
3
3
)
*
m
e
d
i
a
n
_
i
n
t
e
n
s
i
t
y
)
)

 
 
 
 
u
p
p
e
r
_
t
h
r
e
s
h
o
l
d
=
i
n
t
(
m
i
n
(
2
5
5
,
 
(
1
.
0
 
+
 
0
.
3
3
)
*
m
e
d
i
a
n
_
i
n
t
e
n
s
i
t
y
)
)

 
 
 
 
#
캐
니
 
경
계
선
 
감
지
기
를
 
이
용
합
니
다

 
 
 
 
i
m
a
g
e
=
c
v
2
.
C
a
n
n
y
(
i
m
a
g
e
,
 
l
o
w
e
r
_
t
h
r
e
s
h
o
l
d
,
 
u
p
p
e
r
_
t
h
r
e
s
h
o
l
d
)

 
 
 
 
p
a
t
h
_
s
p
l
i
t
=
p
a
t
h
.
s
p
l
i
t
(
'
/
'
)
[
-
1
]

 
 
 
 
c
v
2
.
i
m
w
r
i
t
e
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
/
i
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
'
+
p
a
t
h
_
s
p
l
i
t
,
i
m
a
g
e
)

s
h
u
t
i
l
.
m
a
k
e
_
a
r
c
h
i
v
e
(
'
3
8
4
_
t
r
a
i
n
'
,
'
z
i
p
'
,
'
3
8
4
_
t
r
a
i
n
'
)
```

<pre>
1
0
0
%
|
█
█
█
█
█
█
█
█
█
█
|
 
8
5
8
/
8
5
8
 
[
0
0
:
0
4
<
0
0
:
0
0
,
 
1
8
5
.
5
9
i
t
/
s
]

</pre>
<pre>
'
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
3
8
4
_
t
r
a
i
n
.
z
i
p
'
</pre>

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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
 
 
 
 
f
i
l
e
_
n
a
m
e

0
 
 
 
 
 
0
0
1
.
p
n
g

1
 
 
 
 
 
0
0
2
.
p
n
g

2
 
 
 
 
 
0
0
3
.
p
n
g

3
 
 
 
 
 
0
0
4
.
p
n
g

4
 
 
 
 
 
0
0
5
.
p
n
g

.
.
 
 
 
 
 
 
 
 
.
.
.

2
1
0
 
 
 
2
1
1
.
p
n
g

2
1
1
 
 
 
2
1
2
.
p
n
g

2
1
2
 
 
 
2
1
3
.
p
n
g

2
1
3
 
 
 
2
1
4
.
p
n
g

2
1
4
 
 
 
2
1
5
.
p
n
g


[
2
1
5
 
r
o
w
s
 
x
 
1
 
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
'
+
t
e
s
t
[
'
f
i
l
e
_
n
a
m
e
'
]

t
e
s
t
```

<pre>
 
 
 
 
f
i
l
e
_
n
a
m
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h

0
 
 
 
 
 
0
0
1
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
0
1
.
p
n
g

1
 
 
 
 
 
0
0
2
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
0
2
.
p
n
g

2
 
 
 
 
 
0
0
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
0
3
.
p
n
g

3
 
 
 
 
 
0
0
4
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
0
4
.
p
n
g

4
 
 
 
 
 
0
0
5
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
0
0
5
.
p
n
g

.
.
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.

2
1
0
 
 
 
2
1
1
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
2
1
1
.
p
n
g

2
1
1
 
 
 
2
1
2
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
2
1
2
.
p
n
g

2
1
2
 
 
 
2
1
3
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
2
1
3
.
p
n
g

2
1
3
 
 
 
2
1
4
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
2
1
4
.
p
n
g

2
1
4
 
 
 
2
1
5
.
p
n
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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
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
/
2
1
5
.
p
n
g


[
2
1
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

```python
f
r
o
m
 
P
I
L
 
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

I
m
a
g
e
.
o
p
e
n
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
/
i
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
/
t
r
a
i
n
/
6
4
1
.
p
n
g
'
)
```

<pre>
<
P
I
L
.
P
n
g
I
m
a
g
e
P
l
u
g
i
n
.
P
n
g
I
m
a
g
e
F
i
l
e
 
i
m
a
g
e
 
m
o
d
e
=
R
G
B
 
s
i
z
e
=
2
2
4
x
2
2
4
 
a
t
 
0
x
7
F
8
9
B
D
A
E
D
9
9
0
>
</pre>

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
```


```python
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
 
S
t
r
a
t
i
f
i
e
d
K
F
o
l
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

s
k
f
=
S
t
r
a
t
i
f
i
e
d
K
F
o
l
d
(
n
_
s
p
l
i
t
s
=
5
,
s
h
u
f
f
l
e
=
T
r
u
e
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
8
8
)
 
#
 
1
0
 
1
5
 
2
0
 
#
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
 
변
경

r
e
s
u
l
t
=
0

f
o
r
 
t
r
a
i
n
_
i
n
d
e
x
,
 
v
a
l
i
d
_
i
n
d
e
x
 
i
n
 
s
k
f
.
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
r
a
i
n
[
'
l
a
b
e
l
'
]
)
:

 
 
 
 
x
_
t
r
a
i
n
 
=
 
t
r
a
i
n
.
i
l
o
c
[
t
r
a
i
n
_
i
n
d
e
x
]

 
 
 
 
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
.
i
l
o
c
[
v
a
l
i
d
_
i
n
d
e
x
]

 
 
 
 
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
l
a
b
e
l
'
,
 
t
a
r
g
e
t
_
s
i
z
e
=
(
3
8
4
,
3
8
4
)
,
 
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
=
1
6
)
 
#
2
2
4
/
3
2
,

 
 
 
 
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
l
a
b
e
l
'
,
 
t
a
r
g
e
t
_
s
i
z
e
=
(
3
8
4
,
3
8
4
)
,
 
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
=
1
6
)
 
#
2
2
4
/
3
2
,

 
 
 
 

 
 
 
 
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
1
1
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
6
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
4
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
최
적
 
주
변
에
서
 
미
세
 
조
정
,
 
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
 
줄
이
는
 
방
법
 

 
 
 
 
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

 
 
 
 
r
e
s
u
l
t
+
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
 
w
o
r
k
e
r
s
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
)
/
5
```

<pre>
F
o
u
n
d
 
6
8
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
 
1
1
 
c
l
a
s
s
e
s
.

F
o
u
n
d
 
1
7
2
 
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
 
1
1
 
c
l
a
s
s
e
s
.

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

4
3
/
4
3
 
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
 
3
6
s
 
5
9
6
m
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
 
1
.
1
1
6
0
 
-
 
a
c
c
:
 
0
.
6
3
4
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
9
3
2
4
 
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
7
2
0
9

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
3
0
7
5
 
-
 
a
c
c
:
 
0
.
9
0
9
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
6
0
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
7
3
8
4

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
5
4
1
 
-
 
a
c
c
:
 
0
.
9
0
6
7
 
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
9
0
1
0
 
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
7
6
1
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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
5
m
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
1
6
6
8
 
-
 
a
c
c
:
 
0
.
9
5
1
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
5
6
0
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
8
3
7
2

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
1
3
8
6
 
-
 
a
c
c
:
 
0
.
9
4
7
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
3
0
6
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
8
8
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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
5
m
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
1
2
5
6
 
-
 
a
c
c
:
 
0
.
9
5
6
3
 
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
3
9
3
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
3
6
0

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
6
m
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
1
2
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
6
0
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
3
3
7
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
0
1
2

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

4
3
/
4
3
 
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
 
2
3
s
 
5
3
0
m
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
9
1
 
-
 
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
2
5
1
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
4
7
7

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
5
7
8
 
-
 
a
c
c
:
 
0
.
9
8
5
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
2
3
6
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
4
7
7

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
1
8
 
-
 
a
c
c
:
 
0
.
9
8
5
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
2
9
9
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
2
4
4

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
4
 
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
7
 
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
5
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
6
5
1

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
2
1
7
3
 
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
3
0
2

E
p
o
c
h
 
1
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
4
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
7
 
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
2
3
8
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
3
6
0

E
p
o
c
h
 
1
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
6
2
 
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
2
0
9
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
5
3
5

E
p
o
c
h
 
1
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
9
7
1
 
-
 
a
c
c
:
 
0
.
9
6
9
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
4
0
1
4
 
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
3
0
2


E
p
o
c
h
 
0
0
0
1
5
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
6
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
5
9
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
4
0
 
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
2
0
2
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
3
6
0

E
p
o
c
h
 
1
7
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
4
4
 
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
7
 
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
2
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
5
3
5

F
o
u
n
d
 
2
1
5
 
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

7
/
7
 
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
 
2
s
 
8
7
m
s
/
s
t
e
p

F
o
u
n
d
 
6
8
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
 
1
1
 
c
l
a
s
s
e
s
.

F
o
u
n
d
 
1
7
2
 
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
 
1
1
 
c
l
a
s
s
e
s
.

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

4
3
/
4
3
 
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
 
3
5
s
 
5
6
5
m
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
 
1
.
1
7
5
4
 
-
 
a
c
c
:
 
0
.
6
0
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
 
1
.
2
7
2
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
6
2
7
9

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

4
3
/
4
3
 
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
 
2
3
s
 
5
3
2
m
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
4
1
7
1
 
-
 
a
c
c
:
 
0
.
8
6
4
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
8
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
7
3
2
6

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
8
5
5
 
-
 
a
c
c
:
 
0
.
9
0
5
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
3
0
8
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
1
2
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
4
7
 
-
 
a
c
c
:
 
0
.
9
3
5
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
 
1
.
0
3
4
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
7
3
2
6

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
1
3
0
8
 
-
 
a
c
c
:
 
0
.
9
6
2
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
4
4
0
 
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
3
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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
1
0
5
1
 
-
 
a
c
c
:
 
0
.
9
5
9
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
3
4
2
3
 
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
1
2
8

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
1
1
3
1
 
-
 
a
c
c
:
 
0
.
9
5
9
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
1
9
7
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
4
1
9

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
1
 
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
0
 
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
3
6
0
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
8
9
5
3

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
8
5
 
-
 
a
c
c
:
 
0
.
9
8
1
0
 
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
2
0
2
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
5
9
3


E
p
o
c
h
 
0
0
0
0
9
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
0
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
0
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
6
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
1
1
4
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
0
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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
2
8
 
-
 
a
c
c
:
 
0
.
9
9
7
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
9
9
3
 
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
0
9

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
0
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
8
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
9
4
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
7
0
9

E
p
o
c
h
 
1
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
8
1
 
-
 
a
c
c
:
 
0
.
9
9
7
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
9
7
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
7
0
9

E
p
o
c
h
 
1
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
2
m
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
7
2
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
9
0
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
7
0
9

E
p
o
c
h
 
1
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
9
6
 
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
9
1
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
5
1

E
p
o
c
h
 
1
6
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
5
5
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
8
9
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
7
0
9

E
p
o
c
h
 
1
7
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
4
2
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
8
7
0
 
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
0
9

E
p
o
c
h
 
1
8
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
7
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
7
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
8
6
3
 
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
0
9

E
p
o
c
h
 
1
9
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
4
7
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
8
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
6
5
1

E
p
o
c
h
 
2
0
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
7
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
7
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
9
3
3
 
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
 
2
1
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
3
4
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
9
7
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
6
5
1

E
p
o
c
h
 
2
2
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
 
1
.
0
0
0
0
 
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
9
6
0
 
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
0
9

E
p
o
c
h
 
2
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
2
6
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
9
7
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
7
0
9


E
p
o
c
h
 
0
0
0
2
3
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
 
1
.
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
4
e
-
0
5
.

E
p
o
c
h
 
2
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
3
5
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
9
5
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
0
9

E
p
o
c
h
 
2
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
2
4
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
9
6
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
0
9

F
o
u
n
d
 
2
1
5
 
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

7
/
7
 
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
 
2
s
 
8
8
m
s
/
s
t
e
p

F
o
u
n
d
 
6
8
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
 
1
1
 
c
l
a
s
s
e
s
.

F
o
u
n
d
 
1
7
2
 
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
 
1
1
 
c
l
a
s
s
e
s
.

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

4
3
/
4
3
 
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
 
3
7
s
 
5
5
9
m
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
 
1
.
1
0
7
3
 
-
 
a
c
c
:
 
0
.
6
3
8
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
8
3
2
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
7
7
3
3

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
3
5
8
6
 
-
 
a
c
c
:
 
0
.
8
9
3
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
1
8
3
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
7
0
3
5

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
1
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
2
8
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
6
3
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
8
2
5
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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
1
4
5
5
 
-
 
a
c
c
:
 
0
.
9
5
6
3
 
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
4
3
4
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
8
8
9
5

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
1
3
7
1
 
-
 
a
c
c
:
 
0
.
9
6
2
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
4
4
2
0
 
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
8
3
7

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
1
7
2
2
 
-
 
a
c
c
:
 
0
.
9
4
6
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
 
1
.
0
2
2
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
7
5
5
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
6
m
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
1
1
6
6
 
-
 
a
c
c
:
 
0
.
9
6
2
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
4
4
0
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
8
8
3
7

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
6
m
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
5
0
9
 
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
0
 
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
2
3
3
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
3
0
2

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
1
0
0
0
 
-
 
a
c
c
:
 
0
.
9
7
0
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
4
2
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
8
3
7

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
6
 
-
 
a
c
c
:
 
0
.
9
8
8
3
 
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
3
3
9
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
1
8
6

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
2
m
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
9
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
5
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
2
9
4
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
1
2
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
5
1
4
 
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
0
 
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
5
8
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
7
7
9


E
p
o
c
h
 
0
0
0
1
2
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
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
1
1
 
-
 
a
c
c
:
 
0
.
9
8
8
3
 
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
8
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
5
3
5

E
p
o
c
h
 
1
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
7
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
8
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
7
2
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
5
3
5

E
p
o
c
h
 
1
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
6
m
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
1
2
 
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
6
0
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
5
3
5

E
p
o
c
h
 
1
6
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
9
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
7
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
4
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
5
3
5

E
p
o
c
h
 
1
7
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
4
2
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
4
4
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
3
5

E
p
o
c
h
 
1
8
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
6
m
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
2
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
7
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
4
3
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
5
3
5

E
p
o
c
h
 
1
9
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
3
2
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
4
0
4
 
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
3
5

E
p
o
c
h
 
2
0
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
6
m
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
5
6
 
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
4
3
4
 
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
3
5

E
p
o
c
h
 
2
1
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
5
8
 
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
4
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
5
3
5

E
p
o
c
h
 
2
2
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
3
7
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
4
4
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
5
3
5

E
p
o
c
h
 
2
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
7
m
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
4
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
4
7
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
5
3
5


E
p
o
c
h
 
0
0
0
2
3
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
 
1
.
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
4
e
-
0
5
.

E
p
o
c
h
 
2
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
2
0
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
4
7
4
 
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
3
5

E
p
o
c
h
 
2
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
6
m
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
5
8
 
-
 
a
c
c
:
 
0
.
9
9
7
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
4
7
0
 
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
3
5

F
o
u
n
d
 
2
1
5
 
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

7
/
7
 
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
 
2
s
 
7
5
m
s
/
s
t
e
p

F
o
u
n
d
 
6
8
7
 
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
 
1
1
 
c
l
a
s
s
e
s
.

F
o
u
n
d
 
1
7
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
 
1
1
 
c
l
a
s
s
e
s
.

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

4
3
/
4
3
 
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
 
3
6
s
 
5
9
7
m
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
 
1
.
1
2
9
8
 
-
 
a
c
c
:
 
0
.
6
0
2
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
9
9
3
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
5
3
8
0

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
3
8
6
9
 
-
 
a
c
c
:
 
0
.
8
5
7
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
8
3
4
3
 
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
7
4
8
5

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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
3
5
0
3
 
-
 
a
c
c
:
 
0
.
8
8
0
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
3
1
8
3
 
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
7
0
1
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
1
9
4
4
 
-
 
a
c
c
:
 
0
.
9
3
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
 
0
.
3
7
1
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
8
9
4
7

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
1
7
6
2
 
-
 
a
c
c
:
 
0
.
9
5
2
0
 
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
8
6
6
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
2
4
6

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
1
1
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
6
6
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
2
7
3
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
1
8
1

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
9
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
7
3
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
6
5
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
4
9

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
7
9
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
2
1
3
4
 
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
0
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
7
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
2
4
9
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
4
7
4

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
8
 
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
5
3
2

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
3
m
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
7
8
6
 
-
 
a
c
c
:
 
0
.
9
7
2
3
 
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
3
6
0
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
1
8
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

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
1
2
 
-
 
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
4
9
4
 
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
4
9

E
p
o
c
h
 
1
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
8
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
8
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
4
1
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
7
0
8

E
p
o
c
h
 
1
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
4
6
 
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
4
1
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
7
0
8

E
p
o
c
h
 
1
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
2
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
8
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
2
4
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
7
6
6

E
p
o
c
h
 
1
6
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
7
m
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
7
8
 
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
2
7
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
7
6
6

E
p
o
c
h
 
1
7
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
6
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
3
0
3
 
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
0
8

E
p
o
c
h
 
1
8
/
1
0
0
0

4
3
/
4
3
 
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
 
2
3
s
 
5
2
6
m
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
4
3
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
2
9
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
7
0
8

E
p
o
c
h
 
1
9
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
7
1
 
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
3
1
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
4
9


E
p
o
c
h
 
0
0
0
1
9
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
 
1
.
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
4
e
-
0
5
.

E
p
o
c
h
 
2
0
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
2
8
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
3
1
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
4
9

E
p
o
c
h
 
2
1
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
3
5
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
3
1
4
 
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
4
9

F
o
u
n
d
 
2
1
5
 
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

7
/
7
 
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
 
2
s
 
8
8
m
s
/
s
t
e
p

F
o
u
n
d
 
6
8
7
 
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
 
1
1
 
c
l
a
s
s
e
s
.

F
o
u
n
d
 
1
7
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
 
1
1
 
c
l
a
s
s
e
s
.

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

4
3
/
4
3
 
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
 
3
5
s
 
5
7
2
m
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
 
1
.
2
0
6
9
 
-
 
a
c
c
:
 
0
.
5
7
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
 
1
.
2
7
0
3
 
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
5
1
4
6

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
4
7
4
2
 
-
 
a
c
c
:
 
0
.
8
3
5
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
8
7
5
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
8
3
6
3

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
5
m
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
8
3
2
 
-
 
a
c
c
:
 
0
.
8
9
5
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
 
1
.
8
9
8
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
6
6
0
8

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
7
4
0
 
-
 
a
c
c
:
 
0
.
9
0
5
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
2
6
7
0
 
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
1
2
3

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
1
5
1
3
 
-
 
a
c
c
:
 
0
.
9
5
2
0
 
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
3
4
9
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
2
9
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
1
m
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
1
2
8
5
 
-
 
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
3
5
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
1
2
3

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
9
8
9
 
-
 
a
c
c
:
 
0
.
9
6
3
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
2
2
8
0
 
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
2
9
8

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
1
3
0
3
 
-
 
a
c
c
:
 
0
.
9
5
9
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
4
2
9
3
 
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
8
3
0

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
2
m
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
1
2
4
8
 
-
 
a
c
c
:
 
0
.
9
5
6
3
 
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
3
6
2
3
 
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
1
2
3

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
3
m
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
7
6
2
 
-
 
a
c
c
:
 
0
.
9
7
2
3
 
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
2
3
9
4
 
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
1
5

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

4
3
/
4
3
 
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
 
2
3
s
 
5
2
4
m
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
7
1
 
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
7
 
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
0
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
5
3
2

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

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
9
5
3
 
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
0
8

E
p
o
c
h
 
1
3
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
4
m
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
7
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
8
0
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
7
6
6

E
p
o
c
h
 
1
4
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
7
m
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
2
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
8
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
3
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
7
0
8

E
p
o
c
h
 
1
5
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
2
m
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
9
 
-
 
a
c
c
:
 
1
.
0
0
0
0
 
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
3
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
2
5

E
p
o
c
h
 
1
6
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
5
m
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
2
6
 
-
 
a
c
c
:
 
0
.
9
9
1
3
 
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
3
2
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
4
1
5

E
p
o
c
h
 
1
7
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
5
m
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
3
4
2
 
-
 
a
c
c
:
 
0
.
9
9
1
3
 
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
5
1
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
8
3
0
4

E
p
o
c
h
 
1
8
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
7
4
9
 
-
 
a
c
c
:
 
0
.
9
7
9
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
3
7
3
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
8
6
5
5

E
p
o
c
h
 
1
9
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
9
m
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
1
2
0
8
 
-
 
a
c
c
:
 
0
.
9
6
0
7
 
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
9
6
9
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
7
8
3
6


E
p
o
c
h
 
0
0
0
1
9
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
 
2
0
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
2
0
m
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
5
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
7
8
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
2
2
3
3
 
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
7
4

E
p
o
c
h
 
2
1
/
1
0
0
0

4
3
/
4
3
 
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
 
2
2
s
 
5
1
8
m
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
1
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
7
 
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
2
2
0
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
4
7
4

F
o
u
n
d
 
2
1
5
 
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

7
/
7
 
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
 
2
s
 
7
1
m
s
/
s
t
e
p

</pre>
예
외
 
:
 
s
i
z
e
가
 
원
본
보
다
 
커
질
 
때
(
픽
셀
 
늘
렸
을
 
때
,
 
정
보
 
이
득
 
x
)
 
v
a
l
_
l
o
s
s
 
개
선
/
속
도
 
저
하




원
본
의
 
s
i
z
e
가
 
큰
 
경
우
 
>
 
전
처
리
에
서
 
s
i
z
e
줄
일
 
때
 
덜
 
줄
이
면
 
정
보
에
서
 
이
득


n
_
s
p
l
i
t
s
 
5
개
 
f
o
l
d


1
개
 
f
o
l
d
 
마
쳤
을
 
때
 
:
 
F
o
u
n
d
 
*
*
*
 
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
 
1
1
 
c
l
a
s
s
e
s
.



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
m
a
g
e
-
c
l
a
s
s
i
f
i
c
a
t
i
o
n
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
 
 
 
 
f
i
l
e
_
n
a
m
e
 
 
l
a
b
e
l

0
 
 
 
 
 
0
0
1
.
p
n
g
 
 
 
 
 
 
0

1
 
 
 
 
 
0
0
2
.
p
n
g
 
 
 
 
 
 
0

2
 
 
 
 
 
0
0
3
.
p
n
g
 
 
 
 
 
 
0

3
 
 
 
 
 
0
0
4
.
p
n
g
 
 
 
 
 
 
0

4
 
 
 
 
 
0
0
5
.
p
n
g
 
 
 
 
 
 
0

.
.
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
.
.
.

2
1
0
 
 
 
2
1
1
.
p
n
g
 
 
 
 
 
 
0

2
1
1
 
 
 
2
1
2
.
p
n
g
 
 
 
 
 
 
0

2
1
2
 
 
 
2
1
3
.
p
n
g
 
 
 
 
 
 
0

2
1
3
 
 
 
2
1
4
.
p
n
g
 
 
 
 
 
 
0

2
1
4
 
 
 
2
1
5
.
p
n
g
 
 
 
 
 
 
0


[
2
1
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

```python
s
u
b
[
'
l
a
b
e
l
'
]
=
r
e
s
u
l
t
.
a
r
g
m
a
x
(
1
)

s
u
b
```

<pre>
 
 
 
 
f
i
l
e
_
n
a
m
e
 
 
l
a
b
e
l

0
 
 
 
 
 
0
0
1
.
p
n
g
 
 
 
 
 
 
0

1
 
 
 
 
 
0
0
2
.
p
n
g
 
 
 
 
 
 
3

2
 
 
 
 
 
0
0
3
.
p
n
g
 
 
 
 
 
 
0

3
 
 
 
 
 
0
0
4
.
p
n
g
 
 
 
 
 
 
7

4
 
 
 
 
 
0
0
5
.
p
n
g
 
 
 
 
 
 
9

.
.
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
.
.
.

2
1
0
 
 
 
2
1
1
.
p
n
g
 
 
 
 
 
 
6

2
1
1
 
 
 
2
1
2
.
p
n
g
 
 
 
 
 
 
9

2
1
2
 
 
 
2
1
3
.
p
n
g
 
 
 
 
 
 
4

2
1
3
 
 
 
2
1
4
.
p
n
g
 
 
 
 
 
 
7

2
1
4
 
 
 
2
1
5
.
p
n
g
 
 
 
 
 
 
0


[
2
1
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

```python
c
l
a
s
s
_
l
i
s
t
=
l
i
s
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
.
c
l
a
s
s
_
i
n
d
i
c
e
s
)

c
l
a
s
s
_
l
i
s
t
```

<pre>
[
'
1
'
,
 
'
1
0
-
1
'
,
 
'
1
0
-
2
'
,
 
'
2
'
,
 
'
3
'
,
 
'
4
'
,
 
'
5
'
,
 
'
6
'
,
 
'
7
'
,
 
'
8
'
,
 
'
9
'
]
</pre>

```python
c
l
a
s
s
_
d
i
c
t
=
d
i
c
t
(
z
i
p
(
r
a
n
g
e
(
1
1
)
,
c
l
a
s
s
_
l
i
s
t
)
)

c
l
a
s
s
_
d
i
c
t
```

<pre>
{
0
:
 
'
1
'
,

 
1
:
 
'
1
0
-
1
'
,

 
2
:
 
'
1
0
-
2
'
,

 
3
:
 
'
2
'
,

 
4
:
 
'
3
'
,

 
5
:
 
'
4
'
,

 
6
:
 
'
5
'
,

 
7
:
 
'
6
'
,

 
8
:
 
'
7
'
,

 
9
:
 
'
8
'
,

 
1
0
:
 
'
9
'
}
</pre>

```python
s
u
b
[
'
l
a
b
e
l
'
]
=
s
u
b
[
'
l
a
b
e
l
'
]
.
r
e
p
l
a
c
e
(
c
l
a
s
s
_
d
i
c
t
)

s
u
b
```

<pre>
 
 
 
 
f
i
l
e
_
n
a
m
e
 
l
a
b
e
l

0
 
 
 
 
 
0
0
1
.
p
n
g
 
 
 
 
 
1

1
 
 
 
 
 
0
0
2
.
p
n
g
 
 
 
 
 
2

2
 
 
 
 
 
0
0
3
.
p
n
g
 
 
 
 
 
1

3
 
 
 
 
 
0
0
4
.
p
n
g
 
 
 
 
 
6

4
 
 
 
 
 
0
0
5
.
p
n
g
 
 
 
 
 
8

.
.
 
 
 
 
 
 
 
 
.
.
.
 
 
 
.
.
.

2
1
0
 
 
 
2
1
1
.
p
n
g
 
 
 
 
 
5

2
1
1
 
 
 
2
1
2
.
p
n
g
 
 
 
 
 
8

2
1
2
 
 
 
2
1
3
.
p
n
g
 
 
 
 
 
3

2
1
3
 
 
 
2
1
4
.
p
n
g
 
 
 
 
 
6

2
1
4
 
 
 
2
1
5
.
p
n
g
 
 
 
 
 
1


[
2
1
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
e
s
6
_
r
l
4
_
8
8
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


```python
p
d
.
D
a
t
a
F
r
a
m
e
(
r
e
s
u
l
t
)
.
t
o
_
c
s
v
(
'
c
u
t
t
i
n
g
_
c
a
n
n
y
_
r
e
s
u
l
t
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
 
#
E
n
s
e
m
b
l
e
에
 
활
```
