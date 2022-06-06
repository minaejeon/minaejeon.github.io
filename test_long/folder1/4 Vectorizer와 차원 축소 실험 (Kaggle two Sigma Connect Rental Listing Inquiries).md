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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
i
m
a
g
e
s
_
s
a
m
p
l
e
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
K
a
g
g
l
e
-
r
e
n
t
h
o
p
.
t
o
r
r
e
n
t

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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
t
e
s
t
.
j
s
o
n
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
t
r
a
i
n
.
j
s
o
n
.
z
i
p

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
j
s
o
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
t
r
a
i
n
.
j
s
o
n
.
z
i
p
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
j
s
o
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
/
t
e
s
t
.
j
s
o
n
.
z
i
p
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
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
)
```

<pre>
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
8
5
7
9
a
0
b
0
d
5
4
d
b
8
0
3
8
2
1
a
3
5
a
4
a
6
1
5
e
9
7
a
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
b
8
e
7
5
f
c
9
4
9
a
6
c
d
8
2
2
5
b
4
5
5
6
4
8
a
9
5
1
7
1
2
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
c
d
7
5
9
a
9
8
8
b
8
f
2
3
9
2
4
b
5
a
2
0
5
8
d
5
a
b
2
b
4
9
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
1
.
5
 
 
 
 
 
 
 
 
 
3
 
 
5
3
a
5
b
1
1
9
b
a
8
f
7
b
6
1
d
4
e
0
1
0
5
1
2
e
0
d
f
c
8
5
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
b
f
b
9
4
0
5
1
4
9
b
f
f
f
4
2
a
9
2
9
8
0
b
5
9
4
c
2
8
2
3
4
 
 
 

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
2
4
0
0
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
9
2
b
b
b
f
3
8
b
a
a
d
f
d
e
0
5
7
6
f
c
4
9
6
b
d
4
1
7
4
9
c
 
 
 

1
2
4
0
0
2
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
5
5
6
5
d
b
9
b
7
c
b
a
3
6
0
3
8
3
4
c
4
a
a
6
f
2
9
5
0
9
6
0
 
 
 

1
2
4
0
0
4
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
6
7
9
9
7
a
1
2
8
0
5
6
e
e
1
e
d
7
d
0
4
6
b
b
b
8
5
6
e
3
c
7
 
 
 

1
2
4
0
0
8
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
3
c
0
5
7
4
a
7
4
0
1
5
4
8
0
6
c
1
8
b
d
f
1
f
d
d
d
3
d
9
6
6
 
 
 

1
2
4
0
0
9
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
d
8
9
f
5
1
4
c
3
e
d
0
a
b
a
a
e
5
2
c
b
a
7
0
1
7
a
c
0
7
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
r
e
a
t
e
d
 
 
\

4
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
6
 
0
5
:
5
5
:
2
7
 
 
 

6
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
0
1
 
0
5
:
4
4
:
3
3
 
 
 

9
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
4
 
1
5
:
1
9
:
5
9
 
 
 

1
0
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
4
 
0
7
:
5
4
:
2
4
 
 
 

1
5
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
8
 
0
3
:
5
0
:
2
3
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
0
 
 
2
0
1
6
-
0
4
-
0
5
 
0
3
:
5
8
:
3
3
 
 
 

1
2
4
0
0
2
 
 
2
0
1
6
-
0
4
-
0
2
 
0
2
:
2
5
:
3
1
 
 
 

1
2
4
0
0
4
 
 
2
0
1
6
-
0
4
-
2
6
 
0
5
:
4
2
:
0
3
 
 
 

1
2
4
0
0
8
 
 
2
0
1
6
-
0
4
-
1
9
 
0
2
:
4
7
:
3
3
 
 
 

1
2
4
0
0
9
 
 
2
0
1
6
-
0
4
-
2
0
 
0
5
:
3
4
:
0
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
e
s
c
r
i
p
t
i
o
n
 
 
\

4
 
 
 
 
 
 
 
S
p
a
c
i
o
u
s
 
1
 
B
e
d
r
o
o
m
 
1
 
B
a
t
h
r
o
o
m
 
i
n
 
W
i
l
l
i
a
m
s
b
u
r
g
!
.
.
.
 
 
 

6
 
 
 
 
 
 
 
B
R
A
N
D
 
N
E
W
 
G
U
T
 
R
E
N
O
V
A
T
E
D
 
T
R
U
E
 
2
 
B
E
D
R
O
O
M
F
i
n
d
 
y
o
u
.
.
.
 
 
 

9
 
 
 
 
 
 
 
*
*
F
L
E
X
 
2
 
B
E
D
R
O
O
M
 
W
I
T
H
 
F
U
L
L
 
P
R
E
S
S
U
R
I
Z
E
D
 
W
A
L
L
*
*
L
.
.
.
 
 
 

1
0
 
 
 
 
 
 
A
 
B
r
a
n
d
 
N
e
w
 
3
 
B
e
d
r
o
o
m
 
1
.
5
 
b
a
t
h
 
A
p
a
r
t
m
e
n
t
E
n
j
o
y
 
.
.
.
 
 
 

1
5
 
 
 
 
 
 
O
v
e
r
-
s
i
z
e
d
 
S
t
u
d
i
o
 
w
 
a
b
u
n
d
a
n
t
 
c
l
o
s
e
t
s
.
 
A
v
a
i
l
a
b
l
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
2
4
0
0
0
 
 
T
h
e
r
e
 
i
s
 
7
0
0
 
s
q
u
a
r
e
 
f
e
e
t
 
o
f
 
r
e
c
e
n
t
l
y
 
r
e
n
o
v
a
t
e
d
.
.
.
 
 
 

1
2
4
0
0
2
 
 
2
 
b
e
d
r
o
o
m
 
a
p
a
r
t
m
e
n
t
 
w
i
t
h
 
u
p
d
a
t
e
d
 
k
i
t
c
h
e
n
,
 
r
e
c
e
.
.
.
 
 
 

1
2
4
0
0
4
 
 
N
o
 
B
r
o
k
e
r
s
 
F
e
e
 
*
 
N
e
v
e
r
 
L
i
v
e
d
 
1
 
B
e
d
r
o
o
m
 
1
 
B
a
t
h
r
.
.
.
 
 
 

1
2
4
0
0
8
 
 
W
o
n
d
e
r
f
u
l
 
B
r
i
g
h
t
 
C
h
e
l
s
e
a
 
2
 
B
e
d
r
o
o
m
 
a
p
a
r
t
m
e
n
t
 
o
.
.
.
 
 
 

1
2
4
0
0
9
 
 
*
*
*
P
R
I
M
E
 
M
I
D
T
O
W
N
 
E
A
S
T
 
O
F
F
 
P
A
R
K
 
A
V
E
*
*
*
T
R
U
E
 
3
 
B
E
.
.
.
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
\

4
 
 
 
 
 
 
 
 
1
4
5
 
B
o
r
i
n
q
u
e
n
 
P
l
a
c
e
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
4
4
t
h
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
5
6
t
h
 
S
t
r
e
e
t
 
 
 

1
0
 
 
 
 
 
 
 
M
e
t
r
o
p
o
l
i
t
a
n
 
A
v
e
n
u
e
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
3
4
t
h
 
S
t
r
e
e
t
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
0
 
 
 
 
 
 
 
 
 
 
W
 
1
7
1
 
S
t
r
e
e
t
 
 
 

1
2
4
0
0
2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
B
r
o
a
d
w
a
y
 
 
 

1
2
4
0
0
4
 
 
2
1
0
 
B
r
i
g
h
t
o
n
 
1
5
t
h
 
S
t
 
 
 

1
2
4
0
0
8
 
 
 
 
 
 
W
e
s
t
 
2
1
s
t
 
S
t
r
e
e
t
 
 
 

1
2
4
0
0
9
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
5
4
t
h
 
S
t
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
 
 
l
a
t
i
t
u
d
e
 
 
\

4
 
 
 
 
 
 
 
[
D
i
n
i
n
g
 
R
o
o
m
,
 
P
r
e
-
W
a
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
.
.
.
 
 
 
4
0
.
7
1
0
8
 
 
 

6
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
5
1
3
 
 
 

9
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
L
a
u
n
d
.
.
.
 
 
 
4
0
.
7
5
7
5
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
1
4
5
 
 
 

1
5
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
F
i
t
n
e
s
s
 
C
e
n
t
e
r
,
 
L
a
u
n
d
r
y
 
i
n
.
.
.
 
 
 
4
0
.
7
4
3
9
 
 
 

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
2
4
0
0
0
 
 
 
 
 
 
 
 
 
 
 
 
[
E
l
e
v
a
t
o
r
,
 
D
i
s
h
w
a
s
h
e
r
,
 
H
a
r
d
w
o
o
d
 
F
l
o
o
r
s
]
 
 
 
4
0
.
8
4
3
3
 
 
 

1
2
4
0
0
2
 
 
[
C
o
m
m
o
n
 
O
u
t
d
o
o
r
 
S
p
a
c
e
,
 
C
a
t
s
 
A
l
l
o
w
e
d
,
 
D
o
g
s
 
A
l
l
o
.
.
.
 
 
 
4
0
.
8
1
9
8
 
 
 

1
2
4
0
0
4
 
 
[
D
i
n
i
n
g
 
R
o
o
m
,
 
E
l
e
v
a
t
o
r
,
 
P
r
e
-
W
a
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
.
.
.
 
 
 
4
0
.
5
7
6
5
 
 
 

1
2
4
0
0
8
 
 
[
P
r
e
-
W
a
r
,
 
L
a
u
n
d
r
y
 
i
n
 
U
n
i
t
,
 
D
i
s
h
w
a
s
h
e
r
,
 
N
o
 
F
e
e
,
.
.
.
 
 
 
4
0
.
7
4
4
8
 
 
 

1
2
4
0
0
9
 
 
[
D
i
n
i
n
g
 
R
o
o
m
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
.
.
.
 
 
 
4
0
.
7
5
9
4
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
a
n
a
g
e
r
_
i
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
7
1
7
0
3
2
5
 
 
 
-
7
3
.
9
5
3
9
 
 
a
1
0
d
b
4
5
9
0
8
4
3
d
7
8
c
7
8
4
1
7
1
a
1
0
7
b
d
a
c
b
4
 
 
 

6
 
 
 
 
 
 
 
 
 
 
7
0
9
2
3
4
4
 
 
 
-
7
3
.
9
7
2
2
 
 
9
5
5
d
b
3
3
4
7
7
a
f
4
f
4
0
0
0
4
8
2
0
b
4
a
e
d
8
0
4
a
0
 
 
 

9
 
 
 
 
 
 
 
 
 
 
7
1
5
8
6
7
7
 
 
 
-
7
3
.
9
6
2
5
 
 
c
8
b
1
0
a
3
1
7
b
7
6
6
2
0
4
f
0
8
e
6
1
3
c
e
f
4
c
e
7
a
0
 
 
 

1
0
 
 
 
 
 
 
 
 
 
7
2
1
1
2
1
2
 
 
 
-
7
3
.
9
4
2
5
 
 
5
b
a
9
8
9
2
3
2
d
0
4
8
9
d
a
1
b
5
f
2
c
4
5
f
6
6
8
8
a
d
c
 
 
 

1
5
 
 
 
 
 
 
 
 
 
7
2
2
5
2
9
2
 
 
 
-
7
3
.
9
7
4
3
 
 
2
c
3
b
4
1
f
5
8
8
f
b
b
5
2
3
4
d
8
a
1
e
8
8
5
a
4
3
6
c
f
a
 
 
 

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
2
4
0
0
0
 
 
 
 
 
6
8
2
4
8
0
0
 
 
 
-
7
3
.
9
3
9
6
 
 
a
6
1
e
2
1
d
a
3
b
a
1
8
c
7
a
3
d
5
4
c
f
d
c
c
2
4
7
e
1
f
8
 
 
 

1
2
4
0
0
2
 
 
 
 
 
6
8
1
3
2
6
8
 
 
 
-
7
3
.
9
5
7
8
 
 
8
f
9
0
e
5
e
1
0
e
8
a
2
d
7
c
f
9
9
7
f
0
1
6
d
8
9
2
3
0
e
b
 
 
 

1
2
4
0
0
4
 
 
 
 
 
6
9
2
7
0
9
3
 
 
 
-
7
3
.
9
5
5
4
 
 
a
1
0
d
b
4
5
9
0
8
4
3
d
7
8
c
7
8
4
1
7
1
a
1
0
7
b
d
a
c
b
4
 
 
 

1
2
4
0
0
8
 
 
 
 
 
6
8
9
2
8
1
6
 
 
 
-
7
4
.
0
0
1
7
 
 
c
3
c
d
4
5
f
4
3
8
1
a
c
3
7
1
5
0
7
0
9
0
e
9
f
f
a
b
e
a
8
0
 
 
 

1
2
4
0
0
9
 
 
 
 
 
6
9
0
1
0
2
3
 
 
 
-
7
3
.
9
7
1
2
 
 
e
9
0
f
2
d
e
d
8
4
3
c
d
b
2
e
f
d
6
5
e
f
4
7
d
9
f
c
8
0
2
9
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
h
o
t
o
s
 
 
p
r
i
c
e
 
 
\

4
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
7
0
3
2
5
_
3
b
b
5
a
c
8
4
.
.
.
 
 
 
2
4
0
0
 
 
 

6
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
0
9
2
3
4
4
_
7
6
6
3
c
1
9
a
.
.
.
 
 
 
3
8
0
0
 
 
 

9
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
5
8
6
7
7
_
c
8
9
7
a
1
3
4
.
.
.
 
 
 
3
4
9
5
 
 
 

1
0
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
1
1
2
1
2
_
1
e
d
4
5
4
2
e
.
.
.
 
 
 
3
0
0
0
 
 
 

1
5
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
2
5
2
9
2
_
9
0
1
f
1
9
8
4
.
.
.
 
 
 
2
7
9
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
2
4
0
0
0
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
2
4
8
0
0
_
0
6
8
2
b
e
1
6
.
.
.
 
 
 
2
8
0
0
 
 
 

1
2
4
0
0
2
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
1
3
2
6
8
_
1
e
6
f
c
c
3
2
.
.
.
 
 
 
2
3
9
5
 
 
 

1
2
4
0
0
4
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
2
7
0
9
3
_
9
3
a
5
2
1
0
4
.
.
.
 
 
 
1
8
5
0
 
 
 

1
2
4
0
0
8
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
9
2
8
1
6
_
1
a
8
d
0
8
7
a
.
.
.
 
 
 
4
1
9
5
 
 
 

1
2
4
0
0
9
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
0
1
0
2
3
_
0
2
0
5
2
d
9
0
.
.
.
 
 
 
4
2
8
0
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
i
n
t
e
r
e
s
t
_
l
e
v
e
l
 
 

4
 
 
 
 
 
 
 
 
 
 
 
1
4
5
 
B
o
r
i
n
q
u
e
n
 
P
l
a
c
e
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
3
0
 
E
a
s
t
 
4
4
t
h
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 

9
 
 
 
 
 
 
 
 
 
 
4
0
5
 
E
a
s
t
 
5
6
t
h
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
0
 
 
 
 
 
 
7
9
2
 
M
e
t
r
o
p
o
l
i
t
a
n
 
A
v
e
n
u
e
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
5
 
 
 
 
 
 
 
 
 
3
4
0
 
E
a
s
t
 
3
4
t
h
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 

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
2
4
0
0
0
 
 
 
 
 
 
 
 
 
6
2
0
 
W
 
1
7
1
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 

1
2
4
0
0
2
 
 
 
 
 
 
 
 
 
 
 
 
3
3
3
3
 
B
r
o
a
d
w
a
y
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
2
4
0
0
4
 
 
 
 
 
2
1
0
 
B
r
i
g
h
t
o
n
 
1
5
t
h
 
S
t
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
2
4
0
0
8
 
 
 
 
 
3
5
0
 
W
e
s
t
 
2
1
s
t
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
2
4
0
0
9
 
 
 
 
 
 
 
 
 
 
 
 
1
2
3
 
E
 
5
4
t
h
 
S
t
 
 
 
 
 
 
 
 
 
 
 
h
i
g
h
 
 


[
4
9
3
5
2
 
r
o
w
s
 
x
 
1
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
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
7
9
7
8
0
b
e
1
5
1
4
f
6
4
5
d
7
e
6
b
e
9
9
a
3
d
e
6
9
6
c
5
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
f
9
c
8
2
6
1
0
4
b
9
1
d
8
6
8
e
6
9
b
d
2
5
7
4
6
4
4
8
c
0
c
 
 
 

5
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
8
1
0
6
2
9
3
6
e
1
2
e
e
5
f
a
6
c
d
2
b
9
6
5
6
9
8
e
1
7
d
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
 
 
 

1
2
4
0
0
3
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
b
d
8
6
3
d
2
8
a
6
b
1
1
9
a
c
3
b
c
7
2
d
5
f
2
7
b
0
7
f
2
4
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
9
1
7
4
b
7
5
c
0
c
d
9
7
8
e
b
0
e
5
a
a
9
3
a
f
b
a
d
7
5
4
b
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
2
 
 
c
9
0
c
0
1
0
e
5
5
0
5
3
6
5
6
7
6
5
3
8
e
6
4
d
0
2
a
a
1
e
0
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
1
a
6
c
f
9
b
7
1
d
a
6
5
c
d
c
0
c
f
d
5
0
1
5
a
7
5
3
1
7
a
c
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
r
e
a
t
e
d
 
 
\

0
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
1
 
0
5
:
2
9
:
4
1
 
 
 

1
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
4
 
0
6
:
3
6
:
3
4
 
 
 

2
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
7
 
0
1
:
2
3
:
3
9
 
 
 

3
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
1
 
0
5
:
0
6
:
0
2
 
 
 

5
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
6
 
0
7
:
2
4
:
2
7
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
3
 
 
2
0
1
6
-
0
4
-
2
6
 
1
6
:
0
9
:
5
5
 
 
 

1
2
4
0
0
5
 
 
2
0
1
6
-
0
4
-
2
1
 
0
5
:
0
6
:
1
9
 
 
 

1
2
4
0
0
6
 
 
2
0
1
6
-
0
4
-
2
0
 
0
1
:
3
1
:
5
2
 
 
 

1
2
4
0
0
7
 
 
2
0
1
6
-
0
4
-
0
8
 
0
2
:
2
6
:
4
5
 
 
 

1
2
4
0
1
0
 
 
2
0
1
6
-
0
4
-
1
8
 
0
2
:
5
1
:
2
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
e
s
c
r
i
p
t
i
o
n
 
 
\

0
 
 
 
 
 
 
 
L
a
r
g
e
 
w
i
t
h
 
a
w
e
s
o
m
e
 
t
e
r
r
a
c
e
-
-
a
c
c
e
s
s
i
b
l
e
 
v
i
a
 
b
e
d
.
.
.
 
 
 

1
 
 
 
 
 
 
 
P
r
i
m
e
 
S
o
h
o
 
-
 
b
e
t
w
e
e
n
 
B
l
e
e
c
k
e
r
 
a
n
d
 
H
o
u
s
t
o
n
 
-
 
N
e
.
.
.
 
 
 

2
 
 
 
 
 
 
 
S
p
a
c
i
o
u
s
 
s
t
u
d
i
o
 
i
n
 
P
r
i
m
e
 
L
o
c
a
t
i
o
n
.
 
C
l
e
a
n
b
u
i
l
d
i
.
.
.
 
 
 

3
 
 
 
 
 
 
 
F
o
r
 
i
m
m
e
d
i
a
t
e
 
a
c
c
e
s
s
 
c
a
l
l
 
B
r
y
a
n
.
<
b
r
 
/
>
<
b
r
 
/
>
B
o
.
.
.
 
 
 

5
 
 
 
 
 
 
 
B
e
a
u
t
i
f
u
l
 
T
R
U
E
 
1
 
b
e
d
r
o
o
m
 
i
n
 
a
 
l
u
x
u
r
y
 
b
u
i
l
d
i
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
 
 
 

1
2
4
0
0
3
 
 
B
R
A
N
D
 
N
E
W
 
T
O
 
M
A
R
K
E
T
 
1
B
D
R
 
\
r
1
0
7
T
H
 
A
N
D
 
L
E
X
I
N
G
T
O
N
.
.
.
 
 
 

1
2
4
0
0
5
 
 
C
o
n
v
e
r
t
i
b
l
e
 
2
B
R
 
a
p
a
r
t
m
e
n
t
 
f
e
a
t
u
r
e
s
 
a
 
b
r
a
n
d
 
n
e
w
.
.
.
 
 
 

1
2
4
0
0
6
 
 
L
e
t
'
s
 
g
e
t
 
y
o
u
 
i
n
 
t
o
 
s
e
e
 
t
h
i
s
 
$
2
,
4
0
0
/
m
o
,
 
r
e
c
e
n
t
.
.
.
 
 
 

1
2
4
0
0
7
 
 
C
o
o
p
e
r
C
o
o
p
e
r
.
c
o
m
 
:
:
 
W
e
b
 
I
D
 
#
1
7
1
3
5
7
;
 
A
c
c
e
s
s
 
1
0
0
.
.
.
 
 
 

1
2
4
0
1
0
 
 
N
e
w
 
r
e
n
o
v
a
t
e
d
 
B
r
i
g
h
t
 
3
B
r
 
M
u
r
r
a
y
 
H
i
l
l
.
 
3
 
Q
U
E
E
N
 
.
.
.
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
\

0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
f
f
o
l
k
 
S
t
r
e
e
t
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
 
T
h
o
m
p
s
o
n
 
S
t
r
e
e
t
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
S
u
l
l
i
v
a
n
 
S
t
r
e
e
t
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
J
o
n
e
s
 
S
t
r
e
e
t
 
 
 

5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
E
x
c
h
a
n
g
e
 
P
l
a
c
e
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
3
 
 
1
5
0
 
E
A
S
T
 
1
0
7
T
H
 
S
T
R
E
E
T
 
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
3
3
r
d
 
S
t
.
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
L
e
x
i
n
g
t
o
n
 
A
v
e
n
u
e
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
 
 
 
P
a
r
k
 
A
v
e
n
u
e
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
3
5
 
S
t
r
e
e
t
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
 
 
l
a
t
i
t
u
d
e
 
 
\

0
 
 
 
 
 
 
 
[
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
L
a
u
n
d
r
y
 
i
n
 
U
n
i
.
.
.
 
 
 
4
0
.
7
1
8
5
 
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
P
r
e
-
W
a
r
,
 
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
2
7
8
 
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
P
r
e
-
W
a
r
,
 
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
2
6
0
 
 
 

3
 
 
 
 
 
 
 
 
 
 
 
[
H
a
r
d
w
o
o
d
 
F
l
o
o
r
s
,
 
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
3
2
1
 
 
 

5
 
 
 
 
 
 
 
[
R
o
o
f
 
D
e
c
k
,
 
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
F
i
t
n
e
s
s
 
C
e
n
t
e
r
,
.
.
.
 
 
 
4
0
.
7
0
5
4
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
9
2
5
 
 
 

1
2
4
0
0
5
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
4
5
6
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
1
6
 
 
 

1
2
4
0
0
7
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
C
a
t
s
 
A
l
l
o
w
e
d
,
 
D
o
g
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
8
5
 
 
 

1
2
4
0
1
0
 
 
[
G
a
r
d
e
n
/
P
a
t
i
o
,
 
L
a
u
n
d
r
y
 
i
n
 
U
n
i
t
,
 
D
i
s
h
w
a
s
h
e
r
,
 
H
a
.
.
.
 
 
 
4
0
.
7
4
4
7
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
a
n
a
g
e
r
_
i
d
 
 
\

0
 
 
 
 
 
 
 
 
 
 
7
1
4
2
6
1
8
 
 
 
-
7
3
.
9
8
6
5
 
 
b
1
b
1
8
5
2
c
4
1
6
d
7
8
d
7
7
6
5
d
7
4
6
c
b
1
b
8
9
2
1
f
 
 
 

1
 
 
 
 
 
 
 
 
 
 
7
2
1
0
0
4
0
 
 
 
-
7
4
.
0
0
0
0
 
 
d
0
b
5
6
4
8
0
1
7
8
3
2
b
2
4
2
7
e
e
b
9
9
5
6
d
9
6
6
a
1
4
 
 
 

2
 
 
 
 
 
 
 
 
 
 
7
1
7
4
5
6
6
 
 
 
-
7
4
.
0
0
2
6
 
 
e
6
4
7
2
c
7
2
3
7
3
2
7
d
d
3
9
0
3
b
3
d
6
f
6
a
9
4
5
1
5
a
 
 
 

3
 
 
 
 
 
 
 
 
 
 
7
1
9
1
3
9
1
 
 
 
-
7
4
.
0
0
2
8
 
 
4
1
7
3
5
6
4
5
e
0
f
8
f
1
3
9
9
3
c
4
2
8
9
4
0
2
3
f
8
e
5
8
 
 
 

5
 
 
 
 
 
 
 
 
 
 
7
1
7
1
6
9
5
 
 
 
-
7
4
.
0
0
9
5
 
 
a
7
4
2
c
f
7
d
d
3
b
2
6
2
7
d
8
3
4
1
7
b
c
3
a
1
b
3
e
c
9
6
 
 
 

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
2
4
0
0
3
 
 
 
 
 
6
9
2
8
1
0
8
 
 
 
-
7
3
.
9
4
5
4
 
 
4
5
3
d
4
6
f
8
1
1
3
e
1
f
2
c
7
3
0
c
2
e
e
5
a
4
4
6
9
c
7
1
 
 
 

1
2
4
0
0
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
 
-
7
3
.
9
7
9
7
 
 
2
9
8
3
e
4
5
f
7
e
0
a
d
8
7
d
6
7
7
d
a
c
d
1
3
e
3
6
2
7
8
5
 
 
 

1
2
4
0
0
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
 
-
7
3
.
9
8
2
9
 
 
e
6
4
7
2
c
7
2
3
7
3
2
7
d
d
3
9
0
3
b
3
d
6
f
6
a
9
4
5
1
5
a
 
 
 

1
2
4
0
0
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
 
-
7
3
.
9
8
0
0
 
 
6
e
5
c
1
0
2
4
6
1
5
6
a
e
5
b
d
c
d
9
b
4
8
7
c
a
9
9
d
9
6
a
 
 
 

1
2
4
0
1
0
 
 
 
 
 
6
8
8
9
3
1
9
 
 
 
-
7
3
.
9
7
4
1
 
 
d
9
0
3
9
c
4
3
9
8
3
f
6
e
5
6
4
b
1
4
8
2
b
2
7
3
b
d
7
b
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
h
o
t
o
s
 
 
p
r
i
c
e
 
 
\

0
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
1
c
4
5
a
2
c
8
.
.
.
 
 
 
2
9
5
0
 
 
 

1
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
1
0
0
4
0
_
d
8
2
4
c
c
7
1
.
.
.
 
 
 
2
8
5
0
 
 
 

2
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
7
4
5
6
6
_
b
a
3
a
3
5
c
5
.
.
.
 
 
 
2
2
9
5
 
 
 

3
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
9
1
3
9
1
_
8
c
2
f
2
d
4
9
.
.
.
 
 
 
2
9
0
0
 
 
 

5
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
7
1
6
9
5
_
0
8
9
f
f
e
e
2
.
.
.
 
 
 
3
2
5
4
 
 
 

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
2
4
0
0
3
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
2
8
1
0
8
_
2
3
1
e
b
9
8
3
.
.
.
 
 
 
1
7
0
0
 
 
 

1
2
4
0
0
5
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
0
6
6
7
4
_
9
f
e
8
9
9
a
8
.
.
.
 
 
 
4
1
9
5
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
2
4
0
0
 
 
 

1
2
4
0
0
7
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
4
2
1
8
3
_
b
1
f
e
5
1
f
4
.
.
.
 
 
 
6
8
9
5
 
 
 

1
2
4
0
1
0
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
8
9
3
1
9
_
7
9
f
1
8
6
e
7
.
.
.
 
 
 
4
6
9
5
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
9
9
 
S
u
f
f
o
l
k
 
S
t
r
e
e
t
 
 

1
 
 
 
 
 
 
 
 
 
 
1
7
6
 
T
h
o
m
p
s
o
n
 
S
t
r
e
e
t
 
 

2
 
 
 
 
 
 
 
 
 
 
1
1
5
 
S
u
l
l
i
v
a
n
 
S
t
r
e
e
t
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
3
 
J
o
n
e
s
 
S
t
r
e
e
t
 
 

5
 
 
 
 
 
 
 
 
 
 
 
 
2
0
 
E
x
c
h
a
n
g
e
 
P
l
a
c
e
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

1
2
4
0
0
3
 
 
1
5
8
 
E
A
S
T
 
1
0
7
T
H
 
S
T
R
E
E
T
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
1
4
1
 
E
 
3
3
r
d
 
S
t
.
 
 

1
2
4
0
0
6
 
 
 
 
 
9
5
 
L
e
x
i
n
g
t
o
n
 
A
v
e
n
u
e
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
4
1
 
P
a
r
k
 
A
v
e
n
u
e
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
3
2
6
 
E
 
3
5
 
S
t
r
e
e
t
 
 


[
7
4
6
5
9
 
r
o
w
s
 
x
 
1
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
```

