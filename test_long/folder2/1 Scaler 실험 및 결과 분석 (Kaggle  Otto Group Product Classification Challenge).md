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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
/
s
a
m
p
l
e
S
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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
/
t
e
s
t
.
c
s
v

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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
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
o
t
t
o
-
g
r
o
u
p
-
p
r
o
d
u
c
t
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
-
c
h
a
l
l
e
n
g
e
/
s
a
m
p
l
e
S
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

d
i
s
p
l
a
y
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
,
s
u
b
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
i
d
 
 
f
e
a
t
_
1
 
 
f
e
a
t
_
2
 
 
f
e
a
t
_
3
 
 
f
e
a
t
_
4
 
 
f
e
a
t
_
5
 
 
f
e
a
t
_
6
 
 
f
e
a
t
_
7
 
 
f
e
a
t
_
8
 
 
\

0
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 

2
 
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 

3
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
6
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
.
.
.
 
 
 
 
 
.
.
.
 
 
 

6
1
8
7
3
 
 
6
1
8
7
4
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
4
 
 
6
1
8
7
5
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
5
 
 
6
1
8
7
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
3
 
 
 

6
1
8
7
6
 
 
6
1
8
7
7
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
7
 
 
6
1
8
7
8
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
.
.
.
 
 
f
e
a
t
_
8
5
 
 
f
e
a
t
_
8
6
 
 
f
e
a
t
_
8
7
 
 
f
e
a
t
_
8
8
 
 
f
e
a
t
_
8
9
 
 
f
e
a
t
_
9
0
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
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
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
.
.
.
 
 
 

6
1
8
7
3
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
4
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
5
 
 
 
 
 
 
 
1
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
6
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 

6
1
8
7
7
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
f
e
a
t
_
9
2
 
 
f
e
a
t
_
9
3
 
 
 
t
a
r
g
e
t
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
1
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
1
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
1
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
1
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
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
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
.
.
.
 
 

6
1
8
7
3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
9
 
 

6
1
8
7
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
9
 
 

6
1
8
7
5
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
9
 
 

6
1
8
7
6
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
1
0
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
9
 
 

6
1
8
7
7
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
C
l
a
s
s
_
9
 
 


[
6
1
8
7
8
 
r
o
w
s
 
x
 
9
5
 
c
o
l
u
m
n
s
]
</pre>
<pre>
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
f
e
a
t
_
1
 
 
f
e
a
t
_
2
 
 
f
e
a
t
_
3
 
 
f
e
a
t
_
4
 
 
f
e
a
t
_
5
 
 
f
e
a
t
_
6
 
 
f
e
a
t
_
7
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
2
 
 
 
 
 
 
1
4
 
 
 
 
 
 
1
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
1
2
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
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
 
 
 
 
 
.
.
.
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
1
4
4
3
6
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
4
 
 
1
4
4
3
6
5
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
5
 
 
1
4
4
3
6
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
6
 
 
1
4
4
3
6
7
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
7
 
 
1
4
4
3
6
8
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
f
e
a
t
_
9
 
 
.
.
.
 
 
f
e
a
t
_
8
4
 
 
f
e
a
t
_
8
5
 
 
f
e
a
t
_
8
6
 
 
f
e
a
t
_
8
7
 
 
f
e
a
t
_
8
8
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
1
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
2
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
1
1
 
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
5
 
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
9
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
6
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
f
e
a
t
_
9
0
 
 
f
e
a
t
_
9
1
 
 
f
e
a
t
_
9
2
 
 
f
e
a
t
_
9
3
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
9
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
.
.
.
 
 

1
4
4
3
6
3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 


[
1
4
4
3
6
8
 
r
o
w
s
 
x
 
9
4
 
c
o
l
u
m
n
s
]
</pre>
<pre>
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
C
l
a
s
s
_
1
 
 
C
l
a
s
s
_
2
 
 
C
l
a
s
s
_
3
 
 
C
l
a
s
s
_
4
 
 
C
l
a
s
s
_
5
 
 
C
l
a
s
s
_
6
 
 
C
l
a
s
s
_
7
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
1
4
4
3
6
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
4
 
 
1
4
4
3
6
5
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
5
 
 
1
4
4
3
6
6
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
6
 
 
1
4
4
3
6
7
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
7
 
 
1
4
4
3
6
8
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
 
C
l
a
s
s
_
8
 
 
C
l
a
s
s
_
9
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

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
4
4
3
6
3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 


