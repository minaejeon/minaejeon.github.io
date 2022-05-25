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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
d
8
7
b
3
6
a
e
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
e
8
4
9
2
c
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
8
d
6
a
c
b
e
9
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
5
4
b
3
a
f
d
5
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
6
0
4
9
2
3
4
e
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
4
a
e
9
3
9
d
7
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
b
8
6
6
4
f
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
6
2
8
b
0
8
c
8
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
9
a
b
3
b
6
1
d
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
0
8
6
8
9
4
2
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
d
f
5
8
4
c
a
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
9
0
2
6
d
a
4
9
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
1
a
9
a
8
5
9
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
c
4
8
b
7
8
8
a
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
c
6
4
3
a
4
2
4
f
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
6
7
e
3
7
d
e
9
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
8
b
3
5
2
2
2
d
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
4
e
0
c
e
f
1
1
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
8
4
2
8
1
d
d
7
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
d
0
4
e
f
f
4
5
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
2
a
a
6
0
0
4
5
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
a
4
7
c
f
e
e
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
c
0
2
5
e
2
8
8
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
4
8
1
4
1
d
6
a
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
e
d
5
4
0
b
e
b
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
4
8
3
9
e
4
5
7
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
3
0
4
1
d
1
4
7
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
f
e
f
5
e
7
0
6
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
e
d
7
1
9
8
7
a
e
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
6
d
6
3
e
b
9
8
f
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
9
3
d
9
8
5
8
f
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
d
e
8
2
f
9
6
f
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
6
d
2
f
1
1
b
5
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
1
7
d
3
e
7
e
2
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
f
9
d
5
9
7
9
5
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
6
5
b
a
0
f
4
9
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
f
c
0
2
b
8
4
6
6
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
2
6
6
2
1
1
c
3
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
9
8
8
1
1
3
5
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
f
2
c
2
2
a
1
b
f
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
b
d
6
6
8
1
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
6
b
c
c
0
c
2
5
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
3
f
c
4
7
d
e
3
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
d
8
5
9
7
a
a
6
a
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
4
2
0
f
3
6
5
4
f
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
5
7
7
3
1
e
b
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
4
0
c
5
7
5
7
c
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
2
8
2
8
5
e
b
9
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
1
d
0
0
f
7
f
a
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
e
d
d
a
f
3
d
4
7
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
7
f
7
3
1
3
1
1
e
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
0
0
2
6
8
e
9
7
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
6
8
5
0
9
1
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
a
8
6
b
9
c
0
c
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
f
f
9
f
2
9
1
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
0
0
d
0
3
0
e
a
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
8
5
f
3
3
f
c
e
e
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
5
8
e
2
2
d
2
5
a
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
7
a
d
f
f
2
9
a
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
b
8
a
c
3
7
d
c
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
8
0
5
6
c
3
5
9
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
8
9
6
a
2
3
e
a
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
9
7
b
f
b
d
c
f
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
d
a
6
6
2
1
a
c
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
d
3
3
d
1
0
a
1
8
.
p
n
g

</pre>
t
r
a
i
n
 
폴
더
안
에
 
이
미
지
 
파
일
로
 
데
이
터
가
 
주
어
져
 
있
습
니
다
.




각
 
파
일
의
 
특
징
을
 
추
출
한
 
d
a
t
a
f
r
a
m
e
을
 
만
들
고
자
 
g
l
o
b
를
 
사
용
합
니
다
.



```python
i
m
p
o
r
t
 
g
l
o
b

t
r
a
i
n
=
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
{
'
p
a
t
h
'
:
g
l
o
b
.
g
l
o
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
*
/
*
'
)
}
)

p
d
.
o
p
t
i
o
n
s
.
d
i
s
p
l
a
y
.
m
a
x
_
c
o
l
w
i
d
t
h
=
9
9

t
r
a
i
n
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h

0
 
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
4
a
e
9
3
9
d
7
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
b
8
6
6
4
f
7
0
5
.
p
n
g

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
6
2
8
b
0
8
c
8
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
9
a
b
3
b
6
1
d
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
0
8
6
8
9
4
2
7
4
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

4
7
4
5
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
f
0
1
2
7
f
7
0
d
.
p
n
g

4
7
4
6
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
1
7
9
c
e
d
c
9
e
.
p
n
g

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
a
0
e
c
3
3
8
6
9
.
p
n
g

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
3
3
0
1
0
c
8
c
b
.
p
n
g

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
a
a
d
8
1
b
2
7
b
.
p
n
g


[
4
7
5
0
 
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
데
이
터
가
 
주
어
질
 
때
,
 
p
l
a
n
t
 
s
p
e
c
i
e
s
별
로
 
이
미
지
가
 
분
류
되
어
 
있
습
니
다
.




'
p
a
t
h
'
의
 
정
보
로
부
터
 
p
l
a
n
t
 
s
p
e
c
i
e
s
 
정
보
를
 
분
류
할
 
수
 
있
습
니
다
.




/
기
호
 
역
으
로
 
2
번
째
에
 
해
당
하
므
로
 
/
기
준
으
로
 
s
p
l
i
t
하
였
을
 
때
 
-
2
 
위
치
에
 
해
당
합
니
다
.
 
이
를
 
칼
럼
으
로
 
만
들
어
 
보
겠
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
s
p
e
c
i
e
s
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
p
a
t
h
'
]
.
a
p
p
l
y
(
l
a
m
b
d
a
 
x
 
:
 
x
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
2
]
)

t
r
a
i
n
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h
 
 
\

0
 
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
4
a
e
9
3
9
d
7
d
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
b
8
6
6
4
f
7
0
5
.
p
n
g
 
 
 

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
6
2
8
b
0
8
c
8
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
9
a
b
3
b
6
1
d
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
0
8
6
8
9
4
2
7
4
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
 
 
 

4
7
4
5
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
f
0
1
2
7
f
7
0
d
.
p
n
g
 
 
 

4
7
4
6
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
1
7
9
c
e
d
c
9
e
.
p
n
g
 
 
 

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
a
0
e
c
3
3
8
6
9
.
p
n
g
 
 
 

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
3
3
0
1
0
c
8
c
b
.
p
n
g
 
 
 

4
7
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
a
a
d
8
1
b
2
7
b
.
p
n
g
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
p
e
c
i
e
s
 
 

0
 
 
 
 
 
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 

1
 
 
 
 
 
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 

2
 
 
 
 
 
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 

3
 
 
 
 
 
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 

4
 
 
 
 
 
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

4
7
4
5
 
 
 
 
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 

4
7
4
6
 
 
 
 
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 

4
7
4
7
 
 
 
 
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 

4
7
4
8
 
 
 
 
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 

4
7
4
9
 
 
 
 
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 


[
4
7
5
0
 
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
r
a
i
n
[
'
s
p
e
c
i
e
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
 
 
 
 
 
 
 
 
 
 
 
 
 
6
5
4

C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
 
 
 
 
 
 
 
 
 
 
 
 
 
6
1
1

S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
 
 
 
 
 
 
 
 
 
 
 
 
5
1
6

S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
 
 
 
 
4
9
6

F
a
t
 
H
e
n
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
4
7
5

C
h
a
r
l
o
c
k
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
9
0

S
u
g
a
r
 
b
e
e
t
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
8
5

C
l
e
a
v
e
r
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
8
7

B
l
a
c
k
-
g
r
a
s
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
6
3

S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
3
1

C
o
m
m
o
n
 
w
h
e
a
t
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
2
1

M
a
i
z
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
2
1

N
a
m
e
:
 
s
p
e
c
i
e
s
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
s
p
e
c
i
e
s
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
s
p
e
c
i
e
s
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
s
p
e
c
i
e
s
=
t
r
a
i
n
[
'
s
p
e
c
i
e
s
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

s
p
e
c
i
e
s
.
i
n
d
e
x
```