<pre>
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
8
5
7
9
a
0
b
0
d
5
4
d
b
8
0
3
8
2
1
a
3
5
a
4
a
6
1
5
e
9
7
a
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
b
8
e
7
5
f
c
9
4
9
a
6
c
d
8
2
2
5
b
4
5
5
6
4
8
a
9
5
1
7
1
2
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
c
d
7
5
9
a
9
8
8
b
8
f
2
3
9
2
4
b
5
a
2
0
5
8
d
5
a
b
2
b
4
9
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
1
.
5
 
 
 
 
 
 
 
 
 
3
 
 
5
3
a
5
b
1
1
9
b
a
8
f
7
b
6
1
d
4
e
0
1
0
5
1
2
e
0
d
f
c
8
5
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
b
f
b
9
4
0
5
1
4
9
b
f
f
f
4
2
a
9
2
9
8
0
b
5
9
4
c
2
8
2
3
4
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
b
d
8
6
3
d
2
8
a
6
b
1
1
9
a
c
3
b
c
7
2
d
5
f
2
7
b
0
7
f
2
4
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
9
1
7
4
b
7
5
c
0
c
d
9
7
8
e
b
0
e
5
a
a
9
3
a
f
b
a
d
7
5
4
b
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
2
 
 
c
9
0
c
0
1
0
e
5
5
0
5
3
6
5
6
7
6
5
3
8
e
6
4
d
0
2
a
a
1
e
0
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
1
a
6
c
f
9
b
7
1
d
a
6
5
c
d
c
0
c
f
d
5
0
1
5
a
7
5
3
1
7
a
c
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
r
e
a
t
e
d
 
 
\

4
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
6
 
0
5
:
5
5
:
2
7
 
 
 

6
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
0
1
 
0
5
:
4
4
:
3
3
 
 
 

9
 
 
 
 
 
 
 
2
0
1
6
-
0
6
-
1
4
 
1
5
:
1
9
:
5
9
 
 
 

1
0
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
4
 
0
7
:
5
4
:
2
4
 
 
 

1
5
 
 
 
 
 
 
2
0
1
6
-
0
6
-
2
8
 
0
3
:
5
0
:
2
3
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
3
 
 
2
0
1
6
-
0
4
-
2
6
 
1
6
:
0
9
:
5
5
 
 
 

1
2
4
0
0
5
 
 
2
0
1
6
-
0
4
-
2
1
 
0
5
:
0
6
:
1
9
 
 
 

1
2
4
0
0
6
 
 
2
0
1
6
-
0
4
-
2
0
 
0
1
:
3
1
:
5
2
 
 
 

1
2
4
0
0
7
 
 
2
0
1
6
-
0
4
-
0
8
 
0
2
:
2
6
:
4
5
 
 
 

1
2
4
0
1
0
 
 
2
0
1
6
-
0
4
-
1
8
 
0
2
:
5
1
:
2
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
e
s
c
r
i
p
t
i
o
n
 
 
\

4
 
 
 
 
 
 
 
S
p
a
c
i
o
u
s
 
1
 
B
e
d
r
o
o
m
 
1
 
B
a
t
h
r
o
o
m
 
i
n
 
W
i
l
l
i
a
m
s
b
u
r
g
!
.
.
.
 
 
 

6
 
 
 
 
 
 
 
B
R
A
N
D
 
N
E
W
 
G
U
T
 
R
E
N
O
V
A
T
E
D
 
T
R
U
E
 
2
 
B
E
D
R
O
O
M
F
i
n
d
 
y
o
u
.
.
.
 
 
 

9
 
 
 
 
 
 
 
*
*
F
L
E
X
 
2
 
B
E
D
R
O
O
M
 
W
I
T
H
 
F
U
L
L
 
P
R
E
S
S
U
R
I
Z
E
D
 
W
A
L
L
*
*
L
.
.
.
 
 
 

1
0
 
 
 
 
 
 
A
 
B
r
a
n
d
 
N
e
w
 
3
 
B
e
d
r
o
o
m
 
1
.
5
 
b
a
t
h
 
A
p
a
r
t
m
e
n
t
E
n
j
o
y
 
.
.
.
 
 
 

1
5
 
 
 
 
 
 
O
v
e
r
-
s
i
z
e
d
 
S
t
u
d
i
o
 
w
 
a
b
u
n
d
a
n
t
 
c
l
o
s
e
t
s
.
 
A
v
a
i
l
a
b
l
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
2
4
0
0
3
 
 
B
R
A
N
D
 
N
E
W
 
T
O
 
M
A
R
K
E
T
 
1
B
D
R
 
\
r
1
0
7
T
H
 
A
N
D
 
L
E
X
I
N
G
T
O
N
.
.
.
 
 
 

1
2
4
0
0
5
 
 
C
o
n
v
e
r
t
i
b
l
e
 
2
B
R
 
a
p
a
r
t
m
e
n
t
 
f
e
a
t
u
r
e
s
 
a
 
b
r
a
n
d
 
n
e
w
.
.
.
 
 
 

1
2
4
0
0
6
 
 
L
e
t
'
s
 
g
e
t
 
y
o
u
 
i
n
 
t
o
 
s
e
e
 
t
h
i
s
 
$
2
,
4
0
0
/
m
o
,
 
r
e
c
e
n
t
.
.
.
 
 
 

1
2
4
0
0
7
 
 
C
o
o
p
e
r
C
o
o
p
e
r
.
c
o
m
 
:
:
 
W
e
b
 
I
D
 
#
1
7
1
3
5
7
;
 
A
c
c
e
s
s
 
1
0
0
.
.
.
 
 
 

1
2
4
0
1
0
 
 
N
e
w
 
r
e
n
o
v
a
t
e
d
 
B
r
i
g
h
t
 
3
B
r
 
M
u
r
r
a
y
 
H
i
l
l
.
 
3
 
Q
U
E
E
N
 
.
.
.
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
\

4
 
 
 
 
 
 
 
 
 
 
1
4
5
 
B
o
r
i
n
q
u
e
n
 
P
l
a
c
e
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
4
4
t
h
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
5
6
t
h
 
S
t
r
e
e
t
 
 
 

1
0
 
 
 
 
 
 
 
 
 
M
e
t
r
o
p
o
l
i
t
a
n
 
A
v
e
n
u
e
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
E
a
s
t
 
3
4
t
h
 
S
t
r
e
e
t
 
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 

1
2
4
0
0
3
 
 
1
5
0
 
E
A
S
T
 
1
0
7
T
H
 
S
T
R
E
E
T
 
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
3
3
r
d
 
S
t
.
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
L
e
x
i
n
g
t
o
n
 
A
v
e
n
u
e
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
 
 
 
P
a
r
k
 
A
v
e
n
u
e
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
E
 
3
5
 
S
t
r
e
e
t
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
 
 
l
a
t
i
t
u
d
e
 
 
\

4
 
 
 
 
 
 
 