[
1
4
4
3
6
8
 
r
o
w
s
 
x
 
1
0
 
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
a
l
l
d
a
t
a
=
p
d
.
c
o
n
c
a
t
(
[
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
]
)

a
l
l
d
a
t
a
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
 
 
 
 
 
 
 
f
e
a
t
_
2
 
 
 
 
 
 
 
 
 
f
e
a
t
_
3
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
5
9
8
1
0
.
1
6
0
0
8
6
 
 
 
 
 
 
 
0
.
3
8
6
3
4
4
 
 
 
 
 
 
 
0
.
2
6
3
4
3
8
 
 
 
 
 
 
 
0
.
9
0
0
3
1
3
 
 
 

s
t
d
 
 
 
 
 
4
0
8
5
0
.
3
0
0
5
2
2
 
 
 
 
 
 
 
1
.
4
8
6
0
3
9
 
 
 
 
 
 
 
1
.
2
5
8
9
6
3
 
 
 
 
 
 
 
2
.
9
4
4
8
1
9
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
2
5
7
8
1
.
2
5
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
5
1
5
6
2
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
9
2
8
0
6
.
7
5
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
1
4
4
3
6
8
.
0
0
0
0
0
0
 
 
 
 
 
 
6
4
.
0
0
0
0
0
0
 
 
 
 
 
 
5
1
.
0
0
0
0
0
0
 
 
 
 
 
 
8
4
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
4
 
 
 
 
 
 
 
 
 
f
e
a
t
_
5
 
 
 
 
 
 
 
 
 
f
e
a
t
_
6
 
 
 
 
 
 
 
 
 
f
e
a
t
_
7
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
7
8
0
2
3
3
 
 
 
 
 
 
 
0
.
0
7
1
3
6
1
 
 
 
 
 
 
 
0
.
0
2
6
2
1
6
 
 
 
 
 
 
 
0
.
1
9
8
2
2
9
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
8
2
8
8
4
6
 
 
 
 
 
 
 
0
.
4
3
1
6
9
4
 
 
 
 
 
 
 
0
.
2
2
4
5
2
6
 
 
 
 
 
 
 
1
.
0
5
7
6
4
8
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
8
2
.
0
0
0
0
0
0
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 
 
 
 
1
1
.
0
0
0
0
0
0
 
 
 
 
 
 
4
4
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
.
.
.
 
 
 
 
 
 
 
 
f
e
a
t
_
8
4
 
 
 
 
 
 
 
 
f
e
a
t
_
8
5
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
.
.
.
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
6
6
5
8
9
4
 
 
 
 
 
 
 
1
.
0
2
8
0
7
8
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
7
3
7
1
8
 
 
 
 
 
 
 
0
.
5
3
6
6
3
1
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
2
7
7
5
5
3
 
 
 
 
 
 
 
3
.
5
2
6
6
4
8
 
 
.
.
.
 
 
 
 
 
 
 
1
.
2
4
9
0
3
3
 
 
 
 
 
 
 
1
.
9
0
4
4
1
5
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
 
 
 
 
4
7
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
1
3
2
.
0
0
0
0
0
0
 
 
 
 
 
 
5
6
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
6
 
 
 
 
 
 
 
 
f
e
a
t
_
8
7
 
 
 
 
 
 
 
 
f
e
a
t
_
8
8
 
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
1
.
1
2
8
7
2
0
 
 
 
 
 
 
 
0
.
4
0
1
7
3
9
 
 
 
 
 
 
 
0
.
8
7
5
3
4
3
 
 
 
 
 
 
 
0
.
4
6
8
6
3
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
6
8
2
2
1
8
 
 
 
 
 
 
 
1
.
6
1
4
9
4
1
 
 
 
 
 
 
 
2
.
0
9
7
8
6
9
 
 
 
 
 
 
 
1
.
5
9
1
2
6
3
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
7
3
.
0
0
0
0
0
0
 
 
 
 
 
 
6
7
.
0
0
0
0
0
0
 
 
 
 
 
 
3
7
.
0
0
0
0
0
0
 
 
 
 
 
 
6
2
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
0
 
 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
 
 
 
 
 
 
f
e
a
t
_
9
2
 
 
 
 
 
 
 
 
f
e
a
t
_
9
3
 
 

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
8
1
3
5
3
3
 
 
 
 
 
 
 
0
.
2
6
9
2
9
5
 
 
 
 
 
 
 
0
.
3
8
5
8
7
9
 
 
 
 
 
 
 
0
.
1
3
0
7
1
3
 
 

s
t
d
 
 
 
 
 
 
 
 
 
4
.
6
0
1
8
8
8
 
 
 
 
 
 
 
2
.
0
6
5
2
6
9
 
 
 
 
 
 
 
0
.
9
9
9
6
3
7
 
 
 
 
 
 
 
1
.
2
7
3
2
4
2
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
 
1
3
0
.
0
0
0
0
0
0
 
 
 
 
 
 
7
4
.
0
0
0
0
0
0
 
 
 
 
 
 
2
2
.
0
0
0
0
0
0
 
 
 
 
 
 
9
1
.
0
0
0
0
0
0
 
 


[
8
 
r
o
w
s
 
x
 
9
4
 
c
o
l
u
m
n
s
]
</pre>
m
i
n
과
 
m
a
x
의
 
차
이
가
 
있
음
에
도
 
불
구
하
고
 
2
5
%
,
 
5
0
%
 
7
0
%
 
p
e
r
c
e
n
t
i
l
e
에
서
 
대
부
분
 
0
의
 
값
을
 
나
타
내
고
 
있
습
니
다
.




원
인
을
 
알
아
보
기
 
위
해
 
c
o
u
n
t
p
l
o
t
으
로
 
시
각
화
하
여
 
원
인
을
 
알
아
 
보
겠
습
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
 
m
a
t
p
l
o
t
l
i
b
.
p
y
p
l
o
t
 
a
s
 
p
l
t

i
m
p
o
r
t
 
s
e
a
b
o
r
n
 
a
s
 
s
n
s

s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
<
A
x
e
s
S
u
b
p
l
o
t
:
x
l
a
b
e
l
=
'
f
e
a
t
_
2
'
,
 
y
l
a
b
e
l
=
'
c
o
u
n
t
'
>
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>
대
부
분
의
 
값
이
 
0
이
 
1
7
5
0
0
0
개
로
 
압
도
적
으
로
 
많
고
 
1
부
터
의
 
값
은
 
2
5
0
0
0
이
하
로
 
값
이
 
잘
 
보
이
지
 
않
습
니
다
.




y
축
을
 
확
대
하
여
 
보
겠
습
니
다
.



```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
2
0
0
0
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
2
0
0
0
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
5
0
0
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
5
0
0
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
1
0
0
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
1
0
0
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
5
0
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
5
0
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
1
0
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
1
0
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
5
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
5
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>

```python
s
n
s
.
c
o
u
n
t
p
l
o
t
(
a
l
l
d
a
t
a
[
'
f
e
a
t
_
2
'
]
)

p
l
t
.
y
l
i
m
(
0
,
1
0
)
```

<pre>
/
o
p
t
/
c
o
n
d
a
/
l
i
b
/
p
y
t
h
o
n
3
.
7
/
s
i
t
e
-
p
a
c
k
a
g
e
s
/
s
e
a
b
o
r
n
/
_
d
e
c
o
r
a
t
o
r
s
.
p
y
:
4
3
:
 
F
u
t
u
r
e
W
a
r
n
i
n
g
:
 
P
a
s
s
 
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
 
v
a
r
i
a
b
l
e
 
a
s
 
a
 
k
e
y
w
o
r
d
 
a
r
g
:
 
x
.
 
F
r
o
m
 
v
e
r
s
i
o
n
 
0
.
1
2
,
 
t
h
e
 
o
n
l
y
 
v
a
l
i
d
 
p
o
s
i
t
i
o
n
a
l
 
a
r
g
u
m
e
n
t
 
w
i
l
l
 
b
e
 
`
d
a
t
a
`
,
 
a
n
d
 
p
a
s
s
i
n
g
 
o
t
h
e
r
 
a
r
g
u
m
e
n
t
s
 
w
i
t
h
o
u
t
 
a
n
 
e
x
p
l
i
c
i
t
 
k
e
y
w
o
r
d
 
w
i
l
l
 
r
e
s
u
l
t
 
i
n
 
a
n
 
e
r
r
o
r
 
o
r
 
m
i
s
i
n
t
e
r
p
r
e
t
a
t
i
o
n
.

 
 
F
u
t
u
r
e
W
a
r
n
i
n
g

</pre>
<pre>
(
0
.
0
,
 
1
0
.
0
)
</pre>
<pre>
<
F
i
g
u
r
e
 
s
i
z
e
 
4
3
2
x
2
8
8
 
w
i
t
h
 
1
 
A
x
e
s
>
</pre>
0
의
 
값
이
 
1
에
 
비
해
 
1
0
배
 
이
상
 
많
고
,
 
1
의
 
값
이
 
2
에
 
비
해
 
2
배
 
이
상
 
많
습
니
다
.




f
e
a
t
_
1
 
뿐
만
 
아
니
라
 
다
른
 
c
o
l
u
m
n
도
 
조
회
하
였
을
 
때
,
 
비
슷
한
 
양
상
을
 
보
입
니
다
.




따
라
서
 
S
c
a
l
e
r
 
방
식
에
 
따
라
 
전
처
리
 
데
이
터
의
 
정
확
도
가
 
달
라
지
게
 
될
 
것
으
로
 
보
입
니
다
.



```python
a
l
l
d
a
t
a
2
=
a
l
l
d
a
t
a
.
d
r
o
p
(
c
o
l
u
m
n
s
=
[
'
i
d
'
,
'
t
a
r
g
e
t
'
]
)

a
l
l
d
a
t
a
2
```

<pre>
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
f
e
a
t
_
2
 
 
f
e
a
t
_
3
 
 
f
e
a
t
_
4
 
 
f
e
a
t
_
5
 
 
f
e
a
t
_
6
 
 
f
e
a
t
_
7
 
 
f
e
a
t
_
8
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
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
 
 
 
 
 
 
 
1
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
6
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
f
e
a
t
_
1
0
 
 
.
.
.
 
 
f
e
a
t
_
8
4
 
 
f
e
a
t
_
8
5
 
 
f
e
a
t
_
8
6
 
 
f
e
a
t
_
8
7
 
 
f
e
a
t
_
8
8
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
.
.
.
 
 
 
 
 
 
 
2
2
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
1
1
 
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
5
 
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
.
.
.
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
9
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
6
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
f
e
a
t
_
9
0
 
 
f
e
a
t
_
9
1
 
 
f
e
a
t
_
9
2
 
 
f
e
a
t
_
9
3
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
.
.
.
 
 

1
4
4
3
6
3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 


[
2
0
6
2
4
6
 
r
o
w
s
 
x
 
9
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
*
R
o
b
u
s
t
S
c
a
l
e
r
*




특
이
 
치
에
 
강
력
한
 
통
계
를
 
사
용
하
여
 
기
능
을
 
확
장
합
니
다
.




이
 
스
케
일
러
는
 
중
앙
값
을
 
제
거
하
고
 
Q
u
a
n
t
i
l
e
 
범
위
(
 
기
본
값
을
 
I
Q
R
 
:
 
I
n
t
e
r
q
u
r
t
i
l
e
 
R
a
n
g
e
)
에
 
따
라
 
데
이
터
를
 
스
케
일
링
합
니
다
.




I
Q
R
은
 
1
분
위
(
2
5
분
위
)
와
 
3
분
위
(
7
5
분
위
)
 
사
이
의
 
범
위
입
니
다
.




센
터
링
 
및
 
스
케
일
링
은
 
학
습
 
세
트
의
 
샘
플
에
 
대
한
 
관
련
 
통
계
를
 
계
산
하
여
 
각
 
기
능
에
서
 
독
립
적
으
로
 
발
생
합
니
다
.
 




그
런
 
다
음
 
중
앙
값
과
 
사
 
분
위
수
 
범
위
를
 
저
장
하
여
 
t
r
a
n
s
f
o
r
m
방
법
을
 
사
용
하
여
 
나
중
에
 
데
이
터
에
 
사
용
합
니
다
.




평
균
과
 
분
산
 
대
신
 
중
간
값
과
 
사
분
위
 
값
을
 
조
정
하
여
 
아
주
 
동
 
떨
어
진
 
데
이
터
를
 
제
거
해
 
줍
니
다
.




S
t
a
n
d
a
r
d
S
c
a
l
e
r
와
 
비
슷
 
하
지
만
 
평
균
과
 
분
산
대
신
 
중
간
값
(
m
e
d
i
a
n
)
과
 
사
분
위
값
(
q
u
a
r
t
i
l
e
)
을
 
사
용
합
니
다
.




이
런
 
방
식
 
때
문
에
 
R
o
b
u
s
t
S
c
a
l
e
r
는
 
전
체
 
데
이
터
와
 
아
주
 
동
떨
어
진
 
데
이
터
 
포
인
트
 
(
예
를
 
들
면
 
측
정
 
에
러
)
에
 
영
향
을
 
받
지
 
않
습
니
다
.




중
앙
값
(
m
e
d
i
a
n
)
과
 
I
Q
R
(
i
n
t
e
r
q
u
a
r
t
i
l
e
 
r
a
n
g
e
)
을
 
사
용
하
기
 
때
문
에
 
S
t
a
n
d
a
r
d
S
c
a
l
e
r
와
 
비
교
해
보
면
 
표
준
화
 
후
 
동
일
한
 
값
을
 
더
 
넓
게
 
분
포
 
시
킵
니
다
.




아
웃
라
이
어
의
 
영
향
을
 
최
소
화
하
고
,
 
I
Q
R
 
=
 
Q
3
 
-
 
Q
1
 
즉
 
2
5
퍼
센
타
일
과
 
7
5
퍼
센
타
일
의
 
값
을
 
다
룹
니
다
.




아
웃
라
이
어
가
 
많
을
 
때
 
R
o
b
u
s
t
S
c
a
l
e
r
 
작
동
 
방
식
 
:
 
특
이
치
에
 
대
해
 
강
력
한
 
통
계
를
 
사
용
하
여
 
기
능
을
 
확
장
합
니
다
.




이
 
방
법
은
 
중
앙
값
을
 
제
거
하
고
 
1
사
분
위
와
 
3
사
 
분
위
 
범
위
의
 
데
이
터
를
 
스
케
일
링
합
니
다
.




즉
,
 
2
5
번
째
 
분
위
수
와
 
7
5
번
째
 
분
위
수
 
범
위
 
사
이
,
 
이
번
위
를
 
사
분
위
수
 
범
위
 
라
고
도
 
합
니
다
.



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
 
i
m
p
o
r
t
 
R
o
b
u
s
t
S
c
a
l
e
r

r
s
=
R
o
b
u
s
t
S
c
a
l
e
r
(
)

a
l
l
d
a
t
a
3
=
r
s
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
a
l
l
d
a
t
a
2
)

a
l
l
d
a
t
a
3
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
a
l
l
d
a
t
a
3
,
c
o
l
u
m
n
s
=
a
l
l
d
a
t
a
2
.
c
o
l
u
m
n
s
)

a
l
l
d
a
t
a
3
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
 
 
 
 
 
 
 
f
e
a
t
_
2
 
 
 
 
 
 
 
 
 
f
e
a
t
_
3
 
 
 
 
 
 
 
 
 
f
e
a
t
_
4
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
3
8
6
3
4
4
 
 
 
 
 
 
 
0
.
2
6
3
4
3
8
 
 
 
 
 
 
 
0
.
9
0
0
3
1
3
 
 
 
 
 
 
 
0
.
7
8
0
2
3
3
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
1
.
4
8
6
0
3
9
 
 
 
 
 
 
 
1
.
2
5
8
9
6
3
 
 
 
 
 
 
 
2
.
9
4
4
8
1
9
 
 
 
 
 
 
 
2
.
8
2
8
8
4
6
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
6
4
.
0
0
0
0
0
0
 
 
 
 
 
 
5
1
.
0
0
0
0
0
0
 
 
 
 
 
 
8
4
.
0
0
0
0
0
0
 
 
 
 
 
 
8
2
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
5
 
 
 
 
 
 
 
 
 
f
e
a
t
_
6
 
 
 
 
 
 
 
 
 
f
e
a
t
_
7
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
7
1
3
6
1
 
 
 
 
 
 
 
0
.
0
2
6
2
1
6
 
 
 
 
 
 
 
0
.
1
9
8
2
2
9
 
 
 
 
 
 
 
0
.
6
6
5
8
9
4
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
4
3
1
6
9
4
 
 
 
 
 
 
 
0
.
2
2
4
5
2
6
 
 
 
 
 
 
 
1
.
0
5
7
6
4
8
 
 
 
 
 
 
 
2
.
2
7
7
5
5
3
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
1
9
.
0
0
0
0
0
0
 
 
 
 
 
 
1
1
.
0
0
0
0
0
0
 
 
 
 
 
 
4
4
.
0
0
0
0
0
0
 
 
 
 
 
1
0
0
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
 
 
 
 
 
 
f
e
a
t
_
1
0
 
 
.
.
.
 
 
 
 
 
 
 
 
f
e
a
t
_
8
4
 
 
 
 
 
 
 
 
f
e
a
t
_
8
5
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
.
.
.
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
1
.
0
2
8
0
7
8
 
 
 
 
 
 
 
0
.
2
6
7
3
1
7
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
7
3
7
1
8
 
 
 
 
 
 
 
0
.
5
3
6
6
3
1
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
3
.
5
2
6
6
4
8
 
 
 
 
 
 
 
1
.
1
5
7
1
2
4
 
 
.
.
.
 
 
 
 
 
 
 
1
.
2
4
9
0
3
3
 
 
 
 
 
 
 
1
.
9
0
4
4
1
5
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
4
7
.
0
0
0
0
0
0
 
 
 
 
 
 
5
9
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
1
3
2
.
0
0
0
0
0
0
 
 
 
 
 
 
5
6
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
6
 
 
 
 
 
 
 
 
f
e
a
t
_
8
7
 
 
 
 
 
 
 
 
f
e
a
t
_
8
8
 
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
1
.
1
2
8
7
2
0
 
 
 
 
 
 
 
0
.
4
0
1
7
3
9
 
 
 
 
 
 
 
0
.
8
7
5
3
4
3
 
 
 
 
 
 
 
0
.
4
6
8
6
3
0
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
2
.
6
8
2
2
1
8
 
 
 
 
 
 
 
1
.
6
1
4
9
4
1
 
 
 
 
 
 
 
2
.
0
9
7
8
6
9
 
 
 
 
 
 
 
1
.
5
9
1
2
6
3
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
7
3
.
0
0
0
0
0
0
 
 
 
 
 
 
6
7
.
0
0
0
0
0
0
 
 
 
 
 
 
3
7
.
0
0
0
0
0
0
 
 
 
 
 
 
6
2
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
0
 
 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
 
 
 
 
 
 
f
e
a
t
_
9
2
 
 
 
 
 
 
 
 
f
e
a
t
_
9
3
 
 

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
8
1
3
5
3
3
 
 
 
 
 
 
 
0
.
2
6
9
2
9
5
 
 
 
 
 
 
 
0
.
3
8
5
8
7
9
 
 
 
 
 
 
 
0
.
1
3
0
7
1
3
 
 

s
t
d
 
 
 
 
 
 
 
 
 
4
.
6
0
1
8
8
8
 
 
 
 
 
 
 
2
.
0
6
5
2
6
9
 
 
 
 
 
 
 
0
.
9
9
9
6
3
7
 
 
 
 
 
 
 
1
.
2
7
3
2
4
2
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
 
1
3
0
.
0
0
0
0
0
0
 
 
 
 
 
 
7
4
.
0
0
0
0
0
0
 
 
 
 
 
 
2
2
.
0
0
0
0
0
0
 
 
 
 
 
 
9
1
.
0
0
0
0
0
0
 
 


[
8
 
r
o
w
s
 
x
 
9
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
*
M
i
n
M
a
x
S
c
a
l
e
r
*




데
이
터
값
을
 
0
과
 
1
사
이
의
 
범
위
 
값
으
로
 
변
환
합
니
다
.
(
음
수
 
값
이
 
있
으
면
 
-
1
에
서
 
1
값
으
로
 
변
환
합
니
다
.
)




데
이
터
의
 
분
포
가
 
가
우
시
안
 
분
포
가
 
아
닐
 
경
우
에
 
M
i
n
,
 
M
a
x
 
S
c
a
l
e
을
 
적
용
해
 
볼
 
수
 
있
습
니
다
.




모
든
 
피
처
에
 
0
에
서
 
1
 
사
이
의
 
값
으
로
 
변
환
되
는
 
스
케
일
링
이
 
적
용
됩
니
다
.




변
숫
값
이
 
취
하
는
 
범
위
를
 
특
정
 
구
간
 
(
보
통
 
0
에
서
 
1
 
사
이
 
구
간
)
으
로
 
변
환
하
는
 
최
소
-
최
대
 
스
케
일
링
(
m
i
n
-
m
a
x
 
s
c
a
l
i
n
g
)
방
법
.




(
X
-
X
m
i
n
)
/
(
X
m
a
x
-
X
m
i
n
)
으
로
 
표
현
됩
니
다
.




변
환
 
후
의
 
평
균
이
 
정
확
히
 
0
이
 
되
지
 
않
고
 
이
상
치
의
 
악
영
향
을
 
받
기
 
더
 
쉽
다
는
 
단
점
이
 
있
으
므
로
 
표
준
화
 
방
법
이
 
더
 
자
주
 
쓰
입
니
다
.




한
편
 
이
미
지
 
데
이
터
의
 
각
 
픽
셀
값
 
등
은
 
처
음
부
터
 
0
~
2
5
5
로
 
범
위
가
 
정
해
진
 
변
수
이
므
로
 
최
소
-
최
대
 
스
케
일
링
을
 
이
용
하
는
 
게
 
자
연
스
러
울
 
수
 
있
습
니
다
.





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
 
i
m
p
o
r
t
 
M
i
n
M
a
x
S
c
a
l
e
r

m
m
s
=
M
i
n
M
a
x
S
c
a
l
e
r
(
)

a
l
l
d
a
t
a
3
=
m
m
s
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
a
l
l
d
a
t
a
2
)

a
l
l
d
a
t
a
3
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
a
l
l
d
a
t
a
3
,
c
o
l
u
m
n
s
=
a
l
l
d
a
t
a
2
.
c
o
l
u
m
n
s
)

a
l
l
d
a
t
a
3
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
 
 
 
 
 
 
 
f
e
a
t
_
2
 
 
 
 
 
 
 
 
 
f
e
a
t
_
3
 
 
 
 
 
 
 
 
 
f
e
a
t
_
4
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
0
6
0
3
7
 
 
 
 
 
 
 
0
.
0
0
5
1
6
5
 
 
 
 
 
 
 
0
.
0
1
0
7
1
8
 
 
 
 
 
 
 
0
.
0
0
9
5
1
5
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
0
2
3
2
1
9
 
 
 
 
 
 
 
0
.
0
2
4
6
8
6
 
 
 
 
 
 
 
0
.
0
3
5
0
5
7
 
 
 
 
 
 
 
0
.
0
3
4
4
9
8
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
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
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
5
 
 
 
 
 
 
 
 
 
f
e
a
t
_
6
 
 
 
 
 
 
 
 
 
f
e
a
t
_
7
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
0
3
7
5
6
 
 
 
 
 
 
 
0
.
0
0
2
3
8
3
 
 
 
 
 
 
 
0
.
0
0
4
5
0
5
 
 
 
 
 
 
 
0
.
0
0
6
6
5
9
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
0
2
2
7
2
1
 
 
 
 
 
 
 
0
.
0
2
0
4
1
1
 
 
 
 
 
 
 
0
.
0
2
4
0
3
7
 
 
 
 
 
 
 
0
.
0
2
2
7
7
6
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
1
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
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
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
 
 
 
 
 
 
f
e
a
t
_
1
0
 
 
.
.
.
 
 
 
 
 
 
 
 
f
e
a
t
_
8
4
 
 
 
 
 
 
 
 
f
e
a
t
_
8
5
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
.
.
.
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
2
1
8
7
4
 
 
 
 
 
 
 
0
.
0
0
4
5
3
1
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
5
5
8
 
 
 
 
 
 
 
0
.
0
0
9
5
8
3
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
0
7
5
0
3
5
 
 
 
 
 
 
 
0
.
0
1
9
6
1
2
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
9
4
6
2
 
 
 
 
 
 
 
0
.
0
3
4
0
0
7
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
.
.
.
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
6
 
 
 
 
 
 
 
 
f
e
a
t
_
8
7
 
 
 
 
 
 
 
 
f
e
a
t
_
8
8
 
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
\

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
1
5
4
6
2
 
 
 
 
 
 
 
0
.
0
0
5
9
9
6
 
 
 
 
 
 
 
0
.
0
2
3
6
5
8
 
 
 
 
 
 
 
0
.
0
0
7
5
5
9
 
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
0
3
6
7
4
3
 
 
 
 
 
 
 
0
.
0
2
4
1
0
4
 
 
 
 
 
 
 
0
.
0
5
6
6
9
9
 
 
 
 
 
 
 
0
.
0
2
5
6
6
6
 
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
1
3
6
9
9
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
2
7
0
2
7
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
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
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
0
 
 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
 
 
 
 
 
 
f
e
a
t
_
9
2
 
 
 
 
 
 
 
 
f
e
a
t
_
9
3
 
 

c
o
u
n
t
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 
2
0
6
2
4
6
.
0
0
0
0
0
0
 
 

m
e
a
n
 
 
 
 
 
 
 
 
0
.
0
0
6
2
5
8
 
 
 
 
 
 
 
0
.
0
0
3
6
3
9
 
 
 
 
 
 
 
0
.
0
1
7
5
4
0
 
 
 
 
 
 
 
0
.
0
0
1
4
3
6
 
 

s
t
d
 
 
 
 
 
 
 
 
 
0
.
0
3
5
3
9
9
 
 
 
 
 
 
 
0
.
0
2
7
9
0
9
 
 
 
 
 
 
 
0
.
0
4
5
4
3
8
 
 
 
 
 
 
 
0
.
0
1
3
9
9
2
 
 

m
i
n
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

2
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

5
0
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

7
5
%
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

m
a
x
 
 
 
 
 
 
 
 
 
1
.
0
0
0
0
0
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
.
0
0
0
0
0
0
 
 
 
 
 
 
 
1
.
0
0
0
0
0
0
 
 


[
8
 
r
o
w
s
 
x
 
9
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
*
b
o
x
-
c
o
x
 
변
환
,
 
y
e
o
-
j
o
h
n
s
o
n
 
변
환
*




표
준
화
와
 
최
소
-
최
대
 
스
케
일
링
은
 
선
형
 
변
환
이
므
로
 
변
수
의
 
분
포
가
 
유
동
적
일
 
뿐
 
형
태
 
그
 
자
체
는
 
변
하
지
 
않
습
니
다
.




한
편
으
로
는
 
비
선
형
변
환
(
n
o
n
l
i
n
e
a
r
 
t
r
a
n
s
f
o
r
m
a
t
i
o
n
)
을
 
통
해
 
변
수
의
 
분
포
 
형
태
를
 
바
꾸
는
 
편
이
 
바
람
직
한
 
경
우
도
 
있
습
니
다
.




변
수
의
 
분
포
는
 
보
통
 
어
느
 
한
 
쪽
으
로
 
지
나
치
게
 
치
우
치
지
 
않
는
 
게
 
좋
습
니
다
.




b
o
x
-
c
o
x
변
환
은
 
로
그
 
변
환
을
 
일
반
화
한
 
것
으
로
 
변
환
 
매
개
변
수
 
람
다
=
0
일
 
때
가
 
로
그
변
환




y
e
o
-
j
o
h
n
s
o
n
 
변
환
은
 
음
의
 
값
을
 
갖
는
 
변
수
에
도
 
적
용
할
 
수
 
있
습
니
다
.




변
환
에
 
사
용
하
는
 
매
개
변
수
는
 
되
도
록
 
정
규
 
분
포
 
(
n
o
r
m
a
l
 
d
i
s
t
r
i
b
u
t
i
o
n
)
에
 
근
접
하
도
록
 
라
이
브
러
리
 
측
에
서
 
최
적
의
 
값
을
 
추
정
해
줄
 
때
가
 
많
은
 
만
큼
 
반
드
시
 
명
시
적
으
로
 
지
정
할
 
필
요
는
 
없
습
니
다
.



```python
#
 
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
 
i
m
p
o
r
t
 
P
o
w
e
r
T
r
a
n
s
f
o
r
m
e
r

#
 
p
t
=
P
o
w
e
r
T
r
a
n
s
f
o
r
m
e
r
(
m
e
t
h
o
d
=
'
b
o
x
-
c
o
x
'
)

#
 
a
l
l
d
a
t
a
3
=
p
t
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
a
l
l
d
a
t
a
2
)