<pre>
I
n
d
e
x
(
[
'
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
'
,
 
'
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
'
,
 
'
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
'
,

 
 
 
 
 
 
 
'
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
'
,
 
'
F
a
t
 
H
e
n
'
,
 
'
C
h
a
r
l
o
c
k
'
,
 
'
S
u
g
a
r
 
b
e
e
t
'
,

 
 
 
 
 
 
 
'
C
l
e
a
v
e
r
s
'
,
 
'
B
l
a
c
k
-
g
r
a
s
s
'
,
 
'
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
'
,
 
'
C
o
m
m
o
n
 
w
h
e
a
t
'
,
 
'
M
a
i
z
e
'
]
,

 
 
 
 
 
 
d
t
y
p
e
=
'
o
b
j
e
c
t
'
)
</pre>

```python
i
m
a
g
e
 
d
a
t
a
 
학
습
 
m
o
d
e
l
은
 
동
일
하
게
 
적
용
하
고
,
 
i
m
a
g
e
 
전
처
리
 
기
법
을
 
달
리
하
여
 
점
수
의
 
변
화
를
 
살
펴
 
보
겠
습
니
다
.
```

이
미
지
 
자
르
기
 
(
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
2
2
1
)




•
 
이
미
지
 
주
변
을
 
제
거
하
여
 
차
원
을
 
줄
일
 
수
 
있
습
니
다
.




•
 
이
미
지
는
 
2
차
원
 
넘
파
이
 
배
열
로
 
저
장
됩
니
다
.




•
 
배
열
 
슬
라
이
싱
을
 
사
용
해
 
간
단
하
게
 
이
미
지
를
 
자
를
 
수
 
있
습
니
다




•
 
O
p
e
n
C
V
는
 
이
미
지
를
 
행
렬
로
 
표
현
하
므
로
 
이
미
지
에
서
 
남
기
고
 
싶
은
 
특
정
 
부
분
을
 
행
과
 
열
을
 
선
택
하
여
 
이
미
지
 
자
르
기
 
기
능
을
 
사
용
합
니
다
.



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
1
:
3
8
<
0
0
:
0
0
,
 
 
8
.
1
9
s
/
i
t
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
6
2
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
이
미
지
 
투
명
도
 
처
리
(
s
c
o
r
e
:
 
0
.
9
4
7
1
0
)




•
 
이
미
지
를
 
흐
리
게
 
하
려
면
 
각
 
픽
셀
을
 
주
변
 
픽
셀
의
 
평
균
값
으
로
 
변
환
합
니
다
.




•
 
주
변
 
픽
셀
에
 
수
행
되
는
 
연
산
을
 
수
학
적
으
로
 
커
널
이
라
 
표
현
합
니
다
.




•
 
커
널
의
 
크
기
는
 
흐
림
의
 
정
도
를
 
결
정
합
니
다
.




•
 
커
널
이
 
클
수
록
 
이
미
지
가
 
더
 
부
드
러
워
집
니
다
.




•
 
커
널
은
 
이
미
지
를
 
선
명
하
게
 
만
드
는
 
것
부
터
 
경
계
선
 
감
지
까
지
 
이
미
지
 
처
리
 
작
업
을
 
하
는
데
 
널
리
 
사
용
됩
니
다
.



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
)
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
5
5
<
0
0
:
0
0
,
 
 
4
.
6
4
s
/
i
t
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
6
2
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
이
미
지
 
투
명
도
 
처
리
 
(
s
c
o
r
e
 
:
 
0
.
9
4
8
3
6
)




•
 
커
널
은
 
이
미
지
를
 
선
명
하
게
 
만
드
는
 
것
부
터
 
경
계
선
 
감
지
까
지
 
이
미
지
 
처
리
 
작
업
을
 
하
는
데
 
널
리
 
사
용
됩
니
다
.




•
 
커
널
 
P
C
A
와
 
서
포
트
 
벡
터
 
머
신
이
 
사
용
하
는
 
비
선
형
 