[
D
i
n
i
n
g
 
R
o
o
m
,
 
P
r
e
-
W
a
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
.
.
.
 
 
 
4
0
.
7
1
0
8
 
 
 

6
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
5
1
3
 
 
 

9
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
L
a
u
n
d
.
.
.
 
 
 
4
0
.
7
5
7
5
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
1
4
5
 
 
 

1
5
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
F
i
t
n
e
s
s
 
C
e
n
t
e
r
,
 
L
a
u
n
d
r
y
 
i
n
.
.
.
 
 
 
4
0
.
7
4
3
9
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
9
2
5
 
 
 

1
2
4
0
0
5
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
4
5
6
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
1
6
 
 
 

1
2
4
0
0
7
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
C
a
t
s
 
A
l
l
o
w
e
d
,
 
D
o
g
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
8
5
 
 
 

1
2
4
0
1
0
 
 
[
G
a
r
d
e
n
/
P
a
t
i
o
,
 
L
a
u
n
d
r
y
 
i
n
 
U
n
i
t
,
 
D
i
s
h
w
a
s
h
e
r
,
 
H
a
.
.
.
 
 
 
4
0
.
7
4
4
7
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
a
n
a
g
e
r
_
i
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
7
1
7
0
3
2
5
 
 
 
-
7
3
.
9
5
3
9
 
 
a
1
0
d
b
4
5
9
0
8
4
3
d
7
8
c
7
8
4
1
7
1
a
1
0
7
b
d
a
c
b
4
 
 
 

6
 
 
 
 
 
 
 
 
 
 
7
0
9
2
3
4
4
 
 
 
-
7
3
.
9
7
2
2
 
 
9
5
5
d
b
3
3
4
7
7
a
f
4
f
4
0
0
0
4
8
2
0
b
4
a
e
d
8
0
4
a
0
 
 
 

9
 
 
 
 
 
 
 
 
 
 
7
1
5
8
6
7
7
 
 
 
-
7
3
.
9
6
2
5
 
 
c
8
b
1
0
a
3
1
7
b
7
6
6
2
0
4
f
0
8
e
6
1
3
c
e
f
4
c
e
7
a
0
 
 
 

1
0
 
 
 
 
 
 
 
 
 
7
2
1
1
2
1
2
 
 
 
-
7
3
.
9
4
2
5
 
 
5
b
a
9
8
9
2
3
2
d
0
4
8
9
d
a
1
b
5
f
2
c
4
5
f
6
6
8
8
a
d
c
 
 
 

1
5
 
 
 
 
 
 
 
 
 
7
2
2
5
2
9
2
 
 
 
-
7
3
.
9
7
4
3
 
 
2
c
3
b
4
1
f
5
8
8
f
b
b
5
2
3
4
d
8
a
1
e
8
8
5
a
4
3
6
c
f
a
 
 
 

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
2
4
0
0
3
 
 
 
 
 
6
9
2
8
1
0
8
 
 
 
-
7
3
.
9
4
5
4
 
 
4
5
3
d
4
6
f
8
1
1
3
e
1
f
2
c
7
3
0
c
2
e
e
5
a
4
4
6
9
c
7
1
 
 
 

1
2
4
0
0
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
 
-
7
3
.
9
7
9
7
 
 
2
9
8
3
e
4
5
f
7
e
0
a
d
8
7
d
6
7
7
d
a
c
d
1
3
e
3
6
2
7
8
5
 
 
 

1
2
4
0
0
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
 
-
7
3
.
9
8
2
9
 
 
e
6
4
7
2
c
7
2
3
7
3
2
7
d
d
3
9
0
3
b
3
d
6
f
6
a
9
4
5
1
5
a
 
 
 

1
2
4
0
0
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
 
-
7
3
.
9
8
0
0
 
 
6
e
5
c
1
0
2
4
6
1
5
6
a
e
5
b
d
c
d
9
b
4
8
7
c
a
9
9
d
9
6
a
 
 
 

1
2
4
0
1
0
 
 
 
 
 
6
8
8
9
3
1
9
 
 
 
-
7
3
.
9
7
4
1
 
 
d
9
0
3
9
c
4
3
9
8
3
f
6
e
5
6
4
b
1
4
8
2
b
2
7
3
b
d
7
b
0
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
h
o
t
o
s
 
 
p
r
i
c
e
 
 
\

4
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
7
0
3
2
5
_
3
b
b
5
a
c
8
4
.
.
.
 
 
 
2
4
0
0
 
 
 

6
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
0
9
2
3
4
4
_
7
6
6
3
c
1
9
a
.
.
.
 
 
 
3
8
0
0
 
 
 

9
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
5
8
6
7
7
_
c
8
9
7
a
1
3
4
.
.
.
 
 
 
3
4
9
5
 
 
 

1
0
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
1
1
2
1
2
_
1
e
d
4
5
4
2
e
.
.
.
 
 
 
3
0
0
0
 
 
 

1
5
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
2
5
2
9
2
_
9
0
1
f
1
9
8
4
.
.
.
 
 
 
2
7
9
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
2
4
0
0
3
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
2
8
1
0
8
_
2
3
1
e
b
9
8
3
.
.
.
 
 
 
1
7
0
0
 
 
 

1
2
4
0
0
5
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
0
6
6
7
4
_
9
f
e
8
9
9
a
8
.
.
.
 
 
 
4
1
9
5
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
2
4
0
0
 
 
 

1
2
4
0
0
7
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
4
2
1
8
3
_
b
1
f
e
5
1
f
4
.
.
.
 
 
 
6
8
9
5
 
 
 

1
2
4
0
1
0
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
8
9
3
1
9
_
7
9
f
1
8
6
e
7
.
.
.
 
 
 
4
6
9
5
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
i
n
t
e
r
e
s
t
_
l
e
v
e
l
 
 

4
 
 
 
 
 
 
 
 
 
 
 
1
4
5
 
B
o
r
i
n
q
u
e
n
 
P
l
a
c
e
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
3
0
 
E
a
s
t
 
4
4
t
h
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 

9
 
 
 
 
 
 
 
 
 
 
4
0
5
 
E
a
s
t
 
5
6
t
h
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
0
 
 
 
 
 
 
7
9
2
 
M
e
t
r
o
p
o
l
i
t
a
n
 
A
v
e
n
u
e
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 

1
5
 
 
 
 
 
 
 
 
 
3
4
0
 
E
a
s
t
 
3
4
t
h
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 

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
2
4
0
0
3
 
 
 
1
5
8
 
E
A
S
T
 
1
0
7
T
H
 
S
T
R
E
E
T
 
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
 
1
4
1
 
E
 
3
3
r
d
 
S
t
.
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
2
4
0
0
6
 
 
 
 
 
 
9
5
 
L
e
x
i
n
g
t
o
n
 
A
v
e
n
u
e
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
 
4
1
 
P
a
r
k
 
A
v
e
n
u
e
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
 
3
2
6
 
E
 
3
5
 
S
t
r
e
e
t
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 


[
1
2
4
0
1
1
 
r
o
w
s
 
x
 
1
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

```python
a
l
l
d
a
t
a
[
'
p
h
o
t
o
s
'
]
[
0
]
```

<pre>
[
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
1
c
4
5
a
2
c
8
f
4
5
e
6
4
9
b
9
e
e
7
7
6
8
1
c
c
7
c
a
4
3
8
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
2
a
0
2
6
8
f
f
0
1
f
8
3
4
c
1
0
3
9
0
2
7
a
0
4
e
5
4
e
d
f
4
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
1
6
4
5
e
d
a
e
b
3
8
9
2
d
3
5
c
1
9
0
3
5
6
e
e
b
1
6
b
d
7
5
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
c
a
5
c
0
3
3
3
9
b
d
1
f
0
2
1
b
9
4
d
a
7
2
a
f
7
3
5
6
b
c
a
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
b
1
2
9
d
4
3
2
a
9
6
a
0
a
d
4
1
9
f
1
a
f
4
3
0
f
4
a
2
0
f
f
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
d
d
3
c
3
6
5
1
b
9
9
1
4
5
5
d
3
e
d
7
4
0
3
7
6
6
c
6
9
4
1
d
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
4
d
d
e
f
2
a
e
e
0
c
3
4
3
f
5
a
8
6
d
a
7
1
1
3
f
9
3
3
6
f
c
.
j
p
g
'
,

 
'
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
4
2
6
1
8
_
6
c
5
1
a
e
c
6
4
5
7
0
a
f
f
e
c
c
5
7
3
e
f
b
d
c
4
4
5
3
c
a
.
j
p
g
'
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
[
'
f
e
a
t
u
r
e
s
'
]
[
0
]
```

<pre>
[
'
E
l
e
v
a
t
o
r
'
,

 
'
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
'
,

 
'
L
a
u
n
d
r
y
 
i
n
 
U
n
i
t
'
,

 
'
D
i
s
h
w
a
s
h
e
r
'
,

 
'
H
a
r
d
w
o
o
d
 
F
l
o
o
r
s
'
,

 
'
O
u
t
d
o
o
r
 
S
p
a
c
e
'
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
[
'
d
e
s
c
r
i
p
t
i
o
n
'
]
[
2
]
```

<pre>
'
S
p
a
c
i
o
u
s
 
s
t
u
d
i
o
 
i
n
 
P
r
i
m
e
 
L
o
c
a
t
i
o
n
.
 
C
l
e
a
n
b
u
i
l
d
i
n
g
 
w
i
t
h
 
h
a
n
d
s
 
o
n
 
m
a
n
a
g
e
m
e
n
t
 
a
n
d
 
s
u
p
e
r
.
 
L
o
c
a
t
e
d
 
v
e
r
y
 
c
l
o
s
e
 
t
o
 
a
l
l
 
m
a
j
o
r
 
s
u
b
w
a
y
 
l
i
n
e
s
.
 
H
a
r
d
w
o
o
d
 
f
l
o
o
r
s
 
t
h
r
o
u
g
h
o
u
t
,
 
u
p
d
a
t
e
d
 
k
i
t
c
h
e
n
 
w
i
t
h
 
G
r
a
n
i
t
e
 
c
o
u
n
t
e
r
 
t
o
p
s
,
 
a
n
d
 
m
a
r
b
l
e
 
b
a
t
h
r
o
o
m
.
 
P
l
e
a
s
e
 
c
o
n
t
a
c
t
 
Y
a
n
a
 
f
o
r
 
p
r
i
v
a
t
e
 
a
p
p
o
i
n
t
m
e
n
t
.
 
'
</pre>

```python
[
x
+
1
 
f
o
r
 
x
 
i
n
 
[
1
,
4
,
6
]
]
```

<pre>
[
2
,
 
5
,
 
7
]
</pre>

```python
x
=
[
'
k
a
g
g
l
e
'
,
 
'
a
p
p
l
e
'
,
 
'
k
i
w
i
'
]

"
 
"
.
j
o
i
n
(
x
)
```

<pre>
'
k
a
g
g
l
e
 
a
p
p
l
e
 
k
i
w
i
'
</pre>
정
형
 
데
이
터
와
 
텍
스
트
가
 
혼
재
되
어
 
있
어
,
 
각
 
c
o
l
u
m
n
으
로
 
부
터
 
유
의
미
한
 
데
이
터
를
 
전
처
리
 
해
줍
니
다
.




p
h
o
t
o
의
 
갯
수
가
 
선
호
도
에
 
영
향
을
 
줄
 
것
으
로
 
생
각
하
였
고
,
 
d
e
s
c
r
i
p
t
i
o
n
과
 
f
e
a
t
u
r
e
의
 
갯
수
도
 
선
호
도
에
 
영
향
을
 
줄
 
것
으
로
 
생
각
하
였
습
니
다
.




특
히
 
d
e
s
c
r
i
p
t
i
o
n
과
 
f
e
a
t
u
r
e
는
 
내
포
된
 
특
정
한
 
단
어
로
 
인
한
 
선
호
도
 
증
감
 
유
무
를
 
확
인
 
해
보
려
 
합
니
다
.




p
h
o
t
o
는
 
사
진
을
 
볼
 
수
 
있
는
 
s
i
t
e
가
 
l
i
s
t
 
형
식
으
로
 
구
성
되
어
 
있
습
니
다
.
 
>
 
a
l
l
d
a
t
a
[
'
n
u
m
_
p
h
o
t
o
s
'
]
=
a
l
l
d
a
t
a
[
'
p
h
o
t
o
s
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
e
n
)






d
e
s
c
r
i
p
t
i
o
n
은
 
t
e
x
t
로
 
구
성
되
어
 
있
는
데
 
띄
어
쓰
기
 
기
준
으
로
 
c
o
u
n
t
i
n
g
하
려
 
합
니
다
.
 
>
 
a
l
l
d
a
t
a
[
'
n
u
m
_
d
e
s
c
r
i
p
t
i
o
n
'
]
=
a
l
l
d
a
t
a
[
'
d
e
s
c
r
i
p
t
i
o
n
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
 
l
e
n
(
x
.
s
p
l
i
t
(
)
)
)




f
e
a
t
u
r
e
s
 
또
한
 
l
i
s
t
 
형
식
으
로
 
구
성
되
어
 
있
어
 
a
p
p
l
y
(
l
e
n
)
을
 
이
용
하
여
 
쉽
게
 
c
o
u
n
t
i
n
g
할
 
수
 
있
습
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
[
'
n
u
m
_
p
h
o
t
o
s
'
]
=
a
l
l
d
a
t
a
[
'
p
h
o
t
o
s
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
e
n
)

a
l
l
d
a
t
a
[
'
n
u
m
_
f
e
a
t
u
r
e
s
'
]
=
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
u
r
e
s
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
e
n
)

#
 
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
u
r
e
s
'
]
=
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
u
r
e
s
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
 
"
 
"
.
j
o
i
n
(
[
"
_
"
.
j
o
i
n
(
i
.
s
p
l
i
t
(
)
)
 
f
o
r
 
i
 
i
n
 
x
]
)
)

a
l
l
d
a
t
a
[
'
n
u
m
_
d
e
s
c
r
i
p
t
i
o
n
'
]
=
a
l
l
d
a
t
a
[
'
d
e
s
c
r
i
p
t
i
o
n
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
 
l
e
n
(
x
.
s
p
l
i
t
(
)
)
)
```


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

p
l
t
.
f
i
g
u
r
e
(
f
i
g
s
i
z
e
=
(
1
6
,
8
)
)

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
"
n
u
m
_
p
h
o
t
o
s
"
]
,
h
u
e
=
a
l
l
d
a
t
a
[
"
i
n
t
e
r
e
s
t
_
l
e
v
e
l
"
]
)

p
l
t
.
x
l
i
m
(
-
1
,
1
5
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
-
1
.
0
,
 
1
5
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
 
1
1
5
2
x
5
7
6
 
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
사
진
의
 
갯
수
가
 
많
을
 
수
록
 
i
n
t
e
r
e
s
t
_
l
e
v
e
l
이
 
낮
은
 
경
우
가
 
급
격
히
 
감
소
함
을
 
알
 
수
 
있
습
니
다
.




따
라
서
 
n
u
m
_
p
h
o
t
o
s
 
c
o
l
u
m
n
은
 
예
측
에
 
도
움
을
 
주
는
 
c
o
l
u
m
n
으
로
 
볼
 
수
 
있
습
니
다
.



```python
d
i
s
p
l
a
y
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
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
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
,
a
l
l
d
a
t
a
[
'
s
t
r
e
e
t
_
a
d
d
r
e
s
s
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
,
a
l
l
d
a
t
a
[
'
b
u
i
l
d
i
n
g
_
i
d
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
,
a
l
l
d
a
t
a
[
'
m
a
n
a
g
e
r
_
i
d
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
)
```

<pre>
1
6
0
6
8
</pre>
<pre>
2
5
7
6
6
</pre>
<pre>
1
1
6
3
5
</pre>
<pre>
4
3
9
9
</pre>
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
와
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
는
 
각
 
명
칭
으
로
 
되
어
 
있
고
,
 
b
u
i
l
d
i
n
g
_
i
d
와
 
m
a
n
a
g
e
r
_
i
d
는
 
일
련
번
호
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
 
(
모
두
 
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
에
 
존
재
하
는
 
c
o
l
u
m
n
입
니
다
)




a
l
l
d
a
t
a
의
 
총
 
l
o
w
 
갯
수
는
 
1
2
4
0
1
1
인
데
 
위
에
 
언
급
한
 
각
 
칼
럼
의
 
n
u
n
i
q
u
e
를
 
살
펴
보
아
 
중
복
 
여
부
를
 
확
인
하
였
습
니
다
.




d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
:
 
1
6
0
6
8
 
개


 
 
 
 


s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
:
 
2
5
7
6
6
 
개


 
 
 
 


b
u
i
l
d
i
n
g
_
i
d
 
:
 
1
1
6
3
5
개


 
 
 
 


m
a
n
a
g
e
r
_
i
d
 
:
 
4
3
9
9
개


 
 
 
 


따
라
서
 
위
의
 
c
o
l
u
m
n
들
은
 
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
를
 
사
용
하
여
 
처
리
함
으
로
써
 
숫
자
 
형
식
으
로
 
통
일
 
시
키
려
 
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

a
l
l
d
a
t
a
[
'
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
'
]
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
a
l
l
d
a
t
a
[
'
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
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
[
'
s
t
r
e
e
t
_
a
d
d
r
e
s
s
'
]
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
a
l
l
d
a
t
a
[
'
s
t
r
e
e
t
_
a
d
d
r
e
s
s
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
[
'
b
u
i
l
d
i
n
g
_
i
d
'
]
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
a
l
l
d
a
t
a
[
'
b
u
i
l
d
i
n
g
_
i
d
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
[
'
m
a
n
a
g
e
r
_
i
d
'
]
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
a
l
l
d
a
t
a
[
'
m
a
n
a
g
e
r
_
i
d
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
```

<pre>
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
r
e
a
t
e
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
6
0
8
3
 
 
2
0
1
6
-
0
6
-
1
6
 
0
5
:
5
5
:
2
7
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
8
4
1
7
 
 
2
0
1
6
-
0
6
-
0
1
 
0
5
:
4
4
:
3
3
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
3
4
4
 
 
2
0
1
6
-
0
6
-
1
4
 
1
5
:
1
9
:
5
9
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
1
.
5
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
3
7
9
7
 
 
2
0
1
6
-
0
6
-
2
4
 
0
7
:
5
4
:
2
4
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
8
7
1
7
 
 
2
0
1
6
-
0
6
-
2
8
 
0
3
:
5
0
:
2
3
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
8
6
2
3
 
 
2
0
1
6
-
0
4
-
2
6
 
1
6
:
0
9
:
5
5
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
6
6
0
0
 
 
2
0
1
6
-
0
4
-
2
1
 
0
5
:
0
6
:
1
9
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
2
0
1
6
-
0
4
-
2
0
 
0
1
:
3
1
:
5
2
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
1
3
1
 
 
2
0
1
6
-
0
4
-
0
8
 
0
2
:
2
6
:
4
5
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
1
2
0
5
 
 
2
0
1
6
-
0
4
-
1
8
 
0
2
:
5
1
:
2
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
e
s
c
r
i
p
t
i
o
n
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
\

4
 
 
 
 
 
 
 
S
p
a
c
i
o
u
s
 
1
 
B
e
d
r
o
o
m
 
1
 
B
a
t
h
r
o
o
m
 
i
n
 
W
i
l
l
i
a
m
s
b
u
r
g
!
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
1
8
8
7
 
 
 

6
 
 
 
 
 
 
 
B
R
A
N
D
 
N
E
W
 
G
U
T
 
R
E
N
O
V
A
T
E
D
 
T
R
U
E
 
2
 
B
E
D
R
O
O
M
F
i
n
d
 
y
o
u
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
8
4
8
 
 
 

9
 
 
 
 
 
 
 
*
*
F
L
E
X
 
2
 
B
E
D
R
O
O
M
 
W
I
T
H
 
F
U
L
L
 
P
R
E
S
S
U
R
I
Z
E
D
 
W
A
L
L
*
*
L
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
9
0
4
 
 
 

1
0
 
 
 
 
 
 
A
 
B
r
a
n
d
 
N
e
w
 
3
 
B
e
d
r
o
o
m
 
1
.
5
 
b
a
t
h
 
A
p
a
r
t
m
e
n
t
E
n
j
o
y
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
2
8
2
 
 
 

1
5
 
 
 
 
 
 
O
v
e
r
-
s
i
z
e
d
 
S
t
u
d
i
o
 
w
 
a
b
u
n
d
a
n
t
 
c
l
o
s
e
t
s
.
 
A
v
a
i
l
a
b
l
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
7
9
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
 
 
 

1
2
4
0
0
3
 
 
B
R
A
N
D
 
N
E
W
 
T
O
 
M
A
R
K
E
T
 
1
B
D
R
 
\
r
1
0
7
T
H
 
A
N
D
 
L
E
X
I
N
G
T
O
N
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
2
0
0
8
 
 
 

1
2
4
0
0
5
 
 
C
o
n
v
e
r
t
i
b
l
e
 
2
B
R
 
a
p
a
r
t
m
e
n
t
 
f
e
a
t
u
r
e
s
 
a
 
b
r
a
n
d
 
n
e
w
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
0
8
 
 
 

1
2
4
0
0
6
 
 
L
e
t
'
s
 
g
e
t
 
y
o
u
 
i
n
 
t
o
 
s
e
e
 
t
h
i
s
 
$
2
,
4
0
0
/
m
o
,
 
r
e
c
e
n
t
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
0
4
7
 
 
 

1
2
4
0
0
7
 
 
C
o
o
p
e
r
C
o
o
p
e
r
.
c
o
m
 
:
:
 
W
e
b
 
I
D
 
#
1
7
1
3
5
7
;
 
A
c
c
e
s
s
 
1
0
0
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
6
8
7
 
 
 

1
2
4
0
1
0
 
 
N
e
w
 
r
e
n
o
v
a
t
e
d
 
B
r
i
g
h
t
 
3
B
r
 
M
u
r
r
a
y
 
H
i
l
l
.
 
3
 
Q
U
E
E
N
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
2
2
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
 
 
l
a
t
i
t
u
d
e
 
 
\

4
 
 
 
 
 
 
 
[
D
i
n
i
n
g
 
R
o
o
m
,
 
P
r
e
-
W
a
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
.
.
.
 
 
 
4
0
.
7
1
0
8
 
 
 

6
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
5
1
3
 
 
 

9
 
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
L
a
u
n
d
.
.
.
 
 
 
4
0
.
7
5
7
5
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
1
4
5
 
 
 

1
5
 
 
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
F
i
t
n
e
s
s
 
C
e
n
t
e
r
,
 
L
a
u
n
d
r
y
 
i
n
.
.
.
 
 
 
4
0
.
7
4
3
9
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
4
0
.
7
9
2
5
 
 
 

1
2
4
0
0
5
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
L
a
u
n
d
r
y
 
i
n
 
B
u
i
l
d
i
n
g
,
 
D
i
s
h
w
.
.
.
 
 
 
4
0
.
7
4
5
6
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
D
o
g
s
 
A
l
l
o
w
e
d
,
 
C
a
t
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
1
6
 
 
 

1
2
4
0
0
7
 
 
 
 
[
D
o
o
r
m
a
n
,
 
E
l
e
v
a
t
o
r
,
 
C
a
t
s
 
A
l
l
o
w
e
d
,
 
D
o
g
s
 
A
l
l
o
w
e
d
]
 
 
 
4
0
.
7
4
8
5
 
 
 

1
2
4
0
1
0
 
 
[
G
a
r
d
e
n
/
P
a
t
i
o
,
 
L
a
u
n
d
r
y
 
i
n
 
U
n
i
t
,
 
D
i
s
h
w
a
s
h
e
r
,
 
H
a
.
.
.
 
 
 
4
0
.
7
4
4
7
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
m
a
n
a
g
e
r
_
i
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
7
1
7
0
3
2
5
 
 
 
-
7
3
.
9
5
3
9
 
 
 
 
 
 
 
 
2
7
6
7
 
 
 

6
 
 
 
 
 
 
 
 
 
 
7
0
9
2
3
4
4
 
 
 
-
7
3
.
9
7
2
2
 
 
 
 
 
 
 
 
2
5
6
5
 
 
 

9
 
 
 
 
 
 
 
 
 
 
7
1
5
8
6
7
7
 
 
 
-
7
3
.
9
6
2
5
 
 
 
 
 
 
 
 
3
4
5
8
 
 
 

1
0
 
 
 
 
 
 
 
 
 
7
2
1
1
2
1
2
 
 
 
-
7
3
.
9
4
2
5
 
 
 
 
 
 
 
 
1
5
6
8
 
 
 

1
5
 
 
 
 
 
 
 
 
 
7
2
2
5
2
9
2
 
 
 
-
7
3
.
9
7
4
3
 
 
 
 
 
 
 
 
 
7
9
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
 
 
 

1
2
4
0
0
3
 
 
 
 
 
6
9
2
8
1
0
8
 
 
 
-
7
3
.
9
4
5
4
 
 
 
 
 
 
 
 
1
2
1
0
 
 
 

1
2
4
0
0
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
 
-
7
3
.
9
7
9
7
 
 
 
 
 
 
 
 
 
7
4
3
 
 
 

1
2
4
0
0
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
 
-
7
3
.
9
8
2
9
 
 
 
 
 
 
 
 
3
9
5
9
 
 
 

1
2
4
0
0
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
 
-
7
3
.
9
8
0
0
 
 
 
 
 
 
 
 
1
8
8
3
 
 
 

1
2
4
0
1
0
 
 
 
 
 
6
8
8
9
3
1
9
 
 
 
-
7
3
.
9
7
4
1
 
 
 
 
 
 
 
 
3
7
3
3
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
p
h
o
t
o
s
 
 
p
r
i
c
e
 
 
\

4
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
7
0
3
2
5
_
3
b
b
5
a
c
8
4
.
.
.
 
 
 
2
4
0
0
 
 
 

6
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
0
9
2
3
4
4
_
7
6
6
3
c
1
9
a
.
.
.
 
 
 
3
8
0
0
 
 
 

9
 
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
1
5
8
6
7
7
_
c
8
9
7
a
1
3
4
.
.
.
 
 
 
3
4
9
5
 
 
 

1
0
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
1
1
2
1
2
_
1
e
d
4
5
4
2
e
.
.
.
 
 
 
3
0
0
0
 
 
 

1
5
 
 
 
 
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
7
2
2
5
2
9
2
_
9
0
1
f
1
9
8
4
.
.
.
 
 
 
2
7
9
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
2
4
0
0
3
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
2
8
1
0
8
_
2
3
1
e
b
9
8
3
.
.
.
 
 
 
1
7
0
0
 
 
 

1
2
4
0
0
5
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
9
0
6
6
7
4
_
9
f
e
8
9
9
a
8
.
.
.
 
 
 
4
1
9
5
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
]
 
 
 
2
4
0
0
 
 
 

1
2
4
0
0
7
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
4
2
1
8
3
_
b
1
f
e
5
1
f
4
.
.
.
 
 
 
6
8
9
5
 
 
 

1
2
4
0
1
0
 
 
[
h
t
t
p
s
:
/
/
p
h
o
t
o
s
.
r
e
n
t
h
o
p
.
c
o
m
/
2
/
6
8
8
9
3
1
9
_
7
9
f
1
8
6
e
7
.
.
.
 
 
 
4
6
9
5
 
 
 


 
 
 
 
 
 
 
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
i
n
t
e
r
e
s
t
_
l
e
v
e
l
 
 
n
u
m
_
p
h
o
t
o
s
 
 
n
u
m
_
f
e
a
t
u
r
e
s
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
3
4
3
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 
 
 
 
 
 
 
 
 
1
2
 
 
 
 
 
 
 
 
 
 
 
 
 
7
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
9
0
0
8
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 
 
 
 
 
 
 
 
 
 
6
 
 
 
 
 
 
 
 
 
 
 
 
 
6
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
6
6
3
4
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 
 
 
 
 
 
 
 
 
 
6
 
 
 
 
 
 
 
 
 
 
 
 
 
6
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
2
3
4
8
4
 
 
 
 
 
 
 
 
 
m
e
d
i
u
m
 
 
 
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
7
0
5
 
 
 
 
 
 
 
 
 
 
 
 
l
o
w
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
4
3
2
1
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
 
 
3
1
1
7
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
 
 
 
 
 
 
 
8
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
2
4
5
8
8
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
2
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
 
1
6
7
6
8
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
8
 
 
 
 
 
 
 
 
 
 
 
 
 
4
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
 
 
1
3
7
5
2
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
8
 
 
 
 
 
 
 
 
 
 
 
 
 
6
 
 
 


 
 
 
 
 
 
 
 
n
u
m
_
d
e
s
c
r
i
p
t
i
o
n
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
7
5
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
2
9
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
1
7
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
9
3
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
3
9
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

1
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
4
6
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
0
7
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
4
0
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
 
 
 
 
 
1
0
0
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
5
6
 
 


[
1
2
4
0
1
1
 
r
o
w
s
 
x
 
1
8
 
c
o
l
u
m
n
s
]
</pre>
f
e
a
t
u
r
e
s
는
 
1
개
의
 
특
징
내
에
 
띄
어
쓰
기
가
 
들
어
가
는
 
경
우
가
 
있
으
므
로
 
이
를
 
'
-
'
로
 
이
어
준
 
후
 
다
른
 
f
e
a
t
u
r
e
간
 
'
 
'
 
띄
어
쓰
기
 
처
리
하
여
 
전
처
리
 
하
였
습
니
다
.




 
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
u
r
e
s
'
]
=
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
u
r
e
s
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
 
"
 
"
.
j
o
i
n
(
[
"
_
"
.
j
o
i
n
(
i
.
s
p
l
i
t
(
)
)
 
f
o
r
 
i
 
i
n
 
x
]
)
)



```python
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
u
r
e
s
'
]
=
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
u
r
e
s
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
 
'
 
'
.
j
o
i
n
(
[
'
_
'
.
j
o
i
n
(
i
.
s
p
l
i
t
(
)
)
 
f
o
r
 
i
 
i
n
 
x
]
)
)

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
u
r
e
s
'
]
[
0
]
```

<pre>
'
E
l
e
v
a
t
o
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
l
d
i
n
g
 
L
a
u
n
d
r
y
_
i
n
_
U
n
i
t
 
D
i
s
h
w
a
s
h
e
r
 
H
a
r
d
w
o
o
d
_
F
l
o
o
r
s
 
O
u
t
d
o
o
r
_
S
p
a
c
e
'
</pre>
f
e
a
t
u
r
e
s
 
c
o
l
u
m
n
은
 
텍
스
트
 
형
식
을
 
지
니
고
 
있
는
데
,
 
텍
스
트
 
데
이
터
의
 
특
징
을
 
추
출
함
으
로
써
 
예
측
 
정
확
도
를
 
높
일
 
수
 
있
습
니
다


[
C
o
u
n
t
V
e
c
t
o
r
i
z
e
r
]




문
서
를
 
토
큰
 
리
스
트
로
 
변
환
한
다
.




각
 
문
서
에
서
 
토
큰
의
 
출
현
 
빈
도
를
 
센
다
.




각
 
문
서
를
 
B
O
W
 
인
코
딩
 
벡
터
로
 
변
환
한
다
.




가
장
 
단
순
한
 
특
징
으
로
,
 
텍
스
트
에
서
 
단
위
별
 
등
장
횟
수
를
 
카
운
팅
하
여
 
수
치
벡
터
화
 
하
는
 
것
입
니
다
.


단
위
는
 
정
하
는
대
로
입
니
다
.




문
서
 
단
위
,
 
문
장
 
단
위
,
 
단
어
 
단
위
.
.
.




가
장
 
많
이
 
사
용
되
는
 
것
은
 
단
어
단
위
의
 
카
운
팅
입
니
다
.




카
운
팅
 
방
법


:
 
텍
스
트
 
카
운
팅
은
 
먼
저
 
단
어
 
사
전
 
벡
터
를
 
만
들
고
,
 
카
운
팅
할
 
문
장
을
 
확
인
하
며
 
그
 
단
어
 
사
전
의
 
횟
수
를
 
카
운
팅
하
는
 
것
입
니
다
.




예
를
들
면
 
단
어
사
전
에




[
나
는
,
 
너
가
,
 
매
일
,
 
공
부
를
,
 
한
다
,
 
좋
아
한
다
]




이
러
한
 
벡
터
가
 
존
재
한
다
면
,




'
나
는
 
매
일
 
공
부
를
 
한
다
'




라
는
 
문
장
을
 
카
운
팅
한
다
면
,




[
1
,
0
,
1
,
1
,
1
,
0
]




이
라
는
 
벡
터
로
 
특
징
을
 
추
출
할
수
 
있
습
니
다
.




'
나
는
 
매
일
 
매
일
 
공
부
를
 
한
다
'




라
는
 
문
장
이
라
면
,




[
1
,
0
,
2
,
1
,
1
,
0
]




이
라
는
 
벡
터
를
 
추
출
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
f
e
a
t
u
r
e
_
e
x
t
r
a
c
t
i
o
n
.
t
e
x
t
 
i
m
p
o
r
t
 
C
o
u
n
t
V
e
c
t
o
r
i
z
e
r

c
v
=
C
o
u
n
t
V
e
c
t
o
r
i
z
e
r
(
)

f
e
a
t
u
r
e
s
=
c
v
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
[
'
f
e
a
t
u
r
e
s
'
]
)
```

[
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
]




C
o
u
n
t
V
e
c
t
o
r
i
z
e
r
는
 
모
든
 
작
업
을
 
메
모
리
 
상
에
서
 
수
행
하
므
로
 
처
리
할
 
문
서
의
 
크
기
가
 
커
지
면
 
속
도
가
 
느
려
지
거
나
 
실
행
이
 
불
가
능
해
진
다
.




이
 
때
 
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
를
 
사
용
하
면
 
해
시
 
함
수
를
 
사
용
하
여
 
단
어
에
 
대
한
 
인
덱
스
 
번
호
를
 
생
성
하
기
 
때
문
에
 
메
모
리
 
및
 
실
행
 
시
간
을
 
줄
일
 
수
 
있
다
.


이
 
데
이
터
에
 
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
를
 
적
용
 
후
 
N
M
F
로
 
차
원
 
축
소
를
 
하
게
 
되
면
 




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
 
N
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
s
 
i
n
 
d
a
t
a
 
p
a
s
s
e
d
 
t
o
 
N
M
F
 
(
i
n
p
u
t
 
X
)
 
에
러
가
 
발
생
합
니
다
.




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




f
e
a
t
u
r
e
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
[
'
f
e
a
t
u
r
e
s
'
]
.
i
l
o
c
[
:
,
:
-
1
]
)




H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
를
 
정
규
화
 
하
더
라
도
 
I
n
d
e
x
i
n
g
E
r
r
o
r
:
 
T
o
o
 
m
a
n
y
 
i
n
d
e
x
e
r
s
 
가
 
발
생
합
니
다
.




따
라
서
 
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
를
 
적
용
하
였
을
 
때
,
 
이
 
데
이
터
는
 
N
M
F
로
 
차
원
 
축
소
가
 
불
가
능
 
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
f
e
a
t
u
r
e
_
e
x
t
r
a
c
t
i
o
n
.
t
e
x
t
 
i
m
p
o
r
t
 
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r

h
v
=
H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
(
)

f
e
a
t
u
r
e
s
=
h
v
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
[
'
f
e
a
t
u
r
e
s
'
]
)
```

[
T
f
i
d
f
V
e
c
t
o
r
i
z
e
r
]




T
F
-
I
D
F
(
T
e
r
m
 
F
r
e
q
u
e
n
c
y
 
–
 
I
n
v
e
r
s
e
 
D
o
c
u
m
e
n
t
 
F
r
e
q
u
e
n
c
y
)
 
인
코
딩
은
 
단
어
를
 
갯
수
 
그
대
로
 
카
운
트
하
지
 
않
고
 
모
든
 
문
서
에
 
공
통
적
으
로
 
들
어
있
는
 
단
어
의
 
경
우
 
문
서
 
구
별
 
능
력
이
 
떨
어
진
다
고
 
보
아
 
가
중
치
를
 
축
소
하
는
 
방
법
이
다
.




구
제
적
으
로
는
 
문
서
 
d
(
d
o
c
u
m
e
n
t
)
와
 
단
어
 
t
 
에
 
대
해
 
다
음
과
 
같
이
 
계
산
한
다
.




t
f
-
i
d
f
(
d
,
t
)
=
t
f
(
d
,
t
)
⋅
i
d
f
(
t
)


여
기
에
서




t
f
(
d
,
t
)
:
 
t
e
r
m
 
f
r
e
q
u
e
n
c
y
.
 
특
정
한
 
단
어
의
 
빈
도
수




i
d
f
(
t
)
 
:
 
i
n
v
e
r
s
e
 
d
o
c
u
m
e
n
t
 
f
r
e
q
u
e
n
c
y
.
 
특
정
한
 
단
어
가
 
들
어
 
있
는
 
문
서
의
 
수
에
 
반
비
례
하
는
 
수




i
d
f
(
d
,
t
)
=
l
o
g
n
1
+
d
f
(
t
)


n
 
:
 
전
체
 
문
서
의
 
수




d
f
(
t
)
:
 
단
어
 
t
를
 
가
진
 
문
서
의
 
수




-
 
T
F
(
T
e
r
m
 
F
r
e
q
u
e
n
c
y
)
 
:
 
특
정
 
단
어
가
 
하
나
의
 
데
이
터
 
안
에
서
 
등
장
하
는
 
횟
수




D
F
(
D
o
c
u
m
e
n
t
 
F
r
e
q
u
e
n
c
y
)
 
:
 
특
정
 
단
어
가
 
여
러
 
데
이
터
에
 
자
주
 
등
장
하
는
지
를
 
알
려
주
는
 
지
표
.




I
D
F
(
I
n
v
e
r
s
e
 
D
o
c
u
m
e
n
t
 
F
r
e
q
u
e
n
c
y
)
 
:
 
D
F
에
 
역
수
를
 
취
해
(
i
n
v
e
r
s
e
)
 
구
함




T
F
-
I
D
F
 
:
 
T
F
와
 
I
D
F
를
 
곱
한
 
값
.
 
즉
 
T
F
가
 
높
고
,
 
D
F
가
 
낮
을
수
록
 
값
이
 
커
지
는
 
것
을
 
이
용
하
는
 
것
입
니
다
.




 
 
 
 
조
금
 
더
 
풀
어
 
설
명
하
자
면
,
 
해
당
 
단
위
(
문
장
)
 
안
에
서
는
 
많
이
 
등
장
하
지
만
,
 
다
른
 
문
서
들
까
지
 
전
체
에
서
는
 
적
게
 
사
용
될
수
록
,




 
 
 
 
분
별
력
 
있
는
 
특
징
이
란
 
것
입
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
f
e
a
t
u
r
e
_
e
x
t
r
a
c
t
i
o
n
.
t
e
x
t
 
i
m
p
o
r
t
 
T
f
i
d
f
V
e
c
t
o
r
i
z
e
r

t
v
=
T
f
i
d
f
V
e
c
t
o
r
i
z
e
r
(
s
t
o
p
_
w
o
r
d
s
=
'
e
n
g
l
i
s
h
'
)

f
e
a
t
u
r
e
s
=
t
v
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
[
"
f
e
a
t
u
r
e
s
"
]
)

f
e
a
t
u
r
e
s
[
2
]
```

<pre>
<
1
x
2
9
8
4
 
s
p
a
r
s
e
 
m
a
t
r
i
x
 
o
f
 
t
y
p
e
 
'
<
c
l
a
s
s
 
'
n
u
m
p
y
.
f
l
o
a
t
6
4
'
>
'

	
w
i
t
h
 
6
 
s
t
o
r
e
d
 
e
l
e
m
e
n
t
s
 
i
n
 
C
o
m
p
r
e
s
s
e
d
 
S
p
a
r
s
e
 
R
o
w
 
f
o
r
m
a
t
>
</pre>
*
차
원
축
소
*




차
원
 
축
소
는
 
단
순
히
 
데
이
터
의
 
압
축
을
 
의
미
하
는
 
것
이
 
아
닌
,
 
좀
 
더
 
데
이
터
를
 
잘
 
설
명
할
 
수
 
있
는
 
잠
재
적
인
 
요
소
를
 
추
출
하
는
 
것
.




텍
스
트
 
데
이
터
의
 
경
우
 
숨
겨
진
 
의
미
를
 
추
출
하
는
 
것
.
 
텍
스
트
 
데
이
터
에
는
 
많
은
 
단
어
로
 
구
성
되
어
 
있
고
,
 
어
떤
 
의
미
나
 
의
도
를
 
내
포
함
에
 
따
라
 
단
어
를
 
사
용
하
게
 
됩
니
다
.




사
람
의
 
경
우
 
문
서
를
 
읽
으
며
 
의
미
나
 
의
도
를
 
인
지
하
는
데
 
차
원
 
축
소
 
알
고
리
즘
은
 
문
서
 
내
 
단
어
들
의
 
구
성
에
서
 
숨
겨
져
 
있
는
 
시
맨
틱
(
S
e
m
a
n
t
i
c
)
의
미
나
 
토
픽
(
T
o
p
i
c
)
을
 
잠
재
요
소
로
 
간
주
하
고
 
이
를
 
찾
아
낼
 
수
 
있
습
니
다
.


[
P
C
A
]


여
러
 
변
수
 
간
에
 
존
재
하
는
 
상
관
관
계
를
 
이
용
해
 
이
를
 
대
표
하
는
 
주
성
분
(
P
r
i
n
c
i
p
a
l
 
C
o
m
p
o
n
e
n
t
)
을
 
추
출
해
 
차
원
을
 
축
소
하
는
 
기
법
입
니
다
.




P
C
A
로
 
차
원
을
 
축
소
할
 
때
는
 
기
존
 
데
이
터
의
 
정
보
 
유
실
이
 
최
소
화
 
되
며
 
이
를
 
위
해
 
P
C
A
는
 
가
장
 
높
은
 
분
산
을
 
가
지
는
 
데
이
터
의
 
축
을
 
찾
아
 
이
 
축
으
로
 
차
원
을
 
축
소
하
는
데
,
 
이
것
이
 
P
C
A
의
 
주
성
분
이
 
됩
니
다
.
 
(
즉
,
 
분
산
이
 
데
이
터
의
 
특
성
을
 
가
장
 
잘
 
나
타
내
는
 
것
으
로
 
간
주
합
니
다
.
)




P
C
A
는
 
제
일
 
먼
저
 
가
장
 
큰
 
데
이
터
 
변
동
성
(
V
a
r
i
a
n
c
e
)
을
 
기
반
으
로
 
첫
 
번
째
 
벡
터
 
축
을
 
생
성
하
고
,
 
두
 
번
째
 
축
은
 
이
 
벡
터
 
축
에
 
직
각
이
 
되
는
 
벡
터
 
(
직
교
 
벡
터
)
를
 
축
으
로
 
합
니
다
.




세
번
째
 
축
은
 
다
시
 
두
 
번
째
 
축
과
 
직
각
이
 
되
는
 
벡
터
를
 
설
정
하
는
 
방
식
으
로
 
축
을
 
생
성
합
니
다
.




이
렇
게
 
생
성
된
 
벡
터
 
축
에
 
원
본
 
데
이
터
를
 
투
영
하
면
 
벡
터
 
축
의
 
개
수
만
큼
의
 
차
원
으
로
 
원
본
 
데
이
터
가
 
차
원
 
축
소
됩
니
다
.




입
력
 
데
이
터
의
 
공
분
산
 
행
렬
이
 
고
유
벡
터
와
 
고
유
값
으
로
 
분
해
될
 
수
 
있
으
며
,
 
이
렇
게
 
분
해
된
 
고
유
벡
터
를
 
이
용
해
 
입
력
 
데
이
터
를
 
선
형
 
변
환
하
는
 
방
식
이
 
P
C
A
라
는
 
것
입
니
다
.




보
통
 
P
C
A
는
 
다
음
과
 
같
은
 
스
텝
으
로
 
수
행
됩
니
다
.




1
.
 
입
력
 
데
이
터
 
세
트
의
 
공
분
산
 
행
렬
을
 
생
성
합
니
다
.




2
.
 
공
분
산
 
행
렬
의
 
고
유
벡
터
와
 
고
유
값
을
 
계
산
합
니
다
.




3
.
 
고
유
값
이
 
가
장
 
큰
 
순
으
로
 
K
개
(
P
C
A
 
변
환
 
차
수
만
큼
)
만
큼
 
고
유
벡
터
를
 
추
출
합
니
다
.




4
.
 
고
유
값
이
 
가
장
 
큰
 
순
으
로
 
추
출
된
 
고
유
벡
터
를
 
이
용
해
 
새
롭
게
 
입
력
 
데
이
터
를
 
변
환
합
니
다
.




P
C
A
는
 
많
은
 
속
성
으
로
 
구
성
된
 
원
본
 
데
이
터
를
 
그
 
핵
심
을
 
구
성
하
는
 
데
이
터
로
 
압
축
한
 
것
입
니
다
.




원
본
 
데
이
터
 
세
트
 
대
비
 
예
측
 
정
확
도
는
 
P
C
A
 
변
환
 
차
원
 
개
수
에
 
따
라
 
예
측
 
성
능
이
 
떨
어
질
 
수
 
밖
에
 
없
습
니
다
.
 
보
통
 
차
원
이
 
감
소
하
면
서
 
예
측
 
성
능
의
 
정
확
도
가
 
원
본
 
데
이
터
 
대
비
 
하
락
합
니
다
.




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
d
e
c
o
m
p
o
s
i
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
 
P
C
A




p
c
a
=
P
C
A
(
n
_
c
o
m
p
o
n
e
n
t
s
=
1
0
)




f
e
a
t
u
r
e
s
_
d
e
c
=
p
c
a
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
f
e
a
t
u
r
e
s
)




f
e
a
t
u
r
e
s
_
d
e
c




결
과
 
:
 
 
T
y
p
e
E
r
r
o
r
:
 
P
C
A
 
d
o
e
s
 
n
o
t
 
s
u
p
p
o
r
t
 
s
p
a
r
s
e
 
i
n
p
u
t
.
 
S
e
e
 
T
r
u
n
c
a
t
e
d
S
V
D
 
f
o
r
 
a
 
p
o
s
s
i
b
l
e
 
a
l
t
e
r
n
a
t
i
v
e
.




해
결
하
고
자
 
P
C
A
 
차
원
 
축
소
 
바
로
 
이
전
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
를
 
이
용
해
 
평
균
이
 
0
,
 
분
산
이
 
1
인
 
표
준
 
정
규
 
분
포
로
 
변
경
하
고
자
 
하
였
습
니
다
.




P
C
A
를
 
적
용
하
기
 
전
에
 
개
별
 
속
성
을
 
함
께
 
스
케
일
링
해
야
 
합
니
다
.
 
P
C
A
는
 
여
러
 
속
성
의
 
값
을
 
연
산
해
야
 
하
므
로
 
속
성
의
 
스
케
일
에
 
영
향
을
 
받
습
니
다
.




따
라
서
 
여
러
 
속
성
을
 
P
C
A
로
 
압
축
하
기
 
전
에
 
각
 
속
성
값
을
 
동
일
한
 
스
케
일
로
 
변
환
하
는
 
것
이
 
필
요
합
니
다
.
 
사
이
킷
런
의
 
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
를
 
이
용
해
 
평
균
이
 
0
,
 
분
산
이
 
1
인
 
표
준
 
정
규
 
분
포
로
 
데
이
터
 
세
트
의
 
속
성
값
들
을
 
변
환
합
니
다
.




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




f
e
a
t
u
r
e
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
[
'
f
e
a
t
u
r
e
s
'
]
.
i
l
o
c
[
:
,
:
-
1
]
)




'
t
o
o
 
m
a
n
y
 
i
n
d
e
x
r
s
'
라
는
 
e
r
r
o
r
가
 
발
생
하
여
 
데
이
터
가
 
많
은
 
이
 
경
우
에
는
 
적
합
치
 
않
아
 
보
입
니
다



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


#
 
f
e
a
t
u
r
e
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
[
'
f
e
a
t
u
r
e
s
'
]
.
i
l
o
c
[
:
,
:
-
1
]
)


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
d
e
c
o
m
p
o
s
i
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
 
P
C
A


#
 
p
c
a
=
P
C
A
(
n
_
c
o
m
p
o
n
e
n
t
s
=
2
)


#
 
f
e
a
t
u
r
e
s
_
d
e
c
=
p
c
a
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
f
e
a
t
u
r
e
s
)


#
 
f
e
a
t
u
r
e
s
_
d
e
c
```

[
L
D
A
]




L
D
A
(
L
i
n
e
a
r
 
D
i
s
c
r
i
m
i
n
a
n
t
 
A
n
a
l
y
s
i
s
)
는
 
선
형
 
판
별
 
분
석
법
으
로
 
불
리
며
,
 
P
C
A
와
 
매
우
 
유
사
합
니
다
.




L
D
A
는
 
P
C
A
와
 
유
사
하
게
 
입
력
 
데
이
터
 
세
트
를
 
저
차
원
 
공
간
에
 
투
영
해
 
차
원
을
 
축
소
하
는
 
기
법
이
지
만
,
 
중
요
한
 
차
이
는
 
L
D
A
는
 
지
도
학
습
의
 
분
류
(
C
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
)
에
서
 
사
용
하
기
 
쉽
도
록
 
개
별
 
클
래
스
를
 
분
별
할
 
수
 
있
는
 
기
준
을
 
최
대
한
 
유
지
하
면
서
 
차
원
을
 
축
소
합
니
다
.




P
C
A
는
 
입
력
 
데
이
터
의
 
변
동
성
의
 
가
장
 
큰
 
축
을
 
찾
았
지
만
,
 
L
D
A
는
 
입
력
 
데
이
터
의
 
결
정
 
값
 
클
래
스
를
 
최
대
한
 
분
리
할
 
수
 
있
는
 
축
을
 
찾
습
니
다
.




L
D
A
는
 
특
정
 
공
간
상
에
서
 
클
래
스
 
분
리
를
 
최
대
화
하
는
 
축
을
 
찾
기
 
위
해
 
클
래
스
 
간
 
분
산
과
 
클
래
스
 
내
부
 
분
산
의
 
비
율
을
 
최
대
화
하
는
 
방
식
으
로
 
차
원
을
 
축
소
합
니
다
.




즉
,
 
클
래
스
 
간
 
분
산
은
 
최
대
한
 
크
게
 
가
져
가
고
,
 
클
래
스
 
내
부
의
 
분
산
은
 
최
대
한
 
작
게
 
가
져
가
는
 
방
시
깁
니
다
.




일
반
적
으
로
 
L
D
A
를
 
구
하
는
 
스
텝
은
 
P
C
A
와
 
유
사
하
나
 
가
장
 
큰
 
차
이
점
은
 
공
분
산
 
행
렬
이
 
아
니
라
 
위
에
 
설
명
한
 
클
래
스
 
간
 
분
산
과
 
클
래
스
 
내
부
 
분
산
 
행
렬
을
 
생
성
한
 
뒤
,
 
이
 
행
렬
에
 
기
반
해
 
고
유
벡
터
를
 
구
하
고
 
입
력
 
데
이
터
를
 
투
영
한
다
는
 
점
입
니
다
.




L
D
A
를
 
구
하
는
 
스
텝
은
 
다
음
과
 
같
습
니
다
.




1
.
 
클
래
스
 
내
부
와
 
클
래
스
 
간
 
분
산
 
행
렬
을
 
구
합
니
다
.
 
이
 
두
 
개
의
 
행
렬
은
 
입
력
 
데
이
터
의
 
결
정
 
값
 
클
래
스
별
로
 
개
별
 
피
치
의
 
평
균
 
벡
터
(
m
e
a
n
 
v
e
c
t
o
r
)
를
 
기
반
으
로
 
구
합
니
다
.




2
.
 
고
유
값
이
 
가
장
 
큰
 
순
으
로
 
K
개
(
L
D
A
 
변
환
 
차
수
 
만
큼
)
 
추
출
합
니
다
.




3
.
 
고
유
값
이
 
가
장
 
큰
 
순
으
로
 
추
출
된
 
고
유
벡
터
를
 
이
용
해
 
새
롭
게
 
입
력
 
데
이
터
를
 
변
환
합
니
다
.




P
C
A
와
 
다
르
기
 
L
D
A
에
서
 
한
 
가
지
 
유
의
해
야
 
할
 
점
은
 
L
D
A
는
 
실
제
로
는
 
P
C
A
와
 
다
르
게
 
비
지
도
학
습
이
 
아
닌
 
지
도
학
습
이
라
는
 
것
입
니
다
.




즉
,
 
클
래
스
의
 
결
정
값
이
 
변
환
 
시
에
 
필
요
합
니
다
.
 
L
D
A
 
객
체
의
 
f
i
t
(
)
 
메
서
드
를
 
호
출
할
 
때
 
결
정
값
이
 
입
력
됐
음
에
 
유
의
하
세
요
.




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
d
i
s
c
r
i
m
i
n
a
n
t
_
a
n
a
l
y
s
i
s
 
i
m
p
o
r
t
 
L
i
n
e
a
r
D
i
s
c
r
i
m
i
n
a
n
t
A
n
a
l
y
s
i
s




l
d
a
=
L
i
n
e
a
r
D
i
s
c
r
i
m
i
n
a
n
t
A
n
a
l
y
s
i
s
(
n
_
c
o
m
p
o
n
e
n
t
s
=
1
0
)




f
e
a
t
u
r
e
s
_
d
e
c
=
l
d
a
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
f
e
a
t
u
r
e
s
,
t
r
a
i
n
[
'
i
n
t
e
r
e
s
t
_
l
e
v
e
l
'
]
)