#
 
a
l
l
d
a
t
a
3
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
a
l
l
d
a
t
a
3
,
c
o
l
u
m
n
s
=
a
l
l
d
a
t
a
2
.
c
o
l
u
m
n
s
)

#
 
a
l
l
d
a
t
a
3
```

V
a
l
u
e
E
r
r
o
r
:
 
T
h
e
 
B
o
x
-
C
o
x
 
t
r
a
n
s
f
o
r
m
a
t
i
o
n
 
c
a
n
 
o
n
l
y
 
b
e
 
a
p
p
l
i
e
d
 
t
o
 
s
t
r
i
c
t
l
y
 
p
o
s
i
t
i
v
e
 
d
a
t
a




d
a
t
a
에
 
음
수
가
 
포
함
되
어
 
있
어
 
적
용
이
 
어
렵
습
니
다
.



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
 
i
m
p
o
r
t
 
P
o
w
e
r
T
r
a
n
s
f
o
r
m
e
r

p
t
=
P
o
w
e
r
T
r
a
n
s
f
o
r
m
e
r
(
m
e
t
h
o
d
=
'
y
e
o
-
j
o
h
n
s
o
n
'
)

a
l
l
d
a
t
a
3
=
p
t
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
a
l
l
d
a
t
a
2
)

a
l
l
d
a
t
a
3
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
a
l
l
d
a
t
a
3
,
c
o
l
u
m
n
s
=
a
l
l
d
a
t
a
2
.
c
o
l
u
m
n
s
)

a
l
l
d
a
t
a
3
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
 
 
 
 
 
 
f
e
a
t
_
2
 
 
 
 
 
 
 
 
f
e
a
t
_
3
 
 
 
 
 
 
 
 
f
e
a
t
_
4
 
 
 
 
 
 
 
 
f
e
a
t
_
5
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
-
3
.
6
6
3
9
1
6
e
-
1
5
 
-
2
.
1
9
1
9
3
8
e
-
1
4
 
-
3
.
8
3
1
6
6
4
e
-
1
5
 
 
2
.
2
3
8
9
9
4
e
-
1
4
 
 
1
.
5
7
9
2
0
0
e
-
1
4
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
4
.
5
1
2
3
1
7
e
-
0
1
 
-
3
.
5
3
1
0
8
4
e
-
0
1
 
-
5
.
0
5
6
7
0
4
e
-
0
1
 
-
5
.
2
6
0
2
3
9
e
-
0
1
 
-
2
.
2
5
6
0
4
8
e
-
0
1
 
 
 

2
5
%
 
 
 
-
4
.
5
1
2
3
1
7
e
-
0
1
 
-
3
.
5
3
1
0
8
4
e
-
0
1
 
-
5
.
0
5
6
7
0
4
e
-
0
1
 
-
5
.
2
6
0
2
3
9
e
-
0
1
 
-
2
.
2
5
6
0
4
8
e
-
0
1
 
 
 

5
0
%
 
 
 
-
4
.
5
1
2
3
1
7
e
-
0
1
 
-
3
.
5
3
1
0
8
4
e
-
0
1
 
-
5
.
0
5
6
7
0
4
e
-
0
1
 
-
5
.
2
6
0
2
3
9
e
-
0
1
 
-
2
.
2
5
6
0
4
8
e
-
0
1
 
 
 

7
5
%
 
 
 
-
4
.
5
1
2
3
1
7
e
-
0
1
 
-
3
.
5
3
1
0
8
4
e
-
0
1
 
-
5
.
0
5
6
7
0
4
e
-
0
1
 
-
5
.
2
6
0
2
3
9
e
-
0
1
 
-
2
.
2
5
6
0
4
8
e
-
0
1
 
 
 

m
a
x
 
 
 
 
2
.
2
5
2
5
5
7
e
+
0
0
 
 
2
.
8
3
6
6
5
1
e
+
0
0
 
 
2
.
1
1
3
9
1
1
e
+
0
0
 
 
2
.
0
3
4
5
6
9
e
+
0
0
 
 
4
.
4
3
2
5
2
9
e
+
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
6
 
 
 
 
 
 
 
 
f
e
a
t
_
7
 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
 
 
 
 
 
f
e
a
t
_
1
0
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
-
3
.
5
1
7
8
9
9
e
-
1
5
 
-
1
.
1
6
7
3
0
6
e
-
1
4
 
 
2
.
3
4
2
5
1
0
e
-
1
4
 
-
4
.
6
1
6
8
5
4
e
-
1
5
 
-
1
.
6
9
3
5
2
8
e
-
1
4
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
1
.
3
8
5
0
3
6
e
-
0
1
 
-
3
.
1
3
5
1
5
0
e
-
0
1
 
-
6
.
0
3
8
3
9
7
e
-
0
1
 
-
4
.
9
3
1
4
2
2
e
-
0
1
 
-
3
.
7
7
1
1
9
1
e
-
0
1
 
 
 

2
5
%
 
 
 
-
1
.
3
8
5
0
3
6
e
-
0
1
 
-
3
.
1
3
5
1
5
0
e
-
0
1
 
-
6
.
0
3
8
3
9
7
e
-
0
1
 
-
4
.
9
3
1
4
2
2
e
-
0
1
 
-
3
.
7
7
1
1
9
1
e
-
0
1
 
 
 

5
0
%
 
 
 
-
1
.
3
8
5
0
3
6
e
-
0
1
 
-
3
.
1
3
5
1
5
0
e
-
0
1
 
-
6
.
0
3
8
3
9
7
e
-
0
1
 
-
4
.
9
3
1
4
2
2
e
-
0
1
 
-
3
.
7
7
1
1
9
1
e
-
0
1
 
 
 

7
5
%
 
 
 
-
1
.
3
8
5
0
3
6
e
-
0
1
 
-
3
.
1
3
5
1
5
0
e
-
0
1
 
 
1
.
5
2
7
0
3
5
e
+
0
0
 
-
4
.
9
3
1
4
2
2
e
-
0
1
 
-
3
.
7
7
1
1
9
1
e
-
0
1
 
 
 

m
a
x
 
 
 
 
7
.
2
2
0
0
2
8
e
+
0
0
 
 
3
.
1
9
0
5
9
1
e
+
0
0
 
 
1
.
8
6
4
5
8
6
e
+
0
0
 
 
2
.
1
7
6
2
5
3
e
+
0
0
 
 
2
.
6
5
9
1
1
9
e
+
0
0
 
 
 


 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
f
e
a
t
_
8
4
 
 
 
 
 
 
 
f
e
a
t
_
8
5
 
 
 
 
 
 
 
f
e
a
t
_
8
6
 
 
 
 
 
 
 
f
e
a
t
_
8
7
 
 
\

c
o
u
n
t
 
 
.
.
.
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
 
.
.
.
 
 
1
.
1
4
4
3
0
8
e
-
1
4
 
 
7
.
8
0
0
8
2
4
e
-
1
5
 
 
2
.
0
9
9
0
0
1
e
-
1
4
 
 
1
.
6
0
7
1
2
6
e
-
1
4
 
 
 

s
t
d
 
 
 
 
.
.
.
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
 
.
.
.
 
-
1
.
5
4
7
8
9
8
e
-
0
1
 
-
5
.
1
6
8
4
5
8
e
-
0
1
 
-
8
.
1
2
9
7
2
7
e
-
0
1
 
-
4
.
9
4
1
9
6
9
e
-
0
1
 
 
 

2
5
%
 
 
 
 
.
.
.
 
-
1
.
5
4
7
8
9
8
e
-
0
1
 
-
5
.
1
6
8
4
5
8
e
-
0
1
 
-
8
.
1
2
9
7
2
7
e
-
0
1
 
-
4
.
9
4
1
9
6
9
e
-
0
1
 
 
 

5
0
%
 
 
 
 
.
.
.
 
-
1
.
5
4
7
8
9
8
e
-
0
1
 
-
5
.
1
6
8
4
5
8
e
-
0
1
 
-
8
.
1
2
9
7
2
7
e
-
0
1
 
-
4
.
9
4
1
9
6
9
e
-
0
1
 
 
 

7
5
%
 
 
 
 
.
.
.
 
-
1
.
5
4
7
8
9
8
e
-
0
1
 
-
5
.
1
6
8
4
5
8
e
-
0
1
 
 
8
.
2
5
2
7
8
7
e
-
0
1
 
-
4
.
9
4
1
9
6
9
e
-
0
1
 
 
 

m
a
x
 
 
 
 
.
.
.
 
 
6
.
4
6
0
3
7
4
e
+
0
0
 
 
2
.
0
3
0
3
0
8
e
+
0
0
 
 
1
.
9
0
3
2
6
2
e
+
0
0
 
 
2
.
0
7
9
8
5
3
e
+
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
8
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
 
 
 
 
 
f
e
a
t
_
9
0
 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
 
 
 
 
 
f
e
a
t
_
9
2
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
-
8
.
1
2
1
5
7
1
e
-
1
5
 
-
1
.
9
6
4
0
7
7
e
-
1
4
 
 
2
.
7
6
3
0
4
1
e
-
1
4
 
-
2
.
0
8
6
1
1
3
e
-
1
4
 
-
1
.
9
6
7
1
9
3
e
-
1
5
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
6
.
8
8
6
6
2
8
e
-
0
1
 
-
5
.
3
2
2
8
7
1
e
-
0
1
 
-
3
.
9
6
2
9
1
9
e
-
0
1
 
-
2
.
9
2
7
5
4
6
e
-
0
1
 
-
5
.
3
2
3
2
2
0
e
-
0
1
 
 
 

2
5
%
 
 
 
-
6
.
8
8
6
6
2
8
e
-
0
1
 
-
5
.
3
2
2
8
7
1
e
-
0
1
 
-
3
.
9
6
2
9
1
9
e
-
0
1
 
-
2
.
9
2
7
5
4
6
e
-
0
1
 
-
5
.
3
2
3
2
2
0
e
-
0
1
 
 
 

5
0
%
 
 
 
-
6
.
8
8
6
6
2
8
e
-
0
1
 
-
5
.
3
2
2
8
7
1
e
-
0
1
 
-
3
.
9
6
2
9
1
9
e
-
0
1
 
-
2
.
9
2
7
5
4
6
e
-
0
1
 
-
5
.
3
2
3
2
2
0
e
-
0
1
 
 
 

7
5
%
 
 
 
 
1
.
1
8
6
3
2
8
e
+
0
0
 
-
5
.
3
2
2
8
7
1
e
-
0
1
 
-
3
.
9
6
2
9
1
9
e
-
0
1
 
-
2
.
9
2
7
5
4
6
e
-
0
1
 
-
5
.
3
2
3
2
2
0
e
-
0
1
 
 
 

m
a
x
 
 
 
 
1
.
8
1
9
6
9
3
e
+
0
0
 
 
1
.
9
7
2
4
3
9
e
+
0
0
 
 
2
.
5
6
4
6
4
2
e
+
0
0
 
 
3
.
4
1
6
5
5
2
e
+
0
0
 
 
1
.
9
5
7
7
3
6
e
+
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
3
 
 

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 

m
e
a
n
 
 
 
2
.
7
3
4
7
6
6
e
-
1
4
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 

m
i
n
 
 
 
-
2
.
5
4
5
4
3
2
e
-
0
1
 
 

2
5
%
 
 
 
-
2
.
5
4
5
4
3
2
e
-
0
1
 
 

5
0
%
 
 
 
-
2
.
5
4
5
4
3
2
e
-
0
1
 
 

7
5
%
 
 
 
-
2
.
5
4
5
4
3
2
e
-
0
1
 
 

m
a
x
 
 
 
 
3
.
9
2
8
6
1
9
e
+
0
0
 
 


[
8
 
r
o
w
s
 
x
 
9
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
*
S
t
a
n
d
a
r
d
S
c
a
l
e
r
*




S
t
a
n
d
a
r
d
S
c
a
l
e
r
는
 
표
준
화
를
 
쉽
게
 
지
원
하
기
 
위
한
 
클
래
스
입
니
다
.




즉
,
 
개
별
 
피
처
를
 
평
균
이
 
0
이
고
,
 
분
산
이
 
1
인
 
값
으
로
 
변
환
해
줍
니
다
.




이
렇
게
 
가
우
시
안
 
정
규
 
분
포
를
 
가
질
 
수
 
있
도
록
 
데
이
터
를
 
변
환
하
는
 
것
은
 
몇
몇
 
알
고
리
즘
에
서
 
매
우
 
중
요
합
니
다
.




특
히
 
사
이
킷
런
에
서
 
구
현
한
 
R
B
F
 
커
널
을
 
이
용
하
는
 
서
포
트
 
벡
터
 
머
신
(
S
u
p
p
o
r
t
 
V
e
c
t
o
r
 
M
a
c
h
i
n
e
)
이
나
 
선
형
 
회
귀
(
L
i
n
e
a
r
 
R
e
g
r
e
s
s
i
o
n
)
,
 
로
지
스
틱
 
회
귀
(
L
o
g
i
s
t
i
c
 
R
e
g
r
e
s
s
i
o
n
)
는
 
데
이
터
가
 
가
우
시
안
 
분
포
를
 
가
지
고
 
있
다
고
 
가
정
하
고
 
구
현
됐
기
 
때
문
에
 
사
전
에
 
표
준
화
를
 
적
용
하
는
 
것
은
 
예
측
 
성
능
 
향
상
에
 
중
요
한
 
요
소
가
 
될
 
수
 
있
습
니
다
.




모
든
 
칼
럼
 
값
의
 
평
균
이
 
0
에
 
아
주
 
가
까
운
 
값
으
로
,
 
그
리
고
 
분
산
은
 
1
에
 
아
주
 
가
까
운
 
값
으
로
 
변
환
됩
니
다
.




가
장
 
기
본
적
인
 
변
환
 
방
법
은
 
곱
셈
과
 
덧
셈
만
으
로
 
변
환
하
는
 
선
형
변
환
(
l
i
n
e
a
r
 
t
r
a
n
s
f
o
r
m
a
t
i
o
n
)
으
로
 
변
숫
값
의
 
범
위
를
 
변
경
하
는
 
것
입
니
다
.




선
형
변
환
을
 
통
해
 
변
수
의
 
평
균
을
 
0
,
 
표
준
편
차
를
 
1
로
 
만
드
는
 
방
법
을
 
표
준
화
라
고
 
합
니
다
.




수
식
은
 
(
x
-
평
균
)
/
표
준
편
차
으
로
 
표
현
됩
니
다
.




선
형
 
회
귀
나
 
로
지
스
틱
 
회
귀
 
등
의
 
선
형
 
모
델
에
서
는
 
값
의
 
범
위
가
 
큰
 
변
수
일
수
록
 
회
귀
 
계
수
(
r
e
g
r
e
s
s
i
o
n
 
c
o
e
f
f
i
c
i
e
n
t
)
가
 
작
아
지
므
로
,
 
표
준
화
하
지
 
않
으
면
 
그
러
한
 
변
수
의
 
정
규
화
(
r
e
g
u
l
a
r
i
z
a
t
i
o
n
)
가
 
어
려
워
집
니
다
.




신
경
망
에
서
도
 
변
수
들
 
간
의
 
값
의
 
범
위
가
 
크
게
 
차
이
나
는
 
상
태
로
는
 
학
습
이
 
잘
 
진
행
되
지
 
않
을
 
때
가
 
많
습
니
다
.




또
한
 
평
균
은
 
0
에
서
 
크
게
 
벗
어
나
지
 
않
는
 
게
 
좋
습
니
다
.




또
한
 
0
 
또
는
 
1
의
 
두
 
값
으
로
 
나
타
나
는
 
변
수
는
 
0
과
 
1
의
 
비
율
이
 
어
느
 
한
 
쪽
으
로
 
치
우
치
면
 
표
준
편
차
가
 
작
으
므
로
,
 
변
환
한
 
뒤
에
 
0
 
또
는
 
1
 
중
에
 
어
느
 
한
 
쪽
의
 
절
댓
값
이
 
커
질
 
가
능
성
이
 
있
습
니
다
.
 
이
들
 
두
 
값
을
 
갖
는
 
이
진
 
변
수
에
 
대
해
서
는
 
표
준
화
를
 
실
시
하
지
 
않
아
도
 
됩
니
다
.



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
 
i
m
p
o
r
t
 
S
t
a
n
d
a
r
d
S
c
a
l
e
r

s
s
=
S
t
a
n
d
a
r
d
S
c
a
l
e
r
(
)

a
l
l
d
a
t
a
3
=
s
s
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
a
l
l
d
a
t
a
2
)

a
l
l
d
a
t
a
3
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
a
l
l
d
a
t
a
3
,
c
o
l
u
m
n
s
=
a
l
l
d
a
t
a
2
.
c
o
l
u
m
n
s
)

a
l
l
d
a
t
a
3
.
d
e
s
c
r
i
b
e
(
)
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
1
 
 
 
 
 
 
 
 
f
e
a
t
_
2
 
 
 
 
 
 
 
 
f
e
a
t
_
3
 
 
 
 
 
 
 
 
f
e
a
t
_
4
 
 
 
 
 
 
 
 
f
e
a
t
_
5
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
 
4
.
0
9
9
4
9
4
e
-
1
5
 
-
1
.
9
6
4
5
9
6
e
-
1
4
 
-
8
.
6
8
8
2
8
2
e
-
1
5
 
-
1
.
4
5
0
6
0
2
e
-
1
4
 
-
4
.
4
2
4
3
0
2
e
-
1
5
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
2
.
5
9
9
8
3
3
e
-
0
1
 
-
2
.
0
9
2
5
0
4
e
-
0
1
 
-
3
.
0
5
7
2
8
6
e
-
0
1
 
-
2
.
7
5
8
1
3
9
e
-
0
1
 
-
1
.
6
5
3
0
6
0
e
-
0
1
 
 
 

2
5
%
 
 
 
-
2
.
5
9
9
8
3
3
e
-
0
1
 
-
2
.
0
9
2
5
0
4
e
-
0
1
 
-
3
.
0
5
7
2
8
6
e
-
0
1
 
-
2
.
7
5
8
1
3
9
e
-
0
1
 
-
1
.
6
5
3
0
6
0
e
-
0
1
 
 
 

5
0
%
 
 
 
-
2
.
5
9
9
8
3
3
e
-
0
1
 
-
2
.
0
9
2
5
0
4
e
-
0
1
 
-
3
.
0
5
7
2
8
6
e
-
0
1
 
-
2
.
7
5
8
1
3
9
e
-
0
1
 
-
1
.
6
5
3
0
6
0
e
-
0
1
 
 
 

7
5
%
 
 
 
-
2
.
5
9
9
8
3
3
e
-
0
1
 
-
2
.
0
9
2
5
0
4
e
-
0
1
 
-
3
.
0
5
7
2
8
6
e
-
0
1
 
-
2
.
7
5
8
1
3
9
e
-
0
1
 
-
1
.
6
5
3
0
6
0
e
-
0
1
 
 
 

m
a
x
 
 
 
 
4
.
2
8
0
7
6
3
e
+
0
1
 
 
4
.
0
3
0
0
3
9
e
+
0
1
 
 
2
.
8
2
1
9
0
1
e
+
0
1
 
 
2
.
8
7
1
1
3
4
e
+
0
1
 
 
4
.
3
8
4
7
4
9
e
+
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
6
 
 
 
 
 
 
 
 
f
e
a
t
_
7
 
 
 
 
 
 
 
 
f
e
a
t
_
8
 
 
 
 
 
 
 
 
f
e
a
t
_
9
 
 
 
 
 
 
 
f
e
a
t
_
1
0
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
-
2
.
6
9
9
6
7
9
e
-
1
5
 
 
2
.
9
8
4
7
0
1
e
-
1
5
 
-
4
.
5
0
0
3
7
2
e
-
1
4
 
-
1
.
5
9
0
1
4
8
e
-
1
4
 
 
1
.
6
0
0
1
9
7
e
-
1
4
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
1
.
1
6
7
6
2
8
e
-
0
1
 
-
1
.
8
7
4
2
5
1
e
-
0
1
 
-
2
.
9
2
3
7
3
4
e
-
0
1
 
-
2
.
9
1
5
1
7
8
e
-
0
1
 
-
2
.
3
1
0
1
8
7
e
-
0
1
 
 
 

2
5
%
 
 
 
-
1
.
1
6
7
6
2
8
e
-
0
1
 
-
1
.
8
7
4
2
5
1
e
-
0
1
 
-
2
.
9
2
3
7
3
4
e
-
0
1
 
-
2
.
9
1
5
1
7
8
e
-
0
1
 
-
2
.
3
1
0
1
8
7
e
-
0
1
 
 
 

5
0
%
 
 
 
-
1
.
1
6
7
6
2
8
e
-
0
1
 
-
1
.
8
7
4
2
5
1
e
-
0
1
 
-
2
.
9
2
3
7
3
4
e
-
0
1
 
-
2
.
9
1
5
1
7
8
e
-
0
1
 
-
2
.
3
1
0
1
8
7
e
-
0
1
 
 
 

7
5
%
 
 
 
-
1
.
1
6
7
6
2
8
e
-
0
1
 
-
1
.
8
7
4
2
5
1
e
-
0
1
 
 
1
.
4
6
6
9
5
5
e
-
0
1
 
-
2
.
9
1
5
1
7
8
e
-
0
1
 
-
2
.
3
1
0
1
8
7
e
-
0
1
 
 
 

m
a
x
 
 
 
 
4
.
8
8
7
5
3
6
e
+
0
1
 
 
4
.
1
4
1
4
4
2
e
+
0
1
 
 
4
.
3
6
1
4
5
1
e
+
0
1
 
 
1
.
3
0
3
5
6
2
e
+
0
1
 
 
5
.
0
7
5
7
5
7
e
+
0
1
 
 
 


 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
f
e
a
t
_
8
4
 
 
 
 
 
 
 
f
e
a
t
_
8
5
 
 
 
 
 
 
 
f
e
a
t
_
8
6
 
 
 
 
 
 
 
f
e
a
t
_
8
7
 
 
\

c
o
u
n
t
 
 
.
.
.
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
 
.
.
.
 
 
2
.
3
9
0
0
3
8
e
-
1
6
 
 
3
.
7
8
9
9
5
1
e
-
1
5
 
-
7
.
8
2
7
1
4
4
e
-
1
5
 
 
2
.
0
7
2
0
6
2
e
-
1
4
 
 
 

s
t
d
 
 
 
 
.
.
.
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
 
.
.
.
 
-
5
.
9
0
2
0
0
6
e
-
0
2
 
-
2
.
8
1
7
8
3
3
e
-
0
1
 
-
4
.
2
0
8
1
7
0
e
-
0
1
 
-
2
.
4
8
7
6
4
3
e
-
0
1
 
 
 

2
5
%
 
 
 
 
.
.
.
 
-
5
.
9
0
2
0
0
6
e
-
0
2
 
-
2
.
8
1
7
8
3
3
e
-
0
1
 
-
4
.
2
0
8
1
7
0
e
-
0
1
 
-
2
.
4
8
7
6
4
3
e
-
0
1
 
 
 

5
0
%
 
 
 
 
.
.
.
 
-
5
.
9
0
2
0
0
6
e
-
0
2
 
-
2
.
8
1
7
8
3
3
e
-
0
1
 
-
4
.
2
0
8
1
7
0
e
-
0
1
 
-
2
.
4
8
7
6
4
3
e
-
0
1
 
 
 

7
5
%
 
 
 
 
.
.
.
 
-
5
.
9
0
2
0
0
6
e
-
0
2
 
-
2
.
8
1
7
8
3
3
e
-
0
1
 
-
4
.
7
9
9
0
2
8
e
-
0
2
 
-
2
.
4
8
7
6
4
3
e
-
0
1
 
 
 

m
a
x
 
 
 
 
.
.
.
 
 
1
.
0
5
6
2
3
0
e
+
0
2
 
 
2
.
9
1
2
3
6
4
e
+
0
1
 
 
2
.
6
7
9
5
5
3
e
+
0
1
 
 
4
.
1
2
3
8
9
2
e
+
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
8
8
 
 
 
 
 
 
 
f
e
a
t
_
8
9
 
 
 
 
 
 
 
f
e
a
t
_
9
0
 
 
 
 
 
 
 
f
e
a
t
_
9
1
 
 
 
 
 
 
 
f
e
a
t
_
9
2
 
 
\

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 
 

m
e
a
n
 
 
 
1
.
7
4
5
0
8
9
e
-
1
4
 
-
1
.
7
2
0
5
5
2
e
-
1
4
 
-
2
.
3
6
5
8
2
6
e
-
1
4
 
 
1
.
1
8
1
2
9
5
e
-
1
4
 
-
2
.
8
0
1
9
3
6
e
-
1
4
 
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 
 

m
i
n
 
 
 
-
4
.
1
7
2
5
4
5
e
-
0
1
 
-
2
.
9
4
5
0
2
5
e
-
0
1
 
-
1
.
7
6
7
8
3
0
e
-
0
1
 
-
1
.
3
0
3
9
2
5
e
-
0
1
 
-
3
.
8
6
0
1
9
9
e
-
0
1
 
 
 

2
5
%
 
 
 
-
4
.
1
7
2
5
4
5
e
-
0
1
 
-
2
.
9
4
5
0
2
5
e
-
0
1
 
-
1
.
7
6
7
8
3
0
e
-
0
1
 
-
1
.
3
0
3
9
2
5
e
-
0
1
 
-
3
.
8
6
0
1
9
9
e
-
0
1
 
 
 

5
0
%
 
 
 
-
4
.
1
7
2
5
4
5
e
-
0
1
 
-
2
.
9
4
5
0
2
5
e
-
0
1
 
-
1
.
7
6
7
8
3
0
e
-
0
1
 
-
1
.
3
0
3
9
2
5
e
-
0
1
 
-
3
.
8
6
0
1
9
9
e
-
0
1
 
 
 

7
5
%
 
 
 
 
5
.
9
4
2
0
9
1
e
-
0
2
 
-
2
.
9
4
5
0
2
5
e
-
0
1
 
-
1
.
7
6
7
8
3
0
e
-
0
1
 
-
1
.
3
0
3
9
2
5
e
-
0
1
 
-
3
.
8
6
0
1
9
9
e
-
0
1
 
 
 

m
a
x
 
 
 
 
1
.
7
2
1
9
7
4
e
+
0
1
 
 
3
.
8
6
6
8
3
6
e
+
0
1
 
 
2
.
8
0
7
2
5
6
e
+
0
1
 
 
3
.
5
7
0
0
3
8
e
+
0
1
 
 
2
.
1
6
2
2
0
1
e
+
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
_
9
3
 
 

c
o
u
n
t
 
 
2
.
0
6
2
4
6
0
e
+
0
5
 
 

m
e
a
n
 
 
 
7
.
1
8
7
3
9
9
e
-
1
6
 
 

s
t
d
 
 
 
 
1
.
0
0
0
0
0
2
e
+
0
0
 
 

m
i
n
 
 
 
-
1
.
0
2
6
6
1
7
e
-
0
1
 
 

2
5
%
 
 
 
-
1
.
0
2
6
6
1
7
e
-
0
1
 
 

5
0
%
 
 
 
-
1
.
0
2
6
6
1
7
e
-
0
1
 
 

7
5
%
 
 
 
-
1
.
0
2
6
6
1
7
e
-
0
1
 
 

m
a
x
 
 
 
 
7
.
1
3
6
8
6
0
e
+
0
1
 
 


[
8
 
r
o
w
s
 
x
 
9
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
2
=
a
l
l
d
a
t
a
3
[
:
l
e
n
(
t
r
a
i
n
)
]

t
e
s
t
2
=
a
l
l
d
a
t
a
3
[
l
e
n
(
t
r
a
i
n
)
:
]
```