함
수
를
 
커
널
이
라
 
부
릅
니
다
.




•
 
M
e
a
n
s
h
i
f
t
 
알
고
리
즘
에
서
는
 
샘
플
의
 
영
향
 
범
위
를
 
커
널
이
라
 
부
릅
니
다
.




•
 
신
경
망
의
 
가
중
치
를
 
커
널
이
라
 
부
릅
니
다




•
 
커
널
 
크
기
는
 
(
너
비
,
 
높
이
)
로
 
지
정
합
니
다
.




•
 
주
변
 
픽
셀
값
의
 
평
균
을
 
계
산
하
는
 
커
널
은
 
이
미
지
를
 
흐
리
게
 
처
리
합
니
다
.




•
 
b
l
u
r
 
함
수
는
 
각
 
픽
셀
에
 
커
널
 
개
수
의
 
역
수
를
 
곱
하
여
 
모
두
 
더
합
니
다
.
 
(
 
이
 
값
이
 
중
앙
 
픽
셀
의
 
값
이
 
됩
니
다
.
)



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
)
)

 
 
 
 
 
 
 
 
k
e
r
n
e
l
=
n
p
.
o
n
e
s
(
(
5
,
5
)
)
 
/
 
2
5
.
0

 
 
 
 
 
 
 
 
k
e
r
n
e
l

 
 
 
 
 
 
 
 
i
m
a
g
e
_
k
e
r
n
e
l
=
c
v
2
.
f
i
l
t
e
r
2
D
(
i
m
a
g
e
,
 
-
1
,
 
k
e
r
n
e
l
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
G
a
u
s
s
i
a
n
B
l
u
r
(
i
m
a
g
e
_
k
e
r
n
e
l
,
 
(
5
,
5
)
,
 
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
1
:
0
5
<
0
0
:
0
0
,
 
 
5
.
4
3
s
/
i
t
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
6
2
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
이
미
지
 
선
명
하
게
 
하
기
(
s
c
o
r
e
 
:
 
0
.
9
4
2
0
6
)




•
 
대
상
 
픽
셀
을
 
강
조
하
는
 
커
널
을
 
만
들
고
 
f
i
l
t
e
r
2
D
를
 
사
용
하
여
 
이
미
지
에
 
커
널
을
 
적
용
합
니
다




•
 
중
앙
 
픽
셀
을
 
부
각
하
는
 
커
널
을
 
만
들
면
 
이
미
지
의
 
경
계
선
에
서
 
대
비
가
 
더
욱
 
두
드
러
지
는
 
효
과
가
 
생
깁
니
다
.



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
)
)

 
 
 
 
 
 
 
 
k
e
r
n
e
l
 
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
[
0
,
 
-
1
,
 
0
]
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
-
1
,
 
5
,
 
-
1
]
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
0
,
 
-
1
,
 
0
]
]
)

 
 
 
 
 
 
 
 
i
m
a
g
e
_
k
e
r
n
e
l
=
c
v
2
.
f
i
l
t
e
r
2
D
(
i
m
a
g
e
,
 
-
1
,
 
k
e
r
n
e
l
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
G
a
u
s
s
i
a
n
B
l
u
r
(
i
m
a
g
e
_
k
e
r
n
e
l
,
 
(
5
,
5
)
,
 
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
5
6
<
0
0
:
0
0
,
 
 
4
.
7
0
s
/
i
t
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
6
2
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
이
미
지
 
대
비
 
높
이
기
 
(
S
c
o
r
e
 
:
 
0
.
9
5
4
6
5
)




•
 
히
스
토
그
램
 
평
활
화
는
 
객
체
의
 
형
태
가
 
두
드
러
지
도
록
 
만
들
어
주
는
 
이
미
지
 
처
리
 
도
구
입
니
다




•
 
Y
는
 
루
마
(
l
u
m
a
)
 
또
는
 
밝
기
이
고
 
U
와
 
V
는
 
컬
러
를
 
나
타
냅
니
다
.
.




•
 
흑
백
 
이
미
지
에
는
 
O
p
e
n
C
V
의
 
e
q
u
a
l
i
z
e
H
i
s
t
(
)
를
 
바
로
 
적
용
할
 
수
 
있
습
니
다
.




•
 
히
스
토
그
램
 
평
활
화
는
 
픽
셀
값
의
 
범
위
가
 
커
지
도
록
 
이
미
지
를
 
변
환
합
니
다
.




•
 
히
스
토
그
램
 
평
활
화
는
 
관
심
 
대
상
을
 
다
른
 
객
체
나
 
배
경
과
 
잘
 
구
분
되
도
록
 
만
들
어
줍
니
다
.




에
러
 
발
생




두
가
지
 
과
정
으
로
 
쪼
갬
 
흑
백
/
컬
러



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
,
c
v
2
.
I
M
R
E
A
D
_
G
R
A
Y
S
C
A
L
E
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
6
2
,
3
6
2
)
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
e
q
u
a
l
i
z
e
H
i
s
t
(
i
m
a
g
e
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
5
2
<
0
0
:
0
0
,
 
 
4
.
3
9
s
/
i
t
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
6
2
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
s
c
o
r
e
 
:
 
0
.
9
3
9
5
4



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
:

 
 
 
 
 
 
 
 
i
m
a
g
e
_
b
g
r
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
_
b
g
r
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
_
b
g
r
,
(
3
6
2
,
3
6
2
)
)

 
 
 
 
 
 
 
 
i
m
a
g
e
_
y
u
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
_
b
g
r
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
Y
U
V
)

 
 
 
 
 
 
 
 