f
e
a
t
u
r
e
s
_
d
e
c




T
y
p
e
E
r
r
o
r
:
 
A
 
s
p
a
r
s
e
 
m
a
t
r
i
x
 
w
a
s
 
p
a
s
s
e
d
,
 
b
u
t
 
d
e
n
s
e
 
d
a
t
a
 
i
s
 
r
e
q
u
i
r
e
d
.
 
U
s
e
 
X
.
t
o
a
r
r
a
y
(
)
 
t
o
 
c
o
n
v
e
r
t
 
t
o
 
a
 
d
e
n
s
e
 
n
u
m
p
y
 
a
r
r
a
y
.




t
e
x
t
데
이
터
를
 
온
전
히
 
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
 
처
럼
 
기
준
을
 
잡
기
에
 
부
적
합
해
 
보
입
니
다
.
 
(
데
이
터
 
또
한
 
양
이
 
방
대
하
여
 
L
D
A
를
 
적
용
하
기
 
어
렵
습
니
다
.
)


[
T
r
u
n
c
a
t
e
d
S
V
D
]


S
V
D
 
역
시
 
P
C
A
와
 
유
사
한
 
행
렬
 
분
해
 
기
법
을
 
이
용
합
니
다
.




P
C
A
의
 
경
우
 
정
방
행
렬
(
즉
,
 
행
과
 
열
의
 
크
기
가
 
같
은
 
행
렬
)
만
을
 