```python
f
r
o
m
 
c
a
t
b
o
o
s
t
 
i
m
p
o
r
t
 
C
a
t
B
o
o
s
t
C
l
a
s
s
i
f
i
e
r

c
b
c
=
C
a
t
B
o
o
s
t
C
l
a
s
s
i
f
i
e
r
(
t
a
s
k
_
t
y
p
e
=
'
G
P
U
'
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
0
0
)

c
b
c
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
2
,
t
r
a
i
n
[
'
t
a
r
g
e
t
'
]
)

r
e
s
u
l
t
=
c
b
c
.
p
r
e
d
i
c
t
_
p
r
o
b
a
(
t
e
s
t
2
)
 
#
분
류
 
확
률
 
p
r
e
d
i
c
t
_
p
r
o
b
a
```

<pre>
L
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
 
s
e
t
 
t
o
 
0
.
1
5
0
5
7
6

0
:
	
l
e
a
r
n
:
 
1
.
8
2
3
7
5
8
0
	
t
o
t
a
l
:
 
5
9
.
9
m
s
	
r
e
m
a
i
n
i
n
g
:
 
5
9
.
9
s

1
0
0
:
	
l
e
a
r
n
:
 
0
.
5
9
5
1
0
5
9
	
t
o
t
a
l
:
 