i
m
a
g
e
_
y
u
v
[
:
,
 
:
,
 
0
]
=
c
v
2
.
e
q
u
a
l
i
z
e
H
i
s
t
(
i
m
a
g
e
_
y
u
v
[
:
,
:
,
0
]
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
y
u
v
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
Y
U
V
2
R
G
B
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
5
5
<
0
0
:
0
0
,
 
 
4
.
6
2
s
/
i
t
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
6
2
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
색
상
 
구
분
 
(
s
c
o
r
e
 
:
 
0
.
9
4
4
5
8
)




•
 
이
미
지
에
서
 
한
 
색
상
을
 
구
분
하
려
면
 
색
 
범
위
를
 
정
의
하
고
 
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
합
니
다
.




•
 
이
미
지
를
 
H
S
V
(
색
상
,
 
채
도
,
 
명
도
)
로
 
변
환
 
-
>
 
격
리
시
킬
 
값
의
 
범
위
를
 
정
의
 
-
>
 
이
미
지
에
 
적
용
할
 
마
스
크
를
 
만
듭
니
다
.
(
마
 
스
크
의
 
흰
색
 
영
역
만
 
유
지
)




•
 
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
)
는
 
마
스
크
를
 
적
용
하
고
 
원
하
는
 
포
맷
으
로
 
변
환



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
.
i
n
d
e
x
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
5
4
<
0
0
:
0
0
,
 
 
4
.
5
3
s
/
i
t
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
6
2
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
이
미
지
 
이
진
화
 
(
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
0
9
5
)




•
 
이
미
지
 
이
진
화
(
임
계
처
리
)
t
h
r
e
s
h
o
l
d
i
n
g
은
 
어
떤
 
값
보
다
 
큰
 
값
을
 
가
진
 
픽
셀
을
 
흰
색
으
로
 
만
들
고
 
작
은
 
값
을
 
가
진
 
픽
셀
은
 
검
은
색
으
로
 
만
드
는
 
과
정
입
니
다
.




•
 
적
응
적
 
이
진
화
(
임
계
처
리
)
a
d
a
p
t
i
v
e
 
t
h
r
e
s
h
o
l
d
i
n
g
은
 
픽
셀
의
 
임
계
값
이
 
주
변
 
픽
셀
의
 
강
도
에
 
의
해
 
결
정
됩
니
다
.




•
 
이
진
화
는
 
이
미
지
 
안
의
 
영
역
 
마
다
 
빛
 
조
건
이
 
달
라
질
 
때
 
도
움
이
 
됩
니
다
.




•
 
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
)
의
 
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
매
개
변
수
는
 
출
력
 
픽
셀
 
강
도
의
 
최
대
값
을
 
결
정




•
 
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
는
 
픽
셀
의
 
임
계
값
을
 
주
변
 
픽
셀
 
강
도
의
 
가
중
치
 
합
으
로
 
설
정
합
니
다




•
 
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
M
E
A
N
_
C
는
 
픽
셀
의
 
임
계
값
을
 
주
변
 
픽
셀
의
 
평
균
으
로
 
설
정
합
니
다




에
러
 
발
생




흑
백
화
해
서
 
사
용