고
유
 
벡
터
로
 
분
해
할
 
수
 
있
지
만
,
 
S
V
D
는
 
정
방
행
렬
뿐
만
 
아
니
라
 
행
과
 
열
의
 
크
기
가
 
다
른
 
행
렬
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




일
반
적
으
로
 
S
V
D
는
 
m
 
X
 
n
 
크
기
의
 
행
렬
 
A
를
 
다
음
과
 
같
이
 
분
해
하
는
 
것
을
 
의
미
합
니
다
.
 
파
이
썬
 
책
 
(
3
9
6
P
)




S
V
D
는
 
특
이
값
 
분
해
로
 
불
리
며
,
 
행
렬
 
U
와
 
V
에
 
속
한
 
벡
터
는
 
특
이
벡
터
(
s
i
n
g
u
l
a
r
 
v
e
c
t
o
r
)
이
며
,
 
모
든
 
특
이
 
벡
터
는
 
서
로
 
직
교
하
는
 
성
질
을
 
가
집
니
다
.




s
u
m
은
 
대
각
행
렬
이
며
,
 
행
렬
의
 
대
각
에
 
위
치
한
 
값
만
 
0
이
 
아
니
고
 
나
머
지
 
위
치
의
 
값
은
 
모
두
 
0
입
니
다
.