1
.
9
5
s
	
r
e
m
a
i
n
i
n
g
:
 
1
7
.
3
s

2
0
0
:
	
l
e
a
r
n
:
 
0
.
5
1
8
8
0
7
9
	
t
o
t
a
l
:
 
3
.
3
6
s
	
r
e
m
a
i
n
i
n
g
:
 
1
3
.
4
s

3
0
0
:
	
l
e
a
r
n
:
 
0
.
4
8
8
1
2
6
7
	
t
o
t
a
l
:
 
4
.
5
2
s
	
r
e
m
a
i
n
i
n
g
:
 
1
0
.
5
s

4
0
0
:
	
l
e
a
r
n
:
 
0
.
4
6
0
4
9
3
5
	
t
o
t
a
l
:
 
5
.
6
6
s
	
r
e
m
a
i
n
i
n
g
:
 
8
.
4
5
s

5
0
0
:
	
l
e
a
r
n
:
 
0
.
4
4
0
4
3
2
4
	
t
o
t
a
l
:
 
6
.
7
2
s
	
r
e
m
a
i
n
i
n
g
:
 
6
.
7
s

6
0
0
:
	
l
e
a
r
n
:
 
0
.
4
2
1
7
8
0
9
	
t
o
t
a
l
:
 
7
.
7
9
s
	