```python
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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
:

 
 
 
 
 
 
 
 
i
m
a
g
e
_
g
r
a
y
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
,
c
v
2
.
I
M
R
E
A
D
_
G
R
A
Y
S
C
A
L
E
)

 
 
 
 
 
 
 
 
i
m
a
g
e
_
g
r
a
y
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
_
g
r
a
y
,
 
(
3
6
2
,
3
6
2
)
)

 
 
 
 
 
 
 
 
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
_
g
r
a
y
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
0
0
<
0
0
:
0
0
,
 
7
7
1
.
2
8
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
6
2
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
경
계
선
 
감
지
 
(
s
c
o
r
e
:
0
.
9
7
1
0
3
)




•
 
캐
니
(
C
a
n
n
y
)
 
경
계
선
 
감
지
기
와
 
같
은
 
경
계
선
 
감
지
 
기
술
 
사
용




•
 
경
계
선
 
감
지
는
 
컴
퓨
터
 
비
전
의
 
주
요
 
관
심
 
대
상
이
며
 
경
계
선
은
 
많
은
 
정
보
가
 
담
긴
 
영
역
입
니
다
.




•
 
경
계
선
 
감
지
를
 
사
용
하
여
 
정
보
가
 
적
은
 
영
역
을
 
제
거
하
고
 
대
부
분
의
 
정
보
가
 
담
긴
 
이
미
지
 
영
역
을
 
구
분
할
 
수
 
있
습
니
다
.




•
 
캐
니
 
감
지
기
는
 
그
레
이
디
언
트
 
임
계
값
의
 
저
점
과
 
고
점
을
 
나
타
내
는
 
두
 
매
개
변
수
가
 
필
요
합
니
다
.




•
 
낮
은
 
임
계
값
과
 
높
은
 
임
계
값
 
사
이
의
 
가
능
성
 
있
는
 
경
계
선
 
픽
셀
은
 
약
한
 
경
계
선
 
픽
셀
로
 
간
주
됩
니
다




•
 
O
p
e
n
C
V
의
 
C
a
n
n
y
 
함
수
는
 
낮
은
 
임
곗
값
과
 
높
은
 
임
곗
값
이
 
필
수
 
매
개
변
수
입
니
다
.




•
 
C
a
n
n
y
를
 
전
체
 
이
미
지
 
모
음
에
 
적
용
하
기
 
전
에
 
몇
 
개
의
 
이
미
지
를
 
테
스
트
하
여
 
낮
은
 
임
계
값
과
 
높
은
 
임
곗
값
의
 
적
절
한
 
쌍
 
을
 
찾
는
 
것
이
 
좋
은
 
결
과
를
 
만
듭
니
다
.




•
 
예
제
 
실
습
은
 
낮
은
 
임
곗
값
과
 
높
은
 
임
곗
값
을
 
이
미
지
 
중
간
 
픽
셀
 
강
도
의
 
1
표
준
편
차
 
아
래
 
값
과
 
위
 
값
으
로
 
설
정



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

f
o
r
 
c
a
t
e
g
o
r
y
 
i
n
 
t
q
d
m
(
s
p
e
c
i
e
s
)
:

 
 
 
 
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
6
2
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
r
a
i
n
[
t
r
a
i
n
[
'
s
p
e
c
i
e
s
'
]
=
=
c
a
t
e
g
o
r
y
]
[
'
p
a
t
h
'
]
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
6
2
,
3
6
2
)
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
a
t
e
g
o
r
y
+
'
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
6
2
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
6
2
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
 
1
2
/
1
2
 
[
0
0
:
0
0
<
0
0
:
0
0
,
 
8
0
2
.
0
5
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
6
2
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
t
e
s
t
의
 
데
이
터
도
 
또
한
 
폴
더
안
에
 
이
미
지
가
 
저
장
되
어
 
있
으
나
,
 
s
p
e
c
i
e
s
로
 
분
류
되
어
 
있
지
 
않
습
니
다
.




g
l
o
b
로
 
p
a
t
h
 
c
o
l
u
m
n
을
 
가
져
와
서
 
d
a
t
a
f
r
a
m
e
의
 
형
식
으
로
 
특
징
을
 
추
출
할
 
수
 
있
으
나
,
 
g
l
o
b
로
는
 
순
서
가
 
뒤
엉
킨
다
는
 
단
점
이
 
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
와
 
t
e
s
t
 
d
a
t
a
를
 
모
두
 
g
l
o
b
사
용
하
는
 
경
우
,
 
t
e
s
t
 
d
a
t
a
는
 
순
서
를
 
f
i
x
하
는
 
i
n
d
e
x
 
r
e
s
e
t
작
업
을
 
추
가
로
 
진
행
 
해
주
어
야
 
합
니
다
.




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
서
 
t
e
s
t
 
d
a
t
a
를
 
가
져
오
는
 
것
으
로
 
먼
저
 
생
각
했
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
 
 
 
 
 
s
p
e
c
i
e
s

0
 
 
 
 
0
0
2
1
e
9
0
e
4
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

1
 
 
 
 
0
0
3
d
6
1
0
4
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

2
 
 
 
 
0
0
7
b
3
d
a
8
b
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

3
 
 
 
 
0
0
8
6
a
6
3
4
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

4
 
 
 
 
0
0
c
4
7
e
9
8
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
.
.
.

7
8
9
 
 
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
0
 
 
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
1
 
 
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
2
 
 
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
3
 
 
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t


[
7
9
4
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
 
 
 
 
 
s
p
e
c
i
e
s
 
 
\

0
 
 
 
 
0
0
2
1
e
9
0
e
4
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

1
 
 
 
 
0
0
3
d
6
1
0
4
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

2
 
 
 
 
0
0
7
b
3
d
a
8
b
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

3
 
 
 
 
0
0
8
6
a
6
3
4
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

4
 
 
 
 
0
0
c
4
7
e
9
8
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

7
8
9
 
 
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

7
9
0
 
 
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

7
9
1
 
 
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

7
9
2
 
 
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 

7
9
3
 
 
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
a
t
h
 
 

0
 
 
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
1
e
9
0
e
4
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
d
6
1
0
4
2
.
p
n
g
 
 

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
7
b
3
d
a
8
b
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
8
6
a
6
3
4
0
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
c
4
7
e
9
8
0
.
p
n
g
 
 

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

7
8
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 

7
9
0
 
 
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 

7
9
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 

7
9
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 

7
9
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 


[
7
9
4
 
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
이
미
지
 
분
류
 
학
습
에
 
사
용
할
 
데
이
터
를
 
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
 
로
 
나
누
어
 
학
습
을
 
진
행
하
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
s
p
e
c
i
e
s
'
]
)
```

i
m
a
g
e
 
데
이
터
를
 
처
리
해
야
 
하
므
로
,
 
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
 
변
환
하
여
 
줍
니
다
.



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
s
p
e
c
i
e
s
'
)
```

<pre>
F
o
u
n
d
 
3
8
0
0
 
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
s
p
e
c
i
e
s
'
)
```

<pre>
F
o
u
n
d
 
9
5
0
 
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

성
능
이
 
비
교
적
 
우
수
한
 
것
으
로
 
알
려
져
있
는
 
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
를
 
이
용
하
여
 
학
습
에
 
사
용
합
니
다
.



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
2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
2
4
0
1
0
7
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
4
0
6
0
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
4
8
4
6
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
6
7
0
9
:
 
I
 
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
/
c
o
r
e
/
p
l
a
t
f
o
r
m
/
c
p
u
_
f
e
a
t
u
r
e
_
g
u
a
r
d
.
c
c
:
1
4
2
]
 
T
h
i
s
 
T
e
n
s
o
r
F
l
o
w
 
b
i
n
a
r
y
 
i
s
 
o
p
t
i
m
i
z
e
d
 
w
i
t
h
 
o
n
e
A
P
I
 
D
e
e
p
 
N
e
u
r
a
l
 
N
e
t
w
o
r
k
 
L
i
b
r
a
r
y
 
(
o
n
e
D
N
N
)
 
t
o
 
u
s
e
 
t
h
e
 
f
o
l
l
o
w
i
n
g
 
C
P
U
 
i
n
s
t
r
u
c
t
i
o
n
s
 
i
n
 
p
e
r
f
o
r
m
a
n
c
e
-
c
r
i
t
i
c
a
l
 
o
p
e
r
a
t
i
o
n
s
:
 
 
A
V
X
2
 
A
V
X
5
1
2
F
 
F
M
A

T
o
 
e
n
a
b
l
e
 
t
h
e
m
 
i
n
 
o
t
h
e
r
 
o
p
e
r
a
t
i
o
n
s
,
 
r
e
b
u
i
l
d
 
T
e
n
s
o
r
F
l
o
w
 
w
i
t
h
 
t
h
e
 
a
p
p
r
o
p
r
i
a
t
e
 
c
o
m
p
i
l
e
r
 