s
u
m
이
 
위
치
한
 
0
이
 
아
닌
 
값
이
 
바
로
 
행
렬
 
A
의
 
특
이
값
입
니
다
.




S
V
D
는
 
A
의
 
차
원
이
 
m
 
X
 
n
 
일
때
 
U
의
 
차
원
이
 
m
 
X
 
m
 
,
 
s
u
m
의
 
 
차
원
이
 
m
 
X
 
n
,
 
V
의
 
T
제
곱
의
 
차
원
이
 
n
 
X
 
n
으
로
 
분
해
합
니
다
.




하
지
만
 
일
반
적
으
로
는
 
다
음
과
 
같
이
 
s
u
m
의
 
비
대
각
인
 
부
분
과
 
대
각
우
너
소
 
중
에
 
특
이
값
이
 
0
인
 
부
분
도
 
모
두
 
제
거
하
고
 
제
거
된
 
s
u
m
에
 
대
응
되
는
 
U
와
 
V
 
원
소
도
 
함
께
 
제
거
해
 
차
원
을
 
줄
인
 
형
태
로
 
S
V
D
를
 
적
용
합
니
다
.




이
렇
게
 
컴
팩
트
한
 
형
태
로
 
S
V
D
를
 
적
용
하
면
 
A
의
 
차
원
이
 
m
 
X
 
n
일
 
때
,
 
U
의
 
차
원
을
 
m
 
X
 
p
,
 
s
u
m
의
 
차
원
을
 
p
 
X
 
p
,
 
V
의
 
T
제
곱
의
 
차
원
을
 
p
 
X
 
n
으
로
 
분
해
합
니
다
.




T
r
u
n
c
a
t
e
d
 
S
V
D
는
 
S
U
M
의
 
대
각
원
소
 
중
에
 
상
위
 
몇
 
개
만
 
추
출
해
서
 
여
기
에
 
대
응
하
는
 
U
와
 
V
의
 
원
소
도
 
함
께
 
제
거
해
 
더
욱
 
차
원
을
 
줄
인
 
형
태
로
 
분
해
하
는
 
것
입
니
다
.




일
반
적
인
 
S
V
D
는
 
보
통
 
넘
파
이
나
 
사
이
파
이
 
라
이
브
러
리
를
 
이
용
해
 
수
행
합
니
다
.




T
r
u
n
c
a
t
e
d
 
S
V
D
는
 
s
u
m
 
행
렬
에
 
있
는
 
대
각
원
소
,
 
즉
 
특
이
값
 
중
 
상
위
 
일
부
 
데
이
터
만
 
추
출
해
 
분
해
하
는
 
방
식
입
니
다
.
 
이
렇
게
 
분
해
하
면
 
인
위
적
으
로
 
더
 
작
은
 
차
원
의
 
U
,
 
S
U
M
,
 
V
의
 
T
제
곱
으
로
 
분
해
하
기
 
때
문
에
 
원
본
 
행
렬
을
 
정
확
하
게
 
다
시
 
원
상
복
귀
할
 
수
는
 
없
습
니
다
.




하
지
만
 
데
이
터
 
정
보
가
 
압
축
되
어
 
분
해
됨
에
도
 
불
구
하
고
 
상
당
한
 
수
준
으
로
 
원
본
 
행
렬
을
 
근
사
할
 
수
 
있
습
니
다
.




사
이
킷
런
의
 
t
R
U
N
C
A
T
E
D
s
v
d
 
클
래
스
는
 
사
이
파
이
의
 
s
v
d
s
와
 
같
이
 
T
r
u
n
c
a
t
e
d
 
S
V
D
 
연
산
을
 
수
행
해
 
원
본
 
행
렬
을
 
분
해
한
 
U
,
 
S
i
g
m
a
,
 
V
t
 
행
렬
을
 
반
환
하
는
 
않
습
니
다
.




사
이
킷
런
의
 
T
r
u
n
c
a
t
e
d
S
V
D
 
클
래
스
는
 
P
C
A
 
클
래
스
와
 
유
사
하
게
 
f
i
t
(
)
와
 
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
)
을
 
호
출
해
 
원
본
 
데
이
터
를
 
몇
 
개
의
 
주
요
 
컴
포
넌
트
(
즉
,
 
T
r
u
n
c
a
t
e
d
 
S
V
D
의
 
K
 
컴
포
넌
트
 
수
)
로
 
차
원
을
 
축
소
해
 
변
환
합
니
다
.




P
C
A
는
 
밀
집
 
행
렬
(
D
e
n
s
e
 
M
a
t
r
i
x
)
에
 
대
한
 
변
환
만
 
가
능
하
며
 
S
V
D
는
 
희
소
 
행
렬
(
S
p
a
r
s
e
 
M
a
t
r
i
x
)
에
 
대
한
 
변
환
도
 
가
능
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
d
e
c
o
m
p
o
s
i
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
 
T
r
u
n
c
a
t
e
d
S
V
D

s
v
d
=
T
r
u
n
c
a
t
e
d
S
V
D
(
n
_
c
o
m
p
o
n
e
n
t
s
=
1
0
)

f
e
a
t
u
r
e
s
_
d
e
c
=
s
v
d
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
f
e
a
t
u
r
e
s
)

f
e
a
t
u
r
e
s
_
d
e
c
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
 
0
.
6
4
8
1
9
3
5
8
,
 
 
0
.
2
2
6
8
2
9
7
 
,
 
 
0
.
4
3
4
2
2
1
8
1
,
 
.
.
.
,
 
-
0
.
1
9
3
3
0
3
1
6
,

 
 
 
 
 
 
 
 
 
0
.
0
8
6
8
4
5
5
7
,
 
-
0
.
0
5
5
7
2
7
8
7
]
,

 
 
 
 
 
 
 
[
 
0
.
7
4
9
2
5
6
2
8
,
 
-
0
.
4
8
3
0
1
1
0
6
,
 
-
0
.
0
0
9
9
8
8
5
9
,
 
.
.
.
,
 
 
0
.
0
1
1
2
2
0
2
1
,

 
 
 
 
 
 
 
 
 
0
.
0
1
2
8
8
6
5
2
,
 
-
0
.
1
0
8
1
7
6
2
9
]
,

 
 
 
 
 
 
 
[
 
0
.
6
7
5
9
1
4
1
 
,
 
-
0
.
4
4
9
6
5
0
6
7
,
 
 
0
.
0
0
3
4
0
2
7
6
,
 
.
.
.
,
 
 
0
.
2
8
7
7
5
8
3
7
,

 
 
 
 
 
 
 
 
 
0
.
3
0
1
7
8
0
2
2
,
 
-
0
.
0
8
6
1
4
2
5
 
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
 
0
.
4
8
5
6
7
8
3
4
,
 
 
0
.
7
3
3
9
1
3
8
1
,
 
-
0
.
3
8
4
1
7
8
7
2
,
 
.
.
.
,
 
-
0
.
0
7
2
8
2
0
7
7
,

 
 
 
 
 
 
 
 
 
0
.
0
5
4
1
0
5
7
6
,
 
-
0
.
0
5
1
8
5
5
5
5
]
,

 
 
 
 
 
 
 
[
 
0
.
6
6
6
2
6
4
9
4
,
 
 
0
.
4
0
3
3
9
0
6
7
,
 
-
0
.
4
1
0
2
4
9
1
6
,
 
.
.
.
,
 
 
0
.
2
0
2
6
4
5
0
3
,

 
 
 
 
 
 
 
 
-
0
.
1
4
8
6
5
6
7
9
,
 
-
0
.
1
1
4
6
6
4
1
8
]
,

 
 
 
 
 
 
 
[
 
0
.
4
1
5
4
9
0
4
7
,
 
 
0
.
0
3
8
7
5
0
4
5
,
 
-
0
.
0
6
2
0
0
7
6
1
,
 
.
.
.
,
 
 
0
.
0
1
2
2
5
7
6
7
,

 
 
 
 
 
 
 
 
-
0
.
0
6
4
5
4
4
8
 
,
 
-
0
.
0
7
9
1
8
9
1
 
]
]
)
</pre>
[
N
M
F
]




N
M
F
는
 
T
r
u
n
c
a
t
e
d
 
S
V
D
와
 
같
이
 
낮
은
 
랭
크
를
 
통
한
 
행
렬
 
근
사
(
L
o
w
-
R
a
n
k
 
A
p
p
r
o
x
i
m
a
t
i
o
n
)
 
방
식
의
 
변
형
입
니
다
.




N
M
F
는
 
원
본
 
행
렬
 
내
의
 
모
든
 
원
소
 
값
이
 
모
두
 
양
수
(
0
 
이
상
)
라
는
 
게
 
보
장
되
면
 
좀
 
더
 
간
단
하
게
 
두
 
개
의
 
기
반
 
양
수
 
행
렬
로
 
분
해
될
 
수
 
있
는
 
기
법
을
 
지
칭
합
니
다
.




V
(
4
X
6
)
 
근
사
값
은
 
W
(
4
X
2
)
 
X
 
H
(
2
X
6
)




행
렬
 
분
해
(
M
a
t
r
i
x
 
F
a
c
t
o
r
i
z
a
t
i
o
n
)
는
 
일
반
적
으
로
 
S
V
D
와
 
같
은
 
행
렬
 
분
해
 
기
법
을
 
통
칭
하
는
 
것
입
니
다
.




이
처
럼
 
행
렬
 
분
해
를
 
하
게
 
되
면
 
W
 
행
렬
과
 
H
 
행
렬
은
 
일
반
적
으
로
 
길
고
 
가
는
 
행
렬
 
W
(
즉
,
 
원
본
 
행
렬
의
 
행
 
크
기
와
 
같
고
 
열
 
크
기
 
보
다
 
작
은
 
행
렬
)
와
 
작
고
 
넓
은
 
행
렬
 
H
(
원
본
 
행
렬
의
 
행
 
크
기
보
다
 
작
고
 
열
 
크
기
와
 
같
은
 
행
렬
)
로
 
분
해
됩
니
다
.




이
렇
게
 
분
해
된
 
행
렬
은
 
잠
재
 
요
소
를
 
특
성
으
로
 
가
지
게
 
됩
니
다
.




분
해
 
행
렬
 
W
는
 
원
본
 
행
에
 
대
해
서
 
이
 
잠
재
 
요
소
의
 
값
이
 
얼
마
나
 
되
는
지
에
 
대
응
하
며
,
 
분
해
 
행
렬
 
H
는
 
이
 
잠
재
 
요
소
가
 
원
본
 
열
(
즉
,
 
원
본
 
속
성
)
로
 
어
떻
게
 
구
성
됐
는
지
를
 
나
타
내
는
 
행
렬
입
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
d
e
c
o
m
p
o
s
i
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
 
N
M
F

n
m
f
=
N
M
F
(
n
_
c
o
m
p
o
n
e
n
t
s
=
1
0
)

f
e
a
t
u
r
e
s
_
d
e
c
=
n
m
f
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
f
e
a
t
u
r
e
s
)

f
e
a
t
u
r
e
s
_
d
e
c
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
k
l
e
a
r
n
/
d
e
c
o
m
p
o
s
i
t
i
o
n
/
_
n
m
f
.
p
y
:
2
9
4
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
 
T
h
e
 
'
i
n
i
t
'
 
v
a
l
u
e
,
 
w
h
e
n
 
'
i
n
i
t
=
N
o
n
e
'
 
a
n
d
 
n
_
c
o
m
p
o
n
e
n
t
s
 
i
s
 
l
e
s
s
 
t
h
a
n
 
n
_
s
a
m
p
l
e
s
 
a
n
d
 
n
_
f
e
a
t
u
r
e
s
,
 
w
i
l
l
 
b
e
 
c
h
a
n
g
e
d
 
f
r
o
m
 
'
n
n
d
s
v
d
'
 
t
o
 
'
n
n
d
s
v
d
a
'
 
i
n
 
1
.
1
 
(
r
e
n
a
m
i
n
g
 
o
f
 
0
.
2
6
)
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
,

</pre>
<pre>
a
r
r
a
y
(
[
[
3
.
5
3
9
8
2
9
6
9
e
-
0
2
,
 
3
.
6
4
3
6
4
7
9
4
e
-
0
2
,
 
5
.
6
2
4
8
4
6
8
8
e
-
0
2
,
 
.
.
.
,

 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
2
.
1
4
6
6
2
2
8
8
e
-
0
2
,
 
1
.
7
8
2
5
6
0
8
1
e
-
0
4
]
,

 
 
 
 
 
 
 
[
4
.
6
7
0
0
0
2
4
9
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
.
.
.
,

 
 
 
 
 
 
 
 
4
.
7
3
9
1
9
1
2
4
e
-
0
2
,
 
4
.
0
6
8
9
0
9
9
1
e
-
0
3
,
 
3
.
7
0
0
1
8
7
2
3
e
-
0
4
]
,

 
 
 
 
 
 
 
[
4
.
1
8
8
7
4
3
1
6
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
.
.
.
,

 
 
 
 
 
 
 
 
4
.
3
4
9
2
4
4
3
4
e
-
0
2
,
 
4
.
9
6
0
0
8
4
6
3
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
9
.
5
3
0
2
7
8
8
7
e
-
0
2
,
 
1
.
7
6
6
9
7
1
0
3
e
-
0
5
,
 
.
.
.
,

 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
]
,

 
 
 
 
 
 
 
[
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
6
.
7
6
4
5
6
2
8
7
e
-
0
2
,
 
1
.
1
3
9
7
3
1
4
0
e
-
0
5
,
 
.
.
.
,

 
 
 
 
 
 
 
 
5
.
9
9
1
2
4
9
7
0
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
]
,

 
 
 
 
 
 
 
[
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
3
.
2
0
6
6
1
2
6
2
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
.
.
.
,

 
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
,
 
5
.
4
3
8
5
0
2
8
6
e
-
0
2
,
 
0
.
0
0
0
0
0
0
0
0
e
+
0
0
]
]
)
</pre>
v
e
c
t
o
r
i
z
e
r
후
 
차
원
 
축
소
된
 
1
0
개
의
 
값
을
 
a
l
l
d
a
t
a
의
 
c
o
l
u
m
n
으
로
 
넣
어
줍
니
다
.



```python
f
o
r
 
i
 
i
n
 
r
a
n
g
e
(
1
0
)
:

 
 
 
 
a
l
l
d
a
t
a
[
"
f
e
a
t
u
r
e
s
_
d
e
c
"
 
+
 
s
t
r
(
i
)
]
=
f
e
a
t
u
r
e
s
_
d
e
c
[
:
,
i
]

 
 
 
 

d
i
s
p
l
a
y
(
a
l
l
d
a
t
a
,
a
l
l
d
a
t
a
.
c
o
l
u
m
n
s
)
```

<pre>
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
r
e
a
t
e
d
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
6
0
8
3
 
 
2
0
1
6
-
0
6
-
1
6
 
0
5
:
5
5
:
2
7
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
8
4
1
7
 
 
2
0
1
6
-
0
6
-
0
1
 
0
5
:
4
4
:
3
3
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
3
4
4
 
 
2
0
1
6
-
0
6
-
1
4
 
1
5
:
1
9
:
5
9
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
1
.
5
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
3
7
9
7
 
 
2
0
1
6
-
0
6
-
2
4
 
0
7
:
5
4
:
2
4
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
8
7
1
7
 
 
2
0
1
6
-
0
6
-
2
8
 
0
3
:
5
0
:
2
3
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
8
6
2
3
 
 
2
0
1
6
-
0
4
-
2
6
 