r
e
m
a
i
n
i
n
g
:
 
5
.
1
7
s

7
0
0
:
	
l
e
a
r
n
:
 
0
.
4
0
5
4
7
1
7
	
t
o
t
a
l
:
 
8
.
8
7
s
	
r
e
m
a
i
n
i
n
g
:
 
3
.
7
8
s

8
0
0
:
	
l
e
a
r
n
:
 
0
.
3
9
0
1
9
6
5
	
t
o
t
a
l
:
 
9
.
9
6
s
	
r
e
m
a
i
n
i
n
g
:
 
2
.
4
7
s

9
0
0
:
	
l
e
a
r
n
:
 
0
.
3
7
6
8
8
1
1
	
t
o
t
a
l
:
 
1
1
.
1
s
	
r
e
m
a
i
n
i
n
g
:
 
1
.
2
1
s

9
9
9
:
	
l
e
a
r
n
:
 
0
.
3
6
3
9
2
9
1
	
t
o
t
a
l
:
 
1
2
.
1
s
	
r
e
m
a
i
n
i
n
g
:
 
0
u
s

</pre>

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
 
i
m
p
o
r
t
 
*

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
```


```python
t
r
a
i
n
[
'
t
a
r
g
e
t
'
]
.
n
u
n
i
q
u
e
(
)
```

<pre>
9
</pre>

```python
#
 
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
 