f
l
a
g
s
.

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
7
0
5
6
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
7
7
9
9
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
3
.
3
7
8
5
3
8
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
5
.
4
9
9
4
8
8
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
5
.
5
0
0
4
1
8
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
5
.
5
0
1
1
0
7
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
g
p
u
_
e
x
e
c
u
t
o
r
.
c
c
:
9
3
7
]
 
s
u
c
c
e
s
s
f
u
l
 
N
U
M
A
 
n
o
d
e
 
r
e
a
d
 
f
r
o
m
 
S
y
s
F
S
 
h
a
d
 
n
e
g
a
t
i
v
e
 
v
a
l
u
e
 
(
-
1
)
,
 
b
u
t
 
t
h
e
r
e
 
m
u
s
t
 
b
e
 
a
t
 
l
e
a
s
t
 
o
n
e
 
N
U
M
A
 
n
o
d
e
,
 
s
o
 
r
e
t
u
r
n
i
n
g
 
N
U
M
A
 
n
o
d
e
 
z
e
r
o

2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
5
.
5
0
2
4
4
4
:
 
I
 
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
/
c
o
r
e
/
c
o
m
m
o
n
_
r
u
n
t
i
m
e
/
g
p
u
/
g
p
u
_
d
e
v
i
c
e
.
c
c
:
1
5
1
0
]
 
C
r
e
a
t
e
d
 
d
e
v
i
c
e
 
/
j
o
b
:
l
o
c
a
l
h
o
s
t
/
r
e
p
l
i
c
a
:
0
/
t
a
s
k
:
0
/
d
e
v
i
c
e
:
G
P
U
:
0
 
w
i
t
h
 
1
5
4
0
3
 
M
B
 
m
e
m
o
r
y
:
 
 
-
>
 
d
e
v
i
c
e
:
 
0
,
 
n
a
m
e
:
 
T
e
s
l
a
 
P
1
0
0
-
P
C
I
E
-
1
6
G
B
,
 
p
c
i
 
b
u
s
 
i
d
:
 
0
0
0
0
:
0
0
:
0
4
.
0
,
 
c
o
m
p
u
t
e
 
c
a
p
a
b
i
l
i
t
y
:
 
6
.
0

</pre>
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

</pre>
<pre>
2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
0
8
.
9
5
4
2
8
9
:
 
I
 
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
/
c
o
m
p
i
l
e
r
/
m
l
i
r
/
m
l
i
r
_
g
r
a
p
h
_
o
p
t
i
m
i
z
a
t
i
o
n
_
p
a
s
s
.
c
c
:
1
8
5
]
 
N
o
n
e
 
o
f
 
t
h
e
 
M
L
I
R
 
O
p
t
i
m
i
z
a
t
i
o
n
 
P
a
s
s
e
s
 
a
r
e
 
e
n
a
b
l
e
d
 
(
r
e
g
i
s
t
e
r
e
d
 
2
)

</pre>
<pre>
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

</pre>
<pre>
2
0
2
2
-
0
5
-
2
2
 
0
4
:
1
2
:
1
7
.
6
3
4
3
2
8
:
 
I
 
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
/
s
t
r
e
a
m
_
e
x
e
c
u
t
o
r
/
c
u
d
a
/
c
u
d
a
_
d
n
n
.
c
c
:
3
6
9
]
 
L
o
a
d
e
d
 
c
u
D
N
N
 
v
e
r
s
i
o
n
 
8
0
0
5

</pre>
<pre>
1
1
9
/
1
1
9
 
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
9
s
 
5
4
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
5
7
8
1
 
-
 
a
c
c
:
 
0
.
8
0
7
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
2
5
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
6
7
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

1
1
9
/
1
1
9
 
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
3
s
 
5
2
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
1
9
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
3
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
8
2
6
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
7
9
1
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

1
1
9
/
1
1
9
 
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
1
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
6
3
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
1
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
4
2

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

1
1
9
/
1
1
9
 
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
5
s
 
5
4
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
8
9
4
 
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
4
4
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
2
6
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

1
1
9
/
1
1
9
 
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
1
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
6
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
 
0
.
4
4
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
8
6
0
0

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

1
1
9
/
1
1
9
 
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
7
8
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
3
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
1
4
7

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

1
1
9
/
1
1
9
 
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
5
1
7
 
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
5
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
4
7
4

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

1
1
9
/
1
1
9
 
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
5
0
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
3
4
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
9
0
7
4


E
p
o
c
h
 
0
0
0
0
8
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
5
c
9
0
1
5
6
5
9
0
>
</pre>
p
r
e
d
i
c
t
할
 
t
e
s
t
값
을
 
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
 
변
환
해
 
줍
니
다
.



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
```

<pre>
F
o
u
n
d
 
7
9
4
 
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
```

<pre>
2
5
/
2
5
 
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
s
 
2
1
0
m
s
/
s
t
e
p

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
 
 
 
 
 
s
p
e
c
i
e
s

0
 
 
 
 
0
0
2
1
e
9
0
e
4
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

1
 
 
 
 
0
0
3
d
6
1
0
4
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

2
 
 
 
 
0
0
7
b
3
d
a
8
b
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

3
 
 
 
 
0
0
8
6
a
6
3
4
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

4
 
 
 
 
0
0
c
4
7
e
9
8
0
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
.
.
.

7
8
9
 
 
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
0
 
 
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
1
 
 
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
2
 
 
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t

7
9
3
 
 
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 
S
u
g
a
r
 
b
e
e
t