1
6
:
0
9
:
5
5
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
6
6
0
0
 
 
2
0
1
6
-
0
4
-
2
1
 
0
5
:
0
6
:
1
9
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
2
0
1
6
-
0
4
-
2
0
 
0
1
:
3
1
:
5
2
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
1
3
1
 
 
2
0
1
6
-
0
4
-
0
8
 
0
2
:
2
6
:
4
5
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
1
2
0
5
 
 
2
0
1
6
-
0
4
-
1
8
 
0
2
:
5
1
:
2
1
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
d
e
s
c
r
i
p
t
i
o
n
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
\

4
 
 
 
 
 
 
 
S
p
a
c
i
o
u
s
 
1
 
B
e
d
r
o
o
m
 
1
 
B
a
t
h
r
o
o
m
 
i
n
 
W
i
l
l
i
a
m
s
b
u
r
g
!
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
1
8
8
7
 
 
 

6
 
 
 
 
 
 
 
B
R
A
N
D
 
N
E
W
 
G
U
T
 
R
E
N
O
V
A
T
E
D
 
T
R
U
E
 
2
 
B
E
D
R
O
O
M
F
i
n
d
 
y
o
u
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
8
4
8
 
 
 

9
 
 
 
 
 
 
 
*
*
F
L
E
X
 
2
 
B
E
D
R
O
O
M
 
W
I
T
H
 
F
U
L
L
 
P
R
E
S
S
U
R
I
Z
E
D
 
W
A
L
L
*
*
L
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
9
0
4
 
 
 

1
0
 
 
 
 
 
 
A
 
B
r
a
n
d
 
N
e
w
 
3
 
B
e
d
r
o
o
m
 
1
.
5
 
b
a
t
h
 
A
p
a
r
t
m
e
n
t
E
n
j
o
y
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
2
8
2
 
 
 

1
5
 
 
 
 
 
 
O
v
e
r
-
s
i
z
e
d
 
S
t
u
d
i
o
 
w
 
a
b
u
n
d
a
n
t
 
c
l
o
s
e
t
s
.
 
A
v
a
i
l
a
b
l
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
0
7
9
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
 
 
 

1
2
4
0
0
3
 
 
B
R
A
N
D
 
N
E
W
 
T
O
 
M
A
R
K
E
T
 
1
B
D
R
 
\
r
1
0
7
T
H
 
A
N
D
 
L
E
X
I
N
G
T
O
N
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
2
0
0
8
 
 
 

1
2
4
0
0
5
 
 
C
o
n
v
e
r
t
i
b
l
e
 
2
B
R
 
a
p
a
r
t
m
e
n
t
 
f
e
a
t
u
r
e
s
 
a
 
b
r
a
n
d
 
n
e
w
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
0
8
 
 
 

1
2
4
0
0
6
 
 
L
e
t
'
s
 
g
e
t
 
y
o
u
 
i
n
 
t
o
 
s
e
e
 
t
h
i
s
 
$
2
,
4
0
0
/
m
o
,
 
r
e
c
e
n
t
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
0
4
7
 
 
 

1
2
4
0
0
7
 
 
C
o
o
p
e
r
C
o
o
p
e
r
.
c
o
m
 
:
:
 
W
e
b
 
I
D
 
#
1
7
1
3
5
7
;
 
A
c
c
e
s
s
 
1
0
0
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
1
2
6
8
7
 
 
 

1
2
4
0
1
0
 
 
N
e
w
 
r
e
n
o
v
a
t
e
d
 
B
r
i
g
h
t
 
3
B
r
 
M
u
r
r
a
y
 
H
i
l
l
.
 
3
 
Q
U
E
E
N
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
2
2
 
 
 


 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
 
 
l
a
t
i
t
u
d
e
 
 
\

4
 
 
 
 
 
 
 
D
i
n
i
n
g
_
R
o
o
m
 
P
r
e
-
W
a
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
l
d
i
n
g
 
D
i
s
h
w
a
.
.
.
 
 
 
4
0
.
7
1
0
8
 
 
 

6
 
 
 
 
 
 
 
D
o
o
r
m
a
n
 
E
l
e
v
a
t
o
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
l
d
i
n
g
 
D
i
s
h
w
a
s
h
e
.
.
.
 
 
 
4
0
.
7
5
1
3
 
 
 

9
 
 
 
 
 
 
 
D
o
o
r
m
a
n
 
E
l
e
v
a
t
o
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
l
d
i
n
g
 
L
a
u
n
d
r
y
_
i
.
.
.
 
 
 
4
0
.
7
5
7
5
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
4
0
.
7
1
4
5
 
 
 

1
5
 
 
 
 
 
 
D
o
o
r
m
a
n
 
E
l
e
v
a
t
o
r
 
F
i
t
n
e
s
s
_
C
e
n
t
e
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
.
.
.
 
 
 
4
0
.
7
4
3
9
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
4
0
.
7
9
2
5
 
 
 

1
2
4
0
0
5
 
 
D
o
o
r
m
a
n
 
E
l
e
v
a
t
o
r
 
L
a
u
n
d
r
y
_
i
n
_
B
u
i
l
d
i
n
g
 
D
i
s
h
w
a
s
h
e
.
.
.
 
 
 
4
0
.
7
4
5
6
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
D
o
g
s
_
A
l
l
o
w
e
d
 
C
a
t
s
_
A
l
l
o
w
e
d
 
 
 
4
0
.
7
4
1
6
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
 
D
o
o
r
m
a
n
 
E
l
e
v
a
t
o
r
 
C
a
t
s
_
A
l
l
o
w
e
d
 
D
o
g
s
_
A
l
l
o
w
e
d
 
 
 
4
0
.
7
4
8
5
 
 
 

1
2
4
0
1
0
 
 
G
a
r
d
e
n
/
P
a
t
i
o
 
L
a
u
n
d
r
y
_
i
n
_
U
n
i
t
 
D
i
s
h
w
a
s
h
e
r
 
H
a
r
d
w
o
.
.
.
 
 
 
4
0
.
7
4
4
7
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
.
.
.
 
 
f
e
a
t
u
r
e
s
_
d
e
c
0
 
f
e
a
t
u
r
e
s
_
d
e
c
1
 
 
\

4
 
 
 
 
 
 
 
 
 
 
7
1
7
0
3
2
5
 
 
 
-
7
3
.
9
5
3
9
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
3
5
3
9
8
 
 
 
 
 
 
0
.
0
3
6
4
3
6
 
 
 

6
 
 
 
 
 
 
 
 
 
 
7
0
9
2
3
4
4
 
 
 
-
7
3
.
9
7
2
2
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
4
6
7
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
 
 
 

9
 
 
 
 
 
 
 
 
 
 
7
1
5
8
6
7
7
 
 
 
-
7
3
.
9
6
2
5
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
4
1
8
8
7
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

1
0
 
 
 
 
 
 
 
 
 
7
2
1
1
2
1
2
 
 
 
-
7
3
.
9
4
2
5
 
 
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
 
 
 

1
5
 
 
 
 
 
 
 
 
 
7
2
2
5
2
9
2
 
 
 
-
7
3
.
9
7
4
3
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
5
1
9
1
1
 
 
 
 
 
 
0
.
0
0
0
4
3
2
 
 
 

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
2
4
0
0
3
 
 
 
 
 
6
9
2
8
1
0
8
 
 
 
-
7
3
.
9
4
5
4
 
 
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
 
 
 

1
2
4
0
0
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
 
-
7
3
.
9
7
9
7
 
 
.
.
.
 
 
 
 
 
 
 
0
.
0
4
0
7
9
5
 
 
 
 
 
 
0
.
0
4
5
4
9
9
 
 
 

1
2
4
0
0
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
 
-
7
3
.
9
8
2
9
 
 
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
9
5
3
0
3
 
 
 

1
2
4
0
0
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
 
-
7
3
.
9
8
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
6
7
6
4
6
 
 
 

1
2
4
0
1
0
 
 
 
 
 
6
8
8
9
3
1
9
 
 
 
-
7
3
.
9
7
4
1
 
 
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
3
2
0
6
6
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
_
d
e
c
2
 
 
f
e
a
t
u
r
e
s
_
d
e
c
3
 
f
e
a
t
u
r
e
s
_
d
e
c
4
 
 
f
e
a
t
u
r
e
s
_
d
e
c
5
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
5
6
2
4
8
 
 
 
 
 
 
 
0
.
0
3
6
5
2
2
 
 
 
 
 
 
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
4
6
7
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
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
5
3
2
8
3
 
 
 
 
 
 
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
4
8
0
1
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
4
5
0
0
7
 
 
 
 
 
 
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
1
9
2
 
 
 

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
5
 
 
 
 
 
 
 
 
 
 
 
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
3
7
5
0
1
 
 
 
 
 
 
 
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
2
4
0
0
3
 
 
 
 
 
 
 
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
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
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
4
6
6
0
2
 
 
 
 
 
 
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
4
2
0
0
4
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
0
.
0
0
0
0
1
8
 
 
 
 
 
 
 
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
2
4
0
0
7
 
 
 
 
 
 
 
0
.
0
0
0
0
1
1
 
 
 
 
 
 
 
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
2
4
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
 
 
 
 
 
 
 
0
.
0
2
8
4
6
3
 
 
 
 
 
 
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
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
_
d
e
c
6
 
 
f
e
a
t
u
r
e
s
_
d
e
c
7
 
 
f
e
a
t
u
r
e
s
_
d
e
c
8
 
 
f
e
a
t
u
r
e
s
_
d
e
c
9
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
0
0
0
7
8
 
 
 
 
 
 
 
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
1
4
6
6
 
 
 
 
 
 
 
0
.
0
0
0
1
7
8
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
6
0
1
3
 
 
 
 
 
 
 
0
.
0
4
7
3
9
2
 
 
 
 
 
 
 
0
.
0
0
4
0
6
9
 
 
 
 
 
 
 
0
.
0
0
0
3
7
0
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
3
3
0
7
 
 
 
 
 
 
 
0
.
0
4
3
4
9
2
 
 
 
 
 
 
 
0
.
0
4
9
6
0
1
 
 
 
 
 
 
 
0
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
5
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
1
0
9
0
 
 
 
 
 
 
 
0
.
0
5
9
5
9
5
 
 
 
 
 
 
 
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
2
4
0
0
3
 
 
 
 
 
 
 
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
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
0
.
0
3
1
5
0
0
 
 
 
 
 
 
 
0
.
0
4
1
2
3
9
 
 
 
 
 
 
 
0
.
0
0
3
5
6
7
 
 
 
 
 
 
 
0
.
0
0
0
3
2
1
 
 

1
2
4
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
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
0
.
0
4
5
9
5
7
 
 
 
 
 
 
 
0
.
0
5
9
9
1
2
 
 
 
 
 
 
 
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
2
4
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
5
4
3
8
5
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 