i
m
p
o
r
t
 
L
a
b
e
l
E
n
c
o
d
e
r

#
 
l
e
=
L
a
b
e
l
E
n
c
o
d
e
r
(
)

#
 
y
=
l
e
.
f
i
t
_
t
r
a
n
s
f
o
r
m
(
t
r
a
i
n
[
'
t
a
r
g
e
t
'
]
)

#
 
y
```


```python
#
 
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

#
 
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
,
 
y
_
t
r
a
i
n
,
 
y
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
2
,
y
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
y
)
```


```python
s
u
b
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
C
l
a
s
s
_
1
 
 
C
l
a
s
s
_
2
 
 
C
l
a
s
s
_
3
 
 
C
l
a
s
s
_
4
 
 
C
l
a
s
s
_
5
 
 
C
l
a
s
s
_
6
 
 
C
l
a
s
s
_
7
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

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
 
 
 
 
 
 
.
.
.
 
 
 

1
4
4
3
6
3
 
 
1
4
4
3
6
4
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
4
 
 
1
4
4
3
6
5
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
5
 
 
1
4
4
3
6
6
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
6
 
 
1
4
4
3
6
7
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 

1
4
4
3
6
7
 
 
1
4
4
3
6
8
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 


 
 
 
 
 
 
 
 
C
l
a
s
s
_
8
 
 
C
l
a
s
s
_
9
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

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
4
4
3
6
3
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
4
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
5
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
6
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 

1
4
4
3
6
7
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 