[
7
9
4
 
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
r
e
s
u
l
t
의
 
값
을
 
살
펴
보
면
,
 
모
든
 
가
능
한
 
s
p
e
c
i
e
s
별
 
일
치
할
 
확
률
이
 
나
타
나
 
있
습
니
다
.




따
라
서
 
가
장
 
높
은
 
값
을
 
가
져
오
는
 
a
r
g
m
a
x
(
1
)
를
 
이
용
하
여
 
s
u
b
 
d
a
t
a
f
r
a
m
e
의
 
s
p
e
c
i
e
s
 
c
o
l
u
m
n
으
로
 
추
가
할
 
수
 
있
습
니
다
.




그
러
나
 
결
과
에
는
 
각
 
s
p
e
c
i
e
s
에
 
해
당
하
는
 
숫
자
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




따
라
서
 
이
를
 
s
p
e
c
i
e
s
 
명
 
(
문
자
)
로
 
변
환
하
는
 
작
업
이
 
필
요
합
니
다
.




먼
저
 
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
에
서
 
존
재
하
는
 
c
l
a
s
s
의
 
명
칭
 
l
i
s
t
를
 
가
져
와
 
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
로
 
지
정
해
 
주
겠
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
s
p
e
c
i
e
s
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
B
l
a
c
k
-
g
r
a
s
s
'
,

 
'
C
h
a
r
l
o
c
k
'
,

 
'
C
l
e
a
v
e
r
s
'
,

 
'
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
'
,

 
'
C
o
m
m
o
n
 
w
h
e
a
t
'
,

 
'
F
a
t
 
H
e
n
'
,

 
'
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
'
,

 
'
M
a
i
z
e
'
,

 
'
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
'
,

 
'
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
'
,

 
'
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
'
,

 
'
S
u
g
a
r
 
b
e
e
t
'
]
</pre>