[
1
2
4
0
1
1
 
r
o
w
s
 
x
 
2
8
 
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
I
n
d
e
x
(
[
'
b
a
t
h
r
o
o
m
s
'
,
 
'
b
e
d
r
o
o
m
s
'
,
 
'
b
u
i
l
d
i
n
g
_
i
d
'
,
 
'
c
r
e
a
t
e
d
'
,
 
'
d
e
s
c
r
i
p
t
i
o
n
'
,

 
 
 
 
 
 
 
'
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
'
,
 
'
f
e
a
t
u
r
e
s
'
,
 
'
l
a
t
i
t
u
d
e
'
,
 
'
l
i
s
t
i
n
g
_
i
d
'
,
 
'
l
o
n
g
i
t
u
d
e
'
,

 
 
 
 
 
 
 
'
m
a
n
a
g
e
r
_
i
d
'
,
 
'
p
h
o
t
o
s
'
,
 
'
p
r
i
c
e
'
,
 
'
s
t
r
e
e
t
_
a
d
d
r
e
s
s
'
,
 
'
i
n
t
e
r
e
s
t
_
l
e
v
e
l
'
,

 
 
 
 
 
 
 
'
n
u
m
_
p
h
o
t
o
s
'
,
 
'
n
u
m
_
f
e
a
t
u
r
e
s
'
,
 
'
n
u
m
_
d
e
s
c
r
i
p
t
i
o
n
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
0
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
1
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
2
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
3
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
4
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
5
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
6
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
7
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
8
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
9
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
a
l
l
d
a
t
a
에
서
 
l
i
s
t
,
 
문
자
형
 
칼
럼
 
제
외
하
고
 
숫
자
형
(
i
n
t
,
f
l
o
a
t
)
 
c
o
l
u
m
n
은
 
따
로
 
학
습
이
 
필
요
합
니
다
.




따
라
서
 
o
b
j
e
c
t
가
 
아
닌
 
i
n
t
나
 
f
l
o
a
t
 
만
 
a
l
l
d
a
t
a
2
로
 
구
분
하
였
습
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
[
a
l
l
d
a
t
a
.
c
o
l
u
m
n
s
[
a
l
l
d
a
t
a
.
d
t
y
p
e
s
!
=
o
b
j
e
c
t
]
]

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
 
 
 
 
 
 
 
 
b
a
t
h
r
o
o
m
s
 
 
b
e
d
r
o
o
m
s
 
 
b
u
i
l
d
i
n
g
_
i
d
 
 
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
 
 
l
a
t
i
t
u
d
e
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
6
0
8
3
 
 
 
 
 
 
 
 
 
 
 
 
 
1
8
8
7
 
 
 
4
0
.
7
1
0
8
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
8
4
1
7
 
 
 
 
 
 
 
 
 
 
 
 
1
0
8
4
8
 
 
 
4
0
.
7
5
1
3
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
3
4
4
 
 
 
 
 
 
 
 
 
 
 
 
1
0
9
0
4
 
 
 
4
0
.
7
5
7
5
 
 
 

1
0
 
 
 
 
 
 
 
 
 
 
 
 
1
.
5
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
3
7
9
7
 
 
 
 
 
 
 
 
 
 
 
 
1
2
2
8
2
 
 
 
4
0
.
7
1
4
5
 
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
8
7
1
7
 
 
 
 
 
 
 
 
 
 
 
 
1
0
7
9
1
 
 
 
4
0
.
7
4
3
9
 
 
 

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
2
4
0
0
3
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
8
6
2
3
 
 
 
 
 
 
 
 
 
 
 
 
 
2
0
0
8
 
 
 
4
0
.
7
9
2
5
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
6
6
0
0
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
0
8
 
 
 
4
0
.
7
4
5
6
 
 
 

1
2
4
0
0
6
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
1
2
0
4
7
 
 
 
4
0
.
7
4
1
6
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
 
2
.
0
 
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
 
 
 
9
1
3
1
 
 
 
 
 
 
 
 
 
 
 
 
1
2
6
8
7
 
 
 
4
0
.
7
4
8
5
 
 
 

1
2
4
0
1
0
 
 
 
 
 
 
 
 
1
.
0
 
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
 
 
 
1
2
0
5
 
 
 
 
 
 
 
 
 
 
 
 
 
9
6
2
2
 
 
 
4
0
.
7
4
4
7
 
 
 


 
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
l
o
n
g
i
t
u
d
e
 
 
m
a
n
a
g
e
r
_
i
d
 
 
p
r
i
c
e
 
 
s
t
r
e
e
t
_
a
d
d
r
e
s
s
 
 
.
.
.
 
 
\

4
 
 
 
 
 
 
 
 
 
 
7
1
7
0
3
2
5
 
 
 
-
7
3
.
9
5
3
9
 
 
 
 
 
 
 
 
2
7
6
7
 
 
 
2
4
0
0
 
 
 
 
 
 
 
 
 
 
 
 
3
3
4
3
 
 
.
.
.
 
 
 

6
 
 
 
 
 
 
 
 
 
 
7
0
9
2
3
4
4
 
 
 
-
7
3
.
9
7
2
2
 
 
 
 
 
 
 
 
2
5
6
5
 
 
 
3
8
0
0
 
 
 
 
 
 
 
 
 
 
 
 
9
0
0
8
 
 
.
.
.
 
 
 

9
 
 
 
 
 
 
 
 
 
 
7
1
5
8
6
7
7
 
 
 
-
7
3
.
9
6
2
5
 
 
 
 
 
 
 
 
3
4
5
8
 
 
 
3
4
9
5
 
 
 
 
 
 
 
 
 
 
 
1
6
6
3
4
 
 
.
.
.
 
 
 

1
0
 
 
 
 
 
 
 
 
 
7
2
1
1
2
1
2
 
 
 
-
7
3
.
9
4
2
5
 
 
 
 
 
 
 
 
1
5
6
8
 
 
 
3
0
0
0
 
 
 
 
 
 
 
 
 
 
 
2
3
4
8
4
 
 
.
.
.
 
 
 

1
5
 
 
 
 
 
 
 
 
 
7
2
2
5
2
9
2
 
 
 
-
7
3
.
9
7
4
3
 
 
 
 
 
 
 
 
 
7
9
0
 
 
 
2
7
9
5
 
 
 
 
 
 
 
 
 
 
 
1
4
7
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
 
 
.
.
.
 
 
 

1
2
4
0
0
3
 
 
 
 
 
6
9
2
8
1
0
8
 
 
 
-
7
3
.
9
4
5
4
 
 
 
 
 
 
 
 
1
2
1
0
 
 
 
1
7
0
0
 
 
 
 
 
 
 
 
 
 
 
 
4
3
2
1
 
 
.
.
.
 
 
 

1
2
4
0
0
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
 
-
7
3
.
9
7
9
7
 
 
 
 
 
 
 
 
 
7
4
3
 
 
 
4
1
9
5
 
 
 
 
 
 
 
 
 
 
 
 
3
1
1
7
 
 
.
.
.
 
 
 

1
2
4
0
0
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
 
-
7
3
.
9
8
2
9
 
 
 
 
 
 
 
 
3
9
5
9
 
 
 
2
4
0
0
 
 
 
 
 
 
 
 
 
 
 
2
4
5
8
8
 
 
.
.
.
 
 
 

1
2
4
0
0
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
 
-
7
3
.
9
8
0
0
 
 
 
 
 
 
 
 
1
8
8
3
 
 
 
6
8
9
5
 
 
 
 
 
 
 
 
 
 
 
1
6
7
6
8
 
 
.
.
.
 
 
 

1
2
4
0
1
0
 
 
 
 
 
6
8
8
9
3
1
9
 
 
 
-
7
3
.
9
7
4
1
 
 
 
 
 
 
 
 
3
7
3
3
 
 
 
4
6
9
5
 
 
 
 
 
 
 
 
 
 
 
1
3
7
5
2
 
 
.
.
.
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
_
d
e
c
0
 
 
f
e
a
t
u
r
e
s
_
d
e
c
1
 
 
f
e
a
t
u
r
e
s
_
d
e
c
2
 
 
f
e
a
t
u
r
e
s
_
d
e
c
3
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
5
3
9
8
 
 
 
 
 
 
 
0
.
0
3
6
4
3
6
 
 
 
 
 
 
 
0
.
0
5
6
2
4
8
 
 
 
 
 
 
 
0
.
0
3
6
5
2
2
 
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
6
7
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
5
3
2
8
3
 
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
1
8
8
7
 
 
 
 
 
 
 
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
4
5
0
0
7
 
 
 

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
5
 
 
 
 
 
 
 
 
 
 
 
0
.
0
5
1
9
1
1
 
 
 
 
 
 
 
0
.
0
0
0
4
3
2
 
 
 
 
 
 
 
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
2
4
0
0
3
 
 
 
 
 
 
 
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
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
0
.
0
4
0
7
9
5
 
 
 
 
 
 
 
0
.
0
4
5
4
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
4
6
6
0
2
 
 
 

1
2
4
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
0
 
 
 
 
 
 
 
0
.
0
9
5
3
0
3
 
 
 
 
 
 
 
0
.
0
0
0
0
1
8
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
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
6
7
6
4
6
 
 
 
 
 
 
 
0
.
0
0
0
0
1
1
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 
 

1
2
4
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
 
 
 
 
 
 
 
0
.
0
3
2
0
6
6
 
 
 
 
 
 
 
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
8
4
6
3
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
_
d
e
c
4
 
 
f
e
a
t
u
r
e
s
_
d
e
c
5
 
 
f
e
a
t
u
r
e
s
_
d
e
c
6
 
 
f
e
a
t
u
r
e
s
_
d
e
c
7
 
 
\

4
 
 
 
 
 
 
 
 
 
 
 
 
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
4
6
7
 
 
 
 
 
 
 
0
.
0
0
0
0
7
8
 
 
 
 
 
 
 
0
.
0
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
0
 
 
 
 
 
 
 
0
.
0
4
8
0
1
9
 
 
 
 
 
 
 
0
.
0
3
6
0
1
3
 
 
 
 
 
 
 
0
.
0
4
7
3
9
2
 
 
 

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
0
0
1
9
2
 
 
 
 
 
 
 
0
.
0
3
3
3
0
7
 
 
 
 
 
 
 
0
.
0
4
3
4
9
2
 
 
 

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
5
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
7
5
0
1
 
 
 
 
 
 
 
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
4
1
0
9
0
 
 
 
 
 
 
 
0
.
0
5
9
5
9
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
2
4
0
0
3
 
 
 
 
 
 
 
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
 
 
 

1
2
4
0
0
5
 
 
 
 
 
 
 
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
4
2
0
0
4
 
 
 
 
 
 
 
0
.
0
3
1
5
0
0
 
 
 
 
 
 
 
0
.
0
4
1
2
3
9
 
 
 

1
2
4
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
 
 
 

1
2
4
0
0
7
 
 
 
 
 
 
 
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
4
5
9
5
7
 
 
 
 
 
 
 
0
.
0
5
9
9
1
2
 
 
 

1
2
4
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
 
 
 


 
 
 
 
 
 
 
 
f
e
a
t
u
r
e
s
_
d
e
c
8
 
 
f
e
a
t
u
r
e
s
_
d
e
c
9
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
2
1
4
6
6
 
 
 
 
 
 
 
0
.
0
0
0
1
7
8
 
 

6
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
0
4
0
6
9
 
 
 
 
 
 
 
0
.
0
0
0
3
7
0
 
 

9
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
9
6
0
1
 
 
 
 
 
 
 
0
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
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 

1
5
 
 
 
 
 
 
 
 
 
 
 
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

1
2
4
0
0
3
 
 
 
 
 
 
 
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
2
4
0
0
5
 
 
 
 
 
 
 
0
.
0
0
3
5
6
7
 
 
 
 
 
 
 
0
.
0
0
0
3
2
1
 
 

1
2
4
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
2
4
0
0
7
 
 
 
 
 
 
 
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
2
4
0
1
0
 
 
 
 
 
 
 
0
.
0
5
4
3
8
5
 
 
 
 
 
 
 
0
.
0
0
0
0
0
0
 
 


[
1
2
4
0
1
1
 
r
o
w
s
 
x
 
2
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
a
l
l
d
a
t
a
의
 
c
o
l
u
m
n
과
 
비
교
하
였
을
 
때
,
 
a
l
l
d
a
t
a
2
에
는
 
c
r
e
a
t
e
d
 
c
o
l
u
m
n
을
 
제
외
하
고
 
모
두
 
숫
자
형
으
로
 
반
영
 
되
었
음
을
 
알
 
수
 
있
습
니
다
.




(
e
x
.
 
p
h
o
t
o
s
-
>
n
u
m
_
p
h
o
t
o
s
.
.
)



```python
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
b
a
t
h
r
o
o
m
s
'
,
 
'
b
e
d
r
o
o
m
s
'
,
 
'
b
u
i
l
d
i
n
g
_
i
d
'
,
 
'
d
i
s
p
l
a
y
_
a
d
d
r
e
s
s
'
,
 
'
l
a
t
i
t
u
d
e
'
,

 
 
 
 
 
 
 
'
l
i
s
t
i
n
g
_
i
d
'
,
 
'
l
o
n
g
i
t
u
d
e
'
,
 
'
m
a
n
a
g
e
r
_
i
d
'
,
 
'
p
r
i
c
e
'
,
 
'
s
t
r
e
e
t
_
a
d
d
r
e
s
s
'
,

 
 
 
 
 
 
 
'
n
u
m
_
p
h
o
t
o
s
'
,
 
'
n
u
m
_
f
e
a
t
u
r
e
s
'
,
 
'
n
u
m
_
d
e
s
c
r
i
p
t
i
o
n
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
0
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
1
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
2
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
3
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
4
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
5
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
6
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
7
'
,
 
'
f
e
a
t
u
r
e
s
_
d
e
c
8
'
,

 
 
 
 
 
 
 
'
f
e
a
t
u
r
e
s
_
d
e
c
9
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
a
l
l
d
a
t
a
의
 
숫
자
형
으
로
 
반
영
된
 
c
o
l
u
m
n
만
 
분
석
에
 
사
용
하
고
자
 
t
r
a
i
n
2
와
 
t
e
s
t
2
 
s
e
t
는
 
a
l
l
d
a
t
a
2
로
 
부
터
 
분
할
합
니
다
.



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
2
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
2
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

*
v
e
r
b
o
s
e
*




함
수
 
인
자
로
 
v
e
r
b
o
s
e
가
 
있
으
면
 
함
수
 
수
행
시
 
발
생
하
는
 
상
세
한
 
정
보
들
을
 
표
준
 
출
력
으
로
 
자
세
히
 
내
보
낼
 
것
인
가
를
 
나
타
냅
니
다
.




보
통
 
0
 
은
 
출
력
하
지
 
않
고
,
 
1
은
 
자
세
히
,
 
2
는
 
함
축
적
인
 
정
보
만
 
출
력
하
는
 
형
태
로
 
되
어
 
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
"
i
n
t
e
r
e
s
t
_
l
e
v
e
l
"
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
0
9
6
5
3
4

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
0
2
7
4
0
6
8
	
t
o
t
a
l
:
 
8
2
.
1
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
 
1
m
 
2
2
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
2
4
5
3
4
	
t
o
t
a
l
:
 
2
.
5
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
 
2
2
.
8
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
5
6
7
2
7
2
	
t
o
t
a
l
:
 
4
.
6
3
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
8
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
5
3
5
2
4
5
2
	
t
o
t
a
l
:
 
6
.
8
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
5
.
9
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
5
1
7
4
2
0
6
	
t
o
t
a
l
:
 
9
.
1
3
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
6
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
5
0
2
5
6
5
6
	
t
o
t
a
l
:
 
1
1
.
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
1
.
2
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
8
9
1
6
9
2
	
t
o
t
a
l
:
 
1
3
.
3
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
8
4
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
7
7
5
5
4
7
	
t
o
t
a
l
:
 
1
5
.
4
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
5
6
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
4
6
7
0
1
2
3
	
t
o
t
a
l
:
 
1
7
.
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
 
4
.
3
4
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
4
5
6
6
5
5
5
	
t
o
t
a
l
:
 
1
9
.
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
1
5
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
4
4
7
0
2
4
1
	
t
o
t
a
l
:
 
2
1
.
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
 
0
u
s

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
"
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
t
w
o
-
s
i
g
m
a
-
c
o
n
n
e
c
t
-
r
e
n
t
a
l
-
l
i
s
t
i
n
g
-
i
n
q
u
i
r
i
e
s
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
"
)

s
u
b
```

<pre>
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
 
 
 
 
h
i
g
h
 
 
 
 
m
e
d
i
u
m
 
 
 
 
 
 
 
l
o
w

0
 
 
 
 
 
 
 
 
 
7
1
4
2
6
1
8
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

1
 
 
 
 
 
 
 
 
 
7
2
1
0
0
4
0
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

2
 
 
 
 
 
 
 
 
 
7
1
7
4
5
6
6
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

3
 
 
 
 
 
 
 
 
 
7
1
9
1
3
9
1
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

4
 
 
 
 
 
 
 
 
 
7
1
7
1
6
9
5
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

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

7
4
6
5
4
 
 
 
 
 
6
9
2
8
1
0
8
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

7
4
6
5
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

7
4
6
5
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

7
4
6
5
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3

7
4
6
5
8
 
 
 
 
 
6
8
8
9
3
1
9
 
 
0
.
0
7
7
7
8
8
 
 
0
.
2
2
7
5
2
9
 
 
0
.
6
9
4
6
8
3


[
7
4
6
5
9
 
r
o
w
s
 
x
 
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
r
e
s
u
l
t
의
 
값
을
 
s
u
b
에
 
적
용
할
 
때
는
 
c
o
l
u
m
n
중
 
'
l
i
s
t
i
n
g
_
i
d
'
를
 
제
외
한
 
'
h
i
g
h
'
,
 
'
m
e
d
i
u
m
'
,
 
'
l
o
w
'
로
 
i
n
p
u
t
 
해
주
어
야
 
합
니
다
.


따
라
서
 
모
든
 
r
o
w
의
 
값
을
 
적
용
하
되
,
 
'
h
i
g
h
'
 
c
o
l
u
m
n
부
터
 
적
용
 
될
 
수
 
있
도
록


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
로
 
적
용
합
니
다
.



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

r
e
s
u
l
t
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
0
.
0
6
0
4
8
4
0
3
,
 
0
.
5
8
3
7
0
2
6
8
,
 
0
.
3
5
5
8
1
3
2
9
]
,

 
 
 
 
 
 
 
[
0
.
0
1
9
7
5
2
4
3
,
 
0
.
9
3
2
3
7
6
5
2
,
 
0
.
0
4
7
8
7
1
0
5
]
,

 
 
 
 
 
 
 
[
0
.
0
0
2
1
0
4
4
8
,
 
0
.
9
8
6
6
2
5
1
2
,
 
0
.
0
1
1
2
7
0
4
1
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
0
.
0
0
1
4
2
3
9
4
,
 
0
.
9
8
3
7
3
8
5
6
,
 
0
.
0
1
4
8
3
7
5
 
]
,

 
 
 
 
 
 
 
[
0
.
0
0
1
3
9
3
5
6
,
 
0
.
9
8
8
1
7
2
5
9
,
 
0
.
0
1
0
4
3
3
8
5
]
,

 
 
 
 
 
 
 
[
0
.
0
4
7
3
3
9
9
3
,
 
0
.
6
3
4
1
3
0
7
5
,
 
0
.
3
1
8
5
2
9
3
2
]
]
)
</pre>
t
r
a
i
n
과
 
t
e
s
t
는
 
j
s
o
n
 
형
식
으
로
 
비
정
형
 
데
이
터
와
 
정
형
 
데
이
터
가
 
혼
재
 
되
어
 
있
습
니
다
.
 
(
c
o
l
u
m
n
 
고
정
이
 
되
지
 
않
는
 
문
제
가
 
발
생
할
 
수
 
있
습
니
다
.
)




s
u
b
의
 
c
o
l
u
m
n
을
 
고
정
하
고
자
 
할
 
때
는
 
아
래
와
 
같
이
 
진
행
할
 
수
 
있
습
니
다
.



```python
s
u
b
.
c
o
l
u
m
n
s
=
[
"
l
i
s
t
i
n
g
_
i
d
"
,
"
h
i
g
h
"
,
"
m
e
d
i
u
m
"
,
"
l
o
w
"
]

s
u
b
```

<pre>
 
 
 
 
 
 
 
l
i
s
t
i
n
g
_
i
d
 
 
 
 
 
 
h
i
g
h
 
 
 
 
m
e
d
i
u
m
 
 
 
 
 
 
 
l
o
w

0
 
 
 
 
 
 
 
 
 
7
1
4
2
6
1
8
 
 
0
.
0
6
0
4
8
4
 
 
0
.
5
8
3
7
0
3
 
 
0
.
3
5
5
8
1
3

1
 
 
 
 
 
 
 
 
 
7
2
1
0
0
4
0
 
 
0
.
0
1
9
7
5
2
 
 
0
.
9
3
2
3
7
7
 
 
0
.
0
4
7
8
7
1

2
 
 
 
 
 
 
 
 
 
7
1
7
4
5
6
6
 
 
0
.
0
0
2
1
0
4
 
 
0
.
9
8
6
6
2
5
 
 
0
.
0
1
1
2
7
0

3
 
 
 
 
 
 
 
 
 
7
1
9
1
3
9
1
 
 
0
.
2
0
6
6
4
8
 
 
0
.
2
7
2
8
1
6
 
 
0
.
5
2
0
5
3
6

4
 
 
 
 
 
 
 
 
 
7
1
7
1
6
9
5
 
 
0
.
0
1
6
0
3
9
 
 
0
.
8
5
4
1
8
3
 
 
0
.
1
2
9
7
7
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
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

7
4
6
5
4
 
 
 
 
 
6
9
2
8
1
0
8
 
 
0
.
5
3
4
7
8
3
 
 
0
.
1
5
4
7
5
1
 
 
0
.
3
1
0
4
6
6

7
4
6
5
5
 
 
 
 
 
6
9
0
6
6
7
4
 
 
0
.
0
5
1
4
3
1
 
 
0
.
6
4
4
6
0
5
 
 
0
.
3
0
3
9
6
4

7
4
6
5
6
 
 
 
 
 
6
8
9
7
9
6
7
 
 
0
.
0
0
1
4
2
4
 
 
0
.
9
8
3
7
3
9
 
 
0
.
0
1
4
8
3
7

7
4
6
5
7
 
 
 
 
 
6
8
4
2
1
8
3
 
 
0
.
0
0
1
3
9
4
 
 
0
.
9
8
8
1
7
3
 
 
0
.
0
1
0
4
3
4

7
4
6
5
8
 
 
 
 
 
6
8
8
9
3
1
9
 
 
0
.
0
4
7
3
4
0
 
 
0
.
6
3
4
1
3
1
 
 
0
.
3
1
8
5
2
9


[
7
4
6
5
9
 
r
o
w
s
 
x
 
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
"
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
"
,
i
n
d
e
x
=
0
)
```

H
a
s
h
i
n
g
V
e
c
t
o
r
i
z
e
r
를
 
사
용
하
였
을
 
때
 
n
e
g
a
t
i
v
e
 
값
 
발
생
 
및
 
정
규
화
 
어
려
움
으
로
 
N
M
F
는
 
적
용
치
 
못
하
였
습
니
다
.




이
를
 
제
외
하
고
 
총
 
1
5
가
지
 
C
A
S
E
를
 
적
용
하
였
을
 
때
 
다
음
과
 
같
은
 
s
c
o
r
e
를
 
얻
었
습
니
다
.
 
(
s
c
o
r
e
가
 
작
을
 
수
록
 
순
위
가
 
개
선
됩
니
다
.
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
e
9
5
6
a
4
0
6
-
3
e
5
7
-
4
f
0
5
-
8
4
5
e
-
1
8
c
4
6
c
2
e
6
7
7
3
.
p
n
g
)




T
r
u
n
c
a
t
e
d
S
V
D
의
 
경
우
 
차
원
의
 
수
를
 
증
가
(
1
0
에
서
2
0
)
함
에
 
따
라
 
s
c
o
r
e
가
 
개
선
되
는
 
듯
 
보
였
으
나
 
3
0
 
이
상
에
서
 
오
히
려
 
미
개
선
 
되
는
 
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




N
M
F
의
 
경
우
 
C
o
u
n
t
V
e
c
t
o
r
i
z
e
r
에
서
는
 
차
원
의
 
수
를
 
3
0
으
로
 
증
가
하
였
을
 
때
 
가
장
 
좋
으
나
,
 
2
0
에
서
는
 
1
0
보
다
 
미
개
선
 
되
는
 
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




N
M
F
의
 
경
우
 
T
f
i
d
f
V
e
c
t
o
r
i
z
e
r
에
서
는
 
차
원
의
 
수
를
 
증
가
함
에
 
따
라
 
s
c
o
r
e
가
 
개
선
되
는
 
경
향
이
 
가
장
 
뚜
렷
하
게
 
보
였
습
니
다
.




위
 
데
이
터
에
서
는
 
대
부
분
 
T
r
u
n
c
a
t
e
d
S
V
D
가
 
N
M
F
 
보
다
 
정
확
성
이
 
뛰
어
납
니
다
.