[
1
4
4
3
6
8
 
r
o
w
s
 
x
 
1
0
 
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
r
e
s
u
l
t
[
0
]
```

<pre>
a
r
r
a
y
(
[
1
.
1
0
8
4
8
7
6
0
e
-
0
4
,
 
1
.
3
7
4
8
5
2
2
5
e
-
0
1
,
 
4
.
3
0
8
5
0
9
0
4
e
-
0
1
,
 
4
.
2
3
3
8
1
8
0
4
e
-
0
1
,

 
 
 
 
 
 
 
1
.
1
7
5
7
4
3
1
7
e
-
0
6
,
 
7
.
0
9
5
4
3
7
4
9
e
-
0
5
,
 
8
.
0
7
6
6
4
1
2
1
e
-
0
3
,
 
1
.
6
2
0
6
6
1
6
8
e
-
0
5
,

 
 
 
 
 
 
 
6
.
2
4
0
8
2
3
8
0
e
-
0
6
]
)
</pre>

```python
s
u
b
.
i
l
o
c
[
:
,
1
:
]
=
r
e
s
u
l
t
```


```python
s
u
b
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
C
l
a
s
s
_
1
 
 
 
C
l
a
s
s
_
2
 
 
 
C
l
a
s
s
_
3
 
 
 
C
l
a
s
s
_
4
 
 
 
 
 
 
 
C
l
a
s
s
_
5
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
1
 
 
0
.
0
0
0
1
1
1
 
 
0
.
1
3
7
4
8
5
 
 
0
.
4
3
0
8
5
1
 
 
0
.
4
2
3
3
8
2
 
 
1
.
1
7
5
7
4
3
e
-
0
6
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
0
.
0
0
2
9
7
9
 
 
0
.
0
2
6
4
4
7
 
 
0
.
0
0
1
1
8
4
 
 
0
.
0
0
0
9
8
3
 
 
4
.
2
3
0
9
8
5
e
-
0
5
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
3
 
 
0
.
0
0
0
5
6
0
 
 
0
.
0
0
0
0
2
4
 
 
0
.
0
0
0
0
5
7
 
 
0
.
0
0
0
0
8
8
 
 
5
.
6
2
9
0
9
0
e
-
0
7
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
0
.
0
0
0
0
0
9
 
 
0
.
5
3
1
5
5
1
 
 
0
.
4
5
3
0
6
9
 
 
0
.
0
1
5
2
5
6
 
 
3
.
7
8
9
4
9
3
e
-
0
7
 
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
5
 
 
0
.
1
2
4
2
4
8
 
 
0
.
0
0
0
1
6
4
 
 
0
.
0
0
0
0
4
0
 
 
0
.
0
0
0
0
2
4
 
 
3
.
6
5
7
7
0
8
e
-
0
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
4
4
3
6
3
 
 
1
4
4
3
6
4
 
 
0
.
4
9
5
0
2
2
 
 
0
.
0
0
6
9
0
4
 
 
0
.
0
0
3
4
8
7
 
 
0
.
0
1
3
1
1
1
 
 
3
.
3
2
3
3
1
9
e
-
0
5
 
 
 

1
4
4
3
6
4
 
 
1
4
4
3
6
5
 
 
0
.
0
0
0
3
9
5
 
 
0
.
3
0
0
5
8
6
 
 
0
.
5
2
3
4
3
5
 
 
0
.
1
3
3
8
8
3
 
 
3
.
2
1
5
2
0
1
e
-
0
5
 
 
 

1
4
4
3
6
5
 
 
1
4
4
3
6
6
 
 
0
.
0
0
0
0
3
3
 
 
0
.
6
3
5
5
0
6
 
 
0
.
2
5
9
3
2
7
 
 
0
.
1
0
0
9
1
0
 
 
7
.
2
6
2
2
8
9
e
-
0
6
 
 
 

1
4
4
3
6
6
 
 
1
4
4
3
6
7
 
 
0
.
0
0
0
0
7
6
 
 
0
.
3
5
2
3
6
9
 
 
0
.
0
2
1
3
2
3
 
 
0
.
6
2
5
5
1
3
 
 
1
.
2
0
8
3
3
6
e
-
0
5
 
 
 

1
4
4
3
6
7
 
 
1
4
4
3
6
8
 
 
0
.
0
0
0
0
4
2
 
 
0
.
5
5
3
0
9
1
 
 
0
.
4
0
9
2
2
1
 
 
0
.
0
2
3
5
6
3
 
 
2
.
3
1
3
5
9
0
e
-
0
6
 
 
 


 
 
 
 
 
 
 
 
 
C
l
a
s
s
_
6
 
 
 
C
l
a
s
s
_
7
 
 
 
C
l
a
s
s
_
8
 
 
 
C
l
a
s
s
_
9
 
 

0
 
 
 
 
 
 
 
0
.
0
0
0
0
7
1
 
 
0
.
0
0
8
0
7
7
 
 
0
.
0
0
0
0
1
6
 
 
0
.
0
0
0
0
0
6
 
 

1
 
 
 
 
 
 
 
0
.
8
5
1
8
2
0
 
 
0
.
0
0
6
9
3
2
 
 
0
.
1
0
7
3
8
6
 
 
0
.
0
0
2
2
2
8
 
 

2
 
 
 
 
 
 
 
0
.
9
9
3
4
8
9
 
 
0
.
0
0
0
4
6
7
 
 
0
.
0
0
4
5
2
4
 
 
0
.
0
0
0
7
9
1
 
 

3
 
 
 
 
 
 
 
0
.
0
0
0
0
0
4
 
 
0
.
0
0
0
0
4
2
 
 
0
.
0
0
0
0
0
3
 
 
0
.
0
0
0
0
6
4
 
 

4
 
 
 
 
 
 
 
0
.
0
0
5
2
0
3
 
 
0
.
0
0
3
0
7
6
 
 
0
.
1
0
4
4
6
4
 
 
0
.
7
6
2
7
4
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
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.
 
 

1
4
4
3
6
3
 
 
0
.
3
6
4
6
7
8
 
 
0
.
0
6
0
2
1
2
 
 
0
.
0
2
0
7
8
0
 
 
0
.
0
3
5
7
7
2
 
 

1
4
4
3
6
4
 
 
0
.
0
0
0
2
2
7
 
 
0
.
0
4
1
4
1
5
 
 
0
.
0
0
0
0
2
1
 
 
0
.
0
0
0
0
0
7
 
 

1
4
4
3
6
5
 
 
0
.
0
0
0
1
2
8
 
 
0
.
0
0
4
0
4
0
 
 
0
.
0
0
0
0
3
0
 
 
0
.
0
0
0
0
1
7
 
 

1
4
4
3
6
6
 
 
0
.
0
0
0
0
1
2
 
 
0
.
0
0
0
6
8
6
 
 
0
.
0
0
0
0
0
6
 
 
0
.
0
0
0
0
0
3
 
 

1
4
4
3
6
7
 
 
0
.
0
0
0
2
4
8
 
 
0
.
0
1
3
8
0
7
 
 
0
.
0
0
0
0
2
1
 
 
0
.
0
0
0
0
0
5
 
 


[
1
4
4
3
6
8
 
r
o
w
s
 
x
 
1
0
 
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
9
0
8
c
8
d
7
0
-
a
7
3
6
-
4
6
5
a
-
b
5
b
a
-
2
3
3
8
4
5
c
a
9
c
a
8
.
p
n
g
)


a
l
l
d
a
t
a
의
 
각
 
f
e
a
t
 
c
o
l
u
m
n
n
의
 
d
a
t
a
는
 
0
에
 
가
까
운
 
값
이
 
가
장
 
많
습
니
다
.




m
a
x
값
이
 
9
1
인
 
경
우
도
 
있
으
나
 
0
인
 
경
우
가
 
1
5
0
0
0
0
배
로
 
압
도
적
입
니
다
.




따
라
서
 
데
이
터
 
분
석
에
 
앞
서
 
비
선
형
변
환
(
n
o
n
l
i
n
e
a
r
 
t
r
a
n
s
f
o
r
m
a
t
i
o
n
)
을
 
통
해
 
변
수
의
 
분
포
 
형
태
를
 
바
꾸
는
 
전
처
리
 
방
식
이
 
가
장
 
효
과
적
으
로
 
나
타
났
습
니
다
.
(
y
e
o
-
j
o
h
n
s
o
n
)




또
한
 
R
o
b
u
s
t
S
c
a
l
e
r
도
 
I
Q
R
[
1
분
위
(
2
5
분
위
)
와
 
3
분
위
(
7
5
분
위
)
 
사
이
의
 
범
위
]
 
외
의
 
값
을
 
o
u
t
l
i
e
r
로
 
처
리
함
으
로
써
 
가
장
 
많
은
 
경
우
의
 
수
만
 
반
영
하
여
 
전
처
리
함
으
로
써
 
정
확
도
에
 
기
여
하
였
습
니
다
.




S
t
a
n
d
a
r
d
S
c
a
l
e
r
에
 
비
해
 
M
i
n
M
a
x
S
c
a
l
e
r
의
 
전
처
리
가
 
더
 
효
과
적
이
었
던
 
이
유
는
,




a
l
l
d
a
t
a
의
 
각
 
f
e
a
t
 
c
o
l
u
m
n
n
의
 
d
a
t
a
는
 
0
에
 
가
까
운
 
값
이
 
압
도
적
으
로
 
많
아
 
그
대
로
 
정
규
화
하
게
 
되
면
 
부
정
확
하
게
 
전
처
리
 
될
 
가
능
성
이
 
높
기
 
때
문
으
로
 
보
입
니
다
.