```python
s
u
b
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
i
l
e
 
 
s
p
e
c
i
e
s

0
 
 
 
 
0
0
2
1
e
9
0
e
4
.
p
n
g
 
 
 
 
 
 
 
1
0

1
 
 
 
 
0
0
3
d
6
1
0
4
2
.
p
n
g
 
 
 
 
 
 
 
 
5

2
 
 
 
 
0
0
7
b
3
d
a
8
b
.
p
n
g
 
 
 
 
 
 
 
1
1

3
 
 
 
 
0
0
8
6
a
6
3
4
0
.
p
n
g
 
 
 
 
 
 
 
 
3

4
 
 
 
 
0
0
c
4
7
e
9
8
0
.
p
n
g
 
 
 
 
 
 
 
1
1

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
.
.
.

7
8
9
 
 
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 
 
 
 
 
 
 
6

7
9
0
 
 
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 
 
 
 
 
 
1
1

7
9
1
 
 
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 
 
 
 
 
 
1
1

7
9
2
 
 
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 
 
 
 
 
 
 
1

7
9
3
 
 
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 
 
 
 
 
 
 
0


[
7
9
4
 
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
c
l
a
s
s
 
l
i
s
t
에
 
각
 
해
당
하
는
 
숫
자
 
값
을
 
부
여
하
고
 
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
로
 
지
정
해
 
주
겠
습
니
다
.



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
2
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
B
l
a
c
k
-
g
r
a
s
s
'
,

 
1
:
 
'
C
h
a
r
l
o
c
k
'
,

 
2
:
 
'
C
l
e
a
v
e
r
s
'
,

 
3
:
 
'
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
'
,

 
4
:
 
'
C
o
m
m
o
n
 
w
h
e
a
t
'
,

 
5
:
 
'
F
a
t
 
H
e
n
'
,

 
6
:
 
'
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
'
,

 
7
:
 
'
M
a
i
z
e
'
,

 
8
:
 
'
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
'
,

 
9
:
 
'
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
'
,

 
1
0
:
 
'
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
'
,

 
1
1
:
 
'
S
u
g
a
r
 
b
e
e
t
'
}
</pre>
기
존
 
s
u
b
 
d
a
t
a
f
r
a
m
e
의
 
s
p
e
c
i
e
s
 
c
o
l
u
m
n
값
을
 
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
로
 
대
체
하
면
 
해
당
하
는
 
s
p
e
c
i
e
s
 
명
으
로
 
대
체
가
 
됩
니
다
.



```python
s
u
b
[
'
s
p
e
c
i
e
s
'
]
=
s
u
b
[
'
s
p
e
c
i
e
s
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
p
e
c
i
e
s

0
 
 
 
 
0
0
2
1
e
9
0
e
4
.
p
n
g
 
 
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l

1
 
 
 
 
0
0
3
d
6
1
0
4
2
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
F
a
t
 
H
e
n

2
 
 
 
 
0
0
7
b
3
d
a
8
b
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
g
a
r
 
b
e
e
t

3
 
 
 
 
0
0
8
6
a
6
3
4
0
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d

4
 
 
 
 
0
0
c
4
7
e
9
8
0
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
g
a
r
 
b
e
e
t

.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.

7
8
9
 
 
f
e
a
3
5
5
8
5
1
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t

7
9
0
 
 
f
e
a
3
d
a
5
7
c
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
g
a
r
 
b
e
e
t

7
9
1
 
 
f
e
f
2
a
d
e
8
c
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
g
a
r
 
b
e
e
t

7
9
2
 
 
f
f
6
5
b
c
0
0
2
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
C
h
a
r
l
o
c
k

7
9
3
 
 
f
f
c
6
f
8
5
2
7
.
p
n
g
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
B
l
a
c
k
-
g
r
a
s
s


[
7
9
4
 
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
c
u
t
t
i
n
g
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

제
출
하
였
을
 
때
,
 
s
c
o
r
e
가
 
높
을
 
수
록
 
대
회
 
순
위
가
 
개
선
되
었
습
니
다
.




캐
니
 
경
계
선
 
감
지
 
>
 
자
르
기
 
>
 
이
진
화
 
>
 
대
비
 
높
이
기
 
1
번
째
 
>
 
투
명
도
 
처
리
 
2
번
째
 
>
 
투
명
도
 
처
리
 
1
번
째
 
>
 
색
상
 
구
분
 
>
 
선
명
하
게
 
하
기
 
>
 
대
비
 
높
이
기
 
2
번
째




순
으
로
 
s
c
o
r
e
가
 
높
았
습
니
다
.




각
 
s
p
e
c
i
e
s
 
별
 
이
미
지
를
 
한
개
씩
 
불
러
와
 
보
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

d
i
s
p
l
a
y
(
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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
h
a
r
l
o
c
k
/
d
0
4
e
f
f
4
5
0
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
c
e
n
t
l
e
s
s
 
M
a
y
w
e
e
d
/
0
8
6
8
9
4
2
7
4
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
w
h
e
a
t
/
d
f
5
8
4
c
a
2
8
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
B
l
a
c
k
-
g
r
a
s
s
/
2
a
a
6
0
0
4
5
d
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
u
g
a
r
 
b
e
e
t
/
6
d
6
3
e
b
9
8
f
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
L
o
o
s
e
 
S
i
l
k
y
-
b
e
n
t
/
9
3
d
9
8
5
8
f
0
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
M
a
i
z
e
/
f
2
c
2
2
a
1
b
f
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
l
e
a
v
e
r
s
/
b
d
6
6
8
1
c
0
2
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
C
o
m
m
o
n
 
C
h
i
c
k
w
e
e
d
/
e
d
d
a
f
3
d
4
7
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
F
a
t
 
H
e
n
/
7
f
7
3
1
3
1
1
e
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
m
a
l
l
-
f
l
o
w
e
r
e
d
 
C
r
a
n
e
s
b
i
l
l
/
b
8
a
c
3
7
d
c
d
.
p
n
g
'
)
,

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
p
l
a
n
t
-
s
e
e
d
l
i
n
g
s
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
S
h
e
p
h
e
r
d
s
 
P
u
r
s
e
/
8
0
5
6
c
3
5
9
0
.
p
n
g
'
)
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
4
2
2
x
4
2
2
 
a
t
 
0
x
7
F
5
D
0
3
9
C
3
D
5
0
>
</pre>
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
3
7
5
x
3
7
5
 
a
t
 
0
x
7
F
5
D
0
3
9
C
8
5
5
0
>
</pre>
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
5
5
6
x
5
5
6
 
a
t
 
0
x
7
F
5
D
0
3
9
C
3
E
D
0
>
</pre>
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
8
0
0
x
8
0
0
 
a
t
 
0
x
7
F
5
D
0
3
9
C
8
1
9
0
>
</pre>
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
4
4
8
x
4
4
8
 
a
t
 
0
x
7
F
5
D
0
3
0
1
E
D
9
0
>
</pre>
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
1
0
6
x
1
0
6
 
a
t
 
0
x
7
F
5
C
0
5
3
7
1
F
D
0
>
</pre>
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
6
3
1
x
6
3
1
 
a
t
 
0
x
7
F
5
C
0
5
3
7
1
D
5
0
>
</pre>
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
2
x
2
2
2
 
a
t
 
0
x
7
F
5
D
1
2
A
2
3
6
1
0
>
</pre>
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
7
5
x
7
5
 
a
t
 
0
x
7
F
5
D
1
2
A
2
3
9
1
0
>
</pre>
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
1
7
0
x
1
7
0
 
a
t
 
0
x
7
F
5
D
1
2
A
2
3
F
1
0
>
</pre>
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
1
5
7
x
1
5
7
 
a
t
 
0
x
7
F
5
D
0
3
1
7
1
5
1
0
>
</pre>
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
1
2
6
x
1
2
6
 
a
t
 
0
x
7
F
5
D
0
3
1
7
1
6
D
0
>
</pre>
캐
니
 
경
계
선
 
감
지
 
>
 
자
르
기
 
>
 
이
진
화
 
>
 
대
비
 
높
이
기
 
1
번
째
 
>
 
투
명
도
 
처
리
 
2
번
째
 
>
 
투
명
도
 
처
리
 
1
번
째
 
>
 
색
상
 
구
분
 
>
 
선
명
하
게
 
하
기
 
>
 
대
비
 
높
이
기
 
2
번
째




각
 
p
l
a
n
t
s
의
 
가
장
 
두
드
러
진
 
차
이
점
은
 
모
서
리
 
부
분
 
입
니
다
.
 
따
라
서
 
캐
니
 
경
계
선
 
감
지
 
전
처
리
가
 
가
장
 
효
과
적
이
었
고
,
 
이
미
지
를
 
자
르
게
 
되
면
 
학
습
 
효
과
가
 
세
분
화
됩
니
다




이
미
지
 
이
진
화
를
 
하
게
 
되
면
 
어
두
운
 
곳
에
서
 
촬
영
된
 
경
우
 
보
정
하
여
 
학
습
하
므
로
 
정
확
도
를
 
높
인
다
는
 
장
점
이
 
있
습
니
다
.
 
또
한
 
이
미
지
 
대
비
를
 
높
일
 
때
 
컬
러
보
다
 
흑
백
일
 
경
우
 
모
양
이
 
두
드
러
지
지
 
않
아
 
더
욱
 
세
밀
하
게
 
학
습
 
훈
련
할
 
수
 
있
습
니
다
.




이
미
지
 
투
명
도
 
처
리
의
 
경
우
도
 
단
순
히
 
b
l
u
r
 
처
리
를
 
하
는
 
것
보
다
,
 
f
i
l
t
e
r
2
D
이
후
 
G
a
u
s
s
i
a
n
B
l
u
r
를
 
이
용
할
 
때
 
학
습
효
과
가
 
높
았
습
니
다
.




s
p
e
c
i
e
s
간
 
색
상
 
차
이
는
 
크
지
 
않
아
서
 
선
명
하
게
 
혹
은
 
색
상
 
구
분
을
 
극
대
화
하
는
 
것
보
다
 
흑
백
처
리
하
여
 
학
습
하
는
 
것
이
 
더
욱
 
효
과
가
 
높
았
습
니
다
.




주
어
진
 
데
이
터
의
 
두
드
러
진
 
차
이
점
을
 
감
안
하
여
 
데
이
터
 
전
처
리
가
 
필
요
함
을
 
느
꼈
습
니
다
.

