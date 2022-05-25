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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
.
z
i
p

</pre>

```python
d
e
f
 
r
e
d
u
c
e
_
m
e
m
o
r
y
_
u
s
a
g
e
(
d
f
,
 
d
e
e
p
=
T
r
u
e
,
 
v
e
r
b
o
s
e
=
T
r
u
e
,
 
c
a
t
e
g
o
r
i
e
s
=
T
r
u
e
)
:

 
 
 
 
#
 
A
l
l
 
t
y
p
e
s
 
t
h
a
t
 
w
e
 
w
a
n
t
 
t
o
 
c
h
a
n
g
e
 
f
o
r
 
"
l
i
g
h
t
e
r
"
 
o
n
e
s
.

 
 
 
 
#
 
i
n
t
8
 
a
n
d
 
f
l
o
a
t
1
6
 
a
r
e
 
n
o
t
 
i
n
c
l
u
d
e
 
b
e
c
a
u
s
e
 
w
e
 
c
a
n
n
o
t
 
r
e
d
u
c
e

 
 
 
 
#
 
t
h
o
s
e
 
d
a
t
a
 
t
y
p
e
s
.

 
 
 
 
#
 
f
l
o
a
t
3
2
 
i
s
 
n
o
t
 
i
n
c
l
u
d
e
 
b
e
c
a
u
s
e
 
f
l
o
a
t
1
6
 
h
a
s
 
t
o
o
 
l
o
w
 
p
r
e
c
i
s
i
o
n
.

 
 
 
 
n
u
m
e
r
i
c
2
r
e
d
u
c
e
 
=
 
[
"
i
n
t
1
6
"
,
 
"
i
n
t
3
2
"
,
 
"
i
n
t
6
4
"
,
 
"
f
l
o
a
t
6
4
"
]

 
 
 
 
s
t
a
r
t
_
m
e
m
 
=
 
0

 
 
 
 
i
f
 
v
e
r
b
o
s
e
:

 
 
 
 
 
 
 
 
s
t
a
r
t
_
m
e
m
 
=
 
m
e
m
o
r
y
_
u
s
a
g
e
_
m
b
(
d
f
,
 
d
e
e
p
=
d
e
e
p
)


 
 
 
 
f
o
r
 
c
o
l
,
 
c
o
l
_
t
y
p
e
 
i
n
 
d
f
.
d
t
y
p
e
s
.
i
t
e
r
i
t
e
m
s
(
)
:

 
 
 
 
 
 
 
 
b
e
s
t
_
t
y
p
e
 
=
 
N
o
n
e

 
 
 
 
 
 
 
 
i
f
 
c
o
l
_
t
y
p
e
 
=
=
 
"
o
b
j
e
c
t
"
:

 
 
 
 
 
 
 
 
 
 
 
 
d
f
[
c
o
l
]
 
=
 
d
f
[
c
o
l
]
.
a
s
t
y
p
e
(
"
c
a
t
e
g
o
r
y
"
)

 
 
 
 
 
 
 
 
 
 
 
 
b
e
s
t
_
t
y
p
e
 
=
 
"
c
a
t
e
g
o
r
y
"

 
 
 
 
 
 
 
 
e
l
i
f
 
c
o
l
_
t
y
p
e
 
i
n
 
n
u
m
e
r
i
c
2
r
e
d
u
c
e
:

 
 
 
 
 
 
 
 
 
 
 
 
d
o
w
n
c
a
s
t
 
=
 
"
i
n
t
e
g
e
r
"
 
i
f
 
"
i
n
t
"
 
i
n
 
s
t
r
(
c
o
l
_
t
y
p
e
)
 
e
l
s
e
 
"
f
l
o
a
t
"

 
 
 
 
 
 
 
 
 
 
 
 
d
f
[
c
o
l
]
 
=
 
p
d
.
t
o
_
n
u
m
e
r
i
c
(
d
f
[
c
o
l
]
,
 
d
o
w
n
c
a
s
t
=
d
o
w
n
c
a
s
t
)

 
 
 
 
 
 
 
 
 
 
 
 
b
e
s
t
_
t
y
p
e
 
=
 
d
f
[
c
o
l
]
.
d
t
y
p
e
.
n
a
m
e

 
 
 
 
 
 
 
 
#
 
L
o
g
 
t
h
e
 
c
o
n
v
e
r
s
i
o
n
 
p
e
r
f
o
r
m
e
d
.

 
 
 
 
 
 
 
 
i
f
 
v
e
r
b
o
s
e
 
a
n
d
 
b
e
s
t
_
t
y
p
e
 
i
s
 
n
o
t
 
N
o
n
e
 
a
n
d
 
b
e
s
t
_
t
y
p
e
 
!
=
 
s
t
r
(
c
o
l
_
t
y
p
e
)
:

 
 
 
 
 
 
 
 
 
 
 
 
p
r
i
n
t
(
f
"
C
o
l
u
m
n
 
'
{
c
o
l
}
'
 
c
o
n
v
e
r
t
e
d
 
f
r
o
m
 
{
c
o
l
_
t
y
p
e
}
 
t
o
 
{
b
e
s
t
_
t
y
p
e
}
"
)


 
 
 
 
i
f
 
v
e
r
b
o
s
e
:

 
 
 
 
 
 
 
 
e
n
d
_
m
e
m
 
=
 
m
e
m
o
r
y
_
u
s
a
g
e
_
m
b
(
d
f
,
 
d
e
e
p
=
d
e
e
p
)

 
 
 
 
 
 
 
 
d
i
f
f
_
m
e
m
 
=
 
s
t
a
r
t
_
m
e
m
 
-
 
e
n
d
_
m
e
m

 
 
 
 
 
 
 
 
p
e
r
c
e
n
t
_
m
e
m
 
=
 
1
0
0
 
*
 
d
i
f
f
_
m
e
m
 
/
 
s
t
a
r
t
_
m
e
m

 
 
 
 
 
 
 
 
p
r
i
n
t
(
f
"
M
e
m
o
r
y
 
u
s
a
g
e
 
d
e
c
r
e
a
s
e
d
 
f
r
o
m
"

 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
"
 
{
s
t
a
r
t
_
m
e
m
:
.
2
f
}
M
B
 
t
o
 
{
e
n
d
_
m
e
m
:
.
2
f
}
M
B
"

 
 
 
 
 
 
 
 
 
 
 
 
 
 
f
"
 
(
{
d
i
f
f
_
m
e
m
:
.
2
f
}
M
B
,
 
{
p
e
r
c
e
n
t
_
m
e
m
:
.
2
f
}
%
 
r
e
d
u
c
t
i
o
n
)
"
)
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
.
z
i
p
"
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
.
z
i
p
"
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
o
m
m
e
n
t
_
t
e
x
t
 
 
\

0
 
 
 
 
 
 
 
0
0
0
0
9
9
7
9
3
2
d
7
7
7
b
f
 
 
E
x
p
l
a
n
a
t
i
o
n
\
n
W
h
y
 
t
h
e
 
e
d
i
t
s
 
m
a
d
e
 
u
n
d
e
r
 
m
y
 
u
s
e
r
n
.
.
.
 
 
 

1
 
 
 
 
 
 
 
0
0
0
1
0
3
f
0
d
9
c
f
b
6
0
f
 
 
D
'
a
w
w
!
 
H
e
 
m
a
t
c
h
e
s
 
t
h
i
s
 
b
a
c
k
g
r
o
u
n
d
 
c
o
l
o
u
r
 
I
'
m
 
s
.
.
.
 
 
 

2
 
 
 
 
 
 
 
0
0
0
1
1
3
f
0
7
e
c
0
0
2
f
d
 
 
H
e
y
 
m
a
n
,
 
I
'
m
 
r
e
a
l
l
y
 
n
o
t
 
t
r
y
i
n
g
 
t
o
 
e
d
i
t
 
w
a
r
.
 
I
t
.
.
.
 
 
 

3
 
 
 
 
 
 
 
0
0
0
1
b
4
1
b
1
c
6
b
b
3
7
e
 
 
"
\
n
M
o
r
e
\
n
I
 
c
a
n
'
t
 
m
a
k
e
 
a
n
y
 
r
e
a
l
 
s
u
g
g
e
s
t
i
o
n
s
 
o
n
 
.
.
.
 
 
 

4
 
 
 
 
 
 
 
0
0
0
1
d
9
5
8
c
5
4
c
6
e
3
5
 
 
Y
o
u
,
 
s
i
r
,
 
a
r
e
 
m
y
 
h
e
r
o
.
 
A
n
y
 
c
h
a
n
c
e
 
y
o
u
 
r
e
m
e
m
b
e
r
.
.
.
 
 
 

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
9
5
6
6
 
 
f
f
e
9
8
7
2
7
9
5
6
0
d
7
f
f
 
 
"
:
:
:
:
:
A
n
d
 
f
o
r
 
t
h
e
 
s
e
c
o
n
d
 
t
i
m
e
 
o
f
 
a
s
k
i
n
g
,
 
w
h
e
n
 
.
.
.
 
 
 

1
5
9
5
6
7
 
 
f
f
e
a
4
a
d
e
e
e
3
8
4
e
9
0
 
 
Y
o
u
 
s
h
o
u
l
d
 
b
e
 
a
s
h
a
m
e
d
 
o
f
 
y
o
u
r
s
e
l
f
 
\
n
\
n
T
h
a
t
 
i
s
 
.
.
.
 
 
 

1
5
9
5
6
8
 
 
f
f
e
e
3
6
e
a
b
5
c
2
6
7
c
9
 
 
S
p
i
t
z
e
r
 
\
n
\
n
U
m
m
,
 
t
h
e
r
e
s
 
n
o
 
a
c
t
u
a
l
 
a
r
t
i
c
l
e
 
f
o
r
 
.
.
.
 
 
 

1
5
9
5
6
9
 
 
f
f
f
1
2
5
3
7
0
e
4
a
a
a
f
3
 
 
A
n
d
 
i
t
 
l
o
o
k
s
 
l
i
k
e
 
i
t
 
w
a
s
 
a
c
t
u
a
l
l
y
 
y
o
u
 
w
h
o
 
p
u
t
 
.
.
.
 
 
 

1
5
9
5
7
0
 
 
f
f
f
4
6
f
c
4
2
6
a
f
1
f
9
a
 
 
"
\
n
A
n
d
 
.
.
.
 
I
 
r
e
a
l
l
y
 
d
o
n
'
t
 
t
h
i
n
k
 
y
o
u
 
u
n
d
e
r
s
t
a
n
d
.
.
.
 
 
 


 
 
 
 
 
 
 
 
t
o
x
i
c
 
 
s
e
v
e
r
e
_
t
o
x
i
c
 
 
o
b
s
c
e
n
e
 
 
t
h
r
e
a
t
 
 
i
n
s
u
l
t
 
 
i
d
e
n
t
i
t
y
_
h
a
t
e
 
 

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
 
 

2
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
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
 
 

1
5
9
5
6
6
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 

1
5
9
5
6
7
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 

1
5
9
5
6
8
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 

1
5
9
5
6
9
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 

1
5
9
5
7
0
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
 
 


[
1
5
9
5
7
1
 
r
o
w
s
 
x
 
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
o
m
m
e
n
t
_
t
e
x
t

0
 
 
 
 
 
 
 
0
0
0
0
1
c
e
e
3
4
1
f
d
b
1
2
 
 
Y
o
 
b
i
t
c
h
 
J
a
 
R
u
l
e
 
i
s
 
m
o
r
e
 
s
u
c
c
e
s
f
u
l
 
t
h
e
n
 
y
o
u
'
l
l
.
.
.

1
 
 
 
 
 
 
 
0
0
0
0
2
4
7
8
6
7
8
2
3
e
f
7
 
 
=
=
 
F
r
o
m
 
R
f
C
 
=
=
 
\
n
\
n
 
T
h
e
 
t
i
t
l
e
 
i
s
 
f
i
n
e
 
a
s
 
i
t
 
i
s
.
.
.

2
 
 
 
 
 
 
 
0
0
0
1
3
b
1
7
a
d
2
2
0
c
4
6
 
 
"
 
\
n
\
n
 
=
=
 
S
o
u
r
c
e
s
 
=
=
 
\
n
\
n
 
*
 
Z
a
w
e
 
A
s
h
t
o
n
 
o
n
 
L
a
p
.
.
.

3
 
 
 
 
 
 
 
0
0
0
1
7
5
6
3
c
3
f
7
9
1
9
a
 
 
:
I
f
 
y
o
u
 
h
a
v
e
 
a
 
l
o
o
k
 
b
a
c
k
 
a
t
 
t
h
e
 
s
o
u
r
c
e
,
 
t
h
e
 
i
n
.
.
.

4
 
 
 
 
 
 
 
0
0
0
1
7
6
9
5
a
d
8
9
9
7
e
b
 
 
 
 
 
 
 
 
 
 
I
 
d
o
n
'
t
 
a
n
o
n
y
m
o
u
s
l
y
 
e
d
i
t
 
a
r
t
i
c
l
e
s
 
a
t
 
a
l
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
.

1
5
3
1
5
9
 
 
f
f
f
c
d
0
9
6
0
e
e
3
0
9
b
5
 
 
.
 
\
n
 
i
 
t
o
t
a
l
l
y
 
a
g
r
e
e
,
 
t
h
i
s
 
s
t
u
f
f
 
i
s
 
n
o
t
h
i
n
g
 
b
u
.
.
.

1
5
3
1
6
0
 
 
f
f
f
d
7
a
9
a
6
e
b
3
2
c
1
6
 
 
=
=
 
T
h
r
o
w
 
f
r
o
m
 
o
u
t
 
f
i
e
l
d
 
t
o
 
h
o
m
e
 
p
l
a
t
e
.
 
=
=
 
\
n
\
n
.
.
.

1
5
3
1
6
1
 
 
f
f
f
d
a
9
e
8
d
6
f
a
f
a
9
e
 
 
"
 
\
n
\
n
 
=
=
 
O
k
i
n
o
t
o
r
i
s
h
i
m
a
 
c
a
t
e
g
o
r
i
e
s
 
=
=
 
\
n
\
n
 
I
 
.
.
.

1
5
3
1
6
2
 
 
f
f
f
e
8
f
1
3
4
0
a
7
9
f
c
2
 
 
"
 
\
n
\
n
 
=
=
 
"
"
O
n
e
 
o
f
 
t
h
e
 
f
o
u
n
d
i
n
g
 
n
a
t
i
o
n
s
 
o
f
 
t
h
e
.
.
.

1
5
3
1
6
3
 
 
f
f
f
f
c
e
3
f
b
1
8
3
e
e
8
0
 
 
"
 
\
n
 
:
:
:
S
t
o
p
 
a
l
r
e
a
d
y
.
 
Y
o
u
r
 
b
u
l
l
s
h
i
t
 
i
s
 
n
o
t
 
w
e
l
.
.
.


[
1
5
3
1
6
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
r
a
i
n
[
"
c
o
m
m
e
n
t
_
t
e
x
t
"
]
[
0
]
```

<pre>
"
E
x
p
l
a
n
a
t
i
o
n
\
n
W
h
y
 
t
h
e
 
e
d
i
t
s
 
m
a
d
e
 
u
n
d
e
r
 
m
y
 
u
s
e
r
n
a
m
e
 
H
a
r
d
c
o
r
e
 
M
e
t
a
l
l
i
c
a
 
F
a
n
 
w
e
r
e
 
r
e
v
e
r
t
e
d
?
 
T
h
e
y
 
w
e
r
e
n
'
t
 
v
a
n
d
a
l
i
s
m
s
,
 
j
u
s
t
 
c
l
o
s
u
r
e
 
o
n
 
s
o
m
e
 
G
A
s
 
a
f
t
e
r
 
I
 
v
o
t
e
d
 
a
t
 
N
e
w
 
Y
o
r
k
 
D
o
l
l
s
 
F
A
C
.
 
A
n
d
 
p
l
e
a
s
e
 
d
o
n
'
t
 
r
e
m
o
v
e
 
t
h
e
 
t
e
m
p
l
a
t
e
 
f
r
o
m
 
t
h
e
 
t
a
l
k
 
p
a
g
e
 
s
i
n
c
e
 
I
'
m
 
r
e
t
i
r
e
d
 
n
o
w
.
8
9
.
2
0
5
.
3
8
.
2
7
"
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
c
o
m
m
e
n
t
_
t
e
x
t
 
 
\

0
 
 
 
 
 
 
 
0
0
0
0
9
9
7
9
3
2
d
7
7
7
b
f
 
 
E
x
p
l
a
n
a
t
i
o
n
\
n
W
h
y
 
t
h
e
 
e
d
i
t
s
 
m
a
d
e
 
u
n
d
e
r
 
m
y
 
u
s
e
r
n
.
.
.
 
 
 

1
 
 
 
 
 
 
 
0
0
0
1
0
3
f
0
d
9
c
f
b
6
0
f
 
 
D
'
a
w
w
!
 
H
e
 
m
a
t
c
h
e
s
 
t
h
i
s
 
b
a
c
k
g
r
o
u
n
d
 
c
o
l
o
u
r
 
I
'
m
 
s
.
.
.
 
 
 

2
 
 
 
 
 
 
 
0
0
0
1
1
3
f
0
7
e
c
0
0
2
f
d
 
 
H
e
y
 
m
a
n
,
 
I
'
m
 
r
e
a
l
l
y
 
n
o
t
 
t
r
y
i
n
g
 
t
o
 
e
d
i
t
 
w
a
r
.
 
I
t
.
.
.
 
 
 

3
 
 
 
 
 
 
 
0
0
0
1
b
4
1
b
1
c
6
b
b
3
7
e
 
 
"
\
n
M
o
r
e
\
n
I
 
c
a
n
'
t
 
m
a
k
e
 
a
n
y
 
r
e
a
l
 
s
u
g
g
e
s
t
i
o
n
s
 
o
n
 
.
.
.
 
 
 

4
 
 
 
 
 
 
 
0
0
0
1
d
9
5
8
c
5
4
c
6
e
3
5
 
 
Y
o
u
,
 
s
i
r
,
 
a
r
e
 
m
y
 
h
e
r
o
.
 
A
n
y
 
c
h
a
n
c
e
 
y
o
u
 
r
e
m
e
m
b
e
r
.
.
.
 
 
 

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
3
1
5
9
 
 
f
f
f
c
d
0
9
6
0
e
e
3
0
9
b
5
 
 
.
 
\
n
 
i
 
t
o
t
a
l
l
y
 
a
g
r
e
e
,
 
t
h
i
s
 
s
t
u
f
f
 
i
s
 
n
o
t
h
i
n
g
 
b
u
.
.
.
 
 
 

1
5
3
1
6
0
 
 
f
f
f
d
7
a
9
a
6
e
b
3
2
c
1
6
 
 
=
=
 
T
h
r
o
w
 
f
r
o
m
 
o
u
t
 
f
i
e
l
d
 
t
o
 
h
o
m
e
 
p
l
a
t
e
.
 
=
=
 
\
n
\
n
.
.
.
 
 
 

1
5
3
1
6
1
 
 
f
f
f
d
a
9
e
8
d
6
f
a
f
a
9
e
 
 
"
 
\
n
\
n
 
=
=
 
O
k
i
n
o
t
o
r
i
s
h
i
m
a
 
c
a
t
e
g
o
r
i
e
s
 
=
=
 
\
n
\
n
 
I
 
.
.
.
 
 
 

1
5
3
1
6
2
 
 
f
f
f
e
8
f
1
3
4
0
a
7
9
f
c
2
 
 
"
 
\
n
\
n
 
=
=
 
"
"
O
n
e
 
o
f
 
t
h
e
 
f
o
u
n
d
i
n
g
 
n
a
t
i
o
n
s
 
o
f
 
t
h
e
.
.
.
 
 
 

1
5
3
1
6
3
 
 
f
f
f
f
c
e
3
f
b
1
8
3
e
e
8
0
 
 
"
 
\
n
 
:
:
:
S
t
o
p
 
a
l
r
e
a
d
y
.
 
Y
o
u
r
 
b
u
l
l
s
h
i
t
 
i
s
 
n
o
t
 
w
e
l
.
.
.
 
 
 


 
 
 
 
 
 
 
 
t
o
x
i
c
 
 
s
e
v
e
r
e
_
t
o
x
i
c
 
 
o
b
s
c
e
n
e
 
 
t
h
r
e
a
t
 
 
i
n
s
u
l
t
 
 
i
d
e
n
t
i
t
y
_
h
a
t
e
 
 

0
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 

1
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 

2
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 

3
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 

4
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
0
.
0
 
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
0
.
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
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
 
 

1
5
3
1
5
9
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
5
3
1
6
0
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
5
3
1
6
1
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
5
3
1
6
2
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 

1
5
3
1
6
3
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
N
a
N
 
 
 
 
 
 
 
 
 
 
 
 
N
a
N
 
 


[
3
1
2
7
3
5
 
r
o
w
s
 
x
 
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
a
l
l
d
a
t
a
의
 
'
c
o
m
m
e
n
t
_
t
e
x
t
'
 
c
o
l
u
m
n
은
 
t
e
x
t
 
형
식
으
로
 
K
e
r
a
s
에
서
 
제
공
하
는
 
T
o
k
e
n
i
z
e
r
를
 
이
용
하
여
 
빈
도
수
가
 
높
은
 
순
서
대
로
 
정
렬
하
여
 
각
 
단
어
에
 
숫
자
를
 
부
여
합
니
다



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
o
k
e
n
i
z
e
r

T
K
=
T
o
k
e
n
i
z
e
r
(
)

T
K
.
f
i
t
_
o
n
_
t
e
x
t
s
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
c
o
m
m
e
n
t
_
t
e
x
t
"
]
)

T
K
.
w
o
r
d
_
i
n
d
e
x
```

<pre>
{
'
t
h
e
'
:
 
1
,

 
'
t
o
'
:
 
2
,

 
'
o
f
'
:
 
3
,

 
'
a
'
:
 
4
,

 
'
a
n
d
'
:
 
5
,

 
'
y
o
u
'
:
 
6
,

 
'
i
'
:
 
7
,

 
'
i
s
'
:
 
8
,

 
'
t
h
a
t
'
:
 
9
,

 
'
i
n
'
:
 
1
0
,

 
'
i
t
'
:
 
1
1
,

 
'
f
o
r
'
:
 
1
2
,

 
'
t
h
i
s
'
:
 
1
3
,

 
'
n
o
t
'
:
 
1
4
,

 
'
o
n
'
:
 
1
5
,

 
'
b
e
'
:
 
1
6
,

 
'
a
s
'
:
 
1
7
,

 
'
a
r
e
'
:
 
1
8
,

 
'
h
a
v
e
'
:
 
1
9
,

 
'
y
o
u
r
'
:
 
2
0
,

 
'
w
i
t
h
'
:
 
2
1
,

 
'
i
f
'
:
 
2
2
,

 
'
a
r
t
i
c
l
e
'
:
 
2
3
,

 
'
w
a
s
'
:
 
2
4
,

 
'
o
r
'
:
 
2
5
,

 
'
b
u
t
'
:
 
2
6
,

 
'
a
n
'
:
 
2
7
,

 
'
w
i
k
i
p
e
d
i
a
'
:
 
2
8
,

 
'
p
a
g
e
'
:
 
2
9
,

 
'
m
y
'
:
 
3
0
,

 
'
f
r
o
m
'
:
 
3
1
,

 
'
b
y
'
:
 
3
2
,

 
'
a
t
'
:
 
3
3
,

 
'
d
o
'
:
 
3
4
,

 
'
a
b
o
u
t
'
:
 
3
5
,

 
'
s
o
'
:
 
3
6
,

 
'
m
e
'
:
 
3
7
,

 
'
w
h
a
t
'
:
 
3
8
,

 
'
c
a
n
'
:
 
3
9
,

 
'
a
l
l
'
:
 
4
0
,

 
'
t
h
e
r
e
'
:
 
4
1
,

 
'
h
a
s
'
:
 
4
2
,

 
'
w
o
u
l
d
'
:
 
4
3
,

 
'
n
o
'
:
 
4
4
,

 
'
w
i
l
l
'
:
 
4
5
,

 
'
t
a
l
k
'
:
 
4
6
,

 
'
o
n
e
'
:
 
4
7
,

 
'
l
i
k
e
'
:
 
4
8
,

 
'
j
u
s
t
'
:
 
4
9
,

 
'
p
l
e
a
s
e
'
:
 
5
0
,

 
'
t
h
e
y
'
:
 
5
1
,

 
'
h
e
'
:
 
5
2
,

 
'
w
e
'
:
 
5
3
,

 
'
w
h
i
c
h
'
:
 
5
4
,

 
'
a
n
y
'
:
 
5
5
,

 
'
s
h
o
u
l
d
'
:
 
5
6
,

 
'
b
e
e
n
'
:
 
5
7
,

 
'
m
o
r
e
'
:
 
5
8
,

 
"
d
o
n
'
t
"
:
 
5
9
,

 
'
s
o
m
e
'
:
 
6
0
,

 
'
o
t
h
e
r
'
:
 
6
1
,

 
'
w
h
o
'
:
 
6
2
,

 
'
s
e
e
'
:
 
6
3
,

 
'
h
e
r
e
'
:
 
6
4
,

 
'
t
h
i
n
k
'
:
 
6
5
,

 
'
a
l
s
o
'
:
 
6
6
,

 
'
f
u
c
k
'
:
 
6
7
,

 
'
h
i
s
'
:
 
6
8
,

 
'
b
e
c
a
u
s
e
'
:
 
6
9
,

 
'
k
n
o
w
'
:
 
7
0
,

 
"
i
t
'
s
"
:
 
7
1
,

 
"
i
'
m
"
:
 
7
2
,

 
'
u
p
'
:
 
7
3
,

 
'
h
o
w
'
:
 
7
4
,

 
'
p
e
o
p
l
e
'
:
 
7
5
,

 
'
o
u
t
'
:
 
7
6
,

 
'
o
n
l
y
'
:
 
7
7
,

 
'
w
h
y
'
:
 
7
8
,

 
'
e
d
i
t
'
:
 
7
9
,

 
'
w
h
e
n
'
:
 
8
0
,

 
'
a
m
'
:
 
8
1
,

 
'
u
s
e
'
:
 
8
2
,

 
'
a
r
t
i
c
l
e
s
'
:
 
8
3
,

 
'
t
h
e
n
'
:
 
8
4
,

 
'
t
i
m
e
'
:
 
8
5
,

 
'
w
e
r
e
'
:
 
8
6
,

 
'
m
a
y
'
:
 
8
7
,

 
'
t
h
e
m
'
:
 
8
8
,

 
'
n
o
w
'
:
 
8
9
,

 
'
d
i
d
'
:
 
9
0
,

 
'
b
e
i
n
g
'
:
 
9
1
,

 
'
t
h
e
i
r
'
:
 
9
2
,

 
'
t
h
a
n
'
:
 
9
3
,

 
'
g
e
t
'
:
 
9
4
,

 
'
t
h
a
n
k
s
'
:
 
9
5
,

 
'
e
v
e
n
'
:
 
9
6
,

 
'
m
a
k
e
'
:
 
9
7
,

 
'
g
o
o
d
'
:
 
9
8
,

 
'
h
a
d
'
:
 
9
9
,

 
'
d
o
e
s
'
:
 
1
0
0
,

 
'
w
e
l
l
'
:
 
1
0
1
,

 
'
v
e
r
y
'
:
 
1
0
2
,

 
'
c
o
u
l
d
'
:
 
1
0
3
,

 
'
i
t
s
'
:
 
1
0
4
,

 
'
i
n
f
o
r
m
a
t
i
o
n
'
:
 
1
0
5
,

 
'
s
o
u
r
c
e
s
'
:
 
1
0
6
,

 
'
u
s
e
r
'
:
 
1
0
7
,

 
'
w
a
n
t
'
:
 
1
0
8
,

 
'
n
a
m
e
'
:
 
1
0
9
,

 
'
w
a
y
'
:
 
1
1
0
,

 
'
s
u
c
h
'
:
 
1
1
1
,

 
'
t
h
e
s
e
'
:
 
1
1
2
,

 
'
w
p
'
:
 
1
1
3
,

 
'
f
i
r
s
t
'
:
 
1
1
4
,

 
'
n
e
w
'
:
 
1
1
5
,

 
'
s
e
c
t
i
o
n
'
:
 
1
1
6
,

 
'
s
a
y
'
:
 
1
1
7
,

 
'
g
o
'
:
 
1
1
8
,

 
'
d
e
l
e
t
i
o
n
'
:
 
1
1
9
,

 
'
s
o
u
r
c
e
'
:
 
1
2
0
,

 
'
h
e
l
p
'
:
 
1
2
1
,

 
'
n
e
e
d
'
:
 
1
2
2
,

 
'
i
m
a
g
e
'
:
 
1
2
3
,

 
'
p
a
g
e
s
'
:
 
1
2
4
,

 
'
w
h
e
r
e
'
:
 
1
2
5
,

 
'
r
e
a
l
l
y
'
:
 
1
2
6
,

 
'
a
g
a
i
n
'
:
 
1
2
7
,

 
'
m
u
c
h
'
:
 
1
2
8
,

 
'
e
d
i
t
i
n
g
'
:
 
1
2
9
,

 
'
m
a
n
y
'
:
 
1
3
0
,

 
'
m
a
d
e
'
:
 
1
3
1
,

 
'
m
o
s
t
'
:
 
1
3
2
,

 
'
u
s
e
d
'
:
 
1
3
3
,

 
'
t
h
a
n
k
'
:
 
1
3
4
,

 
'
i
n
t
o
'
:
 
1
3
5
,

 
'
f
i
n
d
'
:
 
1
3
6
,

 
"
i
'
v
e
"
:
 
1
3
7
,

 
'
d
i
s
c
u
s
s
i
o
n
'
:
 
1
3
8
,

 
'
s
a
m
e
'
:
 
1
3
9
,

 
'
e
d
i
t
s
'
:
 
1
4
0
,

 
'
t
h
o
s
e
'
:
 
1
4
1
,

 
'
w
o
r
k
'
:
 
1
4
2
,

 
'
r
i
g
h
t
'
:
 
1
4
3
,

 
'
s
i
n
c
e
'
:
 
1
4
4
,

 
'
p
o
i
n
t
'
:
 
1
4
5
,

 
'
d
e
l
e
t
e
d
'
:
 
1
4
6
,

 
'
l
o
o
k
'
:
 
1
4
7
,

 
'
o
v
e
r
'
:
 
1
4
8
,

 
'
t
w
o
'
:
 
1
4
9
,

 
'
b
e
f
o
r
e
'
:
 
1
5
0
,

 
'
a
f
t
e
r
'
:
 
1
5
1
,

 
'
a
d
d
'
:
 
1
5
2
,

 
'
s
t
i
l
l
'
:
 
1
5
3
,

 
'
h
i
m
'
:
 
1
5
4
,

 
'
t
o
o
'
:
 
1
5
5
,

 
'
r
e
a
d
'
:
 
1
5
6
,

 
'
b
a
c
k
'
:
 
1
5
7
,

 
'
s
o
m
e
o
n
e
'
:
 
1
5
8
,

 
'
t
a
k
e
'
:
 
1
5
9
,

 
'
2
'
:
 
1
6
0
,

 
'
l
i
s
t
'
:
 
1
6
1
,

 
'
1
'
:
 
1
6
2
,

 
'
s
o
m
e
t
h
i
n
g
'
:
 
1
6
3
,

 
"
y
o
u
'
r
e
"
:
 
1
6
4
,

 
'
g
o
i
n
g
'
:
 
1
6
5
,

 
'
f
a
c
t
'
:
 
1
6
6
,

 
'
s
a
i
d
'
:
 
1
6
7
,

 
'
u
'
:
 
1
6
8
,

 
'
l
i
n
k
'
:
 
1
6
9
,

 
'
o
w
n
'
:
 
1
7
0
,

 
'
s
t
o
p
'
:
 
1
7
1
,

 
'
h
e
r
'
:
 
1
7
2
,

 
'
a
d
d
e
d
'
:
 
1
7
3
,

 
'
c
o
n
t
e
n
t
'
:
 
1
7
4
,

 
'
o
u
r
'
:
 
1
7
5
,

 
'
h
t
t
p
'
:
 
1
7
6
,

 
'
w
i
t
h
o
u
t
'
:
 
1
7
7
,

 
'
h
i
'
:
 
1
7
8
,

 
'
h
i
s
t
o
r
y
'
:
 
1
7
9
,

 
'
w
i
k
i
'
:
 
1
8
0
,

 
"
d
o
e
s
n
'
t
"
:
 
1
8
1
,

 
'
u
n
d
e
r
'
:
 
1
8
2
,

 
'
a
n
o
t
h
e
r
'
:
 
1
8
3
,

 
'
m
i
g
h
t
'
:
 
1
8
4
,

 
"
t
h
a
t
'
s
"
:
 
1
8
5
,

 
'
s
u
r
e
'
:
 
1
8
6
,

 
'
r
e
m
o
v
e
d
'
:
 
1
8
7
,

 
'
b
l
o
c
k
e
d
'
:
 
1
8
8
,

 
'
s
h
e
'
:
 
1
8
9
,

 
'
s
t
y
l
e
'
:
 
1
9
0
,

 
'
u
s
'
:
 
1
9
1
,

 
'
o
f
f
'
:
 
1
9
2
,

 
'
n
o
t
e
'
:
 
1
9
3
,

 
'
g
a
y
'
:
 
1
9
4
,

 
'
s
e
e
m
s
'
:
 
1
9
5
,

 
'
w
e
l
c
o
m
e
'
:
 
1
9
6
,

 
'
h
o
w
e
v
e
r
'
:
 
1
9
7
,

 
'
c
a
s
e
'
:
 
1
9
8
,

 
'
n
e
v
e
r
'
:
 
1
9
9
,

 
'
f
r
e
e
'
:
 
2
0
0
,

 
'
b
e
t
t
e
r
'
:
 
2
0
1
,

 
'
p
l
a
c
e
'
:
 
2
0
2
,

 
'
a
c
t
u
a
l
l
y
'
:
 
2
0
3
,

 
'
p
u
t
'
:
 
2
0
4
,

 
'
e
d
i
t
o
r
s
'
:
 
2
0
5
,

 
'
c
o
m
m
e
n
t
'
:
 
2
0
6
,

 
'
d
o
n
e
'
:
 
2
0
7
,

 
'
w
h
i
l
e
'
:
 
2
0
8
,

 
'
u
s
i
n
g
'
:
 
2
0
9
,

 
'
b
o
t
h
'
:
 
2
1
0
,

 
'
f
e
e
l
'
:
 
2
1
1
,

 
'
r
e
a
s
o
n
'
:
 
2
1
2
,

 
'
b
l
o
c
k
'
:
 
2
1
3
,

 
'
q
u
e
s
t
i
o
n
'
:
 
2
1
4
,

 
'
a
n
y
t
h
i
n
g
'
:
 
2
1
5
,

 
'
u
t
c
'
:
 
2
1
6
,

 
'
v
a
n
d
a
l
i
s
m
'
:
 
2
1
7
,

 
'
t
h
i
n
g
s
'
:
 
2
1
8
,

 
'
a
s
k
'
:
 
2
1
9
,

 
'
b
e
l
i
e
v
e
'
:
 
2
2
0
,

 
'
b
e
s
t
'
:
 
2
2
1
,

 
'
p
e
r
s
o
n
'
:
 
2
2
2
,

 
'
p
a
r
t
'
:
 
2
2
3
,

 
'
l
i
n
k
s
'
:
 
2
2
4
,

 
'
y
o
u
r
s
e
l
f
'
:
 
2
2
5
,

 
'
h
o
p
e
'
:
 
2
2
6
,

 
'
s
h
i
t
'
:
 
2
2
7
,

 
'
t
h
i
n
g
'
:
 
2
2
8
,

 
"
c
a
n
'
t
"
:
 
2
2
9
,

 
'
p
o
l
i
c
y
'
:
 
2
3
0
,

 
"
i
'
l
l
"
:
 
2
3
1
,

 
'
n
i
g
g
e
r
'
:
 
2
3
2
,

 
'
3
'
:
 
2
3
3
,

 
'
c
o
m
m
e
n
t
s
'
:
 
2
3
4
,

 
'
l
i
t
t
l
e
'
:
 
2
3
5
,

 
'
c
h
a
n
g
e
'
:
 
2
3
6
,

 
'
a
l
r
e
a
d
y
'
:
 
2
3
7
,

 
'
t
h
o
u
g
h
'
:
 
2
3
8
,

 
"
d
i
d
n
'
t
"
:
 
2
3
9
,

 
'
f
u
c
k
i
n
g
'
:
 
2
4
0
,

 
'
n
o
t
h
i
n
g
'
:
 
2
4
1
,

 
'
p
e
r
s
o
n
a
l
'
:
 
2
4
2
,

 
'
c
o
m
'
:
 
2
4
3
,

 
'
w
o
r
l
d
'
:
 
2
4
4
,

 
'
m
u
s
t
'
:
 
2
4
5
,

 
'
k
e
e
p
'
:
 
2
4
6
,

 
'
w
r
o
n
g
'
:
 
2
4
7
,

 
'
a
g
a
i
n
s
t
'
:
 
2
4
8
,

 
'
p
r
o
b
l
e
m
'
:
 
2
4
9
,

 
'
l
o
n
g
'
:
 
2
5
0
,

 
'
e
n
g
l
i
s
h
'
:
 
2
5
1
,

 
'
•
'
:
 
2
5
2
,

 
'
t
e
x
t
'
:
 
2
5
3
,

 
'
q
u
e
s
t
i
o
n
s
'
:
 
2
5
4
,

 
'
a
b
o
v
e
'
:
 
2
5
5
,

 
'
r
e
m
o
v
e
'
:
 
2
5
6
,

 
'
s
u
b
j
e
c
t
'
:
 
2
5
7
,

 
'
g
i
v
e
'
:
 
2
5
8
,

 
'
a
n
y
o
n
e
'
:
 
2
5
9
,

 
'
f
e
w
'
:
 
2
6
0
,

 
'
r
e
l
i
a
b
l
e
'
:
 
2
6
1
,

 
'
l
a
s
t
'
:
 
2
6
2
,

 
'
a
g
r
e
e
'
:
 
2
6
3
,

 
'
r
a
t
h
e
r
'
:
 
2
6
4
,

 
'
e
'
:
 
2
6
5
,

 
'
s
u
c
k
'
:
 
2
6
6
,

 
'
i
s
s
u
e
'
:
 
2
6
7
,

 
'
t
r
y
i
n
g
'
:
 
2
6
8
,

 
'
c
o
m
e
'
:
 
2
6
9
,

 
'
w
o
r
d
'
:
 
2
7
0
,

 
'
d
i
f
f
e
r
e
n
t
'
:
 
2
7
1
,

 
'
c
o
p
y
r
i
g
h
t
'
:
 
2
7
2
,

 
'
r
e
f
e
r
e
n
c
e
'
:
 
2
7
3
,

 
'
y
e
a
r
s
'
:
 
2
7
4
,

 
'
u
n
d
e
r
s
t
a
n
d
'
:
 
2
7
5
,

 
'
m
e
a
n
'
:
 
2
7
6
,

 
'
t
a
g
'
:
 
2
7
7
,

 
'
l
e
t
'
:
 
2
7
8
,

 
'
t
o
p
'
:
 
2
7
9
,

 
'
s
o
r
r
y
'
:
 
2
8
0
,

 
'
n
o
n
'
:
 
2
8
1
,

 
'
g
o
t
'
:
 
2
8
2
,

 
'
s
'
:
 
2
8
3
,

 
'
g
r
e
a
t
'
:
 
2
8
4
,

 
"
i
s
n
'
t
"
:
 
2
8
5
,

 
'
s
a
y
s
'
:
 
2
8
6
,

 
'
o
t
h
e
r
s
'
:
 
2
8
7
,

 
'
p
r
o
b
a
b
l
y
'
:
 
2
8
8
,

 
'
t
r
y
'
:
 
2
8
9
,

 
'
m
a
k
i
n
g
'
:
 
2
9
0
,

 
'
f
o
u
n
d
'
:
 
2
9
1
,

 
'
e
d
i
t
o
r
'
:
 
2
9
2
,

 
'
s
p
e
e
d
y
'
:
 
2
9
3
,

 
'
—
'
:
 
2
9
4
,

 
'
r
e
f
e
r
e
n
c
e
s
'
:
 
2
9
5
,

 
'
y
e
s
'
:
 
2
9
6
,

 
'
s
t
a
t
e
'
:
 
2
9
7
,

 
'
d
o
i
n
g
'
:
 
2
9
8
,

 
'
o
r
i
g
i
n
a
l
'
:
 
2
9
9
,

 
'
l
i
f
e
'
:
 
3
0
0
,

 
'
s
t
u
p
i
d
'
:
 
3
0
1
,

 
'
f
a
i
r
'
:
 
3
0
2
,

 
'
d
a
y
'
:
 
3
0
3
,

 
'
e
i
t
h
e
r
'
:
 
3
0
4
,

 
'
e
n
o
u
g
h
'
:
 
3
0
5
,

 
'
e
v
e
r
y
'
:
 
3
0
6
,

 
'
c
o
n
t
i
n
u
e
'
:
 
3
0
7
,

 
'
l
e
a
s
t
'
:
 
3
0
8
,

 
'
s
i
m
p
l
y
'
:
 
3
0
9
,

 
'
a
d
d
i
n
g
'
:
 
3
1
0
,

 
'
e
x
a
m
p
l
e
'
:
 
3
1
1
,

 
'
w
w
w
'
:
 
3
1
2
,

 
'
f
a
r
'
:
 
3
1
3
,

 
'
s
h
o
w
'
:
 
3
1
4
,

 
'
a
r
o
u
n
d
'
:
 
3
1
5
,

 
'
c
a
l
l
e
d
'
:
 
3
1
6
,

 
'
l
e
a
v
e
'
:
 
3
1
7
,

 
'
p
o
o
p
'
:
 
3
1
8
,

 
'
c
o
n
s
e
n
s
u
s
'
:
 
3
1
9
,

 
'
h
e
l
l
o
'
:
 
3
2
0
,

 
'
e
t
c
'
:
 
3
2
1
,

 
'
d
o
w
n
'
:
 
3
2
2
,

 
'
n
e
e
d
s
'
:
 
3
2
3
,

 
'
p
e
n
i
s
'
:
 
3
2
4
,

 
'
r
e
a
l
'
:
 
3
2
5
,

 
'
w
a
r
'
:
 
3
2
6
,

 
'
o
p
i
n
i
o
n
'
:
 
3
2
7
,

 
'
c
h
e
c
k
'
:
 
3
2
8
,

 
'
b
e
t
w
e
e
n
'
:
 
3
2
9
,

 
'
t
h
r
o
u
g
h
'
:
 
3
3
0
,

 
'
e
l
s
e
'
:
 
3
3
1
,

 
'
t
h
o
u
g
h
t
'
:
 
3
3
2
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
:
 
3
3
3
,

 
'
i
p
'
:
 
3
3
4
,

 
'
v
i
e
w
'
:
 
3
3
5
,

 
'
r
e
q
u
e
s
t
'
:
 
3
3
6
,

 
'
b
o
o
k
'
:
 
3
3
7
,

 
'
t
i
t
l
e
'
:
 
3
3
8
,

 
'
g
i
v
e
n
'
:
 
3
3
9
,

 
'
a
s
s
'
:
 
3
4
0
,

 
'
s
i
t
e
'
:
 
3
4
1
,

 
'
n
o
t
a
b
l
e
'
:
 
3
4
2
,

 
'
o
l
d
'
:
 
3
4
3
,

 
'
i
m
a
g
e
s
'
:
 
3
4
4
,

 
'
p
o
s
t
'
:
 
3
4
5
,

 
'
m
a
t
e
r
i
a
l
'
:
 
3
4
6
,

 
'
s
u
p
p
o
r
t
'
:
 
3
4
7
,

 
'
l
o
t
'
:
 
3
4
8
,

 
'
e
v
e
r
'
:
 
3
4
9
,

 
'
w
r
i
t
e
'
:
 
3
5
0
,

 
'
y
e
t
'
:
 
3
5
1
,

 
'
m
a
y
b
e
'
:
 
3
5
2
,

 
'
t
e
r
m
'
:
 
3
5
3
,

 
'
m
a
t
t
e
r
'
:
 
3
5
4
,

 
'
h
a
v
i
n
g
'
:
 
3
5
5
,

 
'
d
e
l
e
t
e
'
:
 
3
5
6
,

 
'
r
e
'
:
 
3
5
7
,

 
'
s
a
y
i
n
g
'
:
 
3
5
8
,

 
'
b
i
t
'
:
 
3
5
9
,

 
'
h
a
t
e
'
:
 
3
6
0
,

 
'
l
a
n
g
u
a
g
e
'
:
 
3
6
1
,

 
'
d
i
e
'
:
 
3
6
2
,

 
'
5
'
:
 
3
6
3
,

 
'
s
e
e
m
'
:
 
3
6
4
,

 
'
4
'
:
 
3
6
5
,

 
'
b
a
d
'
:
 
3
6
6
,

 
"
i
'
d
"
:
 
3
6
7
,

 
'
r
e
v
e
r
t
e
d
'
:
 
3
6
8
,

 
'
a
l
w
a
y
s
'
:
 
3
6
9
,

 
'
t
e
m
p
l
a
t
e
'
:
 
3
7
0
,

 
'
q
u
i
t
e
'
:
 
3
7
1
,

 
'
n
u
m
b
e
r
'
:
 
3
7
2
,

 
'
t
e
l
l
'
:
 
3
7
3
,

 
'
c
o
r
r
e
c
t
'
:
 
3
7
4
,

 
'
p
e
r
h
a
p
s
'
:
 
3
7
5
,

 
'
c
'
:
 
3
7
6
,

 
'
m
e
s
s
a
g
e
'
:
 
3
7
7
,

 
'
b
i
t
c
h
'
:
 
3
7
8
,

 
'
r
e
v
i
e
w
'
:
 
3
7
9
,

 
'
t
r
u
e
'
:
 
3
8
0
,

 
'
c
l
e
a
r
'
:
 
3
8
1
,

 
'
i
n
s
t
e
a
d
'
:
 
3
8
2
,

 
'
c
l
e
a
r
l
y
'
:
 
3
8
3
,

 
'
e
n
c
y
c
l
o
p
e
d
i
a
'
:
 
3
8
4
,

 
'
w
h
e
t
h
e
r
'
:
 
3
8
5
,

 
'
s
t
a
t
e
s
'
:
 
3
8
6
,

 
'
a
c
c
o
u
n
t
'
:
 
3
8
7
,

 
'
u
n
t
i
l
'
:
 
3
8
8
,

 
'
e
v
i
d
e
n
c
e
'
:
 
3
8
9
,

 
'
m
e
d
i
a
'
:
 
3
9
0
,

 
'
w
r
i
t
t
e
n
'
:
 
3
9
1
,

 
'
m
e
n
t
i
o
n
'
:
 
3
9
2
,

 
'
i
m
p
o
r
t
a
n
t
'
:
 
3
9
3
,

 
'
r
e
s
e
a
r
c
h
'
:
 
3
9
4
,

 
"
t
h
e
r
e
'
s
"
:
 
3
9
5
,

 
'
d
'
:
 
3
9
6
,

 
'
m
a
k
e
s
'
:
 
3
9
7
,

 
'
r
e
v
e
r
t
'
:
 
3
9
8
,

 
'
f
u
r
t
h
e
r
'
:
 
3
9
9
,

 
'
m
a
n
'
:
 
4
0
0
,

 
'
b
a
s
e
d
'
:
 
4
0
1
,

 
'
t
i
m
e
s
'
:
 
4
0
2
,

 
'
c
l
a
i
m
'
:
 
4
0
3
,

 
'
g
e
t
t
i
n
g
'
:
 
4
0
4
,

 
'
i
d
e
a
'
:
 
4
0
5
,

 
'
o
r
g
'
:
 
4
0
6
,

 
'
v
e
r
s
i
o
n
'
:
 
4
0
7
,

 
'
o
n
c
e
'
:
 
4
0
8
,

 
'
w
o
r
d
s
'
:
 
4
0
9
,

 
'
u
s
e
r
s
'
:
 
4
1
0
,

 
'
c
o
n
s
i
d
e
r
'
:
 
4
1
1
,

 
'
y
e
a
r
'
:
 
4
1
2
,

 
'
p
o
v
'
:
 
4
1
3
,

 
'
c
o
n
t
r
i
b
u
t
i
o
n
s
'
:
 
4
1
4
,

 
'
o
h
'
:
 
4
1
5
,

 
'
l
e
f
t
'
:
 
4
1
6
,

 
'
c
o
l
o
r
'
:
 
4
1
7
,

 
'
a
d
m
i
n
'
:
 
4
1
8
,

 
'
c
o
n
s
i
d
e
r
e
d
'
:
 
4
1
9
,

 
'
t
h
r
e
e
'
:
 
4
2
0
,

 
'
w
e
b
s
i
t
e
'
:
 
4
2
1
,

 
'
c
h
a
n
g
e
s
'
:
 
4
2
2
,

 
'
b
i
g
'
:
 
4
2
3
,

 
'
c
u
r
r
e
n
t
'
:
 
4
2
4
,

 
'
m
e
a
n
s
'
:
 
4
2
5
,

 
'
s
t
a
r
t
'
:
 
4
2
6
,

 
'
g
u
i
d
e
l
i
n
e
s
'
:
 
4
2
7
,

 
'
a
m
e
r
i
c
a
n
'
:
 
4
2
8
,

 
'
c
u
n
t
'
:
 
4
2
9
,

 
'
s
e
v
e
r
a
l
'
:
 
4
3
0
,

 
'
c
a
n
n
o
t
'
:
 
4
3
1
,

 
'
m
a
i
n
'
:
 
4
3
2
,

 
'
e
a
c
h
'
:
 
4
3
3
,

 
'
c
r
i
t
e
r
i
a
'
:
 
4
3
4
,

 
'
d
a
t
e
'
:
 
4
3
5
,

 
'
g
e
n
e
r
a
l
'
:
 
4
3
6
,

 
'
s
e
c
o
n
d
'
:
 
4
3
7
,

 
'
g
r
o
u
p
'
:
 
4
3
8
,

 
'
r
e
d
i
r
e
c
t
'
:
 
4
3
9
,

 
'
l
i
s
t
e
d
'
:
 
4
4
0
,

 
'
p
o
s
s
i
b
l
e
'
:
 
4
4
1
,

 
'
w
h
o
l
e
'
:
 
4
4
2
,

 
'
c
o
u
r
s
e
'
:
 
4
4
3
,

 
'
f
a
g
g
o
t
'
:
 
4
4
4
,

 
'
m
e
n
t
i
o
n
e
d
'
:
 
4
4
5
,

 
'
s
e
e
n
'
:
 
4
4
6
,

 
'
t
o
p
i
c
'
:
 
4
4
7
,

 
'
i
n
c
l
u
d
e
'
:
 
4
4
8
,

 
'
k
i
n
d
'
:
 
4
4
9
,

 
'
b
a
c
k
g
r
o
u
n
d
'
:
 
4
5
0
,

 
'
f
o
l
l
o
w
i
n
g
'
:
 
4
5
1
,

 
'
1
0
'
:
 
4
5
2
,

 
'
e
n
d
'
:
 
4
5
3
,

 
'
n
o
t
i
c
e
'
:
 
4
5
4
,

 
'
h
e
y
'
:
 
4
5
5
,

 
'
r
e
g
a
r
d
i
n
g
'
:
 
4
5
6
,

 
'
s
t
a
t
e
m
e
n
t
'
:
 
4
5
7
,

 
'
c
a
l
l
'
:
 
4
5
8
,

 
'
a
d
d
r
e
s
s
'
:
 
4
5
9
,

 
'
m
o
v
e
'
:
 
4
6
0
,

 
'
0
'
:
 
4
6
1
,

 
'
l
e
s
s
'
:
 
4
6
2
,

 
'
o
k
'
:
 
4
6
3
,

 
'
i
s
s
u
e
s
'
:
 
4
6
4
,

 
'
s
e
n
t
e
n
c
e
'
:
 
4
6
5
,

 
'
c
a
r
e
'
:
 
4
6
6
,

 
'
k
n
o
w
n
'
:
 
4
6
7
,

 
'
s
u
g
g
e
s
t
'
:
 
4
6
8
,

 
'
s
e
n
s
e
'
:
 
4
6
9
,

 
'
r
e
l
a
t
e
d
'
:
 
4
7
0
,

 
'
c
r
e
a
t
e
'
:
 
4
7
1
,

 
'
j
p
g
'
:
 
4
7
2
,

 
'
i
n
c
l
u
d
i
n
g
'
:
 
4
7
3
,

 
'
e
n
'
:
 
4
7
4
,

 
'
r
u
l
e
s
'
:
 
4
7
5
,

 
'
d
o
n
t
'
:
 
4
7
6
,

 
'
l
o
v
e
'
:
 
4
7
7
,

 
'
c
a
t
e
g
o
r
y
'
:
 
4
7
8
,

 
'
f
a
c
t
s
'
:
 
4
7
9
,

 
'
s
c
h
o
o
l
'
:
 
4
8
0
,

 
'
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
'
:
 
4
8
1
,

 
'
h
a
p
p
y
'
:
 
4
8
2
,

 
'
s
e
x
'
:
 
4
8
3
,

 
'
n
e
w
s
'
:
 
4
8
4
,

 
'
c
h
a
n
g
e
d
'
:
 
4
8
5
,

 
'
p
i
c
t
u
r
e
'
:
 
4
8
6
,

 
'
i
n
f
o
'
:
 
4
8
7
,

 
'
l
i
n
e
'
:
 
4
8
8
,

 
'
m
i
n
d
'
:
 
4
8
9
,

 
'
n
e
x
t
'
:
 
4
9
0
,

 
'
l
o
o
k
i
n
g
'
:
 
4
9
1
,

 
'
f
o
u
r
'
:
 
4
9
2
,

 
'
p
r
o
j
e
c
t
'
:
 
4
9
3
,

 
'
s
p
e
c
i
f
i
c
'
:
 
4
9
4
,

 
'
a
n
y
w
a
y
'
:
 
4
9
5
,

 
'
d
a
y
s
'
:
 
4
9
6
,

 
'
p
e
r
'
:
 
4
9
7
,

 
'
p
r
o
v
i
d
e
'
:
 
4
9
8
,

 
'
m
y
s
e
l
f
'
:
 
4
9
9
,

 
'
a
l
t
h
o
u
g
h
'
:
 
5
0
0
,

 
'
p
'
:
 
5
0
1
,

 
'
i
n
c
l
u
d
e
d
'
:
 
5
0
2
,

 
'
n
o
t
a
b
i
l
i
t
y
'
:
 
5
0
3
,

 
'
a
w
a
y
'
:
 
5
0
4
,

 
"
y
o
u
'
v
e
"
:
 
5
0
5
,

 
'
t
'
:
 
5
0
6
,

 
'
b
'
:
 
5
0
7
,

 
"
w
i
k
i
p
e
d
i
a
'
s
"
:
 
5
0
8
,

 
'
f
i
l
e
'
:
 
5
0
9
,

 
'
f
u
l
l
'
:
 
5
1
0
,

 
'
r
e
l
e
v
a
n
t
'
:
 
5
1
1
,

 
'
f
'
:
 
5
1
2
,

 
'
s
t
a
r
t
e
d
'
:
 
5
1
3
,

 
'
l
e
a
d
'
:
 
5
1
4
,

 
'
s
u
m
m
a
r
y
'
:
 
5
1
5
,

 
'
n
e
u
t
r
a
l
'
:
 
5
1
6
,

 
'
s
i
g
n
'
:
 
5
1
7
,

 
'
a
t
t
a
c
k
'
:
 
5
1
8
,

 
'
l
a
t
e
r
'
:
 
5
1
9
,

 
'
e
x
p
l
a
i
n
'
:
 
5
2
0
,

 
'
p
r
e
t
t
y
'
:
 
5
2
1
,

 
'
d
i
c
k
'
:
 
5
2
2
,

 
'
c
o
m
m
o
n
'
:
 
5
2
3
,

 
'
–
'
:
 
5
2
4
,

 
'
a
n
s
w
e
r
'
:
 
5
2
5
,

 
'
l
o
o
k
s
'
:
 
5
2
6
,

 
'
o
r
d
e
r
'
:
 
5
2
7
,

 
'
s
i
n
g
l
e
'
:
 
5
2
8
,

 
'
r
e
c
e
n
t
'
:
 
5
2
9
,

 
'
r
e
m
o
v
i
n
g
'
:
 
5
3
0
,

 
'
s
u
c
k
s
'
:
 
5
3
1
,

 
'
a
l
i
g
n
'
:
 
5
3
2
,

 
'
b
l
a
c
k
'
:
 
5
3
3
,

 
'
c
u
r
r
e
n
t
l
y
'
:
 
5
3
4
,

 
'
2
0
0
5
'
:
 
5
3
5
,

 
'
s
t
u
f
f
'
:
 
5
3
6
,

 
'
g
o
d
'
:
 
5
3
7
,

 
'
c
l
a
i
m
s
'
:
 
5
3
8
,

 
'
c
o
m
m
u
n
i
t
y
'
:
 
5
3
9
,

 
'
i
t
s
e
l
f
'
:
 
5
4
0
,

 
'
w
r
o
t
e
'
:
 
5
4
1
,

 
'
n
a
m
e
s
'
:
 
5
4
2
,

 
'
e
s
p
e
c
i
a
l
l
y
'
:
 
5
4
3
,

 
'
d
e
'
:
 
5
4
4
,

 
'
e
v
e
r
y
o
n
e
'
:
 
5
4
5
,

 
'
c
o
u
n
t
r
y
'
:
 
5
4
6
,

 
'
d
u
r
i
n
g
'
:
 
5
4
7
,

 
'
w
i
s
h
'
:
 
5
4
8
,

 
'
h
e
l
l
'
:
 
5
4
9
,

 
'
p
u
b
l
i
c
'
:
 
5
5
0
,

 
'
c
e
r
t
a
i
n
l
y
'
:
 
5
5
1
,

 
'
h
a
r
d
'
:
 
5
5
2
,

 
'
w
r
i
t
i
n
g
'
:
 
5
5
3
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
e
d
'
:
 
5
5
4
,

 
'
t
a
k
e
n
'
:
 
5
5
5
,

 
'
w
i
t
h
i
n
'
:
 
5
5
6
,

 
'
a
p
p
e
a
r
s
'
:
 
5
5
7
,

 
'
6
'
:
 
5
5
8
,

 
'
a
b
l
e
'
:
 
5
5
9
,

 
'
1
0
0
'
:
 
5
6
0
,

 
'
a
n
t
i
'
:
 
5
6
1
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
'
:
 
5
6
2
,

 
'
d
i
s
c
u
s
s
'
:
 
5
6
3
,

 
'
h
i
g
h
'
:
 
5
6
4
,

 
'
u
n
l
e
s
s
'
:
 
5
6
5
,

 
'
g
a
m
e
'
:
 
5
6
6
,

 
'
b
e
l
o
w
'
:
 
5
6
7
,

 
'
o
f
f
i
c
i
a
l
'
:
 
5
6
8
,

 
'
0
0
0
'
:
 
5
6
9
,

 
'
p
o
l
i
c
i
e
s
'
:
 
5
7
0
,

 
'
s
e
l
f
'
:
 
5
7
1
,

 
"
h
e
'
s
"
:
 
5
7
2
,

 
'
n
i
c
e
'
:
 
5
7
3
,

 
'
c
o
m
p
l
e
t
e
l
y
'
:
 
5
7
4
,

 
'
p
o
s
i
t
i
o
n
'
:
 
5
7
5
,

 
'
r
e
p
o
r
t
'
:
 
5
7
6
,

 
'
w
a
n
t
e
d
'
:
 
5
7
7
,

 
'
w
h
i
t
e
'
:
 
5
7
8
,

 
'
a
c
c
o
r
d
i
n
g
'
:
 
5
7
9
,

 
'
e
v
e
r
y
t
h
i
n
g
'
:
 
5
8
0
,

 
'
7
'
:
 
5
8
1
,

 
'
q
u
o
t
e
'
:
 
5
8
2
,

 
'
l
o
l
'
:
 
5
8
3
,

 
'
r
e
m
e
m
b
e
r
'
:
 
5
8
4
,

 
'
c
a
m
e
'
:
 
5
8
5
,

 
'
w
e
b
'
:
 
5
8
6
,

 
'
w
a
r
n
i
n
g
'
:
 
5
8
7
,

 
'
f
a
i
t
h
'
:
 
5
8
8
,

 
'
c
o
c
k
'
:
 
5
8
9
,

 
'
b
o
o
k
s
'
:
 
5
9
0
,

 
'
r
e
a
d
i
n
g
'
:
 
5
9
1
,

 
'
p
u
b
l
i
s
h
e
d
'
:
 
5
9
2
,

 
"
w
a
s
n
'
t
"
:
 
5
9
3
,

 
'
b
a
l
l
s
'
:
 
5
9
4
,

 
'
l
e
a
r
n
'
:
 
5
9
5
,

 
'
d
u
e
'
:
 
5
9
6
,

 
'
l
i
v
e
'
:
 
5
9
7
,

 
'
c
l
a
s
s
'
:
 
5
9
8
,

 
'
p
r
o
c
e
s
s
'
:
 
5
9
9
,

 
'
p
a
r
a
g
r
a
p
h
'
:
 
6
0
0
,

 
'
e
n
t
r
y
'
:
 
6
0
1
,

 
'
f
u
t
u
r
e
'
:
 
6
0
2
,

 
'
2
0
'
:
 
6
0
3
,

 
'
p
a
r
t
y
'
:
 
6
0
4
,

 
'
o
b
v
i
o
u
s
l
y
'
:
 
6
0
5
,

 
'
s
t
a
y
'
:
 
6
0
6
,

 
'
t
h
e
r
e
f
o
r
e
'
:
 
6
0
7
,

 
'
g
'
:
 
6
0
8
,

 
'
t
a
l
k
i
n
g
'
:
 
6
0
9
,

 
'
s
m
a
l
l
'
:
 
6
1
0
,

 
'
u
s
e
f
u
l
'
:
 
6
1
1
,

 
'
s
a
n
d
b
o
x
'
:
 
6
1
2
,

 
'
g
u
y
'
:
 
6
1
3
,

 
'
p
o
l
i
t
i
c
a
l
'
:
 
6
1
4
,

 
'
g
o
o
g
l
e
'
:
 
6
1
5
,

 
'
1
1
'
:
 
6
1
6
,

 
'
w
h
a
t
e
v
e
r
'
:
 
6
1
7
,

 
'
s
i
m
i
l
a
r
'
:
 
6
1
8
,

 
'
a
t
t
a
c
k
s
'
:
 
6
1
9
,

 
'
g
o
v
e
r
n
m
e
n
t
'
:
 
6
2
0
,

 
'
n
o
r
'
:
 
6
2
1
,

 
'
8
'
:
 
6
2
2
,

 
'
t
o
d
a
y
'
:
 
6
2
3
,

 
"
w
o
n
'
t
"
:
 
6
2
4
,

 
'
s
y
s
t
e
m
'
:
 
6
2
5
,

 
'
i
n
v
o
l
v
e
d
'
:
 
6
2
6
,

 
'
a
r
g
u
m
e
n
t
'
:
 
6
2
7
,

 
'
c
i
t
y
'
:
 
6
2
8
,

 
'
p
a
s
t
'
:
 
6
2
9
,

 
'
w
o
r
k
i
n
g
'
:
 
6
3
0
,

 
'
\
x
a
0
'
:
 
6
3
1
,

 
'
l
a
r
g
e
'
:
 
6
3
2
,

 
'
a
g
o
'
:
 
6
3
3
,

 
'
e
x
a
c
t
l
y
'
:
 
6
3
4
,

 
'
o
f
t
e
n
'
:
 
6
3
5
,

 
'
a
s
k
e
d
'
:
 
6
3
6
,

 
'
e
d
i
t
e
d
'
:
 
6
3
7
,

 
'
s
e
a
r
c
h
'
:
 
6
3
8
,

 
'
r
e
s
p
o
n
s
e
'
:
 
6
3
9
,

 
'
a
d
m
i
n
s
'
:
 
6
4
0
,

 
'
f
o
r
m
'
:
 
6
4
1
,

 
'
b
r
i
t
i
s
h
'
:
 
6
4
2
,

 
'
u
n
i
t
e
d
'
:
 
6
4
3
,

 
'
n
o
n
s
e
n
s
e
'
:
 
6
4
4
,

 
'
w
i
k
i
p
r
o
j
e
c
t
'
:
 
6
4
5
,

 
'
p
a
r
t
i
c
u
l
a
r
'
:
 
6
4
6
,

 
'
r
e
g
a
r
d
s
'
:
 
6
4
7
,

 
'
1
2
'
:
 
6
4
8
,

 
'
l
a
w
'
:
 
6
4
9
,

 
'
g
u
e
s
s
'
:
 
6
5
0
,

 
'
t
o
o
k
'
:
 
6
5
1
,

 
'
r
e
a
s
o
n
s
'
:
 
6
5
2
,

 
'
m
u
s
i
c
'
:
 
6
5
3
,

 
'
s
i
d
e
'
:
 
6
5
4
,

 
'
2
0
0
6
'
:
 
6
5
5
,

 
'
t
r
u
t
h
'
:
 
6
5
6
,

 
'
a
l
m
o
s
t
'
:
 
6
5
7
,

 
'
n
o
t
i
c
e
d
'
:
 
6
5
8
,

 
'
f
i
l
m
'
:
 
6
5
9
,

 
'
d
e
f
i
n
i
t
i
o
n
'
:
 
6
6
0
,

 
'
b
e
c
o
m
e
'
:
 
6
6
1
,

 
'
p
o
w
e
r
'
:
 
6
6
2
,

 
'
n
e
e
d
e
d
'
:
 
6
6
3
,

 
'
m
a
j
o
r
'
:
 
6
6
4
,

 
'
f
i
n
e
'
:
 
6
6
5
,

 
'
f
i
v
e
'
:
 
6
6
6
,

 
'
t
e
r
m
s
'
:
 
6
6
7
,

 
'
p
l
a
c
e
d
'
:
 
6
6
8
,

 
'
c
h
e
e
r
s
'
:
 
6
6
9
,

 
'
p
o
s
t
e
d
'
:
 
6
7
0
,

 
'
v
a
n
d
a
l
i
z
e
'
:
 
6
7
1
,

 
'
c
o
m
p
a
n
y
'
:
 
6
7
2
,

 
'
s
h
o
r
t
'
:
 
6
7
3
,

 
'
l
i
k
e
l
y
'
:
 
6
7
4
,

 
'
9
'
:
 
6
7
5
,

 
'
d
i
s
p
u
t
e
'
:
 
6
7
6
,

 
'
a
l
o
n
g
'
:
 
6
7
7
,

 
'
p
r
o
b
l
e
m
s
'
:
 
6
7
8
,

 
'
f
a
l
s
e
'
:
 
6
7
9
,

 
'
n
a
t
i
o
n
a
l
'
:
 
6
8
0
,

 
'
n
p
o
v
'
:
 
6
8
1
,

 
'
b
o
r
d
e
r
'
:
 
6
8
2
,

 
'
u
k
'
:
 
6
8
3
,

 
'
o
t
h
e
r
w
i
s
e
'
:
 
6
8
4
,

 
'
a
p
p
r
e
c
i
a
t
e
'
:
 
6
8
5
,

 
'
w
i
d
t
h
'
:
 
6
8
6
,

 
'
s
a
w
'
:
 
6
8
7
,

 
'
y
o
u
f
u
c
k
'
:
 
6
8
8
,

 
'
f
a
t
'
:
 
6
8
9
,

 
'
s
t
o
r
y
'
:
 
6
9
0
,

 
'
s
t
a
t
u
s
'
:
 
6
9
1
,

 
'
m
o
v
e
d
'
:
 
6
9
2
,

 
'
p
r
e
s
e
n
t
'
:
 
6
9
3
,

 
'
o
'
:
 
6
9
4
,

 
'
c
i
t
e
d
'
:
 
6
9
5
,

 
'
d
e
a
t
h
'
:
 
6
9
6
,

 
'
s
h
o
w
s
'
:
 
6
9
7
,

 
'
p
o
i
n
t
s
'
:
 
6
9
8
,

 
'
1
5
'
:
 
6
9
9
,

 
'
a
r
e
a
'
:
 
7
0
0
,

 
'
g
e
n
e
r
a
l
l
y
'
:
 
7
0
1
,

 
"
h
a
v
e
n
'
t
"
:
 
7
0
2
,

 
'
t
a
k
i
n
g
'
:
 
7
0
3
,

 
'
2
4
'
:
 
7
0
4
,

 
'
t
r
i
e
d
'
:
 
7
0
5
,

 
'
k
i
l
l
'
:
 
7
0
6
,

 
'
s
e
t
'
:
 
7
0
7
,

 
'
s
o
r
t
'
:
 
7
0
8
,

 
'
o
p
e
n
'
:
 
7
0
9
,

 
'
2
0
0
7
'
:
 
7
1
0
,

 
'
f
o
l
l
o
w
'
:
 
7
1
1
,

 
'
u
s
e
r
n
a
m
e
'
:
 
7
1
2
,

 
'
r
e
c
e
n
t
l
y
'
:
 
7
1
3
,

 
'
2
0
0
8
'
:
 
7
1
4
,

 
'
h
u
m
a
n
'
:
 
7
1
5
,

 
'
s
t
a
t
e
d
'
:
 
7
1
6
,

 
'
c
i
t
a
t
i
o
n
'
:
 
7
1
7
,

 
'
d
e
l
e
t
i
n
g
'
:
 
7
1
8
,

 
'
f
a
m
i
l
y
'
:
 
7
1
9
,

 
'
c
e
r
t
a
i
n
'
:
 
7
2
0
,

 
'
j
e
w
s
'
:
 
7
2
1
,

 
'
t
y
p
e
'
:
 
7
2
2
,

 
'
r
u
l
e
'
:
 
7
2
3
,

 
'
v
e
r
t
i
c
a
l
'
:
 
7
2
4
,

 
'
c
i
t
e
'
:
 
7
2
5
,

 
'
p
i
e
c
e
'
:
 
7
2
6
,

 
'
e
n
t
i
r
e
'
:
 
7
2
7
,

 
'
i
m
'
:
 
7
2
8
,

 
'
m
i
d
d
l
e
'
:
 
7
2
9
,

 
'
s
o
o
n
'
:
 
7
3
0
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
:
 
7
3
1
,

 
'
c
o
n
t
e
x
t
'
:
 
7
3
2
,

 
'
e
x
p
l
a
n
a
t
i
o
n
'
:
 
7
3
3
,

 
'
i
n
d
e
e
d
'
:
 
7
3
4
,

 
'
m
o
t
h
e
r
'
:
 
7
3
5
,

 
'
p
r
o
v
i
d
e
d
'
:
 
7
3
6
,

 
'
r
e
v
e
r
t
i
n
g
'
:
 
7
3
7
,

 
'
c
o
p
y
'
:
 
7
3
8
,

 
'
r
'
:
 
7
3
9
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
i
n
g
'
:
 
7
4
0
,

 
'
h
a
n
d
'
:
 
7
4
1
,

 
'
g
u
y
s
'
:
 
7
4
2
,

 
'
a
c
t
u
a
l
'
:
 
7
4
3
,

 
'
u
p
l
o
a
d
e
d
'
:
 
7
4
4
,

 
'
r
e
p
l
y
'
:
 
7
4
5
,

 
'
b
a
n
d
'
:
 
7
4
6
,

 
'
g
e
r
m
a
n
'
:
 
7
4
7
,

 
'
k
n
o
w
l
e
d
g
e
'
:
 
7
4
8
,

 
'
a
w
a
r
e
'
:
 
7
4
9
,

 
'
s
i
m
p
l
e
'
:
 
7
5
0
,

 
'
v
i
e
w
s
'
:
 
7
5
1
,

 
'
w
o
r
k
s
'
:
 
7
5
2
,

 
'
a
d
m
i
n
i
s
t
r
a
t
o
r
'
:
 
7
5
3
,

 
'
a
p
p
e
a
r
'
:
 
7
5
4
,

 
'
o
b
v
i
o
u
s
'
:
 
7
5
5
,

 
"
w
o
u
l
d
n
'
t
"
:
 
7
5
6
,

 
'
a
l
o
n
e
'
:
 
7
5
7
,

 
'
i
m
p
r
o
v
e
'
:
 
7
5
8
,

 
'
t
h
e
m
s
e
l
v
e
s
'
:
 
7
5
9
,

 
'
y
e
a
h
'
:
 
7
6
0
,

 
'
u
n
i
v
e
r
s
i
t
y
'
:
 
7
6
1
,

 
'
i
d
i
o
t
'
:
 
7
6
2
,

 
'
m
'
:
 
7
6
3
,

 
'
d
e
c
i
d
e
'
:
 
7
6
4
,

 
'
t
h
e
o
r
y
'
:
 
7
6
5
,

 
'
w
e
e
k
'
:
 
7
6
6
,

 
"
a
r
e
n
'
t
"
:
 
7
6
7
,

 
'
e
x
t
e
r
n
a
l
'
:
 
7
6
8
,

 
'
j
o
h
n
'
:
 
7
6
9
,

 
'
t
a
g
s
'
:
 
7
7
0
,

 
'
w
e
n
t
'
:
 
7
7
1
,

 
'
t
h
u
s
'
:
 
7
7
2
,

 
'
b
a
n
n
e
d
'
:
 
7
7
3
,

 
'
p
r
o
p
o
s
e
d
'
:
 
7
7
4
,

 
'
s
o
u
r
c
e
d
'
:
 
7
7
5
,

 
'
s
t
a
n
d
a
r
d
'
:
 
7
7
6
,

 
'
r
e
s
u
l
t
'
:
 
7
7
7
,

 
'
t
o
l
d
'
:
 
7
7
8
,

 
'
a
t
t
e
n
t
i
o
n
'
:
 
7
7
9
,

 
'
s
e
r
i
o
u
s
l
y
'
:
 
7
8
0
,

 
'
c
i
t
a
t
i
o
n
s
'
:
 
7
8
1
,

 
'
t
h
i
r
d
'
:
 
7
8
2
,

 
'
v
a
r
i
o
u
s
'
:
 
7
8
3
,

 
'
o
n
e
s
'
:
 
7
8
4
,

 
"
t
h
e
y
'
r
e
"
:
 
7
8
5
,

 
'
i
n
t
e
r
n
e
t
'
:
 
7
8
6
,

 
'
n
'
:
 
7
8
7
,

 
'
x
'
:
 
7
8
8
,

 
'
d
i
s
a
g
r
e
e
'
:
 
7
8
9
,

 
'
c
o
m
e
s
'
:
 
7
9
0
,

 
'
m
e
a
n
i
n
g
'
:
 
7
9
1
,

 
'
c
o
n
t
r
i
b
s
'
:
 
7
9
2
,

 
'
j
o
b
'
:
 
7
9
3
,

 
'
e
m
a
i
l
'
:
 
7
9
4
,

 
'
m
e
m
b
e
r
s
'
:
 
7
9
5
,

 
'
c
o
m
p
l
e
t
e
'
:
 
7
9
6
,

 
'
t
e
s
t
'
:
 
7
9
7
,

 
'
m
r
'
:
 
7
9
8
,

 
"
'
"
:
 
7
9
9
,

 
'
1
4
'
:
 
8
0
0
,

 
'
c
o
n
f
l
i
c
t
'
:
 
8
0
1
,

 
'
s
e
r
i
e
s
'
:
 
8
0
2
,

 
'
g
o
e
s
'
:
 
8
0
3
,

 
'
s
o
l
i
d
'
:
 
8
0
4
,

 
'
a
v
o
i
d
'
:
 
8
0
5
,

 
'
l
o
n
g
e
r
'
:
 
8
0
6
,

 
"
s
h
o
u
l
d
n
'
t
"
:
 
8
0
7
,

 
'
p
r
e
v
i
o
u
s
'
:
 
8
0
8
,

 
'
l
i
v
i
n
g
'
:
 
8
0
9
,

 
'
h
e
a
d
'
:
 
8
1
0
,

 
'
v
a
n
d
a
l
'
:
 
8
1
1
,

 
'
h
a
p
p
e
n
e
d
'
:
 
8
1
2
,

 
'
a
d
d
i
t
i
o
n
'
:
 
8
1
3
,

 
'
c
o
n
t
a
c
t
'
:
 
8
1
4
,

 
'
w
'
:
 
8
1
5
,

 
'
1
6
'
:
 
8
1
6
,

 
"
a
r
t
i
c
l
e
'
s
"
:
 
8
1
7
,

 
'
b
a
n
'
:
 
8
1
8
,

 
'
a
l
l
o
w
e
d
'
:
 
8
1
9
,

 
'
h
e
a
r
d
'
:
 
8
2
0
,

 
'
c
o
n
t
r
i
b
u
t
i
n
g
'
:
 
8
2
1
,

 
'
d
e
a
l
'
:
 
8
2
2
,

 
'
p
r
o
p
e
r
'
:
 
8
2
3
,

 
'
s
c
i
e
n
c
e
'
:
 
8
2
4
,

 
'
c
a
l
l
i
n
g
'
:
 
8
2
5
,

 
'
v
i
d
e
o
'
:
 
8
2
6
,

 
'
e
n
j
o
y
'
:
 
8
2
7
,

 
'
u
s
u
a
l
l
y
'
:
 
8
2
8
,

 
'
h
i
m
s
e
l
f
'
:
 
8
2
9
,

 
'
s
i
t
e
s
'
:
 
8
3
0
,

 
'
a
u
t
h
o
r
'
:
 
8
3
1
,

 
'
c
r
e
a
t
i
n
g
'
:
 
8
3
2
,

 
'
n
e
c
e
s
s
a
r
y
'
:
 
8
3
3
,

 
'
e
x
i
s
t
'
:
 
8
3
4
,

 
"
w
h
a
t
'
s
"
:
 
8
3
5
,

 
'
s
p
a
c
e
'
:
 
8
3
6
,

 
'
b
u
l
l
s
h
i
t
'
:
 
8
3
7
,

 
'
2
0
0
9
'
:
 
8
3
8
,

 
'
l
e
v
e
l
'
:
 
8
3
9
,

 
'
t
o
g
e
t
h
e
r
'
:
 
8
4
0
,

 
'
j
e
w
i
s
h
'
:
 
8
4
1
,

 
'
a
v
a
i
l
a
b
l
e
'
:
 
8
4
2
,

 
'
s
e
c
t
i
o
n
s
'
:
 
8
4
3
,

 
'
2
0
1
0
'
:
 
8
4
4
,

 
'
h
e
l
p
f
u
l
'
:
 
8
4
5
,

 
'
c
a
u
s
e
'
:
 
8
4
6
,

 
'
a
s
s
h
o
l
e
'
:
 
8
4
7
,

 
'
f
a
g
'
:
 
8
4
8
,

 
"
'
'
'
'
'
'
"
:
 
8
4
9
,

 
'
j
u
l
y
'
:
 
8
5
0
,

 
'
a
c
t
i
o
n
'
:
 
8
5
1
,

 
'
v
'
:
 
8
5
2
,

 
'
1
3
'
:
 
8
5
3
,

 
'
a
u
t
o
m
a
t
i
c
a
l
l
y
'
:
 
8
5
4
,

 
'
r
e
s
t
'
:
 
8
5
5
,

 
"
l
e
t
'
s
"
:
 
8
5
6
,

 
'
o
p
i
n
i
o
n
s
'
:
 
8
5
7
,

 
'
s
e
r
i
o
u
s
'
:
 
8
5
8
,

 
'
a
s
s
u
m
e
'
:
 
8
5
9
,

 
'
a
f
d
'
:
 
8
6
0
,

 
'
w
o
r
k
e
d
'
:
 
8
6
1
,

 
'
a
c
t
'
:
 
8
6
2
,

 
'
s
t
a
t
e
m
e
n
t
s
'
:
 
8
6
3
,

 
'
3
0
'
:
 
8
6
4
,

 
'
d
a
t
a
'
:
 
8
6
5
,

 
'
d
e
b
a
t
e
'
:
 
8
6
6
,

 
'
h
o
u
r
s
'
:
 
8
6
7
,

 
'
1
8
'
:
 
8
6
8
,

 
'
m
u
l
t
i
p
l
e
'
:
 
8
6
9
,

 
'
v
a
l
i
d
'
:
 
8
7
0
,

 
'
b
i
a
s
'
:
 
8
7
1
,

 
'
m
a
n
u
a
l
'
:
 
8
7
2
,

 
'
p
e
r
s
o
n
a
l
l
y
'
:
 
8
7
3
,

 
'
c
l
o
s
e
'
:
 
8
7
4
,

 
'
m
e
m
b
e
r
'
:
 
8
7
5
,

 
'
r
e
s
p
e
c
t
'
:
 
8
7
6
,

 
'
d
e
t
a
i
l
s
'
:
 
8
7
7
,

 
'
1
7
'
:
 
8
7
8
,

 
'
p
l
a
y
'
:
 
8
7
9
,

 
'
c
r
a
p
'
:
 
8
8
0
,

 
'
r
u
n
'
:
 
8
8
1
,

 
'
f
i
x
'
:
 
8
8
2
,

 
'
s
o
u
t
h
'
:
 
8
8
3
,

 
'
s
e
p
a
r
a
t
e
'
:
 
8
8
4
,

 
'
h
i
s
t
o
r
i
c
a
l
'
:
 
8
8
5
,

 
'
r
e
c
o
r
d
'
:
 
8
8
6
,

 
'
a
c
c
u
r
a
t
e
'
:
 
8
8
7
,

 
"
y
o
u
'
l
l
"
:
 
8
8
8
,

 
'
a
c
c
e
p
t
'
:
 
8
8
9
,

 
'
k
'
:
 
8
9
0
,

 
'
2
2
'
:
 
8
9
1
,

 
'
m
o
n
t
h
s
'
:
 
8
9
2
,

 
'
d
o
u
b
t
'
:
 
8
9
3
,

 
'
g
e
t
s
'
:
 
8
9
4
,

 
'
c
r
i
t
i
c
i
s
m
'
:
 
8
9
5
,

 
'
f
a
c
e
'
:
 
8
9
6
,

 
'
c
o
u
p
l
e
'
:
 
8
9
7
,

 
'
e
a
r
l
y
'
:
 
8
9
8
,

 
'
b
i
a
s
e
d
'
:
 
8
9
9
,

 
'
t
i
l
d
e
s
'
:
 
9
0
0
,

 
'
m
o
r
o
n
'
:
 
9
0
1
,

 
'
r
e
f
e
r
'
:
 
9
0
2
,

 
'
a
t
t
e
m
p
t
'
:
 
9
0
3
,

 
'
a
c
c
e
p
t
e
d
'
:
 
9
0
4
,

 
'
s
o
n
g
'
:
 
9
0
5
,

 
'
r
i
g
h
t
s
'
:
 
9
0
6
,

 
'
t
a
b
l
e
'
:
 
9
0
7
,

 
'
b
o
r
n
'
:
 
9
0
8
,

 
'
v
o
t
e
'
:
 
9
0
9
,

 
'
o
n
l
i
n
e
'
:
 
9
1
0
,

 
'
p
h
o
t
o
'
:
 
9
1
1
,

 
'
2
1
'
:
 
9
1
2
,

 
'
p
r
i
m
a
r
y
'
:
 
9
1
3
,

 
'
r
a
c
i
s
t
'
:
 
9
1
4
,

 
'
a
c
t
i
o
n
s
'
:
 
9
1
5
,

 
'
c
h
u
r
c
h
'
:
 
9
1
6
,

 
'
t
a
g
g
e
d
'
:
 
9
1
7
,

 
'
q
u
a
l
i
t
y
'
:
 
9
1
8
,

 
'
1
9
'
:
 
9
1
9
,

 
'
i
n
d
i
c
a
t
e
'
:
 
9
2
0
,

 
'
v
i
o
l
a
t
i
o
n
'
:
 
9
2
1
,

 
'
w
i
k
i
p
e
d
i
a
n
'
:
 
9
2
2
,

 
'
w
a
t
c
h
'
:
 
9
2
3
,

 
'
l
e
g
a
l
'
:
 
9
2
4
,

 
'
n
o
n
e
'
:
 
9
2
5
,

 
'
l
a
c
k
'
:
 
9
2
6
,

 
'
s
o
c
k
'
:
 
9
2
7
,

 
'
a
p
p
a
r
e
n
t
l
y
'
:
 
9
2
8
,

 
'
u
p
o
n
'
:
 
9
2
9
,

 
'
d
i
f
f
e
r
e
n
c
e
'
:
 
9
3
0
,

 
'
d
e
a
d
'
:
 
9
3
1
,

 
'
c
o
u
n
t
r
i
e
s
'
:
 
9
3
2
,

 
'
r
e
d
'
:
 
9
3
3
,

 
'
i
n
d
i
a
'
:
 
9
3
4
,

 
'
d
i
r
e
c
t
l
y
'
:
 
9
3
5
,

 
'
b
o
x
'
:
 
9
3
6
,

 
'
o
k
a
y
'
:
 
9
3
7
,

 
'
u
s
e
s
'
:
 
9
3
8
,

 
'
p
e
r
i
o
d
'
:
 
9
3
9
,

 
'
s
i
t
u
a
t
i
o
n
'
:
 
9
4
0
,

 
'
m
e
a
n
t
'
:
 
9
4
1
,

 
'
h
t
m
l
'
:
 
9
4
2
,

 
'
s
o
m
e
t
i
m
e
s
'
:
 
9
4
3
,

 
'
c
h
a
n
g
i
n
g
'
:
 
9
4
4
,

 
'
e
x
c
e
p
t
'
:
 
9
4
5
,

 
'
p
r
o
o
f
'
:
 
9
4
6
,

 
'
s
p
e
c
i
a
l
'
:
 
9
4
7
,

 
'
m
o
d
e
r
n
'
:
 
9
4
8
,

 
'
d
i
c
k
s
'
:
 
9
4
9
,

 
'
t
h
i
n
k
i
n
g
'
:
 
9
5
0
,

 
'
2
0
1
2
'
:
 
9
5
1
,

 
'
s
p
e
c
i
f
i
c
a
l
l
y
'
:
 
9
5
2
,

 
'
m
a
r
c
h
'
:
 
9
5
3
,

 
'
d
a
m
n
'
:
 
9
5
4
,

 
'
2
3
'
:
 
9
5
5
,

 
'
c
u
l
t
u
r
e
'
:
 
9
5
6
,

 
'
d
e
s
c
r
i
b
e
d
'
:
 
9
5
7
,

 
'
e
x
p
l
a
i
n
i
n
g
'
:
 
9
5
8
,

 
'
s
i
g
n
i
f
i
c
a
n
t
'
:
 
9
5
9
,

 
'
r
e
l
e
a
s
e
'
:
 
9
6
0
,

 
'
c
a
s
e
s
'
:
 
9
6
1
,

 
'
s
i
z
e
'
:
 
9
6
2
,

 
'
r
a
t
i
o
n
a
l
e
'
:
 
9
6
3
,

 
'
e
a
t
'
:
 
9
6
4
,

 
'
i
n
f
o
b
o
x
'
:
 
9
6
5
,

 
'
t
e
a
m
'
:
 
9
6
6
,

 
'
a
l
b
u
m
'
:
 
9
6
7
,

 
'
u
n
b
l
o
c
k
'
:
 
9
6
8
,

 
'
2
0
1
1
'
:
 
9
6
9
,

 
'
a
s
k
i
n
g
'
:
 
9
7
0
,

 
'
m
i
l
i
t
a
r
y
'
:
 
9
7
1
,

 
'
s
u
p
p
o
s
e
d
'
:
 
9
7
2
,

 
'
a
m
o
n
g
'
:
 
9
7
3
,

 
'
i
n
c
o
r
r
e
c
t
'
:
 
9
7
4
,

 
'
i
n
c
l
u
s
i
o
n
'
:
 
9
7
5
,

 
'
h
a
l
f
'
:
 
9
7
6
,

 
'
i
n
t
e
r
n
a
t
i
o
n
a
l
'
:
 
9
7
7
,

 
'
n
i
g
g
e
r
s
'
:
 
9
7
8
,

 
'
u
n
s
i
g
n
e
d
'
:
 
9
7
9
,

 
'
p
u
r
p
o
s
e
'
:
 
9
8
0
,

 
'
a
u
g
u
s
t
'
:
 
9
8
1
,

 
'
s
p
e
a
k
'
:
 
9
8
2
,

 
'
c
o
m
i
n
g
'
:
 
9
8
3
,

 
'
p
r
o
v
e
'
:
 
9
8
4
,

 
'
o
u
t
s
i
d
e
'
:
 
9
8
5
,

 
'
e
x
i
s
t
i
n
g
'
:
 
9
8
6
,

 
'
c
i
v
i
l
'
:
 
9
8
7
,

 
'
w
a
n
k
e
r
'
:
 
9
8
8
,

 
'
m
e
s
s
a
g
e
s
'
:
 
9
8
9
,

 
"
w
e
'
r
e
"
:
 
9
9
0
,

 
'
5
0
'
:
 
9
9
1
,

 
'
w
o
m
e
n
'
:
 
9
9
2
,

 
'
p
o
s
s
i
b
l
y
'
:
 
9
9
3
,

 
'
j
e
w
'
:
 
9
9
4
,

 
'
f
i
e
l
d
'
:
 
9
9
5
,

 
'
w
o
r
t
h
'
:
 
9
9
6
,

 
'
m
i
l
l
i
o
n
'
:
 
9
9
7
,

 
'
h
o
u
s
e
'
:
 
9
9
8
,

 
'
w
a
i
t
'
:
 
9
9
9
,

 
'
b
a
s
t
a
r
d
'
:
 
1
0
0
0
,

 
.
.
.
}
</pre>

```python
T
K
.
w
o
r
d
_
c
o
u
n
t
s
[
"
t
o
x
i
c
"
]
```

<pre>
1
2
3
</pre>
a
l
l
d
a
t
a
의
 
'
c
o
m
m
e
n
t
_
t
e
x
t
'
 
c
o
l
u
m
n
만
 
따
로
 
t
e
x
t
로
 
정
의
하
고
,
 
숫
자
가
 
순
서
대
로
 
m
a
t
c
h
i
n
g
 
되
어
 
들
어
갑
니
다
.



```python
t
e
x
t
=
T
K
.
t
e
x
t
s
_
t
o
_
s
e
q
u
e
n
c
e
s
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
c
o
m
m
e
n
t
_
t
e
x
t
"
]
)

t
e
x
t
```

<pre>
[
[
7
3
3
,

 
 
7
8
,

 
 
1
,

 
 
1
4
0
,

 
 
1
3
1
,

 
 
1
8
2
,

 
 
3
0
,

 
 
7
1
2
,

 
 
4
4
3
8
,

 
 
1
0
2
8
4
,

 
 
1
2
5
2
,

 
 
8
6
,

 
 
3
6
8
,

 
 
5
1
,

 
 
2
2
3
0
,

 
 
1
4
0
3
9
,

 
 
4
9
,

 
 
6
7
4
4
,

 
 
1
5
,

 
 
6
0
,

 
 
2
6
2
4
,

 
 
1
5
1
,

 
 
7
,

 
 
2
8
3
2
,

 
 
3
3
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
1
6
1
2
9
,

 
 
2
5
1
7
,

 
 
5
,

 
 
5
0
,

 
 
5
9
,

 
 
2
5
6
,

 
 
1
,

 
 
3
7
0
,

 
 
3
1
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
1
4
4
,

 
 
7
2
,

 
 
3
9
3
1
,

 
 
8
9
,

 
 
4
2
0
8
,

 
 
6
3
6
8
,

 
 
2
6
8
7
,

 
 
1
1
8
3
]
,

 
[
1
6
0
3
6
6
,

 
 
5
2
,

 
 
2
9
1
1
,

 
 
1
3
,

 
 
4
5
0
,

 
 
3
7
8
2
,

 
 
7
2
,

 
 
4
8
7
1
,

 
 
2
6
7
6
,

 
 
2
1
,

 
 
9
5
,

 
 
4
6
,

 
 
9
1
2
,

 
 
3
2
2
5
,

 
 
1
0
2
4
,

 
 
6
1
6
,

 
 
9
9
8
3
,

 
 
2
1
6
]
,

 
[
4
5
5
,

 
 
4
0
0
,

 
 
7
2
,

 
 
1
2
6
,

 
 
1
4
,

 
 
2
6
8
,

 
 
2
,

 
 
7
9
,

 
 
3
2
6
,

 
 
7
1
,

 
 
4
9
,

 
 
9
,

 
 
1
3
,

 
 
6
1
3
,

 
 
8
,

 
 
2
4
7
0
,

 
 
5
3
0
,

 
 
5
1
1
,

 
 
1
0
5
,

 
 
5
,

 
 
6
0
9
,

 
 
2
,

 
 
3
7
,

 
 
3
3
0
,

 
 
1
4
0
,

 
 
3
8
2
,

 
 
3
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
5
2
,

 
 
1
9
5
,

 
 
2
,

 
 
4
6
6
,

 
 
5
8
,

 
 
3
5
,

 
 
1
,

 
 
2
4
0
4
,

 
 
9
3
,

 
 
1
,

 
 
7
4
3
,

 
 
4
8
7
]
,

 
[
5
8
,

 
 
7
,

 
 
2
2
9
,

 
 
9
7
,

 
 
5
5
,

 
 
3
2
5
,

 
 
1
4
0
8
,

 
 
1
5
,

 
 
2
1
2
0
,

 
 
7
,

 
 
5
7
1
5
,

 
 
2
2
,

 
 
1
,

 
 
1
1
6
,

 
 
2
3
8
8
,

 
 
5
6
,

 
 
1
6
,

 
 
5
1
9
,

 
 
1
5
,

 
 
2
5
,

 
 
4
,

 
 
3
8
5
4
,

 
 
3
,

 
 
1
3
6
9
,

 
 
3
,

 
 
1
0
6
4
0
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
9
5
,

 
 
8
7
,

 
 
1
2
2
,

 
 
1
3
5
9
7
,

 
 
3
6
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
4
0
,

 
 
1
0
,

 
 
1
,

 
 
1
5
2
3
,

 
 
1
3
9
,

 
 
1
2
9
6
,

 
 
2
1
2
6
,

 
 
4
3
5
,

 
 
1
2
9
6
,

 
 
3
2
1
,

 
 
7
,

 
 
3
9
,

 
 
3
4
,

 
 
9
,

 
 
5
1
9
,

 
 
1
5
,

 
 
2
2
,

 
 
4
4
,

 
 
4
7
,

 
 
3
3
1
,

 
 
1
0
0
,

 
 
1
1
4
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
4
4
5
8
,

 
 
1
2
,

 
 
2
4
0
4
,

 
 
1
9
0
,

 
 
1
5
,

 
 
2
9
5
,

 
 
2
5
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
1
,

 
 
2
2
5
,

 
 
5
0
,

 
 
2
7
8
,

 
 
3
7
,

 
 
7
0
,

 
 
4
1
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
5
9
4
6
,

 
 
1
5
,

 
 
8
3
,

 
 
1
2
,

 
 
3
7
9
,

 
 
3
6
,

 
 
7
,

 
 
6
5
0
,

 
 
4
1
,

 
 
8
7
,

 
 
1
6
,

 
 
4
,

 
 
2
1
9
0
,

 
 
3
8
8
,

 
 
4
,

 
 
2
9
9
8
,

 
 
3
0
2
2
,

 
 
7
3
,

 
 
7
1
,

 
 
4
4
0
,

 
 
1
0
,

 
 
1
,

 
 
5
1
1
,

 
 
6
4
1
,

 
 
3
4
4
6
,

 
 
2
8
,

 
 
9
8
,

 
 
2
3
,

 
 
3
1
5
1
,

 
 
5
4
4
5
]
,

 
[
6
,
 
1
7
4
4
,
 
1
8
,
 
3
0
,
 
3
5
9
8
,
 
5
5
,
 
1
1
0
5
,
 
6
,
 
5
8
4
,
 
3
8
,
 
2
9
,
 
1
8
5
,
 
1
5
]
,

 
[
2
7
4
0
,
 
3
1
,
 
3
7
,
 
1
7
,
 
1
0
1
,
 
8
2
,
 
1
,
 
2
3
7
8
,
 
1
0
1
,
 
1
0
4
1
9
,
 
4
6
]
,

 
[
2
6
0
3
,
 
1
5
0
,
 
6
,
 
2
3
3
6
,
 
3
1
5
,
 
1
5
,
 
3
0
,
 
1
4
2
]
,

 
[
2
0
,

 
 
2
1
7
,

 
 
2
,

 
 
1
,

 
 
3
8
0
5
,

 
 
1
6
0
3
6
7
,

 
 
2
3
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
5
0
,

 
 
5
9
,

 
 
3
4
,

 
 
1
1
,

 
 
1
2
7
,

 
 
2
5
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
7
7
3
]
,

 
[
2
8
0
,

 
 
2
2
,

 
 
1
,

 
 
2
7
0
,

 
 
4
2
3
3
1
,

 
 
2
4
,

 
 
1
4
6
3
,

 
 
2
,

 
 
6
,

 
 
4
9
5
,

 
 
7
2
,

 
 
1
4
,

 
 
9
6
8
8
,

 
 
2
,

 
 
3
5
0
,

 
 
2
1
5
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
4
1
8
,

 
 
5
1
,

 
 
4
3
,

 
 
2
8
9
8
,

 
 
1
5
,

 
 
3
7
,

 
 
1
2
,

 
 
2
1
7
,

 
 
7
2
,

 
 
1
1
3
1
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
5
8
,

 
 
1
3
1
0
,

 
 
3
6
,

 
 
4
7
,

 
 
3
9
,

 
 
8
2
,

 
 
1
1
,

 
 
1
2
,

 
 
4
8
0
,

 
 
1
7
,

 
 
4
,

 
 
2
7
3
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
2
,

 
 
1
,

 
 
5
0
8
9
,

 
 
8
9
7
5
,

 
 
2
9
,

 
 
2
6
,

 
 
7
1
,

 
 
6
5
7
,

 
 
4
,

 
 
1
3
3
2
,

 
 
1
1
,

 
 
6
9
8
,

 
 
2
,

 
 
6
9
7
4
4
,

 
 
1
6
0
3
6
8
,

 
 
5
4
,

 
 
8
,

 
 
4
,

 
 
6
7
3
,

 
 
7
9
9
2
,

 
 
2
3
,

 
 
9
,

 
 
1
0
5
8
,

 
 
6
,

 
 
4
4
,

 
 
4
8
7
,

 
 
4
1
,

 
 
2
4
5
,

 
 
1
6
,

 
 
1
5
8
,

 
 
3
1
5
,

 
 
2
1
,

 
 
3
6
4
4
,

 
 
1
0
,

 
 
1
1
9
4
7
,

 
 
4
3
9
0
,

 
 
6
2
2
4
,

 
 
5
3
7
2
,

 
 
6
8
2
8
]
,

 
[
1
2
0
6
6
,
 
1
5
,
 
1
3
,
 
2
5
7
,
 
5
,
 
5
4
,
 
1
8
,
 
1
9
6
5
,
 
2
,
 
1
4
1
,
 
3
,
 
1
0
6
4
6
1
]
,

 
[
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
1
2
,

 
 
1
2
3
,

 
 
6
9
7
4
5
,

 
 
4
7
2
,

 
 
9
5
,

 
 
1
2
,

 
 
1
5
1
6
,

 
 
1
2
3
,

 
 
6
9
7
4
5
,

 
 
4
7
2
,

 
 
7
,

 
 
4
5
4
,

 
 
1
,

 
 
1
2
3
,

 
 
2
9
,

 
 
3
0
7
0
,

 
 
9
,

 
 
1
,

 
 
1
2
3
,

 
 
8
,

 
 
9
1
,

 
 
1
3
3
,

 
 
1
8
2
,

 
 
3
0
2
,

 
 
8
2
,

 
 
2
6
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
7
3
3
,

 
 
2
5
,

 
 
9
6
3
,

 
 
1
7
,

 
 
2
,

 
 
7
8
,

 
 
1
0
4
,

 
 
8
2
,

 
 
1
0
,

 
 
2
8
,

 
 
8
3
,

 
 
2
7
3
2
,

 
 
3
0
2
,

 
 
8
2
,

 
 
1
0
,

 
 
8
1
3
,

 
 
2
,

 
 
1
,

 
 
8
2
4
4
,

 
 
3
0
2
,

 
 
8
2
,

 
 
3
7
0
,

 
 
6
,

 
 
2
4
5
,

 
 
6
6
,

 
 
3
5
0
,

 
 
7
6
,

 
 
1
5
,

 
 
1
,

 
 
1
2
3
,

 
 
7
3
1
,

 
 
2
9
,

 
 
4
,

 
 
4
9
4
,

 
 
7
3
3
,

 
 
2
5
,

 
 
9
6
3
,

 
 
1
2
,

 
 
7
8
,

 
 
2
0
9
,

 
 
1
3
,

 
 
1
2
3
,

 
 
1
0
,

 
 
4
3
3
,

 
 
2
3
,

 
 
8
,

 
 
1
9
4
2
,

 
 
2
1
,

 
 
3
0
2
,

 
 
8
2
,

 
 
5
0
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
1
2
3
,

 
 
7
3
1
,

 
 
2
9
,

 
 
5
,

 
 
7
9
,

 
 
1
1
,

 
 
2
,

 
 
4
4
8
,

 
 
4
,

 
 
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
7
4
4
,

 
 
6
1
,

 
 
3
0
2
,

 
 
8
2
,

 
 
3
9
0
,

 
 
4
1
1
,

 
 
1
4
6
4
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
2
1
4
6
,

 
 
1
,

 
 
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
1
5
,

 
 
1
4
1
,

 
 
1
2
4
,

 
 
1
5
5
,

 
 
6
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
2
5
7
8
,

 
 
1
2
4
,

 
 
6
,

 
 
1
9
,

 
 
6
3
7
,

 
 
3
2
,

 
 
1
6
7
3
,

 
 
1
5
,

 
 
1
,

 
 
3
0
,

 
 
4
1
4
,

 
 
1
6
9
,

 
 
1
1
,

 
 
8
,

 
 
1
8
3
6
,

 
 
3
3
,

 
 
1
,

 
 
1
0
2
,

 
 
2
7
9
,

 
 
3
,

 
 
5
5
,

 
 
2
8
,

 
 
2
9
,

 
 
8
0
,

 
 
6
,

 
 
1
8
,

 
 
1
7
6
0
,

 
 
1
0
,

 
 
5
,

 
 
8
4
,

 
 
3
2
8
5
,

 
 
1
2
3
,

 
 
3
1
,

 
 
1
,

 
 
3
7
2
4
,

 
 
9
3
6
,

 
 
1
9
3
,

 
 
9
,

 
 
5
5
,

 
 
3
0
2
,

 
 
8
2
,

 
 
3
4
4
,

 
 
7
4
4
,

 
 
1
5
1
,

 
 
3
6
5
,

 
 
8
7
,

 
 
6
5
5
,

 
 
5
,

 
 
2
6
3
0
,

 
 
1
1
1
,

 
 
2
7
,

 
 
7
3
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
4
6
,

 
 
4
7
,

 
 
7
6
6
,

 
 
1
5
1
,

 
 
5
1
,

 
 
1
9
,

 
 
5
7
,

 
 
7
4
4
,

 
 
1
7
,

 
 
9
5
7
,

 
 
1
5
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
5
0
,

 
 
2
1
9
,

 
 
8
8
,

 
 
3
3
,

 
 
1
,

 
 
3
9
0
,

 
 
2
7
2
,

 
 
2
5
4
,

 
 
2
9
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
,

 
 
2
5
2
,

 
 
7
9
2
,

 
 
2
5
2
,

 
 
7
1
9
6
,

 
 
1
2
0
,

 
 
1
2
,

 
 
1
2
3
,

 
 
6
9
7
4
5
,

 
 
4
7
2
,

 
 
9
5
,

 
 
1
2
,

 
 
1
5
1
6
,

 
 
1
2
3
,

 
 
6
9
7
4
5
,

 
 
4
7
2
,

 
 
7
,

 
 
6
5
8
,

 
 
9
,

 
 
1
,

 
 
6
8
0
6
,

 
 
7
3
1
,

 
 
2
9
,

 
 
5
3
4
,

 
 
1
8
1
,

 
 
2
2
0
1
,

 
 
6
2
,

 
 
3
3
3
,

 
 
1
,

 
 
1
7
4
,

 
 
3
6
,

 
 
1
,

 
 
2
7
2
,

 
 
6
9
1
,

 
 
8
,

 
 
2
2
1
2
,

 
 
2
2
,

 
 
6
,

 
 
9
0
,

 
 
1
4
,

 
 
4
7
1
,

 
 
1
3
,

 
 
5
0
9
,

 
 
2
2
5
,

 
 
8
4
,

 
 
6
,

 
 
4
5
,

 
 
1
2
2
,

 
 
2
,

 
 
2
2
0
1
,

 
 
1
,

 
 
2
4
5
1
,

 
 
3
,

 
 
1
,

 
 
2
7
2
,

 
 
2
2
,

 
 
6
,

 
 
3
8
0
6
,

 
 
1
1
,

 
 
3
1
,

 
 
4
,

 
 
4
2
1
,

 
 
8
4
,

 
 
4
,

 
 
1
6
9
,

 
 
2
,

 
 
1
,

 
 
4
2
1
,

 
 
3
1
,

 
 
5
4
,

 
 
1
1
,

 
 
2
4
,

 
 
5
5
5
,

 
 
8
4
0
,

 
 
2
1
,

 
 
4
,

 
 
7
8
8
5
,

 
 
3
,

 
 
9
,

 
 
4
7
0
8
,

 
 
6
6
7
,

 
 
3
,

 
 
8
2
,

 
 
3
,

 
 
1
0
4
,

 
 
1
7
4
,

 
 
8
,

 
 
8
2
8
,

 
 
1
8
2
1
,

 
 
1
0
5
,

 
 
1
9
7
,

 
 
2
2
,

 
 
1
,

 
 
2
7
2
,

 
 
2
2
6
7
,

 
 
8
,

 
 
2
7
1
,

 
 
3
1
,

 
 
1
,

 
 
4
7
0
8
,

 
 
2
8
0
3
,

 
 
8
4
,

 
 
9
2
,

 
 
2
7
2
,

 
 
5
6
,

 
 
6
6
,

 
 
1
6
,

 
 
3
5
3
2
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
3
1
0
,

 
 
1
,

 
 
1
2
0
,

 
 
5
0
,

 
 
1
5
2
,

 
 
4
,

 
 
8
2
3
,

 
 
2
7
2
,

 
 
3
6
5
7
,

 
 
2
7
7
,

 
 
2
2
,

 
 
1
,

 
 
5
0
9
,

 
 
1
8
1
,

 
 
1
9
,

 
 
4
7
,

 
 
2
3
7
,

 
 
2
2
,

 
 
6
,

 
 
3
3
3
,

 
 
6
5
1
,

 
 
1
,

 
 
4
8
6
,

 
 
3
0
6
7
,

 
 
2
5
,

 
 
8
2
6
,

 
 
8
4
,

 
 
1
,

 
 
2
7
7
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
9
6
0
,

 
 
1
1
,

 
 
1
8
2
,

 
 
1
,

 
 
2
3
4
0
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
1
,

 
 
3
9
0
,

 
 
1
3
5
9
,

 
 
1
,

 
 
4
3
4
,

 
 
3
3
,

 
 
2
8
,

 
 
3
0
2
,

 
 
8
2
,

 
 
8
2
,

 
 
4
,

 
 
2
7
7
,

 
 
1
1
1
,

 
 
1
7
,

 
 
2
5
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
7
7
0
,

 
 
4
4
0
,

 
 
3
3
,

 
 
2
8
,

 
 
1
2
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
3
0
2
,

 
 
8
2
,

 
 
6
3
,

 
 
2
8
,

 
 
1
2
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
1
2
,

 
 
1
,

 
 
5
1
0
,

 
 
1
6
1
,

 
 
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
9
,

 
 
6
,

 
 
3
9
,

 
 
8
2
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
7
4
4
,

 
 
6
1
,

 
 
1
4
6
6
,

 
 
4
1
1
,

 
 
1
4
6
4
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
2
1
4
6
,

 
 
9
2
,

 
 
1
2
0
,

 
 
5
,

 
 
9
1
7
,

 
 
8
8
,

 
 
1
5
5
,

 
 
6
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
1
4
6
6
,

 
 
6
,

 
 
1
9
,

 
 
7
4
4
,

 
 
3
2
,

 
 
4
5
1
,

 
 
1
3
,

 
 
1
6
9
,

 
 
1
2
5
9
,

 
 
5
,

 
 
4
8
7
2
,

 
 
3
4
4
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
4
7
,

 
 
7
6
6
,

 
 
1
5
1
,

 
 
5
1
,

 
 
1
9
,

 
 
5
7
,

 
 
9
1
7
,

 
 
1
7
,

 
 
9
5
7
,

 
 
1
5
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
1
2
3
,

 
 
8
,

 
 
1
5
0
0
,

 
 
1
8
2
,

 
 
4
,

 
 
2
8
1
,

 
 
2
0
0
,

 
 
1
1
5
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
3
0
2
,

 
 
8
2
,

 
 
8
4
,

 
 
1
,

 
 
1
2
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
1
0
9
,

 
 
8
6
7
,

 
 
1
5
1
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
5
0
,

 
 
2
1
9
,

 
 
8
8
,

 
 
3
3
,

 
 
1
,

 
 
3
9
0
,

 
 
2
7
2
,

 
 
2
5
4
,

 
 
2
9
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
,

 
 
2
5
2
,

 
 
7
9
2
,

 
 
2
5
2
]
,

 
[
2
3
1
5
9
,
 
1
6
,
 
4
,
 
4
0
0
,
 
5
,
 
2
2
1
3
,
 
5
6
3
,
 
1
1
,
 
3
5
2
,
 
1
4
8
,
 
1
,
 
2
8
0
0
]
,

 
[
4
5
5
,

 
 
3
8
,

 
 
8
,

 
 
1
1
,

 
 
4
6
,

 
 
3
8
,

 
 
8
,

 
 
1
1
,

 
 
2
7
,

 
 
4
3
5
4
,

 
 
4
3
8
,

 
 
3
,

 
 
6
0
,

 
 
1
1
3
,

 
 
5
4
2
5
9
,

 
 
6
2
,

 
 
1
8
,

 
 
9
8
,

 
 
3
3
,

 
 
5
7
1
6
,

 
 
5
7
1
,

 
 
4
7
2
2
,

 
 
4
9
3
9
5
,

 
 
6
2
,

 
 
3
6
6
8
,

 
 
7
3
,

 
 
5
5
,

 
 
4
7
,

 
 
6
2
,

 
 
5
3
7
3
,

 
 
8
8
,

 
 
2
5
4
,

 
 
2
1
0
6
7
,

 
 
9
2
,

 
 
5
6
1
,

 
 
1
1
9
6
,

 
 
5
,

 
 
6
0
1
9
,

 
 
2
8
1
,

 
 
1
3
5
8
,

 
 
3
3
,

 
 
1
1
3
,

 
 
2
1
9
,

 
 
8
3
5
1
2
,

 
 
2
,

 
 
1
5
3
8
,

 
 
7
3
,

 
 
6
8
,

 
 
1
0
0
8
,

 
 
9
3
,

 
 
2
6
7
,

 
 
3
7
,

 
 
6
5
1
7
,

 
 
1
4
0
7
]
,

 
[
1
5
0
,

 
 
6
,

 
 
4
2
6
,

 
 
4
0
8
0
,

 
 
1
4
7
2
,

 
 
5
,

 
 
1
4
0
7
,

 
 
3
3
,

 
 
3
7
,

 
 
2
2
1
3
,

 
 
3
7
9
,

 
 
1
,

 
 
7
9
,

 
 
5
4
0
,

 
 
2
9
0
,

 
 
1
6
1
1
,

 
 
5
0
4
6
,

 
 
6
1
9
,

 
 
2
8
5
,

 
 
1
6
5
,

 
 
2
,

 
 
1
3
5
9
8
,

 
 
2
0
,

 
 
6
2
7
,

 
 
1
1
,

 
 
4
5
,

 
 
1
1
3
1
,

 
 
9
7
,

 
 
1
1
,

 
 
1
4
7
,

 
 
4
8
,

 
 
6
,

 
 
1
8
,

 
 
3
0
7
3
,

 
 
2
0
,

 
 
6
6
2
,

 
 
1
7
,

 
 
2
7
,

 
 
4
1
8
,

 
 
8
9
,

 
 
1
,

 
 
7
9
,

 
 
5
4
0
,

 
 
8
,

 
 
5
1
1
,

 
 
1
3
,

 
 
8
,

 
 
2
8
8
,

 
 
1
,

 
 
5
2
8
,

 
 
1
3
2
,

 
 
3
4
1
2
,

 
 
3
5
,

 
 
1
1
3
6
,

 
 
8
2
9
1
,

 
 
5
2
,

 
 
4
8
4
,

 
 
1
7
,

 
 
3
,

 
 
1
3
5
0
,

 
 
6
8
,

 
 
3
8
0
7
,

 
 
8
,

 
 
3
4
2
,

 
 
1
4
4
,

 
 
5
2
,

 
 
8
,

 
 
1
,

 
 
7
7
,

 
 
8
0
9
,

 
 
3
0
4
5
,

 
 
1
2
6
6
,

 
 
6
2
,

 
 
9
0
,

 
 
1
4
,

 
 
5
3
5
5
,

 
 
1
8
5
,

 
 
5
5
1
,

 
 
5
8
,

 
 
3
4
2
,

 
 
9
3
,

 
 
6
8
,

 
 
3
3
6
4
1
,

 
 
2
7
,

 
 
1
6
0
3
6
9
,

 
 
7
4
7
3
,

 
 
7
,

 
 
2
7
2
8
,

 
 
2
,

 
 
3
9
8
,

 
 
1
3
,

 
 
7
9
,

 
 
1
0
,

 
 
6
1
2
8
,

 
 
3
,

 
 
1
6
3
7
9
,

 
 
1
,

 
 
7
7
9
,

 
 
3
,

 
 
2
7
,

 
 
4
1
8
,

 
 
9
,

 
 
8
,

 
 
1
3
1
5
,

 
 
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
2
6
7
,

 
 
5
4
0
,

 
 
5
,

 
 
1
4
,

 
 
2
5
7
4
,

 
 
1
4
7
2
,

 
 
3
1
5
,

 
 
3
7
1
,

 
 
3
6
,

 
 
1
6
3
8
0
,

 
 
3
7
5
,

 
 
2
2
,

 
 
6
,

 
 
3
4
0
3
,

 
 
4
,

 
 
8
3
9
,

 
 
3
,

 
 
2
0
4
7
,

 
 
1
2
5
,

 
 
6
,

 
 
3
9
,

 
 
3
4
,

 
 
1
3
,

 
 
5
3
,

 
 
3
9
,

 
 
1
9
,

 
 
4
,

 
 
4
0
9
4
,

 
 
1
3
8
,

 
 
1
5
,

 
 
1
,

 
 
4
4
7
,

 
 
5
,

 
 
2
3
8
4
,

 
 
1
,

 
 
3
5
4
,

 
 
1
6
3
8
1
]
,

 
[
4
1
5
,

 
 
5
,

 
 
1
,

 
 
1
6
4
0
,

 
 
2
5
5
,

 
 
5
1
3
,

 
 
1
7
2
,

 
 
1
0
2
0
,

 
 
2
1
,

 
 
3
7
,

 
 
1
8
9
,

 
 
2
6
7
6
,

 
 
1
7
2
,

 
 
4
0
8
1
,

 
 
1
2
5
,

 
 
1
1
,

 
 
1
8
1
,

 
 
1
3
1
6
,

 
 
7
,

 
 
2
2
0
,

 
 
1
,

 
 
6
2
7
,

 
 
2
4
,

 
 
3
2
9
,

 
 
3
7
,

 
 
5
,

 
 
1
6
0
3
7
0
,

 
 
2
6
,

 
 
4
8
,

 
 
7
,

 
 
1
6
7
,

 
 
1
,

 
 
9
4
0
,

 
 
2
4
,

 
 
3
6
2
2
,

 
 
5
,

 
 
7
,

 
 
7
2
2
1
,

 
 
9
5
]
,

 
[
3
5
3
4
6
,

 
 
1
6
0
3
7
1
,

 
 
1
1
0
3
,

 
 
1
0
,

 
 
2
4
6
6
,

 
 
3
5
3
4
6
,

 
 
2
2
0
9
5
,

 
 
2
4
,

 
 
8
6
8
,

 
 
2
7
4
,

 
 
3
4
3
,

 
 
8
4
,

 
 
5
8
5
,

 
 
1
2
4
8
,

 
 
5
7
6
7
,

 
 
5
4
,

 
 
3
9
7
,

 
 
3
5
3
4
6
,

 
 
1
3
7
7
,

 
 
9
1
9
,

 
 
2
9
0
,

 
 
1
8
1
0
,

 
 
2
1
,

 
 
1
,

 
 
2
3
8
1
3
,

 
 
1
,

 
 
7
8
2
,

 
 
4
9
3
9
6
,

 
 
2
,

 
 
1
6
,

 
 
2
1
6
7
,

 
 
2
,

 
 
1
6
0
3
7
2
,

 
 
1
9
3
4
,

 
 
1
8
2
,

 
 
7
2
8
9
,

 
 
4
,

 
 
1
8
3
6
3
,

 
 
1
0
,

 
 
1
8
8
7
,

 
 
5
2
,

 
 
2
4
,

 
 
6
0
3
,

 
 
2
7
4
,

 
 
3
4
3
,

 
 
9
8
3
,

 
 
7
6
,

 
 
2
1
,

 
 
6
8
,

 
 
1
7
0
,

 
 
3
6
7
3
,

 
 
6
9
7
4
6
,

 
 
1
6
0
7
,

 
 
5
,

 
 
3
2
2
,

 
 
3
6
,

 
 
2
9
6
,

 
 
5
2
,

 
 
8
,

 
 
9
0
8
,

 
 
1
0
,

 
 
6
3
8
2
,

 
 
5
2
,

 
 
1
2
6
,

 
 
8
,

 
 
7
4
,

 
 
1
0
3
,

 
 
5
2
,

 
 
1
6
,

 
 
2
2
1
6
,

 
 
8
4
,

 
 
9
6
2
9
,

 
 
6
4
9
6
,

 
 
5
,

 
 
7
4
,

 
 
1
0
3
,

 
 
5
2
,

 
 
1
6
,

 
 
8
9
1
,

 
 
8
0
,

 
 
6
8
,

 
 
3
7
8
8
,

 
 
2
1
3
0
,

 
 
1
,

 
 
1
6
1
3
0
,

 
 
4
9
3
9
6
,

 
 
8
,

 
 
9
5
5
,

 
 
2
7
4
,

 
 
3
4
3
,

 
 
6
3
8
2
,

 
 
6
5
5
,

 
 
3
5
3
4
6
,

 
 
6
9
6
,

 
 
5
3
7
,

 
 
9
7
4
2
,

 
 
2
2
,

 
 
2
0
,

 
 
9
5
0
,

 
 
3
5
,

 
 
9
,

 
 
7
8
4
4
,

 
 
9
5
5
,

 
 
1
1
8
,

 
 
2
,

 
 
2
0
,

 
 
1
6
0
3
7
3
,

 
 
5
,

 
 
1
7
1
,

 
 
9
4
4
,

 
 
6
8
,

 
 
4
1
2
,

 
 
3
,

 
 
1
6
6
9
,

 
 
3
0
,

 
 
5
3
7
]
,

 
[
2
5
9
4
,
 
5
9
,
 
1
4
7
,
 
2
6
9
,
 
2
5
,
 
6
5
,
 
3
,
 
1
8
3
6
4
,
 
1
5
7
,
 
1
5
2
5
6
]
,

 
[
4
3
9
,
 
4
6
,
 
1
6
0
3
7
4
,
 
1
8
0
1
,
 
5
4
2
6
0
,
 
1
0
6
4
6
2
]
,

 
[
1
,

 
 
1
6
0
3
7
5
,

 
 
1
4
5
,

 
 
1
3
1
,

 
 
4
4
,

 
 
4
6
9
,

 
 
7
8
,

 
 
1
4
,

 
 
1
3
5
3
,

 
 
2
,

 
 
4
4
8
,

 
 
4
7
7
4
,

 
 
1
5
,

 
 
4
2
3
3
2
,

 
 
1
6
0
3
7
6
,

 
 
2
9
,

 
 
2
,

 
 
4
4
8
,

 
 
5
8
,

 
 
1
0
5
]
,

 
[
5
9
,

 
 
2
7
6
,

 
 
2
,

 
 
1
6
2
5
,

 
 
6
,

 
 
7
,

 
 
6
3
,

 
 
9
,

 
 
1
6
4
,

 
 
5
5
3
,

 
 
1
6
3
,

 
 
4
5
6
,

 
 
5
3
0
,

 
 
2
1
5
,

 
 
6
7
0
,

 
 
6
4
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
3
4
,

 
 
4
1
5
,

 
 
1
0
1
,

 
 
2
6
,

 
 
2
2
,

 
 
1
4
,

 
 
5
,

 
 
6
,

 
 
3
9
,

 
 
4
2
3
3
3
,

 
 
5
6
3
,

 
 
1
3
,

 
 
2
1
,

 
 
3
7
,

 
 
8
4
,

 
 
9
6
,

 
 
2
0
1
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
2
1
9
,

 
 
6
,

 
 
2
,

 
 
1
5
9
,

 
 
4
,

 
 
2
8
8
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
8
0
6
9
,

 
 
3
7
8
9
,

 
 
3
9
5
7
,

 
 
2
6
7
3
4
,

 
 
5
,

 
 
1
,

 
 
1
0
5
2
,

 
 
4
4
0
,

 
 
1
0
,

 
 
1
1
,

 
 
1
6
4
4
,

 
 
1
1
2
,

 
 
1
0
5
2
,

 
 
1
3
1
6
,

 
 
8
4
0
,

 
 
1
0
,

 
 
6
0
,

 
 
2
6
7
3
4
,

 
 
8
,

 
 
4
1
,

 
 
2
1
5
,

 
 
9
,

 
 
6
,

 
 
6
5
,

 
 
5
3
,

 
 
3
9
,

 
 
3
4
,

 
 
2
1
,

 
 
1
,

 
 
2
6
7
3
4
,

 
 
1
5
5
6
,

 
 
1
0
6
4
6
3
,

 
 
1
1
]
,

 
[
4
5
6
,

 
 
2
0
,

 
 
5
2
9
,

 
 
1
4
0
,

 
 
4
0
8
,

 
 
1
2
7
,

 
 
5
0
,

 
 
1
5
6
,

 
 
1
1
3
,

 
 
4
9
3
9
7
,

 
 
1
5
0
,

 
 
1
2
9
,

 
 
5
5
,

 
 
5
8
,

 
 
6
5
9
,

 
 
8
3
,

 
 
2
0
,

 
 
1
4
0
,

 
 
1
8
,

 
 
3
0
9
,

 
 
1
4
,

 
 
9
8
,

 
 
2
1
,

 
 
1
0
5
9
,

 
 
1
5
5
,

 
 
1
3
0
,

 
 
2
0
0
5
,

 
 
8
7
7
,

 
 
5
,

 
 
1
0
2
,

 
 
3
6
6
,

 
 
5
5
3
,

 
 
5
0
,

 
 
1
7
1
,

 
 
1
5
0
,

 
 
6
,

 
 
3
4
,

 
 
3
9
9
,

 
 
2
3
6
9
,

 
 
2
3
8
1
4
,

 
 
2
1
5
7
1
]
,

 
[
9
8
,
 
2
,
 
7
0
,
 
3
5
,
 
3
7
,
 
7
6
0
,
 
7
2
,
 
5
0
4
7
,
 
8
9
,
 
5
4
2
6
1
]
,

 
[
8
3
5
1
3
,

 
 
1
8
,

 
 
1
4
,

 
 
3
6
9
,

 
 
2
5
9
1
6
,

 
 
1
8
2
,

 
 
8
2
0
6
,

 
 
1
1
,

 
 
8
,

 
 
7
1
6
,

 
 
9
,

 
 
4
,

 
 
4
9
3
9
8
,

 
 
3
6
9
,

 
 
4
2
,

 
 
1
7
0
0
,

 
 
2
3
8
1
5
,

 
 
2
7
5
7
,

 
 
1
3
,

 
 
2
2
2
1
,

 
 
8
,

 
 
3
0
9
,

 
 
1
4
,

 
 
3
8
0
,

 
 
5
7
9
,

 
 
2
,

 
 
9
9
2
4
,

 
 
1
6
0
3
7
7
,

 
 
1
,

 
 
2
6
4
,

 
 
2
5
1
3
0
,

 
 
1
5
6
6
9
,

 
 
2
5
9
1
7
,

 
 
1
8
,

 
 
3
2
,

 
 
3
1
3
,

 
 
1
,

 
 
1
3
2
,

 
 
5
2
3
,

 
 
2
8
8
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
0
4
,

 
 
3
7
3
7
2
,

 
 
3
5
9
4
,

 
 
7
9
9
3
,

 
 
1
6
0
3
7
8
,

 
 
6
3
2
3
,

 
 
6
3
2
3
,

 
 
2
3
2
0
,

 
 
1
2
3
8
6
,

 
 
1
5
8
,

 
 
1
2
6
,

 
 
1
2
2
,

 
 
2
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
6
8
,

 
 
3
4
1
,

 
 
5
,

 
 
9
4
,

 
 
4
7
9
,

 
 
1
9
2
,

 
 
3
,

 
 
1
1
,

 
 
6
9
,

 
 
7
,

 
 
1
5
3
,

 
 
6
3
,

 
 
4
,

 
 
2
8
7
3
,

 
 
3
7
2
,

 
 
3
,

 
 
5
4
2
6
2
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
3
7
0
8
,

 
 
3
7
,

 
 
7
2
8
,

 
 
1
1
5
,

 
 
3
3
,

 
 
1
3
,

 
 
5
,

 
 
4
7
6
,

 
 
1
0
8
,

 
 
2
,

 
 
7
9
,

 
 
2
1
5
]
,

 
[
1
,
 
4
0
5
6
,
 
7
0
4
,
 
1
1
0
8
,
 
9
5
1
,
 
1
5
6
,
 
1
3
,
 
4
0
5
6
,
 
1
0
,
 
5
1
0
,
 
5
2
8
,
 
2
9
,
 
8
6
0
4
]
,

 
[
3
5
7
,

 
 
1
3
8
0
,

 
 
2
5
5
1
,

 
 
6
0
0
,

 
 
7
9
,

 
 
7
,

 
 
5
9
,

 
 
2
7
5
,

 
 
1
,

 
 
6
5
2
,

 
 
1
2
,

 
 
2
3
9
8
,

 
 
5
2
9
,

 
 
7
9
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
1
4
,

 
 
9
,

 
 
7
2
,

 
 
1
8
6
,

 
 
9
,

 
 
1
,

 
 
8
6
5
,

 
 
1
8
,

 
 
1
8
8
3
,

 
 
2
4
7
,

 
 
2
6
4
,

 
 
7
2
,

 
 
1
4
7
0
9
,

 
 
9
,

 
 
1
,

 
 
4
5
6
4
,

 
 
3
,

 
 
4
4
8
5
,

 
 
1
3
7
2
,

 
 
1
1
6
4
6
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
6
0
0
,

 
 
8
,

 
 
2
7
,

 
 
5
0
1
9
,

 
 
1
5
9
0
,

 
 
2
,

 
 
1
3
,

 
 
4
9
4
,

 
 
2
5
7
,

 
 
7
,

 
 
1
9
3
,

 
 
9
,

 
 
8
3
,

 
 
3
5
,

 
 
6
1
,

 
 
3
6
8
9
,

 
 
2
2
6
2
2
,

 
 
1
9
,

 
 
5
7
,

 
 
2
9
9
9
,

 
 
1
2
7
2
0
,

 
 
5
,

 
 
7
,

 
 
6
6
,

 
 
2
2
0
,

 
 
1
4
1
,

 
 
4
2
2
,

 
 
1
8
,

 
 
4
4
,

 
 
2
1
2
0
,

 
 
1
0
,

 
 
3
4
7
,

 
 
3
,

 
 
3
0
,

 
 
3
3
5
,

 
 
9
,

 
 
1
3
,

 
 
7
9
,

 
 
5
6
,

 
 
1
6
,

 
 
3
6
8
,

 
 
7
,

 
 
4
3
,

 
 
3
1
1
4
,

 
 
2
5
9
,

 
 
2
,

 
 
3
5
7
,

 
 
1
8
7
7
,

 
 
8
3
,

 
 
3
9
1
,

 
 
3
5
,

 
 
1
,

 
 
4
5
1
,

 
 
1
0
0
9
5
,

 
 
3
,

 
 
2
9
6
7
0
,

 
 
6
6
2
2
,

 
 
7
6
2
9
,

 
 
4
5
4
8
8
,

 
 
1
3
9
0
5
,

 
 
2
2
7
3
,

 
 
7
4
1
,

 
 
9
1
9
8
,

 
 
7
6
9
,

 
 
8
9
2
7
,

 
 
2
1
0
6
8
,

 
 
8
2
4
5
,

 
 
7
6
9
,

 
 
8
9
2
7
,

 
 
2
1
0
6
8
,

 
 
1
5
0
5
,

 
 
1
,

 
 
2
1
4
,

 
 
2
2
1
5
,

 
 
4
3
,

 
 
1
,

 
 
4
2
4
,

 
 
4
0
7
,

 
 
3
,

 
 
1
,

 
 
2
8
,

 
 
2
3
,

 
 
3
5
,

 
 
5
5
,

 
 
4
7
,

 
 
3
,

 
 
8
8
,

 
 
2
5
,

 
 
3
0
4
,

 
 
4
5
6
5
,

 
 
1
6
,

 
 
2
1
5
9
,

 
 
3
2
,

 
 
1
3
7
2
,

 
 
5
9
9
8
,

 
 
1
0
,

 
 
1
,

 
 
6
6
2
3
,

 
 
6
0
0
,

 
 
7
,

 
 
6
5
,

 
 
1
4
,

 
 
3
7
5
,

 
 
1
1
,

 
 
1
8
0
7
,

 
 
2
,

 
 
1
9
0
4
,

 
 
4
,

 
 
4
2
3
3
4
,

 
 
6
2
7
,

 
 
2
1
0
6
9
,

 
 
1
3
7
3
7
,

 
 
3
,

 
 
8
8
2
2
,

 
 
6
4
9
,

 
 
3
9
7
,

 
 
8
0
,

 
 
1
8
9
,

 
 
2
0
3
6
,

 
 
9
,

 
 
6
0
,

 
 
1
5
,

 
 
1
,

 
 
4
8
2
8
,

 
 
6
4
9
,

 
 
7
0
3
5
,

 
 
1
2
1
0
,

 
 
7
4
,

 
 
4
2
3
3
5
,

 
 
2
7
6
6
9
,

 
 
3
7
5
7
,

 
 
2
1
6
0
,

 
 
3
8
,

 
 
2
8
7
,

 
 
1
9
,

 
 
3
1
2
7
,

 
 
2
,

 
 
4
8
5
4
,

 
 
3
5
,

 
 
1
,

 
 
4
4
4
9
,

 
 
3
,

 
 
4
4
1
7
,

 
 
7
,

 
 
4
3
,

 
 
2
2
6
,

 
 
1
3
,

 
 
1
4
1
6
8
,

 
 
1
4
7
1
0
,

 
 
6
0
8
6
,

 
 
1
,

 
 
1
4
5
,

 
 
4
6
2
,

 
 
8
8
7
9
,

 
 
2
6
,

 
 
2
7
,

 
 
9
6
,

 
 
5
1
4
7
,

 
 
6
2
7
,

 
 
8
,

 
 
1
,

 
 
4
7
,

 
 
1
7
4
4
4
,

 
 
1
9
7
9
,

 
 
3
9
7
,

 
 
8
0
,

 
 
5
2
,

 
 
1
6
8
8
,

 
 
3
0
7
4
,

 
 
2
,

 
 
1
5
3
1
,

 
 
6
8
,

 
 
6
4
9
,

 
 
1
8
9
6
,

 
 
2
,

 
 
9
7
9
2
,

 
 
3
3
,

 
 
4
,

 
 
2
9
7
0
,

 
 
7
2
,

 
 
4
8
1
2
,

 
 
1
3
,

 
 
7
9
,

 
 
1
1
,

 
 
2
2
7
4
,

 
 
2
,

 
 
1
6
,

 
 
2
5
1
3
1
]
,

 
[
1
6
3
8
2
,

 
 
1
3
9
0
6
,

 
 
4
3
0
,

 
 
8
9
,

 
 
8
7
7
8
,

 
 
1
8
0
5
1
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
1
0
6
4
6
4
,

 
 
8
6
,

 
 
3
2
1
4
2
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
6
0
3
7
9
,

 
 
2
5
,

 
 
9
6
,

 
 
3
5
3
4
7
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
6
0
3
8
0
,

 
 
1
6
0
3
8
1
]
,

 
[
3
9
5
,

 
 
4
4
,

 
 
1
2
2
,

 
 
2
,

 
 
1
7
3
2
,

 
 
4
,

 
 
2
8
,

 
 
2
3
,

 
 
8
,

 
 
1
3
1
,

 
 
1
2
,

 
 
5
4
2
6
3
,

 
 
7
4
8
,

 
 
3
5
,

 
 
4
,

 
 
2
5
7
,

 
 
3
1
,

 
 
2
7
1
,

 
 
1
0
6
,

 
 
5
,

 
 
5
0
5
,

 
 
2
0
7
,

 
 
1
7
9
,

 
 
1
6
0
2
,

 
 
5
,

 
 
1
4
,

 
 
9
5
1
0
,

 
 
1
6
0
2
,

 
 
7
,

 
 
6
5
0
,

 
 
7
,

 
 
1
0
3
,

 
 
5
3
5
6
,

 
 
1
,

 
 
2
9
,

 
 
2
6
5
,

 
 
1
4
2
4
,

 
 
1
1
,

 
 
2
,

 
 
6
,

 
 
5
,

 
 
8
4
,

 
 
6
,

 
 
1
0
3
,

 
 
2
1
9
,

 
 
1
5
8
,

 
 
2
,

 
 
3
0
2
9
,

 
 
1
,

 
 
2
9
]
,

 
[
2
9
6
,

 
 
6
9
,

 
 
1
,

 
 
7
3
5
,

 
 
3
,

 
 
1
,

 
 
1
2
5
0
,

 
 
1
0
,

 
 
1
,

 
 
1
9
8
,

 
 
2
4
8
,

 
 
1
5
7
5
,

 
 
3
2
2
0
,

 
 
2
4
,

 
 
4
3
1
8
,

 
 
1
0
,

 
 
6
4
,

 
 
4
4
0
0
,

 
 
5
,

 
 
3
7
3
7
3
,

 
 
5
,

 
 
7
2
9
0
,

 
 
9
2
9
,

 
 
1
7
2
,

 
 
1
0
1
5
,

 
 
4
9
,

 
 
1
7
,

 
 
1
8
0
5
2
,

 
 
1
7
,

 
 
2
1
0
7
0
,

 
 
3
5
3
4
8
,

 
 
8
2
9
,

 
 
5
9
,

 
 
3
7
3
,

 
 
3
7
,

 
 
2
,

 
 
1
2
8
4
,

 
 
1
1
,

 
 
5
,

 
 
6
9
7
4
7
,

 
 
4
9
9
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
3
0
7
,

 
 
1
3
7
3
8
,

 
 
1
,

 
 
8
3
7
,

 
 
9
,

 
 
7
8
4
5
,

 
 
1
8
2
8
,

 
 
4
0
8
0
,

 
 
3
3
,

 
 
3
7
,

 
 
8
6
8
,

 
 
1
5
2
1
,

 
 
8
1
6
,

 
 
2
8
0
4
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
4
6
3
,

 
 
2
6
,

 
 
1
1
,

 
 
4
5
,

 
 
1
5
9
,

 
 
4
,

 
 
3
5
9
,

 
 
3
,

 
 
1
4
2
,

 
 
2
6
,

 
 
7
,

 
 
2
2
9
,

 
 
3
7
1
,

 
 
4
8
6
,

 
 
1
1
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
2
7
,

 
 
3
1
1
,

 
 
7
,

 
 
3
9
,

 
 
2
1
7
5
,

 
 
1
1
,

 
 
1
5
,

 
 
1
,

 
 
3
5
0
9
]
,

 
[
4
,
 
1
1
4
1
,
 
1
2
,
 
6
,
 
1
,
 
3
2
5
,
 
3
0
0
,
 
1
1
4
1
,
 
2
2
1
3
,
 
1
9
1
,
 
1
6
,
 
1
,
 
3
3
0
4
]
,

 
[
7
4
,
 
1
0
3
,
 
7
,
 
3
4
5
,
 
1
5
0
,
 
1
,
 
2
1
3
,
 
4
9
3
6
,
 
1
,
 
1
2
5
1
,
 
2
2
8
,
 
8
,
 
6
,
 
6
5
,
 
7
2
,
 
9
1
,
 
2
6
0
0
]
,

 
[
1
4
,
 
1
8
6
,
 
3
5
,
 
4
,
 
2
1
6
2
,
 
3
,
 
1
0
6
4
6
5
,
 
1
2
,
 
8
3
5
1
4
,
 
3
8
,
 
4
5
,
 
1
1
,
 
1
7
5
7
]
,

 
[
4
7
9
7
,
 
1
0
3
2
,
 
3
3
,
 
1
3
,
 
2
3
,
 
3
5
,
 
5
5
8
,
 
8
9
2
,
 
6
3
3
,
 
1
2
8
,
 
2
1
5
9
]
,

 
[
7
,

 
 
2
4
,

 
 
5
5
9
,

 
 
2
,

 
 
3
4
5
,

 
 
1
,

 
 
2
5
5
,

 
 
1
6
1
,

 
 
3
6
,

 
 
1
7
3
3
,

 
 
6
9
,

 
 
7
,

 
 
2
3
7
,

 
 
9
9
,

 
 
1
1
,

 
 
1
0
,

 
 
4
,

 
 
2
5
3
,

 
 
5
0
9
,

 
 
1
0
,

 
 
3
0
,

 
 
5
5
2
,

 
 
1
9
6
2
,

 
 
1
3
7
,

 
 
5
7
,

 
 
7
9
1
,

 
 
2
,

 
 
9
4
,

 
 
3
1
5
,

 
 
2
,

 
 
3
5
5
4
,

 
 
1
,

 
 
1
0
7
5
,

 
 
1
6
1
,

 
 
1
2
,

 
 
6
0
,

 
 
8
5
,

 
 
8
9
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
9
7
4
3
,

 
 
5
6
2
,

 
 
1
3
7
,

 
 
1
9
5
0
,

 
 
4
9
2
,

 
 
2
7
4
,

 
 
2
6
8
,

 
 
2
,

 
 
8
8
2
3
,

 
 
7
3
,

 
 
5
8
,

 
 
5
6
2
,

 
 
1
0
,

 
 
2
6
3
9
,

 
 
2
6
1
4
,

 
 
5
1
0
,

 
 
1
8
0
8
,

 
 
2
9
9
3
,

 
 
6
5
3
,

 
 
1
1
2
5
,

 
 
3
0
,

 
 
1
8
8
9
,

 
 
1
4
3
3
,

 
 
7
2
,

 
 
1
5
3
,

 
 
3
5
1
7
,

 
 
1
,

 
 
7
7
,

 
 
4
7
,

 
 
6
2
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
,

 
 
2
9
9
3
,

 
 
6
5
3
,

 
 
6
4
5
,

 
 
2
4
,

 
 
1
4
,

 
 
5
5
4
,

 
 
2
8
,

 
 
4
6
,

 
 
6
4
5
,

 
 
2
9
9
3
,

 
 
6
5
3
,

 
 
1
0
2
2
,

 
 
3
6
3
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
1
6
0
3
8
2
,

 
 
4
6
,

 
 
6
4
5
,

 
 
6
5
3
,

 
 
1
0
2
2
,

 
 
2
3
3
,

 
 
7
,

 
 
1
0
3
,

 
 
8
2
,

 
 
6
0
,

 
 
1
6
0
3
8
3
,

 
 
4
6
,

 
 
6
4
5
,

 
 
6
5
3
,

 
 
1
0
2
2
,

 
 
1
6
0
,

 
 
1
6
0
3
8
4
,

 
 
6
4
2
6
,

 
 
5
,

 
 
1
,

 
 
6
5
3
,

 
 
1
6
1
,

 
 
3
6
,

 
 
7
,

 
 
1
2
6
,

 
 
9
9
,

 
 
3
3
9
,

 
 
7
3
,

 
 
2
6
8
,

 
 
2
,

 
 
5
6
2
,

 
 
2
8
7
,

 
 
1
,

 
 
1
0
7
5
,

 
 
1
6
1
,

 
 
2
4
,

 
 
1
0
4
7
,

 
 
1
5
,

 
 
1
8
0
5
3
,

 
 
4
,

 
 
2
0
8
,

 
 
1
5
7
,

 
 
1
7
6
,

 
 
1
8
0
5
3
,

 
 
2
4
3
,

 
 
6
5
3
,

 
 
2
8
,

 
 
4
2
,

 
 
2
0
0
,

 
 
2
9
9
3
,

 
 
6
5
3
,

 
 
1
4
1
6
9
,

 
 
1
1
,

 
 
2
8
2
,

 
 
1
7
7
4
7
,

 
 
4
9
3
9
9
,

 
 
5
4
,

 
 
8
,

 
 
2
7
2
2
,

 
 
1
0
2
,

 
 
5
8
4
9
]
,

 
[
1
0
1
,

 
 
1
4
,

 
 
1
5
0
,

 
 
1
,

 
 
5
9
9
,

 
 
2
6
,

 
 
1
5
0
,

 
 
7
4
,

 
 
5
3
,

 
 
3
4
,

 
 
2
1
8
,

 
 
2
1
,

 
 
8
2
4
6
,

 
 
6
8
,

 
 
1
3
9
3
,

 
 
8
,

 
 
4
4
0
,

 
 
1
5
,

 
 
1
0
6
4
6
6
,

 
 
2
9
,

 
 
5
,

 
 
6
,

 
 
3
9
,

 
 
1
3
6
,

 
 
1
1
,

 
 
2
2
,

 
 
6
,

 
 
1
4
7
,

 
 
1
1
0
8
,

 
 
1
0
0
1
,

 
 
7
,

 
 
6
5
,

 
 
7
,

 
 
1
9
,

 
 
3
0
,

 
 
2
2
0
6
,

 
 
2
1
,

 
 
2
1
1
7
,

 
 
3
7
6
,

 
 
2
,

 
 
1
6
,

 
 
1
8
6
,

 
 
2
6
,

 
 
2
4
,

 
 
1
8
4
9
,

 
 
2
,

 
 
6
3
,

 
 
4
,

 
 
2
1
3
,

 
 
3
6
,

 
 
7
,

 
 
4
1
6
,

 
 
4
,

 
 
1
9
3
,

 
 
5
0
6
,

 
 
3
7
6
]
,

 
[
1
4
,

 
 
3
3
,

 
 
4
0
,

 
 
6
,

 
 
1
8
,

 
 
2
9
0
,

 
 
4
,

 
 
4
6
8
2
,

 
 
4
0
0
,

 
 
6
2
7
,

 
 
6
4
,

 
 
7
,

 
 
1
9
9
,

 
 
1
4
4
5
,

 
 
1
0
6
4
6
7
,

 
 
9
9
,

 
 
9
,

 
 
5
7
5
,

 
 
2
6
4
,

 
 
9
,

 
 
8
5
0
7
,

 
 
5
,

 
 
4
5
3
2
,

 
 
1
0
,

 
 
1
,

 
 
9
9
5
,

 
 
2
0
4
8
,

 
 
1
,

 
 
1
2
2
7
5
,

 
 
5
7
5
,

 
 
5
4
,

 
 
8
,

 
 
6
3
4
,

 
 
3
8
,

 
 
1
,

 
 
5
8
2
,

 
 
2
8
6
,

 
 
5
,

 
 
6
6
,

 
 
1
6
3
,

 
 
1
0
6
4
6
7
,

 
 
4
0
0
6
,

 
 
2
1
,

 
 
1
2
7
,

 
 
7
,

 
 
2
4
,

 
 
2
7
6
7
0
,

 
 
1
,

 
 
3
3
7
2
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
4
,

 
 
2
8
1
5
,

 
 
2
2
3
,

 
 
2
,

 
 
4
0
3
,

 
 
9
,

 
 
6
6
9
8
,

 
 
8
,

 
 
4
,

 
 
1
1
6
5
,

 
 
5
8
0
1
,

 
 
1
4
4
,

 
 
1
3
0
,

 
 
4
5
3
2
,

 
 
1
3
0
8
,

 
 
1
3
,

 
 
5
7
5
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
3
0
5
4
,

 
 
2
,

 
 
4
5
8
,

 
 
1
1
,

 
 
2
8
1
5
,

 
 
1
,

 
 
4
4
5
0
,

 
 
2
2
3
,

 
 
8
,

 
 
4
7
9
8
,

 
 
1
0
,

 
 
1
,

 
 
9
9
5
,

 
 
6
0
,

 
 
1
3
5
3
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
4
4
5
0
,

 
 
3
3
,

 
 
4
0
,

 
 
6
0
,

 
 
3
4
,

 
 
3
3
,

 
 
1
,

 
 
4
5
3
,

 
 
3
,

 
 
1
,

 
 
3
0
3
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
1
2
3
4
,

 
 
3
5
1
0
,

 
 
1
7
,

 
 
1
6
8
9
0
,

 
 
1
6
5
3
,

 
 
7
6
,

 
 
1
0
2
3
,

 
 
1
0
,

 
 
1
,

 
 
1
6
7
4
,

 
 
1
4
,

 
 
4
,

 
 
1
0
6
1
,

 
 
3
1
4
4
,

 
 
2
2
,

 
 
5
3
,

 
 
1
5
2
7
,

 
 
2
,

 
 
9
7
,

 
 
1
3
,

 
 
1
2
3
4
,

 
 
3
5
1
0
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
7
1
6
,

 
 
3
8
3
,

 
 
5
,

 
 
1
4
,

 
 
3
5
9
5
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
1
0
6
1
,

 
 
1
2
6
7
]
,

 
[
8
1
7
4
,

 
 
2
5
9
5
,

 
 
1
4
9
0
,

 
 
1
,

 
 
1
9
7
6
,

 
 
1
1
9
4
8
,

 
 
3
,

 
 
2
1
0
7
1
,

 
 
4
9
4
0
0
,

 
 
2
2
4
8
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
2
7
8
9
,

 
 
2
6
,

 
 
9
1
,

 
 
4
9
4
,

 
 
8
,

 
 
6
6
5
,

 
 
1
5
5
,

 
 
7
,

 
 
4
9
,

 
 
2
9
1
,

 
 
4
,

 
 
7
1
7
,

 
 
1
2
,

 
 
4
,

 
 
5
8
,

 
 
3
5
1
1
,

 
 
3
8
3
8
,

 
 
1
2
3
8
,

 
 
3
2
,

 
 
6
2
7
4
,

 
 
5
6
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
7
5
,

 
 
1
6
0
3
8
5
,

 
 
5
,

 
 
2
6
0
9
,

 
 
3
6
,

 
 
3
1
3
,

 
 
7
1
7
,

 
 
1
2
,

 
 
5
4
2
6
4
,

 
 
9
5
6
,

 
 
2
4
,

 
 
1
3
7
3
,

 
 
2
,

 
 
1
8
2
2
,

 
 
3
2
,

 
 
1
9
4
0
2
,

 
 
3
1
,

 
 
2
7
8
9
,

 
 
6
2
,

 
 
1
0
,

 
 
1
3
7
7
,

 
 
5
6
4
8
,

 
 
9
2
,

 
 
4
1
9
3
,

 
 
2
,

 
 
8
7
3
3
,

 
 
2
5
9
5
,

 
 
8
8
3
,

 
 
1
2
0
1
,

 
 
5
3
5
,

 
 
3
8
3
8
,

 
 
1
2
3
8
,

 
 
3
2
,

 
 
6
2
7
4
,

 
 
2
6
4
3
,

 
 
1
,

 
 
5
4
2
6
4
,

 
 
8
1
0
2
,

 
 
3
1
,

 
 
2
7
8
9
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
,

 
 
6
9
4
,

 
 
2
2
0
9
6
,

 
 
3
3
6
4
2
,

 
 
8
3
3
4
,

 
 
5
,

 
 
6
1
,

 
 
8
3
3
4
,

 
 
2
1
,

 
 
8
7
4
,

 
 
7
9
6
6
,

 
 
2
8
6
2
5
,

 
 
6
9
4
,

 
 
1
6
0
3
8
6
,

 
 
5
,

 
 
6
9
4
,

 
 
1
6
0
3
8
7
,

 
 
4
2
3
3
6
,

 
 
9
,

 
 
1
,

 
 
7
2
7
,

 
 
6
9
4
,

 
 
1
5
4
6
5
,

 
 
4
2
,

 
 
5
7
,

 
 
7
7
4
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
8
7
3
3
,

 
 
2
4
2
7
,

 
 
1
6
0
6
,

 
 
9
2
,

 
 
6
6
0
,

 
 
3
,

 
 
8
7
3
3
,

 
 
2
5
9
5
,

 
 
1
4
9
0
,

 
 
2
4
3
3
,

 
 
1
2
0
1
,

 
 
8
4
,

 
 
1
6
0
3
8
8
,

 
 
9
,

 
 
1
,

 
 
8
3
5
1
5
,

 
 
3
,

 
 
2
1
5
7
2
,

 
 
9
9
2
5
,

 
 
3
1
,

 
 
8
7
3
3
,

 
 
2
5
9
5
,

 
 
6
6
,

 
 
1
3
7
3
,

 
 
1
5
4
6
5
,

 
 
6
9
4
,

 
 
1
8
0
5
1
,

 
 
2
,

 
 
2
7
8
9
,

 
 
5
,

 
 
1
8
7
5
,

 
 
2
,

 
 
1
8
2
2
,

 
 
1
0
,

 
 
1
,

 
 
1
3
3
2
6
,

 
 
6
0
0
,

 
 
1
1
,

 
 
3
8
6
,

 
 
5
3
,

 
 
1
7
8
5
,

 
 
9
,

 
 
1
,

 
 
5
4
2
6
4
,

 
 
1
1
5
8
,

 
 
1
7
4
4
5
,

 
 
1
5
2
5
7
,

 
 
3
1
,

 
 
1
1
7
3
9
,

 
 
9
9
2
5
,

 
 
9
,

 
 
9
9
,

 
 
9
2
,

 
 
2
9
3
0
,

 
 
1
0
,

 
 
1
9
4
0
3
,

 
 
2
5
9
5
,

 
 
3
7
5
,

 
 
1
6
5
,

 
 
1
5
7
,

 
 
2
,

 
 
1
,

 
 
1
6
0
6
,

 
 
3
,

 
 
8
8
2
4
,

 
 
1
0
,

 
 
1
3
,

 
 
1
6
1
3
,

 
 
6
9
7
4
8
,

 
 
3
8
3
8
,

 
 
1
2
3
8
,

 
 
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
4
,

 
 
1
7
0
3
,

 
 
4
5
9
4
,

 
 
9
5
6
9
,

 
 
3
,

 
 
1
6
0
,

 
 
2
5
7
2
,

 
 
6
0
4
2
,

 
 
3
1
,

 
 
2
8
7
7
,

 
 
2
4
2
7
,

 
 
5
1
3
5
,

 
 
4
7
3
,

 
 
1
7
0
0
,

 
 
5
1
3
5
,

 
 
2
0
1
9
9
,

 
 
3
1
,

 
 
1
0
8
0
,

 
 
1
,

 
 
1
2
9
7
,

 
 
2
0
6
4
8
]
,

 
[
5
2
1
,

 
 
1
2
8
,

 
 
5
4
5
,

 
 
3
1
,

 
 
6
6
7
5
,

 
 
1
5
9
4
,

 
 
4
3
0
2
,

 
 
3
6
2
3
,

 
 
2
4
,

 
 
9
0
8
,

 
 
3
3
,

 
 
6
9
7
4
9
,

 
 
3
3
6
8
,

 
 
4
1
9
4
,

 
 
4
9
9
,

 
 
5
0
2
,

 
 
1
9
7
,

 
 
7
2
,

 
 
1
4
,

 
 
1
8
6
,

 
 
1
3
,

 
 
3
9
4
4
,

 
 
2
5
9
,

 
 
1
7
,

 
 
9
1
,

 
 
4
,

 
 
6
9
7
4
9
,

 
 
3
3
6
8
,

 
 
1
6
9
6
,

 
 
8
4
1
6
,

 
 
3
9
6
4
,

 
 
8
,

 
 
7
,

 
 
2
2
0
,

 
 
2
0
3
,

 
 
3
1
,

 
 
1
,

 
 
1
6
0
7
,

 
 
3
,

 
 
3
2
0
2
,

 
 
1
6
0
3
8
9
,

 
 
5
7
0
1
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
2
4
,

 
 
1
7
3
,

 
 
3
2
,

 
 
2
1
3
6
,

 
 
5
6
0
,

 
 
6
1
4
9
,

 
 
7
1
9
7
,

 
 
1
8
9
2
,

 
 
1
3
9
9
,

 
 
3
1
5
8
,

 
 
9
8
1
,

 
 
9
1
9
,

 
 
7
1
0
,

 
 
2
1
6
]
,

 
[
1
7
8
,

 
 
3
8
5
9
,

 
 
3
9
,

 
 
6
,

 
 
2
1
3
,

 
 
6
9
4
,

 
 
2
2
0
9
7
,

 
 
1
2
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
5
,

 
 
1
,

 
 
4
5
4
8
9
,

 
 
3
7
3
7
4
,

 
 
1
1
3
,

 
 
5
2
,

 
 
4
2
,

 
 
1
3
1
,

 
 
4
3
0
,

 
 
1
4
0
,

 
 
5
4
,

 
 
3
9
,

 
 
7
7
,

 
 
1
6
,

 
 
9
5
7
,

 
 
1
7
,

 
 
2
3
1
6
]
,

 
[
5
0
3
,

 
 
3
,

 
 
1
0
6
4
6
8
,

 
 
8
3
5
1
6
,

 
 
4
,

 
 
2
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
8
,

 
 
1
5
,

 
 
1
0
6
4
6
8
,

 
 
8
3
5
1
6
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
7
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
3
5
,

 
 
4
,

 
 
2
2
2
,

 
 
4
3
8
,

 
 
3
,

 
 
7
5
,

 
 
7
4
6
,

 
 
1
1
9
3
,

 
 
6
7
2
,

 
 
2
5
,

 
 
5
8
6
,

 
 
1
7
4
,

 
 
2
6
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
9
2
0
,

 
 
7
4
,

 
 
2
5
,

 
 
7
8
,

 
 
1
,

 
 
2
5
7
,

 
 
8
,

 
 
3
4
2
,

 
 
9
,

 
 
8
,

 
 
7
8
,

 
 
2
7
,

 
 
2
3
,

 
 
3
5
,

 
 
9
,

 
 
2
5
7
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
2
8
,

 
 
1
8
2
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
8
3
,

 
 
9
,

 
 
3
4
,

 
 
1
4
,

 
 
2
0
1
1
,

 
 
5
0
3
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
3
3
,

 
 
5
5
,

 
 
8
5
,

 
 
5
0
,

 
 
6
3
,

 
 
1
,

 
 
4
2
7
,

 
 
1
2
,

 
 
3
8
,

 
 
8
,

 
 
7
0
1
,

 
 
9
0
4
,

 
 
1
7
,

 
 
3
4
2
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
3
9
,

 
 
9
2
0
,

 
 
7
8
,

 
 
1
,

 
 
2
5
7
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
3
4
2
,

 
 
6
,

 
 
8
7
,

 
 
1
1
5
9
,

 
 
1
,

 
 
1
6
7
9
,

 
 
2
,

 
 
3
4
,

 
 
1
3
,

 
 
1
5
2
,

 
 
1
5
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
5
6
7
,

 
 
1
,

 
 
9
8
6
,

 
 
1
7
7
6
,

 
 
2
7
7
,

 
 
5
,

 
 
3
1
7
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
8
1
7
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
7
7
,

 
 
2
2
5
,

 
 
2
6
,

 
 
5
9
,

 
 
1
5
2
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
4
3
,

 
 
1
5
5
4
,

 
 
1
0
4
,

 
 
1
9
0
7
,

 
 
5
0
3
,

 
 
1
8
2
,

 
 
1
,

 
 
4
2
7
,

 
 
1
2
,

 
 
4
2
7
,

 
 
1
5
,

 
 
4
9
4
,

 
 
1
3
6
9
,

 
 
3
,

 
 
8
3
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
7
5
,

 
 
4
3
4
,

 
 
1
2
,

 
 
1
3
9
5
,

 
 
1
2
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
1
2
,

 
 
1
7
2
8
,

 
 
2
5
,

 
 
1
2
,

 
 
1
5
2
8
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
1
7
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
3
5
,

 
 
1
3
]
,

 
[
1
8
6
,

 
 
2
6
,

 
 
1
,

 
 
5
1
4
,

 
 
2
4
5
,

 
 
4
0
0
7
,

 
 
4
4
3
9
,

 
 
4
5
4
9
0
,

 
 
1
7
9
,

 
 
7
,

 
 
3
0
9
,

 
 
1
7
3
,

 
 
3
8
,

 
 
7
,

 
 
2
9
1
,

 
 
8
3
3
,

 
 
2
2
,

 
 
2
5
9
,

 
 
1
5
9
5
,

 
 
1
3
,

 
 
2
5
,

 
 
9
,

 
 
4
6
5
,

 
 
8
,

 
 
2
8
7
8
,

 
 
1
2
,

 
 
1
,

 
 
5
1
4
,

 
 
5
1
,

 
 
1
8
,

 
 
1
9
6
,

 
 
2
,

 
 
2
5
6
,

 
 
9
7
,

 
 
1
4
0
,

 
 
4
6
]
,

 
[
7
5
0
0
,

 
 
7
,

 
 
6
5
,

 
 
5
3
,

 
 
4
9
,

 
 
8
3
5
1
7
,

 
 
7
,

 
 
6
5
,

 
 
5
3
,

 
 
2
2
2
2
,

 
 
2
,

 
 
4
3
3
,

 
 
6
1
,

 
 
1
7
7
,

 
 
1
2
3
7
,

 
 
4
3
3
,

 
 
2
8
7
,

 
 
3
0
1
9
,

 
 
7
,

 
 
1
7
3
,

 
 
1
6
3
,

 
 
1
0
,

 
 
6
3
9
,

 
 
2
,

 
 
1
2
3
9
,

 
 
2
6
,

 
 
5
9
,

 
 
7
0
,

 
 
2
2
,

 
 
6
,

 
 
6
8
7
,

 
 
1
1
6
8
,

 
 
5
0
6
,

 
 
3
7
6
,

 
 
1
1
3
,

 
 
2
5
6
0
,

 
 
1
1
3
,

 
 
4
9
2
]
,

 
[
6
,

 
 
1
8
,

 
 
1
9
4
,

 
 
2
5
,

 
 
1
6
0
3
9
0
,

 
 
2
7
6
7
1
,

 
 
5
7
8
,

 
 
5
8
3
0
,

 
 
1
4
7
1
1
,

 
 
1
6
0
3
9
1
,

 
 
4
0
6
7
,

 
 
4
1
,

 
 
1
8
,

 
 
1
4
9
,

 
 
1
2
6
9
,

 
 
7
8
,

 
 
6
,

 
 
3
4
,

 
 
4
6
4
7
,

 
 
3
0
,

 
 
2
0
6
,

 
 
3
5
,

 
 
8
0
3
0
,

 
 
9
,

 
 
2
3
8
5
,

 
 
2
4
,

 
 
1
6
1
3
1
,

 
 
4
9
4
0
1
,

 
 
3
,

 
 
7
2
1
,

 
 
5
,

 
 
1
4
,

 
 
5
6
1
2
,

 
 
6
9
7
5
0
,

 
 
7
1
6
8
,

 
 
2
5
9
,

 
 
1
6
2
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
5
6
1
,

 
 
1
0
6
4
6
9
,

 
 
9
3
,

 
 
1
5
8
7
9
,

 
 
2
0
,

 
 
8
1
0
,

 
 
7
9
6
7
,

 
 
5
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
2
6
7
3
5
,

 
 
8
3
7
7
,

 
 
1
6
0
,

 
 
2
2
,

 
 
6
,

 
 
8
9
3
,

 
 
4
0
9
,

 
 
3
,

 
 
1
,

 
 
2
1
1
8
,

 
 
9
,

 
 
3
4
8
3
,

 
 
8
,

 
 
4
,

 
 
1
0
4
2
0
,

 
 
5
6
4
9
,

 
 
9
7
,

 
 
4
,

 
 
3
0
8
0
0
,

 
 
6
9
7
5
1
,

 
 
1
5
,

 
 
2
0
,

 
 
1
4
3
6
1
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
8
3
5
1
8
,

 
 
6
4
2
7
,

 
 
2
1
,

 
 
2
0
,

 
 
1
9
4
,

 
 
1
9
8
0
7
,

 
 
2
3
3
,

 
 
1
1
4
,

 
 
5
,

 
 
2
6
2
,

 
 
5
8
7
,

 
 
6
,

 
 
2
4
0
,

 
 
1
9
4
,

 
 
7
,

 
 
6
2
4
,

 
 
6
8
5
,

 
 
2
2
,

 
 
5
5
,

 
 
5
8
,

 
 
1
1
4
3
,

 
 
1
0
6
4
7
0
,

 
 
4
3
,

 
 
3
5
0
,

 
 
1
0
,

 
 
3
0
,

 
 
2
9
,

 
 
7
,

 
 
5
9
,

 
 
5
4
8
,

 
 
2
,

 
 
4
6
,

 
 
2
,

 
 
6
,

 
 
1
3
5
4
,

 
 
7
7
0
3
,

 
 
3
,

 
 
1
,

 
 
2
1
6
9
,

 
 
6
5
4
]
,

 
[
6
7
,
 
2
0
,
 
5
8
8
2
,
 
7
3
5
,
 
1
0
,
 
1
,
 
3
4
0
,
 
5
2
6
5
]
,

 
[
7
2
,

 
 
2
8
0
,

 
 
7
2
,

 
 
2
8
0
,

 
 
7
,

 
 
5
8
0
2
,

 
 
3
1
5
,

 
 
2
1
,

 
 
9
6
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
0
2
,

 
 
3
6
6
,

 
 
2
,

 
 
3
4
,

 
 
7
,

 
 
7
0
,

 
 
7
4
,

 
 
3
5
5
,

 
 
1
,

 
 
1
1
4
7
,

 
 
1
5
,

 
 
9
2
,

 
 
4
6
,

 
 
2
9
,

 
 
1
8
0
7
,

 
 
6
,

 
 
2
0
1
1
,

 
 
2
0
,

 
 
1
1
7
4
0
,

 
 
1
4
8
,

 
 
8
8
,

 
 
7
,

 
 
7
0
,

 
 
7
,

 
 
5
6
,

 
 
6
5
4
4
,

 
 
3
2
2
,

 
 
2
,

 
 
1
,

 
 
1
2
2
7
6
,

 
 
1
2
5
3
,

 
 
2
6
,

 
 
8
4
,

 
 
1
2
7
,

 
 
7
2
,

 
 
1
6
5
,

 
 
2
,

 
 
1
1
8
,

 
 
8
7
9
,

 
 
9
8
5
,

 
 
2
1
,

 
 
2
0
,

 
 
2
5
8
7
,

 
 
2
5
9
0
,

 
 
5
4
1
1
,

 
 
4
2
3
9
,

 
 
3
1
7
8
]
,

 
[
7
,

 
 
5
9
,

 
 
2
2
0
,

 
 
1
,

 
 
6
9
7
5
2
,

 
 
8
9
5
,

 
 
6
9
3
,

 
 
4
1
,

 
 
1
2
6
1
4
,

 
 
2
1
,

 
 
1
,

 
 
2
3
8
1
6
,

 
 
7
2
3
,

 
 
6
9
7
5
2
,

 
 
1
8
1
,

 
 
1
9
,

 
 
4
,

 
 
5
1
6
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
2
,

 
 
1
9
7
4
,

 
 
2
1
,

 
 
2
2
,

 
 
2
7
,

 
 
1
5
5
2
,

 
 
2
,

 
 
4
5
4
9
1
,

 
 
2
5
,

 
 
9
6
,

 
 
1
3
1
4
,

 
 
3
7
9
,

 
 
3
,

 
 
4
5
4
9
1
,

 
 
1
1
1
7
,

 
 
3
3
6
4
3
,

 
 
4
,

 
 
2
7
6
7
2
,

 
 
1
3
5
,

 
 
9
5
0
,

 
 
1
7
2
,

 
 
1
4
0
2
,

 
 
1
9
,

 
 
5
7
,

 
 
1
4
8
8
1
,

 
 
1
,

 
 
1
0
6
4
7
1
,

 
 
8
,

 
 
1
5
3
,

 
 
1
5
5
8
,

 
 
8
7
0
,

 
 
2
2
,

 
 
6
,

 
 
7
0
,

 
 
6
,

 
 
1
8
,

 
 
1
3
4
6
,

 
 
1
,

 
 
6
5
6
,

 
 
6
,

 
 
4
5
,

 
 
1
3
5
3
,

 
 
2
1
,

 
 
2
5
6
1
,

 
 
2
5
,

 
 
2
0
6
4
9
,

 
 
6
6
,

 
 
2
2
3
,

 
 
3
,

 
 
6
9
7
5
3
,

 
 
3
9
4
,

 
 
2
4
,

 
 
4
,

 
 
1
4
5
4
0
,

 
 
3
,

 
 
1
,

 
 
4
2
3
3
7
,

 
 
6
9
0
,

 
 
1
2
5
,

 
 
4
4
1
,

 
 
2
,

 
 
1
6
5
1
,

 
 
2
2
,

 
 
5
5
,

 
 
8
6
,

 
 
6
7
9
,

 
 
1
6
0
3
9
2
,

 
 
1
0
,

 
 
4
0
,

 
 
8
3
5
1
9
,

 
 
1
,

 
 
4
2
3
3
7
,

 
 
4
0
7
,

 
 
3
,

 
 
1
1
1
1
,

 
 
1
2
2
7
7
,

 
 
3
8
,

 
 
1
,

 
 
1
6
7
0
,

 
 
1
6
7
,

 
 
8
1
2
,

 
 
2
0
3
3
,

 
 
9
,

 
 
6
9
7
5
2
,

 
 
8
,

 
 
4
,

 
 
2
9
3
5
,

 
 
5
7
1
7
,

 
 
8
,

 
 
5
4
9
4
,

 
 
2
2
,

 
 
5
4
2
6
5
,

 
 
8
,

 
 
4
,

 
 
2
9
3
5
,

 
 
5
7
1
7
,

 
 
7
,

 
 
2
6
3
,

 
 
9
,

 
 
3
0
,

 
 
7
9
,

 
 
5
9
3
,

 
 
1
7
,

 
 
5
1
6
,

 
 
1
7
,

 
 
4
4
1
,

 
 
2
3
8
,

 
 
3
6
,

 
 
1
7
3
2
,

 
 
1
2
,

 
 
9
,

 
 
1
5
3
,

 
 
1
6
3
,

 
 
2
4
5
,

 
 
1
6
,

 
 
2
0
7
,

 
 
6
4
]
,

 
[
6
,
 
9
9
,
 
4
,
 
1
4
5
,
 
5
,
 
7
1
,
 
8
9
,
 
3
3
6
4
4
,
 
2
1
,
 
4
8
1
,
 
1
3
1
0
,
 
5
0
3
,
 
1
8
6
9
]
,

 
[
1
0
,

 
 
6
1
,

 
 
4
0
9
,

 
 
1
6
4
,

 
 
1
5
5
,

 
 
3
1
8
4
,

 
 
2
,

 
 
2
0
3
,

 
 
1
4
5
,

 
 
2
1
5
,

 
 
7
6
,

 
 
3
8
8
,

 
 
6
,

 
 
2
3
6
,

 
 
9
,

 
 
1
5
9
0
,

 
 
1
,

 
 
2
7
7
,

 
 
8
0
3
]
,

 
[
1
7
,

 
 
1
2
,

 
 
2
0
,

 
 
5
3
8
,

 
 
3
,

 
 
2
8
8
5
,

 
 
9
,

 
 
8
,

 
 
2
7
2
3
,

 
 
2
4
3
6
,

 
 
5
,

 
 
3
7
1
0
,

 
 
7
7
,

 
 
2
,

 
 
4
2
3
3
8
,

 
 
1
,

 
 
9
4
0
,

 
 
7
,

 
 
1
9
,

 
 
2
6
5
4
,

 
 
9
8
,

 
 
5
8
8
,

 
 
5
,

 
 
9
8
,

 
 
3
4
3
0
,

 
 
1
5
,

 
 
2
0
,

 
 
2
2
3
,

 
 
5
,

 
 
1
9
,

 
 
1
9
9
,

 
 
1
2
9
3
,

 
 
2
5
,

 
 
4
4
6
,

 
 
2
1
2
,

 
 
2
,

 
 
4
6
8
,

 
 
9
,

 
 
6
,

 
 
1
8
4
,

 
 
1
9
,

 
 
6
0
,

 
 
1
6
8
9
1
,

 
 
6
8
0
7
,

 
 
1
0
,

 
 
1
4
6
9
,

 
 
3
1
0
,

 
 
2
2
4
,

 
 
2
,

 
 
4
7
,

 
 
4
9
4
,

 
 
8
2
9
2
,

 
 
5
8
6
,

 
 
2
9
,

 
 
6
2
1
,

 
 
1
2
,

 
 
9
,

 
 
3
5
4
,

 
 
1
9
,

 
 
7
,

 
 
3
4
9
,

 
 
1
3
1
,

 
 
5
5
,

 
 
1
2
5
7
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
2
7
,

 
 
3
0
3
0
,

 
 
3
5
4
,

 
 
2
5
,

 
 
9
6
,

 
 
4
4
5
,

 
 
1
1
1
,

 
 
4
,

 
 
1
4
1
9
,

 
 
3
8
3
,

 
 
1
7
,

 
 
4
,

 
 
6
0
4
,

 
 
2
,

 
 
1
3
,

 
 
3
4
3
5
,

 
 
7
,

 
 
4
3
,

 
 
1
4
,

 
 
3
4
,

 
 
3
6
,

 
 
3
3
,

 
 
5
5
,

 
 
1
9
6
8
,

 
 
1
7
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
4
,

 
 
8
0
1
,

 
 
3
,

 
 
5
6
2
,

 
 
7
,

 
 
4
3
,

 
 
2
1
9
,

 
 
9
,

 
 
6
,

 
 
7
7
2
,

 
 
5
1
7
3
,

 
 
1
,

 
 
1
3
9
,

 
 
9
8
,

 
 
5
8
8
,

 
 
2
5
8
3
,

 
 
3
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
2
9
0
,

 
 
6
2
2
5
,

 
 
5
,

 
 
5
3
7
4
,

 
 
1
4
7
2
,

 
 
3
2
1
4
3
]
,

 
[
2
5
9
1
8
,

 
 
1
0
,

 
 
6
4
7
,

 
 
2
,

 
 
1
4
3
6
2
,

 
 
3
0
8
0
1
,

 
 
3
1
9
,

 
 
6
2
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
5
5
9
3
,

 
 
5
3
8
,

 
 
1
1
7
0
,

 
 
7
8
2
,

 
 
1
1
0
,

 
 
5
8
8
3
,

 
 
4
6
8
3
,

 
 
1
0
,

 
 
6
6
2
,

 
 
3
5
3
4
9
,

 
 
2
6
4
,

 
 
3
9
8
7
,

 
 
1
7
,

 
 
4
,

 
 
1
4
3
,

 
 
1
9
8
6
,

 
 
1
0
9
4
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
7
2
,

 
 
7
4
9
,

 
 
1
0
5
0
3
,

 
 
1
5
9
6
,

 
 
5
9
0
,

 
 
1
5
,

 
 
1
,

 
 
2
5
7
,

 
 
9
,

 
 
8
,

 
 
1
4
,

 
 
1
,

 
 
3
0
8
0
1
,

 
 
3
1
9
,

 
 
3
3
,

 
 
4
0
,

 
 
1
,

 
 
3
1
9
,

 
 
2
2
2
4
,

 
 
3
2
,

 
 
2
9
3
5
,

 
 
1
9
5
8
,

 
 
3
,

 
 
4
6
8
3
,

 
 
6
2
,

 
 
3
5
0
,

 
 
1
0
,

 
 
4
,

 
 
1
4
6
7
,

 
 
5
4
,

 
 
8
,

 
 
1
4
,

 
 
8
7
1
,

 
 
2
,

 
 
5
5
,

 
 
5
6
2
,

 
 
4
3
8
,

 
 
1
1
1
,

 
 
1
7
,

 
 
5
1
7
4
,

 
 
9
8
5
9
,

 
 
3
3
6
4
5
,

 
 
1
4
3
6
3
,

 
 
5
1
7
4
,

 
 
1
0
6
4
7
2
,

 
 
5
,

 
 
1
6
0
3
9
3
,

 
 
1
0
6
4
7
3
,

 
 
4
0
,

 
 
1
6
0
3
9
4
,

 
 
4
6
8
3
,

 
 
1
7
,

 
 
4
,

 
 
7
8
2
,

 
 
1
1
0
,

 
 
1
7
,

 
 
1
,

 
 
2
9
5
,

 
 
3
1
4
,

 
 
1
,

 
 
7
7
,

 
 
2
1
5
7
3
,

 
 
7
2
,

 
 
7
4
9
,

 
 
3
,

 
 
6
2
,

 
 
3
6
4
,

 
 
2
,

 
 
6
5
,

 
 
4
6
8
3
,

 
 
4
2
,

 
 
4
9
4
0
2
,

 
 
4
4
,

 
 
7
4
1
6
,

 
 
5
1
1
2
,

 
 
5
,

 
 
8
,

 
 
1
1
3
1
,

 
 
4
,

 
 
4
0
8
2
,

 
 
1
4
3
,

 
 
6
2
5
,

 
 
1
8
,

 
 
1
7
2
2
,

 
 
8
3
9
,

 
 
8
6
8
0
,

 
 
6
2
,

 
 
1
0
8
,

 
 
2
,

 
 
2
0
4
,

 
 
1
7
,

 
 
1
2
8
,

 
 
3
2
4
1
,

 
 
3
2
9
,

 
 
1
,

 
 
4
8
2
9
,

 
 
1
7
,

 
 
4
4
1
,

 
 
1
3
,

 
 
3
,

 
 
4
4
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
6
9
,

 
 
3
1
,

 
 
4
1
2
3
,

 
 
7
5
,

 
 
1
0
,

 
 
4
,

 
 
5
7
5
,

 
 
2
,

 
 
3
5
0
,

 
 
5
9
0
,

 
 
1
2
,

 
 
3
1
1
,

 
 
9
6
,

 
 
1
,

 
 
1
0
0
9
6
,

 
 
3
0
8
0
1
,

 
 
1
6
2
0
,

 
 
1
5
,

 
 
4
6
8
3
,

 
 
5
,

 
 
4
,

 
 
1
1
6
0
,

 
 
8
7
5
,

 
 
3
,

 
 
2
1
0
,

 
 
1
,

 
 
2
1
3
7
,

 
 
6
0
4
,

 
 
5
,

 
 
8
4
,

 
 
3
0
6
0
,

 
 
6
0
4
,

 
 
3
,

 
 
3
3
5
6
,

 
 
8
3
5
2
0
,

 
 
5
4
4
,

 
 
3
5
3
5
0
,

 
 
1
8
1
,

 
 
2
8
9
,

 
 
2
,

 
 
1
1
4
0
,

 
 
7
3
,

 
 
1
0
4
,

 
 
4
9
4
0
3
,

 
 
2
9
3
0
,

 
 
5
,

 
 
7
8
2
,

 
 
1
1
0
,

 
 
6
9
1
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
4
0
0
,

 
 
6
2
,

 
 
4
2
,

 
 
5
4
1
,

 
 
4
,

 
 
5
2
6
6
,

 
 
2
0
7
4
,

 
 
3
0
2
0
,

 
 
7
2
6
,

 
 
1
5
,

 
 
1
4
0
4
0
]
,

 
[
5
0
4
8
,

 
 
6
,

 
 
1
6
7
,

 
 
6
,

 
 
5
7
7
,

 
 
2
,

 
 
4
6
,

 
 
3
3
,

 
 
1
,

 
 
1
2
1
6
,

 
 
3
,

 
 
1
,

 
 
5
1
4
,

 
 
1
1
6
,

 
 
6
,

 
 
1
9
,

 
 
3
9
1
,

 
 
1
0
4
,

 
 
1
7
7
4
8
,

 
 
1
1
5
5
9
,

 
 
1
0
,

 
 
4
0
6
8
,

 
 
9
,

 
 
1
,

 
 
2
0
6
5
0
,

 
 
1
2
9
0
,

 
 
1
0
3
,

 
 
1
6
,

 
 
2
8
5
8
,

 
 
8
6
4
6
,

 
 
2
1
,

 
 
3
8
,

 
 
8
,

 
 
1
7
1
5
2
,

 
 
3
3
2
,

 
 
2
,

 
 
1
6
,

 
 
3
3
6
4
6
,

 
 
2
0
9
,

 
 
4
,

 
 
8
3
6
,

 
 
1
2
9
5
1
,

 
 
2
6
,

 
 
1
,

 
 
2
0
6
5
0
,

 
 
8
,

 
 
1
4
,

 
 
8
6
4
6
,

 
 
2
1
,

 
 
6
1
,

 
 
9
7
4
4
,

 
 
2
0
6
5
1
,

 
 
3
3
4
5
,

 
 
1
0
,

 
 
8
1
3
,

 
 
1
,

 
 
9
7
4
4
,

 
 
2
0
6
5
0
,

 
 
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
1
7
7
,

 
 
1
4
,

 
 
8
3
5
2
1
,

 
 
1
2
4
9
7
,

 
 
2
0
9
,

 
 
5
8
6
5
,

 
 
8
4
2
,

 
 
2
4
5
2
,

 
 
4
5
6
,

 
 
1
0
,

 
 
8
1
3
,

 
 
1
,

 
 
9
7
4
4
,

 
 
2
0
6
5
0
,

 
 
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
1
7
7
,

 
 
1
4
,

 
 
8
3
5
2
1
,

 
 
1
2
4
9
7
,

 
 
2
0
9
,

 
 
5
8
6
5
,

 
 
8
4
2
,

 
 
2
4
5
2
,

 
 
9
,

 
 
4
5
7
,

 
 
5
5
7
,

 
 
2
,

 
 
2
6
9
,

 
 
3
1
,

 
 
1
6
7
8
,

 
 
2
3
3
,

 
 
1
5
,

 
 
2
9
,

 
 
4
5
2
,

 
 
1
,

 
 
5
1
0
,

 
 
5
8
2
,

 
 
8
,

 
 
2
2
,

 
 
1
,

 
 
1
4
6
9
,

 
 
3
,

 
 
1
,

 
 
2
0
6
5
1
,

 
 
7
5
7
,

 
 
5
1
3
,

 
 
2
,

 
 
1
1
4
6
8
,

 
 
2
2
7
5
,

 
 
4
0
2
,

 
 
1
,

 
 
1
4
6
9
,

 
 
3
,

 
 
1
,

 
 
1
8
7
1
2
,

 
 
8
4
,

 
 
9
,

 
 
2
4
,

 
 
2
7
,

 
 
3
6
3
7
,

 
 
1
,

 
 
6
4
6
,

 
 
6
4
4
6
,

 
 
9
1
,

 
 
4
1
9
,

 
 
2
4
,

 
 
1
4
,

 
 
8
3
5
2
1
,

 
 
1
2
4
9
7
,

 
 
2
0
9
,

 
 
5
8
6
5
,

 
 
8
4
2
,

 
 
2
4
5
2
,

 
 
5
0
0
,

 
 
1
,

 
 
2
9
8
7
,

 
 
1
8
4
,

 
 
6
6
1
,

 
 
1
2
4
9
7
,

 
 
1
0
,

 
 
1
,

 
 
1
3
9
4
,

 
 
6
0
2
,

 
 
1
7
,

 
 
2
0
1
,

 
 
2
4
5
2
,

 
 
6
6
1
,

 
 
8
4
2
,

 
 
2
1
,

 
 
1
5
9
7
,

 
 
6
0
7
2
4
,

 
 
1
4
8
8
2
,

 
 
3
3
,

 
 
1
5
9
7
,

 
 
8
5
0
8
,

 
 
9
8
6
0
,

 
 
1
1
,

 
 
8
4
,

 
 
8
0
3
,

 
 
1
5
,

 
 
2
,

 
 
1
1
7
,

 
 
1
7
,

 
 
5
3
,

 
 
1
1
4
9
,

 
 
6
3
,

 
 
5
8
6
5
,

 
 
8
4
2
,

 
 
1
8
9
0
,

 
 
2
4
5
2
,

 
 
4
5
,

 
 
5
8
0
3
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
6
0
7
2
5
,

 
 
5
4
2
6
6
,

 
 
6
6
3
,

 
 
1
,

 
 
9
1
3
,

 
 
3
7
7
,

 
 
5
3
,

 
 
1
0
8
,

 
 
2
,

 
 
3
1
7
,

 
 
2
1
,

 
 
1
,

 
 
1
0
6
8
,

 
 
8
,

 
 
2
0
6
5
2
,

 
 
5
9
,

 
 
1
2
2
,

 
 
4
3
6
1
,

 
 
2
4
5
2
,

 
 
4
8
,

 
 
1
6
0
3
9
5
,

 
 
1
0
2
8
5
,

 
 
5
9
7
2
,

 
 
1
6
0
3
9
6
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
8
3
6
,

 
 
2
0
6
5
1
,

 
 
7
9
2
7
,

 
 
1
2
,

 
 
4
,

 
 
6
0
7
2
5
,

 
 
6
2
5
,

 
 
9
8
6
,

 
 
2
4
5
2
,

 
 
4
5
,

 
 
3
4
,

 
 
1
6
8
0
,

 
 
3
6
,

 
 
1
1
,

 
 
4
3
,

 
 
7
5
4
,

 
 
9
,

 
 
6
,

 
 
8
4
6
0
,

 
 
2
0
,

 
 
2
7
3
,

 
 
1
,

 
 
2
0
6
5
1
,

 
 
1
4
6
9
,

 
 
3
,

 
 
2
2
7
5
,

 
 
4
0
2
,

 
 
1
4
6
9
,

 
 
3
,

 
 
1
,

 
 
1
8
7
1
2
,

 
 
1
4
6
9
,

 
 
8
,

 
 
1
,

 
 
3
5
1
2
,

 
 
2
6
8
2
,

 
 
2
,

 
 
1
,

 
 
2
4
9
,

 
 
1
9
5
1
,

 
 
1
2
5
,

 
 
1
,

 
 
2
0
6
5
1
,

 
 
1
4
6
9
,

 
 
8
,

 
 
4
6
2
,

 
 
9
3
,

 
 
2
2
7
5
,

 
 
4
0
2
,

 
 
1
,

 
 
1
8
7
1
2
,

 
 
1
4
6
9
,

 
 
3
9
,

 
 
1
6
,

 
 
2
1
6
5
,

 
 
2
1
,

 
 
5
8
6
5
,

 
 
8
4
2
,

 
 
1
8
9
0
,

 
 
2
4
5
2
,

 
 
2
,

 
 
3
9
9
,

 
 
1
6
3
8
3
,

 
 
1
3
,

 
 
1
,

 
 
1
7
0
6
,

 
 
2
,

 
 
1
,

 
 
5
7
6
,

 
 
3
8
6
,

 
 
1
,

 
 
3
3
5
1
,

 
 
1
7
0
6
,

 
 
3
,

 
 
1
,

 
 
4
5
5
7
,

 
 
7
,

 
 
6
0
7
2
5
,

 
 
1
2
3
8
,

 
 
1
2
9
1
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
1
2
9
0
,

 
 
8
,

 
 
2
6
0
4
,

 
 
1
2
4
9
7
,

 
 
5
3
,

 
 
1
9
,

 
 
1
2
2
7
8
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
3
6
7
6
,

 
 
6
2
5
,

 
 
2
5
9
1
9
,

 
 
9
,

 
 
4
5
,

 
 
1
0
7
2
,

 
 
5
4
2
6
7
,

 
 
1
3
2
6
,

 
 
1
0
3
5
5
,

 
 
3
5
1
3
,

 
 
7
6
7
0
,

 
 
2
,

 
 
1
6
,

 
 
3
5
9
6
,

 
 
2
1
,

 
 
2
7
6
7
3
,

 
 
1
1
5
6
0
,

 
 
8
3
6
,

 
 
2
0
6
5
1
,

 
 
7
6
7
0
,

 
 
2
,

 
 
4
9
8
,

 
 
4
,

 
 
1
9
8
3
,

 
 
3
,

 
 
1
3
7
6
,

 
 
4
9
4
0
4
,

 
 
3
1
,

 
 
1
,

 
 
3
5
8
1
,

 
 
3
,

 
 
1
,

 
 
1
1
8
7
,

 
 
1
3
5
,

 
 
1
1
8
7
,

 
 
8
0
7
0
,

 
 
1
2
,

 
 
5
8
,

 
 
9
3
,

 
 
4
7
,

 
 
6
0
7
2
5
,

 
 
4
2
7
1
,

 
 
1
2
9
0
,

 
 
5
3
,

 
 
1
9
,

 
 
2
2
2
4
,

 
 
4
,

 
 
1
8
6
1
,

 
 
1
7
3
4
,

 
 
2
0
9
,

 
 
9
8
6
,

 
 
2
5
,

 
 
1
3
9
4
,

 
 
3
5
3
,

 
 
7
6
7
0
,

 
 
5
3
,

 
 
1
2
2
0
,

 
 
9
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
6
0
7
2
5
,

 
 
4
2
7
1
,

 
 
3
3
4
5
,

 
 
4
5
,

 
 
9
8
4
,

 
 
2
9
9
9
,

 
 
2
6
0
4
,

 
 
1
2
4
9
7
,

 
 
8
0
,

 
 
1
0
2
2
5
,

 
 
2
,

 
 
1
8
5
5
,

 
 
1
8
6
1
,

 
 
1
6
0
2
,

 
 
1
,

 
 
1
9
5
1
,

 
 
1
8
,

 
 
5
7
4
,

 
 
3
9
6
3
7
,

 
 
5
,

 
 
1
9
,

 
 
1
,

 
 
1
8
4
2
,

 
 
3
,

 
 
1
1
9
4
9
,

 
 
6
9
6
1
,

 
 
1
,

 
 
2
8
5
8
,

 
 
3
,

 
 
1
1
8
7
,

 
 
2
,

 
 
8
0
7
0
,

 
 
8
3
6
,

 
 
1
0
3
3
,

 
 
4
5
6
,

 
 
2
6
,

 
 
1
,

 
 
2
0
6
5
0
,

 
 
8
,

 
 
1
4
,

 
 
8
6
4
6
,

 
 
2
1
,

 
 
6
1
,

 
 
9
7
4
4
,

 
 
2
0
6
5
1
,

 
 
3
3
4
5
,

 
 
5
,

 
 
4
,

 
 
2
1
0
4
,

 
 
9
0
9
4
,

 
 
5
7
6
,

 
 
1
5
,

 
 
1
,

 
 
1
0
6
4
7
4
,

 
 
3
,

 
 
8
6
4
7
,

 
 
3
7
3
7
5
,

 
 
2
1
,

 
 
5
4
2
6
7
,

 
 
8
2
0
7
,

 
 
5
2
0
0
,

 
 
9
,

 
 
1
0
,

 
 
4
3
6
,

 
 
1
,

 
 
2
8
1
,

 
 
1
1
5
6
0
,

 
 
2
0
6
5
1
,

 
 
5
4
2
6
8
,

 
 
1
2
9
0
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
4
7
,

 
 
8
6
4
6
,

 
 
2
1
,

 
 
1
,

 
 
1
1
5
6
0
,

 
 
2
0
6
5
1
,

 
 
3
3
4
5
,

 
 
1
,

 
 
5
1
0
,

 
 
5
8
2
,

 
 
8
,

 
 
5
4
2
6
8
,

 
 
1
0
,

 
 
3
7
2
9
,

 
 
6
9
7
5
4
,

 
 
7
7
4
,

 
 
1
,

 
 
1
6
0
3
9
7
,

 
 
1
6
0
3
9
8
,

 
 
1
7
,

 
 
4
,

 
 
1
7
3
4
,

 
 
2
,

 
 
1
,

 
 
2
5
9
2
0
,

 
 
3
2
9
,

 
 
1
,

 
 
3
7
3
7
6
,

 
 
1
1
7
4
1
,

 
 
1
1
8
4
2
,

 
 
3
,

 
 
4
,

 
 
5
4
2
6
7
,

 
 
9
9
2
6
,

 
 
5
,

 
 
1
,

 
 
1
0
8
8
4
,

 
 
1
1
8
4
2
,

 
 
3
,

 
 
8
3
6
,

 
 
5
4
2
6
6
,

 
 
1
4
4
,

 
 
1
,

 
 
1
0
8
8
4
,

 
 
2
2
7
9
,

 
 
3
,

 
 
1
,

 
 
8
3
6
,

 
 
2
0
6
5
1
,

 
 
2
3
1
6
0
,

 
 
2
1
,

 
 
4
9
2
6
,

 
 
1
6
0
3
9
9
]
,

 
[
9
4
,

 
 
1
6
0
0
,

 
 
7
3
,

 
 
9
4
,

 
 
1
6
0
4
0
0
,

 
 
7
3
,

 
 
2
8
2
,

 
 
4
,

 
 
3
0
8
9
,

 
 
9
,

 
 
6
,

 
 
1
6
9
4
,

 
 
2
0
4
,

 
 
3
2
2
,

 
 
9
4
,

 
 
6
7
,

 
 
7
3
,

 
 
9
4
,

 
 
1
6
0
0
,

 
 
7
3
,

 
 
7
2
,

 
 
1
6
0
0
,

 
 
7
3
,

 
 
1
4
3
,

 
 
8
9
]
,

 
[
1
8
,

 
 
6
,

 
 
3
1
5
7
,

 
 
3
7
,

 
 
1
2
,

 
 
6
9
3
7
,

 
 
1
9
4
0
,

 
 
7
,

 
 
7
0
,

 
 
1
0
,

 
 
2
0
,

 
 
5
4
6
,

 
 
7
1
,

 
 
3
7
1
,

 
 
5
2
3
,

 
 
2
,

 
 
3
7
6
6
,

 
 
2
0
,

 
 
1
1
0
,

 
 
3
3
0
,

 
 
4
,

 
 
1
3
8
,

 
 
5
,

 
 
2
2
3
3
,

 
 
9
8
6
1
,

 
 
6
,

 
 
1
0
8
,

 
 
2
6
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
1
8
6
3
]
,

 
[
9
5
,

 
 
1
0
5
0
4
,

 
 
2
4
,

 
 
5
8
,

 
 
9
3
,

 
 
3
6
7
,

 
 
7
2
2
2
,

 
 
1
2
,

 
 
7
2
,

 
 
5
5
2
9
,

 
 
1
,

 
 
6
9
1
,

 
 
3
,

 
 
2
9
4
6
,

 
 
6
2
0
,

 
 
4
7
3
,

 
 
1
1
6
1
,

 
 
6
2
0
,

 
 
2
7
2
,

 
 
6
9
1
,

 
 
2
6
,

 
 
7
1
,

 
 
3
0
2
1
,

 
 
1
6
5
,

 
 
9
2
8
,

 
 
7
5
2
,

 
 
3
,

 
 
1
,

 
 
3
5
6
2
,

 
 
6
2
0
,

 
 
1
8
,

 
 
8
2
8
,

 
 
5
5
0
,

 
 
1
6
6
5
,

 
 
2
6
,

 
 
5
3
,

 
 
5
9
,

 
 
1
9
,

 
 
4
,

 
 
6
1
8
,

 
 
2
3
,

 
 
1
5
,

 
 
2
9
4
6
,

 
 
3
6
,

 
 
7
,

 
 
6
5
0
,

 
 
2
3
1
,

 
 
1
9
,

 
 
2
,

 
 
3
9
4
,

 
 
1
,

 
 
3
4
3
,

 
 
1
1
3
7
9
,

 
 
2
8
1
,

 
 
3
1
8
4
,

 
 
2
0
3
,

 
 
2
6
1
,

 
 
1
1
0
,

 
 
2
5
,

 
 
2
1
9
,

 
 
1
,

 
 
2
7
2
,

 
 
1
2
1
,

 
 
2
1
3
1
,

 
 
4
8
,

 
 
6
,

 
 
1
2
9
3
,

 
 
1
0
,

 
 
1
,

 
 
3
6
9
3
,

 
 
7
2
,

 
 
2
0
9
,

 
 
1
,

 
 
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
1
4
4
,

 
 
7
1
,

 
 
8
7
0
,

 
 
2
0
8
,

 
 
1
,

 
 
1
2
3
,

 
 
8
,

 
 
1
3
3
,

 
 
1
0
,

 
 
2
7
,

 
 
2
3
,

 
 
9
5
,

 
 
1
2
7
]
,

 
[
2
3
1
3
,
 
8
4
,
 
2
3
1
,
 
3
0
9
,
 
4
9
2
7
,
 
2
0
,
 
4
5
4
,
 
9
5
]
,

 
[
3
0
1
,

 
 
1
7
4
6
,

 
 
3
,

 
 
2
2
7
,

 
 
1
7
1
,

 
 
7
1
8
,

 
 
3
0
,

 
 
5
3
6
,

 
 
8
4
7
,

 
 
1
1
8
,

 
 
3
6
2
,

 
 
5
,

 
 
1
7
9
4
,

 
 
1
0
,

 
 
4
,

 
 
1
2
7
3
,

 
 
1
1
8
,

 
 
2
,

 
 
5
4
9
]
,

 
[
2
9
5
6
,
 
1
2
0
6
7
,
 
8
,
 
6
0
5
,
 
4
,
 
1
6
0
4
0
1
,
 
5
2
,
 
2
8
0
5
,
 
2
7
,
 
5
0
2
0
,
 
7
3
,
 
6
8
,
 
3
4
0
]
,

 
[
1
1
2
4
,

 
 
3
7
9
,

 
 
1
5
0
5
,

 
 
7
2
,

 
 
2
8
0
,

 
 
2
,

 
 
1
1
7
,

 
 
1
3
,

 
 
2
6
,

 
 
7
,

 
 
1
9
,

 
 
2
,

 
 
1
6
3
5
,

 
 
1
3
,

 
 
8
1
7
,

 
 
6
2
7
5
,

 
 
1
,

 
 
4
3
0
,

 
 
6
6
4
,

 
 
6
7
8
,

 
 
9
,

 
 
1
3
7
3
,

 
 
7
3
,

 
 
1
0
,

 
 
1
3
,

 
 
8
1
7
,

 
 
8
0
8
,

 
 
1
1
2
4
,

 
 
2
8
9
9
,

 
 
1
9
,

 
 
1
4
,

 
 
5
7
,

 
 
3
4
7
9
,

 
 
1
7
,

 
 
2
8
3
,

 
 
5
2
,

 
 
4
2
,

 
 
1
6
7
,

 
 
1
5
0
,

 
 
3
7
,

 
 
5
2
,

 
 
8
1
7
,

 
 
1
1
3
,

 
 
5
1
4
,

 
 
5
6
,

 
 
1
6
,

 
 
8
0
6
,

 
 
1
,

 
 
1
7
9
,

 
 
3
9
0
,

 
 
7
7
9
,

 
 
4
9
5
9
,

 
 
1
9
6
6
,

 
 
6
2
0
,

 
 
6
1
9
4
,

 
 
2
5
1
1
,

 
 
5
,

 
 
1
3
8
4
,

 
 
1
0
5
,

 
 
1
1
6
,

 
 
1
8
,

 
 
1
0
2
,

 
 
1
4
1
7
0
,

 
 
1
0
,

 
 
6
9
7
5
5
,

 
 
6
6
,

 
 
3
9
6
3
8
,

 
 
5
,

 
 
1
3
8
4
,

 
 
1
0
5
,

 
 
5
6
,

 
 
1
6
,

 
 
6
9
0
8
,

 
 
1
3
5
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
1
2
7
,

 
 
5
0
,

 
 
1
4
7
,

 
 
1
4
8
,

 
 
1
1
3
,

 
 
1
9
8
0
8
,

 
 
5
,

 
 
8
8
2
,

 
 
1
1
2
,

 
 
2
4
9
,

 
 
8
4
,

 
 
2
1
0
7
2
,

 
 
1
1
,

 
 
1
2
,

 
 
1
1
2
4
,

 
 
5
9
8
,

 
 
1
9
7
,

 
 
7
,

 
 
1
9
,

 
 
3
5
7
,

 
 
5
9
4
7
,

 
 
1
3
,

 
 
2
3
,

 
 
1
7
,

 
 
5
0
7
,

 
 
5
9
8
,

 
 
1
7
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
0
9
2
,

 
 
5
0
7
,

 
 
5
9
8
,

 
 
4
3
4
,

 
 
3
0
,

 
 
6
4
7
]
,

 
[
3
0
,

 
 
7
4
6
,

 
 
4
3
4
7
,

 
 
1
1
9
,

 
 
6
,

 
 
3
3
2
,

 
 
7
,

 
 
2
4
,

 
 
1
0
8
6
,

 
 
7
1
8
,

 
 
1
,

 
 
2
0
6
,

 
 
7
,

 
 
6
7
0
,

 
 
1
5
,

 
 
2
0
,

 
 
4
9
4
0
5
,

 
 
1
5
2
5
8
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
5
6
,

 
 
3
0
,

 
 
2
7
9
4
,

 
 
1
2
,

 
 
2
0
,

 
 
9
5
7
0
,

 
 
1
1
5
1
,

 
 
2
,

 
 
3
5
6
,

 
 
3
0
,

 
 
2
9
,

 
 
6
,

 
 
1
7
4
4
,

 
 
1
8
,

 
 
1
5
3
,

 
 
4
,

 
 
5
8
9
,

 
 
3
5
3
3
,

 
 
4
4
8
6
,

 
 
6
7
,

 
 
2
8
5
1
,

 
 
1
5
7
,

 
 
1
2
,

 
 
4
,

 
 
4
3
7
,

 
 
5
,

 
 
6
5
,

 
 
3
5
,

 
 
3
8
,

 
 
2
0
,

 
 
3
0
0
,

 
 
4
2
,

 
 
6
6
1
,

 
 
2
0
7
,

 
 
9
,

 
 
2
3
9
,

 
 
1
5
9
,

 
 
2
5
0
,

 
 
9
0
,

 
 
1
1
,

 
 
4
9
9
0
,

 
 
6
9
,

 
 
1
7
,

 
 
7
,

 
 
8
1
,

 
 
1
3
2
,

 
 
5
5
1
,

 
 
7
4
9
,

 
 
2
0
,

 
 
3
0
0
,

 
 
8
,

 
 
4
,

 
 
3
2
1
4
4
,

 
 
3
,

 
 
3
6
8
9
,

 
 
1
0
,

 
 
1
4
2
0
,

 
 
3
,

 
 
1
,

 
 
1
0
0
5
,

 
 
1
0
2
2
6
,

 
 
2
,

 
 
3
0
3
8
,

 
 
7
3
8
5
,

 
 
2
0
,

 
 
1
8
8
9
,

 
 
2
,

 
 
9
4
,

 
 
2
4
8
8
,

 
 
3
,

 
 
3
7
,

 
 
1
8
,

 
 
1
3
0
7
5
,

 
 
3
3
,

 
 
2
2
1
,

 
 
6
,

 
 
1
8
,

 
 
2
4
7
0
,

 
 
3
5
3
3
,

 
 
1
,

 
 
5
2
2
,

 
 
3
,

 
 
2
7
0
3
,

 
 
6
,

 
 
5
9
,

 
 
1
0
8
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
2
0
3
4
,

 
 
1
0
1
,

 
 
1
5
5
,

 
 
3
6
6
,

 
 
1
6
0
4
0
2
,

 
 
1
6
0
4
0
3
,

 
 
5
0
5
,

 
 
2
8
2
,

 
 
4
7
,

 
 
3
1
,

 
 
3
7
,

 
 
6
,

 
 
3
9
,

 
 
1
1
8
,

 
 
1
1
8
6
,

 
 
5
,

 
 
3
5
6
,

 
 
3
0
,

 
 
2
5
7
7
,

 
 
3
1
,

 
 
2
8
,

 
 
2
3
1
,

 
 
4
9
,

 
 
9
7
,

 
 
1
8
3
,

 
 
4
7
,

 
 
5
,

 
 
2
6
9
,

 
 
1
4
3
,

 
 
1
5
7
,

 
 
2
,

 
 
1
6
0
4
0
4
,

 
 
4
6
,

 
 
2
9
,

 
 
5
,

 
 
2
0
2
8
,

 
 
1
,

 
 
5
2
2
,

 
 
1
9
2
,

 
 
3
,

 
 
6
,

 
 
7
4
,

 
 
1
0
3
,

 
 
6
,

 
 
5
4
2
6
9
,

 
 
1
,

 
 
7
1
3
9
,

 
 
3
,

 
 
2
7
,

 
 
2
9
2
5
,

 
 
1
9
0
4
0
,

 
 
4
1
2
,

 
 
3
4
3
,

 
 
1
2
4
2
,

 
 
1
6
8
9
2
,

 
 
2
6
8
,

 
 
2
,

 
 
9
7
,

 
 
4
,

 
 
1
0
9
,

 
 
1
2
,

 
 
6
8
,

 
 
7
4
6
,

 
 
1
0
0
,

 
 
9
,

 
 
9
7
,

 
 
6
,

 
 
4
8
2
,

 
 
2
4
0
,

 
 
2
1
,

 
 
7
5
,

 
 
6
9
,

 
 
1
6
4
,

 
 
2
7
,

 
 
1
5
2
5
9
,

 
 
5
2
8
,

 
 
3
4
3
,

 
 
4
0
0
,

 
 
1
0
,

 
 
4
,

 
 
9
3
1
,

 
 
4
5
3
,

 
 
7
9
3
,

 
 
9
0
,

 
 
6
,

 
 
3
2
5
1
,

 
 
9
,

 
 
3
7
5
,

 
 
1
5
8
,

 
 
3
3
1
,

 
 
2
4
,

 
 
1
6
5
,

 
 
2
,

 
 
7
1
1
,

 
 
6
8
,

 
 
7
1
3
9
,

 
 
5
,

 
 
6
,

 
 
8
6
,

 
 
2
6
8
,

 
 
2
,

 
 
1
3
0
8
,

 
 
1
5
4
,

 
 
1
5
7
,

 
 
3
6
,

 
 
1
2
6
1
,

 
 
3
3
1
,

 
 
1
0
3
,

 
 
4
9
3
7
,

 
 
4
8
,

 
 
6
,

 
 
2
9
6
,

 
 
6
,

 
 
9
0
,

 
 
7
,

 
 
5
9
,

 
 
9
7
,

 
 
3
3
7
9
,

 
 
1
8
1
3
,

 
 
3
6
,

 
 
7
,

 
 
6
2
4
,

 
 
1
6
,

 
 
3
5
8
,

 
 
2
1
5
,

 
 
6
7
7
,

 
 
1
,

 
 
1
5
4
2
,

 
 
3
,

 
 
6
9
7
5
6
,

 
 
2
5
5
6
,

 
 
2
0
2
0
0
,

 
 
2
5
,

 
 
6
9
7
5
6
,

 
 
9
6
4
,

 
 
1
,

 
 
1
0
1
4
,

 
 
3
1
,

 
 
5
5
6
,

 
 
2
0
,

 
 
1
6
3
8
4
,

 
 
1
6
0
4
0
5
,

 
 
2
6
,

 
 
7
,

 
 
4
5
,

 
 
1
1
7
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
8
4
7
,

 
 
1
1
5
0
,

 
 
3
,

 
 
4
,

 
 
3
7
8
,

 
 
7
3
5
,

 
 
2
4
0
,

 
 
5
8
9
,

 
 
7
0
1
4
,

 
 
3
6
,

 
 
1
1
8
,

 
 
9
6
4
,

 
 
6
0
,

 
 
5
8
,

 
 
1
8
4
7
,

 
 
5
,

 
 
1
5
4
6
6
,

 
 
2
0
,

 
 
5
4
2
7
0
,

 
 
6
,

 
 
8
0
6
9
,

 
 
5
4
2
7
1
,

 
 
7
9
6
7
,

 
 
4
8
9
7
,

 
 
6
7
,

 
 
6
,

 
 
5
6
,

 
 
3
4
,

 
 
1
6
3
,

 
 
5
7
3
,

 
 
1
2
,

 
 
2
2
5
,

 
 
3
5
2
,

 
 
1
1
8
,

 
 
8
9
2
8
,

 
 
4
,

 
 
8
9
7
,

 
 
3
,

 
 
1
0
8
8
5
,

 
 
7
5
5
9
,

 
 
2
6
7
3
6
,

 
 
3
1
,

 
 
2
0
,

 
 
1
1
6
1
,

 
 
7
8
4
6
,

 
 
3
7
5
2
,

 
 
5
,

 
 
2
1
4
9
,

 
 
1
9
2
,

 
 
1
2
,

 
 
4
,

 
 
2
3
5
,

 
 
8
0
6
,

 
 
9
3
,

 
 
4
2
0
,

 
 
1
5
4
3
,

 
 
3
3
4
0
,

 
 
2
6
1
0
,

 
 
2
7
,

 
 
8
4
7
,

 
 
1
8
5
,

 
 
2
0
1
,

 
 
9
3
,

 
 
6
,

 
 
1
0
,

 
 
3
0
6
,

 
 
1
1
0
]
,

 
[
7
8
,

 
 
2
2
9
,

 
 
6
,

 
 
2
2
0
,

 
 
7
4
,

 
 
6
8
9
,

 
 
3
9
6
3
9
,

 
 
8
,

 
 
9
0
,

 
 
6
,

 
 
6
3
,

 
 
1
5
4
,

 
 
1
5
,

 
 
6
8
,

 
 
5
2
9
,

 
 
1
9
0
4
1
,

 
 
1
5
,

 
 
1
,

 
 
3
3
4
0
,

 
 
3
1
4
,

 
 
2
1
,

 
 
4
2
4
0
,

 
 
2
2
6
2
3
,

 
 
5
2
,

 
 
5
2
6
,

 
 
1
0
7
6
,

 
 
3
7
9
0
,

 
 
2
2
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
2
0
4
,

 
 
1
0
8
5
,

 
 
1
5
,

 
 
1
1
,

 
 
3
6
7
,

 
 
1
1
7
,

 
 
9
,

 
 
3
9
6
3
9
,

 
 
1
9
4
0
4
,

 
 
8
,

 
 
4
,

 
 
2
2
9
,

 
 
2
4
3
0
,

 
 
2
6
2
0
,

 
 
1
2
,

 
 
1
,

 
 
7
1
0
,

 
 
9
3
1
,

 
 
5
5
7
9
,

 
 
2
6
7
1
,

 
 
2
4
6
,

 
 
2
0
,

 
 
4
7
7
5
,

 
 
5
7
1
8
,

 
 
1
9
2
,

 
 
3
,

 
 
3
0
,

 
 
2
5
5
,

 
 
2
0
6
,

 
 
7
1
6
9
,

 
 
6
,

 
 
2
5
6
,

 
 
1
1
,

 
 
7
,

 
 
4
5
,

 
 
6
0
6
6
,

 
 
1
1
]
,

 
[
1
1
5
6
1
,

 
 
1
3
,

 
 
2
9
,

 
 
4
3
,

 
 
6
6
,

 
 
2
1
5
5
,

 
 
1
1
3
,

 
 
9
4
5
4
,

 
 
3
8
5
,

 
 
6
,

 
 
4
8
,

 
 
1
1
,

 
 
2
5
,

 
 
1
4
,

 
 
6
0
6
7
,

 
 
1
8
,

 
 
1
3
2
0
,

 
 
1
5
5
]
,

 
[
4
,

 
 
6
2
7
6
,

 
 
4
8
,

 
 
4
,

 
 
2
7
5
8
,

 
 
2
5
,

 
 
4
,

 
 
9
2
5
2
,

 
 
8
,

 
 
1
4
,

 
 
1
7
8
7
,

 
 
3
2
,

 
 
1
1
6
5
,

 
 
2
1
7
0
,

 
 
1
2
8
,

 
 
4
8
,

 
 
4
,

 
 
6
9
9
,

 
 
4
1
2
,

 
 
3
4
3
,

 
 
1
2
6
4
,

 
 
6
2
,

 
 
8
,

 
 
7
7
0
4
,

 
 
2
,

 
 
4
,

 
 
1
6
4
0
,

 
 
6
3
2
4
,

 
 
2
6
,

 
 
4
2
,

 
 
1
9
9
,

 
 
9
9
,

 
 
4
8
3
,

 
 
8
,

 
 
1
5
3
,

 
 
1
6
1
4
,

 
 
4
,

 
 
2
2
2
,

 
 
6
2
,

 
 
8
,

 
 
2
0
3
,

 
 
6
3
2
4
,

 
 
7
7
0
4
,

 
 
2
0
6
5
3
,

 
 
3
2
,

 
 
1
,

 
 
1
3
9
,

 
 
4
8
3
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
,

 
 
2
2
5
0
,

 
 
4
8
3
,

 
 
8
,

 
 
6
2
7
6
]
,

 
[
4
3
9
,
 
4
6
,
 
3
0
5
5
,
 
1
0
6
4
1
,
 
8
4
6
1
]
,

 
[
1
0
1
9
,

 
 
3
1
3
8
,

 
 
1
7
8
,

 
 
1
0
3
,

 
 
6
,

 
 
5
0
,

 
 
1
7
1
,

 
 
8
5
5
5
,

 
 
1
,

 
 
4
7
8
,

 
 
1
0
1
9
,

 
 
3
1
3
8
,

 
 
1
5
,

 
 
2
8
1
,

 
 
2
6
3
5
,

 
 
2
2
6
8
,

 
 
8
0
9
,

 
 
1
0
,

 
 
1
,

 
 
7
2
9
,

 
 
1
3
0
6
,

 
 
1
3
,

 
 
8
,

 
 
2
4
7
,

 
 
5
3
,

 
 
7
2
9
,

 
 
2
0
8
7
,

 
 
2
2
6
8
,

 
 
2
3
8
,

 
 
1
4
,

 
 
3
1
3
8
,

 
 
1
9
,

 
 
1
0
8
6
,

 
 
3
3
0
,

 
 
6
9
7
5
7
,

 
 
5
,

 
 
9
,

 
 
3
2
3
,

 
 
2
,

 
 
1
7
1
,

 
 
5
3
,

 
 
1
8
,

 
 
1
4
,

 
 
3
1
3
8
,

 
 
5
3
,

 
 
1
9
,

 
 
1
7
5
,

 
 
1
7
0
,

 
 
2
8
6
7
,

 
 
5
,

 
 
5
3
,

 
 
8
0
7
,

 
 
1
6
,

 
 
2
3
3
3
,

 
 
2
,

 
 
1
6
,

 
 
3
1
6
,

 
 
1
0
1
9
,

 
 
3
1
3
8
,

 
 
2
2
,

 
 
4
,

 
 
1
0
1
9
,

 
 
1
3
0
3
,

 
 
8
,

 
 
9
0
8
,

 
 
1
0
,

 
 
1
,

 
 
7
2
9
,

 
 
1
3
0
6
,

 
 
5
6
,

 
 
5
2
,

 
 
1
6
,

 
 
3
1
6
,

 
 
4
,

 
 
1
0
1
9
,

 
 
1
9
0
9
,

 
 
6
9
,

 
 
3
,

 
 
9
,

 
 
2
1
2
,

 
 
7
5
7
,

 
 
5
0
,

 
 
2
7
5
,

 
 
5
1
,

 
 
1
8
,

 
 
1
0
0
3
8
,

 
 
2
2
6
8
,

 
 
7
,

 
 
2
6
5
,

 
 
3
,

 
 
6
1
7
7
,

 
 
3
4
1
8
,

 
 
5
,

 
 
1
3
2
,

 
 
3
,

 
 
8
8
,

 
 
9
8
2
,

 
 
1
0
0
9
7
,

 
 
2
3
8
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
8
8
,

 
 
1
8
,

 
 
8
9
2
9
,

 
 
1
1
,

 
 
1
7
,

 
 
1
5
8
,

 
 
6
2
,

 
 
3
4
9
6
,

 
 
1
0
0
9
7
,

 
 
6
,

 
 
5
6
,

 
 
8
7
6
,

 
 
1
3
,

 
 
1
6
6
,

 
 
5
,

 
 
1
4
,

 
 
1
7
7
4
9
,

 
 
1
8
0
6
,

 
 
6
2
,

 
 
1
0
8
,

 
 
2
,

 
 
4
5
8
,

 
 
5
4
5
,

 
 
3
1
3
8
,

 
 
4
9
,

 
 
6
9
,

 
 
7
8
5
,

 
 
1
0
,

 
 
1
,

 
 
7
2
9
,

 
 
1
3
0
6
,

 
 
5
3
,

 
 
1
8
,

 
 
1
4
,

 
 
2
5
0
9
,

 
 
4
7
0
,

 
 
2
,

 
 
1
,

 
 
3
1
3
8
,

 
 
3
1
,

 
 
1
6
0
4
0
6
,

 
 
5
3
,

 
 
1
9
,

 
 
1
7
5
,

 
 
1
7
0
,

 
 
2
8
6
7
,

 
 
5
0
,

 
 
1
7
1
,

 
 
6
0
6
8
,

 
 
9
2
9
,

 
 
1
9
1
,

 
 
6
0
,

 
 
4
8
8
5
,

 
 
1
9
0
9
,

 
 
2
8
6
7
,

 
 
1
8
5
,

 
 
1
0
1
6
1
,

 
 
4
6
,

 
 
6
4
8
,

 
 
8
7
8
,

 
 
1
3
6
1
,

 
 
2
8
0
4
,

 
 
7
1
0
,

 
 
2
1
6
]
,

 
[
1
9
0
4
2
,

 
 
1
6
3
2
,

 
 
5
0
0
5
,

 
 
2
4
9
2
,

 
 
2
8
6
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
1
0
9
,

 
 
1
2
,

 
 
9
,

 
 
1
1
9
1
,

 
 
7
,

 
 
3
4
,

 
 
7
0
,

 
 
4
1
,

 
 
8
,

 
 
2
3
7
,

 
 
2
7
,

 
 
1
1
9
1
,

 
 
2
1
,

 
 
9
,

 
 
1
0
9
,

 
 
2
6
,

 
 
5
0
0
5
,

 
 
2
8
6
,

 
 
7
1
,

 
 
1
1
0
4
7
,

 
 
2
8
6
,

 
 
5
9
]
,

 
[
4
0
,

 
 
3
,

 
 
3
0
,

 
 
1
4
0
,

 
 
1
8
,

 
 
9
8
,

 
 
3
2
3
4
,

 
 
4
8
,

 
 
6
,

 
 
6
2
,

 
 
3
9
8
,

 
 
9
8
,

 
 
1
4
0
,

 
 
6
9
,

 
 
1
6
4
,

 
 
1
5
5
,

 
 
3
0
1
,

 
 
2
,

 
 
2
7
5
,

 
 
7
4
,

 
 
2
,

 
 
3
5
0
,

 
 
1
0
1
,

 
 
5
,

 
 
8
4
,

 
 
3
9
8
,

 
 
6
1
,

 
 
1
4
0
,

 
 
4
9
,

 
 
6
9
,

 
 
5
0
5
,

 
 
1
0
7
8
,

 
 
2
,

 
 
2
5
3
0
,

 
 
4
,

 
 
9
6
8
9
,

 
 
9
2
9
8
,

 
 
1
8
,

 
 
1
,

 
 
2
4
9
,

 
 
3
5
2
,

 
 
4
7
,

 
 
3
0
3
,

 
 
8
8
8
,

 
 
3
3
4
1
,

 
 
1
,

 
 
2
3
6
9
,

 
 
6
,

 
 
9
0
,

 
 
2
,

 
 
4
,

 
 
5
8
5
0
,

 
 
4
9
3
,

 
 
5
8
5
1
,

 
 
7
0
1
5
,

 
 
6
8
0
8
,

 
 
5
8
0
4
]
,

 
[
4
2
3
3
9
,

 
 
4
6
0
2
,

 
 
1
5
,

 
 
6
,

 
 
7
6
7
,

 
 
9
1
,

 
 
7
3
2
1
,

 
 
3
3
,

 
 
4
0
,

 
 
2
2
,

 
 
6
,

 
 
5
9
,

 
 
7
9
,

 
 
1
3
9
0
7
,

 
 
6
,

 
 
5
9
,

 
 
9
4
,

 
 
3
6
8
,

 
 
6
0
7
2
6
]
,

 
[
7
,

 
 
7
7
1
,

 
 
4
1
,

 
 
3
1
5
,

 
 
1
,

 
 
1
3
9
,

 
 
8
5
,

 
 
5
2
,

 
 
9
0
,

 
 
5
,

 
 
9
,

 
 
5
5
1
,

 
 
2
4
,

 
 
1
4
,

 
 
1
,

 
 
1
9
8
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
5
1
9
,

 
 
1
5
,

 
 
5
1
,

 
 
2
3
4
1
,

 
 
7
0
3
,

 
 
1
0
1
4
,

 
 
3
1
,

 
 
1
1
1
,

 
 
4
,

 
 
1
4
8
1
,

 
 
1
1
0
3
]
,

 
[
4
1
,

 
 
2
4
5
,

 
 
1
6
,

 
 
6
0
,

 
 
4
2
6
3
,

 
 
1
7
7
5
0
,

 
 
1
0
,

 
 
2
0
,

 
 
5
5
5
5
,

 
 
1
8
,

 
 
6
,

 
 
4
6
3
,

 
 
1
,

 
 
8
4
1
7
,

 
 
6
,

 
 
7
4
2
,

 
 
1
8
,

 
 
5
5
3
,

 
 
1
2
6
,

 
 
3
9
7
,

 
 
3
7
,

 
 
2
1
1
,

 
 
2
8
0
,

 
 
1
2
,

 
 
6
,

 
 
5
9
,

 
 
3
4
9
,

 
 
1
1
8
,

 
 
2
,

 
 
6
4
9
,

 
 
4
8
0
,

 
 
6
,

 
 
4
3
,

 
 
3
4
,

 
 
1
,

 
 
9
2
4
,

 
 
6
0
4
3
,

 
 
3
6
6
]
,

 
[
1
6
0
4
0
7
,

 
 
6
,

 
 
1
8
,

 
 
2
6
8
,

 
 
2
,

 
 
5
9
0
7
,

 
 
6
0
7
2
7
,

 
 
7
4
,

 
 
3
9
,

 
 
6
,

 
 
1
1
7
,

 
 
9
,

 
 
1
,

 
 
2
3
4
,

 
 
3
,

 
 
6
0
7
2
7
,

 
 
1
8
,

 
 
2
5
5
4
,

 
 
6
0
7
2
7
,

 
 
8
,

 
 
2
6
8
,

 
 
2
,

 
 
4
6
8
,

 
 
9
,

 
 
4
1
,

 
 
5
6
,

 
 
1
6
,

 
 
4
4
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
1
0
,

 
 
1
,

 
 
2
8
,

 
 
5
,

 
 
5
2
,

 
 
8
,

 
 
1
4
3
]
,

 
[
1
4
3
6
,

 
 
5
2
4
,

 
 
1
7
,

 
 
1
,

 
 
2
3
,

 
 
1
8
8
8
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
1
7
2
,

 
 
2
7
3
,

 
 
1
8
2
,

 
 
1
,

 
 
1
1
3
,

 
 
2
7
3
,

 
 
4
2
7
,

 
 
2
2
,

 
 
1
3
,

 
 
2
6
7
,

 
 
8
,

 
 
2
3
2
6
,

 
 
7
,

 
 
5
9
,

 
 
5
5
,

 
 
4
6
4
,

 
 
2
1
,

 
 
1
1
,

 
 
9
1
,

 
 
6
9
2
,

 
 
2
,

 
 
1
,

 
 
5
6
1
3
,

 
 
1
6
0
4
0
8
]
,

 
[
7
,

 
 
4
3
,

 
 
6
8
5
,

 
 
2
7
,

 
 
2
5
7
9
,

 
 
3
1
,

 
 
2
1
0
,

 
 
3
,

 
 
6
,

 
 
2
6
,

 
 
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
,

 
 
8
,

 
 
2
5
0
5
,

 
 
2
2
,

 
 
1
4
,

 
 
5
0
,

 
 
5
9
,

 
 
1
5
5
0
,

 
 
3
0
,

 
 
8
5
,

 
 
5
5
,

 
 
8
0
6
,

 
 
2
1
,

 
 
1
8
8
9
,

 
 
3
3
,

 
 
2
6
8
,

 
 
2
0
0
1
,

 
 
3
0
4
,

 
 
2
0
,

 
 
2
5
,

 
 
1
2
6
1
5
,

 
 
2
3
1
1
,

 
 
2
3
1
6
1
,

 
 
2
5
8
3
,

 
 
3
7
,

 
 
2
5
,

 
 
1
6
2
5
,

 
 
3
7
,

 
 
5
5
,

 
 
8
0
6
,

 
 
3
5
,

 
 
1
3
,

 
 
2
6
7
,

 
 
5
,

 
 
7
,

 
 
1
1
4
9
,

 
 
3
1
7
,

 
 
6
,

 
 
7
5
7
,

 
 
5
,

 
 
2
3
8
9
,

 
 
2
8
7
,

 
 
6
4
,

 
 
6
2
,

 
 
1
8
9
3
,

 
 
3
0
,

 
 
1
4
3
6
4
,

 
 
7
7
9
]
,

 
[
5
1
,
 
1
8
,
 
1
4
,
 
2
9
9
,
 
3
9
4
,
 
5
1
,
 
1
8
,
 
1
6
5
3
,
 
1
0
,
 
1
,
 
2
0
8
1
]
,

 
[
3
8
5
5
,

 
 
3
6
,

 
 
3
9
6
4
0
,

 
 
1
4
9
6
,

 
 
3
9
,

 
 
2
7
6
,

 
 
5
8
,

 
 
9
3
,

 
 
4
7
,

 
 
2
2
8
,

 
 
7
,

 
 
4
5
,

 
 
2
3
1
6
2
,

 
 
6
,

 
 
1
5
,

 
 
9
,

 
 
9
5
,

 
 
2
9
4
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
3
2
,

 
 
5
2
0
1
,

 
 
4
7
3
7
,

 
 
2
9
7
1
,

 
 
5
7
3
0
,

 
 
3
,

 
 
4
4
3
,

 
 
1
1
,

 
 
3
9
,

 
 
1
,

 
 
2
7
0
,

 
 
1
4
9
6
,

 
 
5
9
3
,

 
 
3
2
2
6
,

 
 
1
5
,

 
 
1
,

 
 
5
7
1
9
,

 
 
3
,

 
 
1
,

 
 
1
4
9
6
,

 
 
2
0
0
,

 
 
2
9
7
,

 
 
4
6
,

 
 
5
8
2
,

 
 
3
7
,

 
 
4
0
,

 
 
6
,

 
 
1
0
8
,

 
 
1
1
,

 
 
3
7
4
4
,

 
 
1
5
,

 
 
1
,

 
 
7
3
2
,

 
 
3
,

 
 
1
,

 
 
3
5
3
,

 
 
8
0
,

 
 
1
0
4
,

 
 
9
1
,

 
 
1
3
3
,

 
 
1
7
,

 
 
2
,

 
 
3
8
5
,

 
 
1
0
4
,

 
 
3
8
2
4
,

 
 
2
5
,

 
 
1
4
,

 
 
1
9
3
,

 
 
7
4
,

 
 
7
,

 
 
1
6
7
,

 
 
4
4
5
1
,

 
 
5
,

 
 
2
8
6
7
,

 
 
7
,

 
 
1
9
9
,

 
 
4
4
5
,

 
 
2
5
9
1
,

 
 
5
4
,

 
 
8
,

 
 
1
,

 
 
3
2
5
,

 
 
1
8
3
8
,

 
 
7
9
1
,

 
 
1
,

 
 
2
5
9
1
,

 
 
7
9
1
,

 
 
3
,

 
 
1
,

 
 
3
5
3
,

 
 
8
,

 
 
1
,

 
 
8
8
2
5
,

 
 
1
3
3
,

 
 
6
4
1
,

 
 
1
5
,

 
 
2
8
,

 
 
1
0
,

 
 
2
5
9
1
,

 
 
6
6
7
,

 
 
1
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
1
,

 
 
1
4
4
4
,

 
 
3
,

 
 
1
5
9
1
,

 
 
2
6
,

 
 
6
,

 
 
2
3
7
,

 
 
7
0
,

 
 
9
,

 
 
7
2
,

 
 
1
8
6
,

 
 
4
6
,

 
 
1
0
,

 
 
2
5
9
1
,

 
 
6
6
7
,

 
 
1
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
1
,

 
 
1
4
4
4
,

 
 
3
,

 
 
1
5
9
1
,

 
 
4
4
,

 
 
1
1
1
,

 
 
5
4
6
,

 
 
3
6
,

 
 
2
5
9
1
,

 
 
6
6
7
,

 
 
1
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
1
5
9
1
,

 
 
2
9
4
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
3
2
,

 
 
5
2
0
1
,

 
 
2
5
9
0
,

 
 
6
8
4
8
,

 
 
6
5
9
9
,

 
 
4
1
5
,

 
 
1
4
1
8
,

 
 
1
5
9
1
,

 
 
1
7
,

 
 
1
0
,

 
 
1
5
9
1
,

 
 
1
,

 
 
2
9
7
,

 
 
1
4
0
9
,

 
 
5
6
8
,

 
 
7
3
1
,

 
 
8
,

 
 
1
,

 
 
1
4
4
4
,

 
 
3
,

 
 
1
5
9
1
,

 
 
3
4
3
9
,

 
 
1
,

 
 
1
4
5
,

 
 
1
0
,

 
 
1
3
,

 
 
1
0
2
8
6
,

 
 
2
0
2
4
,

 
 
4
6
,

 
 
1
5
9
1
,

 
 
1
4
0
9
,

 
 
5
6
8
,

 
 
1
0
9
,

 
 
8
,

 
 
1
5
9
1
,

 
 
2
9
4
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
3
2
,

 
 
5
2
0
1
,

 
 
2
5
9
0
,

 
 
6
8
4
8
,

 
 
6
5
9
9
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
2
3
5
8
,

 
 
2
1
2
6
,

 
 
1
6
0
3
,

 
 
1
6
0
4
0
9
,

 
 
2
2
4
0
,

 
 
5
9
1
,

 
 
1
2
,

 
 
6
,

 
 
6
6
,

 
 
7
,

 
 
6
3
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
2
3
5
8
,

 
 
2
1
2
6
,

 
 
1
6
0
3
,

 
 
1
6
0
4
1
0
,

 
 
2
2
4
0
,

 
 
1
7
,

 
 
6
,

 
 
9
8
2
,

 
 
2
1
0
,

 
 
2
9
4
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
3
2
,

 
 
5
2
0
1
,

 
 
4
0
3
1
,

 
 
7
4
1
7
,

 
 
9
9
1
]
,

 
[
2
0
8
,

 
 
1
,

 
 
2
0
6
5
4
,

 
 
6
0
7
2
8
,

 
 
2
8
6
,

 
 
8
5
,

 
 
1
,

 
 
3
9
2
2
,

 
 
1
0
9
,

 
 
8
,

 
 
8
5
,

 
 
3
4
0
4
,

 
 
6
,

 
 
3
9
,

 
 
1
1
8
5
,

 
 
1
4
7
,

 
 
1
3
,

 
 
7
3
,

 
 
1
5
,

 
 
1
,

 
 
6
1
,

 
 
7
4
1
,

 
 
6
0
7
2
9
,

 
 
8
3
5
2
2
,

 
 
8
,

 
 
3
6
9
,

 
 
1
,

 
 
3
9
2
2
,

 
 
1
0
9
,

 
 
6
,

 
 
3
9
,

 
 
1
4
7
,

 
 
1
3
,

 
 
7
3
,

 
 
1
7
,

 
 
1
0
1
]
,

 
[
1
5
9
,
 
2
0
,
 
8
0
7
1
,
 
5
,
 
1
6
0
4
1
1
,
 
1
0
6
4
7
5
,
 
1
6
1
6
,
 
1
5
5
,
 
1
3
5
0
,
 
1
2
,
 
6
4
]
,

 
[
1
8
5
,

 
 
3
8
,

 
 
7
2
,

 
 
4
9
1
,

 
 
3
3
0
,

 
 
1
1
,

 
 
5
2
6
,

 
 
4
8
,

 
 
5
2
,

 
 
2
4
,

 
 
4
9
,

 
 
9
1
,

 
 
2
7
,

 
 
4
0
,

 
 
3
1
5
,

 
 
5
2
2
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
2
3
8
,

 
 
7
1
,

 
 
2
4
1
,

 
 
1
5
5
,

 
 
3
6
6
,

 
 
2
3
8
,

 
 
5
2
6
,

 
 
5
8
,

 
 
4
8
,

 
 
2
7
,

 
 
6
7
4
5
,

 
 
2
,

 
 
2
2
3
4
,

 
 
8
2
9
,

 
 
1
1
7
2
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
1
3
6
3
,

 
 
6
6
,

 
 
6
6
9
]
,

 
[
1
0
,

 
 
1
,

 
 
1
3
9
,

 
 
2
3
3
1
,

 
 
8
,

 
 
1
1
,

 
 
1
2
6
,

 
 
8
3
3
,

 
 
2
,

 
 
1
0
9
,

 
 
4
0
,

 
 
1
,

 
 
1
9
1
,

 
 
3
8
6
,

 
 
6
2
,

 
 
2
5
1
8
,

 
 
1
1
,

 
 
7
8
,

 
 
1
4
,

 
 
2
5
8
,

 
 
4
9
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
3
8
6
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
2
7
,

 
 
4
2
8
,

 
 
3
8
4
,

 
 
2
6
,

 
 
2
7
,

 
 
3
8
0
8
,

 
 
4
7
,

 
 
7
,

 
 
5
9
,

 
 
6
3
,

 
 
7
8
,

 
 
3
0
6
,

 
 
5
2
8
,

 
 
1
9
1
,

 
 
3
8
6
,

 
 
5
4
,

 
 
2
5
1
8
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
0
6
9
,

 
 
1
0
9
6
4
]
,

 
[
6
0
3
,

 
 
1
1
1
2
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
6
,

 
 
2
4
5
,

 
 
1
4
,

 
 
8
7
9
,

 
 
1
3
0
7
,

 
 
7
0
6
4
,

 
 
8
0
4
,

 
 
1
6
0
,

 
 
9
,

 
 
6
3
5
,

 
 
7
6
7
1
,

 
 
8
,

 
 
1
,

 
 
1
0
3
5
6
,

 
 
7
0
6
4
,

 
 
4
,

 
 
7
,

 
 
9
,

 
 
7
7
1
,

 
 
4
5
4
9
2
,

 
 
1
5
1
,

 
 
8
0
4
,

 
 
7
8
1
3
,

 
 
7
4
4
,

 
 
1
0
6
4
7
6
,

 
 
5
9
0
8
,

 
 
9
1
9
,

 
 
2
5
4
5
]
,

 
[
1
7
8
,
 
7
,
 
8
1
,
 
1
5
7
,
 
1
2
7
,
 
2
6
2
,
 
5
8
7
,
 
1
7
1
,
 
3
7
7
2
,
 
3
0
,
 
1
4
0
,
 
2
5
,
 
3
6
2
]
,

 
[
4
5
4
9
3
,

 
 
3
,

 
 
2
7
6
7
4
,

 
 
5
4
2
7
2
,

 
 
4
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
3
7
0
,

 
 
4
2
,

 
 
5
7
,

 
 
1
7
3
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
4
5
4
9
3
,

 
 
3
,

 
 
2
7
6
7
4
,

 
 
5
4
2
7
2
,

 
 
1
8
7
8
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
4
6
,

 
 
5
7
9
,

 
 
2
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
5
9
9
,

 
 
4
0
,

 
 
4
1
4
,

 
 
1
8
,

 
 
1
3
4
7
,

 
 
2
6
,

 
 
1
3
,

 
 
2
3
,

 
 
8
7
,

 
 
1
4
,

 
 
2
9
4
8
,

 
 
5
0
8
,

 
 
4
3
4
,

 
 
1
2
,

 
 
9
7
5
,

 
 
5
,

 
 
1
,

 
 
1
1
9
,

 
 
4
5
4
,

 
 
5
6
,

 
 
5
2
0
,

 
 
7
8
,

 
 
6
3
,

 
 
6
6
,

 
 
3
8
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
5
,

 
 
5
0
8
,

 
 
1
1
9
,

 
 
2
3
0
,

 
 
6
,

 
 
8
7
,

 
 
1
5
2
9
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
3
2
,

 
 
5
3
0
,

 
 
1
,

 
 
4
5
4
,

 
 
2
6
,

 
 
5
0
,

 
 
5
2
0
,

 
 
7
8
,

 
 
6
,

 
 
7
8
9
,

 
 
2
1
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
1
0
,

 
 
2
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
2
5
,

 
 
1
5
,

 
 
1
0
4
,

 
 
4
6
,

 
 
2
9
,

 
 
6
6
,

 
 
5
0
,

 
 
4
1
1
,

 
 
1
6
8
1
,

 
 
1
,

 
 
2
3
,

 
 
2
,

 
 
4
5
9
,

 
 
1
,

 
 
4
6
4
,

 
 
1
5
9
8
,

 
 
9
6
,

 
 
2
3
8
,

 
 
5
3
0
,

 
 
1
,

 
 
1
1
9
,

 
 
4
5
4
,

 
 
4
5
,

 
 
1
5
2
9
,

 
 
1
1
9
,

 
 
3
3
0
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
5
9
9
,

 
 
1
,

 
 
2
3
,

 
 
8
7
,

 
 
1
5
3
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
2
,

 
 
1
1
,

 
 
2
9
1
1
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
4
3
4
,

 
 
2
5
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
1
2
2
7
,

 
 
2
,

 
 
8
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
2
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
2
,

 
 
3
1
9
,

 
 
2
,

 
 
3
5
6
,

 
 
8
,

 
 
1
6
5
5
,

 
 
2
2
,

 
 
6
,

 
 
2
6
3
,

 
 
2
1
,

 
 
1
,

 
 
1
1
9
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
6
,

 
 
1
8
,

 
 
1
,

 
 
7
7
,

 
 
2
2
2
,

 
 
6
2
,

 
 
4
2
,

 
 
1
3
1
,

 
 
2
4
4
7
,

 
 
1
4
0
,

 
 
2
,

 
 
1
,

 
 
2
9
,

 
 
5
0
,

 
 
1
5
2
,

 
 
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
4
5
4
9
3
,

 
 
3
,

 
 
2
7
6
7
4
,

 
 
5
4
2
7
2
]
,

 
[
8
,

 
 
1
1
,

 
 
1
0
6
1
,

 
 
2
,

 
 
5
4
1
2
,

 
 
2
7
,

 
 
1
1
3
6
,

 
 
4
,

 
 
2
,

 
 
8
4
6
,

 
 
5
0
7
,

 
 
1
2
5
,

 
 
8
4
6
,

 
 
5
0
7
,

 
 
2
4
,

 
 
4
5
9
5
,

 
 
2
4
1
2
,

 
 
2
1
,

 
 
6
0
,

 
 
7
0
8
,

 
 
3
,

 
 
2
6
7
7
,

 
 
2
3
0
9
,

 
 
5
9
,

 
 
5
2
5
,

 
 
1
,

 
 
2
5
4
,

 
 
1
2
7
0
,

 
 
9
,

 
 
1
0
1
,

 
 
1
,

 
 
2
4
9
,

 
 
2
1
,

 
 
1
4
,

 
 
4
3
9
1
,

 
 
1
2
7
0
,

 
 
9
,

 
 
8
,

 
 
9
,

 
 
2
0
,

 
 
3
1
1
,

 
 
8
,

 
 
5
7
4
,

 
 
1
5
6
7
0
,

 
 
4
1
,

 
 
1
8
,

 
 
4
3
0
,

 
 
6
6
4
,

 
 
3
3
5
1
,

 
 
6
7
8
,

 
 
6
4
,

 
 
1
1
4
,

 
 
6
,

 
 
5
7
4
,

 
 
1
6
3
5
,

 
 
2
,

 
 
3
9
2
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
1
,

 
 
2
2
4
1
,

 
 
1
0
5
7
,

 
 
1
4
2
8
,

 
 
8
,

 
 
3
7
1
,

 
 
2
5
3
1
,

 
 
1
4
,

 
 
3
,

 
 
1
3
,

 
 
1
1
8
7
,

 
 
1
8
5
3
,

 
 
8
2
4
,

 
 
1
8
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
4
,

 
 
4
5
4
9
4
,

 
 
6
3
,

 
 
1
1
,

 
 
8
,

 
 
2
1
6
5
,

 
 
3
2
,

 
 
1
3
7
3
9
,

 
 
5
,

 
 
8
4
,

 
 
1
3
6
,

 
 
2
7
,

 
 
2
0
1
2
,

 
 
4
9
1
,

 
 
3
3
6
4
7
,

 
 
4
5
4
9
4
,

 
 
5
,

 
 
3
9
6
4
1
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
3
1
,

 
 
3
2
,

 
 
2
0
1
2
,

 
 
4
9
1
,

 
 
1
3
7
3
9
,

 
 
9
,

 
 
8
,

 
 
4
7
3
8
,

 
 
2
7
1
,

 
 
9
3
,

 
 
3
5
8
,

 
 
1
1
,

 
 
2
4
,

 
 
1
3
1
,

 
 
3
2
,

 
 
1
6
3
,

 
 
1
4
,

 
 
3
,

 
 
1
3
,

 
 
1
1
8
7
,

 
 
1
4
2
8
,

 
 
4
2
,

 
 
3
3
,

 
 
1
0
4
,

 
 
2
5
4
3
,

 
 
1
,

 
 
3
3
7
2
,

 
 
9
,

 
 
1
6
3
,

 
 
9
8
5
,

 
 
1
,

 
 
6
2
5
,

 
 
5
3
,

 
 
3
9
,

 
 
6
6
9
9
,

 
 
8
,

 
 
3
3
,

 
 
8
4
6
,

 
 
6
4
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
8
2
4
,

 
 
1
0
,

 
 
5
5
,

 
 
4
6
9
,

 
 
3
,

 
 
1
,

 
 
2
7
0
,

 
 
1
1
,

 
 
8
,

 
 
5
2
0
2
,

 
 
8
0
,

 
 
1
7
1
6
,

 
 
1
0
6
4
7
7
,

 
 
2
4
,

 
 
3
5
5
,

 
 
4
,

 
 
3
7
8
9
,

 
 
1
7
8
8
,

 
 
2
1
,

 
 
1
0
7
9
5
,

 
 
6
8
,

 
 
1
5
7
2
,

 
 
1
4
1
7
1
,

 
 
5
1
,

 
 
5
1
4
8
,

 
 
7
3
,

 
 
3
6
,

 
 
1
2
8
,

 
 
8
2
9
3
,

 
 
5
1
,

 
 
3
3
3
,

 
 
1
,

 
 
2
8
4
,

 
 
1
1
1
3
0
,

 
 
4
4
,

 
 
3
8
9
,

 
 
3
,

 
 
1
7
1
6
,

 
 
5
,

 
 
6
8
,

 
 
1
4
1
7
1
,

 
 
1
4
2
5
,

 
 
7
,

 
 
2
7
6
,

 
 
1
2
6
,

 
 
4
3
7
,

 
 
1
8
5
3
,

 
 
8
2
4
,

 
 
1
1
0
9
,

 
 
2
7
,

 
 
1
5
9
0
,

 
 
2
,

 
 
7
4
8
,

 
 
9
,

 
 
2
4
1
,

 
 
8
,

 
 
4
6
7
,

 
 
1
0
6
1
,

 
 
6
4
9
,

 
 
5
6
5
,

 
 
1
1
,

 
 
8
,

 
 
1
6
3
8
5
,

 
 
1
7
4
0
,

 
 
2
4
5
,

 
 
1
9
,

 
 
2
3
3
4
,

 
 
1
7
7
9
,

 
 
1
0
1
6
2
,

 
 
8
6
5
,

 
 
2
,

 
 
1
5
7
,

 
 
1
1
,

 
 
7
3
,

 
 
1
4
2
8
,

 
 
3
0
2
2
,

 
 
1
3
,

 
 
1
5
,

 
 
1
0
4
,

 
 
8
1
0
,

 
 
5
,

 
 
1
0
0
,

 
 
2
7
,

 
 
4
5
3
,

 
 
8
8
1
,

 
 
3
1
5
,

 
 
7
4
8
,

 
 
5
,

 
 
3
8
4
7
,

 
 
1
1
3
9
,

 
 
2
1
,

 
 
1
9
8
0
9
,

 
 
2
2
,

 
 
4
4
,

 
 
4
7
,

 
 
3
9
,

 
 
1
1
7
,

 
 
7
4
,

 
 
5
4
2
7
3
,

 
 
1
5
,

 
 
1
1
4
6
9
,

 
 
1
0
3
,

 
 
1
9
,

 
 
3
0
9
0
,

 
 
3
8
3
9
,

 
 
7
4
,

 
 
1
0
,

 
 
1
,

 
 
5
4
9
,

 
 
3
9
,

 
 
1
4
2
8
,

 
 
6
8
0
9
,

 
 
2
6
9
,

 
 
7
3
,

 
 
2
1
,

 
 
5
5
,

 
 
7
0
8
,

 
 
3
,

 
 
1
2
7
2
1
,

 
 
8
8
7
,

 
 
4
7
8
5
,

 
 
3
,

 
 
5
4
2
7
3
,

 
 
3
8
3
9
,

 
 
8
0
3
1
,

 
 
1
5
,

 
 
1
1
4
6
9
,

 
 
2
2
,

 
 
6
,

 
 
5
9
,

 
 
2
7
5
,

 
 
1
1
,

 
 
6
,

 
 
2
2
9
,

 
 
3
4
,

 
 
2
3
8
8
,

 
 
1
5
,

 
 
1
1
,

 
 
1
4
2
8
,

 
 
1
2
1
7
7
,

 
 
1
4
3
,

 
 
1
4
8
,

 
 
9
,

 
 
2
3
1
6
3
,

 
 
5
,

 
 
1
1
0
9
,

 
 
2
1
5
,

 
 
9
,

 
 
1
8
1
,

 
 
1
9
,

 
 
4
,

 
 
7
9
6
,

 
 
1
8
5
5
,

 
 
1
8
5
3
,

 
 
7
3
3
,

 
 
5
,

 
 
3
3
6
4
8
,

 
 
1
0
,

 
 
9
2
,

 
 
1
7
0
,

 
 
2
3
8
8
,

 
 
9
,

 
 
1
1
7
,

 
 
1
0
1
,

 
 
7
1
,

 
 
3
6
,

 
 
1
8
0
5
4
,

 
 
1
2
,

 
 
1
3
,

 
 
2
,

 
 
1
0
3
8
,

 
 
9
,

 
 
1
5
8
,

 
 
2
4
5
,

 
 
1
9
,

 
 
2
4
1
2
,

 
 
1
1
,

 
 
1
3
,

 
 
8
,

 
 
1
1
1
,

 
 
4
,

 
 
1
8
7
1
3
,

 
 
3
,

 
 
8
2
4
,

 
 
6
,

 
 
3
9
,

 
 
1
1
6
4
7
,

 
 
1
9
8
0
9
,

 
 
2
,

 
 
1
6
3
,

 
 
6
,

 
 
5
9
,

 
 
2
7
5
,

 
 
1
4
2
8
,

 
 
8
,

 
 
4
9
,

 
 
2
9
0
,

 
 
7
3
,

 
 
9
2
,

 
 
1
0
1
1
,

 
 
1
0
7
0
,

 
 
2
0
,

 
 
3
1
1
,

 
 
4
2
,

 
 
4
,

 
 
5
0
7
,

 
 
1
2
5
,

 
 
5
0
7
,

 
 
2
4
,

 
 
4
5
9
5
,

 
 
1
8
6
1
,

 
 
1
8
5
,

 
 
4
0
,

 
 
1
0
1
,

 
 
5
,

 
 
9
8
,

 
 
1
2
,

 
 
4
,

 
 
1
5
6
7
0
,

 
 
3
1
1
,

 
 
9
4
5
,

 
 
9
,

 
 
2
1
,

 
 
8
7
6
,

 
 
2
,

 
 
3
0
0
,

 
 
1
5
,

 
 
1
1
8
7
,

 
 
5
0
7
,

 
 
8
,

 
 
2
4
0
7
,

 
 
2
0
,

 
 
4
,

 
 
5
0
7
,

 
 
3
1
1
,

 
 
1
8
4
,

 
 
2
7
0
4
,

 
 
1
7
,

 
 
1
1
0
4
8
,

 
 
8
2
4
,

 
 
2
2
,

 
 
4
,

 
 
8
6
,

 
 
4
,

 
 
9
3
1
,

 
 
1
0
4
4
,

 
 
5
,

 
 
5
0
7
,

 
 
8
6
,

 
 
4
,

 
 
4
9
4
9
,

 
 
1
0
,

 
 
1
,

 
 
2
0
6
0
,

 
 
6
,

 
 
6
3
,

 
 
4
,

 
 
1
4
3
1
,

 
 
3
,

 
 
9
3
1
,

 
 
4
1
2
4
,

 
 
2
1
,

 
 
8
4
6
2
,

 
 
3
3
0
,

 
 
1
,

 
 
2
0
6
0
,

 
 
1
,

 
 
4
9
0
,

 
 
8
5
,

 
 
6
,

 
 
6
3
,

 
 
4
,

 
 
1
0
4
4
,

 
 
2
1
,

 
 
4
,

 
 
4
9
4
9
,

 
 
3
3
0
,

 
 
1
,

 
 
2
0
6
0
,

 
 
6
,

 
 
3
9
,

 
 
2
8
8
,

 
 
1
0
4
0
,

 
 
1
8
5
,

 
 
3
8
,

 
 
1
0
8
7
,

 
 
1
5
4
,

 
 
6
,

 
 
5
9
,

 
 
1
9
,

 
 
9
,

 
 
2
1
,

 
 
3
0
0
,

 
 
1
5
,

 
 
1
1
8
7
,

 
 
6
,

 
 
1
9
,

 
 
4
7
,

 
 
6
4
4
6
,

 
 
4
,

 
 
5
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
6
1
,

 
 
9
6
1
,

 
 
2
,

 
 
6
6
9
9
,

 
 
2
5
,

 
 
7
9
7
,

 
 
3
6
,

 
 
1
0
,

 
 
9
,

 
 
4
6
9
,

 
 
4
,

 
 
5
0
7
,

 
 
8
,

 
 
1
4
,

 
 
1
0
6
1
,

 
 
2
2
,

 
 
5
0
5
,

 
 
1
9
9
,

 
 
2
0
3
,

 
 
4
2
6
4
,

 
 
5
0
7
,

 
 
1
2
0
6
,

 
 
5
0
7
,

 
 
8
,

 
 
3
0
1
5
,

 
 
2
6
7
7
,

 
 
7
5
6
0
,

 
 
5
4
,

 
 
4
2
,

 
 
1
9
9
,

 
 
5
7
,

 
 
4
2
6
4
,

 
 
3
6
,

 
 
1
0
,

 
 
9
,

 
 
4
6
9
,

 
 
4
4
,

 
 
1
1
,

 
 
2
8
5
,

 
 
8
2
4
]
,

 
[
4
5
4
9
5
,

 
 
4
5
5
,

 
 
7
,

 
 
6
5
8
,

 
 
2
0
,

 
 
2
3
4
,

 
 
1
5
,

 
 
1
,

 
 
8
2
0
8
,

 
 
4
5
4
9
5
,

 
 
1
3
8
,

 
 
2
9
,

 
 
7
,

 
 
1
0
7
8
,

 
 
1
4
4
,

 
 
1
1
0
4
,

 
 
9
4
5
,

 
 
1
5
8
,

 
 
2
1
,

 
 
4
4
,

 
 
3
8
7
,

 
 
5
9
7
3
,

 
 
2
,

 
 
3
8
,

 
 
6
,

 
 
1
6
7
,

 
 
7
,

 
 
4
3
,

 
 
7
5
9
3
,

 
 
2
3
6
,

 
 
1
,

 
 
2
9
,

 
 
4
,

 
 
2
3
5
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
3
0
2
,

 
 
7
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
3
7
3
,

 
 
6
,

 
 
6
9
,

 
 
7
,

 
 
3
3
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
7
0
,

 
 
7
,

 
 
7
7
,

 
 
4
8
5
,

 
 
4
,

 
 
2
6
0
,

 
 
4
0
9
,

 
 
3
3
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
1
1
4
,

 
 
6
0
0
,

 
 
5
,

 
 
1
7
3
,

 
 
1
6
3
,

 
 
2
,

 
 
1
,

 
 
4
3
7
,

 
 
4
7
,

 
 
2
2
,

 
 
2
0
,

 
 
1
4
,

 
 
2
9
0
5
,

 
 
1
2
8
0
,

 
 
6
6
5
,

 
 
2
6
,

 
 
7
,

 
 
3
3
2
,

 
 
1
4
4
,

 
 
6
,

 
 
8
6
,

 
 
1
9
6
3
,

 
 
1
2
,

 
 
5
,

 
 
2
4
1
,

 
 
2
4
,

 
 
9
6
,

 
 
1
6
7
,

 
 
7
,

 
 
1
8
4
,

 
 
1
0
5
7
7
,

 
 
3
7
3
,

 
 
6
]
,

 
[
1
0
2
8
,

 
 
6
5
5
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
1
,

 
 
2
9
,

 
 
4
9
1
3
,

 
 
1
8
0
5
5
,

 
 
1
5
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
]
,

 
[
2
4
3
4
,

 
 
4
3
0
3
,

 
 
8
,

 
 
3
2
9
4
,

 
 
1
2
,

 
 
6
0
7
,

 
 
3
0
6
,

 
 
1
0
9
3
,

 
 
4
2
,

 
 
1
,

 
 
1
3
9
,

 
 
4
3
0
3
,

 
 
1
9
9
,

 
 
1
9
8
1
0
,

 
 
2
,

 
 
1
9
4
0
5
,

 
 
3
7
]
,

 
[
3
9
,

 
 
6
,

 
 
9
8
4
,

 
 
1
1
,

 
 
2
8
5
,

 
 
2
2
,

 
 
6
,

 
 
9
9
,

 
 
4
,

 
 
2
0
1
,

 
 
7
4
8
,

 
 
3
,

 
 
1
,

 
 
2
5
1
,

 
 
3
6
1
,

 
 
1
1
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
7
5
5
,

 
 
2
,

 
 
6
]
,

 
[
4
3
,
 
6
,
 
2
1
0
,
 
1
1
1
8
,
 
7
3
,
 
6
,
 
5
9
,
 
8
8
1
,
 
2
8
,
 
5
4
3
,
 
4
,
 
3
0
1
,
 
2
1
8
6
]
,

 
[
4
1
5
,
 
7
1
,
 
3
7
,
 
3
3
8
7
,
 
6
7
0
0
,
 
6
3
,
 
6
4
,
 
3
0
9
9
]
,

 
[
4
2
1
,

 
 
4
5
5
,

 
 
4
0
,

 
 
7
,

 
 
2
4
,

 
 
9
5
0
,

 
 
3
,

 
 
4
0
4
,

 
 
4
9
9
,

 
 
4
,

 
 
4
2
1
,

 
 
2
,

 
 
2
6
7
8
,

 
 
3
0
,

 
 
1
0
5
3
,

 
 
5
,

 
 
1
3
,

 
 
2
4
,

 
 
1
,

 
 
2
2
0
9
8
,

 
 
2
2
8
,

 
 
7
,

 
 
1
0
3
,

 
 
1
3
6
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
3
5
,

 
 
2
8
7
,

 
 
2
6
,

 
 
1
7
4
4
6
,

 
 
5
,

 
 
6
0
7
3
0
,

 
 
6
,

 
 
7
4
2
,

 
 
1
9
,

 
 
1
4
3
9
,

 
 
3
4
,

 
 
6
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
5
8
0
5
,

 
 
1
0
3
,

 
 
6
,

 
 
4
9
8
,

 
 
5
5
,

 
 
2
0
1
,

 
 
4
6
6
8
,

 
 
1
2
1
,

 
 
3
1
,

 
 
5
5
,

 
 
6
1
,

 
 
8
1
3
8
,

 
 
8
7
5
,

 
 
8
,

 
 
6
6
,

 
 
1
3
4
7
,

 
 
9
5
,

 
 
4
6
]
,

 
[
9
5
,
 
5
9
1
,
 
4
1
,
 
8
9
]
,

 
[
2
4
2
,

 
 
6
1
9
,

 
 
1
0
,

 
 
5
9
8
2
,

 
 
1
6
8
9
3
,

 
 
4
5
5
8
,

 
 
3
0
,

 
 
2
1
1
5
,

 
 
2
2
,

 
 
7
2
,

 
 
9
1
,

 
 
2
,

 
 
1
8
0
5
,

 
 
2
6
,

 
 
7
,

 
 
2
1
1
,

 
 
9
,

 
 
1
3
0
,

 
 
3
,

 
 
1
,

 
 
2
3
4
,

 
 
1
3
1
,

 
 
1
0
,

 
 
1
,

 
 
5
9
8
2
,

 
 
1
6
8
9
3
,

 
 
4
5
5
8
,

 
 
8
6
6
,

 
 
8
6
,

 
 
3
1
3
,

 
 
3
1
,

 
 
1
2
2
5
,

 
 
4
1
,

 
 
9
9
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
5
8
,

 
 
7
7
3
4
,

 
 
1
1
0
,

 
 
2
,

 
 
7
8
9
,

 
 
2
1
,

 
 
2
3
9
8
,

 
 
2
2
2
1
,

 
 
1
5
,

 
 
1
,

 
 
2
3
5
0
,

 
 
4
6
5
,

 
 
9
3
,

 
 
5
9
,

 
 
1
4
2
2
,

 
 
1
1
,

 
 
3
9
7
,

 
 
6
,

 
 
1
4
7
,

 
 
9
6
,

 
 
5
8
,

 
 
8
4
6
3
,

 
 
5
9
5
,

 
 
2
,

 
 
8
9
6
,

 
 
7
3
,

 
 
2
,

 
 
8
0
,

 
 
5
0
5
,

 
 
3
9
6
4
2
,

 
 
1
1
,

 
 
4
5
,

 
 
1
1
8
,

 
 
4
,

 
 
2
5
0
,

 
 
1
1
0
,

 
 
1
0
,

 
 
2
0
,

 
 
3
0
0
,

 
 
1
,

 
 
6
1
9
,

 
 
3
4
,

 
 
2
,

 
 
6
8
,

 
 
1
1
0
3
,

 
 
5
5
1
,

 
 
6
8
2
,

 
 
1
5
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
8
6
,

 
 
1
0
6
4
7
8
,

 
 
9
9
2
7
,

 
 
1
5
8
8
0
,

 
 
2
5
,

 
 
2
5
9
2
1
,

 
 
4
3
,

 
 
6
,

 
 
1
9
,

 
 
5
0
2
,

 
 
1
,

 
 
2
0
6
,

 
 
1
5
,

 
 
7
4
,

 
 
1
6
0
4
1
2
,

 
 
5
2
,

 
 
8
,

 
 
7
,

 
 
5
9
,

 
 
1
2
2
0
,

 
 
6
,

 
 
2
,

 
 
3
8
9
0
,

 
 
2
,

 
 
2
5
9
,

 
 
2
6
,

 
 
7
,

 
 
1
0
8
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
3
8
1
,

 
 
9
,

 
 
7
,

 
 
4
1
1
,

 
 
2
0
,

 
 
2
3
4
,

 
 
1
0
,

 
 
1
3
,

 
 
4
5
5
8
,

 
 
8
6
6
,

 
 
1
1
3
5
,

 
 
5
,

 
 
7
,

 
 
6
5
,

 
 
9
2
,

 
 
1
8
,

 
 
1
3
0
,

 
 
7
9
5
,

 
 
3
,

 
 
1
,

 
 
5
3
9
,

 
 
6
2
,

 
 
4
3
,

 
 
2
6
3
,

 
 
2
1
,

 
 
3
7
,

 
 
4
6
,

 
 
1
7
5
3
,

 
 
2
8
8
6
,

 
 
5
3
5
,

 
 
2
8
9
1
,

 
 
5
8
1
,

 
 
2
1
6
]
,

 
[
8
7
7
9
,

 
 
3
,

 
 
1
2
1
4
,

 
 
2
0
2
,

 
 
5
4
2
,

 
 
1
0
,

 
 
5
5
3
,

 
 
3
5
,

 
 
6
5
7
1
,

 
 
5
0
3
0
,

 
 
1
2
,

 
 
1
,

 
 
1
3
2
0
8
,

 
 
2
8
,

 
 
5
3
,

 
 
1
8
,

 
 
1
2
7
7
,

 
 
1
1
,

 
 
1
1
8
0
,

 
 
2
,

 
 
1
7
3
8
,

 
 
2
8
6
2
6
,

 
 
1
,

 
 
1
2
1
4
,

 
 
2
0
2
,

 
 
5
4
2
,

 
 
1
2
,

 
 
3
1
1
,

 
 
3
4
,

 
 
5
3
,

 
 
6
9
7
9
,

 
 
1
8
5
9
,

 
 
6
0
7
3
1
,

 
 
1
7
,

 
 
1
0
6
4
7
9
,

 
 
1
6
0
4
1
3
,

 
 
2
5
,

 
 
1
0
6
4
7
9
,

 
 
1
6
0
4
1
4
,

 
 
2
5
,

 
 
3
7
5
,

 
 
1
6
3
,

 
 
5
7
4
,

 
 
2
7
1
,

 
 
3
9
,

 
 
1
2
6
1
,

 
 
5
0
,

 
 
1
2
1
,

 
 
3
2
,

 
 
4
5
4
9
6
,

 
 
1
,

 
 
1
6
1
,

 
 
3
3
9
,

 
 
1
0
,

 
 
1
9
8
7
,

 
 
1
2
1
7
8
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
6
0
4
1
5
,

 
 
1
6
0
4
1
6
,

 
 
1
6
0
4
1
7
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
0
2
5
,

 
 
1
,

 
 
1
6
1
,

 
 
6
4
,

 
 
1
7
,

 
 
7
,

 
 
5
9
,

 
 
1
0
8
,

 
 
2
,

 
 
7
4
7
4
,

 
 
7
3
,

 
 
1
3
,

 
 
2
9
,

 
 
9
5
]
,

 
[
6
5
7
,
 
2
8
2
,
 
3
7
,
 
1
5
5
,
 
7
,
 
9
9
,
 
2
,
 
1
4
7
,
 
1
1
,
 
7
3
,
 
2
,
 
6
3
,
 
2
2
,
 
1
1
,
 
2
4
,
 
3
2
5
,
 
4
6
]
,

 
[
7
4
,

 
 
3
9
,

 
 
4
7
,

 
 
1
2
4
9
8
,

 
 
1
5
8
,

 
 
6
2
,

 
 
1
5
9
5
,

 
 
1
,

 
 
5
6
5
0
,

 
 
7
1
1
4
,

 
 
3
5
3
4
,

 
 
8
,

 
 
2
7
5
2
,

 
 
3
2
,

 
 
5
2
4
8
,

 
 
6
4
9
]
,

 
[
9
2
6
,

 
 
3
,

 
 
2
2
6
0
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
7
8
0
,

 
 
7
6
,

 
 
3
,

 
 
2
2
6
0
,

 
 
1
1
,

 
 
4
3
,

 
 
1
9
9
7
,

 
 
2
7
0
0
,

 
 
3
1
,

 
 
1
,

 
 
1
1
9
9
,

 
 
3
,

 
 
1
3
8
4
,

 
 
1
0
5
,

 
 
3
5
,

 
 
1
,

 
 
1
3
1
2
,

 
 
2
2
1
4
,

 
 
3
,

 
 
1
,

 
 
5
0
6
,

 
 
2
7
1
9
,

 
 
4
9
,

 
 
1
2
,

 
 
1
,

 
 
8
8
6
,

 
 
1
3
,

 
 
7
0
8
,

 
 
3
,

 
 
2
2
6
0
,

 
 
2
4
9
,

 
 
8
,

 
 
1
4
,

 
 
8
6
0
5
,

 
 
8
0
,

 
 
4
1
,

 
 
8
,

 
 
2
7
,

 
 
1
4
8
,

 
 
1
5
6
7
1
,

 
 
1
5
,

 
 
1
,

 
 
7
5
2
,

 
 
3
,

 
 
4
,

 
 
6
4
6
,

 
 
8
3
1
,

 
 
1
2
,

 
 
3
1
1
,

 
 
3
0
0
0
,

 
 
5
,

 
 
6
5
4
5
,

 
 
3
,

 
 
4
,

 
 
5
0
6
,

 
 
2
7
1
9
,

 
 
3
2
,

 
 
1
,

 
 
1
9
1
,

 
 
1
3
1
1
,

 
 
2
3
1
6
4
,

 
 
9
4
5
5
,

 
 
4
4
2
5
,

 
 
6
0
,

 
 
1
0
2
,

 
 
8
5
8
,

 
 
6
7
8
,

 
 
2
1
,

 
 
1
,

 
 
5
3
0
6
,

 
 
1
3
,

 
 
7
2
2
,

 
 
3
,

 
 
1
0
5
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
2
,

 
 
1
0
1
8
,

 
 
1
1
,

 
 
1
5
7
,

 
 
1
3
5
,

 
 
2
2
6
0
]
,

 
[
9
5
,

 
 
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
,

 
 
2
4
2
2
,

 
 
3
8
3
,

 
 
7
1
6
,

 
 
2
8
,

 
 
2
3
0
,

 
 
8
,

 
 
4
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
6
0
,

 
 
7
5
,

 
 
1
7
,

 
 
8
,

 
 
8
9
,

 
 
9
1
,

 
 
1
4
2
3
,

 
 
1
6
1
6
,

 
 
9
3
5
0
,

 
 
7
3
,

 
 
4
7
,

 
 
6
1
,

 
 
1
8
0
,

 
 
4
9
3
,

 
 
1
6
0
4
1
8
,

 
 
5
,

 
 
8
4
,

 
 
4
1
1
0
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
3
0
3
,

 
 
1
5
,

 
 
2
7
,

 
 
3
9
3
,

 
 
2
4
2
,

 
 
1
3
3
5
,

 
 
6
0
1
,

 
 
8
4
,

 
 
2
3
1
,

 
 
1
1
8
,

 
 
1
3
6
,

 
 
6
1
,

 
 
1
1
9
2
,

 
 
3
,

 
 
1
4
8
9
,

 
 
1
0
6
4
8
0
,

 
 
6
7
7
7
,

 
 
1
3
8
,

 
 
3
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
1
,

 
 
3
5
3
,

 
 
8
4
1
,

 
 
7
8
8
6
,

 
 
3
6
,

 
 
9
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
2
,

 
 
2
0
4
,

 
 
1
5
7
,

 
 
7
3
,

 
 
1
,

 
 
1
4
6
,

 
 
1
2
4
9
9
,

 
 
1
8
6
4
,

 
 
2
3
,

 
 
1
4
3
,

 
 
5
0
4
,

 
 
4
9
7
,

 
 
4
6
,

 
 
8
4
1
,

 
 
7
8
8
6
,

 
 
1
1
3
,

 
 
8
5
2
,

 
 
4
3
6
2
,

 
 
8
4
1
,

 
 
5
1
2
0
,

 
 
1
8
4
1
,

 
 
5
,

 
 
1
2
4
9
9
,

 
 
1
8
6
4
,

 
 
9
1
3
8
,

 
 
5
5
3
0
,

 
 
4
6
]
,

 
[
1
7
8
,
 
9
5
,
 
1
2
,
 
1
7
5
,
 
4
4
9
,
 
4
0
9
,
 
6
3
,
 
6
,
 
3
1
5
,
 
4
6
]
,

 
[
1
6
3
8
6
,

 
 
1
0
,

 
 
1
1
4
7
0
,

 
 
1
3
,

 
 
8
,

 
 
2
9
3
7
,

 
 
1
7
,

 
 
1
3
2
,

 
 
2
3
8
1
7
,

 
 
6
4
1
,

 
 
3
,

 
 
8
9
3
0
,

 
 
1
0
,

 
 
1
1
4
7
0
,

 
 
3
7
5
,

 
 
6
0
,

 
 
3
9
2
,

 
 
3
,

 
 
1
3
,

 
 
2
5
,

 
 
3
1
1
,

 
 
8
,

 
 
6
1
9
5
]
,

 
[
9
5
,

 
 
1
2
8
,

 
 
1
9
7
,

 
 
2
2
,

 
 
7
1
,

 
 
5
7
,

 
 
2
3
2
6
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
6
2
3
,

 
 
8
0
,

 
 
7
,

 
 
2
3
9
,

 
 
3
5
0
,

 
 
2
1
5
,

 
 
1
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
4
3
1
9
,

 
 
2
0
4
,

 
 
1
0
4
,

 
 
1
6
1
1
,

 
 
1
0
,

 
 
3
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
9
3
6
,

 
 
1
6
0
4
1
9
,

 
 
4
6
]
,

 
[
6
,

 
 
3
9
,

 
 
3
4
,

 
 
4
0
,

 
 
1
6
4
,

 
 
2
9
8
,

 
 
1
4
3
,

 
 
8
9
,

 
 
2
6
,

 
 
2
2
,

 
 
6
,

 
 
9
4
,

 
 
4
,

 
 
7
1
2
,

 
 
8
8
8
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
3
4
,

 
 
5
8
,

 
 
5
,

 
 
1
9
,

 
 
5
8
,

 
 
2
3
6
2
,

 
 
8
,

 
 
3
8
,

 
 
7
2
,

 
 
3
5
8
,

 
 
5
,

 
 
6
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
1
0
2
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
5
8
0
,

 
 
3
6
,

 
 
6
,

 
 
2
8
8
,

 
 
1
9
,

 
 
4
,

 
 
7
1
2
,

 
 
4
9
,

 
 
9
4
,

 
 
4
7
,

 
 
1
1
,

 
 
1
1
0
9
,

 
 
4
5
2
,

 
 
3
3
4
6
,

 
 
1
8
0
5
6
]
,

 
[
1
9
7
,

 
 
1
,

 
 
1
6
0
4
2
0
,

 
 
7
9
,

 
 
1
2
2
8
,

 
 
3
2
,

 
 
3
7
8
3
,

 
 
1
6
0
4
2
1
,

 
 
2
4
,

 
 
3
7
,

 
 
1
5
,

 
 
6
9
7
5
8
,

 
 
4
3
1
2
,

 
 
7
3
,

 
 
1
6
0
4
2
2
,

 
 
3
6
,

 
 
1
2
5
1
]
,

 
[
3
2
8
,

 
 
1
,

 
 
4
5
1
,

 
 
1
4
3
9
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
0
6
4
8
1
,

 
 
2
4
3
,

 
 
8
3
3
5
,

 
 
8
3
5
2
3
,

 
 
8
3
5
2
3
,

 
 
1
3
6
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
5
1
2
,

 
 
4
0
6
,

 
 
1
0
0
3
9
,

 
 
1
8
0
5
7
,

 
 
1
6
0
4
2
3
,

 
 
8
3
5
2
3
,

 
 
2
3
2
0
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
6
0
4
2
4
,

 
 
2
4
3
,

 
 
1
0
6
4
8
2
,

 
 
1
0
6
4
8
2
,

 
 
2
3
2
0
]
,

 
[
7
,

 
 
2
2
9
,

 
 
2
2
0
,

 
 
4
4
,

 
 
4
7
,

 
 
4
2
,

 
 
2
3
7
,

 
 
2
0
4
,

 
 
7
3
,

 
 
1
3
,

 
 
2
9
,

 
 
1
6
0
4
2
5
,

 
 
1
2
2
7
9
,

 
 
1
1
3
9
,

 
 
3
6
,

 
 
7
,

 
 
9
0
]
,

 
[
1
0
1
,

 
 
1
5
1
,

 
 
7
,

 
 
6
3
6
,

 
 
6
,

 
 
2
,

 
 
4
9
8
,

 
 
1
,

 
 
3
4
5
2
,

 
 
5
5
6
,

 
 
4
7
,

 
 
1
9
4
1
,

 
 
3
,

 
 
2
0
,

 
 
4
9
0
,

 
 
7
9
,

 
 
6
4
,

 
 
6
,

 
 
1
3
1
,

 
 
2
7
,

 
 
7
9
,

 
 
2
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
6
4
,

 
 
5
,

 
 
8
4
,

 
 
9
0
,

 
 
1
4
,

 
 
4
9
8
,

 
 
1
,

 
 
3
4
5
2
,

 
 
7
,

 
 
1
3
3
3
,

 
 
5
5
6
,

 
 
4
7
,

 
 
1
9
4
1
,

 
 
3
,

 
 
9
,

 
 
7
9
,

 
 
7
,

 
 
8
4
,

 
 
6
8
1
0
,

 
 
6
,

 
 
1
2
,

 
 
4
3
3
1
,

 
 
2
,

 
 
4
9
8
,

 
 
1
,

 
 
1
3
3
3
,

 
 
3
4
5
2
,

 
 
1
0
,

 
 
4
,

 
 
1
2
6
1
6
,

 
 
1
4
6
7
,

 
 
5
4
,

 
 
1
5
1
,

 
 
5
8
,

 
 
9
3
,

 
 
4
,

 
 
7
6
6
,

 
 
6
,

 
 
1
9
,

 
 
1
5
3
,

 
 
1
4
,

 
 
2
0
7
,

 
 
7
1
7
0
,

 
 
2
0
,

 
 
3
3
6
,

 
 
2
,

 
 
5
1
7
5
,

 
 
1
,

 
 
6
5
1
8
,

 
 
8
,

 
 
3
5
6
3
]
,

 
[
3
8
,

 
 
2
9
,

 
 
1
0
6
4
8
3
,

 
 
4
1
,

 
 
1
6
,

 
 
1
2
,

 
 
3
9
3
,

 
 
1
2
9
4
,

 
 
9
,

 
 
5
9
,

 
 
1
0
6
4
8
4
,

 
 
9
0
3
2
,

 
 
5
3
3
,

 
 
6
6
0
0
,

 
 
1
6
0
4
2
6
,

 
 
3
2
1
]
,

 
[
4
,
 
4
5
6
5
,
 
3
,
 
9
9
4
,
 
6
2
2
6
,
 
1
5
2
6
0
,
 
1
1
4
3
,
 
6
0
7
3
2
]
,

 
[
7
,

 
 
2
0
7
6
,

 
 
2
,

 
 
6
5
,

 
 
9
,

 
 
8
0
,

 
 
1
,

 
 
1
6
1
,

 
 
8
,

 
 
8
0
6
,

 
 
9
3
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
3
9
5
,

 
 
4
,

 
 
2
4
9
,

 
 
3
0
4
,

 
 
1
,

 
 
1
7
9
,

 
 
5
,

 
 
4
6
4
8
,

 
 
5
6
,

 
 
1
6
,

 
 
2
0
4
2
,

 
 
3
,

 
 
1
,

 
 
1
6
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
9
0
4
3
,

 
 
7
,

 
 
8
7
3
,

 
 
4
8
,

 
 
1
,

 
 
3
1
9
,

 
 
9
,

 
 
2
4
,

 
 
1
6
5
5
,

 
 
1
0
,

 
 
1
,

 
 
1
0
6
4
8
5
,

 
 
2
3
,

 
 
3
2
9
,

 
 
5
,

 
 
2
8
7
,

 
 
4
9
9
,

 
 
5
0
2
,

 
 
5
3
,

 
 
1
0
7
8
,

 
 
9
,

 
 
1
,

 
 
5
4
6
,

 
 
3
,

 
 
1
6
0
6
,

 
 
5
6
,

 
 
1
6
,

 
 
7
2
4
9
,

 
 
2
1
,

 
 
1
,

 
 
1
3
2
,

 
 
1
0
2
9
,

 
 
4
1
,

 
 
5
3
,

 
 
9
0
,

 
 
6
9
7
5
9
,

 
 
1
2
9
5
2
,

 
 
5
,

 
 
1
8
4
8
,

 
 
1
8
4
8
,

 
 
1
4
9
0
,

 
 
4
0
,

 
 
2
8
1
,

 
 
8
4
6
4
,

 
 
1
0
2
9
,

 
 
1
3
,

 
 
1
1
0
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
2
7
,

 
 
2
3
,

 
 
1
0
,

 
 
2
7
,

 
 
3
8
4
,

 
 
1
4
,

 
 
4
,

 
 
1
6
1
,

 
 
7
5
,

 
 
3
9
,

 
 
1
3
6
,

 
 
1
1
0
7
,

 
 
1
5
1
3
,

 
 
5
,

 
 
1
,

 
 
2
3
,

 
 
5
6
,

 
 
2
7
3
,

 
 
1
3
,

 
 
6
6
,

 
 
1
,

 
 
1
9
0
,

 
 
2
3
8
8
,

 
 
1
8
,

 
 
3
6
6
,

 
 
8
0
,

 
 
6
,

 
 
1
1
7
,

 
 
1
9
0
,

 
 
2
3
8
8
,

 
 
1
1
,

 
 
1
0
8
2
,

 
 
4
8
,

 
 
4
,

 
 
1
4
1
7
2
,

 
 
1
4
,

 
 
4
,

 
 
7
3
1
,

 
 
2
7
,

 
 
3
8
4
,

 
 
5
6
,

 
 
7
1
1
,

 
 
1
,

 
 
1
7
7
2
,

 
 
5
,

 
 
2
2
,

 
 
1
,

 
 
1
1
6
0
,

 
 
8
,

 
 
1
3
3
,

 
 
4
,

 
 
7
1
7
,

 
 
5
6
,

 
 
7
1
1
,

 
 
5
,

 
 
8
8
8
,

 
 
1
4
,

 
 
1
3
6
,

 
 
4
,

 
 
8
7
0
,

 
 
4
7
,

 
 
1
2
,

 
 
1
3
,

 
 
1
9
0
,

 
 
1
0
,

 
 
7
1
,

 
 
5
4
6
,

 
 
3
,

 
 
1
6
0
6
]
,

 
[
8
3
5
,

 
 
7
3
,

 
 
2
1
,

 
 
1
3
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
1
5
4
6
7
,

 
 
2
5
,

 
 
3
4
9
2
,

 
 
4
1
5
2
,

 
 
2
,

 
 
2
2
3
3
,

 
 
1
3
,

 
 
2
5
,

 
 
9
,

 
 
2
6
7
,

 
 
5
0
,

 
 
1
5
7
1
,

 
 
3
1
,

 
 
6
0
9
,

 
 
1
5
,

 
 
3
0
,

 
 
2
9
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
5
5
4
,

 
 
6
8
4
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
4
6
,

 
 
3
5
,

 
 
5
1
1
,

 
 
1
4
0
,

 
 
6
4
,

 
 
2
5
,

 
 
8
2
4
,

 
 
8
3
5
2
4
,

 
 
4
6
,

 
 
7
,

 
 
4
3
,

 
 
1
4
4
0
,

 
 
2
2
,

 
 
1
,

 
 
4
5
1
,

 
 
4
1
0
,

 
 
1
9
9
,

 
 
3
4
5
,

 
 
6
4
,

 
 
1
7
7
5
1
,

 
 
1
6
0
4
2
7
,

 
 
1
0
6
4
8
6
,

 
 
1
3
,

 
 
6
1
3
,

 
 
8
,

 
 
4
,

 
 
5
9
2
,

 
 
3
9
3
8
,

 
 
6
4
0
1
,

 
 
1
4
3
,

 
 
3
7
5
,

 
 
5
2
,

 
 
1
8
1
,

 
 
7
0
,

 
 
6
,

 
 
1
9
,

 
 
1
0
3
3
,

 
 
2
,

 
 
7
7
3
5
,

 
 
5
,

 
 
1
,

 
 
2
2
1
,

 
 
1
0
6
,

 
 
6
,

 
 
5
6
,

 
 
1
4
5
,

 
 
9
,

 
 
7
6
,

 
 
5
8
,

 
 
6
3
5
,

 
 
1
1
,

 
 
1
8
1
,

 
 
2
6
9
,

 
 
1
0
8
0
,

 
 
1
7
,

 
 
4
8
9
,

 
 
1
6
0
4
2
8
,

 
 
7
2
5
0
,

 
 
6
6
,

 
 
7
,

 
 
1
5
8
0
,

 
 
9
,

 
 
2
9
2
,

 
 
8
,

 
 
4
,

 
 
9
1
4
,

 
 
6
3
,

 
 
6
,

 
 
1
5
,

 
 
1
,

 
 
1
8
0
,

 
 
5
7
0
2
,

 
 
5
7
6
8
,

 
 
7
7
3
6
,

 
 
2
4
6
7
]
,

 
[
7
2
,

 
 
1
4
,

 
 
1
9
1
1
,

 
 
7
2
,

 
 
4
9
,

 
 
3
5
5
,

 
 
1
1
5
6
,

 
 
4
0
0
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
4
6
9
,

 
 
3
,

 
 
4
2
0
9
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
7
2
,

 
 
1
9
1
1
,

 
 
5
3
6
,

 
 
8
3
5
2
5
,

 
 
4
0
6
,

 
 
1
3
,

 
 
3
4
1
,

 
 
8
9
]
,

 
[
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
9
0
3
3
,

 
 
5
2
0
3
,

 
 
8
3
5
2
6
,

 
 
1
,

 
 
4
2
7
2
,

 
 
3
8
4
,

 
 
3
5
,

 
 
1
4
9
2
,

 
 
3
0
0
,

 
 
4
7
0
9
,

 
 
9
0
3
3
,

 
 
5
2
0
3
,

 
 
8
3
5
2
6
,

 
 
1
,

 
 
4
2
7
2
,

 
 
3
8
4
,

 
 
3
5
,

 
 
1
4
9
2
,

 
 
3
0
0
,

 
 
4
7
0
9
]
,

 
[
4
7
3
,
 
6
0
,
 
4
8
1
,
 
3
9
2
,
 
3
,
 
1
,
 
1
1
0
4
9
,
 
2
3
,
 
8
,
 
1
4
,
 
1
7
7
,
 
6
0
,
 
8
3
9
,
 
3
,
 
3
4
7
]
,

 
[
2
0
6
,
 
7
,
 
1
0
3
,
 
1
4
,
 
1
6
5
1
,
 
1
,
 
4
0
3
,
 
4
6
]
,

 
[
4
7
8
6
,

 
 
1
4
4
4
,

 
 
8
,

 
 
1
0
,

 
 
1
5
3
5
,

 
 
1
3
7
8
,

 
 
1
,

 
 
2
9
7
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
2
1
2
,

 
 
7
8
,

 
 
7
5
,

 
 
1
8
,

 
 
2
9
0
,

 
 
1
1
1
,

 
 
2
1
5
7
4
,

 
 
5
4
3
,

 
 
5
8
,

 
 
1
2
0
4
,

 
 
8
,

 
 
9
,

 
 
5
1
,

 
 
6
,

 
 
4
3
,

 
 
1
5
4
5
,

 
 
1
,

 
 
3
9
2
,

 
 
3
,

 
 
1
0
3
1
,

 
 
1
1
5
6
2
,

 
 
1
0
,

 
 
1
9
1
7
,

 
 
3
,

 
 
1
0
3
1
,

 
 
1
2
2
8
0
,

 
 
3
,

 
 
1
1
5
6
2
,

 
 
5
4
6
4
,

 
 
5
4
,

 
 
3
1
8
9
,

 
 
9
6
,

 
 
4
,

 
 
5
1
3
6
,

 
 
7
0
0
,

 
 
6
1
,

 
 
9
3
,

 
 
2
4
4
4
9
,

 
 
1
,

 
 
5
4
6
4
,

 
 
1
0
,

 
 
9
,

 
 
1
6
1
3
,

 
 
9
3
2
,

 
 
1
8
,

 
 
1
8
3
6
,

 
 
5
5
6
,

 
 
1
0
9
6
5
,

 
 
3
5
1
,

 
 
1
2
,

 
 
6
0
,

 
 
2
1
2
,

 
 
6
,

 
 
3
0
0
1
,

 
 
2
,

 
 
1
0
7
2
,

 
 
1
3
,

 
 
2
3
,

 
 
2
,

 
 
1
6
,

 
 
2
0
6
5
5
,

 
 
4
,

 
 
6
1
1
1
,

 
 
1
3
,

 
 
5
2
8
,

 
 
3
1
6
6
,

 
 
7
5
7
,

 
 
4
3
,

 
 
1
9
,

 
 
1
3
1
,

 
 
4
,

 
 
2
3
5
5
,

 
 
9
3
0
,

 
 
1
2
,

 
 
1
0
1
0
,

 
 
7
2
,

 
 
2
3
9
0
,

 
 
3
,

 
 
2
0
3
3
,

 
 
2
1
,

 
 
7
5
,

 
 
6
2
,

 
 
1
8
,

 
 
2
3
1
7
,

 
 
1
8
0
,

 
 
6
0
7
3
3
,

 
 
5
8
5
2
,

 
 
2
,

 
 
1
7
1
5
3
,

 
 
1
5
,

 
 
4
,

 
 
3
3
9
,

 
 
2
3
,

 
 
7
0
4
,

 
 
2
0
1
4
,

 
 
7
8
4
7
,

 
 
4
4
5
9
]
,

 
[
9
5
,

 
 
5
4
2
7
4
,

 
 
7
,

 
 
5
1
4
9
,

 
 
2
9
4
9
,

 
 
6
,

 
 
1
5
5
,

 
 
7
,

 
 
2
4
,

 
 
5
9
4
8
,

 
 
3
2
,

 
 
1
,

 
 
1
1
5
1
,

 
 
5
4
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
9
7
4
,

 
 
2
,

 
 
1
6
6
4
,

 
 
3
1
9
,

 
 
1
0
0
,

 
 
4
9
,

 
 
4
7
,

 
 
2
1
6
4
,

 
 
1
0
6
4
8
7
,

 
 
9
7
,

 
 
1
1
,

 
 
7
5
7
,

 
 
3
7
1
0
,

 
 
3
7
,

 
 
1
4
3
,

 
 
1
2
,

 
 
7
7
3
7
,

 
 
8
5
,

 
 
3
1
,

 
 
5
8
,

 
 
8
0
7
2
,

 
 
3
2
5
,

 
 
2
4
4
,

 
 
8
2
4
7
,

 
 
2
,

 
 
1
2
7
2
2
,

 
 
1
0
,

 
 
4
,

 
 
1
1
5
6
,

 
 
4
6
8
4
,

 
 
1
3
7
,

 
 
2
2
7
3
,

 
 
3
0
,

 
 
4
8
7
3
,

 
 
5
,

 
 
6
2
4
,

 
 
1
5
5
0
,

 
 
8
5
,

 
 
4
8
,

 
 
9
,

 
 
1
2
7
,

 
 
2
3
1
,

 
 
1
4
6
8
,

 
 
2
,

 
 
2
6
1
6
,

 
 
1
,

 
 
2
3
5
,

 
 
2
1
8
,

 
 
7
,

 
 
8
8
1
,

 
 
1
0
8
0
,

 
 
1
7
,

 
 
7
,

 
 
1
5
6
,

 
 
8
3
,

 
 
1
2
,

 
 
3
0
,

 
 
1
7
0
,

 
 
1
0
5
]
,

 
[
4
5
4
9
7
,

 
 
2
6
3
,

 
 
9
,

 
 
8
8
8
0
,

 
 
1
9
9
8
,

 
 
2
4
5
,

 
 
1
6
,

 
 
5
7
2
0
,

 
 
1
7
3
3
,

 
 
3
6
,

 
 
5
1
,

 
 
3
9
,

 
 
1
6
,

 
 
6
4
9
7
,

 
 
2
5
0
,

 
 
3
0
5
,

 
 
2
,

 
 
1
6
,

 
 
2
6
9
,

 
 
3
3
6
4
7
,

 
 
1
9
7
,

 
 
1
,

 
 
3
5
3
,

 
 
3
3
6
4
7
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
0
2
,

 
 
3
5
1
4
,

 
 
3
5
3
,

 
 
4
1
,

 
 
1
8
,

 
 
4
3
0
,

 
 
4
0
4
8
,

 
 
5
,

 
 
6
0
7
3
4
,

 
 
1
6
1
3
2
,

 
 
4
4
4
9
,

 
 
5
4
,

 
 
3
2
6
3
,

 
 
2
,

 
 
8
8
8
0
,

 
 
1
9
9
8
,

 
 
9
,

 
 
7
7
7
,

 
 
1
0
,

 
 
3
8
,

 
 
8
,

 
 
3
2
6
4
,

 
 
3
1
6
,

 
 
4
,

 
 
8
9
3
1
,

 
 
4
7
,

 
 
6
6
4
,

 
 
3
1
6
6
,

 
 
1
1
0
0
,

 
 
3
8
,

 
 
4
4
9
,

 
 
3
,

 
 
1
0
5
0
5
,

 
 
1
8
,

 
 
2
,

 
 
1
6
,

 
 
3
3
6
4
7
,

 
 
3
5
3
5
1
,

 
 
5
4
2
7
5
,

 
 
1
6
0
4
2
9
,

 
 
4
9
4
0
6
,

 
 
5
1
5
0
,

 
 
4
2
3
4
0
,

 
 
4
0
5
7
,

 
 
1
2
8
3
7
,

 
 
3
2
1
,

 
 
5
,

 
 
8
6
9
,

 
 
4
4
4
9
,

 
 
8
7
,

 
 
4
4
8
,

 
 
1
0
6
4
8
8
,

 
 
1
6
0
4
3
0
,

 
 
1
0
6
4
8
9
,

 
 
3
8
1
3
,

 
 
6
0
7
3
5
,

 
 
1
6
0
4
3
1
,

 
 
3
2
1
,

 
 
6
0
9
,

 
 
3
5
,

 
 
4
9
4
0
7
,

 
 
8
,

 
 
4
,

 
 
2
0
9
4
,

 
 
2
6
7
,

 
 
1
9
7
,

 
 
1
2
7
4
,

 
 
1
1
0
5
0
,

 
 
8
,

 
 
1
4
,

 
 
4
8
8
6
,

 
 
1
,

 
 
6
6
4
,

 
 
2
1
4
,

 
 
8
,

 
 
7
4
,

 
 
2
5
0
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
5
9
,

 
 
1
2
,

 
 
1
1
2
,

 
 
4
4
4
9
,

 
 
2
,

 
 
1
4
2
,

 
 
1
5
,

 
 
8
8
8
0
,

 
 
1
0
6
4
9
0
,

 
 
1
0
,

 
 
1
,

 
 
3
2
0
3
,

 
 
5
1
,

 
 
1
8
,

 
 
2
9
1
,

 
 
1
0
,

 
 
6
7
0
1
,

 
 
5
4
2
7
6
,

 
 
4
2
,

 
 
4
3
8
2
,

 
 
1
0
,

 
 
2
7
,

 
 
3
0
8
0
2
,

 
 
3
,

 
 
1
9
9
8
,

 
 
2
1
9
2
,

 
 
3
3
6
4
7
,

 
 
3
2
,

 
 
7
8
3
,

 
 
4
4
4
9
,

 
 
1
0
,

 
 
1
,

 
 
5
9
7
4
,

 
 
5
4
,

 
 
3
,

 
 
4
4
3
,

 
 
2
4
5
7
,

 
 
9
,

 
 
3
3
9
,

 
 
1
,

 
 
1
4
3
,

 
 
2
8
0
6
,

 
 
2
7
9
5
,

 
 
3
5
8
2
,

 
 
1
8
,

 
 
1
4
,

 
 
2
7
,

 
 
2
6
7
,

 
 
1
,

 
 
6
0
7
3
4
,

 
 
4
4
4
9
,

 
 
1
8
,

 
 
2
5
6
2
,

 
 
3
8
8
,

 
 
2
7
,

 
 
1
1
4
7
1
,

 
 
8
,

 
 
1
9
2
4
,

 
 
3
2
9
,

 
 
1
,

 
 
4
2
6
3
,

 
 
1
6
0
4
3
2
,

 
 
3
,

 
 
1
,

 
 
1
1
0
5
0
,

 
 
3
4
1
,

 
 
5
,

 
 
1
,

 
 
1
9
0
4
4
,

 
 
3
,

 
 
1
,

 
 
8
8
8
0
,

 
 
1
9
9
8
,

 
 
6
8
7
7
,

 
 
2
4
4
5
0
,

 
 
2
3
8
1
8
,

 
 
3
4
,

 
 
1
4
,

 
 
1
2
2
0
,

 
 
9
,

 
 
8
8
8
0
,

 
 
1
9
9
8
,

 
 
5
7
2
0
,

 
 
5
4
7
,

 
 
1
,

 
 
6
8
7
7
,

 
 
8
6
,

 
 
5
7
4
,

 
 
3
3
6
4
7
,

 
 
5
5
6
,

 
 
1
,

 
 
4
7
,

 
 
4
1
2
,

 
 
9
3
9
,

 
 
3
,

 
 
1
,

 
 
6
8
7
7
,

 
 
2
6
,

 
 
2
6
4
,

 
 
9
,

 
 
4
1
,

 
 
4
2
,

 
 
5
7
,

 
 
6
0
,

 
 
1
3
9
0
8
,

 
 
2
7
4
,

 
 
1
2
,

 
 
1
,

 
 
4
4
4
9
,

 
 
2
,

 
 
1
9
,

 
 
5
7
,

 
 
6
3
0
,

 
 
1
2
8
,

 
 
5
8
,

 
 
1
4
2
,

 
 
3
2
3
,

 
 
2
,

 
 
1
6
,

 
 
2
0
7
,

 
 
1
5
,

 
 
1
,

 
 
5
4
2
7
6
,

 
 
3
,

 
 
8
8
8
0
,

 
 
1
9
9
8
,

 
 
3
5
1
,

 
 
7
4
,

 
 
4
7
,

 
 
2
0
6
5
6
,

 
 
9
6
,

 
 
1
4
1
,

 
 
1
1
1
7
,

 
 
4
5
,

 
 
7
6
7
2
,

 
 
9
2
9
,

 
 
5
4
,

 
 
2
4
4
,

 
 
3
3
5
,

 
 
6
,

 
 
1
5
2
7
,

 
 
2
,

 
 
2
2
0
,

 
 
2
1
]
,

 
[
6
6
,
 
7
,
 
6
5
,
 
1
9
8
1
1
,
 
1
4
1
7
3
,
 
3
2
3
,
 
7
1
,
 
1
7
0
,
 
2
8
,
 
2
9
]
,

 
[
9
9
2
8
,

 
 
2
7
3
,

 
 
1
,

 
 
1
5
9
2
,

 
 
8
,

 
 
2
0
1
,

 
 
4
6
7
,

 
 
1
7
,

 
 
4
9
,

 
 
1
,

 
 
3
6
9
4
,

 
 
5
,

 
 
9
5
7
1
,

 
 
1
7
7
0
,

 
 
5
4
,

 
 
6
,

 
 
8
7
,

 
 
1
9
,

 
 
4
,

 
 
1
1
8
0
,

 
 
8
5
,

 
 
1
2
7
7
,

 
 
3
7
3
0
,

 
 
1
5
,

 
 
1
2
5
,

 
 
6
,

 
 
5
9
7
,

 
 
7
,

 
 
3
1
6
8
,

 
 
1
0
8
0
,

 
 
1
,

 
 
2
3
,

 
 
4
,

 
 
2
6
0
,

 
 
2
7
4
,

 
 
6
3
3
,

 
 
2
0
8
,

 
 
5
5
2
9
,

 
 
1
6
3
,

 
 
3
3
1
,

 
 
5
,

 
 
1
3
1
,

 
 
4
,

 
 
7
3
8
,

 
 
1
1
,

 
 
8
,

 
 
3
8
3
,

 
 
3
5
7
4
,

 
 
3
1
,

 
 
1
0
7
9
,

 
 
1
2
3
5
,

 
 
5
,

 
 
8
9
3
2
,

 
 
1
,

 
 
1
7
8
9
,

 
 
1
7
,

 
 
4
,

 
 
1
2
7
5
,

 
 
3
0
,

 
 
4
4
2
,

 
 
1
4
5
,

 
 
1
0
,

 
 
1
5
0
1
,

 
 
1
1
,

 
 
2
4
,

 
 
2
,

 
 
3
1
4
,

 
 
9
,

 
 
1
,

 
 
1
7
8
9
,

 
 
6
1
7
,

 
 
1
1
,

 
 
2
4
,

 
 
2
4
,

 
 
1
4
,

 
 
1
0
5
9
,

 
 
3
3
3
,

 
 
1
4
2
9
,

 
 
2
7
4
,

 
 
1
5
1
,

 
 
1
,

 
 
1
6
6
,

 
 
2
2
,

 
 
6
,

 
 
3
1
7
,

 
 
3
7
,

 
 
2
0
,

 
 
7
9
4
,

 
 
7
,

 
 
4
5
,

 
 
5
3
5
6
,

 
 
1
,

 
 
2
9
,

 
 
5
,

 
 
7
9
4
,

 
 
6
,

 
 
4
,

 
 
2
2
4
0
]
,

 
[
6
6
,

 
 
6
3
,

 
 
1
3
,

 
 
2
2
,

 
 
6
,

 
 
1
6
9
4
,

 
 
1
6
4
7
,

 
 
1
6
0
4
3
3
,

 
 
1
6
0
4
3
4
,

 
 
1
7
6
,

 
 
5
9
0
,

 
 
6
1
5
,

 
 
2
4
3
,

 
 
5
9
0
,

 
 
1
4
2
8
,

 
 
1
6
0
4
3
5
,

 
 
3
6
3
3
,

 
 
8
3
5
2
7
,

 
 
5
9
4
9
,

 
 
3
9
6
4
3
,

 
 
3
2
1
4
5
,

 
 
5
0
9
0
,

 
 
4
7
4
,

 
 
2
2
8
8
,

 
 
7
8
8
,

 
 
5
8
6
6
,

 
 
1
6
0
4
3
6
,

 
 
8
6
4
8
,

 
 
1
6
0
4
3
7
,

 
 
8
5
2
,

 
 
8
7
3
4
,

 
 
2
0
4
4
,

 
 
3
9
6
4
3
,

 
 
1
0
6
4
9
1
,

 
 
5
1
2
,

 
 
6
7
9
]
,

 
[
2
4
2
3
,

 
 
3
1
1
8
,

 
 
3
,

 
 
5
2
8
,

 
 
7
6
3
0
,

 
 
2
0
4
,

 
 
4
,

 
 
3
4
7
1
,

 
 
1
5
,

 
 
1
1
,

 
 
5
0
,

 
 
1
5
9
,

 
 
3
0
,

 
 
1
1
2
2
,

 
 
5
,

 
 
1
7
6
6
,

 
 
7
3
,

 
 
1
,

 
 
2
1
8
5
,

 
 
1
0
,

 
 
1
,

 
 
1
1
6
,

 
 
8
9
7
6
,

 
 
7
0
1
,

 
 
1
9
,

 
 
6
7
3
,

 
 
2
1
8
5
,

 
 
7
1
,

 
 
5
5
2
,

 
 
5
,

 
 
3
9
6
5
,

 
 
2
,

 
 
5
4
2
7
7
,

 
 
3
6
,

 
 
1
2
8
,

 
 
1
0
5
,

 
 
3
3
,

 
 
4
0
8
,

 
 
3
6
,

 
 
5
3
3
3
,

 
 
1
,

 
 
2
1
8
5
,

 
 
4
5
,

 
 
7
5
8
,

 
 
1
,

 
 
3
0
9
1
,

 
 
2
9
4
,

 
 
1
2
4
7
,

 
 
4
6
]
,

 
[
9
7
9
3
,
 
9
8
,
 
4
7
,
 
7
,
 
1
9
,
 
1
8
7
,
 
1
1
]
,

 
[
3
5
5
,

 
 
1
6
7
,

 
 
9
,

 
 
1
3
7
,

 
 
4
5
0
7
,

 
 
1
8
7
,

 
 
3
0
,

 
 
1
2
9
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
4
9
4
0
8
,

 
 
1
1
2
2
,

 
 
3
4
8
0
,

 
 
4
,

 
 
3
3
6
,

 
 
1
2
,

 
 
3
1
9
,

 
 
1
3
7
,

 
 
6
3
6
,

 
 
1
2
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
7
,

 
 
4
3
3
2
,

 
 
2
5
9
,

 
 
5
9
1
,

 
 
1
3
,

 
 
2
,

 
 
9
0
9
,

 
 
3
6
,

 
 
5
3
,

 
 
4
0
,

 
 
7
0
,

 
 
3
8
,

 
 
1
,

 
 
5
3
9
,

 
 
1
0
7
7
]
,

 
[
1
5
2
6
1
,

 
 
1
7
,

 
 
6
0
8
7
,

 
 
7
,

 
 
8
7
,

 
 
1
9
,

 
 
1
9
2
9
,

 
 
1
1
,

 
 
2
6
,

 
 
1
3
,

 
 
2
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
6
4
,

 
 
2
,

 
 
4
5
9
,

 
 
1
5
2
6
1
,

 
 
1
7
,

 
 
4
9
,

 
 
4
,

 
 
6
0
8
7
,

 
 
1
6
0
8
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
1
1
0
,

 
 
9
,

 
 
5
3
,

 
 
3
3
2
8
,

 
 
2
,

 
 
1
9
2
5
,

 
 
3
6
,

 
 
9
,

 
 
5
3
,

 
 
3
9
,

 
 
1
6
,

 
 
2
2
7
6
,

 
 
2
5
,

 
 
9
,

 
 
5
3
,

 
 
3
3
2
8
,

 
 
2
,

 
 
2
0
1
9
,

 
 
6
9
,

 
 
5
3
,

 
 
3
8
8
4
,

 
 
4
,

 
 
1
2
2
,

 
 
1
2
,

 
 
2
7
,

 
 
2
5
9
2
2
,

 
 
1
3
4
0
,

 
 
6
0
8
8
,

 
 
8
1
0
3
,

 
 
3
0
8
5
,

 
 
6
8
2
9
]
,

 
[
1
7
8
,

 
 
7
,

 
 
8
1
,

 
 
1
1
5
,

 
 
2
,

 
 
2
8
,

 
 
1
5
6
,

 
 
7
3
,

 
 
1
5
,

 
 
1
6
0
4
3
8
,

 
 
6
2
3
,

 
 
7
,

 
 
8
1
,

 
 
5
0
6
5
,

 
 
3
2
,

 
 
1
,

 
 
9
1
8
,

 
 
3
,

 
 
1
0
5
,

 
 
2
,

 
 
3
0
,

 
 
7
4
8
,

 
 
1
4
,

 
 
1
1
8
5
,

 
 
8
4
2
,

 
 
1
6
1
6
,

 
 
1
0
,

 
 
1
,

 
 
1
3
9
,

 
 
1
1
8
5
,

 
 
4
8
7
4
,

 
 
1
2
9
6
,

 
 
1
3
4
,

 
 
6
,

 
 
4
0
,

 
 
3
,

 
 
6
,

 
 
1
2
,

 
 
8
3
2
,

 
 
1
3
,

 
 
1
7
4
,

 
 
5
,

 
 
2
9
0
,

 
 
1
1
,

 
 
4
8
7
4
]
,

 
[
5
6
,

 
 
1
1
7
,

 
 
1
6
3
,

 
 
3
5
,

 
 
6
8
,

 
 
7
5
1
,

 
 
1
7
,

 
 
2
7
,

 
 
1
0
6
4
9
2
,

 
 
5
,

 
 
3
0
6
0
,

 
 
6
1
4
,

 
 
9
7
9
4
,

 
 
1
6
9
,

 
 
2
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
6
0
4
3
9
,

 
 
6
9
7
6
0
,

 
 
2
7
4
2
,

 
 
1
6
0
4
4
0
,

 
 
1
6
0
4
4
1
,

 
 
9
4
2
,

 
 
1
6
8
8
,

 
 
1
3
,

 
 
4
,

 
 
3
5
9
,

 
 
5
2
,

 
 
5
1
3
7
,

 
 
1
7
,

 
 
2
7
,

 
 
1
7
9
0
,

 
 
2
6
2
0
,

 
 
1
2
,

 
 
8
7
6
]
,

 
[
6
1
2
,

 
 
5
9
,

 
 
1
5
9
,

 
 
1
,

 
 
3
7
0
,

 
 
7
6
,

 
 
3
,

 
 
1
,

 
 
6
1
2
,

 
 
1
1
,

 
 
2
8
6
,

 
 
5
9
,

 
 
2
5
6
,

 
 
1
2
,

 
 
4
,

 
 
2
1
2
,

 
 
6
1
6
,

 
 
2
4
6
7
,

 
 
4
5
2
,

 
 
2
8
1
9
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
5
1
8
8
,

 
 
7
1
,

 
 
4
,

 
 
3
5
9
,

 
 
3
,

 
 
4
,

 
 
7
3
8
,

 
 
3
,

 
 
2
8
,

 
 
6
4
5
,

 
 
1
6
1
7
,

 
 
3
7
8
9
,

 
 
2
6
,

 
 
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
1
4
7
,

 
 
4
,

 
 
3
5
9
,

 
 
8
8
2
6
,

 
 
5
,

 
 
2
0
1
,

 
 
9
,

 
 
1
1
0
]
,

 
[
9
4
5
6
,

 
 
3
2
0
,

 
 
2
6
7
3
7
,

 
 
6
6
2
4
,

 
 
3
5
9
9
,

 
 
3
7
2
5
,

 
 
6
2
2
4
,

 
 
4
4
4
0
,

 
 
4
2
3
4
1
,

 
 
1
7
1
5
4
,

 
 
8
5
5
6
,

 
 
4
9
4
0
9
,

 
 
3
3
6
4
9
,

 
 
3
5
3
5
2
,

 
 
5
4
2
7
8
,

 
 
2
5
2
,

 
 
1
9
8
1
2
,

 
 
3
5
3
5
3
,

 
 
6
9
7
6
1
,

 
 
6
9
7
6
2
,

 
 
6
9
7
6
3
,

 
 
5
4
2
7
9
,

 
 
6
9
7
6
4
,

 
 
6
9
7
6
5
,

 
 
6
9
7
6
6
,

 
 
6
9
7
6
7
,

 
 
1
9
8
1
3
,

 
 
3
7
3
7
7
,

 
 
9
1
3
9
,

 
 
9
9
8
4
,

 
 
1
6
8
0
,

 
 
2
8
6
2
7
,

 
 
1
7
1
5
5
,

 
 
5
4
2
8
0
,

 
 
5
4
2
8
1
,

 
 
4
9
4
1
0
,

 
 
3
3
6
5
0
,

 
 
4
9
4
1
1
,

 
 
5
4
2
8
2
,

 
 
5
4
2
8
3
,

 
 
4
5
4
9
8
,

 
 
4
2
3
4
2
,

 
 
5
4
2
8
4
,

 
 
5
4
2
8
5
,

 
 
4
9
4
1
2
,

 
 
4
9
4
1
3
,

 
 
5
4
2
8
6
,

 
 
5
4
2
8
7
,

 
 
5
4
2
8
8
,

 
 
5
4
2
8
9
,

 
 
5
4
2
9
0
,

 
 
3
5
3
5
4
,

 
 
5
4
2
9
1
,

 
 
3
9
6
4
4
,

 
 
2
5
1
3
2
,

 
 
5
4
2
9
2
,

 
 
5
4
2
9
3
,

 
 
3
7
3
7
8
,

 
 
5
4
2
9
4
,

 
 
4
9
4
1
4
,

 
 
4
5
4
9
9
,

 
 
4
5
5
0
0
,

 
 
1
2
7
2
3
,

 
 
9
9
8
5
,

 
 
5
4
2
7
,

 
 
5
0
2
1
,

 
 
3
9
6
4
5
,

 
 
3
5
3
5
5
,

 
 
1
2
9
4
,

 
 
1
9
0
4
5
,

 
 
1
9
0
4
5
,

 
 
2
9
6
7
1
,

 
 
2
9
6
7
1
,

 
 
8
6
8
1
,

 
 
8
6
8
1
,

 
 
1
8
7
1
4
,

 
 
1
8
7
1
4
,

 
 
3
7
3
7
9
,

 
 
3
7
3
7
9
,

 
 
3
5
3
5
6
,

 
 
3
5
3
5
6
,

 
 
1
8
3
6
5
,

 
 
1
8
3
6
5
,

 
 
3
3
6
5
1
,

 
 
3
3
6
5
1
,

 
 
3
5
3
5
7
,

 
 
3
5
3
5
7
,

 
 
2
9
6
7
2
,

 
 
2
9
6
7
2
,

 
 
2
4
4
5
1
,

 
 
2
4
4
5
1
,

 
 
3
5
3
5
8
,

 
 
3
5
3
5
8
,

 
 
7
1
1
5
,

 
 
7
1
1
5
,

 
 
2
1
5
7
5
,

 
 
2
1
5
7
5
,

 
 
2
9
6
7
3
,

 
 
2
9
6
7
3
,

 
 
3
0
8
0
3
,

 
 
3
0
8
0
3
,

 
 
3
5
3
5
9
,

 
 
3
5
3
5
9
,

 
 
3
2
1
4
6
,

 
 
3
2
1
4
6
,

 
 
3
3
6
5
2
,

 
 
3
3
6
5
2
,

 
 
2
5
1
3
3
,

 
 
2
5
1
3
3
,

 
 
3
2
1
4
7
,

 
 
3
2
1
4
7
,

 
 
3
0
8
0
4
,

 
 
3
0
8
0
4
,

 
 
2
1
5
7
6
,

 
 
2
1
5
7
6
,

 
 
3
2
1
4
8
,

 
 
3
2
1
4
8
,

 
 
2
6
7
3
8
,

 
 
2
6
7
3
8
,

 
 
3
2
1
4
9
,

 
 
3
2
1
4
9
,

 
 
3
2
1
5
0
,

 
 
3
2
1
5
0
,

 
 
2
9
6
7
4
,

 
 
2
9
6
7
4
,

 
 
2
9
6
7
5
,

 
 
2
9
6
7
5
,

 
 
2
4
4
5
2
,

 
 
2
4
4
5
2
,

 
 
3
0
8
0
5
,

 
 
3
0
8
0
5
,

 
 
2
8
6
2
8
,

 
 
2
8
6
2
8
,

 
 
2
4
4
5
3
,

 
 
2
4
4
5
3
,

 
 
2
6
7
3
9
,

 
 
2
6
7
3
9
,

 
 
3
0
8
0
6
,

 
 
3
0
8
0
6
,

 
 
2
2
0
9
9
,

 
 
3
5
3
6
0
,

 
 
3
5
3
6
0
,

 
 
3
5
3
6
1
,

 
 
3
5
3
6
1
,

 
 
3
5
3
6
2
,

 
 
3
5
3
6
2
,

 
 
2
6
7
4
0
,

 
 
2
6
7
4
0
,

 
 
3
2
1
5
1
,

 
 
3
2
1
5
1
,

 
 
3
5
3
6
3
,

 
 
3
5
3
6
3
,

 
 
3
2
1
5
2
,

 
 
3
2
1
5
2
,

 
 
2
5
1
3
4
,

 
 
2
5
1
3
4
,

 
 
3
5
3
6
4
,

 
 
3
5
3
6
4
,

 
 
3
5
3
6
5
,

 
 
3
5
3
6
5
,

 
 
3
3
6
5
3
,

 
 
3
3
6
5
3
,

 
 
3
5
3
6
6
,

 
 
3
5
3
6
6
,

 
 
3
2
1
5
3
,

 
 
3
2
1
5
3
,

 
 
2
9
6
7
6
,

 
 
2
9
6
7
6
,

 
 
3
2
1
5
4
,

 
 
3
2
1
5
4
,

 
 
2
5
9
2
3
,

 
 
2
5
9
2
3
,

 
 
3
5
3
6
7
,

 
 
3
5
3
6
7
,

 
 
3
9
6
4
6
,

 
 
3
9
6
4
6
,

 
 
3
2
1
5
5
,

 
 
3
2
1
5
5
,

 
 
3
7
3
8
0
,

 
 
3
7
3
8
0
,

 
 
3
9
6
4
7
,

 
 
3
9
6
4
7
,

 
 
3
7
3
8
1
,

 
 
3
7
3
8
1
,

 
 
3
7
3
8
2
,

 
 
3
7
3
8
2
,

 
 
3
3
6
5
4
,

 
 
3
3
6
5
4
,

 
 
3
9
6
4
8
,

 
 
3
9
6
4
8
,

 
 
3
9
6
4
9
,

 
 
3
9
6
4
9
,

 
 
2
5
9
2
4
,

 
 
2
5
9
2
4
,

 
 
3
7
3
8
3
,

 
 
3
7
3
8
3
,

 
 
3
7
3
8
4
,

 
 
3
7
3
8
4
,

 
 
2
9
6
7
7
,

 
 
2
9
6
7
7
,

 
 
3
5
3
6
8
,

 
 
3
5
3
6
8
,

 
 
3
5
3
6
9
,

 
 
3
5
3
6
9
,

 
 
3
7
3
8
5
,

 
 
3
7
3
8
5
,

 
 
3
7
3
8
6
,

 
 
3
7
3
8
6
,

 
 
3
7
3
8
7
,

 
 
3
7
3
8
7
,

 
 
3
5
3
7
0
,

 
 
3
5
3
7
0
,

 
 
3
7
3
8
8
,

 
 
3
7
3
8
8
,

 
 
3
7
3
8
9
,

 
 
4
2
3
4
3
,

 
 
3
9
6
5
0
,

 
 
4
2
3
4
4
,

 
 
3
9
6
5
1
,

 
 
3
9
6
5
1
,

 
 
3
5
3
7
1
,

 
 
3
5
3
7
1
,

 
 
3
9
6
5
2
,

 
 
3
9
6
5
2
,

 
 
3
7
3
9
0
,

 
 
3
7
3
9
0
,

 
 
3
9
6
5
3
,

 
 
3
9
6
5
3
,

 
 
3
9
6
5
4
,

 
 
3
9
6
5
4
,

 
 
3
9
6
5
5
,

 
 
3
9
6
5
5
,

 
 
3
9
6
5
6
,

 
 
3
9
6
5
6
,

 
 
3
9
6
5
7
,

 
 
3
9
6
5
7
,

 
 
4
2
3
4
5
,

 
 
2
5
9
2
5
,

 
 
3
9
6
5
8
,

 
 
3
9
6
5
8
,

 
 
3
9
6
5
9
,

 
 
3
9
6
5
9
,

 
 
3
9
6
6
0
,

 
 
3
9
6
6
0
,

 
 
3
3
6
5
5
,

 
 
3
3
6
5
5
,

 
 
3
9
6
6
1
,

 
 
3
9
6
6
1
,

 
 
3
9
6
6
2
,

 
 
3
9
6
6
2
,

 
 
3
5
3
7
2
,

 
 
3
5
3
7
2
,

 
 
3
7
3
9
1
,

 
 
3
7
3
9
1
,

 
 
3
9
6
6
3
,

 
 
3
9
6
6
3
,

 
 
3
9
6
6
4
,

 
 
3
9
6
6
4
,

 
 
3
9
6
6
5
,

 
 
3
9
6
6
5
,

 
 
3
7
3
9
2
,

 
 
3
7
3
9
2
,

 
 
3
9
6
6
6
,

 
 
3
9
6
6
6
,

 
 
3
9
6
6
7
,

 
 
3
9
6
6
7
,

 
 
3
9
6
6
8
,

 
 
3
9
6
6
8
,

 
 
3
9
6
6
9
,

 
 
3
9
6
6
9
,

 
 
3
5
3
7
3
,

 
 
3
5
3
7
3
,

 
 
3
7
3
9
3
,

 
 
3
7
3
9
3
,

 
 
3
7
3
9
4
,

 
 
3
7
3
9
4
,

 
 
3
7
3
9
5
,

 
 
3
7
3
9
5
,

 
 
2
3
1
6
5
,

 
 
2
3
1
6
5
,

 
 
2
3
8
1
9
,

 
 
2
3
8
1
9
,

 
 
2
1
0
7
3
,

 
 
2
1
0
7
3
,

 
 
3
3
6
5
6
,

 
 
3
3
6
5
6
,

 
 
1
9
4
0
6
,

 
 
1
9
4
0
6
,

 
 
1
8
7
1
5
,

 
 
1
8
7
1
5
,

 
 
2
1
5
7
7
,

 
 
2
1
5
7
7
,

 
 
1
8
3
6
6
,

 
 
1
8
3
6
6
,

 
 
1
0
5
0
,

 
 
4
5
5
0
1
,

 
 
4
5
5
0
1
,

 
 
4
5
5
0
2
,

 
 
4
5
5
0
2
,

 
 
2
5
1
3
5
,

 
 
2
5
1
3
5
,

 
 
4
5
5
0
3
,

 
 
4
5
5
0
3
,

 
 
3
7
3
9
6
,

 
 
3
7
3
9
6
,

 
 
4
5
5
0
4
,

 
 
4
5
5
0
4
,

 
 
4
5
5
0
5
,

 
 
4
5
5
0
5
,

 
 
1
4
3
6
5
,

 
 
1
4
3
6
5
,

 
 
2
5
1
3
6
,

 
 
2
5
1
3
6
,

 
 
2
4
4
5
4
,

 
 
2
4
4
5
4
,

 
 
2
1
5
7
8
,

 
 
2
1
5
7
8
,

 
 
1
4
8
8
3
,

 
 
1
4
8
8
3
,

 
 
2
8
6
2
9
,

 
 
2
8
6
2
9
,

 
 
1
2
7
2
4
,

 
 
1
2
7
2
4
,

 
 
2
4
4
5
5
,

 
 
2
4
4
5
5
,

 
 
3
3
6
5
7
,

 
 
3
3
6
5
7
,

 
 
2
5
9
2
6
,

 
 
2
5
9
2
6
,

 
 
1
9
8
1
4
,

 
 
1
9
8
1
4
,

 
 
1
8
3
6
7
,

 
 
1
8
3
6
7
,

 
 
2
9
6
7
8
,

 
 
2
9
6
7
8
,

 
 
2
5
9
2
7
,

 
 
2
5
9
2
7
,

 
 
1
4
0
4
1
,

 
 
1
4
0
4
1
,

 
 
1
5
6
7
2
,

 
 
1
5
6
7
2
,

 
 
2
9
6
7
9
,

 
 
2
9
6
7
9
,

 
 
1
9
0
4
6
,

 
 
1
9
0
4
6
,

 
 
5
4
2
9
5
,

 
 
2
6
7
4
1
,

 
 
2
6
7
4
1
,

 
 
3
5
3
7
4
,

 
 
3
5
3
7
4
,

 
 
1
9
0
4
7
,

 
 
1
9
0
4
7
,

 
 
2
6
7
4
2
,

 
 
2
6
7
4
2
,

 
 
1
6
6
3
3
,

 
 
1
6
6
3
3
,

 
 
1
4
5
4
1
,

 
 
1
4
5
4
1
,

 
 
1
0
4
2
1
,

 
 
1
1
9
5
0
,

 
 
1
1
9
5
0
,

 
 
2
6
7
4
3
,

 
 
2
6
7
4
3
,

 
 
6
2
2
7
,

 
 
6
2
2
7
,

 
 
2
7
6
7
5
,

 
 
2
7
6
7
5
,

 
 
4
5
5
0
6
,

 
 
4
5
5
0
6
,

 
 
3
9
6
7
0
,

 
 
3
9
6
7
0
,

 
 
2
8
6
3
0
,

 
 
2
8
6
3
0
,

 
 
3
9
6
7
1
,

 
 
3
9
6
7
1
,

 
 
1
4
8
8
4
,

 
 
1
4
8
8
4
,

 
 
4
5
5
0
7
,

 
 
4
5
5
0
7
,

 
 
3
5
3
7
5
,

 
 
3
5
3
7
5
,

 
 
2
9
6
8
0
,

 
 
2
9
6
8
0
,

 
 
2
9
6
8
1
,

 
 
2
9
6
8
1
,

 
 
4
5
5
0
8
,

 
 
4
5
5
0
8
,

 
 
6
1
1
2
,

 
 
6
1
1
2
,

 
 
2
4
4
5
6
,

 
 
2
4
4
5
6
,

 
 
4
2
3
4
6
,

 
 
4
2
3
4
6
,

 
 
3
5
3
7
6
,

 
 
3
5
3
7
6
,

 
 
4
5
5
0
9
,

 
 
4
5
5
0
9
,

 
 
2
1
5
7
9
,

 
 
2
1
5
7
9
,

 
 
3
9
6
7
2
,

 
 
3
9
6
7
2
,

 
 
3
3
6
5
8
,

 
 
3
3
6
5
8
,

 
 
4
2
3
4
7
,

 
 
4
2
3
4
7
,

 
 
2
8
6
3
1
,

 
 
2
8
6
3
1
,

 
 
2
8
6
3
2
,

 
 
2
8
6
3
2
,

 
 
4
5
5
1
0
,

 
 
4
5
5
1
0
,

 
 
1
6
1
3
3
,

 
 
1
6
1
3
3
,

 
 
3
7
3
9
7
,

 
 
3
7
3
9
7
,

 
 
3
0
8
0
7
,

 
 
3
0
8
0
7
,

 
 
1
0
7
9
6
,

 
 
1
0
7
9
6
,

 
 
2
6
7
4
4
,

 
 
2
6
7
4
4
,

 
 
3
7
3
9
8
,

 
 
3
7
3
9
8
,

 
 
1
6
1
3
4
,

 
 
1
6
1
3
4
,

 
 
4
5
5
1
1
,

 
 
4
5
5
1
1
,

 
 
4
5
5
1
2
,

 
 
4
5
5
1
2
,

 
 
3
9
6
7
3
,

 
 
3
9
6
7
3
,

 
 
4
2
3
4
8
,

 
 
4
2
3
4
8
,

 
 
2
8
6
3
3
,

 
 
2
8
6
3
3
,

 
 
4
2
3
4
9
,

 
 
4
2
3
4
9
,

 
 
4
5
5
1
3
,

 
 
4
5
5
1
3
,

 
 
4
2
3
5
0
,

 
 
4
2
3
5
0
,

 
 
3
2
1
5
6
,

 
 
3
2
1
5
6
,

 
 
4
2
3
5
1
,

 
 
4
2
3
5
1
,

 
 
4
5
5
1
4
,

 
 
4
5
5
1
4
,

 
 
3
3
6
5
9
,

 
 
3
3
6
5
9
,

 
 
4
2
3
5
2
,

 
 
4
2
3
5
2
,

 
 
9
7
9
5
,

 
 
9
7
9
5
,

 
 
6
7
2
2
,

 
 
8
3
5
2
8
,

 
 
8
3
5
2
9
,

 
 
5
4
2
9
6
,

 
 
6
9
7
6
8
,

 
 
6
0
7
3
6
,

 
 
6
9
7
6
9
,

 
 
6
0
7
3
7
,

 
 
6
0
7
3
8
,

 
 
6
0
7
3
9
,

 
 
5
4
2
9
7
,

 
 
4
5
5
1
5
,

 
 
5
4
2
9
8
,

 
 
6
9
7
7
0
,

 
 
6
0
7
4
0
,

 
 
6
0
7
4
1
,

 
 
6
0
7
4
2
,

 
 
3
7
3
9
9
,

 
 
6
0
7
4
3
,

 
 
5
4
2
9
9
,

 
 
2
6
7
4
5
,

 
 
6
0
7
4
4
,

 
 
6
0
7
4
5
,

 
 
6
0
7
4
6
,

 
 
5
4
3
0
0
,

 
 
6
0
7
4
7
,

 
 
6
9
7
7
1
,

 
 
3
9
6
7
4
,

 
 
6
9
7
7
2
,

 
 
6
9
7
7
3
,

 
 
6
0
7
4
8
,

 
 
6
9
7
7
4
,

 
 
3
5
3
7
7
,

 
 
6
9
7
7
5
,

 
 
6
9
7
7
6
,

 
 
6
0
7
4
9
,

 
 
6
9
7
7
7
,

 
 
6
9
7
7
8
,

 
 
6
9
7
7
9
,

 
 
6
9
7
8
0
,

 
 
6
9
7
8
1
,

 
 
5
4
3
0
1
,

 
 
4
5
5
1
6
,

 
 
6
9
7
8
2
,

 
 
6
9
7
8
3
,

 
 
6
9
7
8
4
,

 
 
6
9
7
8
5
,

 
 
6
9
7
8
6
,

 
 
6
9
7
8
7
,

 
 
8
3
5
3
0
,

 
 
8
3
5
3
1
,

 
 
8
3
5
3
2
,

 
 
4
5
5
1
7
,

 
 
2
9
6
8
2
,

 
 
8
3
5
3
3
,

 
 
8
3
5
3
4
,

 
 
8
3
5
3
5
,

 
 
8
3
5
3
6
,

 
 
8
3
5
3
7
,

 
 
6
9
7
8
8
,

 
 
6
0
7
5
0
,

 
 
8
3
5
3
8
,

 
 
8
3
5
3
9
,

 
 
8
3
5
4
0
,

 
 
8
3
5
4
1
,

 
 
8
3
5
4
2
,

 
 
1
8
3
6
6
,

 
 
8
3
5
4
3
,

 
 
6
0
7
5
1
,

 
 
8
3
5
4
4
,

 
 
8
3
5
4
5
,

 
 
8
3
5
4
6
,

 
 
6
9
7
8
9
,

 
 
4
9
4
1
5
,

 
 
6
9
7
9
0
,

 
 
8
3
5
4
7
,

 
 
6
0
7
5
2
,

 
 
6
9
7
9
1
,

 
 
8
3
5
4
8
,

 
 
8
3
5
4
9
,

 
 
8
3
5
5
0
,

 
 
8
3
5
5
1
,

 
 
8
3
5
5
2
,

 
 
8
3
5
5
3
,

 
 
6
9
7
9
2
,

 
 
6
9
7
9
3
,

 
 
8
3
5
5
4
,

 
 
6
9
7
9
4
,

 
 
5
4
3
0
2
,

 
 
8
3
5
5
5
,

 
 
3
0
,

 
 
1
6
1
8
,

 
 
2
3
,

 
 
6
9
7
9
5
,

 
 
8
6
4
9
,

 
 
1
1
3
8
0
,

 
 
2
8
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
8
,

 
 
4
,

 
 
2
8
4
,

 
 
8
4
1
8
,

 
 
9
,

 
 
4
2
,

 
 
5
7
,

 
 
2
1
3
0
,

 
 
3
2
2
,

 
 
3
3
0
,

 
 
1
,

 
 
5
7
3
1
,

 
 
3
,

 
 
1
3
0
,

 
 
3
6
4
5
,

 
 
1
4
8
7
,

 
 
3
,

 
 
1
2
8
7
,

 
 
1
1
0
3
,

 
 
1
0
1
5
,

 
 
2
5
,

 
 
7
4
8
,

 
 
1
,

 
 
9
8
5
,

 
 
2
4
4
,

 
 
1
0
8
4
,

 
 
2
3
5
,

 
 
3
5
,

 
 
1
1
2
,

 
 
2
1
0
7
4
,

 
 
1
2
9
4
,

 
 
5
,

 
 
1
,

 
 
8
4
1
8
,

 
 
3
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
2
,

 
 
1
4
1
,

 
 
6
2
,

 
 
1
9
,

 
 
3
4
9
,

 
 
5
7
,

 
 
4
,

 
 
2
6
7
3
7
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
1
6
7
,

 
 
2
,

 
 
1
9
,

 
 
5
7
,

 
 
4
,

 
 
2
8
4
,

 
 
8
4
1
8
,

 
 
5
0
0
,

 
 
1
,

 
 
9
3
5
1
,

 
 
6
6
3
,

 
 
1
2
,

 
 
1
,

 
 
7
9
3
,

 
 
1
9
,

 
 
1
9
9
,

 
 
5
7
,

 
 
1
4
3
6
6
,

 
 
4
,

 
 
2
2
2
,

 
 
8
7
,

 
 
1
4
,

 
 
8
9
,

 
 
5
1
,

 
 
8
6
,

 
 
4
,

 
 
2
6
7
3
7
,

 
 
1
2
,

 
 
1
3
0
,

 
 
2
7
4
,

 
 
3
8
8
,

 
 
5
1
,

 
 
1
8
,

 
 
3
1
6
,

 
 
3
2
,

 
 
1
1
6
0
,

 
 
1
0
6
4
9
3
,

 
 
1
4
9
9
,

 
 
7
1
3
9
,

 
 
1
0
3
5
7
,

 
 
3
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
8
,

 
 
4
6
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
7
2
0
,

 
 
1
0
7
9
5
,

 
 
1
2
5
6
,

 
 
2
5
,

 
 
1
,

 
 
1
2
8
,

 
 
5
5
3
1
,

 
 
4
6
7
,

 
 
1
6
0
4
4
2
,

 
 
1
,

 
 
6
9
3
,

 
 
2
6
7
3
7
,

 
 
8
,

 
 
2
7
,

 
 
6
1
6
,

 
 
4
1
2
,

 
 
3
4
3
,

 
 
1
2
6
4
,

 
 
4
1
0
1
,

 
 
7
6
2
9
,

 
 
7
9
2
8
,

 
 
6
2
,

 
 
8
,

 
 
1
6
7
,

 
 
2
,

 
 
1
9
,

 
 
6
6
1
,

 
 
4
,

 
 
2
6
7
3
7
,

 
 
1
5
1
,

 
 
5
2
,

 
 
1
6
3
3
,

 
 
1
3
,

 
 
1
6
0
4
4
3
,

 
 
2
8
6
3
4
,

 
 
1
0
,

 
 
6
8
,

 
 
2
7
9
,

 
 
1
4
3
,

 
 
1
6
0
4
4
4
,

 
 
5
2
,

 
 
4
2
,

 
 
1
4
,

 
 
7
7
8
,

 
 
4
,

 
 
2
8
4
,

 
 
3
7
2
,

 
 
3
,

 
 
7
5
,

 
 
6
8
,

 
 
6
1
5
0
,

 
 
2
6
,

 
 
4
2
,

 
 
6
9
0
9
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
1
0
,

 
 
2
7
4
,

 
 
2
,

 
 
2
6
9
,

 
 
1
7
9
,

 
 
1
,

 
 
6
9
3
,

 
 
2
4
4
,

 
 
4
2
,

 
 
7
7
,

 
 
2
6
9
,

 
 
1
6
0
4
4
5
,

 
 
2
1
,

 
 
1
,

 
 
7
4
8
,

 
 
3
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
0
,

 
 
6
9
3
,

 
 
2
7
4
,

 
 
6
9
,

 
 
1
1
6
0
,

 
 
8
3
5
5
6
,

 
 
1
9
,

 
 
1
4
,

 
 
5
7
,

 
 
3
6
,

 
 
5
5
0
,

 
 
3
5
,

 
 
1
,

 
 
8
4
1
8
,

 
 
2
,

 
 
5
5
5
6
,

 
 
2
1
,

 
 
1
,

 
 
2
9
6
8
3
,

 
 
5
,

 
 
4
9
4
1
6
,

 
 
1
0
,

 
 
9
2
,

 
 
8
5
,

 
 
1
,

 
 
3
5
3
,

 
 
1
6
0
4
4
6
,

 
 
8
,

 
 
4
,

 
 
7
3
2
2
,

 
 
2
7
0
,

 
 
3
,

 
 
1
,

 
 
5
9
2
8
,

 
 
6
9
7
9
5
,

 
 
5
,

 
 
5
4
3
0
3
,

 
 
6
9
7
9
5
,

 
 
9
1
,

 
 
2
7
,

 
 
7
9
2
9
,

 
 
1
0
5
6
,

 
 
3
5
3
,

 
 
1
2
,

 
 
9
1
4
0
,

 
 
2
2
2
,

 
 
3
,

 
 
2
2
1
0
,

 
 
6
4
7
1
,

 
 
5
,

 
 
1
5
2
6
2
,

 
 
6
0
7
5
3
,

 
 
1
6
0
4
4
7
,

 
 
6
9
7
9
5
,

 
 
8
,

 
 
6
6
,

 
 
9
4
3
,

 
 
1
6
2
3
,

 
 
2
1
,

 
 
3
6
6
,

 
 
3
4
0
5
,

 
 
1
2
,

 
 
3
7
4
0
0
,

 
 
6
5
2
,

 
 
8
2
3
,

 
 
1
7
9
,

 
 
1
7
,

 
 
8
9
8
,

 
 
1
7
,

 
 
1
,

 
 
6
9
3
8
,

 
 
1
0
5
6
,

 
 
8
3
5
5
6
,

 
 
8
6
,

 
 
4
1
9
,

 
 
4
5
5
1
8
,

 
 
5
,

 
 
1
4
8
1
,

 
 
1
0
1
4
,

 
 
8
6
,

 
 
3
7
1
1
,

 
 
2
,

 
 
1
0
7
1
3
,

 
 
8
8
,

 
 
2
1
,

 
 
7
9
3
0
,

 
 
1
3
,

 
 
1
9
3
9
,

 
 
2
,

 
 
1
,

 
 
2
5
5
1
,

 
 
2
6
7
3
7
,

 
 
8
2
4
8
,

 
 
3
,

 
 
6
0
7
5
4
,

 
 
8
0
,

 
 
1
,

 
 
4
2
4
,

 
 
2
6
7
3
7
,

 
 
5
,

 
 
6
8
,

 
 
4
3
4
8
,

 
 
2
5
3
9
,

 
 
4
,

 
 
6
2
7
7
,

 
 
2
,

 
 
1
5
9
,

 
 
1
4
8
,

 
 
1
,

 
 
1
1
6
1
,

 
 
2
1
9
7
,

 
 
5
5
0
8
,

 
 
9
6
6
,

 
 
1
3
,

 
 
8
2
4
8
,

 
 
3
9
9
,

 
 
2
3
8
2
0
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
7
,

 
 
5
2
,

 
 
5
,

 
 
6
8
,

 
 
4
3
4
8
,

 
 
8
6
,

 
 
5
4
3
0
4
,

 
 
4
3
2
0
,

 
 
1
6
0
4
4
8
,

 
 
3
3
,

 
 
4
,

 
 
6
2
0
,

 
 
2
9
4
9
,

 
 
9
,

 
 
4
1
2
,

 
 
1
,

 
 
9
3
9
,

 
 
3
1
,

 
 
6
4
,

 
 
2
,

 
 
1
,

 
 
8
9
8
,

 
 
2
1
5
8
0
,

 
 
2
4
,

 
 
4
,

 
 
2
1
6
9
,

 
 
8
5
,

 
 
1
0
,

 
 
1
,

 
 
1
0
6
4
9
3
,

 
 
1
7
9
,

 
 
1
9
7
,

 
 
9
8
,

 
 
4
0
2
,

 
 
8
6
,

 
 
2
,

 
 
2
6
9
,

 
 
1
2
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
3
0
,

 
 
1
5
3
3
,

 
 
7
5
,

 
 
6
5
1
,

 
 
2
2
3
,

 
 
1
0
,

 
 
1
4
6
9
,

 
 
1
3
5
9
9
,

 
 
5
,

 
 
5
2
3
7
,

 
 
1
2
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
0
,

 
 
1
,

 
 
5
8
8
4
,

 
 
1
6
1
2
,

 
 
7
3
,

 
 
2
,

 
 
4
,

 
 
2
8
4
,

 
 
1
1
6
4
,

 
 
1
0
,

 
 
1
,

 
 
1
7
9
,

 
 
1
,

 
 
2
8
4
,

 
 
8
2
4
8
,

 
 
3
,

 
 
4
7
7
6
,

 
 
1
3
,

 
 
2
4
,

 
 
8
0
,

 
 
4
3
0
,

 
 
2
6
7
3
7
,

 
 
8
3
5
5
7
,

 
 
2
1
1
0
,

 
 
1
,

 
 
5
3
3
4
,

 
 
3
7
0
0
,

 
 
3
,

 
 
1
,

 
 
9
9
8
,

 
 
3
,

 
 
1
3
1
3
,

 
 
4
6
0
3
,

 
 
5
9
0
9
,

 
 
1
8
0
5
8
,

 
 
2
6
,

 
 
6
8
4
,

 
 
5
7
4
,

 
 
4
7
9
9
,

 
 
1
3
,

 
 
2
4
,

 
 
3
3
2
,

 
 
2
,

 
 
1
6
,

 
 
2
7
,

 
 
8
6
2
,

 
 
3
,

 
 
1
6
0
4
4
9
,

 
 
1
9
7
,

 
 
1
3
0
,

 
 
7
5
,

 
 
6
2
,

 
 
9
0
3
4
,

 
 
1
3
,

 
 
8
3
7
8
,

 
 
1
6
0
8
,

 
 
8
6
,

 
 
1
6
0
4
5
0
,

 
 
2
8
6
3
5
,

 
 
5
,

 
 
1
6
0
4
5
1
,

 
 
3
3
6
6
0
,

 
 
1
2
,

 
 
2
3
8
2
1
,

 
 
1
3
,

 
 
4
3
8
,

 
 
3
,

 
 
7
5
,

 
 
5
0
2
,

 
 
1
3
0
,

 
 
1
4
8
1
,

 
 
1
0
1
4
,

 
 
6
2
,

 
 
8
6
,

 
 
2
3
3
3
,

 
 
2
,

 
 
1
1
8
,

 
 
2
,

 
 
5
4
3
0
5
,

 
 
1
0
,

 
 
4
,

 
 
2
9
7
,

 
 
3
,

 
 
2
6
1
7
,

 
 
1
5
4
6
8
,

 
 
5
2
4
9
,

 
 
3
1
,

 
 
1
5
0
8
9
,

 
 
1
1
,

 
 
2
4
,

 
 
3
3
,

 
 
1
3
,

 
 
8
5
,

 
 
9
,

 
 
1
,

 
 
6
2
0
,

 
 
1
0
7
0
,

 
 
6
5
1
,

 
 
1
5
0
4
,

 
 
8
5
1
,

 
 
1
2
,

 
 
1
,

 
 
2
6
7
3
7
,

 
 
1
0
,

 
 
4
1
0
2
,

 
 
.
.
.
]
,

 
[
4
6
3
,

 
 
4
9
,

 
 
2
3
7
3
,

 
 
3
0
,

 
 
3
9
5
8
,

 
 
2
4
1
7
,

 
 
3
,

 
 
1
,

 
 
1
2
3
8
7
,

 
 
2
9
,

 
 
1
,

 
 
1
8
2
7
,

 
 
9
,

 
 
8
6
,

 
 
1
8
7
,

 
 
8
6
,

 
 
1
7
3
5
,

 
 
2
,

 
 
1
,

 
 
7
6
3
1
,

 
 
1
8
2
7
,

 
 
2
9
,

 
 
3
6
,

 
 
5
3
,

 
 
1
9
,

 
 
4
,

 
 
8
8
6
,

 
 
9
,

 
 
5
3
,

 
 
1
0
3
2
,

 
 
3
3
,

 
 
8
8
,

 
 
8
3
5
5
8
]
,

 
[
1
5
,

 
 
2
9
4
0
,

 
 
8
0
0
,

 
 
6
5
5
,

 
 
4
,

 
 
1
7
4
4
7
,

 
 
3
8
1
4
,

 
 
1
6
7
,

 
 
1
,

 
 
5
3
5
7
,

 
 
3
,

 
 
1
,

 
 
9
0
9
5
,

 
 
8
6
,

 
 
1
4
,

 
 
3
,

 
 
5
5
,

 
 
7
7
3
8
,

 
 
9
,

 
 
2
4
,

 
 
1
0
6
4
9
4
,

 
 
9
5
9
,

 
 
6
3
,

 
 
1
3
9
6
,

 
 
4
5
5
1
9
,

 
 
1
,

 
 
1
0
6
1
,

 
 
1
9
8
3
,

 
 
2
0
0
6
,

 
 
2
,

 
 
1
,

 
 
6
9
7
9
6
,

 
 
3
8
6
5
,

 
 
1
2
8
1
,

 
 
1
5
,

 
 
1
7
2
,

 
 
1
5
0
9
0
,

 
 
3
4
1
,

 
 
1
2
,

 
 
1
0
5
7
8
,

 
 
2
2
4
]
,

 
[
1
,

 
 
4
5
7
,

 
 
4
0
3
2
,

 
 
3
1
,

 
 
2
0
2
0
1
,

 
 
1
9
4
6
,

 
 
1
6
9
8
,

 
 
1
4
,

 
 
1
6
0
4
5
2
,

 
 
1
4
,

 
 
2
1
,

 
 
5
5
0
9
,

 
 
8
,

 
 
4
0
3
2
,

 
 
3
1
,

 
 
2
0
2
0
1
,

 
 
1
9
4
6
,

 
 
1
4
9
9
,

 
 
3
9
6
4
,

 
 
3
9
6
7
5
,

 
 
1
0
2
0
,

 
 
5
,

 
 
1
9
4
6
,

 
 
5
,

 
 
6
1
1
3
,

 
 
1
3
5
,

 
 
1
,

 
 
2
8
,

 
 
2
3
,

 
 
7
1
,

 
 
1
5
5
,

 
 
1
2
8
,

 
 
3
,

 
 
4
,

 
 
5
2
8
4
,

 
 
9
,

 
 
4
,

 
 
5
8
,

 
 
2
5
,

 
 
4
6
2
,

 
 
1
1
1
3
1
,

 
 
3
,

 
 
3
9
6
4
,

 
 
1
0
5
7
9
,

 
 
8
,

 
 
1
6
5
,

 
 
2
,

 
 
2
6
9
,

 
 
7
3
,

 
 
2
1
,

 
 
4
,

 
 
2
7
3
,

 
 
2
,

 
 
7
9
3
1
,

 
 
1
9
4
6
,

 
 
1
5
,

 
 
6
8
,

 
 
1
7
0
,

 
 
6
3
4
,

 
 
1
,

 
 
1
3
9
,

 
 
1
5
1
4
,

 
 
3
9
6
4
,

 
 
1
0
5
7
9
,

 
 
3
9
7
,

 
 
1
7
7
,

 
 
3
5
5
,

 
 
1
1
4
,

 
 
4
4
6
,

 
 
1
,

 
 
1
5
1
4
,

 
 
1
3
1
,

 
 
1
0
,

 
 
3
9
6
4
,

 
 
1
0
5
7
9
,

 
 
1
9
4
6
,

 
 
1
8
5
3
,

 
 
1
1
4
8
]
,

 
[
2
8
0
,

 
 
3
5
,

 
 
9
,

 
 
7
,

 
 
9
9
,

 
 
1
5
4
7
,

 
 
2
6
,

 
 
9
9
,

 
 
7
7
,

 
 
2
6
9
,

 
 
7
3
,

 
 
2
1
,

 
 
1
0
6
4
9
5
,

 
 
3
5
6
4
,

 
 
1
6
6
3
,

 
 
7
,

 
 
9
9
,

 
 
1
9
2
9
,

 
 
1
,

 
 
1
0
6
4
9
5
,

 
 
1
3
4
8
,

 
 
2
9
,

 
 
5
7
4
,

 
 
2
1
1
5
,

 
 
1
2
7
,

 
 
7
1
,

 
 
1
4
,

 
 
9
6
,

 
 
1
7
,

 
 
2
2
,

 
 
1
1
,

 
 
2
4
,

 
 
4
0
4
,

 
 
1
0
0
6
,

 
 
1
3
5
0
,

 
 
3
3
,

 
 
1
1
6
6
,

 
 
1
,

 
 
1
6
1
3
5
,

 
 
3
,

 
 
1
0
7
9
7
,

 
 
1
1
2
0
3
,

 
 
3
7
5
]
,

 
[
1
9
4
0
7
,

 
 
7
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
4
,

 
 
3
8
9
,

 
 
9
,

 
 
6
0
7
5
5
,

 
 
8
,

 
 
4
,

 
 
1
9
4
0
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
3
5
7
4
,

 
 
3
1
,

 
 
1
9
4
0
7
,

 
 
2
2
,

 
 
4
4
,

 
 
4
7
,

 
 
3
2
0
7
,

 
 
2
3
1
,

 
 
2
0
2
,

 
 
4
,

 
 
7
1
7
,

 
 
1
9
3
,

 
 
1
0
,

 
 
1
,

 
 
2
3
]
,

 
[
1
0
1
,

 
 
1
1
,

 
 
1
5
3
,

 
 
3
2
3
,

 
 
2
7
4
7
,

 
 
1
0
,

 
 
1
4
8
6
,

 
 
7
8
1
,

 
 
1
0
,

 
 
2
8
7
,

 
 
5
8
,

 
 
3
4
4
,

 
 
2
4
,

 
 
1
6
5
,

 
 
2
,

 
 
9
4
,

 
 
4
,

 
 
2
8
0
1
,

 
 
3
,

 
 
1
,

 
 
9
0
3
5
,

 
 
2
3
7
5
,

 
 
3
6
5
8
,

 
 
3
3
4
0
,

 
 
3
3
,

 
 
1
,

 
 
8
3
5
5
9
,

 
 
5
6
6
,

 
 
2
6
,

 
 
2
1
9
3
,

 
 
3
0
,

 
 
4
3
1
9
,

 
 
5
,

 
 
4
,

 
 
4
0
5
8
,

 
 
3
7
9
,

 
 
7
3
8
,

 
 
7
9
,

 
 
3
2
,

 
 
1
5
8
,

 
 
2
1
,

 
 
4
,

 
 
2
0
1
,

 
 
2
2
6
2
4
,

 
 
1
2
,

 
 
4
0
9
,

 
 
9
3
,

 
 
7
,

 
 
2
6
,

 
 
1
4
2
,

 
 
2
4
4
5
7
,

 
 
2
4
4
5
8
]
,

 
[
4
,

 
 
4
3
9
,

 
 
1
2
7
9
,

 
 
1
2
4
5
,

 
 
2
5
5
6
,

 
 
2
3
8
,

 
 
7
,

 
 
1
5
3
,

 
 
5
9
,

 
 
6
5
,

 
 
5
5
,

 
 
6
9
4
,

 
 
1
,

 
 
2
2
1
9
,

 
 
1
8
,

 
 
4
4
4
1
,

 
 
2
6
,

 
 
8
4
,

 
 
2
2
,

 
 
5
2
,

 
 
5
1
8
9
,

 
 
1
,

 
 
5
0
3
,

 
 
7
4
7
5
,

 
 
6
0
,

 
 
3
0
3
,

 
 
1
,

 
 
1
2
4
1
,

 
 
3
4
6
,

 
 
8
,

 
 
1
5
3
,

 
 
4
1
,

 
 
2
,

 
 
1
4
2
,

 
 
2
1
]
,

 
[
6
9
7
9
7
,

 
 
1
3
7
,

 
 
9
9
,

 
 
4
,

 
 
1
1
8
,

 
 
3
3
,

 
 
3
7
4
0
1
,

 
 
1
,

 
 
6
9
7
9
7
,

 
 
2
3
,

 
 
1
0
,

 
 
4
,

 
 
1
9
0
,

 
 
1
8
5
,

 
 
5
8
,

 
 
7
7
6
,

 
 
1
2
,

 
 
2
8
,

 
 
8
3
,

 
 
1
5
8
,

 
 
4
3
,

 
 
2
8
8
,

 
 
1
9
,

 
 
1
4
6
,

 
 
1
1
,

 
 
5
2
1
,

 
 
1
7
3
3
,

 
 
2
2
,

 
 
1
1
,

 
 
9
9
,

 
 
6
3
2
5
,

 
 
1
0
,

 
 
1
,

 
 
6
4
1
,

 
 
6
,

 
 
6
7
0
,

 
 
3
6
7
,

 
 
1
6
,

 
 
4
3
3
3
,

 
 
2
2
,

 
 
6
,

 
 
1
0
3
,

 
 
1
2
1
,

 
 
3
3
,

 
 
4
6
,

 
 
6
9
7
9
7
,

 
 
3
5
,

 
 
1
,

 
 
2
4
4
8
,

 
 
1
1
2
5
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
2
5
6
,

 
 
2
0
,

 
 
2
2
4
,

 
 
1
,

 
 
8
0
1
,

 
 
3
,

 
 
5
6
2
,

 
 
4
2
7
,

 
 
2
7
3
3
,

 
 
2
4
8
,

 
 
2
0
5
,

 
 
2
1
9
4
,

 
 
2
,

 
 
9
2
,

 
 
1
7
0
,

 
 
8
3
0
,

 
 
5
,

 
 
6
6
,

 
 
5
0
8
,

 
 
3
0
6
1
,

 
 
2
3
0
,

 
 
1
1
3
,

 
 
8
1
3
9
,

 
 
1
6
7
1
,

 
 
9
,

 
 
1
0
5
,

 
 
5
6
,

 
 
2
6
9
,

 
 
3
1
,

 
 
7
8
2
,

 
 
6
0
4
,

 
 
5
9
2
,

 
 
1
0
6
,

 
 
2
6
4
,

 
 
9
3
,

 
 
2
4
2
,

 
 
1
4
3
9
,

 
 
3
4
,

 
 
6
,

 
 
7
0
,

 
 
3
,

 
 
5
5
,

 
 
9
8
,

 
 
1
7
0
9
,

 
 
3
3
7
,

 
 
1
2
3
5
,

 
 
3
,

 
 
6
9
7
9
7
,

 
 
1
9
9
3
,

 
 
3
8
,

 
 
8
,

 
 
1
,

 
 
1
6
0
4
5
3
,

 
 
1
6
0
4
5
4
,

 
 
2
4
3
,

 
 
3
4
1
,

 
 
4
,

 
 
2
4
2
,

 
 
3
4
1
,

 
 
3
2
,

 
 
4
,

 
 
8
7
5
]
,

 
[
2
3
8
,

 
 
1
3
,

 
 
8
,

 
 
5
5
1
,

 
 
4
,

 
 
6
1
0
,

 
 
2
3
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
3
6
,

 
 
1
5
8
8
1
,

 
 
1
7
,

 
 
2
,

 
 
3
5
6
5
,

 
 
6
0
7
5
6
,

 
 
1
1
,

 
 
5
5
6
,

 
 
1
,

 
 
6
6
7
7
,

 
 
5
5
1
0
,

 
 
2
3
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
4
0
6
9
,

 
 
2
3
,

 
 
5
,

 
 
5
6
,

 
 
1
1
6
7
,

 
 
7
5
7
,

 
 
8
9
1
,

 
 
8
7
,

 
 
5
3
5
]
,

 
[
7
6
0
,
 
8
5
6
,
 
1
1
0
1
,
 
1
,
 
1
7
4
,
 
1
4
,
 
1
8
6
,
 
2
2
,
 
1
5
0
9
1
,
 
1
7
4
4
8
,
 
8
,
 
1
,
 
1
3
9
,
 
7
2
2
,
 
3
,
 
2
0
6
5
7
]
,

 
[
1
2
3
,

 
 
1
6
0
4
5
5
,

 
 
4
7
2
,

 
 
7
,

 
 
6
5
,

 
 
7
,

 
 
8
7
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
9
4
,

 
 
4
,

 
 
2
0
1
,

 
 
9
1
1
,

 
 
3
,

 
 
1
3
,

 
 
1
6
1
1
,

 
 
2
2
,

 
 
7
2
,

 
 
5
5
9
,

 
 
2
,

 
 
3
4
,

 
 
9
,

 
 
8
,

 
 
1
1
,

 
 
9
3
7
,

 
 
2
2
,

 
 
7
,

 
 
8
2
,

 
 
1
1
,

 
 
2
,

 
 
1
5
4
5
,

 
 
1
3
,

 
 
4
2
4
,

 
 
4
7
,

 
 
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
2
8
,

 
 
2
1
,

 
 
6
,

 
 
1
1
4
,

 
 
1
5
0
,

 
 
2
9
8
,

 
 
2
1
5
,

 
 
6
0
7
5
7
]
,

 
[
4
,
 
5
2
2
1
,
 
1
2
,
 
6
,
 
4
,
 
5
2
2
1
,
 
1
2
,
 
6
]
,

 
[
4
8
7
5
,
 
3
8
,
 
4
,
 
1
2
5
0
0
,
 
1
1
8
,
 
5
,
 
1
5
6
4
,
 
2
,
 
1
6
0
4
5
6
]
,

 
[
1
7
5
3
,

 
 
1
3
6
5
,

 
 
1
1
1
2
,

 
 
7
1
0
,

 
 
2
1
6
,

 
 
4
6
0
8
,

 
 
5
8
3
,

 
 
1
,

 
 
3
2
1
5
7
,

 
 
6
0
4
,

 
 
2
5
2
7
,

 
 
3
2
1
5
7
,

 
 
6
0
4
,

 
 
8
,

 
 
3
5
5
,

 
 
1
8
3
,

 
 
1
1
8
,

 
 
1
,

 
 
3
4
3
1
,

 
 
1
0
2
,

 
 
2
6
2
,

 
 
1
5
,

 
 
1
,

 
 
8
5
0
9
,

 
 
1
7
9
0
,

 
 
3
5
5
5
,

 
 
4
6
2
,

 
 
2
0
2
6
,

 
 
9
3
,

 
 
3
4
2
,

 
 
2
,

 
 
2
0
3
,

 
 
1
6
,

 
 
4
4
5
,

 
 
3
2
,

 
 
1
,

 
 
1
1
0
,

 
 
1
4
4
2
,

 
 
1
6
3
,

 
 
1
0
2
,

 
 
2
3
5
,

 
 
7
5
,

 
 
1
9
,

 
 
3
2
3
8
,

 
 
7
6
,

 
 
1
,

 
 
1
1
5
,

 
 
2
3
5
8
,

 
 
3
,

 
 
2
5
2
7
,

 
 
4
2
,

 
 
5
7
,

 
 
1
3
7
3
,

 
 
2
,

 
 
7
5
0
1
,

 
 
1
6
0
4
5
7
,

 
 
1
6
3
8
7
,

 
 
1
,

 
 
4
1
0
2
,

 
 
2
3
5
8
,

 
 
1
1
6
4
8
,

 
 
9
,

 
 
1
7
,

 
 
4
,

 
 
2
6
8
3
,

 
 
5
,

 
 
1
5
1
,

 
 
1
,

 
 
1
9
4
0
8
,

 
 
9
7
1
,

 
 
1
8
1
4
,

 
 
1
9
6
7
,

 
 
2
4
,

 
 
2
1
6
7
,

 
 
3
2
9
,

 
 
7
6
3
2
,

 
 
5
,

 
 
1
0
8
8
6
,

 
 
1
,

 
 
2
4
4
5
9
,

 
 
3
3
1
7
,

 
 
1
0
4
,

 
 
8
6
8
2
,

 
 
2
1
,

 
 
1
2
5
0
1
,

 
 
5
,

 
 
1
,

 
 
6
2
0
,

 
 
7
5
0
2
,

 
 
3
3
6
2
,

 
 
1
1
5
,

 
 
3
1
4
5
,

 
 
6
9
,

 
 
9
,

 
 
2
4
,

 
 
1
3
7
4
0
,

 
 
1
7
,

 
 
2
7
,

 
 
8
6
2
,

 
 
3
,

 
 
2
8
2
8
,

 
 
1
2
6
1
7
,

 
 
3
0
5
,

 
 
2
,

 
 
1
6
,

 
 
7
0
5
,

 
 
3
1
,

 
 
5
2
2
2
,

 
 
4
6
5
,

 
 
5
4
,

 
 
1
,

 
 
1
7
1
5
6
,

 
 
8
7
8
0
,

 
 
3
1
,

 
 
8
4
,

 
 
2
,

 
 
6
8
,

 
 
6
9
6
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
2
6
5
9
,

 
 
1
0
,

 
 
2
5
2
7
,

 
 
5
,

 
 
2
,

 
 
1
6
,

 
 
7
0
5
,

 
 
1
2
,

 
 
1
2
6
1
7
,

 
 
9
7
3
,

 
 
6
1
,

 
 
6
5
2
,

 
 
1
3
,

 
 
2
3
5
8
,

 
 
3
7
9
1
,

 
 
1
,

 
 
3
2
5
6
,

 
 
3
1
,

 
 
9
,

 
 
1
2
6
2
,

 
 
5
,

 
 
5
1
,

 
 
6
2
4
,

 
 
1
9
,

 
 
2
,

 
 
1
1
8
,

 
 
2
,

 
 
3
5
1
8
,

 
 
2
2
,

 
 
5
1
,

 
 
2
5
1
8
,

 
 
5
5
,

 
 
6
4
1
,

 
 
3
,

 
 
3
9
9
,

 
 
2
7
4
3
,

 
 
3
,

 
 
7
3
8
6
,

 
 
1
0
,

 
 
3
2
9
5
,

 
 
6
9
9
]
,

 
[
1
1
5
,

 
 
6
4
5
,

 
 
5
4
6
5
,

 
 
7
5
9
4
,

 
 
5
3
,

 
 
1
9
,

 
 
5
3
3
5
,

 
 
4
,

 
 
1
1
5
,

 
 
7
5
9
4
,

 
 
3
3
,

 
 
1
,

 
 
6
4
5
,

 
 
5
4
6
5
,

 
 
2
7
,

 
 
2
1
2
0
,

 
 
1
9
6
2
,

 
 
1
7
,

 
 
4
,

 
 
8
7
5
,

 
 
4
4
0
,

 
 
6
4
,

 
 
6
,

 
 
1
8
,

 
 
9
1
,

 
 
4
8
9
8
,

 
 
5
0
,

 
 
6
3
,

 
 
2
8
,

 
 
4
6
,

 
 
6
4
5
,

 
 
5
4
6
5
,

 
 
3
6
3
,

 
 
3
6
3
,

 
 
3
6
3
,

 
 
2
1
2
0
,

 
 
1
9
6
2
,

 
 
5
,

 
 
2
8
,

 
 
6
4
5
,

 
 
5
4
6
5
,

 
 
3
3
6
4
,

 
 
1
2
,

 
 
5
8
,

 
 
8
7
7
,

 
 
6
6
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
3
6
5
9
,

 
 
6
,

 
 
2
,

 
 
2
4
6
,

 
 
2
7
,

 
 
1
5
8
9
,

 
 
1
5
,

 
 
1
,

 
 
4
9
3
,

 
 
4
6
,

 
 
2
9
,

 
 
3
3
,

 
 
2
8
,

 
 
4
6
,

 
 
6
4
5
,

 
 
5
4
6
5
,

 
 
9
5
]
,

 
[
7
4
5
,

 
 
1
8
,

 
 
6
,

 
 
9
1
,

 
 
2
5
1
3
7
,

 
 
2
2
,

 
 
1
4
,

 
 
6
,

 
 
4
3
,

 
 
1
9
,

 
 
3
3
6
6
1
,

 
 
1
,

 
 
1
3
9
,

 
 
3
7
7
,

 
 
2
,

 
 
3
0
8
0
8
,

 
 
5
,

 
 
8
3
5
6
0
,

 
 
1
7
,

 
 
3
0
,

 
 
4
0
9
,

 
 
8
6
,

 
 
4
4
,

 
 
5
8
,

 
 
9
4
0
5
,

 
 
9
3
,

 
 
5
2
8
5
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
3
8
9
,

 
 
1
2
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
5
3
8
,

 
 
1
3
1
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
8
4
,

 
 
7
,

 
 
4
5
,

 
 
7
7
,

 
 
1
6
,

 
 
1
5
5
,

 
 
1
3
2
1
,

 
 
2
,

 
 
4
9
8
,

 
 
6
,

 
 
6
6
,

 
 
1
4
3
3
,

 
 
2
,

 
 
4
9
8
,

 
 
3
4
5
2
,

 
 
1
0
,

 
 
2
0
,

 
 
3
7
7
,

 
 
2
,

 
 
3
7
,

 
 
1
0
,

 
 
6
4
7
,

 
 
2
,

 
 
5
4
,

 
 
4
0
9
,

 
 
1
6
4
,

 
 
1
5
0
6
,

 
 
1
8
,

 
 
6
9
7
9
8
,

 
 
3
7
5
,

 
 
1
1
3
,

 
 
8
5
9
,

 
 
9
8
,

 
 
5
8
8
,

 
 
1
,

 
 
1
4
9
,

 
 
4
1
0
,

 
 
2
4
7
0
,

 
 
4
9
3
8
,

 
 
5
,

 
 
7
1
1
,

 
 
3
7
,

 
 
2
,

 
 
8
3
,

 
 
2
9
0
,

 
 
1
0
4
1
,

 
 
1
4
0
,

 
 
1
0
,

 
 
9
2
1
,

 
 
3
,

 
 
1
5
9
6
,

 
 
2
8
,

 
 
4
2
7
,

 
 
1
1
3
,

 
 
4
9
3
8
,

 
 
8
,

 
 
4
9
,

 
 
4
7
,

 
 
1
2
,

 
 
3
1
1
,

 
 
1
,

 
 
1
1
2
9
,

 
 
3
,

 
 
7
8
2
,

 
 
6
0
4
,

 
 
2
9
5
,

 
 
3
1
,

 
 
8
3
,

 
 
5
4
,

 
 
5
9
,

 
 
3
7
5
8
,

 
 
9
2
,

 
 
4
1
3
,

 
 
1
7
7
,

 
 
6
4
2
8
,

 
 
2
7
,

 
 
7
9
,

 
 
5
1
5
,

 
 
4
1
9
,

 
 
3
2
,

 
 
2
8
,

 
 
4
2
7
,

 
 
1
7
,

 
 
3
6
6
,

 
 
5
8
8
,

 
 
5
,

 
 
4
,

 
 
9
2
1
,

 
 
3
,

 
 
1
1
3
,

 
 
1
8
7
3
,

 
 
1
,

 
 
9
2
1
,

 
 
3
,

 
 
1
1
3
,

 
 
3
0
7
5
,

 
 
3
2
,

 
 
3
1
0
,

 
 
5
3
2
5
,

 
 
1
8
3
6
8
,

 
 
2
,

 
 
1
,

 
 
8
3
,

 
 
3
,

 
 
5
3
7
5
,

 
 
6
2
,

 
 
5
1
,

 
 
3
4
,

 
 
1
4
,

 
 
8
7
3
,

 
 
2
6
3
,

 
 
2
1
,

 
 
1
1
7
0
,

 
 
9
1
,

 
 
1
3
1
,

 
 
7
4
9
,

 
 
3
,

 
 
1
,

 
 
2
3
0
,

 
 
1
1
7
0
,

 
 
1
4
,

 
 
3
5
5
,

 
 
5
5
,

 
 
2
7
3
,

 
 
2
,

 
 
1
,

 
 
1
6
7
,

 
 
2
9
7
8
,

 
 
9
1
,

 
 
9
5
7
,

 
 
2
1
,

 
 
1
6
7
,

 
 
1
6
0
4
5
8
,

 
 
5
,

 
 
1
1
7
0
,

 
 
1
,

 
 
5
3
9
,

 
 
1
0
8
3
,

 
 
2
4
7
0
,

 
 
5
3
0
,

 
 
1
,

 
 
5
3
2
5
,

 
 
3
5
3
,

 
 
1
,

 
 
1
3
9
,

 
 
2
7
7
,

 
 
9
6
6
,

 
 
1
3
4
5
4
,

 
 
3
9
,

 
 
1
6
,

 
 
1
2
2
1
,

 
 
2
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
4
8
,

 
 
1
5
9
6
,

 
 
6
1
,

 
 
2
0
5
,

 
 
6
2
,

 
 
7
9
,

 
 
8
3
,

 
 
1
5
,

 
 
6
4
2
,

 
 
9
5
6
,

 
 
5
,

 
 
3
9
6
7
6
,

 
 
6
1
9
6
,

 
 
1
4
,

 
 
4
9
,

 
 
2
4
8
,

 
 
3
7
,

 
 
1
2
7
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
3
8
9
,

 
 
4
9
,

 
 
2
1
9
,

 
 
1
1
,

 
 
4
3
,

 
 
3
6
4
,

 
 
1
9
7
,

 
 
4
9
1
,

 
 
3
3
,

 
 
1
,

 
 
9
8
9
,

 
 
1
5
,

 
 
2
0
,

 
 
1
9
5
2
,

 
 
2
5
5
,

 
 
5
4
3
,

 
 
1
,

 
 
5
9
8
3
,

 
 
1
6
0
4
5
9
,

 
 
1
8
2
,

 
 
6
8
3
,

 
 
2
0
2
2
,

 
 
1
1
6
,

 
 
9
,

 
 
3
0
8
0
8
,

 
 
1
9
4
0
9
,

 
 
6
,

 
 
1
2
6
1
,

 
 
5
2
,

 
 
1
9
5
,

 
 
1
0
2
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
1
0
,

 
 
9
2
1
,

 
 
3
,

 
 
1
1
3
,

 
 
1
5
4
6
9
,

 
 
9
5
2
,

 
 
1
,

 
 
1
1
6
,

 
 
1
5
,

 
 
2
8
,

 
 
1
5
4
6
9
,

 
 
1
2
3
8
8
,

 
 
8
7
,

 
 
5
6
2
,

 
 
6
,

 
 
2
2
,

 
 
1
6
4
,

 
 
1
6
5
,

 
 
2
,

 
 
1
6
,

 
 
2
7
,

 
 
4
1
8
,

 
 
8
7
,

 
 
7
,

 
 
4
6
8
,

 
 
6
,

 
 
5
0
,

 
 
9
7
,

 
 
2
2
5
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
1
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
,

 
 
7
,

 
 
1
9
,

 
 
1
2
8
5
,

 
 
1
0
,

 
 
1
3
,

 
 
3
7
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
2
3
2
7
,

 
 
3
7
,

 
 
4
,

 
 
1
0
7
,

 
 
6
2
,

 
 
8
,

 
 
9
1
,

 
 
1
6
0
4
6
0
,

 
 
3
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
7
1
1
6
,

 
 
8
7
1
,

 
 
8
,

 
 
1
4
,

 
 
1
0
9
9
,

 
 
1
6
4
,

 
 
6
4
,

 
 
2
,

 
 
9
7
,

 
 
1
8
6
,

 
 
9
,

 
 
1
7
5
,

 
 
5
7
0
,

 
 
1
8
,

 
 
1
3
6
0
0
,

 
 
1
4
,

 
 
2
,

 
 
6
9
6
2
,

 
 
1
0
,

 
 
1
2
,

 
 
1
,

 
 
2
0
8
2
,

 
 
3
,

 
 
4
,

 
 
1
0
1
2
,

 
 
9
5
]
,

 
[
5
0
1
,

 
 
2
8
3
,

 
 
7
1
,

 
 
1
4
,

 
 
3
3
3
6
,

 
 
2
,

 
 
4
6
,

 
 
2
,

 
 
7
5
,

 
 
1
0
5
7
,

 
 
9
2
,

 
 
8
0
3
2
,

 
 
5
0
,

 
 
2
5
6
,

 
 
2
0
,

 
 
2
3
4
,

 
 
3
1
,

 
 
1
6
0
4
6
1
,

 
 
4
6
,

 
 
2
9
,

 
 
2
0
2
0
2
,

 
 
1
6
4
,

 
 
1
4
3
,

 
 
7
,

 
 
7
7
1
,

 
 
2
,

 
 
3
2
8
,

 
 
2
0
,

 
 
8
0
8
,

 
 
7
9
,

 
 
5
,

 
 
2
9
1
,

 
 
4
,

 
 
2
9
,

 
 
1
5
,

 
 
1
,

 
 
7
9
9
4
,

 
 
3
4
1
,

 
 
9
,

 
 
3
8
3
0
,

 
 
1
1
,

 
 
2
5
1
3
8
,

 
 
2
6
,

 
 
8
9
,

 
 
7
,

 
 
8
1
,

 
 
1
2
7
7
,

 
 
1
3
0
,

 
 
5
8
,

 
 
9
,

 
 
3
3
8
8
,

 
 
1
1
,

 
 
1
7
3
8
,

 
 
9
5
,

 
 
1
2
,

 
 
1
,

 
 
1
4
0
,

 
 
1
6
0
4
6
2
]
,

 
[
1
,

 
 
2
1
3
,

 
 
1
7
8
,

 
 
4
9
,

 
 
1
2
8
2
,

 
 
2
2
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
1
7
9
1
,

 
 
1
,

 
 
1
7
1
5
7
,

 
 
1
6
6
3
4
,

 
 
4
5
,

 
 
1
6
,

 
 
4
,

 
 
1
4
0
4
2
,

 
 
1
5
,

 
 
1
,

 
 
2
1
3
,

 
 
9
5
]
,

 
[
3
2
7
,

 
 
5
0
,

 
 
7
6
7
3
,

 
 
1
5
0
5
,

 
 
1
7
,

 
 
4
2
3
5
3
,

 
 
2
1
5
7
,

 
 
2
,

 
 
9
7
,

 
 
2
4
2
,

 
 
2
1
9
8
,

 
 
1
5
1
,

 
 
1
8
9
,

 
 
1
6
7
,

 
 
1
8
9
,

 
 
7
5
6
,

 
 
8
7
,

 
 
7
,

 
 
8
5
9
,

 
 
6
,

 
 
4
5
,

 
 
1
2
1
,

 
 
3
7
,

 
 
2
1
,

 
 
4
,

 
 
1
1
3
,

 
 
1
1
4
4
,

 
 
1
6
8
,

 
 
6
6
,

 
 
7
,

 
 
2
2
0
,

 
 
1
8
9
,

 
 
4
2
,

 
 
2
9
6
1
,

 
 
1
,

 
 
1
4
9
1
,

 
 
7
2
3
,

 
 
6
2
3
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
4
8
,

 
 
4
7
,

 
 
8
8
7
,

 
 
2
7
0
,

 
 
8
,

 
 
1
2
0
4
,

 
 
1
7
,

 
 
8
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
0
,

 
 
4
3
6
,

 
 
8
5
6
,

 
 
9
7
,

 
 
1
1
,

 
 
1
7
1
,

 
 
8
7
,

 
 
7
,

 
 
6
6
,

 
 
2
1
9
,

 
 
3
8
,

 
 
2
4
,

 
 
2
4
7
,

 
 
2
1
,

 
 
1
,

 
 
1
7
1
0
,

 
 
4
5
7
,

 
 
7
,

 
 
1
3
1
,

 
 
1
5
,

 
 
4
6
,

 
 
2
9
,

 
 
5
,

 
 
3
8
,

 
 
6
,

 
 
2
7
6
,

 
 
3
2
,

 
 
9
5
7
0
,

 
 
1
3
3
2
7
,

 
 
7
,

 
 
6
8
5
,

 
 
5
5
,

 
 
2
4
9
9
,

 
 
5
,

 
 
1
9
6
,

 
 
5
5
,

 
 
2
5
4
,

 
 
1
2
0
6
,

 
 
8
0
,

 
 
3
4
,

 
 
1
9
4
1
0
,

 
 
8
8
7
,

 
 
1
0
1
,

 
 
1
2
8
5
,

 
 
1
8
2
7
,

 
 
6
6
1
,

 
 
8
4
6
5
,

 
 
3
0
,

 
 
1
1
1
6
,

 
 
8
,

 
 
9
,

 
 
1
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
1
6
0
4
6
3
,

 
 
1
2
5
0
2
,

 
 
1
4
,

 
 
2
,

 
 
3
5
1
4
,

 
 
5
9
2
9
,

 
 
4
8
7
,

 
 
1
0
,

 
 
1
,

 
 
5
1
7
6
,

 
 
3
,

 
 
1
1
1
1
,

 
 
9
5
]
,

 
[
4
9
4
1
7
,
 
2
5
,
 
8
2
4
9
,
 
4
9
4
1
7
,
 
2
5
2
3
,
 
8
2
4
9
,
 
4
6
8
5
,
 
1
6
8
3
]
,

 
[
4
1
6
7
,

 
 
3
2
0
,

 
 
4
,

 
 
4
1
6
7
,

 
 
6
,

 
 
1
8
,

 
 
2
0
9
,

 
 
3
7
0
,

 
 
1
0
7
,

 
 
1
6
0
4
6
4
,

 
 
4
2
,

 
 
5
7
,

 
 
6
9
2
,

 
 
2
,

 
 
1
0
7
,

 
 
8
3
6
,

 
 
4
9
7
,

 
 
1
1
3
,

 
 
2
1
0
7
5
,

 
 
1
,

 
 
1
1
5
,

 
 
1
6
9
,

 
 
8
,

 
 
5
,

 
 
3
1
7
,

 
 
5
5
,

 
 
2
5
4
,

 
 
6
,

 
 
8
7
,

 
 
1
5
3
,

 
 
1
9
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
3
4
,

 
 
6
]
,

 
[
2
2
,

 
 
6
,

 
 
2
0
3
,

 
 
1
5
9
,

 
 
1
,

 
 
8
5
,

 
 
2
,

 
 
3
4
,

 
 
4
,

 
 
2
3
5
,

 
 
3
5
9
,

 
 
3
,

 
 
3
9
4
,

 
 
4
9
4
1
8
,

 
 
3
8
2
,

 
 
3
,

 
 
5
6
6
6
,

 
 
1
3
5
,

 
 
3
8
,

 
 
6
,

 
 
7
1
4
0
,

 
 
2
,

 
 
1
6
,

 
 
2
7
,

 
 
6
2
5
2
,

 
 
2
,

 
 
4
7
6
8
,

 
 
2
0
,

 
 
8
0
3
3
,

 
 
2
4
8
,

 
 
3
7
,

 
 
1
1
0
2
,

 
 
1
9
,

 
 
5
8
6
7
,

 
 
3
2
,

 
 
8
9
,

 
 
1
7
,

 
 
4
3
,

 
 
2
0
,

 
 
9
9
8
6
,

 
 
8
3
5
6
1
,

 
 
9
,

 
 
1
0
,

 
 
4
0
,

 
 
4
7
8
5
,

 
 
1
,

 
 
4
2
3
5
4
,

 
 
1
3
8
3
,

 
 
2
4
9
3
,

 
 
4
3
3
,

 
 
4
5
5
2
0
,

 
 
4
9
,

 
 
2
7
1
,

 
 
6
6
7
,

 
 
1
0
,

 
 
1
3
3
,

 
 
1
0
,

 
 
2
7
1
,

 
 
1
2
4
0
,

 
 
1
2
,

 
 
1
,

 
 
1
3
9
,

 
 
3
5
7
5
,

 
 
5
4
,

 
 
8
,

 
 
7
8
,

 
 
7
,

 
 
3
2
0
8
,

 
 
8
3
5
6
1
,

 
 
2
,

 
 
1
0
4
8
,

 
 
1
6
3
,

 
 
2
8
7
3
,

 
 
1
5
,

 
 
1
,

 
 
4
3
3
,

 
 
4
5
5
2
0
,

 
 
5
4
,

 
 
7
,

 
 
5
8
8
5
,

 
 
5
4
1
3
,

 
 
1
6
,

 
 
2
2
3
6
,

 
 
2
,

 
 
3
4
,

 
 
1
1
2
7
8
]
,

 
[
3
1
,

 
 
3
8
,

 
 
1
3
7
,

 
 
4
4
6
,

 
 
2
1
,

 
 
2
0
5
,

 
 
6
1
,

 
 
9
3
,

 
 
3
6
1
2
,

 
 
1
,

 
 
7
2
5
1
,

 
 
1
0
,

 
 
1
,

 
 
2
0
7
7
,

 
 
8
,

 
 
1
,

 
 
2
6
7
,

 
 
3
,

 
 
7
2
5
2
,

 
 
1
3
7
4
1
,

 
 
1
,

 
 
2
5
3
0
,

 
 
6
1
7
,

 
 
1
,

 
 
5
4
9
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
4
5
8
,

 
 
6
5
1
9
,

 
 
3
7
5
9
,

 
 
7
2
5
2
,

 
 
4
4
,

 
 
4
7
,

 
 
1
0
7
7
,

 
 
2
,

 
 
2
0
3
7
,

 
 
9
,

 
 
4
7
,

 
 
9
6
,

 
 
2
3
8
,

 
 
7
1
,

 
 
2
6
0
0
,

 
 
1
7
,

 
 
5
4
9
,

 
 
5
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
1
,

 
 
7
5
9
5
,

 
 
3
,

 
 
1
4
4
9
,

 
 
2
7
1
7
,

 
 
1
5
8
,

 
 
1
0
7
7
,

 
 
2
,

 
 
9
4
,

 
 
2
4
8
8
,

 
 
3
,

 
 
1
5
8
,

 
 
2
5
,

 
 
9
4
,

 
 
9
2
,

 
 
1
1
0
,

 
 
1
8
5
,

 
 
1
,

 
 
2
2
3
,

 
 
9
,

 
 
3
7
4
0
2
,

 
 
3
7
,

 
 
8
2
0
9
]
,

 
[
1
6
0
4
6
5
,

 
 
4
1
,

 
 
1
8
,

 
 
1
4
9
,

 
 
3
9
3
,

 
 
2
3
5
3
,

 
 
3
,

 
 
1
3
7
4
2
,

 
 
1
2
9
0
,

 
 
3
,

 
 
1
,

 
 
8
2
9
4
,

 
 
7
4
1
,

 
 
1
1
4
,

 
 
2
3
7
0
,

 
 
2
4
,

 
 
1
4
,

 
 
7
3
8
7
,

 
 
4
,

 
 
1
1
9
6
,

 
 
2
3
0
,

 
 
9
,

 
 
7
5
,

 
 
5
6
,

 
 
8
6
2
,

 
 
1
0
,

 
 
9
2
,

 
 
1
7
0
,

 
 
5
7
1
,

 
 
5
6
2
,

 
 
2
6
,

 
 
2
6
4
,

 
 
2
4
,

 
 
2
4
3
1
,

 
 
2
7
,

 
 
4
2
6
4
,

 
 
2
3
6
3
,

 
 
1
4
5
9
,

 
 
9
,

 
 
7
5
,

 
 
3
4
,

 
 
8
6
2
,

 
 
1
0
,

 
 
9
2
,

 
 
1
7
0
,

 
 
5
6
2
,

 
 
4
3
7
,

 
 
2
3
7
0
,

 
 
2
4
,

 
 
1
4
,

 
 
1
5
0
6
,

 
 
9
,

 
 
4
0
,

 
 
5
7
1
,

 
 
5
6
2
,

 
 
4
2
,

 
 
6
3
8
3
,

 
 
2
3
5
4
,

 
 
1
5
,

 
 
1
,

 
 
5
3
9
,

 
 
5
2
,

 
 
9
0
,

 
 
1
4
,

 
 
1
3
5
3
,

 
 
9
,

 
 
5
7
1
,

 
 
5
6
2
,

 
 
8
,

 
 
3
6
9
,

 
 
9
8
,

 
 
5
2
,

 
 
1
1
3
1
,

 
 
3
2
4
5
,

 
 
2
4
8
,

 
 
1
,

 
 
3
3
5
,

 
 
9
,

 
 
5
7
1
,

 
 
5
6
2
,

 
 
8
,

 
 
1
8
8
3
,

 
 
3
6
6
,

 
 
1
1
,

 
 
8
,

 
 
9
9
6
,

 
 
3
8
1
5
,

 
 
9
,

 
 
9
2
9
,

 
 
6
8
,

 
 
6
9
6
,

 
 
2
3
7
0
,

 
 
4
1
6
,

 
 
1
2
8
,

 
 
3
,

 
 
6
8
,

 
 
2
4
2
,

 
 
5
5
9
4
,

 
 
2
,

 
 
6
2
7
8
,

 
 
9
8
,

 
 
8
5
6
,

 
 
4
0
,

 
 
9
7
,

 
 
1
8
6
,

 
 
5
3
,

 
 
2
0
4
,

 
 
2
5
7
5
,

 
 
1
,

 
 
4
0
5
,

 
 
9
,

 
 
3
6
4
6
,

 
 
2
3
7
0
,

 
 
2
4
,

 
 
4
,

 
 
3
0
6
0
,

 
 
1
8
5
,

 
 
1
,

 
 
2
8
,

 
 
1
1
0
]
,

 
[
2
8
0
,

 
 
2
8
6
3
6
,

 
 
2
6
,

 
 
4
4
,

 
 
4
7
,

 
 
3
4
9
,

 
 
1
6
7
,

 
 
5
2
2
,

 
 
2
4
,

 
 
3
7
2
,

 
 
4
7
,

 
 
2
6
,

 
 
5
2
,

 
 
8
,

 
 
3
8
3
,

 
 
4
4
0
,

 
 
1
7
,

 
 
9
1
,

 
 
4
3
7
,

 
 
7
7
,

 
 
2
,

 
 
5
5
3
2
,

 
 
5
,

 
 
4
,

 
 
2
4
8
3
,

 
 
1
1
0
5
1
,

 
 
5
,

 
 
5
2
3
8
,

 
 
2
1
2
7
,

 
 
5
,

 
 
5
7
,

 
 
5
3
0
7
,

 
 
1
0
,

 
 
4
0
,

 
 
1
,

 
 
4
4
5
,

 
 
4
5
5
9
,

 
 
1
6
0
4
6
6
,

 
 
4
4
,

 
 
1
2
2
,

 
 
2
,

 
 
3
9
2
,

 
 
1
0
,

 
 
2
4
9
6
,

 
 
6
2
9
9
,

 
 
3
5
,

 
 
1
,

 
 
5
4
2
8
,

 
 
5
7
2
,

 
 
1
0
6
0
,

 
 
5
,

 
 
1
8
5
0
,

 
 
6
9
,

 
 
1
2
8
0
,

 
 
1
4
,

 
 
3
8
,

 
 
2
7
,

 
 
1
6
0
4
6
7
,

 
 
8
,

 
 
9
7
2
,

 
 
2
,

 
 
3
4
,

 
 
6
6
,

 
 
3
8
,

 
 
2
0
,

 
 
2
4
9
,

 
 
8
,

 
 
2
0
,

 
 
1
6
5
,

 
 
3
2
,

 
 
1
2
1
2
,

 
 
4
5
3
,

 
 
5
4
3
0
6
,

 
 
5
,

 
 
1
4
,

 
 
5
6
4
,

 
 
4
5
3
,

 
 
5
4
3
0
6
,

 
 
1
2
5
,

 
 
5
7
2
,

 
 
1
9
8
4
,

 
 
5
8
,

 
 
9
3
,

 
 
4
,

 
 
1
7
8
8
,

 
 
1
2
,

 
 
4
,

 
 
3
9
0
2
,

 
 
4
8
,

 
 
4
2
3
5
5
,

 
 
5
,

 
 
2
4
4
6
0
,

 
 
1
3
6
0
1
,

 
 
3
2
2
,

 
 
1
0
,

 
 
4
7
,

 
 
3
,

 
 
6
8
,

 
 
5
9
7
5
,

 
 
4
5
5
2
1
]
,

 
[
1
,
 
4
6
9
7
,
 
4
0
7
,
 
9
9
,
 
1
8
7
1
6
,
 
1
,
 
6
7
0
2
,
 
4
0
7
,
 
9
0
,
 
1
4
]
,

 
[
5
4
2
9
,

 
 
7
,

 
 
4
9
,

 
 
1
9
,

 
 
4
4
6
,

 
 
9
,

 
 
2
2
0
3
,

 
 
3
1
,

 
 
1
,

 
 
2
3
,

 
 
5
2
8
6
,

 
 
3
,

 
 
2
7
5
7
,

 
 
3
,

 
 
1
,

 
 
1
6
6
3
5
,

 
 
1
9
0
9
,

 
 
2
6
6
7
,

 
 
1
4
4
4
,

 
 
4
1
,

 
 
8
,

 
 
6
6
,

 
 
4
,

 
 
2
7
1
,

 
 
2
3
,

 
 
1
0
6
9
,

 
 
5
2
8
6
,

 
 
3
,

 
 
2
7
5
7
,

 
 
3
,

 
 
1
3
4
9
,

 
 
1
1
4
7
2
,

 
 
9
,

 
 
6
9
7
,

 
 
3
8
3
,

 
 
9
,

 
 
6
0
,

 
 
4
1
0
,

 
 
6
4
,

 
 
1
9
,

 
 
3
4
9
2
,

 
 
4
3
7
3
,

 
 
3
4
3
0
,

 
 
5
,

 
 
3
6
6
,

 
 
5
8
8
,

 
 
5
0
0
,

 
 
5
1
,

 
 
4
0
3
,

 
 
2
,

 
 
1
6
,

 
 
5
1
6
,

 
 
2
2
,

 
 
5
1
,

 
 
8
6
,

 
 
5
1
6
,

 
 
7
1
1
7
,

 
 
5
1
,

 
 
4
3
,

 
 
1
4
2
,

 
 
1
5
,

 
 
1
,

 
 
5
2
8
6
,

 
 
3
,

 
 
2
7
5
7
,

 
 
3
,

 
 
1
3
4
9
,

 
 
1
1
4
7
2
,

 
 
2
3
,

 
 
4
9
4
1
9
,

 
 
3
,

 
 
2
6
8
,

 
 
2
,

 
 
1
1
0
1
,

 
 
1
,

 
 
1
4
9
,

 
 
8
3
,

 
 
5
,

 
 
4
4
1
8
,

 
 
1
1
]
,

 
[
5
3
,

 
 
1
8
,

 
 
1
4
,

 
 
5
2
0
4
,

 
 
1
3
,

 
 
1
7
,

 
 
4
,

 
 
1
5
4
8
,

 
 
4
,

 
 
2
1
4
,

 
 
1
0
2
8
7
,

 
 
5
,

 
 
2
4
,

 
 
4
9
6
0
,

 
 
2
8
8
7
,

 
 
4
5
3
,

 
 
3
,

 
 
6
9
0
]
,

 
[
9
7
1
,

 
 
1
7
9
,

 
 
6
4
5
,

 
 
2
5
0
7
,

 
 
2
6
7
,

 
 
1
5
0
5
,

 
 
1
,

 
 
1
0
2
8
,

 
 
6
5
5
,

 
 
2
6
7
,

 
 
3
,

 
 
1
,

 
 
4
9
3
,

 
 
2
5
0
7
,

 
 
8
,

 
 
8
9
,

 
 
7
6
,

 
 
6
,

 
 
8
7
,

 
 
1
5
6
,

 
 
1
3
,

 
 
2
6
7
,

 
 
2
5
,

 
 
2
3
6
,

 
 
1
,

 
 
1
2
9
6
,

 
 
1
0
,

 
 
5
4
,

 
 
6
0
2
,

 
 
4
6
4
,

 
 
4
5
,

 
 
1
6
,

 
 
4
8
9
9
,

 
 
2
,

 
 
6
,

 
 
3
2
,

 
 
4
5
1
,

 
 
1
,

 
 
1
6
9
,

 
 
9
5
]
,

 
[
3
2
9
,

 
 
1
,

 
 
9
6
8
,

 
 
2
3
5
2
,

 
 
5
,

 
 
6
3
9
,

 
 
4
1
,

 
 
8
,

 
 
4
6
2
,

 
 
9
,

 
 
2
3
3
,

 
 
1
5
4
3
,

 
 
5
4
,

 
 
3
2
4
2
,

 
 
9
,

 
 
1
3
,

 
 
7
5
3
,

 
 
9
0
,

 
 
1
4
,

 
 
1
7
9
5
,

 
 
3
0
5
,

 
 
7
7
9
,

 
 
2
,

 
 
1
3
,

 
 
1
9
8
]
,

 
[
2
0
,

 
 
3
3
6
,

 
 
2
,

 
 
1
6
,

 
 
2
2
6
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
8
3
3
,

 
 
1
2
,

 
 
1
,

 
 
4
5
1
,

 
 
2
1
2
,

 
 
2
8
3
,

 
 
3
2
3
9
,

 
 
7
1
2
,

 
 
2
3
6
,

 
 
2
,

 
 
1
6
0
4
6
8
,

 
 
5
0
,

 
 
2
0
4
,

 
 
1
3
,

 
 
3
3
6
,

 
 
1
0
,

 
 
3
3
,

 
 
2
8
,

 
 
9
4
4
,

 
 
7
1
2
,

 
 
1
7
,

 
 
7
3
0
,

 
 
1
7
,

 
 
4
4
1
,

 
 
2
,

 
 
8
0
5
,

 
 
3
5
7
,

 
 
1
0
8
9
,

 
 
3
3
6
,

 
 
4
4
7
3
,

 
 
3
2
,

 
 
5
6
5
1
,

 
 
7
5
3
,

 
 
5
0
,

 
 
3
2
8
,

 
 
1
2
,

 
 
1
3
4
5
,

 
 
1
5
4
7
0
,

 
 
1
5
,

 
 
1
3
,

 
 
1
0
7
,

 
 
1
5
1
,

 
 
5
0
6
7
,

 
 
1
,

 
 
9
6
8
,

 
 
3
3
6
]
,

 
[
4
0
8
,

 
 
1
2
7
,

 
 
7
,

 
 
2
2
2
2
,

 
 
2
,

 
 
1
6
0
4
6
9
,

 
 
1
9
4
3
,

 
 
1
2
,

 
 
6
8
,

 
 
7
9
,

 
 
5
,

 
 
7
,

 
 
1
0
3
5
,

 
 
3
0
,

 
 
1
9
4
3
,

 
 
1
2
,

 
 
3
0
,

 
 
7
9
,

 
 
2
9
6
,

 
 
1
1
,

 
 
8
,

 
 
1
0
7
6
,

 
 
5
1
1
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
4
1
,

 
 
1
8
,

 
 
6
1
,

 
 
1
2
4
0
,

 
 
1
2
,

 
 
1
,

 
 
1
3
8
,

 
 
1
5
,

 
 
4
1
6
8
,

 
 
1
2
8
3
8
,

 
 
9
3
,

 
 
1
0
,

 
 
1
,

 
 
4
5
6
6
,

 
 
2
6
7
9
,

 
 
2
3
]
,

 
[
9
6
8
,

 
 
3
7
,

 
 
2
5
,

 
 
2
3
1
,

 
 
9
4
,

 
 
3
0
,

 
 
5
8
8
6
,

 
 
1
5
,

 
 
2
,

 
 
6
,

 
 
1
2
,

 
 
1
0
8
9
,

 
 
3
0
,

 
 
5
0
0
6
,

 
 
1
4
3
,

 
 
2
,

 
 
2
0
0
,

 
 
1
7
0
1
]
,

 
[
1
0
9
6
6
,

 
 
5
,

 
 
1
7
7
5
2
,

 
 
3
,

 
 
8
3
3
5
,

 
 
3
9
7
4
,

 
 
2
0
,

 
 
1
5
5
1
,

 
 
2
,

 
 
9
5
6
,

 
 
3
,

 
 
9
2
9
9
,

 
 
8
,

 
 
6
2
5
3
,

 
 
6
0
,

 
 
6
7
8
,

 
 
3
,

 
 
4
3
0
4
,

 
 
8
3
3
5
,

 
 
2
5
,

 
 
1
0
9
6
6
,

 
 
8
8
,

 
 
2
,

 
 
7
2
0
,

 
 
1
0
1
,

 
 
4
6
7
,

 
 
6
6
0
1
,

 
 
1
9
5
1
,

 
 
8
7
,

 
 
2
8
1
8
,

 
 
6
4
,

 
 
7
,

 
 
1
7
8
5
,

 
 
4
,

 
 
3
7
1
,

 
 
1
9
9
9
,

 
 
5
8
6
8
,

 
 
3
,

 
 
1
1
,

 
 
1
2
5
,

 
 
6
6
0
,

 
 
8
7
,

 
 
1
4
,

 
 
1
6
,

 
 
3
1
3
4
,

 
 
2
1
,

 
 
4
7
,

 
 
7
2
0
,

 
 
2
7
0
,

 
 
8
5
1
0
,

 
 
1
9
7
,

 
 
2
,

 
 
7
1
1
,

 
 
7
2
0
,

 
 
1
7
7
5
2
,

 
 
1
9
9
8
,

 
 
3
0
,

 
 
2
3
5
0
,

 
 
1
2
6
8
,

 
 
1
5
,

 
 
1
3
,

 
 
4
1
5
9
,

 
 
1
,

 
 
7
8
4
,

 
 
1
7
0
4
,

 
 
9
3
9
,

 
 
3
,

 
 
7
4
1
8
,

 
 
6
8
0
,

 
 
8
5
5
7
,

 
 
9
3
9
,

 
 
6
0
,

 
 
2
7
4
8
,

 
 
2
7
2
4
,

 
 
2
5
,

 
 
6
1
,

 
 
1
8
8
0
,

 
 
5
0
9
1
,

 
 
3
,

 
 
1
3
,

 
 
9
3
9
,

 
 
1
8
,

 
 
6
3
5
,

 
 
9
5
7
,

 
 
1
7
,

 
 
4
5
5
2
2
,

 
 
1
3
,

 
 
6
6
0
,

 
 
8
,

 
 
1
4
,

 
 
6
7
9
,

 
 
2
6
,

 
 
6
0
,

 
 
5
8
,

 
 
5
0
7
6
,

 
 
2
1
8
,

 
 
5
6
,

 
 
1
6
,

 
 
1
7
3
,

 
 
6
0
,

 
 
6
4
7
2
,

 
 
3
,

 
 
9
2
9
9
,

 
 
5
3
,

 
 
5
6
,

 
 
4
2
5
4
,

 
 
2
3
1
0
,

 
 
1
2
6
8
,

 
 
3
,

 
 
1
,

 
 
1
3
0
7
6
,

 
 
8
5
5
7
,

 
 
3
1
,

 
 
5
1
9
,

 
 
3
2
1
5
8
,

 
 
5
4
,

 
 
8
,

 
 
5
8
,

 
 
4
6
7
,

 
 
1
2
,

 
 
1
9
1
,

 
 
1
8
8
0
,

 
 
2
4
4
6
1
,

 
 
3
,

 
 
1
,

 
 
5
1
9
,

 
 
1
3
0
7
6
,

 
 
1
5
0
9
2
,

 
 
8
7
,

 
 
1
6
,

 
 
1
7
8
7
,

 
 
1
7
,

 
 
3
2
1
5
8
,

 
 
1
0
,

 
 
4
,

 
 
1
8
8
0
,

 
 
7
3
2
,

 
 
3
,

 
 
9
2
9
9
,

 
 
2
6
,

 
 
5
1
,

 
 
3
2
1
5
9
,

 
 
6
6
,

 
 
3
1
1
0
,

 
 
3
,

 
 
7
4
1
8
,

 
 
1
8
8
0
,

 
 
3
2
0
9
,

 
 
5
,

 
 
9
2
,

 
 
3
1
1
0
,

 
 
8
7
,

 
 
1
6
,

 
 
4
4
6
,

 
 
1
7
,

 
 
1
6
3
,

 
 
3
0
9
,

 
 
3
2
6
4
,

 
 
7
4
1
8
,

 
 
7
,

 
 
2
7
6
,

 
 
9
,

 
 
1
1
1
,

 
 
1
9
3
1
,

 
 
1
0
,

 
 
1
7
,

 
 
8
3
5
6
2
,

 
 
8
,

 
 
4
4
6
,

 
 
1
7
,

 
 
1
8
0
5
9
,

 
 
1
0
,

 
 
7
4
1
8
,

 
 
7
3
2
,

 
 
2
6
,

 
 
1
1
,

 
 
6
6
,

 
 
5
,

 
 
9
6
,

 
 
5
8
,

 
 
8
,

 
 
4
,

 
 
3
4
4
0
,

 
 
3
,

 
 
7
4
1
8
,

 
 
9
5
6
,

 
 
8
0
,

 
 
1
0
,

 
 
1
3
0
3
,

 
 
2
5
,

 
 
2
4
4
,

 
 
2
0
5
1
,

 
 
7
3
2
,

 
 
4
,

 
 
4
9
5
0
,

 
 
3
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
5
5
5
,

 
 
3
1
,

 
 
1
9
4
6
,

 
 
3
,

 
 
9
3
4
,

 
 
7
5
0
3
,

 
 
2
7
6
7
6
,

 
 
1
0
1
,

 
 
4
6
7
,

 
 
5
1
3
8
,

 
 
3
1
1
9
,

 
 
4
9
9
1
,

 
 
8
,

 
 
4
6
7
,

 
 
1
2
,

 
 
1
9
1
,

 
 
1
7
,

 
 
4
,

 
 
3
4
4
0
,

 
 
3
,

 
 
9
5
6
,

 
 
3
,

 
 
9
3
4
,

 
 
2
9
0
,

 
 
9
3
4
,

 
 
5
8
,

 
 
5
2
6
7
,

 
 
5
,

 
 
2
8
8
2
,

 
 
1
2
,

 
 
1
3
4
9
,

 
 
7
5
,

 
 
8
,

 
 
1
3
1
4
,

 
 
1
7
,

 
 
4
3
2
,

 
 
6
8
,

 
 
1
5
5
1
,

 
 
2
,

 
 
1
3
4
9
,

 
 
9
5
6
,

 
 
2
6
,

 
 
1
0
,

 
 
6
8
,

 
 
1
7
0
,

 
 
5
4
6
,

 
 
5
2
,

 
 
2
4
,

 
 
4
4
6
,

 
 
1
7
,

 
 
4
,

 
 
1
8
0
5
9
,

 
 
1
5
5
,

 
 
6
2
,

 
 
2
4
,

 
 
9
4
4
,

 
 
2
3
9
1
,

 
 
1
8
8
0
,

 
 
2
2
9
1
,

 
 
5
4
3
,

 
 
4
9
4
2
0
,

 
 
7
8
4
,

 
 
1
3
,

 
 
1
1
0
,

 
 
6
6
,

 
 
7
4
1
8
,

 
 
1
8
8
0
,

 
 
3
2
8
8
,

 
 
3
,

 
 
1
,

 
 
7
8
7
,

 
 
1
5
0
9
2
,

 
 
1
0
3
,

 
 
1
6
,

 
 
4
4
6
,

 
 
1
7
,

 
 
4
5
5
2
2
,

 
 
5
4
,

 
 
8
6
,

 
 
3
5
3
7
8
,

 
 
1
8
8
0
,

 
 
2
2
9
1
,

 
 
5
,

 
 
9
4
4
,

 
 
4
9
4
2
0
,

 
 
7
8
4
,

 
 
1
0
,

 
 
7
4
1
8
,

 
 
7
3
2
,

 
 
5
1
,

 
 
6
6
,

 
 
3
9
,

 
 
1
6
,

 
 
4
4
6
,

 
 
1
7
,

 
 
4
5
5
2
2
,

 
 
1
0
,

 
 
4
,

 
 
4
2
7
3
,

 
 
7
3
2
,

 
 
2
6
,

 
 
5
8
,

 
 
1
2
,

 
 
1
6
0
4
7
0
,

 
 
1
3
4
9
,

 
 
7
5
,

 
 
2
1
,

 
 
7
4
1
8
,

 
 
9
5
6
,

 
 
9
3
,

 
 
1
2
,

 
 
9
2
,

 
 
1
1
5
4
,

 
 
1
5
5
1
,

 
 
1
3
5
,

 
 
1
3
4
9
,

 
 
9
5
6
,

 
 
8
3
5
6
2
,

 
 
8
,

 
 
1
,

 
 
2
2
1
,

 
 
3
1
1
,

 
 
6
4
,

 
 
1
0
,

 
 
6
1
,

 
 
1
1
0
,

 
 
1
,

 
 
5
1
9
,

 
 
7
4
1
8
,

 
 
4
5
5
2
2
,

 
 
5
1
,

 
 
2
5
9
2
8
,

 
 
1
2
0
2
,

 
 
2
,

 
 
5
1
9
,

 
 
2
9
4
3
,

 
 
4
7
7
7
,

 
 
3
1
,

 
 
3
8
8
5
,

 
 
4
6
6
9
,

 
 
3
,

 
 
1
,

 
 
3
4
3
1
,

 
 
1
0
5
6
,

 
 
1
3
1
4
,

 
 
7
5
9
,

 
 
2
2
3
,

 
 
3
,

 
 
1
3
4
9
,

 
 
1
6
0
4
7
1
,

 
 
1
2
5
8
,

 
 
5
,

 
 
9
2
,

 
 
4
3
2
,

 
 
9
8
0
,

 
 
4
9
1
,

 
 
7
0
1
,

 
 
2
4
,

 
 
2
,

 
 
3
2
8
9
,

 
 
1
3
4
9
,

 
 
1
3
0
3
,

 
 
1
2
6
8
,

 
 
1
3
5
,

 
 
7
4
1
8
,

 
 
1
8
8
0
,

 
 
3
0
0
,

 
 
6
3
,

 
 
1
,

 
 
9
0
7
,

 
 
5
6
7
,

 
 
5
3
,

 
 
6
3
,

 
 
1
4
9
,

 
 
2
7
1
,

 
 
4
8
2
9
,

 
 
5
,

 
 
1
4
9
,

 
 
2
7
1
,

 
 
2
4
4
,

 
 
3
7
4
0
3
,

 
 
6
4
,

 
 
1
,

 
 
2
4
9
,

 
 
8
,

 
 
9
,

 
 
2
1
0
,

 
 
4
8
2
9
,

 
 
1
1
7
4
2
,

 
 
5
4
3
,

 
 
9
2
,

 
 
6
1
4
,

 
 
8
3
3
6
,

 
 
9
0
,

 
 
5
,

 
 
1
8
7
1
7
,

 
 
3
,

 
 
1
2
6
8
,

 
 
3
2
9
,

 
 
8
8
,

 
 
8
,

 
 
1
0
1
,

 
 
4
4
6
,

 
 
3
6
,

 
 
1
3
0
,

 
 
4
5
3
2
,

 
 
5
9
,

 
 
1
7
9
5
,

 
 
7
7
9
,

 
 
2
,

 
 
1
3
,

 
 
9
3
0
,

 
 
5
4
3
,

 
 
1
0
,

 
 
1
,

 
 
1
8
0
9
,

 
 
9
3
9
,

 
 
8
0
,

 
 
6
8
0
,

 
 
1
2
6
8
,

 
 
8
6
,

 
 
2
4
9
2
,

 
 
5
5
3
3
,

 
 
8
2
5
0
,

 
 
1
0
,

 
 
7
3
1
,

 
 
3
,

 
 
1
1
2
,

 
 
4
8
2
9
,

 
 
2
4
,

 
 
8
1
9
,

 
 
2
6
5
,

 
 
6
0
8
,

 
 
7
2
9
1
,

 
 
1
0
6
4
9
6
,

 
 
1
0
6
4
9
7
,

 
 
6
2
,

 
 
3
8
3
,

 
 
3
7
4
4
,

 
 
2
,

 
 
1
,

 
 
1
1
4
,

 
 
2
9
4
3
,

 
 
8
,

 
 
6
3
5
,

 
 
9
5
7
,

 
 
1
7
,

 
 
1
9
9
9
,

 
 
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
2
2
7
6
,

 
 
1
0
,

 
 
4
,

 
 
4
6
9
,

 
 
3
,

 
 
1
,

 
 
4
3
7
,

 
 
2
9
4
3
,

 
 
1
7
,

 
 
4
0
5
,

 
 
3
,

 
 
7
9
9
5
,

 
 
9
3
9
,

 
 
5
,

 
 
2
9
4
3
,

 
 
2
7
4
8
,

 
 
2
7
2
4
,

 
 
8
7
8
1
,

 
 
3
2
1
,

 
 
1
0
,

 
 
4
,

 
 
7
3
2
,

 
 
3
,

 
 
9
2
9
9
,

 
 
1
0
,

 
 
2
7
,

 
 
1
3
0
3
,

 
 
7
3
2
,

 
 
1
,

 
 
6
8
0
,

 
 
8
5
5
7
,

 
 
9
3
9
,

 
 
1
,

 
 
4
6
7
0
,

 
 
2
9
4
3
,

 
 
1
2
8
3
9
,

 
 
1
0
9
6
7
,

 
 
5
2
4
,

 
 
9
5
1
1
,

 
 
1
4
7
1
2
,

 
 
5
,

 
 
7
9
9
6
,

 
 
8
3
5
6
2
,

 
 
1
4
7
1
2
,

 
 
1
0
6
4
9
8
,

 
 
1
6
0
4
7
2
,

 
 
7
5
0
3
,

 
 
5
,

 
 
7
2
9
1
,

 
 
1
6
0
4
7
3
,

 
 
1
6
0
4
7
4
,

 
 
1
6
0
4
7
5
,

 
 
5
4
3
0
7
,

 
 
1
6
0
4
7
6
,

 
 
1
6
0
4
7
7
,

 
 
1
6
0
4
7
8
,

 
 
1
2
7
2
5
,

 
 
8
3
5
6
3
,

 
 
1
6
0
4
7
9
,

 
 
1
6
0
4
8
0
,

 
 
1
6
0
4
8
1
,

 
 
1
6
0
4
8
2
,

 
 
1
6
0
4
8
3
,

 
 
7
9
9
6
,

 
 
1
6
0
4
8
4
,

 
 
1
6
0
4
8
5
,

 
 
7
2
9
1
,

 
 
1
0
6
4
9
6
,

 
 
1
0
6
4
9
7
,

 
 
2
5
1
3
9
,

 
 
5
,

 
 
1
0
6
4
9
9
,

 
 
3
,

 
 
7
4
1
8
,

 
 
9
5
6
,

 
 
6
6
2
5
,

 
 
3
,

 
 
7
4
1
8
,

 
 
9
5
6
,

 
 
6
5
7
,

 
 
2
4
0
7
,

 
 
1
5
0
,

 
 
8
8
,

 
 
1
,

 
 
9
3
9
,

 
 
3
2
9
,

 
 
9
0
9
6
,

 
 
5
,

 
 
4
3
5
5
,

 
 
5
,

 
 
3
4
5
,

 
 
3
2
6
,

 
 
2
7
4
,

 
 
1
2
7
2
5
,

 
 
8
5
2
,

 
 
1
6
0
4
8
6
,

 
 
1
6
0
4
8
7
,

 
 
1
0
6
4
9
8
,

 
 
1
6
0
4
8
8
,

 
 
2
1
1
1
,

 
 
1
6
0
4
8
9
,

 
 
1
6
0
4
9
0
,

 
 
5
2
4
,

 
 
1
6
0
4
9
1
,

 
 
2
7
4
8
,

 
 
4
0
,

 
 
1
6
0
4
9
2
,

 
 
4
3
8
,

 
 
7
2
9
1
,

 
 
1
6
0
4
9
3
,

 
 
1
6
0
4
9
4
,

 
 
4
5
5
2
2
,

 
 
4
4
8
5
,

 
 
1
1
5
,

 
 
1
3
4
9
,

 
 
1
2
6
8
,

 
 
1
3
5
,

 
 
7
4
1
8
,

 
 
1
8
8
0
,

 
 
3
0
0
,

 
 
1
5
3
5
,

 
 
1
3
0
3
,

 
 
3
2
1
5
8
,

 
 
1
9
3
,

 
 
1
1
0
7
,

 
 
3
,

 
 
8
3
3
5
,

 
 
2
8
5
,

 
 
7
9
6
,

 
 
6
4
,

 
 
6
2
1
,

 
 
7
1
,

 
 
1
3
1
,

 
 
3
0
6
8
,

 
 
3
2
,

 
 
7
0
6
5
,

 
 
2
0
1
7
,

 
 
3
2
2
5
,

 
 
1
0
0
1
,

 
 
6
8
4
9
,

 
 
8
1
6
,

 
 
2
1
6
]
,

 
[
2
0
3
,

 
 
1
1
5
4
,

 
 
1
2
8
8
,

 
 
9
,

 
 
7
6
7
,

 
 
1
0
,

 
 
2
9
7
2
,

 
 
3
7
2
6
,

 
 
5
,

 
 
7
6
7
,

 
 
3
3
6
9
,

 
 
1
8
,

 
 
7
0
1
,

 
 
4
6
7
,

 
 
1
7
,

 
 
3
9
9
7
,

 
 
5
,

 
 
2
5
,

 
 
2
7
2
,

 
 
5
4
9
5
,

 
 
2
6
,

 
 
1
,

 
 
6
5
7
2
,

 
 
3
4
6
,

 
 
2
8
5
,

 
 
1
,

 
 
2
6
7
,

 
 
1
7
,

 
 
6
,

 
 
1
0
1
,

 
 
7
0
,

 
 
1
,

 
 
3
4
6
,

 
 
3
1
,

 
 
1
,

 
 
8
4
1
,

 
 
8
5
1
,

 
 
1
8
7
1
8
,

 
 
8
,

 
 
1
,

 
 
2
4
9
]
,

 
[
6
0
7
5
8
,

 
 
3
7
4
0
4
,

 
 
1
0
3
,

 
 
6
,

 
 
5
7
3
2
,

 
 
1
0
,

 
 
3
3
,

 
 
1
,

 
 
1
2
1
6
,

 
 
3
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
1
2
,

 
 
6
0
7
5
8
,

 
 
3
7
4
0
4
,

 
 
4
5
6
,

 
 
1
,

 
 
9
7
5
,

 
 
3
,

 
 
2
7
,

 
 
1
2
3
,

 
 
3
,

 
 
1
7
2
,

 
 
3
7
0
,

 
 
1
0
7
,

 
 
1
6
0
4
9
5
,

 
 
9
5
,

 
 
1
2
,

 
 
7
3
7
,

 
 
8
1
7
5
,

 
 
2
5
0
7
,

 
 
2
6
7
,

 
 
1
6
2
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
6
6
2
6
,

 
 
4
4
4
2
,

 
 
4
2
7
4
,

 
 
6
7
4
6
,

 
 
4
4
4
2
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
5
9
8
,

 
 
3
0
3
9
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
1
7
2
6
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
3
2
1
6
0
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
1
2
9
5
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
1
7
,

 
 
5
6
9
,

 
 
2
0
1
5
,

 
 
1
6
3
8
8
,

 
 
7
6
,

 
 
8
,

 
 
4
,

 
 
1
4
5
4
,

 
 
5
5
5
7
,

 
 
3
3
,

 
 
3
2
3
9
,

 
 
4
1
0
,

 
 
2
,

 
 
1
0
1
8
,

 
 
4
6
4
,

 
 
9
,

 
 
5
1
,

 
 
1
9
,

 
 
9
9
,

 
 
1
0
,

 
 
2
8
,

 
 
2
,

 
 
4
,

 
 
4
4
9
6
,

 
 
7
8
8
7
,

 
 
5
,

 
 
7
8
4
8
,

 
 
3
5
5
0
,

 
 
4
4
,

 
 
4
7
,

 
 
3
9
,

 
 
7
0
,

 
 
7
4
,

 
 
5
3
,

 
 
2
1
1
,

 
 
2
2
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
1
1
7
,

 
 
5
3
,

 
 
4
3
1
,

 
 
1
2
2
0
,

 
 
2
,

 
 
9
4
,

 
 
1
1
1
6
,

 
 
2
2
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
2
1
9
,

 
 
1
2
,

 
 
1
1
,

 
 
4
4
,

 
 
4
7
,

 
 
4
5
,

 
 
6
7
6
,

 
 
9
,

 
 
9
4
3
,

 
 
1
3
9
0
9
,

 
 
4
6
4
,

 
 
1
8
,

 
 
1
5
5
,

 
 
1
2
8
,

 
 
1
2
,

 
 
4
7
,

 
 
2
2
2
,

 
 
1
1
,

 
 
8
,

 
 
3
0
2
,

 
 
2
,

 
 
1
1
7
,

 
 
9
,

 
 
9
4
3
,

 
 
5
0
8
,

 
 
6
7
8
,

 
 
1
7
9
4
,

 
 
1
8
2
,

 
 
1
,

 
 
1
3
9
,

 
 
2
1
6
2
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
2
0
2
,

 
 
1
2
5
,

 
 
6
,

 
 
3
9
,

 
 
1
0
1
8
,

 
 
1
,

 
 
6
0
7
5
9
,

 
 
9
,

 
 
3
9
,

 
 
9
4
3
,

 
 
1
6
,

 
 
2
8
2
,

 
 
1
5
,

 
 
1
3
,

 
 
4
9
3
,

 
 
1
2
,

 
 
7
7
9
,

 
 
4
0
1
8
,

 
 
1
6
0
4
9
6
,

 
 
4
0
1
8
,

 
 
1
1
8
4
3
,

 
 
1
4
5
4
,

 
 
6
5
4
6
,

 
 
3
3
,

 
 
4
6
0
9
,

 
 
4
1
0
,

 
 
6
2
,

 
 
1
8
,

 
 
9
4
0
6
,

 
 
1
6
6
3
6
,

 
 
1
,

 
 
5
3
9
,

 
 
3
,

 
 
7
3
2
3
,

 
 
4
0
1
8
,

 
 
5
,

 
 
7
5
2
,

 
 
1
0
,

 
 
1
3
3
2
8
,

 
 
2
1
,

 
 
1
,

 
 
1
0
6
5
0
0
,

 
 
3
3
,

 
 
2
6
8
,

 
 
2
,

 
 
2
0
6
8
,

 
 
2
7
9
6
,

 
 
3
,

 
 
4
0
1
8
,

 
 
5
,

 
 
9
8
6
2
,

 
 
8
8
,

 
 
1
9
3
,

 
 
3
1
,

 
 
1
,

 
 
1
6
0
4
9
7
,

 
 
2
,

 
 
1
3
,

 
 
1
1
5
,

 
 
1
2
9
6
,

 
 
3
,

 
 
1
,

 
 
8
1
7
5
,

 
 
2
5
0
7
,

 
 
5
4
,

 
 
5
8
5
,

 
 
3
5
,

 
 
5
4
7
,

 
 
1
,

 
 
2
6
2
,

 
 
9
3
0
0
,

 
 
2
1
9
7
,

 
 
2
9
4
9
,

 
 
5
3
,

 
 
2
2
6
,

 
 
6
,

 
 
4
8
,

 
 
1
1
,

 
 
1
,

 
 
6
6
4
,

 
 
4
2
2
,

 
 
1
8
,

 
 
9
,

 
 
4
3
3
,

 
 
1
2
4
3
,

 
 
1
4
3
,

 
 
1
5
1
,

 
 
1
,

 
 
2
1
9
7
,

 
 
2
9
4
9
,

 
 
1
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
2
2
7
,

 
 
7
6
,

 
 
5
,

 
 
4
5
,

 
 
4
4
8
,

 
 
1
4
9
,

 
 
1
0
4
7
,

 
 
3
2
1
3
,

 
 
5
,

 
 
4
,

 
 
4
1
7
8
,

 
 
7
3
,

 
 
3
,

 
 
1
,

 
 
2
9
4
9
,

 
 
6
6
,

 
 
1
1
,

 
 
4
5
,

 
 
1
6
,

 
 
2
1
6
7
,

 
 
3
2
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
9
3
0
0
,

 
 
2
1
9
7
,

 
 
7
9
5
,

 
 
1
4
,

 
 
4
9
,

 
 
1
9
,

 
 
2
7
,

 
 
6
0
7
6
0
,

 
 
4
5
3
,

 
 
3
,

 
 
9
5
3
,

 
 
5
4
5
,

 
 
5
9
8
,

 
 
3
0
3
9
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
2
3
1
4
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
4
2
3
5
6
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
3
3
6
6
2
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
7
6
9
,

 
 
1
6
0
,

 
 
2
4
8
4
,

 
 
3
6
3
,

 
 
1
9
0
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
3
3
6
6
2
,

 
 
1
,

 
 
2
6
2
,

 
 
4
9
0
0
,

 
 
2
9
4
9
,

 
 
5
1
0
,

 
 
1
3
5
2
,

 
 
1
9
0
,

 
 
4
1
7
,

 
 
5
6
9
,

 
 
6
0
2
,

 
 
8
3
7
7
,

 
 
1
8
,

 
 
2
,

 
 
1
6
,

 
 
1
5
8
1
,

 
 
8
6
5
0
,

 
 
1
4
,

 
 
8
3
5
6
4
,

 
 
1
7
,

 
 
1
5
0
,

 
 
6
4
4
7
,

 
 
5
,

 
 
1
0
3
3
,

 
 
8
3
9
,

 
 
4
2
2
,

 
 
2
2
0
3
,

 
 
3
1
,

 
 
8
3
5
6
5
,

 
 
1
0
,

 
 
1
,

 
 
3
4
6
5
,

 
 
2
1
6
1
,

 
 
1
8
,

 
 
2
,

 
 
1
6
,

 
 
1
0
8
8
,

 
 
3
3
,

 
 
1
,

 
 
1
1
5
,

 
 
1
3
5
2
,

 
 
1
0
,

 
 
1
,

 
 
3
4
6
5
,

 
 
2
1
6
1
,

 
 
4
1
,

 
 
8
,

 
 
1
6
5
,

 
 
2
,

 
 
1
6
,

 
 
7
7
,

 
 
4
7
,

 
 
1
1
3
7
,

 
 
3
3
,

 
 
4
,

 
 
8
5
,

 
 
1
,

 
 
7
1
4
1
,

 
 
1
6
7
1
,

 
 
7
9
5
,

 
 
2
,

 
 
1
9
,

 
 
3
8
1
6
,

 
 
1
4
0
,

 
 
5
,

 
 
1
6
0
,

 
 
1
3
2
4
,

 
 
1
2
9
,

 
 
7
8
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
1
9
8
,

 
 
4
5
,

 
 
1
6
,

 
 
4
1
1
1
,

 
 
4
,

 
 
1
1
5
,

 
 
1
3
8
7
,

 
 
3
,

 
 
2
2
5
7
,

 
 
4
5
,

 
 
1
6
,

 
 
9
2
5
3
,

 
 
3
2
,

 
 
5
,

 
 
7
7
4
,

 
 
2
,

 
 
1
,

 
 
8
1
7
5
,

 
 
5
3
9
,

 
 
1
,

 
 
3
9
0
3
,

 
 
4
8
1
3
,

 
 
4
0
5
,

 
 
8
,

 
 
2
,

 
 
1
6
,

 
 
3
5
2
0
,

 
 
2
4
9
2
,

 
 
7
1
4
1
,

 
 
4
9
4
2
1
,

 
 
1
8
,

 
 
2
,

 
 
1
6
,

 
 
1
0
3
4
,

 
 
1
0
,

 
 
6
0
2
,

 
 
1
4
,

 
 
2
8
3
2
,

 
 
1
5
,

 
 
1
,

 
 
9
3
0
0
,

 
 
2
1
9
7
,

 
 
8
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
1
6
,

 
 
7
7
4
,

 
 
2
,

 
 
1
6
,

 
 
2
0
4
2
,

 
 
3
2
,

 
 
1
,

 
 
9
3
0
0
,

 
 
2
1
9
7
,

 
 
7
5
9
,

 
 
2
2
,

 
 
2
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
1
7
8
5
,

 
 
1
1
,

 
 
5
1
,

 
 
4
5
,

 
 
1
5
6
4
]
,

 
[
4
2
3
5
7
,

 
 
4
0
3
,

 
 
7
,

 
 
8
1
,

 
 
1
3
2
,

 
 
5
5
1
,

 
 
1
4
,

 
 
4
,

 
 
1
2
5
4
,

 
 
3
,

 
 
1
0
6
5
0
1
,

 
 
5
0
,

 
 
7
4
4
3
,

 
 
2
0
,

 
 
4
2
3
5
7
,

 
 
4
0
3
,

 
 
3
3
,

 
 
4
0
8
]
,

 
[
9
,

 
 
8
,

 
 
1
2
7
4
,

 
 
2
2
,

 
 
5
3
,

 
 
7
7
,

 
 
2
6
8
2
,

 
 
1
,

 
 
1
3
8
,

 
 
1
2
,

 
 
9
4
4
,

 
 
1
,

 
 
3
3
8
,

 
 
2
6
,

 
 
1
3
8
0
,

 
 
1
,

 
 
8
0
8
,

 
 
1
1
9
2
,

 
 
1
2
,

 
 
8
9
2
,

 
 
3
9
,

 
 
1
9
,

 
 
4
,

 
 
8
7
0
,

 
 
2
1
2
,

 
 
1
2
,

 
 
1
,

 
 
4
6
0
]
,

 
[
3
4
4
1
,

 
 
8
6
8
,

 
 
2
6
8
7
,

 
 
8
5
0
,

 
 
8
6
8
,

 
 
5
3
5
,

 
 
2
1
6
,

 
 
5
0
1
,

 
 
2
8
3
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
1
7
,

 
 
4
,

 
 
3
7
7
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
2
1
,

 
 
2
1
5
,

 
 
2
5
,

 
 
3
0
9
,

 
 
5
4
8
,

 
 
2
,

 
 
1
1
7
,

 
 
3
2
0
]
,

 
[
5
,

 
 
3
,

 
 
4
4
3
,

 
 
3
3
6
6
3
,

 
 
8
,

 
 
5
8
,

 
 
9
3
,

 
 
4
9
,

 
 
4
,

 
 
1
1
9
6
,

 
 
1
7
1
5
8
,

 
 
5
7
2
,

 
 
4
7
,

 
 
1
4
0
9
,

 
 
5
2
9
,

 
 
3
9
4
,

 
 
4
2
,

 
 
3
0
9
2
,

 
 
2
6
1
1
,

 
 
1
5
,

 
 
1
,

 
 
1
1
9
6
,

 
 
2
2
1
4
,

 
 
3
,

 
 
2
7
7
8
,

 
 
2
3
6
,

 
 
5
,

 
 
8
,

 
 
7
7
2
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
7
,

 
 
3
7
0
1
,

 
 
2
,

 
 
2
0
6
,

 
 
1
5
,

 
 
1
,

 
 
2
9
7
,

 
 
3
,

 
 
3
1
9
,

 
 
1
7
,

 
 
4
,

 
 
2
8
9
2
,

 
 
4
5
6
,

 
 
6
8
,

 
 
1
2
3
8
,

 
 
1
1
,

 
 
1
8
7
0
,

 
 
5
7
,

 
 
5
9
2
,

 
 
1
0
,

 
 
4
,

 
 
1
5
5
9
,

 
 
1
4
2
3
,

 
 
1
7
7
0
,

 
 
2
6
,

 
 
1
,

 
 
1
1
1
7
,

 
 
1
9
,

 
 
1
8
6
5
,

 
 
1
0
,

 
 
1
3
0
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
1
0
,

 
 
1
2
1
7
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
2
2
7
2
,

 
 
4
4
,

 
 
3
8
1
7
,

 
 
9
3
,

 
 
1
7
,

 
 
2
2
,

 
 
3
3
6
6
3
,

 
 
8
2
9
,

 
 
2
5
,

 
 
5
5
,

 
 
6
1
,

 
 
3
8
1
4
,

 
 
9
9
,

 
 
1
8
7
1
9
,

 
 
3
3
6
6
1
,

 
 
1
,

 
 
2
9
0
6
,

 
 
9
3
5
,

 
 
2
,

 
 
4
,

 
 
6
1
1
4
,

 
 
2
5
3
1
,

 
 
8
1
0
4
,

 
 
3
,

 
 
1
9
2
7
,

 
 
3
,

 
 
1
8
0
,

 
 
8
3
,

 
 
1
7
5
7
,

 
 
1
1
1
,

 
 
2
9
5
,

 
 
1
1
5
4
,

 
 
1
2
8
8
,

 
 
3
1
,

 
 
2
4
7
2
,

 
 
5
4
,

 
 
7
5
4
,

 
 
1
0
,

 
 
4
4
,

 
 
6
1
,

 
 
1
2
0
,

 
 
2
6
,

 
 
3
3
0
,

 
 
1
,

 
 
4
9
9
2
,

 
 
3
,

 
 
4
,

 
 
2
6
5
5
,

 
 
6
1
1
4
]
,

 
[
1
7
8
,

 
 
1
7
8
,

 
 
9
8
,

 
 
3
0
3
,

 
 
3
0
,

 
 
1
8
3
6
9
,

 
 
2
1
1
5
,

 
 
9
,

 
 
7
,

 
 
9
9
,

 
 
1
3
1
,

 
 
1
,

 
 
2
3
6
,

 
 
7
,

 
 
9
9
,

 
 
1
3
1
,

 
 
1
,

 
 
2
3
6
,

 
 
1
1
,

 
 
2
4
,

 
 
6
9
,

 
 
7
,

 
 
2
4
,

 
 
4
1
,

 
 
1
5
,

 
 
1
,

 
 
3
0
3
,

 
 
7
,

 
 
2
4
,

 
 
4
1
,

 
 
1
5
,

 
 
1
,

 
 
3
0
3
,

 
 
8
0
,

 
 
5
1
,

 
 
1
8
,

 
 
4
0
,

 
 
4
8
8
,

 
 
7
3
,

 
 
1
,

 
 
1
3
2
,

 
 
1
0
6
5
0
2
,

 
 
4
7
,

 
 
1
6
1
4
,

 
 
4
8
8
,

 
 
1
,

 
 
1
3
2
,

 
 
2
3
7
6
,

 
 
1
,

 
 
1
3
2
,

 
 
2
1
0
7
6
,

 
 
5
,

 
 
2
8
2
8
,

 
 
1
4
7
4
,

 
 
1
0
,

 
 
1
,

 
 
4
3
3
4
,

 
 
1
4
8
,

 
 
3
0
,

 
 
8
1
0
,

 
 
8
0
,

 
 
1
,

 
 
6
0
2
0
,

 
 
5
2
2
3
,

 
 
6
4
8
,

 
 
6
3
4
,

 
 
3
3
,

 
 
1
,

 
 
1
7
7
5
3
,

 
 
1
5
,

 
 
9
,

 
 
3
0
3
,

 
 
1
,

 
 
4
3
5
,

 
 
5
4
,

 
 
7
,

 
 
7
3
6
,

 
 
1
1
,

 
 
2
4
,

 
 
1
,

 
 
1
3
2
,

 
 
3
1
6
9
,

 
 
2
2
8
,

 
 
7
,

 
 
3
4
9
,

 
 
6
3
,

 
 
7
,

 
 
7
0
,

 
 
1
3
0
,

 
 
2
2
8
,

 
 
1
2
2
,

 
 
9
8
4
,

 
 
2
6
,

 
 
7
,

 
 
7
0
,

 
 
3
8
,

 
 
7
,

 
 
6
8
7
,

 
 
9
,

 
 
3
0
3
,

 
 
1
1
,

 
 
8
,

 
 
7
3
,

 
 
2
,

 
 
6
,

 
 
8
9
,

 
 
2
6
,

 
 
1
1
,

 
 
2
4
,

 
 
9
3
7
,

 
 
2
2
,

 
 
5
3
3
,

 
 
5
,

 
 
5
7
8
,

 
 
9
8
4
,

 
 
2
,

 
 
1
6
,

 
 
6
6
3
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
5
5
,

 
 
3
0
,

 
 
5
9
5
0
,

 
 
2
1
1
5
,

 
 
1
2
,

 
 
1
,

 
 
1
4
0
0
,

 
 
7
,

 
 
9
9
,

 
 
8
4
6
,

 
 
6
,

 
 
7
,

 
 
8
1
,

 
 
3
1
,

 
 
8
8
3
,

 
 
1
3
0
6
,

 
 
2
5
9
5
,

 
 
7
2
,

 
 
4
,

 
 
2
5
9
5
,

 
 
5
,

 
 
7
,

 
 
5
8
5
,

 
 
3
1
,

 
 
4
,

 
 
1
0
2
,

 
 
2
3
9
1
,

 
 
1
1
6
3
,

 
 
7
1
9
,

 
 
1
9
,

 
 
4
,

 
 
7
8
1
4
,

 
 
3
0
3
]
,

 
[
6
,

 
 
5
6
,

 
 
1
6
,

 
 
3
3
6
5
,

 
 
1
6
4
,

 
 
4
,

 
 
7
0
3
6
,

 
 
2
2
6
2
5
,

 
 
6
2
,

 
 
8
,

 
 
1
5
5
,

 
 
3
1
8
4
,

 
 
2
,

 
 
3
4
,

 
 
3
9
4
,

 
 
1
1
,

 
 
3
9
7
,

 
 
3
7
,

 
 
1
6
2
4
,

 
 
9
,

 
 
7
5
,

 
 
4
8
,

 
 
6
,

 
 
8
3
4
,

 
 
1
0
,

 
 
1
3
,

 
 
2
4
4
]
,

 
[
1
1
,

 
 
5
2
6
,

 
 
2
,

 
 
3
7
,

 
 
4
8
,

 
 
5
2
,

 
 
8
,

 
 
2
4
2
2
,

 
 
1
1
3
,

 
 
3
9
0
3
,

 
 
2
6
,

 
 
7
1
,

 
 
5
2
1
,

 
 
1
1
1
0
,

 
 
2
3
1
,

 
 
1
4
5
,

 
 
1
3
,

 
 
7
6
,

 
 
2
,

 
 
1
5
4
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
1
4
9
,

 
 
1
8
,

 
 
3
5
5
,

 
 
4
,

 
 
1
7
4
,

 
 
8
0
1
,

 
 
8
4
,

 
 
6
,

 
 
3
9
,

 
 
2
8
9
,

 
 
1
,

 
 
2
0
2
2
,

 
 
4
5
1
8
,

 
 
3
2
,

 
 
1
,

 
 
1
1
0
,

 
 
7
1
,

 
 
7
0
1
,

 
 
1
6
6
0
,

 
 
2
,

 
 
5
1
7
,

 
 
2
1
,

 
 
9
3
,

 
 
3
1
6
7
,

 
 
7
6
,

 
 
1
9
,

 
 
4
,

 
 
1
7
1
,

 
 
3
2
,

 
 
1
0
,

 
 
1
,

 
 
3
4
6
5
,

 
 
2
1
6
1
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
3
9
9
,

 
 
1
1
2
2
,

 
 
3
2
,

 
 
1
,

 
 
1
1
0
,

 
 
4
6
]
,

 
[
4
,

 
 
6
6
4
7
,

 
 
1
5
,

 
 
1
,

 
 
8
1
0
,

 
 
1
4
3
6
7
,

 
 
6
,

 
 
1
8
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
1
3
2
,

 
 
3
0
3
5
,

 
 
1
3
2
0
,

 
 
7
,

 
 
7
0
,

 
 
5
,

 
 
7
2
,

 
 
6
0
7
6
1
,

 
 
1
0
,

 
 
4
7
7
,

 
 
2
1
,

 
 
6
,

 
 
3
6
7
,

 
 
2
5
8
,

 
 
6
,

 
 
4
,

 
 
1
1
4
1
,

 
 
2
6
,

 
 
1
0
,

 
 
1
,

 
 
4
5
3
,

 
 
1
1
0
2
,

 
 
4
9
,

 
 
1
4
8
8
5
,

 
 
1
1
,

 
 
7
3
,

 
 
5
,

 
 
9
3
0
1
,

 
 
1
1
,

 
 
3
8
2
,

 
 
2
7
8
,

 
 
3
7
,

 
 
1
5
5
2
,

 
 
1
3
,

 
 
1
8
7
2
0
,

 
 
6
6
4
7
,

 
 
1
5
,

 
 
1
,

 
 
8
1
0
,

 
 
9
9
8
7
,

 
 
3
4
,

 
 
2
8
6
3
7
,

 
 
9
9
8
7
,

 
 
3
4
,

 
 
6
3
,

 
 
6
,

 
 
3
1
5
,

 
 
1
7
4
4
9
]
,

 
[
1
9
3
,
 
9
,
 
1
,
 
6
1
2
,
 
8
,
 
1
,
 
1
4
3
,
 
2
0
2
,
 
2
,
 
1
0
6
5
0
3
,
 
9
5
]
,

 
[
1
6
0
4
9
8
,

 
 
3
2
7
,

 
 
8
,

 
 
7
5
0
,

 
 
7
,

 
 
6
5
0
,

 
 
1
8
7
2
1
,

 
 
2
4
,

 
 
4
4
,

 
 
3
7
7
3
,

 
 
1
4
5
,

 
 
7
4
7
,

 
 
8
6
,

 
 
1
5
,

 
 
1
2
7
2
6
,

 
 
1
5
0
,

 
 
5
,

 
 
1
5
1
,

 
 
7
,

 
 
6
5
,

 
 
4
2
9
4
,

 
 
3
7
4
,

 
 
4
7
2
3
,

 
 
9
9
,

 
 
5
8
,

 
 
6
1
9
7
,

 
 
1
5
0
,

 
 
5
,

 
 
1
5
1
,

 
 
5
1
,

 
 
2
1
5
9
,

 
 
9
2
,

 
 
6
8
3
0
,

 
 
1
9
0
4
8
,

 
 
1
3
,

 
 
1
0
,

 
 
4
6
7
1
,

 
 
2
3
3
3
,

 
 
3
0
1
6
,

 
 
2
,

 
 
1
2
7
2
6
,

 
 
7
7
,

 
 
1
,

 
 
5
7
4
6
,

 
 
8
6
,

 
 
1
4
,

 
 
1
,

 
 
2
4
9
,

 
 
1
5
1
,

 
 
1
,

 
 
1
3
9
0
,

 
 
3
,

 
 
1
8
7
2
1
,

 
 
1
,

 
 
5
8
0
6
,

 
 
5
,

 
 
8
5
5
8
,

 
 
6
0
7
6
2
,

 
 
8
6
,

 
 
5
8
,

 
 
1
0
,

 
 
1
9
1
7
,

 
 
1
2
,

 
 
3
0
1
6
,

 
 
8
4
,

 
 
1
5
0
,

 
 
6
0
,

 
 
1
3
2
4
,

 
 
1
5
1
,

 
 
1
8
7
2
1
,

 
 
7
4
7
,

 
 
5
3
0
6
,

 
 
1
6
0
4
9
9
,

 
 
8
6
,

 
 
1
5
9
7
,

 
 
9
3
,

 
 
1
5
0
,

 
 
1
8
7
2
1
,

 
 
6
0
7
6
3
]
,

 
[
4
1
5
,
 
7
,
 
2
3
9
,
 
7
0
,
 
9
5
]
,

 
[
2
2
6
2
6
,

 
 
1
0
6
5
0
4
,

 
 
2
0
,

 
 
7
2
6
,

 
 
1
5
,

 
 
2
2
6
2
6
,

 
 
1
0
6
5
0
4
,

 
 
6
5
7
3
,

 
 
1
2
8
,

 
 
3
,

 
 
1
7
2
,

 
 
4
5
0
,

 
 
5
,

 
 
5
8
0
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
7
2
,

 
 
6
9
6
,

 
 
7
,

 
 
1
9
,

 
 
1
5
2
6
,

 
 
1
1
,

 
 
5
0
,

 
 
3
7
9
,

 
 
2
2
,

 
 
3
9
5
,

 
 
2
1
5
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
1
5
2
,

 
 
3
0
9
5
,

 
 
4
0
5
9
,

 
 
6
4
0
2
,

 
 
5
7
4
7
]
,

 
[
7
0
,
 
1
,
 
4
8
3
,
 
3
,
 
1
,
 
5
4
3
0
8
]
,

 
[
7
,

 
 
6
5
,

 
 
9
,

 
 
2
0
,

 
 
4
,

 
 
1
6
8
9
4
,

 
 
9
4
,

 
 
4
,

 
 
1
6
0
5
0
0
,

 
 
5
,

 
 
3
1
2
8
,

 
 
1
0
,

 
 
5
4
9
,

 
 
7
,

 
 
3
6
0
,

 
 
6
,

 
 
1
5
8
8
2
,

 
 
2
8
0
,

 
 
5
3
,

 
 
1
6
9
4
,

 
 
1
9
,

 
 
5
5
,

 
 
5
8
,

 
 
4
8
3
,

 
 
7
2
,

 
 
1
5
6
0
,

 
 
7
6
,

 
 
3
,

 
 
1
6
0
5
0
1
]
,

 
[
2
2
5
3
,
 
1
3
6
5
,
 
6
8
3
1
,
 
3
1
5
8
,
 
2
2
5
3
,
 
1
3
6
5
,
 
6
8
3
1
,
 
3
1
5
8
,
 
1
8
9
2
,
 
9
1
2
,
 
8
0
0
,
 
8
7
,
 
7
1
0
]
,

 
[
2
8
0
,

 
 
1
,

 
 
1
6
9
,

 
 
6
,

 
 
1
0
3
5
,

 
 
3
7
,

 
 
8
,

 
 
9
3
1
,

 
 
5
,

 
 
7
,

 
 
4
1
6
9
,

 
 
1
0
,

 
 
3
9
6
7
7
,

 
 
3
6
,

 
 
5
4
3
0
,

 
 
1
2
1
,

 
 
1
0
,

 
 
9
,

 
 
3
5
4
]
,

 
[
7
4
5
,

 
 
2
5
5
,

 
 
9
,

 
 
2
4
,

 
 
3
7
,

 
 
1
0
6
7
,

 
 
1
,

 
 
1
4
4
7
,

 
 
4
4
6
0
,

 
 
4
5
0
8
,

 
 
2
,

 
 
1
6
,

 
 
2
2
3
,

 
 
3
,

 
 
8
7
3
3
,

 
 
2
5
9
5
,

 
 
5
,

 
 
3
1
3
,

 
 
1
7
,

 
 
7
,

 
 
7
0
,

 
 
4
5
0
8
,

 
 
8
,

 
 
2
2
3
,

 
 
3
,

 
 
5
4
3
0
9
,

 
 
5
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
2
2
3
,

 
 
3
,

 
 
1
0
2
1
,

 
 
2
8
6
3
8
,

 
 
2
1
,

 
 
1
7
4
5
0
,

 
 
5
,

 
 
4
0
,

 
 
1
4
1
,

 
 
2
2
7
,

 
 
9
3
2
,

 
 
4
9
5
,

 
 
2
0
,

 
 
9
5
6
,

 
 
4
2
,

 
 
3
6
9
,

 
 
5
7
,

 
 
5
8
,

 
 
3
8
6
6
,

 
 
3
2
,

 
 
2
5
1
0
,

 
 
9
3
,

 
 
6
6
7
8
,

 
 
1
1
6
3
,

 
 
1
7
,

 
 
1
0
,

 
 
8
2
3
,

 
 
4
9
4
0
0
,

 
 
6
6
7
8
,

 
 
1
1
6
3
,

 
 
1
4
,

 
 
1
,

 
 
2
0
1
8
,

 
 
5
3
5
8
,

 
 
4
1
3
5
,

 
 
1
0
,

 
 
2
6
7
4
6
,

 
 
6
9
7
9
9
,

 
 
4
9
,

 
 
1
5
6
2
,

 
 
9
,

 
 
6
,

 
 
6
1
2
9
,

 
 
1
8
,

 
 
4
0
,

 
 
4
,

 
 
1
4
3
1
,

 
 
3
,

 
 
9
0
3
6
,

 
 
8
8
0
,

 
 
7
5
,

 
 
4
0
,

 
 
1
,

 
 
1
3
0
6
,

 
 
2
4
2
7
,

 
 
7
5
,

 
 
1
3
7
,

 
 
2
8
5
9
,

 
 
2
,

 
 
1
5
9
5
,

 
 
3
,

 
 
4
5
0
8
,

 
 
1
7
,

 
 
4
,

 
 
1
0
2
,

 
 
6
5
7
4
,

 
 
2
2
3
,

 
 
3
,

 
 
2
5
1
0
,

 
 
5
,

 
 
5
3
,

 
 
4
0
,

 
 
6
5
,

 
 
1
6
4
,

 
 
8
1
0
5
,

 
 
1
9
7
7
,

 
 
5
,

 
 
9
8
2
,

 
 
1
0
,

 
 
4
,

 
 
2
8
5
2
,

 
 
1
0
0
9
8
,

 
 
3
6
1
,

 
 
1
8
1
,

 
 
3
5
4
,

 
 
3
8
,

 
 
8
8
0
,

 
 
6
,

 
 
1
9
8
1
5
,

 
 
1
5
,

 
 
2
8
,

 
 
6
2
4
,

 
 
2
3
6
,

 
 
1
,

 
 
1
1
0
,

 
 
7
5
,

 
 
1
0
,

 
 
1
,

 
 
3
2
5
,

 
 
2
4
4
,

 
 
6
5
]
,

 
[
1
3
6
5
,

 
 
9
8
1
,

 
 
6
5
5
,

 
 
1
4
1
8
,

 
 
7
,

 
 
2
7
5
,

 
 
9
,

 
 
1
,

 
 
1
3
2
0
9
,

 
 
7
,

 
 
1
7
3
,

 
 
2
4
,

 
 
1
4
,

 
 
5
9
1
0
,

 
 
5
,

 
 
1
2
6
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
3
6
,

 
 
1
,

 
 
1
7
4
,

 
 
2
6
,

 
 
3
8
,

 
 
8
,

 
 
1
3
,

 
 
4
2
,

 
 
1
,

 
 
5
3
9
,

 
 
1
4
,

 
 
2
7
9
0
,

 
 
2
7
8
2
,

 
 
2
4
,

 
 
1
1
,

 
 
1
4
,

 
 
1
8
8
4
,

 
 
3
2
,

 
 
1
,

 
 
1
2
1
7
9
,

 
 
1
9
,

 
 
7
,

 
 
1
4
,

 
 
7
7
5
,

 
 
1
,

 
 
4
5
7
,

 
 
1
7
,

 
 
6
3
6
,

 
 
8
,

 
 
1
1
,

 
 
1
4
,

 
 
4
,

 
 
1
6
6
,

 
 
8
,

 
 
1
1
,

 
 
1
4
,

 
 
1
0
5
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
4
,

 
 
1
2
1
,

 
 
2
5
5
5
,

 
 
7
5
,

 
 
1
7
,

 
 
2
,

 
 
7
8
,

 
 
3
2
1
6
1
,

 
 
3
3
6
8
,

 
 
8
,

 
 
1
4
,

 
 
1
7
,

 
 
6
3
2
,

 
 
1
7
,

 
 
1
1
,

 
 
4
8
7
1
,

 
 
4
0
8
,

 
 
2
4
,

 
 
8
,

 
 
1
1
,

 
 
1
4
,

 
 
1
,

 
 
7
7
,

 
 
1
2
6
1
8
,

 
 
3
,

 
 
1
0
5
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
7
2
5
3
,

 
 
1
,

 
 
7
2
9
2
,

 
 
3
,

 
 
8
5
,

 
 
3
2
9
,

 
 
1
4
0
4
3
,

 
 
5
,

 
 
6
9
3
,

 
 
8
,

 
 
1
,

 
 
6
9
8
0
0
,

 
 
3
,

 
 
1
,

 
 
7
9
,

 
 
1
,

 
 
7
7
,

 
 
4
3
4
,

 
 
1
3
3
,

 
 
2
,

 
 
2
1
7
4
,

 
 
2
2
,

 
 
1
1
,

 
 
4
5
,

 
 
1
6
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
4
,

 
 
2
2
,

 
 
3
6
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
2
2
8
,

 
 
9
,

 
 
7
,

 
 
3
0
9
,

 
 
3
5
7
,

 
 
1
7
3
,

 
 
1
,

 
 
1
0
5
,

 
 
1
5
1
,

 
 
1
1
,

 
 
2
4
,

 
 
1
8
7
,

 
 
2
4
,

 
 
1
4
,

 
 
1
,

 
 
1
1
2
9
,

 
 
3
9
6
7
8
,

 
 
5
,

 
 
6
5
2
0
,

 
 
3
8
,

 
 
8
,

 
 
1
,

 
 
2
4
9
,

 
 
7
8
,

 
 
2
7
1
3
,

 
 
1
5
,

 
 
1
,

 
 
3
8
0
7
,

 
 
3
,

 
 
1
3
,

 
 
4
5
7
,

 
 
1
1
,

 
 
8
,

 
 
2
0
6
5
8
,

 
 
1
1
,

 
 
8
,

 
 
1
5
2
6
3
,

 
 
7
,

 
 
8
1
,

 
 
3
5
7
,

 
 
3
1
0
,

 
 
1
,

 
 
1
0
5
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
1
4
5
3
,

 
 
5
0
7
,

 
 
7
7
5
,

 
 
5
,

 
 
3
7
6
,

 
 
2
9
3
1
,

 
 
7
,

 
 
8
5
9
,

 
 
9
,

 
 
1
4
4
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
2
1
2
,

 
 
2
,

 
 
2
5
6
,

 
 
1
1
,

 
 
1
2
7
,

 
 
2
5
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
9
,

 
 
6
,

 
 
5
,

 
 
4
0
,

 
 
6
1
,

 
 
1
8
0
,

 
 
2
4
1
3
,

 
 
4
5
,

 
 
8
9
7
7
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
3
1
4
,

 
 
2
1
,

 
 
1
7
2
9
,

 
 
1
4
0
,

 
 
5
0
,

 
 
6
3
,

 
 
1
,

 
 
7
9
,

 
 
3
0
8
0
9
,

 
 
1
,

 
 
1
5
8
8
3
,

 
 
7
,

 
 
7
0
,

 
 
1
1
,

 
 
2
4
,

 
 
3
4
8
4
,

 
 
7
6
,

 
 
3
2
,

 
 
1
,

 
 
2
8
4
,

 
 
1
6
0
5
0
2
,

 
 
8
3
5
6
6
,

 
 
2
6
,

 
 
3
8
4
0
,

 
 
9
,

 
 
2
4
,

 
 
1
,

 
 
1
1
4
,

 
 
1
7
2
9
,

 
 
2
3
6
]
,

 
[
6
,
 
1
8
,
 
4
,
 
3
0
1
,
 
6
7
,
 
5
,
 
2
0
,
 
5
9
9
9
,
 
4
2
9
,
 
5
1
7
7
]
,

 
[
2
1
0
7
7
,
 
7
6
9
,
 
3
9
6
,
 
3
2
1
6
2
,
 
9
9
8
,
 
1
6
3
8
9
,
 
4
6
]
,

 
[
1
1
5
,

 
 
4
1
6
7
,

 
 
9
2
5
4
,

 
 
1
4
2
8
,

 
 
9
2
5
4
,

 
 
1
4
2
8
,

 
 
3
7
6
,

 
 
5
7
8
,

 
 
9
2
5
4
,

 
 
4
8
7
,

 
 
1
3
,

 
 
1
0
7
,

 
 
8
,

 
 
4
,

 
 
4
4
4
,

 
 
9
2
5
4
,

 
 
4
8
7
,

 
 
3
7
6
,

 
 
1
7
7
5
4
,

 
 
9
2
5
4
,

 
 
6
8
2
,

 
 
3
7
6
,

 
 
5
3
3
,

 
 
9
2
5
4
,

 
 
1
0
6
5
0
5
,

 
 
4
5
6
0
,

 
 
1
3
2
0
,

 
 
9
2
5
4
,

 
 
1
0
6
5
0
6
,

 
 
9
2
5
4
,

 
 
9
2
5
4
,

 
 
9
2
5
4
,

 
 
6
0
7
6
4
,

 
 
3
7
0
,

 
 
8
5
4
,

 
 
3
3
6
6
4
,

 
 
1
,

 
 
1
0
7
,

 
 
1
0
,

 
 
4
5
6
0
]
,

 
[
8
1
6
,

 
 
1
1
1
2
,

 
 
5
3
5
,

 
 
2
1
6
,

 
 
3
3
6
6
5
,

 
 
1
8
1
,

 
 
4
6
,

 
 
3
5
,

 
 
1
4
1
,

 
 
4
2
2
,

 
 
3
3
,

 
 
4
0
,

 
 
3
3
6
6
5
,

 
 
2
4
,

 
 
7
0
3
7
,

 
 
2
,

 
 
1
,

 
 
1
8
3
3
,

 
 
1
1
6
,

 
 
9
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
4
1
,

 
 
8
1
6
,

 
 
3
3
4
8
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
6
7
1
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
2
9
6
8
4
,

 
 
6
0
7
6
5
,

 
 
2
5
1
4
0
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
2
6
7
4
7
,

 
 
8
0
7
3
]
,

 
[
3
7
4
,

 
 
9
3
1
,

 
 
8
,

 
 
9
3
1
,

 
 
4
1
,

 
 
1
8
,

 
 
1
9
7
,

 
 
1
0
6
5
0
7
,

 
 
3
,

 
 
1
2
1
8
0
,

 
 
1
5
6
5
,

 
 
1
,

 
 
3
1
1
5
,

 
 
8
0
,

 
 
5
1
,

 
 
1
8
,

 
 
8
5
8
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
4
1
3
,

 
 
5
9
2
8
]
,

 
[
7
,

 
 
1
1
7
6
,

 
 
1
,

 
 
2
8
0
1
,

 
 
2
2
,

 
 
2
5
9
,

 
 
1
5
3
,

 
 
2
9
1
7
,

 
 
9
,

 
 
1
1
,

 
 
5
6
,

 
 
4
6
0
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
2
0
7
,

 
 
1
,

 
 
6
8
1
1
]
,

 
[
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
0
2
4
,

 
 
4
0
1
9
,

 
 
5
5
5
8
,

 
 
1
7
6
,

 
 
1
4
6
0
,

 
 
1
5
5
3
,

 
 
4
0
6
,

 
 
2
8
,

 
 
1
3
1
3
,

 
 
1
6
2
,

 
 
4
5
2
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
0
2
4
,

 
 
5
4
6
6
,

 
 
2
1
,

 
 
1
1
1
1
,

 
 
3
8
1
8
,

 
 
1
,

 
 
4
5
6
7
,

 
 
1
2
,

 
 
1
,

 
 
1
1
0
8
,

 
 
7
9
2
9
,

 
 
6
1
9
,

 
 
5
2
6
,

 
 
1
5
5
,

 
 
3
1
3
,

 
 
1
4
3
,

 
 
6
5
,

 
 
6
,

 
 
1
0
3
,

 
 
1
3
5
1
,

 
 
1
1
,

 
 
7
8
,

 
 
1
8
,

 
 
1
,

 
 
8
6
5
,

 
 
6
9
8
,

 
 
3
4
5
,

 
 
5
3
5
,

 
 
6
5
7
3
]
,

 
[
2
8
0
,

 
 
2
,

 
 
1
6
6
3
7
,

 
 
2
6
,

 
 
7
2
,

 
 
3
3
,

 
 
1
3
0
7
7
,

 
 
1
4
0
,

 
 
8
9
,

 
 
1
,

 
 
1
1
4
,

 
 
2
2
7
5
,

 
 
8
6
,

 
 
6
7
4
,

 
 
4
9
,

 
 
1
5
,

 
 
3
0
,

 
 
1
7
0
,

 
 
1
2
4
,

 
 
5
,

 
 
6
9
,

 
 
7
,

 
 
2
4
,

 
 
9
7
0
,

 
 
1
2
,

 
 
1
2
1
,

 
 
3
6
,

 
 
1
2
8
,

 
 
3
6
,

 
 
3
5
2
,

 
 
4
9
,

 
 
4
1
4
5
,

 
 
2
5
,

 
 
3
5
2
,

 
 
4
6
2
,

 
 
2
6
,

 
 
1
1
,

 
 
1
5
3
,

 
 
4
4
9
,

 
 
3
,

 
 
3
8
4
8
,

 
 
1
0
6
5
0
8
]
,

 
[
1
0
7
6
,

 
 
8
2
,

 
 
3
,

 
 
9
,

 
 
2
7
0
,

 
 
8
,

 
 
1
5
0
9
,

 
 
1
5
6
8
,

 
 
9
6
,

 
 
2
1
,

 
 
7
9
9
,

 
 
5
4
3
1
0
,

 
 
1
,

 
 
1
6
8
7
,

 
 
9
9
,

 
 
2
4
1
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
0
6
5
0
9
,

 
 
4
,

 
 
1
1
0
5
0
,

 
 
8
2
5
1
,

 
 
1
9
4
1
1
,

 
 
1
0
6
5
0
9
,

 
 
3
2
,

 
 
6
6
0
,

 
 
4
2
,

 
 
1
6
0
5
0
3
,

 
 
1
6
0
5
0
4
,

 
 
8
3
6
,

 
 
1
3
,

 
 
1
6
8
7
,

 
 
2
4
,

 
 
4
7
,

 
 
8
0
4
,

 
 
5
6
8
0
,

 
 
3
,

 
 
6
3
8
4
,

 
 
2
1
,

 
 
4
4
,

 
 
6
4
2
9
,

 
 
8
3
6
,

 
 
2
5
,

 
 
3
7
4
0
5
,

 
 
1
1
,

 
 
2
4
,

 
 
1
3
7
4
3
,

 
 
1
7
,

 
 
4
,

 
 
2
5
0
2
,

 
 
1
3
7
4
4
]
,

 
[
7
,

 
 
4
9
,

 
 
6
5
8
,

 
 
9
,

 
 
1
,

 
 
1
9
4
0
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
1
7
5
4
,

 
 
1
4
,

 
 
3
2
,

 
 
3
7
,

 
 
1
0
,

 
 
1
0
3
6
,

 
 
3
,

 
 
9
,

 
 
7
,

 
 
1
2
7
,

 
 
2
1
9
,

 
 
9
,

 
 
3
0
,

 
 
3
4
5
,

 
 
6
4
,

 
 
5
,

 
 
3
0
,

 
 
3
9
7
4
,

 
 
2
,

 
 
5
6
3
,

 
 
7
4
,

 
 
5
,

 
 
3
8
5
,

 
 
1
9
4
0
,

 
 
3
9
,

 
 
1
6
,

 
 
4
3
1
3
,

 
 
1
4
,

 
 
1
6
,

 
 
1
4
6
,

 
 
1
1
,

 
 
8
,

 
 
1
1
4
5
,

 
 
5
1
1
,

 
 
5
,

 
 
2
6
9
6
,

 
 
7
8
8
8
,

 
 
4
9
2
8
,

 
 
1
0
,

 
 
4
8
9
,

 
 
1
,

 
 
7
2
3
,

 
 
9
,

 
 
4
1
,

 
 
1
8
,

 
 
4
4
,

 
 
3
7
4
0
6
,

 
 
1
5
,

 
 
2
8
,

 
 
1
0
,

 
 
8
5
,

 
 
1
6
6
3
8
,

 
 
1
5
,

 
 
6
5
6
,

 
 
4
5
,

 
 
1
6
,

 
 
4
3
1
3
]
,

 
[
2
0
5
,

 
 
5
9
,

 
 
4
6
6
,

 
 
3
5
,

 
 
2
0
,

 
 
3
2
7
9
,

 
 
2
2
,

 
 
7
8
5
,

 
 
1
4
,

 
 
8
5
1
1
,

 
 
3
2
,

 
 
2
6
1
,

 
 
5
9
2
,

 
 
1
0
6
,

 
 
7
,

 
 
1
0
3
,

 
 
5
2
0
,

 
 
7
8
,

 
 
7
,

 
 
3
3
2
,

 
 
2
7
7
2
,

 
 
7
5
3
0
,

 
 
3
9
6
6
,

 
 
2
6
,

 
 
7
,

 
 
4
3
,

 
 
9
4
,

 
 
1
,

 
 
1
3
9
,

 
 
3
4
3
2
,

 
 
2
2
,

 
 
7
,

 
 
2
3
9
,

 
 
4
9
8
,

 
 
1
0
6
,

 
 
1
7
1
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
5
,

 
 
6
9
3
,

 
 
1
0
6
,

 
 
4
6
,

 
 
2
,

 
 
3
7
]
,

 
[
3
5
,
 
2
0
2
0
3
,
 
6
9
2
,
 
2
,
 
3
9
6
7
9
,
 
7
,
 
1
9
,
 
4
4
,
 
4
0
5
,
 
1
1
,
 
5
9
3
,
 
3
7
,
 
1
5
,
 
2
9
8
,
 
9
]
,

 
[
3
0
4
0
,
 
5
,
 
3
2
1
6
3
,
 
1
,
 
1
4
9
,
 
2
5
5
,
 
1
2
5
4
,
 
1
7
4
5
1
,
 
1
2
3
5
,
 
4
7
3
]
,

 
[
4
1
5
,

 
 
6
6
,

 
 
7
5
6
,

 
 
1
8
7
6
,

 
 
9
,

 
 
1
8
,

 
 
1
0
6
9
,

 
 
4
2
0
,

 
 
2
5
,

 
 
6
0
,

 
 
4
8
5
5
,

 
 
7
3
8
8
,

 
 
1
6
,

 
 
4
4
0
,

 
 
1
5
,

 
 
1
,

 
 
6
0
2
1
,

 
 
2
9
,

 
 
5
,

 
 
1
4
,

 
 
1
5
,

 
 
6
4
,

 
 
4
9
,

 
 
1
2
8
2
,

 
 
6
9
,

 
 
1
1
,

 
 
3
9
7
,

 
 
1
2
8
,

 
 
5
8
,

 
 
4
6
9
,

 
 
2
,

 
 
3
7
,

 
 
7
,

 
 
1
7
3
2
,

 
 
1
0
,

 
 
2
1
9
5
,

 
 
1
2
,

 
 
7
2
0
,

 
 
1
9
1
2
,

 
 
6
2
,

 
 
1
8
,

 
 
1
5
5
,

 
 
4
2
8
4
,

 
 
2
,

 
 
1
2
2
2
,

 
 
1
,

 
 
6
5
6
]
,

 
[
3
7
9
,

 
 
3
3
6
,

 
 
1
7
8
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
3
3
6
,

 
 
2
8
6
3
9
,

 
 
1
2
,

 
 
4
,

 
 
1
1
2
4
,

 
 
5
9
8
,

 
 
3
7
9
,

 
 
3
9
,

 
 
2
5
9
,

 
 
3
4
,

 
 
9
,

 
 
1
1
,

 
 
1
9
5
,

 
 
2
,

 
 
1
9
,

 
 
1
3
0
,

 
 
6
1
8
,

 
 
5
3
6
,

 
 
2
,

 
 
6
1
,

 
 
3
3
6
6
6
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
1
8
4
4
,

 
 
1
2
0
6
8
,

 
 
5
,

 
 
1
1
3
8
1
,

 
 
6
2
5
4
,

 
 
6
6
9
,

 
 
1
0
6
5
1
0
]
,

 
[
7
,

 
 
5
9
,

 
 
3
3
,

 
 
4
0
,

 
 
1
7
8
5
,

 
 
9
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
5
4
7
1
,

 
 
1
7
,

 
 
1
6
0
5
0
5
,

 
 
1
0
,

 
 
1
3
,

 
 
2
5
,

 
 
5
5
,

 
 
6
1
,

 
 
2
3
,

 
 
2
2
,

 
 
2
1
5
,

 
 
3
3
,

 
 
4
0
,

 
 
4
9
,

 
 
4
,

 
 
1
9
5
6
,

 
 
3
9
2
,

 
 
3
,

 
 
1
,

 
 
4
6
5
7
,

 
 
3
,

 
 
8
2
9
5
,

 
 
5
,

 
 
2
0
5
3
,

 
 
1
0
,

 
 
4
,

 
 
1
9
1
8
,

 
 
1
2
6
1
9
,

 
 
3
2
0
3
,

 
 
4
3
,

 
 
5
8
0
3
,

 
 
7
,

 
 
4
9
,

 
 
3
3
2
,

 
 
1
1
,

 
 
2
4
,

 
 
2
7
,

 
 
4
2
8
,

 
 
2
2
8
,

 
 
2
,

 
 
2
8
1
8
,

 
 
1
5
0
,

 
 
5
4
3
1
1
,

 
 
7
,

 
 
3
4
,

 
 
1
1
,

 
 
4
9
9
,

 
 
2
6
,

 
 
7
,

 
 
6
3
5
,

 
 
1
2
2
2
,

 
 
2
2
6
2
7
,

 
 
3
4
,

 
 
1
1
,

 
 
3
7
1
,

 
 
4
,

 
 
3
5
9
,

 
 
1
7
,

 
 
1
0
1
,

 
 
5
,

 
 
7
,

 
 
5
9
,

 
 
1
2
2
2
,

 
 
2
5
1
,

 
 
7
5
,

 
 
3
4
,

 
 
1
1
,

 
 
3
3
,

 
 
4
0
,

 
 
1
,

 
 
7
7
,

 
 
9
3
0
,

 
 
8
,

 
 
9
,

 
 
1
4
8
2
,

 
 
1
9
,

 
 
4
,

 
 
5
0
3
1
,

 
 
2
,

 
 
1
6
0
5
0
6
,

 
 
1
1
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
4
6
5
7
,

 
 
1
1
,

 
 
7
2
,

 
 
1
4
,

 
 
1
2
6
,

 
 
1
8
4
9
,

 
 
6
,

 
 
5
9
,

 
 
1
9
,

 
 
4
,

 
 
2
9
7
9
,

 
 
5
5
9
5
,

 
 
9
1
,

 
 
4
,

 
 
9
2
2
,

 
 
7
2
,

 
 
1
4
,

 
 
3
5
8
,

 
 
7
1
,

 
 
1
4
,

 
 
4
4
1
,

 
 
1
6
4
,

 
 
1
4
3
,

 
 
7
,

 
 
2
4
,

 
 
4
9
,

 
 
4
4
9
,

 
 
3
,

 
 
9
5
0
,

 
 
1
4
5
4
2
]
,

 
[
6
3
0
0
,

 
 
1
8
,

 
 
2
3
0
9
,

 
 
1
5
,

 
 
4
5
5
2
3
,

 
 
9
2
,

 
 
1
0
0
8
,

 
 
6
0
7
,

 
 
5
1
,

 
 
4
5
,

 
 
1
9
4
1
2
,

 
 
5
5
,

 
 
2
6
3
1
,

 
 
2
,

 
 
4
6
8
,

 
 
9
,

 
 
1
6
1
8
,

 
 
1
5
1
9
,

 
 
1
8
,

 
 
1
9
4
,

 
 
1
0
,

 
 
1
3
,

 
 
1
1
0
,

 
 
9
2
,

 
 
1
1
0
,

 
 
3
,

 
 
3
0
0
,

 
 
4
5
,

 
 
1
6
,

 
 
1
3
7
5
,

 
 
1
7
,

 
 
9
1
,

 
 
1
4
,

 
 
7
7
,

 
 
9
2
5
5
,

 
 
2
6
,

 
 
1
5
5
8
,

 
 
1
5
3
3
,

 
 
1
7
,

 
 
5
7
3
1
,

 
 
3
,

 
 
7
5
,

 
 
2
3
1
8
,

 
 
3
1
,

 
 
6
7
7
8
,

 
 
2
,

 
 
1
0
6
4
2
,

 
 
5
,

 
 
1
8
,

 
 
4
4
2
5
,

 
 
2
,

 
 
1
3
,

 
 
4
5
6
4
,

 
 
5
1
,

 
 
5
8
8
7
,

 
 
2
0
9
1
,

 
 
4
,

 
 
7
0
3
8
,

 
 
1
2
,

 
 
3
4
8
3
,

 
 
1
0
,

 
 
1
3
,

 
 
1
1
0
,

 
 
1
1
,

 
 
8
,

 
 
8
9
,

 
 
6
5
7
,

 
 
5
7
6
9
,

 
 
9
0
4
,

 
 
1
7
,

 
 
4
,

 
 
6
8
7
8
,

 
 
2
5
,

 
 
3
6
7
6
,

 
 
1
0
0
8
,

 
 
2
5
,

 
 
1
1
0
,

 
 
3
,

 
 
9
1
,

 
 
6
1
8
,

 
 
2
,

 
 
4
,

 
 
1
0
4
5
,

 
 
1
2
8
7
,

 
 
2
5
,

 
 
2
5
9
1
,

 
 
2
2
6
2
8
]
,

 
[
1
0
1
7
,

 
 
4
5
5
2
4
,

 
 
1
3
,

 
 
2
3
,

 
 
2
4
,

 
 
4
,

 
 
2
8
1
,

 
 
3
4
2
,

 
 
1
4
3
2
,

 
 
5
7
9
,

 
 
2
,

 
 
1
,

 
 
4
3
4
,

 
 
7
0
7
,

 
 
7
6
,

 
 
1
0
,

 
 
1
1
3
,

 
 
1
9
5
3
,

 
 
1
8
7
2
2
]
,

 
[
1
6
9
,

 
 
2
,

 
 
1
8
7
2
3
,

 
 
7
,

 
 
6
6
8
,

 
 
4
,

 
 
2
8
,

 
 
1
6
9
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
1
2
5
,

 
 
1
,

 
 
2
7
0
,

 
 
1
8
7
2
3
,

 
 
5
5
7
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
6
2
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
2
8
8
5
,

 
 
3
7
,

 
 
5
,

 
 
8
,

 
 
7
3
7
,

 
 
5
8
0
,

 
 
9
,

 
 
7
,

 
 
3
4
,

 
 
5
3
8
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
1
8
3
7
0
,

 
 
3
2
,

 
 
2
9
8
,

 
 
1
3
,

 
 
7
,

 
 
1
9
,

 
 
1
5
6
,

 
 
1
,

 
 
2
3
0
,

 
 
5
,

 
 
6
5
,

 
 
7
,

 
 
2
7
5
,

 
 
1
1
,

 
 
5
,

 
 
7
,

 
 
7
8
9
,

 
 
2
1
,

 
 
1
5
4
,

 
 
1
,

 
 
2
7
0
,

 
 
1
8
7
2
3
,

 
 
2
4
,

 
 
1
4
,

 
 
1
0
0
2
,

 
 
1
5
1
3
,

 
 
3
3
1
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
1
5
0
,

 
 
7
,

 
 
1
3
1
,

 
 
1
,

 
 
1
6
9
,

 
 
5
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
3
0
,

 
 
1
6
9
,

 
 
7
3
6
,

 
 
9
8
,

 
 
7
3
2
,

 
 
1
2
,

 
 
4
,

 
 
1
0
6
8
,

 
 
6
2
,

 
 
9
0
,

 
 
1
4
,

 
 
7
0
,

 
 
3
9
6
8
0
,

 
 
6
7
0
3
,

 
 
2
6
,

 
 
3
3
2
,

 
 
9
,

 
 
3
5
2
,

 
 
5
1
,

 
 
1
3
3
7
,

 
 
1
8
7
2
3
,

 
 
2
4
,

 
 
4
1
,

 
 
2
1
5
,

 
 
2
4
7
,

 
 
2
1
,

 
 
3
0
,

 
 
1
6
9
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
1
5
8
,

 
 
2
0
0
7
,

 
 
2
,

 
 
2
5
8
,

 
 
9
2
,

 
 
8
5
7
,

 
 
3
4
9
7
,

 
 
7
9
9
7
,

 
 
2
3
1
4
,

 
 
5
9
8
4
]
,

 
[
2
0
,

 
 
2
0
2
7
,

 
 
4
1
3
,

 
 
1
8
2
5
,

 
 
1
0
5
4
,

 
 
3
,

 
 
6
,

 
 
7
4
2
,

 
 
4
2
,

 
 
1
3
1
,

 
 
5
5
,

 
 
1
3
5
8
,

 
 
2
,

 
 
1
3
,

 
 
2
1
1
2
,

 
 
1
7
9
,

 
 
2
3
,

 
 
6
1
,

 
 
9
3
,

 
 
2
,

 
 
5
8
8
8
,

 
 
2
0
,

 
 
4
9
4
2
2
,

 
 
2
8
9
5
,

 
 
9
4
8
,

 
 
4
1
3
,

 
 
1
0
,

 
 
3
0
,

 
 
8
9
6
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
1
7
9
,

 
 
2
3
,

 
 
1
7
9
,

 
 
1
9
,

 
 
6
,

 
 
8
2
0
,

 
 
3
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
2
1
2
,

 
 
7
8
,

 
 
3
6
,

 
 
1
3
0
,

 
 
7
5
,

 
 
9
4
,

 
 
3
6
9
5
,

 
 
1
9
2
,

 
 
3
5
,

 
 
1
,

 
 
3
0
8
1
0
,

 
 
5
,

 
 
7
1
4
2
,

 
 
5
,

 
 
3
2
1
6
4
,

 
 
3
,

 
 
2
8
,

 
 
1
1
7
1
,

 
 
1
9
8
1
6
,

 
 
9
4
,

 
 
4
,

 
 
5
1
2
,

 
 
8
3
3
7
,

 
 
3
0
0
]
,

 
[
2
6
1
,
 
1
0
6
,
 
9
2
0
,
 
6
8
4
,
 
5
0
,
 
3
4
,
 
1
4
,
 
1
3
4
1
,
 
2
0
,
 
2
4
2
,
 
1
7
8
0
,
 
1
3
5
,
 
1
,
 
2
3
,
 
4
6
]
,

 
[
7
,

 
 
9
0
,

 
 
3
9
4
,

 
 
1
3
4
,

 
 
6
,

 
 
1
0
2
,

 
 
1
2
8
,

 
 
5
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
1
0
,

 
 
1
,

 
 
2
9
0
3
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
7
,

 
 
6
5
,

 
 
6
,

 
 
8
7
,

 
 
1
9
,

 
 
2
,

 
 
1
6
0
5
0
7
,

 
 
1
1
3
,

 
 
2
1
1
7
,

 
 
2
,

 
 
6
0
7
6
6
,

 
 
1
8
6
,

 
 
6
,

 
 
3
3
4
1
,

 
 
1
,

 
 
4
7
9
,

 
 
3
5
,

 
 
7
8
,

 
 
1
1
2
,

 
 
2
2
4
,

 
 
1
8
,

 
 
9
1
,

 
 
1
4
6
,

 
 
7
,

 
 
8
1
,

 
 
1
3
1
5
,

 
 
2
,

 
 
2
6
3
,

 
 
2
1
,

 
 
7
5
,

 
 
9
,

 
 
7
7
,

 
 
1
,

 
 
5
6
8
,

 
 
8
3
0
,

 
 
5
6
,

 
 
1
6
,

 
 
4
1
,

 
 
6
0
7
,

 
 
7
,

 
 
1
1
4
9
,

 
 
3
5
6
,

 
 
1
,

 
 
5
6
6
,

 
 
3
4
1
,

 
 
5
,

 
 
1
,

 
 
8
3
5
6
7
,

 
 
8
9
]
,

 
[
4
,

 
 
4
9
4
2
3
,

 
 
4
5
4
,

 
 
4
3
,

 
 
2
8
8
,

 
 
1
6
,

 
 
4
8
1
,

 
 
3
3
9
,

 
 
1
,

 
 
3
2
1
0
,

 
 
3
,

 
 
3
4
3
5
,

 
 
9
,

 
 
1
3
8
1
,

 
 
6
4
,

 
 
2
6
,

 
 
7
,

 
 
4
3
1
,

 
 
2
7
5
,

 
 
7
8
,

 
 
1
0
0
9
9
,

 
 
8
6
3
,

 
 
2
5
4
6
,

 
 
3
2
,

 
 
6
0
,

 
 
1
7
,

 
 
2
9
6
2
,

 
 
4
3
,

 
 
3
5
4
7
,

 
 
8
3
5
6
8
,

 
 
1
,

 
 
2
3
,

 
 
7
7
3
9
,

 
 
4
2
,

 
 
6
6
,

 
 
1
3
3
,

 
 
9
,

 
 
1
2
6
3
,

 
 
7
1
3
,

 
 
2
6
,

 
 
7
,

 
 
2
6
4
,

 
 
6
5
,

 
 
9
,

 
 
2
1
8
8
,

 
 
5
,

 
 
1
0
4
9
,

 
 
1
0
5
,

 
 
8
,

 
 
5
8
,

 
 
3
,

 
 
4
,

 
 
8
3
5
6
9
,

 
 
9
3
,

 
 
8
,

 
 
4
,

 
 
3
7
0
,

 
 
4
5
4
,

 
 
2
,

 
 
5
2
5
,

 
 
2
0
,

 
 
4
3
7
,

 
 
2
1
4
,

 
 
3
0
,

 
 
6
5
4
,

 
 
4
2
,

 
 
1
3
7
3
,

 
 
1
3
1
8
,

 
 
4
,

 
 
1
2
8
9
,

 
 
5
,

 
 
1
,

 
 
6
1
,

 
 
6
5
4
,

 
 
4
2
,

 
 
1
4
,

 
 
3
5
1
,

 
 
2
2
2
2
,

 
 
1
3
,

 
 
8
,

 
 
3
9
9
8
,

 
 
1
9
4
2
,

 
 
2
1
,

 
 
5
2
9
,

 
 
6
3
2
6
,

 
 
3
,

 
 
2
1
9
0
,

 
 
2
3
1
,

 
 
9
7
,

 
 
4
4
,

 
 
2
0
6
,

 
 
1
5
,

 
 
3
8
5
,

 
 
2
5
,

 
 
1
4
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
4
5
9
5
,

 
 
4
5
6
4
]
,

 
[
1
3
7
,

 
 
4
7
2
4
,

 
 
2
4
1
,

 
 
2
0
,

 
 
1
8
1
3
,

 
 
1
8
,

 
 
1
4
1
7
,

 
 
7
7
7
4
,

 
 
2
,

 
 
1
,

 
 
4
7
5
,

 
 
3
,

 
 
2
8
,

 
 
4
0
,

 
 
7
,

 
 
1
9
,

 
 
3
4
9
,

 
 
2
0
7
,

 
 
8
,

 
 
7
0
5
,

 
 
2
,

 
 
7
5
8
,

 
 
1
,

 
 
9
1
8
,

 
 
3
,

 
 
2
8
,

 
 
8
3
,

 
 
5
,

 
 
2
4
9
7
,

 
 
1
,

 
 
1
1
2
8
,

 
 
3
,

 
 
9
1
8
,

 
 
7
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
2
2
7
2
,

 
 
4
8
,

 
 
4
,

 
 
8
1
1
,

 
 
6
2
,

 
 
7
7
,

 
 
2
4
7
6
,

 
 
2
,

 
 
1
5
8
8
4
,

 
 
7
3
,

 
 
8
3
,

 
 
3
0
,

 
 
3
8
7
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
8
8
,

 
 
7
,

 
 
5
6
,

 
 
1
6
,

 
 
2
7
,

 
 
7
5
3
]
,

 
[
2
5
8
,

 
 
3
7
,

 
 
4
,

 
 
1
6
0
5
0
8
,

 
 
2
1
3
,

 
 
8
3
5
7
0
,

 
 
5
8
4
,

 
 
3
7
,

 
 
1
8
0
6
,

 
 
4
7
6
,

 
 
6
,

 
 
1
9
9
4
,

 
 
1
2
,

 
 
1
1
2
,

 
 
3
4
4
,

 
 
5
1
,

 
 
1
8
,

 
 
2
6
8
,

 
 
2
,

 
 
2
5
5
6
,

 
 
1
9
1
,

 
 
2
6
,

 
 
5
1
,

 
 
1
6
9
4
,

 
 
1
4
7
,

 
 
1
1
2
,

 
 
3
4
4
,

 
 
1
8
,

 
 
2
0
7
5
,

 
 
5
,

 
 
1
9
,

 
 
2
4
1
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
5
1
2
,

 
 
2
5
,

 
 
1
7
5
,

 
 
5
2
0
5
,

 
 
9
6
,

 
 
9
2
,

 
 
2
3
,

 
 
8
,

 
 
3
6
,

 
 
1
4
9
5
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
2
7
,

 
 
5
9
1
1
,

 
 
1
2
0
,

 
 
1
0
4
,

 
 
2
7
,

 
 
3
8
4
,

 
 
1
2
,

 
 
1
,

 
 
1
6
6
6
,

 
 
5
4
,

 
 
4
2
,

 
 
1
4
,

 
 
9
9
8
8
,

 
 
2
5
9
,

 
 
3
9
,

 
 
7
9
,

 
 
2
5
,

 
 
3
5
0
,

 
 
6
1
7
,

 
 
5
1
,

 
 
6
5
,

 
 
4
9
,

 
 
4
8
,

 
 
1
6
0
5
0
9
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
5
2
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
0
8
4
,

 
 
3
8
,

 
 
1
5
1
2
,

 
 
8
,

 
 
5
,

 
 
5
2
,

 
 
2
8
5
4
,

 
 
3
5
,

 
 
1
1
,

 
 
3
6
,

 
 
1
6
8
9
,

 
 
3
5
,

 
 
1
8
0
,

 
 
1
0
4
,

 
 
1
4
9
5
,

 
 
5
1
,

 
 
1
9
,

 
 
4
4
,

 
 
9
9
8
8
,

 
 
7
,

 
 
1
8
6
8
,

 
 
5
1
,

 
 
5
6
,

 
 
1
5
2
,

 
 
3
6
9
5
,

 
 
2
4
3
4
,

 
 
1
0
,

 
 
1
6
0
5
1
0
,

 
 
2
3
,

 
 
5
1
,

 
 
5
6
]
,

 
[
3
1
1
4
,

 
 
1
7
8
,

 
 
7
,

 
 
1
5
3
,

 
 
9
0
,

 
 
1
4
,

 
 
1
9
,

 
 
8
5
,

 
 
2
,

 
 
3
5
0
,

 
 
1
,

 
 
8
3
,

 
 
3
5
,

 
 
1
,

 
 
1
7
4
5
2
,

 
 
3
,

 
 
1
,

 
 
1
1
2
7
9
,

 
 
9
5
6
,

 
 
5
,

 
 
1
3
4
0
,

 
 
9
,

 
 
4
3
,

 
 
1
9
,

 
 
3
4
6
6
,

 
 
4
,

 
 
1
5
3
3
,

 
 
4
2
5
9
,

 
 
1
2
7
0
,

 
 
1
,

 
 
7
7
7
5
,

 
 
7
,

 
 
2
2
6
,

 
 
1
0
,

 
 
1
,

 
 
1
3
9
4
,

 
 
6
0
2
,

 
 
2
3
1
,

 
 
4
8
6
3
,

 
 
2
,

 
 
3
4
,

 
 
1
1
,

 
 
3
1
,

 
 
1
,

 
 
2
6
2
,

 
 
1
3
8
,

 
 
7
,

 
 
4
9
,

 
 
3
1
2
7
,

 
 
2
,

 
 
7
4
4
4
,

 
 
2
0
1
,

 
 
4
7
8
,

 
 
1
1
2
7
9
,

 
 
7
5
,

 
 
3
2
,

 
 
5
4
6
,

 
 
5
,

 
 
4
7
8
,

 
 
1
1
2
7
9
,

 
 
7
5
,

 
 
3
2
,

 
 
2
9
3
2
,

 
 
5
,

 
 
4
7
1
,

 
 
6
0
,

 
 
5
8
,

 
 
8
3
,

 
 
3
5
,

 
 
1
1
2
7
9
,

 
 
1
5
1
9
]
,

 
[
7
,
 
6
3
6
,
 
1
5
4
,
 
4
,
 
2
1
4
,
 
3
5
,
 
2
3
4
6
,
 
3
5
2
,
 
9
,
 
4
3
,
 
9
7
,
 
6
,
 
4
6
2
,
 
1
1
4
7
3
,
 
3
8
7
]
,

 
[
2
8
6
,
 
4
4
,
 
3
1
9
,
 
2
4
,
 
3
4
9
,
 
1
6
5
5
,
 
1
7
,
 
5
2
,
 
3
6
8
,
 
3
0
,
 
1
4
0
,
 
6
4
]
,

 
[
7
,

 
 
1
3
6
,

 
 
1
1
,

 
 
1
1
8
0
,

 
 
2
,

 
 
1
0
0
7
,

 
 
3
0
,

 
 
7
2
9
3
,

 
 
5
,

 
 
7
,

 
 
1
5
3
,

 
 
2
1
1
,

 
 
9
,

 
 
7
9
8
,

 
 
5
4
3
1
2
,

 
 
1
6
0
5
1
1
,

 
 
2
4
,

 
 
3
6
6
]
,

 
[
6
7
,
 
6
,
 
2
1
3
,
 
3
7
,
 
6
,
 
4
4
4
,
 
1
1
1
3
]
,

 
[
2
2
9
3
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
7
4
,

 
 
7
,

 
 
8
1
,

 
 
2
6
8
,

 
 
2
,

 
 
9
7
,

 
 
4
,

 
 
1
4
5
,

 
 
3
5
,

 
 
7
4
,

 
 
1
1
3
3
,

 
 
1
1
,

 
 
8
,

 
 
2
,

 
 
7
9
,

 
 
2
8
,

 
 
5
,

 
 
6
8
,

 
 
7
2
6
,

 
 
1
5
,

 
 
1
4
7
7
,

 
 
3
2
1
6
5
,

 
 
2
9
,

 
 
3
3
2
1
,

 
 
3
0
,

 
 
1
4
5
,

 
 
1
1
,

 
 
8
,

 
 
5
2
3
,

 
 
2
0
2
,

 
 
1
2
,

 
 
1
3
2
0
,

 
 
2
,

 
 
1
2
1
,

 
 
4
3
3
,

 
 
6
1
,

 
 
9
7
,

 
 
2
0
1
,

 
 
5
,

 
 
4
,

 
 
3
4
8
,

 
 
5
5
3
1
,

 
 
8
7
1
,

 
 
1
4
0
,

 
 
5
,

 
 
9
,

 
 
8
,

 
 
4
0
,

 
 
7
,

 
 
2
4
,

 
 
2
6
8
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
2
2
,

 
 
6
,

 
 
7
5
6
,

 
 
4
8
9
,

 
 
5
0
,

 
 
1
0
3
,

 
 
6
,

 
 
2
5
6
,

 
 
9
,

 
 
5
8
7
]
,

 
[
5
0
,

 
 
6
3
,

 
 
1
6
7
8
,

 
 
1
6
2
,

 
 
3
6
5
,

 
 
3
6
3
,

 
 
5
5
8
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
4
4
5
,

 
 
3
2
,

 
 
2
8
,

 
 
1
2
,

 
 
1
0
2
8
8
,

 
 
3
9
7
5
,

 
 
2
2
6
7
,

 
 
3
,

 
 
9
3
4
,

 
 
2
6
6
2
,

 
 
7
,

 
 
4
4
5
,

 
 
3
5
,

 
 
4
8
4
,

 
 
1
8
9
1
,

 
 
3
3
7
,

 
 
3
5
,

 
 
3
2
5
,

 
 
3
0
0
,

 
 
6
5
7
5
,

 
 
3
2
,

 
 
1
7
8
3
,

 
 
3
4
2
,

 
 
2
6
1
,

 
 
2
7
3
,

 
 
3
4
,

 
 
1
4
,

 
 
6
,

 
 
2
1
1
,

 
 
3
8
3
8
,

 
 
4
3
8
,

 
 
8
,

 
 
2
6
1
,

 
 
3
4
2
,

 
 
2
7
3
,

 
 
1
7
,

 
 
1
0
4
,

 
 
2
9
,

 
 
1
3
8
1
,

 
 
1
5
,

 
 
2
8
,

 
 
3
4
,

 
 
6
,

 
 
1
2
6
,

 
 
2
2
0
,

 
 
9
,

 
 
3
8
,

 
 
3
4
9
,

 
 
2
5
,

 
 
6
2
,

 
 
3
6
,

 
 
3
4
9
,

 
 
4
9
8
,

 
 
1
0
5
,

 
 
1
2
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
3
5
5
,

 
 
3
6
6
,

 
 
3
4
3
0
,

 
 
1
0
,

 
 
2
0
,

 
 
4
0
9
,

 
 
9
2
7
,

 
 
1
3
9
1
0
,

 
 
9
0
,

 
 
7
,

 
 
6
3
6
,

 
 
1
2
9
3
,

 
 
2
1
5
,

 
 
3
1
,

 
 
6
,

 
 
2
,

 
 
7
9
,

 
 
2
5
,

 
 
3
5
0
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
2
0
0
,

 
 
4
0
0
,

 
 
2
,

 
 
1
4
8
3
,

 
 
1
0
5
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
2
0
0
,

 
 
2
2
2
,

 
 
2
,

 
 
1
5
6
7
3
,

 
 
1
1
,

 
 
1
8
,

 
 
6
,

 
 
2
5
5
,

 
 
2
8
,

 
 
8
0
,

 
 
1
6
7
8
,

 
 
1
6
2
,

 
 
3
6
5
,

 
 
3
6
3
,

 
 
5
5
8
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
4
4
5
,

 
 
3
2
,

 
 
2
8
,

 
 
1
2
,

 
 
1
0
2
8
8
,

 
 
3
9
7
5
,

 
 
2
2
6
7
,

 
 
3
,

 
 
9
3
4
,

 
 
1
2
,

 
 
1
,

 
 
2
5
7
,

 
 
7
8
,

 
 
6
,

 
 
9
8
2
,

 
 
1
0
,

 
 
3
6
6
,

 
 
4
0
9
,

 
 
2
0
,

 
 
4
0
9
,

 
 
6
0
8
9
,

 
 
5
5
,

 
 
3
3
7
,

 
 
2
5
,

 
 
3
7
9
,

 
 
5
4
,

 
 
1
0
7
1
4
,

 
 
1
,

 
 
1
2
1
8
1
,

 
 
1
0
2
8
8
,

 
 
3
9
7
5
,

 
 
2
2
6
7
,

 
 
5
,

 
 
1
,

 
 
1
0
2
8
8
,

 
 
5
4
4
6
,

 
 
3
9
7
5
,

 
 
2
2
6
7
,

 
 
1
0
,

 
 
1
,

 
 
2
4
4
,

 
 
4
0
3
,

 
 
9
,

 
 
3
0
8
1
1
,

 
 
5
,

 
 
6
8
,

 
 
3
1
7
0
,

 
 
1
8
,

 
 
1
8
2
5
,

 
 
2
6
3
2
,

 
 
1
7
,

 
 
4
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
7
4
,

 
 
3
9
,

 
 
6
,

 
 
8
1
0
6
,

 
 
7
5
,

 
 
3
1
,

 
 
3
6
8
2
,

 
 
1
0
5
,

 
 
5
4
,

 
 
8
,

 
 
5
1
1
,

 
 
2
6
1
,

 
 
1
0
6
5
1
1
,

 
 
6
2
2
4
,

 
 
8
6
4
,

 
 
6
7
0
4
]
,

 
[
4
9
4
2
4
,

 
 
2
3
3
8
,

 
 
2
,

 
 
4
9
0
,

 
 
1
3
2
3
,

 
 
7
4
2
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
6
3
,

 
 
6
,

 
 
7
0
3
,

 
 
3
0
3
6
,

 
 
2
,

 
 
2
8
,

 
 
1
2
9
8
,

 
 
1
2
,

 
 
2
0
2
2
,

 
 
7
,

 
 
3
9
,

 
 
1
4
,

 
 
3
4
,

 
 
1
3
,

 
 
7
9
3
,

 
 
6
9
,

 
 
7
,

 
 
3
6
9
,

 
 
6
1
9
8
,

 
 
3
1
,

 
 
1
9
0
4
9
,

 
 
1
0
6
4
3
,

 
 
1
4
7
0
,

 
 
1
0
3
3
,

 
 
5
,

 
 
4
5
1
,

 
 
1
4
1
,

 
 
3
0
3
6
,

 
 
1
0
3
,

 
 
7
7
7
,

 
 
1
0
,

 
 
1
1
5
,

 
 
3
5
3
7
9
,

 
 
1
1
9
5
,

 
 
4
5
5
2
5
,

 
 
3
,

 
 
4
0
9
,

 
 
3
2
,

 
 
1
,

 
 
1
7
6
7
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
1
0
8
,

 
 
9
,

 
 
1
6
0
5
1
2
,

 
 
1
0
3
,

 
 
6
,

 
 
5
0
,

 
 
7
1
1
,

 
 
1
,

 
 
2
3
4
2
,

 
 
1
0
,

 
 
1
,

 
 
1
6
9
,

 
 
7
,

 
 
7
3
6
,

 
 
1
3
4
,

 
 
6
,

 
 
4
9
4
2
4
,

 
 
2
3
3
8
,

 
 
2
,

 
 
1
1
5
,

 
 
2
7
3
,

 
 
3
2
,

 
 
8
3
5
7
1
,

 
 
3
3
,

 
 
2
6
2
,

 
 
5
3
,

 
 
2
6
3
,

 
 
1
5
,

 
 
1
6
3
,

 
 
3
,

 
 
4
4
3
,

 
 
9
,

 
 
1
,

 
 
1
1
5
,

 
 
1
1
6
,

 
 
8
,

 
 
4
,

 
 
9
8
,

 
 
4
0
5
,

 
 
1
,

 
 
6
7
9
,

 
 
1
7
4
5
3
,

 
 
3
0
7
9
,

 
 
3
1
,

 
 
1
6
0
5
1
3
,

 
 
4
5
,

 
 
6
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
4
1
,

 
 
2
6
9
,

 
 
1
6
0
5
1
4
,

 
 
2
4
2
8
,

 
 
4
2
6
,

 
 
5
5
3
,

 
 
9
,

 
 
1
1
6
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
1
0
8
,

 
 
4
0
,

 
 
1
,

 
 
9
9
2
9
,

 
 
1
2
,

 
 
4
9
9
,

 
 
1
,

 
 
1
1
5
,

 
 
7
7
4
,

 
 
2
3
,

 
 
8
,

 
 
3
2
,

 
 
8
9
,

 
 
2
7
,

 
 
1
2
9
1
,

 
 
1
3
1
,

 
 
7
7
,

 
 
3
2
,

 
 
3
7
,

 
 
2
6
,

 
 
5
8
4
,

 
 
6
8
1
,

 
 
5
,

 
 
1
0
6
,

 
 
4
0
,

 
 
1
,

 
 
1
0
6
,

 
 
4
9
,

 
 
4
8
,

 
 
3
7
,

 
 
1
5
0
1
,

 
 
2
1
1
7
,

 
 
2
1
0
7
8
,

 
 
1
0
,

 
 
1
,

 
 
1
1
6
,

 
 
3
5
,

 
 
1
,

 
 
5
3
0
8
,

 
 
3
5
,

 
 
1
,

 
 
1
0
6
5
1
2
,

 
 
3
,

 
 
1
,

 
 
8
1
0
7
,

 
 
3
7
8
4
,

 
 
6
6
9
,

 
 
7
3
4
,

 
 
4
,

 
 
9
8
,

 
 
1
4
5
,

 
 
5
,

 
 
4
0
,

 
 
1
,

 
 
2
1
9
8
,

 
 
1
0
,

 
 
1
2
5
0
3
,

 
 
1
5
5
,

 
 
5
,

 
 
1
,

 
 
3
2
5
2
,

 
 
1
0
6
5
1
3
,

 
 
3
,

 
 
2
5
9
2
9
,

 
 
8
3
5
7
2
,

 
 
5
9
2
,

 
 
1
0
,

 
 
2
1
1
7
,

 
 
1
9
0
5
0
,

 
 
7
,

 
 
2
6
3
,

 
 
2
1
,

 
 
6
,

 
 
5
6
0
,

 
 
1
6
0
5
1
5
,

 
 
3
8
,

 
 
4
9
4
2
4
,

 
 
1
5
8
8
5
,

 
 
2
,

 
 
3
9
2
,

 
 
1
5
,

 
 
1
,

 
 
1
1
6
,

 
 
3
5
,

 
 
1
,

 
 
8
1
0
7
,

 
 
3
7
8
4
,

 
 
8
,

 
 
9
,

 
 
5
2
,

 
 
7
7
,

 
 
1
7
3
,

 
 
1
3
2
1
0
,

 
 
2
9
5
,

 
 
8
0
,

 
 
7
,

 
 
7
5
6
1
,

 
 
9
,

 
 
5
2
,

 
 
3
4
,

 
 
3
6
,

 
 
1
,

 
 
2
9
9
,

 
 
4
0
7
,

 
 
5
2
,

 
 
3
3
3
,

 
 
2
4
,

 
 
1
0
5
9
,

 
 
4
1
3
,

 
 
1
7
,

 
 
8
,

 
 
1
2
8
,

 
 
3
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
7
7
4
,

 
 
2
3
,

 
 
6
6
,

 
 
4
0
,

 
 
1
,

 
 
1
0
6
,

 
 
9
,

 
 
5
2
,

 
 
1
7
3
,

 
 
3
1
,

 
 
2
1
1
7
,

 
 
3
9
6
8
1
,

 
 
1
8
,

 
 
7
7
,

 
 
8
4
2
,

 
 
2
,

 
 
1
8
0
6
0
,

 
 
6
8
1
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
6
,

 
 
1
8
,

 
 
1
4
3
,

 
 
5
4
3
1
3
,

 
 
1
0
,

 
 
2
0
,

 
 
4
9
4
2
4
,

 
 
1
5
8
8
5
,

 
 
1
1
6
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
1
4
,

 
 
1
1
0
5
2
,

 
 
2
,

 
 
2
1
1
7
,

 
 
2
1
0
7
8
,

 
 
7
,

 
 
8
1
,

 
 
2
8
0
,

 
 
2
6
,

 
 
1
5
8
8
6
,

 
 
2
0
,

 
 
2
4
9
,

 
 
3
0
,

 
 
1
0
6
4
3
,

 
 
1
0
3
3
,

 
 
6
6
,

 
 
4
2
,

 
 
6
0
,

 
 
1
0
2
2
7
,

 
 
4
8
,

 
 
1
8
8
1
,

 
 
1
0
3
3
,

 
 
2
,

 
 
2
1
1
7
,

 
 
2
1
0
7
8
,

 
 
5
,

 
 
1
3
0
,

 
 
1
3
0
,

 
 
6
1
,

 
 
2
4
7
7
,

 
 
5
,

 
 
5
9
0
,

 
 
1
5
8
8
6
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
5
2
,

 
 
1
2
,

 
 
3
0
,

 
 
4
3
5
4
,

 
 
8
2
,

 
 
3
,

 
 
1
9
0
4
9
,

 
 
7
8
6
,

 
 
1
0
6
5
1
4
,

 
 
9
1
4
1
,

 
 
1
2
8
,

 
 
1
6
6
0
,

 
 
1
2
,

 
 
3
7
,

 
 
2
,

 
 
1
4
2
,

 
 
6
4
,

 
 
5
9
6
,

 
 
2
,

 
 
1
,

 
 
1
1
3
3
,

 
 
1
0
2
8
9
,

 
 
3
,

 
 
1
0
6
,

 
 
3
4
,

 
 
6
,

 
 
6
3
,

 
 
1
,

 
 
4
5
5
2
5
,

 
 
3
,

 
 
4
0
9
,

 
 
8
,

 
 
1
6
0
5
1
6
,

 
 
7
,

 
 
6
5
,

 
 
3
2
,

 
 
2
0
1
,

 
 
1
0
6
,

 
 
1
2
0
6
,

 
 
2
2
,

 
 
6
,

 
 
3
5
0
,

 
 
1
8
2
,

 
 
4
,

 
 
4
9
4
2
4
,

 
 
2
3
3
8
,

 
 
1
1
6
,

 
 
6
,

 
 
1
8
,

 
 
1
1
0
5
3
,

 
 
3
0
,

 
 
8
3
6
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
4
8
9
,

 
 
1
2
6
,

 
 
2
6
,

 
 
6
,

 
 
1
8
,

 
 
2
9
8
,

 
 
1
1
,

 
 
1
8
7
2
4
,

 
 
1
1
5
,

 
 
1
6
0
5
1
7
,

 
 
1
5
,

 
 
2
0
,

 
 
9
8
9
,

 
 
2
,

 
 
8
0
5
,

 
 
1
3
,

 
 
5
0
,

 
 
3
5
0
,

 
 
9
8
5
,

 
 
4
9
4
2
4
,

 
 
2
3
3
8
,

 
 
8
4
3
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
1
,

 
 
7
7
4
,

 
 
2
3
,

 
 
8
,

 
 
4
1
3
,

 
 
1
4
2
,

 
 
1
0
,

 
 
1
1
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
6
8
1
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
1
4
,

 
 
1
1
6
8
,

 
 
2
3
1
,

 
 
1
5
9
,

 
 
1
,

 
 
2
7
5
9
,

 
 
3
,

 
 
6
,

 
 
1
0
6
5
1
5
,

 
 
1
,

 
 
7
4
5
,

 
 
5
,

 
 
2
0
4
,

 
 
1
1
,

 
 
6
4
,

 
 
7
1
,

 
 
1
0
2
,

 
 
6
7
3
,

 
 
1
,

 
 
2
6
7
,

 
 
8
,

 
 
1
4
,

 
 
3
8
5
,

 
 
7
,

 
 
1
0
5
8
0
,

 
 
2
,

 
 
2
1
1
7
,

 
 
2
1
0
7
8
,

 
 
1
0
4
,

 
 
3
8
5
,

 
 
1
,

 
 
7
5
,

 
 
6
2
,

 
 
1
5
6
,

 
 
2
7
,

 
 
2
3
,

 
 
1
0
,

 
 
1
,

 
 
2
5
1
,

 
 
2
8
,

 
 
1
0
5
8
0
,

 
 
2
,

 
 
1
1
,

 
 
4
0
,

 
 
1
0
6
,

 
 
1
3
3
,

 
 
5
6
,

 
 
1
6
,

 
 
4
8
7
4
,

 
 
2
,

 
 
4
0
,

 
 
1
0
1
0
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
1
0
2
5
,

 
 
1
0
,

 
 
4
,

 
 
1
2
0
,

 
 
9
,

 
 
1
0
1
0
,

 
 
4
5
,

 
 
1
4
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
6
3
,

 
 
4
9
,

 
 
3
6
,

 
 
6
,

 
 
3
9
,

 
 
4
0
3
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
6
8
1
,

 
 
8
,

 
 
2
,

 
 
3
0
,

 
 
4
8
9
,

 
 
5
7
4
,

 
 
4
9
1
4
,

 
 
4
0
,

 
 
1
0
6
,

 
 
1
3
3
,

 
 
5
6
,

 
 
1
6
,

 
 
4
8
7
4
,

 
 
2
,

 
 
4
0
,

 
 
1
0
1
0
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
1
0
2
,

 
 
1
2
5
1
,

 
 
5
4
3
1
3
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
7
1
1
,

 
 
1
3
,

 
 
1
2
7
5
,

 
 
3
,

 
 
1
2
3
9
,

 
 
5
0
,

 
 
1
7
8
5
,

 
 
6
6
,

 
 
1
,

 
 
1
1
9
,

 
 
3
,

 
 
4
0
,

 
 
5
9
0
,

 
 
1
7
,

 
 
1
0
6
,

 
 
6
9
,

 
 
9
0
,

 
 
6
,

 
 
7
0
,

 
 
4
1
,

 
 
8
,

 
 
3
6
9
,

 
 
1
5
8
,

 
 
1
7
7
,

 
 
1
3
,

 
 
2
5
,

 
 
9
,

 
 
3
3
7
,

 
 
3
5
6
,

 
 
4
0
,

 
 
2
9
5
,

 
 
2
,

 
 
1
0
0
4
,

 
 
2
5
,

 
 
1
8
1
7
,

 
 
3
7
3
5
,

 
 
6
9
,

 
 
9
,

 
 
1
0
7
,

 
 
1
0
,

 
 
4
3
2
2
,

 
 
4
2
,

 
 
4
4
,

 
 
1
0
0
4
,

 
 
5
,

 
 
4
4
,

 
 
1
8
1
7
,

 
 
3
3
,

 
 
1
0
4
2
,

 
 
3
5
6
,

 
 
4
0
,

 
 
1
,

 
 
2
9
5
,

 
 
1
0
,

 
 
1
4
0
5
,

 
 
6
9
,

 
 
9
0
,

 
 
6
,

 
 
7
0
,

 
 
4
1
,

 
 
1
8
,

 
 
4
1
0
,

 
 
6
2
,

 
 
7
0
,

 
 
4
4
,

 
 
1
4
0
5
,

 
 
9
1
4
1
,

 
 
4
,

 
 
3
9
3
9
,

 
 
2
,

 
 
1
5
6
,

 
 
1
3
,

 
 
4
4
9
,

 
 
3
,

 
 
1
2
5
1
,

 
 
4
0
0
8
,

 
 
1
2
6
,

 
 
7
,

 
 
9
9
,

 
 
4
,

 
 
9
8
,

 
 
2
8
9
3
,

 
 
1
0
7
,

 
 
5
4
3
1
3
,

 
 
7
4
,

 
 
2
0
2
5
,

 
 
9
,

 
 
6
,

 
 
5
6
,

 
 
1
3
6
,

 
 
1
1
,

 
 
3
6
,

 
 
1
2
5
1
,

 
 
1
5
1
,

 
 
4
0
,

 
 
1
3
2
,

 
 
3
,

 
 
1
,

 
 
1
0
6
,

 
 
5
3
,

 
 
1
8
,

 
 
1
7
8
3
,

 
 
5
6
,

 
 
7
5
0
1
,

 
 
4
1
0
,

 
 
2
,

 
 
1
3
6
,

 
 
7
6
,

 
 
5
8
,

 
 
1
0
5
,

 
 
3
5
,

 
 
3
8
,

 
 
8
,

 
 
9
1
,

 
 
7
7
5
,

 
 
3
6
,

 
 
2
,

 
 
2
8
7
0
,

 
 
1
5
2
7
,

 
 
1
0
6
,

 
 
9
,

 
 
1
6
7
5
,

 
 
1
4
1
,

 
 
4
1
0
,

 
 
2
,

 
 
1
7
9
5
,

 
 
2
,

 
 
6
3
,

 
 
1
,

 
 
1
0
5
,

 
 
8
,

 
 
1
4
,

 
 
1
2
5
1
,

 
 
7
1
,

 
 
3
0
9
,

 
 
4
1
1
2
,

 
 
2
5
3
4
,

 
 
1
0
,

 
 
1
,

 
 
2
5
1
,

 
 
2
8
,

 
 
7
,

 
 
4
3
,

 
 
1
3
5
3
,

 
 
9
,

 
 
6
0
2
2
,

 
 
4
,

 
 
1
4
0
5
,

 
 
2
5
,

 
 
6
1
,

 
 
1
8
4
8
,

 
 
3
6
1
,

 
 
1
2
0
,

 
 
8
0
,

 
 
2
7
,

 
 
2
5
3
4
,

 
 
8
7
0
,

 
 
1
2
0
,

 
 
1
3
8
1
,

 
 
1
0
,

 
 
2
5
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
9
7
,

 
 
4
6
9
,

 
 
9
4
5
,

 
 
3
7
5
,

 
 
2
,

 
 
1
4
1
,

 
 
6
2
,

 
 
1
8
,

 
 
1
5
5
,

 
 
1
9
3
3
,

 
 
5
9
3
0
,

 
 
2
0
,

 
 
2
5
1
4
1
,

 
 
8
,

 
 
4
2
4
1
,

 
 
1
0
,

 
 
2
0
,

 
 
6
3
9
,

 
 
1
8
7
2
,

 
 
2
3
3
]
,

 
[
1
5
6
5
,

 
 
7
8
,

 
 
7
,

 
 
1
8
7
,

 
 
1
1
,

 
 
1
7
4
,

 
 
3
,

 
 
9
,

 
 
1
1
4
8
,

 
 
8
,

 
 
1
4
,

 
 
2
1
6
3
,

 
 
1
2
,

 
 
2
8
,

 
 
2
9
6
8
5
,

 
 
3
2
,

 
 
1
1
3
,

 
 
1
4
,

 
 
2
6
,

 
 
3
7
5
,

 
 
1
2
,

 
 
4
7
,

 
 
3
,

 
 
1
0
4
,

 
 
2
5
6
3
,

 
 
2
1
0
0
,

 
 
1
1
1
,

 
 
1
7
,

 
 
5
8
8
9
]
,

 
[
1
0
6
5
1
6
,

 
 
1
7
8
9
,

 
 
1
3
7
,

 
 
1
8
7
,

 
 
1
3
,

 
 
1
6
0
5
1
8
,

 
 
1
7
,

 
 
1
1
,

 
 
1
8
1
,

 
 
1
2
6
,

 
 
4
4
4
3
,

 
 
2
,

 
 
1
,

 
 
1
1
9
1
,

 
 
1
2
8
,

 
 
1
4
6
5
,

 
 
7
1
,

 
 
3
2
2
7
,

 
 
1
9
2
,

 
 
4
4
7
]
,

 
[
5
,

 
 
3
2
8
,

 
 
1
3
,

 
 
7
6
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
3
2
1
6
6
,

 
 
1
5
2
6
4
,

 
 
3
5
9
4
,

 
 
1
0
6
5
1
7
,

 
 
1
6
0
5
1
9
,

 
 
1
8
0
5
,

 
 
9
4
2
,

 
 
1
9
5
3
]
,

 
[
7
0
6
,

 
 
4
0
,

 
 
9
7
8
,

 
 
7
,

 
 
1
9
,

 
 
5
5
2
,

 
 
9
,

 
 
2
8
7
,

 
 
1
9
,

 
 
1
6
7
,

 
 
1
3
,

 
 
5
6
,

 
 
1
3
,

 
 
1
6
,

 
 
5
0
2
,

 
 
9
,

 
 
6
1
3
0
,

 
 
9
4
3
,

 
 
1
1
7
,

 
 
1
1
2
]
,

 
[
1
1
5
,

 
 
1
0
7
,

 
 
3
2
0
,

 
 
1
3
2
1
1
,

 
 
8
7
3
5
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
1
1
5
,

 
 
1
0
7
,

 
 
1
5
,

 
 
2
8
,

 
 
5
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
2
1
9
,

 
 
2
2
,

 
 
3
0
,

 
 
1
1
5
,

 
 
2
9
,

 
 
1
0
3
,

 
 
1
6
,

 
 
1
8
7
,

 
 
3
1
,

 
 
1
,

 
 
1
1
9
,

 
 
1
6
1
,

 
 
3
0
,

 
 
1
1
5
,

 
 
2
9
,

 
 
8
,

 
 
1
6
0
5
2
0
,

 
 
5
,

 
 
7
,

 
 
1
5
3
,

 
 
1
9
,

 
 
4
,

 
 
3
4
8
,

 
 
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
1
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
1
2
,

 
 
1
1
,

 
 
2
4
,

 
 
4
1
9
,

 
 
8
,

 
 
6
9
,

 
 
1
1
,

 
 
2
8
3
6
,

 
 
1
9
2
,

 
 
4
8
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
0
,

 
 
6
1
9
9
,

 
 
2
6
,

 
 
7
6
0
,

 
 
4
9
,

 
 
2
5
8
,

 
 
3
7
,

 
 
6
0
,

 
 
8
5
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
2
0
1
,

 
 
9
5
]
,

 
[
4
5
6
,

 
 
1
4
0
,

 
 
1
3
1
,

 
 
5
4
7
,

 
 
1
1
1
2
,

 
 
6
1
6
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
2
,

 
 
1
1
0
5
4
,

 
 
8
3
5
7
3
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
,

 
 
2
2
,

 
 
1
3
,

 
 
8
,

 
 
2
7
,

 
 
3
3
4
,

 
 
4
5
9
,

 
 
5
,

 
 
1
1
,

 
 
8
,

 
 
1
2
6
0
,

 
 
3
2
,

 
 
8
6
9
,

 
 
4
1
0
,

 
 
1
2
8
4
,

 
 
1
3
,

 
 
5
8
7
,

 
 
2
2
,

 
 
6
,

 
 
9
0
,

 
 
1
4
,

 
 
9
7
,

 
 
5
5
,

 
 
2
8
9
5
,

 
 
1
4
0
]
,

 
[
1
1
1
2
,

 
 
9
6
9
,

 
 
3
2
0
,

 
 
5
,

 
 
1
9
6
,

 
 
5
0
0
,

 
 
5
4
5
,

 
 
8
,

 
 
1
9
6
,

 
 
2
,

 
 
1
0
4
6
,

 
 
3
3
,

 
 
3
0
8
,

 
 
4
7
,

 
 
3
,

 
 
2
0
,

 
 
5
2
9
,

 
 
1
4
0
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
4
7
,

 
 
6
,

 
 
1
3
1
,

 
 
2
,

 
 
5
0
2
2
,

 
 
3
7
8
4
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
9
0
,

 
 
1
4
,

 
 
7
5
4
,

 
 
2
,

 
 
1
6
,

 
 
1
5
9
3
,

 
 
5
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
1
3
4
,

 
 
6
,

 
 
3
9
7
6
]
,

 
[
6
,

 
 
1
8
,

 
 
2
4
7
,

 
 
5
0
0
,

 
 
7
,

 
 
2
4
,

 
 
1
8
8
,

 
 
1
5
,

 
 
6
0
,

 
 
5
0
3
2
,

 
 
7
,

 
 
2
4
,

 
 
1
9
9
,

 
 
1
8
8
,

 
 
1
2
,

 
 
2
6
1
2
,

 
 
2
5
,

 
 
2
1
7
,

 
 
1
1
,

 
 
2
4
,

 
 
6
9
,

 
 
3
,

 
 
2
0
6
1
,

 
 
1
5
,

 
 
8
6
9
,

 
 
1
3
6
8
,

 
 
2
1
,

 
 
7
8
3
,

 
 
3
4
4
7
,

 
 
3
,

 
 
1
0
7
,

 
 
2
2
6
2
9
,

 
 
1
0
7
,

 
 
1
6
0
5
2
1
,

 
 
2
1
0
,

 
 
3
,

 
 
5
4
,

 
 
1
8
,

 
 
4
9
4
2
5
,

 
 
7
,

 
 
1
9
,

 
 
1
9
9
,

 
 
1
3
3
,

 
 
5
5
,

 
 
6
1
,

 
 
3
8
7
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
3
4
6
6
,

 
 
2
,

 
 
7
9
,

 
 
8
4
,

 
 
6
,

 
 
5
6
,

 
 
9
4
,

 
 
6
1
,

 
 
1
2
3
5
,

 
 
1
4
6
,

 
 
5
4
,

 
 
2
8
6
,

 
 
6
,

 
 
1
8
,

 
 
2
8
6
4
0
,

 
 
4
4
,

 
 
8
1
0
8
]
,

 
[
7
,
 
7
7
,
 
1
4
6
,
 
2
4
2
,
 
6
1
9
]
,

 
[
5
0
,
 
5
0
,
 
3
0
7
,
 
3
7
3
,
 
3
7
,
 
3
8
,
 
6
,
 
1
2
6
,
 
6
5
]
,

 
[
2
7
,

 
 
3
9
3
,

 
 
3
7
7
,

 
 
2
1
3
,

 
 
3
7
,

 
 
7
,

 
 
3
9
,

 
 
5
9
7
,

 
 
2
1
,

 
 
1
1
,

 
 
1
,

 
 
1
7
6
4
,

 
 
1
8
5
,

 
 
9
1
,

 
 
1
3
1
,

 
 
3
,

 
 
7
9
3
2
,

 
 
8
5
2
,

 
 
2
2
8
7
,

 
 
3
,

 
 
4
5
9
6
,

 
 
8
,

 
 
7
8
,

 
 
2
8
,

 
 
2
2
9
,

 
 
3
5
5
1
,

 
 
2
5
5
,

 
 
1
,

 
 
8
3
9
,

 
 
3
,

 
 
4
,

 
 
1
0
5
0
6
,

 
 
1
3
3
5
,

 
 
1
,

 
 
1
2
5
5
,

 
 
1
1
6
,

 
 
1
8
1
,

 
 
1
3
1
6
,

 
 
4
1
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
5
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
6
,

 
 
5
,

 
 
6
1
,

 
 
2
8
1
,

 
 
2
6
7
2
,

 
 
1
8
,

 
 
9
2
5
6
,

 
 
1
4
0
7
,

 
 
2
7
9
1
,

 
 
2
8
,

 
 
4
2
,

 
 
6
6
1
,

 
 
4
,

 
 
6
1
2
,

 
 
1
2
,

 
 
1
7
5
8
,

 
 
2
8
0
,

 
 
7
,

 
 
2
2
9
,

 
 
1
6
,

 
 
5
8
,

 
 
3
3
3
6
,

 
 
2
6
,

 
 
1
8
5
,

 
 
1
,

 
 
2
5
0
,

 
 
5
,

 
 
6
7
3
,

 
 
3
,

 
 
1
1
,

 
 
7
9
9
]
,

 
[
7
2
,
 
1
3
7
6
,
 
1
3
,
 
2
,
 
1
,
 
4
6
,
 
2
9
]
,

 
[
1
0
2
,

 
 
1
0
1
,

 
 
7
,

 
 
6
3
,

 
 
9
,

 
 
3
1
9
,

 
 
4
2
,

 
 
3
0
9
0
,

 
 
2
,

 
 
3
1
4
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
7
3
4
,

 
 
1
4
,

 
 
4
1
3
,

 
 
2
6
,

 
 
3
6
6
,

 
 
3
1
4
4
,

 
 
1
5
,

 
 
3
0
,

 
 
2
2
3
,

 
 
9
5
,

 
 
1
2
,

 
 
1
,

 
 
2
3
4
,

 
 
4
9
5
,

 
 
1
1
4
7
4
,

 
 
2
5
1
4
2
,

 
 
8
5
6
,

 
 
4
6
]
,

 
[
1
7
6
,

 
 
3
1
2
,

 
 
4
1
0
,

 
 
1
0
6
5
1
8
,

 
 
2
4
3
,

 
 
1
6
0
5
2
2
,

 
 
1
6
0
5
2
3
,

 
 
9
4
2
,

 
 
3
2
0
9
,

 
 
3
1
,

 
 
1
9
1
4
,

 
 
1
6
0
5
2
4
,

 
 
1
0
,

 
 
3
2
8
0
,

 
 
1
6
0
5
2
5
,

 
 
1
0
6
,

 
 
4
0
3
,

 
 
9
,

 
 
1
,

 
 
1
9
1
4
,

 
 
2
4
,

 
 
2
1
0
5
,

 
 
4
7
1
0
]
,

 
[
1
,

 
 
1
1
4
2
,

 
 
3
,

 
 
1
8
2
3
,

 
 
1
3
6
8
,

 
 
9
5
6
,

 
 
8
,

 
 
4
5
1
9
,

 
 
1
1
0
,

 
 
3
2
2
,

 
 
1
1
1
5
,

 
 
1
,

 
 
4
5
3
,

 
 
1
5
1
,

 
 
3
0
6
6
,

 
 
5
,

 
 
7
5
0
4
,

 
 
5
4
,

 
 
8
,

 
 
1
1
3
5
,

 
 
1
,

 
 
1
0
5
,

 
 
1
1
6
,

 
 
8
,

 
 
6
9
3
9
,

 
 
6
0
6
9
,

 
 
2
1
,

 
 
1
7
9
,

 
 
5
,

 
 
1
8
5
5
,

 
 
4
4
7
4
,

 
 
5
4
,

 
 
3
9
7
,

 
 
1
1
,

 
 
1
4
,

 
 
7
7
,

 
 
2
3
8
2
2
,

 
 
2
6
,

 
 
6
6
,

 
 
9
0
9
7
,

 
 
1
0
5
,

 
 
8
,

 
 
2
5
1
4
3
,

 
 
4
0
,

 
 
3
3
0
,

 
 
1
,

 
 
1
8
2
3
,

 
 
8
4
3
,

 
 
1
7
7
,

 
 
1
7
6
8
,

 
 
2
,

 
 
3
8
5
,

 
 
2
5
,

 
 
1
4
,

 
 
5
1
,

 
 
1
3
9
1
,

 
 
4
1
,

 
 
3
4
4
6
,

 
 
1
,

 
 
4
4
7
4
,

 
 
1
1
6
,

 
 
2
8
3
6
,

 
 
2
1
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
7
3
,

 
 
8
,

 
 
1
,

 
 
5
1
2
1
,

 
 
1
9
8
8
,

 
 
2
9
7
,

 
 
9
,

 
 
8
,

 
 
1
4
,

 
 
3
7
3
1
,

 
 
4
4
7
4
,

 
 
5
,

 
 
1
7
9
8
,

 
 
1
0
,

 
 
1
,

 
 
1
1
9
9
,

 
 
2
7
7
8
,

 
 
1
7
9
8
,

 
 
1
1
1
5
,

 
 
1
,

 
 
1
7
7
2
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
3
7
5
,

 
 
1
5
0
,

 
 
1
6
0
5
2
6
,

 
 
3
6
2
3
,

 
 
5
,

 
 
2
1
3
4
,

 
 
8
,

 
 
1
4
,

 
 
1
1
1
,

 
 
2
7
,

 
 
7
4
0
,

 
 
4
6
7
1
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
2
1
3
4
,

 
 
3
,

 
 
1
9
4
1
3
,

 
 
8
4
6
6
,

 
 
3
9
,

 
 
1
6
,

 
 
2
7
,

 
 
7
4
0
,

 
 
4
4
7
,

 
 
1
5
,

 
 
1
0
4
,

 
 
1
7
0
,

 
 
6
9
,

 
 
7
3
,

 
 
4
2
,

 
 
4
3
0
,

 
 
7
4
0
,

 
 
2
1
3
4
,

 
 
5
,

 
 
3
6
2
3
,

 
 
4
3
3
,

 
 
2
1
,

 
 
6
9
8
0
1
,

 
 
3
,

 
 
1
0
4
,

 
 
1
7
0
,

 
 
4
8
,

 
 
1
,

 
 
1
6
0
5
2
7
,

 
 
3
,

 
 
1
0
6
5
1
9
,

 
 
2
9
6
8
6
,

 
 
3
,

 
 
1
6
0
5
2
8
,

 
 
5
,

 
 
3
9
6
8
2
,

 
 
3
,

 
 
1
6
0
5
2
9
,

 
 
1
0
,

 
 
1
6
6
,

 
 
7
,

 
 
5
8
4
,

 
 
4
1
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
1
1
1
,

 
 
1
0
5
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
5
0
]
,

 
[
7
,

 
 
5
9
,

 
 
7
0
,

 
 
1
,

 
 
5
2
5
,

 
 
2
,

 
 
1
3
,

 
 
2
6
,

 
 
4
1
7
0
,

 
 
7
4
,

 
 
8
,

 
 
1
1
,

 
 
4
4
1
,

 
 
1
2
,

 
 
4
,

 
 
1
7
0
7
,

 
 
3
4
9
8
,

 
 
2
,

 
 
2
1
5
5
,

 
 
1
8
3
,

 
 
1
7
0
7
,

 
 
2
8
6
4
1
,

 
 
9
8
7
,

 
 
9
0
6
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
2
2
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
1
1
6
,

 
 
8
1
7
6
,

 
 
2
4
,

 
 
4
4
9
7
,

 
 
1
8
2
,

 
 
1
0
,

 
 
1
,

 
 
2
0
7
2
,

 
 
1
9
8
,

 
 
2
6
,

 
 
2
2
,

 
 
2
5
9
,

 
 
1
0
3
,

 
 
5
2
0
,

 
 
1
3
,

 
 
7
,

 
 
4
3
,

 
 
6
8
5
,

 
 
1
1
,

 
 
6
,

 
 
3
9
,

 
 
1
3
5
3
,

 
 
3
8
5
,

 
 
2
5
,

 
 
1
4
,

 
 
1
,

 
 
3
7
6
7
,

 
 
3
,

 
 
1
,

 
 
2
9
7
,

 
 
1
8
1
9
,

 
 
2
6
5
9
,

 
 
2
4
,

 
 
2
7
5
2
,

 
 
1
8
5
,

 
 
1
2
6
,

 
 
1
4
,

 
 
3
0
,

 
 
1
3
6
3
,

 
 
6
4
,

 
 
1
4
4
,

 
 
7
1
,

 
 
4
,

 
 
9
3
1
,

 
 
1
7
4
3
,

 
 
7
2
,

 
 
1
3
1
4
,

 
 
3
5
,

 
 
3
8
5
,

 
 
1
,

 
 
3
3
9
8
,

 
 
9
8
7
,

 
 
9
0
6
,

 
 
9
0
3
7
,

 
 
2
4
,

 
 
9
2
4
,

 
 
2
2
,

 
 
1
,

 
 
2
9
7
,

 
 
1
8
1
9
,

 
 
3
2
1
6
7
,

 
 
2
4
,

 
 
4
,

 
 
1
8
3
7
1
,

 
 
3
,

 
 
2
2
4
2
,

 
 
7
1
,

 
 
1
4
,

 
 
1
,

 
 
1
1
4
,

 
 
8
5
,

 
 
1
4
7
,

 
 
3
3
,

 
 
8
3
5
7
4
,

 
 
8
3
5
7
5
,

 
 
2
2
3
,

 
 
3
,

 
 
3
5
5
,

 
 
4
,

 
 
5
7
4
8
,

 
 
1
1
1
6
,

 
 
3
,

 
 
1
3
,

 
 
7
0
8
,

 
 
3
,

 
 
2
2
8
,

 
 
8
,

 
 
2
,

 
 
1
4
7
8
,

 
 
9
,

 
 
1
,

 
 
2
4
0
5
,

 
 
2
2
4
2
,

 
 
6
2
5
,

 
 
2
8
5
,

 
 
1
7
8
1
,

 
 
5
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
7
2
9
4
,

 
 
9
,

 
 
2
9
2
5
,

 
 
7
5
,

 
 
4
5
,

 
 
1
6
,

 
 
4
4
3
3
,

 
 
5
,

 
 
9
,

 
 
2
9
2
1
,

 
 
7
5
,

 
 
4
5
,

 
 
1
6
,

 
 
1
6
0
5
3
0
,

 
 
3
1
,

 
 
8
5
,

 
 
2
,

 
 
8
5
,

 
 
1
8
5
,

 
 
1
,

 
 
3
1
1
9
,

 
 
6
,

 
 
1
7
9
5
,

 
 
1
2
,

 
 
3
5
5
,

 
 
4
,

 
 
9
2
4
,

 
 
6
2
5
,

 
 
1
0
,

 
 
1
,

 
 
4
5
3
,

 
 
1
5
8
,

 
 
4
2
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
1
1
5
1
,

 
 
5
,

 
 
9
4
3
,

 
 
5
1
,

 
 
8
7
,

 
 
1
4
,

 
 
1
8
8
3
,

 
 
9
4
,

 
 
1
1
,

 
 
1
4
3
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
7
1
,

 
 
1
6
5
,

 
 
7
6
,

 
 
1
5
,

 
 
4
,

 
 
1
9
0
5
1
,

 
 
2
,

 
 
1
1
7
,

 
 
9
,

 
 
1
,

 
 
8
3
5
7
5
,

 
 
1
9
8
,

 
 
8
,

 
 
5
7
4
,

 
 
1
2
7
0
,

 
 
4
0
,

 
 
1
2
2
5
,

 
 
2
0
6
5
]
,

 
[
3
1
2
8
,

 
 
1
0
7
9
8
,

 
 
2
2
,

 
 
9
9
3
0
,

 
 
7
2
5
4
,

 
 
3
1
2
8
,

 
 
1
0
7
9
8
,

 
 
8
,

 
 
4
8
,

 
 
3
8
,

 
 
7
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
9
3
,

 
 
5
2
,

 
 
8
,

 
 
1
0
,

 
 
1
2
,

 
 
4
,

 
 
1
6
0
5
3
1
,

 
 
2
7
6
7
7
,

 
 
3
2
1
6
8
,

 
 
1
6
8
4
]
,

 
[
1
6
0
5
3
2
,

 
 
4
3
8
,

 
 
7
9
5
,

 
 
1
3
7
,

 
 
4
4
6
,

 
 
4
,

 
 
2
6
0
,

 
 
8
3
,

 
 
1
2
5
,

 
 
7
4
6
,

 
 
7
9
5
,

 
 
1
9
,

 
 
9
2
,

 
 
1
0
9
,

 
 
1
6
0
5
3
3
,

 
 
3
2
,

 
 
7
8
4
9
,

 
 
3
4
3
9
,

 
 
2
4
7
,

 
 
4
2
3
5
8
,

 
 
9
,

 
 
7
1
,

 
 
4
9
,

 
 
4
,

 
 
2
3
5
,

 
 
2
0
8
3
,

 
 
1
0
5
,

 
 
1
2
,

 
 
7
5
,

 
 
6
2
,

 
 
3
4
,

 
 
1
4
,

 
 
2
3
7
,

 
 
7
0
,

 
 
1
3
,

 
 
1
6
4
4
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
4
3
2
,

 
 
2
1
2
,

 
 
1
1
1
,

 
 
1
,

 
 
8
3
,

 
 
8
3
4
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
2
5
,

 
 
9
6
,

 
 
7
8
,

 
 
1
,

 
 
4
4
2
,

 
 
2
8
,

 
 
3
4
1
,

 
 
1
3
8
1
,

 
 
8
3
5
,

 
 
3
6
,

 
 
3
6
6
,

 
 
3
5
,

 
 
3
1
0
,

 
 
1
3
,

 
 
2
7
0
,

 
 
1
5
1
,

 
 
1
9
2
6
,

 
 
5
4
2
,

 
 
2
2
,

 
 
5
1
,

 
 
1
8
,

 
 
4
4
,

 
 
8
0
6
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
1
,

 
 
8
,

 
 
1
4
5
3
,

 
 
2
8
1
,

 
 
1
0
6
5
2
0
,

 
 
5
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
3
2
1
2
,

 
 
8
8
,

 
 
1
0
,

 
 
4
9
5
]
,

 
[
3
2
1
6
9
,

 
 
5
4
3
1
4
,

 
 
2
9
6
8
7
,

 
 
7
,

 
 
6
5
8
,

 
 
6
,

 
 
1
7
3
,

 
 
4
,

 
 
6
3
2
,

 
 
1
0
5
8
1
,

 
 
2
,

 
 
1
3
,

 
 
2
3
,

 
 
7
1
3
,

 
 
1
0
3
,

 
 
6
,

 
 
3
4
5
,

 
 
2
0
,

 
 
1
0
6
,

 
 
8
3
7
9
,

 
 
5
9
0
,

 
 
3
2
1
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
1
2
6
,

 
 
8
4
5
,

 
 
9
5
,

 
 
9
5
5
,

 
 
2
9
5
0
,

 
 
8
5
0
,

 
 
1
3
6
5
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
7
,

 
 
1
7
3
,

 
 
1
0
5
,

 
 
3
5
,

 
 
6
0
4
4
,

 
 
5
4
4
,

 
 
1
6
0
5
3
4
,

 
 
3
3
9
9
,

 
 
3
2
4
6
,

 
 
3
5
,

 
 
7
1
4
1
,

 
 
1
8
7
9
,

 
 
2
6
,

 
 
1
5
8
,

 
 
1
8
7
,

 
 
1
,

 
 
1
4
5
3
,

 
 
1
0
5
,

 
 
6
9
,

 
 
5
1
,

 
 
1
6
7
,

 
 
1
1
,

 
 
2
4
,

 
 
1
4
,

 
 
1
2
8
5
,

 
 
1
1
,

 
 
2
4
,

 
 
1
4
5
3
,

 
 
2
6
,

 
 
1
4
,

 
 
1
2
8
5
,

 
 
7
,

 
 
2
3
9
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
,

 
 
1
0
5
,

 
 
1
2
7
,

 
 
2
1
,

 
 
2
9
5
,

 
 
2
6
,

 
 
2
4
,

 
 
1
4
,

 
 
2
6
4
4
,

 
 
7
,

 
 
1
7
3
8
,

 
 
1
7
3
,

 
 
1
,

 
 
1
2
8
7
,

 
 
5
,

 
 
4
7
2
5
,

 
 
3
,

 
 
8
3
5
7
6
,

 
 
1
6
0
5
3
5
,

 
 
4
0
8
,

 
 
2
6
,

 
 
1
5
8
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
2
,

 
 
6
2
,

 
 
1
8
7
,

 
 
1
,

 
 
1
4
5
3
,

 
 
1
0
5
,

 
 
7
,

 
 
7
3
6
,

 
 
1
8
2
,

 
 
7
1
4
1
,

 
 
1
8
7
9
,

 
 
2
4
,

 
 
4
1
5
3
,

 
 
1
7
9
9
,

 
 
5
,

 
 
7
1
6
,

 
 
1
1
,

 
 
2
4
,

 
 
2
1
7
,

 
 
5
,

 
 
1
0
8
8
,

 
 
1
1
,

 
 
7
4
,

 
 
3
9
,

 
 
1
3
,

 
 
1
6
,

 
 
5
,

 
 
7
8
,

 
 
1
8
,

 
 
1
1
2
,

 
 
3
6
5
1
,

 
 
4
1
9
,

 
 
1
3
1
2
,

 
 
6
2
,

 
 
5
6
2
9
,

 
 
3
8
,

 
 
8
,

 
 
3
6
8
,

 
 
1
5
,

 
 
8
3
5
7
6
,

 
 
1
0
6
5
2
1
,

 
 
1
7
0
,

 
 
2
8
,

 
 
3
4
1
,

 
 
1
,

 
 
2
7
0
,

 
 
5
3
3
,

 
 
7
,

 
 
1
4
4
0
,

 
 
1
5
0
8
,

 
 
4
2
8
,

 
 
8
,

 
 
4
4
5
,

 
 
1
7
0
0
,

 
 
4
0
2
,

 
 
5
,

 
 
1
7
2
,

 
 
4
7
2
5
,

 
 
8
,

 
 
4
4
5
,

 
 
1
4
8
,

 
 
5
,

 
 
1
4
8
,

 
 
1
2
7
,

 
 
1
1
2
,

 
 
1
8
,

 
 
1
4
,

 
 
3
7
5
3
,

 
 
3
3
,

 
 
4
0
,

 
 
5
,

 
 
3
9
,

 
 
1
6
,

 
 
1
2
8
5
,

 
 
3
2
,

 
 
2
7
,

 
 
3
3
0
5
,

 
 
2
8
,

 
 
3
4
1
,

 
 
5
,

 
 
8
3
5
7
6
,

 
 
1
0
6
5
2
1
,

 
 
1
7
0
,

 
 
3
9
3
,

 
 
4
0
2
5
,

 
 
3
8
,

 
 
8
,

 
 
1
,

 
 
2
4
9
]
,

 
[
5
0
,

 
 
1
7
1
,

 
 
3
1
0
,

 
 
6
4
4
,

 
 
2
,

 
 
2
8
,

 
 
1
1
,

 
 
8
,

 
 
4
1
9
,

 
 
2
1
7
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
1
2
2
9
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
3
4
,

 
 
6
,

 
 
2
1
0
4
]
,

 
[
1
0
1
,

 
 
7
,

 
 
4
5
,

 
 
8
2
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
8
4
,

 
 
5
9
,

 
 
3
7
3
,

 
 
1
6
0
5
3
6
,

 
 
1
5
6
6
,

 
 
2
5
6
,

 
 
1
1
,

 
 
1
5
5
,

 
 
6
9
,

 
 
9
,

 
 
4
5
,

 
 
2
3
3
6
,

 
 
3
7
,

 
 
1
9
2
,

 
 
5
,

 
 
1
9
6
2
,

 
 
3
7
,

 
 
4
5
9
7
,

 
 
6
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
2
9
0
,

 
 
4
,

 
 
2
4
2
,

 
 
1
0
6
5
2
2
,

 
 
1
5
,

 
 
3
6
7
7
,

 
 
1
6
9
1
,

 
 
7
,

 
 
8
1
,

 
 
3
5
8
,

 
 
5
2
,

 
 
8
,

 
 
4
,

 
 
3
5
9
,

 
 
2
,

 
 
1
1
8
4
5
,

 
 
4
7
6
,

 
 
6
,

 
 
6
5
,

 
 
5
7
2
,

 
 
2
8
2
,

 
 
5
5
8
,

 
 
9
9
7
,

 
 
4
3
3
5
,

 
 
2
3
7
,

 
 
5
,

 
 
8
9
,

 
 
5
7
2
,

 
 
9
7
0
,

 
 
1
2
,

 
 
5
8
]
,

 
[
7
,

 
 
3
3
2
,

 
 
7
,

 
 
4
3
,

 
 
1
5
5
2
,

 
 
6
,

 
 
6
0
,

 
 
2
7
3
3
,

 
 
1
0
5
7
7
,

 
 
1
6
2
,

 
 
4
4
,

 
 
2
8
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
6
0
,

 
 
4
4
,

 
 
2
0
3
3
,

 
 
2
1
,

 
 
2
8
,

 
 
1
2
5
3
,

 
 
2
3
3
,

 
 
8
7
,

 
 
7
,

 
 
6
6
,

 
 
3
6
5
9
,

 
 
6
,

 
 
3
,

 
 
1
,

 
 
4
2
0
,

 
 
3
9
8
,

 
 
7
2
3
]
,

 
[
1
6
8
,

 
 
7
3
9
,

 
 
4
,

 
 
1
0
3
5
8
,

 
 
6
7
,

 
 
1
9
2
,

 
 
1
6
8
,

 
 
1
9
4
,

 
 
1
2
6
4
,

 
 
1
6
8
,

 
 
7
3
9
,

 
 
8
3
8
0
,

 
 
6
7
,

 
 
1
4
8
8
,

 
 
2
9
3
8
,

 
 
2
8
6
4
2
]
,

 
[
1
0
4
,

 
 
6
6
,

 
 
1
1
5
6
3
,

 
 
2
4
8
,

 
 
4
2
7
,

 
 
2
,

 
 
1
2
5
0
4
,

 
 
1
0
,

 
 
1
5
8
8
7
,

 
 
2
2
4
,

 
 
1
0
,

 
 
1
,

 
 
1
3
8
,

 
 
1
1
6
,

 
 
1
7
,

 
 
6
9
8
0
2
,

 
 
4
2
,

 
 
2
0
7
,

 
 
2
1
,

 
 
6
8
,

 
 
1
6
0
5
,

 
 
1
3
4
4
,

 
 
1
6
9
,

 
 
2
5
5
,

 
 
2
6
,

 
 
1
7
,

 
 
8
2
9
6
,

 
 
1
7
9
6
,

 
 
1
3
,

 
 
2
9
,

 
 
1
,

 
 
4
7
5
,

 
 
5
9
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
2
0
0
6
,

 
 
2
,

 
 
6
9
8
0
2
,

 
 
7
8
,

 
 
5
9
,

 
 
6
,

 
 
4
9
,

 
 
1
1
8
,

 
 
4
4
2
,

 
 
1
1
3
8
2
,

 
 
5
,

 
 
1
5
2
,

 
 
1
1
,

 
 
2
,

 
 
1
6
0
5
3
7
,

 
 
4
3
2
,

 
 
2
9
,

 
 
4
1
,

 
 
1
8
,

 
 
1
9
1
5
,

 
 
3
,

 
 
6
5
7
6
,

 
 
1
0
6
,

 
 
4
1
,

 
 
8
9
,

 
 
5
,

 
 
4
4
,

 
 
4
1
8
,

 
 
1
9
5
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
5
5
,

 
 
1
6
9
,

 
 
1
2
3
6
,

 
 
4
1
6
,

 
 
1
9
8
6
,

 
 
2
7
6
8
,

 
 
6
1
7
,

 
 
6
,

 
 
4
6
6
,

 
 
2
,

 
 
8
2
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
3
0
2
,

 
 
5
6
6
,

 
 
1
2
,

 
 
6
9
8
0
2
,

 
 
2
3
6
7
,

 
 
5
6
0
,

 
 
8
2
5
2
,

 
 
9
5
5
]
,

 
[
1
1
9
,

 
 
3
,

 
 
3
8
7
,

 
 
4
6
3
,

 
 
3
5
3
8
0
,

 
 
1
2
9
,

 
 
3
1
,

 
 
1
6
0
5
3
8
,

 
 
1
6
0
5
3
9
,

 
 
1
6
0
5
4
0
,

 
 
4
2
,

 
 
5
7
,

 
 
5
4
4
6
,

 
 
3
2
,

 
 
3
7
4
0
7
,

 
 
1
2
,

 
 
1
,

 
 
4
5
1
,

 
 
2
1
2
,

 
 
2
8
3
,

 
 
5
8
5
,

 
 
1
5
7
,

 
 
3
1
,

 
 
1
5
8
2
,

 
 
1
9
4
1
,

 
 
2
1
3
,

 
 
5
,

 
 
3
3
2
2
,

 
 
1
1
,

 
 
1
4
3
,

 
 
1
5
7
,

 
 
7
3
,

 
 
1
2
7
,

 
 
5
,

 
 
4
4
1
7
,

 
 
3
2
,

 
 
1
7
9
,

 
 
1
4
,

 
 
6
7
4
,

 
 
2
,

 
 
9
4
,

 
 
1
1
,

 
 
1
2
,

 
 
1
3
,

 
 
1
3
,

 
 
8
,

 
 
2
,

 
 
4
5
8
,

 
 
7
7
9
,

 
 
2
,

 
 
4
,

 
 
4
4
7
,

 
 
5
4
,

 
 
2
4
,

 
 
2
3
2
6
,

 
 
1
5
0
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
1
7
0
8
,

 
 
8
6
,

 
 
1
7
7
7
,

 
 
4
1
,

 
 
1
8
,

 
 
7
2
2
3
,

 
 
7
1
8
,

 
 
2
8
,

 
 
1
7
9
,

 
 
2
4
3
5
,

 
 
5
,

 
 
6
1
1
5
,

 
 
1
6
0
5
4
1
,

 
 
7
9
,

 
 
3
,

 
 
7
0
6
6
,

 
 
3
,

 
 
6
0
2
3
,

 
 
2
4
,

 
 
3
0
9
,

 
 
4
,

 
 
1
1
2
0
4
,

 
 
5
,

 
 
2
4
1
,

 
 
5
8
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
5
4
3
1
5
,

 
 
1
5
6
7
4
,

 
 
3
,

 
 
4
4
4
4
,

 
 
1
4
8
8
6
,

 
 
7
0
6
6
,

 
 
5
,

 
 
1
,

 
 
7
0
6
6
,

 
 
3
,

 
 
6
0
2
3
,

 
 
5
,

 
 
1
,

 
 
7
0
6
6
,

 
 
3
,

 
 
6
0
2
3
,

 
 
8
,

 
 
1
4
,

 
 
1
1
6
1
,

 
 
6
2
5
5
,

 
 
9
3
5
2
,

 
 
9
,

 
 
8
,

 
 
4
8
,

 
 
3
5
8
,

 
 
1
,

 
 
7
0
6
6
,

 
 
3
,

 
 
3
2
5
3
,

 
 
8
,

 
 
1
0
1
6
3
,

 
 
2
5
1
4
4
,

 
 
2
5
,

 
 
9
,

 
 
1
,

 
 
7
0
6
6
,

 
 
3
,

 
 
1
5
4
0
,

 
 
8
,

 
 
1
5
2
6
5
,

 
 
3
9
6
8
3
,

 
 
2
5
,

 
 
9
,

 
 
1
,

 
 
7
0
6
6
,

 
 
3
,

 
 
1
0
3
7
,

 
 
8
,

 
 
1
5
4
7
2
,

 
 
1
0
4
,

 
 
9
9
3
1
,

 
 
7
5
9
6
,

 
 
5
,

 
 
1
9
0
5
2
,

 
 
1
,

 
 
4
3
2
,

 
 
1
4
5
,

 
 
6
4
,

 
 
8
,

 
 
7
8
,

 
 
9
0
,

 
 
1
,

 
 
4
1
8
,

 
 
1
0
,

 
 
2
1
4
,

 
 
3
5
6
,

 
 
1
,

 
 
1
7
9
,

 
 
5
,

 
 
4
4
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
2
3
2
6
,

 
 
3
8
8
,

 
 
9
,

 
 
2
4
9
,

 
 
8
,

 
 
1
7
7
7
,

 
 
5
,

 
 
7
,

 
 
7
0
5
,

 
 
1
3
0
4
,

 
 
1
1
,

 
 
2
1
,

 
 
9
,

 
 
1
0
7
,

 
 
9
3
5
,

 
 
5
,

 
 
3
0
,

 
 
3
8
7
,

 
 
2
4
,

 
 
3
2
6
5
,

 
 
9
,

 
 
1
0
7
,

 
 
8
,

 
 
1
4
,

 
 
7
0
9
,

 
 
1
2
,

 
 
1
3
8
,

 
 
2
5
,

 
 
1
6
0
5
4
2
,

 
 
9
,

 
 
4
1
8
,

 
 
9
9
8
9
,

 
 
1
,

 
 
5
3
7
,

 
 
2
0
9
4
,

 
 
5
,

 
 
1
6
0
5
4
3
,

 
 
3
7
,

 
 
3
1
,

 
 
9
6
,

 
 
1
2
9
,

 
 
3
0
,

 
 
1
7
0
,

 
 
2
9
,

 
 
1
5
6
5
,

 
 
1
,

 
 
2
1
2
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
9
9
9
,

 
 
2
,

 
 
1
6
,

 
 
1
9
0
5
3
,

 
 
2
,

 
 
3
4
5
,

 
 
6
4
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
8
3
5
7
7
,

 
 
6
4
,

 
 
2
,

 
 
1
5
7
,

 
 
5
,

 
 
6
6
1
,

 
 
5
0
0
7
,

 
 
4
1
8
,

 
 
2
4
4
6
2
,

 
 
1
5
7
,

 
 
4
9
4
2
6
,

 
 
1
,

 
 
4
4
7
,

 
 
2
9
,

 
 
3
8
8
,

 
 
8
3
5
7
8
,

 
 
3
5
4
,

 
 
8
,

 
 
2
3
2
6
,

 
 
3
2
9
,

 
 
8
3
5
7
9
,

 
 
5
,

 
 
4
9
9
,

 
 
1
7
,

 
 
7
,

 
 
7
,

 
 
4
5
,

 
 
1
4
,

 
 
1
6
0
5
4
4
,

 
 
4
9
9
,

 
 
2
,

 
 
5
5
,

 
 
3
9
9
,

 
 
5
0
0
8
,

 
 
3
7
4
0
8
,

 
 
2
5
,

 
 
2
4
2
,

 
 
3
0
8
1
2
,

 
 
1
4
,

 
 
6
7
4
,

 
 
2
,

 
 
9
4
,

 
 
1
1
,

 
 
3
1
9
4
,

 
 
3
7
3
6
,

 
 
1
5
6
4
,

 
 
7
3
,

 
 
6
,

 
 
4
5
,

 
 
3
5
6
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
5
,

 
 
3
8
7
,

 
 
3
1
,

 
 
1
,

 
 
1
8
0
,

 
 
1
0
6
5
2
3
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
3
8
9
5
,

 
 
3
7
,

 
 
5
,

 
 
2
4
6
,

 
 
3
0
,

 
 
1
0
9
,

 
 
1
7
4
,

 
 
2
5
,

 
 
2
5
7
7
,

 
 
7
,

 
 
8
1
,

 
 
7
6
,

 
 
3
,

 
 
1
3
,

 
 
2
4
4
6
3
,

 
 
5
4
,

 
 
8
,

 
 
2
8
,

 
 
1
2
,

 
 
9
8
,

 
 
3
5
6
,

 
 
1
1
,

 
 
4
0
,

 
 
8
9
,

 
 
1
0
6
5
2
3
]
,

 
[
4
1
8
5
,
 
6
9
8
0
3
,
 
3
,
 
1
6
1
3
6
]
,

 
[
3
6
6
,

 
 
4
3
9
,

 
 
5
0
,

 
 
2
5
6
,

 
 
1
,

 
 
4
3
9
,

 
 
3
1
,

 
 
1
,

 
 
7
8
8
,

 
 
1
6
0
5
4
5
,

 
 
2
9
,

 
 
9
,

 
 
2
5
6
6
,

 
 
2
4
,

 
 
1
1
8
4
6
,

 
 
2
7
1
,

 
 
1
0
,

 
 
1
8
6
1
,

 
 
1
6
1
3
7
,

 
 
2
8
1
3
,

 
 
3
2
1
,

 
 
5
,

 
 
2
0
5
4
,

 
 
9
,

 
 
3
9
6
8
4
,

 
 
2
3
3
7
,

 
 
1
7
4
,

 
 
2
,

 
 
1
0
4
,

 
 
2
9
,

 
 
2
2
8
3
,

 
 
3
0
9
5
,

 
 
2
1
2
1
,

 
 
2
2
8
0
]
,

 
[
5
8
,

 
 
4
8
7
,

 
 
9
5
,

 
 
1
2
,

 
 
6
4
2
8
,

 
 
1
3
,

 
 
2
3
,

 
 
4
1
,

 
 
1
8
,

 
 
4
,

 
 
2
6
0
,

 
 
1
7
2
0
,

 
 
5
4
,

 
 
7
,

 
 
1
9
,

 
 
1
9
9
5
,

 
 
1
1
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
5
7
3
,

 
 
2
2
,

 
 
6
,

 
 
9
9
,

 
 
1
4
,

 
 
3
0
9
,

 
 
1
2
1
9
,

 
 
5
,

 
 
4
3
6
3
,

 
 
1
,

 
 
2
5
3
,

 
 
3
1
,

 
 
1
,

 
 
3
8
1
,

 
 
3
2
0
2
,

 
 
2
3
]
,

 
[
6
8
,

 
 
1
0
9
,

 
 
2
4
,

 
 
1
3
4
5
5
,

 
 
1
6
0
5
4
6
,

 
 
1
4
,

 
 
1
3
4
5
5
,

 
 
6
9
8
0
4
,

 
 
7
,

 
 
8
1
,

 
 
4
9
1
,

 
 
3
3
,

 
 
6
8
,

 
 
1
7
4
5
4
,

 
 
1
5
6
7
5
,

 
 
2
5
2
4
,

 
 
1
4
3
,

 
 
8
9
,

 
 
7
,

 
 
6
6
,

 
 
1
9
,

 
 
6
8
,

 
 
1
7
4
5
4
,

 
 
6
5
4
7
,

 
 
2
0
6
0
,

 
 
2
1
,

 
 
1
6
0
,

 
 
6
9
8
0
5
,

 
 
1
,

 
 
4
0
0
,

 
 
2
4
,

 
 
4
,

 
 
3
2
6
,

 
 
3
5
9
8
,

 
 
1
0
,

 
 
1
,

 
 
2
3
7
6
,

 
 
2
4
4
,

 
 
3
2
6
,

 
 
3
4
9
,

 
 
7
,

 
 
4
9
9
,

 
 
8
1
,

 
 
4
,

 
 
2
8
9
2
,

 
 
1
7
9
,

 
 
1
8
9
6
,

 
 
9
4
0
7
,

 
 
2
9
4
0
,

 
 
3
,

 
 
1
8
9
2
,

 
 
3
1
,

 
 
1
6
0
5
4
7
]
,

 
[
1
1
,
 
8
,
 
7
4
0
,
 
2
,
 
1
9
3
,
 
9
,
 
2
1
0
,
 
2
5
6
6
,
 
9
9
9
0
,
 
3
3
,
 
1
,
 
1
3
9
,
 
3
7
4
0
9
,
 
1
0
,
 
6
0
2
3
]
,

 
[
9
5
,
 
1
2
,
 
2
6
1
6
,
 
9
,
 
1
2
7
,
 
2
7
,
 
4
5
5
2
6
,
 
4
8
6
]
,

 
[
5
,
 
7
,
 
4
3
,
 
4
8
,
 
2
,
 
3
7
4
1
0
,
 
3
2
2
,
 
1
5
,
 
8
8
]
,

 
[
5
,
 
4
0
0
,
 
4
2
,
 
6
6
,
 
3
3
3
,
 
1
1
5
,
 
4
0
9
,
 
9
6
,
 
1
5
1
,
 
9
4
8
,
 
1
3
8
8
,
 
1
9
,
 
2
3
7
,
 
5
7
,
 
1
2
7
1
]
,

 
[
7
1
,

 
 
1
0
,

 
 
1
,

 
 
1
7
9
,

 
 
2
5
,

 
 
5
8
,

 
 
1
0
4
2
2
,

 
 
1
0
,

 
 
2
0
,

 
 
1
7
0
,

 
 
7
9
2
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
,

 
 
7
3
3
,

 
 
2
6
,

 
 
9
,

 
 
5
9
3
,

 
 
4
,

 
 
4
2
3
,

 
 
8
2
2
,

 
 
7
,

 
 
2
4
,

 
 
5
8
,

 
 
2
9
2
2
,

 
 
3
2
,

 
 
2
0
,

 
 
4
3
7
,

 
 
1
6
0
5
4
8
,

 
 
3
7
,

 
 
1
9
2
,

 
 
2
1
,

 
 
4
,

 
 
3
0
8
1
3
,

 
 
3
5
,

 
 
3
4
8
5
,

 
 
4
,

 
 
1
8
3
7
2
,

 
 
3
0
1
7
,

 
 
5
,

 
 
4
,

 
 
4
5
4
3
,

 
 
1
0
6
5
2
4
,

 
 
3
5
,

 
 
7
0
8
8
,

 
 
1
6
0
5
4
9
,

 
 
3
7
,

 
 
1
7
,

 
 
2
7
,

 
 
1
0
6
5
2
5
,

 
 
7
2
6
,

 
 
3
,

 
 
7
8
6
,

 
 
1
2
2
8
1
,

 
 
2
6
4
,

 
 
9
3
,

 
 
4
,

 
 
1
9
8
9
,

 
 
7
1
5
,

 
 
2
1
7
1
,

 
 
2
,

 
 
2
5
8
,

 
 
2
7
,

 
 
1
7
1
0
,

 
 
3
8
7
,

 
 
3
,

 
 
3
1
0
1
,

 
 
2
7
,

 
 
3
8
7
,

 
 
5
4
,

 
 
3
3
6
6
7
,

 
 
7
5
6
2
,

 
 
1
8
7
,

 
 
1
7
,

 
 
6
,

 
 
1
1
7
,

 
 
1
0
1
,

 
 
7
,

 
 
2
7
5
,

 
 
9
,

 
 
2
6
8
,

 
 
2
,

 
 
1
0
4
6
,

 
 
2
,

 
 
1
,

 
 
6
9
8
0
,

 
 
2
4
,

 
 
4
,

 
 
3
6
6
,

 
 
4
0
5
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
1
6
0
5
5
0
,

 
 
5
1
0
,

 
 
1
7
1
5
9
,

 
 
1
3
5
,

 
 
2
9
5
6
,

 
 
1
2
0
6
7
,

 
 
1
5
1
,

 
 
1
0
7
9
9
,

 
 
2
,

 
 
8
0
5
,

 
 
1
5
4
,

 
 
1
5
,

 
 
3
4
6
5
,

 
 
1
2
,

 
 
4
,

 
 
4
4
2
,

 
 
1
2
4
3
,

 
 
2
,

 
 
1
,

 
 
1
6
0
5
5
1
,

 
 
2
1
2
0
,

 
 
3
,

 
 
3
0
,

 
 
9
1
8
,

 
 
3
,

 
 
3
0
0
,

 
 
4
9
5
,

 
 
1
3
7
,

 
 
3
6
9
,

 
 
4
4
6
,

 
 
6
,

 
 
1
7
,

 
 
1
2
6
1
,

 
 
6
2
,

 
 
1
8
8
8
,

 
 
7
3
,

 
 
1
2
,

 
 
1
,

 
 
3
9
6
8
5
,

 
 
2
9
4
,

 
 
7
,

 
 
5
8
4
,

 
 
1
5
2
6
6
,

 
 
2
0
,

 
 
8
1
3
,

 
 
3
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
1
,

 
 
2
0
7
0
,

 
 
1
6
0
5
5
2
,

 
 
7
,

 
 
2
4
,

 
 
1
5
5
5
,

 
 
2
,

 
 
6
3
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
6
9
8
0
6
,

 
 
3
,

 
 
8
7
6
,

 
 
4
6
]
,

 
[
6
0
,
 
7
2
2
,
 
5
,
 
1
8
,
 
1
5
,
 
4
,
 
5
8
3
1
,
 
9
3
6
]
,

 
[
2
9
6
,
 
5
1
,
 
1
8
,
 
7
3
4
,
 
1
3
7
,
 
1
6
3
1
,
 
9
,
 
4
3
7
,
 
4
7
,
 
2
1
,
 
4
,
 
5
1
5
,
 
3
,
 
4
5
2
0
,
 
9
0
6
,
 
4
6
]
,

 
[
2
5
9
,

 
 
3
9
,

 
 
3
4
,

 
 
2
7
,

 
 
1
0
,

 
 
2
5
3
,

 
 
6
3
8
,

 
 
1
2
,

 
 
1
6
0
,

 
 
5
,

 
 
2
3
3
,

 
 
5
,

 
 
6
3
,

 
 
1
,

 
 
2
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
7
2
7
,

 
 
2
1
8
7
,

 
 
1
5
,

 
 
4
7
,

 
 
1
2
0
,

 
 
1
,

 
 
2
8
0
3
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
,

 
 
2
1
6
4
,

 
 
1
1
9
4
,

 
 
3
,

 
 
1
4
9
,

 
 
7
8
1
,

 
 
2
8
6
0
,

 
 
1
,

 
 
2
8
0
3
,

 
 
1
8
,

 
 
1
2
,

 
 
2
1
0
5
,

 
 
4
7
9
,

 
 
4
6
4
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
2
4
3
5
,

 
 
5
8
0
7
,

 
 
5
6
9
,

 
 
9
,

 
 
1
8
,

 
 
1
0
,

 
 
1
,

 
 
1
3
4
2
,

 
 
1
8
4
1
]
,

 
[
8
6
0
6
,

 
 
6
3
9
,

 
 
3
9
,

 
 
1
6
3
7
,

 
 
1
3
6
,

 
 
4
9
4
2
7
,

 
 
6
3
9
,

 
 
2
,

 
 
1
1
0
5
5
,

 
 
1
6
0
5
5
3
,

 
 
7
8
,

 
 
2
3
9
,

 
 
8
6
0
6
,

 
 
1
7
,

 
 
1
,

 
 
1
0
1
6
4
,

 
 
3
,

 
 
1
,

 
 
9
4
0
8
,

 
 
2
2
8
,

 
 
1
1
9
3
,

 
 
1
5
4
,

 
 
1
3
3
8
,

 
 
1
5
1
,

 
 
9
,

 
 
4
7
]
,

 
[
6
2
0
0
,
 
2
5
8
,
 
4
,
 
7
4
5
,
 
2
9
6
,
 
2
5
,
 
4
4
]
,

 
[
1
0
5
4
,

 
 
3
,

 
 
1
,

 
 
1
4
9
,

 
 
1
7
3
,

 
 
2
8
6
8
,

 
 
3
4
7
,

 
 
1
,

 
 
2
2
2
1
,

 
 
6
9
1
0
,

 
 
1
5
8
8
8
,

 
 
5
,

 
 
1
2
2
8
2
,

 
 
1
8
,

 
 
1
,

 
 
1
3
9
,

 
 
3
9
6
8
6
,

 
 
1
1
,

 
 
1
9
9
8
,

 
 
1
2
5
9
,

 
 
5
,

 
 
1
7
,

 
 
1
3
9
4
,

 
 
1
7
,

 
 
7
,

 
 
3
9
,

 
 
3
7
3
,

 
 
3
9
5
,

 
 
7
7
,

 
 
4
7
,

 
 
2
2
2
,

 
 
2
9
0
,

 
 
1
3
,

 
 
4
0
3
,

 
 
1
1
7
0
,

 
 
4
0
,

 
 
1
,

 
 
5
3
8
,

 
 
3
,

 
 
3
1
9
,

 
 
1
2
5
9
,

 
 
3
4
6
,

 
 
8
9
4
,

 
 
1
8
7
,

 
 
1
8
5
,

 
 
1
8
0
,

 
 
2
3
0
,

 
 
1
3
7
,

 
 
3
3
9
,

 
 
6
,

 
 
4
,

 
 
1
2
4
3
,

 
 
2
,

 
 
1
3
6
,

 
 
4
,

 
 
1
2
0
,

 
 
2
5
,

 
 
9
0
3
8
,

 
 
1
,

 
 
6
0
1
,

 
 
3
6
,

 
 
9
,

 
 
1
1
,

 
 
3
9
8
8
,

 
 
3
8
,

 
 
1
,

 
 
1
0
6
,

 
 
2
0
3
,

 
 
1
1
7
,

 
 
7
2
,

 
 
3
7
6
8
,

 
 
1
,

 
 
7
1
7
,

 
 
6
6
3
,

 
 
2
7
7
,

 
 
5
,

 
 
2
2
,

 
 
3
9
5
,

 
 
4
4
,

 
 
1
2
0
,

 
 
1
0
,

 
 
4
,

 
 
3
0
3
,

 
 
2
5
,

 
 
3
6
,

 
 
1
,

 
 
6
0
1
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
7
]
,

 
[
4
,

 
 
6
7
3
,

 
 
5
1
5
,

 
 
3
,

 
 
2
8
6
0
,

 
 
1
9
4
1
4
,

 
 
2
1
0
7
9
,

 
 
1
2
,

 
 
2
3
7
2
,

 
 
7
,

 
 
6
5
8
,

 
 
5
0
5
,

 
 
6
6
,

 
 
1
4
3
6
6
,

 
 
2
7
,

 
 
1
8
3
2
,

 
 
2
1
,

 
 
1
6
0
5
5
4
,

 
 
1
5
,

 
 
2
0
,

 
 
1
8
6
6
,

 
 
9
5
,

 
 
1
2
,

 
 
9
,

 
 
1
1
,

 
 
3
9
7
,

 
 
6
3
0
,

 
 
2
1
,

 
 
6
,

 
 
5
,

 
 
2
2
9
4
,

 
 
1
2
5
,

 
 
1
6
4
,

 
 
9
8
3
,

 
 
3
1
,

 
 
4
,

 
 
3
4
8
,

 
 
1
6
6
0
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
3
5
,

 
 
3
0
,

 
 
3
7
9
,

 
 
3
,

 
 
2
0
,

 
 
2
3
,

 
 
3
4
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
1
7
,

 
 
3
7
,

 
 
4
,

 
 
3
7
7
,

 
 
2
5
,

 
 
1
4
8
3
,

 
 
3
7
,

 
 
2
7
,

 
 
7
9
4
,

 
 
6
6
9
,

 
 
6
0
7
6
7
]
,

 
[
1
2
,

 
 
2
0
,

 
 
1
0
5
,

 
 
6
,

 
 
1
9
,

 
 
2
3
7
,

 
 
5
7
,

 
 
1
0
8
8
,

 
 
3
0
2
,

 
 
3
7
8
5
,

 
 
4
6
,

 
 
3
5
,

 
 
2
2
5
,

 
 
5
,

 
 
2
0
,

 
 
6
8
3
2
,

 
 
2
,

 
 
1
0
7
2
,

 
 
1
2
,

 
 
5
1
1
,

 
 
1
0
5
,

 
 
5
4
,

 
 
8
,

 
 
1
4
5
3
,

 
 
3
1
,

 
 
9
1
,

 
 
6
7
0
,

 
 
6
,

 
 
1
8
,

 
 
6
0
5
,

 
 
1
,

 
 
8
9
9
,

 
 
6
0
4
,

 
 
5
,

 
 
2
7
,

 
 
1
1
3
5
,

 
 
3
4
4
0
,

 
 
1
2
,

 
 
2
8
]
,

 
[
1
3
9
,
 
1
2
,
 
5
0
9
,
 
1
6
0
5
5
5
,
 
4
7
2
,
 
5
,
 
5
0
9
,
 
1
6
0
5
5
6
,
 
2
1
5
2
]
,

 
[
1
1
5
8
,
 
7
3
9
,
 
5
3
,
 
2
9
8
,
 
1
3
,
 
6
6
4
7
]
,

 
[
9
5
,

 
 
1
2
,

 
 
1
,

 
 
7
3
8
,

 
 
7
9
,

 
 
4
3
6
4
,

 
 
1
1
,

 
 
1
8
0
2
,

 
 
3
6
,

 
 
1
6
1
7
,

 
 
7
,

 
 
6
8
5
,

 
 
1
1
,

 
 
4
,

 
 
3
4
8
,

 
 
7
6
0
,

 
 
7
,

 
 
1
3
3
7
,

 
 
9
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
4
,

 
 
2
4
9
,

 
 
9
3
7
,

 
 
1
4
4
2
,

 
 
1
,

 
 
1
5
7
,

 
 
6
9
0
,

 
 
2
,

 
 
1
1
,

 
 
6
5
4
8
,

 
 
9
9
,

 
 
1
0
4
4
,

 
 
5
6
8
1
,

 
 
2
0
8
,

 
 
5
2
,

 
 
2
4
,

 
 
4
,

 
 
5
8
9
0
,

 
 
5
4
7
,

 
 
4
,

 
 
9
4
0
9
,

 
 
5
4
7
,

 
 
1
,

 
 
1
5
1
,

 
 
6
0
4
,

 
 
1
0
,

 
 
5
4
,

 
 
1
,

 
 
3
9
4
5
,

 
 
2
4
,

 
 
4
,

 
 
5
3
3
,

 
 
1
0
3
6
,

 
 
4
7
,

 
 
2
0
3
1
,

 
 
1
0
3
,

 
 
6
3
,

 
 
9
,

 
 
6
5
4
8
,

 
 
1
5
3
,

 
 
9
9
,

 
 
5
6
8
1
,

 
 
1
5
,

 
 
1
5
4
,

 
 
1
7
,

 
 
1
1
,

 
 
3
0
6
2
,

 
 
1
1
7
4
3
,

 
 
1
9
2
,

 
 
2
5
,

 
 
1
6
3
,

 
 
2
,

 
 
1
6
,

 
 
1
8
6
,

 
 
2
1
4
9
,

 
 
9
9
,

 
 
4
,

 
 
5
3
3
,

 
 
1
0
3
6
,

 
 
4
3
2
1
,

 
 
1
0
,

 
 
6
8
,

 
 
9
4
1
0
,

 
 
5
,

 
 
8
0
,

 
 
1
2
0
6
9
,

 
 
5
8
5
,

 
 
1
0
,

 
 
5
2
,

 
 
1
9
1
9
,

 
 
1
1
,

 
 
1
5
,

 
 
5
4
,

 
 
4
3
8
2
,

 
 
1
0
,

 
 
1
2
0
6
9
,

 
 
3
5
5
,

 
 
1
,

 
 
5
6
8
1
,

 
 
4
0
,

 
 
1
4
8
,

 
 
1
7
2
,

 
 
6
3
,

 
 
6
4
,

 
 
2
5
,

 
 
2
2
,

 
 
6
1
7
,

 
 
7
,

 
 
4
9
,

 
 
1
6
7
,

 
 
1
8
1
,

 
 
9
7
,

 
 
4
6
9
,

 
 
1
5
6
,

 
 
6
4
,

 
 
5
,

 
 
6
4
,

 
 
3
5
,

 
 
1
,

 
 
5
6
8
1
,

 
 
1
5
3
,

 
 
1
5
,

 
 
6
5
4
8
,

 
 
5
,

 
 
1
,

 
 
5
3
3
,

 
 
1
0
3
6
,

 
 
5
1
8
,

 
 
7
6
0
,

 
 
7
,

 
 
3
3
2
,

 
 
3
5
2
,

 
 
2
2
,

 
 
7
5
,

 
 
6
8
7
,

 
 
9
,

 
 
1
,

 
 
1
1
2
4
,

 
 
1
9
3
,

 
 
5
1
,

 
 
6
2
4
,

 
 
3
1
7
,

 
 
3
7
,

 
 
4
,

 
 
3
7
7
,

 
 
2
3
8
,

 
 
9
,

 
 
2
3
9
,

 
 
1
4
2
,

 
 
1
7
,

 
 
4
,

 
 
1
0
7
,

 
 
4
1
6
,

 
 
3
7
,

 
 
4
,

 
 
3
7
7
,

 
 
4
5
6
,

 
 
2
7
,

 
 
2
3
,

 
 
7
,

 
 
1
4
2
3
,

 
 
1
3
,

 
 
4
2
,

 
 
2
,

 
 
1
4
2
,

 
 
1
0
,

 
 
1
,

 
 
6
0
2
,

 
 
7
2
,

 
 
4
,

 
 
1
9
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
2
0
1
,

 
 
7
,

 
 
1
5
3
,

 
 
7
0
2
,

 
 
2
7
9
0
,

 
 
1
,

 
 
1
1
0
5
,

 
 
2
,

 
 
6
3
,

 
 
1
1
,

 
 
2
6
,

 
 
7
,

 
 
1
9
,

 
 
2
,

 
 
6
3
,

 
 
1
1
,

 
 
7
,

 
 
1
2
2
,

 
 
2
,

 
 
7
0
,

 
 
3
8
,

 
 
8
1
2
,

 
 
5
,

 
 
5
3
6
,

 
 
1
0
1
,

 
 
1
5
1
,

 
 
7
,

 
 
2
8
2
,

 
 
1
,

 
 
4
8
4
,

 
 
9
,

 
 
5
2
,

 
 
1
0
6
0
,

 
 
7
,

 
 
5
1
3
,

 
 
1
7
3
9
,

 
 
6
8
,

 
 
3
1
9
8
,

 
 
5
,

 
 
1
3
4
6
,

 
 
4
9
9
,

 
 
9
,

 
 
2
3
1
,

 
 
1
9
9
,

 
 
6
3
,

 
 
6
8
,

 
 
3
7
8
9
,

 
 
2
9
1
2
,

 
 
1
2
7
,

 
 
7
,

 
 
2
3
9
,

 
 
3
7
1
2
,

 
 
7
,

 
 
2
4
,

 
 
4
9
,

 
 
1
5
5
5
,

 
 
1
,

 
 
1
1
6
6
,

 
 
1
5
,

 
 
4
4
5
2
,

 
 
7
,

 
 
1
0
6
0
,

 
 
1
1
,

 
 
5
,

 
 
1
4
0
4
4
,

 
 
6
1
7
,

 
 
7
,

 
 
2
3
9
,

 
 
6
5
,

 
 
9
,

 
 
2
4
,

 
 
1
2
5
6
,

 
 
9
9
9
1
,

 
 
2
3
9
,

 
 
4
8
9
,

 
 
2
6
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
1
2
6
,

 
 
7
,

 
 
1
5
3
,

 
 
5
9
,

 
 
6
3
,

 
 
9
,

 
 
8
9
6
,

 
 
4
8
,

 
 
9
1
8
,

 
 
2
,

 
 
1
5
4
,

 
 
7
,

 
 
6
5
,

 
 
4
2
4
2
,

 
 
8
7
9
,

 
 
8
5
1
2
,

 
 
7
6
,

 
 
4
8
,

 
 
5
4
3
1
,

 
 
1
1
7
3
,

 
 
6
,

 
 
7
0
,

 
 
9
8
,

 
 
2
1
,

 
 
1
,

 
 
5
4
6
7
,

 
 
2
6
,

 
 
1
5
3
,

 
 
1
9
,

 
 
1
5
4
,

 
 
1
3
6
0
2
,

 
 
9
9
9
2
,

 
 
3
5
2
,

 
 
8
4
6
,

 
 
4
0
,

 
 
1
,

 
 
1
1
5
,

 
 
7
5
,

 
 
1
8
,

 
 
1
3
6
0
2
,

 
 
5
,

 
 
5
1
,

 
 
1
2
2
,

 
 
6
0
,

 
 
5
8
6
9
,

 
 
6
2
,

 
 
1
0
8
4
,

 
 
1
2
8
3
,

 
 
3
,

 
 
8
5
1
2
,

 
 
4
2
4
9
,

 
 
6
8
,

 
 
3
7
8
8
,

 
 
1
9
1
9
,

 
 
8
6
4
,

 
 
1
0
1
,

 
 
2
2
,

 
 
6
,

 
 
5
8
4
,

 
 
6
8
,

 
 
1
1
4
,

 
 
8
3
5
8
0
,

 
 
3
3
2
3
,

 
 
2
4
,

 
 
9
9
9
1
,

 
 
3
6
,

 
 
5
7
3
,

 
 
2
,

 
 
6
3
,

 
 
9
,

 
 
5
2
,

 
 
9
0
,

 
 
9
,

 
 
2
,

 
 
7
2
5
5
,

 
 
4
0
,

 
 
1
0
,

 
 
1
,

 
 
8
9
3
3
,

 
 
3
5
3
8
1
,

 
 
6
,

 
 
1
8
,

 
 
1
9
6
,

 
 
1
2
,

 
 
1
6
0
5
5
7
,

 
 
5
,

 
 
2
6
7
4
8
,

 
 
7
,

 
 
6
5
0
,

 
 
1
3
9
2
]
,

 
[
2
2
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
3
1
4
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
3
2
0
,

 
 
1
6
0
5
5
8
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
5
0
,

 
 
5
8
4
,

 
 
2
,

 
 
5
1
7
,

 
 
2
0
,

 
 
1
0
9
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
3
2
,

 
 
1
6
7
3
,

 
 
2
5
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
0
4
8
,

 
 
2
0
,

 
 
7
1
2
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
6
6
,

 
 
5
0
,

 
 
3
4
,

 
 
2
0
,

 
 
2
2
1
,

 
 
2
,

 
 
3
6
9
,

 
 
1
9
0
8
,

 
 
1
0
,

 
 
1
,

 
 
7
9
,

 
 
5
1
5
,

 
 
9
9
5
,

 
 
5
6
7
,

 
 
1
8
,

 
 
6
0
,

 
 
6
1
1
,

 
 
2
2
4
,

 
 
2
,

 
 
3
3
1
8
,

 
 
2
0
,

 
 
1
9
9
0
,

 
 
4
8
2
,

 
 
1
2
9
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
4
6
1
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
0
4
,

 
 
5
1
3
,

 
 
1
1
9
9
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
5
9
1
2
,

 
 
1
1
9
0
,

 
 
2
,

 
 
2
8
,

 
 
1
2
7
7
,

 
 
2
0
,

 
 
1
1
0
,

 
 
3
1
5
,

 
 
9
0
7
,

 
 
3
,

 
 
1
6
3
9
,

 
 
2
0
0
8
,

 
 
2
7
1
2
,

 
 
1
2
9
,

 
 
8
3
,

 
 
7
4
,

 
 
2
,

 
 
2
0
9
1
,

 
 
2
7
,

 
 
2
3
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
4
6
1
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
7
6
9
,

 
 
1
6
0
,

 
 
1
9
0
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
4
0
4
,

 
 
1
2
1
,

 
 
1
9
0
,

 
 
4
1
7
,

 
 
5
6
9
,

 
 
1
8
2
0
,

 
 
6
3
6
,

 
 
2
5
4
,

 
 
5
1
2
2
,

 
 
1
2
5
,

 
 
2
,

 
 
2
1
9
,

 
 
4
,

 
 
2
1
4
,

 
 
1
2
1
,

 
 
1
2
4
,

 
 
1
1
5
,

 
 
3
6
2
4
,

 
 
1
2
1
,

 
 
2
9
,

 
 
2
3
,

 
 
2
5
1
2
,

 
 
4
,

 
 
2
5
1
2
,

 
 
2
,

 
 
1
2
1
,

 
 
6
,

 
 
4
7
1
,

 
 
8
3
]
,

 
[
8
0
0
,

 
 
2
0
1
7
,

 
 
1
9
2
0
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
7
4
,

 
 
9
,

 
 
2
8
2
,

 
 
2
,

 
 
1
6
,

 
 
2
6
,

 
 
7
2
,

 
 
4
,

 
 
4
2
3
,

 
 
5
4
9
6
,

 
 
3
,

 
 
1
,

 
 
7
8
8
,

 
 
1
4
6
6
,

 
 
5
,

 
 
1
3
7
,

 
 
4
8
,

 
 
4
4
6
,

 
 
6
5
7
,

 
 
3
0
6
,

 
 
1
1
9
1
,

 
 
5
,

 
 
1
4
,

 
 
4
0
8
,

 
 
9
0
,

 
 
1
1
,

 
 
3
9
2
,

 
 
3
9
6
8
7
,

 
 
9
1
,

 
 
1
,

 
 
1
4
4
8
,

 
 
3
,

 
 
1
6
0
5
5
9
,

 
 
2
2
5
8
,

 
 
2
2
9
,

 
 
1
9
,

 
 
3
6
9
0
,

 
 
1
0
2
,

 
 
2
1
1
4
,

 
 
3
9
,

 
 
6
,

 
 
2
0
2
3
,

 
 
9
1
,

 
 
1
0
6
5
2
6
,

 
 
1
1
5
0
,

 
 
8
,

 
 
1
8
2
0
,

 
 
1
2
8
5
,

 
 
2
,

 
 
1
0
,

 
 
1
,

 
 
1
1
2
3
,

 
 
1
1
9
1
,

 
 
4
9
,

 
 
1
9
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
3
0
,

 
 
8
1
0
,

 
 
5
0
9
2
,

 
 
3
8
,

 
 
1
8
,

 
 
6
,

 
 
9
5
0
,

 
 
3
5
,

 
 
3
9
6
8
7
,

 
 
3
0
,

 
 
1
1
5
0
,

 
 
6
8
,

 
 
7
3
5
,

 
 
4
9
4
2
8
,

 
 
1
7
5
,

 
 
1
1
5
0
,

 
 
3
9
6
8
7
,

 
 
7
,

 
 
1
0
3
5
,

 
 
1
5
4
,

 
 
7
3
,

 
 
1
7
5
,

 
 
1
1
5
0
,

 
 
7
,

 
 
2
4
,

 
 
3
6
,

 
 
1
7
5
0
,

 
 
6
,

 
 
1
0
3
,

 
 
1
9
9
,

 
 
3
7
0
8
,

 
 
3
7
,

 
 
1
4
,

 
 
2
,

 
 
3
9
2
,

 
 
1
,

 
 
3
5
4
8
,

 
 
5
2
6
,

 
 
9
,

 
 
3
9
6
8
7
,

 
 
5
,

 
 
4
9
4
2
8
,

 
 
2
5
8
,

 
 
4
3
3
,

 
 
6
1
,

 
 
8
0
,

 
 
1
,

 
 
1
6
0
5
6
0
,

 
 
3
3
,

 
 
1
,

 
 
3
3
3
7
,

 
 
5
3
7
3
,

 
 
4
2
1
0
,

 
 
4
9
4
2
8
,

 
 
2
8
5
,

 
 
1
1
,

 
 
3
8
0
,

 
 
9
,

 
 
6
,

 
 
5
,

 
 
3
9
6
8
7
,

 
 
8
6
,

 
 
6
2
0
1
,

 
 
5
,

 
 
6
,

 
 
2
8
2
,

 
 
7
2
5
6
,

 
 
5
,

 
 
9
9
,

 
 
6
8
,

 
 
4
7
7
,

 
 
1
2
5
0
]
,

 
[
7
1
7
,

 
 
1
6
0
5
6
1
,

 
 
1
6
0
5
6
2
,

 
 
8
5
2
,

 
 
1
,

 
 
6
2
8
,

 
 
3
,

 
 
6
4
4
8
,

 
 
8
8
2
7
,

 
 
1
6
0
,

 
 
2
8
3
,

 
 
3
7
6
,

 
 
7
3
9
,

 
 
2
5
9
3
0
,

 
 
8
4
6
7
,

 
 
8
0
7
4
,

 
 
2
9
6
8
8
,

 
 
1
6
0
5
6
3
]
,

 
[
1
5
6
9
,

 
 
5
0
,

 
 
2
4
6
,

 
 
1
,

 
 
1
6
1
,

 
 
3
,

 
 
6
9
1
1
,

 
 
1
0
,

 
 
1
0
2
2
8
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
6
9
1
1
,

 
 
1
0
,

 
 
1
0
2
2
8
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
2
8
6
4
3
,

 
 
2
1
,

 
 
1
,

 
 
7
0
0
,

 
 
5
9
,

 
 
7
9
,

 
 
1
3
,

 
 
1
6
1
,

 
 
8
3
5
8
1
,

 
 
2
1
9
9
,

 
 
6
0
7
6
8
,

 
 
5
,

 
 
2
1
5
8
,

 
 
1
8
,

 
 
1
4
,

 
 
1
0
,

 
 
1
0
2
2
8
,

 
 
5
0
,

 
 
5
9
,

 
 
1
6
,

 
 
2
9
1
3
,

 
 
8
0
,

 
 
7
,

 
 
4
8
3
0
,

 
 
1
3
,

 
 
6
6
,

 
 
4
,

 
 
1
0
2
2
8
,

 
 
6
3
8
5
,

 
 
4
5
9
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
7
6
,

 
 
9
,

 
 
1
,

 
 
4
8
0
,

 
 
8
,

 
 
1
0
,

 
 
1
0
2
2
8
,

 
 
1
,

 
 
4
5
9
,

 
 
1
2
1
8
2
,

 
 
3
1
3
,

 
 
1
0
,

 
 
6
0
,

 
 
2
0
2
,

 
 
4
,

 
 
6
0
3
,

 
 
2
6
5
1
,

 
 
5
0
3
3
,

 
 
5
0
4
,

 
 
9
5
]
,

 
[
3
8
8
,

 
 
6
,

 
 
1
3
6
,

 
 
1
,

 
 
1
1
0
,

 
 
2
,

 
 
2
0
4
,

 
 
1
,

 
 
1
0
3
9
,

 
 
2
8
6
8
,

 
 
9
,

 
 
8
6
,

 
 
1
0
,

 
 
1
,

 
 
2
9
,

 
 
1
5
7
,

 
 
7
,

 
 
8
1
,

 
 
2
5
9
3
1
,

 
 
6
4
]
,

 
[
5
3
,

 
 
5
6
1
4
,

 
 
3
,

 
 
1
6
0
5
6
4
,

 
 
8
7
8
2
,

 
 
2
1
5
8
1
,

 
 
2
3
1
6
6
,

 
 
3
3
8
0
,

 
 
1
0
6
5
2
7
,

 
 
1
8
,

 
 
7
8
8
9
,

 
 
4
5
5
2
7
,

 
 
5
,

 
 
1
4
,

 
 
6
9
8
0
7
]
,

 
[
1
0
3
,

 
 
6
,

 
 
1
8
4
3
,

 
 
3
4
,

 
 
6
,

 
 
1
0
8
,

 
 
3
7
,

 
 
2
,

 
 
4
2
6
,

 
 
2
7
,

 
 
1
1
4
4
,

 
 
7
,

 
 
5
9
,

 
 
6
3
,

 
 
9
,

 
 
4
7
,

 
 
2
4
,

 
 
4
4
0
,

 
 
1
0
,

 
 
1
,

 
 
2
9
,

 
 
1
7
9
,

 
 
3
,

 
 
4
6
,

 
 
4
5
5
2
8
,

 
 
1
6
0
3
]
,

 
[
5
3
7
6
,
 
8
,
 
5
1
0
,
 
3
,
 
8
7
1
,
 
2
2
7
]
,

 
[
6
,

 
 
2
0
9
5
,

 
 
3
7
,

 
 
2
,

 
 
1
1
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
1
1
7
,

 
 
9
8
,

 
 
1
4
2
,

 
 
1
2
,

 
 
5
6
1
5
,

 
 
3
7
,

 
 
2
,

 
 
1
,

 
 
3
9
8
,

 
 
1
5
,

 
 
1
,

 
 
1
2
9
5
3
,

 
 
4
7
2
6
,

 
 
2
3
,

 
 
7
,

 
 
3
6
9
,

 
 
8
2
7
,

 
 
1
1
,

 
 
8
0
,

 
 
7
,

 
 
7
0
,

 
 
1
5
8
,

 
 
3
3
1
,

 
 
8
,

 
 
1
5
,

 
 
1
,

 
 
4
9
0
1
,

 
 
1
2
,

 
 
2
3
7
9
,

 
 
4
8
2
,

 
 
6
6
7
9
,

 
 
6
6
9
,

 
 
1
0
0
3
]
,

 
[
6
,

 
 
1
8
7
,

 
 
1
,

 
 
1
6
9
,

 
 
2
,

 
 
1
,

 
 
1
3
9
,

 
 
2
9
5
,

 
 
1
3
3
,

 
 
1
0
,

 
 
1
,

 
 
1
7
2
7
,

 
 
1
2
3
8
,

 
 
5
4
,

 
 
1
1
7
,

 
 
9
,

 
 
4
,

 
 
3
7
1
3
,

 
 
8
2
,

 
 
3
,

 
 
1
,

 
 
2
7
6
7
8
,

 
 
9
7
4
5
,

 
 
8
,

 
 
7
8
,

 
 
1
0
3
5
9
,

 
 
1
6
6
6
,

 
 
1
9
,

 
 
5
7
3
3
,

 
 
2
8
6
4
4
,

 
 
3
1
,

 
 
1
,

 
 
1
1
6
,

 
 
1
5
,

 
 
8
3
5
8
2
,

 
 
1
1
8
1
,

 
 
4
3
,

 
 
8
6
5
,

 
 
3
1
,

 
 
1
,

 
 
4
4
2
,

 
 
3
,

 
 
2
1
5
8
,

 
 
1
3
5
7
,

 
 
1
2
,

 
 
6
,

 
 
1
,

 
 
1
7
0
7
,

 
 
5
,

 
 
5
5
0
,

 
 
1
0
3
5
9
,

 
 
1
8
7
9
,

 
 
1
0
,

 
 
2
1
5
8
,

 
 
1
9
,

 
 
1
5
6
7
6
,

 
 
2
0
6
5
,

 
 
1
6
0
5
6
5
,

 
 
5
1
7
8
,

 
 
3
,

 
 
6
4
8
,

 
 
2
,

 
 
4
2
7
5
,

 
 
3
,

 
 
9
2
,

 
 
1
7
4
5
5
,

 
 
3
9
9
9
,

 
 
1
4
8
7
,

 
 
3
,

 
 
3
8
,

 
 
1
,

 
 
5
6
8
,

 
 
5
7
5
,

 
 
8
,

 
 
5
,

 
 
7
,

 
 
2
0
1
1
,

 
 
6
4
,

 
 
2
6
,

 
 
4
3
,

 
 
1
4
,

 
 
3
4
,

 
 
3
6
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
1
,

 
 
2
5
9
3
2
,

 
 
5
7
5
,

 
 
2
4
,

 
 
4
,

 
 
1
4
2
2
,

 
 
1
0
,

 
 
5
2
7
,

 
 
1
2
,

 
 
1
0
3
5
9
,

 
 
1
5
6
9
,

 
 
2
,

 
 
1
4
,

 
 
7
5
4
,

 
 
4
8
,

 
 
4
,

 
 
7
9
6
,

 
 
3
0
7
6
,

 
 
1
0
3
5
9
,

 
 
1
5
4
9
,

 
 
1
8
,

 
 
7
1
4
3
,

 
 
1
8
2
,

 
 
8
3
5
8
3
,

 
 
9
,

 
 
1
6
6
,

 
 
5
6
,

 
 
1
6
,

 
 
1
0
,

 
 
1
,

 
 
2
3
]
,

 
[
9
5
,

 
 
1
2
,

 
 
9
,

 
 
2
3
1
,

 
 
1
5
9
,

 
 
4
,

 
 
2
5
0
6
,

 
 
5
4
4
7
,

 
 
5
,

 
 
1
9
,

 
 
4
,

 
 
1
1
8
,

 
 
3
3
,

 
 
2
7
,

 
 
2
0
3
5
,

 
 
2
3
2
1
,

 
 
7
,

 
 
2
5
4
6
,

 
 
1
,

 
 
1
2
0
,

 
 
3
,

 
 
1
,

 
 
1
3
1
9
,

 
 
1
6
5
9
,

 
 
1
4
8
,

 
 
1
,

 
 
6
8
2
,

 
 
5
,

 
 
2
4
6
0
,

 
 
9
,

 
 
1
,

 
 
7
3
5
6
,

 
 
8
,

 
 
3
3
2
4
,

 
 
1
0
,

 
 
1
,

 
 
2
8
5
5
,

 
 
1
3
7
,

 
 
4
1
1
1
,

 
 
1
,

 
 
1
0
4
2
3
,

 
 
1
1
6
,

 
 
5
,

 
 
4
5
,

 
 
2
0
0
1
,

 
 
1
,

 
 
8
6
3
,

 
 
3
2
,

 
 
2
7
3
,

 
 
2
,

 
 
1
,

 
 
5
2
0
6
,

 
 
1
7
9
,

 
 
8
3
,

 
 
1
5
,

 
 
1
2
4
9
,

 
 
9
2
5
7
,

 
 
5
,

 
 
1
3
0
6
,

 
 
9
2
5
7
,

 
 
1
4
1
6
,

 
 
2
3
1
,

 
 
5
0
0
9
,

 
 
2
,

 
 
4
,

 
 
2
6
2
1
,

 
 
1
7
7
,

 
 
3
1
7
9
,

 
 
9
4
4
,

 
 
1
,

 
 
3
7
6
7
,

 
 
3
,

 
 
1
,

 
 
8
0
8
,

 
 
1
1
9
2
,

 
 
8
4
,

 
 
4
6
0
,

 
 
2
4
1
8
,

 
 
2
,

 
 
4
5
5
2
9
,

 
 
1
,

 
 
2
9
5
,

 
 
2
8
8
,

 
 
1
1
6
,

 
 
3
2
,

 
 
1
1
6
]
,

 
[
7
4
7
,

 
 
2
3
,

 
 
3
,

 
 
1
,

 
 
3
0
3
,

 
 
1
1
7
8
,

 
 
1
7
0
5
,

 
 
7
4
7
,

 
 
2
8
,

 
 
8
,

 
 
2
9
5
1
,

 
 
2
,

 
 
6
9
3
,

 
 
1
,

 
 
2
3
,

 
 
3
,

 
 
1
,

 
 
3
0
3
,

 
 
1
7
6
,

 
 
5
4
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
2
8
,

 
 
1
6
0
5
6
6
,

 
 
1
2
6
,

 
 
4
9
4
2
9
,

 
 
1
2
6
,

 
 
2
8
3
7
,

 
 
9
9
6
,

 
 
4
,

 
 
2
1
0
8
0
,

 
 
1
7
6
,

 
 
5
4
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
6
0
5
6
7
,

 
 
9
5
7
2
,

 
 
1
6
0
5
6
8
,

 
 
1
0
,

 
 
4
3
3
6
,

 
 
2
3
5
7
,

 
 
1
0
6
5
2
8
,

 
 
6
,

 
 
1
8
4
,

 
 
7
5
8
,

 
 
2
0
,

 
 
7
4
7
,

 
 
5
9
1
,

 
 
1
1
,

 
 
3
9
5
,

 
 
4
,

 
 
3
4
8
,

 
 
2
,

 
 
5
9
5
,

 
 
1
2
3
9
,

 
 
2
1
5
8
2
]
,

 
[
7
,

 
 
2
6
3
,

 
 
4
8
,

 
 
7
,

 
 
6
9
8
0
8
,

 
 
1
9
,

 
 
7
1
6
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
1
4
0
4
5
,

 
 
2
,

 
 
4
3
2
,

 
 
2
3
,

 
 
2
6
,

 
 
3
6
0
4
,

 
 
3
9
3
,

 
 
6
9
,

 
 
7
,

 
 
1
1
3
1
,

 
 
1
6
0
5
6
9
,

 
 
1
,

 
 
1
6
0
5
7
0
,

 
 
1
8
7
2
5
,

 
 
3
2
,

 
 
2
1
0
,

 
 
1
9
5
9
,

 
 
3
0
,

 
 
7
7
,

 
 
5
6
2
,

 
 
6
4
,

 
 
8
,

 
 
8
8
5
,

 
 
1
4
5
9
,

 
 
3
1
5
9
,

 
 
7
8
,

 
 
5
9
,

 
 
6
,

 
 
2
0
3
,

 
 
1
0
9
6
8
,

 
 
1
,

 
 
9
4
0
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
6
0
5
7
1
,

 
 
2
0
,

 
 
2
2
8
4
,

 
 
2
2
6
4
,

 
 
1
6
6
3
9
,

 
 
2
1
9
8
,

 
 
1
6
0
5
7
2
,

 
 
1
5
0
9
3
,

 
 
1
9
,

 
 
5
7
,

 
 
1
7
1
7
,

 
 
2
,

 
 
2
9
4
1
,

 
 
1
1
8
4
7
,

 
 
5
,

 
 
7
1
6
9
,

 
 
1
3
,

 
 
1
3
8
5
,

 
 
5
2
,

 
 
1
4
7
1
3
,

 
 
1
0
,

 
 
1
0
8
0
0
,

 
 
5
,

 
 
7
0
1
6
,

 
 
1
6
0
8
,

 
 
2
1
0
8
1
,

 
 
4
5
,

 
 
3
7
3
,

 
 
6
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
2
5
0
,

 
 
8
6
8
3
,

 
 
2
9
7
,

 
 
2
5
,

 
 
1
7
3
6
,

 
 
1
0
,

 
 
4
9
4
3
0
,

 
 
1
5
0
,

 
 
1
7
1
3
,

 
 
4
0
2
,

 
 
5
3
,

 
 
3
9
,

 
 
5
0
6
,

 
 
4
9
,

 
 
1
0
7
2
,

 
 
1
,

 
 
2
0
3
5
,

 
 
6
0
0
,

 
 
2
,

 
 
1
5
6
,

 
 
4
8
,

 
 
6
0
,

 
 
2
1
0
8
2
,

 
 
1
3
3
2
9
,

 
 
5
8
6
,

 
 
3
4
1
]
,

 
[
7
,

 
 
2
9
1
,

 
 
4
7
,

 
 
7
0
8
,

 
 
3
,

 
 
4
9
7
3
,

 
 
1
,

 
 
5
8
6
,

 
 
3
4
1
,

 
 
1
2
,

 
 
1
6
0
5
7
3
,

 
 
4
0
6
,

 
 
2
8
5
,

 
 
1
0
2
2
9
,

 
 
2
6
,

 
 
7
,

 
 
1
9
,

 
 
2
7
,

 
 
2
3
,

 
 
3
1
,

 
 
8
8
,

 
 
1
0
,

 
 
4
,

 
 
1
5
7
4
,

 
 
1
2
0
,

 
 
7
2
,

 
 
1
6
5
,

 
 
2
,

 
 
2
5
6
,

 
 
1
,

 
 
4
9
0
2
,

 
 
4
6
5
,

 
 
8
9
,

 
 
1
0
,

 
 
1
3
0
7
8
,

 
 
1
1
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
2
8
4
,

 
 
2
2
,

 
 
1
3
,

 
 
1
1
1
0
,

 
 
1
7
4
,

 
 
2
6
7
,

 
 
1
0
3
,

 
 
1
9
,

 
 
5
7
,

 
 
2
3
2
6
,

 
 
2
1
,

 
 
2
9
5
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
]
,

 
[
7
,

 
 
1
9
,

 
 
7
3
6
,

 
 
1
9
1
5
,

 
 
3
,

 
 
2
7
3
,

 
 
2
4
5
2
,

 
 
3
5
1
,

 
 
6
,

 
 
1
9
,

 
 
7
3
6
,

 
 
9
2
5
,

 
 
4
0
,

 
 
4
0
2
5
,

 
 
1
0
,

 
 
1
1
8
4
8
,

 
 
1
1
6
,

 
 
1
9
,

 
 
7
9
0
,

 
 
3
1
,

 
 
1
0
6
,

 
 
9
,

 
 
1
8
,

 
 
1
2
1
5
,

 
 
3
5
1
,

 
 
6
,

 
 
1
9
,

 
 
7
3
6
,

 
 
9
2
5
,

 
 
6
,

 
 
1
8
,

 
 
1
,

 
 
4
7
,

 
 
2
1
,

 
 
1
,

 
 
1
4
1
7
4
,

 
 
8
3
5
8
4
,

 
 
6
,

 
 
1
5
3
,

 
 
1
9
,

 
 
1
4
,

 
 
7
3
6
,

 
 
5
5
,

 
 
1
2
1
5
,

 
 
1
0
6
,

 
 
2
,

 
 
3
1
4
,

 
 
9
,

 
 
1
2
0
7
0
,

 
 
5
,

 
 
1
1
8
4
8
,

 
 
1
8
,

 
 
2
7
1
,

 
 
1
6
1
3
8
,

 
 
9
,

 
 
6
5
1
,

 
 
7
3
,

 
 
3
0
8
1
4
,

 
 
1
8
,

 
 
4
6
7
,

 
 
1
7
,

 
 
4
9
4
3
1
,

 
 
4
,

 
 
7
5
0
,

 
 
6
1
5
,

 
 
6
3
8
,

 
 
1
5
,

 
 
1
2
0
7
0
,

 
 
1
1
8
4
8
,

 
 
4
5
,

 
 
4
9
8
,

 
 
6
,

 
 
2
1
,

 
 
4
9
9
3
,

 
 
2
2
4
,

 
 
3
5
3
8
2
]
,

 
[
2
1
3
,
 
8
9
7
8
,
 
3
3
4
,
 
1
8
8
,
 
6
1
3
]
,

 
[
7
,
 
6
3
,
 
9
,
 
1
1
,
 
4
2
,
 
4
,
 
3
7
2
,
 
3
,
 
7
8
1
,
 
1
5
,
 
7
9
3
3
]
,

 
[
4
5
5
,

 
 
7
8
,

 
 
6
,

 
 
1
8
,

 
 
4
9
0
3
,

 
 
1
0
8
8
7
,

 
 
5
,

 
 
2
6
8
,

 
 
2
,

 
 
1
8
8
6
,

 
 
6
7
9
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
7
5
,

 
 
6
,

 
 
1
4
,

 
 
9
6
,

 
 
7
0
,

 
 
6
2
,

 
 
1
8
5
0
,

 
 
1
,

 
 
1
3
9
0
,

 
 
5
,

 
 
6
2
,

 
 
1
0
6
0
,

 
 
6
,

 
 
1
8
,

 
 
1
,

 
 
2
2
0
9
8
,

 
 
2
2
2
,

 
 
1
5
,

 
 
1
,

 
 
1
1
8
7
,

 
 
2
3
4
3
,

 
 
1
6
7
2
,

 
 
1
5
4
4
,

 
 
3
2
8
,

 
 
1
0
6
,

 
 
1
5
0
,

 
 
4
9
0
3
,

 
 
5
2
3
9
]
,

 
[
7
,

 
 
5
6
,

 
 
1
5
2
,

 
 
6
4
,

 
 
1
2
,

 
 
5
5
,

 
 
4
1
8
,

 
 
1
3
8
0
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
1
8
8
,

 
 
1
2
,

 
 
7
0
4
,

 
 
8
6
7
,

 
 
3
2
,

 
 
1
0
7
,

 
 
1
4
7
1
4
,

 
 
3
,

 
 
1
9
0
5
4
,

 
 
1
3
2
4
,

 
 
6
3
3
,

 
 
3
6
,

 
 
4
1
,

 
 
8
,

 
 
5
8
,

 
 
4
5
0
,

 
 
2
2
,

 
 
1
2
8
0
,

 
 
5
1
1
,

 
 
5
,

 
 
7
,

 
 
5
6
,

 
 
1
9
,

 
 
2
2
7
3
,

 
 
3
0
,

 
 
4
8
7
3
,

 
 
8
4
,

 
 
2
2
1
0
0
,

 
 
4
6
]
,

 
[
2
3
6
,

 
 
3
,

 
 
7
1
2
,

 
 
1
9
4
1
5
,

 
 
3
3
6
,

 
 
3
3
6
,

 
 
1
5
3
,

 
 
1
0
,

 
 
2
4
5
8
,

 
 
1
0
5
8
2
,

 
 
7
6
3
,

 
 
2
3
4
7
,

 
 
8
3
5
8
5
,

 
 
1
7
8
,

 
 
7
,

 
 
1
9
,

 
 
1
3
3
3
,

 
 
1
2
,

 
 
2
3
6
,

 
 
3
,

 
 
7
1
2
,

 
 
2
0
9
,

 
 
1
9
4
1
5
,

 
 
3
1
,

 
 
1
0
5
8
2
,

 
 
7
6
3
,

 
 
2
3
4
7
,

 
 
8
3
5
8
5
,

 
 
7
1
,

 
 
6
5
7
,

 
 
6
2
2
,

 
 
4
9
6
,

 
 
3
1
,

 
 
1
,

 
 
4
3
5
,

 
 
3
,

 
 
3
3
6
,

 
 
2
6
,

 
 
1
5
3
,

 
 
1
1
,

 
 
6
9
7
,

 
 
1
0
,

 
 
2
4
5
8
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
7
0
,

 
 
7
4
,

 
 
1
2
8
,

 
 
8
5
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
1
0
9
,

 
 
2
,

 
 
7
9
6
,

 
 
1
,

 
 
3
3
6
,

 
 
5
,

 
 
7
4
,

 
 
2
5
0
,

 
 
4
3
,

 
 
1
1
,

 
 
1
5
9
,

 
 
2
,

 
 
7
9
6
,

 
 
5
0
,

 
 
7
4
5
,

 
 
1
7
,

 
 
7
3
0
,

 
 
1
7
,

 
 
4
4
1
,

 
 
1
3
4
,

 
 
6
,

 
 
1
6
9
,

 
 
1
0
5
8
2
,

 
 
7
6
3
,

 
 
2
3
4
7
,

 
 
8
3
5
8
5
]
,

 
[
5
3
5
,
 
2
1
6
,
 
6
9
9
,
 
3
0
4
1
,
 
8
7
8
,
 
1
1
1
2
]
,

 
[
6
9
,
 
6
8
4
,
 
8
,
 
4
1
3
,
 
1
4
7
,
 
3
3
,
 
1
7
7
5
5
,
 
5
7
7
0
,
 
1
9
8
]
,

 
[
2
9
6
,

 
 
1
6
0
5
7
4
,

 
 
1
8
,

 
 
1
3
3
,

 
 
1
0
,

 
 
6
0
,

 
 
1
8
3
7
3
,

 
 
1
7
,

 
 
1
0
1
,

 
 
5
0
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
1
6
,

 
 
1
4
7
1
,

 
 
5
,

 
 
1
2
1
,

 
 
7
5
8
,

 
 
1
,

 
 
2
3
]
,

 
[
4
0
4
,
 
1
5
3
3
,
 
3
5
3
,
 
8
,
 
1
3
3
,
 
3
2
,
 
4
,
 
7
4
7
,
 
3
7
5
4
,
 
3
2
,
 
1
,
 
1
1
0
,
 
7
,
 
2
8
2
,
 
1
1
,
 
3
1
,
 
4
1
]
,

 
[
2
4
6
,

 
 
1
,

 
 
2
9
9
,

 
 
3
3
8
,

 
 
3
3
,

 
 
6
1
7
8
,

 
 
5
0
0
,

 
 
6
,

 
 
3
9
,

 
 
1
9
,

 
 
1
3
8
4
,

 
 
1
6
6
1
,

 
 
4
8
,

 
 
6
1
7
8
,

 
 
5
,

 
 
7
8
8
,

 
 
9
3
6
,

 
 
9
,

 
 
4
3
9
,

 
 
2
,

 
 
1
3
,

 
 
2
3
]
,

 
[
5
,

 
 
6
,

 
 
1
8
,

 
 
2
7
8
,

 
 
3
7
,

 
 
7
0
,

 
 
8
0
,

 
 
5
0
5
,

 
 
8
3
5
8
6
,

 
 
7
6
,

 
 
3
,

 
 
9
2
,

 
 
2
2
1
0
1
,

 
 
8
4
9
,

 
 
5
2
2
,

 
 
1
7
7
5
6
,

 
 
8
,

 
 
9
3
1
]
,

 
[
1
,

 
 
2
4
9
,

 
 
8
,

 
 
9
,

 
 
7
5
,

 
 
2
4
6
,

 
 
2
6
8
,

 
 
2
,

 
 
2
9
7
,

 
 
9
,

 
 
1
6
0
5
7
5
,

 
 
5
7
0
,

 
 
1
8
,

 
 
1
3
,

 
 
5
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
2
3
0
,

 
 
9
,

 
 
2
8
6
,

 
 
2
7
5
8
,

 
 
8
9
3
4
,

 
 
4
3
1
,

 
 
1
6
,

 
 
7
9
5
,

 
 
2
,

 
 
2
9
7
,

 
 
6
8
4
,

 
 
8
,

 
 
4
,

 
 
1
4
2
2
,

 
 
5
,

 
 
2
5
,

 
 
4
9
,

 
 
1
6
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
3
9
6
8
8
,

 
 
2
9
,

 
 
1
8
1
,

 
 
1
0
7
2
,

 
 
6
,

 
 
2
9
7
,

 
 
1
4
0
2
,

 
 
2
5
,

 
 
1
5
2
,

 
 
2
5
,

 
 
6
,

 
 
3
9
,

 
 
1
6
1
,

 
 
2
1
8
,

 
 
1
7
,

 
 
2
3
1
6
7
,

 
 
3
,

 
 
1
,

 
 
4
7
5
,

 
 
5
,

 
 
2
1
8
,

 
 
4
8
,

 
 
9
,

 
 
2
6
,

 
 
1
1
,

 
 
6
,

 
 
2
8
9
,

 
 
2
,

 
 
1
1
7
,

 
 
9
4
1
1
,

 
 
1
0
0
,

 
 
1
3
,

 
 
2
5
,

 
 
9
4
1
1
,

 
 
1
0
0
,

 
 
9
,

 
 
8
4
,

 
 
6
,

 
 
1
2
2
,

 
 
2
,

 
 
1
6
,

 
 
1
8
6
,

 
 
9
4
1
1
,

 
 
2
0
3
,

 
 
2
8
6
,

 
 
9
,

 
 
9
6
,

 
 
1
,

 
 
2
3
1
6
7
,

 
 
3
,

 
 
1
,

 
 
4
7
5
,

 
 
1
2
2
,

 
 
1
0
6
,

 
 
4
9
,

 
 
6
9
,

 
 
2
7
,

 
 
2
9
2
,

 
 
1
8
4
,

 
 
1
0
6
5
2
9
,

 
 
1
,

 
 
4
7
5
,

 
 
1
8
1
,

 
 
2
7
6
,

 
 
2
5
9
,

 
 
1
0
,

 
 
1
7
3
0
,

 
 
4
2
,

 
 
3
9
,

 
 
6
,

 
 
1
3
6
,

 
 
4
,

 
 
1
2
0
,

 
 
1
2
,

 
 
1
2
7
9
,

 
 
1
2
5
,

 
 
4
,

 
 
2
7
5
8
,

 
 
3
8
5
6
,

 
 
2
4
,

 
 
1
8
7
,

 
 
3
1
,

 
 
1
,

 
 
1
4
5
4
,

 
 
4
9
,

 
 
1
2
,

 
 
9
1
,

 
 
4
,

 
 
4
6
2
6
,

 
 
2
7
5
8
,

 
 
3
8
5
6
,

 
 
8
4
,

 
 
1
3
4
1
,

 
 
1
1
,

 
 
5
6
5
,

 
 
6
,

 
 
1
9
,

 
 
1
1
,

 
 
2
5
,

 
 
2
7
,

 
 
7
4
3
,

 
 
2
3
0
,

 
 
3
1
,

 
 
1
8
7
2
6
,

 
 
9
,

 
 
2
8
6
,

 
 
6
,

 
 
2
2
9
,

 
 
1
6
,

 
 
2
7
,

 
 
4
6
2
6
,

 
 
2
7
5
8
,

 
 
3
8
5
6
,

 
 
8
7
5
,

 
 
8
4
,

 
 
3
8
,

 
 
8
,

 
 
9
1
,

 
 
1
7
3
,

 
 
8
,

 
 
2
5
]
,

 
[
8
3
9
,

 
 
1
6
2
,

 
 
3
7
7
,

 
 
3
2
0
,

 
 
5
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
8
7
,

 
 
5
4
8
,

 
 
2
,

 
 
3
4
,

 
 
7
,

 
 
2
4
3
8
,

 
 
6
,

 
 
2
,

 
 
6
6
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
5
6
2
,

 
 
1
0
,

 
 
2
8
]
,

 
[
7
2
,
 
2
3
8
2
3
,
 
1
5
,
 
2
9
8
,
 
8
2
4
,
 
3
3
,
 
1
,
 
1
1
6
4
,
 
2
3
1
0
,
 
1
,
 
3
1
7
1
]
,

 
[
1
8
3
,

 
 
2
1
4
,

 
 
1
0
0
,

 
 
1
3
,

 
 
1
9
0
,

 
 
1
0
5
,

 
 
1
7
1
6
0
,

 
 
3
2
6
3
,

 
 
7
7
,

 
 
2
7
1
7
,

 
 
4
,

 
 
3
4
6
1
,

 
 
5
4
0
,

 
 
8
,

 
 
6
3
7
,

 
 
2
5
,

 
 
1
2
,

 
 
4
6
2
,

 
 
1
0
2
9
0
,

 
 
1
4
0
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
3
7
6
,

 
 
4
,

 
 
3
4
6
1
,

 
 
3
1
5
,

 
 
2
2
,

 
 
9
6
,

 
 
1
0
0
9
9
,

 
 
5
,

 
 
3
2
8
5
,

 
 
1
,

 
 
3
4
6
1
,

 
 
1
0
,

 
 
2
2
1
0
2
,

 
 
3
9
7
,

 
 
1
1
,

 
 
1
8
7
2
7
,

 
 
8
4
,

 
 
7
,

 
 
8
0
7
,

 
 
9
6
,

 
 
1
6
,

 
 
4
4
1
8
,

 
 
2
1
,

 
 
2
2
1
0
2
,

 
 
3
3
,

 
 
4
0
]
,

 
[
2
3
,

 
 
3
5
,

 
 
2
2
8
9
,

 
 
2
6
7
4
9
,

 
 
1
7
8
,

 
 
1
3
7
,

 
 
4
9
,

 
 
6
9
2
,

 
 
1
7
5
,

 
 
2
3
,

 
 
3
5
,

 
 
2
2
8
9
,

 
 
2
6
7
4
9
,

 
 
5
,

 
 
4
5
5
3
0
,

 
 
1
2
8
4
0
,

 
 
2
,

 
 
2
2
8
9
,

 
 
2
6
7
4
9
,

 
 
5
,

 
 
5
1
3
,

 
 
2
7
8
7
,

 
 
1
1
,

 
 
7
3
,

 
 
2
,

 
 
4
3
5
,

 
 
4
3
,

 
 
6
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
1
,

 
 
5
,

 
 
5
0
,

 
 
8
8
2
,

 
 
5
5
,

 
 
2
0
6
5
9
,

 
 
6
,

 
 
3
2
5
1
,

 
 
9
5
,

 
 
3
9
6
8
9
]
,

 
[
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
1
5
6
0
,

 
 
3
1
5
,

 
 
4
3
0
,

 
 
4
6
,

 
 
1
2
4
,

 
 
2
3
2
7
,

 
 
3
7
,

 
 
5
,

 
 
4
3
0
,

 
 
2
8
7
,

 
 
3
,

 
 
7
9
,

 
 
1
5
7
8
,

 
 
5
0
,

 
 
1
1
8
,

 
 
1
5
,

 
 
5
,

 
 
9
8
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
5
,

 
 
3
3
1
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
,

 
 
1
1
4
,

 
 
4
7
,

 
 
2
,

 
 
1
6
,

 
 
1
8
8
,

 
 
2
6
6
2
,

 
 
6
,

 
 
4
3
1
,

 
 
9
8
4
,

 
 
2
0
,

 
 
4
1
3
,

 
 
5
,

 
 
8
0
,

 
 
6
0
2
4
,

 
 
1
6
5
,

 
 
3
1
5
,

 
 
2
9
0
,

 
 
1
4
7
2
,

 
 
8
,

 
 
4
,

 
 
9
8
,

 
 
1
1
0
,

 
 
7
6
,

 
 
2
1
3
7
]
,

 
[
2
9
6
,

 
 
7
,

 
 
1
3
7
5
,

 
 
1
,

 
 
3
9
6
7
,

 
 
2
6
5
,

 
 
1
4
2
4
,

 
 
1
5
,

 
 
9
5
1
,

 
 
1
9
2
0
,

 
 
6
1
6
,

 
 
2
1
,

 
 
7
1
2
,

 
 
3
0
,

 
 
2
6
5
,

 
 
1
4
2
4
,

 
 
4
5
9
,

 
 
5
,

 
 
4
5
8
1
,

 
 
1
6
0
5
7
6
,

 
 
1
1
,

 
 
2
4
,

 
 
1
9
2
0
,

 
 
6
1
6
]
,

 
[
7
,

 
 
8
1
,

 
 
5
3
4
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
3
6
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
2
2
3
6
,

 
 
2
,

 
 
1
5
2
,

 
 
9
,

 
 
2
7
7
,

 
 
1
9
7
,

 
 
7
,

 
 
9
0
,

 
 
1
5
9
,

 
 
9
,

 
 
4
8
6
]
,

 
[
1
3
,
 
1
0
7
,
 
8
,
 
1
1
1
,
 
4
,
 
3
1
1
6
,
 
6
4
3
0
,
 
4
4
4
,
 
6
7
,
 
6
,
 
4
4
4
]
,

 
[
7
1
,
 
2
7
,
 
1
2
5
9
,
 
9
1
9
9
,
 
3
2
7
,
 
5
,
 
6
0
7
,
 
2
8
4
1
,
 
1
1
3
,
 
6
2
1
,
 
5
,
 
2
5
,
 
1
1
3
,
 
6
8
1
]
,

 
[
1
2
3
,

 
 
1
0
6
5
3
0
,

 
 
4
7
2
,

 
 
7
,

 
 
1
9
,

 
 
9
1
7
,

 
 
1
2
3
,

 
 
1
0
6
5
3
0
,

 
 
4
7
2
,

 
 
1
7
,

 
 
6
9
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
4
9
8
,

 
 
4
,

 
 
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
1
,

 
 
1
2
3
,

 
 
2
,

 
 
1
6
,

 
 
1
0
9
9
,

 
 
1
2
,

 
 
3
0
2
,

 
 
8
2
,

 
 
5
7
9
,

 
 
2
,

 
 
2
8
,

 
 
2
3
0
,

 
 
5
0
,

 
 
4
9
8
,

 
 
4
,

 
 
9
6
3
,

 
 
9
5
8
,

 
 
1
7
,

 
 
1
2
8
,

 
 
1
0
,

 
 
3
4
5
5
,

 
 
2
1
,

 
 
1
,

 
 
3
0
2
,

 
 
8
2
,

 
 
9
6
3
,

 
 
1
2
1
8
,

 
 
1
5
,

 
 
1
,

 
 
1
2
3
,

 
 
7
3
1
,

 
 
2
9
,

 
 
5
0
,

 
 
6
6
,

 
 
4
1
1
,

 
 
2
0
9
,

 
 
2
5
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
7
7
0
,

 
 
4
4
0
,

 
 
3
3
,

 
 
2
8
,

 
 
1
2
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
3
0
2
,

 
 
8
2
,

 
 
1
3
4
,

 
 
6
,

 
 
4
0
0
]
,

 
[
6
7
,
 
1
9
2
,
 
6
,
 
1
8
,
 
1
4
,
 
2
7
,
 
7
5
3
,
 
6
,
 
5
9
,
 
1
9
,
 
1
,
 
1
4
7
5
,
 
2
,
 
3
7
3
,
 
3
7
,
 
3
8
,
 
2
,
 
3
4
]
,

 
[
7
4
,
 
1
0
6
5
3
1
,
 
8
4
1
9
,
 
2
5
1
4
5
]
,

 
[
1
0
1
,

 
 
6
,

 
 
1
8
,

 
 
1
2
0
4
,

 
 
1
0
,

 
 
1
6
6
,

 
 
7
,

 
 
1
5
8
0
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
1
4
5
4
3
,

 
 
5
0
,

 
 
2
1
3
,

 
 
3
7
,

 
 
7
,

 
 
4
7
6
,

 
 
4
6
6
]
,

 
[
1
3
3
3
0
,

 
 
8
5
,

 
 
2
,

 
 
4
6
0
,

 
 
1
5
,

 
 
2
,

 
 
1
2
2
8
3
,

 
 
6
5
4
9
,

 
 
7
,

 
 
4
6
8
,

 
 
1
0
7
,

 
 
1
4
7
1
5
,

 
 
1
,

 
 
1
6
4
0
,

 
 
6
2
,

 
 
1
1
7
4
,

 
 
1
5
4
]
,

 
[
2
7
3
4
,

 
 
2
8
0
0
,

 
 
1
6
0
5
7
7
,

 
 
1
7
8
,

 
 
1
0
1
0
0
,

 
 
7
,

 
 
3
6
8
,

 
 
2
0
,

 
 
2
3
6
,

 
 
1
5
,

 
 
1
,

 
 
2
7
3
4
,

 
 
2
8
0
0
,

 
 
2
3
,

 
 
1
0
5
4
,

 
 
3
9
8
9
,

 
 
6
2
1
,

 
 
1
0
4
,

 
 
8
5
5
9
,

 
 
1
9
,

 
 
1
3
1
,

 
 
5
5
,

 
 
5
6
8
,

 
 
8
6
3
,

 
 
1
5
,

 
 
3
8
5
,

 
 
5
5
8
0
,

 
 
1
5
6
0
,

 
 
2
7
3
4
,

 
 
2
8
0
0
,

 
 
5
8
1
,

 
 
3
6
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
6
0
5
7
8
,

 
 
2
,

 
 
2
7
3
4
,

 
 
2
8
0
0
,

 
 
6
2
2
,

 
 
1
,

 
 
2
9
5
,

 
 
3
3
9
,

 
 
3
2
,

 
 
1
8
3
,

 
 
1
0
7
,

 
 
1
8
,

 
 
2
7
6
8
,

 
 
9
,

 
 
1
8
,

 
 
7
7
7
6
,

 
 
1
5
,

 
 
9
5
7
3
]
,

 
[
1
2
0
6
,

 
 
6
1
7
,

 
 
1
1
5
1
,

 
 
2
7
,

 
 
5
4
3
1
6
,

 
 
5
4
8
,

 
 
2
,

 
 
1
5
9
,

 
 
5
2
,

 
 
5
6
,

 
 
5
8
4
,

 
 
9
,

 
 
1
3
,

 
 
2
1
3
,

 
 
8
,

 
 
1
5
5
,

 
 
4
5
6
8
,

 
 
3
3
9
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
6
8
,

 
 
1
1
4
,

 
 
9
2
1
,

 
 
1
4
4
,

 
 
5
2
,

 
 
3
2
8
6
,

 
 
2
8
]
,

 
[
1
3
7
,

 
 
7
0
5
,

 
 
2
,

 
 
1
6
,

 
 
1
7
,

 
 
2
0
0
7
,

 
 
1
7
,

 
 
4
4
1
,

 
 
5
,

 
 
2
8
1
0
,

 
 
1
,

 
 
8
3
1
,

 
 
1
0
,

 
 
3
0
,

 
 
8
1
0
,

 
 
1
7
,

 
 
1
5
8
,

 
 
2
3
9
2
,

 
 
1
1
4
,

 
 
4
6
7
2
,

 
 
8
,

 
 
1
4
,

 
 
2
5
1
,

 
 
7
,

 
 
6
5
,

 
 
1
1
9
5
1
,

 
 
8
,

 
 
6
6
4
8
,

 
 
3
4
2
,

 
 
2
6
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
1
4
,

 
 
7
,

 
 
1
9
5
0
,

 
 
2
7
,

 
 
1
9
4
1
,

 
 
8
7
3
6
,

 
 
1
1
9
5
1
,

 
 
1
0
2
3
,

 
 
6
2
3
,

 
 
5
,

 
 
2
9
1
,

 
 
2
4
1
,

 
 
9
4
5
,

 
 
9
,

 
 
5
2
,

 
 
4
2
,

 
 
2
9
5
7
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
5
3
6
,

 
 
1
0
1
,

 
 
7
,

 
 
1
9
,

 
 
2
0
7
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
5
3
6
,

 
 
1
0
,

 
 
3
0
,

 
 
3
0
0
,

 
 
7
2
,

 
 
9
6
,

 
 
6
6
4
8
,

 
 
3
4
2
,

 
 
1
0
,

 
 
4
,

 
 
6
1
0
,

 
 
9
9
5
,

 
 
2
6
,

 
 
2
4
1
,

 
 
2
,

 
 
3
5
6
5
,

 
 
2
7
,

 
 
2
3
,

 
 
1
5
,

 
 
3
7
,

 
 
5
4
3
,

 
 
4
7
,

 
 
9
,

 
 
6
0
7
6
9
,

 
 
2
4
1
,

 
 
2
2
4
,

 
 
2
,

 
 
4
8
,

 
 
1
3
,

 
 
4
7
,

 
 
2
1
5
0
,

 
 
7
,

 
 
2
2
6
,

 
 
1
,

 
 
8
3
1
,

 
 
4
9
,

 
 
3
9
7
,

 
 
1
1
,

 
 
3
4
2
,

 
 
2
3
1
,

 
 
1
1
2
0
,

 
 
2
,

 
 
1
5
4
,

 
 
2
1
,

 
 
6
0
7
7
0
,

 
 
1
6
0
5
7
9
,

 
 
2
6
,

 
 
7
,

 
 
3
9
,

 
 
5
0
6
,

 
 
1
2
1
,

 
 
1
5
4
,

 
 
5
5
,

 
 
3
9
9
]
,

 
[
1
2
9
5
4
,

 
 
2
1
8
,

 
 
3
8
,

 
 
4
,

 
 
4
8
7
6
,

 
 
4
0
5
,

 
 
1
1
4
1
,

 
 
1
2
,

 
 
4
3
2
3
,

 
 
3
3
1
1
,

 
 
3
0
6
,

 
 
4
4
1
,

 
 
1
1
0
,

 
 
2
,

 
 
1
2
1
,

 
 
6
1
,

 
 
4
1
0
,

 
 
5
4
3
,

 
 
1
4
1
,

 
 
7
,

 
 
1
6
9
8
,

 
 
2
3
9
,

 
 
6
5
,

 
 
4
3
,

 
 
1
4
2
,

 
 
2
6
,

 
 
9
0
,

 
 
7
,

 
 
6
3
0
1
,

 
 
1
5
8
5
,

 
 
3
7
6
]
,

 
[
4
5
,
 
6
,
 
9
7
,
 
1
,
 
2
3
6
,
 
2
,
 
2
1
0
,
 
3
6
9
4
,
 
8
3
]
,

 
[
9
5
,

 
 
5
,

 
 
7
,

 
 
1
7
3
2
,

 
 
1
2
,

 
 
3
0
,

 
 
2
0
6
,

 
 
3
6
7
,

 
 
4
8
,

 
 
6
,

 
 
2
,

 
 
7
0
,

 
 
9
,

 
 
7
,

 
 
2
7
5
,

 
 
2
0
,

 
 
5
7
5
,

 
 
8
1
6
,

 
 
2
3
9
3
,

 
 
5
8
1
,

 
 
3
6
3
8
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
2
4
7
1
,

 
 
1
0
,

 
 
8
8
5
,

 
 
2
4
4
0
,

 
 
1
,

 
 
1
4
8
1
,

 
 
2
4
0
8
,

 
 
1
6
3
9
0
,

 
 
5
5
7
,

 
 
1
7
,

 
 
4
,

 
 
1
0
1
5
,

 
 
1
0
,

 
 
2
0
2
3
,

 
 
1
6
0
5
8
0
,

 
 
1
6
0
5
8
1
,

 
 
2
9
5
2
,

 
 
3
2
5
7
,

 
 
1
6
0
5
8
2
,

 
 
8
,

 
 
1
3
,

 
 
4
8
1
,

 
 
2
,

 
 
3
9
2
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
3
4
,

 
 
8
7
3
7
,

 
 
8
7
3
8
]
,

 
[
6
4
7
3
,

 
 
5
,

 
 
3
5
3
8
3
,

 
 
7
8
,

 
 
1
8
,

 
 
6
,

 
 
2
9
2
6
,

 
 
8
5
,

 
 
1
0
6
5
3
2
,

 
 
3
5
3
8
3
,

 
 
1
2
3
5
,

 
 
5
4
,

 
 
1
8
,

 
 
1
1
3
,

 
 
3
5
0
9
,

 
 
7
,

 
 
8
1
,

 
 
4
9
,

 
 
5
7
7
1
,

 
 
1
0
8
9
,

 
 
8
8
,

 
 
1
5
,

 
 
4
1
9
5
,

 
 
2
6
,

 
 
1
,

 
 
6
4
7
3
,

 
 
3
3
6
,

 
 
3
9
7
,

 
 
2
7
3
,

 
 
2
,

 
 
6
0
,

 
 
1
6
8
5
,

 
 
5
4
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
3
5
,

 
 
4
6
]
,

 
[
4
9
7
,

 
 
1
1
3
,

 
 
5
3
9
8
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
1
8
8
,

 
 
3
3
1
2
,

 
 
1
2
,

 
 
3
7
1
4
,

 
 
2
8
2
0
,

 
 
2
,

 
 
1
,

 
 
4
9
3
,

 
 
4
7
3
,

 
 
2
1
7
,

 
 
1
0
4
1
,

 
 
1
2
9
,

 
 
5
,

 
 
9
2
7
,

 
 
3
3
7
3
,

 
 
1
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
1
2
9
8
,

 
 
1
2
,

 
 
1
4
6
1
,

 
 
2
9
0
0
,

 
 
9
3
5
3
,

 
 
4
2
2
7
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
1
3
,

 
 
2
1
3
,

 
 
8
,

 
 
6
4
9
8
,

 
 
5
0
,

 
 
3
3
6
,

 
 
4
7
,

 
 
1
0
,

 
 
1
,

 
 
1
5
3
3
,

 
 
1
4
6
7
,

 
 
6
3
1
,

 
 
4
6
]
,

 
[
7
2
,

 
 
1
8
6
,

 
 
2
2
,

 
 
6
,

 
 
8
6
1
,

 
 
1
5
,

 
 
8
3
,

 
 
6
1
,

 
 
9
3
,

 
 
1
4
3
6
8
,

 
 
1
1
0
2
,

 
 
3
4
,

 
 
6
6
5
,

 
 
6
,

 
 
1
4
9
,

 
 
3
6
4
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
4
3
3
,

 
 
6
1
,

 
 
3
6
,

 
 
7
8
,

 
 
3
4
,

 
 
6
,

 
 
2
3
8
9
,

 
 
1
5
4
,

 
 
7
6
,

 
 
5
,

 
 
7
9
,

 
 
1
2
5
,

 
 
5
2
,

 
 
1
0
0
,

 
 
2
0
6
6
0
]
,

 
[
6
7
,
 
6
,
 
6
7
,
 
6
,
 
1
5
8
5
,
 
1
1
8
,
 
6
7
,
 
2
2
5
]
,

 
[
2
8
0
,

 
 
3
5
,

 
 
1
,

 
 
7
9
,

 
 
8
0
1
,

 
 
7
2
,

 
 
1
3
2
1
,

 
 
6
,

 
 
8
6
,

 
 
5
5
9
,

 
 
2
,

 
 
1
7
1
6
1
,

 
 
3
0
,

 
 
1
4
0
,

 
 
1
7
,

 
 
2
,

 
 
2
0
,

 
 
2
1
4
,

 
 
3
5
,

 
 
3
0
8
1
5
,

 
 
2
9
6
,

 
 
7
,

 
 
6
5
,

 
 
5
3
,

 
 
4
5
,

 
 
1
9
,

 
 
2
,

 
 
6
5
,

 
 
3
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
6
8
1
2
,

 
 
1
,

 
 
2
3
,

 
 
1
3
5
,

 
 
8
4
3
,

 
 
5
,

 
 
8
0
3
4
,

 
 
6
6
,

 
 
1
,

 
 
2
0
3
5
,

 
 
8
7
,

 
 
1
2
2
,

 
 
6
0
,

 
 
2
2
6
3
0
,

 
 
7
6
,

 
 
1
5
0
,

 
 
2
2
6
3
1
,

 
 
1
,

 
 
1
0
6
8
,

 
 
2
1
,

 
 
1
8
1
4
,

 
 
6
6
7
,

 
 
4
8
,

 
 
1
6
0
5
8
3
,

 
 
5
,

 
 
4
5
5
3
1
,

 
 
7
,

 
 
4
5
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
1
,

 
 
1
6
0
5
8
4
,

 
 
1
8
7
2
,

 
 
7
0
4
,

 
 
8
0
0
,

 
 
3
4
6
7
,

 
 
5
3
5
,

 
 
2
1
6
,

 
 
1
0
2
,

 
 
1
2
5
6
,

 
 
4
8
2
,

 
 
2
,

 
 
1
2
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
5
3
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
7
,

 
 
4
5
,

 
 
6
6
,

 
 
3
4
,

 
 
6
0
,

 
 
3
9
4
,

 
 
2
,

 
 
5
1
7
3
,

 
 
1
1
,

 
 
4
6
,

 
 
1
3
4
5
6
,

 
 
1
8
7
2
,

 
 
1
1
8
3
,

 
 
3
4
6
7
,

 
 
8
0
0
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
1
2
4
8
,

 
 
1
1
5
3
,

 
 
2
1
6
,

 
 
2
0
6
,

 
 
9
0
,

 
 
1
,

 
 
1
2
8
9
,

 
 
2
3
6
,

 
 
2
5
,

 
 
1
6
3
,

 
 
1
5
8
,

 
 
1
7
3
,

 
 
1
3
3
3
,

 
 
4
6
0
,

 
 
3
6
5
8
,

 
 
2
,

 
 
1
3
,

 
 
1
1
6
,

 
 
8
0
,

 
 
7
1
,

 
 
3
8
3
,

 
 
1
4
,

 
 
4
7
,

 
 
2
1
3
6
,

 
 
9
9
1
,

 
 
7
9
6
8
,

 
 
5
7
3
4
,

 
 
8
7
8
,

 
 
9
9
1
,

 
 
5
8
1
]
,

 
[
2
2
1
,

 
 
1
1
9
5
2
,

 
 
1
0
,

 
 
1
2
6
2
0
,

 
 
1
6
2
,

 
 
1
,

 
 
1
6
0
5
8
5
,

 
 
5
7
,

 
 
1
,

 
 
2
2
1
,

 
 
5
2
8
7
,

 
 
1
0
,

 
 
1
3
8
2
,

 
 
1
2
,

 
 
5
5
8
,

 
 
2
7
4
,

 
 
8
9
,

 
 
1
6
0
,

 
 
2
5
9
3
3
,

 
 
5
2
8
7
,

 
 
2
3
3
,

 
 
1
,

 
 
6
4
2
,

 
 
2
2
1
0
3
,

 
 
3
6
5
,

 
 
2
3
6
9
,

 
 
3
4
0
4
,

 
 
2
7
,

 
 
2
0
8
5
,

 
 
5
2
8
7
]
,

 
[
7
,
 
5
9
,
 
9
6
,
 
7
0
,
 
1
2
5
,
 
2
,
 
1
9
7
4
,
 
1
5
,
 
4
3
1
5
,
 
2
,
 
4
6
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
6
7
1
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
1
6
0
5
8
6
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
3
3
6
6
8
]
,

 
[
2
4
6
,

 
 
2
0
,

 
 
1
5
8
9
,

 
 
1
5
,

 
 
1
1
,

 
 
4
4
,

 
 
4
7
,

 
 
2
4
9
4
,

 
 
4
6
3
,

 
 
7
5
,

 
 
3
9
,

 
 
2
0
4
,

 
 
3
8
,

 
 
5
1
,

 
 
1
0
8
,

 
 
1
5
,

 
 
6
4
,

 
 
5
,

 
 
1
5
3
8
,

 
 
1
1
,

 
 
7
3
,

 
 
4
0
,

 
 
6
,

 
 
1
0
8
,

 
 
2
6
,

 
 
4
4
,

 
 
4
7
,

 
 
2
4
9
4
,

 
 
5
3
7
,

 
 
1
6
4
,

 
 
3
6
,

 
 
1
3
3
3
1
,

 
 
3
0
1
,

 
 
6
9
8
0
9
]
,

 
[
1
,
 
1
1
9
1
,
 
1
6
1
,
 
2
,
 
2
4
6
,
 
1
,
 
1
1
9
1
,
 
1
6
1
,
 
2
5
5
,
 
1
,
 
2
9
5
]
,

 
[
1
4
8
,
 
1
,
 
4
9
0
,
 
8
6
4
,
 
8
6
7
,
 
2
5
,
 
3
6
]
,

 
[
3
2
1
1
,

 
 
6
6
4
9
,

 
 
3
0
8
5
,

 
 
1
1
2
8
0
,

 
 
4
3
6
5
,

 
 
5
8
6
5
,

 
 
5
3
,

 
 
1
8
,

 
 
2
5
9
3
4
,

 
 
2
7
,

 
 
7
0
9
,

 
 
3
2
6
,

 
 
2
4
8
,

 
 
3
2
6
6
,

 
 
2
9
6
8
9
,

 
 
9
5
6
,

 
 
3
2
6
6
,

 
 
4
1
6
,

 
 
6
3
5
,

 
 
1
3
7
4
5
,

 
 
1
3
,

 
 
9
5
6
,

 
 
1
7
,

 
 
8
6
0
7
,

 
 
5
,

 
 
7
8
5
0
,

 
 
9
6
,

 
 
4
9
4
3
2
,

 
 
9
1
,

 
 
1
0
,

 
 
1
1
8
8
,

 
 
3
,

 
 
2
2
5
6
,

 
 
4
2
3
5
9
,

 
 
6
0
4
,

 
 
3
2
6
6
,

 
 
2
1
1
1
,

 
 
8
3
5
8
7
,

 
 
1
0
6
5
3
3
,

 
 
1
2
,

 
 
1
3
8
6
,

 
 
3
5
9
2
,

 
 
1
5
,

 
 
2
2
6
3
2
,

 
 
6
6
8
0
,

 
 
1
0
,

 
 
2
2
1
0
4
,

 
 
1
5
,

 
 
4
3
0
,

 
 
5
0
3
2
,

 
 
1
3
,

 
 
4
1
2
,

 
 
1
0
0
1
,

 
 
2
1
,

 
 
7
7
,

 
 
4
7
,

 
 
2
0
7
8
,

 
 
2
,

 
 
1
2
0
7
1
,

 
 
1
,

 
 
1
3
9
,

 
 
6
6
8
0
,

 
 
5
,

 
 
1
0
4
,

 
 
2
9
3
6
,

 
 
1
3
4
5
7
,

 
 
3
1
4
6
,

 
 
1
8
3
,

 
 
1
8
0
6
1
,

 
 
3
,

 
 
3
2
6
6
,

 
 
4
1
6
,

 
 
1
6
0
5
8
7
,

 
 
1
6
0
5
8
8
,

 
 
1
4
3
4
,

 
 
2
,

 
 
6
8
,

 
 
6
1
4
,

 
 
4
6
3
8
,

 
 
1
5
,

 
 
1
,

 
 
1
4
3
,

 
 
1
7
,

 
 
2
2
6
3
2
,

 
 
2
0
4
9
,

 
 
6
0
,

 
 
9
6
,

 
 
4
0
3
,

 
 
1
,

 
 
2
6
8
0
,

 
 
1
6
0
6
,

 
 
3
,

 
 
3
2
6
6
,

 
 
2
9
6
8
9
,

 
 
9
5
6
,

 
 
4
5
1
,

 
 
1
,

 
 
4
8
8
,

 
 
3
,

 
 
2
3
9
1
,

 
 
1
8
5
6
,

 
 
2
6
8
0
,

 
 
1
6
0
5
8
9
,

 
 
4
0
,

 
 
8
3
5
8
8
,

 
 
7
5
,

 
 
5
,

 
 
9
2
,

 
 
9
5
6
,

 
 
1
8
,

 
 
2
6
8
0
,

 
 
1
9
7
,

 
 
3
2
6
6
,

 
 
2
9
6
8
9
,

 
 
1
1
8
4
9
,

 
 
5
,

 
 
1
0
4
,

 
 
2
9
3
6
,

 
 
2
2
6
3
2
,

 
 
3
2
0
9
,

 
 
8
,

 
 
6
0
7
7
1
,

 
 
3
2
6
6
,

 
 
1
9
0
5
5
,

 
 
8
3
5
8
9
,

 
 
1
6
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
3
8
3
1
,

 
 
1
6
2
3
,

 
 
2
1
,

 
 
1
3
,

 
 
9
5
6
,

 
 
1
2
,

 
 
3
1
1
,

 
 
1
,

 
 
1
1
4
,

 
 
3
9
1
,

 
 
1
9
6
4
,

 
 
3
5
,

 
 
1
,

 
 
1
3
2
,

 
 
1
2
0
8
,

 
 
4
4
9
8
,

 
 
3
5
9
8
,

 
 
3
,

 
 
2
3
9
1
,

 
 
2
2
6
3
2
,

 
 
6
5
3
,

 
 
2
5
1
4
6
,

 
 
4
5
5
3
2
,

 
 
8
,

 
 
1
6
2
3
,

 
 
2
1
,

 
 
1
9
0
5
5
,

 
 
1
8
7
4
,

 
 
1
0
6
5
3
4
,

 
 
3
3
0
,

 
 
1
5
6
7
7
,

 
 
1
6
0
5
9
0
,

 
 
3
3
7
,

 
 
1
6
0
5
9
1
,

 
 
7
,

 
 
1
6
0
5
9
2
,

 
 
1
6
0
5
9
3
,

 
 
1
0
6
5
3
5
,

 
 
6
6
,

 
 
1
,

 
 
1
1
4
,

 
 
8
8
5
,

 
 
1
9
6
4
,

 
 
5
4
,

 
 
4
4
5
,

 
 
2
2
6
3
2
,

 
 
1
9
3
5
,

 
 
5
,

 
 
1
0
4
,

 
 
6
6
8
0
,

 
 
5
2
0
7
,

 
 
1
0
,

 
 
1
7
1
6
2
,

 
 
8
3
5
9
0
,

 
 
9
6
,

 
 
8
9
,

 
 
4
,

 
 
3
0
9
3
,

 
 
3
2
6
6
,

 
 
2
1
1
1
,

 
 
9
0
8
,

 
 
1
0
,

 
 
1
7
1
6
2
,

 
 
1
0
6
5
3
6
,

 
 
1
0
6
5
3
7
,

 
 
1
0
6
5
3
8
,

 
 
2
7
1
4
,

 
 
1
9
1
,

 
 
4
,

 
 
6
9
0
,

 
 
3
5
,

 
 
6
8
,

 
 
5
0
9
3
,

 
 
6
6
,

 
 
3
1
,

 
 
1
7
1
6
2
,

 
 
7
0
0
,

 
 
6
2
,

 
 
1
0
3
,

 
 
2
9
6
9
0
,

 
 
1
5
9
6
,

 
 
2
2
6
3
2
,

 
 
1
8
1
0
,

 
 
1
0
6
5
3
6
,

 
 
1
0
6
5
3
7
,

 
 
1
0
6
5
3
8
,

 
 
2
2
6
3
2
,

 
 
1
6
0
5
9
4
,

 
 
8
7
,

 
 
1
0
3
9
,

 
 
3
9
7
6
,

 
 
5
0
1
,

 
 
2
6
4
0
,

 
 
1
7
1
6
2
,

 
 
8
,

 
 
6
6
,

 
 
4
,

 
 
1
0
4
2
,

 
 
3
,

 
 
4
9
4
3
3
,

 
 
1
9
7
4
,

 
 
9
0
8
,

 
 
1
6
0
5
9
5
,

 
 
5
4
3
1
7
,

 
 
4
,

 
 
3
3
8
9
,

 
 
3
,

 
 
1
6
1
8
,

 
 
2
2
6
3
2
,

 
 
1
9
3
5
,

 
 
1
4
3
6
9
,

 
 
5
0
0
,

 
 
7
5
6
3
,

 
 
1
8
9
,

 
 
2
4
,

 
 
5
5
9
,

 
 
2
,

 
 
2
3
8
2
4
,

 
 
3
2
,

 
 
2
0
6
0
,

 
 
2
7
,

 
 
1
0
9
6
9
,

 
 
3
7
2
,

 
 
3
,

 
 
2
2
6
3
2
,

 
 
1
8
1
0
,

 
 
6
0
,

 
 
3
,

 
 
5
4
,

 
 
8
6
,

 
 
2
5
3
5
,

 
 
1
0
,

 
 
1
6
0
5
9
6
,

 
 
3
,

 
 
3
2
6
6
,

 
 
4
4
9
8
,

 
 
6
0
4
5
,

 
 
1
4
,

 
 
3
1
3
,

 
 
3
1
,

 
 
1
7
1
6
2
,

 
 
1
8
3
,

 
 
1
0
2
9
1
,

 
 
6
2
8
,

 
 
1
0
6
5
3
9
,

 
 
5
2
4
,

 
 
2
4
,

 
 
6
6
,

 
 
4
,

 
 
2
5
9
3
5
,

 
 
3
,

 
 
3
2
6
6
,

 
 
2
2
6
3
2
,

 
 
6
5
3
,

 
 
2
0
3
,

 
 
1
3
,

 
 
1
6
1
3
,

 
 
1
0
3
,

 
 
1
6
,

 
 
4
1
9
,

 
 
1
,

 
 
2
0
7
1
,

 
 
3
,

 
 
4
0
,

 
 
3
2
6
6
,

 
 
2
2
6
3
2
,

 
 
2
0
4
9
,

 
 
1
3
,

 
 
8
3
3
8
,

 
 
7
0
0
,

 
 
6
6
,

 
 
1
0
3
5
,

 
 
1
6
6
9
,

 
 
2
,

 
 
4
9
4
3
4
,

 
 
8
3
5
9
1
,

 
 
1
6
0
5
9
7
,

 
 
5
7
6
7
,

 
 
1
0
5
6
,

 
 
1
5
7
4
,

 
 
7
0
6
7
,

 
 
6
2
,

 
 
8
,

 
 
3
3
4
7
,

 
 
1
7
,

 
 
1
,

 
 
1
4
4
8
,

 
 
3
,

 
 
4
0
,

 
 
2
2
6
3
2
,

 
 
2
0
4
9
,

 
 
3
,

 
 
4
1
6
0
,

 
 
5
,

 
 
1
2
7
0
,

 
 
2
,

 
 
8
4
1
8
,

 
 
1
6
0
5
9
8
,

 
 
1
4
2
,

 
 
7
8
1
5
,

 
 
8
3
5
9
2
,

 
 
1
,

 
 
1
3
2
,

 
 
1
6
1
8
,

 
 
3
2
6
6
,

 
 
2
5
9
3
6
,

 
 
2
1
6
5
,

 
 
4
,

 
 
1
3
3
3
2
,

 
 
1
0
,

 
 
1
0
3
7
,

 
 
1
4
3
8
,

 
 
8
3
5
9
1
,

 
 
1
0
,

 
 
6
8
,

 
 
3
3
6
6
9
,

 
 
7
0
6
8
,

 
 
1
6
0
9
,

 
 
2
2
6
3
2
,

 
 
6
6
8
0
,

 
 
1
0
,

 
 
8
1
3
,

 
 
2
,

 
 
8
3
5
9
1
,

 
 
1
0
6
5
3
9
,

 
 
8
3
5
9
3
,

 
 
2
3
6
0
,

 
 
4
,

 
 
2
8
4
,

 
 
1
3
0
,

 
 
6
1
,

 
 
4
3
4
8
,

 
 
3
,

 
 
3
2
6
6
,

 
 
2
2
6
3
2
,

 
 
6
5
3
,

 
 
5
7
9
,

 
 
2
,

 
 
1
3
9
6
,

 
 
2
5
9
3
7
,

 
 
8
3
5
9
4
,

 
 
1
6
0
5
9
9
,

 
 
6
2
,

 
 
1
2
8
8
,

 
 
1
,

 
 
1
4
2
,

 
 
3
,

 
 
3
2
6
6
,

 
 
8
3
5
9
5
,

 
 
1
0
6
5
4
0
,

 
 
1
0
6
5
4
1
,

 
 
1
6
0
6
0
0
,

 
 
7
5
7
,

 
 
2
3
6
0
,

 
 
4
,

 
 
2
8
4
,

 
 
3
7
2
,

 
 
3
,

 
 
2
2
6
3
2
,

 
 
2
0
4
9
,

 
 
1
4
5
0
,

 
 
2
1
,

 
 
1
0
6
5
4
0
,

 
 
1
6
0
6
0
1
,

 
 
1
6
0
6
0
2
,

 
 
5
4
3
1
8
,

 
 
3
2
1
7
0
,

 
 
5
,

 
 
2
8
6
4
5
,

 
 
2
1
,

 
 
1
,

 
 
1
3
2
,

 
 
4
6
7
,

 
 
3
1
3
9
,

 
 
1
0
6
5
4
1
,

 
 
5
2
4
,

 
 
1
6
0
6
0
3
,

 
 
2
7
6
7
9
,

 
 
8
7
3
9
,

 
 
1
7
,

 
 
1
2
,

 
 
1
9
0
5
5
,

 
 
9
9
2
,

 
 
5
1
,

 
 
2
3
9
,

 
 
8
7
9
,

 
 
2
2
6
3
2
,

 
 
7
1
,

 
 
4
1
9
,

 
 
4
,

 
 
1
8
3
7
,

 
 
2
1
7
0
,

 
 
7
7
,

 
 
3
5
1
,

 
 
5
1
,

 
 
8
6
,

 
 
4
3
2
3
,

 
 
6
2
6
,

 
 
1
0
,

 
 
4
9
0
3
,

 
 
2
2
6
3
2
,

 
 
6
5
3
,

 
 
3
2
,

 
 
2
6
7
5
0
,

 
 
1
0
4
,

 
 
1
0
7
5
,

 
 
1
6
0
6
0
4
,

 
 
1
6
0
6
0
5
,

 
 
1
,

 
 
6
4
0
1
,

 
 
3
,

 
 
1
9
0
5
5
,

 
 
4
4
9
8
,

 
 
6
0
4
5
,

 
 
1
0
,

 
 
1
,

 
 
7
0
3
9
,

 
 
3
8
6
,

 
 
1
0
,

 
 
6
8
,

 
 
3
3
7
,

 
 
1
6
0
6
0
6
,

 
 
1
6
0
6
0
7
,

 
 
6
2
2
8
,

 
 
9
,

 
 
1
3
2
,

 
 
3
,

 
 
6
8
,

 
 
1
9
0
5
5
,

 
 
4
4
9
8
,

 
 
6
0
4
5
,

 
 
2
3
4
5
,

 
 
2
4
,

 
 
3
8
0
6
,

 
 
3
2
,

 
 
9
9
2
,

 
 
5
4
3
,

 
 
1
,

 
 
7
8
4
,

 
 
3
1
,

 
 
1
,

 
 
1
8
7
4
,

 
 
3
,

 
 
1
0
6
5
3
4
,

 
 
1
,

 
 
3
0
8
1
6
,

 
 
8
3
5
9
3
,

 
 
6
6
,

 
 
9
0
3
4
,

 
 
1
1
9
7
,

 
 
2
2
6
3
2
,

 
 
3
1
4
6
,

 
 
2
5
1
,

 
 
2
1
1
1
,

 
 
5
4
3
1
9
,

 
 
7
6
3
,

 
 
8
3
5
9
6
,

 
 
9
9
3
2
,

 
 
3
3
0
,

 
 
3
0
8
1
6
,

 
 
1
6
1
3
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
4
6
6
9
,

 
 
3
,

 
 
3
4
3
1
,

 
 
1
0
5
6
,

 
 
3
8
6
,

 
 
1
0
,

 
 
1
7
2
,

 
 
3
3
7
,

 
 
1
2
8
4
1
,

 
 
1
,

 
 
1
4
7
9
,

 
 
1
2
5
,

 
 
1
3
0
6
,

 
 
1
3
5
9
,

 
 
1
2
4
9
,

 
 
9
,

 
 
1
,

 
 
2
2
6
3
2
,

 
 
2
4
,

 
 
1
,

 
 
6
8
0
,

 
 
6
6
8
0
,

 
 
3
,

 
 
1
,

 
 
1
6
1
3
,

 
 
1
7
,

 
 
1
2
,

 
 
2
9
6
8
9
,

 
 
1
6
1
3
9
,

 
 
5
4
,

 
 
6
5
1
,

 
 
2
0
2
,

 
 
3
3
,

 
 
6
7
7
9
,

 
 
5
,

 
 
7
2
0
,

 
 
1
0
8
8
8
,

 
 
5
1
,

 
 
1
8
,

 
 
1
0
2
,

 
 
6
0
7
7
2
,

 
 
5
,

 
 
7
4
0
,

 
 
5
,

 
 
9
9
6
,

 
 
1
6
5
,

 
 
4
,

 
 
2
5
0
,

 
 
1
1
0
,

 
 
2
,

 
 
6
3
,

 
 
9
1
,

 
 
4
,

 
 
8
2
5
3
,

 
 
3
,

 
 
1
5
3
7
,

 
 
6
8
1
3
,

 
 
2
8
8
,

 
 
2
3
3
7
,

 
 
1
0
,

 
 
1
3
7
8
,

 
 
5
0
1
,

 
 
3
0
6
9
,

 
 
1
3
,

 
 
1
6
3
9
1
,

 
 
1
2
,

 
 
2
9
6
8
9
,

 
 
4
4
9
8
,

 
 
6
5
3
,

 
 
1
0
0
6
,

 
 
2
2
6
3
2
,

 
 
2
4
,

 
 
4
4
6
,

 
 
1
0
,

 
 
2
1
0
,

 
 
1
9
0
5
5
,

 
 
8
3
5
9
7
,

 
 
5
,

 
 
4
9
4
3
5
,

 
 
1
0
6
5
4
2
,

 
 
1
6
0
6
0
8
,

 
 
1
,

 
 
6
4
0
1
,

 
 
3
,

 
 
1
3
,

 
 
5
0
4
9
,

 
 
6
5
3
,

 
 
2
2
9
1
,

 
 
9
9
,

 
 
1
0
8
8
,

 
 
9
,

 
 
5
4
7
,

 
 
6
8
,

 
 
1
1
1
3
2
,

 
 
3
3
0
,

 
 
1
2
8
4
1
,

 
 
1
0
,

 
 
1
,

 
 
8
9
7
9
,

 
 
5
2
,

 
 
6
8
7
,

 
 
4
,

 
 
1
2
5
0
,

 
 
3
7
4
5
,

 
 
4
2
0
,

 
 
2
7
4
,

 
 
3
4
3
,

 
 
1
6
0
9
,

 
 
2
2
6
3
2
,

 
 
2
7
6
8
0
,

 
 
1
6
0
6
0
9
,

 
 
1
6
0
6
1
0
,

 
 
1
0
6
5
4
3
,

 
 
1
6
0
6
1
1
,

 
 
1
6
0
6
1
2
,

 
 
1
6
0
6
1
3
,

 
 
1
6
0
6
1
4
,

 
 
5
0
1
,

 
 
6
7
5
,

 
 
8
9
,

 
 
2
2
1
3
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
5
4
2
,

 
 
3
,

 
 
6
0
,

 
 
1
9
0
5
5
,

 
 
2
2
8
6
,

 
 
4
6
8
6
,

 
 
5
,

 
 
2
3
7
2
,

 
 
1
0
6
5
4
4
,

 
 
1
6
0
6
1
5
,

 
 
1
6
0
6
1
6
,

 
 
1
6
0
6
1
7
,

 
 
1
6
0
6
1
8
,

 
 
1
6
0
6
1
9
,

 
 
6
9
8
1
0
,

 
 
3
2
1
,

 
 
3
8
,

 
 
3
4
,

 
 
5
1
,

 
 
1
9
,

 
 
1
0
,

 
 
5
2
3
,

 
 
3
,

 
 
4
4
3
,

 
 
9
2
,

 
 
5
4
2
,

 
 
9
0
2
,

 
 
2
,

 
 
1
,

 
 
1
3
0
7
9
,

 
 
2
2
6
3
2
,

 
 
3
1
4
6
,

 
 
3
,

 
 
1
,

 
 
1
6
1
3
,

 
 
3
5
5
,

 
 
1
3
,

 
 
1
0
,

 
 
4
8
9
,

 
 
4
7
,

 
 
1
0
8
0
1
,

 
 
7
8
,

 
 
1
3
,

 
 
2
9
5
1
,

 
 
3
2
6
6
,

 
 
3
2
0
9
,

 
 
4
2
,

 
 
6
6
1
,

 
 
6
5
7
,

 
 
8
7
7
8
,

 
 
7
8
,

 
 
3
4
,

 
 
5
3
,

 
 
1
9
,

 
 
3
6
,

 
 
2
6
0
,

 
 
2
2
6
3
2
,

 
 
2
0
4
9
,

 
 
6
2
3
,

 
 
8
,

 
 
1
1
,

 
 
4
,

 
 
7
7
7
,

 
 
3
,

 
 
1
8
0
6
2
,

 
 
5
4
3
2
0
,

 
 
3
,

 
 
9
4
8
,

 
 
3
2
6
6
,

 
 
1
3
4
0
,

 
 
1
2
5
,

 
 
1
6
6
4
0
,

 
 
9
5
6
,

 
 
8
,

 
 
9
1
,

 
 
4
1
9
,

 
 
5
9
5
1
,

 
 
2
,

 
 
1
7
0
3
,

 
 
1
0
9
7
,

 
 
1
6
3
9
2
,

 
 
4
1
3
6
,

 
 
9
5
6
,

 
 
2
2
,

 
 
3
6
,

 
 
7
8
,

 
 
4
2
,

 
 
1
6
0
6
2
0
,

 
 
6
5
3
,

 
 
3
,

 
 
1
8
2
6
,

 
 
4
1
6
0
,

 
 
4
4
7
5
,

 
 
2
0
5
1
,

 
 
5
6
1
6
,

 
 
3
1
,

 
 
1
,

 
 
3
2
6
6
,

 
 
5
7
1
9
,

 
 
2
0
8
,

 
 
1
0
4
,

 
 
2
9
6
8
9
,

 
 
1
3
3
3
3
,

 
 
2
2
6
3
2
,

 
 
6
5
3
,

 
 
8
,

 
 
1
0
3
2
,

 
 
9
2
9
,

 
 
2
1
,

 
 
6
6
5
0
,

 
 
5
,

 
 
7
0
9
,

 
 
1
6
0
6
2
1
]
,

 
[
1
,

 
 
1
1
9
4
,

 
 
1
0
9
3
,

 
 
4
5
2
,

 
 
2
7
0
5
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
7
8
8
,

 
 
2
1
,

 
 
1
,

 
 
2
6
5
,

 
 
4
1
7
8
,

 
 
3
,

 
 
1
,

 
 
1
2
8
5
,

 
 
1
0
6
5
4
5
,

 
 
1
0
,

 
 
1
,

 
 
1
6
0
6
2
2
,

 
 
1
0
,

 
 
9
6
5
]
,

 
[
2
,
 
4
,
 
4
4
3
3
,
 
1
9
4
1
6
]
,

 
[
3
8
0
5
,

 
 
9
6
3
1
,

 
 
8
,

 
 
3
6
,

 
 
1
4
5
4
4
,

 
 
4
9
4
3
6
,

 
 
2
5
3
,

 
 
3
9
0
,

 
 
3
1
1
,

 
 
9
6
3
2
,

 
 
1
6
0
6
2
3
,

 
 
9
6
3
1
,

 
 
8
,

 
 
3
6
,

 
 
1
4
5
4
4
]
,

 
[
5
8
3
,
 
2
2
1
7
,
 
1
6
4
,
 
1
2
6
,
 
5
5
6
8
,
 
9
,
 
6
8
1
,
 
8
,
 
4
,
 
2
5
4
3
,
 
2
3
0
,
 
7
6
7
,
 
6
,
 
4
6
,
 
1
2
7
2
7
,
 
7
9
2
]
,

 
[
6
1
5
1
,

 
 
1
2
1
1
,

 
 
3
,

 
 
2
8
,

 
 
2
8
9
,

 
 
2
0
,

 
 
2
2
1
,

 
 
2
8
,

 
 
2
8
9
,

 
 
2
0
,

 
 
2
2
1
,

 
 
4
,

 
 
2
9
,

 
 
6
,

 
 
3
1
7
9
,

 
 
2
2
6
5
,

 
 
2
,

 
 
4
2
,

 
 
5
7
,

 
 
1
3
2
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
0
,

 
 
8
5
7
,

 
 
1
5
,

 
 
1
,

 
 
3
5
4
,

 
 
1
8
,

 
 
1
9
6
,

 
 
5
0
,

 
 
1
6
7
7
,

 
 
1
0
,

 
 
1
,

 
 
1
3
8
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
0
,

 
 
2
3
4
,

 
 
3
3
,

 
 
2
8
,

 
 
6
1
5
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
8
,

 
 
2
8
9
,

 
 
2
0
,

 
 
2
2
1
,

 
 
5
,

 
 
5
0
,

 
 
1
6
,

 
 
1
8
6
,

 
 
2
,

 
 
5
1
7
,

 
 
2
0
,

 
 
2
3
4
,

 
 
2
1
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
6
,

 
 
1
8
,

 
 
2
0
0
,

 
 
2
,

 
 
7
9
,

 
 
1
,

 
 
1
7
4
,

 
 
3
,

 
 
2
8
,

 
 
2
8
9
,

 
 
2
0
,

 
 
2
2
1
,

 
 
5
4
7
,

 
 
1
,

 
 
1
3
8
,

 
 
2
6
,

 
 
5
6
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
6
1
5
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
3
7
0
,

 
 
3
1
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
1
1
1
,

 
 
4
,

 
 
1
1
2
9
,

 
 
4
5
,

 
 
1
4
,

 
 
4
5
3
,

 
 
1
,

 
 
1
1
9
,

 
 
1
3
8
,

 
 
1
3
4
,

 
 
6
,

 
 
2
0
0
2
,

 
 
4
1
4
,

 
 
4
6
]
,

 
[
4
3
9
,
 
4
6
,
 
1
6
1
,
 
3
,
 
8
8
3
,
 
6
2
7
9
,
 
1
0
6
5
4
6
,
 
5
1
3
9
]
,

 
[
6
2
,

 
 
2
4
9
4
,

 
 
2
2
,

 
 
7
,

 
 
2
4
,

 
 
1
8
8
,

 
 
1
5
,

 
 
3
8
3
2
,

 
 
2
5
,

 
 
1
2
9
5
5
,

 
 
6
5
3
,

 
 
1
3
7
0
,

 
 
8
4
,

 
 
7
,

 
 
4
3
,

 
 
1
6
,

 
 
5
8
,

 
 
1
3
1
4
]
,

 
[
1
7
6
,

 
 
3
1
2
,

 
 
6
0
7
7
3
,

 
 
2
4
3
,

 
 
3
5
6
6
,

 
 
1
0
2
2
,

 
 
9
5
1
,

 
 
1
7
8
2
,

 
 
1
6
0
6
2
4
,

 
 
7
4
,

 
 
1
,

 
 
7
8
6
,

 
 
1
3
1
,

 
 
6
7
2
3
,

 
 
1
5
0
9
4
,

 
 
4
,

 
 
1
4
7
4
,

 
 
1
0
,

 
 
4
6
2
,

 
 
9
3
,

 
 
4
,

 
 
7
6
6
,

 
 
1
6
0
6
2
5
,

 
 
1
2
0
,

 
 
9
5
8
,

 
 
7
8
,

 
 
5
2
,

 
 
8
,

 
 
4
,

 
 
1
4
7
4
,

 
 
6
3
6
9
,

 
 
7
3
8
9
,

 
 
4
3
6
6
,

 
 
2
2
8
0
]
,

 
[
5
3
7
,

 
 
8
,

 
 
9
3
1
,

 
 
7
,

 
 
5
9
,

 
 
2
7
6
,

 
 
2
,

 
 
1
6
0
6
2
6
,

 
 
2
5
9
,

 
 
2
6
,

 
 
5
3
7
,

 
 
8
,

 
 
9
3
1
,

 
 
5
3
,

 
 
5
6
,

 
 
1
4
,

 
 
1
9
9
4
,

 
 
3
5
,

 
 
1
5
4
,

 
 
1
3
5
4
,

 
 
4
9
,

 
 
3
3
2
,

 
 
7
,

 
 
4
3
,

 
 
2
7
8
,

 
 
5
4
5
,

 
 
7
0
,

 
 
1
0
1
,

 
 
4
4
8
7
,

 
 
5
,

 
 
9
8
,

 
 
1
4
5
1
,

 
 
2
1
,

 
 
2
0
,

 
 
6
9
8
1
1
,

 
 
3
7
7
4
,

 
 
3
,

 
 
5
8
8
,

 
 
7
0
4
,

 
 
4
7
3
7
,

 
 
6
3
6
8
,

 
 
6
1
4
9
]
,

 
[
3
2
0
,
 
7
,
 
8
1
,
 
1
5
7
,
 
4
5
5
3
3
,
 
1
0
7
,
 
2
9
,
 
4
5
,
 
1
6
,
 
2
5
1
9
,
 
1
0
,
 
1
6
2
,
 
2
6
5
1
]
,

 
[
7
2
,

 
 
3
6
9
,

 
 
1
5
,

 
 
1
,

 
 
1
2
9
8
,

 
 
1
2
,

 
 
2
9
,

 
 
1
3
2
7
,

 
 
2
2
,

 
 
7
,

 
 
8
2
5
4
,

 
 
5
5
,

 
 
1
1
3
8
,

 
 
1
5
2
6
7
,

 
 
1
1
4
7
,

 
 
2
,

 
 
6
3
,

 
 
2
2
,

 
 
1
,

 
 
1
2
5
3
,

 
 
3
9
,

 
 
3
7
4
,

 
 
8
8
]
,

 
[
5
4
3
2
,
 
3
3
,
 
1
3
,
 
2
3
1
9
,
 
1
0
4
,
 
1
4
,
 
1
0
2
,
 
3
8
1
,
 
3
8
,
 
1
2
6
3
,
 
8
,
 
2
0
3
,
 
9
1
,
 
1
0
3
4
]
,

 
[
1
8
0
6
3
,

 
 
1
6
0
6
2
7
,

 
 
5
9
,

 
 
9
7
,

 
 
3
7
,

 
 
2
8
9
3
,

 
 
1
8
1
,

 
 
7
5
4
,

 
 
2
,

 
 
8
3
4
,

 
 
1
,

 
 
7
1
7
,

 
 
1
2
,

 
 
1
2
8
,

 
 
3
,

 
 
1
,

 
 
8
9
8
,

 
 
1
7
9
,

 
 
3
,

 
 
1
,

 
 
2
8
9
3
,

 
 
1
7
4
5
,

 
 
5
5
7
,

 
 
1
4
,

 
 
2
,

 
 
8
3
4
,

 
 
1
,

 
 
2
1
5
6
,

 
 
5
9
8
5
,

 
 
3
,

 
 
3
1
1
7
,

 
 
1
8
1
,

 
 
8
3
4
,

 
 
1
0
,

 
 
1
,

 
 
4
2
0
,

 
 
1
7
7
0
,

 
 
1
2
5
0
5
,

 
 
1
3
7
,

 
 
5
4
1
4
]
,

 
[
1
9
,

 
 
6
,

 
 
4
4
6
,

 
 
1
,

 
 
2
7
3
,

 
 
2
,

 
 
9
2
,

 
 
4
0
3
,

 
 
6
,

 
 
1
6
0
6
2
8
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
2
0
,

 
 
9
1
4
1
,

 
 
9
2
,

 
 
4
1
3
,

 
 
4
0
8
,

 
 
7
,

 
 
1
9
,

 
 
5
8
,

 
 
8
5
,

 
 
7
,

 
 
4
5
,

 
 
3
2
6
7
,

 
 
2
0
,

 
 
1
0
9
7
0
,

 
 
2
8
8
3
,

 
 
8
5
6
0
,

 
 
6
4
,

 
 
1
5
,

 
 
1
8
0
,

 
 
5
,

 
 
2
5
8
,

 
 
5
2
7
,

 
 
2
,

 
 
3
0
,

 
 
3
2
1
7
1
,

 
 
5
,

 
 
1
0
2
3
0
,

 
 
1
,

 
 
7
0
4
0
,

 
 
3
,

 
 
8
4
2
0
,

 
 
1
0
,

 
 
1
,

 
 
7
2
7
,

 
 
1
8
2
6
,

 
 
3
6
4
7
,

 
 
3
2
2
,

 
 
2
,

 
 
8
3
5
9
8
,

 
 
8
3
5
9
9
,

 
 
1
0
6
5
4
7
,

 
 
1
0
6
5
4
8
,

 
 
1
0
6
5
4
9
,

 
 
1
0
6
5
5
0
,

 
 
4
9
4
3
7
,

 
 
3
0
8
1
7
,

 
 
2
8
6
4
6
,

 
 
3
3
6
7
0
,

 
 
8
6
0
8
,

 
 
8
3
6
0
0
,

 
 
3
,

 
 
4
4
8
8
,

 
 
6
9
8
1
2
,

 
 
3
6
2
2
,

 
 
5
,

 
 
6
5
1
,

 
 
2
8
1
,

 
 
1
0
9
7
0
,

 
 
5
2
8
8
,

 
 
5
0
4
,

 
 
5
,

 
 
2
3
9
1
,

 
 
1
1
4
7
5
,

 
 
9
3
2
,

 
 
3
7
2
5
,

 
 
3
0
4
1
,

 
 
5
2
0
8
,

 
 
5
1
9
0
]
,

 
[
1
3
9
3
,
 
2
1
4
,
 
3
0
9
,
 
2
1
4
7
,
 
3
8
,
 
8
,
 
1
,
 
2
1
4
,
 
6
,
 
1
4
1
0
,
 
2
,
 
3
0
4
6
,
 
6
4
,
 
4
6
]
,

 
[
8
0
,

 
 
6
,

 
 
1
1
7
,

 
 
1
6
0
6
2
9
,

 
 
1
6
8
7
,

 
 
3
8
,

 
 
6
3
4
,

 
 
3
4
,

 
 
6
,

 
 
2
7
6
,

 
 
7
,

 
 
5
9
7
,

 
 
1
5
,

 
 
2
7
,

 
 
1
0
6
5
5
1
,

 
 
2
1
3
,

 
 
5
4
,

 
 
9
3
8
,

 
 
2
1
5
8
3
,

 
 
1
6
0
6
3
0
,

 
 
5
,

 
 
7
2
,

 
 
1
4
,

 
 
3
1
3
,

 
 
3
1
,

 
 
1
,

 
 
1
1
1
3
3
,

 
 
2
1
6
1
,

 
 
4
5
5
3
4
,

 
 
4
0
,

 
 
1
4
7
,

 
 
1
,

 
 
1
3
9
,

 
 
1
7
9
6
,

 
 
1
6
0
6
3
1
,

 
 
1
3
7
,

 
 
2
8
2
,

 
 
4
,

 
 
2
3
5
,

 
 
5
7
7
2
,

 
 
8
5
,

 
 
8
9
,

 
 
2
,

 
 
8
9
2
8
,

 
 
6
0
,

 
 
5
8
,

 
 
6
4
0
3
,

 
 
2
3
8
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
2
3
1
,

 
 
9
4
,

 
 
7
6
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
1
6
0
6
3
2
,

 
 
2
8
2
,

 
 
5
5
,

 
 
1
2
9
8
,

 
 
4
6
]
,

 
[
1
3
,
 
6
9
8
1
3
,
 
1
6
,
 
3
0
,
 
2
6
2
,
 
8
2
,
 
3
,
 
1
3
,
 
2
0
2
0
4
,
 
5
0
,
 
3
5
6
,
 
1
1
]
,

 
[
1
4
9
1
,

 
 
9
2
1
,

 
 
3
2
,

 
 
8
3
6
0
1
,

 
 
1
0
7
,

 
 
1
0
7
,

 
 
8
3
6
0
1
,

 
 
8
,

 
 
7
3
7
,

 
 
4
,

 
 
7
7
5
,

 
 
3
4
5
,

 
 
5
2
,

 
 
8
,

 
 
6
6
,

 
 
2
4
2
2
,

 
 
1
,

 
 
1
4
9
1
,

 
 
1
2
,

 
 
1
6
0
6
3
3
,

 
 
5
4
3
2
1
]
,

 
[
7
,

 
 
5
5
3
4
,

 
 
1
2
6
,

 
 
2
2
9
3
,

 
 
1
5
4
,

 
 
1
7
2
,

 
 
4
5
6
,

 
 
1
,

 
 
8
2
9
7
,

 
 
4
3
9
2
,

 
 
2
3
,

 
 
1
6
0
6
3
4
,

 
 
3
4
,

 
 
6
,

 
 
7
0
,

 
 
2
2
,

 
 
8
2
9
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
3
1
,

 
 
7
5
,

 
 
1
5
5
,

 
 
7
,

 
 
1
9
,

 
 
1
3
0
8
0
,

 
 
2
3
7
4
,

 
 
1
5
5
,

 
 
6
,

 
 
7
0
,

 
 
7
,

 
 
3
9
,

 
 
6
3
,

 
 
1
,

 
 
6
0
2
,

 
 
1
4
8
3
,

 
 
4
0
,

 
 
1
1
2
,

 
 
8
2
9
7
,

 
 
4
3
9
2
,

 
 
2
,

 
 
6
6
0
2
,

 
 
5
,

 
 
5
1
,

 
 
4
5
,

 
 
4
0
,

 
 
1
6
,

 
 
3
2
6
5
,

 
 
1
0
,

 
 
3
3
6
7
1
,

 
 
1
2
,

 
 
9
1
,

 
 
7
8
5
1
,

 
 
2
7
4
8
]
,

 
[
2
9
6
,

 
 
4
1
,

 
 
8
,

 
 
5
8
0
8
,

 
 
1
2
3
4
,

 
 
1
0
,

 
 
1
0
9
7
1
,

 
 
1
,

 
 
1
0
6
1
,

 
 
6
6
8
0
,

 
 
1
0
2
9
2
,

 
 
2
6
,

 
 
7
,

 
 
5
9
,

 
 
2
2
0
,

 
 
1
1
,

 
 
1
7
9
8
,

 
 
2
1
,

 
 
1
,

 
 
1
1
8
8
,

 
 
1
0
2
9
2
,

 
 
1
6
1
4
0
,

 
 
3
8
5
4
,

 
 
1
1
,

 
 
8
,

 
 
1
2
6
,

 
 
4
,

 
 
1
8
7
1
2
,

 
 
5
,

 
 
1
4
,

 
 
2
0
3
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
1
2
0
7
2
,

 
 
2
3
9
9
,

 
 
3
6
,

 
 
1
1
,

 
 
5
4
3
2
2
,

 
 
1
,

 
 
3
0
9
1
,

 
 
7
,

 
 
1
6
2
7
,

 
 
2
,

 
 
4
6
0
,

 
 
1
1
,

 
 
2
,

 
 
1
,

 
 
7
0
4
1
,

 
 
1
4
5
4
,

 
 
2
8
1
3
,

 
 
1
3
6
9
,

 
 
1
1
6
,

 
 
1
2
5
,

 
 
7
,

 
 
6
5
,

 
 
1
1
,

 
 
1
2
6
,

 
 
1
7
9
8
,

 
 
8
0
,

 
 
7
,

 
 
7
9
,

 
 
1
,

 
 
1
6
1
4
0
,

 
 
3
8
5
4
,

 
 
2
,

 
 
7
5
8
,

 
 
1
,

 
 
1
2
6
3
,

 
 
3
0
9
1
,

 
 
4
,

 
 
3
5
9
]
,

 
[
1
3
4
,

 
 
6
,

 
 
3
0
8
1
8
,

 
 
7
1
,

 
 
3
7
,

 
 
1
,

 
 
2
0
2
3
,

 
 
2
2
6
,

 
 
1
2
5
2
,

 
 
6
5
0
,

 
 
3
8
,

 
 
7
,

 
 
8
1
,

 
 
1
5
7
,

 
 
3
3
,

 
 
4
,

 
 
1
1
5
,

 
 
3
3
4
,

 
 
1
9
4
8
,

 
 
2
,

 
 
6
7
1
,

 
 
5
8
0
,

 
 
4
5
6
,

 
 
2
0
2
3
,

 
 
2
2
6
,

 
 
5
,

 
 
6
,

 
 
2
2
9
,

 
 
3
4
,

 
 
5
2
8
9
,

 
 
5
0
6
,

 
 
2
,

 
 
1
7
1
,

 
 
3
7
,

 
 
3
5
2
,

 
 
2
1
9
0
,

 
 
3
7
,

 
 
2
6
,

 
 
4
4
,

 
 
5
4
9
7
,

 
 
3
7
,

 
 
3
6
,

 
 
2
2
1
3
,

 
 
5
3
0
9
,

 
 
2
,

 
 
6
0
,

 
 
5
8
,

 
 
2
0
2
3
,

 
 
2
2
6
,

 
 
2
1
5
8
4
,

 
 
3
2
,

 
 
2
3
8
2
5
,

 
 
6
8
,

 
 
5
0
1
,

 
 
5
4
3
2
3
,

 
 
1
0
,

 
 
3
0
,

 
 
2
0
5
3
]
,

 
[
2
9
6
,

 
 
3
7
1
,

 
 
3
7
1
4
,

 
 
7
2
,

 
 
3
5
,

 
 
2
,

 
 
4
9
,

 
 
4
7
1
,

 
 
1
,

 
 
2
3
,

 
 
4
9
9
,

 
 
6
1
,

 
 
1
1
5
,

 
 
4
1
0
,

 
 
1
8
,

 
 
1
6
5
,

 
 
2
,

 
 
9
4
,

 
 
1
0
6
0
,

 
 
1
0
,

 
 
1
3
,

 
 
1
3
8
,

 
 
5
0
6
,

 
 
3
7
6
]
,

 
[
6
7
,
 
6
,
 
1
0
7
,
 
1
,
 
2
5
9
3
8
,
 
8
3
6
0
2
,
 
7
6
0
,
 
1
8
5
,
 
1
4
3
,
 
3
7
8
,
 
6
,
 
1
8
,
 
4
0
,
 
2
9
4
1
,
 
3
,
 
2
2
7
]
,

 
[
2
9
6
,

 
 
1
1
,

 
 
5
2
6
,

 
 
1
2
8
,

 
 
2
0
1
,

 
 
9
3
,

 
 
1
5
0
,

 
 
3
3
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
1
1
,

 
 
2
8
6
,

 
 
1
3
,

 
 
2
3
,

 
 
3
2
3
,

 
 
1
3
8
4
,

 
 
7
8
1
,

 
 
1
2
,

 
 
3
8
3
3
,

 
 
8
7
,

 
 
1
6
,

 
 
4
7
5
1
,

 
 
3
8
4
,

 
 
1
0
3
,

 
 
1
2
1
,

 
 
3
1
0
,

 
 
7
8
1
,

 
 
7
,

 
 
6
3
0
2
,

 
 
6
6
9
]
,

 
[
9
3
7
,

 
 
2
3
1
,

 
 
2
5
8
,

 
 
1
1
,

 
 
1
8
3
,

 
 
3
5
3
8
4
,

 
 
1
4
9
9
,

 
 
7
9
4
,

 
 
2
2
,

 
 
1
8
3
5
,

 
 
7
9
0
,

 
 
2
,

 
 
1
8
3
5
,

 
 
7
,

 
 
2
6
5
,

 
 
2
2
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
9
4
,

 
 
4
,

 
 
7
4
5
,

 
 
7
3
0
,

 
 
9
3
,

 
 
7
,

 
 
3
9
,

 
 
3
6
9
,

 
 
4
9
,

 
 
8
2
,

 
 
1
1
5
,

 
 
1
2
3
5
,

 
 
2
2
,

 
 
7
,

 
 
8
1
,

 
 
2
0
4
8
,

 
 
5
,

 
 
9
,

 
 
1
1
0
,

 
 
1
1
,

 
 
4
5
,

 
 
4
9
,

 
 
2
4
6
,

 
 
1
4
1
,

 
 
6
2
,

 
 
1
9
,

 
 
5
7
,

 
 
2
8
8
5
,

 
 
3
7
,

 
 
5
0
2
3
,

 
 
3
2
2
,

 
 
1
9
3
3
,

 
 
1
0
2
9
3
,

 
 
3
7
,

 
 
3
1
5
,

 
 
2
6
4
,

 
 
9
3
,

 
 
2
6
8
,

 
 
2
,

 
 
3
5
6
,

 
 
1
7
4
,

 
 
1
5
9
,

 
 
4
6
6
]
,

 
[
1
0
3
1
,

 
 
2
0
8
7
,

 
 
1
6
1
3
,

 
 
3
,

 
 
2
6
7
5
1
,

 
 
1
8
0
,

 
 
2
8
6
,

 
 
1
0
3
1
,

 
 
2
0
8
7
,

 
 
1
6
1
3
,

 
 
3
,

 
 
2
6
7
5
1
,

 
 
8
,

 
 
6
0
7
7
4
,

 
 
1
6
1
3
,

 
 
1
9
7
,

 
 
5
6
8
,

 
 
3
6
1
,

 
 
3
,

 
 
1
9
8
1
7
,

 
 
5
9
8
6
,

 
 
3
,

 
 
2
6
7
5
1
,

 
 
8
,

 
 
1
4
,

 
 
6
0
7
7
4
,

 
 
2
6
,

 
 
4
7
7
4
,

 
 
1
0
6
5
5
2
,

 
 
1
3
,

 
 
8
,

 
 
1
7
6
1
,

 
 
3
6
,

 
 
1
1
,

 
 
3
2
3
,

 
 
6
0
,

 
 
2
5
6
9
,

 
 
1
7
,

 
 
2
,

 
 
7
4
,

 
 
2
6
9
,

 
 
2
2
8
7
,

 
 
3
,

 
 
2
6
7
5
1
,

 
 
1
2
5
,

 
 
1
,

 
 
5
6
8
,

 
 
3
6
1
,

 
 
8
,

 
 
4
7
7
4
,

 
 
1
0
6
5
5
2
,

 
 
1
0
3
,

 
 
1
6
,

 
 
6
0
7
7
4
,

 
 
1
6
1
3
,

 
 
7
7
,

 
 
1
4
1
,

 
 
5
9
8
6
,

 
 
4
3
,

 
 
1
6
,

 
 
1
0
,

 
 
6
0
7
7
4
,

 
 
1
6
1
3
,

 
 
1
2
5
,

 
 
5
6
8
,

 
 
3
6
1
,

 
 
8
,

 
 
6
0
7
7
4
]
,

 
[
1
,

 
 
9
0
9
,

 
 
2
4
,

 
 
1
5
,

 
 
1
,

 
 
7
4
1
9
,

 
 
1
9
8
,

 
 
2
6
,

 
 
1
,

 
 
9
1
3
,

 
 
2
1
2
,

 
 
2
4
,

 
 
1
,

 
 
1
2
1
4
,

 
 
1
1
7
4
4
,

 
 
1
5
2
6
8
,

 
 
2
4
,

 
 
1
7
7
4
,

 
 
2
,

 
 
1
7
1
6
3
,

 
 
9
,

 
 
1
,

 
 
1
1
7
4
4
,

 
 
8
6
,

 
 
1
,

 
 
3
9
6
8
,

 
 
3
,

 
 
6
8
,

 
 
2
2
4
3
,

 
 
1
6
0
6
3
5
,

 
 
5
4
1
,

 
 
2
,

 
 
1
,

 
 
1
1
3
0
,

 
 
1
5
,

 
 
5
8
1
,

 
 
1
1
6
9
,

 
 
7
6
7
4
,

 
 
6
8
7
,

 
 
7
9
8
,

 
 
1
5
2
6
8
,

 
 
6
2
,

 
 
1
0
,

 
 
7
4
5
,

 
 
2
,

 
 
3
0
,

 
 
2
1
4
,

 
 
3
4
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
1
3
7
7
,

 
 
1
,

 
 
6
2
0
,

 
 
7
6
,

 
 
1
6
7
,

 
 
2
9
6
,

 
 
2
6
,

 
 
1
4
,

 
 
1
5
,

 
 
1
,

 
 
7
4
1
9
,

 
 
2
6
7
,

 
 
2
6
,

 
 
1
5
,

 
 
1
,

 
 
1
2
1
4
,

 
 
1
1
7
4
4
,

 
 
5
4
,

 
 
1
,

 
 
5
4
6
,

 
 
7
0
1
,

 
 
2
3
8
2
6
,

 
 
5
2
,

 
 
4
1
5
4
,

 
 
4
4
,

 
 
1
4
9
2
,

 
 
2
,

 
 
4
,

 
 
1
5
8
8
9
,

 
 
1
1
,

 
 
4
2
,

 
 
3
6
9
,

 
 
5
7
,

 
 
2
3
3
9
,

 
 
6
0
,

 
 
9
2
0
0
,

 
 
1
2
,

 
 
1
1
,

 
 
1
5
0
,

 
 
8
9
,

 
 
2
3
8
,

 
 
5
2
,

 
 
8
,

 
 
1
6
8
2
,

 
 
2
,

 
 
8
3
6
0
3
,

 
 
1
,

 
 
9
9
3
3
,

 
 
1
7
9
4
,

 
 
7
9
9
,

 
 
5
,

 
 
1
1
,

 
 
8
,

 
 
3
8
0
,

 
 
9
,

 
 
7
7
,

 
 
1
0
,

 
 
1
,

 
 
9
9
8
,

 
 
3
,

 
 
1
3
1
3
,

 
 
8
6
,

 
 
8
3
6
0
4
,

 
 
6
9
8
1
4
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
,

 
 
7
4
1
9
,

 
 
1
9
8
,

 
 
5
2
4
,

 
 
3
3
,

 
 
1
2
6
2
1
,

 
 
1
5
,

 
 
1
6
0
,

 
 
1
1
6
9
,

 
 
5
2
,

 
 
3
2
1
7
2
,

 
 
1
1
2
0
5
,

 
 
1
5
,

 
 
1
,

 
 
1
9
6
7
,

 
 
4
3
1
3
,

 
 
3
3
,

 
 
4
,

 
 
3
4
4
8
,

 
 
1
0
,

 
 
1
6
5
9
,

 
 
1
5
,

 
 
1
,

 
 
3
7
4
1
1
,

 
 
1
6
2
7
,

 
 
1
2
,

 
 
2
5
9
3
9
,

 
 
5
,

 
 
8
4
,

 
 
1
9
5
0
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
1
7
0
1
,

 
 
2
1
0
8
3
,

 
 
2
1
5
8
5
,

 
 
2
7
6
8
1
,

 
 
1
5
,

 
 
1
,

 
 
3
3
5
2
,

 
 
1
0
8
8
9
,

 
 
6
0
7
7
5
,

 
 
2
,

 
 
1
0
4
,

 
 
1
0
8
9
0
,

 
 
5
,

 
 
1
4
8
8
7
,

 
 
2
,

 
 
2
9
4
1
,

 
 
1
,

 
 
1
2
1
4
,

 
 
1
9
6
7
,

 
 
2
6
,

 
 
1
,

 
 
1
1
2
3
,

 
 
8
6
6
,

 
 
1
5
,

 
 
6
2
2
,

 
 
1
1
6
9
,

 
 
2
4
,

 
 
4
,

 
 
2
7
6
,

 
 
8
5
0
9
,

 
 
6
0
7
0
,

 
 
1
4
9
,

 
 
4
9
6
,

 
 
1
5
0
,

 
 
1
0
,

 
 
4
,

 
 
2
9
4
9
,

 
 
5
4
,

 
 
2
4
,

 
 
1
6
3
,

 
 
3
,

 
 
4
,

 
 
1
0
6
5
5
3
,

 
 
1
4
7
1
6
,

 
 
1
6
0
6
3
6
,

 
 
1
,

 
 
8
4
2
1
,

 
 
1
0
7
8
,

 
 
2
,

 
 
1
5
9
,

 
 
1
1
,

 
 
1
7
,

 
 
4
,

 
 
9
0
9
,

 
 
3
,

 
 
4
6
8
7
,

 
 
1
5
0
9
5
,

 
 
2
,

 
 
1
1
8
,

 
 
7
6
,

 
 
1
5
,

 
 
1
,

 
 
7
4
1
9
,

 
 
1
9
8
,

 
 
2
,

 
 
4
,

 
 
5
0
9
4
,

 
 
1
5
,

 
 
1
,

 
 
1
2
1
4
,

 
 
1
1
7
4
4
,

 
 
5
4
,

 
 
1
8
4
,

 
 
2
5
8
,

 
 
1
,

 
 
4
1
6
,

 
 
1
9
8
6
,

 
 
1
5
5
,

 
 
1
2
8
,

 
 
7
0
6
5
,

 
 
1
6
0
6
3
7
,

 
 
5
,

 
 
1
2
1
8
3
,

 
 
5
0
1
,

 
 
2
8
6
4
7
]
,

 
[
7
8
4
5
,
 
1
7
1
,
 
1
,
 
4
0
0
9
,
 
5
5
0
,
 
2
7
0
2
,
 
4
1
0
3
]
,

 
[
4
4
,

 
 
7
,

 
 
4
9
,

 
 
1
8
2
4
,

 
 
1
1
6
4
9
,

 
 
9
,

 
 
2
8
5
4
,

 
 
3
5
,

 
 
1
2
0
8
,

 
 
5
,

 
 
1
3
5
5
,

 
 
2
6
6
3
,

 
 
5
1
,

 
 
1
8
,

 
 
2
5
3
1
,

 
 
1
0
,

 
 
1
,

 
 
1
3
9
,

 
 
6
0
0
,

 
 
4
6
]
,

 
[
6
0
2
,
 
1
7
8
1
,
 
3
3
,
 
9
5
7
4
,
 
1
2
8
4
2
,
 
8
0
0
,
 
3
0
4
1
,
 
8
1
6
]
,

 
[
1
0
,

 
 
4
3
6
,

 
 
1
,

 
 
9
8
5
,

 
 
2
1
2
4
,

 
 
5
6
,

 
 
1
1
4
6
8
,

 
 
1
,

 
 
2
0
0
3
,

 
 
2
1
2
4
,

 
 
2
2
,

 
 
3
9
5
,

 
 
2
7
,

 
 
7
2
7
,

 
 
1
1
6
,

 
 
1
7
7
,

 
 
5
5
,

 
 
2
9
5
,

 
 
6
,

 
 
5
9
,

 
 
1
9
,

 
 
3
0
5
,

 
 
1
,

 
 
2
4
4
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
4
,

 
 
1
0
1
0
1
,

 
 
1
2
2
,

 
 
1
3
,

 
 
4
3
,

 
 
7
0
1
,

 
 
1
6
,

 
 
4
4
6
,

 
 
1
7
,

 
 
1
4
8
,

 
 
1
,

 
 
2
7
9
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
3
7
4
1
2
,

 
 
2
3
,

 
 
1
2
,

 
 
1
2
6
8
,

 
 
1
5
,

 
 
7
4
,

 
 
2
,

 
 
9
8
2
,

 
 
3
5
,

 
 
2
0
,

 
 
4
3
8
]
,

 
[
1
8
5
,

 
 
4
,

 
 
2
6
4
,

 
 
1
3
7
4
6
,

 
 
6
4
4
9
,

 
 
2
,

 
 
1
3
5
3
,

 
 
1
4
3
8
,

 
 
2
7
,

 
 
4
0
7
0
,

 
 
3
7
2
,

 
 
3
,

 
 
1
3
8
9
,

 
 
8
5
1
3
,

 
 
1
4
3
8
,

 
 
7
0
4
,

 
 
2
7
1
,

 
 
4
5
2
0
,

 
 
6
4
5
0
,

 
 
2
1
0
1
,

 
 
2
,

 
 
4
7
,

 
 
7
1
5
,

 
 
1
8
3
7
,

 
 
3
2
4
,

 
 
2
3
3
,

 
 
3
6
5
,

 
 
3
,

 
 
1
,

 
 
1
1
0
,

 
 
3
2
2
,

 
 
1
,

 
 
2
9
,

 
 
1
5
,

 
 
1
,

 
 
2
7
5
3
,

 
 
2
3
,

 
 
1
2
,

 
 
1
8
3
7
,

 
 
1
1
2
8
1
,

 
 
1
3
,

 
 
5
7
3
5
,

 
 
1
,

 
 
4
8
6
4
,

 
 
1
8
3
7
,

 
 
8
7
1
,

 
 
1
0
,

 
 
2
5
0
3
,

 
 
1
7
4
,

 
 
1
5
,

 
 
2
8
,

 
 
2
2
5
3
,

 
 
8
5
3
,

 
 
6
3
2
7
,

 
 
5
2
9
0
]
,

 
[
9
3
7
,

 
 
7
,

 
 
1
9
,

 
 
8
9
,

 
 
7
0
5
,

 
 
2
,

 
 
4
9
,

 
 
3
5
6
,

 
 
1
,

 
 
1
4
6
3
,

 
 
1
6
4
8
,

 
 
1
0
,

 
 
1
,

 
 
1
4
1
2
,

 
 
3
5
,

 
 
7
9
8
,

 
 
1
0
1
6
5
,

 
 
9
1
,

 
 
4
,

 
 
4
5
5
3
5
,

 
 
1
6
0
6
3
8
,

 
 
1
0
6
5
5
4
,

 
 
5
2
,

 
 
2
8
6
,

 
 
8
2
9
,

 
 
5
2
,

 
 
8
,

 
 
1
4
,

 
 
5
,

 
 
1
0
7
1
5
,

 
 
9
,

 
 
1
3
0
,

 
 
7
2
1
,

 
 
8
6
,

 
 
1
0
8
7
,

 
 
5
4
7
,

 
 
1
,

 
 
3
2
6
,

 
 
1
9
7
,

 
 
5
2
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
1
8
,

 
 
6
7
7
,

 
 
2
1
,

 
 
1
,

 
 
5
5
8
,

 
 
9
9
7
,

 
 
7
2
1
,

 
 
1
0
8
7
,

 
 
1
0
4
0
,

 
 
1
7
,

 
 
5
2
,

 
 
5
4
3
2
4
,

 
 
1
,

 
 
3
7
2
,

 
 
2
,

 
 
1
6
,

 
 
1
9
7
6
,

 
 
5
,

 
 
1
1
,

 
 
1
2
6
,

 
 
7
9
0
,

 
 
3
2
2
,

 
 
2
,

 
 
9
,

 
 
1
2
6
5
,

 
 
4
2
,

 
 
1
,

 
 
1
4
3
,

 
 
2
,

 
 
2
1
4
,

 
 
2
1
5
,

 
 
3
1
9
0
,

 
 
2
,

 
 
1
7
9
,

 
 
5
,

 
 
8
0
3
0
,

 
 
8
,

 
 
6
8
,

 
 
2
8
6
4
8
,

 
 
5
,

 
 
5
2
,

 
 
2
0
3
,

 
 
3
9
7
,

 
 
4
,

 
 
8
0
9
,

 
 
3
,

 
 
4
8
1
2
,

 
 
5
,

 
 
1
2
0
7
3
,

 
 
1
1
8
5
0
,

 
 
1
0
6
,

 
 
7
,

 
 
6
6
,

 
 
1
0
7
8
,

 
 
2
,

 
 
3
5
6
,

 
 
1
,

 
 
3
8
7
,

 
 
3
5
,

 
 
1
5
4
,

 
 
1
3
7
4
7
,

 
 
4
,

 
 
1
1
5
2
,

 
 
1
9
8
,

 
 
1
0
,

 
 
2
1
0
4
,

 
 
1
2
6
5
,

 
 
1
9
,

 
 
5
6
3
0
,

 
 
4
3
0
,

 
 
4
0
4
1
,

 
 
9
6
1
,

 
 
1
5
0
,

 
 
1
0
,

 
 
4
0
7
1
,

 
 
5
2
,

 
 
1
8
5
0
,

 
 
1
6
0
6
3
9
,

 
 
2
5
1
3
2
,

 
 
4
0
4
1
,

 
 
2
3
6
9
,

 
 
2
4
8
,

 
 
2
7
,

 
 
2
5
1
,

 
 
4
0
7
2
,

 
 
1
7
0
9
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
5
2
,

 
 
1
3
,

 
 
8
5
,

 
 
1
0
6
0
,

 
 
8
,

 
 
1
4
,

 
 
1
6
3
,

 
 
9
,

 
 
5
6
,

 
 
1
0
4
0
,

 
 
3
3
,

 
 
1
,

 
 
8
1
0
,

 
 
3
,

 
 
6
8
,

 
 
9
0
3
9
,

 
 
1
3
0
,

 
 
7
5
,

 
 
6
6
,

 
 
1
3
6
,

 
 
1
1
,

 
 
6
3
2
8
,

 
 
9
,

 
 
4
,

 
 
2
2
2
9
,

 
 
3
9
,

 
 
6
9
8
1
5
,

 
 
3
8
,

 
 
4
,

 
 
2
2
2
,

 
 
8
,

 
 
2
5
,

 
 
8
,

 
 
1
4
,

 
 
5
,

 
 
3
8
,

 
 
2
2
2
6
,

 
 
5
2
,

 
 
3
9
2
8
]
,

 
[
4
1
,
 
1
3
7
,
 
1
3
1
,
 
1
5
4
,
 
1
4
7
1
,
 
1
2
8
0
,
 
2
0
1
,
 
3
3
6
7
2
,
 
4
6
]
,

 
[
1
5
1
,

 
 
9
,

 
 
3
0
,

 
 
1
4
4
8
,

 
 
5
1
3
,

 
 
5
5
5
,

 
 
1
6
0
6
4
0
,

 
 
8
9
,

 
 
1
1
,

 
 
8
,

 
 
1
8
0
3
,

 
 
1
6
2
,

 
 
5
,

 
 
9
7
6
,

 
 
4
1
2
,

 
 
5
,

 
 
6
8
,

 
 
1
7
2
7
,

 
 
3
3
7
4
,

 
 
8
,

 
 
1
4
,

 
 
9
8
,

 
 
7
,

 
 
8
1
,

 
 
8
6
8
4
,

 
 
2
1
,

 
 
1
,

 
 
5
8
9
1
]
,

 
[
7
2
,

 
 
5
2
1
,

 
 
1
8
6
,

 
 
1
,

 
 
1
7
8
9
,

 
 
4
2
,

 
 
2
3
7
,

 
 
5
7
,

 
 
5
0
2
,

 
 
5
,

 
 
7
,

 
 
7
0
,

 
 
7
4
,

 
 
2
,

 
 
2
6
2
6
,

 
 
3
0
,

 
 
1
7
0
,

 
 
3
3
,

 
 
6
8
1
4
,

 
 
1
5
5
,

 
 
6
2
2
]
,

 
[
7
2
,
 
1
7
5
0
,
 
1
8
5
,
 
4
,
 
2
1
5
4
,
 
1
6
9
,
 
1
2
,
 
3
7
]
,

 
[
4
6
3
,
 
3
5
2
,
 
6
,
 
1
0
8
,
 
2
,
 
2
0
6
,
 
1
5
,
 
1
,
 
4
6
,
 
2
9
,
 
3
5
,
 
9
,
 
7
1
,
 
1
6
0
6
4
1
,
 
2
,
 
7
0
]
,

 
[
1
4
3
6
,

 
 
7
,

 
 
1
3
6
,

 
 
1
1
,

 
 
5
5
2
,

 
 
2
,

 
 
2
2
0
,

 
 
1
3
,

 
 
1
6
7
1
,

 
 
2
7
,

 
 
1
1
4
4
,

 
 
2
6
,

 
 
1
1
1
,

 
 
8
,

 
 
1
,

 
 
2
1
0
8
4
,

 
 
2
2
1
0
5
,

 
 
1
9
4
1
7
,

 
 
1
9
4
1
8
]
,

 
[
1
7
9
,

 
 
3
9
,

 
 
1
5
8
,

 
 
4
9
8
,

 
 
6
0
,

 
 
1
0
5
,

 
 
4
5
6
,

 
 
1
,

 
 
3
0
8
1
9
,

 
 
3
,

 
 
1
,

 
 
4
9
0
0
,

 
 
1
1
8
8
,

 
 
7
0
0
,

 
 
4
9
0
0
,

 
 
8
2
1
0
,

 
 
1
3
3
,

 
 
2
,

 
 
2
4
7
3
,

 
 
1
3
2
,

 
 
3
,

 
 
1
,

 
 
2
1
3
4
,

 
 
3
,

 
 
1
,

 
 
2
5
9
4
0
,

 
 
1
5
8
9
0
,

 
 
2
6
,

 
 
1
,

 
 
2
1
3
4
,

 
 
1
2
3
2
,

 
 
5
1
4
8
,

 
 
7
6
,

 
 
4
9
0
0
,

 
 
8
2
1
0
,

 
 
5
,

 
 
8
9
,

 
 
8
8
1
,

 
 
9
2
,

 
 
1
7
0
,

 
 
2
3
9
9
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
2
1
2
,

 
 
2
4
,

 
 
9
,

 
 
4
9
0
0
,

 
 
8
2
1
0
,

 
 
2
4
,

 
 
1
8
2
,

 
 
3
8
1
9
,

 
 
1
,

 
 
1
1
0
5
6
,

 
 
2
0
8
,

 
 
4
1
1
0
,

 
 
9
2
,

 
 
1
0
8
5
,

 
 
1
5
,

 
 
6
9
8
1
6
,

 
 
2
3
9
9
,

 
 
1
0
,

 
 
1
,

 
 
3
6
8
3
,

 
 
1
4
8
6
,

 
 
9
,

 
 
1
7
9
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
4
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
8
4
9
,

 
 
4
6
]
,

 
[
5
0
,
 
3
4
,
 
1
4
,
 
4
7
1
,
 
5
5
,
 
5
8
,
 
7
2
5
1
,
 
6
4
4
,
 
1
2
4
,
 
4
6
]
,

 
[
7
,

 
 
5
,

 
 
1
7
7
8
,

 
 
1
6
8
9
5
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
7
,

 
 
5
,

 
 
4
6
,

 
 
1
2
7
2
7
,

 
 
7
9
2
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
4
6
6
,

 
 
9
,

 
 
6
5
2
1
,

 
 
9
6
,

 
 
4
8
5
6
,

 
 
1
3
9
6
,

 
 
3
5
3
8
5
,

 
 
1
7
,

 
 
2
7
,

 
 
1
6
2
0
,

 
 
5
,

 
 
7
8
5
2
,

 
 
3
0
8
2
0
,

 
 
6
4
,

 
 
1
9
8
7
,

 
 
4
7
4
,

 
 
6
5
2
1
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
6
5
2
1
,

 
 
3
5
5
6
,

 
 
2
6
4
8
,

 
 
8
4
2
2
,

 
 
6
9
8
1
7
,

 
 
1
0
6
5
5
5
,

 
 
4
5
5
3
6
,

 
 
3
5
3
8
5
,

 
 
3
5
,

 
 
8
7
8
3
,

 
 
3
,

 
 
1
9
1
,

 
 
9
7
1
,

 
 
3
9
7
7
,

 
 
1
0
,

 
 
4
2
7
6
,

 
 
5
3
,

 
 
3
0
9
,

 
 
3
4
,

 
 
1
4
,

 
 
4
6
6
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
4
6
6
,

 
 
9
6
,

 
 
2
2
,

 
 
5
2
,

 
 
1
0
7
1
6
,

 
 
1
5
,

 
 
3
8
8
6
,

 
 
2
5
,

 
 
6
5
7
2
,

 
 
2
5
,

 
 
1
8
2
4
,

 
 
1
5
,

 
 
3
8
8
6
,

 
 
5
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
4
0
2
,

 
 
4
8
,

 
 
6
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
3
8
8
6
,

 
 
2
4
3
,

 
 
1
1
9
8
,

 
 
1
7
5
3
,

 
 
8
1
6
,

 
 
3
2
7
,

 
 
2
2
1
8
,

 
 
6
0
7
7
6
,

 
 
4
2
7
6
,

 
 
3
5
3
8
5
,

 
 
1
2
9
9
,

 
 
9
4
2
,

 
 
1
7
6
,

 
 
1
0
6
5
5
6
,

 
 
2
7
6
8
,

 
 
3
8
8
6
,

 
 
2
4
3
,

 
 
9
5
1
,

 
 
1
8
7
2
,

 
 
2
0
1
7
,

 
 
4
2
6
5
,

 
 
1
8
3
8
,

 
 
2
,

 
 
7
2
9
,

 
 
1
0
6
5
5
7
,

 
 
6
5
5
0
,

 
 
3
8
4
1
,

 
 
1
7
6
,

 
 
2
2
5
1
,

 
 
3
8
8
6
,

 
 
2
4
3
,

 
 
1
1
9
8
,

 
 
1
8
3
9
,

 
 
1
8
7
2
,

 
 
2
4
4
,

 
 
5
4
3
2
5
,

 
 
4
2
7
6
,

 
 
3
3
6
7
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
5
4
,

 
 
9
6
,

 
 
2
2
,

 
 
2
1
5
1
,

 
 
2
4
4
,

 
 
1
1
8
8
,

 
 
1
3
1
,

 
 
1
9
5
3
,

 
 
3
,

 
 
1
5
4
,

 
 
6
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
2
1
5
1
,

 
 
1
0
8
1
,

 
 
6
8
3
,

 
 
1
2
0
7
4
,

 
 
1
0
6
5
5
8
,

 
 
7
0
4
2
,

 
 
1
4
,

 
 
3
5
4
,

 
 
2
2
,

 
 
3
8
8
6
,

 
 
5
,

 
 
1
6
9
7
,

 
 
9
7
7
,

 
 
5
4
1
,

 
 
3
5
,

 
 
1
5
4
,

 
 
5
,

 
 
6
8
,

 
 
7
1
9
,

 
 
7
9
5
,

 
 
9
1
,

 
 
1
0
8
7
,

 
 
6
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
8
3
6
0
5
,

 
 
2
4
3
,

 
 
4
7
4
,

 
 
1
0
6
5
5
9
,

 
 
4
2
7
6
,

 
 
4
5
5
3
6
,

 
 
3
5
3
8
5
,

 
 
1
9
4
1
9
,

 
 
7
1
9
,

 
 
2
3
1
6
8
,

 
 
9
8
7
,

 
 
3
2
6
,

 
 
4
5
5
3
7
,

 
 
2
3
2
8
,

 
 
4
5
5
3
8
,

 
 
3
2
9
0
,

 
 
7
,

 
 
5
,

 
 
4
6
,

 
 
1
2
7
2
7
,

 
 
7
9
2
,

 
 
4
5
,

 
 
1
9
9
,

 
 
2
3
6
,

 
 
1
7
5
,

 
 
3
2
7
,

 
 
4
6
,

 
 
8
,

 
 
3
6
9
,

 
 
1
4
3
,

 
 
5
3
,

 
 
6
6
,

 
 
4
7
6
,

 
 
4
6
6
,

 
 
9
,

 
 
5
2
,

 
 
5
9
2
,

 
 
1
0
,

 
 
6
5
7
,

 
 
4
0
,

 
 
6
8
0
,

 
 
5
,

 
 
9
7
7
,

 
 
6
7
4
7
,

 
 
4
7
3
,

 
 
2
6
4
9
,

 
 
5
,

 
 
1
3
7
2
,

 
 
7
5
2
,

 
 
4
8
,

 
 
6
4
,

 
 
1
9
8
7
,

 
 
2
8
5
6
,

 
 
6
1
5
,

 
 
2
4
3
,

 
 
2
8
5
6
,

 
 
5
0
9
0
,

 
 
4
7
4
,

 
 
2
0
4
4
,

 
 
4
5
5
3
6
,

 
 
3
5
3
8
5
,

 
 
1
6
1
4
1
,

 
 
1
7
,

 
 
3
7
4
1
3
,

 
 
1
6
2
,

 
 
1
0
6
5
6
0
,

 
 
1
7
,

 
 
8
3
6
0
6
,

 
 
7
,

 
 
5
,

 
 
4
6
,

 
 
1
8
,

 
 
1
4
3
,

 
 
5
3
,

 
 
1
8
,

 
 
8
4
1
,

 
 
5
,

 
 
5
3
,

 
 
1
8
,

 
 
1
4
3
,

 
 
5
,

 
 
5
3
,

 
 
4
5
,

 
 
1
9
9
,

 
 
2
3
6
,

 
 
1
7
5
,

 
 
3
2
7
,

 
 
6
1
7
,

 
 
3
8
9
,

 
 
6
,

 
 
3
1
4
]
,

 
[
1
8
,

 
 
6
,

 
 
4
6
3
,

 
 
1
1
7
8
,

 
 
7
,

 
 
4
5
4
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
6
3
2
9
,

 
 
3
1
,

 
 
2
8
,

 
 
1
2
,

 
 
4
,

 
 
2
6
0
,

 
 
4
9
6
,

 
 
7
1
,

 
 
4
2
3
6
0
,

 
 
3
6
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
9
9
1
,

 
 
5
0
,

 
 
8
8
9
,

 
 
3
0
,

 
 
9
8
,

 
 
2
0
6
6
,

 
 
7
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
6
3
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
6
6
5
,

 
 
6
4
7
]
,

 
[
2
7
4
0
,

 
 
1
2
,

 
 
1
,

 
 
7
8
2
,

 
 
3
,

 
 
8
7
,

 
 
3
0
8
2
1
,

 
 
5
0
9
5
,

 
 
1
8
8
2
,

 
 
5
,

 
 
7
1
,

 
 
1
5
3
,

 
 
1
0
2
8
,

 
 
9
5
,

 
 
1
2
,

 
 
2
0
,

 
 
1
5
5
1
]
,

 
[
1
8
7
2
8
,

 
 
5
7
8
,

 
 
1
0
7
1
7
,

 
 
4
9
4
3
8
,

 
 
6
0
7
7
7
,

 
 
1
6
9
5
,

 
 
5
,

 
 
4
,

 
 
2
6
0
,

 
 
2
8
7
,

 
 
1
1
2
,

 
 
3
4
4
,

 
 
8
6
,

 
 
1
7
3
8
,

 
 
1
6
0
6
4
2
,

 
 
5
,

 
 
4
0
,

 
 
1
0
5
,

 
 
2
4
,

 
 
3
3
9
,

 
 
3
5
,

 
 
1
,

 
 
3
4
4
,

 
 
9
,

 
 
8
6
,

 
 
8
3
3
,

 
 
6
0
,

 
 
8
6
,

 
 
9
6
,

 
 
3
0
,

 
 
1
7
0
,

 
 
5
,

 
 
7
,

 
 
1
0
3
5
,

 
 
5
1
0
,

 
 
1
4
5
7
,

 
 
1
2
,

 
 
9
2
,

 
 
8
2
,

 
 
1
5
,

 
 
2
8
,

 
 
2
7
6
8
2
]
,

 
[
1
1
,

 
 
2
8
5
,

 
 
3
5
,

 
 
2
9
4
2
,

 
 
7
1
,

 
 
4
,

 
 
4
1
3
7
,

 
 
9
,

 
 
8
0
3
,

 
 
1
5
7
,

 
 
3
3
,

 
 
3
0
8
,

 
 
5
6
0
,

 
 
2
7
4
,

 
 
2
,

 
 
1
,

 
 
4
9
6
,

 
 
3
,

 
 
3
2
1
7
3
,

 
 
5
,

 
 
1
2
5
0
6
,

 
 
1
4
7
1
7
,

 
 
1
9
7
,

 
 
2
2
,

 
 
6
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
2
3
,

 
 
1
8
3
7
4
,

 
 
1
1
6
,

 
 
2
5
5
,

 
 
8
8
8
,

 
 
6
3
,

 
 
1
1
,

 
 
4
2
,

 
 
6
0
2
5
,

 
 
4
4
,

 
 
5
7
3
3
,

 
 
9
3
,

 
 
4
9
2
,

 
 
1
1
9
,

 
 
1
1
9
2
,

 
 
5
,

 
 
5
3
,

 
 
3
4
,

 
 
1
6
7
5
,

 
 
2
2
0
2
,

 
 
1
0
6
,

 
 
5
,

 
 
1
0
7
1
8
,

 
 
8
,

 
 
1
8
7
,

 
 
1
5
,

 
 
4
1
9
5
,

 
 
1
5
2
6
9
]
,

 
[
3
6
0
,

 
 
8
,

 
 
3
0
,

 
 
4
4
7
,

 
 
8
,

 
 
3
6
0
,

 
 
2
2
,

 
 
6
,

 
 
3
6
0
,

 
 
4
,

 
 
2
2
2
,

 
 
4
2
5
,

 
 
6
,

 
 
4
8
,

 
 
9
,

 
 
2
2
2
,

 
 
2
0
,

 
 
3
6
0
,

 
 
3
9
,

 
 
1
3
7
7
,

 
 
1
3
5
,

 
 
2
0
,

 
 
4
7
7
]
,

 
[
2
9
,
 
7
,
 
7
0
5
,
 
2
,
 
4
7
1
,
 
8
,
 
8
9
,
 
2
7
,
 
7
4
3
,
 
2
9
,
 
5
8
3
,
 
6
,
 
7
7
3
,
 
3
7
,
 
1
2
,
 
2
4
1
]
,

 
[
2
0
,

 
 
5
7
6
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
9
0
,

 
 
4
,

 
 
5
7
6
,

 
 
1
5
,

 
 
2
8
,

 
 
7
5
3
,

 
 
3
9
7
7
,

 
 
2
4
8
,

 
 
2
1
7
,

 
 
2
0
9
8
,

 
 
5
,

 
 
5
3
0
,

 
 
2
1
7
,

 
 
8
,

 
 
5
9
2
9
,

 
 
2
,

 
 
1
,

 
 
9
1
4
2
,

 
 
3
,

 
 
2
8
,

 
 
5
,

 
 
4
0
,

 
 
4
1
0
,

 
 
1
8
,

 
 
3
7
1
1
,

 
 
2
,

 
 
3
9
8
,

 
 
3
1
6
0
,

 
 
5
,

 
 
5
7
6
,

 
 
2
1
7
,

 
 
1
9
7
,

 
 
1
2
5
3
,

 
 
1
8
,

 
 
7
0
1
,

 
 
7
7
,

 
 
5
5
9
,

 
 
2
,

 
 
2
1
3
,

 
 
4
1
0
,

 
 
2
2
,

 
 
5
1
,

 
 
1
9
,

 
 
1
3
7
5
,

 
 
4
,

 
 
5
2
9
,

 
 
1
1
2
3
,

 
 
5
8
7
,

 
 
4
7
,

 
 
9
,

 
 
1
6
8
8
,

 
 
9
,

 
 
1
,

 
 
1
0
7
,

 
 
8
7
,

 
 
1
6
,

 
 
1
8
8
,

 
 
5
,

 
 
5
1
,

 
 
1
9
,

 
 
7
1
3
,

 
 
2
6
4
1
,

 
 
1
5
1
,

 
 
9
,

 
 
5
8
7
,

 
 
2
4
,

 
 
3
3
9
,

 
 
1
,

 
 
1
0
8
8
,

 
 
1
0
7
,

 
 
4
2
,

 
 
1
4
,

 
 
3
5
1
,

 
 
5
7
,

 
 
1
8
8
,

 
 
6
9
,

 
 
1
1
,

 
 
5
5
7
,

 
 
1
3
,

 
 
4
2
,

 
 
1
4
,

 
 
2
9
8
4
,

 
 
3
5
1
,

 
 
2
2
,

 
 
1
3
,

 
 
1
0
7
,

 
 
2
1
5
7
,

 
 
2
,

 
 
6
7
1
,

 
 
9
6
,

 
 
1
5
1
,

 
 
9
2
,

 
 
1
1
2
3
,

 
 
5
8
7
,

 
 
5
0
,

 
 
5
7
6
,

 
 
8
8
,

 
 
2
,

 
 
1
,

 
 
5
2
4
0
,

 
 
1
7
5
5
,

 
 
1
2
7
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
]
,

 
[
6
8
1
,

 
 
5
0
,

 
 
1
7
1
,

 
 
3
1
0
,

 
 
1
4
,

 
 
4
7
0
,

 
 
1
1
9
5
3
,

 
 
4
6
4
,

 
 
2
,

 
 
1
6
6
3
5
,

 
 
8
3
,

 
 
2
0
8
,

 
 
2
6
8
,

 
 
2
,

 
 
1
4
7
,

 
 
5
1
6
,

 
 
7
,

 
 
4
5
,

 
 
3
9
8
,

 
 
1
1
,

 
 
1
2
7
,

 
 
1
2
7
,

 
 
1
7
,

 
 
9
,

 
 
5
6
6
7
,

 
 
1
8
,

 
 
3
8
1
,

 
 
4
1
3
,

 
 
1
8
2
5
]
,

 
[
1
2
8
4
3
,
 
7
1
5
,
 
3
6
1
,
 
3
6
4
5
,
 
1
0
6
5
6
1
,
 
2
1
5
2
,
 
7
1
5
,
 
3
6
1
,
 
3
6
4
5
,
 
1
0
,
 
1
0
6
5
6
1
,
 
5
0
9
]
,

 
[
4
,
 
7
0
4
3
,
 
1
2
,
 
6
,
 
6
,
 
1
8
,
 
4
,
 
9
8
,
 
2
2
2
]
,

 
[
4
6
3
,

 
 
6
4
,

 
 
1
1
,

 
 
8
,

 
 
1
5
5
9
,

 
 
3
3
4
7
,

 
 
1
2
,

 
 
6
4
8
,

 
 
8
9
2
,

 
 
5
,

 
 
5
9
2
,

 
 
3
3
,

 
 
1
3
7
2
,

 
 
1
0
2
2
,

 
 
1
5
,

 
 
4
8
8
,

 
 
1
2
9
5
6
,

 
 
1
5
,

 
 
4
,

 
 
3
7
4
6
,

 
 
2
5
1
4
7
,

 
 
4
5
5
3
9
,

 
 
4
2
3
6
1
,

 
 
1
7
7
3
,

 
 
3
2
1
7
4
,

 
 
1
2
9
5
6
,

 
 
6
9
8
1
8
,

 
 
3
9
6
9
0
,

 
 
1
1
7
3
,

 
 
7
1
4
,

 
 
4
3
8
3
,

 
 
5
0
1
,

 
 
2
7
,

 
 
2
3
2
9
,

 
 
3
,

 
 
1
2
5
0
7
,

 
 
1
1
5
6
4
,

 
 
4
5
3
3
,

 
 
1
7
3
7
,

 
 
4
5
6
,

 
 
1
,

 
 
1
3
9
1
1
,

 
 
4
1
3
7
,

 
 
1
0
,

 
 
5
2
6
5
,

 
 
5
4
3
2
6
,

 
 
8
1
4
,

 
 
3
5
3
8
6
,

 
 
3
4
6
,

 
 
4
6
9
8
,

 
 
5
,

 
 
1
2
5
0
7
,

 
 
4
,

 
 
2
0
0
,

 
 
2
2
4
0
,

 
 
1
9
6
4
,

 
 
8
4
2
,

 
 
6
4
,

 
 
2
5
,

 
 
3
1
2
,

 
 
1
2
9
5
6
,

 
 
2
2
6
6
,

 
 
4
0
6
,

 
 
2
9
1
,

 
 
6
4
,

 
 
2
5
,

 
 
3
3
,

 
 
3
1
2
,

 
 
6
0
7
7
8
,

 
 
3
9
6
9
1
,

 
 
7
5
9
7
,

 
 
1
7
7
3
,

 
 
6
4
,

 
 
8
2
,

 
 
6
3
8
,

 
 
4
0
9
,

 
 
1
3
9
1
1
,

 
 
2
7
6
8
3
,

 
 
3
9
6
9
0
,

 
 
2
5
,

 
 
1
,

 
 
1
1
5
4
,

 
 
3
9
6
9
1
,

 
 
1
6
9
,

 
 
6
4
]
,

 
[
4
1
3
,

 
 
1
8
2
5
,

 
 
6
0
7
7
9
,

 
 
2
6
4
5
,

 
 
1
3
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
,

 
 
8
3
6
0
7
,

 
 
4
1
8
6
,

 
 
2
1
,

 
 
7
2
1
,

 
 
2
4
,

 
 
2
8
7
1
,

 
 
3
0
5
,

 
 
9
,

 
 
5
7
9
,

 
 
2
,

 
 
1
1
6
0
,

 
 
8
1
0
,

 
 
3
,

 
 
1
,

 
 
1
5
8
7
,

 
 
2
,

 
 
2
3
4
8
,

 
 
1
8
0
9
,

 
 
1
0
7
1
9
,

 
 
3
3
,

 
 
1
,

 
 
1
6
0
6
4
3
,

 
 
6
0
,

 
 
1
8
0
9
,

 
 
1
3
4
4
,

 
 
7
5
2
,

 
 
5
4
1
5
,

 
 
3
5
,

 
 
4
7
8
7
,

 
 
4
0
1
0
,

 
 
1
0
,

 
 
1
7
7
5
7
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
7
9
6
,

 
 
4
1
3
,

 
 
2
,

 
 
1
8
3
7
5
,

 
 
1
,

 
 
6
0
9
0
,

 
 
5
,

 
 
4
8
6
,

 
 
1
7
7
5
7
,

 
 
1
7
,

 
 
2
7
,

 
 
2
9
7
8
,

 
 
2
2
1
1
,

 
 
2
,

 
 
7
2
1
,

 
 
3
8
2
,

 
 
3
,

 
 
2
7
,

 
 
2
9
7
8
,

 
 
5
4
,

 
 
1
1
7
4
2
,

 
 
2
1
,

 
 
1
,

 
 
3
0
1
6
,

 
 
1
5
,

 
 
5
4
3
2
7
,

 
 
1
,

 
 
8
4
1
,

 
 
7
5
]
,

 
[
4
3
9
,
 
4
6
,
 
4
,
 
1
8
6
4
,
 
5
5
6
,
 
9
6
7
]
,

 
[
1
1
3
,

 
 
1
4
0
3
,

 
 
2
2
3
7
,

 
 
7
,

 
 
4
9
,

 
 
1
8
7
,

 
 
1
8
3
,

 
 
3
,

 
 
2
0
,

 
 
1
5
9
9
,

 
 
5
4
,

 
 
6
6
8
,

 
 
5
4
3
3
,

 
 
5
,

 
 
4
9
2
9
,

 
 
2
4
5
2
,

 
 
1
3
5
,

 
 
1
0
2
3
1
,

 
 
3
3
6
7
4
,

 
 
1
2
5
5
,

 
 
1
1
3
,

 
 
2
4
0
9
,

 
 
8
7
,

 
 
1
3
6
6
,

 
 
2
,

 
 
6
,

 
 
1
4
4
,

 
 
6
,

 
 
3
6
4
,

 
 
2
,

 
 
7
9
,

 
 
1
5
0
8
,

 
 
4
2
8
,

 
 
4
7
0
,

 
 
8
3
,

 
 
5
,

 
 
3
3
6
7
4
,

 
 
4
1
1
8
,

 
 
2
0
,

 
 
4
5
4
4
,

 
 
7
9
,

 
 
5
1
5
,

 
 
2
4
,

 
 
1
4
8
,

 
 
1
,

 
 
2
7
9
]
,

 
[
1
8
,

 
 
5
1
,

 
 
1
,

 
 
1
0
6
5
6
2
,

 
 
1
8
,

 
 
5
1
,

 
 
1
,

 
 
1
0
6
5
6
2
,

 
 
1
,

 
 
1
3
9
,

 
 
3
2
1
7
5
,

 
 
1
7
,

 
 
1
0
,

 
 
6
9
8
1
,

 
 
4
2
,

 
 
1
6
3
7
,

 
 
3
3
2
,

 
 
3
,

 
 
1
3
]
,

 
[
1
,

 
 
1
3
8
,

 
 
3
,

 
 
8
0
,

 
 
4
1
,

 
 
1
1
4
,

 
 
8
6
,

 
 
1
3
9
1
2
,

 
 
5
5
1
0
,

 
 
2
1
,

 
 
4
6
2
7
,

 
 
8
2
5
5
,

 
 
8
,

 
 
1
0
2
,

 
 
2
0
2
5
,

 
 
8
6
8
5
,

 
 
1
8
,

 
 
6
,

 
 
3
7
3
7
,

 
 
5
,

 
 
6
0
,

 
 
3
4
1
9
,

 
 
1
6
0
7
,

 
 
1
0
,

 
 
8
6
0
9
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
1
3
,

 
 
3
9
7
,

 
 
1
2
8
,

 
 
4
6
9
,

 
 
5
4
3
,

 
 
1
4
4
,

 
 
1
,

 
 
1
6
4
8
,

 
 
1
2
9
2
,

 
 
2
1
4
3
,

 
 
1
1
2
,

 
 
2
5
4
7
,

 
 
9
,

 
 
6
1
,

 
 
2
1
3
4
,

 
 
9
9
,

 
 
5
4
3
2
8
,

 
 
4
5
5
4
0
,

 
 
1
3
9
1
2
,

 
 
2
3
9
4
,

 
 
5
5
1
0
,

 
 
1
0
,

 
 
1
,

 
 
8
9
8
,

 
 
2
7
4
,

 
 
3
,

 
 
1
,

 
 
3
4
3
1
,

 
 
1
0
5
6
,

 
 
1
,

 
 
2
3
,

 
 
6
9
5
,

 
 
1
2
,

 
 
1
,

 
 
1
0
3
1
,

 
 
6
2
7
9
,

 
 
1
6
0
7
,

 
 
2
2
,

 
 
1
5
6
,

 
 
2
1
1
4
,

 
 
1
2
6
,

 
 
7
7
,

 
 
3
8
6
,

 
 
9
,

 
 
1
,

 
 
3
1
4
6
,

 
 
3
,

 
 
3
5
5
,

 
 
1
3
9
1
2
,

 
 
4
5
5
4
0
,

 
 
5
5
1
0
,

 
 
1
0
,

 
 
9
,

 
 
4
9
4
,

 
 
1
6
0
7
,

 
 
1
9
4
9
,

 
 
1
0
,

 
 
8
6
8
5
,

 
 
1
4
,

 
 
9
,

 
 
1
,

 
 
1
6
0
7
,

 
 
5
3
8
,

 
 
1
1
,

 
 
2
4
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
2
,

 
 
1
9
,

 
 
1
1
1
,

 
 
5
5
1
0
,

 
 
7
,

 
 
8
1
,

 
 
3
4
3
,

 
 
3
0
5
,

 
 
2
,

 
 
1
9
,

 
 
5
7
,

 
 
3
1
5
,

 
 
1
0
,

 
 
8
6
8
5
,

 
 
2
3
8
,

 
 
7
,

 
 
2
4
,

 
 
4
,

 
 
6
1
0
,

 
 
1
2
6
4
,

 
 
5
,

 
 
7
,

 
 
3
9
,

 
 
3
7
3
,

 
 
6
,

 
 
9
,

 
 
5
3
,

 
 
5
,

 
 
1
7
5
,

 
 
1
1
8
5
1
,

 
 
1
0
,

 
 
2
4
3
3
,

 
 
2
1
5
8
,

 
 
9
9
,

 
 
4
5
5
4
0
,

 
 
1
3
9
1
2
,

 
 
5
5
1
0
,

 
 
1
4
5
5
,

 
 
2
,

 
 
8
6
8
5
,

 
 
5
,

 
 
4
4
,

 
 
4
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
6
8
7
9
,

 
 
2
5
,

 
 
4
0
2
6
,

 
 
1
,

 
 
1
7
9
,

 
 
6
4
,

 
 
8
,

 
 
2
9
2
3
,

 
 
2
,

 
 
1
1
7
,

 
 
1
,

 
 
3
0
8
]
,

 
[
3
8
,

 
 
7
9
0
,

 
 
4
9
0
,

 
 
4
0
8
,

 
 
5
3
,

 
 
2
1
1
,

 
 
4
8
,

 
 
2
2
4
4
,

 
 
2
7
9
0
,

 
 
6
2
9
,

 
 
1
,

 
 
6
7
6
,

 
 
2
3
1
9
,

 
 
7
,

 
 
4
3
,

 
 
1
1
7
,

 
 
5
3
,

 
 
1
9
,

 
 
1
5
8
,

 
 
5
6
,

 
 
3
4
5
,

 
 
4
,

 
 
3
3
6
,

 
 
1
2
,

 
 
2
9
,

 
 
1
3
7
4
8
,

 
 
3
6
,

 
 
9
,

 
 
5
3
,

 
 
3
9
,

 
 
4
6
0
,

 
 
1
,

 
 
1
1
5
,

 
 
4
0
7
,

 
 
1
0
,

 
 
6
,

 
 
1
8
4
,

 
 
6
6
,

 
 
3
9
2
,

 
 
9
,

 
 
1
,

 
 
4
1
8
,

 
 
5
6
,

 
 
1
1
0
1
,

 
 
4
7
9
9
,

 
 
6
7
3
,

 
 
3
6
1
3
,

 
 
6
9
8
0
,

 
 
1
0
,

 
 
3
6
,

 
 
9
,

 
 
5
3
,

 
 
3
9
,

 
 
2
4
6
,

 
 
1
,

 
 
2
9
,

 
 
1
7
9
,

 
 
2
5
,

 
 
2
3
1
,

 
 
3
4
,

 
 
1
1
,

 
 
5
1
9
,

 
 
3
3
4
0
,

 
 
1
1
,

 
 
1
8
1
,

 
 
1
2
6
,

 
 
3
5
4
,

 
 
4
6
]
,

 
[
4
3
9
,
 
4
6
,
 
1
,
 
2
2
1
,
 
3
,
 
1
4
0
4
6
]
,

 
[
4
9
,

 
 
5
3
9
9
,

 
 
3
2
,

 
 
7
,

 
 
3
3
2
,

 
 
3
6
7
,

 
 
3
1
7
,

 
 
4
,

 
 
2
3
5
,

 
 
1
8
6
0
,

 
 
1
5
5
,

 
 
4
,

 
 
1
0
4
7
,

 
 
4
8
6
,

 
 
8
,

 
 
1
4
,

 
 
3
6
9
,

 
 
2
0
4
,

 
 
1
5
,

 
 
1
,

 
 
4
3
2
,

 
 
2
9
,

 
 
1
7
,

 
 
1
2
2
8
,

 
 
3
2
,

 
 
1
1
3
,

 
 
1
0
4
2
4
,

 
 
1
2
,

 
 
3
1
1
,

 
 
1
,

 
 
1
4
8
0
,

 
 
9
7
4
6
,

 
 
2
7
6
8
4
,

 
 
8
3
6
0
8
,

 
 
2
4
,

 
 
1
4
,

 
 
1
3
3
,

 
 
1
7
,

 
 
1
1
,

 
 
2
4
,

 
 
2
9
1
,

 
 
1
5
5
,

 
 
1
8
7
2
9
,

 
 
2
8
,

 
 
4
8
6
,

 
 
3
,

 
 
1
,

 
 
3
0
3
,

 
 
9
4
1
2
,

 
 
1
4
7
6
,

 
 
4
3
0
,

 
 
1
0
5
3
,

 
 
9
,

 
 
8
6
,

 
 
1
4
,

 
 
1
3
3
,

 
 
6
9
,

 
 
5
1
,

 
 
1
1
2
0
6
,

 
 
1
5
5
,

 
 
1
2
8
,

 
 
8
6
0
6
,

 
 
2
5
,

 
 
1
8
,

 
 
3
,

 
 
4
,

 
 
8
3
6
0
9
,

 
 
1
1
4
8
,

 
 
4
,

 
 
1
0
4
7
,

 
 
4
8
6
,

 
 
4
0
1
9
,

 
 
8
,

 
 
2
3
1
7
,

 
 
4
3
6
7
,

 
 
9
,

 
 
1
,

 
 
5
3
9
,

 
 
2
9
1
7
,

 
 
9
,

 
 
1
,

 
 
1
2
3
,

 
 
8
,

 
 
3
,

 
 
5
6
4
,

 
 
9
1
8
,

 
 
5
,

 
 
5
6
4
,

 
 
1
3
1
0
,

 
 
1
2
3
4
,

 
 
1
5
,

 
 
4
,

 
 
6
5
4
,

 
 
1
9
3
,

 
 
1
0
4
2
4
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
7
3
,

 
 
2
,

 
 
9
5
,

 
 
1
2
,

 
 
7
0
3
,

 
 
7
3
,

 
 
1
,

 
 
5
6
4
8
,

 
 
4
5
0
9
,

 
 
4
5
5
4
1
]
,

 
[
6
0
,

 
 
3
,

 
 
1
,

 
 
1
0
6
,

 
 
4
4
0
,

 
 
1
7
,

 
 
4
1
0
4
,

 
 
1
0
9
7
2
,

 
 
6
1
5
3
,

 
 
4
8
4
,

 
 
2
8
7
4
,

 
 
4
8
4
,

 
 
2
7
,

 
 
1
9
2
2
,

 
 
2
1
,

 
 
4
2
3
6
2
,

 
 
1
2
8
3
,

 
 
3
,

 
 
1
,

 
 
2
5
7
,

 
 
9
3
5
,

 
 
1
0
,

 
 
7
3
9
0
,

 
 
1
5
2
7
0
,

 
 
5
,

 
 
1
9
1
,

 
 
4
9
0
4
,

 
 
4
,

 
 
1
0
0
4
,

 
 
1
1
9
0
,

 
 
1
9
2
2
,

 
 
2
7
,

 
 
2
3
,

 
 
1
0
,

 
 
1
,

 
 
2
2
5
9
,

 
 
4
8
6
5
,

 
 
8
0
3
5
,

 
 
1
,

 
 
1
7
0
9
,

 
 
3
1
,

 
 
1
,

 
 
1
6
0
7
,

 
 
4
2
3
6
2
,

 
 
4
9
7
4
,

 
 
7
3
,

 
 
1
0
,

 
 
1
9
8
1
8
,

 
 
2
0
8
8
,

 
 
4
8
4
,

 
 
2
2
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
4
1
1
,

 
 
1
4
1
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
6
,

 
 
1
9
,

 
 
4
,

 
 
2
4
9
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
7
,

 
 
3
9
,

 
 
1
3
6
,

 
 
6
0
3
,

 
 
5
8
,

 
 
1
0
6
,

 
 
3
1
,

 
 
8
7
0
,

 
 
2
6
1
,

 
 
2
8
2
1
,

 
 
5
,

 
 
4
4
3
4
,

 
 
5
8
0
,

 
 
8
,

 
 
8
7
0
,

 
 
5
,

 
 
7
7
5
,

 
 
5
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
8
7
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
1
,

 
 
6
9
0
,

 
 
3
,

 
 
1
7
2
,

 
 
3
0
0
,

 
 
2
8
,

 
 
8
,

 
 
2
7
,

 
 
3
8
4
,

 
 
1
2
,

 
 
4
7
9
,

 
 
5
,

 
 
3
8
,

 
 
8
,

 
 
6
7
0
,

 
 
8
,

 
 
1
6
6
]
,

 
[
1
,

 
 
2
1
2
,

 
 
8
,

 
 
1
,

 
 
2
9
7
3
,

 
 
3
,

 
 
4
,

 
 
3
7
0
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
6
0
6
4
4
,

 
 
1
5
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
1
,

 
 
3
9
9
,

 
 
2
9
7
3
,

 
 
3
,

 
 
1
,

 
 
3
7
0
,

 
 
8
,

 
 
2
,

 
 
1
6
,

 
 
3
3
2
4
]
,

 
[
4
2
7
7
,

 
 
4
2
7
7
,

 
 
4
2
7
7
,

 
 
4
9
6
1
,

 
 
2
3
9
4
,

 
 
7
,

 
 
2
7
6
8
5
,

 
 
4
6
7
,

 
 
1
,

 
 
1
6
0
6
4
5
,

 
 
3
4
1
3
,

 
 
1
6
0
6
4
6
,

 
 
6
7
8
0
,

 
 
6
0
7
8
0
,

 
 
1
0
6
5
6
3
,

 
 
1
3
3
3
2
,

 
 
3
3
,

 
 
1
,

 
 
4
6
9
9
,

 
 
3
3
1
3
,

 
 
4
8
2
,

 
 
2
3
9
4
,

 
 
8
3
6
1
0
]
,

 
[
7
,
 
6
8
7
,
 
9
,
 
2
7
3
,
 
5
,
 
7
,
 
1
7
3
,
 
4
,
 
1
9
3
,
 
6
3
,
 
1
9
3
,
 
4
5
2
,
 
3
2
,
 
1
,
 
1
0
9
,
 
1
4
4
4
]
,

 
[
4
5
5
,

 
 
2
7
2
0
,

 
 
9
8
,

 
 
2
,

 
 
6
3
,

 
 
6
,

 
 
3
1
5
,

 
 
1
6
4
,

 
 
1
4
3
,

 
 
7
,

 
 
2
4
,

 
 
1
5
,

 
 
4
,

 
 
4
4
,

 
 
3
1
9
,

 
 
1
7
7
5
8
,

 
 
1
1
1
5
,

 
 
3
5
6
,

 
 
2
6
,

 
 
1
4
,

 
 
4
,

 
 
3
8
1
,

 
 
3
5
6
,

 
 
6
9
,

 
 
3
,

 
 
1
,

 
 
1
4
9
,

 
 
4
0
2
,

 
 
3
,

 
 
9
3
4
,

 
 
1
0
6
,

 
 
5
,

 
 
4
7
,

 
 
5
8
,

 
 
1
2
0
,

 
 
1
2
7
,

 
 
3
1
,

 
 
1
,

 
 
4
0
2
,

 
 
3
,

 
 
9
3
4
,

 
 
9
,

 
 
8
,

 
 
3
5
5
7
,

 
 
1
5
,

 
 
1
,

 
 
6
3
8
,

 
 
5
6
3
1
,

 
 
3
8
,

 
 
4
3
,

 
 
6
,

 
 
4
8
,

 
 
3
7
,

 
 
2
,

 
 
3
4
,

 
 
6
4
,

 
 
7
,

 
 
3
9
,

 
 
3
5
7
,

 
 
1
6
1
,

 
 
1
,

 
 
8
6
0
,

 
 
2
2
,

 
 
6
,

 
 
1
8
4
,

 
 
1
4
4
0
,

 
 
9
,

 
 
3
7
7
]
,

 
[
5
,

 
 
2
2
,

 
 
5
2
,

 
 
8
6
,

 
 
4
,

 
 
2
6
7
3
,

 
 
1
9
8
9
,

 
 
2
9
2
,

 
 
7
,

 
 
7
5
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
4
9
,

 
 
2
1
,

 
 
1
5
4
,

 
 
2
6
,

 
 
1
4
4
,

 
 
5
2
,

 
 
1
9
5
,

 
 
2
,

 
 
2
7
8
,

 
 
1
,

 
 
6
6
2
,

 
 
3
,

 
 
9
1
,

 
 
2
7
,

 
 
4
1
8
,

 
 
1
1
8
,

 
 
2
,

 
 
6
8
,

 
 
8
1
0
,

 
 
7
,

 
 
1
9
,

 
 
2
7
,

 
 
2
6
7
,

 
 
2
1
,

 
 
1
5
4
,

 
 
5
0
,

 
 
1
5
6
,

 
 
3
8
,

 
 
1
9
9
8
,

 
 
3
,

 
 
6
8
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
0
2
9
,

 
 
3
,

 
 
1
3
,

 
 
7
2
,

 
 
4
,

 
 
6
1
1
5
,

 
 
1
5
,

 
 
4
,

 
 
1
0
2
,

 
 
1
2
0
8
,

 
 
7
8
6
,

 
 
1
3
8
,

 
 
1
3
7
0
,

 
 
5
,

 
 
7
,

 
 
4
3
,

 
 
1
9
9
,

 
 
1
2
8
4
,

 
 
4
,

 
 
8
7
0
,

 
 
2
1
4
,

 
 
3
1
,

 
 
4
,

 
 
1
0
7
]
,

 
[
8
,

 
 
1
5
6
6
,

 
 
1
2
1
,

 
 
1
9
1
,

 
 
2
,

 
 
5
2
,

 
 
8
,

 
 
1
7
6
0
,

 
 
1
0
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
4
6
,

 
 
2
,

 
 
1
5
4
,

 
 
1
5
,

 
 
6
8
,

 
 
4
6
,

 
 
2
9
]
,

 
[
5
1
,
 
1
4
7
,
 
2
8
4
,
 
2
,
 
3
7
,
 
2
9
4
,
 
1
7
8
2
,
 
1
8
7
2
,
 
2
7
9
7
,
 
8
5
3
,
 
1
0
0
1
,
 
2
1
6
]
,

 
[
1
0
2
8
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
2
8
,

 
 
6
0
2
6
,

 
 
1
2
8
,

 
 
9
5
,

 
 
1
2
,

 
 
2
6
1
6
,

 
 
1
6
8
1
,

 
 
1
,

 
 
9
0
7
,

 
 
1
3
8
7
,

 
 
4
4
,

 
 
2
1
2
,

 
 
3
5
2
,

 
 
1
5
2
,

 
 
1
,

 
 
4
8
7
,

 
 
1
2
5
,

 
 
6
,

 
 
2
9
1
,

 
 
1
,

 
 
3
2
8
7
,

 
 
8
,

 
 
9
,

 
 
1
0
,

 
 
5
2
3
,

 
 
8
2
9
8
,

 
 
6
3
1
,

 
 
4
0
,

 
 
1
,

 
 
4
7
7
8
,

 
 
1
8
,

 
 
7
5
9
8
,

 
 
1
1
4
5
,

 
 
4
2
3
6
3
,

 
 
2
2
,

 
 
6
,

 
 
7
0
,

 
 
2
0
,

 
 
1
1
0
,

 
 
3
1
5
,

 
 
6
8
8
0
,

 
 
1
3
7
,

 
 
5
7
,

 
 
9
7
0
,

 
 
2
2
9
7
,

 
 
1
2
,

 
 
4
,

 
 
8
2
9
8
,

 
 
5
4
1
6
,

 
 
2
,

 
 
1
5
3
8
,

 
 
7
3
,

 
 
4
0
,

 
 
1
,

 
 
9
6
9
0
,

 
 
1
5
,

 
 
1
,

 
 
4
3
2
,

 
 
2
9
,

 
 
1
8
0
6
4
,

 
 
4
8
,

 
 
5
3
,

 
 
4
7
6
,

 
 
4
0
,

 
 
1
9
,

 
 
3
0
5
,

 
 
2
,

 
 
3
4
,

 
 
2
3
7
,

 
 
3
1
9
4
,

 
 
3
6
,

 
 
1
3
0
,

 
 
2
1
0
0
,

 
 
3
6
,

 
 
2
6
0
,

 
 
1
7
7
5
9
,

 
 
4
5
2
,

 
 
3
1
1
1
,

 
 
6
1
6
]
,

 
[
1
1
7
8
,

 
 
2
5
9
4
1
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
1
4
3
,

 
 
2
,

 
 
3
7
3
,

 
 
7
5
,

 
 
2
,

 
 
3
6
2
,

 
 
1
0
,

 
 
4
,

 
 
1
3
9
7
,

 
 
4
9
,

 
 
6
9
,

 
 
9
,

 
 
3
3
4
,

 
 
4
5
9
,

 
 
8
,

 
 
9
1
,

 
 
1
3
3
,

 
 
1
2
,

 
 
1
8
0
6
5
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
7
6
,

 
 
6
,

 
 
3
9
,

 
 
4
6
,

 
 
2
,

 
 
7
5
,

 
 
4
8
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
,

 
 
2
7
7
3
,

 
 
1
0
6
7
,

 
 
9
3
,

 
 
1
,

 
 
2
2
2
,

 
 
6
2
,

 
 
6
,

 
 
2
1
3
]
,

 
[
6
,

 
 
1
9
,

 
 
1
1
5
,

 
 
9
8
9
,

 
 
2
6
2
,

 
 
2
3
6
,

 
 
5
,

 
 
1
,

 
 
4
5
4
,

 
 
5
6
7
,

 
 
7
7
7
,

 
 
3
1
,

 
 
1
0
7
,

 
 
1
0
6
5
6
4
,

 
 
5
,

 
 
1
0
7
,

 
 
2
0
2
0
5
,

 
 
8
4
2
3
,

 
 
1
3
,

 
 
4
2
1
,

 
 
1
7
,

 
 
4
,

 
 
7
7
7
,

 
 
3
,

 
 
2
7
,

 
 
2
5
0
3
,

 
 
6
7
6
,

 
 
1
7
,

 
 
2
,

 
 
3
8
5
,

 
 
2
,

 
 
4
4
8
,

 
 
1
5
4
7
3
,

 
 
3
5
3
8
7
,

 
 
3
3
5
,

 
 
3
,

 
 
1
9
1
,

 
 
6
1
4
,

 
 
4
9
8
2
,

 
 
1
5
,

 
 
1
,

 
 
1
6
1
4
2
,

 
 
5
2
6
8
,

 
 
2
9
,

 
 
7
,

 
 
2
6
5
,

 
 
1
,

 
 
1
6
1
4
2
,

 
 
5
2
6
8
,

 
 
4
,

 
 
1
3
1
9
,

 
 
1
3
3
,

 
 
1
0
,

 
 
1
,

 
 
4
4
1
9
,

 
 
3
,

 
 
1
,

 
 
4
5
6
6
,

 
 
6
0
4
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
9
4
5
7
,

 
 
3
9
1
,

 
 
3
2
,

 
 
1
5
4
,

 
 
1
,

 
 
1
6
1
4
2
,

 
 
5
2
6
8
,

 
 
4
,

 
 
1
2
9
0
,

 
 
1
4
0
4
7
,

 
 
9
2
9
,

 
 
1
0
,

 
 
6
8
,

 
 
6
0
4
6
,

 
 
9
2
,

 
 
5
2
9
,

 
 
1
4
0
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
2
3
,

 
 
3
3
,

 
 
9
4
7
,

 
 
4
1
4
,

 
 
1
0
6
5
6
4
,

 
 
5
,

 
 
9
4
7
,

 
 
4
1
4
,

 
 
2
0
2
0
5
,

 
 
5
,

 
 
3
6
8
,

 
 
1
2
5
,

 
 
4
8
1
]
,

 
[
2
1
8
1
,

 
 
1
,

 
 
1
7
1
3
,

 
 
3
9
,

 
 
6
0
,

 
 
4
7
,

 
 
2
0
2
,

 
 
1
3
,

 
 
5
,

 
 
2
5
6
,

 
 
1
,

 
 
2
2
6
3
3
,

 
 
1
1
8
5
2
,

 
 
3
1
,

 
 
1
,

 
 
1
0
9
7
3
,

 
 
5
4
,

 
 
8
,

 
 
1
4
,

 
 
2
2
3
,

 
 
3
,

 
 
5
,

 
 
1
5
4
5
,

 
 
1
1
,

 
 
2
1
,

 
 
1
3
,

 
 
1
0
5
,

 
 
5
,

 
 
2
0
2
,

 
 
6
8
,

 
 
5
2
8
6
,

 
 
3
,

 
 
2
7
5
7
,

 
 
5
5
,

 
 
2
5
4
,

 
 
4
9
,

 
 
2
6
5
,

 
 
1
4
2
4
,

 
 
3
7
,

 
 
6
0
7
8
1
,

 
 
2
6
7
5
2
,

 
 
6
9
8
1
9
,

 
 
6
0
7
8
2
,

 
 
2
4
,

 
 
5
4
3
2
9
,

 
 
3
,

 
 
1
,

 
 
7
0
8
9
,

 
 
3
1
,

 
 
1
3
9
9
,

 
 
1
2
4
8
,

 
 
2
,

 
 
8
5
3
,

 
 
9
5
3
,

 
 
1
1
9
8
,

 
 
7
7
2
,

 
 
1
,

 
 
4
2
3
6
4
,

 
 
3
,

 
 
1
6
5
8
,

 
 
6
0
7
8
3
,

 
 
8
,

 
 
1
3
4
5
8
]
,

 
[
1
1
4
4
,

 
 
6
,

 
 
5
2
1
,

 
 
1
2
8
,

 
 
1
1
0
5
7
,

 
 
3
3
0
,

 
 
3
0
,

 
 
8
7
6
,

 
 
8
0
,

 
 
6
,

 
 
7
0
5
,

 
 
2
,

 
 
3
0
2
3
,

 
 
7
,

 
 
2
5
8
,

 
 
7
3
,

 
 
3
0
,

 
 
3
1
8
0
,

 
 
3
0
,

 
 
5
7
5
,

 
 
8
,

 
 
1
0
2
,

 
 
1
0
2
,

 
 
7
5
0
,

 
 
1
,

 
 
6
4
0
4
,

 
 
8
6
,

 
 
4
1
9
6
,

 
 
5
1
,

 
 
5
6
,

 
 
1
4
,

 
 
1
9
,

 
 
5
7
,

 
 
3
5
3
9
,

 
 
7
,

 
 
1
1
7
6
,

 
 
1
,

 
 
1
0
9
0
]
,

 
[
7
,

 
 
5
9
,

 
 
3
5
6
,

 
 
3
4
6
,

 
 
9
,

 
 
7
7
4
0
,

 
 
2
1
,

 
 
1
1
3
,

 
 
2
3
0
,

 
 
5
7
9
,

 
 
2
,

 
 
2
0
,

 
 
1
7
0
,

 
 
4
1
3
,

 
 
4
0
7
3
,

 
 
1
8
0
,

 
 
1
5
2
7
1
,

 
 
1
2
6
2
2
,

 
 
3
9
6
9
2
]
,

 
[
5
,
 
3
9
8
,
 
6
8
,
 
1
4
0
]
,

 
[
4
5
5
4
2
,

 
 
1
0
,

 
 
4
3
6
,

 
 
1
3
7
,

 
 
5
7
,

 
 
6
2
6
,

 
 
1
0
,

 
 
4
,

 
 
2
5
0
,

 
 
1
3
8
,

 
 
1
4
8
,

 
 
1
5
,

 
 
4
6
,

 
 
1
4
8
8
8
,

 
 
4
0
4
9
,

 
 
1
4
8
,

 
 
3
8
5
,

 
 
1
,

 
 
1
4
8
8
8
,

 
 
1
0
,

 
 
1
,

 
 
1
1
2
6
,

 
 
8
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
1
7
,

 
 
1
,

 
 
1
4
8
8
8
,

 
 
1
0
,

 
 
1
,

 
 
8
0
2
,

 
 
2
1
,

 
 
6
9
8
2
0
,

 
 
2
0
3
3
,

 
 
9
,

 
 
5
1
,

 
 
7
6
7
,

 
 
5
,

 
 
9
,

 
 
1
3
0
4
,

 
 
1
,

 
 
1
4
8
8
8
,

 
 
1
0
,

 
 
4
9
,

 
 
4
7
,

 
 
2
3
,

 
 
2
4
,

 
 
1
8
0
6
6
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
6
8
,

 
 
6
2
7
,

 
 
8
,

 
 
3
3
,

 
 
4
0
,

 
 
8
7
0
,

 
 
2
6
,

 
 
1
0
,

 
 
1
,

 
 
4
4
3
,

 
 
3
,

 
 
4
9
1
,

 
 
5
3
6
,

 
 
7
3
,

 
 
1
5
,

 
 
1
,

 
 
5
8
6
,

 
 
1
3
7
,

 
 
2
6
6
4
,

 
 
9
,

 
 
6
0
,

 
 
2
0
0
4
,

 
 
3
,

 
 
1
,

 
 
1
1
2
6
,

 
 
9
2
8
,

 
 
4
1
1
,

 
 
1
,

 
 
1
0
8
0
2
,

 
 
1
6
2
,

 
 
8
0
2
,

 
 
2
,

 
 
1
6
,

 
 
1
6
6
3
,

 
 
8
9
8
0
,

 
 
2
5
,

 
 
2
8
1
,

 
 
5
5
9
6
,

 
 
7
2
,

 
 
1
4
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
1
,

 
 
1
4
8
8
8
,

 
 
1
2
5
2
,

 
 
5
3
9
,

 
 
4
9
,

 
 
1
,

 
 
3
1
4
,

 
 
5
4
0
,

 
 
3
6
,

 
 
7
,

 
 
5
9
,

 
 
2
1
1
,

 
 
5
2
9
1
,

 
 
3
1
0
,

 
 
1
3
8
,

 
 
3
,

 
 
1
3
,

 
 
9
3
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
1
0
0
,

 
 
2
5
9
,

 
 
7
0
,

 
 
5
5
,

 
 
8
7
7
,

 
 
3
5
,

 
 
1
3
,

 
 
1
1
1
,

 
 
1
7
,

 
 
7
4
,

 
 
4
4
7
6
,

 
 
1
3
,

 
 
2
5
8
4
,

 
 
1
3
9
1
3
,

 
 
8
,

 
 
1
7
5
3
,

 
 
3
1
1
1
,

 
 
6
7
5
,

 
 
6
8
4
9
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
6
1
5
4
,

 
 
5
0
,

 
 
1
7
1
,

 
 
9
4
4
,

 
 
1
9
7
6
,

 
 
1
9
8
,

 
 
5
2
3
,

 
 
1
0
0
4
0
,

 
 
2
,

 
 
3
5
1
2
,

 
 
1
9
8
,

 
 
1
7
,

 
 
1
0
,

 
 
1
,

 
 
6
7
2
,

 
 
4
2
,

 
 
1
,

 
 
6
7
2
,

 
 
4
2
,

 
 
1
1
3
,

 
 
6
9
8
2
1
,

 
 
1
4
7
6
,

 
 
9
,

 
 
2
8
,

 
 
9
1
4
3
,

 
 
2
0
0
5
,

 
 
6
1
5
4
,

 
 
8
2
3
,

 
 
1
0
0
4
0
,

 
 
5
,

 
 
1
,

 
 
1
1
4
,

 
 
2
7
0
,

 
 
1
0
,

 
 
4
,

 
 
4
6
5
,

 
 
1
8
,

 
 
6
1
7
9
,

 
 
5
,

 
 
1
4
,

 
 
1
2
8
,

 
 
5
8
,

 
 
8
3
6
1
1
]
,

 
[
6
3
,

 
 
4
0
3
,

 
 
4
2
0
,

 
 
6
4
,

 
 
1
7
6
,

 
 
5
4
3
3
0
,

 
 
2
0
6
6
1
,

 
 
2
4
3
,

 
 
9
0
4
0
,

 
 
4
5
2
,

 
 
2
2
6
3
4
,

 
 
1
6
0
6
4
7
,

 
 
1
6
0
6
4
8
,

 
 
5
1
0
,

 
 
4
5
5
4
3
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
2
6
1
,

 
 
1
2
0
]
,

 
[
2
2
,

 
 
5
2
,

 
 
8
,

 
 
1
,

 
 
5
3
9
,

 
 
4
2
2
8
,

 
 
8
4
,

 
 
1
1
4
,

 
 
3
,

 
 
4
0
,

 
 
7
1
,

 
 
4
,

 
 
8
0
1
,

 
 
3
,

 
 
5
6
2
,

 
 
1
2
,

 
 
1
5
4
,

 
 
2
,

 
 
1
6
,

 
 
1
2
9
,

 
 
1
3
,

 
 
5
,

 
 
4
3
7
,

 
 
3
,

 
 
4
0
,

 
 
5
2
,

 
 
4
2
,

 
 
1
,

 
 
6
6
2
,

 
 
2
,

 
 
1
1
7
,

 
 
2
1
2
5
,

 
 
1
5
,

 
 
6
8
,

 
 
3
4
1
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
9
6
0
,

 
 
4
3
5
,

 
 
6
8
4
,

 
 
1
1
7
0
,

 
 
6
2
,

 
 
5
2
,

 
 
8
7
,

 
 
1
6
,

 
 
6
8
,

 
 
5
7
5
,

 
 
8
,

 
 
1
0
9
7
4
,

 
 
2
1
,

 
 
2
8
,

 
 
5
7
0
,

 
 
1
5
2
7
2
,

 
 
1
1
5
0
,

 
 
3
,

 
 
1
,

 
 
8
3
3
9
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
6
7
1
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
1
1
9
5
4
,

 
 
1
4
5
,

 
 
1
2
1
8
4
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
]
,

 
[
7
5
9
9
,

 
 
2
,

 
 
5
7
0
,

 
 
1
7
8
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
6
,

 
 
5
6
,

 
 
1
8
0
6
7
,

 
 
1
0
7
,

 
 
5
4
3
3
1
,

 
 
7
8
,

 
 
7
7
0
,

 
 
1
8
,

 
 
1
5
4
1
,

 
 
1
,

 
 
2
1
7
,

 
 
1
3
2
7
,

 
 
7
7
0
,

 
 
2
5
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
,

 
 
4
0
5
,

 
 
1
3
5
,

 
 
6
0
,

 
 
7
0
8
,

 
 
3
,

 
 
1
2
8
9
,

 
 
2
,

 
 
1
8
0
6
7
,

 
 
8
6
9
,

 
 
9
8
6
3
,

 
 
1
3
2
7
,

 
 
7
7
0
,

 
 
2
,

 
 
4
6
2
,

 
 
9
8
6
3
,

 
 
4
5
2
1
,

 
 
6
6
5
1
,

 
 
1
2
,

 
 
3
1
1
,

 
 
5
4
6
8
,

 
 
2
,

 
 
1
0
1
,

 
 
2
8
8
,

 
 
4
6
0
,

 
 
1
,

 
 
5
1
9
,

 
 
2
,

 
 
1
,

 
 
1
1
6
0
,

 
 
1
2
,

 
 
1
3
,

 
 
1
9
8
,

 
 
1
,

 
 
4
5
2
1
,

 
 
6
6
5
1
,

 
 
1
4
2
,

 
 
1
7
7
6
0
,

 
 
1
8
,

 
 
1
2
8
,

 
 
4
6
2
,

 
 
9
8
6
3
,

 
 
5
,

 
 
1
6
7
3
,

 
 
8
8
,

 
 
4
5
,

 
 
7
1
1
,

 
 
6
,

 
 
2
,

 
 
4
,

 
 
2
9
,

 
 
9
5
8
,

 
 
3
8
,

 
 
1
,

 
 
3
8
9
5
,

 
 
8
,

 
 
1
2
,

 
 
7
,

 
 
1
3
0
2
,

 
 
2
6
3
,

 
 
9
,

 
 
1
,

 
 
6
3
2
,

 
 
9
3
6
,

 
 
2
1
,

 
 
2
5
3
,

 
 
8
,

 
 
1
0
2
,

 
 
9
8
6
3
,

 
 
5
,

 
 
2
0
0
5
,

 
 
1
3
,

 
 
8
,

 
 
5
4
3
,

 
 
3
8
0
,

 
 
8
0
,

 
 
2
8
1
,

 
 
1
0
7
,

 
 
2
8
,

 
 
4
1
0
,

 
 
1
5
6
,

 
 
1
,

 
 
8
3
,

 
 
5
4
,

 
 
2
8
8
,

 
 
2
7
3
2
,

 
 
1
,

 
 
1
0
8
3
,

 
 
3
,

 
 
2
8
,

 
 
1
0
1
0
,

 
 
5
1
,

 
 
2
8
8
,

 
 
5
9
,

 
 
4
6
6
,

 
 
9
,

 
 
5
1
,

 
 
2
2
9
,

 
 
7
9
,

 
 
1
,

 
 
2
3
,

 
 
6
2
1
,

 
 
4
3
,

 
 
5
1
,

 
 
5
,

 
 
3
,

 
 
1
3
2
,

 
 
1
6
0
6
4
9
,

 
 
8
7
,

 
 
4
1
9
7
,

 
 
1
,

 
 
2
7
7
,

 
 
2
1
,

 
 
1
,

 
 
2
3
,

 
 
1
7
4
,

 
 
9
5
]
,

 
[
1
7
8
,
 
1
9
8
1
9
,
 
1
1
,
 
6
0
5
,
 
5
9
3
,
 
4
8
1
,
 
5
,
 
7
,
 
2
6
3
,
 
2
1
,
 
1
,
 
5
8
7
,
 
3
3
9
,
 
3
2
,
 
8
3
6
1
2
]
,

 
[
4
,

 
 
3
3
6
,

 
 
1
0
,

 
 
1
,

 
 
6
0
2
,

 
 
5
0
,

 
 
5
1
7
,

 
 
1
5
1
,

 
 
2
0
,

 
 
7
7
0
,

 
 
1
5
,

 
 
1
,

 
 
6
7
2
4
,

 
 
6
9
8
0
,

 
 
2
9
,

 
 
2
0
8
,

 
 
4
,

 
 
1
1
3
7
,

 
 
8
,

 
 
5
3
4
,

 
 
2
9
8
,

 
 
1
1
,

 
 
1
2
,

 
 
6
,

 
 
7
,

 
 
2
6
5
,

 
 
2
9
4
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
1
7
3
,

 
 
3
2
]
,

 
[
1
3
7
,

 
 
4
0
8
3
,

 
 
1
,

 
 
1
5
3
2
,

 
 
3
1
,

 
 
1
,

 
 
1
4
0
5
,

 
 
3
2
,

 
 
1
6
5
,

 
 
1
5
7
,

 
 
2
,

 
 
1
3
,

 
 
1
0
2
3
,

 
 
7
9
,

 
 
3
3
9
8
,

 
 
1
4
0
,

 
 
1
5
,

 
 
1
,

 
 
1
4
0
5
,

 
 
3
6
1
,

 
 
2
8
,

 
 
3
6
4
,

 
 
2
,

 
 
1
9
,

 
 
5
7
,

 
 
1
4
1
0
,

 
 
2
1
8
7
,

 
 
2
,

 
 
1
3
4
1
,

 
 
2
2
4
,

 
 
2
6
,

 
 
1
9
,

 
 
2
6
1
1
,

 
 
7
2
2
4
,

 
 
1
0
,

 
 
7
1
8
,

 
 
1
0
9
7
5
,

 
 
3
,

 
 
1
,

 
 
2
9
9
,

 
 
2
5
3
,

 
 
9
8
6
4
,

 
 
1
,

 
 
7
7
7
,

 
 
2
1
0
,

 
 
2
0
2
0
6
,

 
 
5
,

 
 
1
5
3
0
,

 
 
8
3
6
1
3
,

 
 
1
3
7
,

 
 
5
5
5
,

 
 
2
3
9
8
,

 
 
1
5
3
2
,

 
 
5
,

 
 
4
3
6
8
,

 
 
1
,

 
 
1
3
3
0
,

 
 
6
5
7
3
,

 
 
2
5
3
,

 
 
5
,

 
 
1
0
8
6
,

 
 
1
4
8
,

 
 
1
,

 
 
4
4
2
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
5
8
,

 
 
2
6
7
5
3
,

 
 
1
0
,

 
 
2
5
1
,

 
 
7
1
,

 
 
1
4
,

 
 
3
7
1
,

 
 
4
1
,

 
 
3
5
1
,

 
 
2
6
,

 
 
8
,

 
 
1
4
1
6
,

 
 
8
9
,

 
 
4
5
5
4
4
]
,

 
[
7
2
,

 
 
2
8
0
,

 
 
2
2
,

 
 
6
,

 
 
4
5
,

 
 
1
4
,

 
 
4
8
,

 
 
1
,

 
 
5
2
5
,

 
 
2
6
,

 
 
7
,

 
 
3
9
,

 
 
1
4
,

 
 
8
8
9
,

 
 
5
5
,

 
 
1
2
6
3
,

 
 
7
3
4
,

 
 
5
5
,

 
 
2
7
0
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
6
6
4
,

 
 
2
5
,

 
 
8
,

 
 
5
0
2
4
,

 
 
1
0
,

 
 
1
0
6
,

 
 
4
3
,

 
 
5
5
,

 
 
3
,

 
 
2
0
,

 
 
4
7
0
0
,

 
 
1
6
,

 
 
4
8
2
,

 
 
2
1
,

 
 
2
7
,

 
 
6
5
7
,

 
 
2
6
4
4
,

 
 
2
5
5
2
,

 
 
7
,

 
 
4
6
6
,

 
 
9
6
,

 
 
4
6
2
,

 
 
3
5
,

 
 
1
,

 
 
7
8
5
3
,

 
 
3
9
0
,

 
 
8
4
,

 
 
7
,

 
 
3
4
,

 
 
3
5
,

 
 
7
8
5
3
,

 
 
1
6
8
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
4
,

 
 
1
6
,

 
 
3
8
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
1
2
2
2
,

 
 
3
0
4
,

 
 
4
0
,

 
 
7
,

 
 
3
9
,

 
 
3
4
,

 
 
8
,

 
 
1
9
0
4
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
1
1
0
,

 
 
1
0
,

 
 
1
3
,

 
 
2
4
4
,

 
 
9
,

 
 
1
,

 
 
7
8
5
3
,

 
 
3
9
1
1
,

 
 
8
6
,

 
 
3
6
6
0
,

 
 
1
8
2
,

 
 
1
0
7
3
,

 
 
3
9
4
0
,

 
 
5
4
7
,

 
 
1
3
,

 
 
1
4
6
3
,

 
 
1
0
4
,

 
 
8
,

 
 
4
9
,

 
 
6
1
8
0
,

 
 
9
6
,

 
 
2
2
,

 
 
7
,

 
 
9
9
,

 
 
4
4
,

 
 
1
1
0
,

 
 
2
,

 
 
7
3
9
1
,

 
 
3
8
,

 
 
7
,

 
 
1
6
7
,

 
 
5
0
6
6
,

 
 
8
7
,

 
 
3
5
0
,

 
 
3
8
,

 
 
5
1
,

 
 
1
0
8
,

 
 
2
6
,

 
 
2
1
9
,

 
 
5
5
,

 
 
9
7
1
,

 
 
3
4
8
6
,

 
 
5
,

 
 
5
2
,

 
 
1
8
9
,

 
 
4
5
,

 
 
3
7
3
,

 
 
6
,

 
 
1
0
4
,

 
 
2
9
6
9
1
,

 
 
1
2
,

 
 
1
,

 
 
9
6
2
,

 
 
3
,

 
 
1
,

 
 
4
2
4
3
,

 
 
2
9
6
9
2
,

 
 
5
4
3
3
2
]
,

 
[
5
,
 
2
0
7
1
,
 
7
7
0
5
,
 
2
6
7
9
]
,

 
[
1
3
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
8
9
5
,

 
 
5
1
5
,

 
 
1
1
6
,

 
 
6
4
,

 
 
1
4
4
,

 
 
9
,

 
 
1
6
3
9
3
,

 
 
1
7
4
,

 
 
3
6
,

 
 
3
1
3
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
5
7
0
3
,

 
 
8
4
6
8
,

 
 
5
1
5
,

 
 
3
,

 
 
1
,

 
 
8
9
5
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
5
6
8
2
,

 
 
2
3
,

 
 
1
1
,

 
 
3
8
3
,

 
 
2
0
3
6
,

 
 
2
,

 
 
1
0
1
0
,

 
 
9
,

 
 
1
2
3
2
,

 
 
4
0
,

 
 
8
9
5
,

 
 
3
,

 
 
3
7
3
8
,

 
 
8
,

 
 
4
7
0
,

 
 
2
,

 
 
1
5
2
2
,

 
 
2
8
3
8
,

 
 
1
0
,

 
 
6
0
,

 
 
1
1
0
,

 
 
2
5
,

 
 
6
1
,

 
 
8
9
,

 
 
9
,

 
 
3
7
3
8
,

 
 
3
4
0
4
,

 
 
4
2
,

 
 
3
3
7
0
,

 
 
9
,

 
 
5
1
,

 
 
9
0
,

 
 
1
0
,

 
 
1
6
6
,

 
 
8
2
,

 
 
1
2
5
0
,

 
 
3
3
5
2
,

 
 
1
3
,

 
 
8
,

 
 
3
8
3
,

 
 
4
,

 
 
3
1
3
,

 
 
3
1
3
,

 
 
5
8
,

 
 
8
5
8
,

 
 
7
2
2
,

 
 
3
,

 
 
8
9
5
,

 
 
9
3
,

 
 
5
8
0
,

 
 
5
3
4
,

 
 
4
4
5
,

 
 
1
0
,

 
 
1
3
,

 
 
4
3
2
,

 
 
8
1
7
,

 
 
8
9
5
,

 
 
5
1
5
,

 
 
1
1
6
,

 
 
1
,

 
 
3
8
5
9
,

 
 
2
7
0
,

 
 
1
2
5
0
,

 
 
4
7
6
9
,

 
 
5
6
,

 
 
1
6
,

 
 
4
4
5
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
4
0
3
1
,

 
 
2
7
1
9
,

 
 
6
4
3
1
,

 
 
8
2
1
1
]
,

 
[
1
1
0
1
,
 
2
1
0
,
 
8
3
,
 
5
6
,
 
1
6
,
 
1
6
6
7
,
 
4
5
5
4
5
,
 
4
5
5
4
6
]
,

 
[
2
2
9
7
,

 
 
2
3
8
,

 
 
7
,

 
 
1
8
4
,

 
 
4
9
,

 
 
4
2
6
,

 
 
1
6
5
,

 
 
6
6
5
2
,

 
 
1
,

 
 
7
2
5
7
,

 
 
3
5
6
7
,

 
 
4
0
,

 
 
1
,

 
 
8
5
,

 
 
6
9
,

 
 
7
,

 
 
1
9
,

 
 
4
,

 
 
6
1
8
,

 
 
2
6
7
,

 
 
2
1
,

 
 
1
,

 
 
1
2
1
8
5
,

 
 
1
6
0
6
5
0
,

 
 
6
9
8
2
2
,

 
 
2
0
6
6
0
]
,

 
[
7
,

 
 
2
6
3
,

 
 
2
1
,

 
 
3
9
5
,

 
 
4
4
,

 
 
1
2
2
,

 
 
2
,

 
 
2
4
6
,

 
 
2
2
1
2
,

 
 
3
3
4
5
,

 
 
5
,

 
 
1
2
6
3
,

 
 
8
0
,

 
 
4
,

 
 
2
0
1
,

 
 
1
4
9
2
,

 
 
1
3
8
1
,

 
 
6
6
,

 
 
3
6
7
,

 
 
2
1
9
,

 
 
2
,

 
 
1
4
,

 
 
3
9
8
,

 
 
2
0
9
,

 
 
1
2
0
,

 
 
1
7
,

 
 
4
,

 
 
2
1
2
,

 
 
8
0
,

 
 
1
2
0
,

 
 
8
,

 
 
2
0
3
,

 
 
4
,

 
 
3
3
7
,

 
 
3
,

 
 
6
8
,

 
 
7
2
5
8
,

 
 
1
1
3
,

 
 
2
4
0
9
,

 
 
5
,

 
 
1
1
3
,

 
 
1
2
5
0
1
,

 
 
7
9
0
,

 
 
2
,

 
 
4
8
9
,

 
 
1
3
7
4
9
]
,

 
[
1
7
8
,

 
 
1
,

 
 
7
8
9
0
,

 
 
2
,

 
 
1
8
2
2
,

 
 
1
8
,

 
 
6
3
5
,

 
 
5
3
2
6
,

 
 
1
5
6
,

 
 
1
1
4
,

 
 
7
,

 
 
9
9
,

 
 
1
,

 
 
6
2
7
,

 
 
9
,

 
 
2
9
6
9
3
,

 
 
9
9
9
3
,

 
 
2
,

 
 
7
9
9
8
,

 
 
1
4
,

 
 
1
6
0
6
5
1
,

 
 
2
6
,

 
 
8
9
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
2
5
4
8
,

 
 
4
,

 
 
3
2
5
8
,

 
 
9
,

 
 
8
3
6
1
4
,

 
 
1
1
0
9
,

 
 
1
1
,

 
 
1
6
7
,

 
 
1
,

 
 
8
3
6
1
4
,

 
 
9
9
9
3
,

 
 
2
,

 
 
8
3
6
1
5
,

 
 
3
1
,

 
 
1
1
3
8
3
,

 
 
1
3
,

 
 
8
,

 
 
3
8
0
,

 
 
2
6
,

 
 
6
,

 
 
2
4
5
,

 
 
6
1
9
8
,

 
 
3
3
0
,

 
 
5
8
3
2
,

 
 
5
0
0
,

 
 
6
,

 
 
4
3
,

 
 
6
0
6
,

 
 
1
5
,

 
 
1
,

 
 
1
3
9
,

 
 
2
4
4
6
4
,

 
 
1
,

 
 
2
9
8
8
,

 
 
3
7
2
,

 
 
3
2
9
,

 
 
8
3
6
1
6
,

 
 
8
3
6
1
7
,

 
 
4
2
2
,

 
 
1
0
,

 
 
5
8
3
2
,

 
 
7
9
1
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
1
5
4
,

 
 
2
9
8
8
,

 
 
3
4
4
6
,

 
 
2
9
8
8
,

 
 
1
6
6
4
1
,

 
 
3
9
6
9
3
,

 
 
8
3
6
1
7
,

 
 
2
9
8
8
,

 
 
3
0
8
2
2
,

 
 
8
3
6
1
7
,

 
 
3
9
6
9
3
,

 
 
1
4
9
9
,

 
 
8
3
6
1
6
,

 
 
9
,

 
 
8
,

 
 
7
4
,

 
 
1
1
,

 
 
7
5
2
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
8
6
,

 
 
5
0
,

 
 
3
2
8
,

 
 
2
9
6
9
4
,

 
 
1
6
0
6
5
2
,

 
 
7
,

 
 
2
9
6
6
,

 
 
7
9
,

 
 
1
,

 
 
2
9
,

 
 
8
9
,

 
 
1
0
,

 
 
2
3
8
6
,

 
 
9
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
7
7
3
]
,

 
[
3
4
7
,

 
 
7
,

 
 
5
,

 
 
4
0
,

 
 
1
,

 
 
6
1
,

 
 
5
1
0
0
,

 
 
1
3
2
0
,

 
 
1
5
,

 
 
2
8
,

 
 
3
4
7
,

 
 
6
,

 
 
1
5
,

 
 
4
1
3
8
,

 
 
6
,

 
 
1
8
,

 
 
3
7
4
,

 
 
7
,

 
 
5
7
4
,

 
 
2
6
3
,

 
 
2
1
,

 
 
5
1
0
0
,

 
 
2
8
9
2
,

 
 
7
2
,

 
 
1
9
3
3
,

 
 
3
3
,

 
 
1
,

 
 
1
1
6
4
,

 
 
2
6
,

 
 
2
2
,

 
 
5
3
,

 
 
1
2
2
,

 
 
2
,

 
 
9
4
,

 
 
1
6
0
6
5
3
,

 
 
4
1
5
5
,

 
 
1
8
8
,

 
 
8
4
,

 
 
1
1
,

 
 
5
6
,

 
 
1
0
3
8
,

 
 
6
9
,

 
 
6
8
,

 
 
2
1
7
,

 
 
8
,

 
 
2
7
0
6
]
,

 
[
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
9
1
4
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
1
,

 
 
2
9
,

 
 
1
2
6
2
3
,

 
 
6
9
8
2
3
,

 
 
1
5
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
,

 
 
8
9
,

 
 
1
1
8
,

 
 
6
7
,

 
 
2
2
5
,

 
 
6
,

 
 
9
1
4
,

 
 
4
2
3
6
5
,

 
 
1
6
0
6
5
4
,

 
 
1
6
8
,

 
 
1
9
,

 
 
2
4
1
,

 
 
2
0
1
,

 
 
2
,

 
 
3
4
,

 
 
9
3
,

 
 
3
0
8
0
,

 
 
1
,

 
 
6
5
6
,

 
 
1
6
8
,

 
 
6
4
3
0
,

 
 
1
6
0
6
5
5
,

 
 
7
2
6
,

 
 
6
9
4
,

 
 
3
4
9
3
,

 
 
2
0
8
6
,

 
 
9
0
1
,

 
 
1
6
0
6
5
6
,

 
 
6
,

 
 
6
0
7
8
4
,

 
 
7
3
9
,

 
 
3
2
5
,

 
 
1
6
0
6
5
7
,

 
 
1
9
8
0
,

 
 
1
9
2
,

 
 
5
4
3
3
3
,

 
 
7
9
,

 
 
1
8
3
,

 
 
1
6
2
,

 
 
3
,

 
 
3
0
,

 
 
5
4
3
3
4
,

 
 
5
,

 
 
8
8
8
,

 
 
1
6
,

 
 
2
4
4
6
5
,

 
 
3
1
,

 
 
1
8
0
,

 
 
3
2
,

 
 
1
7
0
5
,

 
 
6
,

 
 
1
4
5
4
5
,

 
 
1
6
0
6
5
8
,

 
 
3
6
,

 
 
9
2
3
,

 
 
1
1
,

 
 
1
8
3
7
6
,

 
 
7
2
6
,

 
 
3
,

 
 
2
4
6
3
,

 
 
9
1
4
,

 
 
1
8
3
7
6
,

 
 
8
4
7
,

 
 
7
2
8
,

 
 
1
6
0
6
5
9
,

 
 
2
,

 
 
1
6
,

 
 
5
7
3
,

 
 
6
4
,

 
 
3
6
,

 
 
1
5
9
,

 
 
3
8
,

 
 
7
,

 
 
1
1
7
,

 
 
1
7
,

 
 
4
,

 
 
8
2
1
2
,

 
 
1
4
0
4
8
]
,

 
[
1
7
1
6
4
,

 
 
4
3
6
4
,

 
 
6
,

 
 
1
8
,

 
 
2
7
,

 
 
4
1
8
,

 
 
5
,

 
 
6
,

 
 
1
7
9
2
,

 
 
1
,

 
 
7
5
,

 
 
6
2
,

 
 
4
0
3
3
,

 
 
1
,

 
 
1
7
1
6
4
,

 
 
2
3
,

 
 
1
1
2
,

 
 
1
6
6
4
2
,

 
 
1
8
,

 
 
5
6
1
7
,

 
 
4
7
1
0
,

 
 
6
0
0
0
,

 
 
5
4
9
8
,

 
 
5
,

 
 
5
1
,

 
 
4
7
6
,

 
 
1
0
8
,

 
 
2
,

 
 
6
3
,

 
 
1
,

 
 
2
7
0
,

 
 
1
4
1
2
,

 
 
2
1
,

 
 
7
1
4
4
,

 
 
6
,

 
 
1
2
1
,

 
 
8
8
,

 
 
2
5
6
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
3
4
3
,

 
 
1
7
1
6
4
,

 
 
1
8
,

 
 
9
4
4
,

 
 
1
3
5
,

 
 
7
1
6
8
,

 
 
3
2
,

 
 
2
0
,

 
 
7
4
1
,

 
 
2
8
4
]
,

 
[
6
,

 
 
2
4
5
,

 
 
1
6
,

 
 
1
7
6
0
,

 
 
1
0
,

 
 
2
,

 
 
1
4
6
0
,

 
 
1
4
6
6
,

 
 
3
6
,

 
 
1
0
,

 
 
6
1
,

 
 
4
0
9
,

 
 
7
,

 
 
1
9
,

 
 
2
,

 
 
5
1
7
,

 
 
7
3
,

 
 
4
9
,

 
 
2
,

 
 
1
5
2
,

 
 
2
3
3
,

 
 
2
1
8
,

 
 
2
,

 
 
1
6
2
,

 
 
6
0
1
,

 
 
2
,

 
 
5
4
9
,

 
 
2
1
,

 
 
9
,

 
 
1
3
,

 
 
2
0
2
,

 
 
3
9
,

 
 
6
9
8
2
,

 
 
1
2
,

 
 
4
0
,

 
 
7
,

 
 
4
6
6
,

 
 
2
2
8
3
,

 
 
6
2
2
,

 
 
2
2
0
7
,

 
 
5
1
4
0
]
,

 
[
3
9
6
9
4
,

 
 
6
7
2
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
2
1
,

 
 
3
2
5
8
,

 
 
4
3
,

 
 
1
6
,

 
 
2
,

 
 
1
5
7
9
,

 
 
4
,

 
 
1
9
3
,

 
 
3
3
,

 
 
1
1
3
,

 
 
1
0
1
3
,

 
 
5
0
6
,

 
 
3
7
6
,

 
 
1
1
3
,

 
 
4
9
2
,

 
 
1
1
3
,

 
 
2
5
6
0
,

 
 
1
1
3
,

 
 
1
5
0
9
6
]
,

 
[
3
7
7
,

 
 
2
5
0
,

 
 
8
5
,

 
 
4
4
,

 
 
4
6
,

 
 
7
,

 
 
2
4
,

 
 
4
9
,

 
 
1
0
6
5
6
5
,

 
 
3
1
5
,

 
 
1
5
,

 
 
1
8
0
,

 
 
5
,

 
 
3
8
2
5
,

 
 
7
,

 
 
3
3
2
,

 
 
3
,

 
 
6
,

 
 
3
6
,

 
 
4
9
5
,

 
 
7
4
,

 
 
1
6
4
2
,

 
 
1
6
5
,

 
 
7
,

 
 
2
2
6
,

 
 
5
3
,

 
 
3
9
,

 
 
9
4
,

 
 
6
7
7
,

 
 
8
9
,

 
 
4
9
5
,

 
 
4
1
,

 
 
8
,

 
 
2
7
,

 
 
2
6
7
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
9
,

 
 
4
2
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
2
8
,

 
 
4
,

 
 
1
0
7
,

 
 
1
5
,

 
 
6
4
,

 
 
9
9
,

 
 
5
7
,

 
 
2
8
8
5
,

 
 
3
7
,

 
 
5
,

 
 
9
7
0
,

 
 
6
0
,

 
 
1
6
0
6
6
0
,

 
 
2
5
4
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
1
2
6
8
,

 
 
3
,

 
 
3
8
,

 
 
7
,

 
 
1
0
3
,

 
 
3
4
,

 
 
7
,

 
 
7
0
,

 
 
9
,

 
 
1
0
7
,

 
 
8
,

 
 
6
6
,

 
 
3
1
,

 
 
1
7
1
1
,

 
 
1
0
3
,

 
 
1
,

 
 
1
3
4
3
,

 
 
6
4
,

 
 
3
4
,

 
 
5
5
,

 
 
2
2
8
,

 
 
6
6
9
,

 
 
1
2
,

 
 
8
9
,

 
 
5
4
1
1
,

 
 
6
5
7
7
,

 
 
1
1
8
3
,

 
 
7
9
9
9
]
,

 
[
9
5
,

 
 
3
1
,

 
 
3
0
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
4
1
,

 
 
1
8
,

 
 
2
2
0
6
,

 
 
5
,

 
 
1
2
6
2
4
,

 
 
3
2
9
,

 
 
1
,

 
 
1
4
9
,

 
 
3
3
4
5
,

 
 
4
7
,

 
 
4
9
5
0
,

 
 
8
,

 
 
9
,

 
 
2
1
0
,

 
 
3
3
4
5
,

 
 
1
8
,

 
 
9
6
8
8
,

 
 
4
,

 
 
2
4
5
3
,

 
 
2
1
,

 
 
4
,

 
 
1
7
1
6
5
,

 
 
1
0
9
3
,

 
 
1
,

 
 
9
3
0
,

 
 
8
,

 
 
1
,

 
 
1
2
9
0
,

 
 
3
,

 
 
2
7
9
8
,

 
 
1
7
1
6
6
,

 
 
8
,

 
 
9
6
8
8
,

 
 
4
,

 
 
1
7
1
6
5
,

 
 
1
0
9
3
,

 
 
4
5
6
,

 
 
1
,

 
 
3
9
6
9
5
,

 
 
1
2
8
7
,

 
 
6
1
7
,

 
 
1
2
8
7
,

 
 
1
8
4
,

 
 
1
6
,

 
 
1
,

 
 
1
2
9
0
,

 
 
3
,

 
 
8
0
3
6
,

 
 
1
7
1
6
5
,

 
 
3
8
6
,

 
 
8
,

 
 
9
6
8
8
,

 
 
4
,

 
 
1
7
1
6
5
,

 
 
1
0
9
3
,

 
 
4
5
6
,

 
 
1
,

 
 
3
9
6
9
5
,

 
 
2
8
6
7
,

 
 
4
,

 
 
4
3
7
,

 
 
9
3
0
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
1
2
9
0
,

 
 
3
,

 
 
2
7
9
8
,

 
 
1
7
1
6
6
,

 
 
4
2
,

 
 
1
9
3
9
,

 
 
2
,

 
 
5
8
,

 
 
2
2
1
0
,

 
 
2
2
9
1
,

 
 
5
,

 
 
2
8
2
2
,

 
 
1
0
,

 
 
6
1
4
,

 
 
1
3
3
9
,

 
 
1
0
,

 
 
1
7
9
,

 
 
3
1
1
,

 
 
1
,

 
 
2
3
8
5
,

 
 
1
4
,

 
 
7
7
,

 
 
1
2
7
2
8
,

 
 
2
6
,

 
 
6
6
,

 
 
9
8
6
5
,

 
 
3
,

 
 
2
7
0
5
,

 
 
3
,

 
 
7
5
,

 
 
1
0
,

 
 
2
7
,

 
 
4
5
5
4
7
,

 
 
8
9
3
5
,

 
 
5
9
9
,

 
 
1
0
7
,

 
 
3
6
3
8
,

 
 
7
0
6
9
,

 
 
6
5
5
]
,

 
[
1
0
1
,

 
 
7
,

 
 
6
3
,

 
 
4
5
5
4
8
,

 
 
8
,

 
 
4
0
4
,

 
 
3
7
1
,

 
 
2
5
1
3
,

 
 
8
9
,

 
 
2
5
5
4
,

 
 
6
1
,

 
 
2
0
5
,

 
 
6
6
,

 
 
5
,

 
 
1
2
7
,

 
 
9
2
,

 
 
2
0
3
8
,

 
 
8
,

 
 
9
7
,

 
 
1
,

 
 
1
4
5
,

 
 
9
,

 
 
1
,

 
 
1
1
4
,

 
 
3
5
7
6
,

 
 
1
6
2
6
,

 
 
5
,

 
 
1
,

 
 
4
3
7
,

 
 
3
5
7
6
,

 
 
1
6
2
6
,

 
 
1
8
,

 
 
1
4
,

 
 
3
5
7
6
,

 
 
2
5
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
4
,

 
 
4
7
0
,

 
 
5
4
,

 
 
1
8
0
7
,

 
 
9
2
,

 
 
2
5
0
,

 
 
3
5
3
,

 
 
4
5
6
4
,

 
 
1
2
,

 
 
1
,

 
 
6
0
7
1
,

 
 
3
,

 
 
4
,

 
 
3
2
8
0
,

 
 
1
6
8
3
,

 
 
5
,

 
 
2
9
7
,

 
 
6
5
,

 
 
3
5
7
6
,

 
 
1
6
6
4
3
,

 
 
6
2
8
0
,

 
 
3
2
1
,

 
 
5
4
,

 
 
2
2
9
2
,

 
 
3
1
,

 
 
1
2
0
7
5
,

 
 
5
,

 
 
1
,

 
 
7
2
9
,

 
 
3
5
8
2
,

 
 
1
8
5
,

 
 
1
1
,

 
 
1
6
0
6
6
1
,

 
 
1
7
3
8
,

 
 
1
6
5
3
,

 
 
7
6
,

 
 
9
,

 
 
1
1
5
4
,

 
 
6
1
4
,

 
 
7
3
2
4
,

 
 
8
,

 
 
5
7
4
,

 
 
8
3
4
0
,

 
 
1
2
,

 
 
1
,

 
 
4
8
7
,

 
 
9
3
6
,

 
 
4
4
,

 
 
6
1
,

 
 
5
4
6
,

 
 
2
4
9
4
,

 
 
1
2
,

 
 
1
3
,

 
 
1
0
,

 
 
9
2
,

 
 
4
8
7
,

 
 
9
3
6
,

 
 
1
0
5
4
,

 
 
3
1
7
2
,

 
 
1
4
1
1
,

 
 
1
5
9
1
,

 
 
2
8
2
3
,

 
 
3
2
1
,

 
 
3
8
,

 
 
8
,

 
 
3
9
3
,

 
 
8
,

 
 
2
,

 
 
3
1
4
,

 
 
7
4
,

 
 
6
0
4
7
,

 
 
3
0
9
0
,

 
 
6
6
5
2
,

 
 
1
,

 
 
3
5
8
2
]
,

 
[
4
2
3
6
6
,
 
1
1
7
1
,
 
4
,
 
5
0
1
,
 
1
9
6
,
 
2
,
 
2
8
,
 
3
7
5
,
 
6
,
 
1
8
4
,
 
1
3
6
,
 
1
1
3
,
 
5
0
7
7
,
 
3
,
 
5
6
2
]
,

 
[
1
6
,
 
1
7
7
4
,
 
6
2
,
 
6
,
 
4
5
8
,
 
4
,
 
9
0
1
]
,

 
[
3
3
6
7
5
,

 
 
1
4
3
2
,

 
 
1
9
4
2
0
,

 
 
2
4
9
,

 
 
2
9
3
6
,

 
 
4
5
6
,

 
 
1
,

 
 
3
7
6
,

 
 
8
1
5
,

 
 
3
3
6
7
5
,

 
 
1
4
3
2
,

 
 
2
3
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
2
4
1
0
,

 
 
9
5
1
2
,

 
 
3
3
6
7
5
,

 
 
1
5
,

 
 
6
4
8
,

 
 
2
9
4
0
,

 
 
5
4
3
3
5
,

 
 
8
8
8
1
,

 
 
3
6
8
,

 
 
3
0
,

 
 
2
8
7
1
,

 
 
2
2
2
7
,

 
 
3
,

 
 
2
9
4
0
,

 
 
6
7
5
,

 
 
7
,

 
 
1
8
7
,

 
 
4
0
,

 
 
1
,

 
 
1
7
1
6
7
,

 
 
5
,

 
 
2
5
9
4
2
,

 
 
3
1
,

 
 
1
,

 
 
2
3
,

 
 
3
5
1
,

 
 
5
2
,

 
 
9
2
0
1
,

 
 
3
7
,

 
 
3
,

 
 
3
5
5
,

 
 
4
,

 
 
6
8
1
,

 
 
2
4
9
,

 
 
4
4
,

 
 
2
9
2
,

 
 
4
2
,

 
 
1
,

 
 
1
4
3
,

 
 
2
,

 
 
3
9
8
,

 
 
1
,

 
 
9
8
,

 
 
5
8
8
,

 
 
1
3
5
8
,

 
 
3
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
7
,

 
 
4
5
,

 
 
2
2
7
7
,

 
 
6
8
,

 
 
5
4
1
7
,

 
 
3
9
8
,

 
 
1
7
,

 
 
6
,

 
 
1
3
1
,

 
 
4
,

 
 
1
1
1
0
,

 
 
7
9
,

 
 
2
5
,

 
 
1
4
9
,

 
 
1
4
4
,

 
 
8
4
,

 
 
2
0
,

 
 
1
4
0
,

 
 
4
5
,

 
 
2
8
8
,

 
 
1
6
,

 
 
1
0
6
0
,

 
 
6
6
,

 
 
5
0
,

 
 
3
8
8
7
,

 
 
9
5
2
,

 
 
3
8
,

 
 
9
8
6
6
,

 
 
6
,

 
 
1
3
6
,

 
 
1
0
,

 
 
1
,

 
 
2
5
3
,

 
 
5
,

 
 
3
5
2
,

 
 
5
3
,

 
 
3
9
,

 
 
1
4
2
,

 
 
7
6
,

 
 
6
0
,

 
 
1
9
7
1
,

 
 
1
2
6
3
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
4
9
3
9
,

 
 
1
0
,

 
 
1
,

 
 
2
5
7
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
4
9
3
9
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
1
0
1
3
,

 
 
1
2
9
,

 
 
1
3
,

 
 
2
3
]
,

 
[
2
9
0
7
,

 
 
3
0
8
2
3
,

 
 
1
1
4
,

 
 
9
6
3
3
,

 
 
1
6
0
6
6
2
,

 
 
3
9
3
,

 
 
6
9
8
,

 
 
3
3
,

 
 
1
3
,

 
 
1
4
2
1
,

 
 
7
,

 
 
2
0
4
,

 
 
1
0
,

 
 
1
,

 
 
3
0
3
1
,

 
 
1
1
6
,

 
 
6
0
7
8
5
,

 
 
1
0
2
3
,

 
 
2
0
6
,

 
 
1
1
4
,

 
 
5
,

 
 
1
6
5
6
,

 
 
2
1
,

 
 
5
8
,

 
 
3
5
,

 
 
3
8
,

 
 
3
3
6
7
6
,

 
 
1
6
7
,

 
 
7
,

 
 
2
6
5
,

 
 
1
9
0
5
6
,

 
 
3
3
6
7
6
,

 
 
2
9
7
4
,

 
 
9
,

 
 
6
0
7
8
5
,

 
 
2
7
3
5
,

 
 
1
9
,

 
 
1
6
7
0
,

 
 
3
0
8
2
3
,

 
 
3
,

 
 
8
5
6
1
,

 
 
7
7
4
1
,

 
 
5
,

 
 
1
,

 
 
4
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
1
2
,

 
 
6
4
7
4
,

 
 
3
3
6
7
6
,

 
 
5
4
1
,

 
 
9
,

 
 
9
,

 
 
6
0
7
8
5
,

 
 
1
3
8
,

 
 
3
,

 
 
6
1
1
6
,

 
 
5
3
0
,

 
 
6
3
0
0
,

 
 
5
,

 
 
6
1
,

 
 
1
0
9
1
,

 
 
7
7
,

 
 
2
0
0
6
,

 
 
2
,

 
 
1
7
0
7
,

 
 
1
3
4
5
9
,

 
 
4
0
1
,

 
 
3
9
2
9
,

 
 
7
3
2
5
,

 
 
3
1
5
,

 
 
2
3
9
1
,

 
 
3
2
8
7
,

 
 
5
2
,

 
 
1
2
6
0
,

 
 
4
,

 
 
1
7
4
3
,

 
 
2
2
6
,

 
 
5
4
1
,

 
 
2
,

 
 
1
5
4
,

 
 
3
5
8
,

 
 
1
,

 
 
1
9
4
,

 
 
8
9
7
,

 
 
3
2
2
,

 
 
1
,

 
 
1
7
2
2
,

 
 
6
2
,

 
 
4
8
9
,

 
 
9
2
,

 
 
1
7
0
,

 
 
1
0
1
3
,

 
 
4
3
,

 
 
1
4
,

 
 
1
6
,

 
 
8
2
9
9
,

 
 
2
6
,

 
 
7
7
,

 
 
1
4
1
,

 
 
6
2
,

 
 
1
8
,

 
 
4
6
2
6
,

 
 
4
2
2
9
,

 
 
2
,

 
 
1
,

 
 
1
2
4
1
,

 
 
9
2
5
2
,

 
 
2
5
,

 
 
1
7
0
7
,

 
 
2
7
6
0
,

 
 
1
2
6
7
,

 
 
3
,

 
 
1
3
4
0
,

 
 
1
7
,

 
 
7
,

 
 
1
6
7
,

 
 
1
0
,

 
 
3
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
4
9
,

 
 
6
9
,

 
 
6
0
,

 
 
1
5
2
7
,

 
 
2
,

 
 
1
0
7
1
,

 
 
1
5
9
,

 
 
6
8
,

 
 
2
3
4
,

 
 
3
5
,

 
 
3
,

 
 
7
3
2
,

 
 
5
,

 
 
5
1
8
,

 
 
1
5
4
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
7
6
,

 
 
9
,

 
 
2
8
,

 
 
5
6
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
2
,

 
 
1
,

 
 
1
3
9
,

 
 
9
8
0
,

 
 
3
2
9
6
,

 
 
1
6
8
9
6
,

 
 
1
0
6
5
6
6
]
,

 
[
1
,

 
 
1
6
6
,

 
 
3
,

 
 
1
,

 
 
3
5
4
,

 
 
8
,

 
 
9
,

 
 
6
9
8
2
4
,

 
 
5
,

 
 
3
7
4
1
4
,

 
 
1
9
,

 
 
5
7
,

 
 
2
0
9
,

 
 
8
3
6
1
8
,

 
 
2
,

 
 
4
0
5
0
,

 
 
9
0
2
,

 
 
2
,

 
 
1
,

 
 
1
1
4
,

 
 
1
5
7
3
,

 
 
2
3
8
2
7
,

 
 
8
0
2
,

 
 
1
4
4
,

 
 
3
3
,

 
 
3
0
8
,

 
 
6
5
5
,

 
 
3
0
6
,

 
 
3
3
9
8
,

 
 
8
0
2
,

 
 
9
,

 
 
4
2
,

 
 
1
,

 
 
1
6
0
6
6
3
,

 
 
3
4
6
2
,

 
 
4
2
,

 
 
5
7
,

 
 
1
1
6
5
0
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
1
3
,

 
 
7
0
8
,

 
 
3
,

 
 
2
2
8
,

 
 
1
5
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
2
8
5
3
,

 
 
3
4
6
,

 
 
1
2
8
6
,

 
 
3
2
,

 
 
8
8
,

 
 
3
8
9
1
,

 
 
4
2
,

 
 
1
1
,

 
 
1
7
,

 
 
8
3
6
1
8
,

 
 
2
0
8
,

 
 
4
0
,

 
 
1
,

 
 
2
8
7
,

 
 
1
9
,

 
 
5
7
,

 
 
1
6
0
6
6
4
,

 
 
1
6
0
6
6
5
,

 
 
1
6
0
6
6
6
,

 
 
1
6
0
6
6
7
,

 
 
1
6
0
6
6
8
,

 
 
1
6
0
6
6
9
,

 
 
1
6
0
6
7
0
,

 
 
1
6
0
6
7
1
,

 
 
1
6
0
6
7
2
,

 
 
1
6
0
6
7
3
,

 
 
1
6
0
6
7
4
,

 
 
5
4
3
3
6
,

 
 
5
,

 
 
1
0
6
5
6
7
,

 
 
7
,

 
 
2
2
0
,

 
 
8
3
6
1
8
,

 
 
8
,

 
 
6
6
,

 
 
2
3
8
2
8
,

 
 
1
0
8
0
,

 
 
9
2
,

 
 
6
1
1
7
,

 
 
3
5
3
8
8
,

 
 
1
6
1
4
3
]
,

 
[
1
3
0
0
,

 
 
5
4
3
3
7
,

 
 
4
2
,

 
 
1
2
9
3
,

 
 
3
8
2
,

 
 
3
,

 
 
7
5
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
5
1
,

 
 
1
2
6
,

 
 
2
2
9
5
,

 
 
2
,

 
 
8
2
,

 
 
1
,

 
 
1
0
0
4
1
,

 
 
1
0
6
,

 
 
4
2
0
,

 
 
2
,

 
 
6
6
6
,

 
 
9
9
7
,

 
 
3
,

 
 
1
3
,

 
 
3
7
2
,

 
 
1
4
8
4
,

 
 
1
0
,

 
 
3
8
0
1
,

 
 
5
,

 
 
1
0
,

 
 
1
,

 
 
3
1
1
2
,

 
 
3
5
8
9
,

 
 
8
0
3
7
,

 
 
1
8
2
6
,

 
 
2
5
9
4
3
,

 
 
9
7
3
,

 
 
1
,

 
 
1
6
6
4
4
,

 
 
8
6
8
6
,

 
 
6
0
7
2
,

 
 
1
4
8
6
,

 
 
1
0
,

 
 
1
3
7
8
,

 
 
6
0
2
7
,

 
 
7
6
3
,

 
 
1
0
6
5
6
8
,

 
 
1
3
2
1
3
,

 
 
1
7
7
6
1
,

 
 
1
1
5
6
5
,

 
 
7
6
1
,

 
 
1
0
7
9
,

 
 
1
1
8
3
,

 
 
9
8
1
,

 
 
8
4
4
,

 
 
5
0
1
,

 
 
2
1
3
6
,

 
 
1
7
6
,

 
 
5
9
0
,

 
 
6
1
5
,

 
 
2
4
3
,

 
 
5
9
0
,

 
 
1
4
2
8
,

 
 
1
6
0
6
7
5
,

 
 
1
2
5
0
8
,

 
 
6
0
7
8
6
,

 
 
3
6
3
3
,

 
 
1
0
6
5
6
9
,

 
 
8
5
2
,

 
 
8
7
3
4
,

 
 
2
0
4
4
,

 
 
5
1
2
,

 
 
6
7
9
]
,

 
[
7
,

 
 
6
3
,

 
 
9
,

 
 
6
,

 
 
4
9
,

 
 
2
2
9
,

 
 
1
2
1
,

 
 
2
2
5
,

 
 
2
2
,

 
 
6
,

 
 
6
8
7
,

 
 
3
0
,

 
 
9
1
,

 
 
1
8
8
,

 
 
1
7
,

 
 
4
,

 
 
2
1
2
,

 
 
2
,

 
 
1
6
,

 
 
1
5
6
7
8
,

 
 
5
,

 
 
8
9
,

 
 
2
1
1
,

 
 
4
8
,

 
 
2
4
6
,

 
 
1
6
0
6
7
6
,

 
 
1
5
,

 
 
3
7
,

 
 
2
,

 
 
1
,

 
 
7
5
3
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
8
2
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
2
,

 
 
9
,

 
 
1
1
8
,

 
 
1
,

 
 
3
8
5
0
,

 
 
1
7
5
5
,

 
 
1
2
5
,

 
 
1
,

 
 
2
3
5
0
,

 
 
2
2
8
1
,

 
 
2
4
,

 
 
6
7
0
,

 
 
5
,

 
 
1
5
2
,

 
 
3
5
1
,

 
 
1
8
3
,

 
 
3
4
5
,

 
 
1
7
0
4
,

 
 
2
0
,

 
 
1
1
2
2
,

 
 
1
5
,

 
 
3
8
,

 
 
7
,

 
 
1
2
2
,

 
 
2
,

 
 
1
6
0
6
7
7
,

 
 
4
9
9
,

 
 
5
4
3
3
8
,

 
 
1
3
6
6
,

 
 
1
1
,

 
 
1
4
3
,

 
 
1
5
7
,

 
 
3
3
,

 
 
2
2
5
,

 
 
5
4
3
,

 
 
4
5
6
,

 
 
1
1
3
,

 
 
1
0
6
4
4
,

 
 
5
,

 
 
5
0
,

 
 
2
7
5
,

 
 
9
,

 
 
3
1
9
,

 
 
8
,

 
 
4
,

 
 
1
5
2
2
,

 
 
3
,

 
 
4
,

 
 
1
4
5
5
,

 
 
1
3
8
,

 
 
1
4
,

 
 
4
9
,

 
 
5
5
,

 
 
7
2
6
,

 
 
2
8
,

 
 
2
5
3
,

 
 
9
,

 
 
6
3
2
5
,

 
 
2
2
1
0
6
,

 
 
1
2
,

 
 
4
,

 
 
2
0
8
]
,

 
[
1
9
4
,

 
 
1
,

 
 
1
6
9
2
,

 
 
3
,

 
 
5
4
3
3
9
,

 
 
8
,

 
 
3
9
9
,

 
 
9
4
6
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
1
5
5
5
,

 
 
3
1
2
0
,

 
 
5
2
,

 
 
8
,

 
 
6
6
,

 
 
1
0
2
,

 
 
1
8
5
4
,

 
 
5
,

 
 
4
2
,

 
 
4
,

 
 
3
0
7
1
,

 
 
1
2
,

 
 
4
,

 
 
8
9
6
]
,

 
[
1
1
2
5
,

 
 
4
4
1
7
,

 
 
3
1
,

 
 
8
0
8
,

 
 
1
4
0
7
,

 
 
6
0
,

 
 
7
5
,

 
 
6
4
,

 
 
1
9
,

 
 
4
,

 
 
2
6
4
,

 
 
4
0
2
6
,

 
 
3
3
5
,

 
 
3
,

 
 
3
8
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
1
8
,

 
 
1
8
9
9
,

 
 
7
6
,

 
 
9
,

 
 
1
,

 
 
1
9
1
2
,

 
 
2
3
2
7
,

 
 
3
7
,

 
 
3
,

 
 
2
0
9
,

 
 
3
0
4
0
,

 
 
8
6
,

 
 
9
7
4
,

 
 
5
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
,

 
 
1
4
9
,

 
 
4
3
2
,

 
 
7
5
,

 
 
2
9
0
,

 
 
1
,

 
 
1
4
7
2
,

 
 
1
9
,

 
 
5
7
,

 
 
3
5
2
1
,

 
 
3
7
,

 
 
1
2
,

 
 
8
9
2
,

 
 
5
,

 
 
9
9
,

 
 
1
3
3
,

 
 
3
0
4
0
,

 
 
5
,

 
 
3
2
4
7
,

 
 
3
6
9
1
,

 
 
7
5
9
,

 
 
1
2
,

 
 
4
0
4
,

 
 
3
1
5
,

 
 
7
9
,

 
 
3
5
4
9
,

 
 
5
,

 
 
2
,

 
 
8
0
3
8
,

 
 
2
0
2
6
,

 
 
1
5
,

 
 
4
,

 
 
3
3
6
,

 
 
1
2
,

 
 
4
1
8
,

 
 
8
3
6
1
9
,

 
 
1
7
,

 
 
1
6
5
3
,

 
 
7
6
,

 
 
3
2
,

 
 
4
3
0
,

 
 
2
0
5
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
5
5
1
,

 
 
4
3
1
,

 
 
1
6
,

 
 
4
1
9
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
1
8
9
9
,

 
 
7
6
,

 
 
9
,

 
 
6
4
0
,

 
 
9
0
,

 
 
1
4
,

 
 
1
9
,

 
 
5
5
,

 
 
7
4
3
,

 
 
2
3
0
,

 
 
1
2
6
7
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
1
8
0
4
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
1
0
,

 
 
1
6
6
,

 
 
5
7
,

 
 
1
7
9
1
,

 
 
3
2
,

 
 
1
,

 
 
8
3
6
2
0
,

 
 
3
,

 
 
1
,

 
 
1
8
0
4
,

 
 
5
8
,

 
 
9
3
,

 
 
4
0
8
,

 
 
2
1
5
0
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
4
9
1
,

 
 
1
2
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
2
8
9
,

 
 
2
2
5
,

 
 
1
2
,

 
 
2
0
,

 
 
3
4
6
8
,

 
 
2
4
2
2
,

 
 
6
1
9
,

 
 
1
5
,

 
 
3
0
,

 
 
9
1
5
,

 
 
4
0
1
,

 
 
9
2
9
,

 
 
1
4
3
5
,

 
 
1
0
5
,

 
 
5
,

 
 
2
0
3
,

 
 
1
5
6
8
,

 
 
1
0
5
,

 
 
3
3
9
,

 
 
2
,

 
 
6
,

 
 
3
2
,

 
 
6
1
,

 
 
1
9
1
2
,

 
 
2
5
,

 
 
1
2
6
5
,

 
 
9
6
9
1
,

 
 
1
2
,

 
 
1
5
0
6
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
2
1
8
2
,

 
 
8
0
,

 
 
4
0
,

 
 
7
,

 
 
8
1
,

 
 
2
9
8
,

 
 
8
,

 
 
3
3
1
9
,

 
 
4
9
9
,

 
 
3
1
,

 
 
6
7
9
,

 
 
1
4
7
2
,

 
 
3
,

 
 
2
8
7
,

 
 
7
1
,

 
 
1
0
2
,

 
 
3
8
1
,

 
 
9
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
7
5
,

 
 
6
4
,

 
 
1
2
2
,

 
 
2
,

 
 
1
4
7
8
,

 
 
9
,

 
 
1
,

 
 
1
0
2
,

 
 
2
1
8
,

 
 
5
1
,

 
 
1
8
,

 
 
2
3
2
7
,

 
 
3
7
,

 
 
3
,

 
 
5
,

 
 
2
6
8
,

 
 
2
,

 
 
2
0
0
1
,

 
 
1
2
,

 
 
4
,

 
 
2
1
3
,

 
 
1
8
,

 
 
6
3
4
,

 
 
3
8
,

 
 
5
1
,

 
 
7
5
9
,

 
 
1
8
,

 
 
2
9
8
,

 
 
3
1
,

 
 
1
0
5
7
,

 
 
1
,

 
 
1
4
8
8
9
,

 
 
3
,

 
 
2
6
8
,

 
 
2
,

 
 
3
4
3
6
,

 
 
2
1
8
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
4
2
6
,

 
 
1
0
8
9
,

 
 
1
2
,

 
 
4
0
2
7
,

 
 
7
,

 
 
1
8
4
,

 
 
4
6
8
,

 
 
5
3
0
,

 
 
1
2
6
5
,

 
 
9
6
9
1
,

 
 
1
2
,

 
 
4
,

 
 
2
0
8
,

 
 
1
2
,

 
 
6
8
,

 
 
9
1
5
,

 
 
2
5
,

 
 
9
0
4
1
,

 
 
1
2
,

 
 
4
6
1
4
,

 
 
1
5
0
6
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
2
0
9
,

 
 
3
0
4
0
,

 
 
2
5
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
3
5
2
1
,

 
 
1
7
2
,

 
 
2
5
,

 
 
1
,

 
 
5
7
3
6
,

 
 
1
4
0
9
,

 
 
1
0
2
,

 
 
4
6
,

 
 
2
9
,

 
 
2
8
6
,

 
 
5
7
2
,

 
 
1
6
5
,

 
 
2
,

 
 
1
1
8
,

 
 
3
1
5
,

 
 
1
0
8
9
,

 
 
7
5
,

 
 
4
4
,

 
 
2
5
4
,

 
 
6
3
6
,

 
 
5
,

 
 
1
0
,

 
 
1
6
6
,

 
 
9
0
,

 
 
3
6
,

 
 
1
5
1
,

 
 
7
,

 
 
2
7
2
1
,

 
 
1
5
4
,

 
 
3
7
6
8
,

 
 
3
5
7
7
,

 
 
2
2
2
8
,

 
 
1
0
5
,

 
 
1
5
,

 
 
7
4
,

 
 
2
,

 
 
7
5
6
4
,

 
 
1
7
6
7
,

 
 
2
7
,

 
 
2
3
,

 
 
4
6
,

 
 
2
9
,

 
 
4
7
5
,

 
 
5
6
,

 
 
1
3
6
6
,

 
 
2
,

 
 
5
4
5
,

 
 
5
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
7
5
,

 
 
1
9
,

 
 
5
7
,

 
 
4
0
4
,

 
 
5
0
4
,

 
 
2
1
,

 
 
5
2
1
,

 
 
1
6
3
9
4
,

 
 
2
2
3
7
,

 
 
5
,

 
 
2
6
8
,

 
 
2
,

 
 
2
3
8
2
9
,

 
 
8
8
,

 
 
5
0
4
,

 
 
3
2
,

 
 
4
9
,

 
 
6
9
8
3
,

 
 
3
7
,

 
 
1
7
,

 
 
2
7
,

 
 
2
4
1
9
,

 
 
2
4
9
,

 
 
2
9
2
,

 
 
5
,

 
 
1
4
,

 
 
7
0
3
,

 
 
5
5
,

 
 
7
0
8
,

 
 
3
,

 
 
3
5
2
2
,

 
 
1
2
,

 
 
9
2
,

 
 
1
7
0
,

 
 
9
1
5
]
,

 
[
5
2
6
,

 
 
9
8
,

 
 
2
,

 
 
3
7
,

 
 
7
,

 
 
6
5
,

 
 
4
,

 
 
5
7
3
,

 
 
2
8
0
1
,

 
 
3
,

 
 
3
2
1
7
6
,

 
 
3
1
,

 
 
1
0
8
0
,

 
 
1
,

 
 
1
3
0
6
,

 
 
2
2
4
8
,

 
 
4
3
,

 
 
1
6
,

 
 
1
,

 
 
2
2
1
,

 
 
4
4
1
,

 
 
8
1
3
,

 
 
2
,

 
 
1
,

 
 
1
5
2
7
3
,

 
 
2
6
,

 
 
4
1
,

 
 
2
8
5
,

 
 
4
7
,

 
 
5
3
4
,

 
 
8
4
2
,

 
 
1
5
,

 
 
1
8
0
,

 
 
1
3
1
3
]
,

 
[
3
7
5
,

 
 
1
,

 
 
2
1
4
,

 
 
8
,

 
 
5
8
,

 
 
3
,

 
 
2
1
3
8
,

 
 
9
3
,

 
 
3
,

 
 
4
4
4
5
,

 
 
5
,

 
 
5
3
,

 
 
5
9
,

 
 
1
9
,

 
 
5
5
,

 
 
9
3
0
2
,

 
 
3
3
,

 
 
6
4
5
,

 
 
3
5
0
2
,

 
 
6
2
,

 
 
1
8
,

 
 
8
7
8
1
,

 
 
3
,

 
 
4
4
4
5
,

 
 
5
0
6
,

 
 
3
7
6
]
,

 
[
9
4
5
,

 
 
1
2
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
3
9
5
,

 
 
4
4
,

 
 
1
0
5
,

 
 
1
2
,

 
 
1
,

 
 
9
0
7
,

 
 
4
4
,

 
 
3
9
6
7
,

 
 
1
5
,

 
 
3
7
2
,

 
 
3
,

 
 
2
0
8
1
,

 
 
7
8
,

 
 
5
9
,

 
 
6
,

 
 
4
9
,

 
 
2
0
4
,

 
 
9
9
1
,

 
 
1
0
,

 
 
3
6
,

 
 
7
1
,

 
 
4
9
,

 
 
7
4
7
4
,

 
 
5
,

 
 
1
4
,

 
 
2
1
7
,

 
 
5
6
6
8
,

 
 
8
3
0
0
,

 
 
5
3
1
0
,

 
 
7
1
9
8
]
,

 
[
1
4
3
,
 
1
5
,
 
8
7
,
 
1
3
6
1
,
 
2
9
6
9
5
,
 
5
4
,
 
8
,
 
1
4
,
 
1
,
 
3
3
0
4
,
 
5
,
 
8
3
8
1
]
,

 
[
3
7
5
,

 
 
1
3
6
0
3
,

 
 
6
,

 
 
1
0
3
,

 
 
4
9
8
,

 
 
4
,

 
 
1
4
2
1
,

 
 
1
2
,

 
 
1
3
,

 
 
3
3
2
,

 
 
1
7
,

 
 
7
,

 
 
8
1
,

 
 
4
6
1
0
,

 
 
3
,

 
 
1
1
,

 
 
1
2
0
6
,

 
 
7
,

 
 
2
2
6
,

 
 
1
,

 
 
4
6
0
,

 
 
8
,

 
 
1
6
5
,

 
 
7
7
1
,

 
 
4
6
3
]
,

 
[
1
1
,
 
8
,
 
6
6
,
 
3
0
5
4
,
 
9
,
 
7
,
 
2
2
9
,
 
1
1
2
0
,
 
2
,
 
1
,
 
2
1
3
2
,
 
4
6
]
,

 
[
7
,

 
 
1
9
9
,

 
 
2
4
0
,

 
 
1
3
1
,

 
 
1
3
,

 
 
7
3
5
,

 
 
2
4
0
,

 
 
2
3
,

 
 
7
,

 
 
4
9
,

 
 
2
4
0
,

 
 
6
3
7
,

 
 
1
1
,

 
 
5
,

 
 
9
,

 
 
2
4
,

 
 
4
,

 
 
2
4
0
,

 
 
2
5
0
,

 
 
8
5
,

 
 
6
3
3
,

 
 
2
4
0
,

 
 
2
8
6
4
,

 
 
7
8
1
6
,

 
 
3
7
,

 
 
1
9
2
]
,

 
[
4
2
,

 
 
2
5
9
,

 
 
3
4
9
,

 
 
4
1
9
,

 
 
4
7
3
,

 
 
2
7
7
,

 
 
9
6
6
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
7
,

 
 
4
,

 
 
1
4
9
1
,

 
 
9
2
1
,

 
 
8
0
,

 
 
1
4
9
,

 
 
7
5
,

 
 
8
6
2
,

 
 
1
0
,

 
 
1
3
3
2
8
,

 
 
1
3
4
6
0
,

 
 
2
5
,

 
 
4
2
7
8
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
1
3
9
,

 
 
3
9
8
,

 
 
4
9
2
,

 
 
4
0
2
,

 
 
5
1
,

 
 
8
7
,

 
 
1
4
,

 
 
2
6
0
4
,

 
 
2
1
5
5
,

 
 
1
,

 
 
1
4
9
1
,

 
 
7
2
3
,

 
 
2
6
,

 
 
5
1
,

 
 
5
5
1
,

 
 
3
4
,

 
 
3
6
,

 
 
1
0
,

 
 
2
4
5
4
,

 
 
1
3
,

 
 
2
4
,

 
 
1
,

 
 
2
4
9
,

 
 
1
5
,

 
 
2
1
0
,

 
 
1
9
5
9
,

 
 
1
0
,

 
 
1
,

 
 
7
9
,

 
 
3
2
6
,

 
 
1
5
,

 
 
1
,

 
 
1
5
4
0
,

 
 
2
9
,

 
 
5
,

 
 
3
0
6
8
,

 
 
3
8
,

 
 
7
,

 
 
5
7
7
,

 
 
2
,

 
 
8
0
5
,

 
 
1
5
,

 
 
1
,

 
 
9
5
1
3
,

 
 
2
9
,

 
 
4
3
,

 
 
1
1
,

 
 
1
4
,

 
 
1
6
,

 
 
1
6
6
0
,

 
 
2
,

 
 
3
1
6
0
,

 
 
2
0
5
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
6
4
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
1
1
8
,

 
 
3
2
2
,

 
 
1
2
4
,

 
 
1
2
,

 
 
1
3
2
4
,

 
 
3
3
,

 
 
4
,

 
 
8
5
,

 
 
1
7
,

 
 
2
4
,

 
 
2
0
7
,

 
 
1
0
,

 
 
1
,

 
 
1
5
4
0
,

 
 
1
9
8
,

 
 
7
2
,

 
 
1
8
6
,

 
 
1
3
,

 
 
4
3
,

 
 
7
5
0
5
,

 
 
1
,

 
 
1
5
2
7
4
,

 
 
2
4
9
,

 
 
1
7
7
,

 
 
1
0
8
9
,

 
 
1
0
3
3
,

 
 
2
,

 
 
1
2
4
,

 
 
5
5
,

 
 
2
3
4
,

 
 
1
5
,

 
 
1
3
]
,

 
[
1
6
0
0
,
 
2
1
,
 
1
,
 
2
4
7
,
 
1
0
6
5
7
0
,
 
9
1
2
,
 
9
1
9
,
 
8
5
0
,
 
9
5
5
,
 
5
3
5
,
 
2
1
6
]
,

 
[
9
5
,

 
 
2
6
,

 
 
2
7
,

 
 
9
6
8
,

 
 
4
3
,

 
 
1
6
,

 
 
4
,

 
 
1
9
7
1
,

 
 
7
,

 
 
5
9
7
,

 
 
1
5
,

 
 
1
,

 
 
2
3
8
3
0
,

 
 
6
4
,

 
 
8
3
2
,

 
 
8
3
,

 
 
1
5
,

 
 
7
8
3
,

 
 
1
7
1
2
,

 
 
8
4
,

 
 
6
3
,

 
 
8
8
,

 
 
1
4
6
,

 
 
7
1
,

 
 
4
,

 
 
6
4
1
,

 
 
3
,

 
 
3
1
1
8
,

 
 
1
3
5
6
,

 
 
1
3
0
,

 
 
3
,

 
 
8
8
,

 
 
5
9
,

 
 
9
4
,

 
 
1
4
6
,

 
 
4
6
8
8
,

 
 
2
1
3
8
,

 
 
8
,

 
 
1
5
3
,

 
 
4
1
,

 
 
5
,

 
 
1
7
9
,

 
 
3
,

 
 
1
6
4
6
,

 
 
2
,

 
 
1
0
9
,

 
 
4
,

 
 
2
6
0
,

 
 
7
2
,

 
 
4
7
,

 
 
3
,

 
 
1
4
1
,

 
 
7
5
,

 
 
5
1
,

 
 
4
9
,

 
 
5
9
,

 
 
7
0
,

 
 
3
8
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
5
,

 
 
7
,

 
 
4
8
,

 
 
1
1
,

 
 
4
8
,

 
 
9
,

 
 
2
2
5
3
,

 
 
6
3
0
3
,

 
 
5
8
3
3
,

 
 
8
2
5
2
]
,

 
[
2
9
6
,

 
 
7
,

 
 
3
4
,

 
 
2
2
6
,

 
 
2
,

 
 
9
4
,

 
 
1
1
,

 
 
2
,

 
 
1
1
2
4
,

 
 
6
9
1
,

 
 
1
0
,

 
 
1
,

 
 
6
0
2
,

 
 
1
1
3
,

 
 
1
6
0
6
7
8
,

 
 
3
8
6
,

 
 
9
,

 
 
1
2
,

 
 
3
0
3
8
,

 
 
1
2
9
4
,

 
 
9
2
,

 
 
1
5
8
9
1
,

 
 
5
6
,

 
 
2
6
9
,

 
 
1
1
4
,

 
 
5
,

 
 
8
4
,

 
 
1
,

 
 
1
0
5
,

 
 
1
5
,

 
 
9
2
,

 
 
1
0
2
7
,

 
 
5
,

 
 
7
2
5
9
,

 
 
1
1
,

 
 
3
9
7
,

 
 
5
8
,

 
 
4
6
9
,

 
 
2
,

 
 
1
5
6
,

 
 
3
5
,

 
 
3
8
,

 
 
1
5
8
9
1
,

 
 
1
,

 
 
1
0
1
5
,

 
 
4
2
,

 
 
5
7
,

 
 
6
2
6
,

 
 
1
0
,

 
 
1
5
0
,

 
 
1
6
5
,

 
 
1
3
5
,

 
 
1
,

 
 
1
9
6
9
,

 
 
3
,

 
 
1
1
,

 
 
4
0
,

 
 
1
,

 
 
1
3
9
,

 
 
1
9
0
,

 
 
8
,

 
 
1
3
3
,

 
 
1
2
,

 
 
8
3
,

 
 
1
5
,

 
 
5
9
0
,

 
 
1
8
7
6
,

 
 
5
,

 
 
2
1
7
6
,

 
 
6
9
7
,

 
 
2
0
8
1
,

 
 
1
0
6
5
7
1
]
,

 
[
1
7
8
,
 
7
2
8
,
 
4
,
 
2
4
0
,
 
3
7
8
,
 
9
9
1
,
 
5
3
3
6
,
 
5
9
8
4
,
 
7
0
4
4
]
,

 
[
5
0
,

 
 
6
7
8
1
,

 
 
3
7
,

 
 
1
7
,

 
 
2
,

 
 
7
4
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
4
,

 
 
2
7
2
,

 
 
5
4
9
5
,

 
 
5
,

 
 
2
2
,

 
 
3
6
,

 
 
3
1
,

 
 
5
4
,

 
 
1
2
0
,

 
 
4
0
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
1
2
7
1
,

 
 
1
0
3
,

 
 
6
,

 
 
5
2
0
,

 
 
7
4
,

 
 
2
2
1
,

 
 
2
,

 
 
1
1
1
3
4
,

 
 
1
,

 
 
9
4
0
,

 
 
1
3
4
,

 
 
6
]
,

 
[
6
2
0
2
,

 
 
4
5
3
3
,

 
 
1
0
4
0
,

 
 
2
0
8
,

 
 
5
7
3
,

 
 
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
1
2
0
7
,

 
 
1
8
3
8
,

 
 
8
5
,

 
 
3
2
9
,

 
 
8
4
4
,

 
 
6
1
1
8
,

 
 
5
,

 
 
8
4
4
,

 
 
2
4
4
,

 
 
8
0
0
0
,

 
 
1
8
5
,

 
 
4
0
,

 
 
4
1
,

 
 
8
,

 
 
2
,

 
 
1
1
,

 
 
1
0
,

 
 
1
,

 
 
3
3
8
,

 
 
6
0
7
8
7
,

 
 
1
1
0
7
,

 
 
4
,

 
 
8
4
4
,

 
 
3
4
5
,

 
 
6
1
1
8
,

 
 
4
5
3
3
,

 
 
5
,

 
 
8
4
4
,

 
 
4
5
3
3
,

 
 
3
2
1
4
,

 
 
3
4
5
,

 
 
1
6
8
9
7
,

 
 
2
,

 
 
4
7
2
7
,

 
 
1
3
,

 
 
9
3
9
,

 
 
8
,

 
 
9
7
4
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
8
5
,

 
 
1
2
5
,

 
 
1
5
4
0
,

 
 
2
4
,

 
 
6
9
4
0
,

 
 
2
5
5
1
,

 
 
2
1
0
6
,

 
 
1
8
6
3
,

 
 
2
2
4
5
,

 
 
1
,

 
 
1
3
9
,

 
 
2
6
7
,

 
 
4
5
,

 
 
1
0
3
8
,

 
 
1
3
,

 
 
4
1
2
,

 
 
1
7
,

 
 
5
3
8
7
,

 
 
4
5
,

 
 
2
3
6
,

 
 
1
7
5
1
,

 
 
1
5
1
,

 
 
6
1
1
8
,

 
 
5
,

 
 
1
2
7
,

 
 
1
5
1
,

 
 
1
6
8
9
7
,

 
 
2
1
3
6
,

 
 
4
5
4
5
,

 
 
4
7
3
9
,

 
 
5
3
1
0
]
,

 
[
4
1
,
 
1
8
,
 
1
3
0
,
 
2
1
5
4
,
 
3
2
1
7
7
,
 
1
0
,
 
1
3
,
 
4
9
4
3
9
]
,

 
[
9
,

 
 
2
6
2
,

 
 
4
8
8
,

 
 
1
,

 
 
1
1
5
,

 
 
4
0
7
,

 
 
8
,

 
 
2
0
1
,

 
 
8
,

 
 
1
6
0
6
7
9
,

 
 
1
3
,

 
 
3
3
6
7
7
,

 
 
2
0
,

 
 
4
0
7
,

 
 
4
9
,

 
 
3
9
6
9
6
,

 
 
1
,

 
 
2
6
7
,

 
 
5
,

 
 
3
9
7
,

 
 
1
,

 
 
2
3
,

 
 
4
6
2
,

 
 
7
5
0
,

 
 
2
,

 
 
1
5
6
,

 
 
3
7
3
,

 
 
3
7
,

 
 
7
8
,

 
 
2
4
5
,

 
 
3
9
4
6
,

 
 
1
6
,

 
 
4
4
5
,

 
 
1
7
,

 
 
4
,

 
 
1
8
8
0
,

 
 
5
,

 
 
1
0
1
3
,

 
 
5
8
9
2
,

 
 
3
3
,

 
 
4
0
,

 
 
1
3
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
3
3
,

 
 
1
,

 
 
2
0
6
0
,

 
 
3
,

 
 
2
0
,

 
 
8
7
1
,

 
 
1
1
,

 
 
5
5
7
,

 
 
1
7
,

 
 
6
,

 
 
1
0
8
,

 
 
1
,

 
 
7
1
4
5
,

 
 
2
,

 
 
9
4
,

 
 
3
1
,

 
 
5
9
1
,

 
 
1
1
,

 
 
9
,

 
 
3
9
4
6
,

 
 
8
,

 
 
1
6
6
3
,

 
 
1
,

 
 
7
6
0
0
,

 
 
1
0
9
6
,

 
 
5
,

 
 
6
2
8
,

 
 
9
,

 
 
1
1
5
,

 
 
1
4
5
2
,

 
 
1
9
4
2
1
,

 
 
3
1
5
,

 
 
5
,

 
 
5
2
6
,

 
 
7
3
,

 
 
2
,

 
 
7
8
,

 
 
2
4
5
,

 
 
1
3
,

 
 
8
6
1
0
,

 
 
1
6
,

 
 
1
5
,

 
 
1
,

 
 
2
9
]
,

 
[
2
1
6
,

 
 
1
1
,

 
 
1
0
8
2
,

 
 
2
4
7
,

 
 
6
9
,

 
 
1
1
4
,

 
 
1
1
,

 
 
1
8
0
2
,

 
 
1
8
,

 
 
5
4
,

 
 
8
,

 
 
6
9
3
,

 
 
5
5
3
5
,

 
 
6
7
0
5
,

 
 
5
,

 
 
8
4
,

 
 
1
1
,

 
 
1
8
0
2
,

 
 
1
3
3
,

 
 
5
4
,

 
 
8
,

 
 
1
,

 
 
6
2
9
,

 
 
5
5
3
5
,

 
 
7
,

 
 
7
5
0
6
,

 
 
1
,

 
 
4
4
2
,

 
 
2
2
8
,

 
 
2
,

 
 
6
2
9
,

 
 
5
5
3
5
,

 
 
6
9
,

 
 
5
3
,

 
 
1
8
,

 
 
1
3
0
4
,

 
 
2
3
7
,

 
 
5
9
2
,

 
 
7
5
2
,

 
 
1
7
,

 
 
1
6
8
2
,

 
 
2
,

 
 
7
5
2
,

 
 
9
1
,

 
 
5
9
2
,

 
 
2
5
,

 
 
3
5
1
,

 
 
2
,

 
 
1
6
,

 
 
5
9
2
,

 
 
1
0
6
5
7
2
,

 
 
1
0
6
5
7
3
,

 
 
4
5
2
,

 
 
9
1
2
,

 
 
1
0
0
1
,

 
 
5
4
7
9
,

 
 
6
4
8
]
,

 
[
5
,
 
6
,
 
6
5
1
,
 
2
0
,
 
8
5
,
 
2
,
 
5
2
5
]
,

 
[
3
0
8
2
4
,

 
 
9
7
4
,

 
 
1
8
3
7
7
,

 
 
1
7
8
,

 
 
3
0
8
2
4
,

 
 
2
7
,

 
 
9
7
4
,

 
 
1
8
3
7
7
,

 
 
7
1
,

 
 
1
3
9
1
4
,

 
 
1
7
,

 
 
2
,

 
 
7
8
,

 
 
1
1
,

 
 
2
3
9
,

 
 
2
5
1
8
,

 
 
1
,

 
 
2
3
,

 
 
1
7
,

 
 
9
1
,

 
 
3
5
,

 
 
4
,

 
 
2
2
2
,

 
 
9
7
3
,

 
 
6
1
,

 
 
1
2
5
0
9
,

 
 
1
1
,

 
 
5
0
2
,

 
 
1
6
6
9
,

 
 
5
,

 
 
6
9
6
,

 
 
1
5
7
7
,

 
 
3
3
,

 
 
1
,

 
 
2
7
9
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
4
,

 
 
5
4
,

 
 
3
0
8
2
4
,

 
 
9
3
0
3
,

 
 
2
,

 
 
2
8
3
9
,

 
 
4
4
8
,

 
 
1
,

 
 
3
7
4
,

 
 
1
8
3
7
7
,

 
 
4
2
3
6
7
]
,

 
[
8
9
9
,

 
 
2
5
9
2
,

 
 
9
6
3
4
,

 
 
3
9
1
,

 
 
3
2
,

 
 
1
6
0
6
8
0
,

 
 
1
8
0
,

 
 
2
0
5
,

 
 
6
2
0
0
,

 
 
1
7
1
,

 
 
2
0
9
,

 
 
1
,

 
 
2
8
,

 
 
1
2
,

 
 
2
0
,

 
 
1
9
7
7
,

 
 
1
3
4
4
,

 
 
5
,

 
 
1
0
9
7
6
,

 
 
2
3
1
2
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
2
4
1
1
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
1
6
0
6
8
1
,

 
 
3
9
1
2
,

 
 
3
2
,

 
 
1
,

 
 
2
7
0
7
,

 
 
9
1
6
,

 
 
5
,

 
 
2
7
0
7
,

 
 
8
6
5
1
,

 
 
7
4
4
5
,

 
 
4
,

 
 
1
6
8
3
,

 
 
3
9
,

 
 
1
4
,

 
 
1
6
,

 
 
2
5
7
,

 
 
2
,

 
 
4
,

 
 
1
6
0
6
8
2
,

 
 
8
0
,

 
 
1
1
,

 
 
4
2
,

 
 
4
3
0
,

 
 
2
3
1
6
9
,

 
 
1
2
,

 
 
1
6
5
4
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
1
6
6
4
5
,

 
 
1
0
,

 
 
2
6
7
5
4
,

 
 
1
0
6
5
7
4
,

 
 
7
2
1
,

 
 
5
9
,

 
 
1
9
,

 
 
1
1
,

 
 
1
,

 
 
1
6
0
1
,

 
 
8
,

 
 
1
,

 
 
8
6
2
,

 
 
3
,

 
 
6
0
,

 
 
2
5
9
6
,

 
 
3
3
6
7
8
,

 
 
6
2
,

 
 
1
0
8
,

 
 
2
,

 
 
1
7
7
4
9
,

 
 
1
,

 
 
2
7
0
7
,

 
 
7
8
8
6
,

 
 
1
1
,

 
 
4
2
,

 
 
4
4
,

 
 
2
6
1
,

 
 
8
7
0
,

 
 
5
,

 
 
5
1
6
,

 
 
1
7
4
,

 
 
1
1
,

 
 
8
,

 
 
1
0
6
5
7
5
,

 
 
4
,

 
 
7
2
6
,

 
 
3
,

 
 
1
9
7
7
,

 
 
5
,

 
 
1
4
2
2
,

 
 
4
7
9
,

 
 
1
3
3
6
,

 
 
5
,

 
 
3
9
1
,

 
 
3
2
,

 
 
1
0
1
9
,

 
 
1
5
4
7
4
,

 
 
6
3
0
,

 
 
2
,

 
 
7
0
6
,

 
 
3
0
7
7
,

 
 
5
,

 
 
4
7
7
9
,

 
 
1
0
,

 
 
4
2
3
6
8
,

 
 
6
,

 
 
3
9
,

 
 
4
0
3
,

 
 
2
,

 
 
1
6
,

 
 
2
5
7
,

 
 
2
,

 
 
2
4
1
1
,

 
 
1
7
,

 
 
1
2
8
,

 
 
1
7
,

 
 
6
,

 
 
1
0
8
,

 
 
2
6
,

 
 
1
3
,

 
 
2
2
8
,

 
 
9
0
,

 
 
1
9
9
,

 
 
1
0
3
8
,

 
 
6
0
,

 
 
2
7
0
7
,

 
 
1
3
7
5
0
,

 
 
5
,

 
 
7
4
4
5
,

 
 
6
2
,

 
 
8
6
,

 
 
2
1
8
9
,

 
 
4
7
7
9
,

 
 
3
0
7
7
,

 
 
5
,

 
 
1
5
8
9
2
,

 
 
8
6
,

 
 
1
0
8
7
,

 
 
3
2
,

 
 
2
8
4
,

 
 
5
4
4
8
,

 
 
3
,

 
 
1
,

 
 
4
6
8
5
,

 
 
1
6
8
3
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
2
9
5
1
,

 
 
3
,

 
 
8
8
,

 
 
1
1
8
,

 
 
5
,

 
 
4
9
4
4
0
,

 
 
2
0
,

 
 
1
4
2
2
,

 
 
1
7
,

 
 
1
2
8
,

 
 
1
7
,

 
 
6
,

 
 
3
9
,

 
 
6
,

 
 
4
5
,

 
 
3
4
0
3
,

 
 
2
4
1
,

 
 
3
3
6
7
9
]
,

 
[
1
5
2
,
 
4
3
0
5
,
 
1
6
4
5
,
 
1
7
,
 
1
3
8
4
,
 
1
1
3
,
 
6
6
,
 
1
6
9
]
,

 
[
1
0
6
5
7
6
,

 
 
8
9
3
6
,

 
 
7
8
,

 
 
8
,

 
 
1
,

 
 
1
0
0
4
2
,

 
 
6
0
4
,

 
 
1
0
6
5
7
6
,

 
 
8
9
3
6
,

 
 
3
2
9
,

 
 
2
8
1
,

 
 
1
6
0
6
8
3
,

 
 
5
1
,

 
 
1
8
,

 
 
2
0
7
3
,

 
 
8
6
8
0
,

 
 
5
1
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
7
6
,

 
 
3
,

 
 
4
9
4
4
1
,

 
 
2
6
,

 
 
9
,

 
 
2
4
,

 
 
3
6
2
2
,

 
 
5
2
1
,

 
 
2
5
0
,

 
 
6
3
3
,

 
 
1
9
9
9
,

 
 
2
8
8
3
]
,

 
[
7
1
0
,

 
 
2
1
6
,

 
 
4
2
,

 
 
2
5
9
,

 
 
4
1
9
,

 
 
7
4
,

 
 
3
5
4
,

 
 
1
,

 
 
5
3
6
,

 
 
5
3
,

 
 
1
8
,

 
 
4
0
,

 
 
1
3
1
,

 
 
3
1
,

 
 
2
0
3
,

 
 
7
7
0
6
,

 
 
2
1
,

 
 
8
5
,

 
 
5
,

 
 
8
5
,

 
 
3
6
6
1
,

 
 
2
2
,

 
 
7
,

 
 
8
6
,

 
 
2
,

 
 
3
6
6
1
,

 
 
1
5
7
,

 
 
1
0
,

 
 
8
5
,

 
 
4
3
,

 
 
7
,

 
 
1
6
,

 
 
1
6
0
6
8
4
,

 
 
5
,

 
 
6
7
4
8
,

 
 
1
0
,

 
 
2
1
0
8
5
,

 
 
2
9
5
3
,

 
 
5
8
0
,

 
 
3
3
1
,

 
 
3
1
5
,

 
 
3
7
,

 
 
3
6
6
1
,

 
 
6
1
8
1
,

 
 
1
0
,

 
 
8
5
,

 
 
2
5
,

 
 
4
5
,

 
 
7
,

 
 
6
6
,

 
 
6
1
1
6
,

 
 
5
,

 
 
1
8
7
3
0
,

 
 
3
6
6
1
,

 
 
1
5
7
,

 
 
1
0
,

 
 
8
5
,

 
 
9
,

 
 
8
,

 
 
7
,

 
 
9
4
,

 
 
4
6
7
0
,

 
 
5
,

 
 
4
6
7
0
,

 
 
5
,

 
 
8
4
,

 
 
6
9
8
4
,

 
 
6
9
,

 
 
7
,

 
 
2
4
,

 
 
1
4
,

 
 
3
5
1
,

 
 
3
3
3
,

 
 
7
7
2
,

 
 
1
9
0
5
7
,

 
 
1
,

 
 
6
3
0
4
,

 
 
8
0
0
1
,

 
 
5
0
0
,

 
 
2
2
,

 
 
1
1
,

 
 
8
6
,

 
 
4
4
1
,

 
 
1
2
,

 
 
8
5
6
2
,

 
 
2
5
,

 
 
1
0
5
,

 
 
2
,

 
 
3
6
6
1
,

 
 
6
1
8
1
,

 
 
5
,

 
 
1
5
8
9
3
,

 
 
1
0
,

 
 
8
5
,

 
 
1
0
0
,

 
 
1
3
,

 
 
2
6
8
3
,

 
 
8
5
4
,

 
 
5
1
7
3
,

 
 
2
,

 
 
3
5
4
,

 
 
1
7
,

 
 
5
3
,

 
 
7
0
,

 
 
1
1
,

 
 
2
1
2
6
,

 
 
9
0
4
2
,

 
 
1
0
5
1
,

 
 
3
5
5
1
,

 
 
2
,

 
 
9
4
5
8
,

 
 
2
8
6
4
9
,

 
 
5
,

 
 
1
7
7
6
2
,

 
 
5
,

 
 
3
6
7
4
,

 
 
4
8
3
1
,

 
 
5
3
3
7
,

 
 
1
1
1
,

 
 
1
7
,

 
 
4
9
1
5
,

 
 
1
7
8
2
,

 
 
8
6
4
,

 
 
8
6
4
,

 
 
8
5
0
]
,

 
[
7
,

 
 
1
0
8
,

 
 
2
,

 
 
1
5
5
2
,

 
 
6
,

 
 
4
,

 
 
1
1
0
5
8
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
1
4
0
8
,

 
 
5
4
,

 
 
7
,

 
 
2
2
0
,

 
 
4
5
,

 
 
1
6
,

 
 
1
2
5
1
0
,

 
 
2
,

 
 
1
,

 
 
2
6
4
4
,

 
 
9
7
5
,

 
 
3
,

 
 
3
3
6
8
0
,

 
 
1
3
7
,

 
 
8
8
2
8
,

 
 
2
1
5
9
,

 
 
1
,

 
 
2
3
,

 
 
1
4
4
,

 
 
1
,

 
 
8
6
0
,

 
 
1
2
1
1
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
4
4
,

 
 
2
4
2
4
,

 
 
6
7
2
5
,

 
 
7
,

 
 
5
9
3
,

 
 
3
8
1
,

 
 
2
,

 
 
3
7
,

 
 
3
8
,

 
 
2
4
,

 
 
8
3
3
,

 
 
2
,

 
 
1
6
,

 
 
2
0
7
,

 
 
2
1
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
6
,

 
 
8
6
,

 
 
1
6
4
1
,

 
 
1
,

 
 
1
1
4
,

 
 
2
,

 
 
1
2
6
,

 
 
5
2
5
,

 
 
3
0
,

 
 
2
1
4
,

 
 
3
,

 
 
3
8
,

 
 
8
,

 
 
1
1
,

 
 
1
6
5
,

 
 
2
,

 
 
1
5
9
,

 
 
3
6
,

 
 
3
1
,

 
 
1
,

 
 
1
2
1
6
,

 
 
3
,

 
 
3
0
,

 
 
2
0
6
0
,

 
 
1
3
4
,

 
 
6
,

 
 
3
0
8
2
5
,

 
 
1
8
7
3
1
]
,

 
[
7
,

 
 
1
9
,

 
 
2
,

 
 
2
8
9
3
,

 
 
8
0
,

 
 
1
7
3
9
,

 
 
1
,

 
 
3
4
7
2
,

 
 
6
4
2
,

 
 
6
8
0
,

 
 
4
8
4
,

 
 
2
1
,

 
 
7
4
2
,

 
 
3
7
4
5
,

 
 
7
3
,

 
 
2
,

 
 
9
2
,

 
 
3
0
8
2
6
,

 
 
1
0
,

 
 
5
7
3
7
,

 
 
4
1
7
1
,

 
 
9
,

 
 
4
9
4
4
2
,

 
 
8
,

 
 
9
2
9
,

 
 
1
9
1
,

 
 
3
5
1
,

 
 
1
5
,

 
 
1
,

 
 
1
3
9
,

 
 
3
0
3
,

 
 
8
0
,

 
 
5
5
1
0
,

 
 
1
8
,

 
 
9
1
,

 
 
8
1
0
9
,

 
 
3
2
2
,

 
 
5
,

 
 
4
3
2
,

 
 
5
6
8
3
,

 
 
9
1
,

 
 
1
8
8
,

 
 
3
2
,

 
 
5
7
3
7
,

 
 
1
0
,

 
 
3
3
2
0
,

 
 
1
1
,

 
 
1
8
1
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
4
2
1
1
,

 
 
3
3
2
0
,

 
 
8
3
0
1
,

 
 
8
9
4
,

 
 
2
0
4
8
,

 
 
1
5
,

 
 
1
,

 
 
6
8
0
,

 
 
4
8
4
,

 
 
5
,

 
 
9
6
,

 
 
7
5
,

 
 
3
1
,

 
 
1
,

 
 
1
0
3
1
,

 
 
3
,

 
 
1
4
5
2
,

 
 
8
6
,

 
 
3
8
4
2
,

 
 
3
5
,

 
 
1
,

 
 
1
0
5
0
7
,

 
 
1
3
1
,

 
 
3
2
,

 
 
1
,

 
 
2
4
3
3
,

 
 
6
6
5
3
,

 
 
4
8
4
,

 
 
1
1
2
0
8
,

 
 
7
5
4
,

 
 
2
,

 
 
1
6
,

 
 
8
7
8
4
,

 
 
9
,

 
 
2
1
8
,

 
 
1
8
,

 
 
5
3
7
7
,

 
 
2
2
0
3
,

 
 
6
9
,

 
 
3
,

 
 
1
6
3
,

 
 
4
8
,

 
 
1
3
,

 
 
3
0
,

 
 
7
3
5
,

 
 
9
9
,

 
 
4
,

 
 
1
0
2
,

 
 
9
8
,

 
 
2
6
7
5
5
,

 
 
3
3
,

 
 
1
,

 
 
8
7
8
5
,

 
 
5
9
7
,

 
 
1
0
,

 
 
3
3
6
8
1
,

 
 
3
0
0
6
,

 
 
1
0
,

 
 
4
,

 
 
8
9
7
,

 
 
3
,

 
 
7
4
7
6
,

 
 
3
,

 
 
5
7
3
7
,

 
 
2
5
,

 
 
6
3
8
6
,

 
 
4
,

 
 
4
3
2
,

 
 
1
9
3
7
,

 
 
3
7
4
5
,

 
 
1
9
8
2
0
,

 
 
2
5
0
6
,

 
 
6
0
8
8
,

 
 
6
5
7
7
,

 
 
5
6
6
8
,

 
 
9
1
9
,

 
 
1
1
6
5
1
,

 
 
4
5
5
4
9
]
,

 
[
4
,

 
 
2
2
1
1
,

 
 
1
1
2
2
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
2
,

 
 
9
0
2
,

 
 
2
,

 
 
3
7
,

 
 
2
6
7
1
,

 
 
8
2
,

 
 
3
0
7
6
,

 
 
2
0
0
,

 
 
5
,

 
 
1
4
,

 
 
7
7
,

 
 
3
0
7
6
]
,

 
[
2
8
4
,

 
 
2
2
4
,

 
 
2
7
2
2
,

 
 
1
,

 
 
4
2
8
,

 
 
7
5
,

 
 
1
8
,

 
 
1
5
,

 
 
1
,

 
 
4
4
2
,

 
 
9
8
,

 
 
5
,

 
 
2
8
7
3
,

 
 
2
6
,

 
 
1
,

 
 
3
6
,

 
 
3
1
6
,

 
 
3
2
8
8
,

 
 
1
8
,

 
 
1
3
0
2
,

 
 
3
2
4
8
,

 
 
3
2
,

 
 
2
7
,

 
 
6
5
5
1
,

 
 
6
4
7
5
,

 
 
1
5
,

 
 
1
1
4
7
6
,

 
 
5
,

 
 
1
0
0
7
,

 
 
1
3
,

 
 
1
6
0
6
8
5
,

 
 
2
8
6
,

 
 
1
,

 
 
1
3
9
,

 
 
4
6
]
,

 
[
1
1
5
6
6
,

 
 
7
6
1
,

 
 
1
7
,

 
 
7
1
6
,

 
 
1
3
3
0
,

 
 
7
,

 
 
8
1
,

 
 
3
7
1
,

 
 
1
6
0
6
8
6
,

 
 
5
,

 
 
2
,

 
 
1
6
,

 
 
3
7
1
,

 
 
1
7
1
0
,

 
 
4
9
0
5
,

 
 
9
,

 
 
6
,

 
 
4
3
,

 
 
2
5
6
,

 
 
1
,

 
 
1
1
6
,

 
 
6
2
2
9
,

 
 
2
,

 
 
1
,

 
 
1
2
5
1
1
,

 
 
5
4
8
0
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
4
,

 
 
2
4
2
,

 
 
8
0
3
3
,

 
 
2
4
8
,

 
 
1
,

 
 
4
3
5
6
,

 
 
2
5
,

 
 
3
9
7
8
,

 
 
1
1
,

 
 
1
2
,

 
 
6
1
7
,

 
 
2
1
2
,

 
 
6
,

 
 
1
8
7
,

 
 
1
,

 
 
4
5
5
5
0
,

 
 
3
,

 
 
3
4
6
,

 
 
4
5
6
,

 
 
1
,

 
 
2
2
1
0
7
,

 
 
5
,

 
 
6
1
,

 
 
5
4
8
0
,

 
 
5
4
,

 
 
7
,

 
 
1
3
6
,

 
 
2
0
1
2
,

 
 
1
3
8
0
,

 
 
6
1
8
,

 
 
5
4
8
0
,

 
 
1
9
,

 
 
5
7
,

 
 
8
1
9
,

 
 
2
,

 
 
1
4
2
5
,

 
 
1
5
,

 
 
6
1
,

 
 
7
6
1
,

 
 
2
8
,

 
 
1
2
4
,

 
 
1
9
8
2
1
,

 
 
7
1
8
,

 
 
3
4
6
,

 
 
1
7
7
,

 
 
4
3
8
,

 
 
4
8
0
0
,

 
 
2
7
3
2
,

 
 
2
1
7
,

 
 
5
,

 
 
2
0
8
,

 
 
7
,

 
 
8
1
,

 
 
1
8
6
,

 
 
9
,

 
 
2
0
,

 
 
2
0
7
8
,

 
 
2
4
,

 
 
1
4
,

 
 
4
7
7
5
,

 
 
1
1
,

 
 
2
4
,

 
 
4
,

 
 
6
7
3
,

 
 
1
7
1
6
8
,

 
 
4
6
0
,

 
 
1
5
,

 
 
2
0
,

 
 
2
2
3
,

 
 
5
0
,

 
 
1
0
7
2
,

 
 
1
9
1
,

 
 
2
,

 
 
5
6
3
,

 
 
1
3
,

 
 
1
0
,

 
 
1
8
5
6
,

 
 
1
1
7
7
]
,

 
[
6
0
3
,

 
 
1
0
2
4
,

 
 
1
1
9
8
,

 
 
2
1
6
,

 
 
1
,

 
 
6
2
7
,

 
 
3
3
,

 
 
1
1
3
,

 
 
1
8
5
3
,

 
 
1
9
5
,

 
 
2
,

 
 
3
7
2
7
,

 
 
1
5
,

 
 
1
4
3
8
,

 
 
9
,

 
 
1
,

 
 
6
1
,

 
 
1
0
9
,

 
 
8
,

 
 
5
2
3
,

 
 
3
6
,

 
 
6
,

 
 
1
2
2
,

 
 
2
,

 
 
9
8
4
,

 
 
9
,

 
 
1
,

 
 
6
1
,

 
 
1
0
9
,

 
 
8
,

 
 
5
2
3
,

 
 
1
0
1
1
,

 
 
1
8
4
,

 
 
1
2
1
,

 
 
4
,

 
 
3
5
9
,

 
 
6
6
,

 
 
2
5
5
,

 
 
5
3
,

 
 
1
8
,

 
 
7
7
8
,

 
 
9
,

 
 
1
0
6
5
7
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
6
0
6
8
7
,

 
 
8
,

 
 
1
,

 
 
1
0
9
,

 
 
3
,

 
 
1
,

 
 
6
5
9
,

 
 
1
0
,

 
 
1
8
2
2
,

 
 
2
6
,

 
 
1
3
,

 
 
1
9
1
9
,

 
 
7
6
,

 
 
2
,

 
 
1
6
,

 
 
6
7
9
,

 
 
4
3
8
4
,

 
 
1
6
0
6
8
8
,

 
 
6
9
8
2
5
,

 
 
1
1
,

 
 
1
9
5
,

 
 
2
,

 
 
3
7
,

 
 
5
2
6
,

 
 
5
8
,

 
 
4
8
,

 
 
6
8
,

 
 
7
3
5
,

 
 
9
3
,

 
 
6
8
,

 
 
1
4
4
8
,

 
 
3
8
,

 
 
3
4
,

 
 
6
,

 
 
6
5
,

 
 
6
6
,

 
 
7
4
,

 
 
5
9
1
1
,

 
 
8
,

 
 
1
,

 
 
1
1
9
5
5
,

 
 
3
,

 
 
1
,

 
 
1
6
0
6
8
9
,

 
 
1
0
,

 
 
1
3
,

 
 
6
5
9
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
8
8
5
,

 
 
1
1
0
5
9
,

 
 
6
9
9
,

 
 
6
4
8
]
,

 
[
7
1
9
6
,

 
 
1
2
0
,

 
 
1
2
,

 
 
1
2
3
,

 
 
6
1
5
5
,

 
 
3
,

 
 
6
5
7
1
,

 
 
1
0
6
5
7
8
,

 
 
1
0
6
5
7
9
,

 
 
4
7
2
,

 
 
9
5
,

 
 
1
2
,

 
 
1
5
1
6
,

 
 
1
2
3
,

 
 
6
1
5
5
,

 
 
3
,

 
 
6
5
7
1
,

 
 
1
0
6
5
7
8
,

 
 
1
0
6
5
7
9
,

 
 
4
7
2
,

 
 
7
,

 
 
6
5
8
,

 
 
9
,

 
 
1
,

 
 
6
8
0
6
,

 
 
7
3
1
,

 
 
2
9
,

 
 
5
3
4
,

 
 
1
8
1
,

 
 
2
2
0
1
,

 
 
6
2
,

 
 
3
3
3
,

 
 
1
,

 
 
1
7
4
,

 
 
3
6
,

 
 
1
,

 
 
2
7
2
,

 
 
6
9
1
,

 
 
8
,

 
 
2
2
1
2
,

 
 
2
2
,

 
 
6
,

 
 
9
0
,

 
 
1
4
,

 
 
4
7
1
,

 
 
1
3
,

 
 
5
0
9
,

 
 
2
2
5
,

 
 
8
4
,

 
 
6
,

 
 
4
5
,

 
 
1
2
2
,

 
 
2
,

 
 
2
2
0
1
,

 
 
1
,

 
 
2
4
5
1
,

 
 
3
,

 
 
1
,

 
 
2
7
2
,

 
 
2
2
,

 
 
6
,

 
 
3
8
0
6
,

 
 
1
1
,

 
 
3
1
,

 
 
4
,

 
 
4
2
1
,

 
 
8
4
,

 
 
4
,

 
 
1
6
9
,

 
 
2
,

 
 
1
,

 
 
4
2
1
,

 
 
3
1
,

 
 
5
4
,

 
 
1
1
,

 
 
2
4
,

 
 
5
5
5
,

 
 
8
4
0
,

 
 
2
1
,

 
 
4
,

 
 
7
8
8
5
,

 
 
3
,

 
 
9
,

 
 
4
7
0
8
,

 
 
6
6
7
,

 
 
3
,

 
 
8
2
,

 
 
3
,

 
 
1
0
4
,

 
 
1
7
4
,

 
 
8
,

 
 
8
2
8
,

 
 
1
8
2
1
,

 
 
1
0
5
,

 
 
1
9
7
,

 
 
2
2
,

 
 
1
,

 
 
2
7
2
,

 
 
2
2
6
7
,

 
 
8
,

 
 
2
7
1
,

 
 
3
1
,

 
 
1
,

 
 
4
7
0
8
,

 
 
2
8
0
3
,

 
 
8
4
,

 
 
9
2
,

 
 
2
7
2
,

 
 
5
6
,

 
 
6
6
,

 
 
1
6
,

 
 
3
5
3
2
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
3
1
0
,

 
 
1
,

 
 
1
2
0
,

 
 
5
0
,

 
 
1
5
2
,

 
 
4
,

 
 
8
2
3
,

 
 
2
7
2
,

 
 
3
6
5
7
,

 
 
2
7
7
,

 
 
2
2
,

 
 
1
,

 
 
5
0
9
,

 
 
1
8
1
,

 
 
1
9
,

 
 
4
7
,

 
 
2
3
7
,

 
 
2
2
,

 
 
6
,

 
 
3
3
3
,

 
 
6
5
1
,

 
 
1
,

 
 
4
8
6
,

 
 
3
0
6
7
,

 
 
2
5
,

 
 
8
2
6
,

 
 
8
4
,

 
 
1
,

 
 
2
7
7
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
9
6
0
,

 
 
1
1
,

 
 
1
8
2
,

 
 
1
,

 
 
2
3
4
0
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
1
,

 
 
3
9
0
,

 
 
1
3
5
9
,

 
 
1
,

 
 
4
3
4
,

 
 
3
3
,

 
 
2
8
,

 
 
3
0
2
,

 
 
8
2
,

 
 
8
2
,

 
 
4
,

 
 
2
7
7
,

 
 
1
1
1
,

 
 
1
7
,

 
 
2
5
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
7
7
0
,

 
 
4
4
0
,

 
 
3
3
,

 
 
2
8
,

 
 
1
2
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
3
0
2
,

 
 
8
2
,

 
 
6
3
,

 
 
2
8
,

 
 
1
2
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
1
2
,

 
 
1
,

 
 
5
1
0
,

 
 
1
6
1
,

 
 
3
,

 
 
2
7
2
,

 
 
7
7
0
,

 
 
9
,

 
 
6
,

 
 
3
9
,

 
 
8
2
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
7
4
4
,

 
 
6
1
,

 
 
1
4
6
6
,

 
 
4
1
1
,

 
 
1
4
6
4
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
2
1
4
6
,

 
 
9
2
,

 
 
1
2
0
,

 
 
5
,

 
 
9
1
7
,

 
 
8
8
,

 
 
1
5
5
,

 
 
6
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
1
4
6
6
,

 
 
6
,

 
 
1
9
,

 
 
7
4
4
,

 
 
3
2
,

 
 
4
5
1
,

 
 
1
3
,

 
 
1
6
9
,

 
 
1
2
5
9
,

 
 
5
,

 
 
4
8
7
2
,

 
 
3
4
4
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
4
7
,

 
 
7
6
6
,

 
 
1
5
1
,

 
 
5
1
,

 
 
1
9
,

 
 
5
7
,

 
 
9
1
7
,

 
 
1
7
,

 
 
9
5
7
,

 
 
1
5
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
1
2
3
,

 
 
8
,

 
 
1
5
0
0
,

 
 
1
8
2
,

 
 
4
,

 
 
2
8
1
,

 
 
2
0
0
,

 
 
1
1
5
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
3
0
2
,

 
 
8
2
,

 
 
8
4
,

 
 
1
,

 
 
1
2
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
1
0
9
,

 
 
8
6
7
,

 
 
1
5
1
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
5
0
,

 
 
2
1
9
,

 
 
8
8
,

 
 
3
3
,

 
 
1
,

 
 
3
9
0
,

 
 
2
7
2
,

 
 
2
5
4
,

 
 
2
9
,

 
 
1
3
4
,

 
 
6
,

 
 
3
4
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
7
3
2
6
,

 
 
7
6
,

 
 
3
,

 
 
3
3
1
4
,

 
 
1
3
,

 
 
4
5
4
,

 
 
1
7
8
]
,

 
[
1
4
2
9
,

 
 
4
4
7
7
,

 
 
9
3
0
4
,

 
 
9
6
4
,

 
 
1
1
4
6
,

 
 
3
2
4
7
,

 
 
9
3
0
4
,

 
 
1
9
,

 
 
7
0
5
,

 
 
1
4
,

 
 
2
0
7
3
,

 
 
2
5
0
4
,

 
 
1
8
4
7
,

 
 
5
6
1
8
,

 
 
5
9
,

 
 
1
6
0
6
9
0
,

 
 
2
5
,

 
 
4
5
4
3
,

 
 
1
4
5
,

 
 
9
,

 
 
4
0
,

 
 
9
3
0
4
,

 
 
9
6
4
,

 
 
1
0
6
5
8
0
,

 
 
9
,

 
 
2
8
5
,

 
 
3
8
0
]
,

 
[
3
4
7
,

 
 
2
2
1
3
,

 
 
1
7
9
2
,

 
 
5
,

 
 
1
5
6
7
,

 
 
1
3
,

 
 
2
9
,

 
 
3
1
,

 
 
1
0
7
,

 
 
1
0
6
5
8
1
,

 
 
1
3
,

 
 
2
9
,

 
 
4
2
,

 
 
5
1
0
,

 
 
3
,

 
 
1
7
2
0
,

 
 
5
,

 
 
4
1
9
6
,

 
 
2
9
5
]
,

 
[
9
2
8
,

 
 
7
,

 
 
3
3
2
,

 
 
2
5
2
8
,

 
 
2
4
,

 
 
6
7
4
9
,

 
 
5
,

 
 
3
5
3
9
,

 
 
2
7
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
5
7
6
,

 
 
5
,

 
 
2
6
7
5
6
,

 
 
3
3
2
2
,

 
 
1
1
,

 
 
7
3
,

 
 
1
5
0
,

 
 
2
5
2
8
,

 
 
4
4
5
,

 
 
1
,

 
 
2
9
,

 
 
1
3
2
7
,

 
 
2
0
8
4
,

 
 
6
3
,

 
 
2
2
,

 
 
1
1
,

 
 
7
9
3
0
]
,

 
[
2
5
0
7
,

 
 
1
9
7
2
,

 
 
1
9
4
8
,

 
 
1
7
8
,

 
 
1
1
6
5
2
,

 
 
7
,

 
 
1
9
,

 
 
3
5
4
0
,

 
 
2
7
,

 
 
2
3
5
0
,

 
 
1
9
7
2
,

 
 
3
,

 
 
1
7
5
,

 
 
1
9
6
2
,

 
 
1
2
8
4
4
,

 
 
7
3
,

 
 
2
5
0
7
,

 
 
3
3
,

 
 
2
8
,

 
 
6
4
5
,

 
 
8
1
3
8
,

 
 
3
,

 
 
7
3
8
,

 
 
2
0
5
,

 
 
2
0
2
0
7
,

 
 
1
0
2
8
,

 
 
9
5
1
,

 
 
2
2
,

 
 
6
,

 
 
1
0
3
,

 
 
1
3
6
,

 
 
1
,

 
 
8
5
,

 
 
2
,

 
 
3
2
8
,

 
 
1
1
,

 
 
1
4
8
,

 
 
1
5
0
,

 
 
1
1
,

 
 
8
0
3
,

 
 
7
6
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
1
5
7
3
,

 
 
9
5
]
,

 
[
5
6
,
 
1
6
,
 
6
5
7
3
,
 
8
3
6
2
1
]
,

 
[
8
,
 
9
,
 
1
4
,
 
4
,
 
3
8
0
,
 
7
3
1
,
 
1
5
,
 
4
,
 
4
2
3
6
9
,
 
2
2
,
 
1
4
,
 
8
4
,
 
9
8
4
,
 
2
,
 
3
7
,
 
3
8
,
 
8
]
,

 
[
6
0
6
,
 
1
9
2
,
 
3
0
,
 
4
6
,
 
2
9
,
 
5
9
5
2
,
 
6
4
8
,
 
2
8
7
7
,
 
1
6
0
,
 
4
1
6
1
]
,

 
[
3
5
8
3
,

 
 
5
4
4
,

 
 
3
0
8
2
7
,

 
 
1
7
8
,

 
 
7
,

 
 
1
2
2
,

 
 
1
3
,

 
 
2
9
,

 
 
3
9
1
,

 
 
3
5
8
3
,

 
 
5
4
4
,

 
 
3
0
8
2
7
,

 
 
1
1
,

 
 
5
3
4
,

 
 
2
0
3
9
,

 
 
2
,

 
 
4
,

 
 
7
0
6
7
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
1
4
0
8
,

 
 
1
5
,

 
 
1
,

 
 
3
1
5
9
,

 
 
3
3
8
,

 
 
1
8
3
7
8
]
,

 
[
9
5
,
 
5
,
 
4
8
2
,
 
1
1
5
,
 
4
1
2
,
 
2
,
 
6
,
 
1
5
5
,
 
8
4
9
,
 
8
5
6
,
 
4
6
,
 
3
5
,
 
1
1
]
,

 
[
5
8
,
 
5
7
4
8
,
 
1
1
0
,
 
1
5
3
5
,
 
6
7
0
,
 
5
5
8
]
,

 
[
1
7
1
,
 
1
9
1
1
,
 
3
0
,
 
1
8
6
6
,
 
7
,
 
7
0
,
 
7
1
,
 
1
5
8
,
 
3
1
,
 
6
4
]
,

 
[
1
4
3
6
,
 
7
,
 
3
4
,
 
1
4
,
 
6
5
,
 
4
,
 
1
1
0
1
,
 
8
,
 
4
,
 
9
8
,
 
4
0
5
]
,

 
[
3
5
2
,

 
 
2
6
,

 
 
9
,

 
 
1
0
0
,

 
 
1
4
,

 
 
5
1
4
,

 
 
2
,

 
 
1
,

 
 
1
7
0
6
,

 
 
9
,

 
 
1
,

 
 
1
0
6
5
8
2
,

 
 
2
5
6
6
,

 
 
4
2
6
6
,

 
 
1
0
,

 
 
2
0
6
9
,

 
 
5
,

 
 
9
0
,

 
 
1
4
,

 
 
1
5
3
1
,

 
 
1
5
7
,

 
 
1
5
1
,

 
 
1
6
0
6
9
1
,

 
 
1
,

 
 
3
2
4
3
,

 
 
1
,

 
 
2
3
,

 
 
1
5
,

 
 
1
6
0
6
9
2
,

 
 
1
4
7
0
,

 
 
6
6
,

 
 
1
0
0
,

 
 
1
4
,

 
 
7
2
2
5
,

 
 
5
5
,

 
 
1
0
3
6
,

 
 
1
5
,

 
 
1
3
]
,

 
[
9
5
,

 
 
9
5
,

 
 
1
2
,

 
 
1
,

 
 
9
5
,

 
 
7
,

 
 
4
9
,

 
 
3
1
7
,

 
 
8
8
,

 
 
1
0
,

 
 
3
0
,

 
 
2
5
8
1
,

 
 
1
5
1
,

 
 
7
,

 
 
2
9
1
,

 
 
2
7
,

 
 
1
0
2
2
,

 
 
5
1
0
,

 
 
3
,

 
 
2
1
7
,

 
 
4
,

 
 
2
0
8
,

 
 
1
5
7
,

 
 
3
3
9
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
0
6
5
8
3
,

 
 
7
,

 
 
1
5
8
0
,

 
 
5
3
,

 
 
4
5
,

 
 
6
3
,

 
 
4
,

 
 
3
5
9
,

 
 
5
8
,

 
 
3
,

 
 
1
1
,

 
 
7
,

 
 
1
8
4
,

 
 
9
4
,

 
 
1
5
8
,

 
 
3
3
1
,

 
 
2
,

 
 
1
3
0
2
,

 
 
1
7
9
2
,

 
 
1
1
,

 
 
2
2
,

 
 
1
1
,

 
 
2
1
5
7
,

 
 
7
,

 
 
2
2
9
,

 
 
3
4
,

 
 
1
1
,

 
 
6
9
,

 
 
3
,

 
 
2
4
0
9
,

 
 
7
,

 
 
4
3
,

 
 
6
6
,

 
 
4
8
,

 
 
2
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
5
2
4
,

 
 
2
7
,

 
 
7
0
9
,

 
 
4
8
9
,

 
 
9
4
4
,

 
 
2
0
2
6
,

 
 
8
,

 
 
2
7
,

 
 
6
3
5
1
,

 
 
5
1
7
,

 
 
3
,

 
 
9
8
,

 
 
5
8
8
,

 
 
6
4
7
]
,

 
[
3
2
0
,
 
2
2
,
 
1
6
4
,
 
5
5
4
,
 
5
3
,
 
1
0
3
,
 
1
2
6
,
 
8
2
,
 
2
0
,
 
1
2
1
]
,

 
[
5
1
2
,

 
 
8
9
0
,

 
 
4
0
,

 
 
1
6
3
9
5
,

 
 
3
3
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
7
,

 
 
3
6
0
,

 
 
4
0
,

 
 
1
6
3
9
5
,

 
 
3
3
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
6
9
,

 
 
5
1
,

 
 
1
8
,

 
 
5
2
8
9
,

 
 
4
9
4
4
3
,

 
 
5
,

 
 
3
9
6
5
,

 
 
4
0
,

 
 
5
0
3
3
,

 
 
9
1
4
4
,

 
 
3
3
,

 
 
3
7
4
1
5
,

 
 
5
6
,

 
 
1
6
,

 
 
3
3
6
5
,

 
 
7
1
9
9
,

 
 
5
,

 
 
1
2
9
5
7
,

 
 
3
1
2
8
,

 
 
4
0
,

 
 
3
7
4
1
5
,

 
 
3
5
3
8
9
,

 
 
4
2
1
2
,

 
 
4
0
,

 
 
3
7
4
1
5
,

 
 
1
8
5
9
,

 
 
9
1
4
4
,

 
 
2
4
4
6
6
,

 
 
4
0
,

 
 
3
7
4
1
5
,

 
 
6
4
9
9
,

 
 
7
,

 
 
8
2
0
,

 
 
9
,

 
 
4
,

 
 
1
2
6
4
,

 
 
1
4
8
4
,

 
 
1
5
,

 
 
1
6
0
6
9
3
,

 
 
1
5
,

 
 
9
8
1
,

 
 
1
1
5
3
,

 
 
1
8
5
,

 
 
3
0
1
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
5
6
,

 
 
1
9
,

 
 
8
3
6
2
2
,

 
 
2
0
1
,

 
 
2
,

 
 
2
1
6
5
,

 
 
9
,

 
 
5
2
8
9
,

 
 
5
0
6
,

 
 
5
0
3
3
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
2
4
9
4
,

 
 
3
5
,

 
 
1
0
8
5
,

 
 
5
,

 
 
5
2
0
5
,

 
 
1
9
4
2
2
,

 
 
9
3
,

 
 
7
8
5
,

 
 
6
4
9
9
,

 
 
3
1
2
8
,

 
 
9
,

 
 
5
2
8
9
,

 
 
5
0
6
,

 
 
1
8
5
9
,

 
 
3
2
2
,

 
 
5
1
2
,

 
 
8
9
0
,

 
 
6
,

 
 
1
6
3
9
5
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
8
,

 
 
1
6
0
6
9
4
,

 
 
9
3
,

 
 
1
6
0
6
9
5
,

 
 
2
0
7
9
,

 
 
5
,

 
 
7
0
0
,

 
 
3
2
2
5
,

 
 
6
1
8
2
,

 
 
3
,

 
 
1
1
5
6
,

 
 
5
6
,

 
 
3
1
2
8
,

 
 
1
0
,

 
 
5
4
9
]
,

 
[
1
7
,

 
 
2
,

 
 
7
9
3
,

 
 
1
2
,

 
 
6
,

 
 
1
8
6
,

 
 
2
2
8
,

 
 
1
7
,

 
 
7
3
0
,

 
 
1
7
,

 
 
7
,

 
 
1
3
6
,

 
 
8
5
,

 
 
1
2
,

 
 
9
,

 
 
6
6
,

 
 
7
,

 
 
8
3
6
2
3
,

 
 
6
9
8
2
6
,

 
 
9
7
0
,

 
 
1
5
4
,

 
 
2
,

 
 
4
2
6
,

 
 
1
2
9
,

 
 
1
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
6
9
8
2
7
,

 
 
1
3
,

 
 
6
1
3
,

 
 
1
0
8
4
,

 
 
4
,

 
 
3
4
8
,

 
 
3
5
,

 
 
6
8
8
1
,

 
 
5
,

 
 
9
2
,

 
 
1
7
9
]
,

 
[
4
1
5
,

 
 
4
6
3
,

 
 
7
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
6
3
,

 
 
3
8
,

 
 
7
5
,

 
 
3
3
2
,

 
 
4
9
5
,

 
 
1
0
4
,

 
 
7
3
,

 
 
1
2
,

 
 
2
9
1
8
,

 
 
4
5
5
,

 
 
3
4
,

 
 
6
,

 
 
4
8
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
5
9
,

 
 
4
8
9
,

 
 
4
6
,

 
 
3
0
0
7
]
,

 
[
2
4
7
,

 
 
1
,

 
 
2
0
7
1
,

 
 
8
,

 
 
3
7
4
1
6
,

 
 
1
7
,

 
 
1
1
,

 
 
4
2
,

 
 
3
6
9
,

 
 
5
7
,

 
 
1
4
4
,

 
 
8
5
0
,

 
 
8
5
3
,

 
 
9
7
9
6
,

 
 
1
,

 
 
5
6
1
9
,

 
 
3
,

 
 
6
2
0
,

 
 
3
9
4
7
,

 
 
5
,

 
 
1
2
6
6
,

 
 
8
,

 
 
1
0
,

 
 
3
7
4
1
6
,

 
 
6
0
7
8
8
,

 
 
8
,

 
 
7
7
,

 
 
1
,

 
 
5
6
1
9
,

 
 
3
,

 
 
1
,

 
 
1
7
3
6
,

 
 
3
,

 
 
8
3
0
2
,

 
 
1
0
,

 
 
7
5
0
7
,

 
 
5
,

 
 
1
5
5
6
,

 
 
7
7
,

 
 
2
0
7
1
,

 
 
2
1
3
4
,

 
 
1
9
,

 
 
2
3
1
7
0
,

 
 
5
,

 
 
3
7
4
1
6
,

 
 
4
2
,

 
 
8
8
,

 
 
5
,

 
 
3
4
,

 
 
6
,

 
 
6
3
,

 
 
5
5
,

 
 
1
0
,

 
 
6
0
7
8
8
,

 
 
4
4
,

 
 
1
5
5
6
,

 
 
4
4
,

 
 
4
7
,

 
 
1
0
,

 
 
8
3
0
2
,

 
 
6
2
1
,

 
 
1
0
,

 
 
1
,

 
 
2
4
4
,

 
 
1
1
7
,

 
 
9
,

 
 
6
0
7
8
8
,

 
 
8
,

 
 
1
,

 
 
2
0
7
1
,

 
 
3
,

 
 
1
6
0
6
9
6
,

 
 
2
6
,

 
 
3
8
2
,

 
 
5
1
,

 
 
1
1
7
,

 
 
1
1
,

 
 
8
,

 
 
3
7
4
1
6
,

 
 
5
,

 
 
6
6
,

 
 
9
,

 
 
4
2
3
7
0
,

 
 
2
4
,

 
 
3
3
5
7
,

 
 
1
0
,

 
 
3
9
7
6
,

 
 
1
0
2
,

 
 
4
8
1
4
,

 
 
5
,

 
 
4
,

 
 
1
1
5
,

 
 
4
7
,

 
 
8
,

 
 
5
9
6
,

 
 
4
9
0
,

 
 
4
1
2
]
,

 
[
1
3
0
0
,

 
 
1
5
0
5
,

 
 
1
0
6
5
8
4
,

 
 
7
,

 
 
1
8
7
,

 
 
1
,

 
 
1
3
0
0
,

 
 
1
6
0
6
9
7
,

 
 
8
0
3
4
,

 
 
5
,

 
 
1
3
1
,

 
 
8
8
,

 
 
1
2
5
1
2
,

 
 
1
1
0
7
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
2
1
2
,

 
 
1
0
,

 
 
3
0
,

 
 
1
5
6
3
,

 
 
2
,

 
 
1
0
6
5
8
4
,

 
 
4
7
,

 
 
4
8
8
,

 
 
3
,

 
 
1
0
5
]
,

 
[
3
9
,

 
 
4
1
,

 
 
1
6
,

 
 
4
,

 
 
5
8
,

 
 
4
2
1
8
,

 
 
1
6
9
3
,

 
 
1
,

 
 
1
6
9
3
,

 
 
3
,

 
 
6
1
,

 
 
1
0
7
2
0
,

 
 
8
,

 
 
1
2
6
2
5
,

 
 
2
8
8
8
,

 
 
7
8
,

 
 
4
3
8
,

 
 
3
6
5
,

 
 
2
7
1
,

 
 
1
2
0
7
,

 
 
8
4
0
,

 
 
7
8
,

 
 
9
6
,

 
 
3
9
2
,

 
 
2
1
8
,

 
 
9
,

 
 
1
,

 
 
1
1
6
3
,

 
 
1
3
7
5
,

 
 
3
1
7
3
,

 
 
3
1
,

 
 
9
8
5
,

 
 
1
0
6
,

 
 
4
1
,

 
 
5
6
,

 
 
1
6
,

 
 
4
,

 
 
1
2
8
,

 
 
5
8
,

 
 
7
9
6
,

 
 
1
0
1
,

 
 
3
1
2
7
,

 
 
1
6
1
,

 
 
3
,

 
 
1
1
6
3
,

 
 
6
5
5
2
,

 
 
5
4
,

 
 
1
3
7
,

 
 
3
5
1
,

 
 
2
,

 
 
1
3
6
,

 
 
6
7
7
,

 
 
2
1
,

 
 
7
4
,

 
 
1
1
2
,

 
 
8
6
,

 
 
1
3
2
1
4
,

 
 
1
1
5
6
7
,

 
 
5
,

 
 
3
8
5
,

 
 
2
5
,

 
 
1
4
,

 
 
1
2
4
0
,

 
 
4
8
,

 
 
1
3
7
8
,

 
 
2
8
2
,

 
 
8
8
,

 
 
3
1
7
3
,

 
 
3
1
,

 
 
1
,

 
 
1
1
6
3
,

 
 
1
3
,

 
 
1
2
6
,

 
 
3
2
3
,

 
 
1
,

 
 
7
7
9
,

 
 
3
,

 
 
7
5
,

 
 
2
1
,

 
 
6
0
,

 
 
6
9
1
2
,

 
 
3
6
4
4
,

 
 
5
4
,

 
 
7
,

 
 
6
5
0
,

 
 
8
,

 
 
1
5
3
0
,

 
 
4
1
,

 
 
8
0
,

 
 
8
3
6
2
4
,

 
 
1
4
2
,

 
 
5
4
,

 
 
8
,

 
 
1
2
6
2
5
,

 
 
3
1
4
7
,

 
 
1
0
,

 
 
1
7
0
7
,

 
 
1
0
6
4
5
,

 
 
2
4
,

 
 
6
9
5
,

 
 
1
4
,

 
 
4
8
,

 
 
1
,

 
 
3
1
3
5
,

 
 
8
7
8
6
,

 
 
3
4
0
,

 
 
6
2
,

 
 
2
4
,

 
 
5
4
8
1
,

 
 
3
5
,

 
 
1
1
6
3
,

 
 
3
5
1
5
,

 
 
3
5
1
,

 
 
8
4
,

 
 
7
7
1
,

 
 
2
4
1
8
,

 
 
1
1
7
,

 
 
9
,

 
 
5
1
,

 
 
7
7
,

 
 
3
2
2
6
,

 
 
2
5
9
4
4
,

 
 
5
,

 
 
1
5
5
6
,

 
 
7
8
,

 
 
1
8
,

 
 
2
1
8
,

 
 
4
8
,

 
 
1
,

 
 
1
0
9
7
7
,

 
 
5
,

 
 
3
7
4
1
7
,

 
 
4
4
0
,

 
 
1
8
2
,

 
 
6
1
,

 
 
1
0
7
2
0
,

 
 
6
2
,

 
 
2
2
2
4
,

 
 
1
1
2
,

 
 
6
4
7
6
]
,

 
[
1
0
,

 
 
1
7
9
,

 
 
4
1
,

 
 
1
0
3
,

 
 
1
6
,

 
 
4
,

 
 
3
1
9
,

 
 
3
3
5
,

 
 
2
5
,

 
 
4
,

 
 
1
7
3
0
,

 
 
3
3
5
,

 
 
1
0
,

 
 
5
5
8
1
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
1
7
3
0
,

 
 
2
5
,

 
 
3
1
9
,

 
 
3
3
5
,

 
 
1
4
4
,

 
 
1
3
2
,

 
 
3
,

 
 
5
5
8
1
,

 
 
3
7
4
4
,

 
 
9
2
9
,

 
 
1
,

 
 
9
1
6
,

 
 
4
0
1
0
,

 
 
3
,

 
 
1
,

 
 
1
5
6
7
9
,

 
 
8
8
5
,

 
 
4
0
4
2
,

 
 
6
5
4
6
,

 
 
3
3
,

 
 
6
0
7
8
9
,

 
 
5
,

 
 
6
3
0
5
,

 
 
2
0
8
,

 
 
5
5
8
1
,

 
 
3
9
7
,

 
 
4
4
,

 
 
1
1
1
,

 
 
5
3
8
,

 
 
1
1
,

 
 
8
,

 
 
3
8
0
,

 
 
9
,

 
 
4
1
,

 
 
1
8
,

 
 
2
7
0
5
,

 
 
6
2
,

 
 
2
2
0
,

 
 
9
,

 
 
6
9
8
2
8
,

 
 
2
4
,

 
 
3
9
6
9
7
,

 
 
1
0
,

 
 
5
4
9
,

 
 
2
5
,

 
 
4
3
,

 
 
2
2
0
,

 
 
1
1
,

 
 
2
2
,

 
 
5
1
,

 
 
1
3
3
7
,

 
 
3
8
,

 
 
6
9
8
2
8
,

 
 
4
2
5
,

 
 
3
6
,

 
 
1
0
,

 
 
2
5
4
9
,

 
 
9
2
,

 
 
3
3
5
,

 
 
8
,

 
 
3
4
2
,

 
 
2
6
,

 
 
1
7
,

 
 
1
6
0
6
9
8
,

 
 
1
6
7
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
2
0
1
8
,

 
 
3
3
5
,

 
 
1
0
,

 
 
1
,

 
 
5
4
3
4
0
,

 
 
9
6
,

 
 
9
7
3
,

 
 
1
9
5
8
,

 
 
6
2
,

 
 
2
0
3
,

 
 
7
8
9
,

 
 
2
1
,

 
 
6
9
8
2
8
,

 
 
1
,

 
 
1
0
6
,

 
 
1
3
3
,

 
 
2
,

 
 
1
9
9
2
,

 
 
2
8
,

 
 
1
8
,

 
 
1
3
7
2
,

 
 
1
0
6
,

 
 
6
0
7
,

 
 
6
9
8
2
8
,

 
 
5
,

 
 
1
0
4
,

 
 
6
0
3
,

 
 
6
6
0
3
,

 
 
1
0
5
6
,

 
 
1
2
3
8
9
,

 
 
1
8
,

 
 
3
3
9
,

 
 
3
2
,

 
 
3
7
2
8
,

 
 
1
,

 
 
1
2
6
2
,

 
 
5
1
,

 
 
1
9
,

 
 
2
0
0
3
,

 
 
1
,

 
 
7
6
0
1
,

 
 
2
0
8
,

 
 
1
,

 
 
3
3
5
,

 
 
3
,

 
 
1
,

 
 
1
3
7
5
0
,

 
 
8
,

 
 
2
2
7
2
,

 
 
5
7
9
,

 
 
2
,

 
 
1
1
3
,

 
 
2
1
1
9
,

 
 
1
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
7
6
,

 
 
9
,

 
 
2
8
,

 
 
1
0
3
,

 
 
1
1
7
,

 
 
9
,

 
 
1
,

 
 
1
3
7
5
0
,

 
 
1
8
,

 
 
4
5
5
5
1
,

 
 
2
4
7
,

 
 
2
8
,

 
 
4
2
,

 
 
4
4
,

 
 
5
5
8
1
,

 
 
3
,

 
 
1
0
4
,

 
 
1
7
0
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
2
6
8
1
,

 
 
2
,

 
 
1
1
7
,

 
 
9
,

 
 
2
0
0
3
,

 
 
8
8
5
,

 
 
4
0
4
2
,

 
 
5
1
,

 
 
1
8
,

 
 
4
,

 
 
2
0
1
8
,

 
 
3
3
5
,

 
 
3
,

 
 
4
4
3
,

 
 
1
3
,

 
 
1
0
0
,

 
 
1
4
,

 
 
4
7
2
7
,

 
 
8
5
8
,

 
 
4
0
4
2
,

 
 
2
0
7
,

 
 
3
3
,

 
 
1
1
8
4
,

 
 
3
2
1
7
8
,

 
 
1
4
4
,

 
 
1
7
,

 
 
2
8
6
5
0
,

 
 
1
6
7
,

 
 
1
0
,

 
 
4
7
,

 
 
3
,

 
 
6
8
,

 
 
6
0
7
9
0
,

 
 
1
9
1
,

 
 
2
6
7
5
7
,

 
 
5
9
3
1
,

 
 
5
,

 
 
1
5
7
4
,

 
 
7
6
7
5
,

 
 
6
9
8
2
9
,

 
 
5
,

 
 
1
5
4
7
5
,

 
 
1
8
7
9
,

 
 
3
4
,

 
 
3
5
1
6
,

 
 
8
7
8
7
,

 
 
8
8
5
,

 
 
8
9
5
,

 
 
3
9
9
9
,

 
 
3
6
,

 
 
1
0
,

 
 
4
,

 
 
4
6
9
,

 
 
1
9
5
8
,

 
 
3
1
,

 
 
1
1
1
,

 
 
3
2
1
7
8
,

 
 
1
8
,

 
 
4
2
1
9
,

 
 
1
3
4
6
1
,

 
 
2
1
,

 
 
8
8
5
,

 
 
8
9
5
,

 
 
5
,

 
 
2
1
6
5
,

 
 
9
2
,

 
 
1
2
3
9
0
,

 
 
9
2
9
,

 
 
1
0
4
,

 
 
4
2
5
5
,

 
 
7
7
,

 
 
8
6
5
1
,

 
 
6
9
8
2
9
,

 
 
5
,

 
 
1
5
4
7
5
,

 
 
1
8
7
9
,

 
 
1
5
2
7
,

 
 
2
,

 
 
3
7
2
8
,

 
 
2
4
8
,

 
 
8
8
5
,

 
 
8
9
5
,

 
 
5
1
,

 
 
1
8
,

 
 
2
0
0
,

 
 
2
,

 
 
3
4
,

 
 
1
3
,

 
 
2
6
,

 
 
1
3
,

 
 
7
3
9
2
,

 
 
2
4
8
,

 
 
9
2
,

 
 
5
3
8
,

 
 
3
,

 
 
9
1
,

 
 
1
7
3
0
,

 
 
2
3
2
2
]
,

 
[
1
0
1
,

 
 
7
2
,

 
 
2
8
0
,

 
 
2
6
,

 
 
2
2
9
3
,

 
 
3
7
,

 
 
5
,

 
 
3
0
,

 
 
1
4
0
,

 
 
8
,

 
 
6
3
4
,

 
 
3
8
,

 
 
1
6
4
,

 
 
2
9
8
,

 
 
1
4
1
8
,

 
 
3
9
5
,

 
 
6
0
,

 
 
7
8
0
,

 
 
2
5
1
4
8
,

 
 
7
5
,

 
 
1
5
,

 
 
2
8
,

 
 
5
,

 
 
2
9
6
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
1
2
2
,

 
 
2
,

 
 
8
8
4
,

 
 
1
,

 
 
1
0
4
7
,

 
 
5
2
8
,

 
 
5
6
0
,

 
 
2
2
1
0
8
]
,

 
[
7
5
0
0
,

 
 
1
2
1
1
,

 
 
3
,

 
 
3
7
0
,

 
 
8
3
6
2
5
,

 
 
3
7
0
,

 
 
8
3
6
2
5
,

 
 
4
2
,

 
 
5
7
,

 
 
1
3
2
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
6
,

 
 
1
8
,

 
 
2
8
0
2
,

 
 
2
,

 
 
2
0
6
,

 
 
1
5
,

 
 
1
,

 
 
1
3
8
,

 
 
3
3
,

 
 
2
8
,

 
 
1
1
4
7
,

 
 
1
2
,

 
 
1
1
9
,

 
 
3
7
0
,

 
 
8
3
6
2
5
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
,

 
 
3
3
6
8
2
,

 
 
7
,

 
 
1
1
4
9
,

 
 
2
5
6
,

 
 
1
,

 
 
7
5
5
,

 
 
7
8
4
,

 
 
1
,

 
 
4
6
2
,

 
 
7
5
5
,

 
 
7
8
4
,

 
 
6
0
6
,

 
 
7
,

 
 
8
1
,

 
 
8
1
9
,

 
 
2
,

 
 
2
7
6
8
6
,

 
 
3
4
4
,

 
 
2
1
,

 
 
2
1
5
,

 
 
2
2
9
8
,

 
 
7
,

 
 
5
4
8
,

 
 
2
,

 
 
9
6
,

 
 
2
2
,

 
 
7
1
,

 
 
4
,

 
 
4
9
6
2
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
5
4
8
,

 
 
3
7
,

 
 
2
,

 
 
8
2
,

 
 
7
3
,

 
 
3
9
9
,

 
 
1
1
3
,

 
 
1
3
6
0
4
,

 
 
3
2
,

 
 
3
5
7
,

 
 
1
5
1
6
,

 
 
8
8
,

 
 
9
,

 
 
4
2
,

 
 
4
4
,

 
 
1
2
1
7
,

 
 
1
5
,

 
 
3
7
,

 
 
7
,

 
 
2
2
9
,

 
 
3
4
,

 
 
2
1
5
,

 
 
3
8
8
,

 
 
1
3
,

 
 
4
3
3
7
,

 
 
5
,

 
 
2
2
,

 
 
5
5
,

 
 
9
4
,

 
 
1
4
6
,

 
 
7
,

 
 
1
1
4
9
,

 
 
3
5
3
9
0
,

 
 
8
8
,

 
 
1
2
3
9
,

 
 
1
7
7
,

 
 
8
7
6
,

 
 
4
6
,

 
 
7
9
4
,

 
 
6
,

 
 
1
0
3
,

 
 
1
9
,

 
 
1
,

 
 
5
9
1
3
,

 
 
2
,

 
 
7
4
5
,

 
 
7
,

 
 
1
6
7
,

 
 
9
,

 
 
3
6
7
,

 
 
8
2
2
,

 
 
2
1
,

 
 
8
8
,

 
 
1
3
,

 
 
4
3
3
7
,

 
 
2
6
,

 
 
7
7
,

 
 
1
,

 
 
7
8
4
,

 
 
1
2
5
,

 
 
1
,

 
 
2
7
6
8
6
,

 
 
8
,

 
 
3
5
5
7
,

 
 
3
1
,

 
 
1
,

 
 
2
9
,

 
 
3
6
,

 
 
1
9
2
,

 
 
4
6
,

 
 
7
9
4
,

 
 
7
,

 
 
8
1
,

 
 
2
9
9
5
,

 
 
2
,

 
 
3
5
7
,

 
 
1
4
6
0
,

 
 
8
8
,

 
 
2
1
,

 
 
4
6
2
,

 
 
6
0
7
9
1
,

 
 
3
3
6
8
2
,

 
 
1
1
1
,

 
 
1
7
,

 
 
9
,

 
 
1
5
,

 
 
1
2
3
,

 
 
1
5
4
7
6
,

 
 
8
2
1
3
,

 
 
4
7
2
,

 
 
4
6
,

 
 
7
9
4
,

 
 
1
1
,

 
 
5
9
3
,

 
 
2
1
7
,

 
 
7
,

 
 
1
3
3
,

 
 
2
7
,

 
 
7
6
8
,

 
 
1
6
9
,

 
 
1
7
,

 
 
4
9
7
,

 
 
2
0
,

 
 
2
3
4
2
,

 
 
5
4
,

 
 
4
3
8
4
,

 
 
7
2
,

 
 
1
4
,

 
 
4
2
6
7
,

 
 
2
,

 
 
7
1
1
,

 
 
7
,

 
 
8
1
,

 
 
5
5
1
,

 
 
1
5
,

 
 
1
,

 
 
1
1
7
4
5
,

 
 
3
,

 
 
1
1
8
9
,

 
 
2
0
2
2
,

 
 
1
7
,

 
 
6
,

 
 
1
8
,

 
 
6
7
0
6
,

 
 
3
0
,

 
 
3
0
0
,

 
 
1
9
9
,

 
 
4
8
9
,

 
 
1
1
3
,

 
 
2
,

 
 
9
7
,

 
 
4
,

 
 
1
4
5
,

 
 
7
,

 
 
4
5
,

 
 
3
7
3
,

 
 
6
,

 
 
4
7
,

 
 
5
8
,

 
 
8
5
,

 
 
5
5
,

 
 
3
4
4
,

 
 
1
8
,

 
 
2
0
1
,

 
 
9
3
,

 
 
9
2
5
,

 
 
2
2
,

 
 
6
,

 
 
5
4
8
,

 
 
2
,

 
 
9
4
,

 
 
2
0
,

 
 
1
7
0
,

 
 
1
9
0
5
8
,

 
 
3
,

 
 
4
0
,

 
 
1
,

 
 
1
3
1
4
,

 
 
3
4
4
,

 
 
1
6
4
,

 
 
9
5
4
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
9
,

 
 
2
6
,

 
 
5
1
,

 
 
1
8
,

 
 
2
3
4
0
,

 
 
6
0
7
,

 
 
3
9
5
,

 
 
4
4
,

 
 
2
5
3
2
,

 
 
1
2
,

 
 
1
1
2
9
,

 
 
4
6
,

 
 
7
9
4
,

 
 
1
9
9
3
,

 
 
7
,

 
 
1
1
4
9
,

 
 
1
5
2
,

 
 
1
,

 
 
7
6
8
,

 
 
1
6
9
,

 
 
1
2
7
,

 
 
1
4
,

 
 
1
7
,

 
 
2
7
,

 
 
1
2
3
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
2
5
6
,

 
 
1
1
,

 
 
7
,

 
 
1
1
4
9
,

 
 
9
7
,

 
 
4
,

 
 
2
3
5
9
,

 
 
2
2
8
1
,

 
 
2
,

 
 
1
,

 
 
1
5
5
3
,

 
 
1
9
1
0
,

 
 
5
,

 
 
1
,

 
 
1
0
5
,

 
 
1
4
0
4
9
,

 
 
1
0
,

 
 
1
6
5
9
,

 
 
4
6
,

 
 
7
9
4
,

 
 
2
0
,

 
 
2
2
5
7
,

 
 
8
,

 
 
4
,

 
 
2
3
5
,

 
 
1
9
2
,

 
 
1
0
,

 
 
1
3
,

 
 
3
5
4
,

 
 
2
0
8
,

 
 
7
2
,

 
 
4
0
,

 
 
1
2
,

 
 
1
3
0
4
,

 
 
1
,

 
 
4
6
4
,

 
 
2
1
,

 
 
4
1
0
,

 
 
8
5
6
,

 
 
2
4
6
,

 
 
1
1
,

 
 
9
8
7
,

 
 
5
0
,

 
 
9
5
,

 
 
4
6
,

 
 
7
,

 
 
7
8
9
,

 
 
4
3
8
5
,

 
 
1
1
,

 
 
8
,

 
 
3
1
3
,

 
 
5
8
,

 
 
9
3
,

 
 
4
,

 
 
2
3
5
,

 
 
1
9
2
,

 
 
3
4
4
,

 
 
8
3
6
2
6
,

 
 
1
7
,

 
 
1
1
1
,

 
 
1
8
,

 
 
1
4
,

 
 
1
0
,

 
 
5
5
,

 
 
1
1
0
,

 
 
4
8
1
,

 
 
1
2
,

 
 
2
8
,

 
 
1
3
,

 
 
8
,

 
 
2
7
,

 
 
2
0
2
0
8
,

 
 
1
4
,

 
 
4
,

 
 
5
2
9
2
,

 
 
1
2
3
,

 
 
4
9
3
,

 
 
2
2
,

 
 
6
9
8
3
0
,

 
 
2
8
5
,

 
 
4
8
2
,

 
 
2
,

 
 
8
7
9
,

 
 
2
5
2
9
,

 
 
5
2
,

 
 
3
9
,

 
 
1
1
8
,

 
 
1
6
1
6
,

 
 
4
6
,

 
 
7
,

 
 
8
1
,

 
 
3
7
9
2
,

 
 
4
,

 
 
2
3
6
,

 
 
2
,

 
 
1
,

 
 
1
2
3
,

 
 
8
2
,

 
 
2
3
0
,

 
 
2
,

 
 
9
7
4
2
,

 
 
8
3
6
2
6
,

 
 
3
4
4
,

 
 
5
0
,

 
 
1
8
6
4
,

 
 
2
7
,

 
 
3
2
7
,

 
 
3
3
,

 
 
2
8
,

 
 
4
6
,

 
 
1
2
3
,

 
 
8
2
,

 
 
2
3
0
,

 
 
1
0
7
,

 
 
3
3
3
,

 
 
3
4
4
,

 
 
9
5
,

 
 
4
6
,

 
 
7
,

 
 
7
9
,

 
 
3
1
,

 
 
1
,

 
 
6
4
3
,

 
 
1
7
3
6
,

 
 
5
,

 
 
1
8
2
,

 
 
1
,

 
 
4
1
0
2
,

 
 
1
0
0
5
,

 
 
5
5
5
9
,

 
 
8
6
2
,

 
 
1
,

 
 
1
2
9
,

 
 
3
,

 
 
1
0
5
,

 
 
9
1
0
,

 
 
8
,

 
 
2
2
2
8
,

 
 
1
7
7
,

 
 
1
4
5
7
,

 
 
1
,

 
 
2
2
8
2
,

 
 
3
3
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
3
0
6
,

 
 
2
9
,

 
 
9
,

 
 
2
8
6
,

 
 
7
9
,

 
 
1
3
,

 
 
2
9
,

 
 
9
7
3
,

 
 
6
1
,

 
 
2
1
8
,

 
 
2
7
3
2
,

 
 
9
,

 
 
1
4
5
7
,

 
 
2
0
8
,

 
 
1
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
,

 
 
6
4
1
,

 
 
2
8
0
6
,

 
 
1
4
4
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
3
3
7
4
,

 
 
2
4
8
,

 
 
3
0
,

 
 
1
2
3
,

 
 
1
1
,

 
 
4
2
,

 
 
4
,

 
 
9
2
4
,

 
 
1
4
3
,

 
 
2
,

 
 
1
6
,

 
 
4
1
,

 
 
2
0
4
4
,

 
 
2
6
5
,

 
 
3
9
6
,

 
 
4
6
,

 
 
7
9
4
,

 
 
3
8
0
,

 
 
2
6
,

 
 
6
0
7
,

 
 
2
0
,

 
 
8
1
3
,

 
 
2
6
3
2
,

 
 
1
8
2
,

 
 
1
,

 
 
1
3
9
,

 
 
1
6
4
6
,

 
 
6
6
,

 
 
1
5
5
3
,

 
 
1
7
0
,

 
 
1
,

 
 
6
4
7
7
,

 
 
7
1
,

 
 
9
2
,

 
 
1
4
3
,

 
 
2
,

 
 
3
5
6
,

 
 
1
1
,

 
 
1
6
0
6
9
9
,

 
 
6
9
8
3
1
,

 
 
2
1
1
5
,

 
 
2
,

 
 
2
2
8
9
,

 
 
1
2
,

 
 
1
1
0
5
3
,

 
 
6
8
,

 
 
4
6
,

 
 
2
9
,

 
 
2
6
,

 
 
3
8
,

 
 
4
,

 
 
3
0
5
2
,

 
 
3
,

 
 
2
4
3
6
,

 
 
2
8
,

 
 
1
8
,

 
 
1
8
2
,

 
 
4
4
,

 
 
9
2
4
,

 
 
6
6
5
4
,

 
 
2
2
9
8
,

 
 
2
,

 
 
3
2
1
2
,

 
 
2
0
,

 
 
3
4
4
,

 
 
1
4
8
7
,

 
 
3
,

 
 
3
8
5
,

 
 
5
1
,

 
 
1
0
9
2
,

 
 
5
5
,

 
 
2
3
0
,

 
 
7
,

 
 
1
9
,

 
 
4
4
,

 
 
4
0
5
,

 
 
1
8
2
,

 
 
3
8
,

 
 
4
6
7
3
,

 
 
1
6
4
6
,

 
 
6
,

 
 
5
0
3
4
,

 
 
9
,

 
 
1
,

 
 
1
6
6
,

 
 
6
,

 
 
3
9
,

 
 
7
9
,

 
 
2
8
,

 
 
4
2
5
,

 
 
9
,

 
 
2
0
,

 
 
1
4
0
,

 
 
2
4
5
,

 
 
4
1
7
0
,

 
 
1
6
,

 
 
9
0
4
,

 
 
2
2
,

 
 
1
,

 
 
1
0
0
5
,

 
 
5
5
5
9
,

 
 
8
6
2
,

 
 
3
8
6
,

 
 
9
,

 
 
1
,

 
 
1
2
9
,

 
 
3
,

 
 
1
0
5
,

 
 
9
1
0
,

 
 
8
,

 
 
2
2
2
8
,

 
 
1
7
7
,

 
 
1
4
5
7
,

 
 
9
,

 
 
2
4
5
7
,

 
 
9
,

 
 
1
2
9
,

 
 
2
1
,

 
 
1
4
5
7
,

 
 
8
,

 
 
9
2
4
,

 
 
5
,

 
 
2
4
1
,

 
 
5
8
,

 
 
1
7
2
1
,

 
 
3
2
,

 
 
2
0
,

 
 
1
6
4
6
,

 
 
7
,

 
 
1
9
,

 
 
1
,

 
 
9
2
4
,

 
 
1
4
3
,

 
 
2
,

 
 
7
9
,

 
 
2
8
,

 
 
5
,

 
 
2
5
6
,

 
 
2
0
,

 
 
3
4
4
,

 
 
7
,

 
 
1
6
3
5
,

 
 
2
,

 
 
6
3
,

 
 
3
8
,

 
 
1
5
,

 
 
1
1
8
7
,

 
 
6
,

 
 
2
7
2
8
,

 
 
2
,

 
 
3
7
3
,

 
 
2
0
,

 
 
3
8
9
6
,

 
 
2
6
,

 
 
7
,

 
 
5
9
,

 
 
1
8
9
7
,

 
 
1
,

 
 
1
5
5
3
,

 
 
1
3
7
0
,

 
 
1
8
,

 
 
1
5
5
,

 
 
1
3
1
4
,

 
 
6
0
7
9
2
,

 
 
6
9
8
3
2
,

 
 
2
6
0
1
,

 
 
1
,

 
 
8
4
1
7
,

 
 
7
]
,

 
[
4
5
5
5
2
,

 
 
9
5
1
,

 
 
9
6
7
,

 
 
3
2
0
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
4
0
,

 
 
2
0
,

 
 
4
1
4
,

 
 
7
,

 
 
9
7
,

 
 
1
3
,

 
 
3
7
7
,

 
 
1
0
,

 
 
9
8
,

 
 
5
8
8
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
9
7
,

 
 
2
9
6
3
,

 
 
2
3
4
,

 
 
4
8
,

 
 
1
3
,

 
 
1
4
9
3
,

 
 
9
,

 
 
2
7
,

 
 
2
9
2
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
2
2
,

 
 
5
1
,

 
 
2
5
6
,

 
 
4
,

 
 
4
3
9
,

 
 
7
,

 
 
8
1
,

 
 
1
0
,

 
 
4
4
,

 
 
5
7
5
,

 
 
2
,

 
 
1
6
,

 
 
9
7
0
,

 
 
1
3
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
3
5
8
,

 
 
1
3
,

 
 
1
7
,

 
 
1
1
,

 
 
1
0
3
,

 
 
1
6
0
7
0
0
,

 
 
1
1
5
,

 
 
1
8
1
6
,

 
 
6
2
,

 
 
7
6
7
,

 
 
7
4
9
,

 
 
3
,

 
 
1
,

 
 
4
7
5
,

 
 
2
1
0
7
,

 
 
5
1
,

 
 
1
9
,

 
 
5
7
,

 
 
1
8
0
6
8
,

 
 
1
0
,

 
 
1
3
,

 
 
1
9
8
,

 
 
7
,

 
 
6
5
,

 
 
4
,

 
 
4
4
9
,

 
 
1
0
7
,

 
 
4
6
,

 
 
2
9
,

 
 
3
7
7
,

 
 
4
3
,

 
 
1
6
,

 
 
5
8
,

 
 
4
8
1
,

 
 
5
,

 
 
3
0
8
6
,

 
 
6
6
,

 
 
6
,

 
 
7
9
,

 
 
2
4
,

 
 
3
6
8
,

 
 
3
6
,

 
 
7
,

 
 
3
6
8
,

 
 
1
1
,

 
 
1
5
7
,

 
 
2
,

 
 
2
0
,

 
 
4
0
7
,

 
 
2
6
,

 
 
6
6
,

 
 
1
8
7
,

 
 
1
,

 
 
2
1
3
,

 
 
5
8
7
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
8
1
,

 
 
4
4
,

 
 
4
1
8
,

 
 
4
5
,

 
 
5
6
,

 
 
2
1
3
,

 
 
4
9
,

 
 
6
9
,

 
 
4
,

 
 
1
0
7
,

 
 
1
8
7
,

 
 
4
,

 
 
4
3
9
,

 
 
7
2
6
0
,

 
 
2
2
,

 
 
9
,

 
 
2
9
6
3
,

 
 
3
7
7
,

 
 
2
4
,

 
 
9
2
,

 
 
7
7
,

 
 
5
8
7
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
7
4
,

 
 
3
7
,

 
 
2
2
,

 
 
2
4
7
,

 
 
1
2
7
,

 
 
7
,

 
 
3
5
0
,

 
 
1
3
,

 
 
1
0
,

 
 
9
8
,

 
 
5
8
8
,

 
 
6
6
9
,

 
 
4
5
5
5
3
]
,

 
[
4
6
3
9
,

 
 
2
9
1
4
,

 
 
7
5
6
,

 
 
1
1
,

 
 
1
9
,

 
 
5
7
,

 
 
2
9
1
4
,

 
 
1
0
5
8
3
,

 
 
7
4
4
6
,

 
 
2
4
,

 
 
4
,

 
 
1
5
2
7
5
,

 
 
6
8
5
0
,

 
 
5
4
7
,

 
 
1
3
,

 
 
8
5
]
,

 
[
3
3
6
4
5
,

 
 
1
1
2
0
5
,

 
 
1
3
4
8
,

 
 
3
2
0
,

 
 
4
9
,

 
 
2
,

 
 
2
7
8
,

 
 
6
,

 
 
7
0
,

 
 
9
,

 
 
1
7
,

 
 
1
3
,

 
 
8
9
,

 
 
7
7
,

 
 
4
2
,

 
 
1
4
9
,

 
 
1
8
2
7
,

 
 
4
7
,

 
 
3
,

 
 
1
3
,

 
 
1
0
9
,

 
 
5
,

 
 
4
7
,

 
 
2
1
,

 
 
4
,

 
 
1
0
2
,

 
 
6
1
8
,

 
 
1
0
9
,

 
 
7
,

 
 
1
9
,

 
 
9
1
7
,

 
 
1
1
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
0
9
,

 
 
3
7
0
,

 
 
1
7
7
6
,

 
 
6
0
2
1
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
3
5
,

 
 
1
3
,

 
 
5
0
,

 
 
2
7
8
,

 
 
3
7
,

 
 
7
0
,

 
 
2
2
1
,

 
 
2
0
6
6
]
,

 
[
3
0
,

 
 
1
6
0
,

 
 
6
4
3
2
,

 
 
1
7
,

 
 
1
5
8
,

 
 
8
7
4
,

 
 
2
,

 
 
1
,

 
 
2
5
0
4
,

 
 
4
2
8
,

 
 
5
3
9
,

 
 
7
1
,

 
 
5
2
1
,

 
 
7
7
6
,

 
 
1
3
3
9
,

 
 
2
,

 
 
2
5
8
,

 
 
2
1
0
,

 
 
2
7
,

 
 
4
2
8
,

 
 
5
,

 
 
4
,

 
 
2
5
0
4
,

 
 
1
0
9
,

 
 
3
3
,

 
 
1
1
4
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
1
2
,

 
 
1
8
6
,

 
 
9
,

 
 
1
8
5
,

 
 
1
,

 
 
1
9
8
,

 
 
6
4
,

 
 
2
6
,

 
 
7
5
6
,

 
 
1
6
,

 
 
1
8
4
9
,

 
 
7
1
,

 
 
2
8
8
,

 
 
1
2
2
4
,

 
 
1
0
,

 
 
1
7
2
,

 
 
3
3
7
]
,

 
[
1
4
8
4
,

 
 
1
0
,

 
 
1
1
5
3
,

 
 
2
5
,

 
 
1
4
,

 
 
7
,

 
 
6
5
,

 
 
7
1
,

 
 
2
0
1
,

 
 
2
,

 
 
5
3
8
8
,

 
 
1
,

 
 
3
5
4
,

 
 
6
4
,

 
 
3
8
2
,

 
 
3
,

 
 
1
6
5
,

 
 
1
5
7
,

 
 
5
,

 
 
2
5
7
5
,

 
 
3
6
,

 
 
1
,

 
 
3
3
4
,

 
 
1
0
7
,

 
 
5
3
8
,

 
 
9
,

 
 
1
,

 
 
4
4
2
,

 
 
2
2
8
,

 
 
8
,

 
 
4
,

 
 
3
0
6
3
,

 
 
9
,

 
 
1
8
9
,

 
 
1
4
8
4
,

 
 
1
0
,

 
 
1
3
7
8
,

 
 
2
7
4
,

 
 
6
3
3
,

 
 
5
,

 
 
9
,

 
 
3
9
5
,

 
 
4
4
,

 
 
6
0
2
3
,

 
 
2
0
2
0
9
,

 
 
1
1
4
,

 
 
3
,

 
 
4
0
,

 
 
8
,

 
 
1
,

 
 
1
6
0
7
0
1
,

 
 
4
,

 
 
1
0
7
,

 
 
2
8
1
1
,

 
 
4
2
1
,

 
 
7
0
4
,

 
 
6
3
3
0
,

 
 
6
7
5
0
,

 
 
7
3
8
9
,

 
 
3
4
,

 
 
6
,

 
 
7
0
,

 
 
1
7
2
,

 
 
7
1
9
,

 
 
8
7
3
,

 
 
2
5
,

 
 
3
4
,

 
 
6
,

 
 
7
0
,

 
 
1
2
6
1
,

 
 
6
2
,

 
 
1
0
8
4
,

 
 
1
,

 
 
7
1
9
,

 
 
3
9
6
9
,

 
 
4
8
,

 
 
2
,

 
 
9
4
,

 
 
4
,

 
 
5
8
,

 
 
4
5
2
2
,

 
 
1
6
0
7
0
2
,

 
 
1
0
5
7
,

 
 
1
,

 
 
4
0
3
,

 
 
9
,

 
 
1
9
8
1
,

 
 
5
7
,

 
 
9
3
1
,

 
 
2
7
4
,

 
 
6
3
3
,

 
 
7
,

 
 
6
3
,

 
 
9
,

 
 
1
7
2
,

 
 
9
7
2
,

 
 
1
0
8
9
1
,

 
 
8
,

 
 
5
2
1
,

 
 
1
8
5
5
,

 
 
1
8
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
3
5
2
4
,

 
 
1
0
5
,

 
 
8
8
7
,

 
 
2
3
8
,

 
 
5
,

 
 
1
,

 
 
4
8
6
]
,

 
[
9
8
1
,

 
 
7
1
0
,

 
 
2
1
6
,

 
 
1
1
7
8
,

 
 
1
,

 
 
7
0
4
,

 
 
1
9
4
1
,

 
 
2
1
3
,

 
 
9
,

 
 
6
,

 
 
6
6
8
,

 
 
1
5
,

 
 
3
0
,

 
 
3
8
7
,

 
 
2
4
2
4
,

 
 
1
2
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
4
2
,

 
 
4
9
,

 
 
5
3
3
8
,

 
 
5
,

 
 
2
0
8
,

 
 
7
,

 
 
2
4
5
,

 
 
1
1
7
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
1
4
,

 
 
4
8
2
,

 
 
3
5
,

 
 
1
,

 
 
2
1
3
,

 
 
7
,

 
 
1
0
3
6
0
,

 
 
4
4
,

 
 
5
5
2
,

 
 
2
7
9
4
,

 
 
1
1
1
5
,

 
 
6
,

 
 
2
2
,

 
 
6
,

 
 
3
2
8
,

 
 
3
0
,

 
 
8
0
8
,

 
 
4
1
4
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
4
,

 
 
3
1
4
0
,

 
 
2
9
2
,

 
 
1
5
,

 
 
2
8
,

 
 
3
6
7
,

 
 
4
9
,

 
 
4
8
,

 
 
2
,

 
 
2
7
8
,

 
 
6
,

 
 
7
0
,

 
 
9
,

 
 
2
0
8
,

 
 
7
,

 
 
2
4
,

 
 
2
9
2
1
,

 
 
3
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
2
4
8
,

 
 
5
,

 
 
7
,

 
 
2
4
,

 
 
3
0
8
2
8
,

 
 
1
3
5
,

 
 
2
9
8
,

 
 
3
6
,

 
 
3
2
,

 
 
1
1
2
,

 
 
1
4
9
,

 
 
1
9
1
2
,

 
 
1
0
,

 
 
5
2
7
,

 
 
2
,

 
 
8
0
5
,

 
 
6
0
2
,

 
 
1
8
0
4
,

 
 
7
,

 
 
2
8
9
6
,

 
 
1
4
,

 
 
2
,

 
 
2
3
8
7
,

 
 
1
0
,

 
 
1
3
5
4
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
5
,

 
 
2
2
,

 
 
7
,

 
 
8
1
,

 
 
3
0
8
2
8
,

 
 
3
2
,

 
 
3
4
2
0
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
1
2
,

 
 
1
4
9
,

 
 
1
9
1
2
,

 
 
7
,

 
 
4
5
,

 
 
3
0
9
,

 
 
1
2
8
4
,

 
 
8
8
,

 
 
2
4
,

 
 
1
5
1
0
,

 
 
7
3
7
,

 
 
4
,

 
 
2
0
6
,

 
 
5
4
,

 
 
7
,

 
 
1
3
1
,

 
 
1
7
0
4
,

 
 
8
6
3
,

 
 
1
3
1
,

 
 
1
0
,

 
 
1
,

 
 
1
0
8
0
3
,

 
 
8
9
8
1
,

 
 
2
3
,

 
 
5
4
,

 
 
7
,

 
 
2
9
1
,

 
 
2
,

 
 
1
6
,

 
 
8
9
9
,

 
 
3
0
,

 
 
2
6
7
,

 
 
2
1
,

 
 
1
1
0
0
,

 
 
6
8
,

 
 
2
5
1
4
9
,

 
 
5
,

 
 
2
8
6
5
1
,

 
 
5
2
,

 
 
8
,

 
 
3
1
3
,

 
 
1
5
5
,

 
 
1
3
9
1
5
,

 
 
3
,

 
 
8
3
,

 
 
5
4
,

 
 
5
2
,

 
 
4
2
,

 
 
3
3
3
,

 
 
5
,

 
 
5
2
,

 
 
2
2
1
5
,

 
 
1
0
2
,

 
 
2
5
1
3
,

 
 
8
0
,

 
 
1
4
0
,

 
 
1
8
,

 
 
1
3
1
,

 
 
2
,

 
 
1
1
1
,

 
 
8
3
,

 
 
1
5
1
,

 
 
8
6
9
,

 
 
3
9
1
3
,

 
 
3
,

 
 
1
5
7
0
,

 
 
1
4
0
,

 
 
5
4
,

 
 
7
,

 
 
1
3
1
,

 
 
2
,

 
 
6
8
,

 
 
8
3
,

 
 
7
,

 
 
7
7
8
,

 
 
1
5
4
,

 
 
2
,

 
 
3
1
7
,

 
 
3
7
,

 
 
7
5
7
,

 
 
5
2
,

 
 
1
0
6
4
6
,

 
 
2
,

 
 
5
8
0
9
,

 
 
3
0
,

 
 
1
3
8
,

 
 
2
9
,

 
 
2
1
,

 
 
8
7
8
8
,

 
 
5
,

 
 
1
4
8
9
0
,

 
 
2
3
4
,

 
 
8
0
,

 
 
7
,

 
 
5
9
7
3
,

 
 
2
,

 
 
1
3
,

 
 
5
2
,

 
 
3
0
8
2
8
,

 
 
3
7
,

 
 
1
3
5
,

 
 
8
2
5
,

 
 
1
5
4
,

 
 
4
,

 
 
7
0
8
8
,

 
 
2
0
8
,

 
 
7
,

 
 
8
7
6
,

 
 
2
0
,

 
 
1
4
1
9
,

 
 
1
7
,

 
 
4
,

 
 
2
8
,

 
 
7
5
3
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
5
6
3
2
,

 
 
3
3
6
,

 
 
9
,

 
 
1
0
,

 
 
1
,

 
 
6
0
2
,

 
 
6
,

 
 
4
2
5
0
,

 
 
2
0
1
,

 
 
8
3
4
1
,

 
 
8
0
,

 
 
1
0
8
9
,

 
 
4
,

 
 
1
0
7
,

 
 
4
0
1
,

 
 
1
5
,

 
 
4
7
,

 
 
4
3
2
4
,

 
 
1
0
5
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
1
1
1
6
,

 
 
9
1
9
,

 
 
3
3
4
8
,

 
 
6
9
9
]
,

 
[
2
2
4
,
 
1
0
,
 
1
1
1
7
,
 
4
,
 
1
7
6
4
,
 
2
2
4
,
 
1
5
1
3
,
 
9
4
5
,
 
1
,
 
7
4
3
,
 
3
3
7
]
,

 
[
1
1
,

 
 
5
9
3
,

 
 
3
7
,

 
 
9
,

 
 
1
7
3
,

 
 
1
,

 
 
1
6
0
7
0
3
,

 
 
1
8
5
9
,

 
 
1
6
9
,

 
 
2
3
8
,

 
 
7
,

 
 
2
5
9
4
5
,

 
 
9
5
7
5
,

 
 
1
1
,

 
 
1
3
7
,

 
 
1
9
9
,

 
 
2
0
3
,

 
 
5
7
,

 
 
4
1
,

 
 
3
6
,

 
 
7
2
,

 
 
1
7
5
0
,

 
 
7
,

 
 
6
2
4
,

 
 
1
6
,

 
 
3
,

 
 
1
2
8
,

 
 
1
2
1
,

 
 
3
3
,

 
 
1
,

 
 
1
1
6
4
,

 
 
2
3
8
,

 
 
1
3
7
,

 
 
5
7
,

 
 
7
9
1
,

 
 
2
,

 
 
1
1
8
,

 
 
1
4
7
,

 
 
1
2
,

 
 
4
,

 
 
2
0
8
]
,

 
[
1
1
8
,

 
 
5
0
4
,

 
 
7
8
,

 
 
9
0
,

 
 
6
,

 
 
3
9
8
,

 
 
3
0
,

 
 
7
9
,

 
 
1
5
,

 
 
1
6
0
7
0
4
,

 
 
1
0
7
,

 
 
4
6
,

 
 
2
9
,

 
 
1
6
4
4
,

 
 
1
2
8
0
,

 
 
6
8
,

 
 
8
3
6
2
7
,

 
 
4
1
0
,

 
 
4
8
,

 
 
6
,

 
 
2
5
8
,

 
 
2
8
,

 
 
4
,

 
 
3
6
6
,

 
 
1
0
9
,

 
 
1
7
1
,

 
 
9
1
,

 
 
1
1
1
,

 
 
4
,

 
 
2
6
7
5
8
,

 
 
5
7
6
8
,

 
 
6
0
4
8
,

 
 
1
6
2
,

 
 
6
0
8
8
]
,

 
[
1
,

 
 
8
1
0
,

 
 
1
6
0
7
0
5
,

 
 
2
5
9
0
,

 
 
8
2
5
6
,

 
 
5
,

 
 
2
9
1
7
,

 
 
4
8
,

 
 
8
7
9
,

 
 
1
8
0
6
9
,

 
 
4
7
6
,

 
 
1
0
6
5
8
5
,

 
 
8
8
,

 
 
5
1
,

 
 
4
5
,

 
 
1
7
9
4
,

 
 
1
9
2
]
,

 
[
1
4
7
1
4
,

 
 
3
,

 
 
1
9
0
5
4
,

 
 
1
1
2
5
,

 
 
1
2
,

 
 
6
,

 
 
6
,

 
 
4
3
1
,

 
 
8
1
8
,

 
 
4
,

 
 
1
6
6
,

 
 
1
4
7
1
4
,

 
 
3
,

 
 
1
9
0
5
4
,

 
 
1
1
2
5
,

 
 
1
2
,

 
 
6
,

 
 
6
,

 
 
4
3
1
,

 
 
8
1
8
,

 
 
4
,

 
 
1
6
6
,

 
 
1
6
6
,

 
 
6
0
7
9
3
,

 
 
7
7
8
,

 
 
3
7
,

 
 
6
4
,

 
 
1
5
,

 
 
2
8
,

 
 
9
,

 
 
1
5
2
8
,

 
 
2
4
6
,

 
 
9
2
,

 
 
6
9
8
5
,

 
 
1
0
5
8
4
,

 
 
1
0
,

 
 
1
,

 
 
2
6
6
5
,

 
 
1
6
6
,

 
 
9
,

 
 
8
,

 
 
1
0
7
6
,

 
 
3
8
7
1
,

 
 
1
6
6
,

 
 
1
4
7
1
4
,

 
 
3
,

 
 
1
9
0
5
4
,

 
 
6
4
4
7
,

 
 
3
7
,

 
 
1
2
,

 
 
1
4
9
3
,

 
 
9
,

 
 
1
6
6
,

 
 
1
4
7
1
4
,

 
 
3
,

 
 
1
9
0
5
4
,

 
 
3
9
,

 
 
8
1
8
,

 
 
3
7
,

 
 
2
6
,

 
 
4
3
1
,

 
 
8
1
8
,

 
 
4
7
9
]
,

 
[
2
4
6
,

 
 
2
0
,

 
 
1
2
5
1
3
,

 
 
7
3
,

 
 
1
2
3
9
1
,

 
 
2
4
,

 
 
1
4
,

 
 
9
0
4
,

 
 
1
4
8
,

 
 
1
1
6
6
,

 
 
4
1
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
5
8
,

 
 
4
6
9
,

 
 
1
0
,

 
 
1
,

 
 
8
3
6
2
8
,

 
 
2
9
3
0
,

 
 
9
3
,

 
 
1
,

 
 
7
0
8
,

 
 
1
2
1
9
,

 
 
3
8
6
5
,

 
 
9
,

 
 
1
7
5
,

 
 
4
8
4
5
,

 
 
7
7
1
,

 
 
3
1
,

 
 
1
6
3
9
6
,

 
 
1
0
,

 
 
5
5
1
0
,

 
 
2
,

 
 
1
,

 
 
8
3
6
2
9
,

 
 
5
,

 
 
8
4
,

 
 
4
9
4
4
4
,

 
 
5
1
9
,

 
 
1
5
9
,

 
 
7
3
,

 
 
4
,

 
 
6
0
7
9
4
,

 
 
3
0
0
,

 
 
1
9
0
,

 
 
3
6
,

 
 
5
1
,

 
 
1
0
3
,

 
 
7
9
,

 
 
2
8
,

 
 
5
,

 
 
8
9
6
,

 
 
3
3
7
,

 
 
3
2
1
,

 
 
4
0
,

 
 
3
0
3
,

 
 
4
7
,

 
 
7
7
,

 
 
4
2
,

 
 
2
,

 
 
9
2
3
,

 
 
2
3
5
,

 
 
1
6
6
6
,

 
 
1
5
,

 
 
1
,

 
 
4
4
0
1
,

 
 
1
,

 
 
1
1
4
,

 
 
8
5
,

 
 
4
,

 
 
3
8
4
1
,

 
 
1
1
2
8
2
,

 
 
8
8
,

 
 
1
2
1
6
,

 
 
1
4
8
,

 
 
2
1
0
8
6
,

 
 
5
1
,

 
 
8
7
,

 
 
1
0
1
,

 
 
3
7
1
2
,

 
 
5
2
4
,

 
 
2
6
,

 
 
1
5
1
,

 
 
4
,

 
 
8
5
,

 
 
5
1
,

 
 
2
2
9
,

 
 
9
9
9
,

 
 
2
,

 
 
9
4
,

 
 
1
3
5
,

 
 
1
,

 
 
1
3
8
3
,

 
 
1
2
7
,

 
 
1
1
,

 
 
8
,

 
 
1
7
,

 
 
2
2
,

 
 
9
1
,

 
 
3
3
,

 
 
1
0
4
2
,

 
 
1
5
,

 
 
4
,

 
 
2
5
1
0
,

 
 
4
2
2
0
,

 
 
3
2
0
3
,

 
 
8
,

 
 
5
5
2
,

 
 
1
1
5
6
8
,

 
 
1
3
5
,

 
 
9
2
,

 
 
8
3
3
4
,

 
 
1
1
2
5
,

 
 
1
,

 
 
3
5
5
1
,

 
 
1
0
,

 
 
2
5
1
0
,

 
 
8
3
9
,

 
 
1
4
4
,

 
 
1
1
2
,

 
 
4
0
2
,

 
 
4
2
5
,

 
 
9
,

 
 
3
8
9
,

 
 
3
,

 
 
1
1
2
,

 
 
1
0
2
9
1
,

 
 
3
9
2
9
,

 
 
8
7
,

 
 
1
9
9
,

 
 
1
6
,

 
 
2
9
1
,

 
 
2
4
6
,

 
 
2
6
7
5
9
,

 
 
5
0
4
,

 
 
3
8
8
,

 
 
1
,

 
 
3
4
3
,

 
 
3
8
6
5
,

 
 
1
8
0
7
0
,

 
 
5
0
4
]
,

 
[
1
1
4
3
,
 
5
6
3
3
,
 
8
,
 
1
2
2
8
4
,
 
1
8
9
2
,
 
1
1
8
3
,
 
6
0
3
,
 
2
8
1
9
,
 
1
0
0
1
,
 
2
1
6
]
,

 
[
7
4
0
,

 
 
7
,

 
 
1
5
4
7
,

 
 
1
,

 
 
6
1
,

 
 
1
9
8
,

 
 
3
7
2
,

 
 
1
6
0
7
0
6
,

 
 
1
6
0
7
0
7
,

 
 
6
9
5
,

 
 
5
4
,

 
 
2
2
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
2
,

 
 
1
8
0
,

 
 
1
4
4
,

 
 
7
1
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
2
6
,

 
 
1
6
5
,

 
 
4
,

 
 
1
3
2
3
,

 
 
3
9
9
,

 
 
7
,

 
 
2
2
9
,

 
 
1
3
6
,

 
 
9
,

 
 
1
9
8
,

 
 
3
7
2
,

 
 
1
5
,

 
 
2
2
5
9
,

 
 
1
6
0
7
0
8
,

 
 
7
0
9
,

 
 
1
0
3
3
,

 
 
3
0
4
,

 
 
1
0
,

 
 
9
8
7
,

 
 
2
5
,

 
 
2
4
0
5
,

 
 
1
7
1
4
]
,

 
[
1
,

 
 
5
5
9
7
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
1
1
2
4
,

 
 
3
7
9
,

 
 
1
8
1
,

 
 
3
6
4
,

 
 
2
,

 
 
1
3
5
1
,

 
 
1
3
5
,

 
 
1
,

 
 
4
3
2
,

 
 
4
6
,

 
 
2
9
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
1
7
3
8
,

 
 
8
7
,

 
 
1
9
,

 
 
2
,

 
 
1
4
2
6
,

 
 
2
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
4
9
0
6
,

 
 
2
,

 
 
9
4
,

 
 
1
,

 
 
1
3
2
,

 
 
7
3
,

 
 
2
,

 
 
4
3
5
,

 
 
4
0
7
,

 
 
2
8
0
,

 
 
1
0
4
,

 
 
8
3
6
3
0
,

 
 
6
,

 
 
3
9
,

 
 
2
1
5
8
6
,

 
 
1
3
2
,

 
 
3
,

 
 
1
,

 
 
1
7
4
,

 
 
4
7
0
,

 
 
5
3
6
,

 
 
7
,

 
 
6
5
0
]
,

 
[
3
5
9
0
,

 
 
1
0
6
5
8
6
,

 
 
3
,

 
 
1
,

 
 
6
5
2
2
,

 
 
2
8
6
5
,

 
 
1
6
0
7
0
9
,

 
 
1
7
8
,

 
 
3
9
,

 
 
6
,

 
 
5
2
0
,

 
 
1
5
,

 
 
1
0
4
,

 
 
4
6
,

 
 
2
9
,

 
 
7
8
,

 
 
6
,

 
 
1
1
7
4
,

 
 
1
3
,

 
 
2
3
,

 
 
4
1
,

 
 
8
,

 
 
6
0
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
1
6
5
,

 
 
1
5
,

 
 
2
6
,

 
 
1
4
,

 
 
1
0
2
,

 
 
2
3
3
4
,

 
 
1
2
,

 
 
1
,

 
 
1
1
2
8
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
6
6
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
7
6
3
3
,

 
 
1
0
,

 
 
4
,

 
 
2
0
2
2
,

 
 
1
9
8
,

 
 
2
6
,

 
 
9
,

 
 
1
1
0
0
,

 
 
2
0
3
,

 
 
7
7
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
4
7
,

 
 
1
2
0
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
5
,

 
 
8
,

 
 
1
0
4
9
,

 
 
2
,

 
 
1
,

 
 
6
9
3
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
6
0
7
,

 
 
7
,

 
 
2
4
,

 
 
1
2
8
2
,

 
 
3
5
,

 
 
2
0
,

 
 
4
3
6
9
,

 
 
6
4
7
]
,

 
[
3
2
0
,

 
 
7
,

 
 
3
2
8
,

 
 
1
3
,

 
 
2
4
2
,

 
 
2
9
,

 
 
1
0
2
,

 
 
6
3
5
,

 
 
5
0
,

 
 
3
1
7
,

 
 
9
8
9
,

 
 
6
4
,

 
 
1
5
,

 
 
1
5
,

 
 
1
,

 
 
1
3
8
,

 
 
2
9
,

 
 
3
3
6
8
3
,

 
 
1
6
0
7
1
0
]
,

 
[
3
0
,

 
 
9
5
,

 
 
2
,

 
 
6
,

 
 
1
2
,

 
 
1
3
,

 
 
7
,

 
 
1
9
3
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
9
1
,

 
 
1
0
2
9
4
,

 
 
3
2
2
,

 
 
1
2
,

 
 
5
8
0
,

 
 
3
1
,

 
 
9
1
,

 
 
5
7
3
,

 
 
2
,

 
 
2
0
5
,

 
 
7
,

 
 
4
8
,

 
 
2
,

 
 
1
4
2
,

 
 
2
1
,

 
 
4
0
,

 
 
1
,

 
 
1
1
0
,

 
 
2
,

 
 
7
1
8
,

 
 
7
9
9
2
,

 
 
1
2
1
3
,

 
 
3
1
,

 
 
3
0
,

 
 
1
7
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
0
1
,

 
 
4
,

 
 
1
7
6
4
,

 
 
8
,

 
 
4
,

 
 
1
7
6
4
,

 
 
1
2
7
,

 
 
9
5
,

 
 
3
7
3
9
,

 
 
5
0
,

 
 
5
9
,

 
 
1
5
9
,

 
 
9
,

 
 
1
7
,

 
 
1
2
3
9
2
,

 
 
2
5
,

 
 
1
6
0
7
1
1
,

 
 
2
5
9
4
6
]
,

 
[
7
,
 
5
9
,
 
4
6
6
,
 
3
8
,
 
6
,
 
1
1
7
,
 
6
4
,
 
7
,
 
5
9
,
 
2
2
0
,
 
4
7
,
 
4
6
5
,
 
1
3
5
4
]
,

 
[
5
7
7
3
,
 
6
,
 
1
0
8
,
 
4
,
 
1
6
0
7
1
2
,
 
3
7
3
,
 
3
7
]
,

 
[
8
4
4
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
4
5
0
8
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
,

 
 
8
4
4
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
3
1
7
2
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
,

 
 
8
3
8
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
7
1
6
9
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
,

 
 
8
3
8
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
5
9
1
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
,

 
 
7
1
4
,

 
 
1
,

 
 
1
1
0
,

 
 
3
0
8
2
9
,

 
 
5
4
4
,

 
 
1
9
0
5
9
,

 
 
2
1
7
7
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
1
6
0
7
1
3
,

 
 
7
1
4
,

 
 
1
5
0
8
,

 
 
2
2
6
9
,

 
 
9
1
0
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
1
0
6
5
8
7
,

 
 
8
3
6
3
1
,

 
 
1
7
1
7
0
,

 
 
1
2
,

 
 
1
,

 
 
5
0
0
5
,

 
 
6
5
5
,

 
 
1
,

 
 
2
9
6
9
6
,

 
 
7
5
6
5
,

 
 
8
3
6
3
2
,

 
 
9
1
0
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
8
3
6
3
3
,

 
 
8
3
6
3
1
,

 
 
1
7
1
7
0
,

 
 
1
2
,

 
 
1
,

 
 
5
0
0
5
,

 
 
1
7
1
1
,

 
 
1
9
6
9
,

 
 
6
7
2
,

 
 
1
0
0
1
,

 
 
5
0
7
8
,

 
 
1
0
4
2
,

 
 
4
,

 
 
6
9
0
,

 
 
3
,

 
 
3
2
1
7
9
,

 
 
9
1
0
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
1
0
6
5
8
7
,

 
 
8
3
6
3
1
,

 
 
1
7
1
7
0
,

 
 
1
2
,

 
 
1
,

 
 
5
0
0
5
,

 
 
2
3
2
4
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
3
0
6
,

 
 
3
6
0
5
,

 
 
1
7
1
1
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
,

 
 
2
3
2
4
,

 
 
1
0
9
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
2
9
6
9
6
,

 
 
1
7
1
1
,

 
 
1
0
0
4
,

 
 
8
0
2
,

 
 
1
4
5
3
,

 
 
4
1
6
2
,

 
 
5
4
3
4
1
]
,

 
[
1
7
4
5
6
,

 
 
5
,

 
 
1
6
0
7
1
4
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
7
4
5
7
,

 
 
2
1
5
,

 
 
9
,

 
 
2
4
,

 
 
3
0
,

 
 
1
0
4
2
,

 
 
7
,

 
 
2
4
,

 
 
9
0
8
,

 
 
5
,

 
 
1
5
9
8
,

 
 
5
5
8
,

 
 
1
8
0
4
,

 
 
3
1
,

 
 
4
8
2
8
,

 
 
3
0
0
6
,

 
 
5
,

 
 
1
1
,

 
 
2
4
,

 
 
4
0
8
,

 
 
1
,

 
 
2
7
8
4
,

 
 
2
0
2
,

 
 
1
0
,

 
 
1
3
,

 
 
5
4
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
5
5
4
,

 
 
1
0
,

 
 
1
6
0
7
1
5
,

 
 
7
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
3
0
0
6
,

 
 
5
,

 
 
6
3
,

 
 
1
,

 
 
4
6
1
5
,

 
 
5
6
2
0
,

 
 
3
,

 
 
3
0
,

 
 
1
0
4
2
,

 
 
8
0
,

 
 
1
3
,

 
 
1
3
8
5
,

 
 
2
,

 
 
6
,

 
 
7
,

 
 
2
2
6
,

 
 
1
7
4
5
6
,

 
 
8
,

 
 
8
4
6
9
,

 
 
3
0
5
,

 
 
1
2
,

 
 
6
]
,

 
[
5
2
,

 
 
8
,

 
 
5
7
1
,

 
 
1
2
8
4
5
,

 
 
5
,

 
 
3
3
0
5
,

 
 
3
2
,

 
 
3
0
,

 
 
5
2
2
4
,

 
 
6
3
,

 
 
2
6
5
,

 
 
6
0
8
,

 
 
1
7
9
,

 
 
3
,

 
 
1
8
0
9
,

 
 
3
9
0
4
,

 
 
1
2
0
6
,

 
 
1
6
4
,

 
 
1
,

 
 
1
1
4
,

 
 
2
,

 
 
1
6
1
0
]
,

 
[
5
,

 
 
1
2
0
6
,

 
 
1
2
8
3
,

 
 
3
,

 
 
1
,

 
 
2
7
0
7
,

 
 
2
4
1
1
,

 
 
2
2
,

 
 
5
3
,

 
 
1
8
,

 
 
2
,

 
 
7
1
1
,

 
 
2
8
,

 
 
2
5
8
5
,

 
 
3
,

 
 
1
3
2
,

 
 
5
2
3
,

 
 
1
0
9
,

 
 
5
,

 
 
7
,

 
 
5
9
,

 
 
2
6
3
,

 
 
6
1
7
7
,

 
 
8
,

 
 
1
,

 
 
1
3
2
,

 
 
5
2
3
,

 
 
1
0
9
,

 
 
1
7
,

 
 
5
3
,

 
 
6
6
,

 
 
1
9
,

 
 
1
9
8
4
,

 
 
1
3
0
,

 
 
4
0
2
,

 
 
1
5
0
,

 
 
5
3
,

 
 
5
6
,

 
 
2
3
6
,

 
 
1
,

 
 
1
0
9
,

 
 
3
,

 
 
1
,

 
 
4
2
4
,

 
 
2
3
,

 
 
6
1
7
7
,

 
 
2
4
1
1
,

 
 
2
,

 
 
1
6
0
7
1
6
]
,

 
[
2
,

 
 
5
8
2
,

 
 
2
2
,

 
 
4
,

 
 
2
8
,

 
 
2
3
,

 
 
2
2
4
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
1
1
,

 
 
8
,

 
 
6
9
,

 
 
1
5
8
,

 
 
8
,

 
 
1
3
1
4
,

 
 
9
,

 
 
1
,

 
 
2
3
,

 
 
1
5
7
6
,

 
 
2
1
8
8
,

 
 
4
5
7
,

 
 
2
8
3
,

 
 
1
1
1
,

 
 
8
6
3
,

 
 
1
8
,

 
 
1
6
5
6
,

 
 
3
2
,

 
 
1
,

 
 
4
5
1
,

 
 
1
4
0
7
,

 
 
2
9
6
2
,

 
 
5
6
3
,

 
 
1
,

 
 
2
4
4
8
,

 
 
3
,

 
 
4
,

 
 
4
5
7
,

 
 
8
7
,

 
 
1
6
,

 
 
4
,

 
 
8
4
6
,

 
 
1
2
,

 
 
1
3
6
3
,

 
 
2
2
,

 
 
1
1
,

 
 
1
5
7
6
,

 
 
2
5
0
5
,

 
 
1
0
5
,

 
 
1
7
7
,

 
 
1
7
8
3
,

 
 
2
9
5
,

 
 
1
1
,

 
 
1
5
7
6
,

 
 
1
0
5
,

 
 
5
4
,

 
 
8
,

 
 
1
0
0
6
,

 
 
1
1
8
0
,

 
 
2
,

 
 
1
6
5
1
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
3
0
,

 
 
2
9
6
2
,

 
 
2
7
3
,

 
 
1
4
0
,

 
 
1
7
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
2
4
8
,

 
 
1
,

 
 
4
2
7
,

 
 
4
1
,

 
 
7
5
6
,

 
 
1
1
]
,

 
[
1
3
6
0
5
,
 
4
,
 
2
2
2
4
,
 
5
4
6
,
 
5
0
1
0
,
 
2
4
1
,
 
5
8
,
 
2
,
 
1
1
7
,
 
3
1
7
8
,
 
4
8
3
2
,
 
7
5
0
8
,
 
2
3
9
3
]
,

 
[
2
2
1
7
,

 
 
1
5
,

 
 
8
0
7
5
,

 
 
2
3
1
6
,

 
 
2
8
9
,

 
 
1
4
,

 
 
9
1
,

 
 
4
,

 
 
3
0
8
0
,

 
 
1
8
7
3
2
,

 
 
1
1
7
2
,

 
 
6
9
5
,

 
 
1
0
5
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
4
6
]
,

 
[
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
3
5
0
,

 
 
2
7
,

 
 
2
3
,

 
 
3
,

 
 
2
2
6
3
5
,

 
 
1
4
4
8
,

 
 
4
7
3
,

 
 
6
8
,

 
 
3
5
5
1
,

 
 
2
,

 
 
6
5
2
3
,

 
 
3
,

 
 
4
6
0
4
,

 
 
1
4
8
9
1
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
1
3
,

 
 
2
3
,

 
 
8
,

 
 
3
5
,

 
 
1
6
7
6
,

 
 
9
9
0
,

 
 
1
4
,

 
 
5
5
3
,

 
 
4
,

 
 
1
9
4
2
3
,

 
 
3
3
7
,

 
 
1
0
6
5
8
8
,

 
 
1
4
3
2
,

 
 
3
5
,

 
 
1
5
4
,

 
 
2
6
,

 
 
1
4
9
3
,

 
 
4
7
9
,

 
 
1
3
9
,

 
 
1
7
,

 
 
6
1
,

 
 
3
5
2
4
,

 
 
8
3
,

 
 
1
0
,

 
 
2
8
,

 
 
1
,

 
 
8
7
7
,

 
 
3
,

 
 
6
8
,

 
 
7
5
6
6
,

 
 
1
7
6
2
,

 
 
1
8
,

 
 
1
0
4
9
,

 
 
5
0
0
,

 
 
6
8
,

 
 
1
1
6
5
3
,

 
 
1
4
8
9
2
,

 
 
1
7
,

 
 
6
5
2
3
,

 
 
8
,

 
 
1
4
,

 
 
1
3
,

 
 
8
,

 
 
3
5
1
,

 
 
1
8
3
,

 
 
2
6
7
,

 
 
9
,

 
 
4
2
,

 
 
2
3
7
,

 
 
5
7
,

 
 
2
3
2
6
]
,

 
[
9
5
,
 
1
2
6
,
 
1
2
5
6
,
 
1
8
9
8
,
 
1
2
,
 
2
3
1
2
,
 
4
8
,
 
3
8
,
 
7
,
 
1
9
,
 
1
5
,
 
3
0
,
 
1
8
6
6
,
 
2
2
1
,
 
8
3
4
2
,
 
4
2
7
7
]
,

 
[
1
1
,

 
 
8
,

 
 
1
2
5
1
,

 
 
6
9
,

 
 
7
,

 
 
4
3
,

 
 
1
1
7
,

 
 
6
3
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
1
2
,

 
 
6
,

 
 
1
0
6
5
8
9
,

 
 
1
,

 
 
1
2
3
6
,

 
 
1
0
7
,

 
 
2
1
,

 
 
2
7
,

 
 
3
3
4
,

 
 
3
1
,

 
 
2
6
9
2
,

 
 
5
,

 
 
1
,

 
 
1
0
7
,

 
 
1
0
6
5
9
0
,

 
 
2
3
2
7
,

 
 
7
5
,

 
 
1
7
7
,

 
 
4
,

 
 
2
1
2
,

 
 
8
,

 
 
1
4
,

 
 
8
1
9
,

 
 
1
0
,

 
 
2
8
,

 
 
1
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
4
7
5
,

 
 
6
,

 
 
1
8
,

 
 
2
0
0
,

 
 
2
,

 
 
2
1
9
,

 
 
1
2
,

 
 
2
7
,

 
 
2
3
2
9
,

 
 
1
0
,

 
 
1
6
6
,

 
 
7
,

 
 
3
4
,

 
 
2
6
7
1
,

 
 
2
1
9
,

 
 
6
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
2
2
,

 
 
1
3
,

 
 
2
1
7
,

 
 
1
2
3
9
3
,

 
 
7
,

 
 
4
5
,

 
 
2
3
8
9
,

 
 
2
7
,

 
 
1
4
6
1
,

 
 
7
,

 
 
3
4
,

 
 
2
6
7
1
,

 
 
2
1
9
,

 
 
3
1
,

 
 
5
5
,

 
 
6
1
1
5
,

 
 
2
,

 
 
6
3
,

 
 
4
0
,

 
 
1
,

 
 
1
5
9
9
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
6
2
8
1
,

 
 
9
,

 
 
5
1
,

 
 
4
5
,

 
 
4
6
5
8
,

 
 
9
,

 
 
5
1
,

 
 
1
9
,

 
 
5
7
,

 
 
1
0
4
2
5
,

 
 
1
0
8
0
4
,

 
 
2
1
,

 
 
4
,

 
 
3
8
1
,

 
 
4
9
9
4
,

 
 
1
7
0
2
,

 
 
6
,

 
 
4
0
,

 
 
2
3
3
,

 
 
7
4
2
,

 
 
1
9
,

 
 
1
6
3
,

 
 
1
0
,

 
 
5
2
3
,

 
 
6
,

 
 
1
8
,

 
 
4
0
,

 
 
1
0
5
0
,

 
 
4
0
,

 
 
2
3
3
,

 
 
3
,

 
 
6
]
,

 
[
7
,

 
 
4
9
,

 
 
3
6
9
0
,

 
 
1
,

 
 
7
2
7
,

 
 
8
0
2
,

 
 
5
,

 
 
7
,

 
 
2
6
3
,

 
 
1
3
,

 
 
7
2
7
,

 
 
2
3
,

 
 
5
,

 
 
4
3
0
,

 
 
6
1
,

 
 
1
0
,

 
 
1
,

 
 
1
0
6
5
9
1
,

 
 
6
0
7
9
5
,

 
 
8
3
,

 
 
1
8
,

 
 
4
0
,

 
 
3
1
,

 
 
4
,

 
 
1
2
6
1
,

 
 
6
2
,

 
 
1
0
8
4
,

 
 
6
0
7
9
5
,

 
 
8
7
3
,

 
 
7
0
8
,

 
 
3
,

 
 
3
3
5
,

 
 
3
6
,

 
 
7
2
8
,

 
 
1
6
5
,

 
 
2
,

 
 
8
8
2
,

 
 
1
1
]
,

 
[
1
3
0
1
,

 
 
4
5
,

 
 
1
5
9
,

 
 
4
,

 
 
7
9
3
4
,

 
 
3
3
,

 
 
1
1
,

 
 
1
1
,

 
 
6
6
,

 
 
3
2
3
,

 
 
6
6
4
,

 
 
2
4
0
4
,

 
 
2
4
1
7
,

 
 
5
,

 
 
1
7
7
6
3
,

 
 
1
1
,

 
 
1
0
8
2
,

 
 
1
5
5
,

 
 
1
2
8
,

 
 
4
8
,

 
 
4
,

 
 
1
2
5
2
,

 
 
2
0
2
4
,

 
 
1
,

 
 
2
9
5
,

 
 
1
8
,

 
 
4
0
,

 
 
3
0
4
,

 
 
1
6
0
5
,

 
 
2
2
4
,

 
 
2
5
,

 
 
2
4
2
,

 
 
4
9
8
3
,

 
 
7
2
,

 
 
2
6
8
,

 
 
2
,

 
 
3
3
,

 
 
3
0
8
,

 
 
2
2
1
0
9
,

 
 
3
2
2
,

 
 
1
,

 
 
2
2
1
,

 
 
5
5
8
2
,

 
 
3
4
9
,

 
 
8
6
3
,

 
 
1
0
3
,

 
 
8
2
,

 
 
6
0
,

 
 
1
2
1
,

 
 
2
1
,

 
 
1
,

 
 
4
0
6
9
,

 
 
1
1
6
,

 
 
1
5
5
]
,

 
[
2
1
7
,

 
 
8
,

 
 
1
2
,

 
 
2
6
5
,

 
 
6
0
8
,

 
 
1
3
,

 
 
7
2
2
,

 
 
3
,

 
 
7
9
,

 
 
1
2
6
1
,

 
 
1
6
7
,

 
 
9
,

 
 
1
,

 
 
2
8
6
5
2
,

 
 
2
4
,

 
 
1
4
3
0
,

 
 
3
6
,

 
 
7
,

 
 
3
6
8
,

 
 
1
1
,

 
 
1
2
3
2
,

 
 
7
,

 
 
3
6
8
,

 
 
1
1
,

 
 
6
9
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
1
2
0
,

 
 
2
,

 
 
4
6
8
,

 
 
9
,

 
 
5
2
,

 
 
2
4
,

 
 
1
4
3
0
,

 
 
3
6
,

 
 
7
,

 
 
3
4
,

 
 
7
0
,

 
 
3
8
,

 
 
2
1
7
,

 
 
8
,

 
 
7
,

 
 
4
9
,

 
 
1
0
8
,

 
 
2
,

 
 
2
8
6
1
,

 
 
1
5
,

 
 
1
2
9
,

 
 
1
8
0
,

 
 
7
,

 
 
4
7
7
,

 
 
1
3
,

 
 
2
0
2
,

 
 
7
1
,

 
 
2
8
3
7
,

 
 
5
0
,

 
 
5
9
,

 
 
9
7
,

 
 
3
7
,

 
 
3
1
7
,

 
 
8
9
,

 
 
9
,

 
 
1
3
7
,

 
 
1
2
2
4
,

 
 
4
9
9
,

 
 
5
0
,

 
 
5
0
,

 
 
9
6
8
,

 
 
3
7
,

 
 
9
5
,

 
 
6
0
7
9
6
]
,

 
[
4
9
4
4
5
,

 
 
2
6
4
2
,

 
 
8
9
8
2
,

 
 
8
2
6
,

 
 
1
1
3
9
,

 
 
1
3
,

 
 
8
,

 
 
8
4
1
,

 
 
1
3
4
4
,

 
 
1
3
2
9
,

 
 
3
2
,

 
 
4
,

 
 
1
8
0
,

 
 
1
5
3
6
,

 
 
1
0
6
9
,

 
 
1
6
3
9
7
,

 
 
1
1
8
,

 
 
1
0
4
0
,

 
 
4
5
5
,

 
 
1
6
3
9
7
,

 
 
2
8
9
,

 
 
1
5
2
7
6
,

 
 
2
2
5
,

 
 
1
9
8
7
,

 
 
3
1
2
,

 
 
1
6
0
5
,

 
 
2
4
3
,

 
 
9
2
3
,

 
 
8
5
2
,

 
 
1
6
0
7
1
7
,

 
 
1
6
0
7
1
8
]
,

 
[
7
,

 
 
3
9
,

 
 
3
7
3
,

 
 
6
,

 
 
3
8
,

 
 
1
,

 
 
6
2
7
,

 
 
8
,

 
 
3
5
,

 
 
6
4
,

 
 
1
0
6
5
9
2
,

 
 
7
1
,

 
 
3
5
,

 
 
2
0
,

 
 
2
7
6
8
7
,

 
 
3
3
8
1
,

 
 
3
,

 
 
4
,

 
 
7
5
0
,

 
 
7
9
,

 
 
2
6
8
,

 
 
2
,

 
 
4
4
8
,

 
 
1
3
5
5
,

 
 
1
0
7
3
,

 
 
3
8
3
3
,

 
 
3
,

 
 
3
9
6
9
8
,

 
 
3
7
4
1
8
,

 
 
1
0
,

 
 
4
6
7
0
,

 
 
4
9
4
4
6
,

 
 
3
5
3
9
1
,

 
 
3
2
,

 
 
1
0
6
5
9
3
,

 
 
5
,

 
 
2
0
6
6
2
,

 
 
2
1
4
4
,

 
 
1
0
1
7
,

 
 
1
7
7
,

 
 
1
3
8
,

 
 
4
,

 
 
2
7
3
,

 
 
9
,

 
 
7
,

 
 
4
5
4
,

 
 
4
2
,

 
 
1
4
,

 
 
3
5
1
,

 
 
5
7
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
2
7
3
,

 
 
1
6
1
,

 
 
1
5
3
,

 
 
1
5
1
,

 
 
4
0
,

 
 
1
3
,

 
 
8
5
,

 
 
1
3
,

 
 
8
,

 
 
1
5
1
,

 
 
6
,

 
 
1
5
6
2
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
1
6
7
2
,

 
 
3
,

 
 
1
,

 
 
1
5
5
9
,

 
 
3
7
9
,

 
 
1
9
4
6
,

 
 
5
,

 
 
1
,

 
 
1
2
5
5
,

 
 
5
5
,

 
 
9
0
3
,

 
 
2
,

 
 
3
4
,

 
 
7
5
0
,

 
 
2
7
3
,

 
 
1
6
1
,

 
 
1
4
0
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
1
9
,

 
 
5
7
,

 
 
2
7
6
8
8
,

 
 
3
2
,

 
 
4
4
,

 
 
4
6
2
,

 
 
9
,

 
 
6
6
6
,

 
 
6
0
9
1
,

 
 
8
9
9
,

 
 
5
,

 
 
1
6
7
2
,

 
 
2
0
5
,

 
 
1
,

 
 
1
1
6
5
4
,

 
 
2
2
8
,

 
 
2
,

 
 
3
4
,

 
 
6
4
,

 
 
4
3
,

 
 
1
6
,

 
 
2
,

 
 
1
4
7
1
8
,

 
 
2
2
5
,

 
 
3
1
,

 
 
1
2
9
,

 
 
1
,

 
 
2
9
,

 
 
1
7
,

 
 
7
,

 
 
1
9
,

 
 
2
6
,

 
 
7
,

 
 
7
0
2
,

 
 
4
4
6
,

 
 
9
,

 
 
2
6
9
3
,

 
 
3
8
8
,

 
 
8
9
,

 
 
9
8
,

 
 
1
4
5
1
,

 
 
2
1
,

 
 
1
1
,

 
 
5
0
5
,

 
 
2
3
7
,

 
 
1
3
1
,

 
 
7
9
6
,

 
 
4
2
8
5
,

 
 
3
,

 
 
5
0
1
1
]
,

 
[
3
2
0
,
 
7
4
,
 
3
4
,
 
7
,
 
9
4
,
 
1
2
6
1
,
 
2
,
 
8
8
2
,
 
2
2
7
,
 
3
1
5
,
 
6
4
]
,

 
[
6
5
7
8
,

 
 
7
4
,

 
 
2
5
2
1
,

 
 
6
,

 
 
4
5
8
,

 
 
3
0
,

 
 
1
3
5
8
,

 
 
1
1
2
7
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
1
8
0
7
1
,

 
 
5
,

 
 
7
,

 
 
1
3
1
,

 
 
4
,

 
 
6
0
7
9
7
,

 
 
3
,

 
 
5
7
7
4
,

 
 
6
5
7
8
,

 
 
6
,

 
 
2
3
4
3
,

 
 
1
9
1
6
,

 
 
2
8
8
3
,

 
 
5
,

 
 
1
6
0
7
1
9
,

 
 
3
3
6
8
4
,

 
 
7
3
2
7
,

 
 
2
7
8
5
,

 
 
1
1
4
3
,

 
 
9
2
3
,

 
 
7
6
,

 
 
4
4
9
8
,

 
 
1
3
,

 
 
1
8
3
7
9
,

 
 
7
1
4
4
,

 
 
8
,

 
 
2
6
8
,

 
 
2
,

 
 
3
0
8
0
,

 
 
1
,

 
 
7
8
6
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
3
7
4
1
9
,

 
 
2
0
4
3
,

 
 
6
4
,

 
 
4
4
,

 
 
3
5
1
8
,

 
 
5
3
3
9
,

 
 
1
0
,

 
 
2
8
,

 
 
6
,

 
 
3
0
1
,

 
 
7
1
4
4
,

 
 
5
,

 
 
6
,

 
 
2
3
8
3
1
,

 
 
1
0
8
,

 
 
4
0
1
0
,

 
 
2
,

 
 
1
,

 
 
8
3
6
3
4
]
,

 
[
9
2
8
,

 
 
6
1
,

 
 
2
0
5
,

 
 
2
6
3
,

 
 
9
,

 
 
1
,

 
 
1
4
0
,

 
 
7
,

 
 
1
3
1
,

 
 
8
6
,

 
 
2
7
5
2
,

 
 
4
,

 
 
4
3
8
,

 
 
3
,

 
 
3
2
4
7
,

 
 
3
6
9
1
,

 
 
6
3
0
,

 
 
1
7
,

 
 
4
,

 
 
9
6
6
,

 
 
2
,

 
 
3
9
8
,

 
 
2
7
,

 
 
2
3
,

 
 
2
,

 
 
9
2
,

 
 
1
7
0
,

 
 
4
1
3
,

 
 
8
,

 
 
3
8
,

 
 
4
2
,

 
 
1
8
8
4
,

 
 
1
3
,

 
 
2
1
3
,

 
 
3
3
,

 
 
2
6
7
,

 
 
2
4
,

 
 
1
,

 
 
8
6
1
1
,

 
 
2
7
7
,

 
 
5
4
,

 
 
8
,

 
 
2
7
5
2
,

 
 
2
4
,

 
 
6
6
8
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
3
2
,

 
 
4
7
,

 
 
2
9
2
,

 
 
1
6
3
1
,

 
 
3
2
,

 
 
3
7
,

 
 
1
6
3
1
,

 
 
1
2
7
,

 
 
3
2
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
5
,

 
 
1
6
3
1
,

 
 
1
2
7
,

 
 
3
2
,

 
 
3
7
,

 
 
4
2
0
,

 
 
2
0
5
,

 
 
3
6
,

 
 
3
1
3
,

 
 
1
9
,

 
 
3
2
7
4
,

 
 
1
,

 
 
2
7
7
,

 
 
1
7
9
8
,

 
 
4
1
,

 
 
7
2
,

 
 
1
8
6
,

 
 
4
,

 
 
2
5
7
5
,

 
 
2
9
2
,

 
 
8
,

 
 
1
6
5
,

 
 
2
,

 
 
5
7
3
2
,

 
 
1
0
,

 
 
1
5
,

 
 
1
3
,

 
 
6
5
4
,

 
 
1
5
5
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
1
3
3
3
4
,

 
 
2
1
,

 
 
9
9
9
4
,

 
 
3
6
1
,

 
 
5
0
,

 
 
1
9
3
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
5
3
0
,

 
 
9
9
9
4
,

 
 
3
6
1
,

 
 
1
4
3
,

 
 
7
3
,

 
 
2
,

 
 
1
,

 
 
3
8
9
5
,

 
 
7
3
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
3
9
5
,

 
 
1
5
3
,

 
 
1
5
2
5
,

 
 
5
8
,

 
 
1
0
,

 
 
4
1
,

 
 
9
,

 
 
3
2
3
,

 
 
2
,

 
 
2
6
9
,

 
 
7
6
,

 
 
1
5
0
,

 
 
1
,

 
 
8
6
1
1
,

 
 
2
7
7
,

 
 
5
6
,

 
 
1
6
,

 
 
1
8
7
,

 
 
2
8
3
9
,

 
 
7
,

 
 
5
9
,

 
 
2
2
0
,

 
 
7
,

 
 
3
3
1
7
,

 
 
1
,

 
 
1
4
9
1
,

 
 
7
2
3
,

 
 
5
4
,

 
 
1
6
7
1
,

 
 
4
,

 
 
3
0
0
2
,

 
 
3
3
8
1
]
,

 
[
2
0
8
,

 
 
7
,

 
 
2
6
3
,

 
 
9
,

 
 
1
4
5
4
6
,

 
 
4
1
1
9
,

 
 
1
5
6
8
0
,

 
 
8
,

 
 
1
,

 
 
3
7
4
,

 
 
1
0
9
,

 
 
1
2
,

 
 
1
,

 
 
1
5
6
8
0
,

 
 
1
,

 
 
3
0
0
3
,

 
 
1
8
2
4
,

 
 
2
5
5
,

 
 
8
,

 
 
1
4
,

 
 
1
6
0
7
2
0
,

 
 
1
4
5
3
,

 
 
1
0
,

 
 
6
6
7
,

 
 
3
,

 
 
3
5
8
,

 
 
4
3
7
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
9
4
6
,

 
 
3
3
,

 
 
4
0
,

 
 
9
,

 
 
1
,

 
 
7
0
1
7
,

 
 
4
5
5
5
4
,

 
 
3
,

 
 
1
,

 
 
2
5
1
5
0
,

 
 
2
4
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
3
,

 
 
8
9
,

 
 
5
2
6
5
,

 
 
2
2
4
8
,

 
 
1
,

 
 
5
6
6
9
,

 
 
8
,

 
 
5
4
0
,

 
 
7
0
9
,

 
 
2
,

 
 
8
9
3
,

 
 
2
2
0
3
,

 
 
3
1
,

 
 
4
1
,

 
 
9
1
,

 
 
4
7
9
,

 
 
9
4
6
,

 
 
2
,

 
 
9
2
0
,

 
 
9
,

 
 
2
9
6
9
7
,

 
 
9
0
,

 
 
8
3
4
,

 
 
1
7
,

 
 
1
3
,

 
 
5
2
6
5
,

 
 
2
2
4
8
,

 
 
4
7
3
,

 
 
1
4
3
7
0
,

 
 
4
7
9
,

 
 
1
7
,

 
 
2
,

 
 
7
8
,

 
 
1
1
,

 
 
1
4
5
4
7
,

 
 
7
3
,

 
 
1
,

 
 
3
8
9
,

 
 
6
6
,

 
 
6
9
8
,

 
 
2
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
4
,

 
 
4
,

 
 
1
9
0
6
0
,

 
 
3
,

 
 
1
,

 
 
1
4
5
4
6
,

 
 
1
3
7
3
8
,

 
 
1
4
5
,

 
 
2
3
3
,

 
 
3
,

 
 
1
,

 
 
3
0
0
3
,

 
 
1
8
2
4
,

 
 
2
5
5
,

 
 
5
,

 
 
1
0
,

 
 
1
6
6
,

 
 
5
8
9
3
,

 
 
1
,

 
 
6
0
9
0
,

 
 
3
,

 
 
1
,

 
 
6
9
8
3
3
,

 
 
5
,

 
 
1
,

 
 
3
3
6
8
5
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
2
2
4
8
,

 
 
6
2
5
,

 
 
3
,

 
 
7
1
,

 
 
1
7
0
,

 
 
5
,

 
 
2
3
8
,

 
 
4
,

 
 
6
3
2
,

 
 
3
7
2
,

 
 
3
,

 
 
8
3
0
,

 
 
1
9
,

 
 
5
7
,

 
 
2
9
1
,

 
 
6
7
7
,

 
 
1
3
,

 
 
2
2
4
8
,

 
 
6
2
5
,

 
 
9
2
5
,

 
 
3
,

 
 
8
8
,

 
 
1
8
,

 
 
3
,

 
 
1
,

 
 
2
5
1
4
,

 
 
3
,

 
 
1
6
0
7
2
1
,

 
 
1
6
0
7
2
2
,

 
 
1
4
3
0
,

 
 
1
,

 
 
1
4
5
4
6
,

 
 
4
1
1
9
,

 
 
2
7
7
,

 
 
1
7
,

 
 
1
,

 
 
3
7
4
,

 
 
4
7
,

 
 
2
9
6
9
7
,

 
 
9
0
,

 
 
8
3
4
,

 
 
6
2
3
,

 
 
1
,

 
 
7
7
0
7
,

 
 
8
,

 
 
1
7
5
4
,

 
 
5
,

 
 
1
4
,

 
 
1
,

 
 
1
6
9
2
,

 
 
2
9
6
9
8
,

 
 
1
1
,

 
 
8
,

 
 
1
3
3
3
5
,

 
 
5
,

 
 
1
5
6
8
1
,

 
 
1
3
2
5
,

 
 
1
0
6
5
9
4
,

 
 
5
,

 
 
2
8
1
,

 
 
1
3
3
3
5
,

 
 
8
,

 
 
5
8
,

 
 
1
7
5
4
,

 
 
6
2
3
,

 
 
9
3
,

 
 
7
1
,

 
 
1
6
9
2
]
,

 
[
1
1
1
2
,

 
 
1
4
0
6
,

 
 
2
1
6
,

 
 
9
5
,

 
 
7
,

 
 
1
9
,

 
 
5
1
3
,

 
 
6
3
0
,

 
 
1
5
,

 
 
1
6
0
7
2
3
,

 
 
3
5
3
9
2
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
2
2
3
6
,

 
 
2
,

 
 
9
4
,

 
 
1
,

 
 
5
1
0
,

 
 
2
5
3
,

 
 
3
1
,

 
 
1
,

 
 
1
6
0
7
2
4
,

 
 
1
5
8
8
0
,

 
 
1
6
6
4
6
,

 
 
1
2
4
,

 
 
6
9
8
3
4
,

 
 
4
9
4
4
7
,

 
 
3
4
,

 
 
1
4
,

 
 
7
5
4
,

 
 
1
0
,

 
 
1
,

 
 
3
3
7
,

 
 
1
8
2
,

 
 
6
1
5
,

 
 
2
6
0
5
,

 
 
3
9
,

 
 
6
,

 
 
4
6
8
,

 
 
4
,

 
 
2
6
0
5
,

 
 
5
4
,

 
 
1
0
5
8
,

 
 
1
,

 
 
5
1
0
,

 
 
2
5
3
,

 
 
1
0
,

 
 
1
,

 
 
4
0
1
1
,

 
 
7
,

 
 
1
9
,

 
 
3
4
2
5
,

 
 
1
3
,

 
 
6
7
3
,

 
 
2
3
,

 
 
1
6
0
7
2
5
,

 
 
3
5
3
9
2
,

 
 
5
4
,

 
 
6
,

 
 
8
7
,

 
 
4
8
,

 
 
2
,

 
 
6
3
,

 
 
5
,

 
 
1
5
2
,

 
 
7
9
,

 
 
3
0
8
3
0
,

 
 
1
5
2
1
,

 
 
3
1
1
1
,

 
 
2
3
3
]
,

 
[
7
,

 
 
4
8
3
3
,

 
 
7
5
,

 
 
1
5
,

 
 
4
7
4
,

 
 
1
8
0
,

 
 
2
1
,

 
 
4
3
4
,

 
 
2
,

 
 
8
8
2
9
,

 
 
3
0
,

 
 
4
3
2
5
,

 
 
7
0
7
,

 
 
6
,

 
 
1
8
,

 
 
3
0
9
,

 
 
3
0
7
3
,

 
 
1
,

 
 
6
6
2
,

 
 
7
5
,

 
 
4
6
8
9
,

 
 
1
4
8
]
,

 
[
2
0
0
9
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
2
8
4
,

 
 
1
,

 
 
2
3
4
,

 
 
2
9
1
,

 
 
3
3
,

 
 
1
0
4
,

 
 
1
5
5
9
,

 
 
3
7
9
,

 
 
5
6
,

 
 
6
6
,

 
 
1
6
,

 
 
1
0
2
,

 
 
8
4
5
,

 
 
2
6
,

 
 
7
,

 
 
7
0
2
,

 
 
9
9
,

 
 
5
5
,

 
 
8
5
,

 
 
2
,

 
 
2
0
3
,

 
 
8
6
2
,

 
 
9
2
9
,

 
 
1
4
1
,

 
 
1
4
0
8
,

 
 
6
6
9
,

 
 
8
3
6
3
5
]
,

 
[
7
4
,

 
 
3
4
,

 
 
6
,

 
 
7
0
,

 
 
5
2
,

 
 
8
,

 
 
9
3
1
,

 
 
1
0
4
,

 
 
4
9
,

 
 
6
8
,

 
 
4
0
5
1
,

 
 
9
,

 
 
1
1
8
5
3
,

 
 
1
0
6
5
9
5
,

 
 
2
2
9
9
,

 
 
1
8
3
8
0
,

 
 
6
8
,

 
 
4
5
9
7
,

 
 
2
3
7
7
]
,

 
[
4
5
5
5
5
,

 
 
1
7
1
8
,

 
 
3
4
1
,

 
 
2
1
7
,

 
 
1
1
7
8
,

 
 
1
7
7
6
4
,

 
 
7
,

 
 
5
4
1
,

 
 
1
3
,

 
 
1
9
3
,

 
 
2
,

 
 
2
5
5
5
,

 
 
6
,

 
 
9
,

 
 
2
7
,

 
 
2
9
2
,

 
 
8
,

 
 
5
7
3
8
,

 
 
2
3
0
1
,

 
 
3
,

 
 
2
1
7
,

 
 
1
0
,

 
 
1
,

 
 
4
2
1
,

 
 
3
,

 
 
1
,

 
 
1
5
0
8
,

 
 
1
7
1
8
,

 
 
1
9
8
7
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
5
0
8
,

 
 
1
7
1
8
,

 
 
5
0
,

 
 
7
,

 
 
4
3
,

 
 
6
8
5
,

 
 
2
2
,

 
 
6
,

 
 
1
0
3
,

 
 
3
7
3
,

 
 
3
7
,

 
 
6
2
,

 
 
7
,

 
 
5
6
,

 
 
5
7
6
,

 
 
1
3
,

 
 
8
5
1
,

 
 
1
,

 
 
1
3
7
0
,

 
 
1
2
9
9
,

 
 
1
0
9
,

 
 
8
,

 
 
1
9
8
7
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
0
7
,

 
 
8
3
6
3
6
]
,

 
[
6
,

 
 
1
8
,

 
 
4
,

 
 
7
0
,

 
 
1
1
,

 
 
4
0
,

 
 
1
7
0
5
,

 
 
7
8
,

 
 
5
9
,

 
 
6
,

 
 
9
4
,

 
 
4
,

 
 
3
0
0
,

 
 
3
8
2
,

 
 
3
,

 
 
3
6
8
9
,

 
 
1
0
,

 
 
1
4
2
0
,

 
 
3
,

 
 
2
0
,

 
 
1
0
0
5
,

 
 
4
0
,

 
 
3
0
3
,

 
 
1
,

 
 
5
6
4
,

 
 
4
2
3
7
1
,

 
 
3
,

 
 
7
4
8
,

 
 
7
3
4
]
,

 
[
4
0
,

 
 
3
,

 
 
1
4
1
,

 
 
8
6
3
,

 
 
1
2
2
,

 
 
2
,

 
 
1
6
,

 
 
1
2
8
5
,

 
 
1
4
3
0
,

 
 
2
7
,

 
 
2
3
,

 
 
3
6
0
6
,

 
 
1
0
,

 
 
3
0
6
,

 
 
1
1
6
,

 
 
8
4
2
4
,

 
 
1
,

 
 
3
0
8
1
,

 
 
1
2
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
5
,

 
 
1
,

 
 
1
1
9
9
,

 
 
1
2
,

 
 
3
4
5
6
,

 
 
2
1
8
8
,

 
 
1
0
5
,

 
 
2
,

 
 
1
4
5
,

 
 
7
6
,

 
 
4
7
,

 
 
2
2
8
,

 
 
2
3
1
,

 
 
1
0
1
8
,

 
 
7
3
,

 
 
1
4
0
5
0
,

 
 
4
5
5
5
6
,

 
 
8
6
2
,

 
 
9
5
1
,

 
 
1
1
4
,

 
 
1
1
,

 
 
4
2
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
7
7
0
,

 
 
1
5
,

 
 
1
1
,

 
 
1
,

 
 
1
0
2
7
,

 
 
3
,

 
 
8
3
,

 
 
9
,

 
 
1
2
2
,

 
 
2
,

 
 
1
6
,

 
 
9
1
7
,

 
 
5
6
,

 
 
1
6
,

 
 
2
1
2
,

 
 
3
7
2
,

 
 
1
6
2
,

 
 
2
,

 
 
2
5
6
,

 
 
1
,

 
 
1
5
5
7
,

 
 
4
3
7
,

 
 
1
,

 
 
7
7
,

 
 
2
7
3
,

 
 
1
6
9
,

 
 
7
3
6
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
1
3
,

 
 
4
7
,

 
 
2
0
8
,

 
 
1
,

 
 
1
0
5
,

 
 
8
,

 
 
3
1
,

 
 
7
8
3
,

 
 
8
2
4
6
,

 
 
3
,

 
 
9
,

 
 
1
1
,

 
 
5
5
7
,

 
 
9
,

 
 
1
,

 
 
7
5
3
1
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
2
9
1
,

 
 
3
3
,

 
 
1
3
,

 
 
6
3
8
7
,

 
 
1
6
9
,

 
 
7
1
,

 
 
4
4
1
,

 
 
9
,

 
 
6
0
,

 
 
5
8
5
,

 
 
3
1
,

 
 
1
3
,

 
 
1
7
,

 
 
1
0
1
,

 
 
7
,

 
 
2
2
9
,

 
 
3
7
3
,

 
 
2
3
1
,

 
 
6
6
,

 
 
1
9
3
,

 
 
9
,

 
 
1
,

 
 
1
9
0
,

 
 
3
,

 
 
1
,

 
 
5
1
5
,

 
 
1
1
,

 
 
2
4
,

 
 
5
5
5
,

 
 
3
1
,

 
 
2
4
,

 
 
1
9
9
,

 
 
9
4
1
,

 
 
2
,

 
 
1
6
,

 
 
1
3
1
0
,

 
 
3
6
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
1
3
3
3
4
,

 
 
2
1
,

 
 
5
3
5
9
,

 
 
1
7
2
0
,

 
 
1
2
0
2
,

 
 
4
1
2
5
,

 
 
1
6
4
8
,

 
 
1
5
,

 
 
1
0
2
7
,

 
 
1
,

 
 
1
9
0
1
,

 
 
1
5
6
,

 
 
1
4
0
5
0
,

 
 
4
5
5
5
6
,

 
 
8
6
2
,

 
 
9
5
1
,

 
 
1
1
7
3
,

 
 
7
3
9
,

 
 
1
6
0
7
2
6
,

 
 
8
,

 
 
4
,

 
 
1
6
7
6
,

 
 
2
1
3
0
,

 
 
2
,

 
 
1
,

 
 
6
0
7
9
8
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
3
1
2
9
,

 
 
1
3
7
,

 
 
1
9
9
,

 
 
8
2
0
,

 
 
1
3
,

 
 
1
2
0
0
,

 
 
2
,

 
 
2
6
4
,

 
 
9
3
,

 
 
3
2
,

 
 
5
,

 
 
8
5
9
,

 
 
1
1
,

 
 
8
,

 
 
9
7
4
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
4
8
5
,

 
 
1
1
,

 
 
1
,

 
 
5
1
4
,

 
 
8
,

 
 
6
6
,

 
 
1
1
3
8
,

 
 
2
7
,

 
 
3
9
3
,

 
 
8
3
6
3
7
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
6
,

 
 
3
9
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
6
9
8
3
5
]
,

 
[
4
6
3
,
 
7
,
 
4
9
,
 
2
1
9
,
 
1
2
,
 
2
0
,
 
1
1
3
2
,
 
3
8
,
 
6
,
 
6
5
,
 
3
5
,
 
1
,
 
2
2
6
6
]
,

 
[
5
4
4
9
,

 
 
7
4
,

 
 
3
9
,

 
 
2
5
9
,

 
 
8
5
9
,

 
 
9
8
,

 
 
5
8
8
,

 
 
8
0
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
5
5
3
,

 
 
3
6
,

 
 
1
2
8
,

 
 
2
4
8
,

 
 
1
3
3
3
6
,

 
 
1
5
,

 
 
9
,

 
 
2
9
,

 
 
1
1
,

 
 
8
,

 
 
4
2
4
1
,

 
 
3
1
,

 
 
1
,

 
 
1
1
9
2
,

 
 
7
4
,

 
 
1
0
4
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
3
2
8
5
,

 
 
1
0
6
,

 
 
1
2
,

 
 
1
5
4
7
7
,

 
 
5
,

 
 
8
4
,

 
 
1
0
4
2
2
,

 
 
9
2
0
2
,

 
 
1
,

 
 
1
3
9
,

 
 
1
0
6
,

 
 
1
2
,

 
 
1
,

 
 
1
4
0
5
1
,

 
 
6
,

 
 
1
8
,

 
 
1
,

 
 
7
7
,

 
 
2
2
2
,

 
 
3
2
9
7
,

 
 
1
5
,

 
 
9
,

 
 
2
3
,

 
 
5
,

 
 
1
9
1
1
,

 
 
1
1
,

 
 
2
9
6
,

 
 
7
,

 
 
4
5
,

 
 
1
0
4
6
,

 
 
2
,

 
 
6
1
,

 
 
8
3
,

 
 
1
5
,

 
 
1
8
0
,

 
 
1
5
5
,

 
 
2
6
,

 
 
2
7
8
,

 
 
3
7
,

 
 
1
1
4
,

 
 
3
7
4
,

 
 
2
1
8
,

 
 
1
5
,

 
 
1
4
8
9
3
,

 
 
1
7
,

 
 
3
6
,

 
 
1
2
8
,

 
 
2
4
7
,

 
 
4
2
,

 
 
5
7
,

 
 
1
6
5
,

 
 
1
5
,

 
 
4
1
,

 
 
6
,

 
 
2
8
2
,

 
 
1
0
6
5
9
6
,

 
 
7
7
3
,

 
 
5
,

 
 
8
9
,

 
 
6
,

 
 
1
9
,

 
 
2
8
2
,

 
 
3
7
,

 
 
7
7
3
,

 
 
5
,

 
 
6
,

 
 
4
5
,

 
 
9
4
,

 
 
2
5
9
,

 
 
7
7
3
,

 
 
6
,

 
 
8
1
1
0
,

 
 
3
1
,

 
 
2
0
,

 
 
8
9
9
,

 
 
1
1
6
7
,

 
 
1
5
,

 
 
1
3
3
3
6
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
2
5
8
,

 
 
7
3
,

 
 
7
,

 
 
4
5
,

 
 
7
1
1
,

 
 
4
0
,

 
 
1
1
3
,

 
 
5
7
0
,

 
 
5
,

 
 
4
5
,

 
 
2
3
0
2
,

 
 
9
,

 
 
7
,

 
 
9
4
,

 
 
2
1
8
,

 
 
1
9
9
5
,

 
 
1
5
,

 
 
1
4
8
9
3
,

 
 
5
,

 
 
4
7
6
,

 
 
2
7
8
,

 
 
2
0
,

 
 
5
,

 
 
6
0
7
9
9
,

 
 
2
4
2
,

 
 
7
5
1
,

 
 
9
7
4
7
,

 
 
9
,

 
 
2
9
,

 
 
1
7
4
6
]
,

 
[
8
6
4
,

 
 
1
1
1
2
,

 
 
8
3
8
,

 
 
2
1
6
,

 
 
5
9
,

 
 
1
9
9
4
,

 
 
7
,

 
 
7
7
8
,

 
 
6
,

 
 
7
,

 
 
9
9
,

 
 
2
0
,

 
 
1
5
7
,

 
 
5
,

 
 
2
3
1
,

 
 
3
0
7
,

 
 
2
,

 
 
2
2
5
2
,

 
 
1
6
4
2
,

 
 
7
5
6
7
,

 
 
5
3
,

 
 
2
8
2
,

 
 
1
7
5
,

 
 
9
4
6
,

 
 
3
,

 
 
1
4
2
,

 
 
8
0
,

 
 
7
,

 
 
1
1
4
,

 
 
6
8
7
,

 
 
1
1
,

 
 
7
,

 
 
2
4
,

 
 
4
8
,

 
 
4
5
5
5
7
,

 
 
4
4
,

 
 
2
6
1
,

 
 
2
3
8
3
2
,

 
 
8
4
6
,

 
 
7
,

 
 
5
8
4
,

 
 
6
,

 
 
3
6
8
,

 
 
9
,

 
 
1
2
0
,

 
 
4
7
,

 
 
8
5
,

 
 
2
6
,

 
 
8
0
,

 
 
7
,

 
 
1
0
3
2
,

 
 
1
4
8
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
6
8
7
,

 
 
1
6
7
8
,

 
 
4
5
2
3
,

 
 
7
,

 
 
2
4
,

 
 
4
8
,

 
 
3
0
8
3
1
,

 
 
2
8
6
5
3
,

 
 
3
6
,

 
 
7
,

 
 
3
6
8
,

 
 
1
1
,

 
 
7
2
,

 
 
1
3
2
1
,

 
 
6
,

 
 
7
7
1
,

 
 
1
6
5
,

 
 
1
5
7
,

 
 
7
2
,

 
 
1
3
2
1
,

 
 
3
0
,

 
 
1
4
9
,

 
 
4
0
9
,

 
 
1
9
,

 
 
1
0
8
6
,

 
 
1
5
,

 
 
2
,

 
 
1
5
6
7
,

 
 
3
7
,

 
 
2
1
4
,

 
 
4
3
,

 
 
6
,

 
 
4
8
,

 
 
1
2
,

 
 
3
7
,

 
 
2
,

 
 
1
9
7
3
,

 
 
2
8
9
7
,

 
 
1
5
,

 
 
4
0
,

 
 
4
5
3
4
,

 
 
7
9
5
,

 
 
1
3
9
2
,

 
 
9
1
2
,

 
 
1
5
8
2
]
,

 
[
1
1
5
5
,

 
 
1
1
5
3
,

 
 
2
1
6
,

 
 
7
,

 
 
2
6
3
,

 
 
2
1
,

 
 
3
8
3
,

 
 
2
9
6
9
9
,

 
 
8
,

 
 
2
0
9
,

 
 
7
3
,

 
 
6
8
,

 
 
2
2
8
4
,

 
 
3
0
9
6
,

 
 
3
,

 
 
7
5
0
9
,

 
 
2
9
6
9
9
,

 
 
5
0
,

 
 
5
6
3
,

 
 
1
,

 
 
2
3
,

 
 
3
9
6
9
9
,

 
 
5
,

 
 
1
1
6
5
5
,

 
 
1
6
0
,

 
 
5
1
4
0
,

 
 
5
0
1
2
,

 
 
7
3
9
3
,

 
 
1
8
7
2
,

 
 
2
6
8
7
,

 
 
1
3
9
9
]
,

 
[
4
6
3
,

 
 
7
,

 
 
4
8
,

 
 
1
,

 
 
1
6
0
7
2
7
,

 
 
1
2
7
2
9
,

 
 
1
7
4
5
,

 
 
1
0
2
,

 
 
1
2
8
,

 
 
7
3
4
,

 
 
2
2
,

 
 
6
,

 
 
1
0
3
,

 
 
1
4
5
,

 
 
3
7
,

 
 
1
1
1
5
,

 
 
6
1
,

 
 
1
0
5
0
,

 
 
3
9
6
7
6
,

 
 
6
5
3
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
2
8
4
,

 
 
5
,

 
 
1
6
0
7
2
8
,

 
 
1
2
,

 
 
3
7
,

 
 
6
4
,

 
 
1
8
,

 
 
6
0
,

 
 
1
4
9
6
,

 
 
2
8
1
,

 
 
6
0
8
0
0
,

 
 
1
6
0
7
2
9
]
,

 
[
6
3
3
1
,
 
2
1
,
 
4
9
4
4
8
,
 
2
3
7
,
 
8
7
8
,
 
1
9
2
0
,
 
8
1
6
,
 
2
8
0
4
,
 
5
3
5
,
 
2
1
6
]
,

 
[
1
2
7
,

 
 
7
0
7
0
,

 
 
4
6
5
,

 
 
3
5
,

 
 
5
8
1
,

 
 
1
6
0
7
3
0
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
6
0
0
,

 
 
1
2
,

 
 
1
,

 
 
2
1
2
,

 
 
7
1
6
,

 
 
2
5
5
,

 
 
2
2
,

 
 
2
8
7
,

 
 
7
8
9
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
4
3
0
4
,

 
 
7
5
3
2
,

 
 
3
,

 
 
3
9
7
0
0
,

 
 
8
2
4
,

 
 
9
,

 
 
5
6
,

 
 
1
6
,

 
 
3
2
7
4
,

 
 
1
4
3
,

 
 
7
3
,

 
 
1
4
2
0
,

 
 
1
0
,

 
 
1
,

 
 
5
1
5
,

 
 
2
1
8
5
,

 
 
8
4
,

 
 
3
9
,

 
 
5
3
,

 
 
5
6
3
,

 
 
1
1
,

 
 
6
4
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
6
0
9
,

 
 
7
9
,

 
 
1
1
3
9
,

 
 
3
2
,

 
 
5
3
0
,

 
 
2
5
3
,

 
 
1
7
7
,

 
 
3
0
4
,

 
 
7
9
,

 
 
1
8
1
8
,

 
 
2
5
,

 
 
1
3
8
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
]
,

 
[
7
2
,
 
5
5
6
8
,
 
1
1
,
 
5
9
3
,
 
4
,
 
2
6
4
4
,
 
8
8
1
,
 
2
6
,
 
1
1
]
,

 
[
6
9
8
6
,
 
5
4
8
1
,
 
1
0
,
 
1
,
 
1
1
8
5
4
,
 
3
3
6
8
6
]
,

 
[
5
0
,

 
 
1
5
7
1
,

 
 
3
1
,

 
 
3
1
0
,

 
 
6
4
4
,

 
 
2
,

 
 
2
8
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
,

 
 
3
7
4
2
0
,

 
 
1
1
,

 
 
8
,

 
 
4
1
9
,

 
 
2
1
7
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
1
2
2
9
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
6
0
7
3
1
]
,

 
[
5
1
2
3
,

 
 
1
7
8
,

 
 
5
7
7
5
,

 
 
1
5
8
9
4
,

 
 
7
,

 
 
8
1
,

 
 
4
7
,

 
 
3
,

 
 
2
0
,

 
 
2
3
7
6
,

 
 
2
0
0
4
,

 
 
7
,

 
 
1
2
6
,

 
 
4
8
,

 
 
6
,

 
 
7
,

 
 
3
6
9
,

 
 
3
5
8
4
,

 
 
3
,

 
 
6
,

 
 
3
3
,

 
 
1
1
6
6
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
6
,

 
 
2
,

 
 
2
6
9
,

 
 
2
,

 
 
8
3
8
2
,

 
 
1
0
1
6
6
,

 
 
2
,

 
 
3
9
7
0
1
,

 
 
8
3
6
3
8
,

 
 
5
,

 
 
2
5
8
,

 
 
4
,

 
 
5
9
1
4
,

 
 
3
3
,

 
 
1
3
,

 
 
6
2
5
6
,

 
 
4
8
0
,

 
 
7
,

 
 
8
1
,

 
 
1
0
,

 
 
1
,

 
 
5
4
3
4
,

 
 
3
5
6
8
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
6
9
9
,

 
 
2
7
4
,

 
 
3
4
3
,

 
 
7
,

 
 
1
0
8
,

 
 
6
,

 
 
2
,

 
 
2
6
9
,

 
 
5
,

 
 
1
2
1
,

 
 
3
7
,

 
 
2
1
,

 
 
3
0
,

 
 
6
6
8
1
,

 
 
6
3
,

 
 
6
,

 
 
5
1
9
,

 
 
7
,

 
 
4
5
,

 
 
3
5
0
,

 
 
2
,

 
 
6
,

 
 
7
3
0
,

 
 
3
2
]
,

 
[
1
7
8
,

 
 
1
6
0
7
3
2
,

 
 
9
5
,

 
 
1
2
,

 
 
7
0
3
,

 
 
1
,

 
 
8
5
,

 
 
2
,

 
 
3
5
0
,

 
 
1
1
1
,

 
 
4
,

 
 
2
5
0
,

 
 
3
7
7
,

 
 
7
,

 
 
6
8
5
,

 
 
1
3
,

 
 
1
0
,

 
 
6
6
7
,

 
 
3
,

 
 
3
8
,

 
 
7
,

 
 
1
6
7
,

 
 
3
5
,

 
 
1
,

 
 
1
1
0
3
,

 
 
7
,

 
 
2
3
9
,

 
 
2
7
6
,

 
 
2
,

 
 
8
4
6
,

 
 
3
4
0
6
,

 
 
7
,

 
 
3
3
2
,

 
 
7
,

 
 
1
5
6
,

 
 
1
2
7
9
,

 
 
9
,

 
 
6
,

 
 
9
9
,

 
 
2
,

 
 
1
6
,

 
 
1
4
8
,

 
 
8
6
8
,

 
 
2
,

 
 
9
7
,

 
 
1
1
2
,

 
 
3
2
4
6
,

 
 
2
6
,

 
 
7
,

 
 
6
5
,

 
 
7
,

 
 
2
4
,

 
 
4
0
4
,

 
 
1
5
0
3
,

 
 
2
1
,

 
 
1
,

 
 
3
2
8
,

 
 
1
0
7
,

 
 
4
6
1
6
,

 
 
7
,

 
 
1
9
,

 
 
2
3
7
,

 
 
1
5
6
,

 
 
6
0
,

 
 
3
,

 
 
1
4
1
,

 
 
5
7
0
,

 
 
2
6
,

 
 
4
5
,

 
 
1
5
6
,

 
 
1
,

 
 
8
5
5
,

 
 
5
1
9
,

 
 
6
2
3
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
4
,

 
 
1
5
3
6
,

 
 
7
,

 
 
4
9
,

 
 
1
2
2
,

 
 
8
5
,

 
 
2
,

 
 
9
4
,

 
 
1
3
3
,

 
 
2
,

 
 
4
0
,

 
 
1
1
2
,

 
 
1
2
3
9
4
,

 
 
5
7
0
,

 
 
3
2
1
,

 
 
3
1
,

 
 
3
8
,

 
 
5
1
3
,

 
 
7
6
,

 
 
2
1
,

 
 
3
7
,

 
 
5
5
3
,

 
 
2
7
,

 
 
2
3
,

 
 
3
5
,

 
 
3
0
,

 
 
6
3
7
0
,

 
 
4
2
1
,

 
 
4
2
,

 
 
1
9
1
9
,

 
 
1
3
5
,

 
 
4
,

 
 
2
3
5
5
,

 
 
2
2
8
,

 
 
5
4
,

 
 
2
4
,

 
 
1
4
,

 
 
3
8
,

 
 
7
,

 
 
2
4
,

 
 
5
6
3
4
,

 
 
7
,

 
 
1
2
6
,

 
 
5
9
,

 
 
1
9
,

 
 
5
5
,

 
 
5
8
,

 
 
8
5
,

 
 
2
,

 
 
1
3
5
3
,

 
 
5
,

 
 
8
6
6
,

 
 
2
1
,

 
 
1
,

 
 
1
6
0
7
3
3
,

 
 
1
4
4
,

 
 
1
0
4
,

 
 
3
8
1
,

 
 
5
1
,

 
 
4
9
,

 
 
1
0
8
,

 
 
1
1
,

 
 
1
4
6
,

 
 
1
1
7
0
,

 
 
3
8
,

 
 
7
,

 
 
1
9
,

 
 
1
6
7
,

 
 
1
2
,

 
 
3
1
1
,

 
 
4
7
,

 
 
1
0
7
,

 
 
4
9
,

 
 
5
4
1
,

 
 
4
1
,

 
 
8
,

 
 
1
8
3
,

 
 
3
4
1
,

 
 
3
1
6
,

 
 
2
7
6
8
9
,

 
 
1
4
7
0
,

 
 
1
3
,

 
 
8
,

 
 
2
7
6
8
9
,

 
 
2
4
3
,

 
 
1
3
,

 
 
8
,

 
 
3
0
6
8
,

 
 
7
8
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
2
4
6
,

 
 
2
6
1
8
,

 
 
1
5
,

 
 
1
,

 
 
4
5
8
2
,

 
 
3
5
6
,

 
 
2
9
,

 
 
1
0
,

 
 
6
6
7
,

 
 
3
,

 
 
1
,

 
 
8
5
5
,

 
 
7
,

 
 
2
6
3
,

 
 
2
,

 
 
3
4
,

 
 
8
8
,

 
 
3
,

 
 
4
4
3
,

 
 
7
,

 
 
3
9
,

 
 
7
7
,

 
 
3
8
9
0
,

 
 
4
0
8
,

 
 
7
,

 
 
8
1
,

 
 
2
2
6
3
,

 
 
3
9
,

 
 
6
,

 
 
3
8
9
0
,

 
 
1
2
,

 
 
3
7
,

 
 
1
5
,

 
 
4
,

 
 
6
5
4
,

 
 
1
9
3
,

 
 
7
,

 
 
8
1
,

 
 
2
0
3
,

 
 
1
0
2
1
,

 
 
5
,

 
 
8
4
1
,

 
 
2
0
6
2
,

 
 
3
5
,

 
 
1
,

 
 
1
9
4
,

 
 
2
2
3
,

 
 
2
3
8
]
,

 
[
1
9
6
,

 
 
3
2
0
,

 
 
1
6
0
7
3
4
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
4
1
4
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
4
8
,

 
 
1
,

 
 
2
0
2
,

 
 
5
,

 
 
7
6
4
,

 
 
2
,

 
 
6
0
6
,

 
 
6
4
,

 
 
1
8
,

 
 
6
0
,

 
 
1
2
4
,

 
 
9
,

 
 
6
,

 
 
1
8
4
,

 
 
1
3
6
,

 
 
8
4
5
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
1
0
5
5
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
5
,

 
 
7
4
,

 
 
2
,

 
 
2
0
9
1
,

 
 
8
3
,

 
 
7
4
,

 
 
2
,

 
 
4
7
1
,

 
 
2
0
,

 
 
1
1
4
,

 
 
2
3
,

 
 
2
0
9
,

 
 
1
,

 
 
2
3
,

 
 
2
5
1
2
,

 
 
2
2
,

 
 
6
,

 
 
5
4
8
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
8
2
7
,

 
 
1
2
9
,

 
 
6
4
,

 
 
5
,

 
 
9
1
,

 
 
4
,

 
 
9
2
2
,

 
 
5
0
,

 
 
5
1
7
,

 
 
2
0
,

 
 
9
8
9
,

 
 
1
5
,

 
 
1
3
8
,

 
 
1
2
4
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
3
4
1
,

 
 
2
0
,

 
 
7
1
2
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
3
2
8
,

 
 
7
6
,

 
 
2
8
,

 
 
2
5
4
,

 
 
2
1
9
,

 
 
3
7
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
5
,

 
 
2
1
9
,

 
 
2
0
,

 
 
2
1
4
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
5
,

 
 
8
4
,

 
 
2
0
2
,

 
 
1
2
1
,

 
 
3
7
,

 
 
1
5
0
,

 
 
1
,

 
 
2
1
4
,

 
 
1
2
7
,

 
 
1
9
6
,

 
 
6
3
1
,

 
 
3
5
3
9
3
]
,

 
[
7
,

 
 
1
8
7
,

 
 
1
,

 
 
1
7
4
,

 
 
1
5
1
,

 
 
1
1
,

 
 
2
4
,

 
 
9
1
7
,

 
 
1
7
,

 
 
4
9
2
9
,

 
 
3
2
,

 
 
1
9
4
2
4
,

 
 
2
2
,

 
 
3
0
6
,

 
 
2
2
3
1
,

 
 
4
6
7
,

 
 
1
6
6
,

 
 
1
2
2
,

 
 
4
,

 
 
7
2
5
,

 
 
6
9
,

 
 
6
0
,

 
 
2
9
2
,

 
 
4
7
4
,

 
 
1
0
6
5
9
7
,

 
 
1
0
7
7
,

 
 
2
,

 
 
2
9
4
4
,

 
 
1
2
,

 
 
2
2
6
3
6
,

 
 
8
4
,

 
 
1
1
,

 
 
5
5
7
,

 
 
5
3
,

 
 
1
9
,

 
 
4
,

 
 
2
4
9
,

 
 
7
,

 
 
1
0
2
,

 
 
1
2
8
,

 
 
1
5
8
0
,

 
 
6
9
8
3
6
,

 
 
4
4
0
0
,

 
 
6
4
,

 
 
2
6
,

 
 
2
1
5
0
,

 
 
7
,

 
 
8
1
,

 
 
1
5
5
,

 
 
2
3
9
0
,

 
 
3
,

 
 
1
7
2
,

 
 
2
,

 
 
1
6
,

 
 
2
9
0
5
,

 
 
2
,

 
 
5
4
0
0
,

 
 
8
8
,

 
 
3
7
5
,

 
 
4
7
,

 
 
3
,

 
 
1
7
2
,

 
 
1
6
0
7
3
5
,

 
 
1
8
3
8
1
,

 
 
5
8
,

 
 
5
5
4
,

 
 
1
0
,

 
 
1
7
2
,

 
 
9
3
,

 
 
7
,

 
 
4
3
,

 
 
4
6
6
,

 
 
2
,

 
 
8
2
2
,

 
 
2
1
,

 
 
1
3
]
,

 
[
8
,
 
4
7
1
1
,
 
1
2
6
2
6
,
 
1
9
4
,
 
2
5
,
 
1
4
]
,

 
[
9
,

 
 
7
5
6
,

 
 
1
6
,

 
 
1
8
2
1
,

 
 
6
,

 
 
1
2
2
,

 
 
3
8
5
9
,

 
 
1
4
5
7
,

 
 
2
,

 
 
8
2
,

 
 
2
5
3
,

 
 
1
5
0
0
,

 
 
3
2
,

 
 
1
5
8
,

 
 
3
3
1
,

 
 
1
8
2
,

 
 
4
,

 
 
6
2
5
7
,

 
 
2
1
6
3
,

 
 
1
2
,

 
 
2
8
,

 
 
5
0
,

 
 
1
5
6
,

 
 
1
,

 
 
1
1
9
0
,

 
 
2
,

 
 
1
1
8
9
,

 
 
5
,

 
 
4
9
4
4
9
,

 
 
1
4
5
7
,

 
 
2
,

 
 
8
2
,

 
 
1
5
0
0
,

 
 
7
5
2
,

 
 
1
5
,

 
 
2
8
,

 
 
1
9
3
,

 
 
9
,

 
 
1
0
,

 
 
8
1
3
,

 
 
2
,

 
 
2
7
2
,

 
 
2
9
3
9
,

 
 
1
,

 
 
2
3
,

 
 
2
4
5
,

 
 
1
5
3
,

 
 
3
8
4
3
,

 
 
2
1
,

 
 
5
0
3
,

 
 
4
2
7
,

 
 
1
4
4
1
,

 
 
1
0
3
6
1
,

 
 
5
,

 
 
8
0
5
,

 
 
3
5
4
9
,

 
 
3
,

 
 
5
6
2
,

 
 
7
6
3
4
,

 
 
4
6
]
,

 
[
1
,
 
1
1
6
,
 
8
,
 
6
1
1
,
 
4
8
7
,
 
5
,
 
5
6
,
 
6
0
6
,
 
6
,
 
1
8
,
 
3
8
3
,
 
2
4
7
]
,

 
[
2
0
6
,

 
 
3
6
,

 
 
8
9
,

 
 
5
3
,

 
 
1
8
,

 
 
2
6
7
6
,

 
 
2
1
,

 
 
4
,

 
 
7
6
6
,

 
 
3
,

 
 
2
2
7
5
,

 
 
2
1
5
4
,

 
 
2
2
4
,

 
 
1
4
4
,

 
 
6
,

 
 
3
2
7
5
,

 
 
9
,

 
 
1
,

 
 
4
6
0
,

 
 
2
4
,

 
 
4
,

 
 
1
0
9
0
,

 
 
5
,

 
 
1
4
,

 
 
7
9
6
9
,

 
 
4
5
,

 
 
6
,

 
 
5
0
,

 
 
3
9
8
,

 
 
1
1
,

 
 
2
2
,

 
 
2
5
9
,

 
 
1
0
7
7
,

 
 
2
,

 
 
6
7
6
,

 
 
9
,

 
 
1
,

 
 
4
4
9
9
,

 
 
8
,

 
 
1
,

 
 
9
1
3
,

 
 
4
4
7
,

 
 
5
1
,

 
 
3
9
,

 
 
3
4
,

 
 
3
6
,

 
 
1
8
2
,

 
 
4
,

 
 
8
2
3
,

 
 
1
3
3
3
,

 
 
4
6
0
,

 
 
1
3
8
,

 
 
1
7
,

 
 
5
1
,

 
 
5
6
,

 
 
1
9
,

 
 
2
0
7
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
3
1
5
,

 
 
2
5
,

 
 
5
5
9
,

 
 
2
,

 
 
3
4
,

 
 
1
3
,

 
 
6
2
3
,

 
 
2
3
1
,

 
 
2
1
9
,

 
 
4
,

 
 
1
8
3
,

 
 
7
5
3
,

 
 
2
,

 
 
3
4
,

 
 
1
1
]
,

 
[
1
1
,

 
 
3
2
3
,

 
 
2
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
7
3
2
,

 
 
3
,

 
 
4
1
2
6
,

 
 
1
7
,

 
 
1
0
1
,

 
 
2
3
1
,

 
 
2
8
9
,

 
 
5
,

 
 
4
3
2
6
,

 
 
7
3
,

 
 
6
0
,

 
 
1
0
6
,

 
 
1
0
7
,

 
 
4
6
,

 
 
3
7
9
,

 
 
3
7
]
,

 
[
3
9
1
4
,

 
 
3
8
7
9
,

 
 
7
,

 
 
6
8
5
,

 
 
6
,

 
 
7
0
3
,

 
 
1
,

 
 
8
5
,

 
 
2
,

 
 
5
6
3
,

 
 
1
3
,

 
 
2
6
7
,

 
 
6
7
4
9
,

 
 
5
,

 
 
1
2
,

 
 
2
0
,

 
 
7
7
0
8
,

 
 
2
,

 
 
8
6
6
,

 
 
1
1
,

 
 
3
3
,

 
 
1
8
0
8
,

 
 
6
4
,

 
 
1
1
7
0
,

 
 
1
,

 
 
1
0
8
3
,

 
 
3
3
5
,

 
 
6
4
,

 
 
9
1
,

 
 
1
0
,

 
 
2
0
,

 
 
3
3
2
5
,

 
 
2
9
6
,

 
 
7
,

 
 
5
5
1
,

 
 
2
6
3
,

 
 
2
1
,

 
 
2
0
,

 
 
1
0
1
2
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
1
0
2
,

 
 
3
9
3
,

 
 
2
,

 
 
1
2
2
6
,

 
 
1
,

 
 
1
6
0
7
3
6
,

 
 
9
,

 
 
4
,

 
 
4
1
6
3
,

 
 
8
,

 
 
6
9
3
,

 
 
1
0
,

 
 
4
1
,

 
 
8
,

 
 
3
8
3
,

 
 
4
,

 
 
2
3
5
5
,

 
 
1
6
0
7
3
7
,

 
 
3
2
9
,

 
 
1
1
7
,

 
 
3
5
5
,

 
 
6
9
4
1
,

 
 
1
0
,

 
 
1
,

 
 
1
0
2
1
,

 
 
2
5
,

 
 
1
2
9
7
,

 
 
1
0
7
2
1
,

 
 
2
5
,

 
 
3
2
9
,

 
 
1
,

 
 
1
1
6
3
,

 
 
5
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
1
0
7
2
1
,

 
 
1
4
4
,

 
 
1
,

 
 
9
2
4
,

 
 
5
,

 
 
1
5
0
9
7
,

 
 
1
9
5
1
,

 
 
1
8
,

 
 
1
0
2
,

 
 
2
7
1
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
,

 
 
1
8
9
0
,

 
 
4
6
4
8
,

 
 
3
,

 
 
1
,

 
 
6
7
7
9
,

 
 
1
2
7
0
,

 
 
9
,

 
 
1
9
7
,

 
 
1
1
,

 
 
1
9
9
8
,

 
 
3
0
,

 
 
4
1
6
3
,

 
 
3
3
5
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
4
2
3
,

 
 
9
3
0
,

 
 
3
2
9
,

 
 
4
,

 
 
6
4
9
,

 
 
4
1
6
3
,

 
 
3
5
5
,

 
 
2
7
,

 
 
1
5
8
7
,

 
 
1
0
,

 
 
1
1
7
,

 
 
3
3
2
6
,

 
 
2
5
,

 
 
4
2
3
7
2
,

 
 
9
6
,

 
 
2
3
8
,

 
 
5
1
,

 
 
1
8
,

 
 
2
1
0
,

 
 
1
0
,

 
 
1
,

 
 
1
3
9
,

 
 
7
4
2
0
,

 
 
7
,

 
 
6
8
5
,

 
 
9
,

 
 
1
,

 
 
9
4
0
,

 
 
1
0
,

 
 
1
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
8
,

 
 
2
2
0
8
,

 
 
5
8
,

 
 
2
0
9
4
,

 
 
1
4
4
,

 
 
6
,

 
 
1
9
,

 
 
2
1
0
,

 
 
2
0
7
2
,

 
 
5
,

 
 
2
9
7
,

 
 
1
0
7
2
1
,

 
 
9
6
,

 
 
5
5
6
,

 
 
4
3
3
,

 
 
2
9
7
,

 
 
4
1
,

 
 
4
5
,

 
 
1
6
,

 
 
4
2
3
,

 
 
2
2
0
6
,

 
 
3
2
9
,

 
 
1
,

 
 
9
2
4
,

 
 
6
7
7
9
,

 
 
1
0
,

 
 
2
7
1
,

 
 
2
1
3
4
,

 
 
2
3
8
,

 
 
2
,

 
 
2
5
8
,

 
 
2
7
,

 
 
3
1
1
,

 
 
1
,

 
 
2
2
5
9
,

 
 
8
0
3
9
,

 
 
2
4
2
5
,

 
 
4
5
,

 
 
1
6
,

 
 
1
4
,

 
 
4
9
,

 
 
4
,

 
 
3
4
8
,

 
 
2
7
8
2
,

 
 
2
1
0
6
,

 
 
9
3
,

 
 
1
,

 
 
3
3
2
9
,

 
 
4
6
1
1
,

 
 
2
4
2
5
,

 
 
2
6
,

 
 
1
1
,

 
 
4
5
,

 
 
6
6
,

 
 
1
9
,

 
 
4
,

 
 
3
7
1
,

 
 
2
7
1
,

 
 
2
5
7
7
,

 
 
1
5
,

 
 
1
,

 
 
4
4
2
,

 
 
4
,

 
 
3
4
8
,

 
 
5
8
,

 
 
6
3
3
2
,

 
 
1
3
2
1
5
,

 
 
5
,

 
 
3
0
9
2
,

 
 
1
5
,

 
 
5
6
4
,

 
 
4
3
9
3
,

 
 
2
,

 
 
2
5
8
,

 
 
1
8
3
,

 
 
3
1
1
,

 
 
1
0
,

 
 
1
,

 
 
6
8
3
,

 
 
4
,

 
 
6
4
9
,

 
 
4
1
6
3
,

 
 
1
0
3
,

 
 
1
9
9
,

 
 
1
6
,

 
 
2
9
3
7
,

 
 
1
7
,

 
 
9
1
,

 
 
1
6
4
1
,

 
 
2
7
9
,

 
 
1
1
0
6
0
,

 
 
2
2
,

 
 
1
1
,

 
 
2
3
9
,

 
 
1
9
,

 
 
2
7
,

 
 
1
5
8
7
,

 
 
1
0
,

 
 
1
6
5
9
,

 
 
9
6
,

 
 
2
2
,

 
 
1
1
,

 
 
9
9
,

 
 
6
9
4
1
,

 
 
1
0
,

 
 
3
0
6
,

 
 
6
1
,

 
 
4
2
3
,

 
 
6
2
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
1
0
2
,

 
 
2
7
9
,

 
 
1
1
0
6
0
,

 
 
6
8
3
,

 
 
9
9
9
5
,

 
 
2
7
6
9
0
,

 
 
1
9
8
2
2
,

 
 
8
,

 
 
1
4
,

 
 
3
5
1
,

 
 
2
9
3
7
,

 
 
1
7
,

 
 
4
7
,

 
 
3
,

 
 
8
8
,

 
 
1
1
7
0
,

 
 
1
0
4
,

 
 
9
6
2
,

 
 
1
9
,

 
 
4
9
,

 
 
4
7
,

 
 
6
8
3
,

 
 
1
5
8
7
,

 
 
1
0
,

 
 
1
6
5
9
,

 
 
5
0
0
,

 
 
5
1
,

 
 
1
9
,

 
 
6
1
,

 
 
6
9
4
1
,

 
 
8
5
1
4
,

 
 
3
5
8
,

 
 
9
,

 
 
2
7
6
9
0
,

 
 
4
2
,

 
 
4
2
,

 
 
2
6
9
7
,

 
 
6
9
4
1
,

 
 
1
0
8
0
,

 
 
1
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
3
6
0
7
,

 
 
8
8
3
,

 
 
2
0
6
9
,

 
 
1
1
8
4
4
,

 
 
8
8
8
2
,

 
 
1
2
0
1
,

 
 
4
3
,

 
 
1
0
,

 
 
3
0
,

 
 
3
3
5
,

 
 
1
5
3
,

 
 
2
7
6
,

 
 
4
,

 
 
2
7
4
3
,

 
 
3
,

 
 
2
8
1
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
1
0
6
8
,

 
 
5
3
,

 
 
1
0
3
,

 
 
1
7
9
4
,

 
 
1
5
7
,

 
 
1
5
,

 
 
2
0
9
,

 
 
3
6
5
1
,

 
 
4
8
,

 
 
1
0
,

 
 
6
6
4
,

 
 
2
7
7
9
,

 
 
1
3
7
5
1
,

 
 
2
5
,

 
 
1
0
,

 
 
6
6
4
,

 
 
1
8
9
0
,

 
 
1
3
7
5
1
,

 
 
2
5
,

 
 
1
0
,

 
 
4
,

 
 
4
6
7
1
,

 
 
3
,

 
 
6
6
4
,

 
 
2
7
7
9
,

 
 
1
3
7
5
1
,

 
 
5
,

 
 
6
6
4
,

 
 
1
8
9
0
,

 
 
1
3
7
5
1
,

 
 
2
6
,

 
 
8
4
,

 
 
5
3
,

 
 
1
8
,

 
 
4
4
8
5
,

 
 
3
8
,

 
 
8
,

 
 
1
0
,

 
 
3
0
,

 
 
3
3
5
,

 
 
2
7
,

 
 
1
0
6
5
9
8
,

 
 
3
5
2
5
,

 
 
3
,

 
 
2
4
4
6
7
,

 
 
6
0
8
0
1
,

 
 
5
,

 
 
9
6
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
7
,

 
 
3
4
,

 
 
8
8
9
,

 
 
9
,

 
 
2
7
6
9
0
,

 
 
2
1
,

 
 
2
6
9
7
,

 
 
6
9
4
1
,

 
 
8
,

 
 
1
4
3
,

 
 
1
5
,

 
 
1
,

 
 
6
6
4
8
,

 
 
3
,

 
 
3
5
5
,

 
 
1
5
5
,

 
 
1
3
0
,

 
 
6
9
4
1
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
4
2
7
2
,

 
 
2
,

 
 
1
6
1
,

 
 
4
0
,

 
 
3
,

 
 
8
8
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
9
7
,

 
 
7
,

 
 
3
4
,

 
 
6
6
,

 
 
2
1
1
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
2
7
,

 
 
3
9
3
,

 
 
4
3
6
,

 
 
1
4
5
,

 
 
3
,

 
 
5
1
2
4
,

 
 
9
,

 
 
1
0
5
,

 
 
3
5
,

 
 
1
,

 
 
1
5
8
7
,

 
 
4
3
0
6
,

 
 
3
,

 
 
4
,

 
 
6
4
9
,

 
 
4
1
6
3
,

 
 
8
,

 
 
1
0
2
,

 
 
2
8
1
2
,

 
 
1
0
5
,

 
 
2
,

 
 
4
2
2
1
,

 
 
1
,

 
 
1
0
6
8
,

 
 
3
,

 
 
2
7
,

 
 
2
3
,

 
 
1
0
,

 
 
1
1
1
6
,

 
 
1
,

 
 
2
5
7
,

 
 
3
,

 
 
1
1
,

 
 
5
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
7
,

 
 
1
2
8
,

 
 
1
7
,

 
 
4
4
1
]
,

 
[
4
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
9
,

 
 
3
3
,

 
 
4
0
,

 
 
2
2
,

 
 
6
,

 
 
5
9
,

 
 
6
5
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
1
5
8
,

 
 
3
7
4
2
1
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
4
,

 
 
1
5
6
8
2
,

 
 
8
4
,

 
 
1
1
,

 
 
4
9
,

 
 
3
2
4
2
,

 
 
3
0
,

 
 
1
4
5
,

 
 
1
7
,

 
 
2
,

 
 
7
4
,

 
 
3
1
3
,

 
 
1
3
,

 
 
3
4
1
,

 
 
8
,

 
 
2
,

 
 
9
1
,

 
 
2
7
,

 
 
7
4
3
,

 
 
3
8
4
,

 
 
7
1
,

 
 
4
,

 
 
1
5
4
8
,

 
 
1
4
,

 
 
2
7
,

 
 
3
8
4
,

 
 
4
2
3
,

 
 
9
3
0
,

 
 
5
,

 
 
1
8
5
,

 
 
1
4
,

 
 
9
6
,

 
 
3
8
,

 
 
1
3
3
3
7
,

 
 
3
7
,

 
 
1
9
2
,

 
 
1
,

 
 
1
3
2
,

 
 
3
5
,

 
 
3
0
,

 
 
2
9
,

 
 
1
3
4
,

 
 
5
3
7
,

 
 
7
2
,

 
 
5
2
8
,

 
 
2
1
,

 
 
4
4
,

 
 
9
5
1
4
,

 
 
9
5
1
5
,

 
 
3
7
,

 
 
7
6
,

 
 
2
5
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
1
8
3
,

 
 
6
2
0
3
,

 
 
9
2
0
3
,

 
 
3
6
7
,

 
 
1
6
,

 
 
1
5
2
7
7
,

 
 
7
6
,

 
 
2
,

 
 
4
8
1
5
,

 
 
2
1
3
9
,

 
 
3
9
7
9
,

 
 
1
3
,

 
 
3
4
1
,

 
 
7
2
,

 
 
2
0
7
,

 
 
9
5
1
5
,

 
 
3
5
,

 
 
1
,

 
 
1
5
6
8
2
,

 
 
2
2
8
,

 
 
3
0
,

 
 
4
4
2
,

 
 
2
9
,

 
 
4
2
,

 
 
1
7
2
0
,

 
 
3
1
,

 
 
1
,

 
 
1
0
2
,

 
 
1
1
4
,

 
 
4
8
8
,

 
 
3
2
2
,

 
 
2
,

 
 
1
,

 
 
1
0
2
,

 
 
2
6
2
,

 
 
4
8
8
,

 
 
5
,

 
 
9
,

 
 
8
,

 
 
4
4
,

 
 
1
2
7
5
,

 
 
1
1
4
,

 
 
4
8
8
,

 
 
5
,

 
 
1
,

 
 
2
6
2
,

 
 
4
8
8
,

 
 
1
8
,

 
 
2
4
7
]
,

 
[
1
6
0
7
3
8
,

 
 
2
2
6
3
7
,

 
 
7
,

 
 
6
5
1
,

 
 
1
,

 
 
3
1
4
1
,

 
 
1
3
,

 
 
2
3
9
4
,

 
 
8
0
,

 
 
5
5
3
6
,

 
 
3
0
,

 
 
2
5
6
3
,

 
 
5
3
,

 
 
8
6
,

 
 
4
4
9
7
,

 
 
2
7
,

 
 
2
0
8
3
,

 
 
1
6
2
,

 
 
1
2
,

 
 
1
,

 
 
5
4
9
9
,

 
 
9
2
,

 
 
4
2
1
,

 
 
8
7
,

 
 
1
4
,

 
 
1
6
,

 
 
1
5
2
6
,

 
 
2
6
,

 
 
9
,

 
 
8
,

 
 
1
,

 
 
4
2
4
,

 
 
1
4
3
7
1
]
,

 
[
1
5
0
9
8
,
 
4
6
,
 
2
9
,
 
7
8
,
 
9
0
,
 
6
,
 
2
5
6
,
 
9
,
 
5
2
2
5
,
 
7
9
,
 
2
,
 
1
,
 
4
6
,
 
2
9
,
 
1
1
,
 
5
9
3
,
 
1
1
2
7
]
,

 
[
2
9
3
,

 
 
1
1
9
,

 
 
3
,

 
 
3
6
2
5
,

 
 
8
3
6
3
9
,

 
 
4
,

 
 
2
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
8
,

 
 
1
5
,

 
 
3
6
2
5
,

 
 
8
3
6
3
9
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
7
,

 
 
1
8
2
,

 
 
1
1
6
,

 
 
3
3
0
6
,

 
 
3
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
3
5
,

 
 
4
,

 
 
2
2
2
,

 
 
2
5
,

 
 
4
3
8
,

 
 
3
,

 
 
7
5
,

 
 
2
6
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
9
2
0
,

 
 
7
4
,

 
 
2
5
,

 
 
7
8
,

 
 
1
,

 
 
2
5
7
,

 
 
8
,

 
 
3
4
2
,

 
 
9
,

 
 
8
,

 
 
7
8
,

 
 
2
7
,

 
 
2
3
,

 
 
3
5
,

 
 
9
,

 
 
2
5
7
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
2
7
,

 
 
3
8
4
,

 
 
1
8
2
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
8
3
,

 
 
9
,

 
 
3
4
,

 
 
1
4
,

 
 
9
2
0
,

 
 
1
,

 
 
1
9
0
7
,

 
 
1
1
1
9
,

 
 
2
5
,

 
 
1
8
6
9
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
3
3
,

 
 
5
5
,

 
 
8
5
,

 
 
5
0
,

 
 
6
3
,

 
 
1
,

 
 
4
2
7
,

 
 
1
2
,

 
 
3
8
,

 
 
8
,

 
 
7
0
1
,

 
 
9
0
4
,

 
 
1
7
,

 
 
3
4
2
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
7
5
,

 
 
2
5
7
,

 
 
4
9
4
,

 
 
5
0
3
,

 
 
1
2
1
8
,

 
 
1
2
,

 
 
1
3
9
5
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
1
3
,

 
 
4
5
4
,

 
 
2
4
,

 
 
6
6
8
,

 
 
6
4
,

 
 
1
0
,

 
 
1
0
0
9
,

 
 
6
,

 
 
8
7
,

 
 
1
1
5
9
,

 
 
1
,

 
 
1
1
9
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
4
9
,

 
 
5
6
7
,

 
 
1
,

 
 
9
8
6
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
5
,

 
 
1
7
7
6
,

 
 
2
7
7
,

 
 
2
5
5
7
,

 
 
2
1
,

 
 
3
1
0
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
2
6
,

 
 
1
6
,

 
 
7
4
9
,

 
 
9
,

 
 
4
0
8
,

 
 
9
1
7
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
1
3
5
9
,

 
 
1
,

 
 
1
7
7
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
1
7
7
,

 
 
2
1
9
0
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
7
7
,

 
 
2
2
5
,

 
 
2
6
,

 
 
5
9
,

 
 
1
5
2
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
4
3
,

 
 
4
3
,

 
 
2
8
9
4
,

 
 
1
1
,

 
 
5
8
,

 
 
1
0
,

 
 
3
4
0
7
,

 
 
2
1
,

 
 
5
0
8
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
]
,

 
[
1
2
3
,

 
 
1
2
3
,

 
 
1
1
9
,

 
 
5
8
7
,

 
 
1
2
3
,

 
 
2
8
6
5
4
,

 
 
2
7
3
6
,

 
 
5
9
1
5
,

 
 
3
3
8
,

 
 
2
5
5
8
,

 
 
2
7
9
,

 
 
2
6
7
8
,

 
 
4
7
2
,

 
 
4
2
,

 
 
5
7
,

 
 
4
4
0
,

 
 
3
3
,

 
 
2
8
,

 
 
3
4
4
,

 
 
5
,

 
 
3
9
0
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
2
,

 
 
6
,

 
 
2
1
1
,

 
 
9
,

 
 
1
3
,

 
 
1
2
3
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
4
6
,

 
 
5
0
,

 
 
1
1
8
,

 
 
4
1
,

 
 
2
,

 
 
1
8
6
4
,

 
 
2
0
,

 
 
3
2
7
,

 
 
8
1
6
,

 
 
1
5
8
2
,

 
 
9
8
1
,

 
 
1
5
8
2
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
1
,
 
3
2
5
,
 
2
4
2
,
 
6
1
9
,
 
1
8
,
 
1
,
 
2
1
2
2
,
 
3
7
7
2
,
 
3
,
 
3
0
,
 
1
4
0
,
 
3
2
,
 
5
4
5
,
 
3
3
1
]
,

 
[
4
9
9
0
,

 
 
7
,

 
 
2
3
9
,

 
 
1
5
6
,

 
 
1
,

 
 
1
1
9
0
,

 
 
2
,

 
 
6
5
2
4
,

 
 
2
3
9
,

 
 
1
9
,

 
 
8
5
,

 
 
1
,

 
 
1
0
7
,

 
 
1
0
,

 
 
2
1
4
,

 
 
8
,

 
 
2
9
0
9
,

 
 
1
0
,

 
 
2
0
7
0
,

 
 
1
3
7
,

 
 
5
7
,

 
 
2
9
8
,

 
 
1
3
,

 
 
2
5
0
,

 
 
3
0
5
,

 
 
2
,

 
 
7
0
,

 
 
5
,

 
 
7
,

 
 
3
9
,

 
 
9
8
4
,

 
 
1
1
,

 
 
5
2
,

 
 
1
8
9
,

 
 
1
2
9
2
,

 
 
6
6
8
,

 
 
4
,

 
 
3
1
5
7
,

 
 
4
5
4
,

 
 
3
,

 
 
1
0
8
9
,

 
 
3
7
,

 
 
4
1
5
5
,

 
 
1
5
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
3
6
8
,

 
 
1
,

 
 
2
3
,

 
 
2
0
8
,

 
 
7
,

 
 
2
4
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
7
7
,

 
 
3
,

 
 
1
2
9
,

 
 
1
1
,

 
 
3
0
,

 
 
4
3
7
,

 
 
1
6
6
2
,

 
 
1
2
4
5
,

 
 
9
6
,

 
 
5
4
0
1
,

 
 
4
2
2
,

 
 
8
4
,

 
 
4
8
5
,

 
 
6
8
,

 
 
1
7
2
,

 
 
4
8
9
,

 
 
1
7
,

 
 
2
,

 
 
3
0
,

 
 
3
2
5
,

 
 
1
8
0
,

 
 
5
6
4
9
,

 
 
1
4
4
,

 
 
1
,

 
 
1
0
7
2
2
,

 
 
1
2
,

 
 
4
6
1
7
,

 
 
1
,

 
 
2
2
1
1
0
,

 
 
3
0
3
,

 
 
8
4
2
,

 
 
1
7
,

 
 
5
4
2
9
,

 
 
1
5
,

 
 
1
0
2
2
,

 
 
4
0
6
,

 
 
2
4
,

 
 
1
5
,

 
 
1
5
4
,

 
 
1
7
2
,

 
 
1
4
,

 
 
3
7
,

 
 
5
,

 
 
1
,

 
 
2
2
8
4
,

 
 
7
2
9
2
,

 
 
1
2
,

 
 
1
9
1
8
,

 
 
3
7
4
2
2
,

 
 
9
9
,

 
 
5
3
3
8
,

 
 
2
5
0
,

 
 
6
3
3
,

 
 
1
0
7
8
,

 
 
3
0
,

 
 
3
2
5
,

 
 
5
6
4
9
,

 
 
2
4
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
4
1
5
,

 
 
2
6
4
6
,

 
 
5
,

 
 
1
8
4
4
,

 
 
2
,

 
 
3
9
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
9
,

 
 
1
0
0
,

 
 
2
5
,

 
 
1
5
2
,

 
 
7
4
7
4
,

 
 
1
8
6
,

 
 
1
1
,

 
 
3
9
,

 
 
2
6
,

 
 
2
2
,

 
 
1
,

 
 
1
0
7
,

 
 
1
0
,

 
 
2
1
4
,

 
 
2
4
,

 
 
1
2
6
,

 
 
1
3
1
4
,

 
 
3
5
,

 
 
9
,

 
 
3
5
,

 
 
1
,

 
 
9
1
8
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
3
5
,

 
 
1
0
8
9
2
,

 
 
8
7
7
,

 
 
7
8
,

 
 
2
3
9
,

 
 
5
2
,

 
 
1
8
9
,

 
 
9
6
,

 
 
4
5
4
,

 
 
1
4
9
,

 
 
2
1
8
5
,

 
 
2
3
7
,

 
 
4
1
,

 
 
1
7
1
7
1
,

 
 
3
5
,

 
 
1
6
2
,

 
 
2
3
3
,

 
 
3
,

 
 
1
,

 
 
7
2
7
,

 
 
2
3
,

 
 
3
3
6
3
,

 
 
2
1
,

 
 
6
0
2
7
,

 
 
8
3
6
4
0
,

 
 
2
7
,

 
 
3
1
3
6
,

 
 
3
3
7
,

 
 
5
,

 
 
2
7
,

 
 
3
1
3
6
,

 
 
2
9
6
7
,

 
 
6
8
5
1
,

 
 
3
7
5
2
,

 
 
1
0
9
,

 
 
2
3
1
,

 
 
3
7
3
,

 
 
6
,

 
 
7
8
,

 
 
1
,

 
 
1
0
7
,

 
 
5
9
3
,

 
 
2
9
0
9
,

 
 
1
0
,

 
 
9
8
,

 
 
5
8
8
,

 
 
1
8
0
7
2
,

 
 
1
2
9
,

 
 
5
,

 
 
1
,

 
 
1
5
3
3
,

 
 
1
5
7
,

 
 
5
,

 
 
2
5
7
5
,

 
 
9
,

 
 
2
8
9
7
,

 
 
2
,

 
 
2
0
1
,

 
 
8
3
,

 
 
5
2
,

 
 
1
8
9
,

 
 
2
4
,

 
 
6
2
6
,

 
 
1
0
,

 
 
1
0
8
9
,

 
 
1
5
5
1
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
7
8
,

 
 
2
4
,

 
 
1
1
,

 
 
2
4
2
,

 
 
2
4
8
,

 
 
3
7
,

 
 
2
5
,

 
 
2
4
,

 
 
1
1
,

 
 
2
,

 
 
6
2
3
0
,

 
 
1
,

 
 
9
8
6
,

 
 
1
7
4
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
4
7
3
,

 
 
1
,

 
 
6
7
9
,

 
 
5
3
8
,

 
 
5
,

 
 
1
0
8
9
2
,

 
 
3
4
6
,

 
 
1
4
,

 
 
9
6
,

 
 
1
3
1
4
,

 
 
2
1
,

 
 
8
7
4
0
,

 
 
2
5
7
,

 
 
3
3
,

 
 
7
4
1
,

 
 
7
,

 
 
3
9
,

 
 
7
7
,

 
 
9
9
3
4
,

 
 
2
6
,

 
 
3
6
7
,

 
 
6
5
0
,

 
 
7
1
,

 
 
6
0
,

 
 
7
0
8
,

 
 
3
,

 
 
6
6
2
,

 
 
3
2
6
8
,

 
 
5
,

 
 
1
8
0
,

 
 
4
1
2
7
,

 
 
7
,

 
 
5
9
,

 
 
1
2
6
,

 
 
1
9
,

 
 
8
5
,

 
 
1
2
,

 
 
1
3
,

 
 
7
,

 
 
1
9
,

 
 
1
3
1
,

 
 
4
,

 
 
3
0
2
,

 
 
3
7
2
,

 
 
3
,

 
 
1
0
2
,

 
 
9
8
,

 
 
1
4
0
,

 
 
1
4
8
,

 
 
1
,

 
 
2
7
4
,

 
 
5
,

 
 
1
9
,

 
 
8
2
8
,

 
 
1
7
7
6
5
,

 
 
3
1
,

 
 
3
5
8
,

 
 
2
1
5
,

 
 
9
,

 
 
2
8
5
,

 
 
9
3
5
,

 
 
4
7
0
,

 
 
2
,

 
 
1
7
4
,

 
 
5
,

 
 
1
6
8
1
,

 
 
8
3
,

 
 
7
,

 
 
1
0
3
,

 
 
3
5
9
5
,

 
 
1
3
,

 
 
1
0
7
,

 
 
2
3
9
,

 
 
3
4
,

 
 
3
8
,

 
 
5
2
,

 
 
1
8
9
,

 
 
9
0
,

 
 
2
6
,

 
 
7
2
,

 
 
2
9
2
6
,

 
 
3
0
,

 
 
1
7
0
,

 
 
8
5
,

 
 
6
4
,

 
 
5
,

 
 
7
,

 
 
5
9
,

 
 
1
2
6
,

 
 
1
9
,

 
 
4
,

 
 
7
1
1
8
,

 
 
1
0
,

 
 
5
5
,

 
 
1
1
1
,

 
 
1
4
8
8
9
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
5
5
,

 
 
7
1
1
8
,

 
 
1
0
,

 
 
1
6
8
1
,

 
 
1
3
,

 
 
2
3
,

 
 
3
0
4
,

 
 
4
4
,

 
 
1
1
4
6
,

 
 
1
0
,

 
 
1
,

 
 
1
2
8
7
,

 
 
7
,

 
 
4
9
,

 
 
6
3
,

 
 
7
4
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
2
1
5
9
,

 
 
5
,

 
 
1
3
1
,

 
 
5
8
,

 
 
2
9
3
1
,

 
 
1
7
,

 
 
4
,

 
 
2
5
0
,

 
 
3
5
3
,

 
 
2
8
,

 
 
1
0
7
,

 
 
5
,

 
 
2
9
2
,

 
 
7
,

 
 
5
9
,

 
 
6
3
,

 
 
5
5
,

 
 
2
4
9
,

 
 
1
0
,

 
 
5
6
6
6
,

 
 
1
0
,

 
 
5
,

 
 
2
6
1
6
,

 
 
1
6
3
,

 
 
7
,

 
 
6
5
7
,

 
 
1
2
2
0
,

 
 
6
0
,

 
 
7
0
8
,

 
 
3
,

 
 
1
0
6
5
9
9
,

 
 
8
9
,

 
 
2
6
,

 
 
1
4
,

 
 
1
4
8
,

 
 
5
7
4
,

 
 
1
1
1
0
,

 
 
1
4
0
,

 
 
5
4
,

 
 
1
8
,

 
 
1
0
2
,

 
 
9
8
,

 
 
5
,

 
 
1
5
,

 
 
2
5
1
5
,

 
 
1
0
,

 
 
1
0
2
,

 
 
1
1
1
0
,

 
 
1
3
3
2
,

 
 
4
8
,

 
 
8
3
,

 
 
1
,

 
 
2
4
9
,

 
 
2
8
5
,

 
 
3
7
,

 
 
6
4
,

 
 
7
1
,

 
 
9
,

 
 
2
2
,

 
 
7
5
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
1
0
7
,

 
 
1
0
,

 
 
2
1
4
,

 
 
3
9
,

 
 
9
4
,

 
 
5
0
4
,

 
 
2
1
,

 
 
1
3
,

 
 
7
0
8
,

 
 
3
,

 
 
1
0
0
8
,

 
 
5
,

 
 
5
1
,

 
 
1
8
,

 
 
4
0
4
,

 
 
5
0
4
,

 
 
2
1
,

 
 
1
1
,

 
 
2
8
,

 
 
2
2
1
5
,

 
 
4
,

 
 
1
2
8
,

 
 
1
5
4
7
8
,

 
 
2
0
2
,

 
 
4
,

 
 
9
6
8
9
,

 
 
2
9
3
3
,

 
 
2
1
,

 
 
8
8
3
0
,

 
 
2
6
4
,

 
 
9
3
,

 
 
4
,

 
 
1
8
4
1
,

 
 
1
2
5
,

 
 
5
3
,

 
 
3
9
,

 
 
4
0
,

 
 
5
9
5
,

 
 
5
,

 
 
1
5
8
4
,

 
 
6
6
,

 
 
7
,

 
 
5
9
,

 
 
1
6
0
7
3
9
,

 
 
3
4
9
,

 
 
3
5
5
,

 
 
3
1
6
,

 
 
1
5
4
,

 
 
1
7
2
,

 
 
4
,

 
 
1
1
3
7
,

 
 
7
,

 
 
6
5
,

 
 
6
,

 
 
2
0
4
,

 
 
1
4
1
,

 
 
4
0
9
,

 
 
1
0
,

 
 
3
0
,

 
 
2
0
5
3
,

 
 
3
7
5
,

 
 
9
7
9
7
,

 
 
6
8
,

 
 
1
7
2
,

 
 
1
0
0
8
,

 
 
8
,

 
 
4
7
7
5
,

 
 
2
6
,

 
 
2
8
8
,

 
 
1
4
,

 
 
1
5
6
8
3
,

 
 
4
9
,

 
 
1
,

 
 
1
5
3
3
,

 
 
7
1
5
,

 
 
2
3
4
5
,

 
 
3
,

 
 
6
7
8
,

 
 
7
,

 
 
6
5
,

 
 
1
3
,

 
 
1
0
7
,

 
 
5
6
,

 
 
1
6
,

 
 
1
9
4
4
,

 
 
2
4
8
,

 
 
2
6
8
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
2
8
6
5
5
,

 
 
5
2
,

 
 
1
8
9
,

 
 
2
8
5
,

 
 
3
7
1
,

 
 
3
7
0
1
,

 
 
1
2
,

 
 
9
,

 
 
3
3
,

 
 
1
3
,

 
 
1
4
5
,

 
 
4
9
5
,

 
 
5
,

 
 
7
1
,

 
 
3
5
5
,

 
 
4
,

 
 
1
0
2
,

 
 
1
8
3
8
2
,

 
 
1
2
1
7
,

 
 
1
0
8
0
,

 
 
2
8
,

 
 
7
,

 
 
6
2
4
,

 
 
1
6
0
7
4
0
,

 
 
1
0
,

 
 
4
,

 
 
1
3
9
0
,

 
 
3
,

 
 
1
,

 
 
2
8
,

 
 
7
2
3
,

 
 
1
2
3
9
4
,

 
 
7
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
,

 
 
3
5
0
,

 
 
1
0
,

 
 
2
5
1
,

 
 
5
,

 
 
2
,

 
 
1
5
6
,

 
 
8
3
,

 
 
1
5
,

 
 
2
8
,

 
 
1
0
,

 
 
2
5
1
,

 
 
5
,

 
 
2
,

 
 
6
5
,

 
 
3
,

 
 
1
2
6
9
,

 
 
2
,

 
 
7
5
8
,

 
 
8
8
,

 
 
1
0
,

 
 
2
5
1
,

 
 
7
,

 
 
8
1
,

 
 
1
3
0
2
,

 
 
7
4
9
,

 
 
3
,

 
 
7
4
,

 
 
1
,

 
 
6
6
7
,

 
 
2
3
1
7
1
,

 
 
1
8
,

 
 
1
3
3
,

 
 
5
,

 
 
1
1
3
8
4
,

 
 
6
4
,

 
 
5
,

 
 
1
3
2
,

 
 
3
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
8
3
6
4
1
,

 
 
2
4
1
,

 
 
1
1
5
,

 
 
1
8
2
,

 
 
1
,

 
 
2
3
3
2
,

 
 
6
4
,

 
 
2
2
,

 
 
6
,

 
 
1
5
6
,

 
 
1
,

 
 
1
4
0
,

 
 
7
,

 
 
1
3
1
,

 
 
2
1
1
4
,

 
 
5
,

 
 
1
9
3
,

 
 
1
,

 
 
4
0
2
,

 
 
3
,

 
 
1
,

 
 
1
5
9
9
,

 
 
5
,

 
 
1
,

 
 
1
7
9
,

 
 
3
,

 
 
9
1
5
,

 
 
3
2
,

 
 
9
,

 
 
6
1
,

 
 
1
0
7
,

 
 
6
,

 
 
4
5
,

 
 
6
3
,

 
 
7
2
,

 
 
1
4
,

 
 
1
9
2
,

 
 
1
,

 
 
1
3
0
0
,

 
 
6
4
,

 
 
3
3
,

 
 
4
0
,

 
 
7
,

 
 
7
0
,

 
 
8
3
5
,

 
 
1
6
5
,

 
 
1
5
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
7
8
,

 
 
2
6
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
2
,

 
 
5
,

 
 
7
,

 
 
1
2
2
0
,

 
 
1
,

 
 
7
5
1
0
,

 
 
7
6
7
,

 
 
7
4
0
,

 
 
1
1
2
0
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
2
1
5
,

 
 
2
,

 
 
1
1
7
]
,

 
[
1
,

 
 
2
1
3
7
,

 
 
3
8
6
,

 
 
4
0
,

 
 
4
2
0
,

 
 
4
5
8
,

 
 
7
5
9
,

 
 
1
7
,

 
 
1
,

 
 
3
0
6
0
,

 
 
3
8
6
,

 
 
2
1
3
7
,

 
 
8
,

 
 
1
,

 
 
2
7
0
,

 
 
9
,

 
 
2
8
6
5
6
,

 
 
8
2
,

 
 
3
6
,

 
 
5
6
,

 
 
9
,

 
 
1
0
9
,

 
 
1
6
,

 
 
4
8
5
]
,

 
[
5
4
3
4
2
,
 
6
0
8
0
2
,
 
4
,
 
3
7
6
0
,
 
1
7
4
5
8
,
 
5
,
 
2
1
1
1
,
 
2
6
1
1
,
 
3
,
 
5
6
8
4
,
 
3
5
,
 
6
3
0
0
,
 
3
,
 
4
5
0
0
]
,

 
[
3
0
8
7
,

 
 
1
7
4
,

 
 
8
,

 
 
1
0
7
,

 
 
2
8
1
1
,

 
 
5
,

 
 
6
3
5
,

 
 
2
5
7
,

 
 
2
,

 
 
9
7
4
,

 
 
2
6
0
9
,

 
 
5
,

 
 
6
1
8
3
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
1
,

 
 
3
0
8
7
,

 
 
1
5
,

 
 
2
8
,

 
 
1
2
,

 
 
2
8
6
0
,

 
 
8
,

 
 
4
1
9
,

 
 
2
7
0
6
,

 
 
5
,

 
 
1
5
0
9
,

 
 
4
9
5
1
,

 
 
2
8
,

 
 
6
4
5
,

 
 
6
5
9
,

 
 
2
2
6
2
,

 
 
5
7
1
,

 
 
5
9
2
,

 
 
3
9
0
,

 
 
1
8
,

 
 
2
4
0
1
,

 
 
1
4
,

 
 
1
0
9
9
,

 
 
1
3
,

 
 
1
4
9
0
,

 
 
5
5
,

 
 
4
2
1
,

 
 
1
4
0
9
,

 
 
1
7
4
,

 
 
8
,

 
 
2
4
0
1
,

 
 
1
0
7
,

 
 
4
6
4
9
,

 
 
4
7
3
,

 
 
1
,

 
 
7
8
6
,

 
 
1
1
2
6
,

 
 
3
7
4
0
,

 
 
3
0
8
7
,

 
 
1
1
3
,

 
 
6
0
8
0
3
,

 
 
1
7
,

 
 
1
3
7
,

 
 
1
6
7
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
2
5
0
,

 
 
2
6
0
6
,

 
 
3
1
9
,

 
 
2
2
,

 
 
6
,

 
 
7
8
9
,

 
 
7
,

 
 
2
4
3
8
,

 
 
6
,

 
 
2
,

 
 
1
5
9
,

 
 
1
1
,

 
 
7
3
,

 
 
3
3
,

 
 
2
8
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
1
7
5
5
]
,

 
[
7
2
,

 
 
1
1
5
,

 
 
2
,

 
 
1
3
,

 
 
4
2
5
,

 
 
3
,

 
 
8
8
3
1
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
8
6
,

 
 
9
,

 
 
7
,

 
 
5
0
7
9
,

 
 
1
3
,

 
 
1
0
,

 
 
1
,

 
 
1
4
3
,

 
 
6
4
1
,

 
 
1
9
7
,

 
 
7
,

 
 
8
1
,

 
 
2
6
8
4
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
5
2
9
,

 
 
2
1
0
4
,

 
 
7
1
4
,

 
 
4
2
0
2
,

 
 
3
1
5
1
,

 
 
2
3
3
9
,

 
 
2
,

 
 
1
1
8
,

 
 
1
5
,

 
 
1
,

 
 
5
8
6
,

 
 
1
0
,

 
 
1
,

 
 
4
9
0
,

 
 
8
9
7
,

 
 
3
,

 
 
8
9
2
,

 
 
1
0
,

 
 
1
,

 
 
5
9
9
,

 
 
7
,

 
 
1
9
,

 
 
2
2
2
4
,

 
 
4
,

 
 
3
7
4
0
,

 
 
3
,

 
 
1
9
9
5
,

 
 
1
6
1
4
4
,

 
 
2
5
0
,

 
 
1
1
5
6
9
,

 
 
4
0
2
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
6
1
5
,

 
 
1
1
8
7
,

 
 
5
,

 
 
1
3
8
9
,

 
 
5
,

 
 
4
9
4
5
0
,

 
 
1
9
3
8
,

 
 
1
0
,

 
 
1
,

 
 
1
2
1
1
,

 
 
1
4
6
6
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
1
5
8
4
,

 
 
1
3
,

 
 
2
2
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
1
1
0
,

 
 
3
,

 
 
2
9
8
,

 
 
1
1
,

 
 
4
5
4
6
,

 
 
2
,

 
 
1
3
6
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
1
1
8
5
,

 
 
3
2
8
,

 
 
5
,

 
 
3
7
4
,

 
 
9
8
6
,

 
 
5
9
7
6
,

 
 
1
5
,

 
 
1
,

 
 
1
4
6
9
,

 
 
1
8
0
,

 
 
1
1
0
7
,

 
 
4
3
,

 
 
1
3
,

 
 
1
6
,

 
 
6
1
1
,

 
 
1
2
,

 
 
2
5
9
]
,

 
[
1
6
0
7
4
1
,
 
2
0
3
,
 
3
6
8
,
 
1
,
 
2
1
7
,
 
7
,
 
9
0
,
 
1
4
]
,

 
[
2
9
6
,

 
 
7
,

 
 
1
9
,

 
 
1
5
6
,

 
 
8
8
,

 
 
2
1
0
,

 
 
5
,

 
 
7
,

 
 
4
5
,

 
 
8
9
,

 
 
2
1
9
,

 
 
6
,

 
 
2
,

 
 
4
9
8
,

 
 
1
5
7
,

 
 
7
3
,

 
 
1
2
,

 
 
2
0
,

 
 
6
9
0
,

 
 
1
4
,

 
 
9
,

 
 
1
1
,

 
 
1
7
0
8
,

 
 
1
0
,

 
 
1
,

 
 
3
0
8
,

 
 
1
,

 
 
4
7
,

 
 
1
0
4
5
,

 
 
8
,

 
 
1
7
,

 
 
3
6
6
,

 
 
1
7
,

 
 
1
,

 
 
6
1
,

 
 
2
6
,

 
 
6
,

 
 
2
0
1
,

 
 
1
9
,

 
 
6
0
,

 
 
9
4
6
,

 
 
1
2
,

 
 
2
0
,

 
 
5
3
8
,

 
 
4
9
4
5
1
]
,

 
[
7
,

 
 
6
5
,

 
 
1
,

 
 
1
0
0
9
,

 
 
8
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
2
7
6
9
1
,

 
 
1
4
,

 
 
2
4
4
6
8
,

 
 
3
6
,

 
 
1
6
2
,

 
 
3
6
3
,

 
 
9
5
7
6
,

 
 
7
2
,

 
 
1
2
9
,

 
 
1
,

 
 
2
3
,

 
 
9
8
6
7
,

 
 
5
3
,

 
 
1
9
,

 
 
4
,

 
 
2
0
1
,

 
 
7
7
7
,

 
 
2
2
,

 
 
7
2
,

 
 
2
4
7
,

 
 
5
0
,

 
 
2
3
6
,

 
 
1
1
,

 
 
1
5
7
,

 
 
9
5
5
,

 
 
4
5
2
,

 
 
1
5
8
2
,

 
 
2
9
4
0
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
9
5
7
7
,

 
 
2
7
8
3
,

 
 
1
0
6
6
0
0
,

 
 
8
,

 
 
8
3
6
4
2
,

 
 
1
7
1
7
2
,

 
 
5
7
3
9
,

 
 
7
9
3
2
,

 
 
8
2
5
7
,

 
 
4
,

 
 
6
0
2
8
,

 
 
4
2
3
7
3
,

 
 
3
,

 
 
1
6
0
7
4
2
,

 
 
5
,

 
 
4
9
2
,

 
 
3
0
0
6
,

 
 
1
0
5
7
,

 
 
1
,

 
 
4
2
1
3
,

 
 
3
,

 
 
1
2
0
7
6
,

 
 
5
0
2
5
,

 
 
1
4
9
9
,

 
 
6
8
,

 
 
3
4
7
,

 
 
1
2
,

 
 
1
,

 
 
1
1
4
7
8
,

 
 
5
2
,

 
 
8
,

 
 
8
3
6
4
3
,

 
 
3
5
7
,

 
 
1
2
9
,

 
 
1
,

 
 
1
2
1
8
6
,

 
 
1
2
4
,

 
 
1
5
,

 
 
1
,

 
 
8
3
6
4
2
,

 
 
1
1
4
7
8
,

 
 
6
8
,

 
 
1
7
0
,

 
 
5
,

 
 
5
4
5
0
,

 
 
1
6
0
7
4
3
,

 
 
2
9
,

 
 
1
0
,

 
 
5
2
7
,

 
 
2
,

 
 
1
0
8
9
3
,

 
 
6
8
,

 
 
2
0
7
5
,

 
 
1
0
6
6
0
1
,

 
 
5
9
9
8
,

 
 
5
,

 
 
2
1
5
8
7
,

 
 
1
,

 
 
1
9
4
0
,

 
 
3
,

 
 
1
1
2
,

 
 
8
3
,

 
 
5
2
,

 
 
8
9
4
,

 
 
3
1
1
3
,

 
 
2
2
,

 
 
5
2
,

 
 
8
9
4
,

 
 
3
6
9
5
,

 
 
1
9
2
,

 
 
1
2
7
3
0
,

 
 
6
2
2
5
,

 
 
9
2
4
,

 
 
8
5
1
,

 
 
2
6
,

 
 
7
6
0
2
,

 
 
5
7
2
,

 
 
4
1
7
0
,

 
 
7
5
6
3
,

 
 
3
6
,

 
 
5
9
,

 
 
1
6
,

 
 
2
0
4
,

 
 
1
9
2
]
,

 
[
5
1
5
,

 
 
3
,

 
 
9
4
0
,

 
 
1
0
7
,

 
 
1
0
6
6
0
2
,

 
 
4
2
,

 
 
5
5
5
,

 
 
4
,

 
 
3
9
7
8
,

 
 
2
,

 
 
1
3
,

 
 
2
3
,

 
 
5
,

 
 
4
2
,

 
 
7
0
5
,

 
 
1
5
9
6
,

 
 
2
8
2
2
,

 
 
2
,

 
 
3
0
4
,

 
 
9
4
,

 
 
1
1
,

 
 
1
4
6
,

 
 
2
5
,

 
 
1
0
4
,

 
 
1
0
9
,

 
 
4
8
5
,

 
 
1
6
2
,

 
 
5
7
4
,

 
 
4
1
9
6
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
3
3
6
,

 
 
1
6
0
,

 
 
4
1
9
6
,

 
 
6
0
4
9
,

 
 
3
3
6
,

 
 
2
3
3
,

 
 
1
3
2
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
4
9
9
,

 
 
8
6
0
,

 
 
1
1
7
0
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
1
1
,

 
 
9
9
,

 
 
2
1
3
0
,

 
 
2
7
,

 
 
8
6
0
,

 
 
1
3
,

 
 
4
1
2
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
,

 
 
8
6
0
,

 
 
2
4
,

 
 
8
0
4
0
,

 
 
3
3
,

 
 
5
5
8
,

 
 
4
6
1
,

 
 
1
2
,

 
 
2
4
6
,

 
 
1
,

 
 
4
2
4
,

 
 
8
6
0
,

 
 
6
4
,

 
 
1
8
8
8
,

 
 
3
3
,

 
 
6
7
5
,

 
 
4
6
1
,

 
 
1
2
,

 
 
2
4
6
,

 
 
2
6
,

 
 
1
1
7
0
,

 
 
9
,

 
 
1
0
6
6
0
2
,

 
 
4
2
,

 
 
6
0
8
0
4
,

 
 
4
0
,

 
 
1
,

 
 
1
1
0
,

 
 
3
3
0
,

 
 
1
1
,

 
 
4
0
8
,

 
 
1
1
,

 
 
1
3
1
7
,

 
 
3
8
1
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
6
5
,

 
 
2
,

 
 
1
6
,

 
 
1
3
9
8
,

 
 
5
1
,

 
 
1
0
7
8
,

 
 
4
,

 
 
1
0
9
,

 
 
2
3
6
,

 
 
4
3
,

 
 
1
6
,

 
 
2
0
1
,

 
 
3
6
5
,

 
 
4
8
5
,

 
 
1
,

 
 
1
0
9
,

 
 
3
,

 
 
1
,

 
 
7
4
6
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
2
4
,

 
 
7
7
8
,

 
 
2
,

 
 
1
5
9
,

 
 
1
1
,

 
 
2
,

 
 
4
6
,

 
 
1
5
1
,

 
 
4
,

 
 
1
9
5
6
,

 
 
2
8
1
,

 
 
1
3
8
,

 
 
1
5
,

 
 
4
6
,

 
 
6
9
2
,

 
 
1
,

 
 
2
3
,

 
 
4
9
5
,

 
 
5
,

 
 
2
4
,

 
 
3
6
8
,

 
 
7
,

 
 
2
4
,

 
 
1
6
3
8
,

 
 
5
4
3
2
,

 
 
3
,

 
 
1
,

 
 
4
4
0
0
,

 
 
3
,

 
 
1
3
,

 
 
2
9
2
,

 
 
7
8
,

 
 
5
1
,

 
 
8
6
,

 
 
5
7
4
,

 
 
6
5
7
9
,

 
 
2
,

 
 
3
5
6
,

 
 
2
5
,

 
 
4
6
0
,

 
 
1
3
,

 
 
2
3
,

 
 
3
8
8
,

 
 
7
,

 
 
1
2
2
8
,

 
 
5
1
,

 
 
8
6
,

 
 
5
5
4
,

 
 
1
0
,

 
 
4
3
4
9
,

 
 
1
7
1
2
,

 
 
4
7
,

 
 
3
,

 
 
5
4
,

 
 
8
,

 
 
7
6
3
,

 
 
7
,

 
 
4
,

 
 
2
1
2
7
,

 
 
5
,

 
 
1
0
1
6
7
,

 
 
9
,

 
 
5
1
,

 
 
2
5
9
3
,

 
 
9
,

 
 
1
,

 
 
1
4
9
,

 
 
1
0
3
,

 
 
1
6
,

 
 
1
5
0
3
,

 
 
9
2
,

 
 
3
3
9
8
,

 
 
1
0
2
7
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
7
6
3
,

 
 
7
,

 
 
4
,

 
 
1
7
,

 
 
4
,

 
 
4
3
9
,

 
 
2
,

 
 
7
6
3
,

 
 
7
,

 
 
4
,

 
 
2
1
2
7
,

 
 
3
3
2
1
,

 
 
1
3
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
7
,

 
 
8
1
,

 
 
1
3
1
4
,

 
 
1
7
,

 
 
2
,

 
 
3
8
5
,

 
 
1
,

 
 
7
4
6
,

 
 
8
,

 
 
2
0
3
,

 
 
3
1
6
,

 
 
1
5
0
9
9
,

 
 
2
5
,

 
 
7
6
3
,

 
 
7
,

 
 
4
,

 
 
1
1
,

 
 
8
1
1
0
,

 
 
1
,

 
 
7
4
6
,

 
 
5
4
0
,

 
 
9
3
8
,

 
 
7
6
3
,

 
 
7
,

 
 
4
,

 
 
1
7
,

 
 
1
,

 
 
2
1
6
2
,

 
 
1
5
,

 
 
9
2
,

 
 
1
7
0
,

 
 
4
2
1
,

 
 
2
6
,

 
 
8
4
,

 
 
9
3
8
,

 
 
4
,

 
 
4
6
7
1
,

 
 
3
,

 
 
2
1
0
,

 
 
1
6
1
6
,

 
 
1
4
4
,

 
 
1
0
,

 
 
1
,

 
 
1
9
8
,

 
 
3
,

 
 
1
3
2
,

 
 
1
0
6
,

 
 
1
3
,

 
 
8
,

 
 
7
7
,

 
 
6
7
4
,

 
 
2
,

 
 
1
6
,

 
 
1
4
3
7
2
,

 
 
1
2
8
,

 
 
1
7
,

 
 
7
3
9
,

 
 
2
6
5
,

 
 
7
6
3
,

 
 
1
8
,

 
 
3
6
3
4
,

 
 
1
4
5
8
,

 
 
2
,

 
 
1
7
,

 
 
3
2
1
8
0
,

 
 
5
,

 
 
1
4
4
,

 
 
1
,

 
 
2
3
,

 
 
4
2
,

 
 
2
2
9
2
,

 
 
6
4
,

 
 
1
2
,

 
 
4
,

 
 
2
0
8
,

 
 
5
,

 
 
9
,

 
 
4
0
,

 
 
1
,

 
 
3
3
6
8
7
,

 
 
1
1
8
,

 
 
2
,

 
 
1
3
,

 
 
4
0
7
,

 
 
5
,

 
 
1
3
2
,

 
 
3
,

 
 
4
0
,

 
 
6
9
,

 
 
5
3
,

 
 
8
0
7
,

 
 
2
7
8
,

 
 
1
0
4
1
,

 
 
4
1
0
,

 
 
9
4
,

 
 
9
2
,

 
 
1
1
0
,

 
 
1
,

 
 
2
3
,

 
 
5
6
,

 
 
6
0
6
,

 
 
6
4
]
,

 
[
1
1
,

 
 
8
,

 
 
1
0
6
6
0
3
,

 
 
1
2
0
,

 
 
6
9
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
5
4
,

 
 
7
4
,

 
 
1
3
0
,

 
 
3
2
4
3
,

 
 
8
6
,

 
 
1
0
8
7
,

 
 
3
8
,

 
 
1
7
0
8
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
1
6
1
4
5
,

 
 
8
6
,

 
 
2
5
9
4
7
,

 
 
1
5
5
6
,

 
 
9
,

 
 
1
7
5
2
,

 
 
9
,

 
 
1
0
5
,

 
 
1
7
7
,

 
 
2
9
0
,

 
 
5
5
,

 
 
2
1
9
8
,

 
 
3
5
,

 
 
1
,

 
 
1
8
7
3
3
,

 
 
3
,

 
 
1
,

 
 
8
3
8
3
,

 
 
1
9
7
0
,

 
 
1
2
,

 
 
3
1
1
,

 
 
1
,

 
 
7
9
6
,

 
 
3
1
0
2
,

 
 
3
,

 
 
1
,

 
 
1
7
7
6
6
,

 
 
7
1
9
,

 
 
4
7
3
,

 
 
9
9
2
,

 
 
5
,

 
 
1
0
1
4
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
,

 
 
8
0
0
2
,

 
 
1
5
,

 
 
1
,

 
 
5
4
0
2
,

 
 
1
0
9
3
,

 
 
1
0
,

 
 
3
7
4
2
3
,

 
 
1
5
8
9
5
,

 
 
5
,

 
 
4
6
2
8
,

 
 
3
,

 
 
1
5
6
8
4
,

 
 
8
,

 
 
4
1
9
,

 
 
4
1
3
,

 
 
1
5
5
6
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
1
4
,

 
 
1
2
2
1
,

 
 
5
5
,

 
 
1
0
6
,

 
 
1
2
,

 
 
2
0
,

 
 
4
0
3
,

 
 
9
,

 
 
5
4
3
4
3
,

 
 
2
5
9
4
8
,

 
 
3
2
4
3
,

 
 
8
6
,

 
 
1
0
8
7
,

 
 
5
,

 
 
1
7
,

 
 
1
2
,

 
 
1
,

 
 
1
4
0
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
5
4
,

 
 
3
8
,

 
 
6
,

 
 
2
2
0
,

 
 
1
1
,

 
 
7
7
,

 
 
1
7
0
8
,

 
 
3
8
,

 
 
1
,

 
 
2
8
,

 
 
4
7
5
,

 
 
1
8
,

 
 
6
,

 
 
6
7
0
,

 
 
4
,

 
 
3
7
7
,

 
 
1
7
7
,

 
 
8
1
7
7
,

 
 
2
1
5
,

 
 
1
8
5
,

 
 
1
,

 
 
1
3
9
,

 
 
1
7
,

 
 
3
0
7
3
,

 
 
1
,

 
 
8
1
7
,

 
 
1
7
9
,

 
 
1
7
,

 
 
4
,

 
 
3
7
7
,

 
 
1
3
7
0
,

 
 
8
2
,

 
 
1
,

 
 
3
2
5
,

 
 
3
7
7
,

 
 
1
3
7
0
,

 
 
3
8
2
]
,

 
[
2
1
3
9
,

 
 
5
4
1
,

 
 
1
,

 
 
1
7
7
1
,

 
 
7
,

 
 
2
1
1
,

 
 
2
7
5
4
,

 
 
1
2
,

 
 
2
1
3
9
,

 
 
9
9
,

 
 
2
,

 
 
9
2
3
,

 
 
1
,

 
 
1
1
2
6
,

 
 
1
0
,

 
 
1
1
7
7
,

 
 
5
,

 
 
8
4
,

 
 
3
5
0
,

 
 
1
,

 
 
1
7
7
1
,

 
 
4
8
8
,

 
 
6
2
,

 
 
3
4
9
,

 
 
6
5
1
,

 
 
9
2
,

 
 
8
5
,

 
 
2
,

 
 
3
5
0
,

 
 
1
,

 
 
1
7
7
1
,

 
 
1
1
6
,

 
 
2
4
5
,

 
 
1
6
,

 
 
3
9
7
0
2
,

 
 
1
2
,

 
 
3
0
0
,

 
 
1
9
7
,

 
 
1
0
4
,

 
 
1
1
3
8
,

 
 
1
,

 
 
2
2
3
,

 
 
1
2
5
,

 
 
8
3
6
4
4
,

 
 
1
1
5
0
,

 
 
8
,

 
 
1
1
7
4
6
,

 
 
1
5
,

 
 
6
8
,

 
 
1
3
4
6
2
,

 
 
1
6
1
4
6
,

 
 
1
5
,

 
 
4
,

 
 
3
6
9
6
,

 
 
2
3
1
7
2
,

 
 
1
9
0
6
1
,

 
 
9
7
4
8
,

 
 
1
5
4
,

 
 
2
0
8
,

 
 
4
3
0
,

 
 
1
4
8
9
4
,

 
 
1
0
5
2
,

 
 
9
2
3
,

 
 
6
6
,

 
 
3
9
5
,

 
 
6
0
,

 
 
8
2
,

 
 
3
,

 
 
4
,

 
 
7
9
7
0
,

 
 
6
2
8
2
,

 
 
1
0
,

 
 
1
3
,

 
 
2
6
0
2
,

 
 
1
3
,

 
 
8
,

 
 
1
6
4
1
,

 
 
4
7
,

 
 
1
6
2
4
,

 
 
6
5
9
,

 
 
4
4
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
8
3
8
4
,

 
 
3
7
7
,

 
 
1
3
,

 
 
6
5
9
,

 
 
8
,

 
 
1
9
4
1
1
,

 
 
4
,

 
 
7
2
9
,

 
 
4
5
4
3
,

 
 
3
2
,

 
 
1
,

 
 
1
6
2
4
,

 
 
3
7
8
5
,

 
 
6
5
9
,

 
 
8
9
8
3
,

 
 
1
,

 
 
2
5
7
0
,

 
 
2
4
5
,

 
 
1
9
,

 
 
5
7
,

 
 
1
9
0
6
2
,

 
 
1
3
5
,

 
 
4
6
7
4
,

 
 
1
0
,

 
 
1
3
,

 
 
2
8
0
7
,

 
 
6
5
9
,

 
 
3
9
5
,

 
 
8
3
8
4
,

 
 
8
6
0
6
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
2
9
8
9
,

 
 
6
5
9
,

 
 
3
9
7
0
3
,

 
 
5
,

 
 
8
4
,

 
 
3
9
5
,

 
 
1
3
,

 
 
1
5
6
4
,

 
 
2
,

 
 
3
7
,

 
 
5
9
,

 
 
9
2
3
,

 
 
1
3
,

 
 
6
5
9
,

 
 
4
4
,

 
 
3
5
4
,

 
 
7
4
,

 
 
1
2
8
,

 
 
6
,

 
 
1
8
,

 
 
7
5
1
1
]
,

 
[
1
7
,

 
 
5
2
,

 
 
4
2
,

 
 
6
3
6
,

 
 
6
4
0
,

 
 
1
4
,

 
 
2
,

 
 
2
0
6
,

 
 
7
,

 
 
4
5
,

 
 
1
5
7
1
,

 
 
3
1
,

 
 
2
9
8
,

 
 
3
6
,

 
 
7
,

 
 
9
0
,

 
 
1
9
7
,

 
 
2
5
6
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
2
4
8
,

 
 
1
5
4
,

 
 
2
2
,

 
 
2
5
9
,

 
 
2
0
6
6
,

 
 
2
,

 
 
5
6
3
,

 
 
1
3
,

 
 
8
5
1
,

 
 
5
0
,

 
 
7
9
4
,

 
 
3
7
,

 
 
2
7
3
4
]
,

 
[
3
9
,

 
 
5
3
,

 
 
1
9
7
1
,

 
 
6
4
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
5
3
,

 
 
1
9
,

 
 
1
,

 
 
4
3
9
4
,

 
 
1
2
,

 
 
1
6
8
9
8
,

 
 
2
6
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
0
,

 
 
1
,

 
 
5
3
4
0
,

 
 
4
1
,

 
 
8
,

 
 
2
7
,

 
 
1
0
,

 
 
3
2
9
,

 
 
1
3
2
8
,

 
 
5
8
,

 
 
1
7
4
5
9
,

 
 
9
,

 
 
1
0
,

 
 
2
9
2
4
,

 
 
2
4
,

 
 
3
1
6
,

 
 
1
6
8
9
8
,

 
 
1
1
6
5
6
,

 
 
3
6
,

 
 
3
1
3
,

 
 
3
6
,

 
 
9
8
,

 
 
2
8
3
,

 
 
8
9
2
7
,

 
 
7
6
0
2
,

 
 
4
4
,

 
 
4
7
,

 
 
4
2
,

 
 
3
5
1
,

 
 
2
6
6
4
,

 
 
9
,

 
 
6
,

 
 
1
3
3
,

 
 
2
,

 
 
8
8
1
,

 
 
3
4
2
6
,

 
 
1
2
,

 
 
4
,

 
 
2
5
9
4
9
,

 
 
2
5
,

 
 
9
,

 
 
6
,

 
 
3
3
6
8
8
,

 
 
1
0
,

 
 
4
,

 
 
2
5
1
5
1
,

 
 
4
,

 
 
1
2
2
3
,

 
 
3
2
5
7
,

 
 
1
0
6
6
0
4
,

 
 
2
4
,

 
 
1
1
,

 
 
1
0
,

 
 
4
,

 
 
1
7
1
7
,

 
 
1
0
,

 
 
1
,

 
 
2
1
6
9
,

 
 
1
6
0
7
4
4
,

 
 
7
2
,

 
 
1
4
,

 
 
1
3
4
6
,

 
 
4
1
5
,

 
 
7
,

 
 
5
6
,

 
 
2
1
9
,

 
 
6
,

 
 
3
3
,

 
 
2
0
,

 
 
1
3
9
3
,

 
 
3
5
,

 
 
1
,

 
 
8
2
3
,

 
 
8
2
,

 
 
3
,

 
 
7
1
7
,

 
 
1
1
4
7
,

 
 
5
1
9
]
,

 
[
2
8
0
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
8
6
,

 
 
7
4
,

 
 
2
,

 
 
1
5
9
,

 
 
4
6
6
,

 
 
3
,

 
 
1
5
4
,

 
 
5
2
,

 
 
4
2
,

 
 
3
7
1
,

 
 
1
,

 
 
1
7
9
,

 
 
5
,

 
 
2
0
3
,

 
 
4
2
,

 
 
9
2
4
,

 
 
9
6
1
,

 
 
3
3
9
2
,

 
 
1
,

 
 
2
3
1
7
3
,

 
 
2
0
8
8
,

 
 
4
8
4
,

 
 
2
8
,

 
 
8
,

 
 
3
3
,

 
 
2
7
5
9
,

 
 
2
2
,

 
 
5
2
,

 
 
1
4
0
,

 
 
5
5
,

 
 
3
,

 
 
1
4
1
,

 
 
1
2
4
,

 
 
2
5
,

 
 
5
5
,

 
 
4
8
0
1
,

 
 
6
7
2
,

 
 
1
,

 
 
7
4
3
,

 
 
1
2
5
4
,

 
 
8
,

 
 
3
2
0
4
,

 
 
1
5
8
2
,

 
 
2
3
9
3
,

 
 
4
3
9
0
,

 
 
5
4
,

 
 
8
,

 
 
4
,

 
 
2
2
2
5
,

 
 
3
,

 
 
3
9
7
0
4
]
,

 
[
5
3
,

 
 
3
9
,

 
 
2
6
3
,

 
 
2
,

 
 
7
8
9
,

 
 
1
5
,

 
 
1
,

 
 
3
1
3
0
,

 
 
3
7
4
3
,

 
 
3
,

 
 
1
,

 
 
1
3
2
8
,

 
 
5
,

 
 
1
,

 
 
1
0
1
5
,

 
 
2
6
,

 
 
1
,

 
 
9
3
3
,

 
 
1
6
0
7
4
5
,

 
 
8
,

 
 
2
2
3
,

 
 
3
,

 
 
7
1
9
,

 
 
1
6
0
7
4
6
,

 
 
4
9
5
,

 
 
3
6
,

 
 
1
8
5
,

 
 
1
2
0
0
,

 
 
9
8
5
,

 
 
1
0
3
1
,

 
 
1
0
3
7
,

 
 
1
4
3
,

 
 
4
1
]
,

 
[
6
3
2
,

 
 
4
2
8
6
,

 
 
1
8
,

 
 
3
2
6
4
,

 
 
5
6
3
0
,

 
 
1
3
5
,

 
 
1
,

 
 
1
3
8
3
,

 
 
8
0
,

 
 
1
,

 
 
6
9
8
3
7
,

 
 
1
8
,

 
 
3
4
2
5
,

 
 
2
6
,

 
 
9
,

 
 
1
8
1
,

 
 
2
7
6
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
3
3
7
5
,

 
 
1
4
2
,

 
 
8
,

 
 
2
3
7
3
,

 
 
8
2
8
,

 
 
4
1
,

 
 
8
,

 
 
1
5
3
,

 
 
4
,

 
 
9
5
9
,

 
 
1
2
7
2
,

 
 
3
,

 
 
1
4
2
,

 
 
2
,

 
 
1
6
,

 
 
2
0
7
,

 
 
4
7
3
,

 
 
9
3
5
0
,

 
 
1
,

 
 
8
0
4
1
,

 
 
3
,

 
 
1
,

 
 
2
9
9
0
,

 
 
1
6
1
2
,

 
 
1
,

 
 
4
9
4
5
2
,

 
 
3
2
1
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
2
3
,

 
 
1
7
7
6
7
,

 
 
1
6
0
7
4
7
,

 
 
1
8
2
,

 
 
3
3
7
5
,

 
 
4
7
2
,

 
 
1
2
,

 
 
3
1
1
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
1
,

 
 
2
9
9
0
,

 
 
8
,

 
 
2
3
7
,

 
 
1
0
,

 
 
1
,

 
 
1
3
8
3
,

 
 
2
6
,

 
 
4
,

 
 
9
5
9
,

 
 
1
2
7
2
,

 
 
3
,

 
 
1
4
2
,

 
 
8
,

 
 
9
1
,

 
 
2
0
7
,

 
 
2
,

 
 
1
,

 
 
4
9
4
5
2
,

 
 
6
,

 
 
3
9
,

 
 
6
6
,

 
 
1
5
6
,

 
 
2
9
9
0
,

 
 
1
6
3
4
,

 
 
5
,

 
 
9
6
9
2
,

 
 
1
2
,

 
 
5
8
,

 
 
1
0
5
,

 
 
3
5
,

 
 
9
6
9
2
,

 
 
2
2
6
,

 
 
9
,

 
 
1
8
0
7
]
,

 
[
3
3
,

 
 
5
4
,

 
 
1
4
5
,

 
 
7
,

 
 
8
1
,

 
 
2
3
8
3
3
,

 
 
2
0
4
8
,

 
 
5
,

 
 
5
4
3
4
4
,

 
 
5
4
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
1
,

 
 
2
8
,

 
 
8
3
6
4
5
,

 
 
5
6
8
,

 
 
6
3
9
,

 
 
2
,

 
 
5
5
,

 
 
1
1
5
4
,

 
 
4
8
1
2
,

 
 
1
5
,

 
 
1
,

 
 
4
7
4
0
,

 
 
8
5
1
5
,

 
 
2
6
7
,

 
 
4
7
,

 
 
1
8
4
,

 
 
6
5
,

 
 
3
1
6
1
,

 
 
8
0
0
3
,

 
 
2
6
4
8
,

 
 
4
2
3
7
4
,

 
 
2
,

 
 
2
6
2
6
,

 
 
9
2
,

 
 
3
4
5
7
,

 
 
3
8
3
,

 
 
5
1
,

 
 
1
8
,

 
 
7
4
9
,

 
 
3
,

 
 
1
,

 
 
1
6
0
7
4
8
,

 
 
3
,

 
 
9
2
,

 
 
5
7
5
,

 
 
5
,

 
 
7
8
5
,

 
 
1
2
6
,

 
 
2
5
8
2
,

 
 
1
1
,

 
 
4
5
,

 
 
4
9
,

 
 
1
1
8
,

 
 
5
0
4
,

 
 
2
8
0
,

 
 
7
4
2
,

 
 
1
1
,

 
 
6
2
4
]
,

 
[
6
,

 
 
1
2
2
,

 
 
2
,

 
 
9
8
4
,

 
 
5
0
3
,

 
 
2
0
9
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
4
9
,

 
 
6
9
,

 
 
1
1
,

 
 
4
2
,

 
 
6
0
,

 
 
3
3
6
8
9
,

 
 
7
4
,

 
 
6
3
2
,

 
 
1
8
,

 
 
5
1
,

 
 
6
2
,

 
 
3
7
4
1
,

 
 
8
8
,

 
 
1
0
,

 
 
2
2
3
,

 
 
3
,

 
 
4
,

 
 
5
4
6
,

 
 
1
8
1
,

 
 
9
7
,

 
 
1
1
,

 
 
3
4
2
,

 
 
6
6
,

 
 
6
,

 
 
1
2
2
,

 
 
2
,

 
 
2
3
6
,

 
 
2
0
,

 
 
7
1
2
,

 
 
1
3
,

 
 
4
7
,

 
 
4
5
,

 
 
2
8
8
,

 
 
1
6
,

 
 
1
8
8
,

 
 
7
3
0
,

 
 
1
2
,

 
 
2
4
2
2
,

 
 
1
,

 
 
7
1
2
,

 
 
2
3
0
,

 
 
4
4
,

 
 
5
4
2
,

 
 
3
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
8
1
1
1
,

 
 
4
6
,

 
 
2
,

 
 
3
7
]
,

 
[
1
6
0
7
4
9
,

 
 
4
9
5
2
,

 
 
5
,

 
 
3
0
,

 
 
1
1
0
0
,

 
 
7
7
,

 
 
6
9
,

 
 
7
9
8
,

 
 
3
0
8
3
2
,

 
 
9
9
,

 
 
3
6
8
,

 
 
5
5
,

 
 
3
,

 
 
4
1
4
,

 
 
3
,

 
 
1
1
6
8
,

 
 
3
3
9
,

 
 
2
,

 
 
1
3
,

 
 
2
3
,

 
 
3
6
,

 
 
3
1
3
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
1
9
,

 
 
4
,

 
 
5
2
8
,

 
 
1
1
0
5
,

 
 
2
,

 
 
2
0
9
1
,

 
 
1
1
,

 
 
6
8
,

 
 
2
3
,

 
 
3
1
6
,

 
 
1
0
6
6
0
5
,

 
 
8
,

 
 
1
4
,

 
 
3
5
,

 
 
2
1
0
8
7
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
3
5
,

 
 
6
8
,

 
 
6
4
0
5
,

 
 
6
2
,

 
 
1
0
8
4
,

 
 
4
1
,

 
 
1
8
,

 
 
4
,

 
 
1
0
6
4
,

 
 
1
6
0
7
5
0
,

 
 
4
5
6
,

 
 
7
7
,

 
 
1
,

 
 
6
6
0
,

 
 
3
,

 
 
2
1
0
8
7
,

 
 
4
1
,

 
 
1
8
,

 
 
1
3
0
,

 
 
4
0
1
2
,

 
 
3
,

 
 
1
0
5
9
,

 
 
2
7
1
,

 
 
2
1
0
8
7
,

 
 
2
3
4
9
,

 
 
1
4
1
,

 
 
4
8
7
,

 
 
5
4
,

 
 
7
9
8
,

 
 
3
0
8
3
2
,

 
 
1
1
1
,

 
 
5
4
3
4
5
,

 
 
1
3
7
5
2
,

 
 
1
0
,

 
 
1
4
5
2
,

 
 
3
3
5
6
,

 
 
2
5
,

 
 
3
1
7
2
,

 
 
6
4
7
8
,

 
 
1
0
5
6
,

 
 
8
6
,

 
 
9
5
7
,

 
 
1
0
5
9
,

 
 
2
7
1
,

 
 
1
3
6
9
,

 
 
3
,

 
 
1
0
6
6
0
6
,

 
 
1
5
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
1
,

 
 
7
9
8
,

 
 
3
0
8
3
2
,

 
 
3
7
5
,

 
 
1
9
9
,

 
 
8
2
0
,

 
 
6
0
8
0
5
,

 
 
5
3
1
1
,

 
 
2
1
0
8
7
,

 
 
2
5
,

 
 
1
,

 
 
2
1
0
8
7
,

 
 
3
,

 
 
4
5
8
3
,

 
 
6
0
8
0
6
,

 
 
5
3
1
1
,

 
 
3
,

 
 
1
1
3
0
,

 
 
6
7
8
2
,

 
 
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
2
1
0
8
7
,

 
 
3
8
,

 
 
3
5
,

 
 
1
5
7
5
,

 
 
1
6
0
7
5
1
,

 
 
8
,

 
 
1
1
,

 
 
1
4
,

 
 
2
1
0
8
7
,

 
 
8
6
5
2
,

 
 
9
3
0
5
,

 
 
2
5
,

 
 
1
5
6
8
5
,

 
 
7
6
3
5
,

 
 
3
4
,

 
 
9
0
,

 
 
1
4
,

 
 
4
9
7
5
,

 
 
2
1
0
8
7
,

 
 
1
0
0
,

 
 
5
5
,

 
 
3
,

 
 
1
1
2
,

 
 
1
0
6
6
0
6
,

 
 
1
0
7
5
,

 
 
4
9
4
5
3
,

 
 
1
4
,

 
 
2
,

 
 
3
7
,

 
 
2
8
5
,

 
 
7
6
,

 
 
4
1
,

 
 
5
9
2
,

 
 
4
,

 
 
1
9
3
,

 
 
3
5
,

 
 
1
4
1
,

 
 
3
5
2
,

 
 
7
7
,

 
 
6
9
,

 
 
3
0
8
3
2
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
4
7
,

 
 
1
2
,

 
 
1
1
,

 
 
7
8
,

 
 
1
1
,

 
 
4
3
,

 
 
1
4
,

 
 
1
3
9
1
,

 
 
2
,

 
 
6
8
,

 
 
2
3
,

 
 
5
2
,

 
 
4
3
,

 
 
1
9
,

 
 
2
,

 
 
1
5
6
2
,

 
 
9
,

 
 
6
8
,

 
 
7
7
,

 
 
1
2
0
,

 
 
1
6
0
7
5
2
,

 
 
2
4
,

 
 
2
8
8
,

 
 
3
5
5
,

 
 
1
0
,

 
 
1
,

 
 
6
4
7
9
,

 
 
1
6
3
,

 
 
3
3
1
,

 
 
9
3
,

 
 
2
1
0
8
7
,

 
 
2
5
,

 
 
5
2
,

 
 
2
4
,

 
 
4
7
7
0
,

 
 
3
0
8
3
2
,

 
 
1
7
3
3
,

 
 
2
8
6
2
,

 
 
1
4
9
,

 
 
2
5
,

 
 
4
2
0
,

 
 
5
9
0
,

 
 
5
,

 
 
2
1
8
,

 
 
5
2
,

 
 
9
9
,

 
 
2
0
6
6
3
,

 
 
1
,

 
 
2
4
4
,

 
 
1
,

 
 
4
4
2
,

 
 
1
5
6
8
6
,

 
 
3
,

 
 
6
8
,

 
 
1
6
0
7
5
3
,

 
 
2
1
0
8
7
,

 
 
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
3
8
4
,

 
 
1
0
1
,

 
 
3
7
5
,

 
 
1
1
,

 
 
8
,

 
 
3
0
5
,

 
 
1
2
,

 
 
2
8
,

 
 
2
5
,

 
 
8
2
9
,

 
 
2
6
,

 
 
1
4
,

 
 
1
2
,

 
 
3
7
,

 
 
4
4
,

 
 
4
1
,

 
 
8
,

 
 
1
2
8
,

 
 
5
8
,

 
 
7
6
,

 
 
4
1
,

 
 
7
7
,

 
 
4
5
6
,

 
 
1
5
6
8
6
,

 
 
1
2
8
,

 
 
1
2
8
,

 
 
5
8
,

 
 
5
,

 
 
4
9
,

 
 
6
9
,

 
 
6
,

 
 
1
0
7
2
,

 
 
1
7
5
8
,

 
 
4
8
,

 
 
3
0
8
3
2
,

 
 
2
,

 
 
1
6
0
7
5
4
,

 
 
2
8
,

 
 
1
,

 
 
7
5
,

 
 
1
,

 
 
1
0
1
0
,

 
 
3
,

 
 
2
8
,

 
 
4
5
,

 
 
1
5
6
,

 
 
2
2
7
,

 
 
1
2
5
,

 
 
1
8
,

 
 
5
5
,

 
 
3
2
4
2
,

 
 
3
,

 
 
1
,

 
 
3
9
4
,

 
 
4
5
6
,

 
 
1
8
6
2
,

 
 
2
1
0
8
7
,

 
 
3
3
,

 
 
1
6
0
7
5
5
,

 
 
7
9
8
,

 
 
7
0
,

 
 
5
8
0
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
2
1
3
,

 
 
3
7
,

 
 
1
2
7
,

 
 
7
,

 
 
1
9
,

 
 
4
4
,

 
 
2
7
8
0
,

 
 
2
,

 
 
3
5
0
,

 
 
6
4
,

 
 
5
5
,

 
 
5
8
]
,

 
[
5
0
5
,
 
6
6
,
 
3
9
4
8
,
 
1
1
2
,
 
6
9
4
2
,
 
1
0
1
0
2
,
 
2
6
,
 
1
5
3
,
 
3
9
1
,
 
1
0
,
 
2
5
1
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
1
5
4
5
,

 
 
2
8
,

 
 
1
2
4
,

 
 
2
1
,

 
 
1
8
7
3
,

 
 
1
7
4
,

 
 
1
8
7
3
,

 
 
1
2
4
,

 
 
1
8
,

 
 
5
5
3
7
,

 
 
2
,

 
 
2
8
,

 
 
6
9
,

 
 
5
1
,

 
 
1
9
,

 
 
4
,

 
 
5
0
3
1
,

 
 
2
,

 
 
4
1
9
7
,

 
 
1
0
1
0
,

 
 
2
2
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
4
1
2
8
,

 
 
2
3
,

 
 
5
0
,

 
 
4
3
9
,

 
 
1
1
,

 
 
2
,

 
 
2
7
,

 
 
4
8
1
,

 
 
9
8
6
,

 
 
2
9
,

 
 
2
2
,

 
 
1
,

 
 
2
9
,

 
 
4
2
,

 
 
5
7
,

 
 
4
6
0
5
,

 
 
5
0
,

 
 
3
9
8
,

 
 
1
1
,

 
 
2
,

 
 
1
,

 
 
2
6
2
,

 
 
1
5
7
0
,

 
 
4
0
7
,

 
 
2
2
,

 
 
6
,

 
 
2
1
1
,

 
 
9
,

 
 
1
,

 
 
1
7
4
,

 
 
3
,

 
 
4
,

 
 
2
9
,

 
 
8
,

 
 
1
1
3
5
,

 
 
5
0
,

 
 
7
9
,

 
 
1
,

 
 
2
9
,

 
 
5
,

 
 
1
5
4
5
,

 
 
1
1
,

 
 
2
1
,

 
 
4
8
1
,

 
 
1
7
4
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
2
2
6
,

 
 
1
2
,

 
 
1
,

 
 
2
9
,

 
 
5
0
,

 
 
6
3
,

 
 
1
,

 
 
1
1
9
,

 
 
2
3
0
,

 
 
1
2
,

 
 
7
4
,

 
 
2
,

 
 
3
8
2
6
,

 
 
9
5
,

 
 
1
2
,

 
 
8
2
1
,

 
 
2
,

 
 
2
8
,

 
 
4
6
]
,

 
[
3
8
,
 
4
,
 
6
3
5
2
,
 
7
2
6
,
 
3
,
 
8
8
0
,
 
1
4
1
,
 
7
4
2
1
,
 
1
2
,
 
1
0
8
9
,
 
1
9
1
]
,

 
[
8
4
4
,

 
 
2
1
6
,

 
 
1
8
5
,

 
 
6
9
,

 
 
8
0
,

 
 
7
,

 
 
1
3
1
,

 
 
1
4
1
,

 
 
3
0
3
2
,

 
 
7
,

 
 
1
1
3
8
5
,

 
 
5
4
5
,

 
 
1
7
,

 
 
1
0
7
3
,

 
 
5
6
5
,

 
 
7
,

 
 
1
0
3
,

 
 
1
5
5
4
,

 
 
9
2
,

 
 
6
0
4
,

 
 
5
6
6
9
,

 
 
5
7
9
,

 
 
2
,

 
 
1
3
,

 
 
1
,

 
 
6
9
8
3
8
,

 
 
1
4
1
0
,

 
 
2
,

 
 
8
8
1
,

 
 
1
0
,

 
 
4
0
,

 
 
8
7
8
,

 
 
2
5
1
5
2
,

 
 
5
7
9
,

 
 
2
,

 
 
1
3
,

 
 
5
1
,

 
 
9
9
,

 
 
3
3
,

 
 
3
0
8
,

 
 
3
6
3
,

 
 
2
2
1
9
,

 
 
1
3
7
,

 
 
7
7
,

 
 
5
7
,

 
 
5
5
9
,

 
 
2
,

 
 
2
0
6
8
,

 
 
1
4
9
,

 
 
3
6
,

 
 
3
1
3
,

 
 
3
6
,

 
 
5
3
,

 
 
3
4
,

 
 
1
2
2
,

 
 
2
,

 
 
2
0
6
8
,

 
 
5
8
,

 
 
1
7
3
1
,

 
 
9
1
9
,

 
 
1
6
2
,

 
 
1
1
1
2
]
,

 
[
1
8
7
,

 
 
4
1
3
,

 
 
7
,

 
 
1
8
7
,

 
 
2
2
7
7
,

 
 
8
9
5
,

 
 
3
,

 
 
5
5
8
3
,

 
 
6
9
8
3
9
,

 
 
5
,

 
 
4
1
3
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
9
4
1
,

 
 
2
,

 
 
8
2
1
4
,

 
 
1
5
1
9
,

 
 
2
3
1
7
4
,

 
 
3
8
5
,

 
 
2
9
1
6
,

 
 
2
5
,

 
 
9
3
1
,

 
 
1
,

 
 
4
5
1
,

 
 
4
2
,

 
 
5
7
,

 
 
1
8
7
,

 
 
3
1
,

 
 
1
,

 
 
2
3
,

 
 
6
9
8
3
9
,

 
 
9
0
,

 
 
2
3
5
,

 
 
2
,

 
 
5
2
5
0
,

 
 
1
2
8
1
,

 
 
5
8
7
0
,

 
 
3
1
,

 
 
9
7
9
8
,

 
 
1
2
3
9
5
,

 
 
6
8
,

 
 
2
7
7
9
,

 
 
2
3
0
,

 
 
2
,

 
 
4
2
3
7
5
,

 
 
3
0
4
,

 
 
7
7
7
7
,

 
 
2
5
,

 
 
2
7
6
9
2
,

 
 
3
4
8
7
,

 
 
2
7
3
5
,

 
 
6
8
7
,

 
 
1
0
,

 
 
1
1
2
,

 
 
9
1
5
,

 
 
4
,

 
 
1
0
8
,

 
 
3
,

 
 
1
3
0
8
1
,

 
 
2
5
4
9
,

 
 
5
,

 
 
4
,

 
 
9
2
6
,

 
 
3
,

 
 
8
0
4
,

 
 
6
2
8
3
,

 
 
7
4
8
,

 
 
5
2
,

 
 
2
5
9
3
,

 
 
1
0
,

 
 
7
4
8
,

 
 
4
9
,

 
 
3
6
,

 
 
3
1
3
,

 
 
1
7
,

 
 
1
1
,

 
 
2
4
,

 
 
6
7
8
3
,

 
 
1
2
,

 
 
1
5
4
,

 
 
2
,

 
 
2
0
0
1
,

 
 
6
8
,

 
 
1
7
0
,

 
 
7
6
5
,

 
 
9
,

 
 
7
4
8
,

 
 
2
4
,

 
 
4
,

 
 
9
5
7
8
,

 
 
3
2
5
7
,

 
 
5
0
9
6
,

 
 
5
4
1
,

 
 
1
0
,

 
 
4
,

 
 
1
2
8
,

 
 
1
8
2
4
,

 
 
1
7
8
0
,

 
 
1
0
,

 
 
1
4
0
4
3
,

 
 
5
2
,

 
 
2
5
9
3
,

 
 
1
0
,

 
 
5
2
3
,

 
 
1
8
7
9
,

 
 
5
,

 
 
1
4
,

 
 
1
0
,

 
 
6
1
4
,

 
 
8
2
4
,

 
 
1
0
,

 
 
1
6
0
7
5
6
,

 
 
5
,

 
 
6
0
0
1
,

 
 
5
9
0
,

 
 
2
6
,

 
 
1
4
,

 
 
1
0
,

 
 
3
6
4
6
,

 
 
2
3
7
0
,

 
 
2
5
,

 
 
6
8
5
2
,

 
 
1
7
,

 
 
4
7
,

 
 
1
8
4
,

 
 
2
2
0
,

 
 
1
0
,

 
 
1
,

 
 
1
5
4
7
9
,

 
 
9
0
7
,

 
 
2
6
,

 
 
1
4
,

 
 
1
0
,

 
 
3
3
6
9
0
,

 
 
2
5
,

 
 
7
2
6
1
,

 
 
3
2
,

 
 
4
,

 
 
1
8
5
3
,

 
 
1
6
4
6
,

 
 
5
2
,

 
 
1
3
1
,

 
 
3
,

 
 
6
8
,

 
 
1
6
1
4
7
,

 
 
1
0
,

 
 
1
,

 
 
1
5
9
7
,

 
 
7
1
7
1
,

 
 
3
,

 
 
6
1
4
,

 
 
8
2
4
,

 
 
4
,

 
 
1
2
6
7
,

 
 
1
2
,

 
 
6
8
,

 
 
6
1
4
,

 
 
1
3
3
9
,

 
 
5
,

 
 
7
7
2
,

 
 
2
7
6
9
3
,

 
 
8
5
1
,

 
 
1
5
,

 
 
2
6
2
7
,

 
 
5
2
,

 
 
3
4
8
4
,

 
 
7
6
,

 
 
6
8
,

 
 
2
5
4
9
,

 
 
2
,

 
 
1
0
4
,

 
 
4
9
4
5
4
,

 
 
2
9
0
6
,

 
 
3
2
5
7
,

 
 
5
0
9
6
,

 
 
1
,

 
 
6
0
9
2
,

 
 
1
0
3
1
,

 
 
4
2
8
,

 
 
3
7
9
,

 
 
8
5
0
,

 
 
1
4
0
4
3
,

 
 
5
0
1
,

 
 
2
4
6
7
,

 
 
2
6
,

 
 
1
0
,

 
 
4
,

 
 
1
0
2
,

 
 
5
0
0
7
,

 
 
8
5
,

 
 
1
1
,

 
 
4
0
7
4
,

 
 
1
0
1
,

 
 
3
,

 
 
6
9
8
3
9
,

 
 
9
,

 
 
1
1
0
4
,

 
 
3
3
2
,

 
 
9
,

 
 
5
2
,

 
 
1
3
1
,

 
 
1
0
8
5
,

 
 
7
6
,

 
 
3
,

 
 
6
8
,

 
 
8
4
2
1
,

 
 
3
4
5
,

 
 
3
0
4
,

 
 
1
2
,

 
 
8
2
9
,

 
 
2
5
,

 
 
6
8
,

 
 
1
0
4
3
,

 
 
8
0
9
,

 
 
5
5
6
,

 
 
6
8
,

 
 
1
1
7
4
7
,

 
 
5
2
,

 
 
1
6
8
9
9
,

 
 
1
0
,

 
 
4
,

 
 
1
6
3
9
8
,

 
 
9
9
8
,

 
 
1
7
9
6
,

 
 
6
8
,

 
 
9
6
9
3
,

 
 
6
8
,

 
 
7
7
,

 
 
3
2
1
8
1
,

 
 
3
7
9
3
,

 
 
1
0
,

 
 
5
5
3
,

 
 
9
5
1
6
,

 
 
5
,

 
 
1
6
0
9
,

 
 
2
7
6
9
4
,

 
 
2
5
,

 
 
1
1
4
7
0
,

 
 
2
3
8
,

 
 
1
9
9
,

 
 
1
2
,

 
 
1
0
8
5
,

 
 
2
5
6
0
,

 
 
4
0
2
,

 
 
9
5
3
,

 
 
5
5
8
,

 
 
2
7
6
9
5
,

 
 
5
2
,

 
 
8
,

 
 
2
7
,

 
 
2
0
6
6
4
,

 
 
4
0
0
,

 
 
1
6
0
7
5
7
,

 
 
3
2
,

 
 
2
3
8
6
,

 
 
1
9
1
7
,

 
 
1
6
3
9
9
,

 
 
2
5
,

 
 
2
2
6
,

 
 
3
,

 
 
9
0
9
8
,

 
 
5
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
3
7
5
3
,

 
 
7
6
,

 
 
1
3
5
,

 
 
1
6
0
7
5
8
,

 
 
1
8
3
8
3
,

 
 
3
,

 
 
4
7
7
,

 
 
2
5
,

 
 
4
1
8
7
,

 
 
4
,

 
 
1
1
5
,

 
 
1
4
5
2
,

 
 
3
7
5
4
,

 
 
5
4
1
,

 
 
6
8
,

 
 
2
1
0
8
,

 
 
3
2
5
7
,

 
 
5
1
2
,

 
 
1
0
2
1
,

 
 
2
,

 
 
7
6
2
9
,

 
 
5
0
7
,

 
 
1
0
2
1
,

 
 
9
5
3
,

 
 
8
1
6
,

 
 
2
1
5
8
8
,

 
 
7
6
2
9
,

 
 
5
0
7
,

 
 
1
0
2
1
,

 
 
2
5
2
4
,

 
 
1
8
4
1
,

 
 
3
,

 
 
3
1
2
9
,

 
 
1
6
0
7
5
9
,

 
 
2
7
7
9
,

 
 
2
3
0
,

 
 
2
4
,

 
 
4
6
2
,

 
 
1
3
0
8
2
,

 
 
9
3
,

 
 
1
5
4
8
0
,

 
 
1
9
9
9
,

 
 
2
5
1
3
9
,

 
 
9
9
,

 
 
7
2
2
2
,

 
 
9
,

 
 
5
2
,

 
 
4
3
,

 
 
1
3
0
8
3
,

 
 
9
8
7
,

 
 
1
1
8
8
,

 
 
4
8
1
3
,

 
 
5
,

 
 
4
2
4
4
,

 
 
1
,

 
 
5
4
6
,

 
 
1
1
1
5
,

 
 
1
,

 
 
6
0
8
0
7
,

 
 
3
,

 
 
5
4
3
4
6
,

 
 
1
2
2
8
5
,

 
 
2
6
,

 
 
2
0
8
,

 
 
6
9
8
3
9
,

 
 
4
7
2
2
,

 
 
3
5
3
9
4
,

 
 
1
5
,

 
 
1
,

 
 
1
2
6
7
,

 
 
3
,

 
 
2
7
7
4
,

 
 
1
2
,

 
 
1
,

 
 
1
3
2
,

 
 
2
2
3
,

 
 
5
2
,

 
 
9
0
,

 
 
2
3
5
,

 
 
2
,

 
 
1
9
8
2
3
,

 
 
1
0
,

 
 
1
,

 
 
2
5
9
5
0
,

 
 
6
2
5
,

 
 
9
8
5
,

 
 
3
,

 
 
2
1
9
9
,

 
 
3
2
6
9
,

 
 
1
5
,

 
 
2
2
1
1
,

 
 
6
6
7
,

 
 
2
1
,

 
 
1
,

 
 
6
0
4
,

 
 
1
6
1
4
8
,

 
 
3
2
9
6
]
,

 
[
6
,
 
1
7
4
4
,
 
1
8
,
 
2
7
,
 
1
2
6
2
7
,
 
5
,
 
4
,
 
1
1
3
8
6
]
,

 
[
8
3
6
4
6
,

 
 
1
6
2
,

 
 
1
1
,

 
 
2
8
5
,

 
 
5
4
3
3
,

 
 
1
6
0
,

 
 
1
1
,

 
 
4
9
9
5
,

 
 
2
,

 
 
4
,

 
 
1
0
0
5
,

 
 
6
2
5
,

 
 
1
4
,

 
 
4
,

 
 
8
0
9
,

 
 
2
2
2
,

 
 
8
3
6
4
6
,

 
 
1
9
7
0
,

 
 
4
1
0
,

 
 
2
,

 
 
3
4
3
6
,

 
 
1
,

 
 
5
4
3
4
7
,

 
 
2
,

 
 
1
0
3
3
,

 
 
6
1
7
,

 
 
1
,

 
 
1
1
8
8
,

 
 
1
0
,

 
 
2
1
4
,

 
 
8
,

 
 
2
3
3
3
,

 
 
4
7
6
9
,

 
 
8
,

 
 
1
,

 
 
6
6
0
,

 
 
3
9
7
0
,

 
 
4
7
6
9
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
3
9
8
,

 
 
2
0
,

 
 
3
3
8
1
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
3
4
,

 
 
1
1
,

 
 
1
2
7
,

 
 
2
5
,

 
 
7
,

 
 
4
5
,

 
 
5
7
6
,

 
 
6
,

 
 
1
2
,

 
 
2
1
7
,

 
 
6
6
,

 
 
5
0
,

 
 
5
9
,

 
 
1
4
8
3
,

 
 
3
7
,

 
 
3
1
5
7
,

 
 
9
8
9
,

 
 
2
0
2
1
0
,

 
 
3
8
6
7
,

 
 
5
0
5
0
,

 
 
5
9
5
3
,

 
 
4
2
0
8
]
,

 
[
2
1
4
,

 
 
1
5
,

 
 
4
4
1
,

 
 
7
1
7
,

 
 
7
2
,

 
 
2
8
0
,

 
 
2
2
,

 
 
7
,

 
 
1
9
2
9
,

 
 
2
0
,

 
 
2
1
4
,

 
 
7
,

 
 
5
9
,

 
 
1
7
9
5
,

 
 
1
2
8
,

 
 
7
7
9
,

 
 
2
,

 
 
9
,

 
 
2
9
,

 
 
1
0
,

 
 
6
3
9
,

 
 
2
,

 
 
2
0
,

 
 
2
1
4
,

 
 
2
7
8
,

 
 
3
7
,

 
 
4
2
6
,

 
 
3
2
,

 
 
4
0
5
2
,

 
 
3
0
,

 
 
8
2
4
4
,

 
 
9
7
4
9
,

 
 
1
,

 
 
7
9
3
,

 
 
3
,

 
 
2
8
,

 
 
2
0
5
,

 
 
8
,

 
 
2
,

 
 
1
5
4
8
1
,

 
 
4
4
3
9
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
2
0
9
,

 
 
1
,

 
 
5
1
6
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
7
,

 
 
7
0
2
,

 
 
3
5
1
,

 
 
8
6
1
,

 
 
1
0
,

 
 
4
4
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
1
1
3
,

 
 
6
2
1
,

 
 
2
8
6
,

 
 
9
,

 
 
5
3
,

 
 
2
6
7
6
0
,

 
 
8
7
8
9
,

 
 
6
8
4
,

 
 
2
6
1
,

 
 
1
0
5
,

 
 
2
,

 
 
7
2
2
6
,

 
 
3
3
,

 
 
2
9
5
2
,

 
 
2
9
0
6
,

 
 
4
3
6
2
,

 
 
1
4
9
,

 
 
1
1
0
7
,

 
 
5
,

 
 
4
5
8
4
,

 
 
2
9
0
6
,

 
 
3
1
,

 
 
9
2
,

 
 
2
2
0
6
,

 
 
5
,

 
 
5
9
8
7
,

 
 
8
,

 
 
1
3
2
,

 
 
6
7
4
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
5
3
,

 
 
3
9
,

 
 
8
7
8
9
,

 
 
1
0
5
,

 
 
3
6
,

 
 
2
5
0
,

 
 
1
7
,

 
 
5
3
,

 
 
5
9
,

 
 
7
2
2
6
,

 
 
3
3
,

 
 
1
1
5
,

 
 
1
7
4
0
,

 
 
1
8
3
,

 
 
2
5
4
9
,

 
 
2
,

 
 
5
8
4
,

 
 
8
,

 
 
9
,

 
 
2
4
4
6
7
,

 
 
1
0
7
2
3
,

 
 
2
4
4
8
,

 
 
1
,

 
 
5
8
,

 
 
3
5
1
4
,

 
 
5
3
,

 
 
1
8
,

 
 
1
,

 
 
3
8
6
0
,

 
 
1
1
,

 
 
8
,

 
 
2
,

 
 
1
6
,

 
 
8
8
7
,

 
 
4
0
4
,

 
 
3
2
2
,

 
 
2
,

 
 
8
7
7
,

 
 
1
,

 
 
1
6
6
4
7
,

 
 
5
,

 
 
2
0
5
,

 
 
4
2
1
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
3
6
,

 
 
5
3
,

 
 
3
9
,

 
 
8
2
,

 
 
1
1
,

 
 
1
7
,

 
 
4
,

 
 
1
2
0
,

 
 
1
,

 
 
1
9
4
2
5
,

 
 
3
4
1
,

 
 
9
6
,

 
 
2
2
,

 
 
1
5
3
0
,

 
 
2
5
9
2
,

 
 
8
7
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
0
,

 
 
4
,

 
 
1
4
3
5
,

 
 
2
8
8
9
,

 
 
1
7
,

 
 
4
,

 
 
9
1
3
,

 
 
1
2
0
,

 
 
3
5
,

 
 
1
9
4
2
5
,

 
 
7
2
,

 
 
1
4
,

 
 
1
5
1
7
,

 
 
3
0
5
,

 
 
2
1
,

 
 
1
3
,

 
 
4
4
7
,

 
 
2
,

 
 
9
7
,

 
 
2
6
7
6
1
,

 
 
1
5
,

 
 
3
8
,

 
 
4
3
,

 
 
1
6
,

 
 
3
7
4
,

 
 
1
9
7
,

 
 
7
,

 
 
4
3
,

 
 
1
1
7
,

 
 
9
,

 
 
2
0
,

 
 
7
7
4
,

 
 
2
5
3
,

 
 
5
5
7
,

 
 
1
2
2
5
,

 
 
1
,

 
 
1
0
6
,

 
 
1
8
,

 
 
1
8
2
1
,

 
 
5
,

 
 
4
4
,

 
 
2
9
9
,

 
 
2
9
0
6
,

 
 
1
8
,

 
 
1
3
1
,

 
 
1
,

 
 
4
2
1
,

 
 
4
5
5
5
8
,

 
 
2
6
7
,

 
 
8
,

 
 
1
7
6
1
,

 
 
2
,

 
 
3
7
,

 
 
2
6
,

 
 
6
,

 
 
5
6
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
4
4
3
9
,

 
 
3
8
,

 
 
6
,

 
 
1
3
6
,

 
 
1
0
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
2
1
0
6
,

 
 
3
0
,

 
 
3
2
7
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
4
6
2
,

 
 
5
3
,

 
 
1
1
7
,

 
 
3
5
,

 
 
1
,

 
 
2
5
7
,

 
 
1
,

 
 
2
0
1
,

 
 
5
1
8
,

 
 
8
3
,

 
 
1
8
,

 
 
1
4
,

 
 
3
7
1
1
,

 
 
2
0
8
,

 
 
5
3
,

 
 
2
4
5
,

 
 
3
1
4
,

 
 
1
7
5
,

 
 
1
7
1
2
,

 
 
2
4
4
6
9
,

 
 
5
,

 
 
4
0
,

 
 
5
3
,

 
 
8
0
7
,

 
 
2
0
6
6
5
,

 
 
1
,

 
 
2
4
4
6
9
,

 
 
6
2
1
,

 
 
1
2
8
4
,

 
 
9
2
,

 
 
2
0
1
,

 
 
2
3
5
3
,

 
 
2
2
6
0
,

 
 
8
,

 
 
4
,

 
 
2
2
3
,

 
 
3
,

 
 
6
8
1
,

 
 
2
6
,

 
 
6
,

 
 
5
6
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
4
4
3
9
,

 
 
3
8
,

 
 
6
,

 
 
1
3
6
,

 
 
1
0
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
4
1
,

 
 
4
4
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
7
7
,

 
 
4
,

 
 
5
2
,

 
 
1
6
7
,

 
 
1
8
9
,

 
 
1
6
7
,

 
 
1
3
3
5
,

 
 
6
6
7
7
,

 
 
3
2
6
,

 
 
1
1
,

 
 
8
,

 
 
2
4
1
9
,

 
 
1
,

 
 
4
2
1
,

 
 
1
6
0
7
6
0
,

 
 
2
4
,

 
 
1
6
9
0
0
,

 
 
3
2
,

 
 
1
9
4
2
5
,

 
 
1
1
,

 
 
2
8
5
,

 
 
3
8
1
,

 
 
2
2
,

 
 
1
8
9
,

 
 
9
0
,

 
 
5
,

 
 
6
1
,

 
 
4
0
4
8
,

 
 
3
2
9
,

 
 
1
,

 
 
1
5
4
8
,

 
 
5
,

 
 
1
,

 
 
3
3
4
,

 
 
1
8
,

 
 
1
4
,

 
 
4
6
7
,

 
 
1
1
,

 
 
2
4
,

 
 
1
,

 
 
4
5
6
9
,

 
 
8
4
6
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
5
,

 
 
4
0
,

 
 
1
,

 
 
2
0
4
9
,

 
 
6
4
,

 
 
8
6
,

 
 
6
2
6
,

 
 
1
4
9
9
,

 
 
1
1
2
,

 
 
2
7
6
8
,

 
 
7
,

 
 
5
9
,

 
 
6
3
,

 
 
7
4
,

 
 
9
,

 
 
3
9
,

 
 
1
6
,

 
 
2
0
0
7
,

 
 
1
9
4
2
5
,

 
 
7
2
,

 
 
2
8
0
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
9
4
,

 
 
1
5
7
,

 
 
2
,

 
 
6
,

 
 
3
5
,

 
 
1
,

 
 
9
4
1
3
,

 
 
5
3
6
,

 
 
2
1
4
4
,

 
 
1
0
1
7
,

 
 
2
6
,

 
 
1
3
7
,

 
 
5
7
,

 
 
1
5
3
0
,

 
 
2
1
5
8
9
,

 
 
3
3
,

 
 
1
4
2
,

 
 
8
7
3
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
2
0
1
,

 
 
8
9
,

 
 
9
3
,

 
 
8
0
,

 
 
7
,

 
 
1
1
4
,

 
 
6
8
7
,

 
 
1
1
,

 
 
9
5
,

 
 
2
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
1
2
9
1
,

 
 
1
5
,

 
 
1
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
9
1
3
,

 
 
2
0
5
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
2
,

 
 
1
0
1
8
,

 
 
1
,

 
 
2
2
1
,

 
 
1
0
6
,

 
 
5
,

 
 
6
9
3
,

 
 
8
8
,

 
 
1
0
,

 
 
4
,

 
 
1
1
0
,

 
 
9
,

 
 
1
8
1
,

 
 
3
6
4
,

 
 
4
8
,

 
 
4
,

 
 
9
0
4
3
,

 
 
6
6
5
5
,

 
 
8
7
3
7
,

 
 
1
8
,

 
 
2
9
8
,

 
 
4
,

 
 
9
8
,

 
 
7
9
3
,

 
 
5
,

 
 
4
1
,

 
 
5
6
,

 
 
1
6
,

 
 
3
0
5
,

 
 
2
0
5
,

 
 
1
5
,

 
 
3
0
4
,

 
 
6
5
4
,

 
 
2
,

 
 
2
3
0
2
,

 
 
9
,

 
 
1
6
3
,

 
 
1
3
7
5
4
,

 
 
1
9
8
2
4
,

 
 
8
9
4
,

 
 
6
7
0
,

 
 
7
2
,

 
 
1
3
2
1
,

 
 
2
,

 
 
1
2
1
,

 
 
5
,

 
 
2
8
9
,

 
 
5
,

 
 
9
7
,

 
 
1
,

 
 
2
3
,

 
 
2
3
1
7
5
,

 
 
5
,

 
 
7
,

 
 
5
9
,

 
 
2
7
6
,

 
 
2
,

 
 
1
0
7
5
,

 
 
3
3
6
9
1
,

 
 
1
0
,

 
 
1
,

 
 
5
1
5
,

 
 
9
9
5
,

 
 
2
6
,

 
 
4
1
,

 
 
2
4
,

 
 
4
,

 
 
3
4
8
,

 
 
2
,

 
 
2
2
6
3
8
,

 
 
1
0
,

 
 
4
1
,

 
 
9
5
,

 
 
1
2
,

 
 
1
,

 
 
1
9
3
,

 
 
7
,

 
 
6
8
5
,

 
 
1
1
,

 
 
7
,

 
 
4
3
,

 
 
1
1
7
,

 
 
1
0
4
2
6
,

 
 
3
5
8
,

 
 
1
3
7
,

 
 
3
1
6
,

 
 
1
7
2
,

 
 
5
4
2
,

 
 
8
,

 
 
2
7
,

 
 
7
6
,

 
 
5
,

 
 
7
6
,

 
 
9
9
9
6
,

 
 
1
3
7
,

 
 
1
9
9
,

 
 
2
0
7
,

 
 
5
5
,

 
 
1
1
1
,

 
 
2
2
8
,

 
 
2
5
,

 
 
3
8
5
,

 
 
7
1
,

 
 
6
9
,

 
 
5
7
2
,

 
 
5
7
,

 
 
5
5
9
,

 
 
2
,

 
 
2
0
2
8
,

 
 
3
7
,

 
 
5
,

 
 
4
5
8
,

 
 
3
7
,

 
 
5
4
2
,

 
 
1
5
,

 
 
2
8
,

 
 
1
5
1
0
,

 
 
5
,

 
 
1
7
7
,

 
 
4
2
9
5
,

 
 
1
3
7
,

 
 
1
6
7
0
,

 
 
1
7
2
,

 
 
5
,

 
 
1
6
0
7
6
1
,

 
 
3
,

 
 
5
9
5
4
,

 
 
1
,

 
 
1
3
8
3
,

 
 
1
2
,

 
 
1
0
6
6
0
7
,

 
 
5
,

 
 
1
0
6
6
0
8
,

 
 
5
,

 
 
5
1
,

 
 
1
9
,

 
 
9
,

 
 
2
8
5
,

 
 
3
5
3
9
5
,

 
 
3
2
,

 
 
4
,

 
 
2
5
0
,

 
 
6
3
8
8
,

 
 
7
2
,

 
 
1
2
6
,

 
 
1
6
4
0
0
,

 
 
3
,

 
 
1
1
2
,

 
 
6
1
9
,

 
 
1
4
8
,

 
 
1
3
,

 
 
1
3
,

 
 
8
,

 
 
6
6
5
5
,

 
 
7
2
3
,

 
 
2
0
8
,

 
 
1
8
0
7
3
,

 
 
1
9
5
,

 
 
3
7
3
2
,

 
 
1
9
8
1
,

 
 
6
0
7
3
,

 
 
2
1
,

 
 
4
,

 
 
4
2
6
0
,

 
 
2
5
5
4
,

 
 
4
7
5
2
,

 
 
1
,

 
 
1
8
1
3
,

 
 
2
4
8
,

 
 
3
7
,

 
 
1
8
,

 
 
3
2
5
,

 
 
5
,

 
 
1
2
7
3
1
,

 
 
3
2
,

 
 
1
,

 
 
1
9
4
1
,

 
 
9
0
9
9
,

 
 
3
7
,

 
 
6
2
4
,

 
 
9
7
,

 
 
3
0
,

 
 
6
9
8
,

 
 
5
5
,

 
 
4
6
2
,

 
 
8
7
0
,

 
 
1
1
0
4
,

 
 
1
6
6
1
,

 
 
2
,

 
 
1
6
,

 
 
3
3
6
9
2
,

 
 
1
5
,

 
 
3
2
,

 
 
4
,

 
 
5
4
6
7
,

 
 
7
1
,

 
 
1
,

 
 
7
8
6
,

 
 
2
7
5
3
,

 
 
3
,

 
 
2
6
7
6
2
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
9
9
9
6
,

 
 
7
,

 
 
9
4
,

 
 
1
1
6
5
7
,

 
 
2
3
9
0
,

 
 
3
,

 
 
9
1
,

 
 
3
1
6
,

 
 
4
,

 
 
1
5
3
6
,

 
 
2
5
,

 
 
2
2
3
,

 
 
3
,

 
 
4
,

 
 
6
6
5
5
,

 
 
2
5
,

 
 
3
0
7
6
,

 
 
2
5
,

 
 
4
3
8
,

 
 
1
5
3
6
,

 
 
2
5
,

 
 
4
,

 
 
5
7
1
,

 
 
5
5
4
,

 
 
3
9
0
4
,

 
 
2
5
,

 
 
4
,

 
 
1
3
3
5
,

 
 
2
0
6
,

 
 
2
2
1
1
1
,

 
 
2
5
,

 
 
6
1
,

 
 
2
1
8
,

 
 
7
,

 
 
1
0
3
,

 
 
1
4
5
,

 
 
3
3
,

 
 
2
2
,

 
 
7
,

 
 
5
7
7
,

 
 
2
,

 
 
8
3
6
4
7
,

 
 
4
9
9
,

 
 
6
,

 
 
6
6
,

 
 
1
3
1
,

 
 
4
,

 
 
6
2
8
3
,

 
 
2
0
6
,

 
 
3
5
,

 
 
3
7
,

 
 
9
1
,

 
 
3
5
3
9
6
,

 
 
6
8
9
,

 
 
5
,

 
 
1
8
5
4
,

 
 
1
0
2
5
,

 
 
1
,

 
 
2
7
0
,

 
 
2
2
,

 
 
1
0
,

 
 
1
4
2
0
,

 
 
3
,

 
 
1
1
,

 
 
1
8
1
,

 
 
9
7
,

 
 
1
1
,

 
 
5
5
,

 
 
4
6
2
,

 
 
3
,

 
 
2
7
,

 
 
2
0
2
8
,

 
 
1
3
7
,

 
 
7
0
5
,

 
 
2
,

 
 
1
6
,

 
 
3
3
3
6
,

 
 
2
,

 
 
6
,

 
 
5
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
2
6
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
6
3
9
,

 
 
5
,

 
 
5
0
,

 
 
4
5
4
,

 
 
4
8
,

 
 
2
1
5
9
0
,

 
 
1
8
0
7
3
,

 
 
8
,

 
 
2
0
2
0
5
,

 
 
1
,

 
 
4
1
8
,

 
 
2
1
5
9
0
,

 
 
1
,

 
 
1
2
1
7
8
,

 
 
2
5
1
5
3
,

 
 
6
2
,

 
 
2
8
3
4
,

 
 
1
0
,

 
 
7
9
3
5
,

 
 
7
,

 
 
4
2
3
7
6
,

 
 
2
4
8
,

 
 
1
5
2
7
8
,

 
 
1
5
,

 
 
4
6
,

 
 
7
9
2
,

 
 
1
4
1
,

 
 
1
8
,

 
 
1
4
,

 
 
1
6
1
1
,

 
 
5
0
4
6
,

 
 
5
4
2
,

 
 
1
0
4
2
6
,

 
 
3
5
1
,

 
 
5
0
5
,

 
 
1
0
0
2
,

 
 
2
,

 
 
4
,

 
 
1
6
7
4
,

 
 
1
2
5
,

 
 
6
,

 
 
5
,

 
 
2
1
0
8
8
,

 
 
4
2
3
7
7
,

 
 
3
7
,

 
 
4
,

 
 
1
1
3
8
7
,

 
 
6
,

 
 
5
6
,

 
 
1
2
2
2
,

 
 
3
8
,

 
 
1
8
9
,

 
 
1
6
7
,

 
 
1
0
,

 
 
1
7
0
7
,

 
 
8
0
,

 
 
7
,

 
 
6
3
6
,

 
 
1
4
,

 
 
2
,

 
 
1
6
,

 
 
2
8
5
9
,

 
 
3
,

 
 
9
6
9
4
,

 
 
1
0
,

 
 
5
1
7
9
,

 
 
1
5
,

 
 
2
9
0
,

 
 
1
0
3
6
,

 
 
7
1
,

 
 
7
5
5
,

 
 
6
,

 
 
1
4
9
,

 
 
1
8
,

 
 
1
0
0
3
,

 
 
1
0
6
6
0
7
,

 
 
5
,

 
 
1
0
6
6
0
8
,

 
 
1
8
5
,

 
 
5
7
1
,

 
 
5
6
2
,

 
 
5
,

 
 
3
3
5
8
,

 
 
7
3
,

 
 
3
2
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
6
,

 
 
8
8
1
,

 
 
2
,

 
 
1
7
2
,

 
 
1
2
,

 
 
1
9
8
2
5
,

 
 
1
0
1
,

 
 
1
8
0
7
3
,

 
 
3
9
,

 
 
9
7
,

 
 
1
7
2
,

 
 
1
7
0
,

 
 
1
6
0
7
6
2
,

 
 
3
5
,

 
 
1
1
,

 
 
8
4
,

 
 
2
2
9
,

 
 
5
2
8
9
]
,

 
[
9
6
5
,

 
 
4
5
8
5
,

 
 
1
2
3
3
,

 
 
7
1
,

 
 
5
2
1
,

 
 
1
2
8
,

 
 
7
9
6
,

 
 
7
,

 
 
1
2
2
,

 
 
2
,

 
 
9
7
,

 
 
6
0
,

 
 
2
6
9
5
,

 
 
5
,

 
 
9
9
3
,

 
 
1
0
8
0
5
,

 
 
2
1
8
,

 
 
9
,

 
 
8
7
,

 
 
1
8
0
1
,

 
 
7
3
,

 
 
6
,

 
 
1
8
4
,

 
 
1
0
8
,

 
 
2
,

 
 
7
9
7
,

 
 
1
1
,

 
 
7
6
,

 
 
3
6
,

 
 
2
2
,

 
 
4
1
,

 
 
1
8
,

 
 
2
5
4
,

 
 
2
5
,

 
 
1
4
0
8
,

 
 
7
,

 
 
3
9
,

 
 
1
1
8
,

 
 
1
1
8
6
,

 
 
5
,

 
 
4
5
9
,

 
 
8
8
]
,

 
[
3
1
4
,

 
 
3
7
,

 
 
1
2
5
,

 
 
1
5
,

 
 
2
8
,

 
 
1
1
,

 
 
2
8
6
,

 
 
1
,

 
 
9
0
7
,

 
 
6
8
6
,

 
 
4
2
,

 
 
2
,

 
 
1
6
,

 
 
2
1
3
6
,

 
 
2
0
5
1
,

 
 
1
9
8
1
9
,

 
 
7
8
,

 
 
2
2
9
,

 
 
6
,

 
 
5
2
5
,

 
 
3
0
,

 
 
2
1
4
]
,

 
[
7
8
,

 
 
2
4
,

 
 
1
3
,

 
 
2
3
,

 
 
2
5
0
0
,

 
 
1
2
,

 
 
2
6
1
6
,

 
 
7
,

 
 
2
4
,

 
 
2
5
8
2
,

 
 
9
,

 
 
4
1
,

 
 
4
3
,

 
 
1
6
,

 
 
6
0
,

 
 
4
2
7
,

 
 
6
4
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
1
2
,

 
 
3
9
9
,

 
 
3
9
4
,

 
 
5
,

 
 
1
4
0
,

 
 
1
,

 
 
2
3
,

 
 
5
2
6
,

 
 
9
3
7
,

 
 
2
,

 
 
4
,

 
 
9
5
7
9
,

 
 
5
9
1
,

 
 
3
2
,

 
 
4
,

 
 
2
8
1
,

 
 
1
8
0
,

 
 
1
0
6
8
]
,

 
[
7
5
1
2
,

 
 
2
0
6
6
6
,

 
 
1
6
0
7
6
3
,

 
 
2
1
5
7
,

 
 
2
,

 
 
3
9
8
,

 
 
2
,

 
 
6
8
,

 
 
2
3
8
3
4
,

 
 
3
2
2
,

 
 
2
9
5
8
,

 
 
1
2
3
,

 
 
3
,

 
 
7
5
1
2
,

 
 
5
2
,

 
 
4
2
,

 
 
1
4
,

 
 
3
3
5
8
,

 
 
7
3
,

 
 
6
8
,

 
 
1
4
0
,

 
 
2
1
,

 
 
5
5
,

 
 
4
7
9
,

 
 
7
7
,

 
 
4
2
3
7
8
,

 
 
3
5
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
6
0
,

 
 
1
4
7
1
9
,

 
 
5
,

 
 
3
3
7
9
,

 
 
8
6
3
,

 
 
1
8
9
2
,

 
 
2
9
5
0
,

 
 
1
0
3
9
,

 
 
2
7
9
7
,

 
 
5
3
5
,

 
 
2
1
6
]
,

 
[
5
4
3
4
8
,

 
 
3
9
8
,

 
 
2
2
,

 
 
6
,

 
 
2
3
9
,

 
 
4
8
,

 
 
1
,

 
 
9
3
3
,

 
 
1
6
9
,

 
 
9
2
0
4
,

 
 
7
8
,

 
 
5
9
,

 
 
6
,

 
 
4
9
,

 
 
1
5
2
,

 
 
8
8
,

 
 
2
,

 
 
1
,

 
 
9
0
7
,

 
 
7
,

 
 
1
3
1
,

 
 
6
6
,

 
 
6
,

 
 
3
6
8
,

 
 
1
,

 
 
7
9
,

 
 
1
2
5
,

 
 
7
,

 
 
7
7
,

 
 
1
7
3
,

 
 
1
,

 
 
1
9
6
1
,

 
 
3
,

 
 
5
4
3
4
8
,

 
 
1
1
,

 
 
1
6
7
,

 
 
3
6
,

 
 
1
0
,

 
 
1
,

 
 
7
9
,

 
 
5
1
5
]
,

 
[
1
8
3
,

 
 
8
8
0
,

 
 
2
3
,

 
 
3
3
6
9
3
,

 
 
3
8
,

 
 
2
3
3
5
,

 
 
1
4
3
9
,

 
 
3
,

 
 
3
3
6
9
4
,

 
 
1
8
7
9
,

 
 
1
1
7
,

 
 
3
5
,

 
 
6
3
2
3
,

 
 
3
,

 
 
1
6
0
6
,

 
 
5
,

 
 
6
6
,

 
 
9
,

 
 
6
3
0
6
,

 
 
2
2
8
,

 
 
3
2
,

 
 
1
,

 
 
1
3
5
0
,

 
 
1
5
2
7
9
,

 
 
3
3
6
9
4
,

 
 
1
3
1
7
,

 
 
4
,

 
 
2
7
0
,

 
 
1
2
,

 
 
1
7
2
2
,

 
 
1
0
6
6
0
9
,

 
 
7
7
2
,

 
 
3
2
5
6
,

 
 
9
0
,

 
 
1
4
,

 
 
9
9
9
7
,

 
 
2
5
,

 
 
6
5
1
8
,

 
 
1
3
3
9
,

 
 
3
,

 
 
3
3
6
9
4
,

 
 
1
0
,

 
 
3
9
1
5
,

 
 
3
3
6
9
4
,

 
 
5
1
,

 
 
8
6
,

 
 
3
9
1
5
,

 
 
4
1
8
8
,

 
 
1
7
2
2
,

 
 
6
9
8
4
0
,

 
 
7
1
,

 
 
7
8
,

 
 
1
0
6
6
1
0
,

 
 
1
6
0
7
6
4
,

 
 
1
3
3
6
,

 
 
6
8
,

 
 
1
3
5
6
,

 
 
1
7
,

 
 
5
4
3
4
9
,

 
 
3
0
4
8
,

 
 
1
6
0
7
6
5
,

 
 
4
4
,

 
 
2
8
7
3
,

 
 
4
9
4
5
5
,

 
 
4
3
,

 
 
1
6
,

 
 
8
8
8
3
,

 
 
2
,

 
 
2
5
9
5
1
,

 
 
2
1
,

 
 
3
3
6
9
4
,

 
 
5
,

 
 
1
6
0
7
6
6
,

 
 
7
,

 
 
1
0
3
,

 
 
9
0
3
,

 
 
2
,

 
 
4
0
4
3
,

 
 
1
,

 
 
2
3
,

 
 
2
6
,

 
 
7
1
,

 
 
6
6
1
,

 
 
1
1
1
,

 
 
4
,

 
 
1
7
6
4
,

 
 
3
2
,

 
 
8
9
]
,

 
[
7
,
 
1
9
9
,
 
6
3
7
,
 
1
,
 
1
7
4
,
 
3
,
 
2
0
,
 
2
3
4
,
 
5
0
,
 
3
7
4
,
 
2
0
,
 
6
7
9
,
 
2
3
6
1
]
,

 
[
4
3
9
,
 
4
6
,
 
1
1
0
5
4
,
 
1
2
0
7
7
,
 
8
3
6
4
8
]
,

 
[
7
,

 
 
2
6
3
,

 
 
9
,

 
 
1
1
,

 
 
8
0
7
,

 
 
2
6
,

 
 
3
8
3
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
,

 
 
3
9
0
,

 
 
9
7
,

 
 
2
1
5
9
1
,

 
 
1
0
8
9
4
,

 
 
5
4
2
,

 
 
3
9
5
,

 
 
2
4
1
,

 
 
5
3
,

 
 
3
9
,

 
 
3
4
,

 
 
2
,

 
 
1
7
1
,

 
 
9
,

 
 
2
6
,

 
 
1
7
,

 
 
2
7
2
0
,

 
 
6
7
2
6
,

 
 
6
9
8
,

 
 
7
6
,

 
 
1
9
8
2
3
,

 
 
8
,

 
 
5
8
,

 
 
3
4
2
,

 
 
9
3
,

 
 
6
0
,

 
 
6
1
4
,

 
 
2
1
5
9
1
,

 
 
6
9
,

 
 
3
,

 
 
1
7
2
,

 
 
7
0
6
5
,

 
 
1
7
,

 
 
4
,

 
 
5
4
3
5
0
,

 
 
5
,

 
 
9
,

 
 
1
8
4
2
,

 
 
8
0
1
,

 
 
3
,

 
 
5
6
2
,

 
 
5
4
,

 
 
1
8
9
,

 
 
8
,

 
 
2
6
8
,

 
 
2
,

 
 
8
0
5
,

 
 
3
1
8
5
]
,

 
[
1
2
,

 
 
2
4
0
2
,

 
 
6
5
2
,

 
 
7
9
,

 
 
3
2
6
,

 
 
1
7
,

 
 
7
,

 
 
1
6
7
,

 
 
1
0
,

 
 
3
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
1
,

 
 
3
5
3
,

 
 
1
2
,

 
 
2
4
0
2
,

 
 
6
5
2
,

 
 
8
,

 
 
3
8
5
5
,

 
 
5
,

 
 
1
4
,

 
 
1
1
7
2
,

 
 
1
2
7
1
,

 
 
1
0
,

 
 
1
,

 
 
1
2
0
,

 
 
3
9
9
,

 
 
1
1
,

 
 
8
,

 
 
2
0
0
5
,

 
 
1
1
0
2
,

 
 
1
9
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
5
1
0
1
,

 
 
2
5
2
9
,

 
 
2
,

 
 
7
0
,

 
 
7
8
,

 
 
5
1
,

 
 
9
0
,

 
 
1
1
,

 
 
5
,

 
 
1
7
,

 
 
7
,

 
 
1
6
7
,

 
 
1
0
2
3
,

 
 
3
9
7
0
5
,

 
 
8
,

 
 
1
4
,

 
 
1
7
8
1
,

 
 
1
,

 
 
2
1
2
,

 
 
9
,

 
 
4
0
,

 
 
1
,

 
 
6
1
,

 
 
1
2
9
5
8
,

 
 
9
1
0
0
,

 
 
4
0
4
3
,

 
 
9
2
,

 
 
1
3
4
2
,

 
 
3
6
,

 
 
5
1
,

 
 
5
9
,

 
 
1
8
7
1
7
,

 
 
8
,

 
 
6
9
,

 
 
1
,

 
 
1
9
1
,

 
 
1
6
0
7
6
7
,

 
 
3
9
7
,

 
 
8
8
,

 
 
3
4
,

 
 
1
1
,

 
 
3
8
2
5
,

 
 
1
9
4
2
6
,

 
 
8
,

 
 
2
7
1
,

 
 
7
6
0
,

 
 
7
,

 
 
6
5
0
,

 
 
1
8
5
,

 
 
4
9
,

 
 
4
8
,

 
 
1
9
4
2
6
,

 
 
1
9
8
2
6
,

 
 
1
5
2
8
0
,

 
 
1
4
,

 
 
1
7
4
2
,

 
 
4
8
,

 
 
5
5
,

 
 
6
1
,

 
 
1
9
8
2
6
,

 
 
1
1
7
4
8
,

 
 
7
,

 
 
1
2
1
0
,

 
 
2
2
,

 
 
5
1
,

 
 
2
0
3
,

 
 
3
5
0
3
,

 
 
8
4
6
2
]
,

 
[
1
3
,
 
3
2
5
9
,
 
2
0
,
 
2
2
1
1
2
,
 
5
,
 
6
9
8
4
1
,
 
3
3
,
 
1
0
4
1
,
 
1
6
0
8
,
 
2
9
4
,
 
4
6
]
,

 
[
3
2
8
0
,

 
 
4
7
1
0
,

 
 
3
5
7
6
,

 
 
9
9
3
,

 
 
1
4
7
6
,

 
 
1
6
2
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
2
0
2
1
1
,

 
 
1
,

 
 
3
6
1
,

 
 
1
7
,

 
 
1
,

 
 
1
7
,

 
 
4
,

 
 
4
2
6
8
,

 
 
3
,

 
 
1
,

 
 
3
2
8
0
,

 
 
3
6
1
,

 
 
1
6
0
,

 
 
2
6
9
2
,

 
 
3
4
4
6
,

 
 
2
0
2
1
1
,

 
 
3
1
0
8
,

 
 
1
7
,

 
 
1
0
6
6
1
1
,

 
 
3
0
9
4
,

 
 
2
3
3
,

 
 
6
0
4
7
,

 
 
2
8
3
4
,

 
 
9
,

 
 
3
2
8
0
,

 
 
5
,

 
 
1
0
6
6
1
2
,

 
 
4
7
1
0
,

 
 
3
2
8
0
,

 
 
2
,

 
 
2
1
0
,

 
 
1
6
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
3
5
7
6
,

 
 
8
3
6
4
9
,

 
 
3
6
5
,

 
 
1
3
0
3
,

 
 
7
4
7
7
,

 
 
1
2
,

 
 
5
5
3
1
,

 
 
1
3
3
,

 
 
1
3
8
8
,

 
 
4
5
2
4
,

 
 
1
,

 
 
3
6
1
,

 
 
1
7
,

 
 
3
2
8
0
,

 
 
1
0
,

 
 
6
5
5
,

 
 
3
6
3
,

 
 
1
6
1
4
9
,

 
 
1
,

 
 
1
3
2
,

 
 
3
5
1
1
,

 
 
1
1
9
0
,

 
 
2
,

 
 
1
,

 
 
3
3
0
7
,

 
 
1
3
8
8
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
6
1
4
9
,

 
 
4
0
6
,

 
 
3
1
4
,

 
 
5
4
6
,

 
 
5
7
7
6
,

 
 
1
0
9
,

 
 
8
3
0
3
,

 
 
4
1
,

 
 
6
,

 
 
1
1
8
,

 
 
1
2
,

 
 
5
8
,

 
 
2
5
6
9
,

 
 
4
2
3
7
9
,

 
 
5
3
,

 
 
4
0
,

 
 
7
0
,

 
 
1
,

 
 
3
8
9
2
,

 
 
3
,

 
 
1
,

 
 
7
8
3
,

 
 
4
2
3
0
,

 
 
1
0
0
,

 
 
2
5
9
,

 
 
1
9
,

 
 
4
2
4
,

 
 
1
0
6
,

 
 
1
2
,

 
 
1
3
,

 
 
2
2
,

 
 
3
6
,

 
 
5
0
,

 
 
1
5
2
,

 
 
8
8
,

 
 
7
,

 
 
2
2
6
,

 
 
9
,

 
 
1
3
,

 
 
9
0
7
,

 
 
8
,

 
 
3
7
1
5
,

 
 
2
6
,

 
 
9
2
,

 
 
1
5
3
,

 
 
3
2
3
,

 
 
2
,

 
 
1
6
,

 
 
5
8
,

 
 
4
9
4
5
6
,

 
 
4
8
0
2
,

 
 
2
8
2
9
,

 
 
3
2
1
,

 
 
5
0
,

 
 
1
5
2
,

 
 
1
5
9
3
,

 
 
2
3
4
]
,

 
[
2
2
,

 
 
6
,

 
 
2
1
1
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
1
7
4
2
,

 
 
1
0
,

 
 
1
2
8
4
6
,

 
 
4
7
5
3
,

 
 
2
1
,

 
 
3
0
,

 
 
1
1
6
5
8
,

 
 
6
,

 
 
3
9
,

 
 
3
4
5
,

 
 
1
6
3
,

 
 
3
3
,

 
 
2
8
,

 
 
3
8
5
0
,

 
 
1
7
5
5
,

 
 
2
7
6
6
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
9
7
,

 
 
4
2
2
,

 
 
2
,

 
 
7
6
1
,

 
 
3
,

 
 
1
0
6
6
1
3
,

 
 
5
,

 
 
6
,

 
 
1
9
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
2
9
5
,

 
 
2
,

 
 
3
4
7
,

 
 
1
4
1
,

 
 
4
2
2
,

 
 
8
4
,

 
 
3
4
5
,

 
 
1
,

 
 
2
9
5
,

 
 
2
1
,

 
 
1
,

 
 
4
2
2
,

 
 
1
3
,

 
 
1
0
5
5
,

 
 
8
7
,

 
 
1
2
1
,

 
 
2
1
,

 
 
2
9
5
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
8
,

 
 
2
5
4
,

 
 
4
9
,

 
 
2
1
9
]
,

 
[
2
2
3
,

 
 
3
,

 
 
1
2
9
,

 
 
1
2
,

 
 
2
7
,

 
 
3
8
4
,

 
 
8
,

 
 
6
9
6
1
,

 
 
6
3
2
8
,

 
 
5
3
8
,

 
 
2
,

 
 
4
4
7
8
,

 
 
1
6
6
,

 
 
7
,

 
 
8
5
9
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
9
4
1
,

 
 
1
0
,

 
 
4
,

 
 
5
3
2
5
,

 
 
2
8
8
9
,

 
 
6
0
8
8
,

 
 
3
4
8
8
,

 
 
2
3
9
3
,

 
 
6
7
5
]
,

 
[
6
3
0
7
,

 
 
1
2
1
1
,

 
 
3
,

 
 
4
7
8
,

 
 
2
8
,

 
 
1
2
5
3
,

 
 
7
,

 
 
1
9
,

 
 
1
3
2
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
0
,

 
 
8
5
7
,

 
 
1
5
,

 
 
1
,

 
 
3
5
4
,

 
 
1
8
,

 
 
1
9
6
,

 
 
5
0
,

 
 
1
6
7
7
,

 
 
1
0
,

 
 
1
,

 
 
1
3
8
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
0
,

 
 
2
3
4
,

 
 
3
3
,

 
 
1
,

 
 
1
3
8
,

 
 
2
9
,

 
 
1
3
4
,

 
 
6
,

 
 
8
3
8
5
]
,

 
[
7
2
,

 
 
6
6
,

 
 
4
,

 
 
9
2
7
,

 
 
2
2
2
5
,

 
 
3
,

 
 
1
3
,

 
 
3
8
7
,

 
 
2
2
6
3
9
,

 
 
2
6
1
0
,

 
 
1
,

 
 
4
0
0
,

 
 
9
,

 
 
4
5
,

 
 
1
7
4
5
,

 
 
6
,

 
 
3
2
2
,

 
 
3
1
,

 
 
1
,

 
 
7
8
6
,

 
 
5
,

 
 
7
0
6
,

 
 
6
]
,

 
[
4
0
,

 
 
1
,

 
 
1
0
6
,

 
 
6
6
3
,

 
 
1
8
,

 
 
7
3
6
,

 
 
4
0
,

 
 
6
,

 
 
1
2
2
,

 
 
2
,

 
 
3
4
,

 
 
8
,

 
 
1
5
6
,

 
 
1
,

 
 
2
3
,

 
 
2
6
,

 
 
7
,

 
 
6
5
0
,

 
 
6
,

 
 
2
2
9
,

 
 
1
5
6
,

 
 
4
0
8
,

 
 
1
2
7
,

 
 
6
,

 
 
9
8
4
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
9
6
,

 
 
5
9
1
,

 
 
1
,

 
 
2
3
,

 
 
3
0
6
,

 
 
7
9
,

 
 
8
,

 
 
3
3
5
8
,

 
 
7
3
,

 
 
2
1
,

 
 
1
,

 
 
1
2
0
,

 
 
1
1
,

 
 
5
8
5
,

 
 
3
1
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
4
9
8
,

 
 
6
,

 
 
2
1
,

 
 
5
5
,

 
 
8
7
7
,

 
 
6
9
,

 
 
6
,

 
 
1
8
,

 
 
1
1
3
1
,

 
 
4
,

 
 
1
6
0
7
6
8
,

 
 
2
9
2
,

 
 
5
,

 
 
1
4
,

 
 
4
,

 
 
2
8
,

 
 
2
7
5
5
,

 
 
8
7
5
,

 
 
6
,

 
 
1
9
,

 
 
4
0
,

 
 
1
,

 
 
4
8
7
,

 
 
6
,

 
 
1
2
2
,

 
 
5
5
6
,

 
 
1
,

 
 
1
4
5
4
8
,

 
 
2
5
3
,

 
 
1
4
0
,

 
 
2
2
,

 
 
4
,

 
 
7
4
3
,

 
 
2
8
,

 
 
2
7
5
5
,

 
 
8
7
5
,

 
 
1
0
7
7
,

 
 
5
8
,

 
 
6
4
7
2
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
4
8
2
,

 
 
2
,

 
 
4
9
8
,

 
 
8
8
,

 
 
1
4
7
,

 
 
6
,

 
 
1
8
,

 
 
6
0
5
,

 
 
4
,

 
 
5
6
1
,

 
 
6
7
0
7
,

 
 
5
0
5
1
,

 
 
6
2
,

 
 
8
,

 
 
2
9
0
,

 
 
2
1
8
,

 
 
7
3
,

 
 
2
,

 
 
3
4
7
,

 
 
2
0
,

 
 
8
7
1
,

 
 
7
,

 
 
8
1
,

 
 
1
0
5
4
,

 
 
1
0
0
3
,

 
 
1
4
,

 
 
5
6
1
,

 
 
6
7
0
7
,

 
 
7
,

 
 
1
9
,

 
 
4
4
,

 
 
8
7
1
,

 
 
7
,

 
 
1
1
3
1
,

 
 
5
7
6
,

 
 
4
7
9
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
1
4
6
4
,

 
 
1
3
,

 
 
2
9
,

 
 
2
0
8
8
,

 
 
5
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
,

 
 
3
0
4
6
,

 
 
3
0
,

 
 
1
4
5
4
8
,

 
 
6
0
1
,

 
 
6
9
,

 
 
1
1
,

 
 
8
,

 
 
3
2
,

 
 
3
1
3
,

 
 
1
,

 
 
1
3
2
,

 
 
8
8
7
,

 
 
5
,

 
 
3
4
5
6
,

 
 
1
3
2
9
,

 
 
5
3
,

 
 
3
9
,

 
 
3
4
,

 
 
1
3
,

 
 
4
3
0
,

 
 
4
0
2
,

 
 
4
,

 
 
3
0
3
,

 
 
2
2
,

 
 
6
,

 
 
5
4
8
,

 
 
2
5
,

 
 
6
,

 
 
3
9
,

 
 
8
8
9
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
1
1
6
8
,

 
 
8
,

 
 
1
,

 
 
3
8
2
0
,

 
 
4
0
7
,

 
 
5
,

 
 
4
9
,

 
 
8
2
2
,

 
 
2
1
,

 
 
1
1
,

 
 
7
1
,

 
 
7
3
,

 
 
2
,

 
 
6
,

 
 
2
6
,

 
 
7
,

 
 
4
5
,

 
 
3
5
7
,

 
 
7
9
,

 
 
1
5
,

 
 
4
,

 
 
2
0
7
3
,

 
 
1
2
6
7
,

 
 
2
5
,

 
 
5
3
,

 
 
3
9
,

 
 
2
6
3
,

 
 
2
,

 
 
5
4
3
5
,

 
 
2
0
,

 
 
1
6
0
7
6
9
,

 
 
5
,

 
 
1
1
6
8
,

 
 
1
3
5
,

 
 
4
7
,

 
 
2
3
,

 
 
2
6
,

 
 
1
,

 
 
4
2
0
,

 
 
1
4
8
6
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
1
8
7
3
4
,

 
 
1
0
8
7
,

 
 
3
1
,

 
 
5
7
7
7
,

 
 
2
,

 
 
3
5
2
6
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
6
7
0
7
,

 
 
3
0
5
6
,

 
 
1
7
,

 
 
2
1
5
4
,

 
 
3
2
2
,

 
 
3
2
,

 
 
2
1
0
,

 
 
3
9
7
0
5
,

 
 
2
2
4
1
,

 
 
9
1
0
,

 
 
5
,

 
 
1
,

 
 
1
9
4
2
7
,

 
 
5
,

 
 
1
,

 
 
6
7
0
7
,

 
 
1
6
0
7
7
0
,

 
 
1
5
1
4
,

 
 
5
4
,

 
 
4
2
,

 
 
5
7
,

 
 
2
4
1
5
,

 
 
1
0
,

 
 
8
6
9
,

 
 
5
9
0
,

 
 
5
,

 
 
1
7
0
9
,

 
 
1
0
6
,

 
 
1
1
2
,

 
 
4
2
0
,

 
 
2
1
8
,

 
 
1
8
,

 
 
1
2
1
5
,

 
 
5
,

 
 
4
5
,

 
 
1
4
2
5
]
,

 
[
1
8
,

 
 
6
,

 
 
1
4
4
6
,

 
 
7
3
5
,

 
 
1
4
4
6
,

 
 
1
9
,

 
 
2
4
1
,

 
 
2
,

 
 
3
4
,

 
 
2
6
,

 
 
2
1
3
,

 
 
7
6
1
,

 
 
4
1
7
2
,

 
 
1
1
8
,

 
 
5
,

 
 
2
6
6
,

 
 
1
4
8
5
]
,

 
[
7
1
,

 
 
3
1
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
1
3
0
,

 
 
5
9
0
,

 
 
1
5
,

 
 
7
8
3
,

 
 
1
7
2
8
,

 
 
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
2
4
,

 
 
3
1
,

 
 
3
0
7
6
,

 
 
4
5
5
5
9
,

 
 
2
6
,

 
 
7
,

 
 
4
9
,

 
 
1
5
4
7
,

 
 
5
,

 
 
1
6
0
7
7
1
,

 
 
2
8
5
,

 
 
1
0
,

 
 
4
1
,

 
 
7
,

 
 
4
5
,

 
 
2
3
8
9
,

 
 
7
6
,

 
 
4
,

 
 
1
2
0
,

 
 
1
2
,

 
 
1
3
,

 
 
5
8
2
]
,

 
[
3
2
0
,

 
 
6
,

 
 
5
0
3
5
,

 
 
2
,

 
 
5
3
8
9
,

 
 
1
7
1
,

 
 
2
9
2
6
,

 
 
2
8
1
2
,

 
 
7
8
6
,

 
 
2
2
6
2
,

 
 
2
0
,

 
 
2
1
8
9
,

 
 
1
,

 
 
2
4
0
,

 
 
2
4
3
7
,

 
 
5
,

 
 
2
5
7
4
,

 
 
7
6
,

 
 
2
0
,

 
 
3
7
0
2
,

 
 
1
9
9
3
,

 
 
7
1
,

 
 
4
8
,

 
 
3
2
1
8
2
,

 
 
3
8
,

 
 
1
,

 
 
2
8
6
5
7
,

 
 
3
2
2
7
,

 
 
3
0
0
,

 
 
3
4
,

 
 
6
,

 
 
1
9
,

 
 
1
5
,

 
 
2
8
,

 
 
7
0
4
,

 
 
5
8
1
,

 
 
4
,

 
 
1
0
2
,

 
 
1
5
5
5
,

 
 
5
,

 
 
6
0
0
2
,

 
 
4
7
,

 
 
5
8
3
,

 
 
1
3
9
0
9
,

 
 
1
5
5
,

 
 
6
7
3
,

 
 
1
3
6
,

 
 
1
6
3
,

 
 
2
0
1
,

 
 
2
,

 
 
3
4
]
,

 
[
1
3
7
,
 
1
2
2
4
,
 
3
0
,
 
1
9
4
3
,
 
1
2
,
 
1
3
,
 
2
1
3
,
 
3
3
,
 
1
0
7
,
 
4
6
,
 
6
1
3
1
,
 
8
0
4
2
,
 
1
0
7
,
 
1
6
1
7
,
 
1
4
7
2
0
]
,

 
[
8
0
,
 
2
7
,
 
2
3
,
 
8
,
 
3
3
3
,
 
3
5
,
 
9
,
 
9
6
7
,
 
8
4
,
 
4
,
 
1
3
4
8
,
 
2
9
,
 
4
5
,
 
1
6
,
 
3
3
3
]
,

 
[
9
,

 
 
4
3
,

 
 
1
6
,

 
 
5
2
1
,

 
 
2
0
1
2
,

 
 
1
2
,

 
 
1
4
1
,

 
 
2
7
6
9
6
,

 
 
2
3
0
3
,

 
 
2
,

 
 
3
9
2
,

 
 
4
,

 
 
1
1
2
6
,

 
 
9
,

 
 
2
4
,

 
 
3
3
3
,

 
 
1
5
1
,

 
 
1
,

 
 
1
1
1
1
,

 
 
1
2
,

 
 
5
4
,

 
 
2
1
0
,

 
 
1
,

 
 
1
1
2
6
,

 
 
5
,

 
 
1
,

 
 
2
3
0
3
,

 
 
3
4
,

 
 
4
7
0
,

 
 
3
5
,

 
 
1
,

 
 
2
7
6
9
6
,

 
 
2
3
0
3
,

 
 
8
6
,

 
 
1
4
,

 
 
2
8
6
5
8
,

 
 
1
2
,

 
 
1
,

 
 
1
1
2
6
,

 
 
5
6
5
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
9
8
4
,

 
 
4
,

 
 
1
8
3
3
,

 
 
1
5
,

 
 
1
,

 
 
3
6
9
7
,

 
 
1
0
2
,

 
 
2
0
1
2
,

 
 
1
1
,

 
 
8
,

 
 
1
5
5
8
,

 
 
8
7
0
,

 
 
2
,

 
 
8
2
,

 
 
1
,

 
 
2
3
0
3
,

 
 
2
,

 
 
4
4
4
3
,

 
 
2
,

 
 
1
,

 
 
1
3
9
,

 
 
8
8
5
,

 
 
1
1
1
1
,

 
 
2
,

 
 
3
9
9
,

 
 
1
6
5
1
,

 
 
1
,

 
 
3
8
,

 
 
8
1
2
,

 
 
2
6
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
9
1
3
,

 
 
1
2
0
,

 
 
1
0
,

 
 
1
1
1
,

 
 
4
,

 
 
2
4
,

 
 
8
,

 
 
1
4
,

 
 
4
4
4
1
,

 
 
1
2
,

 
 
2
8
,

 
 
1
4
4
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
4
4
1
,

 
 
9
,

 
 
8
,

 
 
7
8
,

 
 
7
,

 
 
4
1
6
,

 
 
1
1
,

 
 
6
4
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
1
5
8
,

 
 
1
0
7
7
,

 
 
2
,

 
 
3
9
4
,

 
 
1
1
,

 
 
5
8
,

 
 
2
,

 
 
1
3
6
,

 
 
4
4
4
1
,

 
 
2
9
5
,

 
 
2
9
4
]
,

 
[
2
0
,

 
 
1
6
1
5
,

 
 
1
1
3
7
,

 
 
2
0
,

 
 
1
1
3
7
,

 
 
8
,

 
 
1
0
5
9
,

 
 
4
7
4
1
,

 
 
9
,

 
 
8
,

 
 
2
4
7
,

 
 
6
,

 
 
5
6
,

 
 
1
4
,

 
 
3
1
7
,

 
 
2
7
,

 
 
1
6
0
7
7
2
,

 
 
2
8
0
8
,

 
 
4
9
,

 
 
1
5
6
0
,

 
 
3
3
0
,

 
 
1
,

 
 
3
4
1
,

 
 
4
8
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
3
1
3
7
,

 
 
3
,

 
 
6
,

 
 
2
,

 
 
1
6
4
3
,

 
 
9
,

 
 
2
0
,

 
 
2
3
8
3
5
,

 
 
6
2
9
9
,

 
 
1
8
,

 
 
3
6
,

 
 
1
7
8
1
,

 
 
9
,

 
 
5
1
,

 
 
4
5
,

 
 
7
7
,

 
 
3
4
9
,

 
 
9
7
,

 
 
8
2
3
,

 
 
1
4
0
,

 
 
3
9
1
5
,

 
 
3
7
,

 
 
1
8
1
,

 
 
1
2
1
,

 
 
2
1
5
,

 
 
6
2
0
4
,

 
 
1
4
4
,

 
 
7
,

 
 
1
9
,

 
 
1
7
,

 
 
1
3
0
,

 
 
2
5
2
5
,

 
 
1
7
,

 
 
7
,

 
 
1
0
8
]
,

 
[
1
4
9
,

 
 
4
0
8
6
,

 
 
1
5
,

 
 
8
2
5
8
,

 
 
1
0
3
,

 
 
6
,

 
 
5
2
0
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
7
8
,

 
 
6
,

 
 
1
9
,

 
 
3
6
8
,

 
 
3
0
,

 
 
7
9
,

 
 
1
7
5
1
]
,

 
[
3
9
7
8
,

 
 
2
1
2
8
,

 
 
5
,

 
 
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
,

 
 
6
,

 
 
4
2
,

 
 
6
7
8
,

 
 
2
1
,

 
 
7
5
,

 
 
6
2
,

 
 
3
4
9
6
,

 
 
1
4
0
5
,

 
 
6
,

 
 
1
8
,

 
 
2
7
,

 
 
1
9
8
2
7
,

 
 
1
5
5
]
,

 
[
1
,

 
 
1
0
9
,

 
 
4
9
4
5
7
,

 
 
1
0
7
2
4
,

 
 
5
2
6
,

 
 
2
,

 
 
1
6
,

 
 
4
9
,

 
 
4
,

 
 
4
8
5
5
,

 
 
3
,

 
 
4
9
4
5
7
,

 
 
5
3
1
2
,

 
 
1
,

 
 
1
0
9
,

 
 
1
2
2
8
6
,

 
 
1
3
3
,

 
 
1
8
2
,

 
 
6
8
,

 
 
1
0
6
6
1
4
,

 
 
3
3
,

 
 
1
,

 
 
4
4
9
9
,

 
 
4
8
0
]
,

 
[
8
4
4
,
 
1
0
7
,
 
4
6
,
 
5
4
3
5
1
,
 
4
9
4
5
8
,
 
1
0
2
2
,
 
3
6
3
,
 
2
7
9
7
,
 
6
9
9
]
,

 
[
7
,

 
 
1
4
7
8
,

 
 
8
9
,

 
 
9
,

 
 
1
,

 
 
2
3
,

 
 
1
8
1
,

 
 
3
7
1
,

 
 
1
1
7
,

 
 
3
8
,

 
 
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
1
6
7
,

 
 
2
2
,

 
 
2
5
9
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
,

 
 
7
1
7
,

 
 
1
4
9
3
,

 
 
9
,

 
 
4
1
,

 
 
1
3
8
1
,

 
 
4
,

 
 
8
2
3
,

 
 
6
0
8
0
8
,

 
 
3
,

 
 
2
6
7
6
3
,

 
 
2
,

 
 
5
4
0
,

 
 
7
,

 
 
4
3
,

 
 
1
6
,

 
 
1
0
2
,

 
 
5
5
4
,

 
 
1
0
,

 
 
1
2
3
7
,

 
 
1
1
,

 
 
5
,

 
 
5
3
,

 
 
1
0
3
,

 
 
6
9
8
4
2
,

 
 
1
,

 
 
5
4
1
8
,

 
 
2
1
,

 
 
1
,

 
 
7
1
7
]
,

 
[
7
,

 
 
2
3
9
,

 
 
6
3
3
3
,

 
 
2
0
9
6
,

 
 
2
1
5
,

 
 
1
1
2
,

 
 
1
8
,

 
 
1
,

 
 
5
6
8
,

 
 
5
,

 
 
7
7
,

 
 
4
7
9
,

 
 
2
0
8
,

 
 
2
3
1
7
,

 
 
3
0
6
,

 
 
3
8
8
6
,

 
 
1
4
5
4
,

 
 
2
4
,

 
 
3
2
2
,

 
 
1
5
6
1
,

 
 
1
0
4
2
7
,

 
 
1
0
6
6
1
5
,

 
 
5
4
,

 
 
8
,

 
 
1
0
4
2
,

 
 
2
,

 
 
1
0
6
6
1
6
,

 
 
7
4
7
8
,

 
 
3
3
4
0
,

 
 
1
6
8
0
,

 
 
5
,

 
 
1
0
6
6
1
7
,

 
 
5
4
,

 
 
8
,

 
 
1
0
4
2
,

 
 
2
,

 
 
1
0
6
6
1
8
,

 
 
1
9
0
6
3
,

 
 
1
0
6
6
1
9
,

 
 
1
6
8
0
,

 
 
4
3
3
,

 
 
9
9
,

 
 
9
2
,

 
 
1
8
3
5
,

 
 
3
1
1
8
,

 
 
1
0
,

 
 
1
,

 
 
8
1
7
8
,

 
 
1
0
,

 
 
6
0
3
,

 
 
2
7
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
8
3
6
5
0
,

 
 
2
4
3
,

 
 
6
9
8
4
3
,

 
 
8
7
,

 
 
9
5
1
,

 
 
5
4
6
6
,

 
 
3
8
8
6
,

 
 
2
1
7
2
,

 
 
6
0
3
,

 
 
4
1
2
,

 
 
1
2
1
2
,

 
 
1
6
0
7
7
3
]
,

 
[
1
1
5
4
,

 
 
9
4
5
9
,

 
 
2
4
7
8
,

 
 
8
,

 
 
1
1
,

 
 
3
7
4
,

 
 
2
,

 
 
1
1
7
,

 
 
9
,

 
 
2
6
0
4
,

 
 
2
2
,

 
 
4
,

 
 
2
3
1
4
,

 
 
1
8
9
6
,

 
 
1
7
1
7
,

 
 
3
2
,

 
 
1
2
1
8
4
,

 
 
1
0
0
4
3
,

 
 
1
,

 
 
5
8
1
0
,

 
 
3
2
4
1
,

 
 
8
4
,

 
 
4
,

 
 
8
6
4
,

 
 
1
8
9
6
,

 
 
2
3
1
4
,

 
 
6
9
9
,

 
 
4
5
,

 
 
2
0
1
5
,

 
 
1
,

 
 
1
3
9
,

 
 
3
2
4
1
,

 
 
1
7
,

 
 
4
,

 
 
2
3
9
5
,

 
 
1
8
9
6
,

 
 
2
3
1
4
,

 
 
6
9
9
,

 
 
1
7
1
7
,

 
 
2
2
,

 
 
3
6
,

 
 
1
0
3
,

 
 
1
,

 
 
1
9
7
6
,

 
 
9
3
,

 
 
2
3
1
4
,

 
 
1
7
1
7
,

 
 
1
6
,

 
 
4
1
9
,

 
 
1
1
5
4
,

 
 
1
3
9
7
,

 
 
5
,

 
 
1
,

 
 
1
5
9
7
,

 
 
9
3
,

 
 
2
3
1
4
,

 
 
1
7
1
7
,

 
 
4
1
9
,

 
 
9
4
5
9
,

 
 
1
3
9
7
,

 
 
2
2
,

 
 
3
6
,

 
 
7
,

 
 
6
5
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
2
8
4
,

 
 
7
3
3
,

 
 
2
5
,

 
 
4
7
,

 
 
1
1
0
,

 
 
3
,

 
 
5
9
3
2
,

 
 
2
1
8
]
,

 
[
3
3
8
,

 
 
1
1
6
,

 
 
3
9
8
,

 
 
1
7
8
,

 
 
7
,

 
 
2
4
,

 
 
3
3
,

 
 
1
,

 
 
1
5
8
7
,

 
 
1
0
2
3
,

 
 
5
,

 
 
7
,

 
 
3
0
6
2
,

 
 
6
5
8
,

 
 
2
0
,

 
 
5
8
7
,

 
 
1
5
0
,

 
 
3
7
6
8
,

 
 
1
,

 
 
3
3
8
,

 
 
3
,

 
 
1
,

 
 
1
1
6
,

 
 
7
2
,

 
 
2
8
0
,

 
 
1
2
,

 
 
9
,

 
 
3
,

 
 
4
4
3
,

 
 
7
,

 
 
6
2
4
,

 
 
3
4
,

 
 
1
1
1
,

 
 
4
,

 
 
3
9
8
,

 
 
1
2
7
,

 
 
4
9
,

 
 
2
,

 
 
1
8
4
3
,

 
 
1
3
7
,

 
 
2
8
6
2
,

 
 
4
,

 
 
1
1
5
,

 
 
1
1
6
,

 
 
2
,

 
 
7
3
4
,

 
 
3
7
5
5
,

 
 
6
0
,

 
 
1
8
1
6
,

 
 
9
,

 
 
5
1
,

 
 
8
6
,

 
 
7
9
7
1
,

 
 
1
0
,

 
 
4
,

 
 
1
1
0
,

 
 
1
0
,

 
 
4
8
8
,

 
 
2
1
,

 
 
1
,

 
 
1
0
2
9
,

 
 
3
,

 
 
3
0
5
7
,

 
 
1
6
0
8
,

 
 
1
7
,

 
 
9
5
7
,

 
 
6
4
,

 
 
1
0
,

 
 
1
5
3
1
,

 
 
1
,

 
 
3
3
8
,

 
 
3
,

 
 
1
,

 
 
1
1
6
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
7
6
,

 
 
2
,

 
 
1
6
3
,

 
 
3
1
3
6
,

 
 
5
,

 
 
4
7
,

 
 
3
,

 
 
3
0
,

 
 
3
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
4
6
4
7
,

 
 
1
1
,

 
 
8
,

 
 
1
,

 
 
1
1
4
,

 
 
8
5
,

 
 
7
,

 
 
6
3
,

 
 
7
5
,

 
 
1
2
9
,

 
 
6
5
5
3
,

 
 
2
1
6
7
,

 
 
4
1
4
,

 
 
1
0
,

 
 
4
,

 
 
4
6
,

 
 
2
9
,

 
 
1
3
,

 
 
4
9
,

 
 
5
2
6
,

 
 
2
1
4
5
,

 
 
2
,

 
 
3
7
]
,

 
[
1
3
9
1
6
,

 
 
6
,

 
 
1
8
,

 
 
2
7
,

 
 
1
6
2
0
,

 
 
5
0
,

 
 
3
3
7
6
,

 
 
2
2
6
4
0
,

 
 
1
7
9
,

 
 
2
0
0
4
,

 
 
2
5
,

 
 
1
,

 
 
3
1
8
4
,

 
 
4
0
2
0
,

 
 
3
5
,

 
 
7
4
,

 
 
1
3
9
1
7
,

 
 
2
9
1
4
,

 
 
7
0
7
1
,

 
 
9
0
,

 
 
1
4
,

 
 
1
0
8
,

 
 
2
,

 
 
2
5
1
5
4
,

 
 
1
,

 
 
1
7
1
8
,

 
 
9
,

 
 
1
,

 
 
6
4
3
,

 
 
1
7
3
6
,

 
 
1
9
4
9
,

 
 
2
1
,

 
 
1
,

 
 
2
7
6
9
7
,

 
 
1
7
,

 
 
1
6
8
2
,

 
 
2
,

 
 
1
,

 
 
4
9
4
5
9
,

 
 
3
7
3
,

 
 
8
8
,

 
 
7
4
,

 
 
1
,

 
 
3
9
7
0
6
,

 
 
7
7
0
9
,

 
 
1
7
9
,

 
 
2
,

 
 
3
0
3
7
,

 
 
5
8
0
,

 
 
1
5
,

 
 
1
,

 
 
2
7
6
9
7
,

 
 
1
6
5
4
,

 
 
1
8
,

 
 
5
2
9
3
,

 
 
1
7
,

 
 
4
2
9
6
,

 
 
1
0
7
2
5
,

 
 
2
1
,

 
 
4
4
,

 
 
1
5
0
4
,

 
 
4
1
4
,

 
 
2
,

 
 
1
,

 
 
6
9
8
7
,

 
 
3
,

 
 
2
8
4
,

 
 
2
3
0
0
,

 
 
1
0
,

 
 
9
2
,

 
 
7
9
3
6
,

 
 
5
,

 
 
1
4
0
5
2
,

 
 
1
8
2
9
,

 
 
1
,

 
 
1
0
6
6
2
0
,

 
 
4
5
,

 
 
8
,

 
 
1
,

 
 
6
8
3
3
,

 
 
2
5
,

 
 
3
3
1
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
7
3
6
,

 
 
1
,

 
 
6
4
2
,

 
 
1
8
4
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
6
,

 
 
8
0
9
,

 
 
1
0
,

 
 
4
,

 
 
1
4
4
4
,

 
 
3
3
,

 
 
3
0
8
,

 
 
2
2
,

 
 
1
,

 
 
4
5
5
6
0
,

 
 
9
9
,

 
 
9
2
,

 
 
1
1
0
,

 
 
9
6
,

 
 
1
,

 
 
3
3
6
9
5
,

 
 
1
7
1
7
3
,

 
 
3
8
8
4
,

 
 
9
,

 
 
1
,

 
 
2
7
6
9
7
,

 
 
3
0
0
8
,

 
 
1
,

 
 
6
8
3
,

 
 
5
0
,

 
 
8
6
6
,

 
 
9
,

 
 
6
4
,

 
 
9
5
]
,

 
[
5
8
7
,

 
 
1
1
8
7
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
3
1
7
,

 
 
6
,

 
 
1
0
3
3
,

 
 
2
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
3
6
,

 
 
9
,

 
 
1
0
,

 
 
3
7
5
,

 
 
1
7
0
0
,

 
 
8
9
2
,

 
 
6
,

 
 
3
9
,

 
 
3
3
7
6
,

 
 
1
9
1
,

 
 
9
,

 
 
5
3
,

 
 
5
6
,

 
 
2
8
9
,

 
 
1
2
7
,

 
 
2
2
,

 
 
1
6
4
,

 
 
3
6
,

 
 
4
8
3
4
,

 
 
2
6
,

 
 
1
6
4
,

 
 
2
9
0
,

 
 
1
1
,

 
 
5
5
2
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
1
1
2
,

 
 
2
8
7
5
,

 
 
2
3
4
,

 
 
7
,

 
 
4
5
,

 
 
1
6
9
0
1
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
0
3
3
]
,

 
[
5
6
,

 
 
1
6
,

 
 
6
0
8
0
9
,

 
 
1
4
8
7
,

 
 
3
,

 
 
3
8
,

 
 
6
1
,

 
 
7
5
,

 
 
1
9
,

 
 
1
0
7
8
,

 
 
1
6
0
7
7
4
,

 
 
1
0
9
,

 
 
5
6
,

 
 
1
6
,

 
 
6
0
8
0
9
,

 
 
1
0
4
,

 
 
4
8
,

 
 
8
2
5
,

 
 
1
0
3
6
,

 
 
3
1
,

 
 
6
9
6
,

 
 
1
9
3
,

 
 
1
6
0
7
7
5
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
0
,

 
 
1
,

 
 
2
8
7
9
,

 
 
1
,

 
 
7
5
,

 
 
2
8
6
5
9
,

 
 
1
5
9
,

 
 
4
6
6
,

 
 
2
,

 
 
1
7
3
8
,

 
 
6
9
7
9
,

 
 
1
,

 
 
6
9
8
4
4
,

 
 
5
4
2
,

 
 
2
1
2
6
,

 
 
4
0
,

 
 
3
,

 
 
8
8
,

 
 
9
4
5
,

 
 
1
6
0
7
7
6
,

 
 
6
0
8
0
9
,

 
 
4
2
5
,

 
 
5
9
1
5
,

 
 
4
,

 
 
7
4
7
,

 
 
2
7
0
,

 
 
6
5
0
,

 
 
3
8
,

 
 
1
6
0
7
7
7
,

 
 
1
0
0
,

 
 
1
0
,

 
 
1
,

 
 
8
0
2
]
,

 
[
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
,

 
 
4
,

 
 
1
6
9
,

 
 
2
,

 
 
1
,

 
 
7
9
,

 
 
7
,

 
 
1
9
,

 
 
3
6
8
,

 
 
3
9
,

 
 
1
6
,

 
 
2
9
1
,

 
 
6
4
,

 
 
1
6
9
,

 
 
2
2
,

 
 
6
,

 
 
2
2
0
,

 
 
1
3
,

 
 
7
9
,

 
 
5
6
,

 
 
1
4
,

 
 
1
9
,

 
 
5
7
,

 
 
3
6
8
,

 
 
5
0
,

 
 
8
1
4
,

 
 
3
7
,

 
 
2
9
4
,

 
 
4
6
]
,

 
[
5
0
,

 
 
5
6
3
,

 
 
7
4
,

 
 
1
4
5
3
,

 
 
8
8
7
,

 
 
3
5
2
4
,

 
 
1
0
5
,

 
 
3
5
,

 
 
1
6
1
5
0
,

 
 
5
9
3
3
,

 
 
8
,

 
 
2
1
7
,

 
 
7
,

 
 
1
4
7
,

 
 
1
3
1
8
,

 
 
2
,

 
 
3
3
3
7
,

 
 
2
0
,

 
 
3
8
9
]
,

 
[
7
,

 
 
6
5
,

 
 
1
,

 
 
7
2
7
,

 
 
2
3
,

 
 
5
6
,

 
 
1
6
,

 
 
9
1
7
,

 
 
1
7
,

 
 
1
9
4
2
8
,

 
 
5
,

 
 
1
,

 
 
2
2
3
,

 
 
3
5
,

 
 
6
0
2
,

 
 
8
1
4
0
,

 
 
1
7
,

 
 
6
1
1
9
,

 
 
3
0
,

 
 
1
4
5
,

 
 
2
4
,

 
 
9
,

 
 
2
4
7
2
,

 
 
1
8
,

 
 
2
8
6
6
0
,

 
 
5
,

 
 
5
3
,

 
 
1
8
,

 
 
5
8
8
7
,

 
 
2
0
9
,

 
 
8
8
,

 
 
1
7
,

 
 
7
0
,

 
 
1
1
,

 
 
4
0
,

 
 
4
9
8
4
,

 
 
2
9
6
,

 
 
5
1
,

 
 
2
8
8
,

 
 
3
9
,

 
 
9
7
,

 
 
4
1
2
3
,

 
 
1
2
8
4
7
,

 
 
2
0
1
,

 
 
9
3
,

 
 
2
5
9
,

 
 
3
3
1
,

 
 
2
6
,

 
 
1
0
4
,

 
 
1
5
3
,

 
 
2
7
,

 
 
4
1
2
3
,

 
 
6
5
0
,

 
 
6
6
,

 
 
2
2
,

 
 
6
,

 
 
2
3
9
,

 
 
4
5
4
,

 
 
7
,

 
 
8
1
,

 
 
1
0
7
1
,

 
 
2
4
8
,

 
 
1
5
6
8
7
,

 
 
2
0
0
5
,

 
 
5
9
7
2
,

 
 
1
7
,

 
 
1
3
,

 
 
4
5
7
,

 
 
7
,

 
 
6
5
,

 
 
1
3
,

 
 
2
3
,

 
 
4
5
5
6
1
,

 
 
1
1
2
0
7
,

 
 
1
,

 
 
1
4
5
,

 
 
9
,

 
 
1
0
9
7
8
,

 
 
5
,

 
 
1
5
5
0
,

 
 
3
,

 
 
4
0
,

 
 
1
3
6
9
,

 
 
1
8
,

 
 
3
0
1
,

 
 
1
2
6
9
,

 
 
2
,

 
 
1
1
8
,

 
 
3
5
,

 
 
2
9
8
,

 
 
2
1
8
,

 
 
1
2
5
,

 
 
2
0
1
,

 
 
1
2
6
9
,

 
 
1
8
,

 
 
4
6
7
,

 
 
5
,

 
 
5
3
,

 
 
1
8
,

 
 
2
9
0
,

 
 
1
1
0
6
1
,

 
 
3
7
6
9
,

 
 
3
,

 
 
4
0
,

 
 
1
7
5
,

 
 
2
5
9
5
2
,

 
 
2
0
5
8
,

 
 
6
9
8
,

 
 
7
6
]
,

 
[
1
3
3
,

 
 
1
6
2
9
,

 
 
1
6
2
0
,

 
 
2
9
,

 
 
1
2
3
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
1
9
3
,

 
 
3
5
,

 
 
1
,

 
 
1
2
3
,

 
 
3
,

 
 
1
3
3
,

 
 
1
6
2
9
,

 
 
1
6
2
0
,

 
 
1
5
9
2
,

 
 
7
,

 
 
1
9
,

 
 
9
9
,

 
 
1
,

 
 
2
7
2
,

 
 
2
4
5
1
,

 
 
6
2
,

 
 
1
0
3
5
,

 
 
3
7
,

 
 
1
4
5
7
,

 
 
1
2
,

 
 
1
,

 
 
4
8
6
,

 
 
7
9
4
,

 
 
1
7
,

 
 
2
5
5
,

 
 
6
3
7
1
,

 
 
3
4
4
1
,

 
 
3
4
4
1
,

 
 
4
6
4
0
]
,

 
[
1
9
7
,

 
 
1
1
,

 
 
8
,

 
 
1
5
3
,

 
 
1
0
,

 
 
1
0
0
9
,

 
 
2
,

 
 
2
0
1
1
,

 
 
5
2
,

 
 
1
8
1
,

 
 
1
4
2
,

 
 
1
,

 
 
5
9
1
6
,

 
 
8
2
9
,

 
 
2
5
,

 
 
9
,

 
 
5
2
,

 
 
8
,

 
 
1
7
4
6
0
]
,

 
[
1
1
4
,

 
 
2
2
4
4
,

 
 
1
7
1
5
,

 
 
1
2
7
1
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
7
5
0
7
,

 
 
3
5
2
7
,

 
 
1
3
3
6
,

 
 
1
7
,

 
 
1
1
1
,

 
 
8
,

 
 
1
5
7
0
,

 
 
4
3
7
,

 
 
7
2
,

 
 
1
4
,

 
 
1
3
0
0
,

 
 
2
7
6
9
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
1
6
0
7
7
8
,

 
 
3
2
,

 
 
1
5
9
6
,

 
 
6
4
0
,

 
 
5
,

 
 
4
1
0
,

 
 
3
3
,

 
 
2
8
,

 
 
6
2
,

 
 
1
9
,

 
 
8
7
3
,

 
 
1
9
2
4
,

 
 
3
7
,

 
 
7
8
2
,

 
 
6
,

 
 
7
2
5
,

 
 
1
,

 
 
6
0
0
,

 
 
1
5
,

 
 
8
5
6
3
,

 
 
1
5
9
2
,

 
 
1
7
,

 
 
2
0
,

 
 
9
1
3
,

 
 
3
1
1
,

 
 
3
,

 
 
4
1
3
,

 
 
5
,

 
 
2
9
9
6
,

 
 
4
7
9
,

 
 
3
8
,

 
 
3
0
6
8
,

 
 
8
,

 
 
1
,

 
 
2
9
9
6
,

 
 
1
6
6
,

 
 
1
0
,

 
 
9
,

 
 
6
0
0
,

 
 
9
,

 
 
1
,

 
 
7
5
0
7
,

 
 
1
7
1
7
4
,

 
 
8
5
6
3
,

 
 
1
5
9
2
,

 
 
9
,

 
 
8
5
6
3
,

 
 
1
5
9
2
,

 
 
5
2
5
1
,

 
 
4
,

 
 
9
6
6
,

 
 
3
,

 
 
5
8
8
6
,

 
 
2
,

 
 
2
2
5
2
,

 
 
2
4
8
,

 
 
6
2
2
5
,

 
 
1
0
4
2
8
,

 
 
9
,

 
 
8
5
6
3
,

 
 
1
5
9
2
,

 
 
7
7
1
,

 
 
1
5
6
8
8
,

 
 
4
0
,

 
 
5
3
8
,

 
 
1
0
,

 
 
9
,

 
 
6
0
0
,

 
 
1
8
,

 
 
1
5
4
8
1
,

 
 
3
8
0
]
,

 
[
5
2
1
,

 
 
8
8
7
9
,

 
 
2
0
6
,

 
 
3
1
,

 
 
1
5
8
,

 
 
6
2
,

 
 
4
4
7
9
,

 
 
1
,

 
 
3
1
3
,

 
 
7
4
1
6
,

 
 
1
3
3
5
,

 
 
2
0
8
8
,

 
 
2
1
5
9
2
,

 
 
1
5
,

 
 
6
8
,

 
 
1
0
7
,

 
 
2
9
]
,

 
[
1
9
5
,
 
5
3
,
 
2
1
0
,
 
1
9
,
 
6
0
]
,

 
[
5
9
,

 
 
1
6
,

 
 
2
3
1
7
6
,

 
 
7
,

 
 
1
1
4
9
,

 
 
1
9
,

 
 
2
,

 
 
1
9
0
4
,

 
 
4
9
9
,

 
 
7
4
,

 
 
1
3
0
,

 
 
7
5
,

 
 
3
2
4
5
,

 
 
1
2
,

 
 
1
0
4
,

 
 
1
1
9
,

 
 
5
9
,

 
 
3
8
9
5
,

 
 
1
2
4
,

 
 
8
0
,

 
 
6
,

 
 
5
9
,

 
 
9
4
,

 
 
2
0
,

 
 
1
7
0
,

 
 
1
1
0
,

 
 
2
9
4
]
,

 
[
7
9
,

 
 
3
3
6
,

 
 
1
5
,

 
 
1
3
6
5
,

 
 
1
1
6
9
,

 
 
1
1
9
8
,

 
 
1
,

 
 
1
0
4
2
9
,

 
 
6
9
8
8
,

 
 
1
5
3
4
,

 
 
3
4
7
3
,

 
 
1
5
,

 
 
1
,

 
 
3
2
8
1
,

 
 
6
5
4
,

 
 
1
0
,

 
 
8
4
1
8
,

 
 
3
,

 
 
1
0
7
2
4
,

 
 
1
1
2
8
3
,

 
 
3
3
,

 
 
8
0
7
3
,

 
 
9
4
6
0
,

 
 
6
7
8
4
,

 
 
4
,

 
 
3
0
3
,

 
 
1
5
1
,

 
 
1
,

 
 
5
4
3
5
2
,

 
 
6
9
6
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
3
7
4
2
4
,

 
 
2
4
3
,

 
 
6
5
3
,

 
 
2
8
4
6
,

 
 
1
0
4
2
9
,

 
 
6
9
8
8
,

 
 
1
1
4
0
,

 
 
1
0
7
2
4
,

 
 
5
4
3
5
3
,

 
 
3
4
7
3
,

 
 
1
5
,

 
 
1
,

 
 
3
2
8
1
,

 
 
6
5
4
,

 
 
1
6
0
7
7
9
]
,

 
[
1
9
6
,

 
 
3
2
0
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
4
1
4
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
4
8
,

 
 
1
,

 
 
2
0
2
,

 
 
5
,

 
 
7
6
4
,

 
 
2
,

 
 
6
0
6
,

 
 
6
4
,

 
 
1
8
,

 
 
6
0
,

 
 
1
2
4
,

 
 
9
,

 
 
6
,

 
 
1
8
4
,

 
 
1
3
6
,

 
 
8
4
5
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
1
2
1
,

 
 
1
2
4
,

 
 
1
0
5
5
,

 
 
7
4
,

 
 
2
,

 
 
3
5
0
,

 
 
4
,

 
 
2
8
4
,

 
 
2
3
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
8
2
7
,

 
 
1
2
9
,

 
 
6
4
,

 
 
5
,

 
 
9
1
,

 
 
4
,

 
 
9
2
2
,

 
 
5
0
,

 
 
5
1
7
,

 
 
2
0
,

 
 
1
0
9
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
0
4
8
,

 
 
2
0
,

 
 
1
0
9
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
3
2
8
,

 
 
7
6
,

 
 
2
8
,

 
 
2
5
4
,

 
 
2
1
9
,

 
 
3
7
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
5
,

 
 
2
1
9
,

 
 
2
0
,

 
 
2
1
4
,

 
 
5
,

 
 
8
4
,

 
 
2
0
2
,

 
 
1
6
2
8
,

 
 
1
5
0
,

 
 
1
,

 
 
2
1
4
,

 
 
1
5
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
2
7
,

 
 
1
9
6
,

 
 
6
3
1
,

 
 
4
6
]
,

 
[
2
2
1
1
3
,

 
 
8
,

 
 
2
7
,

 
 
7
4
0
,

 
 
1
9
8
9
,

 
 
4
9
,

 
 
5
9
,

 
 
1
5
9
,

 
 
6
8
,

 
 
2
3
4
,

 
 
2
,

 
 
2
0
6
0
,

 
 
2
6
,

 
 
1
5
9
,

 
 
6
8
,

 
 
1
1
2
2
,

 
 
1
5
,

 
 
1
3
7
0
,

 
 
1
6
2
,

 
 
4
6
]
,

 
[
1
1
,
 
5
5
3
4
,
 
2
1
7
,
 
2
0
8
6
]
,

 
[
6
,

 
 
1
2
2
,

 
 
2
,

 
 
2
7
5
,

 
 
9
,

 
 
5
2
,

 
 
8
,

 
 
1
4
,

 
 
6
4
,

 
 
3
4
,

 
 
1
2
1
,

 
 
2
8
,

 
 
5
2
,

 
 
8
,

 
 
6
4
,

 
 
2
1
,

 
 
4
,

 
 
6
1
4
,

 
 
2
8
1
3
,

 
 
5
1
8
,

 
 
6
3
0
8
,

 
 
1
0
7
9
,

 
 
4
4
,

 
 
7
2
,

 
 
1
4
,

 
 
2
1
4
5
,

 
 
2
6
,

 
 
7
,

 
 
6
3
,

 
 
1
3
,

 
 
2
1
4
5
,

 
 
7
5
,

 
 
4
0
,

 
 
3
0
3
,

 
 
6
4
,

 
 
1
0
,

 
 
4
3
2
2
]
,

 
[
1
2
3
3
,

 
 
3
6
3
,

 
 
4
6
4
,

 
 
1
4
,

 
 
1
8
6
,

 
 
7
8
,

 
 
6
,

 
 
1
8
7
,

 
 
3
0
,

 
 
1
4
0
,

 
 
1
5
,

 
 
1
,

 
 
1
2
3
3
,

 
 
3
6
3
,

 
 
1
8
7
3
5
,

 
 
2
6
7
,

 
 
2
6
,

 
 
7
,

 
 
6
5
,

 
 
1
1
,

 
 
4
2
,

 
 
2
7
7
4
,

 
 
1
,

 
 
1
1
9
4
,

 
 
9
2
6
,

 
 
3
,

 
 
1
2
3
3
,

 
 
3
6
3
,

 
 
4
8
7
,

 
 
8
,

 
 
1
7
6
1
,

 
 
5
,

 
 
1
4
,

 
 
1
8
6
,

 
 
7
8
,

 
 
1
,

 
 
1
2
3
3
,

 
 
3
6
3
,

 
 
4
8
7
,

 
 
8
,

 
 
1
6
3
1
,

 
 
3
2
,

 
 
1
,

 
 
1
1
2
6
,

 
 
1
0
5
,

 
 
6
,

 
 
1
0
3
,

 
 
1
9
,

 
 
2
7
5
6
,

 
 
3
7
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
5
,

 
 
7
8
,

 
 
6
,

 
 
1
8
7
,

 
 
3
0
,

 
 
1
3
8
,

 
 
2
0
6
]
,

 
[
7
2
9
1
,

 
 
1
1
4
4
,

 
 
7
2
9
1
,

 
 
3
1
,

 
 
6
1
9
9
,

 
 
4
,

 
 
2
2
2
,

 
 
4
4
8
0
,

 
 
2
,

 
 
5
0
4
7
,

 
 
5
,

 
 
6
0
7
2
,

 
 
1
1
1
7
,

 
 
1
0
,

 
 
2
1
3
8
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
1
9
8
,

 
 
9
,

 
 
5
3
,

 
 
2
4
5
,

 
 
4
5
8
,

 
 
1
2
3
9
6
,

 
 
3
9
7
0
7
,

 
 
4
,

 
 
7
2
9
1
,

 
 
1
7
7
,

 
 
1
7
1
7
5
,

 
 
1
0
,

 
 
1
,

 
 
5
1
4
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
2
0
7
,

 
 
1
7
,

 
 
2
7
,

 
 
8
0
7
4
,

 
 
2
5
,

 
 
4
5
7
,

 
 
3
5
,

 
 
1
,

 
 
8
3
9
,

 
 
3
,

 
 
7
9
7
2
,

 
 
2
5
,

 
 
5
6
1
6
,

 
 
3
,

 
 
6
8
,

 
 
2
1
3
8
,

 
 
7
7
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
6
8
,

 
 
1
7
6
2
,

 
 
1
9
3
,

 
 
1
4
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
1
0
6
,

 
 
7
,

 
 
8
2
,

 
 
5
6
7
,

 
 
1
8
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
3
3
,

 
 
6
9
3
,

 
 
1
,

 
 
1
4
5
,

 
 
6
4
,

 
 
8
,

 
 
2
,

 
 
1
1
4
,

 
 
3
3
7
6
,

 
 
1
1
4
4
,

 
 
2
5
9
5
3
,

 
 
9
,

 
 
7
2
9
1
,

 
 
8
,

 
 
8
8
7
,

 
 
5
,

 
 
1
7
1
5
,

 
 
9
0
4
,

 
 
8
4
,

 
 
5
3
,

 
 
3
9
,

 
 
9
7
,

 
 
1
8
6
,

 
 
1
,

 
 
1
3
2
,

 
 
2
6
1
,

 
 
7
8
4
,

 
 
1
8
,

 
 
1
0
,

 
 
2
0
2
,

 
 
2
6
8
8
,

 
 
6
0
5
,

 
 
4
3
3
,

 
 
1
2
0
,

 
 
8
,

 
 
1
6
5
,

 
 
2
,

 
 
8
2
,

 
 
2
2
0
8
,

 
 
2
7
1
,

 
 
5
7
4
9
,

 
 
6
0
,

 
 
4
5
,

 
 
4
5
8
,

 
 
1
5
4
,

 
 
2
1
2
5
,

 
 
4
,

 
 
7
2
9
1
,

 
 
2
5
,

 
 
4
2
,

 
 
7
5
1
,

 
 
1
5
,

 
 
2
1
3
8
,

 
 
2
6
,

 
 
7
,

 
 
6
5
,

 
 
6
,

 
 
5
6
,

 
 
4
1
1
,

 
 
6
0
,

 
 
6
1
,

 
 
3
5
5
8
,

 
 
3
3
9
,

 
 
5
6
7
,

 
 
1
7
,

 
 
2
7
5
3
,

 
 
2
0
9
,

 
 
4
7
,

 
 
2
7
0
,

 
 
7
2
9
1
,

 
 
1
0
,

 
 
1
,

 
 
5
1
4
,

 
 
4
6
5
,

 
 
2
6
6
0
,

 
 
4
0
,

 
 
3
,

 
 
6
8
,

 
 
6
1
4
,

 
 
6
2
5
8
,

 
 
5
,

 
 
1
6
1
5
1
,

 
 
6
9
8
4
5
,

 
 
1
0
,

 
 
4
7
,

 
 
2
7
0
,

 
 
5
4
,

 
 
5
3
,

 
 
8
4
,

 
 
4
5
2
2
,

 
 
1
5
,

 
 
5
1
9
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
4
9
7
6
,

 
 
2
0
2
4
,

 
 
2
1
3
8
,

 
 
3
1
4
,

 
 
1
3
3
,

 
 
2
,

 
 
1
2
2
6
,

 
 
6
8
,

 
 
5
4
3
5
4
,

 
 
1
8
1
7
,

 
 
8
0
2
,

 
 
6
3
5
3
,

 
 
6
3
5
3
,

 
 
2
2
1
1
4
,

 
 
9
3
0
6
,

 
 
8
,

 
 
4
,

 
 
4
2
7
9
,

 
 
3
,

 
 
6
1
4
,

 
 
1
1
9
5
6
,

 
 
1
0
5
0
8
,

 
 
7
7
7
8
,

 
 
1
0
5
0
8
,

 
 
6
7
0
8
,

 
 
8
,

 
 
4
,

 
 
6
1
4
,

 
 
2
1
3
8
,

 
 
1
6
0
7
8
0
,

 
 
1
6
0
7
8
1
,

 
 
2
5
,

 
 
9
4
3
,

 
 
1
6
0
7
8
2
,

 
 
8
,

 
 
4
,

 
 
6
3
5
3
,

 
 
2
1
3
8
,

 
 
3
0
8
3
3
,

 
 
1
0
2
0
,

 
 
1
2
,

 
 
5
3
7
6
,

 
 
1
5
8
8
,

 
 
3
1
,

 
 
1
,

 
 
4
9
7
6
,

 
 
2
,

 
 
1
1
9
6
,

 
 
5
,

 
 
8
8
5
,

 
 
6
9
8
9
,

 
 
4
7
4
2
,

 
 
4
7
4
2
,

 
 
9
4
3
,

 
 
4
6
7
,

 
 
1
7
,

 
 
4
9
7
6
,

 
 
4
7
4
2
,

 
 
6
2
5
8
,

 
 
7
6
5
,

 
 
3
2
5
2
,

 
 
7
6
5
,

 
 
5
,

 
 
3
2
5
2
,

 
 
2
1
3
8
,

 
 
8
,

 
 
4
,

 
 
4
1
5
9
,

 
 
3
,

 
 
2
1
3
8
,

 
 
5
5
3
8
,

 
 
4
7
4
2
,

 
 
5
5
3
8
,

 
 
4
7
4
2
,

 
 
8
,

 
 
4
,

 
 
4
1
5
9
,

 
 
3
,

 
 
3
2
5
2
,

 
 
2
1
3
8
,

 
 
9
1
3
,

 
 
1
2
0
,

 
 
1
7
,

 
 
1
2
3
9
6
,

 
 
3
9
7
0
7
,

 
 
8
,

 
 
4
,

 
 
8
0
9
,

 
 
2
2
2
,

 
 
5
3
,

 
 
5
6
,

 
 
2
5
8
,

 
 
2
8
4
,

 
 
1
2
6
2
,

 
 
2
,

 
 
3
8
,

 
 
5
2
,

 
 
2
8
6
,

 
 
8
,

 
 
1
,

 
 
1
4
9
4
,

 
 
3
,

 
 
6
8
,

 
 
1
4
2
,

 
 
5
,

 
 
6
8
,

 
 
7
1
6
,

 
 
6
0
4
3
,

 
 
5
6
5
,

 
 
4
1
,

 
 
8
,

 
 
2
6
1
,

 
 
3
8
9
,

 
 
2
,

 
 
4
9
7
7
,

 
 
1
5
4
,

 
 
6
0
5
,

 
 
5
3
,

 
 
5
9
,

 
 
1
0
8
,

 
 
2
,

 
 
3
2
1
2
,

 
 
5
5
,

 
 
7
0
8
,

 
 
3
,

 
 
2
0
1
8
,

 
 
5
3
8
,

 
 
2
2
,

 
 
5
3
,

 
 
1
8
,

 
 
2
,

 
 
6
7
6
,

 
 
3
8
,

 
 
5
2
,

 
 
2
8
6
,

 
 
3
5
,

 
 
8
2
9
,

 
 
2
3
8
,

 
 
8
4
,

 
 
5
3
,

 
 
1
0
7
6
,

 
 
2
4
5
,

 
 
1
9
,

 
 
4
,

 
 
1
1
9
7
,

 
 
1
2
6
7
,

 
 
1
2
,

 
 
1
3
,

 
 
2
5
,

 
 
5
3
,

 
 
7
0
9
,

 
 
2
8
,

 
 
2
,

 
 
5
8
5
3
,

 
 
2
5
,

 
 
1
4
8
9
5
,

 
 
1
3
,

 
 
8
,

 
 
7
8
,

 
 
9
3
5
4
,

 
 
1
8
,

 
 
1
5
8
1
,

 
 
2
,

 
 
1
1
9
7
,

 
 
1
1
2
8
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
7
,

 
 
6
5
,

 
 
1
0
,

 
 
1
3
,

 
 
1
9
8
,

 
 
4
1
,

 
 
8
,

 
 
1
1
9
7
,

 
 
5
,

 
 
8
2
1
5
,

 
 
3
8
9
,

 
 
9
,

 
 
8
2
5
,

 
 
8
2
9
,

 
 
4
,

 
 
7
2
9
1
,

 
 
8
,

 
 
2
7
5
2
,

 
 
5
,

 
 
3
7
4
,

 
 
5
2
,

 
 
8
,

 
 
4
,

 
 
9
4
8
,

 
 
7
2
9
1
,

 
 
9
,

 
 
3
0
8
3
4
,

 
 
1
4
9
9
,

 
 
9
4
8
,

 
 
9
1
0
,

 
 
3
9
0
,

 
 
5
4
,

 
 
8
,

 
 
6
0
5
,

 
 
4
,

 
 
1
0
2
,

 
 
1
1
5
,

 
 
4
1
3
7
,

 
 
5
,

 
 
3
6
,

 
 
1
0
4
,

 
 
5
2
6
7
,

 
 
9
,

 
 
1
0
4
,

 
 
2
7
1
,

 
 
9
3
,

 
 
1
,

 
 
3
4
3
,

 
 
4
8
0
,

 
 
8
7
8
1
,

 
 
9
9
0
,

 
 
1
3
3
,

 
 
2
,

 
 
5
4
3
5
4
,

 
 
1
8
1
7
,

 
 
3
5
,

 
 
2
9
,

 
 
3
0
,

 
 
1
4
8
9
6
,

 
 
5
3
9
0
,

 
 
1
5
4
8
2
,

 
 
1
,

 
 
6
1
4
,

 
 
5
4
1
9
,

 
 
3
,

 
 
1
,

 
 
1
1
9
5
6
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
1
7
4
6
1
,

 
 
3
2
,

 
 
2
1
3
8
,

 
 
1
0
0
6
,

 
 
3
2
5
2
,

 
 
1
7
4
0
,

 
 
1
4
4
,

 
 
3
0
,

 
 
2
4
4
5
,

 
 
1
2
0
7
8
,

 
 
7
,

 
 
4
1
6
,

 
 
3
0
,

 
 
1
7
6
2
,

 
 
1
7
,

 
 
4
,

 
 
1
7
6
7
,

 
 
2
3
8
3
6
,

 
 
5
,

 
 
4
7
2
8
,

 
 
2
,

 
 
4
7
6
8
,

 
 
2
1
3
8
,

 
 
5
1
0
,

 
 
8
5
,

 
 
3
3
0
,

 
 
3
0
,

 
 
1
4
2
,

 
 
6
4
,

 
 
3
3
,

 
 
5
4
3
5
4
,

 
 
1
8
1
7
,

 
 
7
,

 
 
1
9
,

 
 
3
9
1
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
5
4
6
5
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
1
3
0
,

 
 
2
0
0
,

 
 
5
9
0
,

 
 
1
5
,

 
 
2
1
3
8
,

 
 
5
4
3
5
4
,

 
 
1
8
1
7
,

 
 
1
,

 
 
3
1
4
,

 
 
9
,

 
 
3
9
7
0
7
,

 
 
8
9
8
4
,

 
 
4
2
,

 
 
1
,

 
 
2
0
2
1
2
,

 
 
1
,

 
 
1
9
8
8
,

 
 
5
,

 
 
1
3
2
,

 
 
1
2
0
8
,

 
 
4
9
7
6
,

 
 
2
0
2
4
,

 
 
1
0
,

 
 
1
,

 
 
2
4
4
,

 
 
1
6
0
7
8
3
,

 
 
5
9
0
,

 
 
3
1
4
,

 
 
9
,

 
 
5
2
,

 
 
8
,

 
 
6
9
8
4
6
,

 
 
2
,

 
 
1
0
4
8
,

 
 
1
6
9
0
2
,

 
 
3
9
1
,

 
 
1
1
1
7
,

 
 
1
0
,

 
 
1
,

 
 
9
9
5
,

 
 
3
,

 
 
2
1
3
8
,

 
 
1
0
0
6
,

 
 
5
7
6
9
,

 
 
6
0
9
3
,

 
 
1
6
0
8
,

 
 
1
6
0
7
8
4
,

 
 
4
,

 
 
4
0
9
4
,

 
 
9
4
6
,

 
 
3
,

 
 
5
5
3
8
,

 
 
4
7
4
2
,

 
 
5
,

 
 
2
4
8
,

 
 
1
,

 
 
4
3
7
4
,

 
 
4
,

 
 
4
2
1
8
,

 
 
1
1
9
0
,

 
 
2
,

 
 
5
3
7
6
,

 
 
5
,

 
 
2
7
6
9
9
,

 
 
5
4
,

 
 
1
8
,

 
 
1
4
9
,

 
 
3
,

 
 
6
8
,

 
 
5
8
,

 
 
2
5
0
6
,

 
 
3
7
4
2
5
,

 
 
1
3
5
,

 
 
1
,

 
 
3
3
5
1
,

 
 
1
1
9
5
6
,

 
 
1
1
9
7
,

 
 
5
3
7
6
,

 
 
1
,

 
 
1
9
8
,

 
 
1
2
,

 
 
8
3
6
5
1
,

 
 
1
,

 
 
7
2
9
,

 
 
1
9
8
2
,

 
 
2
3
,

 
 
7
8
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
7
2
9
1
,

 
 
8
2
6
,

 
 
4
,

 
 
6
3
9
,

 
 
2
,

 
 
2
5
4
,

 
 
3
5
,

 
 
3
0
,

 
 
6
7
7
8
,

 
 
7
5
1
0
,

 
 
1
2
,

 
 
9
6
9
5
,

 
 
2
1
3
8
,

 
 
2
7
,

 
 
1
1
9
9
,

 
 
2
,

 
 
2
1
3
8
,

 
 
8
6
8
,

 
 
2
2
3
,

 
 
8
2
6
,

 
 
4
4
3
,

 
 
2
3
6
0
,

 
 
3
2
,

 
 
3
9
7
0
7
,

 
 
2
4
3
1
,

 
 
1
2
4
1
,

 
 
4
9
7
6
,

 
 
3
3
4
5
,

 
 
1
4
5
9
,

 
 
7
4
8
,

 
 
6
5
6
,

 
 
4
3
7
4
,

 
 
1
0
4
5
,

 
 
4
7
4
2
,

 
 
5
,

 
 
1
6
8
5
,

 
 
6
2
2
,

 
 
5
4
3
5
5
,

 
 
4
9
7
6
,

 
 
2
5
4
,

 
 
4
5
4
7
,

 
 
8
2
6
,

 
 
4
2
3
8
0
,

 
 
6
2
2
,

 
 
2
8
4
,

 
 
4
9
7
6
,

 
 
2
5
4
,

 
 
4
1
9
,

 
 
6
9
8
4
7
,

 
 
8
9
3
7
,

 
 
1
2
,

 
 
5
3
7
,

 
 
3
3
7
1
,

 
 
3
2
,

 
 
4
,

 
 
4
9
7
6
,

 
 
3
2
4
9
,

 
 
8
2
6
,

 
 
9
6
9
,

 
 
4
,

 
 
4
9
7
6
,

 
 
3
7
9
,

 
 
4
7
5
4
,

 
 
1
,

 
 
6
6
4
,

 
 
4
9
7
6
,

 
 
6
1
4
,

 
 
2
3
6
3
,

 
 
5
,

 
 
1
1
9
6
,

 
 
6
5
5
2
,

 
 
3
,

 
 
9
6
9
,

 
 
8
2
6
,

 
 
3
2
9
6
,

 
 
1
9
8
7
,

 
 
3
1
2
,

 
 
1
6
0
5
,

 
 
2
4
3
,

 
 
9
2
3
,

 
 
8
5
2
,

 
 
1
6
0
7
8
5
,

 
 
2
6
8
7
,

 
 
2
1
3
8
,

 
 
1
0
6
6
2
1
]
,

 
[
1
1
3
,

 
 
6
5
9
,

 
 
1
1
1
2
,

 
 
8
4
4
,

 
 
2
5
0
7
,

 
 
1
,

 
 
1
1
1
2
,

 
 
8
4
4
,

 
 
2
6
7
,

 
 
3
,

 
 
1
,

 
 
6
4
5
,

 
 
6
5
9
,

 
 
2
5
0
7
,

 
 
4
2
,

 
 
5
7
,

 
 
5
9
2
,

 
 
6
,

 
 
8
7
,

 
 
1
5
6
,

 
 
1
,

 
 
2
5
0
7
,

 
 
2
3
6
,

 
 
1
,

 
 
1
2
9
6
,

 
 
1
0
,

 
 
5
4
,

 
 
6
0
2
,

 
 
4
6
4
,

 
 
4
5
,

 
 
1
6
,

 
 
4
8
9
9
,

 
 
2
,

 
 
6
,

 
 
2
5
,

 
 
8
6
0
4
,

 
 
3
1
,

 
 
1
3
,

 
 
3
1
3
1
,

 
 
3
2
,

 
 
4
5
1
,

 
 
1
,

 
 
1
6
9
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
2
7
,

 
 
4
0
5
,

 
 
1
2
,

 
 
1
6
8
1
,

 
 
1
,

 
 
2
5
0
7
,

 
 
5
0
,

 
 
3
1
7
,

 
 
4
,

 
 
3
7
7
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
4
8
2
,

 
 
1
2
9
,

 
 
4
6
,

 
 
2
5
2
,

 
 
7
0
7
2
]
,

 
[
1
4
2
9
,

 
 
1
0
3
9
,

 
 
1
0
2
4
,

 
 
7
1
4
,

 
 
2
1
6
,

 
 
4
4
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
9
1
,

 
 
2
6
0
0
,

 
 
2
8
9
,

 
 
1
6
0
7
8
6
,

 
 
1
6
0
7
8
7
,

 
 
5
7
2
,

 
 
3
1
6
,

 
 
6
1
,

 
 
4
1
0
,

 
 
4
,

 
 
1
5
5
0
,

 
 
3
,

 
 
7
6
3
6
,

 
 
4
,

 
 
9
0
1
,

 
 
3
2
1
,

 
 
2
1
3
,

 
 
1
5
4
,

 
 
1
,

 
 
4
7
,

 
 
2
3
9
2
,

 
 
1
6
4
1
,

 
 
2
6
0
0
,

 
 
6
9
8
4
8
,

 
 
7
,

 
 
1
8
6
8
,

 
 
6
,

 
 
1
2
5
6
,

 
 
1
1
,

 
 
1
0
5
8
5
,

 
 
5
,

 
 
2
0
3
3
,

 
 
8
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
9
4
,

 
 
6
,

 
 
2
1
5
,

 
 
1
5
9
,

 
 
4
,

 
 
2
4
4
7
0
,

 
 
5
,

 
 
2
6
9
,

 
 
1
5
7
,

 
 
8
0
,

 
 
1
6
4
,

 
 
2
1
0
7
,

 
 
3
9
7
0
8
,

 
 
6
8
4
,

 
 
6
,

 
 
4
5
,

 
 
1
3
6
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
1
1
7
4
,

 
 
5
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
2
3
3
3
,

 
 
2
,

 
 
1
5
9
,

 
 
4
,

 
 
2
4
4
7
0
,

 
 
7
,

 
 
1
9
,

 
 
4
4
6
,

 
 
2
4
1
,

 
 
3
,

 
 
1
,

 
 
7
0
8
,

 
 
3
1
,

 
 
9
,

 
 
1
0
7
,

 
 
6
2
,

 
 
4
2
,

 
 
1
4
4
,

 
 
5
7
,

 
 
2
9
7
7
,

 
 
3
3
,

 
 
1
,

 
 
1
0
2
,

 
 
3
0
8
,

 
 
1
4
,

 
 
1
0
,

 
 
1
3
,

 
 
4
2
4
,

 
 
9
4
0
,

 
 
2
0
0
2
,

 
 
1
0
6
2
,

 
 
8
5
2
,

 
 
8
5
2
,

 
 
9
5
5
]
,

 
[
6
,
 
2
6
6
,
 
2
2
,
 
6
,
 
5
9
,
 
9
2
5
8
,
 
1
,
 
2
9
,
 
6
7
0
9
,
 
8
3
6
5
2
,
 
7
,
 
4
5
,
 
6
]
,

 
[
6
3
,

 
 
7
8
6
,

 
 
8
8
8
4
,

 
 
2
4
2
5
,

 
 
1
5
8
4
,

 
 
1
7
9
,

 
 
2
9
5
9
,

 
 
3
2
,

 
 
4
1
2
,

 
 
5
,

 
 
4
0
7
,

 
 
3
9
7
0
9
,

 
 
8
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
2
,

 
 
6
0
,

 
 
8
5
,

 
 
2
,

 
 
2
6
9
,

 
 
4
8
,

 
 
1
1
,

 
 
2
5
,

 
 
1
4
,

 
 
2
6
,

 
 
2
2
,

 
 
2
8
7
,

 
 
2
0
9
,

 
 
1
1
,

 
 
1
9
,

 
 
4
4
,

 
 
6
7
8
,

 
 
1
8
5
,

 
 
6
6
5
,

 
 
7
2
,

 
 
1
4
,

 
 
4
9
1
6
,

 
 
3
5
,

 
 
3
0
,

 
 
4
9
4
,

 
 
1
4
3
7
3
,

 
 
2
6
9
,

 
 
2
2
1
1
5
]
,

 
[
7
,

 
 
4
8
,

 
 
1
,

 
 
3
1
1
,

 
 
3
3
9
,

 
 
1
5
,

 
 
1
,

 
 
4
5
1
,

 
 
3
4
5
,

 
 
1
7
6
,

 
 
1
6
0
7
8
8
,

 
 
6
4
8
0
,

 
 
2
4
3
,

 
 
9
6
9
,

 
 
2
0
1
7
,

 
 
8
5
0
,

 
 
1
3
9
9
,

 
 
9
6
9
,

 
 
3
2
5
,

 
 
5
3
3
,

 
 
3
2
5
,

 
 
1
3
2
1
6
,

 
 
9
4
2
,

 
 
8
2
5
2
,

 
 
8
6
4
,

 
 
4
5
4
5
,

 
 
2
1
3
6
]
,

 
[
5
7
9
0
,

 
 
2
8
,

 
 
4
2
,

 
 
4
4
,

 
 
8
7
6
,

 
 
1
2
,

 
 
5
3
7
,

 
 
2
8
,

 
 
8
,

 
 
5
1
0
,

 
 
3
,

 
 
1
4
0
2
,

 
 
2
5
,

 
 
1
5
8
9
6
,

 
 
1
5
4
1
,

 
 
9
7
6
,

 
 
9
4
1
4
,

 
 
2
8
,

 
 
4
2
,

 
 
4
4
,

 
 
8
7
6
,

 
 
1
2
,

 
 
1
0
4
5
,

 
 
1
,

 
 
4
5
1
,

 
 
4
1
0
,

 
 
3
,

 
 
2
8
,

 
 
4
1
0
1
,

 
 
2
9
7
0
0
,

 
 
8
3
6
5
3
,

 
 
5
1
1
3
,

 
 
5
5
1
1
,

 
 
1
0
6
6
2
2
,

 
 
1
0
6
6
2
3
,

 
 
1
0
6
6
2
4
,

 
 
5
,

 
 
3
5
3
9
7
,

 
 
1
9
,

 
 
4
0
,

 
 
2
9
9
1
,

 
 
1
3
7
5
5
,

 
 
5
,

 
 
1
6
0
7
8
9
,

 
 
5
7
9
0
,

 
 
9
2
9
,

 
 
6
,

 
 
9
,

 
 
6
,

 
 
4
5
,

 
 
4
0
,

 
 
2
0
6
6
7
,

 
 
7
,

 
 
5
7
9
0
,

 
 
1
,

 
 
4
5
1
,

 
 
4
1
0
,

 
 
3
,

 
 
2
8
,

 
 
4
1
0
1
,

 
 
2
9
7
0
0
,

 
 
8
3
6
5
3
,

 
 
5
1
1
3
,

 
 
5
5
1
1
,

 
 
1
0
6
6
2
2
,

 
 
1
0
6
6
2
3
,

 
 
1
0
6
6
2
4
,

 
 
5
,

 
 
3
5
3
9
7
,

 
 
9
,

 
 
6
,

 
 
4
5
,

 
 
4
0
,

 
 
2
0
6
6
7
,

 
 
7
,

 
 
5
7
9
0
,

 
 
9
,

 
 
1
,

 
 
2
8
,

 
 
4
5
,

 
 
1
0
5
9
,

 
 
2
0
6
6
7
,

 
 
7
,

 
 
6
8
3
4
,

 
 
1
6
6
4
8
,

 
 
3
1
,

 
 
1
,

 
 
3
3
1
6
,

 
 
5
3
7
,

 
 
2
1
9
1
,

 
 
1
6
1
5
2
,

 
 
1
2
,

 
 
6
0
2
2
,

 
 
1
,

 
 
2
6
7
6
4
,

 
 
2
8
,

 
 
4
2
1
,

 
 
2
,

 
 
3
5
0
,

 
 
3
5
,

 
 
1
,

 
 
6
5
6
,

 
 
4
,

 
 
3
8
0
,

 
 
8
4
7
0
,

 
 
3
,

 
 
1
,

 
 
3
3
1
6
,

 
 
2
1
9
1
,

 
 
1
6
1
5
2
,

 
 
4
2
,

 
 
5
7
,

 
 
2
5
5
6
,

 
 
5
,

 
 
3
0
,

 
 
5
7
9
0
,

 
 
1
9
9
,

 
 
8
0
3
,

 
 
1
0
,

 
 
1
0
0
4
4
,

 
 
7
,

 
 
4
5
,

 
 
1
9
9
,

 
 
1
2
7
,

 
 
7
9
,

 
 
2
5
,

 
 
1
5
6
,

 
 
2
5
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
1
5
4
1
,

 
 
2
8
,

 
 
4
2
1
,

 
 
1
7
1
9
,

 
 
3
5
6
,

 
 
3
0
,

 
 
1
0
7
,

 
 
1
4
2
8
,

 
 
5
,

 
 
4
0
,

 
 
1
4
0
,

 
 
6
,

 
 
1
5
4
1
,

 
 
1
3
2
0
,

 
 
7
9
8
,

 
 
3
5
3
9
7
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
1
8
3
7
,

 
 
1
4
1
7
5
,

 
 
1
2
3
0
,

 
 
5
,

 
 
4
,

 
 
1
8
3
8
4
,

 
 
2
,

 
 
1
,

 
 
2
5
4
3
,

 
 
5
,

 
 
6
,

 
 
4
5
8
,

 
 
2
2
5
,

 
 
2
7
,

 
 
7
5
3
,

 
 
1
2
0
4
,

 
 
7
9
8
,

 
 
3
5
3
9
7
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
5
7
9
0
,

 
 
2
,

 
 
2
0
,

 
 
9
8
6
8
,

 
 
4
,

 
 
4
0
0
,

 
 
4
8
,

 
 
6
,

 
 
6
2
,

 
 
4
3
1
,

 
 
8
7
6
,

 
 
9
9
2
,

 
 
8
,

 
 
4
,

 
 
3
1
1
6
,

 
 
1
0
,

 
 
6
8
,

 
 
9
8
6
8
,

 
 
6
,

 
 
1
3
2
0
,

 
 
1
8
,

 
 
1
7
2
9
,

 
 
7
5
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
4
3
2
7
,

 
 
2
,

 
 
1
,

 
 
9
1
4
5
,

 
 
2
4
4
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
9
6
,

 
 
9
9
6
,

 
 
4
1
8
7
,

 
 
6
,

 
 
1
3
2
0
,

 
 
2
4
5
,

 
 
1
6
,

 
 
2
0
4
8
,

 
 
5
7
9
0
]
,

 
[
5
0
1
0
,

 
 
6
,

 
 
4
7
6
,

 
 
2
0
3
,

 
 
2
2
0
,

 
 
1
3
,

 
 
8
3
7
,

 
 
6
,

 
 
1
8
,

 
 
1
3
4
6
,

 
 
3
7
,

 
 
1
4
3
,

 
 
8
9
,

 
 
6
,

 
 
1
8
,

 
 
6
0
9
,

 
 
3
5
,

 
 
1
,

 
 
1
0
3
3
,

 
 
2
,

 
 
1
,

 
 
5
4
6
,

 
 
2
5
,

 
 
6
6
2
5
,

 
 
2
,

 
 
1
,

 
 
6
2
0
,

 
 
1
4
,

 
 
4
9
0
7
,

 
 
1
2
1
8
7
,

 
 
1
4
4
7
,

 
 
8
2
9
,

 
 
1
4
1
,

 
 
1
8
,

 
 
1
4
9
,

 
 
1
0
7
1
,

 
 
2
7
1
,

 
 
2
1
8
,

 
 
5
0
0
,

 
 
7
,

 
 
1
0
3
,

 
 
2
7
5
,

 
 
2
0
,

 
 
3
2
5
4
,

 
 
1
4
4
,

 
 
1
0
3
1
,

 
 
9
3
0
4
,

 
 
6
5
,

 
 
9
,

 
 
4
9
0
7
,

 
 
1
2
1
8
7
,

 
 
1
4
4
7
,

 
 
8
,

 
 
1
,

 
 
3
2
1
8
3
,

 
 
7
2
8
,

 
 
4
9
,

 
 
3
5
8
,

 
 
1
1
8
,

 
 
1
5
3
6
,

 
 
1
2
7
9
,

 
 
3
3
1
,

 
 
2
1
8
6
]
,

 
[
1
0
8
9
,

 
 
1
5
2
8
1
,

 
 
6
5
0
,

 
 
3
8
,

 
 
1
0
6
7
,

 
 
7
0
,

 
 
3
8
,

 
 
4
,

 
 
8
3
6
5
4
,

 
 
8
,

 
 
9
7
9
3
,

 
 
7
6
3
,

 
 
2
3
6
7
,

 
 
2
8
7
7
,

 
 
6
7
2
7
,

 
 
2
2
5
3
]
,

 
[
5
,

 
 
7
,

 
 
5
9
,

 
 
1
0
8
,

 
 
2
,

 
 
8
2
,

 
 
1
1
,

 
 
1
2
7
,

 
 
7
,

 
 
5
9
,

 
 
2
7
5
,

 
 
7
8
,

 
 
3
2
1
8
4
,

 
 
7
2
2
7
,

 
 
1
5
,

 
 
1
0
6
6
2
5
,

 
 
7
,

 
 
1
0
3
,

 
 
1
9
,

 
 
5
4
1
,

 
 
2
,

 
 
1
5
4
,

 
 
2
0
9
,

 
 
5
5
,

 
 
6
1
,

 
 
3
8
7
,

 
 
3
5
2
,

 
 
5
2
,

 
 
4
3
,

 
 
1
9
,

 
 
1
3
9
8
,

 
 
1
1
,

 
 
3
8
2
,

 
 
3
,

 
 
1
0
6
6
2
5
]
,

 
[
1
1
9
,

 
 
3
,

 
 
1
9
2
1
,

 
 
1
2
1
3
,

 
 
5
7
3
,

 
 
2
8
9
,

 
 
3
3
,

 
 
2
6
8
,

 
 
2
,

 
 
4
4
6
1
,

 
 
1
,

 
 
3
9
7
0
,

 
 
6
2
,

 
 
6
2
4
,

 
 
6
0
6
,

 
 
3
2
2
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
7
0
,

 
 
6
,

 
 
2
5
3
9
,

 
 
2
,

 
 
2
1
3
,

 
 
3
0
,

 
 
3
5
1
,

 
 
1
2
7
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
2
6
9
,

 
 
2
,

 
 
2
8
,

 
 
3
0
6
,

 
 
3
0
3
,

 
 
6
9
,

 
 
7
,

 
 
1
9
,

 
 
1
6
3
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
4
,

 
 
3
0
0
,

 
 
1
7
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
6
,

 
 
1
9
,

 
 
1
4
3
3
,

 
 
1
2
7
,

 
 
1
0
,

 
 
2
1
7
1
,

 
 
2
,

 
 
4
4
6
1
,

 
 
3
7
,

 
 
5
,

 
 
5
8
5
2
,

 
 
2
,

 
 
5
2
5
,

 
 
1
,

 
 
1
6
0
7
9
0
,

 
 
7
8
,

 
 
3
4
,

 
 
6
,

 
 
1
1
1
3
5
,

 
 
4
9
0
1
,

 
 
3
2
2
,

 
 
1
2
1
3
,

 
 
3
,

 
 
1
5
0
8
,

 
 
1
4
8
2
,

 
 
5
,

 
 
3
5
6
,

 
 
8
8
,

 
 
4
0
,

 
 
6
,

 
 
9
0
,

 
 
2
4
,

 
 
3
0
0
1
,

 
 
1
0
3
3
,

 
 
2
,

 
 
6
0
,

 
 
1
0
8
0
6
,

 
 
7
7
1
0
,

 
 
3
7
5
2
,

 
 
5
,

 
 
1
,

 
 
2
2
2
,

 
 
6
,

 
 
4
2
8
7
,

 
 
1
0
,

 
 
2
7
,

 
 
9
0
3
,

 
 
2
,

 
 
2
1
3
,

 
 
3
7
,

 
 
8
,

 
 
1
0
6
9
,

 
 
1
6
0
7
9
1
,

 
 
4
4
,

 
 
4
1
,

 
 
8
,

 
 
1
4
,

 
 
2
7
9
8
,

 
 
1
7
0
2
,

 
 
8
,

 
 
4
1
,

 
 
7
,

 
 
1
9
,

 
 
1
3
1
,

 
 
4
,

 
 
5
5
2
,

 
 
7
3
8
,

 
 
3
,

 
 
2
0
,

 
 
1
4
3
3
,

 
 
9
8
6
9
,

 
 
4
1
5
2
,

 
 
1
8
8
9
,

 
 
2
,

 
 
8
6
1
2
,

 
 
3
7
,

 
 
5
,

 
 
1
9
1
9
,

 
 
8
8
,

 
 
1
4
8
,

 
 
2
,

 
 
1
,

 
 
2
2
6
4
1
]
,

 
[
1
3
4
,
 
6
,
 
7
,
 
4
9
,
 
5
7
7
,
 
2
,
 
1
1
7
,
 
1
1
]
,

 
[
1
0
1
,

 
 
6
,

 
 
1
9
9
,

 
 
2
8
8
7
,

 
 
3
0
,

 
 
2
1
4
,

 
 
3
5
,

 
 
2
0
,

 
 
4
9
4
,

 
 
2
0
7
8
,

 
 
3
3
,

 
 
4
6
,

 
 
5
9
1
7
,

 
 
8
2
4
,

 
 
7
7
7
9
,

 
 
9
5
8
0
,

 
 
2
0
8
1
,

 
 
4
8
6
6
,

 
 
1
3
2
5
,

 
 
2
5
6
4
,

 
 
3
9
,

 
 
7
,

 
 
8
5
9
,

 
 
3
1
,

 
 
2
0
,

 
 
1
1
6
2
,

 
 
3
3
8
,

 
 
9
,

 
 
2
0
,

 
 
2
0
7
8
,

 
 
8
,

 
 
2
,

 
 
4
7
1
,

 
 
1
1
1
4
,

 
 
1
6
0
7
9
2
,

 
 
1
1
9
1
,

 
 
8
3
,

 
 
7
2
,

 
 
1
5
,

 
 
8
8
6
,

 
 
1
7
,

 
 
5
2
4
1
,

 
 
1
3
,

 
 
1
0
3
,

 
 
1
6
,

 
 
6
1
1
,

 
 
2
6
,

 
 
8
1
,

 
 
1
4
,

 
 
3
5
4
0
,

 
 
3
3
,

 
 
1
3
,

 
 
8
5
,

 
 
2
,

 
 
3
4
,

 
 
5
5
,

 
 
9
5
9
,

 
 
1
4
2
,

 
 
1
5
,

 
 
1
1
,

 
 
1
7
,

 
 
7
2
,

 
 
8
8
3
2
,

 
 
1
1
0
,

 
 
1
5
5
,

 
 
4
7
7
1
,

 
 
1
4
3
,

 
 
8
9
,

 
 
6
3
1
,

 
 
4
6
]
,

 
[
1
8
7
3
6
,

 
 
4
9
7
,

 
 
1
8
0
,

 
 
1
1
2
8
,

 
 
8
0
,

 
 
2
,

 
 
8
2
,

 
 
5
,

 
 
7
6
8
,

 
 
1
6
9
,

 
 
1
6
2
,

 
 
8
,

 
 
1
1
,

 
 
8
2
3
,

 
 
1
0
,

 
 
1
,

 
 
7
3
2
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
6
1
1
,

 
 
3
2
1
8
5
,

 
 
2
9
3
1
,

 
 
1
4
5
3
,

 
 
3
2
1
,

 
 
1
6
0
,

 
 
8
,

 
 
1
1
,

 
 
4
,

 
 
8
2
1
6
,

 
 
1
6
9
,

 
 
5
,

 
 
6
7
4
,

 
 
2
,

 
 
3
0
7
,

 
 
9
1
,

 
 
4
,

 
 
8
2
1
6
,

 
 
1
6
9
,

 
 
2
3
3
,

 
 
4
3
3
,

 
 
1
6
9
,

 
 
5
6
,

 
 
1
6
,

 
 
4
1
9
,

 
 
1
5
,

 
 
1
0
4
,

 
 
3
7
4
3
,

 
 
2
0
9
,

 
 
1
,

 
 
4
5
1
,

 
 
4
2
7
,

 
 
1
7
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
7
6
8
,

 
 
2
2
4
,

 
 
1
0
,

 
 
2
7
,

 
 
2
3
,

 
 
9
3
5
5
,

 
 
8
0
6
,

 
 
2
8
9
9
,

 
 
5
6
,

 
 
6
6
1
,

 
 
1
7
7
6
8
,

 
 
8
0
,

 
 
1
0
,

 
 
8
9
3
,

 
 
3
5
,

 
 
1
,

 
 
1
2
9
5
9
,

 
 
3
,

 
 
3
1
0
,

 
 
1
1
5
,

 
 
2
2
4
,

 
 
9
7
,

 
 
4
,

 
 
1
2
5
7
,

 
 
1
5
,

 
 
1
,

 
 
8
1
7
,

 
 
1
9
5
2
,

 
 
5
,

 
 
5
6
3
,

 
 
2
1
,

 
 
6
1
,

 
 
2
0
5
,

 
 
7
,

 
 
7
0
1
,

 
 
8
0
5
,

 
 
7
6
8
,

 
 
2
2
4
,

 
 
9
4
5
,

 
 
8
0
,

 
 
1
1
,

 
 
1
1
0
9
,

 
 
3
7
,

 
 
9
3
5
,

 
 
2
,

 
 
1
,

 
 
1
0
4
2
,

 
 
2
9
,

 
 
3
,

 
 
1
,

 
 
2
5
6
6
,

 
 
1
0
,

 
 
2
1
4
,

 
 
1
3
,

 
 
1
6
9
,

 
 
1
0
0
,

 
 
1
5
9
,

 
 
3
7
,

 
 
9
3
5
,

 
 
2
,

 
 
1
6
0
7
9
3
,

 
 
2
9
,

 
 
1
5
,

 
 
1
3
,

 
 
6
4
6
,

 
 
5
0
1
,

 
 
4
6
5
9
,

 
 
9
,

 
 
3
9
7
,

 
 
1
3
,

 
 
7
6
8
,

 
 
1
6
9
,

 
 
1
9
8
2
8
,

 
 
2
6
3
,

 
 
9
,

 
 
1
3
,

 
 
2
9
,

 
 
1
0
0
,

 
 
1
2
2
,

 
 
5
8
,

 
 
2
9
5
]
,

 
[
7
9
,

 
 
3
3
6
,

 
 
3
1
,

 
 
1
6
0
7
9
4
,

 
 
6
7
5
,

 
 
9
5
3
,

 
 
9
6
9
,

 
 
4
9
,

 
 
4
,

 
 
1
1
1
0
,

 
 
7
9
,

 
 
1
3
7
,

 
 
1
7
3
,

 
 
1
5
8
9
2
,

 
 
2
,

 
 
1
,

 
 
1
6
1
,

 
 
9
,

 
 
2
6
4
3
,

 
 
3
0
7
7
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
6
0
0
,

 
 
1
7
,

 
 
5
3
,

 
 
1
8
,

 
 
1
,

 
 
4
3
7
,

 
 
1
9
8
8
,

 
 
4
6
8
5
,

 
 
1
4
9
7
,

 
 
4
3
8
,

 
 
1
,

 
 
3
0
7
7
,

 
 
2
5
,

 
 
8
3
6
5
5
,

 
 
1
8
,

 
 
2
4
0
6
,

 
 
1
5
2
8
2
,

 
 
1
0
,

 
 
1
8
2
6
,

 
 
1
5
3
5
,

 
 
5
,

 
 
1
3
4
9
,

 
 
2
5
9
5
,

 
 
1
0
2
9
5
,

 
 
2
4
3
3
,

 
 
1
5
8
9
7
,

 
 
5
,

 
 
1
5
8
9
8
,

 
 
1
2
0
1
,

 
 
5
,

 
 
1
3
4
2
,

 
 
3
,

 
 
2
0
8
7
,

 
 
1
3
7
8
,

 
 
5
1
,

 
 
9
8
2
,

 
 
1
3
8
8
,

 
 
7
5
3
3
,

 
 
2
,

 
 
1
,

 
 
4
6
8
5
,

 
 
3
6
1
,

 
 
7
1
9
,

 
 
4
6
8
5
,

 
 
7
5
,

 
 
2
0
2
0
8
,

 
 
4
7
5
1
,

 
 
9
1
0
,

 
 
1
3
7
2
,

 
 
2
2
5
1
,

 
 
8
4
4
,

 
 
5
1
,

 
 
1
5
8
4
,

 
 
2
,

 
 
7
6
3
7
,

 
 
4
0
2
8
,

 
 
7
2
0
,

 
 
1
8
8
0
,

 
 
7
1
7
2
,

 
 
5
,

 
 
8
8
5
,

 
 
1
0
8
9
5
,

 
 
1
,

 
 
3
5
3
,

 
 
4
6
8
5
,

 
 
3
2
5
9
,

 
 
4
,

 
 
2
9
7
9
,

 
 
1
5
2
8
3
,

 
 
4
2
1
4
,

 
 
4
3
8
,

 
 
3
,

 
 
7
5
,

 
 
4
7
3
,

 
 
9
8
6
,

 
 
6
8
5
3
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
1
5
8
9
2
,

 
 
1
6
0
7
9
5
,

 
 
4
9
4
6
0
,

 
 
1
5
2
8
4
,

 
 
1
6
0
7
9
6
,

 
 
1
9
1
6
,

 
 
2
3
8
3
7
,

 
 
2
5
9
5
4
,

 
 
2
4
4
7
1
,

 
 
1
6
0
7
9
7
,

 
 
8
3
6
5
6
,

 
 
1
6
0
7
9
8
,

 
 
1
6
0
7
9
9
,

 
 
2
5
9
5
5
,

 
 
6
0
8
1
0
,

 
 
1
6
0
8
0
0
,

 
 
1
6
0
8
0
1
,

 
 
1
6
0
8
0
2
,

 
 
1
6
0
8
0
3
,

 
 
5
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
7
,

 
 
6
2
9
,

 
 
1
4
3
7
4
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
1
6
0
8
0
4
,

 
 
1
0
6
6
2
6
,

 
 
3
2
1
8
6
,

 
 
1
6
0
8
0
5
,

 
 
3
7
4
2
6
,

 
 
3
5
3
9
8
,

 
 
1
3
2
1
7
,

 
 
6
9
8
4
9
,

 
 
3
9
7
1
0
,

 
 
5
,

 
 
9
9
3
,

 
 
1
,

 
 
3
9
7
1
1
,

 
 
5
,

 
 
1
2
6
2
8
,

 
 
2
6
7
6
5
,

 
 
1
,

 
 
4
5
9
6
,

 
 
3
8
4
,

 
 
8
0
4
3
,

 
 
2
2
5
1
,

 
 
1
6
0
8
0
6
,

 
 
4
5
9
6
,

 
 
7
6
1
,

 
 
1
0
7
9
,

 
 
3
3
9
3
,

 
 
4
7
5
1
,

 
 
2
3
,

 
 
2
1
0
8
9
,

 
 
2
7
4
7
,

 
 
3
,

 
 
1
,

 
 
5
2
6
9
,

 
 
3
9
7
1
0
,

 
 
9
1
0
,

 
 
2
2
5
1
,

 
 
7
1
0
]
,

 
[
1
1
0
4
,
 
2
4
9
4
,
 
7
8
0
,
 
7
1
,
 
4
9
,
 
5
7
1
,
 
2
5
9
5
6
,
 
2
5
1
1
,
 
6
1
3
]
,

 
[
7
,

 
 
2
7
5
,

 
 
3
8
,

 
 
7
,

 
 
6
3
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
6
3
,

 
 
4
0
4
2
,

 
 
7
,

 
 
6
3
,

 
 
7
7
3
7
,

 
 
1
6
6
4
9
,

 
 
1
3
7
5
6
,

 
 
7
1
,

 
 
1
0
6
6
2
7
,

 
 
2
8
9
,

 
 
1
3
,

 
 
1
6
0
,

 
 
1
6
0
,

 
 
3
6
5
,

 
 
1
0
,

 
 
5
5
,

 
 
9
5
6
,

 
 
4
3
2
1
,

 
 
2
,

 
 
3
5
0
2
,

 
 
6
,

 
 
1
2
6
2
9
,

 
 
4
8
,

 
 
1
1
,

 
 
4
4
,

 
 
1
6
0
8
0
7
,

 
 
1
0
,

 
 
3
5
0
2
,

 
 
4
2
3
8
1
,

 
 
7
2
9
5
,

 
 
6
0
4
8
,

 
 
1
3
9
9
,

 
 
9
4
1
5
]
,

 
[
7
,

 
 
6
5
0
,

 
 
1
6
8
,

 
 
5
9
,

 
 
7
0
,

 
 
1
0
5
0
,

 
 
3
8
5
7
,

 
 
1
1
,

 
 
6
5
1
,

 
 
1
6
8
,

 
 
1
7
1
9
,

 
 
2
,

 
 
3
0
2
9
,

 
 
4
3
7
,

 
 
2
2
,

 
 
1
6
8
,

 
 
1
5
6
,

 
 
2
1
1
4
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
1
7
,

 
 
2
1
5
,

 
 
3
5
,

 
 
1
6
8
]
,

 
[
6
,

 
 
1
9
,

 
 
1
9
9
,

 
 
1
9
2
4
,

 
 
2
5
,

 
 
5
7
,

 
 
1
4
1
7
6
,

 
 
2
1
,

 
 
5
8
7
1
,

 
 
2
1
0
9
0
,

 
 
2
1
3
9
,

 
 
6
,

 
 
1
8
,

 
 
7
,

 
 
8
1
,

 
 
9
7
0
,

 
 
6
,

 
 
2
,

 
 
1
4
,

 
 
8
3
8
6
,

 
 
2
1
,

 
 
1
,

 
 
2
3
,

 
 
3
5
,

 
 
5
8
7
1
,

 
 
2
1
0
9
0
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
2
2
6
2
,

 
 
2
5
,

 
 
5
1
1
2
,

 
 
2
,

 
 
1
5
4
,

 
 
5
6
5
,

 
 
6
,

 
 
1
8
,

 
 
1
6
6
3
,

 
 
9
1
,

 
 
9
8
7
0
,

 
 
3
6
,

 
 
1
2
6
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
5
5
,

 
 
7
0
8
,

 
 
3
,

 
 
1
6
2
0
,

 
 
1
5
,

 
 
1
3
,

 
 
2
1
2
7
,

 
 
6
0
3
,

 
 
1
8
9
2
,

 
 
8
7
8
,

 
 
2
9
4
0
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
2
3
8
5
,

 
 
3
7
1
6
,

 
 
2
2
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
7
4
3
,

 
 
9
4
6
,

 
 
9
,

 
 
4
7
1
1
,

 
 
2
5
1
5
5
,

 
 
6
4
0
6
,

 
 
2
3
8
5
,

 
 
3
7
1
6
,

 
 
8
4
,

 
 
1
,

 
 
4
7
8
,

 
 
2
3
8
5
,

 
 
1
1
7
4
9
,

 
 
5
6
,

 
 
1
6
,

 
 
1
8
7
]
,

 
[
2
8
,
 
1
2
5
3
,
 
1
8
,
 
3
3
1
9
,
 
4
,
 
1
4
6
9
,
 
1
2
6
3
0
,
 
1
6
4
0
1
]
,

 
[
2
2
1
7
,

 
 
7
1
,

 
 
3
0
,

 
 
1
1
1
6
,

 
 
9
,

 
 
1
6
4
,

 
 
9
7
2
,

 
 
2
,

 
 
3
1
6
0
,

 
 
1
5
8
,

 
 
1
5
0
,

 
 
9
7
0
,

 
 
1
,

 
 
1
2
5
3
,

 
 
2
,

 
 
2
1
3
,

 
 
8
8
,

 
 
3
6
,

 
 
4
1
1
,

 
 
1
3
,

 
 
4
,

 
 
5
8
7
,

 
 
5
9
,

 
 
3
5
6
,

 
 
3
0
,

 
 
2
3
4
,

 
 
1
2
7
]
,

 
[
1
0
2
8
,
 
8
4
4
,
 
2
0
,
 
1
9
5
4
,
 
5
,
 
2
3
4
,
 
2
,
 
1
8
,
 
1
4
,
 
1
3
4
7
,
 
5
0
,
 
1
4
2
5
,
 
9
8
7
]
,

 
[
3
3
6
,

 
 
1
2
,

 
 
1
2
1
,

 
 
3
3
6
,

 
 
1
2
,

 
 
1
2
1
,

 
 
1
7
8
,

 
 
1
2
7
,

 
 
1
6
9
5
,

 
 
1
7
,

 
 
8
3
6
5
7
,

 
 
7
,

 
 
1
9
,

 
 
6
5
8
,

 
 
4
,

 
 
1
1
9
7
,

 
 
5
6
1
,

 
 
1
0
5
0
,

 
 
8
7
1
,

 
 
1
5
,

 
 
4
3
0
,

 
 
8
3
,

 
 
4
7
0
,

 
 
2
,

 
 
2
9
0
0
,

 
 
1
3
7
,

 
 
9
9
,

 
 
4
6
4
,

 
 
2
1
,

 
 
2
1
0
,

 
 
1
0
6
6
2
8
,

 
 
5
,

 
 
9
7
9
9
,

 
 
6
2
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
6
4
0
,

 
 
9
,

 
 
3
1
1
2
,

 
 
3
3
2
5
,

 
 
7
5
1
3
,

 
 
1
3
7
,

 
 
2
4
9
2
,

 
 
5
4
1
5
,

 
 
1
5
,

 
 
1
,

 
 
4
5
4
,

 
 
1
3
7
0
,

 
 
3
5
,

 
 
9
2
,

 
 
1
8
1
3
,

 
 
2
,

 
 
2
1
3
,

 
 
7
9
,

 
 
1
0
0
8
,

 
 
5
,

 
 
1
3
3
3
8
,

 
 
8
7
4
,

 
 
4
6
7
5
,

 
 
2
1
,

 
 
7
5
5
,

 
 
7
5
1
3
,

 
 
4
1
3
,

 
 
7
9
5
,

 
 
3
,

 
 
2
8
,

 
 
9
5
2
,

 
 
3
7
4
2
7
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
2
8
,

 
 
1
2
5
3
,

 
 
1
1
8
3
,

 
 
1
7
5
5
,

 
 
1
3
,

 
 
2
5
3
6
,

 
 
1
0
6
6
2
9
,

 
 
1
0
7
,

 
 
6
9
8
5
0
,

 
 
1
3
6
5
,

 
 
6
4
2
6
,

 
 
8
,

 
 
2
7
,

 
 
2
5
8
4
,

 
 
4
1
3
,

 
 
9
6
3
5
,

 
 
6
4
2
6
,

 
 
3
8
9
,

 
 
5
6
7
,

 
 
1
7
,

 
 
7
,

 
 
1
6
7
,

 
 
6
0
8
9
,

 
 
1
5
,

 
 
3
9
7
1
2
,

 
 
4
6
,

 
 
2
9
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
1
1
8
0
,

 
 
1
3
9
0
,

 
 
6
9
,

 
 
3
6
,

 
 
3
1
3
,

 
 
7
,

 
 
8
1
,

 
 
7
5
7
,

 
 
3
3
,

 
 
1
,

 
 
1
1
6
4
,

 
 
7
,

 
 
8
1
,

 
 
4
,

 
 
5
1
8
0
,

 
 
5
,

 
 
1
7
,

 
 
7
,

 
 
1
6
7
,

 
 
2
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
4
0
,

 
 
1
5
,

 
 
4
5
4
,

 
 
1
3
7
0
,

 
 
7
,

 
 
2
1
1
,

 
 
4
8
,

 
 
1
5
8
,

 
 
2
0
9
8
,

 
 
4
,

 
 
3
6
6
,

 
 
7
0
7
3
,

 
 
3
3
,

 
 
4
,

 
 
6
9
8
5
1
,

 
 
2
5
2
9
,

 
 
1
9
7
,

 
 
7
,

 
 
1
5
3
,

 
 
1
6
2
7
,

 
 
2
,

 
 
7
1
1
,

 
 
7
3
,

 
 
7
3
0
,

 
 
2
1
,

 
 
4
,

 
 
3
5
1
4
,

 
 
1
6
9
3
,

 
 
3
,

 
 
3
8
,

 
 
7
,

 
 
7
1
4
0
,

 
 
1
7
,

 
 
2
8
1
,

 
 
6
8
1
,

 
 
1
0
0
8
,

 
 
3
2
,

 
 
1
1
2
,

 
 
6
4
0
,

 
 
7
,

 
 
6
5
8
,

 
 
2
0
8
,

 
 
5
5
2
9
,

 
 
1
3
,

 
 
2
6
7
,

 
 
5
0
5
,

 
 
6
6
,

 
 
1
9
,

 
 
6
7
8
,

 
 
2
1
,

 
 
8
8
,

 
 
4
3
,

 
 
1
1
,

 
 
1
6
,

 
 
4
4
1
,

 
 
2
,

 
 
1
6
1
,

 
 
5
5
,

 
 
6
7
8
,

 
 
1
5
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
6
4
,

 
 
3
6
,

 
 
7
,

 
 
3
9
,

 
 
1
5
2
,

 
 
8
8
,

 
 
2
,

 
 
3
0
,

 
 
5
7
6
,

 
 
2
,

 
 
3
1
4
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
7
5
7
,

 
 
1
7
2
1
,

 
 
1
4
4
,

 
 
6
,

 
 
1
9
,

 
 
5
7
,

 
 
3
1
5
,

 
 
8
0
6
,

 
 
6
,

 
 
2
8
8
,

 
 
7
0
,

 
 
5
8
,

 
 
3
0
9
4
,

 
 
9
3
,

 
 
3
7
,

 
 
3
1
5
,

 
 
6
4
,

 
 
4
3
,

 
 
1
1
,

 
 
1
6
,

 
 
4
4
1
,

 
 
2
,

 
 
6
6
,

 
 
8
1
4
,

 
 
8
8
,

 
 
2
,

 
 
2
1
9
,

 
 
8
8
,

 
 
2
2
,

 
 
3
1
6
1
,

 
 
6
6
,

 
 
9
9
,

 
 
6
7
8
,

 
 
2
1
,

 
 
1
4
1
,

 
 
1
4
9
,

 
 
5
,

 
 
2
2
,

 
 
3
6
,

 
 
1
5
2
,

 
 
1
4
1
,

 
 
2
7
6
6
,

 
 
2
,

 
 
2
0
,

 
 
1
6
1
,

 
 
5
,

 
 
3
7
5
,

 
 
9
4
,

 
 
8
8
,

 
 
2
,

 
 
8
1
4
,

 
 
2
8
7
,

 
 
1
2
5
,

 
 
4
7
,

 
 
2
2
2
,

 
 
1
0
3
,

 
 
1
6
,

 
 
9
6
9
6
,

 
 
2
1
,

 
 
1
8
1
3
,

 
 
3
,

 
 
1
0
8
9
,

 
 
1
,

 
 
1
1
0
0
,

 
 
3
,

 
 
1
3
0
,

 
 
4
5
,

 
 
1
6
,

 
 
5
5
5
,

 
 
1
2
8
,

 
 
5
8
,

 
 
7
8
0
,

 
 
7
,

 
 
4
5
,

 
 
3
2
8
,

 
 
1
5
7
,

 
 
6
4
,

 
 
1
0
,

 
 
4
,

 
 
8
9
7
,

 
 
3
,

 
 
4
9
6
,

 
 
1
9
,

 
 
6
9
9
0
,

 
 
6
4
7
,

 
 
4
8
3
2
,

 
 
6
2
2
4
,

 
 
8
3
4
3
,

 
 
2
2
5
3
]
,

 
[
7
,
 
8
1
,
 
7
2
0
,
 
9
,
 
1
1
,
 
2
4
,
 
7
1
7
3
,
 
5
,
 
1
4
,
 
1
5
8
9
9
,
 
1
4
8
7
,
 
3
,
 
7
4
,
 
1
1
,
 
2
9
8
4
]
,

 
[
7
,
 
7
7
8
,
 
6
,
 
7
,
 
6
2
4
,
 
2
0
6
,
 
1
5
,
 
1
1
,
 
1
2
7
,
 
3
8
,
 
5
8
,
 
3
4
,
 
6
,
 
1
0
8
]
,

 
[
2
8
,

 
 
8
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
6
0
8
0
8
,

 
 
4
2
3
8
2
,

 
 
2
0
,

 
 
3
4
5
,

 
 
3
3
,

 
 
1
,

 
 
2
5
5
,

 
 
8
6
0
,

 
 
1
5
,

 
 
4
,

 
 
1
1
5
,

 
 
5
2
3
8
,

 
 
1
3
5
6
,

 
 
9
2
0
5
,

 
 
3
7
,

 
 
1
3
,

 
 
2
4
,

 
 
1
,

 
 
4
0
7
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
9
,

 
 
6
,

 
 
4
0
1
,

 
 
2
0
,

 
 
3
4
5
,

 
 
1
5
,

 
 
6
,

 
 
6
7
0
,

 
 
7
,

 
 
4
9
,

 
 
1
5
6
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
2
,

 
 
1
6
,

 
 
3
7
1
,

 
 
1
7
1
0
,

 
 
2
1
1
,

 
 
9
,

 
 
1
1
,

 
 
1
0
0
,

 
 
2
9
4
8
,

 
 
5
0
8
,

 
 
4
2
7
,

 
 
1
1
,

 
 
8
,

 
 
4
7
9
2
,

 
 
7
7
5
,

 
 
1
4
4
,

 
 
7
,

 
 
2
2
0
,

 
 
1
,

 
 
5
0
3
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
4
9
8
5
,

 
 
1
1
,

 
 
8
9
,

 
 
4
2
,

 
 
6
1
6
,

 
 
1
0
7
3
,

 
 
1
0
6
,

 
 
5
,

 
 
2
,

 
 
7
0
1
8
,

 
 
1
,

 
 
6
2
7
,

 
 
9
1
0
1
,

 
 
3
2
,

 
 
6
4
8
1
,

 
 
1
1
,

 
 
8
,

 
 
2
6
5
6
,

 
 
3
2
,

 
 
1
,

 
 
1
3
4
6
3
,

 
 
4
2
3
8
3
,

 
 
1
2
0
,

 
 
9
,

 
 
1
,

 
 
5
2
3
8
,

 
 
3
2
2
8
,

 
 
8
,

 
 
1
4
,

 
 
2
7
7
0
0
,

 
 
5
0
,

 
 
4
1
1
,

 
 
1
,

 
 
1
1
0
0
,

 
 
1
3
,

 
 
3
4
5
,

 
 
7
4
7
9
,

 
 
7
5
0
,

 
 
1
7
0
8
,

 
 
4
8
,

 
 
2
9
5
,

 
 
5
0
3
,

 
 
5
,

 
 
6
0
8
1
1
,

 
 
7
3
5
7
,

 
 
3
,

 
 
6
4
0
4
,

 
 
5
6
,

 
 
1
6
,

 
 
7
1
1
9
,

 
 
1
2
,

 
 
5
5
,

 
 
1
8
3
8
5
,

 
 
1
8
5
7
,

 
 
1
0
7
,

 
 
5
,

 
 
9
6
3
6
,

 
 
5
,

 
 
8
2
5
9
,

 
 
1
2
,

 
 
5
5
,

 
 
4
1
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
,

 
 
9
5
7
9
,

 
 
3
2
8
,

 
 
6
9
7
,

 
 
9
,

 
 
6
5
7
,

 
 
5
8
0
,

 
 
6
,

 
 
7
1
6
,

 
 
2
4
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
4
,

 
 
2
7
0
,

 
 
1
2
,

 
 
1
1
,

 
 
1
6
1
5
3
,

 
 
8
,

 
 
8
7
4
,

 
 
1
,

 
 
9
0
4
4
,

 
 
1
0
7
3
,

 
 
1
0
6
,

 
 
9
,

 
 
6
,

 
 
7
1
6
,

 
 
1
2
7
1
,

 
 
5
0
3
,

 
 
5
,

 
 
2
8
1
,

 
 
4
9
4
6
1
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
8
6
,

 
 
4
2
0
,

 
 
2
9
5
,

 
 
3
1
,

 
 
1
0
0
1
,

 
 
4
5
5
6
2
,

 
 
7
8
1
7
,

 
 
1
1
2
0
9
,

 
 
5
5
1
,

 
 
1
5
0
,

 
 
1
,

 
 
4
4
7
,

 
 
9
6
,

 
 
2
2
9
2
,

 
 
5
,

 
 
4
0
,

 
 
4
7
0
,

 
 
2
,

 
 
4
,

 
 
3
2
0
5
,

 
 
7
2
6
,

 
 
3
,

 
 
4
8
4
,

 
 
3
5
,

 
 
1
0
4
,

 
 
3
3
3
8
,

 
 
9
1
,

 
 
1
5
,

 
 
1
,

 
 
9
6
6
,

 
 
3
,

 
 
4
,

 
 
5
7
4
,

 
 
2
7
1
,

 
 
3
1
8
1
,

 
 
1
0
,

 
 
5
5
,

 
 
1
1
3
6
,

 
 
1
4
9
,

 
 
2
9
5
,

 
 
3
1
,

 
 
2
5
5
1
,

 
 
9
7
6
,

 
 
5
3
5
,

 
 
1
1
9
5
1
,

 
 
5
7
8
,

 
 
6
5
7
,

 
 
5
5
1
,

 
 
3
4
5
8
,

 
 
5
,

 
 
2
9
7
0
1
,

 
 
1
0
4
9
,

 
 
2
,

 
 
1
,

 
 
3
2
1
8
7
,

 
 
5
0
3
,

 
 
1
,

 
 
1
0
6
6
3
0
,

 
 
2
4
2
,

 
 
2
9
,

 
 
1
5
,

 
 
6
8
,

 
 
1
1
6
1
,

 
 
1
6
0
7
,

 
 
4
2
1
,

 
 
6
5
7
,

 
 
5
5
1
,

 
 
5
7
1
,

 
 
5
9
2
,

 
 
5
6
8
,

 
 
1
9
1
4
,

 
 
4
2
1
,

 
 
4
,

 
 
7
1
4
,

 
 
5
5
9
8
,

 
 
1
9
2
2
,

 
 
1
0
,

 
 
4
,

 
 
2
8
1
,

 
 
3
4
2
,

 
 
5
,

 
 
9
9
3
,

 
 
2
8
1
,

 
 
2
6
1
,

 
 
7
6
1
,

 
 
1
5
9
2
,

 
 
9
2
8
,

 
 
3
,

 
 
1
,

 
 
1
0
6
6
3
0
,

 
 
1
0
6
4
7
,

 
 
2
,

 
 
6
3
,

 
 
2
6
7
2
,

 
 
1
0
,

 
 
4
,

 
 
2
7
1
,

 
 
3
1
8
1
,

 
 
2
1
,

 
 
1
0
8
0
0
,

 
 
2
7
8
1
,

 
 
1
6
2
,

 
 
4
6
5
,

 
 
3
9
2
,

 
 
9
,

 
 
5
8
1
1
,

 
 
1
0
3
4
,

 
 
6
8
,

 
 
1
1
5
,

 
 
3
1
8
1
,

 
 
2
1
,

 
 
8
8
,

 
 
1
5
5
,

 
 
1
,

 
 
2
4
4
7
2
,

 
 
6
7
8
5
,

 
 
1
2
2
3
,

 
 
1
9
2
2
,

 
 
2
3
3
,

 
 
1
8
2
7
,

 
 
2
5
0
0
,

 
 
2
7
3
,

 
 
5
,

 
 
3
4
7
,

 
 
3
,

 
 
3
9
1
,

 
 
2
7
3
,

 
 
2
7
9
2
,

 
 
7
2
6
2
,

 
 
4
2
3
8
3
,

 
 
6
0
5
,

 
 
4
,

 
 
3
3
6
,

 
 
3
2
,

 
 
1
,

 
 
3
3
3
8
,

 
 
2
,

 
 
4
,

 
 
1
0
1
2
,

 
 
9
9
8
6
,

 
 
3
5
0
,

 
 
4
,

 
 
1
7
4
3
,

 
 
3
,

 
 
3
4
7
,

 
 
9
,

 
 
2
4
,

 
 
1
9
9
,

 
 
5
9
2
,

 
 
4
9
5
,

 
 
5
,

 
 
2
8
5
,

 
 
6
9
5
,

 
 
3
6
,

 
 
6
,

 
 
2
2
9
,

 
 
1
9
,

 
 
1
5
6
,

 
 
1
1
,

 
 
1
4
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
9
6
,

 
 
9
9
3
,

 
 
8
7
0
,

 
 
3
8
9
,

 
 
4
,

 
 
6
7
3
,

 
 
2
8
6
6
1
,

 
 
3
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
0
5
,

 
 
4
4
9
,

 
 
1
5
,

 
 
1
,

 
 
1
5
8
5
,

 
 
3
,

 
 
1
,

 
 
1
1
4
,

 
 
3
6
5
,

 
 
5
3
3
,

 
 
2
0
6
6
8
,

 
 
3
2
,

 
 
1
,

 
 
4
8
0
,

 
 
1
0
,

 
 
1
0
4
,

 
 
1
1
6
1
,

 
 
1
2
8
1
,

 
 
1
0
,

 
 
1
9
5
6
,

 
 
3
,

 
 
1
,

 
 
6
1
6
,

 
 
3
6
3
,

 
 
8
6
,

 
 
1
5
0
,

 
 
1
,

 
 
3
1
8
1
,

 
 
2
2
9
2
,

 
 
5
,

 
 
8
6
,

 
 
1
4
,

 
 
9
6
,

 
 
5
7
0
3
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
,

 
 
4
4
7
,

 
 
5
4
0
,

 
 
1
2
8
,

 
 
4
6
2
,

 
 
7
7
5
,

 
 
3
4
6
,

 
 
1
5
,

 
 
1
1
,

 
 
2
5
,

 
 
2
4
4
7
,

 
 
1
4
9
8
,

 
 
5
1
,

 
 
9
9
,

 
 
3
0
6
8
,

 
 
2
0
7
9
,

 
 
1
4
9
8
,

 
 
2
3
3
,

 
 
8
6
,

 
 
5
3
8
,

 
 
3
,

 
 
2
4
2
,

 
 
7
,

 
 
6
5
,

 
 
8
,

 
 
4
,

 
 
2
8
4
,

 
 
6
1
3
,

 
 
2
4
6
1
,

 
 
3
,

 
 
3
4
7
,

 
 
4
9
9
6
,

 
 
2
1
5
9
3
,

 
 
5
,

 
 
2
5
,

 
 
3
9
1
,

 
 
1
5
,

 
 
3
3
6
,

 
 
2
1
,

 
 
2
0
7
9
,

 
 
3
8
9
,

 
 
3
,

 
 
1
2
1
5
,

 
 
1
6
9
2
,

 
 
5
,

 
 
5
5
1
,

 
 
1
0
,

 
 
4
4
,

 
 
1
1
0
,

 
 
4
7
9
2
,

 
 
7
7
5
,

 
 
2
5
,

 
 
1
0
7
3
,

 
 
1
6
2
,

 
 
2
4
,

 
 
5
7
1
,

 
 
3
9
1
,

 
 
1
6
2
,

 
 
2
4
,

 
 
1
,

 
 
3
9
7
1
3
,

 
 
3
,

 
 
2
8
1
,

 
 
1
6
8
8
,

 
 
1
0
,

 
 
4
,

 
 
2
8
1
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
5
2
1
,

 
 
1
2
8
,

 
 
7
,

 
 
1
0
3
4
,

 
 
1
,

 
 
4
4
7
,

 
 
2
1
,

 
 
8
8
,

 
 
1
0
,

 
 
4
,

 
 
1
2
4
2
,

 
 
1
5
9
2
,

 
 
1
9
2
2
,

 
 
1
6
2
,

 
 
8
,

 
 
1
1
6
1
,

 
 
1
0
7
9
,

 
 
1
4
9
8
,

 
 
3
,

 
 
6
8
,

 
 
7
1
2
0
,

 
 
1
8
5
,

 
 
1
4
,

 
 
9
6
,

 
 
4
8
4
,

 
 
1
2
,

 
 
4
,

 
 
3
0
3
,

 
 
2
5
,

 
 
3
8
9
,

 
 
3
,

 
 
2
1
5
,

 
 
1
2
7
0
,

 
 
4
,

 
 
4
4
3
,

 
 
3
2
,

 
 
1
3
,

 
 
1
0
9
,

 
 
8
,

 
 
3
5
6
9
,

 
 
1
7
5
1
,

 
 
4
9
0
4
,

 
 
1
0
,

 
 
1
7
5
,

 
 
1
1
6
1
,

 
 
1
9
1
4
,

 
 
3
0
5
8
,

 
 
2
0
,

 
 
2
8
9
9
,

 
 
3
,

 
 
1
1
2
,

 
 
3
3
,

 
 
8
6
0
,

 
 
2
4
,

 
 
1
1
,

 
 
8
,

 
 
4
7
9
2
,

 
 
7
7
5
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
2
9
7
0
2
,

 
 
8
0
4
,

 
 
1
0
9
8
,

 
 
6
8
6
,

 
 
2
0
1
4
,

 
 
4
1
,

 
 
8
,

 
 
3
7
4
5
,

 
 
4
7
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
1
0
,

 
 
4
0
,

 
 
3
,

 
 
1
4
1
,

 
 
6
1
6
,

 
 
9
,

 
 
1
,

 
 
3
1
8
1
,

 
 
9
6
,

 
 
1
3
8
1
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
7
0
9
,

 
 
3
9
2
,

 
 
9
,

 
 
1
1
,

 
 
1
3
5
9
,

 
 
1
0
,

 
 
4
,

 
 
1
9
1
4
,

 
 
3
0
5
8
,

 
 
1
5
,

 
 
3
0
8
3
5
,

 
 
5
,

 
 
3
2
1
8
8
,

 
 
5
,

 
 
4
9
,

 
 
4
6
4
1
,

 
 
1
0
4
,

 
 
1
1
4
,

 
 
3
6
5
,

 
 
5
3
3
,

 
 
2
0
6
6
8
,

 
 
2
8
8
,

 
 
1
4
9
9
,

 
 
5
7
1
,

 
 
2
1
8
4
,

 
 
1
5
5
1
,

 
 
4
1
,

 
 
8
,

 
 
2
0
7
9
,

 
 
2
6
1
,

 
 
2
1
2
4
,

 
 
1
2
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
8
5
5
,

 
 
9
,

 
 
1
,

 
 
6
9
5
,

 
 
1
2
4
,

 
 
1
8
,

 
 
3
8
9
,

 
 
3
,

 
 
5
0
3
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
2
9
7
0
2
,

 
 
8
0
4
,

 
 
1
0
9
8
,

 
 
6
8
6
,

 
 
2
0
1
4
,

 
 
5
1
,

 
 
5
9
,

 
 
3
9
2
,

 
 
1
1
,

 
 
2
5
,

 
 
9
6
,

 
 
4
3
5
,

 
 
3
1
,

 
 
4
,

 
 
8
5
,

 
 
1
,

 
 
4
4
7
,

 
 
2
2
9
2
,

 
 
6
2
1
,

 
 
1
8
,

 
 
9
1
0
,

 
 
1
9
7
5
,

 
 
7
3
6
,

 
 
7
4
,

 
 
1
5
,

 
 
1
1
8
7
,

 
 
1
0
3
,

 
 
5
1
,

 
 
4
7
9
2
,

 
 
3
8
9
,

 
 
1
1
,

 
 
9
,

 
 
1
,

 
 
6
1
6
,

 
 
1
0
6
,

 
 
1
8
,

 
 
1
0
7
3
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
2
9
7
0
2
,

 
 
8
0
4
,

 
 
1
0
9
8
,

 
 
6
8
6
,

 
 
2
0
1
4
,

 
 
2
3
3
,

 
 
1
8
,

 
 
5
3
8
,

 
 
9
,

 
 
5
0
,

 
 
3
4
7
,

 
 
3
7
,

 
 
2
4
6
1
,

 
 
8
3
4
,

 
 
5
1
,

 
 
1
8
,

 
 
9
6
,

 
 
7
1
6
,

 
 
2
,

 
 
1
6
,

 
 
2
4
2
,

 
 
2
9
5
,

 
 
1
1
2
8
4
,

 
 
5
,

 
 
4
9
2
9
,

 
 
1
6
2
,

 
 
8
,

 
 
6
8
,

 
 
1
7
0
,

 
 
3
8
3
,

 
 
5
7
1
,

 
 
3
9
1
,

 
 
5
8
6
,

 
 
2
9
,

 
 
1
5
,

 
 
4
,

 
 
1
1
6
1
,

 
 
1
9
1
4
,

 
 
5
8
6
,

 
 
3
2
1
2
,

 
 
9
,

 
 
1
,

 
 
2
8
6
8
,

 
 
3
1
4
,

 
 
1
1
,

 
 
8
,

 
 
2
8
1
,

 
 
2
0
2
1
3
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
2
9
7
0
2
,

 
 
8
0
4
,

 
 
1
0
9
8
,

 
 
6
8
6
,

 
 
2
0
1
4
,

 
 
1
,

 
 
2
9
,

 
 
1
8
1
,

 
 
1
6
1
,

 
 
4
,

 
 
1
6
9
,

 
 
3
6
,

 
 
6
,

 
 
2
2
9
,

 
 
1
9
,

 
 
1
5
4
7
,

 
 
1
,

 
 
7
2
5
,

 
 
3
5
1
,

 
 
6
,

 
 
1
1
7
,

 
 
1
,

 
 
7
1
7
,

 
 
3
2
4
2
,

 
 
1
1
,

 
 
1
,

 
 
2
7
3
,

 
 
4
6
2
6
,

 
 
7
1
6
,

 
 
5
3
2
7
,

 
 
7
6
1
,

 
 
5
,

 
 
1
0
2
3
2
,

 
 
1
6
0
8
0
9
,

 
 
4
,

 
 
4
2
3
,

 
 
3
6
3
7
,

 
 
3
,

 
 
1
0
4
,

 
 
7
4
3
,

 
 
1
2
0
,

 
 
8
0
,

 
 
4
,

 
 
1
6
9
,

 
 
2
4
,

 
 
7
3
6
,

 
 
1
5
,

 
 
3
3
6
,

 
 
1
1
,

 
 
3
0
2
2
,

 
 
7
6
,

 
 
1
6
1
5
4
]
,

 
[
3
1
9
9
,

 
 
1
0
9
,

 
 
3
,

 
 
2
5
9
5
7
,

 
 
3
0
8
3
6
,

 
 
2
,

 
 
9
8
6
7
,

 
 
1
0
6
6
3
1
,

 
 
7
,

 
 
3
3
2
,

 
 
6
,

 
 
8
6
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
1
7
5
8
,

 
 
5
4
,

 
 
2
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
2
7
9
1
,

 
 
6
,

 
 
2
0
3
,

 
 
3
4
,

 
 
1
0
1
,

 
 
9
1
4
6
,

 
 
2
4
8
,

 
 
4
9
5
3
,

 
 
4
5
2
,

 
 
1
6
0
8
1
0
,

 
 
1
6
0
8
1
1
,

 
 
1
6
0
8
1
2
,

 
 
1
6
0
8
1
3
,

 
 
1
6
0
8
1
4
,

 
 
1
0
6
6
3
2
,

 
 
1
6
0
8
1
5
,

 
 
1
0
6
6
3
2
,

 
 
1
6
0
8
1
6
,

 
 
1
6
0
8
1
7
,

 
 
1
6
0
8
1
8
,

 
 
5
,

 
 
8
3
6
5
8
,

 
 
6
9
8
5
2
,

 
 
1
0
6
6
3
3
,

 
 
5
,

 
 
1
6
0
8
1
9
,

 
 
5
,

 
 
1
6
0
8
2
0
,

 
 
5
,

 
 
1
6
0
8
2
1
,

 
 
6
,

 
 
6
3
,

 
 
1
0
6
6
3
3
,

 
 
1
8
,

 
 
3
1
,

 
 
1
6
0
8
2
2
,

 
 
1
4
,

 
 
2
,

 
 
1
6
,

 
 
1
5
0
3
,

 
 
2
1
,

 
 
1
0
6
6
3
4
,

 
 
1
1
5
0
,

 
 
3
,

 
 
2
5
1
5
6
,

 
 
1
0
,

 
 
1
,

 
 
3
1
3
,

 
 
1
3
0
6
,

 
 
2
2
1
,

 
 
2
0
6
6
,

 
 
5
,

 
 
2
4
6
,

 
 
7
3
,

 
 
1
,

 
 
9
8
,

 
 
1
4
2
,

 
 
3
4
8
8
,

 
 
5
2
9
0
,

 
 
5
7
0
2
,

 
 
4
7
5
5
]
,

 
[
5
4
,

 
 
5
1
,

 
 
1
8
,

 
 
1
9
,

 
 
6
,

 
 
4
1
9
,

 
 
9
,

 
 
6
,

 
 
1
9
,

 
 
3
7
4
2
8
,

 
 
4
2
4
5
,

 
 
1
5
5
0
,

 
 
2
,

 
 
1
7
0
0
,

 
 
8
9
2
,

 
 
3
,

 
 
3
0
,

 
 
3
0
0
,

 
 
5
4
,

 
 
7
,

 
 
1
9
,

 
 
3
0
3
5
,

 
 
2
,

 
 
1
3
,

 
 
4
9
3
]
,

 
[
9
0
,
 
6
,
 
5
2
4
2
,
 
1
2
,
 
1
0
6
,
 
1
4
5
5
,
 
2
,
 
1
,
 
2
6
9
0
,
 
3
1
9
4
,
 
4
4
,
 
5
0
2
1
,
 
1
3
9
6
,
 
9
1
4
7
]
,

 
[
6
,

 
 
5
3
9
1
,

 
 
2
0
,

 
 
1
7
0
,

 
 
8
5
,

 
 
1
5
9
,

 
 
1
3
,

 
 
1
1
2
2
,

 
 
2
1
,

 
 
6
,

 
 
3
6
3
9
,

 
 
2
0
,

 
 
8
1
0
,

 
 
7
6
,

 
 
3
,

 
 
2
0
,

 
 
3
4
0
,

 
 
1
6
,

 
 
3
2
5
,

 
 
5
,

 
 
5
9
,

 
 
2
0
8
0
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
2
0
,

 
 
3
0
0
,

 
 
3
5
3
3
,

 
 
3
4
0
,

 
 
1
9
,

 
 
4
,

 
 
5
7
3
,

 
 
3
0
0
,

 
 
4
4
8
7
,

 
 
1
8
3
8
6
]
,

 
[
5
9
8
,

 
 
5
7
2
1
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
5
4
3
5
6
,

 
 
4
5
0
,

 
 
5
4
3
5
7
,

 
 
1
1
0
6
,

 
 
4
6
1
,

 
 
1
8
0
0
,

 
 
9
6
2
,

 
 
2
0
1
4
,

 
 
8
5
0
9
,

 
 
1
1
9
5
7
,

 
 
1
7
7
6
9
,

 
 
2
3
2
3
,

 
 
7
0
7
4
,

 
 
5
0
8
0
,

 
 
1
2
0
,

 
 
6
8
0
,

 
 
5
2
6
8
,

 
 
2
9
7
,

 
 
3
,

 
 
6
4
9
,

 
 
8
6
8
2
,

 
 
6
8
0
,

 
 
7
5
1
4
,

 
 
5
2
6
8
,

 
 
1
6
6
5
0
,

 
 
1
0
1
7
,

 
 
1
6
0
8
2
3
,

 
 
5
8
0
4
,

 
 
2
1
0
9
,

 
 
3
5
9
9
,

 
 
1
0
1
7
,

 
 
1
0
6
6
3
5
,

 
 
1
0
1
7
,

 
 
1
6
0
8
2
4
,

 
 
1
1
7
5
0
,

 
 
1
0
1
7
,

 
 
1
6
0
8
2
5
,

 
 
4
4
0
8
,

 
 
1
3
9
9
,

 
 
9
5
1
7
,

 
 
5
4
3
5
8
,

 
 
8
6
8
2
,

 
 
1
6
0
8
2
6
,

 
 
1
6
1
,

 
 
9
5
1
7
,

 
 
2
1
6
8
,

 
 
1
7
1
8
,

 
 
2
1
6
8
,

 
 
4
3
8
,

 
 
3
,

 
 
9
5
1
7
,

 
 
6
9
8
5
3
,

 
 
1
6
0
8
2
7
,

 
 
3
4
5
3
,

 
 
6
9
9
,

 
 
1
8
7
2
,

 
 
1
0
9
6
,

 
 
4
2
4
,

 
 
1
0
1
7
,

 
 
1
6
0
8
2
8
,

 
 
9
5
8
1
,

 
 
5
2
6
8
,

 
 
3
,

 
 
2
6
5
2
,

 
 
2
4
0
7
,

 
 
4
5
2
,

 
 
2
3
3
,

 
 
1
8
7
2
,

 
 
1
0
6
6
3
6
,

 
 
1
1
9
5
7
,

 
 
1
0
6
6
3
6
,

 
 
1
2
5
8
,

 
 
1
6
0
8
2
9
,

 
 
1
6
0
8
3
0
,

 
 
1
0
6
6
3
5
,

 
 
1
6
0
8
3
1
,

 
 
1
6
0
8
3
2
,

 
 
4
7
4
,

 
 
6
9
8
5
4
,

 
 
1
6
0
8
3
3
,

 
 
1
0
6
6
3
7
,

 
 
1
6
0
8
3
4
,

 
 
8
3
0
4
,

 
 
6
2
2
,

 
 
1
6
0
,

 
 
2
8
8
6
,

 
 
6
8
0
,

 
 
1
0
6
6
3
8
,

 
 
1
6
1
,

 
 
6
1
7
7
,

 
 
2
6
6
7
,

 
 
1
2
5
8
,

 
 
1
6
0
8
3
5
,

 
 
8
3
6
5
9
,

 
 
2
3
3
,

 
 
4
6
1
,

 
 
3
5
9
9
,

 
 
1
6
0
8
3
6
,

 
 
2
0
6
6
9
,

 
 
1
0
0
3
8
,

 
 
1
6
0
8
3
7
,

 
 
2
1
9
7
,

 
 
1
0
6
6
3
9
,

 
 
1
6
0
8
3
8
,

 
 
1
6
0
,

 
 
4
6
1
,

 
 
3
2
0
4
,

 
 
2
7
7
0
1
,

 
 
2
9
4
,

 
 
2
9
4
,

 
 
2
3
3
,

 
 
2
9
4
]
,

 
[
7
,

 
 
6
6
,

 
 
7
7
8
,

 
 
1
5
4
,

 
 
9
,

 
 
3
8
4
8
,

 
 
3
,

 
 
2
0
9
,

 
 
4
1
8
,

 
 
2
3
7
8
,

 
 
1
2
,

 
 
5
6
3
5
,

 
 
1
5
,

 
 
1
7
4
,

 
 
5
,

 
 
7
2
6
3
,

 
 
3
,

 
 
2
3
0
,

 
 
8
8
8
5
,

 
 
4
2
,

 
 
5
7
,

 
 
6
8
1
0
,

 
 
1
0
,

 
 
1
,

 
 
6
2
9
]
,

 
[
1
9
6
,

 
 
3
2
0
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
2
0
,

 
 
4
1
4
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
4
7
,

 
 
6
,

 
 
1
3
1
,

 
 
2
,

 
 
1
6
0
8
3
9
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
4
8
,

 
 
1
,

 
 
2
0
2
,

 
 
5
,

 
 
7
6
4
,

 
 
2
,

 
 
6
0
6
,

 
 
6
4
,

 
 
1
8
,

 
 
6
0
,

 
 
1
2
4
,

 
 
6
,

 
 
1
8
4
,

 
 
4
8
,

 
 
2
,

 
 
6
3
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
1
2
1
,

 
 
1
2
4
,

 
 
1
0
5
5
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
5
,

 
 
7
4
,

 
 
2
,

 
 
2
0
9
1
,

 
 
8
3
,

 
 
7
4
,

 
 
2
,

 
 
4
7
1
,

 
 
2
0
,

 
 
1
1
4
,

 
 
2
3
,

 
 
2
0
9
,

 
 
1
,

 
 
2
3
,

 
 
2
5
1
2
,

 
 
2
2
,

 
 
6
,

 
 
5
4
8
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
6
,

 
 
1
8
,

 
 
1
9
6
,

 
 
2
,

 
 
3
0
7
,

 
 
1
2
9
,

 
 
1
7
7
,

 
 
3
8
5
1
,

 
 
1
0
,

 
 
2
6
,

 
 
1
3
0
,

 
 
2
0
5
,

 
 
1
8
6
8
,

 
 
9
,

 
 
6
,

 
 
4
7
1
,

 
 
2
7
,

 
 
3
8
7
,

 
 
2
9
8
,

 
 
3
6
,

 
 
8
,

 
 
2
0
0
,

 
 
1
6
7
1
,

 
 
4
4
,

 
 
2
4
2
,

 
 
1
0
5
,

 
 
5
,

 
 
1
9
6
0
,

 
 
4
3
0
,

 
 
2
7
2
5
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
1
7
3
7
,

 
 
2
,

 
 
4
7
1
,

 
 
8
3
,

 
 
1
2
,

 
 
4
,

 
 
5
1
0
,

 
 
4
2
8
8
,

 
 
5
,

 
 
7
3
3
,

 
 
3
,

 
 
1
,

 
 
2
7
2
5
,

 
 
9
,

 
 
2
6
9
,

 
 
2
1
,

 
 
8
3
2
,

 
 
2
7
,

 
 
3
8
7
,

 
 
5
0
,

 
 
6
3
,

 
 
1
3
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
7
9
,

 
 
1
7
7
,

 
 
4
,

 
 
7
1
2
,

 
 
2
0
,

 
 
3
3
4
,

 
 
4
5
9
,

 
 
6
1
5
6
,

 
 
7
7
8
0
,

 
 
6
3
0
3
,

 
 
5
6
3
6
,

 
 
8
,

 
 
1
3
3
,

 
 
2
,

 
 
2
0
6
8
,

 
 
6
,

 
 
3
8
2
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
8
2
7
,

 
 
1
2
9
,

 
 
6
4
,

 
 
5
,

 
 
9
1
,

 
 
4
,

 
 
9
2
2
,

 
 
5
0
,

 
 
5
1
7
,

 
 
2
0
,

 
 
2
3
4
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
0
4
8
,

 
 
2
0
,

 
 
3
3
4
,

 
 
4
5
9
,

 
 
2
5
,

 
 
7
1
2
,

 
 
2
2
,

 
 
1
6
4
,

 
 
1
7
6
0
,

 
 
1
0
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
3
2
8
,

 
 
7
6
,

 
 
2
8
,

 
 
2
5
4
,

 
 
2
1
9
,

 
 
1
2
,

 
 
1
2
1
,

 
 
3
3
,

 
 
1
,

 
 
5
0
5
2
,

 
 
2
1
9
,

 
 
3
7
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
5
,

 
 
2
1
9
,

 
 
2
0
,

 
 
2
1
4
,

 
 
5
,

 
 
8
4
,

 
 
2
0
2
,

 
 
1
6
2
8
,

 
 
1
5
0
,

 
 
1
,

 
 
2
1
4
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
1
2
7
,

 
 
1
9
6
,

 
 
2
9
4
,

 
 
1
1
5
7
0
]
,

 
[
6
9
8
5
5
,

 
 
4
9
4
6
2
,

 
 
3
5
7
0
,

 
 
1
2
0
7
9
,

 
 
3
3
6
9
6
,

 
 
7
,

 
 
3
4
,

 
 
1
5
6
2
,

 
 
9
,

 
 
8
0
,

 
 
7
,

 
 
2
1
6
7
,

 
 
2
4
1
8
,

 
 
2
8
,

 
 
7
,

 
 
2
4
,

 
 
1
4
,

 
 
7
4
9
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
4
,

 
 
6
6
2
7
,

 
 
5
3
9
,

 
 
3
,

 
 
7
4
8
,

 
 
2
4
1
3
,

 
 
2
6
,

 
 
8
9
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
7
4
9
,

 
 
3
,

 
 
1
1
,

 
 
7
,

 
 
4
5
,

 
 
9
7
,

 
 
1
,

 
 
4
8
1
,

 
 
1
0
4
3
0
,

 
 
7
,

 
 
2
4
,

 
 
1
8
2
,

 
 
1
,

 
 
6
0
5
,

 
 
2
8
2
4
,

 
 
2
0
4
0
,

 
 
9
,

 
 
2
8
,

 
 
2
4
,

 
 
4
,

 
 
6
1
3
2
,

 
 
1
2
,

 
 
4
7
0
1
,

 
 
4
7
9
,

 
 
7
4
8
,

 
 
5
,

 
 
1
0
5
,

 
 
1
,

 
 
3
3
7
2
,

 
 
9
,

 
 
1
,

 
 
6
9
8
5
5
,

 
 
4
9
4
6
2
,

 
 
6
9
0
,

 
 
8
,

 
 
4
,

 
 
5
2
9
2
,

 
 
7
6
5
,

 
 
3
,

 
 
1
1
6
8
,

 
 
8
,

 
 
1
1
9
4
,

 
 
2
4
3
6
,

 
 
1
7
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
9
1
,

 
 
3
5
,

 
 
1
0
3
4
,

 
 
5
,

 
 
7
6
3
1
,

 
 
1
2
,

 
 
5
8
,

 
 
9
3
,

 
 
5
6
0
,

 
 
2
7
4
,

 
 
3
2
,

 
 
2
3
2
2
,

 
 
5
,

 
 
8
8
5
,

 
 
1
0
9
1
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
2
0
4
5
,

 
 
8
8
5
,

 
 
1
3
4
0
,

 
 
3
,

 
 
1
3
9
1
8
,

 
 
1
,

 
 
1
1
9
5
8
,

 
 
9
5
1
0
,

 
 
1
8
3
2
,

 
 
3
,

 
 
1
3
9
1
8
,

 
 
5
,

 
 
1
3
0
,

 
 
5
8
,

 
 
1
5
5
,

 
 
1
5
9
6
,

 
 
2
,

 
 
4
4
8
,

 
 
6
4
,

 
 
4
1
,

 
 
1
3
8
1
,

 
 
1
0
,

 
 
7
8
3
,

 
 
7
7
3
5
,

 
 
5
9
0
,

 
 
5
,

 
 
3
9
2
9
,

 
 
4
,

 
 
6
3
2
,

 
 
1
0
4
4
,

 
 
3
,

 
 
3
9
1
,

 
 
5
,

 
 
5
8
3
4
,

 
 
1
7
9
,

 
 
1
7
0
4
,

 
 
1
,

 
 
4
9
4
6
2
,

 
 
6
9
0
,

 
 
5
4
,

 
 
7
,

 
 
1
9
,

 
 
2
5
3
9
,

 
 
2
,

 
 
1
5
1
5
,

 
 
5
,

 
 
3
3
5
9
,

 
 
2
0
2
,

 
 
1
0
,

 
 
1
,

 
 
1
1
3
,

 
 
1
6
6
5
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
4
,

 
 
6
9
0
,

 
 
8
,

 
 
1
4
,

 
 
9
0
4
,

 
 
3
2
,

 
 
1
7
3
0
,

 
 
4
9
5
9
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
8
7
0
,

 
 
2
1
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
3
,

 
 
3
0
4
,

 
 
3
,

 
 
3
0
,

 
 
4
1
4
,

 
 
3
8
,

 
 
4
2
,

 
 
7
6
7
6
,

 
 
6
4
,

 
 
8
,

 
 
4
,

 
 
2
9
8
9
,

 
 
3
1
1
,

 
 
3
,

 
 
6
9
1
3
,

 
 
3
,

 
 
2
7
,

 
 
1
0
5
,

 
 
3
1
8
2
,

 
 
3
2
,

 
 
4
,

 
 
9
2
5
9
,

 
 
5
6
2
,

 
 
4
3
8
,

 
 
7
,

 
 
2
6
5
,

 
 
1
2
0
8
0
,

 
 
5
,

 
 
6
8
,

 
 
1
0
4
3
,

 
 
6
2
,

 
 
1
8
,

 
 
6
6
2
5
,

 
 
3
,

 
 
1
,

 
 
1
7
3
0
,

 
 
3
3
5
,

 
 
1
2
0
8
0
,

 
 
2
8
7
2
,

 
 
3
5
,

 
 
1
,

 
 
3
9
0
,

 
 
1
4
9
8
,

 
 
7
,

 
 
1
9
,

 
 
9
4
0
7
,

 
 
2
6
,

 
 
1
3
,

 
 
1
9
9
,

 
 
1
8
6
5
,

 
 
1
0
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
1
1
3
,

 
 
4
1
4
,

 
 
7
,

 
 
1
3
1
,

 
 
5
,

 
 
4
9
4
6
3
,

 
 
3
9
2
,

 
 
3
,

 
 
1
,

 
 
3
9
0
,

 
 
1
4
9
8
,

 
 
5
7
3
5
,

 
 
1
,

 
 
2
5
4
3
,

 
 
2
1
2
,

 
 
1
2
,

 
 
4
9
4
6
3
,

 
 
1
3
4
6
4
,

 
 
1
9
5
4
,

 
 
7
5
0
,

 
 
3
4
3
,

 
 
1
1
3
7
9
,

 
 
1
6
1
7
,

 
 
1
4
8
9
7
,

 
 
7
7
2
,

 
 
8
7
0
,

 
 
8
8
5
,

 
 
8
6
5
,

 
 
8
,

 
 
9
1
,

 
 
2
8
7
0
,

 
 
8
3
6
6
0
,

 
 
3
2
,

 
 
1
2
0
8
0
,

 
 
1
2
,

 
 
2
4
2
,

 
 
6
5
2
,

 
 
1
2
,

 
 
3
1
1
,

 
 
1
,

 
 
3
5
7
0
,

 
 
5
5
6
9
,

 
 
1
4
6
8
,

 
 
2
6
2
6
,

 
 
5
4
,

 
 
2
4
,

 
 
2
9
1
,

 
 
1
0
,

 
 
2
7
,

 
 
1
1
6
5
9
,

 
 
8
3
6
6
1
,

 
 
2
5
4
6
,

 
 
3
2
,

 
 
4
,

 
 
1
4
0
5
,

 
 
8
3
6
6
2
,

 
 
8
9
3
8
,

 
 
5
,

 
 
6
9
0
,

 
 
7
7
8
,

 
 
2
,

 
 
3
7
,

 
 
3
2
,

 
 
4
,

 
 
6
9
8
5
6
,

 
 
9
5
1
0
,

 
 
5
7
1
7
,

 
 
1
9
6
6
,

 
 
8
,

 
 
1
0
2
,

 
 
5
1
1
,

 
 
2
,

 
 
1
,

 
 
7
6
5
,

 
 
3
,

 
 
1
,

 
 
3
5
7
0
,

 
 
4
3
8
6
,

 
 
3
,

 
 
1
7
1
1
,

 
 
1
3
,

 
 
4
4
9
,

 
 
3
,

 
 
7
4
8
,

 
 
1
0
1
0
3
,

 
 
8
,

 
 
1
4
,

 
 
3
8
,

 
 
1
8
0
,

 
 
8
,

 
 
3
5
,

 
 
2
6
,

 
 
7
,

 
 
6
5
0
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
4
6
6
,

 
 
1
7
,

 
 
6
,

 
 
7
5
4
,

 
 
2
,

 
 
1
6
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
4
8
2
,

 
 
2
3
5
,

 
 
1
4
2
6
,

 
 
2
5
,

 
 
1
9
,

 
 
5
7
,

 
 
4
7
2
9
,

 
 
1
0
,

 
 
3
2
,

 
 
1
2
0
8
0
,

 
 
5
,

 
 
6
8
,

 
 
2
3
5
,

 
 
7
4
6
,

 
 
3
,

 
 
1
0
8
9
6
,

 
 
5
4
,

 
 
8
,

 
 
4
,

 
 
5
5
6
0
,

 
 
2
6
,

 
 
1
7
9
,

 
 
8
,

 
 
5
1
0
,

 
 
3
,

 
 
1
,

 
 
1
0
1
0
3
,

 
 
3
,

 
 
1
0
5
,

 
 
3
2
,

 
 
9
2
5
9
,

 
 
5
6
2
,

 
 
1
0
9
1
,

 
 
3
6
,

 
 
7
8
,

 
 
5
6
,

 
 
7
,

 
 
1
2
2
0
,

 
 
1
8
0
,

 
 
1
6
,

 
 
5
5
,

 
 
2
7
1
,

 
 
1
5
3
,

 
 
1
1
,

 
 
8
,

 
 
5
4
3
5
9
,

 
 
4
8
2
,

 
 
1
7
1
7
6
]
,

 
[
3
4
6
8
,

 
 
1
6
7
1
,

 
 
3
7
,

 
 
1
4
,

 
 
2
,

 
 
6
5
,

 
 
6
,

 
 
8
6
,

 
 
7
3
7
,

 
 
2
,

 
 
1
,

 
 
3
0
1
1
,

 
 
2
9
5
8
,

 
 
4
0
7
,

 
 
1
1
,

 
 
1
8
4
,

 
 
1
4
7
,

 
 
2
0
1
,

 
 
2
2
,

 
 
6
,

 
 
1
0
7
2
,

 
 
1
8
3
,

 
 
4
1
8
,

 
 
2
,

 
 
9
7
,

 
 
9
,

 
 
7
9
]
,

 
[
1
0
8
0
7
,

 
 
5
0
0
,

 
 
1
,

 
 
5
1
2
5
,

 
 
1
2
7
1
,

 
 
5
1
5
1
,

 
 
5
,

 
 
1
7
1
7
7
,

 
 
2
,

 
 
1
6
,

 
 
3
1
,

 
 
1
0
2
9
6
,

 
 
4
,

 
 
1
6
6
,

 
 
2
2
3
1
,

 
 
9
0
4
,

 
 
3
2
,

 
 
2
0
0
4
,

 
 
1
1
7
0
,

 
 
3
5
5
,

 
 
1
9
9
,

 
 
5
7
,

 
 
4
4
5
,

 
 
1
0
,

 
 
5
5
,

 
 
1
1
3
9
,

 
 
2
0
2
1
4
,

 
 
1
6
6
8
,

 
 
2
,

 
 
9
8
2
,

 
 
2
1
,

 
 
4
,

 
 
1
8
3
7
2
,

 
 
1
0
2
9
6
,

 
 
5
5
9
5
,

 
 
1
,

 
 
1
0
8
0
7
,

 
 
2
2
3
0
,

 
 
4
4
5
,

 
 
1
0
,

 
 
1
,

 
 
1
1
3
9
,

 
 
2
6
,

 
 
1
,

 
 
1
0
0
4
,

 
 
3
1
4
,

 
 
2
4
,

 
 
3
2
1
4
,

 
 
4
,

 
 
2
6
1
4
,

 
 
1
5
2
2
,

 
 
3
8
8
,

 
 
6
4
0
7
,

 
 
1
0
7
8
,

 
 
2
,

 
 
1
1
8
,

 
 
2
1
,

 
 
2
7
,

 
 
2
1
1
2
,

 
 
5
5
9
5
,

 
 
2
0
0
4
,

 
 
2
6
5
4
,

 
 
1
,

 
 
1
0
0
4
,

 
 
3
1
4
,

 
 
5
,

 
 
5
1
9
,

 
 
1
,

 
 
1
1
2
6
,

 
 
5
5
9
5
,

 
 
2
4
,

 
 
1
,

 
 
5
6
8
,

 
 
2
6
0
6
,

 
 
7
7
,

 
 
8
0
,

 
 
3
5
3
9
9
,

 
 
2
5
0
1
,

 
 
5
0
2
,

 
 
2
5
9
5
8
,

 
 
2
5
3
5
,

 
 
1
7
0
1
,

 
 
9
0
,

 
 
2
5
9
,

 
 
1
4
7
8
,

 
 
6
4
0
7
,

 
 
1
4
1
0
,

 
 
8
8
,

 
 
2
,

 
 
1
6
,

 
 
2
1
1
2
,

 
 
1
4
,

 
 
2
1
1
2
,

 
 
4
2
8
,

 
 
7
1
,

 
 
1
,

 
 
1
3
9
,

 
 
2
5
4
9
,

 
 
3
,

 
 
1
5
2
6
,

 
 
5
5
9
6
,

 
 
9
,

 
 
1
4
7
4
,

 
 
7
6
3
8
,

 
 
5
,

 
 
1
4
7
4
,

 
 
1
5
7
8
,

 
 
2
6
1
4
,

 
 
2
5
0
1
,

 
 
8
8
1
,

 
 
1
5
]
,

 
[
3
5
6
,
 
1
3
,
 
4
4
,
 
1
1
0
,
 
7
,
 
4
1
1
,
 
1
1
,
 
4
,
 
1
0
5
8
6
]
,

 
[
2
0
3
,

 
 
1
6
0
8
4
0
,

 
 
4
5
,

 
 
1
6
,

 
 
2
2
3
6
,

 
 
2
,

 
 
7
9
,

 
 
1
,

 
 
2
3
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
1
4
8
0
,

 
 
1
1
7
4
,

 
 
1
7
,

 
 
1
0
1
,

 
 
1
6
0
8
4
1
,

 
 
1
3
5
2
,

 
 
7
6
,

 
 
5
,

 
 
2
8
9
,

 
 
1
2
,

 
 
2
2
5
]
,

 
[
7
,

 
 
2
2
0
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
3
9
7
1
4
,

 
 
1
,

 
 
3
9
2
9
,

 
 
4
7
5
,

 
 
7
,

 
 
3
4
,

 
 
2
7
5
,

 
 
1
,

 
 
4
7
5
,

 
 
3
5
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
2
6
,

 
 
1
1
,

 
 
1
0
6
6
4
0
,

 
 
2
,

 
 
3
7
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
9
1
,

 
 
2
0
0
6
,

 
 
1
5
6
8
9
,

 
 
1
0
,

 
 
1
3
,

 
 
1
3
8
6
,

 
 
7
,

 
 
1
9
,

 
 
7
3
6
,

 
 
4
9
9
3
,

 
 
8
6
7
,

 
 
3
,

 
 
1
3
7
2
,

 
 
3
9
4
,

 
 
5
,

 
 
1
5
5
1
,

 
 
1
2
,

 
 
2
8
,

 
 
5
0
,

 
 
8
5
9
,

 
 
9
8
,

 
 
5
8
8
,

 
 
1
5
,

 
 
1
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
1
0
8
9
,

 
 
4
1
8
,

 
 
7
,

 
 
8
1
,

 
 
2
7
,

 
 
2
6
7
7
,

 
 
3
5
5
2
,

 
 
7
,

 
 
3
8
3
9
,

 
 
8
5
9
,

 
 
9
8
,

 
 
5
8
8
,

 
 
3
8
8
,

 
 
6
1
,

 
 
1
8
4
5
,

 
 
3
1
5
2
,

 
 
5
1
,

 
 
5
9
,

 
 
1
1
,

 
 
1
9
5
,

 
 
2
,

 
 
3
7
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
4
7
,

 
 
6
5
4
,

 
 
4
9
4
0
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
1
5
2
,

 
 
1
2
5
9
,

 
 
1
3
1
2
,

 
 
2
5
,

 
 
1
1
9
5
,

 
 
3
5
2
4
,

 
 
3
4
6
,

 
 
2
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
9
9
3
5
,

 
 
2
2
1
1
6
,

 
 
2
3
7
0
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
8
5
3
]
,

 
[
5
7
7
8
,
 
9
7
9
,
 
2
0
6
,
 
1
7
3
,
 
3
2
,
 
4
6
,
 
2
5
2
,
 
7
9
2
]
,

 
[
2
5
,

 
 
3
2
9
,

 
 
1
,

 
 
1
0
2
1
,

 
 
5
,

 
 
1
,

 
 
1
0
6
6
4
1
,

 
 
3
8
6
1
,

 
 
1
7
5
,

 
 
2
3
,

 
 
1
5
,

 
 
1
0
2
1
,

 
 
7
5
,

 
 
3
8
3
,

 
 
5
4
5
1
,

 
 
1
,

 
 
3
9
7
1
5
,

 
 
1
7
,

 
 
4
,

 
 
3
5
0
4
,

 
 
1
4
9
7
,

 
 
4
3
8
,

 
 
3
7
5
,

 
 
1
1
,

 
 
8
,

 
 
2
2
1
,

 
 
1
4
,

 
 
2
,

 
 
9
7
,

 
 
7
0
4
5
,

 
 
1
5
1
,

 
 
8
6
1
3
,

 
 
1
1
,

 
 
7
3
,

 
 
4
,

 
 
2
6
0
,

 
 
4
0
2
,

 
 
7
,

 
 
1
9
,

 
 
2
0
7
,

 
 
1
2
9
6
0
,

 
 
3
,

 
 
1
3
4
2
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
2
1
8
7
,

 
 
4
,

 
 
2
7
0
,

 
 
5
,

 
 
4
,

 
 
4
6
5
,

 
 
4
1
6
,

 
 
5
,

 
 
1
4
3
,

 
 
2
,

 
 
9
7
,

 
 
1
,

 
 
2
6
2
2
,

 
 
5
,

 
 
2
4
7
8
,

 
 
3
2
9
,

 
 
1
,

 
 
2
9
2
4
,

 
 
5
,

 
 
1
,

 
 
1
7
7
5
5
,

 
 
3
7
1
5
,

 
 
1
,

 
 
2
3
,

 
 
7
0
4
6
,

 
 
2
4
7
0
,

 
 
3
2
9
,

 
 
1
3
4
2
,

 
 
3
5
,

 
 
1
,

 
 
2
9
2
4
,

 
 
7
7
,

 
 
5
,

 
 
1
3
4
2
,

 
 
3
5
,

 
 
1
,

 
 
2
9
2
4
,

 
 
5
,

 
 
1
7
7
5
5
,

 
 
8
4
0
,

 
 
1
3
,

 
 
5
6
,

 
 
8
9
,

 
 
1
6
,

 
 
3
7
1
5
,

 
 
1
,

 
 
6
6
4
,

 
 
2
2
8
,

 
 
4
1
6
,

 
 
2
,

 
 
8
5
1
6
,

 
 
1
8
,

 
 
1
,

 
 
1
1
5
6
4
,

 
 
3
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
2
9
2
4
,

 
 
1
4
4
,

 
 
1
1
2
,

 
 
1
5
3
,

 
 
1
0
1
7
,

 
 
4
4
8
,

 
 
1
,

 
 
1
7
7
5
5
]
,

 
[
6
,
 
1
2
2
,
 
2
,
 
5
1
7
,
 
1
,
 
2
5
5
,
 
5
,
 
2
0
,
 
8
8
8
6
,
 
3
4
5
]
,

 
[
4
,

 
 
2
6
0
,

 
 
2
1
8
,

 
 
2
,

 
 
9
4
,

 
 
1
6
1
4
,

 
 
3
8
7
9
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
4
8
,

 
 
6
,

 
 
6
,

 
 
1
4
7
,

 
 
4
8
,

 
 
4
,

 
 
1
1
4
7
9
,

 
 
2
3
5
,

 
 
1
1
3
4
,

 
 
2
,

 
 
3
7
,

 
 
2
7
0
8
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
4
8
,

 
 
2
0
,

 
 
2
8
6
7
,

 
 
1
4
,

 
 
4
7
,

 
 
2
3
5
,

 
 
3
5
9
,

 
 
3
6
7
,

 
 
4
8
,

 
 
6
,

 
 
2
,

 
 
5
2
0
,

 
 
2
2
5
,

 
 
1
5
,

 
 
9
,

 
 
1
3
5
7
,

 
 
9
2
6
0
,

 
 
2
0
,

 
 
1
1
4
6
,

 
 
8
,

 
 
4
,

 
 
3
5
9
,

 
 
3
,

 
 
4
,

 
 
2
5
1
5
7
,

 
 
3
8
6
7
,

 
 
1
6
2
,

 
 
3
8
6
2
,

 
 
3
0
8
5
]
,

 
[
2
9
8
5
,

 
 
3
4
,

 
 
7
,

 
 
2
1
9
,

 
 
6
,

 
 
1
2
,

 
 
1
,

 
 
1
5
8
5
,

 
 
9
3
5
6
,

 
 
1
8
1
5
,

 
 
2
3
7
,

 
 
4
2
,

 
 
4
,

 
 
9
9
7
,

 
 
7
5
1
,

 
 
1
3
,

 
 
4
1
2
,

 
 
5
,

 
 
3
5
8
3
,

 
 
4
2
8
9
,

 
 
5
0
6
8
,

 
 
9
9
,

 
 
4
,

 
 
9
9
7
,

 
 
1
0
,

 
 
9
5
1
,

 
 
5
0
6
,

 
 
3
7
6
,

 
 
1
1
3
,

 
 
4
9
2
,

 
 
1
1
3
,

 
 
2
5
6
0
,

 
 
1
1
3
,

 
 
1
5
0
9
6
]
,

 
[
3
1
0
,

 
 
5
8
,

 
 
9
3
,

 
 
2
2
4
,

 
 
7
,

 
 
9
0
,

 
 
1
5
2
,

 
 
5
8
,

 
 
1
3
4
,

 
 
2
2
4
,

 
 
2
6
,

 
 
1
,

 
 
7
2
7
,

 
 
2
9
,

 
 
2
4
,

 
 
6
6
,

 
 
2
5
0
0
,

 
 
1
7
,

 
 
1
1
2
7
,

 
 
1
2
,

 
 
4
4
,

 
 
2
1
2
,

 
 
6
1
,

 
 
9
3
,

 
 
1
,

 
 
4
4
,

 
 
4
7
,

 
 
8
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
1
,

 
 
4
7
,

 
 
3
4
7
4
,

 
 
4
1
2
,

 
 
3
4
3
,

 
 
2
0
5
5
,

 
 
5
,

 
 
6
,

 
 
1
5
3
,

 
 
1
9
,

 
 
1
4
,

 
 
5
2
0
,

 
 
7
4
,

 
 
1
,

 
 
2
2
4
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
8
5
3
,

 
 
1
6
1
2
,

 
 
1
8
,

 
 
5
1
1
,

 
 
5
,

 
 
1
1
6
8
,

 
 
8
,

 
 
1
4
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
4
4
6
,

 
 
7
9
5
,

 
 
3
,

 
 
2
1
7
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
4
8
9
,

 
 
2
2
,

 
 
6
,

 
 
2
3
6
,

 
 
1
,

 
 
2
7
0
,

 
 
2
3
3
7
,

 
 
2
,

 
 
2
7
1
5
,

 
 
2
5
,

 
 
2
5
6
,

 
 
2
2
6
9
,

 
 
3
,

 
 
7
1
3
9
,

 
 
3
2
1
,

 
 
2
6
,

 
 
6
,

 
 
1
9
,

 
 
4
6
0
5
,

 
 
1
,

 
 
2
9
,

 
 
5
,

 
 
1
3
1
,

 
 
4
,

 
 
4
5
7
,

 
 
8
9
9
,

 
 
3
2
,

 
 
3
5
8
,

 
 
9
,

 
 
1
3
9
6
,

 
 
6
9
8
5
7
,

 
 
7
7
,

 
 
1
2
2
7
,

 
 
7
6
,

 
 
4
,

 
 
9
2
6
1
,

 
 
3
6
,

 
 
7
,

 
 
3
6
8
,

 
 
1
,

 
 
4
4
2
,

 
 
7
9
,

 
 
6
,

 
 
1
9
,

 
 
6
6
,

 
 
1
0
6
6
4
2
,

 
 
4
6
0
5
,

 
 
1
,

 
 
2
9
,

 
 
3
2
,

 
 
5
3
0
,

 
 
1
,

 
 
5
4
2
,

 
 
3
,

 
 
1
,

 
 
2
9
7
0
3
,

 
 
1
9
5
8
,

 
 
6
2
,

 
 
9
4
0
7
,

 
 
1
3
9
6
,

 
 
1
6
0
8
4
2
,

 
 
1
6
0
8
4
3
,

 
 
4
7
3
,

 
 
1
,

 
 
1
0
5
3
,

 
 
5
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
3
8
1
,

 
 
6
4
1
,

 
 
3
,

 
 
2
1
7
,

 
 
3
6
,

 
 
1
5
0
,

 
 
2
3
2
7
,

 
 
6
1
,

 
 
7
9
5
,

 
 
3
,

 
 
2
1
7
,

 
 
3
4
,

 
 
1
4
,

 
 
4
0
3
3
,

 
 
1
,

 
 
2
9
,

 
 
2
2
5
,

 
 
3
8
,

 
 
7
,

 
 
9
0
,

 
 
2
4
,

 
 
3
8
3
,

 
 
1
4
,

 
 
2
1
7
,

 
 
1
7
,

 
 
7
,

 
 
7
7
,

 
 
3
6
8
,

 
 
2
0
,

 
 
7
9
,

 
 
5
,

 
 
5
5
,

 
 
4
2
2
,

 
 
6
,

 
 
1
3
1
,

 
 
5
,

 
 
1
3
7
3
,

 
 
1
,

 
 
2
9
,

 
 
1
5
7
,

 
 
2
,

 
 
1
0
4
,

 
 
8
0
8
,

 
 
6
4
1
,

 
 
3
6
,

 
 
4
3
,

 
 
6
,

 
 
1
1
4
,

 
 
2
6
7
1
,

 
 
1
5
6
,

 
 
1
,

 
 
4
7
5
,

 
 
3
,

 
 
2
8
,

 
 
5
,

 
 
1
3
6
,

 
 
7
6
,

 
 
1
,

 
 
6
6
0
,

 
 
3
,

 
 
2
1
7
,

 
 
1
5
0
,

 
 
2
3
2
7
,

 
 
1
8
5
7
,

 
 
4
1
0
,

 
 
6
,

 
 
1
8
,

 
 
1
5
3
,

 
 
1
1
5
,

 
 
2
,

 
 
2
8
,

 
 
7
2
,

 
 
1
7
5
0
,

 
 
5
,

 
 
6
,

 
 
1
2
2
,

 
 
2
,

 
 
5
9
5
,

 
 
7
4
,

 
 
1
1
,

 
 
7
5
2
,

 
 
5
,

 
 
1
,

 
 
2
7
1
,

 
 
4
7
5
,

 
 
3
,

 
 
2
8
,

 
 
1
5
0
,

 
 
2
9
0
,

 
 
5
5
,

 
 
3
9
9
,

 
 
1
4
0
]
,

 
[
7
,

 
 
7
0
,

 
 
7
4
,

 
 
7
1
,

 
 
4
3
2
0
,

 
 
1
0
,

 
 
1
9
1
6
,

 
 
1
,

 
 
2
1
4
,

 
 
8
,

 
 
3
8
5
,

 
 
3
9
5
,

 
 
4
,

 
 
4
9
4
,

 
 
4
0
2
1
,

 
 
1
8
5
,

 
 
6
5
8
0
,

 
 
1
0
,

 
 
2
5
1
,

 
 
2
2
,

 
 
1
4
,

 
 
7
1
,

 
 
2
2
1
,

 
 
1
4
,

 
 
2
,

 
 
4
4
8
,

 
 
5
5
,

 
 
2
5
1
,

 
 
1
0
5
8
7
,

 
 
2
5
,

 
 
4
0
2
1
,

 
 
3
0
6
7
,

 
 
5
0
9
]
,

 
[
4
1
5
,

 
 
2
8
0
,

 
 
7
,

 
 
2
0
3
,

 
 
2
9
1
,

 
 
1
1
,

 
 
1
5
,

 
 
2
7
,

 
 
6
1
,

 
 
2
9
,

 
 
2
6
,

 
 
7
,

 
 
2
1
9
3
,

 
 
1
1
,

 
 
4
9
5
,

 
 
1
1
,

 
 
2
4
,

 
 
2
0
3
,

 
 
4
,

 
 
1
9
3
,

 
 
1
2
,

 
 
4
9
9
,

 
 
2
4
,

 
 
1
6
5
,

 
 
2
,

 
 
2
0
5
2
,

 
 
1
,

 
 
2
5
3
,

 
 
1
6
4
3
,

 
 
1
1
,

 
 
1
3
0
8
4
,

 
 
7
6
,

 
 
3
,

 
 
3
0
,

 
 
4
8
9
]
,

 
[
1
0
2
6
,

 
 
7
1
4
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
6
7
1
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
3
9
7
1
6
,

 
 
3
9
7
1
7
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
4
6
]
,

 
[
1
0
5
8
8
,

 
 
1
3
2
1
8
,

 
 
1
7
,

 
 
2
9
7
0
4
,

 
 
7
9
7
,

 
 
8
9
,

 
 
3
7
5
,

 
 
6
,

 
 
6
3
,

 
 
9
,

 
 
9
6
9
7
,

 
 
3
,

 
 
1
0
5
8
8
,

 
 
1
3
2
1
8
,

 
 
8
,

 
 
1
7
,

 
 
2
9
7
0
4
,

 
 
7
9
7
,

 
 
6
,

 
 
1
0
6
6
4
3
,

 
 
9
,

 
 
5
2
1
,

 
 
2
0
2
1
5
,

 
 
2
9
1
6
,

 
 
5
,

 
 
7
4
9
,

 
 
1
4
8
1
,

 
 
8
9
6
,

 
 
1
0
,

 
 
1
4
2
0
,

 
 
3
,

 
 
1
,

 
 
6
6
2
,

 
 
2
0
4
9
,

 
 
1
5
,

 
 
2
1
0
,

 
 
1
,

 
 
4
1
6
,

 
 
5
,

 
 
1
,

 
 
1
4
3
,

 
 
5
,

 
 
6
,

 
 
6
3
,

 
 
7
4
,

 
 
5
1
,

 
 
1
1
2
0
,

 
 
2
2
,

 
 
5
1
,

 
 
1
1
2
0
,

 
 
9
6
9
8
,

 
 
8
4
,

 
 
6
,

 
 
9
7
,

 
 
4
,

 
 
1
9
3
,

 
 
1
1
,

 
 
1
7
,

 
 
2
2
,

 
 
5
1
,

 
 
8
6
,

 
 
4
9
,

 
 
6
0
,

 
 
6
1
8
4
,

 
 
1
0
,

 
 
2
0
,

 
 
1
0
6
4
8
,

 
 
9
,

 
 
8
,

 
 
3
8
,

 
 
9
7
,

 
 
1
6
0
8
4
4
,

 
 
3
6
,

 
 
3
1
5
3
,

 
 
5
,

 
 
1
1
,

 
 
8
,

 
 
4
0
,

 
 
3
8
0
,

 
 
5
,

 
 
6
8
1
,

 
 
3
4
2
,

 
 
5
,

 
 
3
0
2
]
,

 
[
4
6
3
,
 
1
7
1
,
 
9
1
,
 
1
4
9
5
,
 
7
8
0
,
 
1
1
8
,
 
9
2
3
,
 
8
8
3
3
]
,

 
[
6
2
9
,

 
 
5
7
9
1
,

 
 
1
3
2
5
,

 
 
4
9
4
6
4
,

 
 
7
2
,

 
 
8
3
2
,

 
 
4
,

 
 
2
4
2
3
,

 
 
1
2
,

 
 
3
0
,

 
 
1
7
0
,

 
 
8
2
,

 
 
9
,

 
 
1
4
9
0
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
2
5
7
3
,

 
 
1
4
4
,

 
 
4
1
,

 
 
1
8
,

 
 
3
6
,

 
 
1
3
0
,

 
 
2
2
0
6
,

 
 
1
0
,

 
 
1
,

 
 
8
9
8
,

 
 
2
5
7
3
,

 
 
1
7
,

 
 
4
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
1
2
5
2
,

 
 
7
2
,

 
 
5
4
5
2
,

 
 
2
1
,

 
 
1
,

 
 
2
6
7
,

 
 
3
,

 
 
3
8
5
,

 
 
2
,

 
 
1
9
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
2
5
7
3
,

 
 
1
6
8
,

 
 
8
9
0
,

 
 
2
5
7
3
,

 
 
2
5
,

 
 
2
1
0
,

 
 
1
5
,

 
 
3
0
,

 
 
9
1
0
2
,

 
 
7
,

 
 
4
5
,

 
 
3
4
5
,

 
 
3
0
,

 
 
2
4
2
3
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
3
6
,

 
 
9
,

 
 
2
8
7
,

 
 
3
9
,

 
 
2
2
2
9
,

 
 
3
8
5
,

 
 
7
1
,

 
 
2
4
1
4
,

 
 
3
,

 
 
4
7
3
,

 
 
6
4
,

 
 
7
,

 
 
1
4
7
8
,

 
 
4
1
,

 
 
4
5
,

 
 
1
6
,

 
 
6
7
8
,

 
 
4
7
3
,

 
 
1
,

 
 
9
2
6
,

 
 
3
,

 
 
2
0
2
0
,

 
 
2
5
7
3
,

 
 
3
0
,

 
 
9
8
0
,

 
 
8
,

 
 
3
0
9
,

 
 
2
,

 
 
8
8
6
,

 
 
1
,

 
 
1
1
4
,

 
 
9
6
7
,

 
 
2
4
7
1
,

 
 
1
0
,

 
 
2
1
0
,

 
 
1
,

 
 
1
6
8
,

 
 
8
9
0
,

 
 
5
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
3
,

 
 
4
3
3
,

 
 
9
0
5
,

 
 
7
,

 
 
4
5
4
,

 
 
9
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
1
6
8
,

 
 
8
9
0
,

 
 
1
8
1
0
,

 
 
1
8
,

 
 
4
4
0
,

 
 
1
7
,

 
 
6
2
9
,

 
 
5
7
9
1
,

 
 
8
0
,

 
 
5
1
,

 
 
2
0
3
,

 
 
1
1
4
,

 
 
1
8
6
5
,

 
 
1
5
,

 
 
4
9
4
6
4
,

 
 
6
3
7
2
,

 
 
1
,

 
 
4
9
7
8
,

 
 
9
6
7
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
1
,

 
 
2
1
2
,

 
 
1
2
,

 
 
1
3
,

 
 
2
2
,

 
 
1
,

 
 
9
8
0
,

 
 
8
,

 
 
2
,

 
 
1
6
1
,

 
 
1
,

 
 
1
1
4
,

 
 
2
4
7
1
,

 
 
1
5
,

 
 
2
7
,

 
 
9
6
7
,

 
 
3
9
,

 
 
1
5
8
,

 
 
5
2
0
,

 
 
2
5
,

 
 
5
6
,

 
 
5
1
,

 
 
1
6
,

 
 
4
8
5
,

 
 
2
,

 
 
4
9
4
6
4
]
,

 
[
7
4
2
2
,

 
 
1
1
2
6
,

 
 
3
8
4
9
,

 
 
9
0
,

 
 
6
,

 
 
4
7
1
,

 
 
1
,

 
 
7
4
2
2
,

 
 
1
1
2
6
,

 
 
3
8
4
9
,

 
 
1
2
3
,

 
 
2
5
,

 
 
9
0
,

 
 
6
,

 
 
1
2
0
,

 
 
1
1
,

 
 
3
1
,

 
 
1
2
7
9
,

 
 
3
3
1
]
,

 
[
1
2
1
,

 
 
4
5
5
,

 
 
3
9
,

 
 
6
,

 
 
1
2
1
,

 
 
3
7
,

 
 
2
1
,

 
 
1
6
3
,

 
 
7
,

 
 
7
4
4
,

 
 
1
3
,

 
 
1
2
3
,

 
 
2
,

 
 
2
8
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
5
0
9
,

 
 
1
6
0
8
4
5
,

 
 
5
4
3
6
0
,

 
 
2
2
5
9
,

 
 
8
0
3
9
,

 
 
5
2
4
3
,

 
 
4
7
2
,

 
 
7
,

 
 
4
2
8
7
,

 
 
1
,

 
 
6
3
0
9
,

 
 
5
,

 
 
5
2
,

 
 
1
0
3
5
,

 
 
3
7
,

 
 
1
4
5
7
,

 
 
2
,

 
 
8
2
,

 
 
1
1
,

 
 
1
5
,

 
 
2
8
,

 
 
3
6
,

 
 
7
,

 
 
2
4
,

 
 
1
2
8
2
,

 
 
3
8
,

 
 
1
,

 
 
8
2
3
,

 
 
3
6
5
7
,

 
 
4
3
,

 
 
1
6
,

 
 
9
5
,

 
 
1
0
,

 
 
2
1
9
5
]
,

 
[
5
2
6
,

 
 
9
8
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
5
7
3
,

 
 
2
,

 
 
6
3
,

 
 
1
,

 
 
6
1
9
6
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
3
4
8
,

 
 
2
0
1
,

 
 
9
3
,

 
 
1
,

 
 
4
2
4
,

 
 
4
7
,

 
 
9
8
,

 
 
7
9
3
]
,

 
[
1
,

 
 
3
9
7
1
8
,

 
 
4
9
8
6
,

 
 
9
,

 
 
7
8
5
,

 
 
2
0
0
7
,

 
 
3
5
4
0
0
,

 
 
1
5
5
6
,

 
 
4
6
1
7
,

 
 
9
2
,

 
 
9
2
6
,

 
 
3
,

 
 
7
4
8
,

 
 
5
,

 
 
9
2
6
,

 
 
3
,

 
 
3
7
0
3
,

 
 
1
5
,

 
 
1
,

 
 
7
8
3
,

 
 
7
2
2
8
,

 
 
1
2
4
,

 
 
1
9
,

 
 
6
6
,

 
 
5
7
,

 
 
8
7
3
,

 
 
2
2
9
3
,

 
 
3
7
,

 
 
1
5
,

 
 
3
0
,

 
 
1
7
0
,

 
 
4
6
,

 
 
2
9
,

 
 
8
0
,

 
 
7
,

 
 
2
5
2
1
,

 
 
2
8
9
,

 
 
2
,

 
 
2
2
5
2
,

 
 
4
9
9
,

 
 
5
1
,

 
 
2
1
3
,

 
 
3
7
,

 
 
7
6
,

 
 
3
,

 
 
2
8
,

 
 
3
6
,

 
 
1
2
8
,

 
 
1
2
,

 
 
1
7
1
0
,

 
 
4
6
4
2
,

 
 
5
1
,

 
 
2
2
9
,

 
 
1
7
8
6
,

 
 
2
7
,

 
 
6
2
7
,

 
 
1
5
1
5
,

 
 
3
6
,

 
 
5
1
,

 
 
5
1
4
1
,

 
 
2
,

 
 
1
9
7
7
,

 
 
7
5
0
9
]
,

 
[
2
6
8
4
,

 
 
1
8
0
4
,

 
 
6
,

 
 
1
6
7
,

 
 
3
6
7
,

 
 
6
6
,

 
 
4
8
,

 
 
2
,

 
 
2
1
9
,

 
 
6
,

 
 
9
,

 
 
1
0
,

 
 
6
0
2
,

 
 
1
2
,

 
 
1
,

 
 
2
0
8
2
,

 
 
3
,

 
 
5
6
7
0
,

 
 
5
,

 
 
5
9
6
,

 
 
5
9
9
,

 
 
9
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
2
3
8
0
,

 
 
1
,

 
 
9
6
8
,

 
 
1
2
9
8
,

 
 
3
,

 
 
4
1
0
,

 
 
6
,

 
 
2
1
3
,

 
 
2
2
5
,

 
 
5
6
5
,

 
 
1
,

 
 
3
3
6
,

 
 
8
,

 
 
2
1
0
5
,

 
 
6
4
4
,

 
 
2
5
,

 
 
2
8
7
5
,

 
 
3
1
,

 
 
2
7
,

 
 
6
2
5
8
,

 
 
1
7
6
5
,

 
 
3
,

 
 
1
8
0
4
,

 
 
1
8
,

 
 
9
4
1
,

 
 
2
,

 
 
1
6
,

 
 
3
4
8
4
,

 
 
7
6
,

 
 
3
2
,

 
 
4
,

 
 
2
6
5
3
,

 
 
6
0
4
,

 
 
4
5
,

 
 
3
4
,

 
 
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
2
4
,

 
 
5
2
1
,

 
 
3
8
1
,

 
 
1
0
,

 
 
1
3
,

 
 
1
9
8
,

 
 
3
3
9
,

 
 
1
,

 
 
3
6
4
8
,

 
 
1
0
7
,

 
 
2
9
,

 
 
6
6
5
6
,

 
 
3
2
1
,

 
 
3
2
1
,

 
 
3
2
1
,

 
 
9
,

 
 
1
,

 
 
9
6
8
,

 
 
3
3
6
,

 
 
2
4
,

 
 
2
1
0
5
,

 
 
6
4
4
,

 
 
6
6
,

 
 
7
,

 
 
2
4
,

 
 
1
8
2
,

 
 
1
,

 
 
2
0
4
0
,

 
 
9
,

 
 
1
,

 
 
9
6
8
,

 
 
3
3
6
,

 
 
4
3
,

 
 
1
5
3
,

 
 
1
6
,

 
 
3
5
5
7
,

 
 
5
,

 
 
1
4
2
3
,

 
 
3
2
,

 
 
6
1
,

 
 
6
4
0
,

 
 
2
3
1
,

 
 
1
6
,

 
 
5
8
,

 
 
1
7
7
4
,

 
 
1
0
,

 
 
1
,

 
 
6
0
2
]
,

 
[
4
5
6
,

 
 
1
4
0
,

 
 
1
3
1
,

 
 
5
4
7
,

 
 
1
1
1
2
,

 
 
1
5
8
2
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
2
,

 
 
4
5
5
6
3
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
1
5
2
,

 
 
1
1
3
5
,

 
 
7
6
8
,

 
 
2
2
4
,

 
 
2
,

 
 
2
8
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
2
6
7
3
,

 
 
2
7
1
2
,

 
 
3
,

 
 
2
2
4
,

 
 
6
2
1
,

 
 
5
6
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
2
,

 
 
1
4
4
1
,

 
 
2
5
,

 
 
2
3
3
5
,

 
 
1
1
3
5
,

 
 
2
2
4
,

 
 
4
4
8
,

 
 
2
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
4
3
5
,

 
 
2
,

 
 
2
2
4
,

 
 
2
,

 
 
2
4
2
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
2
2
4
,

 
 
2
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
2
1
,

 
 
5
4
,

 
 
6
,

 
 
1
8
,

 
 
4
8
0
1
,

 
 
5
,

 
 
2
2
4
,

 
 
9
,

 
 
8
3
4
,

 
 
2
,

 
 
4
8
8
7
,

 
 
5
3
3
4
,

 
 
2
,

 
 
4
,

 
 
5
8
6
,

 
 
3
4
1
,

 
 
2
5
,

 
 
1
8
3
1
,

 
 
4
,

 
 
1
5
2
2
,

 
 
6
3
,

 
 
1
,

 
 
7
6
8
,

 
 
2
2
4
,

 
 
1
2
1
8
,

 
 
5
,

 
 
1
1
2
7
,

 
 
5
7
0
,

 
 
1
2
,

 
 
3
9
9
,

 
 
3
2
7
9
,

 
 
3
,

 
 
2
2
4
,

 
 
9
,

 
 
1
8
,

 
 
4
1
9
,

 
 
4
8
1
,

 
 
2
2
,

 
 
6
,

 
 
2
1
1
,

 
 
1
,

 
 
1
6
9
,

 
 
5
6
,

 
 
1
6
,

 
 
1
7
3
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
8
4
,

 
 
5
0
,

 
 
5
6
3
,

 
 
1
1
,

 
 
1
5
,

 
 
1
,

 
 
8
1
7
,

 
 
4
6
,

 
 
2
9
,

 
 
2
6
4
,

 
 
9
3
,

 
 
3
5
7
,

 
 
3
1
0
,

 
 
1
1
,

 
 
6
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
2
8
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
]
,

 
[
2
6
9
,

 
 
1
5
,

 
 
2
4
,

 
 
1
3
,

 
 
1
2
6
,

 
 
8
3
3
,

 
 
7
,

 
 
2
7
5
,

 
 
1
2
5
,

 
 
2
0
,

 
 
9
8
3
,

 
 
3
1
,

 
 
2
6
,

 
 
6
,

 
 
1
0
7
5
,

 
 
4
8
,

 
 
4
,

 
 
2
4
4
7
3
,

 
 
3
7
8
,

 
 
8
0
,

 
 
6
,

 
 
1
9
,

 
 
4
,

 
 
4
2
1
,

 
 
9
,

 
 
2
5
9
,

 
 
3
9
,

 
 
7
9
,

 
 
1
3
,

 
 
7
0
8
,

 
 
3
,

 
 
5
3
6
,

 
 
7
9
0
,

 
 
2
1
,

 
 
1
,

 
 
2
4
5
3
,

 
 
5
,

 
 
9
0
,

 
 
6
,

 
 
1
2
6
,

 
 
1
2
2
0
,

 
 
2
5
9
,

 
 
6
1
,

 
 
8
4
,

 
 
1
,

 
 
3
6
5
,

 
 
2
5
,

 
 
3
6
3
,

 
 
7
5
,

 
 
6
2
,

 
 
1
5
3
6
,

 
 
1
1
3
,

 
 
1
2
9
6
1
,

 
 
2
,

 
 
1
5
6
,

 
 
2
0
,

 
 
2
3
4
,

 
 
1
5
,

 
 
4
6
,

 
 
2
0
4
5
,

 
 
1
7
7
7
0
,

 
 
7
1
4
,

 
 
2
5
,

 
 
1
3
,

 
 
4
6
,

 
 
2
9
,

 
 
1
2
,

 
 
9
,

 
 
3
5
4
,

 
 
7
2
,

 
 
6
2
8
1
,

 
 
1
3
2
,

 
 
1
3
4
5
,

 
 
7
9
5
,

 
 
3
,

 
 
1
1
3
,

 
 
1
2
9
6
1
,

 
 
1
9
,

 
 
1
7
3
,

 
 
1
0
8
0
8
,

 
 
3
5
4
0
1
,

 
 
2
,

 
 
9
2
,

 
 
9
2
3
,

 
 
1
6
1
,

 
 
3
6
,

 
 
8
0
,

 
 
5
,

 
 
2
2
,

 
 
1
6
3
,

 
 
1
4
,

 
 
2
,

 
 
9
2
,

 
 
6
5
8
1
,

 
 
8
,

 
 
1
7
3
,

 
 
1
1
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
7
,

 
 
7
5
0
,

 
 
1
7
,

 
 
9
,

 
 
5
,

 
 
2
2
,

 
 
1
6
4
,

 
 
1
6
0
8
4
6
,

 
 
2
1
,

 
 
1
0
2
5
,

 
 
7
3
,

 
 
2
1
,

 
 
7
5
,

 
 
1
4
,

 
 
5
9
1
,

 
 
4
6
,

 
 
2
8
6
6
2
,

 
 
2
2
9
9
,

 
 
4
9
3
0
,

 
 
3
2
2
9
]
,

 
[
7
,

 
 
3
4
,

 
 
1
4
,

 
 
6
3
,

 
 
5
5
,

 
 
5
6
1
,

 
 
5
4
3
6
,

 
 
6
4
,

 
 
2
2
,

 
 
1
,

 
 
6
1
3
,

 
 
1
0
5
8
,

 
 
9
5
1
6
,

 
 
1
0
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
2
3
1
7
7
,

 
 
5
,

 
 
3
5
4
0
2
,

 
 
3
2
2
,

 
 
6
8
,

 
 
5
4
6
,

 
 
3
0
6
,

 
 
5
2
8
,

 
 
2
6
5
1
,

 
 
2
0
9
,

 
 
3
0
6
,

 
 
2
6
3
1
,

 
 
1
0
,

 
 
1
1
1
,

 
 
5
4
8
2
,

 
 
2
8
2
1
,

 
 
1
7
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
3
4
5
,

 
 
8
4
,

 
 
4
7
,

 
 
3
9
,

 
 
2
9
7
,

 
 
9
,

 
 
6
8
,

 
 
2
3
7
1
,

 
 
1
8
,

 
 
1
4
,

 
 
7
7
,

 
 
2
4
2
,

 
 
6
,

 
 
3
9
,

 
 
1
4
,

 
 
1
3
6
,

 
 
5
5
,

 
 
3
4
8
7
,

 
 
2
2
2
,

 
 
9
7
3
,

 
 
4
9
4
6
5
,

 
 
1
0
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
3
4
5
,

 
 
9
3
5
6
,

 
 
2
9
7
0
5
,

 
 
1
2
5
1
4
,

 
 
1
6
0
8
4
7
,

 
 
2
3
1
7
8
,

 
 
8
3
6
6
3
,

 
 
8
7
,

 
 
1
7
2
,

 
 
8
5
5
,

 
 
1
0
,

 
 
1
7
4
6
,

 
 
5
0
0
,

 
 
7
,

 
 
7
0
,

 
 
1
8
9
,

 
 
8
,

 
 
2
1
5
9
4
,

 
 
1
0
,

 
 
5
4
9
,

 
 
5
,

 
 
6
1
,

 
 
1
6
0
8
4
8
,

 
 
1
8
,

 
 
1
,

 
 
7
8
4
,

 
 
6
2
,

 
 
9
7
,

 
 
4
,

 
 
2
8
4
,

 
 
6
7
2
,

 
 
1
2
,

 
 
1
7
7
7
1
,

 
 
6
9
8
5
8
,

 
 
1
3
,

 
 
6
1
3
,

 
 
4
2
,

 
 
4
4
,

 
 
4
8
9
,

 
 
3
3
,

 
 
4
0
,

 
 
7
,

 
 
2
6
3
,

 
 
9
,

 
 
1
6
4
0
2
,

 
 
3
7
4
7
,

 
 
8
,

 
 
2
4
7
,

 
 
2
6
,

 
 
1
,

 
 
3
7
4
7
,

 
 
3
,

 
 
7
3
2
8
,

 
 
9
,

 
 
1
7
7
7
1
,

 
 
6
9
8
5
8
,

 
 
8
,

 
 
3
9
7
1
9
,

 
 
1
2
,

 
 
6
9
,

 
 
5
2
,

 
 
3
0
4
7
,

 
 
1
6
0
8
4
9
,

 
 
5
4
7
,

 
 
9
,

 
 
3
7
4
7
,

 
 
2
4
,

 
 
1
4
,

 
 
5
5
,

 
 
2
0
1
,

 
 
5
,

 
 
2
1
6
8
,

 
 
3
1
7
1
,

 
 
2
4
,

 
 
2
7
5
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
7
4
,

 
 
5
1
,

 
 
1
6
0
8
5
0
,

 
 
1
7
7
7
1
,

 
 
6
9
8
5
8
,

 
 
1
0
,

 
 
2
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
5
,

 
 
1
0
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
3
4
5
,

 
 
4
0
1
,

 
 
1
0
,

 
 
1
3
7
8
,

 
 
3
5
4
0
3
,

 
 
3
,

 
 
1
0
6
6
4
4
,

 
 
1
0
3
5
7
,

 
 
8
,

 
 
1
3
7
8
,

 
 
9
,

 
 
6
1
0
,

 
 
8
,

 
 
9
,

 
 
4
,

 
 
6
1
0
,

 
 
1
6
0
7
,

 
 
7
8
,

 
 
5
9
,

 
 
5
1
,

 
 
1
1
7
,

 
 
4
0
1
,

 
 
1
0
,

 
 
1
,

 
 
2
4
4
,

 
 
3
7
6
0
,

 
 
2
5
,

 
 
8
7
,

 
 
1
6
,

 
 
5
2
,

 
 
8
,

 
 
3
5
5
,

 
 
4
,

 
 
8
8
3
4
,

 
 
1
0
,

 
 
1
6
5
9
,

 
 
2
1
,

 
 
1
0
1
9
,

 
 
1
6
0
8
5
1
,

 
 
5
,

 
 
1
4
8
9
,

 
 
1
3
7
5
7
,

 
 
3
4
6
9
,

 
 
9
3
5
2
,

 
 
1
0
,

 
 
3
8
9
3
,

 
 
5
,

 
 
3
5
5
,

 
 
6
0
,

 
 
9
5
1
6
,

 
 
5
,

 
 
6
9
6
3
,

 
 
2
1
,

 
 
5
6
1
,

 
 
2
8
6
6
3
,

 
 
7
2
1
,

 
 
1
0
,

 
 
5
6
2
1
,

 
 
6
7
2
8
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
1
0
,

 
 
3
2
9
,

 
 
1
3
0
8
5
,

 
 
6
8
,

 
 
5
1
0
,

 
 
3
,

 
 
4
1
8
7
,

 
 
8
3
,

 
 
2
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
3
4
5
,

 
 
2
8
5
,

 
 
1
3
,

 
 
3
0
1
,

 
 
7
4
,

 
 
3
9
,

 
 
6
,

 
 
1
6
0
8
5
2
,

 
 
8
,

 
 
4
0
1
,

 
 
1
0
,

 
 
1
3
7
8
,

 
 
2
5
,

 
 
2
5
9
5
,

 
 
2
5
,

 
 
2
0
6
9
]
,

 
[
7
8
,

 
 
1
8
4
6
,

 
 
5
,

 
 
1
2
5
5
,

 
 
1
0
,

 
 
1
,

 
 
3
2
5
,

 
 
2
4
4
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
2
8
4
8
,

 
 
1
,

 
 
5
5
3
,

 
 
3
,

 
 
4
,

 
 
9
8
,

 
 
2
8
,

 
 
1
5
,

 
 
1
,

 
 
4
4
7
,

 
 
2
7
7
0
2
,

 
 
2
0
3
6
,

 
 
9
,

 
 
6
9
,

 
 
1
,

 
 
3
2
5
,

 
 
2
4
4
,

 
 
4
2
,

 
 
1
4
,

 
 
3
5
1
,

 
 
2
4
4
7
4
,

 
 
7
6
,

 
 
1
,

 
 
6
5
6
,

 
 
3
5
,

 
 
1
,

 
 
3
7
4
2
9
,

 
 
1
1
,

 
 
8
,

 
 
6
0
7
,

 
 
1
9
4
7
,

 
 
1
2
,

 
 
1
9
1
,

 
 
2
,

 
 
7
0
,

 
 
1
,

 
 
6
5
6
,

 
 
5
,

 
 
7
7
2
,

 
 
1
9
4
7
,

 
 
1
2
,

 
 
1
9
1
,

 
 
2
,

 
 
3
5
0
,

 
 
3
5
,

 
 
1
1
,

 
 
7
,

 
 
4
5
2
5
,

 
 
1
1
1
,

 
 
4
,

 
 
3
8
9
2
,

 
 
7
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
1
1
8
0
,

 
 
2
6
,

 
 
3
7
1
,

 
 
4
4
1
,

 
 
2
,

 
 
3
5
0
,

 
 
4
,

 
 
9
1
8
,

 
 
2
8
,

 
 
2
3
,

 
 
3
5
,

 
 
4
,

 
 
4
4
7
,

 
 
9
,

 
 
8
,

 
 
2
3
1
7
9
,

 
 
5
,

 
 
2
5
,

 
 
1
1
9
5
,

 
 
1
2
5
,

 
 
1
3
0
,

 
 
2
8
,

 
 
2
0
5
,

 
 
9
4
,

 
 
1
1
,

 
 
2
4
7
,

 
 
8
,

 
 
9
,

 
 
5
1
,

 
 
2
2
0
,

 
 
5
0
8
,

 
 
7
9
3
,

 
 
8
,

 
 
2
,

 
 
5
7
6
,

 
 
1
,

 
 
6
5
6
,

 
 
1
3
,

 
 
8
,

 
 
2
4
7
,

 
 
5
0
8
,

 
 
7
9
3
,

 
 
8
,

 
 
1
4
,

 
 
2
,

 
 
5
7
6
,

 
 
1
,

 
 
6
5
6
,

 
 
3
0
6
8
,

 
 
6
9
,

 
 
1
1
,

 
 
8
,

 
 
1
1
8
0
,

 
 
2
,

 
 
2
1
7
4
,

 
 
3
8
,

 
 
1
,

 
 
6
5
6
,

 
 
8
,

 
 
5
5
,

 
 
9
0
3
,

 
 
2
,

 
 
3
4
,

 
 
9
,

 
 
8
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
3
8
2
,

 
 
3
,

 
 
6
5
6
,

 
 
2
8
,

 
 
6
5
4
6
,

 
 
1
2
,

 
 
1
7
9
3
,

 
 
2
0
4
,

 
 
4
,

 
 
2
7
1
,

 
 
1
1
0
,

 
 
2
8
,

 
 
8
,

 
 
2
9
9
1
,

 
 
2
,

 
 
4
5
6
1
,

 
 
1
,

 
 
2
9
7
,

 
 
3
,

 
 
7
1
5
,

 
 
7
4
8
,

 
 
5
,

 
 
3
2
7
,

 
 
1
4
,

 
 
1
7
5
,

 
 
8
5
7
,

 
 
2
6
,

 
 
1
4
1
,

 
 
3
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
2
2
,

 
 
1
,

 
 
6
5
6
,

 
 
8
,

 
 
3
8
1
,

 
 
5
,

 
 
7
9
6
9
,

 
 
1
1
,

 
 
8
,

 
 
1
1
3
3
,

 
 
1
2
,

 
 
1
9
1
,

 
 
2
,

 
 
5
7
6
,

 
 
9
,

 
 
2
2
,

 
 
1
,

 
 
6
5
6
,

 
 
8
,

 
 
2
3
1
7
9
,

 
 
5
,

 
 
1
1
9
5
,

 
 
1
1
,

 
 
8
,

 
 
5
8
,

 
 
6
8
8
2
,

 
 
2
6
,

 
 
4
4
1
,

 
 
1
2
,

 
 
1
9
1
,

 
 
2
,

 
 
5
7
6
,

 
 
1
5
,

 
 
3
8
,

 
 
2
7
1
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
2
0
1
1
,

 
 
5
,

 
 
6
5
,

 
 
3
5
,

 
 
4
,

 
 
4
4
7
,

 
 
9
6
,

 
 
2
2
,

 
 
1
1
2
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
8
0
1
,

 
 
1
2
5
,

 
 
2
8
,

 
 
2
0
5
,

 
 
9
4
,

 
 
1
3
5
,

 
 
1
4
0
0
,

 
 
8
,

 
 
8
0
,

 
 
5
1
,

 
 
4
2
6
,

 
 
2
1
5
9
5
,

 
 
2
1
,

 
 
4
7
,

 
 
6
5
4
,

 
 
3
,

 
 
4
,

 
 
1
2
5
5
,

 
 
5
,

 
 
6
8
8
3
,

 
 
9
,

 
 
1
,

 
 
6
5
4
,

 
 
9
,

 
 
5
1
,

 
 
1
9
,

 
 
3
2
9
4
,

 
 
3
2
5
9
,

 
 
1
,

 
 
6
5
6
,

 
 
5
,

 
 
1
4
,

 
 
4
9
,

 
 
4
7
,

 
 
1
9
0
5
,

 
 
2
5
,

 
 
4
1
3
,

 
 
1
5
,

 
 
1
,

 
 
4
4
7
,

 
 
3
3
,

 
 
7
4
1
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
2
6
8
,

 
 
2
,

 
 
1
3
9
2
,

 
 
1
3
,

 
 
6
8
1
,

 
 
3
6
6
9
,

 
 
3
2
5
1
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
1
1
8
0
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
7
7
,

 
 
3
,

 
 
4
,

 
 
1
5
6
0
,

 
 
1
9
8
2
9
,

 
 
8
6
6
,

 
 
3
2
9
,

 
 
1
,

 
 
1
4
9
,

 
 
1
9
5
9
,

 
 
6
0
5
,

 
 
8
,

 
 
6
9
,

 
 
6
0
,

 
 
4
1
0
,

 
 
3
3
6
9
7
,

 
 
5
,

 
 
1
6
0
8
5
3
,

 
 
5
9
,

 
 
1
0
8
,

 
 
2
,

 
 
5
6
3
,

 
 
1
0
,

 
 
1
6
6
,

 
 
5
1
,

 
 
1
0
8
,

 
 
1
9
1
,

 
 
2
,

 
 
2
6
3
,

 
 
2
1
,

 
 
9
2
,

 
 
4
1
3
,

 
 
1
8
5
,

 
 
1
4
,

 
 
1
3
8
,

 
 
3
5
,

 
 
1
,

 
 
6
8
1
,

 
 
1
4
0
,

 
 
1
8
5
,

 
 
7
8
,

 
 
7
,

 
 
2
2
9
9
,

 
 
3
1
,

 
 
1
,

 
 
1
3
8
,

 
 
3
5
,

 
 
1
,

 
 
6
4
1
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
2
7
7
0
3
]
,

 
[
7
,

 
 
9
0
,

 
 
1
4
,

 
 
2
7
2
8
,

 
 
2
,

 
 
1
6
,

 
 
1
0
4
1
,

 
 
7
,

 
 
2
4
,

 
 
1
6
0
8
5
4
,

 
 
2
9
2
2
,

 
 
3
2
,

 
 
1
,

 
 
2
7
0
,

 
 
2
4
7
0
,

 
 
7
,

 
 
7
7
,

 
 
7
0
5
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
1
4
7
,

 
 
4
8
,

 
 
2
7
,

 
 
1
0
2
8
,

 
 
1
5
4
4
,

 
 
1
2
7
5
,

 
 
1
5
1
,

 
 
6
,

 
 
7
3
3
,

 
 
1
3
1
,

 
 
3
7
,

 
 
1
4
7
,

 
 
4
8
,

 
 
2
7
,

 
 
1
6
6
5
1
,

 
 
1
6
1
5
5
]
,

 
[
4
5
6
,

 
 
1
6
0
8
5
5
,

 
 
5
,

 
 
4
5
6
0
,

 
 
1
2
0
7
,

 
 
1
0
3
2
,

 
 
1
3
5
,

 
 
1
1
,

 
 
5
,

 
 
1
3
,

 
 
2
9
2
,

 
 
1
9
5
,

 
 
2
,

 
 
1
6
,

 
 
1
8
2
5
,

 
 
2
7
,

 
 
5
6
1
,

 
 
4
5
6
0
,

 
 
1
7
0
2
,

 
 
3
1
6
1
,

 
 
2
0
7
,

 
 
6
1
8
,

 
 
5
3
6
,

 
 
1
4
8
,

 
 
3
3
,

 
 
5
5
9
9
,

 
 
2
4
8
1
,

 
 
5
,

 
 
1
3
1
,

 
 
5
6
8
,

 
 
4
9
1
,

 
 
1
4
0
7
,

 
 
2
,

 
 
6
1
,

 
 
2
0
5
,

 
 
1
3
,

 
 
5
8
2
,

 
 
8
,

 
 
4
1
1
2
,

 
 
5
,

 
 
8
,

 
 
3
7
1
,

 
 
1
3
4
6
,

 
 
2
,

 
 
1
3
4
1
,

 
 
1
4
1
,

 
 
1
2
0
7
,

 
 
4
3
,

 
 
3
6
7
4
,

 
 
2
5
8
,

 
 
6
1
,

 
 
7
5
,

 
 
6
2
,

 
 
8
7
,

 
 
1
4
,

 
 
9
6
,

 
 
3
4
7
,

 
 
1
,

 
 
4
5
6
0
,

 
 
1
2
5
8
,

 
 
5
9
1
,

 
 
1
,

 
 
2
3
,

 
 
1
,

 
 
2
9
9
2
,

 
 
9
,

 
 
3
0
6
,

 
 
2
2
2
,

 
 
6
2
,

 
 
1
0
0
,

 
 
8
2
7
,

 
 
5
5
9
9
,

 
 
2
4
8
1
,

 
 
8
,

 
 
4
,

 
 
2
7
5
8
,

 
 
5
,

 
 
2
5
,

 
 
2
4
4
9
,

 
 
3
3
6
9
8
,

 
 
7
,

 
 
5
9
,

 
 
8
7
3
,

 
 
9
2
3
,

 
 
1
5
6
,

 
 
5
5
9
9
,

 
 
2
4
8
1
,

 
 
2
5
,

 
 
7
0
,

 
 
1
2
8
,

 
 
3
5
,

 
 
1
1
,

 
 
3
6
,

 
 
7
2
,

 
 
1
4
,

 
 
6
2
8
1
,

 
 
3
0
5
,

 
 
2
,

 
 
3
5
7
,

 
 
1
5
2
,

 
 
1
,

 
 
1
2
0
7
,

 
 
2
6
,

 
 
1
,

 
 
1
9
4
3
,

 
 
1
2
,

 
 
9
2
,

 
 
1
1
2
9
,

 
 
8
,

 
 
4
6
7
3
,

 
 
1
4
8
7
,

 
 
5
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
7
7
5
,

 
 
2
2
3
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
3
5
,

 
 
1
8
6
2
,

 
 
3
4
8
3
,

 
 
4
6
]
,

 
[
3
8
0
5
,

 
 
8
0
,

 
 
1
0
6
6
4
5
,

 
 
4
8
7
,

 
 
8
0
3
,

 
 
5
9
7
,

 
 
1
5
,

 
 
5
1
5
2
,

 
 
9
7
3
,

 
 
6
1
,

 
 
2
1
8
,

 
 
8
8
8
,

 
 
6
3
,

 
 
2
7
,

 
 
3
9
7
4
,

 
 
2
,

 
 
1
6
,

 
 
7
8
5
2
,

 
 
1
3
,

 
 
8
5
,

 
 
8
8
8
,

 
 
1
9
,

 
 
2
7
6
1
,

 
 
2
,

 
 
2
4
8
9
,

 
 
8
5
6
,

 
 
6
3
,

 
 
2
3
9
2
,

 
 
4
,

 
 
3
3
2
3
,

 
 
5
,

 
 
2
3
9
2
,

 
 
4
,

 
 
4
5
9
8
]
,

 
[
9
3
7
,

 
 
7
,

 
 
2
9
1
,

 
 
4
,

 
 
1
9
6
4
,

 
 
9
,

 
 
5
7
3
5
,

 
 
1
,

 
 
3
9
7
2
0
,

 
 
1
6
9
3
,

 
 
3
2
,

 
 
1
,

 
 
6
2
,

 
 
1
5
,

 
 
1
,

 
 
6
2
,

 
 
3
4
1
,

 
 
8
9
,

 
 
4
1
,

 
 
5
6
,

 
 
1
6
,

 
 
4
4
,

 
 
1
4
0
0
,

 
 
2
1
,

 
 
4
7
3
,

 
 
1
,

 
 
2
5
5
,

 
 
2
5
3
]
,

 
[
2
1
5
9
6
,
 
1
0
6
6
4
6
,
 
1
6
0
8
5
6
,
 
1
0
6
6
4
6
,
 
4
,
 
8
9
0
,
 
4
,
 
8
2
5
5
,
 
2
2
]
,

 
[
8
3
6
6
4
,

 
 
8
,

 
 
2
3
3
2
,

 
 
7
,

 
 
2
6
3
,

 
 
2
,

 
 
1
1
0
1
,

 
 
1
6
0
8
5
7
,

 
 
1
0
,

 
 
2
,

 
 
8
3
6
6
4
,

 
 
1
4
4
,

 
 
8
3
6
6
4
,

 
 
8
,

 
 
5
8
,

 
 
6
7
4
,

 
 
2
,

 
 
1
6
,

 
 
3
7
4
,

 
 
7
0
1
9
,

 
 
1
,

 
 
4
5
6
9
,

 
 
3
,

 
 
1
,

 
 
2
7
0
,

 
 
3
8
3
,

 
 
1
1
,

 
 
8
,

 
 
3
,

 
 
6
1
7
7
,

 
 
1
6
0
6
,

 
 
1
0
,

 
 
8
1
3
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
5
2
3
,

 
 
8
0
4
4
,

 
 
3
0
8
3
7
,

 
 
2
,

 
 
6
3
1
0
,

 
 
1
6
0
8
5
8
,

 
 
2
,

 
 
1
6
0
8
5
9
,

 
 
5
,

 
 
7
7
2
,

 
 
6
5
0
0
,

 
 
1
1
,

 
 
8
,

 
 
3
8
3
0
,

 
 
1
7
,

 
 
4
2
3
8
4
,

 
 
1
0
,

 
 
9
4
8
,

 
 
2
6
3
5
]
,

 
[
7
,

 
 
2
1
1
,

 
 
4
8
,

 
 
7
2
,

 
 
7
6
,

 
 
3
,

 
 
1
2
6
8
,

 
 
1
2
,

 
 
8
9
,

 
 
3
6
,

 
 
3
5
2
,

 
 
6
0
,

 
 
6
1
,

 
 
4
1
0
,

 
 
4
5
,

 
 
2
6
9
,

 
 
7
3
,

 
 
2
1
,

 
 
2
1
8
,

 
 
9
,

 
 
4
5
9
,

 
 
2
1
0
,

 
 
1
7
5
,

 
 
1
1
0
0
,

 
 
5
2
4
,

 
 
4
6
,

 
 
1
2
7
2
7
,

 
 
7
9
2
]
,

 
[
1
1
6
9
,

 
 
8
4
4
,

 
 
2
1
6
,

 
 
1
,

 
 
2
9
9
,

 
 
6
3
7
3
,

 
 
5
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
2
6
8
,

 
 
2
,

 
 
2
0
5
4
,

 
 
1
,

 
 
2
3
,

 
 
2
6
,

 
 
2
8
7
,

 
 
1
9
,

 
 
5
7
,

 
 
3
5
8
,

 
 
1
1
,

 
 
2
4
,

 
 
2
9
1
,

 
 
2
,

 
 
1
6
,

 
 
1
6
6
7
,

 
 
3
2
,

 
 
6
,

 
 
3
6
,

 
 
1
1
,

 
 
4
2
,

 
 
2
,

 
 
1
1
6
7
,

 
 
2
1
,

 
 
1
,

 
 
2
9
9
,

 
 
6
3
7
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
6
3
0
,

 
 
2
,

 
 
2
4
6
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
7
4
4
7
,

 
 
5
2
,

 
 
2
4
,

 
 
2
8
2
4
,

 
 
1
0
,

 
 
5
0
5
3
,

 
 
1
,

 
 
2
3
,

 
 
3
,

 
 
4
,

 
 
4
2
1
1
,

 
 
1
0
1
5
,

 
 
3
9
,

 
 
5
3
,

 
 
2
0
5
4
,

 
 
1
1
,

 
 
8
9
,

 
 
2
2
,

 
 
1
5
8
,

 
 
1
0
7
7
,

 
 
2
,

 
 
9
7
,

 
 
4
,

 
 
1
5
7
0
,

 
 
1
2
1
1
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
8
5
,

 
 
6
6
5
,

 
 
1
9
2
0
,

 
 
3
0
2
4
,

 
 
9
1
2
]
,

 
[
3
8
,

 
 
2
4
2
3
,

 
 
1
8
,

 
 
6
,

 
 
4
9
1
,

 
 
3
3
,

 
 
7
,

 
 
5
9
,

 
 
6
3
,

 
 
2
1
5
,

 
 
1
2
7
3
2
,

 
 
9
,

 
 
7
7
0
7
,

 
 
1
0
7
,

 
 
4
6
,

 
 
2
8
6
6
4
,

 
 
1
2
5
1
5
,

 
 
2
0
5
0
]
,

 
[
1
3
0
1
,

 
 
5
0
0
,

 
 
1
1
,

 
 
4
2
5
,

 
 
4
9
4
6
6
,

 
 
1
,

 
 
1
4
9
2
,

 
 
3
3
8
,

 
 
3
2
,

 
 
3
5
1
,

 
 
1
8
3
,

 
 
2
7
0
,

 
 
7
,

 
 
2
4
,

 
 
1
5
4
8
3
,

 
 
1
5
,

 
 
1
,

 
 
1
7
4
9
,

 
 
1
9
5
4
,

 
 
6
4
,

 
 
1
7
,

 
 
1
1
,

 
 
3
8
3
,

 
 
1
9
6
0
,

 
 
1
,

 
 
1
4
5
0
,

 
 
1
4
5
,

 
 
1
2
,

 
 
1
,

 
 
2
3
,

 
 
3
3
,

 
 
7
4
1
,

 
 
6
0
5
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
2
,

 
 
1
6
,

 
 
3
9
1
,

 
 
3
1
,

 
 
4
,

 
 
3
9
7
2
1
,

 
 
6
8
0
,

 
 
1
9
0
5
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
,

 
 
4
7
8
6
,

 
 
1
1
3
2
,

 
 
3
2
3
,

 
 
2
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
3
0
8
6
,

 
 
9
1
,

 
 
1
,

 
 
7
7
,

 
 
9
1
4
2
,

 
 
3
0
3
1
,

 
 
1
0
,

 
 
1
,

 
 
1
6
1
3
,

 
 
3
2
,

 
 
1
,

 
 
8
9
7
9
,

 
 
9
9
,

 
 
2
8
8
2
,

 
 
5
2
2
6
,

 
 
2
1
,

 
 
1
,

 
 
1
2
4
9
,

 
 
9
3
,

 
 
2
8
2
3
,

 
 
9
0
,

 
 
5
,

 
 
2
4
,

 
 
1
4
7
2
1
,

 
 
1
0
,

 
 
4
,

 
 
1
2
8
,

 
 
5
8
,

 
 
7
5
5
,

 
 
5
,

 
 
1
6
9
0
2
,

 
 
1
1
0
,

 
 
9
3
,

 
 
2
8
2
3
,

 
 
2
4
,

 
 
1
,

 
 
1
2
4
9
,

 
 
3
4
9
2
,

 
 
9
0
4
,

 
 
1
,

 
 
8
1
1
2
,

 
 
8
3
4
4
,

 
 
1
5
6
9
0
,

 
 
5
4
,

 
 
2
4
,

 
 
1
4
,

 
 
1
,

 
 
1
9
8
,

 
 
2
1
,

 
 
2
8
2
3
,

 
 
9
,

 
 
1
6
7
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
8
6
,

 
 
2
2
,

 
 
1
,

 
 
9
7
5
,

 
 
3
,

 
 
9
3
2
,

 
 
1
1
1
,

 
 
1
7
,

 
 
6
6
0
2
,

 
 
1
,

 
 
2
1
5
9
7
,

 
 
5
7
5
0
,

 
 
2
5
,

 
 
9
6
,

 
 
3
8
0
1
,

 
 
5
4
,

 
 
9
9
,

 
 
1
9
9
,

 
 
5
7
,

 
 
1
0
7
3
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
8
,

 
 
4
,

 
 
9
8
,

 
 
4
0
5
,

 
 
2
0
8
,

 
 
1
,

 
 
1
2
4
9
,

 
 
1
0
3
,

 
 
1
9
,

 
 
5
2
9
4
,

 
 
2
0
7
,

 
 
5
8
,

 
 
2
,

 
 
3
9
4
9
,

 
 
5
5
,

 
 
3
,

 
 
1
1
2
,

 
 
6
8
5
3
,

 
 
1
5
0
,

 
 
5
,

 
 
1
5
1
,

 
 
1
,

 
 
3
2
6
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
1
,

 
 
8
1
7
,

 
 
1
4
9
4
,

 
 
5
6
,

 
 
1
6
,

 
 
1
5
,

 
 
2
8
2
3
,

 
 
5
,

 
 
1
3
0
8
6
,

 
 
1
0
,

 
 
5
2
7
,

 
 
1
4
,

 
 
3
4
,

 
 
2
7
7
0
4
,

 
 
1
,

 
 
4
4
2
,

 
 
2
6
7
,

 
 
1
5
1
,

 
 
4
0
,

 
 
4
1
,

 
 
8
6
,

 
 
2
8
6
6
5
,

 
 
1
0
,

 
 
1
4
1
1
,

 
 
5
,

 
 
1
,

 
 
1
8
0
9
,

 
 
1
7
1
8
,

 
 
1
5
5
,

 
 
6
2
,

 
 
8
6
,

 
 
6
9
8
5
9
,

 
 
1
9
0
6
4
,

 
 
1
1
1
5
,

 
 
1
3
4
9
,

 
 
4
2
9
7
,

 
 
6
9
,

 
 
3
,

 
 
9
2
,

 
 
5
4
3
6
1
,

 
 
2
3
0
,

 
 
9
1
9
,

 
 
1
7
5
3
,

 
 
8
7
8
,

 
 
4
2
1
5
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
3
2
0
,

 
 
5
4
3
6
2
,

 
 
3
9
,

 
 
7
,

 
 
2
1
9
,

 
 
6
,

 
 
3
8
,

 
 
6
,

 
 
6
5
,

 
 
3
,

 
 
1
,

 
 
1
2
8
9
,

 
 
1
1
4
,

 
 
2
0
4
,

 
 
1
3
1
8
,

 
 
3
2
,

 
 
3
8
0
5
,

 
 
5
3
4
1
,

 
 
1
0
,

 
 
8
5
0
,

 
 
3
3
,

 
 
3
7
0
,

 
 
4
6
,

 
 
5
4
6
,

 
 
8
6
5
,

 
 
1
8
2
6
,

 
 
1
5
9
1
,

 
 
7
,

 
 
1
0
2
9
7
,

 
 
7
,

 
 
8
1
,

 
 
4
4
,

 
 
1
6
2
0
,

 
 
1
5
,

 
 
7
8
7
,

 
 
1
5
9
1
,

 
 
2
6
,

 
 
7
,

 
 
2
2
0
,

 
 
1
3
,

 
 
1
0
3
,

 
 
3
4
3
6
,

 
 
1
,

 
 
2
4
9
,

 
 
3
,

 
 
7
8
7
,

 
 
1
5
9
1
,

 
 
3
5
5
,

 
 
4
4
,

 
 
1
5
5
7
,

 
 
2
,

 
 
2
3
0
5
,

 
 
1
1
,

 
 
1
5
,

 
 
1
8
0
,

 
 
7
,

 
 
1
9
,

 
 
1
3
1
,

 
 
4
,

 
 
2
0
6
,

 
 
3
3
,

 
 
9
,

 
 
2
3
,

 
 
6
6
9
]
,

 
[
4
2
8
,

 
 
1
2
9
6
2
,

 
 
1
7
,

 
 
1
3
8
4
,

 
 
3
1
8
2
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
6
3
,

 
 
4
4
0
,

 
 
1
0
,

 
 
1
,

 
 
2
9
5
,

 
 
5
5
,

 
 
7
8
1
,

 
 
3
,

 
 
1
,

 
 
4
2
8
,

 
 
1
2
9
6
2
,

 
 
8
3
,

 
 
1
0
,

 
 
1
0
2
4
,

 
 
1
8
8
7
,

 
 
6
0
,

 
 
3
,

 
 
5
4
,

 
 
5
6
3
,

 
 
1
3
,

 
 
2
5
7
]
,

 
[
4
5
6
,

 
 
1
,

 
 
1
7
9
3
,

 
 
2
0
2
2
,

 
 
6
,

 
 
4
5
,

 
 
6
8
5
,

 
 
9
,

 
 
5
9
6
,

 
 
2
,

 
 
5
2
9
,

 
 
1
1
1
1
,

 
 
1
0
7
,

 
 
4
6
,

 
 
6
9
8
6
0
,

 
 
1
2
4
8
,

 
 
9
5
1
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
3
9
7
2
2
,

 
 
4
,

 
 
3
2
1
8
9
,

 
 
8
,

 
 
1
1
,

 
 
4
9
,

 
 
3
7
,

 
 
2
5
,

 
 
8
,

 
 
1
1
,

 
 
6
,

 
 
1
5
5
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
3
8
,

 
 
2
,

 
 
3
4
,

 
 
7
4
,

 
 
3
9
,

 
 
5
3
,

 
 
1
1
8
,

 
 
1
3
1
8
,

 
 
3
8
,

 
 
8
,

 
 
2
,

 
 
6
6
1
,

 
 
3
,

 
 
3
7
,

 
 
5
,

 
 
4
0
,

 
 
3
0
,

 
 
2
2
2
6
,

 
 
5
,

 
 
3
2
3
,

 
 
6
2
,

 
 
8
,

 
 
4
1
,

 
 
6
2
,

 
 
2
4
9
4
,

 
 
2
,

 
 
1
5
9
,

 
 
1
0
,

 
 
2
,

 
 
3
8
7
,

 
 
3
0
,

 
 
5
7
5
,

 
 
8
,

 
 
4
1
,

 
 
4
4
,

 
 
8
0
0
4
,

 
 
1
2
,

 
 
1
7
5
,

 
 
2
2
0
6
,

 
 
5
,

 
 
4
3
3
,

 
 
3
,

 
 
1
9
1
,

 
 
3
8
,

 
 
1
1
,

 
 
8
,

 
 
9
,

 
 
6
,

 
 
6
3
,

 
 
9
,

 
 
5
3
,

 
 
1
1
6
7
,

 
 
1
2
,

 
 
1
0
,

 
 
1
,

 
 
2
8
2
8
,

 
 
1
8
9
6
,

 
 
1
7
,

 
 
1
9
1
2
,

 
 
1
2
6
,

 
 
1
1
1
4
,

 
 
1
7
,

 
 
5
3
,

 
 
4
0
,

 
 
1
8
,

 
 
9
1
0
3
,

 
 
1
0
,

 
 
1
7
5
,

 
 
1
7
0
,

 
 
1
1
0
,

 
 
1
7
,

 
 
3
2
5
,

 
 
7
5
,

 
 
2
7
1
,

 
 
2
6
,

 
 
1
,

 
 
1
3
9
,

 
 
2
6
,

 
 
1
1
2
1
,

 
 
2
7
,

 
 
1
1
1
4
,

 
 
4
9
,

 
 
4
8
,

 
 
3
0
6
,

 
 
1
0
4
4
,

 
 
3
3
1
,

 
 
2
8
3
4
,

 
 
5
1
,

 
 
1
8
,

 
 
1
1
7
0
,

 
 
4
0
,

 
 
3
8
9
,

 
 
2
,

 
 
1
,

 
 
1
9
6
5
,

 
 
2
0
6
,

 
 
1
5
,

 
 
1
7
4
,

 
 
1
4
,

 
 
1
5
,

 
 
1
8
1
6
,

 
 
2
5
,

 
 
9
0
,

 
 
7
,

 
 
4
9
,

 
 
3
5
8
4
,

 
 
9
,

 
 
3
0
4
,

 
 
1
1
0
,

 
 
2
5
,

 
 
6
1
7
,

 
 
4
9
,

 
 
5
9
,

 
 
5
9
0
7
,

 
 
1
,

 
 
5
7
7
9
,

 
 
2
5
,

 
 
4
3
1
2
,

 
 
1
,

 
 
2
6
7
6
6
,

 
 
2
4
4
7
5
,

 
 
1
6
0
8
6
0
,

 
 
6
,

 
 
7
0
,

 
 
1
1
,

 
 
3
9
7
,

 
 
4
6
9
,

 
 
2
,

 
 
3
7
,

 
 
8
4
6
,

 
 
7
,

 
 
1
1
7
,

 
 
3
6
,

 
 
6
9
8
6
1
,

 
 
4
6
]
,

 
[
6
,

 
 
1
9
,

 
 
4
4
,

 
 
1
4
7
5
,

 
 
2
,

 
 
1
6
,

 
 
3
3
6
9
9
,

 
 
2
,

 
 
2
1
3
,

 
 
3
7
,

 
 
3
5
,

 
 
3
5
8
,

 
 
1
0
5
,

 
 
3
5
,

 
 
4
,

 
 
6
7
2
,

 
 
7
,

 
 
1
4
2
,

 
 
1
2
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
9
6
,

 
 
7
0
,

 
 
2
1
5
,

 
 
3
5
,

 
 
2
1
0
9
1
,

 
 
3
3
7
0
0
,

 
 
9
,

 
 
8
,

 
 
4
0
,

 
 
7
,

 
 
1
2
3
2
,

 
 
1
6
7
,

 
 
2
2
,

 
 
9
,

 
 
2
4
,

 
 
3
6
,

 
 
5
5
2
,

 
 
2
,

 
 
7
3
2
9
]
,

 
[
1
,

 
 
3
2
5
,

 
 
2
4
9
,

 
 
8
,

 
 
1
,

 
 
3
5
4
0
4
,

 
 
5
,

 
 
1
9
8
3
0
,

 
 
1
9
5
4
,

 
 
9
,

 
 
6
,

 
 
4
8
3
5
,

 
 
1
0
,

 
 
2
0
,

 
 
1
1
4
,

 
 
4
6
5
,

 
 
1
0
,

 
 
1
,

 
 
2
6
2
,

 
 
3
4
5
,

 
 
1
1
,

 
 
2
4
,

 
 
1
6
3
8
,

 
 
1
6
5
6
,

 
 
3
2
,

 
 
2
8
7
,

 
 
1
0
,

 
 
6
1
8
,

 
 
1
1
1
3
6
,

 
 
5
4
,

 
 
6
,

 
 
1
9
,

 
 
1
4
6
,

 
 
2
9
6
,

 
 
7
,

 
 
3
9
,

 
 
1
2
1
9
,

 
 
5
,

 
 
2
2
3
9
,

 
 
3
5
2
7
,

 
 
7
,

 
 
3
9
,

 
 
6
6
,

 
 
5
1
2
6
,

 
 
4
8
1
,

 
 
7
8
4
,

 
 
1
0
,

 
 
1
3
,

 
 
1
9
8
,

 
 
4
7
,

 
 
5
4
,

 
 
6
,

 
 
4
3
,

 
 
3
4
,

 
 
1
0
1
,

 
 
2
,

 
 
4
1
1
,

 
 
7
,

 
 
4
5
,

 
 
1
5
3
1
,

 
 
2
,

 
 
1
3
,

 
 
8
0
,

 
 
7
,

 
 
1
9
,

 
 
8
5
,

 
 
2
8
8
,

 
 
1
3
,

 
 
3
6
7
8
]
,

 
[
5
2
,

 
 
1
0
0
,

 
 
7
5
4
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
3
5
9
,

 
 
3
,

 
 
4
,

 
 
6
9
8
6
2
,

 
 
2
,

 
 
1
6
,

 
 
3
0
2
,

 
 
5
2
,

 
 
4
2
,

 
 
1
7
7
7
2
,

 
 
4
,

 
 
5
7
3
,

 
 
2
3
5
,

 
 
1
7
6
2
,

 
 
1
2
,

 
 
8
2
9
,

 
 
5
,

 
 
5
8
,

 
 
1
5
4
4
,

 
 
1
,

 
 
5
4
3
6
3
,

 
 
9
,

 
 
2
4
4
2
,

 
 
6
8
,

 
 
5
9
0
,

 
 
5
,

 
 
2
2
0
,

 
 
3
8
,

 
 
5
2
,

 
 
2
8
6
,

 
 
2
6
,

 
 
4
8
,

 
 
1
3
0
,

 
 
7
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
7
,

 
 
2
6
9
,

 
 
3
1
,

 
 
9
,

 
 
4
5
0
,

 
 
5
,

 
 
2
7
1
7
,

 
 
6
8
,

 
 
1
0
9
,

 
 
8
,

 
 
4
4
5
,

 
 
1
,

 
 
6
3
9
,

 
 
8
,

 
 
3
6
9
,

 
 
4
1
4
6
,

 
 
6
2
,

 
 
4
4
,

 
 
4
7
,

 
 
9
9
,

 
 
3
4
9
,

 
 
8
2
0
,

 
 
3
,

 
 
1
5
4
,

 
 
3
3
,

 
 
4
0
,

 
 
3
8
8
,

 
 
1
,

 
 
5
9
0
,

 
 
5
1
3
,

 
 
9
8
3
,

 
 
7
6
]
,

 
[
1
1
0
6
2
,

 
 
4
6
3
,

 
 
2
5
3
0
,

 
 
2
1
,

 
 
3
7
,

 
 
3
3
7
0
1
,

 
 
8
,

 
 
4
,

 
 
1
0
4
5
,

 
 
7
1
,

 
 
4
,

 
 
1
1
5
,

 
 
1
0
4
5
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
1
0
4
5
,

 
 
3
3
7
0
1
,

 
 
8
,

 
 
8
3
6
6
5
,

 
 
3
9
3
,

 
 
2
,

 
 
1
0
6
6
4
7
,

 
 
5
3
,

 
 
1
0
8
,

 
 
1
,

 
 
2
7
0
,

 
 
3
5
,

 
 
1
9
1
,

 
 
7
6
,

 
 
4
1
,

 
 
7
5
,

 
 
1
8
,

 
 
1
4
,

 
 
1
5
5
,

 
 
9
3
5
7
,

 
 
3
,

 
 
1
7
5
,

 
 
2
2
2
6
,

 
 
5
3
,

 
 
4
9
,

 
 
1
0
8
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
3
1
4
,

 
 
8
8
,

 
 
9
,

 
 
5
3
,

 
 
2
7
6
,

 
 
4
4
,

 
 
2
8
8
0
,

 
 
8
9
,

 
 
6
,

 
 
1
9
,

 
 
1
,

 
 
1
6
6
5
2
,

 
 
4
0
3
4
,

 
 
9
1
6
,

 
 
1
0
,

 
 
6
4
,

 
 
9
,

 
 
8
,

 
 
1
4
,

 
 
9
6
,

 
 
4
,

 
 
3
2
5
,

 
 
1
0
4
5
,

 
 
3
3
7
0
1
,

 
 
8
,

 
 
3
6
,

 
 
5
0
,

 
 
3
7
3
,

 
 
3
7
,

 
 
3
8
,

 
 
1
,

 
 
1
6
6
5
2
,

 
 
4
0
3
4
,

 
 
4
2
,

 
 
2
0
7
,

 
 
9
,

 
 
3
3
7
0
1
,

 
 
1
8
7
0
,

 
 
3
8
,

 
 
3
9
,

 
 
5
3
,

 
 
3
4
,

 
 
3
6
,

 
 
9
,

 
 
3
3
7
0
1
,

 
 
3
9
,

 
 
1
6
,

 
 
1
5
,

 
 
2
8
,

 
 
6
9
,

 
 
7
,

 
 
8
1
,

 
 
3
5
5
,

 
 
1
4
0
0
,

 
 
1
1
1
6
,

 
 
5
,

 
 
7
,

 
 
1
7
3
2
,

 
 
1
2
,

 
 
1
,

 
 
8
3
6
6
6
,

 
 
1
1
0
6
2
,

 
 
1
1
0
6
2
,

 
 
7
9
9
,

 
 
1
9
7
,

 
 
1
2
8
,

 
 
1
1
5
6
,

 
 
1
1
,

 
 
2
4
,

 
 
7
,

 
 
8
0
7
,

 
 
1
9
,

 
 
2
0
7
,

 
 
1
1
,

 
 
1
6
0
8
6
1
]
,

 
[
7
,
 
1
4
1
0
,
 
1
3
,
 
2
,
 
1
1
8
,
 
1
,
 
2
9
]
,

 
[
4
9
4
6
7
,

 
 
2
6
9
,

 
 
7
6
,

 
 
2
6
9
,

 
 
7
6
,

 
 
1
2
5
,

 
 
3
4
9
,

 
 
6
,

 
 
1
8
,

 
 
7
4
,

 
 
2
0
1
2
,

 
 
9
,

 
 
4
9
4
6
7
,

 
 
8
0
3
,

 
 
5
0
4
,

 
 
5
,

 
 
8
4
,

 
 
1
0
,

 
 
1
,

 
 
4
9
4
6
8
,

 
 
8
3
,

 
 
1
6
0
8
6
2
,

 
 
5
5
7
,

 
 
1
0
,

 
 
1
,

 
 
1
2
9
,

 
 
1
1
0
7
,

 
 
9
7
5
0
,

 
 
9
7
5
0
,

 
 
9
7
5
0
,

 
 
6
0
9
4
,

 
 
6
0
9
4
,

 
 
6
0
9
4
,

 
 
2
0
0
,

 
 
1
5
4
8
4
,

 
 
1
5
4
6
,

 
 
5
4
3
6
4
,

 
 
1
2
4
2
,

 
 
2
1
0
2
,

 
 
1
3
1
1
,

 
 
1
8
3
8
7
,

 
 
7
6
9
,

 
 
9
6
9
9
,

 
 
3
6
,

 
 
6
,

 
 
1
2
6
,

 
 
1
8
,

 
 
9
,

 
 
9
9
3
6
,

 
 
5
2
9
5
,

 
 
2
0
0
,

 
 
3
3
7
0
2
,

 
 
5
4
3
6
4
,

 
 
3
2
9
8
,

 
 
5
,

 
 
1
9
0
6
5
,

 
 
2
4
8
3
,

 
 
6
2
,

 
 
4
2
,

 
 
1
,

 
 
6
0
8
1
2
,

 
 
1
2
,

 
 
7
6
9
,

 
 
9
6
9
9
,

 
 
2
1
,

 
 
6
8
,

 
 
6
7
2
9
,

 
 
1
9
2
,

 
 
7
1
,

 
 
8
5
,

 
 
6
,

 
 
5
8
5
,

 
 
7
6
,

 
 
4
9
4
6
7
]
,

 
[
1
3
,

 
 
2
3
6
1
,

 
 
8
,

 
 
9
3
5
8
,

 
 
1
2
,

 
 
7
,

 
 
1
9
,

 
 
7
7
,

 
 
3
6
8
,

 
 
4
7
,

 
 
7
9
,

 
 
3
0
,

 
 
4
3
7
,

 
 
7
9
,

 
 
2
4
,

 
 
2
,

 
 
1
5
2
,

 
 
1
,

 
 
2
7
3
,

 
 
1
4
,

 
 
4
,

 
 
3
9
8
]
,

 
[
3
4
,
 
1
4
,
 
1
2
1
,
 
1
,
 
9
9
4
,
 
1
6
0
8
6
3
,
 
1
1
2
3
,
 
5
8
7
]
,

 
[
9
9
2
9
,
 
1
2
,
 
5
7
1
6
,
 
2
3
,
 
2
7
2
,
 
1
1
9
5
9
,
 
6
,
 
1
2
6
,
 
1
8
9
3
,
 
5
1
3
8
,
 
3
8
9
7
,
 
1
2
,
 
2
7
2
]
,

 
[
1
9
6
,

 
 
3
2
0
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
5
3
,

 
 
6
8
5
,

 
 
1
3
1
0
,

 
 
4
1
4
,

 
 
2
6
,

 
 
6
0
,

 
 
3
,

 
 
2
0
,

 
 
5
2
9
,

 
 
4
1
4
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
1
4
4
1
,

 
 
2
5
,

 
 
1
2
,

 
 
2
1
8
4
,

 
 
2
3
1
2
,

 
 
2
8
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
0
7
2
,

 
 
1
4
4
1
,

 
 
1
2
,

 
 
5
8
,

 
 
1
0
5
,

 
 
1
5
,

 
 
1
3
,

 
 
6
3
,

 
 
2
3
0
,

 
 
1
5
,

 
 
5
1
6
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
1
2
1
8
,

 
 
1
5
,

 
 
1
1
2
7
,

 
 
1
2
1
8
,

 
 
1
5
,

 
 
7
6
8
,

 
 
2
2
4
,

 
 
1
2
1
8
,

 
 
1
5
,

 
 
8
0
1
,

 
 
3
,

 
 
5
6
2
,

 
 
2
2
,

 
 
6
,

 
 
1
5
3
,

 
 
1
9
,

 
 
2
5
4
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
1
1
5
,

 
 
7
6
3
9
,

 
 
1
2
1
,

 
 
2
9
,

 
 
2
5
,

 
 
6
,

 
 
3
9
,

 
 
3
5
0
,

 
 
1
6
2
8
,

 
 
5
6
7
,

 
 
1
3
,

 
 
3
7
7
,

 
 
6
7
7
,

 
 
2
1
,

 
 
4
,

 
 
2
1
4
,

 
 
5
,

 
 
1
5
8
,

 
 
4
5
,

 
 
1
6
,

 
 
6
7
7
,

 
 
2
,

 
 
5
2
5
,

 
 
1
1
,

 
 
1
7
4
1
,

 
 
6
,

 
 
8
7
,

 
 
6
6
,

 
 
1
3
6
,

 
 
1
,

 
 
4
5
1
,

 
 
1
2
4
,

 
 
6
1
1
,

 
 
1
2
,

 
 
4
,

 
 
4
3
6
,

 
 
1
1
9
9
,

 
 
2
,

 
 
2
8
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
1
2
1
,

 
 
1
2
4
,

 
 
1
0
5
5
,

 
 
7
4
,

 
 
2
,

 
 
3
5
0
,

 
 
4
,

 
 
2
8
4
,

 
 
2
3
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
8
2
7
,

 
 
1
2
9
,

 
 
2
8
,

 
 
5
0
,

 
 
5
1
7
,

 
 
2
0
,

 
 
1
0
9
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
0
4
8
,

 
 
2
0
,

 
 
1
0
9
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
5
0
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
1
2
1
6
,

 
 
3
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
9
4
,

 
 
1
0
,

 
 
2
0
3
7
,

 
 
2
1
,

 
 
3
7
,

 
 
1
2
7
,

 
 
1
9
6
]
,

 
[
1
,

 
 
1
3
3
1
,

 
 
1
6
0
8
6
4
,

 
 
1
2
2
3
,

 
 
1
6
0
8
6
5
,

 
 
4
5
7
0
,

 
 
6
9
8
6
3
,

 
 
5
4
8
3
,

 
 
1
6
0
8
6
6
,

 
 
1
6
0
8
6
7
,

 
 
5
3
1
2
,

 
 
2
4
1
8
,

 
 
4
5
7
0
,

 
 
1
2
9
6
3
,

 
 
1
1
5
8
,

 
 
1
0
1
6
8
,

 
 
8
,

 
 
1
,

 
 
4
7
,

 
 
7
1
6
,

 
 
1
0
,

 
 
1
,

 
 
3
4
4
2
,

 
 
1
0
,

 
 
1
,

 
 
7
2
0
0
,

 
 
4
4
6
2
,

 
 
3
,

 
 
6
5
4
,

 
 
3
2
,

 
 
6
5
4
,

 
 
3
2
,

 
 
5
4
3
6
5
,

 
 
8
4
2
,

 
 
1
2
,

 
 
1
9
4
2
9
,

 
 
7
7
,

 
 
1
3
,

 
 
4
0
7
,

 
 
3
,

 
 
1
,

 
 
9
0
5
,

 
 
1
9
7
,

 
 
1
0
6
6
4
8
,

 
 
1
6
0
8
6
8
,

 
 
3
6
3
3
,

 
 
3
2
1
4
,

 
 
2
,

 
 
1
2
0
8
1
,

 
 
1
,

 
 
4
0
2
1
,

 
 
5
,

 
 
4
2
,

 
 
1
,

 
 
1
9
8
3
1
,

 
 
4
2
4
9
,

 
 
1
,

 
 
2
6
2
,

 
 
2
3
1
,

 
 
1
6
,

 
 
4
9
0
3
,

 
 
2
6
4
,

 
 
9
3
,

 
 
4
1
1
0
,

 
 
1
1
,

 
 
4
3
,

 
 
3
6
4
,

 
 
6
0
7
,

 
 
9
,

 
 
1
3
,

 
 
1
2
0
,

 
 
4
3
1
,

 
 
1
6
,

 
 
4
1
9
,

 
 
9
8
0
0
,

 
 
1
3
,

 
 
9
8
6
4
,

 
 
3
,

 
 
1
,

 
 
2
0
2
,

 
 
1
0
9
,

 
 
1
0
0
,

 
 
9
5
1
8
,

 
 
2
1
,

 
 
8
3
6
6
7
,

 
 
1
6
1
5
6
,

 
 
4
5
6
1
,

 
 
1
5
,

 
 
1
,

 
 
6
5
4
,

 
 
3
2
,

 
 
6
5
4
,

 
 
3
2
,

 
 
5
4
3
6
5
,

 
 
2
5
7
0
,

 
 
9
6
7
,

 
 
1
9
7
,

 
 
1
,

 
 
5
9
2
,

 
 
4
0
7
,

 
 
3
,

 
 
1
,

 
 
9
0
5
,

 
 
1
7
,

 
 
3
0
5
9
,

 
 
1
0
,

 
 
1
,

 
 
1
9
8
3
2
,

 
 
1
1
9
6
0
,

 
 
3
,

 
 
3
7
3
9
,

 
 
5
4
3
6
5
,

 
 
1
8
1
0
,

 
 
2
4
1
0
,

 
 
1
9
8
3
2
,

 
 
6
5
3
,

 
 
5
9
0
,

 
 
6
9
1
4
,

 
 
4
2
,

 
 
1
,

 
 
1
9
8
3
1
,

 
 
3
3
6
6
,

 
 
1
7
,

 
 
1
6
0
8
6
9
,

 
 
1
2
2
3
,

 
 
1
6
0
8
7
0
,

 
 
4
5
7
0
,

 
 
6
9
8
6
3
,

 
 
5
4
8
3
,

 
 
1
6
0
8
7
1
,

 
 
6
9
8
6
4
,

 
 
1
2
2
3
,

 
 
1
6
4
0
3
,

 
 
4
5
7
0
,

 
 
1
2
9
6
3
,

 
 
1
1
5
8
,

 
 
1
0
1
6
8
,

 
 
5
,

 
 
9
1
,

 
 
4
,

 
 
3
3
6
6
,

 
 
1
2
0
,

 
 
1
7
,

 
 
1
6
8
2
,

 
 
2
,

 
 
3
3
7
0
3
,

 
 
1
7
,

 
 
8
,

 
 
1
,

 
 
7
2
0
0
,

 
 
4
4
6
2
,

 
 
3
9
,

 
 
3
2
1
4
,

 
 
1
6
,

 
 
4
1
9
,

 
 
5
2
6
6
,

 
 
9
9
3
7
,

 
 
1
6
0
8
7
2
,

 
 
4
0
2
1
,

 
 
1
5
,

 
 
1
,

 
 
2
9
9
,

 
 
2
5
7
0
,

 
 
4
5
6
1
,

 
 
3
,

 
 
1
,

 
 
2
5
2
0
,

 
 
3
1
4
,

 
 
1
2
,

 
 
5
4
,

 
 
1
,

 
 
9
0
5
,

 
 
2
4
,

 
 
3
9
1
,

 
 
2
3
8
2
,

 
 
1
3
,

 
 
1
3
3
1
,

 
 
5
4
,

 
 
4
3
,

 
 
4
6
8
,

 
 
9
,

 
 
1
,

 
 
3
3
6
6
,

 
 
4
0
7
,

 
 
8
,

 
 
3
7
4
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
3
0
3
8
,

 
 
2
0
2
,

 
 
1
0
9
,

 
 
1
9
7
,

 
 
5
5
,

 
 
1
3
8
,

 
 
3
,

 
 
3
7
4
,

 
 
1
3
3
1
,

 
 
4
0
2
1
,

 
 
8
,

 
 
2
7
,

 
 
1
3
7
2
,

 
 
4
7
,

 
 
3
3
,

 
 
2
2
1
]
,

 
[
5
9
,
 
3
0
8
3
8
,
 
2
0
,
 
8
8
0
,
 
5
0
,
 
3
6
0
,
 
2
,
 
6
3
,
 
1
8
3
,
 
2
3
,
 
9
4
,
 
1
7
5
4
,
 
1
2
,
 
1
9
4
0
,
 
5
9
6
,
 
2
,
 
6
]
,

 
[
8
3
6
6
8
,

 
 
1
6
0
8
7
3
,

 
 
2
0
,

 
 
2
4
0
3
,

 
 
2
4
9
,

 
 
8
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
9
1
,

 
 
1
5
5
,

 
 
5
4
5
3
,

 
 
1
,

 
 
3
5
3
,

 
 
2
4
2
,

 
 
1
7
1
8
,

 
 
8
,

 
 
4
,

 
 
1
0
2
,

 
 
9
4
7
,

 
 
5
,

 
 
1
4
3
5
,

 
 
5
0
0
6
,

 
 
3
5
3
,

 
 
1
1
,

 
 
1
4
3
4
,

 
 
2
,

 
 
1
4
9
,

 
 
2
5
,

 
 
5
8
,

 
 
3
8
6
,

 
 
7
,

 
 
2
6
5
,

 
 
9
3
2
,

 
 
9
,

 
 
3
8
8
4
,

 
 
1
,

 
 
1
3
9
,

 
 
7
8
9
1
,

 
 
1
7
,

 
 
4
1
,

 
 
8
1
0
,

 
 
3
,

 
 
2
9
7
,

 
 
1
9
7
,

 
 
9
2
,

 
 
8
,

 
 
4
4
,

 
 
1
7
1
8
,

 
 
3
,

 
 
9
2
,

 
 
2
5
1
5
8
,

 
 
6
0
,

 
 
1
0
2
9
,

 
 
1
8
,

 
 
7
,

 
 
1
,

 
 
1
7
1
8
,

 
 
3
,

 
 
6
9
8
6
5
,

 
 
6
9
8
6
6
,

 
 
1
0
4
,

 
 
7
9
5
,

 
 
8
6
,

 
 
1
,

 
 
7
7
8
1
,

 
 
3
,

 
 
7
4
4
6
,

 
 
7
0
9
0
,

 
 
5
,

 
 
4
8
4
6
,

 
 
1
3
,

 
 
1
0
3
5
,

 
 
3
5
5
1
,

 
 
2
,

 
 
1
,

 
 
1
6
0
8
7
4
,

 
 
1
2
0
8
2
,

 
 
1
0
,

 
 
8
3
6
6
9
,

 
 
7
,

 
 
2
2
0
,

 
 
4
8
4
6
,

 
 
4
1
6
,

 
 
1
,

 
 
1
7
1
8
,

 
 
1
,

 
 
4
8
0
3
,

 
 
4
1
6
,

 
 
1
4
8
,

 
 
1
7
1
8
,

 
 
3
,

 
 
7
4
4
6
,

 
 
7
0
9
0
,

 
 
2
4
,

 
 
1
3
6
0
6
,

 
 
1
0
,

 
 
2
4
4
7
6
,

 
 
1
7
,

 
 
9
1
,

 
 
7
1
4
6
,

 
 
2
1
,

 
 
4
5
5
6
4
,

 
 
1
6
0
8
7
5
,

 
 
7
6
,

 
 
3
1
3
2
]
,

 
[
7
,

 
 
6
5
,

 
 
1
3
,

 
 
4
7
,

 
 
5
6
,

 
 
3
9
7
2
3
,

 
 
3
7
9
4
,

 
 
1
,

 
 
6
1
,

 
 
4
7
,

 
 
5
6
,

 
 
1
6
,

 
 
3
9
7
2
3
,

 
 
8
2
6
,

 
 
5
6
6
,

 
 
5
,

 
 
3
9
7
2
3
,

 
 
5
6
,

 
 
1
6
,

 
 
4
9
,

 
 
4
,

 
 
1
3
4
8
,

 
 
2
9
]
,

 
[
3
2
,
 
1
4
1
,
 
1
8
2
5
,
 
2
7
,
 
5
6
1
,
 
2
5
1
5
9
,
 
4
1
3
]
,

 
[
6
,
 
1
2
6
,
 
1
8
,
 
4
,
 
7
5
1
5
,
 
6
1
3
,
 
1
0
6
6
4
9
,
 
8
5
,
 
2
,
 
9
4
,
 
5
8
3
4
,
 
3
1
,
 
4
,
 
1
6
0
8
7
6
]
,

 
[
6
6
5
,

 
 
4
9
4
6
9
,

 
 
4
9
1
7
,

 
 
2
6
,

 
 
4
9
,

 
 
9
9
9
,

 
 
3
8
8
,

 
 
5
1
,

 
 
1
0
7
0
,

 
 
7
9
7
3
,

 
 
1
1
,

 
 
8
4
,

 
 
8
8
8
,

 
 
6
3
,

 
 
7
,

 
 
8
1
,

 
 
1
4
3
,

 
 
5
,

 
 
9
,

 
 
6
,

 
 
5
9
,

 
 
7
0
,

 
 
5
8
0
]
,

 
[
1
5
4
8
5
,
 
5
0
8
1
,
 
1
7
1
9
,
 
1
5
4
8
5
,
 
5
0
8
1
,
 
1
6
0
8
7
7
]
,

 
[
3
2
9
5
,

 
 
3
7
0
,

 
 
1
7
8
,

 
 
1
2
7
,

 
 
3
9
,

 
 
6
,

 
 
5
0
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
3
,

 
 
3
7
0
,

 
 
8
0
7
,

 
 
3
2
1
5
,

 
 
3
6
1
,

 
 
1
6
,

 
 
4
4
5
,

 
 
1
1
4
,

 
 
1
4
4
,

 
 
2
0
1
4
,

 
 
3
,

 
 
1
,

 
 
1
0
9
3
,

 
 
1
8
,

 
 
4
8
3
6
,

 
 
7
,

 
 
4
8
5
,

 
 
1
3
,

 
 
2
6
,

 
 
6
0
,

 
 
4
8
4
7
,

 
 
2
8
8
3
,

 
 
2
4
6
,

 
 
7
3
7
,

 
 
3
0
,

 
 
7
9
,

 
 
7
,

 
 
2
2
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
5
7
9
2
,

 
 
6
,

 
 
2
6
,

 
 
6
,

 
 
1
8
,

 
 
4
7
,

 
 
3
,

 
 
2
6
0
,

 
 
6
4
,

 
 
7
,

 
 
4
1
1
,

 
 
2
,

 
 
1
6
,

 
 
5
1
9
1
,

 
 
5
1
6
]
,

 
[
3
,
 
4
4
3
,
 
4
,
 
3
8
0
,
 
1
0
2
9
8
,
 
4
5
,
 
1
1
7
,
 
1
6
0
8
7
8
,
 
2
5
,
 
5
8
,
 
6
7
4
,
 
5
1
2
,
 
4
2
3
8
5
,
 
1
0
8
6
]
,

 
[
7
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
2
3
5
,

 
 
8
4
1
9
,

 
 
3
,

 
 
6
0
8
1
3
,

 
 
2
,

 
 
4
0
3
,

 
 
9
,

 
 
4
,

 
 
2
4
6
8
,

 
 
5
4
,

 
 
9
9
,

 
 
1
0
6
0
,

 
 
1
3
2
,

 
 
3
,

 
 
1
0
4
,

 
 
1
9
6
3
,

 
 
3
9
1
1
,

 
 
2
4
,

 
 
3
9
7
2
4
,

 
 
3
1
,

 
 
1
6
0
8
7
9
,

 
 
8
0
,

 
 
1
0
4
,

 
 
1
9
6
3
,

 
 
3
4
9
4
,

 
 
2
4
,

 
 
8
7
4
,

 
 
2
,

 
 
1
7
1
7
8
]
,

 
[
1
6
2
1
,

 
 
1
0
5
2
,

 
 
2
0
7
0
,

 
 
3
,

 
 
6
3
7
4
,

 
 
2
9
,

 
 
1
1
,

 
 
8
,

 
 
2
8
3
7
,

 
 
7
4
,

 
 
4
2
0
,

 
 
1
6
2
1
,

 
 
1
0
5
2
,

 
 
6
4
5
1
,

 
 
4
0
,

 
 
1
4
8
,

 
 
1
3
,

 
 
2
9
,

 
 
1
4
3
,

 
 
1
5
1
,

 
 
7
,

 
 
1
7
3
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
2
1
8
,

 
 
8
6
4
,

 
 
1
5
4
3
,

 
 
1
5
1
,

 
 
4
0
,

 
 
4
2
0
,

 
 
1
0
5
2
,

 
 
4
0
,

 
 
1
8
0
6
,

 
 
5
,

 
 
3
8
2
7
,

 
 
1
1
,

 
 
7
3
,

 
 
1
0
0
,

 
 
4
,

 
 
1
5
8
6
,

 
 
6
3
0
,

 
 
1
2
,

 
 
7
1
5
,

 
 
9
0
6
,

 
 
1
0
,

 
 
2
6
8
9
,

 
 
1
2
6
,

 
 
9
4
,

 
 
1
8
2
,

 
 
2
0
,

 
 
3
0
1
7
,

 
 
3
6
,

 
 
3
1
3
2
,

 
 
1
4
1
8
,

 
 
3
6
,

 
 
2
7
7
0
5
,

 
 
2
2
,

 
 
6
,

 
 
1
8
,

 
 
3
6
,

 
 
2
3
4
3
,

 
 
1
9
3
3
,

 
 
7
8
,

 
 
1
4
,

 
 
9
4
,

 
 
1
9
3
3
,

 
 
5
,

 
 
1
7
1
,

 
 
3
5
2
1
,

 
 
1
,

 
 
9
9
2
,

 
 
1
8
,

 
 
6
,

 
 
9
,

 
 
3
9
9
0
]
,

 
[
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
3
1
4
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
3
2
0
,

 
 
1
6
0
8
8
0
,

 
 
5
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
5
0
,

 
 
5
8
4
,

 
 
2
,

 
 
5
1
7
,

 
 
2
0
,

 
 
1
0
9
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
3
2
,

 
 
1
6
7
3
,

 
 
2
5
,

 
 
2
0
9
,

 
 
4
9
2
,

 
 
9
0
0
,

 
 
1
3
,

 
 
4
5
,

 
 
8
5
4
,

 
 
1
0
4
8
,

 
 
2
0
,

 
 
7
1
2
,

 
 
5
,

 
 
1
,

 
 
4
3
5
,

 
 
6
6
,

 
 
5
0
,

 
 
3
4
,

 
 
2
0
,

 
 
2
2
1
,

 
 
2
,

 
 
3
6
9
,

 
 
1
9
0
8
,

 
 
1
0
,

 
 
1
,

 
 
7
9
,

 
 
5
1
5
,

 
 
9
9
5
,

 
 
5
6
7
,

 
 
1
8
,

 
 
6
0
,

 
 
6
1
1
,

 
 
2
2
4
,

 
 
2
,

 
 
3
3
1
8
,

 
 
2
0
,

 
 
1
9
9
0
,

 
 
4
8
2
,

 
 
1
2
9
,

 
 
3
7
4
3
0
,

 
 
3
7
4
3
1
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
9
0
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
4
6
1
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
0
4
,

 
 
5
1
3
,

 
 
1
1
9
9
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
7
4
,

 
 
2
,

 
 
7
9
,

 
 
4
,

 
 
2
9
,

 
 
1
2
7
7
,

 
 
2
0
,

 
 
1
1
0
,

 
 
3
1
5
,

 
 
9
0
7
,

 
 
3
,

 
 
1
6
3
9
,

 
 
2
0
0
8
,

 
 
2
7
1
2
,

 
 
1
2
9
,

 
 
8
3
,

 
 
7
4
,

 
 
2
,

 
 
2
0
9
1
,

 
 
2
7
,

 
 
2
3
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
1
9
0
,

 
 
6
8
6
,

 
 
9
9
1
,

 
 
6
8
2
,

 
 
4
6
1
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
6
8
6
,

 
 
5
6
0
,

 
 
1
7
6
9
,

 
 
1
6
0
,

 
 
1
9
0
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
2
7
9
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
4
0
4
,

 
 
1
2
1
,

 
 
1
9
0
,

 
 
4
1
7
,

 
 
5
6
9
,

 
 
1
8
2
0
,

 
 
6
3
6
,

 
 
2
5
4
,

 
 
5
1
2
2
,

 
 
1
2
5
,

 
 
2
,

 
 
2
1
9
,

 
 
4
,

 
 
2
1
4
,

 
 
1
2
1
,

 
 
1
2
4
,

 
 
1
1
5
,

 
 
3
6
2
4
,

 
 
1
2
1
,

 
 
2
9
]
,

 
[
2
3
3
,

 
 
9
8
1
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
4
5
5
,

 
 
5
2
6
,

 
 
4
8
,

 
 
2
0
,

 
 
2
7
7
0
6
,

 
 
1
4
5
4
,

 
 
2
3
9
,

 
 
1
5
9
,

 
 
5
,

 
 
8
9
,

 
 
1
6
0
8
8
1
,

 
 
5
7
,

 
 
5
3
9
,

 
 
7
7
3
,

 
 
2
0
,

 
 
1
5
9
0
,

 
 
8
6
1
,

 
 
7
6
,

 
 
3
2
5
,

 
 
1
0
1
,

 
 
2
3
9
,

 
 
1
1
,

 
 
4
6
,

 
 
6
9
9
,

 
 
1
8
9
2
]
,

 
[
1
4
7
2
2
,

 
 
5
7
5
1
,

 
 
6
2
,

 
 
1
,

 
 
6
2
9
,

 
 
3
4
8
9
,

 
 
6
4
2
8
,

 
 
5
,

 
 
8
0
9
,

 
 
4
2
7
6
,

 
 
1
2
,

 
 
9
2
,

 
 
1
4
0
1
,

 
 
1
0
,

 
 
1
9
1
6
,

 
 
3
9
5
9
,

 
 
1
9
,

 
 
4
4
,

 
 
1
7
8
8
,

 
 
1
0
,

 
 
2
1
5
9
8
,

 
 
3
2
6
,

 
 
9
8
7
1
,

 
 
2
,

 
 
1
3
,

 
 
2
4
8
,

 
 
1
,

 
 
1
9
1
6
,

 
 
3
7
4
7
,

 
 
6
5
8
2
,

 
 
5
,

 
 
1
,

 
 
1
3
1
1
,

 
 
1
8
,

 
 
3
1
3
,

 
 
1
0
5
7
,

 
 
1
0
,

 
 
6
2
9
9
,

 
 
5
,

 
 
2
8
3
0
,

 
 
2
,

 
 
1
7
8
8
,

 
 
1
,

 
 
1
4
7
2
2
,

 
 
5
7
5
1
]
,

 
[
6
9
8
6
7
,

 
 
1
0
6
6
5
0
,

 
 
1
6
0
8
8
2
,

 
 
4
2
3
8
6
,

 
 
3
7
3
3
,

 
 
5
0
0
5
,

 
 
1
8
,

 
 
4
0
,

 
 
1
4
,

 
 
1
1
5
,

 
 
9
3
5
9
,

 
 
1
9
9
,

 
 
1
9
,

 
 
5
7
,

 
 
5
9
,

 
 
5
7
1
,

 
 
2
0
6
8
,

 
 
1
7
,

 
 
5
4
3
6
6
,

 
 
2
0
0
4
,

 
 
5
9
,

 
 
4
1
1
,

 
 
8
8
,

 
 
5
4
3
6
6
,

 
 
3
5
1
,

 
 
1
6
2
,

 
 
1
1
1
4
,

 
 
7
2
2
7
,

 
 
1
5
,

 
 
1
5
2
4
,

 
 
1
6
9
3
,

 
 
8
8
,

 
 
1
5
,

 
 
1
3
,

 
 
2
9
,

 
 
2
0
0
4
,

 
 
3
,

 
 
1
,

 
 
1
7
2
8
,

 
 
4
5
,

 
 
4
9
,

 
 
2
4
6
,

 
 
5
3
0
,

 
 
8
8
,

 
 
6
9
,

 
 
1
1
,

 
 
8
,

 
 
3
0
9
,

 
 
2
4
7
,

 
 
1
4
6
8
,

 
 
2
,

 
 
4
9
4
7
0
,

 
 
5
,

 
 
6
1
,

 
 
2
1
5
9
9
,

 
 
1
7
2
8
,

 
 
2
5
,

 
 
1
3
,

 
 
2
3
,

 
 
4
5
,

 
 
1
6
,

 
 
1
0
,

 
 
1
2
8
4
9
,

 
 
7
9
,

 
 
3
2
6
,

 
 
3
1
7
8
,

 
 
6
4
5
2
,

 
 
7
4
2
3
,

 
 
6
3
7
5
]
,

 
[
7
0
5
,

 
 
2
,

 
 
1
6
,

 
 
3
1
4
0
,

 
 
1
4
7
,

 
 
3
3
,

 
 
3
0
,

 
 
4
1
4
,

 
 
2
6
,

 
 
1
3
9
2
,

 
 
3
0
,

 
 
8
1
0
,

 
 
2
4
8
,

 
 
4
,

 
 
2
5
0
2
,

 
 
3
,

 
 
1
4
3
7
5
,

 
 
1
0
5
0
,

 
 
1
0
1
4
,

 
 
2
5
,

 
 
2
8
8
,

 
 
1
8
2
,

 
 
1
7
9
5
,

 
 
3
1
,

 
 
1
0
5
0
,

 
 
6
2
0
,

 
 
9
,

 
 
1
1
1
3
5
,

 
 
2
4
6
,

 
 
1
9
1
1
,

 
 
1
,

 
 
4
8
0
2
,

 
 
4
7
0
,

 
 
1
2
4
,

 
 
5
,

 
 
2
4
6
,

 
 
1
6
0
8
8
3
,

 
 
1
,

 
 
3
2
1
5
,

 
 
2
0
5
,

 
 
3
8
8
,

 
 
5
1
,

 
 
1
3
4
6
5
,

 
 
5
,

 
 
9
4
,

 
 
7
7
3
,

 
 
1
7
,

 
 
4
,

 
 
2
8
9
2
,

 
 
7
,

 
 
2
1
0
9
2
,

 
 
2
1
,

 
 
3
8
,

 
 
7
,

 
 
1
3
6
,

 
 
1
8
2
4
,

 
 
1
7
,

 
 
2
6
1
,

 
 
1
0
5
,

 
 
1
5
,

 
 
1
,

 
 
2
8
,

 
 
1
2
4
,

 
 
5
,

 
 
1
,

 
 
9
1
8
,

 
 
3
,

 
 
1
,

 
 
2
0
5
,

 
 
5
,

 
 
1
0
6
,

 
 
8
5
,

 
 
2
,

 
 
4
6
0
,

 
 
2
,

 
 
1
,

 
 
1
0
2
1
,

 
 
1
2
4
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
1
0
1
0
,

 
 
4
1
,

 
 
1
5
3
,

 
 
3
6
3
,

 
 
5
8
,

 
 
1
3
8
8
,

 
 
2
,

 
 
1
1
8
,

 
 
2
6
5
0
,

 
 
4
9
0
,

 
 
8
5
,

 
 
2
8
,

 
 
5
3
1
]
,

 
[
1
1
2
8
5
,

 
 
2
8
6
6
6
,

 
 
1
5
2
8
5
,

 
 
3
0
,

 
 
4
0
0
,

 
 
9
5
,

 
 
1
2
,

 
 
2
0
,

 
 
1
2
7
4
,

 
 
9
1
5
,

 
 
5
,

 
 
1
5
8
3
,

 
 
3
5
7
,

 
 
1
3
,

 
 
2
3
,

 
 
4
9
,

 
 
4
,

 
 
1
3
3
2
,

 
 
7
,

 
 
3
3
3
,

 
 
6
9
8
6
8
,

 
 
6
3
3
,

 
 
2
,

 
 
9
4
,

 
 
2
4
8
8
,

 
 
3
,

 
 
9
3
3
,

 
 
2
2
4
,

 
 
1
5
,

 
 
2
0
2
1
6
,

 
 
1
8
0
1
,

 
 
8
3
,

 
 
3
8
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
8
4
2
5
,

 
 
7
5
,

 
 
4
8
,

 
 
1
9
1
,

 
 
2
,

 
 
4
3
7
5
,

 
 
5
,

 
 
1
0
9
7
,

 
 
7
,

 
 
6
5
,

 
 
3
1
8
5
,

 
 
3
9
6
,

 
 
8
,

 
 
4
,

 
 
8
7
5
,

 
 
3
,

 
 
1
,

 
 
9
7
1
,

 
 
5
,

 
 
6
5
3
,

 
 
2
1
0
0
,

 
 
1
7
,

 
 
1
0
1
,

 
 
8
4
,

 
 
1
2
7
,

 
 
1
,

 
 
1
9
4
3
0
,

 
 
1
2
,

 
 
1
5
6
9
1
,

 
 
1
2
,

 
 
3
0
0
,

 
 
5
8
5
,

 
 
3
1
,

 
 
8
3
6
7
0
,

 
 
1
7
2
3
,

 
 
3
,

 
 
2
7
,

 
 
4
2
9
8
,

 
 
1
9
7
0
,

 
 
1
8
1
7
,

 
 
3
9
4
5
,

 
 
6
6
9
]
,

 
[
5
4
3
1
,

 
 
4
6
3
9
,

 
 
4
9
,

 
 
3
5
,

 
 
6
4
5
3
,

 
 
4
6
3
,

 
 
2
8
2
,

 
 
7
6
,

 
 
1
,

 
 
1
3
7
5
8
,

 
 
5
,

 
 
5
4
3
6
7
,

 
 
1
9
2
,

 
 
6
0
,

 
 
5
3
6
,

 
 
6
6
9
,

 
 
4
6
,

 
 
1
2
4
7
,

 
 
7
9
2
]
,

 
[
2
2
,

 
 
6
,

 
 
2
6
3
,

 
 
2
1
,

 
 
2
4
8
3
,

 
 
1
6
0
8
8
4
,

 
 
8
4
,

 
 
3
8
,

 
 
3
5
,

 
 
7
2
3
,

 
 
1
2
,

 
 
2
5
7
2
,

 
 
7
8
8
,

 
 
4
3
7
6
,

 
 
3
4
4
,

 
 
5
,

 
 
3
8
,

 
 
3
5
,

 
 
1
,

 
 
1
5
7
,

 
 
6
5
4
,

 
 
1
2
3
,

 
 
9
,

 
 
2
4
,

 
 
4
6
4
7
,

 
 
1
7
7
,

 
 
3
1
9
,

 
 
5
2
,

 
 
1
9
9
,

 
 
1
0
3
4
,

 
 
1
,

 
 
1
5
7
,

 
 
1
2
3
,

 
 
5
2
,

 
 
4
6
4
7
,

 
 
1
1
,

 
 
7
6
,

 
 
3
,

 
 
1
,

 
 
1
5
7
2
,

 
 
3
8
,

 
 
2
2
,

 
 
7
,

 
 
7
7
1
,

 
 
1
5
,

 
 
2
0
,

 
 
1
0
7
,

 
 
6
8
8
4
,

 
 
1
0
6
6
5
1
,

 
 
5
,

 
 
7
,

 
 
1
6
7
,

 
 
9
,

 
 
4
8
6
,

 
 
1
5
,

 
 
2
0
,

 
 
6
8
8
4
,

 
 
8
,

 
 
1
5
5
,

 
 
4
2
3
,

 
 
1
6
,

 
 
5
5
6
,

 
 
4
2
7
,

 
 
5
,

 
 
7
,

 
 
1
8
7
,

 
 
1
1
,

 
 
6
6
8
,

 
 
1
1
,

 
 
1
2
7
9
,

 
 
3
3
1
,

 
 
5
,

 
 
7
,

 
 
6
6
,

 
 
1
8
7
,

 
 
1
8
3
,

 
 
1
2
3
,

 
 
4
3
,

 
 
2
6
3
,

 
 
2
1
,

 
 
1
5
8
,

 
 
2
9
8
,

 
 
9
,

 
 
2
,

 
 
2
0
,

 
 
6
8
8
4
,

 
 
2
5
,

 
 
4
3
,

 
 
6
,

 
 
1
6
,

 
 
1
3
4
6
6
,

 
 
1
9
7
,

 
 
1
0
6
6
5
1
,

 
 
6
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
1
6
0
9
,

 
 
3
0
5
4
,

 
 
7
0
7
3
,

 
 
6
4
,

 
 
3
2
,

 
 
1
6
0
8
8
5
,

 
 
4
5
5
6
5
,

 
 
1
7
,

 
 
2
2
,

 
 
4
,

 
 
1
3
8
,

 
 
2
4
7
,

 
 
3
8
,

 
 
8
,

 
 
2
0
,

 
 
1
4
5
,

 
 
3
4
,

 
 
6
,

 
 
1
7
0
,

 
 
4
,

 
 
1
5
9
0
0
,

 
 
1
6
2
,

 
 
2
5
,

 
 
2
2
,

 
 
1
4
,

 
 
3
8
,

 
 
8
,

 
 
2
0
,

 
 
1
9
9
0
,

 
 
2
,

 
 
2
4
4
7
7
,

 
 
4
,

 
 
2
5
7
2
,

 
 
7
8
8
,

 
 
4
3
7
6
,

 
 
2
5
,

 
 
5
5
,

 
 
6
1
,

 
 
2
5
7
2
,

 
 
7
8
8
,

 
 
4
3
7
6
,

 
 
1
2
3
,

 
 
5
,

 
 
9
6
,

 
 
5
5
,

 
 
6
1
,

 
 
1
2
3
,

 
 
3
,

 
 
4
,

 
 
1
5
9
0
0
,

 
 
1
6
2
,

 
 
1
0
,

 
 
4
,

 
 
2
7
8
2
,

 
 
6
4
1
]
,

 
[
1
7
,

 
 
4
,

 
 
2
8
6
6
7
,

 
 
9
,

 
 
8
,

 
 
1
0
0
6
,

 
 
3
0
8
2
,

 
 
6
,

 
 
5
6
,

 
 
1
6
,

 
 
7
4
9
,

 
 
9
,

 
 
2
0
5
,

 
 
6
2
,

 
 
7
9
,

 
 
3
2
6
,

 
 
8
7
,

 
 
2
4
5
9
,

 
 
1
,

 
 
6
9
4
3
,

 
 
1
4
8
7
,

 
 
3
,

 
 
1
,

 
 
4
2
5
,

 
 
1
3
3
,

 
 
2
,

 
 
7
9
,

 
 
3
2
6
]
,

 
[
3
8
,
 
3
5
,
 
2
8
1
,
 
4
2
8
,
 
1
8
7
9
,
 
1
5
6
9
2
,
 
2
3
1
7
7
,
 
3
2
1
,
 
3
2
1
,
 
2
8
,
 
8
,
 
3
6
,
 
1
0
3
7
,
 
7
0
9
1
]
,

 
[
9
5
,
 
1
2
,
 
2
6
1
6
,
 
1
3
]
,

 
[
4
4
,

 
 
1
4
,

 
 
1
2
6
,

 
 
5
3
,

 
 
8
7
,

 
 
2
1
9
,

 
 
9
,

 
 
1
,

 
 
3
9
2
,

 
 
3
,

 
 
6
8
9
,

 
 
9
1
,

 
 
1
,

 
 
1
3
9
7
,

 
 
1
2
0
,

 
 
3
,

 
 
1
,

 
 
3
5
4
0
5
,

 
 
3
,

 
 
2
7
0
5
,

 
 
1
6
,

 
 
2
5
1
3
1
,

 
 
2
3
8
,

 
 
6
7
7
,

 
 
2
1
,

 
 
4
,

 
 
2
6
0
,

 
 
6
1
,

 
 
2
4
3
5
,

 
 
1
,

 
 
6
8
9
,

 
 
3
5
4
0
5
,

 
 
1
8
0
,

 
 
1
6
6
,

 
 
8
,

 
 
1
1
8
5
5
,

 
 
3
1
2
,

 
 
1
6
0
8
8
6
,

 
 
3
5
4
0
6
,

 
 
1
6
8
,

 
 
4
4
,

 
 
4
6
2
,

 
 
4
2
3
8
7
,

 
 
2
6
,

 
 
7
8
5
4
,

 
 
2
2
,

 
 
1
,

 
 
1
3
9
,

 
 
8
2
4
,

 
 
2
4
,

 
 
2
0
0
6
,

 
 
2
,

 
 
1
,

 
 
2
3
8
5
,

 
 
1
7
,

 
 
1
1
7
,

 
 
1
,

 
 
1
6
0
8
8
7
,

 
 
2
5
,

 
 
3
8
4
4
,

 
 
2
9
7
0
6
,

 
 
1
,

 
 
1
1
7
4
9
,

 
 
4
3
,

 
 
1
6
,

 
 
4
9
4
7
1
,

 
 
1
6
,

 
 
1
7
7
4
,

 
 
1
7
,

 
 
2
,

 
 
6
2
,

 
 
8
9
4
,

 
 
1
,

 
 
2
5
1
6
0
,

 
 
2
0
1
8
,

 
 
3
7
4
3
2
,

 
 
1
9
3
4
,

 
 
1
0
,

 
 
1
,

 
 
4
5
3
,

 
 
6
,

 
 
9
4
,

 
 
1
,

 
 
1
0
8
0
9
,

 
 
5
,

 
 
2
0
8
4
,

 
 
1
0
1
8
,

 
 
1
,

 
 
4
9
4
7
2
,

 
 
5
8
0
4
,

 
 
5
7
0
4
,

 
 
2
1
2
1
,

 
 
4
7
3
9
]
,

 
[
7
0
2
0
,
 
4
6
,
 
3
5
,
 
2
0
,
 
2
9
7
0
7
,
 
2
5
1
6
1
,
 
5
,
 
9
6
,
 
2
0
,
 
5
4
3
6
8
]
,

 
[
6
,

 
 
7
0
,

 
 
7
,

 
 
2
4
,

 
 
9
5
0
,

 
 
1
1
0
4
,

 
 
1
2
6
,

 
 
2
5
1
9
,

 
 
3
7
,

 
 
1
5
0
,

 
 
7
,

 
 
4
1
2
9
,

 
 
3
0
,

 
 
1
1
0
3
,

 
 
6
4
,

 
 
1
5
1
,

 
 
7
,

 
 
3
3
9
9
,

 
 
9
,

 
 
7
,

 
 
2
4
,

 
 
8
0
0
,

 
 
7
,

 
 
2
4
,

 
 
2
5
7
,

 
 
2
,

 
 
4
,

 
 
2
9
2
7
,

 
 
3
7
7
5
,

 
 
3
,

 
 
2
0
7
0
,

 
 
5
,

 
 
1
0
9
5
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
8
0
3
,

 
 
1
2
,

 
 
8
0
,

 
 
7
,

 
 
2
4
,

 
 
1
5
,

 
 
1
,

 
 
6
1
2
,

 
 
8
0
,

 
 
7
,

 
 
2
4
,

 
 
6
1
6
,

 
 
1
5
0
,

 
 
7
5
,

 
 
1
3
3
7
,

 
 
3
0
,

 
 
1
1
0
3
,

 
 
5
1
,

 
 
2
3
9
,

 
 
4
6
6
,

 
 
1
5
1
,

 
 
7
,

 
 
7
7
8
,

 
 
8
8
,

 
 
3
0
,

 
 
1
1
0
3
,

 
 
5
1
,

 
 
5
6
5
2
,

 
 
3
7
,

 
 
7
1
,

 
 
4
9
,

 
 
3
6
,

 
 
5
1
1
4
,

 
 
7
4
,

 
 
1
,

 
 
7
6
2
,

 
 
1
6
0
8
8
8
,

 
 
6
5
,

 
 
3
,

 
 
9
0
4
5
,

 
 
1
7
,

 
 
9
1
,

 
 
2
0
2
9
,

 
 
1
2
,

 
 
1
,

 
 
2
3
8
0
,

 
 
3
,

 
 
1
,

 
 
6
5
5
4
,

 
 
4
8
,

 
 
1
1
,

 
 
2
4
,

 
 
3
4
9
,

 
 
5
5
,

 
 
9
8
,

 
 
2
,

 
 
1
9
7
4
,

 
 
2
1
,

 
 
1
3
,

 
 
8
,

 
 
1
2
5
1
,

 
 
6
9
,

 
 
1
,

 
 
5
7
5
2
,

 
 
1
8
,

 
 
1
,

 
 
1
1
5
7
1
,

 
 
7
5
,

 
 
6
4
,

 
 
4
5
5
6
6
,

 
 
1
6
0
8
8
9
,

 
 
1
6
0
8
9
0
,

 
 
3
3
7
0
4
,

 
 
2
5
1
6
2
,

 
 
6
9
1
5
,

 
 
1
6
0
8
9
1
,

 
 
1
6
0
8
9
2
,

 
 
1
6
0
8
9
3
,

 
 
5
4
3
6
9
,

 
 
7
8
1
7
,

 
 
2
3
1
8
0
,

 
 
2
6
3
6
,

 
 
1
6
0
8
9
4
,

 
 
1
6
0
8
9
5
,

 
 
9
5
1
9
,

 
 
3
7
4
3
3
,

 
 
2
8
6
6
8
,

 
 
3
2
3
0
,

 
 
3
2
0
2
,

 
 
4
0
,

 
 
5
7
5
2
,

 
 
1
,

 
 
8
8
3
5
,

 
 
7
2
0
1
,

 
 
6
4
,

 
 
1
8
,

 
 
3
2
6
4
,

 
 
1
,

 
 
2
2
1
1
7
,

 
 
7
8
4
,

 
 
8
5
6
,

 
 
6
3
,

 
 
6
0
8
,

 
 
2
0
2
1
7
,

 
 
8
1
0
,

 
 
1
5
9
0
1
,

 
 
3
3
7
0
5
,

 
 
1
6
0
8
9
6
,

 
 
2
5
9
5
9
,

 
 
9
6
,

 
 
2
3
8
,

 
 
5
7
2
,

 
 
4
,

 
 
1
4
1
7
7
,

 
 
1
6
1
5
5
,

 
 
1
6
0
8
9
7
,

 
 
4
9
,

 
 
2
,

 
 
1
0
9
,

 
 
4
,

 
 
2
6
0
,

 
 
4
0
,

 
 
7
,

 
 
3
4
9
,

 
 
6
3
,

 
 
5
7
5
2
,

 
 
1
1
6
2
,

 
 
8
,

 
 
1
9
6
8
,

 
 
3
0
,

 
 
1
3
3
4
,

 
 
1
6
2
,

 
 
3
0
,

 
 
5
8
7
2
,

 
 
4
3
0
7
,

 
 
1
2
5
1
,

 
 
1
6
0
8
9
8
,

 
 
1
6
0
8
9
9
,

 
 
3
7
,

 
 
2
5
,

 
 
1
4
8
8
,

 
 
2
5
8
7
,

 
 
7
,

 
 
4
8
,

 
 
2
,

 
 
1
3
6
7
,

 
 
2
3
5
,

 
 
2
2
4
6
,

 
 
5
,

 
 
4
5
5
,

 
 
3
9
7
2
5
,

 
 
1
4
7
,

 
 
3
3
,

 
 
3
7
,

 
 
7
2
8
,

 
 
2
7
,

 
 
7
7
9
,

 
 
2
2
7
0
,

 
 
6
1
6
,

 
 
1
6
2
,

 
 
1
,

 
 
3
5
5
2
,

 
 
7
2
0
1
,

 
 
6
4
,

 
 
1
8
,

 
 
4
9
5
4
,

 
 
7
0
3
6
,

 
 
8
3
4
5
,

 
 
8
8
3
0
,

 
 
2
1
,

 
 
1
,

 
 
2
6
1
7
,

 
 
3
4
9
4
,

 
 
3
,

 
 
4
,

 
 
1
6
1
5
,

 
 
3
6
5
,

 
 
4
1
2
,

 
 
3
4
3
,

 
 
2
4
2
0
,

 
 
1
3
2
,

 
 
3
,

 
 
1
,

 
 
9
0
4
5
,

 
 
6
4
,

 
 
1
8
,

 
 
8
6
5
3
,

 
 
2
6
7
7
,

 
 
5
7
4
8
,

 
 
5
,

 
 
6
3
5
,

 
 
9
4
6
1
,

 
 
2
6
,

 
 
7
8
5
,

 
 
2
5
7
,

 
 
2
,

 
 
2
9
2
7
,

 
 
2
9
7
0
8
,

 
 
4
1
2
7
,

 
 
3
2
,

 
 
1
,

 
 
7
6
2
,

 
 
3
5
5
2
,

 
 
7
2
0
1
,

 
 
6
2
,

 
 
6
5
,

 
 
7
8
5
,

 
 
1
6
6
3
,

 
 
3
8
2
0
,

 
 
6
9
,

 
 
5
1
,

 
 
8
6
,

 
 
9
0
8
,

 
 
5
,

 
 
3
5
2
0
,

 
 
1
5
,

 
 
9
2
,

 
 
8
1
0
,

 
 
1
0
2
3
,

 
 
6
5
5
4
,

 
 
1
6
4
6
,

 
 
1
9
9
,

 
 
2
6
3
2
,

 
 
2
,

 
 
1
5
9
0
2
,

 
 
3
7
]
,

 
[
7
0
4
7
,

 
 
7
4
,

 
 
3
2
1
9
0
,

 
 
5
8
4
,

 
 
2
0
4
7
,

 
 
8
,

 
 
1
,

 
 
1
8
3
8
,

 
 
9
,

 
 
6
7
1
0
,

 
 
1
0
8
1
0
,

 
 
6
,

 
 
1
0
3
5
,

 
 
3
7
,

 
 
1
2
6
,

 
 
1
4
3
3
,

 
 
2
,

 
 
1
3
7
4
,

 
 
1
,

 
 
3
0
1
7
,

 
 
3
5
2
,

 
 
4
9
,

 
 
3
5
2
,

 
 
5
3
,

 
 
3
9
,

 
 
9
4
,

 
 
6
7
7
,

 
 
7
4
,

 
 
3
5
,

 
 
9
]
,

 
[
1
9
4
3
1
,

 
 
1
7
3
,

 
 
7
,

 
 
8
1
,

 
 
3
1
,

 
 
1
9
4
3
1
,

 
 
6
0
4
7
,

 
 
1
7
5
,

 
 
6
2
8
,

 
 
4
2
,

 
 
6
6
,

 
 
3
2
8
6
,

 
 
1
3
,

 
 
1
6
0
9
0
0
,

 
 
3
6
,

 
 
7
,

 
 
5
0
2
,

 
 
1
1
]
,

 
[
4
3
,
 
6
,
 
4
8
9
,
 
5
8
3
5
,
 
1
5
,
 
8
3
6
7
1
,
 
2
6
4
,
 
8
4
,
 
1
6
0
9
0
1
]
,

 
[
2
3
8
0
,

 
 
4
,

 
 
3
5
9
,

 
 
1
5
5
,

 
 
8
7
4
,

 
 
1
2
,

 
 
8
4
6
9
,

 
 
9
,

 
 
4
7
,

 
 
2
8
9
,

 
 
2
,

 
 
8
0
5
,

 
 
1
,

 
 
6
7
2
,

 
 
1
0
9
,

 
 
3
9
6
0
,

 
 
5
3
,

 
 
9
4
,

 
 
4
,

 
 
3
5
9
,

 
 
2
9
7
0
9
,

 
 
3
5
,

 
 
1
2
3
5
,

 
 
9
,

 
 
7
5
4
,

 
 
2
,

 
 
2
3
0
5
,

 
 
5
3
7
5
]
,

 
[
4
5
5
6
7
,

 
 
5
,

 
 
2
0
1
,

 
 
5
5
3
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
1
,

 
 
4
2
2
,

 
 
5
0
5
,

 
 
1
3
1
,

 
 
7
1
3
,

 
 
2
,

 
 
1
,

 
 
4
5
5
6
7
,

 
 
2
9
,

 
 
1
8
,

 
 
5
9
5
5
,

 
 
5
8
,

 
 
5
8
9
4
,

 
 
1
2
,

 
 
4
4
,

 
 
2
5
8
4
,

 
 
2
1
2
,

 
 
7
2
,

 
 
1
4
,

 
 
1
0
0
6
,

 
 
1
3
1
4
,

 
 
3
5
,

 
 
1
,

 
 
4
2
2
,

 
 
1
0
,

 
 
6
0
,

 
 
1
0
4
3
1
,

 
 
4
3
0
2
,

 
 
7
4
,

 
 
6
0
,

 
 
2
3
7
2
,

 
 
5
,

 
 
1
1
1
1
,

 
 
1
8
,

 
 
8
3
8
7
,

 
 
2
6
,

 
 
3
3
,

 
 
1
,

 
 
1
3
9
,

 
 
8
5
,

 
 
6
,

 
 
1
8
0
7
4
,

 
 
1
6
4
8
,

 
 
2
,

 
 
1
5
6
,

 
 
3
7
1
,

 
 
2
4
9
8
,

 
 
1
4
6
5
,

 
 
6
,

 
 
3
6
4
,

 
 
2
,

 
 
9
4
,

 
 
1
2
6
,

 
 
3
4
8
4
,

 
 
5
0
4
,

 
 
2
1
,

 
 
1
7
1
7
9
,

 
 
3
4
,

 
 
1
0
1
0
,

 
 
1
2
6
,

 
 
1
2
2
,

 
 
4
,

 
 
1
6
9
,

 
 
2
,

 
 
7
0
,

 
 
3
8
,

 
 
4
,

 
 
3
7
8
4
,

 
 
8
]
,

 
[
2
8
1
,
 
5
1
4
,
 
8
0
7
,
 
1
,
 
3
3
8
,
 
3
,
 
1
,
 
2
9
,
 
1
6
,
 
1
7
7
9
,
 
2
5
,
 
1
1
1
0
,
 
3
8
2
,
 
3
,
 
2
8
1
,
 
5
1
4
]
,

 
[
7
,

 
 
2
6
3
,

 
 
2
1
,

 
 
1
0
6
6
5
2
,

 
 
2
3
8
,

 
 
7
,

 
 
1
9
4
9
,

 
 
2
1
7
1
,

 
 
1
9
7
1
,

 
 
2
6
2
,

 
 
1
1
6
6
,

 
 
1
3
8
0
,

 
 
4
4
,

 
 
4
7
,

 
 
3
3
1
,

 
 
2
4
,

 
 
5
5
1
2
,

 
 
3
7
,

 
 
7
3
,

 
 
1
5
,

 
 
1
3
,

 
 
1
0
,

 
 
1
,

 
 
5
6
2
,

 
 
3
,

 
 
1
6
1
2
,

 
 
3
1
9
,

 
 
1
9
7
,

 
 
7
,

 
 
4
5
,

 
 
1
9
3
,

 
 
9
,

 
 
6
1
4
,

 
 
2
2
1
1
8
,

 
 
1
0
,

 
 
1
,

 
 
3
8
0
7
,

 
 
3
,

 
 
2
6
1
,

 
 
7
8
2
,

 
 
6
0
4
,

 
 
1
0
6
,

 
 
1
8
,

 
 
1
1
3
5
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
7
,

 
 
4
5
,

 
 
6
6
,

 
 
1
9
3
,

 
 
1
2
7
,

 
 
9
,

 
 
6
0
,

 
 
3
3
7
0
6
,

 
 
6
4
,

 
 
7
5
4
,

 
 
2
,

 
 
1
6
,

 
 
1
7
6
1
,

 
 
1
,

 
 
8
1
4
1
,

 
 
9
0
9
,

 
 
4
2
1
,

 
 
2
1
,

 
 
1
,

 
 
8
1
4
1
,

 
 
9
0
9
,

 
 
8
3
1
,

 
 
1
3
,

 
 
2
8
,

 
 
2
3
,

 
 
8
,

 
 
3
5
,

 
 
1
,

 
 
4
2
1
,

 
 
1
4
,

 
 
1
,

 
 
8
3
1
,

 
 
6
2
,

 
 
4
2
,

 
 
2
7
,

 
 
2
3
,

 
 
3
,

 
 
6
8
,

 
 
1
7
0
]
,

 
[
1
9
4
3
2
,

 
 
3
7
9
,

 
 
7
,

 
 
1
7
3
,

 
 
6
0
,

 
 
2
3
4
,

 
 
6
4
,

 
 
7
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
3
4
4
3
,

 
 
1
9
4
3
2
,

 
 
1
0
2
,

 
 
3
8
1
,

 
 
2
2
4
4
,

 
 
6
6
3
,

 
 
1
6
3
,

 
 
4
8
,

 
 
1
3
,

 
 
1
2
,

 
 
4
,

 
 
2
5
0
,

 
 
8
5
]
,

 
[
7
,
 
9
0
9
,
 
1
2
,
 
2
4
3
4
,
 
1
6
0
9
0
2
,
 
2
3
8
,
 
1
1
,
 
1
0
3
,
 
1
6
,
 
5
7
3
,
 
2
1
,
 
4
,
 
4
2
7
3
,
 
8
0
4
5
]
,

 
[
1
4
4
2
,
 
2
7
,
 
4
0
5
,
 
1
1
8
,
 
6
7
,
 
2
2
5
,
 
1
0
6
6
5
3
]
,

 
[
2
0
,

 
 
2
4
9
9
,

 
 
5
0
,

 
 
1
,

 
 
8
8
6
,

 
 
6
9
7
,

 
 
6
,

 
 
1
4
6
,

 
 
5
0
9
,

 
 
1
0
6
6
5
4
,

 
 
1
6
0
9
0
3
,

 
 
1
6
0
9
0
4
,

 
 
4
7
2
,

 
 
1
,

 
 
6
0
1
,

 
 
6
,

 
 
4
1
6
,

 
 
1
0
,

 
 
1
,

 
 
1
1
9
,

 
 
1
3
5
2
,

 
 
1
6
7
,

 
 
4
4
0
,

 
 
1
5
,

 
 
1
1
3
,

 
 
2
8
6
6
9
,

 
 
5
8
,

 
 
9
3
,

 
 
8
0
0
,

 
 
4
9
6
,

 
 
7
,

 
 
1
5
0
9
,

 
 
1
5
8
0
,

 
 
9
,

 
 
1
3
,

 
 
2
4
,

 
 
4
,

 
 
2
0
0
,

 
 
1
2
3
,

 
 
4
6
3
9
,

 
 
2
7
2
,

 
 
1
5
4
0
,

 
 
1
3
7
5
2
,

 
 
3
4
4
,

 
 
1
2
,

 
 
9
2
,

 
 
1
1
4
,

 
 
9
9
1
,

 
 
2
7
4
,

 
 
8
0
3
0
,

 
 
2
4
5
0
,

 
 
3
2
0
4
,

 
 
2
7
4
,

 
 
6
3
3
,

 
 
3
6
,

 
 
2
2
,

 
 
1
3
,

 
 
2
4
,

 
 
4
,

 
 
4
6
3
9
,

 
 
2
7
2
,

 
 
1
2
3
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
4
,

 
 
2
0
0
,

 
 
1
2
3
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
3
3
6
,

 
 
5
4
3
7
0
,

 
 
3
,

 
 
1
,

 
 
1
0
5
,

 
 
1
1
4
7
,

 
 
5
,

 
 
6
1
,

 
 
1
0
5
,

 
 
1
6
2
3
,

 
 
2
1
,

 
 
1
3
,

 
 
1
2
3
,

 
 
2
,

 
 
3
7
9
,

 
 
1
2
,

 
 
4
4
1
,

 
 
2
5
6
9
,

 
 
3
,

 
 
6
1
7
,

 
 
2
4
9
,

 
 
2
8
2
,

 
 
1
1
,

 
 
4
4
0
,

 
 
3
3
,

 
 
1
1
3
,

 
 
2
8
6
6
9
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
2
0
2
,

 
 
1
0
3
,

 
 
6
,

 
 
5
0
,

 
 
6
9
8
6
9
,

 
 
1
1
,

 
 
2
]
,

 
[
4
1
8
5
,
 
4
9
4
7
3
,
 
7
1
9
]
,

 
[
3
6
,

 
 
1
1
7
0
,

 
 
2
0
,

 
 
2
6
7
6
7
,

 
 
6
,

 
 
1
8
,

 
 
1
5
3
,

 
 
2
4
7
,

 
 
7
5
,

 
 
3
4
,

 
 
2
5
6
,

 
 
7
8
1
8
,

 
 
7
5
9
6
,

 
 
3
6
0
,

 
 
1
7
0
1
,

 
 
2
9
5
3
,

 
 
3
2
6
9
,

 
 
1
5
,

 
 
1
,

 
 
1
4
3
,

 
 
6
5
4
,

 
 
3
,

 
 
2
3
0
,

 
 
6
,

 
 
1
3
1
,

 
 
4
,

 
 
1
0
2
,

 
 
3
8
1
,

 
 
4
5
7
,

 
 
3
5
,

 
 
2
8
,

 
 
2
3
0
,

 
 
5
,

 
 
7
,

 
 
3
3
2
1
,

 
 
6
,

 
 
8
6
,

 
 
2
4
7
,

 
 
5
,

 
 
6
,

 
 
3
5
6
3
,

 
 
3
0
,

 
 
9
6
8
,

 
 
3
3
6
,

 
 
1
7
,

 
 
4
,

 
 
7
7
7
,

 
 
3
,

 
 
2
0
,

 
 
4
6
2
9
,

 
 
7
,

 
 
7
0
,

 
 
5
6
3
4
,

 
 
2
7
,

 
 
2
5
7
9
,

 
 
3
1
,

 
 
4
,

 
 
2
8
,

 
 
7
5
3
,

 
 
8
,

 
 
4
,

 
 
1
5
5
0
,

 
 
3
,

 
 
8
5
,

 
 
2
6
,

 
 
1
0
,

 
 
6
0
2
,

 
 
6
0
6
,

 
 
5
0
4
,

 
 
3
1
,

 
 
3
7
,

 
 
9
3
7
,

 
 
7
,

 
 
1
4
4
0
,

 
 
2
,

 
 
8
2
2
,

 
 
2
1
,

 
 
6
4
0
,

 
 
6
2
,

 
 
3
4
,

 
 
7
0
,

 
 
1
,

 
 
4
7
5
]
,

 
[
2
9
3
,

 
 
1
1
9
,

 
 
3
,

 
 
8
4
7
1
,

 
 
6
9
8
7
0
,

 
 
2
1
0
7
7
,

 
 
4
,

 
 
2
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
8
,

 
 
1
5
,

 
 
8
4
7
1
,

 
 
6
9
8
7
0
,

 
 
2
1
0
7
7
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
7
,

 
 
1
8
2
,

 
 
1
1
6
,

 
 
1
7
1
8
0
,

 
 
3
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
2
0
2
7
,

 
 
2
7
2
,

 
 
5
4
9
5
,

 
 
1
2
,

 
 
9
2
4
,

 
 
6
5
2
,

 
 
5
3
,

 
 
4
3
1
,

 
 
8
8
9
,

 
 
1
5
0
0
,

 
 
2
5
3
,

 
 
2
5
,

 
 
3
4
4
,

 
 
4
5
1
0
,

 
 
3
1
,

 
 
6
1
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
2
5
,

 
 
3
3
6
6
,

 
 
3
4
6
,

 
 
5
,

 
 
1
7
,

 
 
4
,

 
 
5
6
8
5
,

 
 
2
0
,

 
 
8
1
3
,

 
 
4
5
,

 
 
1
3
2
,

 
 
6
7
4
,

 
 
1
6
,

 
 
1
4
6
,

 
 
6
,

 
 
8
7
,

 
 
8
2
,

 
 
7
6
8
,

 
 
1
4
3
9
,

 
 
1
7
,

 
 
4
,

 
 
1
2
0
,

 
 
3
,

 
 
1
0
5
,

 
 
2
6
,

 
 
1
4
,

 
 
1
7
,

 
 
4
,

 
 
1
2
0
,

 
 
3
,

 
 
1
6
4
8
,

 
 
1
3
,

 
 
2
2
3
,

 
 
8
,

 
 
5
9
1
0
,

 
 
1
1
7
,

 
 
1
1
,

 
 
1
0
,

 
 
2
0
,

 
 
1
7
0
,

 
 
4
0
9
,

 
 
2
2
,

 
 
1
,

 
 
7
6
8
,

 
 
4
2
1
,

 
 
1
7
9
8
,

 
 
2
,

 
 
6
,

 
 
5
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
1
0
7
2
,

 
 
2
8
,

 
 
2
,

 
 
8
2
,

 
 
1
,

 
 
2
5
3
,

 
 
2
9
4
,

 
 
5
4
,

 
 
4
2
5
,

 
 
3
2
3
9
,

 
 
6
1
,

 
 
7
5
,

 
 
2
,

 
 
3
9
3
2
,

 
 
1
1
,

 
 
2
9
4
,

 
 
8
4
,

 
 
6
,

 
 
2
4
5
,

 
 
4
4
8
,

 
 
1
5
,

 
 
1
,

 
 
7
6
8
,

 
 
3
4
1
,

 
 
1
,

 
 
4
5
7
,

 
 
7
,

 
 
1
0
9
,

 
 
8
1
,

 
 
1
,

 
 
8
3
1
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
2
3
,

 
 
1
0
9
,

 
 
5
,

 
 
7
,

 
 
9
6
0
,

 
 
1
0
4
,

 
 
1
7
4
,

 
 
1
8
2
,

 
 
1
,

 
 
6
6
7
,

 
 
3
,

 
 
1
,

 
 
4
4
6
3
,

 
 
2
0
0
,

 
 
2
6
9
5
,

 
 
1
1
5
7
,

 
 
4
0
7
,

 
 
1
6
2
,

 
 
1
6
0
,

 
 
5
,

 
 
5
1
9
,

 
 
6
,

 
 
1
8
4
,

 
 
1
0
8
,

 
 
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
5
0
8
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
,

 
 
1
2
,

 
 
5
8
,

 
 
8
7
7
,

 
 
2
5
,

 
 
2
1
9
,

 
 
4
,

 
 
2
1
4
,

 
 
6
4
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
1
3
,

 
 
4
5
4
,

 
 
2
4
,

 
 
6
6
8
,

 
 
6
4
,

 
 
1
0
,

 
 
1
0
0
9
,

 
 
6
,

 
 
8
7
,

 
 
1
1
5
9
,

 
 
1
,

 
 
1
1
9
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
4
9
,

 
 
5
6
7
,

 
 
1
,

 
 
9
8
6
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
5
,

 
 
1
7
7
6
,

 
 
2
7
7
,

 
 
2
5
5
7
,

 
 
2
1
,

 
 
3
1
0
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
8
1
7
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
2
6
,

 
 
1
6
,

 
 
7
4
9
,

 
 
9
,

 
 
4
0
8
,

 
 
9
1
7
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
1
3
5
9
,

 
 
1
,

 
 
1
7
7
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
1
7
7
,

 
 
2
1
9
0
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
7
7
,

 
 
2
2
5
,

 
 
2
6
,

 
 
5
9
,

 
 
1
5
2
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
4
3
,

 
 
4
3
,

 
 
2
8
9
4
,

 
 
1
1
,

 
 
5
8
,

 
 
1
0
,

 
 
3
4
0
7
,

 
 
2
1
,

 
 
5
0
8
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
]
,

 
[
4
5
,

 
 
3
0
,

 
 
6
3
5
2
,

 
 
4
0
3
5
,

 
 
1
6
,

 
 
1
1
2
8
6
,

 
 
7
,

 
 
2
4
0
,

 
 
2
2
6
,

 
 
3
6
,

 
 
7
2
,

 
 
2
7
8
7
,

 
 
3
0
,

 
 
1
7
0
,

 
 
6
0
2
9
,

 
 
3
2
8
2
,

 
 
1
7
9
5
,

 
 
3
7
,

 
 
8
0
,

 
 
7
,

 
 
9
4
,

 
 
1
5
7
,

 
 
6
1
3
3
,

 
 
4
1
5
,

 
 
7
6
0
,

 
 
1
3
7
,

 
 
2
8
2
,

 
 
4
,

 
 
1
2
7
5
,

 
 
4
,

 
 
7
1
9
,

 
 
5
1
9
2
,

 
 
1
9
9
6
,

 
 
1
1
5
0
,

 
 
3
3
8
9
,

 
 
1
1
4
6
,

 
 
1
0
0
4
5
,

 
 
1
3
5
,

 
 
2
7
,

 
 
6
0
8
1
4
,

 
 
1
5
8
7
,

 
 
5
,

 
 
2
7
1
4
,

 
 
1
5
4
,

 
 
9
,

 
 
3
1
6
1
,

 
 
2
8
2
,

 
 
4
,

 
 
2
8
4
,

 
 
3
9
7
2
6
,

 
 
7
1
1
9
,

 
 
5
2
,

 
 
2
8
6
,

 
 
5
3
,

 
 
5
9
,

 
 
9
6
3
7
,

 
 
4
2
3
8
8
,

 
 
2
3
0
1
,

 
 
5
,

 
 
5
1
,

 
 
1
1
7
,

 
 
2
6
,

 
 
9
9
0
,

 
 
1
2
6
,

 
 
9
8
,

 
 
5
,

 
 
3
6
,

 
 
1
,

 
 
4
2
1
0
,

 
 
2
8
6
,

 
 
6
6
5
,

 
 
2
7
8
,

 
 
3
7
,

 
 
6
3
,

 
 
3
8
,

 
 
5
0
5
,

 
 
2
8
2
,

 
 
2
6
,

 
 
2
2
,

 
 
6
,

 
 
2
6
6
,

 
 
7
2
,

 
 
4
0
8
0
,

 
 
6
,

 
 
7
6
,

 
 
3
6
,

 
 
1
,

 
 
7
1
9
,

 
 
8
9
4
,

 
 
1
9
4
8
,

 
 
1
,

 
 
3
3
8
9
,

 
 
2
1
7
2
,

 
 
1
,

 
 
3
9
8
0
,

 
 
1
9
3
5
,

 
 
5
,

 
 
4
7
1
2
,

 
 
6
5
3
,

 
 
4
4
3
5
,

 
 
1
6
0
9
,

 
 
1
,

 
 
1
4
4
8
,

 
 
2
8
9
8
,

 
 
9
6
3
8
,

 
 
1
,

 
 
1
1
5
0
,

 
 
1
0
,

 
 
1
,

 
 
8
1
0
,

 
 
5
,

 
 
1
6
0
9
0
5
,

 
 
6
8
,

 
 
8
9
6
,

 
 
1
0
,

 
 
1
,

 
 
1
9
8
2
,

 
 
3
8
8
,

 
 
7
1
,

 
 
4
,

 
 
2
3
4
3
,

 
 
1
8
0
7
5
,

 
 
8
4
,

 
 
1
5
9
0
3
,

 
 
2
,

 
 
2
3
5
6
,

 
 
1
9
2
,

 
 
5
,

 
 
3
8
3
4
,

 
 
4
0
,

 
 
1
4
8
,

 
 
6
8
,

 
 
2
0
6
7
0
,

 
 
7
5
6
8
,

 
 
4
0
1
1
,

 
 
1
,

 
 
7
3
5
,

 
 
4
4
3
5
,

 
 
1
4
8
9
8
,

 
 
4
5
4
3
,

 
 
2
4
0
,

 
 
1
,

 
 
3
3
8
9
,

 
 
1
7
,

 
 
1
,

 
 
1
1
4
6
,

 
 
3
0
8
8
,

 
 
1
,

 
 
7
3
5
,

 
 
1
0
,

 
 
1
,

 
 
3
4
0
,

 
 
1
2
7
3
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
1
4
5
,

 
 
8
0
,

 
 
1
,

 
 
1
4
4
8
,

 
 
1
1
0
9
,

 
 
1
,

 
 
3
2
1
9
1
,

 
 
2
0
6
3
,

 
 
3
5
4
,

 
 
3
1
,

 
 
1
,

 
 
1
6
4
0
4
,

 
 
8
1
0
,

 
 
5
,

 
 
4
5
5
6
8
,

 
 
1
1
,

 
 
1
3
5
,

 
 
1
,

 
 
5
9
9
9
,

 
 
1
1
1
3
,

 
 
8
4
,

 
 
4
4
3
5
,

 
 
2
4
0
,

 
 
1
7
2
,

 
 
1
1
1
3
,

 
 
2
0
8
,

 
 
7
3
9
4
,

 
 
5
2
7
0
,

 
 
6
8
,

 
 
4
5
4
3
,

 
 
3
2
2
,

 
 
1
,

 
 
2
1
0
9
3
,

 
 
7
9
3
7
,

 
 
3
8
8
,

 
 
1
8
9
,

 
 
1
6
0
9
0
6
,

 
 
4
0
,

 
 
1
4
8
,

 
 
8
8
,

 
 
2
1
0
,

 
 
8
4
,

 
 
1
,

 
 
1
1
4
6
,

 
 
1
5
2
8
6
,

 
 
1
,

 
 
5
9
9
9
,

 
 
7
4
1
,

 
 
1
9
2
,

 
 
1
7
,

 
 
1
9
8
1
,

 
 
4
5
4
3
,

 
 
2
4
0
,

 
 
1
,

 
 
3
3
8
9
,

 
 
1
4
3
0
,

 
 
1
7
2
,

 
 
7
4
1
,

 
 
1
0
,

 
 
1
,

 
 
2
1
0
9
3
,

 
 
1
1
1
3
,

 
 
1
7
,

 
 
1
8
2
9
,

 
 
1
0
6
6
5
5
,

 
 
4
0
,

 
 
1
4
8
,

 
 
1
,

 
 
2
0
2
,

 
 
1
,

 
 
1
4
4
8
,

 
 
1
1
0
9
,

 
 
1
8
2
9
,

 
 
3
1
,

 
 
1
,

 
 
1
9
8
2
,

 
 
1
7
1
6
7
,

 
 
1
1
,

 
 
4
0
,

 
 
1
4
8
,

 
 
1
,

 
 
5
9
9
9
,

 
 
8
5
6
4
,

 
 
3
5
4
0
7
,

 
 
1
4
8
,

 
 
5
,

 
 
4
4
3
5
,

 
 
1
1
8
5
6
,

 
 
4
0
,

 
 
1
4
8
,

 
 
1
,

 
 
7
0
9
,

 
 
9
6
3
9
,

 
 
1
2
5
,

 
 
1
7
2
,

 
 
7
4
1
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
1
5
0
,

 
 
1
,

 
 
1
1
4
6
,

 
 
3
5
9
,

 
 
1
1
,

 
 
1
9
2
,

 
 
5
1
,

 
 
1
5
9
,

 
 
1
,

 
 
1
1
4
6
,

 
 
5
,

 
 
5
8
8
8
,

 
 
1
1
,

 
 
1
0
,

 
 
4
,

 
 
1
8
3
8
8
,

 
 
1
4
0
5
3
,

 
 
1
1
,

 
 
7
3
,

 
 
3
8
8
,

 
 
1
1
,

 
 
2
5
1
6
3
,

 
 
8
4
,

 
 
1
5
9
,

 
 
1
,

 
 
1
1
4
6
,

 
 
1
9
9
8
,

 
 
4
3
3
8
,

 
 
1
1
,

 
 
2
1
,

 
 
1
,

 
 
7
5
6
6
,

 
 
2
2
7
,

 
 
1
,

 
 
1
6
4
0
4
,

 
 
8
1
0
,

 
 
9
6
3
9
,

 
 
5
,

 
 
1
,

 
 
7
5
6
6
,

 
 
3
8
3
4
,

 
 
5
,

 
 
5
8
8
8
,

 
 
1
1
,

 
 
1
3
5
,

 
 
1
,

 
 
2
1
0
9
3
,

 
 
2
0
5
3
,

 
 
8
4
,

 
 
1
,

 
 
1
4
4
8
,

 
 
4
2
3
8
9
,

 
 
1
,

 
 
1
6
4
0
4
,

 
 
5
2
2
,

 
 
1
9
2
,

 
 
5
,

 
 
3
0
8
8
,

 
 
1
,

 
 
3
3
8
9
,

 
 
2
1
,

 
 
1
1
,

 
 
1
7
,

 
 
1
,

 
 
7
3
5
,

 
 
1
6
0
9
0
7
,

 
 
1
,

 
 
1
6
4
0
4
,

 
 
3
5
8
5
,

 
 
4
9
9
7
,

 
 
8
8
,

 
 
7
0
9
,

 
 
5
,

 
 
8
6
8
7
,

 
 
1
,

 
 
7
6
3
6
,

 
 
9
,

 
 
7
9
0
,

 
 
7
6
,

 
 
8
4
,

 
 
1
,

 
 
7
1
9
,

 
 
1
5
4
2
,

 
 
7
3
,

 
 
5
,

 
 
2
8
6
,

 
 
5
3
2
8
,

 
 
1
2
0
5
,

 
 
3
9
5
,

 
 
4
4
6
1
,

 
 
3
1
,

 
 
1
,

 
 
4
2
1
0
,

 
 
3
8
8
,

 
 
5
2
,

 
 
1
0
7
0
,

 
 
2
8
6
,

 
 
7
,

 
 
4
7
7
,

 
 
1
1
,

 
 
3
8
,

 
 
3
4
,

 
 
6
,

 
 
4
5
8
,

 
 
9
,

 
 
5
,

 
 
1
,

 
 
7
1
9
,

 
 
2
8
6
,

 
 
5
3
,

 
 
4
5
8
,

 
 
1
1
,

 
 
1
,

 
 
2
9
7
1
0
]
,

 
[
1
3
3
3
,

 
 
4
6
0
,

 
 
1
5
4
0
,

 
 
6
8
0
,

 
 
1
3
7
1
,

 
 
9
6
6
,

 
 
1
3
4
8
,

 
 
2
3
4
7
,

 
 
5
2
4
,

 
 
3
9
5
,

 
 
7
,

 
 
7
1
3
,

 
 
6
9
2
,

 
 
1
,

 
 
4
2
8
,

 
 
1
3
7
1
,

 
 
9
6
6
,

 
 
5
4
,

 
 
1
3
3
,

 
 
2
,

 
 
2
8
6
1
,

 
 
1
,

 
 
1
5
2
8
7
,

 
 
1
5
4
0
,

 
 
6
8
0
,

 
 
1
3
7
1
,

 
 
9
6
6
,

 
 
2
,

 
 
1
5
4
0
,

 
 
6
8
0
,

 
 
4
2
8
,

 
 
1
3
7
1
,

 
 
9
6
6
,

 
 
5
,

 
 
7
,

 
 
4
1
1
,

 
 
1
3
,

 
 
4
6
0
,

 
 
3
3
6
,

 
 
2
2
,

 
 
2
6
4
4
,

 
 
2
,

 
 
1
6
,

 
 
3
5
4
0
8
,

 
 
3
,

 
 
9
,

 
 
4
6
0
,

 
 
5
0
7
,

 
 
5
0
7
]
,

 
[
7
,

 
 
6
5
,

 
 
1
6
0
9
0
8
,

 
 
9
,

 
 
2
0
,

 
 
1
2
9
3
,

 
 
2
7
3
,

 
 
2
,

 
 
1
0
6
6
5
6
,

 
 
1
9
9
0
,

 
 
1
0
,

 
 
1
,

 
 
1
0
5
0
9
,

 
 
8
,

 
 
1
5
5
,

 
 
2
5
0
,

 
 
5
,

 
 
9
,

 
 
1
6
3
,

 
 
6
7
7
,

 
 
1
,

 
 
1
5
4
2
,

 
 
3
,

 
 
1
6
0
9
0
9
,

 
 
1
6
0
9
1
0
,

 
 
4
3
,

 
 
1
6
,

 
 
2
0
1
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
1
,

 
 
1
0
5
0
9
,

 
 
2
7
3
,

 
 
3
2
3
,

 
 
2
,

 
 
1
6
,

 
 
6
7
3
,

 
 
1
2
7
9
,

 
 
1
0
,

 
 
1
,

 
 
8
9
8
,

 
 
1
7
6
2
,

 
 
1
1
6
,

 
 
6
7
0
,

 
 
1
5
1
,

 
 
1
,

 
 
2
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
4
2
,

 
 
4
,

 
 
2
3
5
,

 
 
6
8
4
,

 
 
1
,

 
 
2
3
,

 
 
1
8
4
,

 
 
7
5
4
,

 
 
3
3
7
0
7
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
6
2
,

 
 
1
4
5
,

 
 
8
,

 
 
3
9
3
,

 
 
1
7
,

 
 
1
1
,

 
 
1
6
6
8
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
3
1
9
,

 
 
1
6
5
5
,

 
 
3
2
,

 
 
4
,

 
 
3
7
2
,

 
 
3
,

 
 
2
8
,

 
 
2
0
5
,

 
 
1
5
1
,

 
 
1
2
8
,

 
 
5
4
3
7
1
,

 
 
5
,

 
 
6
0
8
1
5
,

 
 
3
,

 
 
5
8
7
3
,

 
 
2
6
,

 
 
1
6
0
9
1
1
,

 
 
1
3
,

 
 
1
9
5
6
,

 
 
1
6
0
9
1
2
,

 
 
2
1
,

 
 
1
0
7
2
6
,

 
 
1
0
,

 
 
2
7
,

 
 
2
1
0
6
,

 
 
2
7
1
8
,

 
 
3
,

 
 
6
8
,

 
 
6
1
4
,

 
 
1
7
6
2
,

 
 
3
3
7
0
8
,

 
 
1
3
5
,

 
 
3
7
4
3
4
,

 
 
2
1
0
1
,

 
 
2
,

 
 
6
8
,

 
 
9
1
,

 
 
3
2
1
9
2
,

 
 
8
9
3
9
,

 
 
1
7
,

 
 
4
,

 
 
7
8
2
,

 
 
1
4
4
9
,

 
 
2
6
2
0
,

 
 
1
3
5
,

 
 
1
,

 
 
5
7
5
,

 
 
3
,

 
 
4
3
7
5
,

 
 
5
5
8
3
,

 
 
3
3
,

 
 
4
,

 
 
8
5
,

 
 
3
,

 
 
3
7
7
4
,

 
 
1
2
,

 
 
1
,

 
 
6
4
2
,

 
 
1
3
1
1
,

 
 
1
0
,

 
 
6
6
7
,

 
 
3
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
4
8
4
8
,

 
 
9
1
,

 
 
1
0
9
7
9
,

 
 
5
,

 
 
4
,

 
 
9
2
6
,

 
 
3
,

 
 
2
2
6
2
,

 
 
1
3
,

 
 
8
,

 
 
3
0
9
,

 
 
1
4
,

 
 
5
0
2
4
,

 
 
3
3
,

 
 
4
0
,

 
 
1
0
,

 
 
1
,

 
 
4
5
5
6
9
,

 
 
2
3
,

 
 
7
,

 
 
7
0
5
,

 
 
8
6
8
8
,

 
 
1
1
,

 
 
1
7
,

 
 
2
3
8
2
,

 
 
6
8
,

 
 
1
0
9
8
0
,

 
 
3
0
9
0
,

 
 
2
2
3
,

 
 
3
,

 
 
4
,

 
 
1
4
7
2
3
,

 
 
8
4
2
1
,

 
 
6
9
8
7
1
,

 
 
3
2
,

 
 
1
,

 
 
2
7
3
6
,

 
 
2
9
2
8
,

 
 
6
2
,

 
 
4
1
9
,

 
 
3
3
,

 
 
3
0
8
,

 
 
4
2
0
,

 
 
6
1
,

 
 
2
2
1
9
,

 
 
1
5
0
,

 
 
2
9
7
1
1
,

 
 
4
5
5
6
9
,

 
 
2
6
,

 
 
1
3
,

 
 
2
4
,

 
 
5
4
3
7
,

 
 
1
7
,

 
 
6
1
1
9
,

 
 
3
2
7
,

 
 
3
2
,

 
 
1
8
7
3
7
,

 
 
2
5
5
,

 
 
9
6
,

 
 
2
3
8
,

 
 
3
1
,

 
 
3
0
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
1
1
,

 
 
8
,

 
 
1
1
8
5
,

 
 
1
,

 
 
1
3
2
,

 
 
9
5
9
,

 
 
1
1
3
6
,

 
 
1
0
,

 
 
1
0
6
6
5
6
,

 
 
1
4
3
2
,

 
 
3
7
5
,

 
 
5
3
,

 
 
3
9
,

 
 
2
0
1
5
,

 
 
4
,

 
 
3
1
9
,

 
 
9
,

 
 
2
2
,

 
 
4
,

 
 
2
0
1
,

 
 
2
7
3
,

 
 
3
9
,

 
 
1
6
,

 
 
1
6
0
9
1
3
,

 
 
7
,

 
 
1
5
8
0
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
6
0
9
1
4
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
3
5
7
,

 
 
5
0
2
,

 
 
7
,

 
 
1
0
8
,

 
 
2
,

 
 
4
0
1
8
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
1
2
7
,

 
 
1
4
,

 
 
9
4
1
,

 
 
2
,

 
 
1
6
,

 
 
2
7
,

 
 
1
6
1
1
,

 
 
5
0
4
6
,

 
 
5
2
2
7
,

 
 
2
4
8
,

 
 
4
5
5
6
9
,

 
 
2
6
,

 
 
1
1
3
1
,

 
 
4
5
8
4
,

 
 
7
7
9
,

 
 
2
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
6
8
,

 
 
1
0
9
8
0
,

 
 
2
4
,

 
 
1
,

 
 
2
7
5
3
,

 
 
3
,

 
 
4
0
8
0
,

 
 
1
5
8
,

 
 
1
0
,

 
 
3
3
,

 
 
1
,

 
 
2
5
0
6
,

 
 
4
5
3
,

 
 
5
,

 
 
7
3
4
,

 
 
5
2
,

 
 
4
2
,

 
 
9
9
,

 
 
4
,

 
 
1
0
2
,

 
 
1
1
8
0
,

 
 
8
5
,

 
 
3
,

 
 
1
1
,

 
 
1
4
4
,

 
 
6
8
,

 
 
1
0
9
8
0
,

 
 
2
0
3
,

 
 
1
1
,

 
 
3
9
8
8
,

 
 
1
5
1
8
,

 
 
1
5
,

 
 
1
7
5
6
,

 
 
5
,

 
 
1
,

 
 
2
2
1
1
9
,

 
 
6
9
8
7
1
]
,

 
[
1
0
5
0
,

 
 
4
7
7
,

 
 
7
2
,

 
 
4
9
1
,

 
 
1
2
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
4
9
4
7
4
,

 
 
4
9
9
,

 
 
4
5
5
7
0
,

 
 
3
1
,

 
 
1
3
,

 
 
1
7
6
4
,

 
 
7
2
,

 
 
1
4
3
0
,

 
 
4
,

 
 
1
9
3
,

 
 
6
4
,

 
 
6
9
,

 
 
6
,

 
 
1
6
1
9
,

 
 
1
3
,

 
 
8
6
0
,

 
 
1
2
5
,

 
 
7
,

 
 
1
3
1
,

 
 
4
,

 
 
7
9
7
4
,

 
 
2
,

 
 
3
4
,

 
 
1
7
,

 
 
6
,

 
 
1
0
8
9
7
,

 
 
1
0
,

 
 
1
,

 
 
3
0
9
7
,

 
 
4
5
7
,

 
 
4
1
,

 
 
1
8
,

 
 
1
4
9
,

 
 
2
0
5
,

 
 
6
2
,

 
 
1
9
,

 
 
2
5
0
,

 
 
4
8
8
8
,

 
 
2
,

 
 
3
5
6
,

 
 
2
5
,

 
 
5
4
3
7
2
,

 
 
1
,

 
 
2
3
,

 
 
4
7
,

 
 
3
,

 
 
1
6
5
4
,

 
 
4
2
,

 
 
1
3
3
,

 
 
4
,

 
 
8
0
2
,

 
 
3
,

 
 
1
0
7
,

 
 
5
4
2
,

 
 
4
9
4
7
5
,

 
 
1
5
,

 
 
6
8
,

 
 
4
2
4
,

 
 
1
0
7
,

 
 
2
9
,

 
 
2
6
,

 
 
8
4
2
,

 
 
3
6
,

 
 
3
3
,

 
 
1
1
4
,

 
 
6
1
3
4
,

 
 
1
1
,

 
 
8
7
,

 
 
7
5
4
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
4
1
,

 
 
1
8
,

 
 
5
8
,

 
 
9
3
,

 
 
1
4
9
,

 
 
2
0
5
,

 
 
1
0
,

 
 
1
,

 
 
1
6
0
9
1
5
,

 
 
3
6
8
4
,

 
 
7
,

 
 
2
8
7
2
,

 
 
6
4
,

 
 
3
5
,

 
 
9
2
,

 
 
1
4
3
7
6
,

 
 
6
1
,

 
 
2
0
5
,

 
 
4
7
3
,

 
 
5
,

 
 
7
,

 
 
3
0
9
,

 
 
2
2
9
,

 
 
3
4
,

 
 
1
1
,

 
 
5
5
,

 
 
8
0
6
,

 
 
7
,

 
 
7
0
2
,

 
 
4
8
5
,

 
 
3
0
,

 
 
5
7
5
,

 
 
1
5
,

 
 
1
,

 
 
4
0
0
0
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
2
6
,

 
 
1
3
7
,

 
 
5
7
,

 
 
1
6
7
0
,

 
 
1
5
,

 
 
7
8
3
,

 
 
4
6
,

 
 
1
2
4
,

 
 
5
,

 
 
1
9
9
,

 
 
1
,

 
 
4
8
1
,

 
 
4
5
4
,

 
 
5
5
7
0
,

 
 
3
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
3
0
5
7
,

 
 
2
8
2
0
,

 
 
5
,

 
 
9
6
,

 
 
6
6
9
8
,

 
 
3
2
,

 
 
6
1
3
5
,

 
 
4
0
,

 
 
1
2
,

 
 
2
6
8
,

 
 
2
,

 
 
2
8
6
1
,

 
 
7
6
,

 
 
3
8
,

 
 
1
,

 
 
5
3
9
,

 
 
1
0
7
8
,

 
 
7
2
,

 
 
2
0
7
,

 
 
7
,

 
 
1
2
2
,

 
 
2
,

 
 
2
6
8
2
,

 
 
3
0
,

 
 
8
5
,

 
 
1
5
,

 
 
2
8
,

 
 
3
3
,

 
 
6
9
3
,

 
 
5
,

 
 
5
4
8
,

 
 
1
2
,

 
 
9
,

 
 
8
5
,

 
 
2
,

 
 
1
6
,

 
 
1
9
5
0
,

 
 
2
5
9
6
0
,

 
 
5
,

 
 
1
7
4
6
2
,

 
 
8
0
,

 
 
1
3
7
,

 
 
1
3
1
,

 
 
4
,

 
 
7
9
7
4
,

 
 
2
3
8
,

 
 
1
1
,

 
 
5
4
3
7
3
,

 
 
3
7
,

 
 
1
4
,

 
 
2
,

 
 
2
4
6
,

 
 
1
1
,

 
 
7
2
,

 
 
1
4
,

 
 
9
7
0
,

 
 
6
,

 
 
2
,

 
 
3
4
,

 
 
2
1
5
,

 
 
7
2
,

 
 
4
9
,

 
 
9
5
8
,

 
 
7
8
,

 
 
7
,

 
 
2
2
9
,

 
 
2
4
6
,

 
 
3
0
,

 
 
2
7
0
,

 
 
1
7
,

 
 
3
3
9
,

 
 
3
3
,

 
 
1
,

 
 
8
6
0
,

 
 
1
4
1
8
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
1
7
6
4
,

 
 
5
5
1
,

 
 
4
4
,

 
 
5
5
2
,

 
 
2
7
9
4
,

 
 
1
5
,

 
 
3
0
,

 
 
4
5
3
,

 
 
1
1
,

 
 
8
,

 
 
3
8
1
,

 
 
6
,

 
 
8
3
6
7
2
,

 
 
1
0
,

 
 
9
8
,

 
 
5
8
8
,

 
 
2
,

 
 
7
5
8
,

 
 
1
,

 
 
2
3
,

 
 
7
,

 
 
1
9
,

 
 
2
9
1
,

 
 
9
,

 
 
2
2
9
4
,

 
 
8
0
,

 
 
2
,

 
 
3
4
7
3
,

 
 
5
0
4
,

 
 
8
,

 
 
2
7
,

 
 
3
8
8
0
,

 
 
6
8
3
0
,

 
 
1
4
,

 
 
7
7
,

 
 
6
4
,

 
 
2
6
,

 
 
1
0
,

 
 
1
,

 
 
3
2
5
,

 
 
2
4
4
,

 
 
9
4
3
,

 
 
2
0
,

 
 
2
9
7
3
,

 
 
1
1
7
0
,

 
 
2
0
,

 
 
2
2
1
,

 
 
3
4
3
0
,

 
 
8
,

 
 
5
5
3
7
,

 
 
2
6
4
,

 
 
9
3
,

 
 
8
4
5
,

 
 
5
,

 
 
9
4
3
,

 
 
4
,

 
 
6
7
6
,

 
 
4
9
,

 
 
2
8
5
,

 
 
9
9
6
,

 
 
1
1
,

 
 
1
3
5
4
,

 
 
2
2
1
,

 
 
3
,

 
 
1
4
5
1
,

 
 
1
0
,

 
 
2
0
,

 
 
6
0
2
,

 
 
1
7
1
8
1
,

 
 
6
4
,

 
 
1
0
6
6
5
7
,

 
 
7
2
,

 
 
1
4
,

 
 
9
,

 
 
2
9
0
5
,

 
 
2
6
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
1
,

 
 
1
0
6
6
5
7
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
4
,

 
 
4
,

 
 
1
0
9
0
,

 
 
1
1
,

 
 
9
0
,

 
 
7
2
5
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
5
8
,

 
 
3
9
3
,

 
 
7
9
4
,

 
 
3
6
0
0
,

 
 
3
2
1
3
,

 
 
3
6
,

 
 
1
1
,

 
 
2
4
,

 
 
1
4
9
3
,

 
 
1
,

 
 
1
1
1
9
,

 
 
1
6
3
,

 
 
9
,

 
 
2
4
,

 
 
9
7
2
,

 
 
2
,

 
 
1
6
,

 
 
1
,

 
 
2
9
9
,

 
 
2
4
9
,

 
 
1
,

 
 
4
3
4
,

 
 
3
0
7
0
,

 
 
4
,

 
 
1
6
0
9
1
6
,

 
 
4
0
3
,

 
 
3
,

 
 
1
8
6
9
,

 
 
1
2
5
1
6
,

 
 
1
2
4
,

 
 
1
8
,

 
 
1
4
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
1
9
7
,

 
 
7
,

 
 
4
3
,

 
 
5
5
1
,

 
 
1
4
,

 
 
1
6
1
0
,

 
 
2
,

 
 
1
1
,

 
 
9
1
,

 
 
1
7
2
5
,

 
 
1
7
,

 
 
4
,

 
 
4
3
9
,

 
 
1
7
,

 
 
1
1
,

 
 
2
4
,

 
 
1
2
,

 
 
4
3
0
,

 
 
1
6
0
9
1
7
,

 
 
1
5
0
,

 
 
6
2
3
,

 
 
4
9
4
1
,

 
 
4
6
,

 
 
4
9
,

 
 
4
,

 
 
1
9
0
6
6
,

 
 
4
5
8
,

 
 
1
1
,

 
 
3
0
,

 
 
1
6
9
0
3
,

 
 
2
6
,

 
 
7
2
,

 
 
4
4
6
4
,

 
 
9
,

 
 
6
8
,

 
 
7
1
2
,

 
 
8
,

 
 
4
,

 
 
1
1
5
4
,

 
 
2
5
4
8
,

 
 
2
,

 
 
8
5
1
7
,

 
 
4
1
8
,

 
 
9
,

 
 
6
,

 
 
7
4
2
,

 
 
6
2
4
,

 
 
2
1
3
,

 
 
1
5
4
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
,

 
 
7
1
2
,

 
 
5
4
0
,

 
 
2
6
,

 
 
6
8
,

 
 
1
3
5
8
,

 
 
3
4
9
6
,

 
 
3
0
2
0
,

 
 
3
,

 
 
6
8
,

 
 
6
4
4
,

 
 
1
9
0
6
7
,

 
 
3
0
,

 
 
6
1
,

 
 
1
9
0
6
6
,

 
 
9
1
,

 
 
5
7
2
,

 
 
4
,

 
 
5
0
7
8
,

 
 
2
9
2
,

 
 
9
3
,

 
 
6
8
,

 
 
7
1
2
,

 
 
1
0
0
,

 
 
4
9
,

 
 
3
0
,

 
 
1
6
0
,

 
 
6
4
3
2
,

 
 
6
6
9
,

 
 
2
1
6
0
0
,

 
 
4
1
,

 
 
1
8
,

 
 
1
9
1
5
,

 
 
3
,

 
 
1
5
7
0
,

 
 
6
5
2
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
5
0
7
8
,

 
 
2
9
2
,

 
 
1
,

 
 
7
1
2
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
2
0
2
7
,

 
 
9
2
1
,

 
 
3
,

 
 
1
,

 
 
2
3
0
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
3
8
9
,

 
 
3
,

 
 
8
2
1
7
,

 
 
5
0
9
,

 
 
3
3
,

 
 
1
1
3
,

 
 
4
7
0
2
,

 
 
9
2
0
6
,

 
 
3
,

 
 
2
3
,

 
 
3
0
8
3
9
,

 
 
6
9
9
1
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
3
3
6
,

 
 
9
,

 
 
1
,

 
 
2
3
,

 
 
3
0
8
3
9
,

 
 
6
9
9
1
,

 
 
1
6
,

 
 
7
6
0
3
,

 
 
6
3
,

 
 
1
,

 
 
1
4
6
,

 
 
4
6
,

 
 
3
0
8
3
9
,

 
 
6
9
9
1
,

 
 
1
2
,

 
 
3
0
,

 
 
6
5
2
,

 
 
1
9
3
,

 
 
4
6
,

 
 
3
0
8
3
9
,

 
 
6
9
9
1
,

 
 
2
4
,

 
 
3
5
6
,

 
 
6
9
,

 
 
3
,

 
 
6
6
2
2
,

 
 
1
4
,

 
 
6
0
8
1
6
,

 
 
1
0
1
,

 
 
4
1
,

 
 
2
4
]
,

 
[
6
3
3
1
,

 
 
1
,

 
 
7
0
4
,

 
 
1
9
8
3
3
,

 
 
1
0
4
0
,

 
 
9
8
3
,

 
 
3
1
,

 
 
1
5
2
8
8
,

 
 
5
,

 
 
4
5
0
8
,

 
 
2
7
,

 
 
4
2
8
,

 
 
7
8
1
9
,

 
 
3
2
,

 
 
6
9
8
0
4
,

 
 
5
0
8
1
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
3
1
0
3
,

 
 
1
0
0
4
6
,

 
 
3
3
,

 
 
1
5
2
8
8
,

 
 
1
6
8
8
,

 
 
2
2
7
5
]
,

 
[
4
1
5
,

 
 
4
5
5
,

 
 
4
,

 
 
6
3
9
,

 
 
1
8
5
,

 
 
1
2
5
6
,

 
 
7
,

 
 
8
7
3
,

 
 
2
1
1
,

 
 
9
,

 
 
3
5
5
,

 
 
1
,

 
 
4
5
5
7
1
,

 
 
2
,

 
 
4
5
8
,

 
 
7
6
,

 
 
2
1
0
9
4
,

 
 
1
5
,

 
 
6
8
,

 
 
7
5
5
,

 
 
7
2
0
2
,

 
 
5
6
,

 
 
3
5
6
5
,

 
 
4
,

 
 
2
6
0
,

 
 
3
5
4
1
,

 
 
7
9
3
8
,

 
 
2
6
,

 
 
7
,

 
 
6
3
,

 
 
1
2
5
,

 
 
1
6
4
,

 
 
9
8
3
,

 
 
3
1
,

 
 
2
2
,

 
 
6
,

 
 
2
7
1
3
,

 
 
1
5
,

 
 
1
5
2
4
,

 
 
1
,

 
 
2
1
3
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
5
1
6
3
,

 
 
3
3
6
,

 
 
1
,

 
 
2
1
2
,

 
 
1
2
,

 
 
1
3
,

 
 
2
5
1
6
4
,

 
 
1
0
8
9
,

 
 
2
,

 
 
1
6
,

 
 
4
8
5
,

 
 
2
,

 
 
1
6
6
4
,

 
 
1
,

 
 
3
2
5
,

 
 
2
1
2
,

 
 
3
8
2
,

 
 
3
,

 
 
9
1
,

 
 
1
2
2
8
,

 
 
1
7
,

 
 
4
,

 
 
5
2
3
,

 
 
8
1
1
,

 
 
3
5
2
,

 
 
4
,

 
 
2
1
2
,

 
 
6
7
7
,

 
 
1
,

 
 
1
5
4
2
,

 
 
3
,

 
 
9
1
,

 
 
4
,

 
 
2
5
3
3
,

 
 
1
0
,

 
 
1
,

 
 
3
4
0
,

 
 
4
8
,

 
 
9
,

 
 
4
7
,

 
 
6
1
3
,

 
 
1
5
,

 
 
8
3
6
7
3
,

 
 
4
6
,

 
 
2
9
,

 
 
7
1
6
,

 
 
1
5
,

 
 
9
,

 
 
2
5
7
,

 
 
3
5
2
,

 
 
5
2
,

 
 
5
6
,

 
 
1
6
,

 
 
1
8
8
,

 
 
1
5
5
,

 
 
1
5
1
,

 
 
4
0
,

 
 
5
2
,

 
 
9
0
,

 
 
8
2
,

 
 
4
,

 
 
2
4
4
7
8
,

 
 
2
7
0
,

 
 
5
,

 
 
1
8
5
,

 
 
2
6
0
4
,

 
 
1
5
1
8
,

 
 
9
3
,

 
 
2
1
5
,

 
 
1
3
7
,

 
 
3
4
9
,

 
 
1
6
7
]
,

 
[
4
4
,

 
 
6
,

 
 
1
9
,

 
 
1
,

 
 
1
4
3
,

 
 
2
,

 
 
2
2
3
4
,

 
 
2
7
,

 
 
3
2
7
,

 
 
9
,

 
 
6
,

 
 
4
1
1
,

 
 
1
1
,

 
 
2
,

 
 
1
6
,

 
 
2
4
4
7
9
,

 
 
2
5
,

 
 
8
8
0
,

 
 
2
5
,

 
 
2
1
0
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
1
9
,

 
 
1
,

 
 
1
4
3
,

 
 
2
,

 
 
2
0
6
8
,

 
 
1
1
,

 
 
1
7
,

 
 
2
4
4
7
9
,

 
 
8
8
0
,

 
 
2
5
,

 
 
2
1
0
]
,

 
[
1
1
2
4
,

 
 
3
7
9
,

 
 
1
3
,

 
 
3
7
9
,

 
 
8
,

 
 
5
5
9
7
,

 
 
3
1
,

 
 
4
6
,

 
 
1
3
9
0
,

 
 
3
,

 
 
1
6
0
9
1
8
,

 
 
1
5
2
8
9
,

 
 
5
9
7
7
,

 
 
1
,

 
 
7
9
,

 
 
1
6
9
,

 
 
1
2
,

 
 
1
3
,

 
 
1
1
6
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
1
5
2
,

 
 
2
3
4
,

 
 
2
,

 
 
1
,

 
 
3
7
9
,

 
 
2
9
9
8
,

 
 
8
4
9
,

 
 
2
9
6
,

 
 
2
3
1
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
1
4
8
,

 
 
1
,

 
 
4
9
0
,

 
 
2
6
0
,

 
 
4
9
6
,

 
 
5
,

 
 
8
4
,

 
 
4
2
6
,

 
 
2
,

 
 
9
7
,

 
 
6
0
,

 
 
2
3
4
,

 
 
8
4
9
,

 
 
2
9
6
]
,

 
[
1
2
,

 
 
3
8
9
,

 
 
5
0
,

 
 
9
7
,

 
 
1
8
6
,

 
 
6
,

 
 
9
7
,

 
 
2
2
5
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
1
4
7
6
,

 
 
1
2
,

 
 
1
,

 
 
1
5
8
0
,

 
 
1
5
0
,

 
 
1
2
9
,

 
 
1
,

 
 
3
8
9
,

 
 
2
9
]
,

 
[
8
6
0
,

 
 
5
0
,

 
 
6
3
,

 
 
2
8
,

 
 
8
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
2
5
1
7
,

 
 
4
2
7
,

 
 
1
2
,

 
 
5
0
3
,

 
 
1
8
,

 
 
6
7
3
0
,

 
 
7
0
1
,

 
 
3
3
,

 
 
1
1
3
,

 
 
7
8
7
,

 
 
5
,

 
 
9
5
2
,

 
 
1
2
,

 
 
1
8
1
0
,

 
 
3
3
,

 
 
1
1
3
,

 
 
4
9
4
7
6
,

 
 
1
3
4
,

 
 
6
]
,

 
[
2
3
7
2
,
 
5
9
8
,
 
4
2
6
,
 
1
1
1
9
,
 
1
2
1
2
,
 
1
6
0
9
1
9
,
 
3
2
3
,
 
9
6
5
,
 
2
9
6
,
 
3
2
3
,
 
1
2
3
,
 
2
9
6
,
 
7
7
9
,
 
6
4
5
]
,

 
[
9
1
5
,
 
1
0
,
 
1
2
2
3
,
 
1
2
2
3
,
 
1
4
7
9
,
 
1
9
,
 
3
2
5
,
 
2
4
4
,
 
4
2
9
5
,
 
5
2
0
8
,
 
3
0
9
5
,
 
6
3
8
9
,
 
9
9
1
]
,

 
[
7
1
4
7
,

 
 
6
9
8
7
2
,

 
 
7
5
2
,

 
 
1
2
,

 
 
1
,

 
 
6
1
3
0
,

 
 
1
0
,

 
 
3
7
4
3
5
,

 
 
1
2
2
3
,

 
 
7
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
,

 
 
1
3
5
1
,

 
 
1
,

 
 
1
1
6
2
,

 
 
1
2
,

 
 
3
7
4
3
5
,

 
 
1
2
2
3
,

 
 
2
,

 
 
1
6
6
4
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
7
3
2
3
,

 
 
6
9
8
7
3
,

 
 
2
2
2
,

 
 
3
,

 
 
1
9
3
,

 
 
2
4
,

 
 
4
,

 
 
6
9
8
7
4
,

 
 
7
3
5
8
,

 
 
5
4
,

 
 
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
,

 
 
3
8
3
1
,

 
 
8
8
7
,

 
 
7
3
1
]
,

 
[
1
6
0
9
2
0
,

 
 
4
1
5
,

 
 
1
3
4
,

 
 
6
,

 
 
1
1
7
5
1
,

 
 
1
2
8
,

 
 
7
,

 
 
2
3
9
,

 
 
7
0
,

 
 
7
,

 
 
2
8
9
6
,

 
 
9
,

 
 
2
3
1
,

 
 
1
9
9
,

 
 
3
4
9
,

 
 
3
4
,

 
 
1
1
,

 
 
1
2
7
,

 
 
4
6
3
]
,

 
[
1
2
,

 
 
5
5
3
9
,

 
 
4
8
7
,

 
 
1
0
0
6
,

 
 
6
4
0
,

 
 
7
,

 
 
2
2
0
,

 
 
1
,

 
 
1
8
9
1
,

 
 
9
2
7
,

 
 
2
2
2
5
,

 
 
1
2
,

 
 
1
0
8
1
1
,

 
 
8
,

 
 
4
9
,

 
 
4
,

 
 
2
3
0
4
,

 
 
7
3
]
,

 
[
7
8
,

 
 
1
8
,

 
 
6
,

 
 
1
0
5
1
,

 
 
3
7
,

 
 
1
4
0
7
,

 
 
1
5
0
,

 
 
1
5
8
,

 
 
3
7
2
6
,

 
 
1
3
,

 
 
1
7
,

 
 
2
1
7
,

 
 
7
,

 
 
1
0
8
,

 
 
6
,

 
 
2
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
5
6
,

 
 
1
3
,

 
 
7
8
,

 
 
8
,

 
 
1
3
,

 
 
2
1
7
,

 
 
7
,

 
 
5
9
,

 
 
2
7
5
,

 
 
7
,

 
 
8
1
,

 
 
1
1
5
,

 
 
2
,

 
 
2
8
,

 
 
5
,

 
 
7
,

 
 
8
1
,

 
 
2
6
8
,

 
 
2
,

 
 
1
0
4
0
,

 
 
1
1
,

 
 
7
6
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
1
3
0
0
,

 
 
1
3
,

 
 
1
7
,

 
 
2
1
7
,

 
 
7
2
,

 
 
8
1
,

 
 
1
4
,

 
 
2
9
8
,

 
 
2
1
5
,

 
 
2
4
7
,

 
 
7
,

 
 
4
9
,

 
 
1
2
2
,

 
 
2
3
3
8
,

 
 
3
1
,

 
 
1
2
6
1
,

 
 
5
0
,

 
 
1
2
1
]
,

 
[
7
2
9
6
,

 
 
5
8
1
2
,

 
 
1
2
,

 
 
1
4
1
6
9
,

 
 
3
5
7
,

 
 
1
7
,

 
 
3
,

 
 
1
1
1
2
,

 
 
1
3
9
9
,

 
 
7
1
0
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
4
1
,

 
 
2
,

 
 
8
2
,

 
 
7
2
9
6
,

 
 
5
8
1
2
,

 
 
2
,

 
 
7
2
9
7
,

 
 
4
2
3
9
0
,

 
 
9
6
,

 
 
2
3
8
,

 
 
1
,

 
 
7
2
9
6
,

 
 
3
0
4
2
,

 
 
4
8
1
6
,

 
 
5
3
8
,

 
 
2
9
6
,

 
 
3
6
8
5
,

 
 
2
4
3
,

 
 
7
2
9
6
,

 
 
5
8
1
2
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
2
4
4
2
,

 
 
3
6
8
5
,

 
 
1
0
5
7
8
,

 
 
5
,

 
 
1
0
6
6
5
8
,

 
 
1
4
1
6
9
,

 
 
3
7
3
1
,

 
 
1
2
8
3
,

 
 
1
3
,

 
 
8
,

 
 
4
,

 
 
6
7
9
,

 
 
4
5
7
,

 
 
1
7
,

 
 
8
6
,

 
 
5
5
9
,

 
 
2
,

 
 
1
7
9
5
,

 
 
1
2
,

 
 
4
3
0
8
,

 
 
2
1
,

 
 
4
,

 
 
7
2
9
6
,

 
 
3
0
4
2
,

 
 
3
3
,

 
 
9
,

 
 
8
5
,

 
 
4
7
,

 
 
2
2
2
,

 
 
2
3
7
,

 
 
1
8
7
,

 
 
9
,

 
 
4
8
8
,

 
 
2
6
,

 
 
1
1
,

 
 
2
4
,

 
 
3
6
8
,

 
 
8
,

 
 
4
1
,

 
 
4
,

 
 
9
8
,

 
 
1
1
0
,

 
 
2
,

 
 
1
1
8
,

 
 
3
5
,

 
 
1
7
8
3
,

 
 
3
8
3
3
]
,

 
[
7
2
,

 
 
9
5
0
,

 
 
3
5
,

 
 
7
1
8
,

 
 
3
2
6
,

 
 
1
5
,

 
 
4
7
3
0
,

 
 
2
5
5
2
,

 
 
1
4
8
9
9
,

 
 
1
2
0
9
,

 
 
1
1
4
8
0
,

 
 
3
,

 
 
2
0
6
9
,

 
 
5
,

 
 
2
5
5
2
,

 
 
1
4
8
9
9
,

 
 
1
2
0
9
,

 
 
3
0
8
4
0
,

 
 
6
9
,

 
 
5
1
,

 
 
1
8
,

 
 
2
8
7
8
,

 
 
3
6
7
,

 
 
4
8
,

 
 
1
2
,

 
 
7
5
,

 
 
9
0
9
,

 
 
1
5
,

 
 
1
1
]
,

 
[
4
4
,

 
 
7
1
,

 
 
1
4
,

 
 
6
1
1
,

 
 
1
0
5
,

 
 
3
5
,

 
 
1
,

 
 
4
4
7
,

 
 
5
,

 
 
7
1
,

 
 
4
,

 
 
9
8
,

 
 
4
0
5
,

 
 
7
7
,

 
 
1
6
2
,

 
 
5
8
5
4
,

 
 
8
,

 
 
8
1
9
,

 
 
4
9
7
,

 
 
5
6
6
,

 
 
3
3
,

 
 
1
3
2
,

 
 
1
6
0
,

 
 
2
2
,

 
 
5
1
,

 
 
1
2
6
,

 
 
1
2
1
8
8
,

 
 
1
6
3
]
,

 
[
3
0
,

 
 
4
8
0
4
,

 
 
5
8
5
,

 
 
7
3
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
2
6
,

 
 
4
0
8
,

 
 
7
,

 
 
2
2
7
6
,

 
 
2
8
,

 
 
7
,

 
 
2
3
9
,

 
 
3
4
5
,

 
 
2
1
5
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
4
7
0
,

 
 
2
,

 
 
3
0
,

 
 
2
4
2
,

 
 
4
8
0
4
,

 
 
9
,

 
 
2
4
,

 
 
4
8
,

 
 
1
,

 
 
2
2
4
5
,

 
 
3
0
3
,

 
 
6
5
7
,

 
 
1
4
9
,

 
 
8
9
2
,

 
 
6
3
3
,

 
 
4
0
,

 
 
3
,

 
 
3
0
,

 
 
2
9
5
,

 
 
1
8
,

 
 
1
2
1
5
,

 
 
3
9
5
,

 
 
2
4
1
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
3
5
,

 
 
3
0
,

 
 
6
4
9
,

 
 
3
7
5
8
,

 
 
2
5
,

 
 
3
0
,

 
 
9
1
,

 
 
2
0
4
,

 
 
1
0
,

 
 
5
5
4
0
,

 
 
1
2
,

 
 
3
9
7
1
,

 
 
1
0
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
9
2
6
2
,

 
 
7
,

 
 
2
3
9
,

 
 
2
0
4
,

 
 
3
0
,

 
 
4
8
0
4
,

 
 
1
0
,

 
 
1
,

 
 
2
2
2
9
,

 
 
3
9
7
2
,

 
 
2
1
0
9
5
,

 
 
2
3
,

 
 
3
0
4
,

 
 
5
0
0
,

 
 
5
2
,

 
 
2
4
,

 
 
3
0
,

 
 
2
2
2
9
,

 
 
7
,

 
 
7
7
1
,

 
 
7
6
,

 
 
3
,

 
 
3
0
,

 
 
1
1
0
,

 
 
2
,

 
 
6
3
8
,

 
 
1
2
,

 
 
2
9
5
,

 
 
5
0
7
9
,

 
 
4
0
,

 
 
1
,

 
 
7
8
3
,

 
 
1
9
5
9
,

 
 
3
,

 
 
1
,

 
 
2
6
7
,

 
 
1
2
,

 
 
1
3
8
6
,

 
 
7
,

 
 
5
4
1
,

 
 
2
,

 
 
1
,

 
 
1
8
0
7
6
,

 
 
5
,

 
 
6
3
6
,

 
 
1
2
,

 
 
9
2
,

 
 
1
5
5
1
,

 
 
5
,

 
 
1
0
,

 
 
1
6
6
,

 
 
6
3
6
,

 
 
8
8
,

 
 
2
,

 
 
1
4
2
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
7
,

 
 
6
6
,

 
 
6
7
0
,

 
 
3
5
,

 
 
4
6
4
,

 
 
6
2
6
,

 
 
2
1
,

 
 
2
0
2
2
,

 
 
5
,

 
 
5
6
7
1
,

 
 
2
1
,

 
 
1
0
0
3
,

 
 
2
1
6
0
1
,

 
 
1
5
0
1
,

 
 
2
9
5
,

 
 
3
1
,

 
 
4
,

 
 
5
8
8
6
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
1
4
1
,

 
 
2
9
5
,

 
 
8
6
,

 
 
1
4
6
,

 
 
3
2
,

 
 
1
5
8
,

 
 
7
,

 
 
2
2
9
,

 
 
5
8
4
,

 
 
6
2
,

 
 
5
,

 
 
5
9
,

 
 
7
0
,

 
 
7
8
,

 
 
3
3
,

 
 
1
3
,

 
 
1
4
5
,

 
 
1
,

 
 
7
7
,

 
 
2
7
3
,

 
 
9
,

 
 
7
,

 
 
6
7
0
,

 
 
9
,

 
 
8
,

 
 
6
2
3
1
,

 
 
3
3
,

 
 
4
0
,

 
 
8
,

 
 
4
,

 
 
1
3
3
5
,

 
 
2
9
0
7
,

 
 
4
,

 
 
9
4
1
6
,

 
 
2
9
0
7
,

 
 
4
,

 
 
1
1
6
0
,

 
 
2
0
7
2
,

 
 
2
2
2
9
,

 
 
5
,

 
 
7
,

 
 
7
0
,

 
 
1
2
,

 
 
1
8
6
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
8
7
0
,

 
 
9
4
1
6
,

 
 
1
,

 
 
6
1
3
,

 
 
6
2
,

 
 
3
3
4
2
,

 
 
1
,

 
 
1
3
3
5
,

 
 
8
,

 
 
4
,

 
 
2
6
5
3
,

 
 
4
1
2
,

 
 
6
4
9
,

 
 
1
9
6
6
,

 
 
5
,

 
 
4
2
,

 
 
4
,

 
 
1
0
1
3
,

 
 
3
6
1
3
,

 
 
8
6
5
,

 
 
2
3
9
9
,

 
 
4
0
5
0
,

 
 
2
,

 
 
5
8
8
6
,

 
 
9
6
,

 
 
1
,

 
 
5
3
6
,

 
 
9
,

 
 
2
4
,

 
 
1
4
6
,

 
 
3
5
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
5
5
1
3
,

 
 
7
,

 
 
9
9
,

 
 
2
9
5
,

 
 
1
2
,

 
 
7
,

 
 
1
5
6
,

 
 
1
0
,

 
 
1
,

 
 
2
8
,

 
 
1
3
8
,

 
 
3
,

 
 
1
0
6
,

 
 
9
,

 
 
2
7
6
8
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
0
,

 
 
6
0
,

 
 
7
2
6
4
,

 
 
7
,

 
 
5
9
,

 
 
2
2
0
,

 
 
9
,

 
 
7
,

 
 
9
0
,

 
 
5
5
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
4
0
,

 
 
7
,

 
 
9
0
,

 
 
8
,

 
 
6
3
8
,

 
 
1
,

 
 
7
8
6
,

 
 
1
2
,

 
 
2
9
5
,

 
 
1
2
,

 
 
1
,

 
 
2
3
,

 
 
7
,

 
 
1
2
6
,

 
 
2
3
9
,

 
 
7
0
,

 
 
3
5
,

 
 
1
6
0
9
2
1
,

 
 
6
2
0
3
,

 
 
2
3
9
9
,

 
 
2
5
,

 
 
1
,

 
 
1
2
7
2
,

 
 
3
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
9
2
6
2
,

 
 
1
5
0
,

 
 
7
,

 
 
5
1
3
,

 
 
6
3
0
,

 
 
1
5
,

 
 
1
3
,

 
 
2
3
,

 
 
7
,

 
 
9
9
,

 
 
2
3
7
,

 
 
5
7
,

 
 
9
5
0
,

 
 
3
5
,

 
 
2
2
9
1
,

 
 
4
0
1
,

 
 
7
4
4
8
,

 
 
2
6
,

 
 
7
,

 
 
5
1
3
,

 
 
9
5
0
,

 
 
3
5
,

 
 
9
,

 
 
4
9
5
,

 
 
6
9
,

 
 
3
,

 
 
3
0
,

 
 
4
8
0
4
,

 
 
2
1
,

 
 
6
9
8
7
5
,

 
 
5
4
,

 
 
4
3
5
,

 
 
1
5
7
,

 
 
2
,

 
 
1
0
0
1
,

 
 
6
6
,

 
 
8
0
,

 
 
7
,

 
 
2
4
,

 
 
4
6
7
0
,

 
 
7
,

 
 
8
6
1
,

 
 
1
7
,

 
 
4
,

 
 
1
9
5
1
,

 
 
1
7
1
8
2
,

 
 
7
,

 
 
9
0
,

 
 
9
4
,

 
 
1
,

 
 
4
8
7
,

 
 
1
5
,

 
 
1
,

 
 
2
0
1
9
,

 
 
5
,

 
 
1
0
2
9
9
,

 
 
3
,

 
 
4
2
0
2
,

 
 
2
7
4
,

 
 
6
3
3
,

 
 
2
6
,

 
 
2
8
,

 
 
2
3
7
,

 
 
9
9
,

 
 
2
7
,

 
 
2
3
,

 
 
1
5
,

 
 
9
,

 
 
5
,

 
 
1
1
,

 
 
2
8
8
,

 
 
4
3
,

 
 
1
9
,

 
 
2
6
9
,

 
 
7
3
,

 
 
4
9
5
,

 
 
1
3
9
,

 
 
1
7
,

 
 
1
,

 
 
1
6
8
,

 
 
7
8
7
,

 
 
1
6
0
9
2
2
,

 
 
1
2
6
,

 
 
2
4
8
9
,

 
 
9
,

 
 
7
,

 
 
2
3
9
,

 
 
1
5
2
,

 
 
4
,

 
 
5
,

 
 
5
0
7
,

 
 
8
4
0
,

 
 
2
,

 
 
9
8
4
,

 
 
4
,

 
 
1
4
5
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
4
,

 
 
1
5
6
9
3
,

 
 
4
8
,

 
 
6
2
3
,

 
 
7
,

 
 
2
4
,

 
 
2
6
8
4
,

 
 
2
6
7
6
8
,

 
 
4
6
5
0
,

 
 
5
,

 
 
1
1
,

 
 
1
6
6
8
,

 
 
9
,

 
 
1
,

 
 
5
1
2
1
,

 
 
6
8
5
4
,

 
 
9
9
,

 
 
4
,

 
 
5
8
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
2
2
1
1
,

 
 
1
5
1
1
,

 
 
5
4
,

 
 
7
,

 
 
6
5
,

 
 
8
,

 
 
6
9
,

 
 
3
,

 
 
2
2
2
9
,

 
 
2
2
7
3
,

 
 
7
4
1
,

 
 
6
2
,

 
 
2
4
,

 
 
1
0
,

 
 
1
,

 
 
5
1
8
1
,

 
 
6
8
5
4
,

 
 
5
,

 
 
1
,

 
 
7
7
,

 
 
2
1
2
,

 
 
7
,

 
 
7
0
,

 
 
3
5
,

 
 
9
,

 
 
8
,

 
 
9
,

 
 
4
7
,

 
 
8
5
,

 
 
7
,

 
 
7
7
1
,

 
 
1
0
,

 
 
3
0
6
,

 
 
2
0
7
2
,

 
 
6
8
5
4
,

 
 
5
,

 
 
5
4
1
4
,

 
 
1
5
,

 
 
1
,

 
 
4
0
9
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
1
0
,

 
 
1
,

 
 
2
7
7
0
7
,

 
 
6
9
,

 
 
7
,

 
 
2
4
,

 
 
2
6
8
,

 
 
2
,

 
 
6
3
,

 
 
2
2
,

 
 
4
1
,

 
 
2
4
,

 
 
4
,

 
 
1
7
9
,

 
 
3
,

 
 
1
0
2
5
,

 
 
1
0
0
3
,

 
 
2
1
6
0
1
,

 
 
1
0
,

 
 
5
5
4
0
,

 
 
1
2
,

 
 
9
1
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
4
4
,

 
 
4
1
,

 
 
2
4
,

 
 
1
4
,

 
 
3
8
,

 
 
7
,

 
 
2
9
1
,

 
 
1
0
,

 
 
1
,

 
 
2
7
7
0
7
,

 
 
2
4
,

 
 
9
,

 
 
6
0
,

 
 
1
3
7
5
9
,

 
 
3
5
6
3
,

 
 
4
0
,

 
 
1
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
7
5
3
4
,

 
 
1
7
7
,

 
 
9
6
,

 
 
3
5
8
,

 
 
7
8
,

 
 
2
6
,

 
 
2
2
2
9
,

 
 
2
2
7
3
,

 
 
7
4
1
,

 
 
1
6
6
8
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
2
2
1
1
,

 
 
7
,

 
 
2
2
0
,

 
 
9
,

 
 
2
0
,

 
 
1
1
6
2
,

 
 
2
1
8
,

 
 
3
5
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
3
5
4
0
9
,

 
 
4
0
4
,

 
 
2
7
,

 
 
3
0
5
4
,

 
 
4
3
7
0
,

 
 
8
,

 
 
5
8
3
1
,

 
 
7
5
6
5
,

 
 
7
,

 
 
3
4
,

 
 
2
7
5
,

 
 
2
0
,

 
 
3
0
7
4
,

 
 
2
,

 
 
1
7
8
6
,

 
 
6
6
5
2
,

 
 
4
0
9
5
,

 
 
2
3
8
,

 
 
5
,

 
 
3
5
,

 
 
6
4
9
,

 
 
1
7
,

 
 
4
,

 
 
1
0
1
3
,

 
 
1
3
7
,

 
 
5
7
,

 
 
2
7
,

 
 
2
3
8
3
6
,

 
 
7
,

 
 
2
3
9
,

 
 
7
0
,

 
 
3
5
,

 
 
1
,

 
 
2
0
7
2
,

 
 
7
6
4
0
,

 
 
1
0
9
6
,

 
 
3
8
8
,

 
 
7
,

 
 
5
1
3
,

 
 
6
3
0
,

 
 
1
5
,

 
 
1
3
,

 
 
2
3
,

 
 
9
,

 
 
3
3
7
,

 
 
1
5
,

 
 
2
6
7
6
8
,

 
 
2
9
8
5
,

 
 
7
,

 
 
2
9
1
,

 
 
4
9
1
,

 
 
1
2
,

 
 
2
9
5
,

 
 
1
2
,

 
 
1
3
,

 
 
2
3
,

 
 
1
,

 
 
8
7
2
,

 
 
1
5
,

 
 
2
0
9
4
,

 
 
9
2
6
2
,

 
 
7
,

 
 
2
9
1
,

 
 
4
9
1
,

 
 
1
2
,

 
 
2
9
5
,

 
 
1
2
,

 
 
1
3
,

 
 
2
3
,

 
 
2
0
3
3
,

 
 
2
1
,

 
 
6
,

 
 
1
8
0
7
,

 
 
3
7
,

 
 
2
,

 
 
1
8
4
3
,

 
 
1
,

 
 
4
6
4
,

 
 
1
2
,

 
 
4
9
9
,

 
 
4
7
,

 
 
2
2
8
,

 
 
7
,

 
 
5
1
3
,

 
 
9
5
0
,

 
 
3
5
,

 
 
4
,

 
 
3
4
8
,

 
 
1
0
,

 
 
1
,

 
 
6
2
9
,

 
 
2
6
0
,

 
 
1
3
2
4
,

 
 
8
,

 
 
4
0
3
6
,

 
 
5
,

 
 
7
4
,

 
 
9
,

 
 
4
0
7
5
,

 
 
1
,

 
 
1
7
9
,

 
 
3
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
9
2
6
2
,

 
 
7
,

 
 
4
4
8
9
,

 
 
1
,

 
 
3
3
7
,

 
 
3
9
7
0
,

 
 
1
6
8
3
,

 
 
3
3
,

 
 
1
,

 
 
1
8
4
1
,

 
 
2
6
,

 
 
7
,

 
 
7
0
2
,

 
 
2
8
2
,

 
 
1
1
,

 
 
3
5
1
,

 
 
2
6
,

 
 
8
9
,

 
 
8
0
,

 
 
7
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
0
0
3
,

 
 
1
7
7
3
,

 
 
6
4
9
,

 
 
1
0
,

 
 
1
,

 
 
2
7
1
,

 
 
3
8
6
,

 
 
7
,

 
 
6
5
,

 
 
2
0
0
,

 
 
2
9
7
,

 
 
3
9
7
0
,

 
 
2
9
7
,

 
 
6
8
2
,

 
 
2
9
7
,

 
 
6
6
,

 
 
4
1
,

 
 
8
6
,

 
 
4
6
4
,

 
 
4
7
0
,

 
 
2
,

 
 
4
2
3
1
,

 
 
1
0
,

 
 
6
0
,

 
 
3
,

 
 
1
,

 
 
1
3
4
9
,

 
 
3
8
6
,

 
 
1
,

 
 
4
7
6
9
,

 
 
1
7
1
8
,

 
 
1
2
5
8
,

 
 
9
9
,

 
 
4
,

 
 
3
4
8
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
1
1
,

 
 
1
5
5
,

 
 
7
,

 
 
6
5
,

 
 
3
6
,

 
 
9
0
,

 
 
1
,

 
 
1
7
9
,

 
 
3
,

 
 
8
3
6
7
4
,

 
 
1
5
1
0
0
,

 
 
5
4
,

 
 
8
,

 
 
3
,

 
 
4
4
3
,

 
 
4
7
0
,

 
 
2
,

 
 
1
0
1
0
4
]
,

 
[
2
8
9
,

 
 
3
2
0
5
,

 
 
5
4
3
7
4
,

 
 
1
,

 
 
6
8
2
,

 
 
3
1
,

 
 
1
4
1
5
,

 
 
2
,

 
 
3
2
5
3
,

 
 
8
8
8
,

 
 
4
5
3
,

 
 
1
0
,

 
 
3
5
1
8
,

 
 
1
5
5
,

 
 
2
6
,

 
 
8
3
6
7
5
,

 
 
4
4
,

 
 
5
1
9
3
,

 
 
4
1
]
,

 
[
1
2
5
9
,

 
 
2
4
2
,

 
 
2
4
4
3
,

 
 
4
,

 
 
1
1
5
,

 
 
3
8
7
,

 
 
4
2
,

 
 
3
5
7
,

 
 
1
7
3
,

 
 
1
3
,

 
 
1
1
,

 
 
5
2
6
,

 
 
4
8
,

 
 
1
2
5
9
,

 
 
2
4
2
,

 
 
2
4
4
3
]
,

 
[
2
0
,

 
 
2
0
6
,

 
 
8
,

 
 
1
5
6
9
4
,

 
 
1
7
,

 
 
2
2
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
6
3
9
,

 
 
2
,

 
 
1
1
6
8
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
,

 
 
4
7
,

 
 
6
2
,

 
 
1
8
7
,

 
 
1
,

 
 
1
3
8
]
,

 
[
8
0
,

 
 
7
,

 
 
1
0
3
2
,

 
 
3
3
,

 
 
1
,

 
 
2
4
4
8
0
,

 
 
7
9
,

 
 
1
1
,

 
 
2
4
,

 
 
3
0
9
,

 
 
4
,

 
 
1
1
2
9
,

 
 
3
,

 
 
1
,

 
 
2
7
3
,

 
 
1
,

 
 
8
1
3
,

 
 
3
,

 
 
1
8
3
,

 
 
1
7
4
6
3
,

 
 
5
,

 
 
4
,

 
 
2
3
6
,

 
 
1
0
,

 
 
1
,

 
 
3
6
1
,

 
 
1
7
7
,

 
 
2
7
,

 
 
7
9
,

 
 
5
1
5
,

 
 
2
,

 
 
5
2
0
,

 
 
1
,

 
 
4
2
2
,

 
 
8
6
,

 
 
6
4
9
8
,

 
 
2
0
,

 
 
2
5
6
9
,

 
 
5
5
1
,

 
 
1
8
0
7
,

 
 
9
5
,

 
 
6
6
,

 
 
1
2
,

 
 
3
1
0
,

 
 
1
,

 
 
2
7
3
,

 
 
1
5
,

 
 
2
4
4
8
1
,

 
 
2
1
5
0
,

 
 
7
,

 
 
9
0
,

 
 
1
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
0
6
,

 
 
1
8
7
,

 
 
2
5
,

 
 
1
7
3
,

 
 
3
0
,

 
 
4
3
2
,

 
 
1
3
6
3
,

 
 
2
4
,

 
 
1
,

 
 
9
2
0
7
,

 
 
1
4
0
,

 
 
1
8
1
8
,

 
 
1
8
,

 
 
3
9
3
,

 
 
5
,

 
 
8
4
,

 
 
7
,

 
 
6
8
7
,

 
 
9
,

 
 
1
,

 
 
9
8
9
,

 
 
3
5
,

 
 
1
1
2
,

 
 
1
3
9
,

 
 
1
1
0
0
,

 
 
3
1
,

 
 
4
,

 
 
2
0
8
,

 
 
1
5
7
,

 
 
3
6
,

 
 
3
0
,

 
 
3
7
7
,

 
 
8
,

 
 
5
8
,

 
 
3
,

 
 
4
,

 
 
5
4
5
4
,

 
 
1
3
2
,

 
 
3
9
8
1
,

 
 
6
,

 
 
1
8
,

 
 
9
7
4
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
2
4
8
,

 
 
1
,

 
 
4
7
5
,

 
 
2
,

 
 
1
5
2
,

 
 
1
2
5
9
,

 
 
3
4
6
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
2
5
4
3
,

 
 
1
7
4
,

 
 
5
7
0
,

 
 
8
,

 
 
1
1
3
,

 
 
8
5
2
,

 
 
5
,

 
 
1
1
3
,

 
 
1
3
8
2
,

 
 
2
5
8
0
,

 
 
1
9
1
,

 
 
2
,

 
 
2
8
6
1
,

 
 
7
6
,

 
 
9
,

 
 
2
3
0
,

 
 
4
8
2
,

 
 
1
2
9
,

 
 
5
2
4
]
,

 
[
5
3
,

 
 
4
0
,

 
 
7
0
,

 
 
9
,

 
 
4
9
,

 
 
3
5
,

 
 
5
4
5
,

 
 
6
4
,

 
 
1
2
5
1
8
,

 
 
1
,

 
 
4
2
4
6
,

 
 
5
2
8
5
,

 
 
4
,

 
 
2
1
2
,

 
 
5
1
,

 
 
7
6
7
,

 
 
4
4
0
,

 
 
1
4
5
4
9
,

 
 
3
3
8
2
]
,

 
[
1
3
7
,

 
 
5
7
,

 
 
2
3
8
,

 
 
1
,

 
 
2
3
,

 
 
7
1
,

 
 
3
0
9
,

 
 
3
8
7
1
,

 
 
9
,

 
 
7
7
,

 
 
1
0
5
2
,

 
 
1
8
,

 
 
3
9
8
7
,

 
 
1
4
5
8
,

 
 
2
,

 
 
4
,

 
 
7
2
1
,

 
 
2
6
,

 
 
1
6
0
9
2
3
,

 
 
5
,

 
 
1
0
1
4
,

 
 
1
8
,

 
 
1
4
,

 
 
1
3
0
,

 
 
6
4
7
4
,

 
 
9
0
2
,

 
 
7
0
1
,

 
 
2
,

 
 
7
2
1
,

 
 
3
8
3
,

 
 
7
9
1
,

 
 
1
0
5
2
,

 
 
1
5
8
6
,

 
 
5
,

 
 
1
0
1
4
,

 
 
7
7
,

 
 
4
7
,

 
 
4
6
5
,

 
 
1
1
3
8
8
,

 
 
2
,

 
 
2
0
,

 
 
8
9
5
,

 
 
1
,

 
 
1
4
1
7
8
,

 
 
3
,

 
 
1
,

 
 
1
0
9
3
,

 
 
1
9
7
,

 
 
4
3
8
2
,

 
 
1
0
,

 
 
8
5
3
,

 
 
7
2
1
,

 
 
1
1
8
3
,

 
 
8
4
1
,

 
 
9
9
2
,

 
 
5
,

 
 
6
1
6
,

 
 
8
4
1
,

 
 
1
0
1
4
,

 
 
3
,

 
 
5
4
,

 
 
8
5
3
,

 
 
7
2
1
,

 
 
5
,

 
 
9
1
9
,

 
 
8
4
1
,

 
 
9
9
2
,

 
 
8
6
,

 
 
1
7
1
7
,

 
 
1
0
,

 
 
1
0
8
1
,

 
 
2
5
5
2
,

 
 
2
1
,

 
 
1
,

 
 
2
4
0
2
,

 
 
1
1
8
8
,

 
 
1
3
,

 
 
6
4
6
,

 
 
4
6
5
,

 
 
5
6
,

 
 
1
6
,

 
 
2
6
9
1
,

 
 
2
3
1
,

 
 
4
9
,

 
 
3
4
,

 
 
1
1
,

 
 
2
6
,

 
 
1
,

 
 
4
6
5
,

 
 
5
4
0
,

 
 
8
,

 
 
8
2
6
0
,

 
 
1
7
6
1
,

 
 
3
6
,

 
 
2
1
3
9
,

 
 
5
4
1
,

 
 
1
1
,

 
 
8
7
,

 
 
5
4
8
,

 
 
2
,

 
 
3
2
8
,

 
 
9
,

 
 
7
,

 
 
2
2
7
6
,

 
 
1
1
,

 
 
1
7
3
8
]
,

 
[
3
2
0
,
 
2
5
0
,
 
8
5
,
 
4
4
,
 
1
0
6
6
5
9
]
,

 
[
6
1
,

 
 
1
3
7
9
,

 
 
8
3
,

 
 
1
4
,

 
 
1
2
8
5
,

 
 
1
0
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
9
2
5
,

 
 
3
,

 
 
1
,

 
 
4
5
1
,

 
 
8
3
,

 
 
8
,

 
 
4
4
5
,

 
 
1
0
,

 
 
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
5
,

 
 
3
7
5
,

 
 
5
6
,

 
 
1
6
,

 
 
1
1
0
5
5
,

 
 
2
0
6
3
,

 
 
7
4
,

 
 
6
4
0
8
,

 
 
1
3
4
6
7
,

 
 
1
3
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
1
8
9
,

 
 
4
5
8
6
,

 
 
2
3
0
,

 
 
3
,

 
 
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
9
1
5
,

 
 
8
9
8
,

 
 
3
0
0
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
3
6
3
,

 
 
2
3
0
,

 
 
3
,

 
 
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
9
1
5
,

 
 
8
1
4
1
,

 
 
1
7
9
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
2
3
9
1
,

 
 
2
7
7
0
8
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
8
4
8
,

 
 
2
3
0
,

 
 
3
,

 
 
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
9
1
5
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
5
,

 
 
1
,

 
 
2
6
5
2
,

 
 
3
2
6
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
7
,

 
 
4
5
0
1
,

 
 
3
,

 
 
2
9
4
6
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
8
4
2
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
1
8
9
,

 
 
1
5
4
6
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
1
8
9
,

 
 
1
5
4
6
,

 
 
2
1
0
4
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
4
1
8
9
,

 
 
1
8
4
1
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
3
9
7
2
7
,

 
 
1
7
8
9
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
3
9
6
8
,

 
 
1
0
9
5
,

 
 
1
2
5
5
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
3
3
1
6
,

 
 
1
1
5
2
,

 
 
2
2
1
9
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
1
0
5
5
,

 
 
1
1
4
,

 
 
3
5
3
,

 
 
1
7
,

 
 
1
2
6
6
,

 
 
3
,

 
 
1
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
1
0
5
5
,

 
 
4
3
7
,

 
 
3
5
3
,

 
 
1
7
,

 
 
1
2
6
6
,

 
 
3
,

 
 
1
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
1
6
1
,

 
 
3
,

 
 
5
9
0
,

 
 
5
,

 
 
1
8
7
6
,

 
 
3
5
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
6
1
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
5
4
6
9
,

 
 
5
,

 
 
3
2
1
3
,

 
 
1
6
1
,

 
 
3
,

 
 
9
2
0
8
,

 
 
1
3
3
,

 
 
3
2
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
6
1
,

 
 
3
,

 
 
7
5
,

 
 
4
5
5
7
2
,

 
 
3
2
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
0
2
1
8
,

 
 
5
4
3
7
5
,

 
 
1
7
4
3
,

 
 
2
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
2
5
8
,

 
 
2
,

 
 
2
6
7
6
9
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
8
5
1
8
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
6
1
7
,

 
 
3
0
0
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
5
5
0
,

 
 
4
7
8
0
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
1
8
4
,

 
 
5
8
8
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
1
,

 
 
1
4
0
2
,

 
 
3
,

 
 
1
4
7
7
,

 
 
8
1
5
,

 
 
1
3
7
9
,

 
 
2
6
7
7
0
,

 
 
1
,

 
 
1
6
8
5
,

 
 
3
,

 
 
9
5
7
8
]
,

 
[
4
,

 
 
7
8
2
,

 
 
3
5
3
,

 
 
8
,

 
 
9
5
9
,

 
 
3
0
9
,

 
 
6
9
,

 
 
1
1
,

 
 
8
,

 
 
3
1
4
7
,

 
 
1
,

 
 
2
3
1
8
1
,

 
 
5
,

 
 
6
0
4
,

 
 
6
3
5
,

 
 
1
5
,

 
 
3
2
4
4
,

 
 
3
,

 
 
1
,

 
 
1
1
6
0
,

 
 
1
8
,

 
 
2
3
8
3
8
,

 
 
2
1
,

 
 
1
,

 
 
6
0
4
,

 
 
2
3
2
3
,

 
 
3
2
,

 
 
1
3
,

 
 
8
5
,

 
 
7
7
2
,

 
 
5
1
,

 
 
3
3
6
0
,

 
 
1
5
4
,

 
 
1
7
2
,

 
 
7
6
,

 
 
1
5
6
,

 
 
3
5
,

 
 
8
4
7
2
,

 
 
1
1
9
6
1
]
,

 
[
6
0
,

 
 
1
9
4
3
3
,

 
 
1
2
,

 
 
6
,

 
 
4
,

 
 
7
2
9
6
,

 
 
1
0
,

 
 
1
,

 
 
6
1
2
8
,

 
 
9
,

 
 
6
,

 
 
4
6
6
0
,

 
 
3
0
,

 
 
8
3
6
7
6
,

 
 
2
1
3
,

 
 
4
,

 
 
2
3
9
1
,

 
 
1
8
4
7
,

 
 
3
1
,

 
 
1
,

 
 
7
2
9
,

 
 
1
3
0
6
,

 
 
1
3
1
,

 
 
2
2
1
,

 
 
1
0
,

 
 
3
6
4
7
,

 
 
8
3
6
7
7
]
,

 
[
1
2
7
6
,

 
 
2
,

 
 
1
7
2
,

 
 
1
7
,

 
 
8
9
8
5
,

 
 
7
,

 
 
2
4
,

 
 
7
7
8
,

 
 
1
0
,

 
 
4
4
,

 
 
8
0
0
5
,

 
 
6
6
7
,

 
 
9
,

 
 
7
,

 
 
1
0
3
,

 
 
1
4
,

 
 
9
0
2
,

 
 
2
,

 
 
2
5
9
,

 
 
8
0
9
,

 
 
2
5
,

 
 
9
3
1
,

 
 
3
2
,

 
 
9
2
,

 
 
2
5
5
1
,

 
 
5
4
2
,

 
 
1
5
,

 
 
1
1
3
,

 
 
2
2
,

 
 
4
,

 
 
1
8
6
2
,

 
 
9
9
,

 
 
4
,

 
 
3
3
8
,

 
 
1
8
9
,

 
 
9
9
,

 
 
2
,

 
 
1
6
,

 
 
1
4
5
8
,

 
 
2
,

 
 
1
7
,

 
 
9
,

 
 
1
7
9
6
,

 
 
1
7
2
,

 
 
2
3
,

 
 
2
1
2
6
,

 
 
2
7
6
7
,

 
 
9
4
1
7
,

 
 
2
5
,

 
 
2
7
6
7
,

 
 
1
4
9
0
0
,

 
 
1
2
,

 
 
9
4
1
7
,

 
 
1
6
0
9
2
4
,

 
 
9
6
,

 
 
2
3
8
,

 
 
2
7
6
7
,

 
 
9
4
1
7
,

 
 
2
4
,

 
 
2
4
7
,

 
 
1
5
0
,

 
 
1
8
9
,

 
 
2
4
,

 
 
2
6
5
7
,

 
 
1
7
,

 
 
1
8
9
,

 
 
2
4
,

 
 
1
,

 
 
3
3
8
9
,

 
 
3
,

 
 
4
,

 
 
6
1
8
5
,

 
 
9
9
,

 
 
4
4
,

 
 
3
3
8
,

 
 
2
4
7
,

 
 
1
5
1
,

 
 
3
2
1
9
3
,

 
 
2
4
,

 
 
1
0
6
6
6
0
,

 
 
4
0
,

 
 
6
8
,

 
 
1
0
1
4
,

 
 
1
0
6
0
,

 
 
9
2
,

 
 
4
7
7
8
,

 
 
1
7
,

 
 
1
2
3
8
9
,

 
 
3
,

 
 
2
7
,

 
 
7
3
9
5
,

 
 
4
,

 
 
3
8
8
1
,

 
 
1
8
9
,

 
 
9
0
,

 
 
1
4
,

 
 
6
6
1
,

 
 
2
7
6
7
,

 
 
1
4
9
0
0
,

 
 
3
8
8
,

 
 
5
1
2
3
,

 
 
7
,

 
 
3
2
1
9
4
,

 
 
1
8
8
5
,

 
 
1
4
9
0
0
,

 
 
1
3
9
4
,

 
 
1
,

 
 
4
5
3
,

 
 
3
,

 
 
8
3
6
7
8
,

 
 
3
0
0
,

 
 
6
2
1
,

 
 
2
4
,

 
 
1
8
9
,

 
 
8
4
,

 
 
2
7
6
7
,

 
 
9
4
1
7
,

 
 
1
4
9
0
0
,

 
 
1
7
,

 
 
4
1
7
0
,

 
 
1
8
9
,

 
 
2
4
,

 
 
4
4
,

 
 
8
0
6
,

 
 
1
,

 
 
1
9
9
6
,

 
 
3
,

 
 
1
,

 
 
1
1
5
0
,

 
 
3
,

 
 
2
7
,

 
 
7
3
9
5
,

 
 
3
8
8
1
,

 
 
7
,

 
 
3
3
2
,

 
 
1
1
,

 
 
2
4
,

 
 
6
6
0
4
,

 
 
2
,

 
 
9
0
2
,

 
 
2
,

 
 
1
7
2
,

 
 
1
7
,

 
 
4
9
,

 
 
9
4
1
7
,

 
 
1
7
9
6
,

 
 
2
6
4
,

 
 
9
3
,

 
 
5
2
0
,

 
 
1
,

 
 
4
2
2
,

 
 
9
,

 
 
2
9
8
4
,

 
 
2
1
,

 
 
1
7
2
,

 
 
1
0
9
,

 
 
4
7
7
8
,

 
 
2
6
,

 
 
2
4
,

 
 
7
7
8
,

 
 
1
1
,

 
 
2
4
,

 
 
2
4
8
,

 
 
1
1
3
,

 
 
4
7
5
,

 
 
2
3
8
,

 
 
7
,

 
 
5
9
3
,

 
 
1
6
5
3
,

 
 
2
,

 
 
4
,

 
 
1
6
9
,

 
 
1
2
,

 
 
1
1
,

 
 
1
0
6
6
6
1
,

 
 
1
8
,

 
 
8
2
8
,

 
 
3
1
6
,

 
 
3
2
,

 
 
9
2
,

 
 
2
5
5
1
,

 
 
5
4
2
,

 
 
2
1
1
0
,

 
 
6
4
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
7
,

 
 
3
9
,

 
 
6
3
,

 
 
9
6
,

 
 
8
0
,

 
 
5
1
,

 
 
1
9
,

 
 
9
1
4
8
,

 
 
1
8
,

 
 
1
4
,

 
 
3
,

 
 
1
6
3
,

 
 
3
3
5
3
,

 
 
3
5
4
1
0
,

 
 
8
,

 
 
3
1
6
,

 
 
3
3
5
3
,

 
 
1
4
,

 
 
2
7
6
7
,

 
 
9
3
0
5
,

 
 
2
5
,

 
 
2
7
6
7
,

 
 
1
5
9
0
4
,

 
 
8
9
8
5
,

 
 
2
5
1
6
5
,

 
 
8
,

 
 
3
1
6
,

 
 
8
9
8
5
,

 
 
1
4
,

 
 
1
,

 
 
1
3
0
8
7
,

 
 
3
,

 
 
2
0
6
7
1
,

 
 
3
2
1
,

 
 
7
8
5
,

 
 
1
4
,

 
 
1
4
0
5
4
,

 
 
1
7
,

 
 
1
2
,

 
 
6
0
4
2
,

 
 
7
,

 
 
2
4
,

 
 
7
7
8
,

 
 
5
1
,

 
 
9
9
,

 
 
2
,

 
 
1
6
,

 
 
1
4
5
8
,

 
 
2
,

 
 
3
2
,

 
 
9
2
,

 
 
3
3
8
,

 
 
2
1
2
6
,

 
 
1
7
4
6
4
,

 
 
2
5
,

 
 
2
6
2
,

 
 
1
0
9
,

 
 
2
1
2
6
,

 
 
1
4
9
0
0
,

 
 
7
,

 
 
2
4
,

 
 
1
5
9
0
1
,

 
 
8
1
0
,

 
 
1
5
,

 
 
6
2
3
2
,

 
 
1
6
5
,

 
 
2
6
,

 
 
4
4
,

 
 
4
7
,

 
 
4
9
,

 
 
2
8
6
,

 
 
1
,

 
 
1
1
3
0
,

 
 
4
0
,

 
 
1
,

 
 
8
5
,

 
 
2
5
,

 
 
1
4
3
4
,

 
 
2
,

 
 
8
8
,

 
 
1
7
,

 
 
2
7
7
0
9
,

 
 
2
5
,

 
 
1
8
2
8
,

 
 
9
4
4
,

 
 
9
2
,

 
 
1
5
0
2
,

 
 
2
1
2
6
,

 
 
3
2
5
7
,

 
 
3
,

 
 
1
0
6
6
6
2
,

 
 
1
6
5
,

 
 
3
1
,

 
 
7
3
9
5
,

 
 
3
,

 
 
1
0
4
3
2
,

 
 
2
,

 
 
3
8
8
1
,

 
 
3
,

 
 
4
9
4
7
7
,

 
 
2
,

 
 
3
8
8
1
,

 
 
3
,

 
 
1
2
5
1
9
,

 
 
2
,

 
 
1
1
3
0
,

 
 
3
,

 
 
1
4
5
2
,

 
 
3
6
,

 
 
7
4
,

 
 
1
0
0
,

 
 
9
1
4
9
,

 
 
9
4
,

 
 
2
,

 
 
1
6
,

 
 
3
9
8
7
,

 
 
1
4
5
8
,

 
 
2
,

 
 
1
7
,

 
 
8
9
8
5
,

 
 
1
7
9
6
,

 
 
1
,

 
 
2
3
,

 
 
1
7
7
,

 
 
1
7
2
,

 
 
3
3
8
,

 
 
1
5
6
9
5
,

 
 
1
3
7
,

 
 
7
7
,

 
 
5
7
,

 
 
6
4
,

 
 
4
,

 
 
2
6
0
,

 
 
8
9
2
,

 
 
7
,

 
 
4
3
,

 
 
6
8
5
,

 
 
1
1
,

 
 
2
2
,

 
 
1
5
8
,

 
 
1
0
3
,

 
 
2
0
3
,

 
 
5
2
0
,

 
 
1
3
,

 
 
2
,

 
 
3
7
,

 
 
1
7
,

 
 
3
0
,

 
 
4
3
2
,

 
 
5
6
2
,

 
 
8
,

 
 
6
4
2
,

 
 
1
7
9
,

 
 
7
,

 
 
8
1
,

 
 
3
7
1
,

 
 
1
5
0
3
]
,

 
[
8
3
6
7
9
,

 
 
2
8
6
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
9
4
4
,

 
 
2
0
,

 
 
1
1
2
8
7
,

 
 
2
5
7
7
,

 
 
1
7
1
7
,

 
 
3
,

 
 
5
1
5
3
,

 
 
2
,

 
 
4
,

 
 
2
0
1
,

 
 
4
8
6
,

 
 
1
7
,

 
 
7
3
0
,

 
 
1
7
,

 
 
7
,

 
 
1
4
6
0
,

 
 
1
1
,

 
 
7
,

 
 
6
8
5
,

 
 
4
4
7
8
,

 
 
4
2
4
0
,

 
 
5
1
5
3
,

 
 
2
0
0
4
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
2
6
7
7
1
,

 
 
2
3
7
6
,

 
 
1
2
5
2
,

 
 
9
5
,

 
 
1
2
,

 
 
2
0
,

 
 
7
7
9
,

 
 
7
,

 
 
6
5
,

 
 
4
2
4
0
,

 
 
4
3
,

 
 
2
6
3
,

 
 
9
,

 
 
4
,

 
 
4
8
6
,

 
 
1
5
,

 
 
2
8
,

 
 
4
2
,

 
 
2
3
5
,

 
 
2
,

 
 
3
4
,

 
 
2
1
,

 
 
2
0
2
1
9
,

 
 
6
8
,

 
 
1
7
6
2
,

 
 
2
6
,

 
 
5
7
3
,

 
 
2
8
9
]
,

 
[
5
1
,

 
 
1
8
,

 
 
4
0
,

 
 
3
2
3
4
,

 
 
7
1
,

 
 
1
4
,

 
 
9
9
6
,

 
 
1
2
9
,

 
 
8
3
,

 
 
6
4
,

 
 
1
7
0
4
,

 
 
5
5
,

 
 
8
5
8
,

 
 
2
6
7
,

 
 
4
0
,

 
 
1
9
5
9
,

 
 
7
3
9
6
,

 
 
3
,

 
 
3
0
4
,

 
 
7
5
,

 
 
5
2
5
1
,

 
 
2
,

 
 
7
9
,

 
 
2
5
,

 
 
7
5
,

 
 
2
1
,

 
 
1
0
2
,

 
 
1
1
9
7
,

 
 
8
5
7
,

 
 
9
,

 
 
4
5
,

 
 
1
9
9
,

 
 
3
4
9
,

 
 
2
3
6
,

 
 
5
1
,

 
 
4
0
6
0
,

 
 
9
2
,

 
 
3
8
9
2
,

 
 
1
7
,

 
 
1
6
3
,

 
 
9
,

 
 
8
,

 
 
7
4
0
,

 
 
2
,

 
 
8
8
,

 
 
3
8
2
,

 
 
3
,

 
 
2
0
9
,

 
 
1
,

 
 
3
8
4
,

 
 
1
7
,

 
 
4
,

 
 
3
3
7
,

 
 
3
,

 
 
7
4
8
,

 
 
5
,

 
 
8
2
1
,

 
 
3
8
,

 
 
5
1
,

 
 
1
8
,

 
 
1
8
6
,

 
 
2
,

 
 
7
0
,

 
 
7
3
0
,

 
 
2
1
,

 
 
1
,

 
 
6
9
8
7
6
,

 
 
3
,

 
 
1
,

 
 
1
4
7
0
,

 
 
1
3
5
,

 
 
2
1
3
5
,

 
 
5
,

 
 
2
1
3
5
,

 
 
8
3
0
,

 
 
1
0
7
3
,

 
 
1
0
5
,

 
 
1
0
,

 
 
4
3
6
,

 
 
4
5
,

 
 
1
6
,

 
 
2
9
7
1
2
,

 
 
2
8
,

 
 
4
,

 
 
4
9
3
,

 
 
9
,

 
 
5
1
3
,

 
 
3
2
,

 
 
7
0
7
5
,

 
 
5
,

 
 
6
9
1
6
,

 
 
5
5
6
,

 
 
9
2
,

 
 
7
0
7
,

 
 
3
4
0
8
,

 
 
4
5
,

 
 
6
6
1
,

 
 
1
,

 
 
1
7
7
7
3
,

 
 
3
,

 
 
7
4
8
,

 
 
1
2
5
,

 
 
3
2
1
0
,

 
 
5
,

 
 
3
8
0
,

 
 
5
2
5
2
,

 
 
8
,

 
 
1
7
1
8
3
,

 
 
1
2
,

 
 
2
1
9
2
,

 
 
1
,

 
 
1
0
7
5
,

 
 
1
0
6
6
6
3
,

 
 
3
,

 
 
3
5
7
1
,

 
 
1
0
7
9
,

 
 
5
,

 
 
1
2
0
8
,

 
 
8
2
4
,

 
 
1
,

 
 
1
1
5
,

 
 
1
8
9
8
,

 
 
9
,

 
 
8
,

 
 
1
4
1
0
,

 
 
2
,

 
 
3
6
0
8
,

 
 
3
0
2
9
,

 
 
8
3
,

 
 
3
1
,

 
 
4
7
,

 
 
2
8
,

 
 
2
,

 
 
2
7
,

 
 
6
1
,

 
 
4
5
,

 
 
3
0
8
4
1
,

 
 
1
,

 
 
2
6
0
,

 
 
6
8
0
,

 
 
6
3
1
1
,

 
 
9
,

 
 
3
3
0
,

 
 
9
2
,

 
 
1
3
2
1
5
,

 
 
4
9
8
,

 
 
1
4
1
,

 
 
3
,

 
 
2
1
0
9
6
,

 
 
3
4
9
4
,

 
 
2
7
,

 
 
1
7
3
7
,

 
 
2
,

 
 
2
0
1
0
,

 
 
3
2
8
,

 
 
4
7
9
,

 
 
3
3
0
,

 
 
6
1
,

 
 
6
9
1
7
,

 
 
2
1
,

 
 
2
6
0
,

 
 
6
1
0
,

 
 
1
0
7
3
,

 
 
8
3
0
,

 
 
4
1
6
,

 
 
2
1
,

 
 
4
4
,

 
 
2
5
,

 
 
2
6
0
,

 
 
2
0
0
,

 
 
7
6
1
,

 
 
1
2
4
,

 
 
4
1
6
,

 
 
3
2
5
,

 
 
7
4
8
,

 
 
4
5
,

 
 
1
6
,

 
 
1
,

 
 
6
9
4
3
,

 
 
3
,

 
 
1
,

 
 
2
6
0
,

 
 
9
,

 
 
7
0
,

 
 
7
4
,

 
 
2
,

 
 
8
2
,

 
 
1
3
7
2
,

 
 
6
3
8
,

 
 
5
6
3
1
,

 
 
5
,

 
 
1
9
,

 
 
1
,

 
 
1
0
8
5
,

 
 
2
,

 
 
1
7
9
5
,

 
 
1
2
,

 
 
8
8
,

 
 
4
0
3
1
,

 
 
2
2
8
0
,

 
 
5
1
9
0
,

 
 
4
8
7
7
]
,

 
[
1
3
7
,

 
 
1
6
7
,

 
 
4
0
8
,

 
 
7
,

 
 
1
1
7
,

 
 
1
1
,

 
 
1
2
7
,

 
 
2
2
,

 
 
6
,

 
 
3
5
2
8
,

 
 
4
8
,

 
 
6
9
8
7
7
,

 
 
1
8
5
,

 
 
6
,

 
 
6
0
8
1
7
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
3
7
1
,

 
 
4
,

 
 
1
5
8
8
,

 
 
3
,

 
 
1
6
0
9
2
5
,

 
 
2
,

 
 
5
8
6
,

 
 
1
2
4
,

 
 
4
7
7
2
,

 
 
1
1
,

 
 
2
8
1
,

 
 
3
4
2
,

 
 
6
,

 
 
1
8
,

 
 
1
9
6
,

 
 
2
,

 
 
3
7
3
,

 
 
1
1
,

 
 
2
,

 
 
4
1
8
,

 
 
1
2
,

 
 
1
1
,

 
 
2
,

 
 
1
6
,

 
 
1
4
6
,

 
 
3
1
7
8
,

 
 
4
8
3
2
,

 
 
7
5
0
8
,

 
 
2
3
9
3
]
,

 
[
5
0
0
,

 
 
1
1
,

 
 
1
8
1
,

 
 
5
1
7
3
,

 
 
2
,

 
 
1
,

 
 
9
4
8
,

 
 
2
4
8
2
,

 
 
6
,

 
 
1
8
4
,

 
 
1
0
8
,

 
 
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
5
3
7
,

 
 
1
5
9
7
,

 
 
2
1
6
0
,

 
 
4
5
4
8
,

 
 
2
,

 
 
6
3
,

 
 
7
4
,

 
 
1
1
,

 
 
4
9
9
5
,

 
 
2
,

 
 
1
1
6
3
,

 
 
1
5
9
7
,

 
 
2
1
6
0
,

 
 
4
5
4
8
]
,

 
[
3
4
,

 
 
1
4
,

 
 
4
9
3
8
,

 
 
6
1
,

 
 
2
0
5
,

 
 
2
1
,

 
 
4
4
,

 
 
1
2
6
7
,

 
 
6
,

 
 
1
9
,

 
 
6
7
0
,

 
 
4
,

 
 
5
4
9
4
,

 
 
5
8
7
,

 
 
2
1
1
3
,

 
 
1
5
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
3
4
,

 
 
1
4
,

 
 
3
4
5
,

 
 
5
5
,

 
 
5
8
,

 
 
2
1
8
,

 
 
1
5
,

 
 
3
0
,

 
 
2
9
,

 
 
6
8
4
,

 
 
7
,

 
 
4
5
,

 
 
2
8
7
2
,

 
 
2
,

 
 
1
,

 
 
1
2
5
3
,

 
 
2
5
,

 
 
9
6
,

 
 
2
7
2
0
,

 
 
1
6
9
1
,

 
 
2
2
,

 
 
7
,

 
 
1
9
,

 
 
2
]
,

 
[
1
,

 
 
6
2
5
9
,

 
 
8
,

 
 
1
4
,

 
 
1
,

 
 
3
7
4
,

 
 
3
3
8
,

 
 
1
2
,

 
 
1
,

 
 
1
1
4
,

 
 
8
0
2
,

 
 
2
9
6
,

 
 
2
9
2
8
,

 
 
1
7
7
,

 
 
1
,

 
 
6
2
5
9
,

 
 
7
,

 
 
2
2
0
,

 
 
1
1
,

 
 
2
4
,

 
 
7
7
,

 
 
2
9
6
,

 
 
2
7
3
6
,

 
 
2
9
2
8
,

 
 
9
,

 
 
3
4
9
,

 
 
9
9
,

 
 
1
,

 
 
6
2
5
9
,

 
 
5
6
5
,

 
 
4
1
,

 
 
1
8
,

 
 
2
2
4
3
,

 
 
7
,

 
 
4
5
,

 
 
1
6
,

 
 
1
3
7
6
,

 
 
1
,

 
 
2
9
]
,

 
[
2
0
0
9
,

 
 
5
,

 
 
5
0
,

 
 
5
9
,

 
 
2
3
6
9
,

 
 
2
0
,

 
 
3
3
7
,

 
 
1
5
,

 
 
1
7
5
,

 
 
3
8
7
,

 
 
1
2
,

 
 
1
8
6
,

 
 
1
1
,

 
 
8
,

 
 
2
7
,

 
 
7
4
0
,

 
 
2
1
4
,

 
 
1
2
5
,

 
 
2
4
,

 
 
1
,

 
 
4
3
1
9
,

 
 
1
8
5
,

 
 
4
,

 
 
3
0
2
,

 
 
2
1
4
,

 
 
2
,

 
 
2
8
9
8
,

 
 
2
,

 
 
1
,

 
 
1
7
0
6
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
1
9
4
7
,

 
 
8
,

 
 
5
7
9
3
,

 
 
2
6
,

 
 
1
8
5
,

 
 
2
4
0
3
,

 
 
1
2
,

 
 
1
,

 
 
5
4
3
7
6
,

 
 
1
,

 
 
4
8
6
,

 
 
8
,

 
 
6
1
1
,

 
 
1
2
,

 
 
1
8
3
,

 
 
2
1
2
,

 
 
1
7
,

 
 
1
1
,

 
 
6
9
7
,

 
 
4
,

 
 
6
1
8
,

 
 
3
1
3
0
,

 
 
5
7
5
,

 
 
3
,

 
 
1
,

 
 
3
9
7
2
8
,

 
 
5
,

 
 
1
,

 
 
2
0
2
2
0
,

 
 
1
2
,

 
 
1
3
,

 
 
7
0
4
1
,

 
 
8
0
0
,

 
 
2
9
8
8
,

 
 
1
7
,

 
 
1
5
,

 
 
9
,

 
 
5
8
6
,

 
 
2
9
,

 
 
9
,

 
 
6
6
2
8
,

 
 
3
5
,

 
 
1
4
1
,

 
 
3
2
0
7
,

 
 
1
0
,

 
 
7
0
4
1
,

 
 
6
4
8
,

 
 
1
0
,

 
 
2
1
0
,

 
 
9
6
1
,

 
 
1
,

 
 
2
0
2
2
0
,

 
 
8
,

 
 
3
3
,

 
 
4
,

 
 
2
3
1
4
,

 
 
1
8
9
6
,

 
 
4
7
5
6
,

 
 
5
0
4
,

 
 
3
1
,

 
 
1
,

 
 
3
9
7
2
8
,

 
 
5
,

 
 
2
1
0
,

 
 
1
,

 
 
1
3
9
4
,

 
 
9
1
1
,

 
 
5
,

 
 
1
,

 
 
8
7
4
1
,

 
 
9
1
1
,

 
 
1
5
,

 
 
9
,

 
 
4
2
1
,

 
 
1
8
,

 
 
1
9
4
2
,

 
 
2
1
,

 
 
4
3
3
,

 
 
6
1
,

 
 
1
1
7
0
,

 
 
1
,

 
 
4
7
0
8
,

 
 
5
3
8
,

 
 
2
,

 
 
1
,

 
 
1
9
6
5
,

 
 
1
,

 
 
5
4
3
7
6
,

 
 
1
6
9
0
4
,

 
 
1
5
,

 
 
4
9
4
,

 
 
2
4
3
5
,

 
 
1
7
,

 
 
9
2
,

 
 
3
8
9
,

 
 
2
6
,

 
 
1
,

 
 
5
8
,

 
 
4
7
,

 
 
4
1
5
4
,

 
 
1
,

 
 
4
8
1
7
,

 
 
4
8
6
,

 
 
1
,

 
 
5
8
,

 
 
9
2
,

 
 
1
3
0
8
8
,

 
 
1
0
2
0
,

 
 
9
4
,

 
 
1
2
2
1
,

 
 
7
3
]
,

 
[
1
7
4
,
 
2
6
7
7
2
,
 
1
3
5
,
 
1
6
0
9
2
6
,
 
2
9
,
 
1
3
9
,
 
6
0
1
,
 
2
7
1
,
 
1
3
3
1
,
 
5
,
 
4
3
9
]
,

 
[
7
6
0
4
,
 
5
3
7
8
,
 
5
,
 
4
0
,
 
1
,
 
2
2
1
,
 
2
,
 
6
]
,

 
[
8
5
3
,

 
 
2
0
1
7
,

 
 
8
,

 
 
8
0
,

 
 
9
,

 
 
2
2
3
,

 
 
3
,

 
 
1
,

 
 
8
2
6
,

 
 
6
9
7
,

 
 
1
1
,

 
 
1
1
,

 
 
2
8
6
,

 
 
1
5
2
5
,

 
 
3
,

 
 
6
1
0
,

 
 
4
6
2
8
,

 
 
1
9
,

 
 
8
1
7
9
,

 
 
1
0
,

 
 
3
9
7
2
9
,

 
 
2
3
8
3
9
,

 
 
5
,

 
 
9
,

 
 
1
3
,

 
 
4
7
,

 
 
9
9
,

 
 
4
,

 
 
5
2
8
,

 
 
3
0
8
4
2
,

 
 
1
0
,

 
 
1
1
,

 
 
1
1
,

 
 
1
8
1
,

 
 
1
1
7
,

 
 
1
0
4
,

 
 
5
2
3
,

 
 
2
2
9
7
,

 
 
2
3
8
]
,

 
[
6
7
,
 
6
,
 
2
3
7
0
,
 
5
0
,
 
1
9
,
 
3
7
,
 
4
8
9
8
,
 
8
0
,
 
6
,
 
3
6
2
,
 
7
,
 
1
0
8
,
 
2
,
 
3
1
3
3
,
 
1
5
,
 
2
0
,
 
5
7
4
0
]
,

 
[
7
,

 
 
1
9
,

 
 
4
4
6
,

 
 
2
0
,

 
 
3
4
5
,

 
 
8
9
,

 
 
2
6
,

 
 
7
,

 
 
1
6
3
1
,

 
 
1
,

 
 
1
8
0
1
,

 
 
2
6
9
9
,

 
 
2
7
3
,

 
 
5
4
,

 
 
2
4
,

 
 
4
1
,

 
 
1
2
7
,

 
 
2
1
,

 
 
1
0
9
7
,

 
 
4
,

 
 
2
6
0
,

 
 
4
9
6
,

 
 
1
5
0
]
,

 
[
5
0
,

 
 
8
0
5
,

 
 
2
0
9
,

 
 
2
8
7
5
,

 
 
7
9
,

 
 
1
8
1
8
,

 
 
1
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
2
0
4
7
,

 
 
5
,

 
 
2
8
,

 
 
4
4
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
9
5
,

 
 
5
,

 
 
4
8
2
,

 
 
1
2
9
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
9
7
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
1
5
,

 
 
6
1
,

 
 
7
5
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
3
3
,

 
 
1
2
5
2
0
,

 
 
6
7
5
1
,

 
 
2
8
,

 
 
4
2
,

 
 
4
,

 
 
2
3
0
,

 
 
2
4
8
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
1
0
,

 
 
6
0
,

 
 
9
6
1
,

 
 
4
1
0
,

 
 
6
2
,

 
 
2
3
8
7
,

 
 
1
0
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
8
7
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
3
2
,

 
 
6
4
0
,

 
 
2
5
,

 
 
7
7
3
,

 
 
3
2
,

 
 
1
,

 
 
1
4
6
1
,

 
 
1
8
4
0
,

 
 
2
0
6
,

 
 
1
5
,

 
 
1
7
4
,

 
 
1
4
,

 
 
1
5
,

 
 
6
1
,

 
 
1
8
1
6
,

 
 
2
5
,

 
 
7
5
,

 
 
5
0
,

 
 
2
3
8
4
,

 
 
2
0
6
1
,

 
 
4
9
6
0
,

 
 
1
3
4
,

 
 
6
]
,

 
[
4
9
4
7
8
,

 
 
2
8
5
,

 
 
1
2
6
,

 
 
4
,

 
 
1
1
5
,

 
 
2
1
9
6
,

 
 
7
1
,

 
 
4
,

 
 
5
4
2
0
,

 
 
7
7
6
,

 
 
2
6
,

 
 
6
0
8
1
8
,

 
 
6
9
8
7
8
,

 
 
1
6
0
9
2
7
,

 
 
3
5
0
5
,

 
 
3
7
4
3
6
,

 
 
1
9
,

 
 
5
7
,

 
 
1
3
3
,

 
 
1
2
,

 
 
4
,

 
 
3
4
8
,

 
 
8
0
6
,

 
 
9
3
,

 
 
1
,

 
 
3
0
0
,

 
 
3
,

 
 
4
9
4
7
8
,

 
 
4
9
4
7
8
,

 
 
8
,

 
 
5
4
0
,

 
 
4
,

 
 
8
8
3
6
,

 
 
2
,

 
 
8
3
6
8
0
,

 
 
1
6
1
5
7
,

 
 
1
6
0
9
2
8
,

 
 
8
,

 
 
1
0
2
,

 
 
6
1
8
,

 
 
5
,

 
 
3
,

 
 
4
4
3
,

 
 
3
0
8
4
3
,

 
 
3
9
6
,

 
 
3
2
1
9
5
,

 
 
5
,

 
 
2
8
7
,

 
 
1
9
,

 
 
5
7
,

 
 
5
2
9
6
,

 
 
1
3
3
,

 
 
1
0
8
0
,

 
 
1
,

 
 
2
4
4
,

 
 
1
2
,

 
 
4
,

 
 
4
6
6
9
,

 
 
5
,

 
 
4
,

 
 
9
7
6
,

 
 
2
,

 
 
4
6
8
,

 
 
4
1
,

 
 
1
8
,

 
 
9
4
7
,

 
 
1
7
2
7
,

 
 
4
6
4
,

 
 
2
1
,

 
 
4
9
4
7
8
,

 
 
4
3
,

 
 
1
3
2
,

 
 
1
1
2
1
,

 
 
1
6
,

 
 
3
5
7
7
,

 
 
2
1
1
9
,

 
 
1
2
6
2
,

 
 
1
5
,

 
 
1
,

 
 
2
5
7
,

 
 
4
9
4
7
8
,

 
 
8
,

 
 
6
5
5
5
,

 
 
1
9
7
6
,

 
 
6
6
2
,

 
 
9
3
,

 
 
1
,

 
 
1
4
0
5
5
,

 
 
1
9
5
1
,

 
 
1
1
,

 
 
1
6
1
5
8
,

 
 
2
1
0
,

 
 
5
4
7
,

 
 
2
7
7
1
0
,

 
 
5
,

 
 
5
5
4
1
,

 
 
6
9
,

 
 
9
6
,

 
 
8
0
,

 
 
1
0
,

 
 
8
2
,

 
 
1
,

 
 
1
1
2
8
8
,

 
 
1
1
4
8
,

 
 
3
,

 
 
1
,

 
 
6
2
5
,

 
 
4
2
5
,

 
 
1
,

 
 
6
2
5
,

 
 
2
8
5
,

 
 
3
9
7
3
0
,

 
 
6
5
2
5
,

 
 
1
7
,

 
 
7
,

 
 
2
2
0
,

 
 
1
3
7
,

 
 
1
6
7
,

 
 
1
5
0
,

 
 
4
1
,

 
 
8
,

 
 
2
4
1
,

 
 
2
4
7
,

 
 
2
1
,

 
 
4
1
,

 
 
9
1
,

 
 
4
,

 
 
1
1
7
2
,

 
 
4
9
3
1
,

 
 
2
3
,

 
 
3
5
,

 
 
1
,

 
 
1
7
2
7
,

 
 
2
3
5
4
,

 
 
3
,

 
 
1
2
1
2
,

 
 
6
6
2
,

 
 
1
8
1
7
,

 
 
2
1
9
6
,

 
 
5
,

 
 
4
1
,

 
 
9
1
,

 
 
4
,

 
 
1
6
9
,

 
 
1
0
,

 
 
1
,

 
 
6
3
,

 
 
6
6
,

 
 
1
1
6
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
2
,

 
 
1
1
,

 
 
9
,

 
 
2
3
,

 
 
3
,

 
 
4
4
3
,

 
 
5
6
,

 
 
1
4
7
,

 
 
2
4
1
,

 
 
4
8
,

 
 
1
,

 
 
1
1
6
,

 
 
7
,

 
 
3
3
7
0
9
,

 
 
4
1
,

 
 
8
,

 
 
2
4
1
,

 
 
3
5
,

 
 
4
9
4
7
8
,

 
 
1
9
7
,

 
 
9
,

 
 
3
7
4
3
,

 
 
4
,

 
 
9
4
7
,

 
 
1
1
6
,

 
 
1
5
,

 
 
1
6
0
9
2
9
,

 
 
1
4
5
5
0
,

 
 
5
4
3
,

 
 
8
0
,

 
 
1
1
5
,

 
 
2
1
9
6
,

 
 
2
5
,

 
 
6
8
4
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
8
5
8
,

 
 
8
3
9
,

 
 
3
,

 
 
1
3
6
3
,

 
 
9
1
,

 
 
2
8
2
5
,

 
 
3
2
,

 
 
2
5
9
,

 
 
4
2
3
2
,

 
 
1
5
,

 
 
1
3
,

 
 
2
6
7
]
,

 
[
7
,
 
2
2
7
,
 
1
5
,
 
2
0
,
 
8
9
6
,
 
6
7
,
 
6
]
,

 
[
6
,
 
1
8
,
 
3
6
,
 
1
6
1
5
]
,

 
[
4
1
0
,

 
 
2
0
9
,

 
 
3
0
4
0
,

 
 
1
0
,

 
 
1
3
,

 
 
1
3
8
,

 
 
1
9
3
,

 
 
9
,

 
 
1
0
7
,

 
 
2
2
1
2
0
,

 
 
8
,

 
 
1
4
5
5
1
,

 
 
3
0
4
0
,

 
 
3
,

 
 
5
4
3
7
7
,

 
 
4
5
5
7
3
,

 
 
2
,

 
 
1
4
1
3
,

 
 
1
3
,

 
 
1
3
8
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
1
8
0
,

 
 
1
0
7
,

 
 
4
6
,

 
 
6
9
8
7
9
,

 
 
1
7
8
,

 
 
6
9
8
7
9
,

 
 
1
3
,

 
 
2
8
5
,

 
 
5
2
9
7
,

 
 
1
3
8
0
,

 
 
5
4
3
7
8
,

 
 
1
8
3
7
9
,

 
 
5
9
3
4
,

 
 
4
1
0
3
,

 
 
5
,

 
 
1
6
1
1
,

 
 
5
0
4
6
,

 
 
1
7
1
6
7
,

 
 
1
1
,

 
 
5
2
6
,

 
 
4
8
,

 
 
1
,

 
 
1
4
5
9
,

 
 
8
,

 
 
9
,

 
 
4
1
,

 
 
1
8
,

 
 
7
7
,

 
 
4
7
,

 
 
2
5
,

 
 
1
4
9
,

 
 
7
4
3
,

 
 
7
5
,

 
 
1
6
8
2
,

 
 
2
,

 
 
3
0
1
5
,

 
 
9
7
5
,

 
 
3
,

 
 
1
,

 
 
2
6
2
,

 
 
1
0
9
,

 
 
5
,

 
 
1
,

 
 
8
5
5
,

 
 
1
8
,

 
 
9
2
,

 
 
3
0
4
0
,

 
 
2
3
8
,

 
 
7
,

 
 
6
5
0
,

 
 
1
1
,

 
 
5
7
3
5
,

 
 
9
,

 
 
2
2
1
2
0
,

 
 
8
,

 
 
1
4
,

 
 
4
7
,

 
 
3
,

 
 
8
3
6
8
1
,

 
 
1
7
0
,

 
 
3
0
4
0
,

 
 
2
7
8
3
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
2
0
9
,

 
 
4
,

 
 
1
0
7
,

 
 
1
0
9
,

 
 
1
0
,

 
 
1
3
,

 
 
3
0
9
,

 
 
2
,

 
 
9
7
,

 
 
1
1
,

 
 
3
8
1
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
4
,

 
 
1
2
5
4
]
,

 
[
9
5
,

 
 
1
9
0
5
6
,

 
 
3
0
,

 
 
1
7
2
3
,

 
 
8
,

 
 
9
,

 
 
7
9
8
,

 
 
5
7
3
,

 
 
6
1
3
,

 
 
1
8
7
,

 
 
1
,

 
 
1
7
4
,

 
 
1
5
0
,

 
 
1
3
0
4
,

 
 
1
1
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
5
2
,

 
 
2
4
,

 
 
1
3
1
4
,

 
 
3
5
,

 
 
1
6
3
9
,

 
 
3
7
1
7
,

 
 
7
,

 
 
3
3
2
,

 
 
7
,

 
 
1
5
6
,

 
 
9
,

 
 
2
0
5
,

 
 
1
8
,

 
 
9
7
2
,

 
 
2
,

 
 
1
0
1
8
,

 
 
1
1
,

 
 
7
3
,

 
 
1
0
,

 
 
1
3
8
,

 
 
1
1
4
,

 
 
5
,

 
 
2
0
1
5
,

 
 
4
,

 
 
3
1
9
,

 
 
3
8
2
,

 
 
3
,

 
 
7
1
8
,

 
 
7
7
5
,

 
 
3
4
6
]
,

 
[
5
4
,
 
7
,
 
1
3
1
,
 
7
3
,
 
3
2
,
 
2
6
1
6
,
 
8
6
8
9
,
 
8
3
]
,

 
[
3
9
2
3
,

 
 
3
3
7
1
0
,

 
 
7
8
,

 
 
1
9
,

 
 
6
,

 
 
1
8
7
,

 
 
3
0
,

 
 
1
5
8
3
,

 
 
2
,

 
 
1
,

 
 
3
9
2
3
,

 
 
3
3
7
1
0
,

 
 
2
9
,

 
 
5
1
,

 
 
8
6
,

 
 
1
0
7
1
,

 
 
5
1
1
]
,

 
[
1
0
,

 
 
4
,

 
 
5
3
0
6
,

 
 
1
2
,

 
 
1
0
6
6
6
4
,

 
 
2
2
6
4
2
,

 
 
1
7
8
0
,

 
 
3
2
1
,

 
 
7
,

 
 
1
6
3
5
,

 
 
2
,

 
 
6
3
,

 
 
7
4
,

 
 
3
0
4
,

 
 
3
,

 
 
1
,

 
 
1
4
9
,

 
 
1
0
5
3
,

 
 
7
1
3
,

 
 
1
7
3
,

 
 
7
5
8
,

 
 
1
,

 
 
2
3
,

 
 
1
0
,

 
 
5
5
,

 
 
1
1
0
]
,

 
[
1
,

 
 
3
4
4
,

 
 
1
9
,

 
 
5
7
,

 
 
1
1
3
8
,

 
 
1
2
,

 
 
4
,

 
 
2
0
8
,

 
 
1
7
,

 
 
2
8
,

 
 
2
4
,

 
 
3
2
2
,

 
 
1
2
,

 
 
3
5
,

 
 
5
5
8
,

 
 
8
6
7
,

 
 
7
,

 
 
4
9
,

 
 
1
3
9
2
,

 
 
3
0
4
9
,

 
 
5
4
,

 
 
9
7
3
,

 
 
6
1
,

 
 
2
1
8
,

 
 
1
7
2
5
,

 
 
1
,

 
 
5
2
0
9
,

 
 
7
9
3
6
,

 
 
5
4
,

 
 
7
,

 
 
8
4
,

 
 
1
8
7
,

 
 
2
6
,

 
 
2
3
9
,

 
 
6
3
,

 
 
6
,

 
 
9
9
,

 
 
1
3
1
,

 
 
6
1
,

 
 
8
7
0
,

 
 
1
4
0
,

 
 
7
,

 
 
6
6
,

 
 
1
0
0
2
,

 
 
9
3
0
7
,

 
 
4
8
3
7
,

 
 
3
1
,

 
 
2
7
3
6
,

 
 
2
9
2
8
,

 
 
2
,

 
 
2
7
3
6
,

 
 
2
9
2
8
,

 
 
3
,

 
 
1
,

 
 
6
4
3
,

 
 
1
7
3
6
,

 
 
1
,

 
 
1
1
9
,

 
 
2
4
,

 
 
2
0
7
,

 
 
3
3
,

 
 
6
9
9
,

 
 
2
4
6
7
,

 
 
7
7
8
2
,

 
 
3
2
,

 
 
5
4
,

 
 
8
5
,

 
 
1
,

 
 
6
4
7
7
,

 
 
8
6
,

 
 
7
3
,

 
 
6
,

 
 
5
6
,

 
 
3
1
2
4
,

 
 
8
4
,

 
 
6
,

 
 
1
0
3
,

 
 
1
1
4
7
8
,

 
 
1
1
2
,

 
 
4
1
9
6
,

 
 
9
8
9
,

 
 
6
6
9
,

 
 
4
6
]
,

 
[
2
8
3
7
,
 
1
3
4
,
 
6
,
 
1
0
2
,
 
1
2
8
]
,

 
[
2
7
7
1
1
,

 
 
6
,

 
 
1
5
5
5
,

 
 
6
7
,

 
 
7
2
,

 
 
1
6
5
,

 
 
2
,

 
 
2
0
5
4
,

 
 
3
0
,

 
 
7
9
,

 
 
5
,

 
 
6
,

 
 
1
8
,

 
 
1
6
5
,

 
 
2
,

 
 
3
1
7
,

 
 
1
1
,

 
 
2
5
,

 
 
3
3
1
,

 
 
7
,

 
 
1
2
6
2
9
,

 
 
8
3
8
8
,

 
 
6
,

 
 
1
0
,

 
 
1
,

 
 
2
7
7
1
1
,

 
 
2
2
5
,

 
 
1
1
3
4
,

 
 
4
4
0
8
,

 
 
4
8
8
9
,

 
 
5
9
8
4
,

 
 
4
0
5
9
]
,

 
[
8
7
,

 
 
1
4
0
6
,

 
 
2
0
,

 
 
1
0
0
8
,

 
 
1
5
,

 
 
1
,

 
 
1
9
5
2
,

 
 
3
,

 
 
3
8
6
8
,

 
 
2
8
6
7
0
,

 
 
4
2
,

 
 
5
7
,

 
 
5
6
7
,

 
 
5
6
8
6
,

 
 
6
,

 
 
3
4
,

 
 
1
4
,

 
 
7
0
,

 
 
7
4
,

 
 
2
,

 
 
1
5
9
,

 
 
5
0
9
4
,

 
 
2
1
,

 
 
5
9
1
3
,

 
 
5
,

 
 
4
2
6
,

 
 
7
9
7
1
,

 
 
2
1
6
0
2
,

 
 
2
7
8
,

 
 
3
7
,

 
 
3
1
6
0
,

 
 
6
,

 
 
9
,

 
 
2
0
,

 
 
4
9
0
,

 
 
3
3
5
4
,

 
 
7
9
,

 
 
4
5
,

 
 
6
7
4
,

 
 
7
7
7
,

 
 
1
0
,

 
 
4
,

 
 
3
9
2
,

 
 
3
3
,

 
 
1
1
3
,

 
 
1
4
7
3
,

 
 
2
5
,

 
 
4
,

 
 
1
0
7
,

 
 
3
7
9
]
,

 
[
8
2
6
,

 
 
5
6
6
,

 
 
1
2
,

 
 
6
7
3
1
,

 
 
2
0
8
2
,

 
 
2
2
,

 
 
7
,

 
 
6
3
,

 
 
9
,

 
 
6
7
9
,

 
 
8
2
6
,

 
 
5
6
6
,

 
 
2
3
,

 
 
4
7
,

 
 
5
8
,

 
 
8
5
,

 
 
2
3
1
,

 
 
2
5
7
4
,

 
 
4
,

 
 
1
6
9
5
,

 
 
7
6
,

 
 
3
,

 
 
1
,

 
 
3
2
7
0
,

 
 
2
1
3
9
,

 
 
6
,

 
 
1
8
,

 
 
1
7
1
,

 
 
1
1
,

 
 
8
9
,

 
 
1
1
,

 
 
2
8
5
,

 
 
1
2
5
1
,

 
 
2
5
,

 
 
5
7
4
1
,

 
 
6
,

 
 
1
8
,

 
 
4
9
,

 
 
2
9
0
,

 
 
4
,

 
 
9
0
1
,

 
 
7
6
,

 
 
3
,

 
 
2
2
5
,

 
 
5
,

 
 
7
,

 
 
2
5
4
0
,

 
 
9
,

 
 
2
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
2
,

 
 
6
2
,

 
 
4
8
5
,

 
 
1
,

 
 
7
9
7
,

 
 
3
0
4
2
,

 
 
4
3
5
,

 
 
1
5
5
]
,

 
[
1
6
0
9
3
0
,

 
 
1
6
0
9
,

 
 
1
2
,

 
 
1
0
1
6
9
,

 
 
2
9
7
,

 
 
1
0
,

 
 
1
,

 
 
6
3
3
4
,

 
 
8
,

 
 
4
,

 
 
2
0
0
,

 
 
1
6
6
2
,

 
 
7
,

 
 
6
5
,

 
 
7
2
,

 
 
5
2
1
,

 
 
1
8
6
,

 
 
5
1
,

 
 
8
6
,

 
 
2
4
6
8
,

 
 
7
,

 
 
8
4
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
1
1
7
5
2
,

 
 
1
1
8
,

 
 
7
2
,

 
 
1
4
,

 
 
1
8
6
,

 
 
1
8
5
,

 
 
2
7
,

 
 
1
6
0
9
3
1
,

 
 
1
6
1
,

 
 
3
3
,

 
 
9
,

 
 
8
3
9
,

 
 
3
,

 
 
4
0
9
5
,

 
 
1
7
,

 
 
1
6
8
2
,

 
 
2
,

 
 
1
1
,

 
 
9
1
,

 
 
1
8
3
8
9
,

 
 
1
3
5
,

 
 
4
,

 
 
4
3
6
,

 
 
3
3
7
1
1
,

 
 
1
2
4
2
,

 
 
1
3
0
8
9
,

 
 
2
3
,

 
 
2
6
,

 
 
7
,

 
 
7
5
6
,

 
 
5
0
9
,

 
 
2
7
,

 
 
8
6
0
,

 
 
1
4
8
,

 
 
1
1
,

 
 
7
1
,

 
 
4
,

 
 
1
9
7
1
,

 
 
4
9
5
,

 
 
1
2
3
7
,

 
 
1
7
,

 
 
1
6
4
,

 
 
6
9
4
4
,

 
 
1
3
5
,

 
 
3
3
7
1
2
,

 
 
5
0
3
,

 
 
1
2
,

 
 
1
4
1
,

 
 
2
3
7
7
,

 
 
1
0
8
,

 
 
4
,

 
 
5
1
0
,

 
 
7
6
6
,

 
 
1
2
,

 
 
1
1
]
,

 
[
1
7
9
,
 
1
6
0
9
3
2
,
 
2
4
,
 
3
3
3
,
 
3
2
,
 
1
0
4
2
6
,
 
1
1
9
6
2
,
 
1
0
,
 
9
5
3
,
 
9
5
1
]
,

 
[
3
1
0
2
,

 
 
7
,

 
 
1
9
3
,

 
 
9
,

 
 
8
3
8
9
,

 
 
2
9
7
,

 
 
3
1
0
2
,

 
 
2
0
3
9
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
5
,

 
 
9
,

 
 
6
1
,

 
 
6
1
8
,

 
 
8
0
0
2
,

 
 
1
0
,

 
 
1
7
9
,

 
 
1
3
2
1
9
,

 
 
6
2
0
,

 
 
1
9
7
0
,

 
 
4
7
9
3
,

 
 
4
9
4
2
,

 
 
1
2
,

 
 
1
0
5
8
9
,

 
 
6
2
0
,

 
 
5
7
0
,

 
 
1
8
,

 
 
1
1
2
1
0
,

 
 
1
7
,

 
 
1
1
1
,

 
 
5
,

 
 
1
1
1
,

 
 
3
1
0
2
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
1
5
7
0
,

 
 
2
1
2
,

 
 
2
0
9
7
,

 
 
3
1
,

 
 
1
0
8
9
8
,

 
 
2
,

 
 
6
2
3
3
,

 
 
4
5
7
1
,

 
 
1
0
,

 
 
1
,

 
 
6
4
3
,

 
 
3
8
6
,

 
 
2
,

 
 
3
0
7
,

 
 
8
2
5
,

 
 
1
3
,

 
 
2
3
,

 
 
8
3
8
9
,

 
 
2
9
7
,

 
 
1
5
6
9
6
,

 
 
1
1
,

 
 
5
6
,

 
 
1
6
,

 
 
4
8
5
,

 
 
2
,

 
 
8
3
8
9
,

 
 
2
9
7
,

 
 
3
1
0
2
,

 
 
4
,

 
 
4
6
3
0
,

 
 
1
1
7
5
3
,

 
 
1
0
,

 
 
1
,

 
 
5
1
4
,

 
 
6
0
0
,

 
 
8
,

 
 
7
7
4
2
,

 
 
7
,

 
 
4
3
,

 
 
6
8
5
,

 
 
1
3
8
,

 
 
1
5
,

 
 
1
3
,

 
 
4
6
0
,

 
 
5
,

 
 
7
,

 
 
4
5
,

 
 
9
0
4
6
,

 
 
1
,

 
 
4
6
0
,

 
 
4
9
9
,

 
 
7
3
0
,

 
 
3
0
5
]
,

 
[
1
5
8
2
,
 
8
5
0
,
 
7
1
0
,
 
5
0
,
 
1
7
1
,
 
2
2
,
 
6
,
 
3
0
7
,
 
2
,
 
6
7
1
,
 
2
8
,
 
6
,
 
4
5
,
 
1
6
,
 
1
8
8
,
 
3
1
,
 
1
2
9
]
,

 
[
4
5
4
,

 
 
3
,

 
 
2
5
5
0
,

 
 
2
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
1
0
,

 
 
3
4
5
5
,

 
 
2
1
,

 
 
1
,

 
 
4
7
5
,

 
 
1
5
,

 
 
1
3
,

 
 
7
,

 
 
6
3
0
1
,

 
 
5
0
6
9
,

 
 
6
,

 
 
3
,

 
 
1
7
5
,

 
 
3
0
,

 
 
2
5
5
0
,

 
 
2
,

 
 
2
0
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
3
,

 
 
1
,

 
 
2
5
7
,

 
 
2
3
,

 
 
1
5
8
7
,

 
 
3
,

 
 
1
,

 
 
1
1
5
2
,

 
 
7
5
3
,

 
 
8
5
2
,

 
 
4
9
4
7
9
,

 
 
3
9
8
2
,

 
 
2
9
7
1
,

 
 
2
6
9
7
,

 
 
5
7
3
0
,

 
 
5
5
8
]
,

 
[
1
2
1
8
3
,
 
7
9
3
9
,
 
1
6
2
,
 
1
6
2
,
 
6
2
2
]
,

 
[
8
1
6
,
 
5
8
1
,
 
8
7
,
 
7
1
0
,
 
2
1
6
,
 
1
6
0
9
3
3
,
 
9
1
2
]
,

 
[
1
4
9
,

 
 
2
1
8
,

 
 
1
1
,

 
 
3
9
7
,

 
 
4
4
,

 
 
9
3
0
,

 
 
2
,

 
 
1
,

 
 
4
0
0
0
,

 
 
3
,

 
 
1
4
0
,

 
 
2
2
,

 
 
2
7
,

 
 
2
9
2
,

 
 
8
,

 
 
2
5
3
6
,

 
 
5
,

 
 
1
6
5
,

 
 
3
1
5
,

 
 
7
3
7
,

 
 
4
,

 
 
1
5
1
9
,

 
 
1
4
0
,

 
 
4
7
4
,

 
 
1
6
4
0
5
,

 
 
6
9
,

 
 
6
,

 
 
2
3
9
,

 
 
4
8
,

 
 
4
7
,

 
 
3
,

 
 
8
8
,

 
 
4
5
,

 
 
1
0
2
3
3
,

 
 
8
5
,

 
 
8
6
9
0
,

 
 
6
7
8
,

 
 
1
2
,

 
 
6
,

 
 
3
8
6
7
,

 
 
4
4
9
0
,

 
 
2
6
8
7
,

 
 
6
9
9
2
]
,

 
[
1
7
8
,

 
 
5
7
3
,

 
 
3
,

 
 
5
4
5
,

 
 
2
,

 
 
1
5
6
4
,

 
 
1
0
1
,

 
 
4
0
6
1
,

 
 
5
7
,

 
 
6
4
,

 
 
1
2
,

 
 
3
5
,

 
 
1
6
0
9
3
4
,

 
 
1
9
,

 
 
9
9
,

 
 
1
0
6
6
6
5
,

 
 
6
7
8
,

 
 
2
6
,

 
 
1
4
9
,

 
 
1
9
,

 
 
5
7
,

 
 
1
,

 
 
1
8
3
5
,

 
 
9
9
,

 
 
4
,

 
 
1
6
0
9
3
5
,

 
 
8
3
6
8
2
,

 
 
6
3
3
,

 
 
1
6
0
9
3
6
,

 
 
2
,

 
 
4
5
8
,

 
 
3
0
,

 
 
2
9
5
5
,

 
 
1
6
0
9
3
7
,

 
 
6
6
3
,

 
 
6
1
,

 
 
7
5
1
,

 
 
2
7
,

 
 
1
6
0
9
3
8
,

 
 
2
4
,

 
 
1
6
0
9
3
9
,

 
 
5
3
,

 
 
4
0
,

 
 
4
4
,

 
 
9
,

 
 
1
4
,

 
 
1
0
6
6
6
6
,

 
 
1
7
4
4
6
,

 
 
9
,

 
 
8
4
6
,

 
 
1
0
4
,

 
 
4
9
,

 
 
4
8
,

 
 
2
7
,

 
 
8
3
6
8
3
,

 
 
5
1
8
2
,

 
 
5
7
,

 
 
5
5
9
,

 
 
2
,

 
 
1
1
8
,

 
 
1
9
,

 
 
4
4
,

 
 
1
1
0
,

 
 
2
,

 
 
9
4
,

 
 
4
1
,

 
 
1
4
6
5
,

 
 
7
,

 
 
1
9
,

 
 
5
6
4
,

 
 
1
8
2
9
,

 
 
2
9
1
9
,

 
 
1
6
0
9
4
0
,

 
 
5
7
,

 
 
1
5
6
0
,

 
 
3
5
,

 
 
1
,

 
 
2
6
2
,

 
 
8
5
,

 
 
2
4
,

 
 
3
1
5
,

 
 
1
6
0
9
4
1
,

 
 
4
8
7
7
,

 
 
7
,

 
 
4
4
,

 
 
1
2
8
0
,

 
 
1
0
2
,

 
 
5
6
4
,

 
 
1
,

 
 
4
1
9
4
,

 
 
8
3
6
8
3
,

 
 
5
4
3
7
9
,

 
 
1
6
0
9
4
2
,

 
 
1
6
7
,

 
 
2
2
,

 
 
7
,

 
 
2
6
4
2
,

 
 
9
4
,

 
 
2
,

 
 
1
,

 
 
3
6
3
5
,

 
 
2
,

 
 
9
4
,

 
 
2
1
6
0
3
,

 
 
1
7
,

 
 
7
3
0
,

 
 
1
7
,

 
 
4
4
1
,

 
 
9
,

 
 
3
2
,

 
 
1
,

 
 
8
5
,

 
 
7
,

 
 
9
0
,

 
 
1
1
,

 
 
4
3
,

 
 
1
6
,

 
 
2
,

 
 
1
3
5
0
,

 
 
2
,

 
 
3
4
,

 
 
5
5
,

 
 
2
2
8
,

 
 
1
2
,

 
 
3
7
,

 
 
7
,

 
 
4
4
,

 
 
1
0
4
,

 
 
2
,

 
 
1
3
5
0
,

 
 
4
0
,

 
 
7
,

 
 
1
0
8
,

 
 
8
,

 
 
2
,

 
 
4
4
,

 
 
7
4
,

 
 
2
5
0
,

 
 
7
,

 
 
1
9
,

 
 
4
1
6
,

 
 
1
9
,

 
 
1
6
0
9
4
3
,

 
 
4
7
,

 
 
1
0
,

 
 
1
6
0
9
4
4
,

 
 
1
2
2
3
,

 
 
4
7
,

 
 
1
0
,

 
 
1
6
0
9
4
5
,

 
 
4
7
,

 
 
1
0
,

 
 
7
8
9
2
,

 
 
1
2
2
3
,

 
 
7
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
6
3
,

 
 
1
6
,

 
 
2
1
6
0
4
,

 
 
7
,

 
 
3
6
2
,

 
 
1
9
,

 
 
4
,

 
 
5
2
5
3
,

 
 
7
,

 
 
1
0
8
,

 
 
1
5
5
,

 
 
2
0
8
0
,

 
 
1
7
,

 
 
1
2
8
,

 
 
3
,

 
 
3
8
,

 
 
7
,

 
 
1
9
,

 
 
4
1
6
,

 
 
2
1
,

 
 
7
,

 
 
4
7
7
,

 
 
3
0
,

 
 
1
6
6
6
,

 
 
2
7
,

 
 
1
6
0
9
4
6
,

 
 
9
3
,

 
 
3
0
0
,

 
 
1
0
4
,

 
 
5
7
1
,

 
 
7
2
8
,

 
 
4
9
1
,

 
 
1
2
,

 
 
6
0
,

 
 
1
2
1
,

 
 
2
,

 
 
9
4
,

 
 
2
,

 
 
4
,

 
 
2
9
5
5
,

 
 
7
,

 
 
4
7
6
,

 
 
1
9
,

 
 
1
,

 
 
1
0
8
5
,

 
 
2
,

 
 
3
4
,

 
 
1
3
,

 
 
1
9
,

 
 
4
4
,

 
 
4
1
6
8
,

 
 
2
,

 
 
9
8
2
,

 
 
3
,

 
 
2
0
7
9
,

 
 
3
0
,

 
 
5
2
5
3
,

 
 
5
,

 
 
7
,

 
 
1
8
,

 
 
2
6
7
7
3
,

 
 
1
4
3
,

 
 
8
9
,

 
 
5
2
,

 
 
8
,

 
 
1
6
5
0
,

 
 
6
8
,

 
 
1
4
4
8
,

 
 
9
,

 
 
4
2
,

 
 
3
0
0
4
,

 
 
6
6
,

 
 
5
2
,

 
 
4
2
,

 
 
4
,

 
 
1
6
0
9
4
7
,

 
 
3
1
,

 
 
4
0
4
,

 
 
2
5
5
6
,

 
 
5
2
,

 
 
4
9
,

 
 
4
2
5
6
,

 
 
4
,

 
 
7
6
0
5
,

 
 
3
1
,

 
 
6
8
,

 
 
1
6
0
9
4
8
,

 
 
2
7
,

 
 
4
2
,

 
 
9
9
,

 
 
2
,

 
 
3
4
,

 
 
2
5
6
7
,

 
 
3
,

 
 
2
6
1
6
,

 
 
1
5
,

 
 
1
1
,

 
 
6
6
,

 
 
2
1
,

 
 
1
,

 
 
1
2
1
,

 
 
3
,

 
 
6
8
,

 
 
3
6
5
2
,

 
 
2
7
8
,

 
 
6
8
,

 
 
1
6
0
9
4
9
,

 
 
3
3
8
9
,

 
 
1
9
6
2
,

 
 
1
1
,

 
 
2
7
,

 
 
1
9
4
1
,

 
 
6
3
3
,

 
 
8
4
6
,

 
 
1
8
9
,

 
 
4
9
,

 
 
1
9
8
5
,

 
 
1
7
2
,

 
 
1
1
5
7
,

 
 
2
7
,

 
 
2
5
9
6
1
,

 
 
1
1
,

 
 
1
0
6
6
6
7
,

 
 
8
9
,

 
 
5
3
,

 
 
4
7
6
,

 
 
1
9
,

 
 
4
,

 
 
1
6
0
9
5
0
,

 
 
2
,

 
 
1
2
1
,

 
 
1
9
1
,

 
 
5
4
5
,

 
 
2
8
6
,

 
 
5
3
7
,

 
 
4
7
6
,

 
 
2
5
8
,

 
 
1
6
8
,

 
 
2
1
5
,

 
 
6
,

 
 
1
6
9
4
,

 
 
2
6
2
6
,

 
 
7
,

 
 
2
7
5
,

 
 
9
,

 
 
2
6
,

 
 
7
,

 
 
1
2
2
,

 
 
6
0
,

 
 
1
2
1
,

 
 
1
0
0
,

 
 
5
5
,

 
 
4
7
,

 
 
7
6
,

 
 
4
1
,

 
 
9
,

 
 
8
7
,

 
 
1
6
,

 
 
1
0
3
,

 
 
1
2
1
,

 
 
3
7
,

 
 
2
1
,

 
 
2
1
5
,

 
 
3
3
,

 
 
4
0
,

 
 
4
9
,

 
 
3
3
2
,

 
 
1
4
2
8
,

 
 
2
8
9
,

 
 
2
,

 
 
2
1
9
,

 
 
1
9
9
,

 
 
1
9
,

 
 
6
3
6
,

 
 
1
5
0
,

 
 
2
,

 
 
1
2
8
,

 
 
4
2
2
2
,

 
 
2
6
,

 
 
7
2
8
,

 
 
1
5
6
0
,

 
 
7
6
,

 
 
3
,

 
 
8
5
,

 
 
5
0
,

 
 
3
9
,

 
 
3
6
,

 
 
4
7
,

 
 
1
2
1
,

 
 
3
7
,

 
 
3
0
,

 
 
7
9
4
,

 
 
8
,

 
 
1
6
0
9
5
1
,

 
 
6
6
0
5
,

 
 
2
4
3
,

 
 
2
5
,

 
 
1
3
,

 
 
3
4
1
,

 
 
5
0
,

 
 
1
2
2
,

 
 
3
6
,

 
 
1
2
1
,

 
 
2
2
,

 
 
2
5
9
,

 
 
3
9
,

 
 
5
3
7
,

 
 
1
0
6
6
6
8
,

 
 
5
4
5
,

 
 
1
0
,

 
 
4
1
,

 
 
8
5
,

 
 
3
,

 
 
1
2
2
,

 
 
7
,

 
 
2
2
6
,

 
 
1
5
8
,

 
 
8
7
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
1
2
1
,

 
 
3
7
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
0
6
6
6
9
,

 
 
2
,

 
 
3
7
,

 
 
3
0
,

 
 
1
1
0
3
,

 
 
6
6
,

 
 
8
,

 
 
1
6
0
9
5
2
,

 
 
9
1
2
,

 
 
7
3
5
9
]
,

 
[
5
2
,

 
 
1
6
6
1
,

 
 
6
0
8
1
9
,

 
 
1
,

 
 
3
4
0
,

 
 
3
2
,

 
 
6
0
8
2
0
,

 
 
3
3
8
0
,

 
 
5
,

 
 
4
7
2
6
,

 
 
4
2
,

 
 
4
,

 
 
3
8
4
5
,

 
 
3
2
4
,

 
 
5
,

 
 
6
6
,

 
 
1
6
0
0
,

 
 
8
6
5
4
]
,

 
[
6
4
,
 
1
8
,
 
1
,
 
3
4
5
2
,
 
3
,
 
6
8
,
 
1
4
0
,
 
3
1
,
 
9
,
 
5
7
6
,
 
4
6
]
,

 
[
1
7
5
3
,
 
6
9
9
,
 
9
1
9
,
 
4
5
0
2
,
 
1
0
0
1
,
 
2
1
6
]
,

 
[
4
9
,
 
1
1
1
8
,
 
7
3
,
 
5
,
 
6
0
6
,
 
1
1
1
8
,
 
5
9
,
 
7
9
,
 
1
3
5
4
]
,

 
[
4
1
5
,
 
9
4
,
 
4
,
 
3
0
0
,
 
6
,
 
1
1
3
4
,
 
3
4
8
8
,
 
4
7
5
5
,
 
6
7
5
0
,
 
1
6
0
]
,

 
[
3
8
,
 
3
3
1
,
 
9
5
2
,
 
3
4
,
 
6
,
 
1
0
8
,
 
2
,
 
7
0
]
,

 
[
8
9
4
0
,

 
 
1
4
,

 
 
1
0
6
6
7
0
,

 
 
1
4
3
,

 
 
5
0
1
,

 
 
5
1
0
2
,

 
 
4
9
4
8
0
,

 
 
1
6
0
2
,

 
 
3
9
2
,

 
 
9
,

 
 
1
,

 
 
1
1
2
7
9
,

 
 
7
5
,

 
 
1
8
,

 
 
1
3
2
,

 
 
2
5
0
9
,

 
 
4
7
0
,

 
 
2
,

 
 
1
,

 
 
2
5
9
6
2
,

 
 
5
,

 
 
8
9
4
0
,

 
 
7
2
,

 
 
5
2
1
,

 
 
1
8
6
,

 
 
1
4
,

 
 
1
0
6
6
7
0
,

 
 
5
2
,

 
 
1
9
3
6
,

 
 
6
1
3
6
,

 
 
1
1
2
7
9
,

 
 
1
6
0
9
5
3
,

 
 
1
,

 
 
2
6
2
2
,

 
 
8
,

 
 
3
9
3
,

 
 
2
2
,

 
 
5
1
,

 
 
1
8
,

 
 
4
8
4
9
,

 
 
7
2
2
9
,

 
 
3
1
,

 
 
8
9
4
0
,

 
 
6
2
,

 
 
8
6
,

 
 
1
9
9
,

 
 
1
2
6
,

 
 
1
0
9
8
1
,

 
 
2
,

 
 
5
5
,

 
 
4
7
,

 
 
2
2
3
,

 
 
3
,

 
 
9
3
4
,

 
 
9
,

 
 
4
3
,

 
 
5
2
0
,

 
 
1
,

 
 
4
2
1
4
,

 
 
4
8
5
5
,

 
 
5
5
6
,

 
 
1
,

 
 
1
5
6
8
1
,

 
 
4
0
9
,

 
 
1
0
,

 
 
1
1
2
7
9
,

 
 
1
2
,

 
 
3
1
1
,

 
 
7
8
,

 
 
1
,

 
 
8
2
,

 
 
3
,

 
 
6
9
4
,

 
 
3
8
2
,

 
 
3
,

 
 
6
2
0
5
,

 
 
3
3
,

 
 
1
,

 
 
4
5
3
,

 
 
3
,

 
 
1
4
0
5
6
,

 
 
1
0
0
4
0
,

 
 
1
0
4
3
1
,

 
 
1
0
,

 
 
1
1
2
7
9
,

 
 
1
3
,

 
 
8
,

 
 
5
5
1
,

 
 
4
,

 
 
7
5
3
2
,

 
 
3
,

 
 
2
5
9
6
3
,

 
 
5
,

 
 
3
0
8
4
4
,

 
 
2
6
,

 
 
8
,

 
 
1
1
,

 
 
4
,

 
 
7
5
3
2
,

 
 
3
,

 
 
8
3
6
8
4
,

 
 
1
3
8
8
,

 
 
4
9
5
,

 
 
2
2
,

 
 
7
2
,

 
 
2
4
7
,

 
 
1
0
,

 
 
2
9
0
,

 
 
1
,

 
 
2
6
2
,

 
 
2
3
6
,

 
 
7
,

 
 
1
3
1
,

 
 
1
7
,

 
 
3
,

 
 
8
9
,

 
 
2
3
1
,

 
 
1
6
,

 
 
4
8
2
,

 
 
2
,

 
 
3
9
8
,

 
 
1
1
,

 
 
4
9
9
,

 
 
4
1
5
,

 
 
3
,

 
 
4
4
3
]
,

 
[
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
6
6
,

 
 
2
,

 
 
5
6
3
,

 
 
9
5
2
,

 
 
3
8
,

 
 
8
,

 
 
8
7
1
,

 
 
4
0
5
3
,

 
 
6
9
5
,

 
 
2
5
,

 
 
1
0
4
9
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
7
,

 
 
4
5
,

 
 
1
2
2
2
,

 
 
3
8
,

 
 
6
,

 
 
1
9
,

 
 
2
,

 
 
1
1
7
,

 
 
3
8
8
,

 
 
8
4
,

 
 
1
2
3
7
,

 
 
1
7
,

 
 
1
,

 
 
6
3
8
,

 
 
3
5
3
,

 
 
4
2
3
9
2
,

 
 
4
2
4
7
,

 
 
1
0
1
0
,

 
 
2
,

 
 
1
3
,

 
 
2
9
,

 
 
7
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
,

 
 
4
4
8
,

 
 
6
9
3
,

 
 
1
0
5
,

 
 
4
2
3
9
3
,

 
 
1
3
,

 
 
4
3
9
4
,

 
 
1
6
7
6
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
2
6
2
,

 
 
8
5
,

 
 
7
,

 
 
4
5
,

 
 
1
9
0
4
,

 
 
1
3
,

 
 
3
0
7
3
,

 
 
2
0
,

 
 
6
6
2
,

 
 
4
5
,

 
 
1
0
2
3
3
,

 
 
6
,

 
 
4
4
,

 
 
1
9
8
2
]
,

 
[
4
0
9
,

 
 
3
,

 
 
1
0
2
3
4
,

 
 
2
,

 
 
1
0
7
,

 
 
3
5
4
1
1
,

 
 
1
0
,

 
 
1
,

 
 
9
6
1
,

 
 
3
,

 
 
6
7
6
,

 
 
2
1
,

 
 
1
,

 
 
4
1
0
,

 
 
2
9
0
9
,

 
 
1
0
,

 
 
3
5
7
6
,

 
 
4
9
9
4
,

 
 
1
3
4
4
,

 
 
3
5
4
1
1
,

 
 
6
,

 
 
1
9
,

 
 
2
6
9
,

 
 
2
,

 
 
1
,

 
 
1
3
9
,

 
 
2
9
0
6
,

 
 
3
5
,

 
 
3
5
7
6
,

 
 
3
5
9
1
,

 
 
1
0
5
6
,

 
 
4
9
9
4
,

 
 
1
3
4
4
,

 
 
1
5
,

 
 
2
5
1
,

 
 
2
8
,

 
 
1
0
7
,

 
 
2
4
4
8
2
,

 
 
8
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
1
3
2
,

 
 
2
7
1
5
,

 
 
2
0
5
,

 
 
1
5
,

 
 
2
8
,

 
 
8
2
1
,

 
 
6
7
9
,

 
 
1
0
5
,

 
 
1
0
,

 
 
1
,

 
 
8
3
,

 
 
3
5
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
3
2
8
0
,

 
 
1
6
8
3
,

 
 
1
7
9
,

 
 
3
6
1
,

 
 
9
5
6
,

 
 
2
2
8
6
,

 
 
5
,

 
 
3
8
,

 
 
3
3
1
,

 
 
1
4
,

 
 
5
2
,

 
 
8
,

 
 
4
1
1
0
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
8
5
,

 
 
6
3
0
,

 
 
1
5
,

 
 
6
8
,

 
 
8
4
6
,

 
 
1
8
2
5
,

 
 
3
5
7
6
,

 
 
1
1
4
8
,

 
 
1
0
,

 
 
1
,

 
 
8
3
,

 
 
3
,

 
 
1
,

 
 
1
6
6
5
,

 
 
3
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
7
4
,

 
 
3
1
3
,

 
 
4
2
,

 
 
5
2
,

 
 
1
0
8
6
,

 
 
1
0
,

 
 
1
8
2
5
,

 
 
1
3
,

 
 
1
3
4
4
,

 
 
6
,

 
 
3
9
,

 
 
6
3
,

 
 
3
3
,

 
 
2
8
,

 
 
6
4
5
,

 
 
1
0
6
6
7
1
,

 
 
1
2
5
,

 
 
5
2
,

 
 
4
2
,

 
 
4
4
0
,

 
 
8
2
9
,

 
 
1
7
,

 
 
4
,

 
 
8
7
5
,

 
 
3
6
,

 
 
4
9
,

 
 
3
0
,

 
 
2
6
0
,

 
 
4
0
9
,

 
 
3
,

 
 
1
3
6
3
,

 
 
1
2
,

 
 
1
,

 
 
3
2
8
0
,

 
 
8
3
,

 
 
1
0
,

 
 
2
5
1
,

 
 
2
8
,

 
 
5
,

 
 
1
,

 
 
2
8
4
,

 
 
2
3
6
9
,

 
 
2
0
7
,

 
 
3
2
,

 
 
1
0
7
,

 
 
2
4
4
8
2
,

 
 
5
,

 
 
6
1
,

 
 
4
1
0
,

 
 
2
1
,

 
 
1
,

 
 
3
5
7
6
,

 
 
5
,

 
 
5
6
1
,

 
 
3
2
8
0
,

 
 
1
3
4
4
,

 
 
1
4
1
6
,

 
 
2
1
,

 
 
1
,

 
 
7
8
6
,

 
 
1
0
3
3
,

 
 
2
1
9
2
,

 
 
5
8
,

 
 
1
7
4
5
9
,

 
 
2
,

 
 
1
,

 
 
7
5
,

 
 
1
0
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
1
,

 
 
2
1
8
,

 
 
4
5
,

 
 
1
1
8
,

 
 
1
0
,

 
 
1
4
3
,

 
 
2
3
3
1
,

 
 
5
3
0
,

 
 
1
,

 
 
3
5
7
6
,

 
 
1
3
4
4
,

 
 
3
1
,

 
 
3
2
8
0
,

 
 
8
3
,

 
 
3
1
4
8
,

 
 
8
8
,

 
 
3
,

 
 
6
7
9
,

 
 
9
1
5
0
,

 
 
1
0
5
,

 
 
5
,

 
 
1
0
5
1
,

 
 
1
,

 
 
4
7
9
,

 
 
2
,

 
 
1
,

 
 
2
4
4
,

 
 
5
,

 
 
1
,

 
 
7
5
1
,

 
 
3
,

 
 
1
,

 
 
3
2
8
0
,

 
 
8
2
4
,

 
 
5
,

 
 
1
0
6
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
1
2
8
,

 
 
8
5
,

 
 
8
9
,

 
 
2
6
,

 
 
1
4
1
6
,

 
 
4
5
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
1
3
6
,

 
 
6
0
,

 
 
5
8
,

 
 
1
0
,

 
 
1
,

 
 
9
8
3
,

 
 
9
3
9
,

 
 
7
,

 
 
8
1
,

 
 
7
0
9
,

 
 
2
,

 
 
5
5
,

 
 
3
3
6
4
,

 
 
1
2
9
1
,

 
 
1
2
,

 
 
1
,

 
 
2
5
5
,

 
 
3
6
1
4
,

 
 
7
,

 
 
8
1
,

 
 
5
6
3
4
,

 
 
9
,

 
 
1
3
,

 
 
1
0
7
,

 
 
2
4
4
8
2
,

 
 
4
5
,

 
 
3
0
7
,

 
 
2
1
,

 
 
1
,

 
 
3
5
7
6
,

 
 
4
9
9
4
,

 
 
1
3
4
4
,

 
 
5
,

 
 
2
4
4
8
3
,

 
 
1
,

 
 
1
2
7
3
3
,

 
 
1
0
,

 
 
1
,

 
 
1
6
6
5
,

 
 
3
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
3
0
9
,

 
 
6
9
,

 
 
5
2
,

 
 
8
,

 
 
5
5
9
,

 
 
2
,

 
 
5
,

 
 
3
9
,

 
 
1
3
6
,

 
 
4
,

 
 
1
2
6
9
,

 
 
2
,

 
 
3
0
7
,

 
 
2
,

 
 
1
4
2
,

 
 
1
5
,

 
 
6
8
,

 
 
1
7
0
2
,

 
 
7
5
1
6
,

 
 
8
,

 
 
2
,

 
 
2
8
9
,

 
 
2
,

 
 
2
5
6
,

 
 
1
1
2
,

 
 
6
7
9
,

 
 
5
3
8
,

 
 
5
,

 
 
1
0
4
6
,

 
 
1
,

 
 
4
7
9
,

 
 
3
5
,

 
 
1
,

 
 
2
9
0
0
,

 
 
3
2
8
0
,

 
 
1
6
8
3
,

 
 
1
7
9
,

 
 
8
3
6
8
5
,

 
 
9
5
6
,

 
 
2
2
8
6
,

 
 
3
5
4
1
1
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
3
5
0
,

 
 
1
6
3
,

 
 
6
4
,

 
 
3
3
,

 
 
3
0
8
,

 
 
2
,

 
 
3
1
4
,

 
 
9
,

 
 
1
0
7
,

 
 
4
6
,

 
 
3
5
4
1
1
,

 
 
5
,

 
 
1
0
7
,

 
 
4
6
,

 
 
4
2
3
9
4
,

 
 
8
,

 
 
1
4
,

 
 
1
,

 
 
1
3
9
,

 
 
1
0
7
,

 
 
6
0
,

 
 
5
2
5
2
,

 
 
1
3
5
,

 
 
3
0
,

 
 
1
0
7
,

 
 
1
0
9
,

 
 
4
2
3
9
4
,

 
 
1
,

 
 
7
7
,

 
 
1
0
7
,

 
 
7
,

 
 
8
1
,

 
 
2
0
9
,

 
 
2
,

 
 
1
0
4
6
,

 
 
2
,

 
 
2
8
,

 
 
8
,

 
 
4
2
3
9
4
,

 
 
1
1
,

 
 
8
,

 
 
6
0
5
0
,

 
 
3
,

 
 
1
,

 
 
1
1
4
,

 
 
1
7
4
3
,

 
 
3
,

 
 
3
0
,

 
 
1
0
9
,

 
 
2
2
6
4
3
,

 
 
5
,

 
 
3
0
,

 
 
2
6
2
,

 
 
1
0
9
,

 
 
1
6
4
0
6
,

 
 
1
0
7
,

 
 
3
5
4
1
1
,

 
 
8
,

 
 
4
,

 
 
8
8
4
,

 
 
1
0
7
,

 
 
2
8
8
,

 
 
9
,

 
 
1
0
7
,

 
 
1
0
9
,

 
 
8
,

 
 
1
8
3
6
4
,

 
 
3
1
,

 
 
1
1
5
7
2
,

 
 
4
,

 
 
3
2
8
0
,

 
 
1
1
4
,

 
 
1
0
9
,

 
 
5
,

 
 
8
9
8
6
,

 
 
2
5
,

 
 
1
,

 
 
1
3
8
7
,

 
 
3
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
0
3
8
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
3
1
,

 
 
1
5
4
0
,

 
 
7
,

 
 
2
4
,

 
 
9
0
8
,

 
 
1
0
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
5
,

 
 
1
9
,

 
 
2
1
4
0
,

 
 
4
1
,

 
 
3
8
8
,

 
 
7
,

 
 
6
9
2
,

 
 
2
,

 
 
1
4
1
5
,

 
 
1
1
4
,

 
 
5
,

 
 
1
5
4
0
,

 
 
1
5
0
,

 
 
5
8
,

 
 
9
3
,

 
 
2
3
3
,

 
 
2
7
4
,

 
 
5
,

 
 
2
9
6
,

 
 
3
5
5
,

 
 
4
0
,

 
 
1
,

 
 
6
7
9
,

 
 
1
0
5
,

 
 
3
1
,

 
 
1
,

 
 
3
5
7
6
,

 
 
4
9
9
4
,

 
 
1
3
4
4
,

 
 
1
1
3
8
9
,

 
 
3
1
,

 
 
1
,

 
 
3
5
9
1
,

 
 
1
0
5
6
,

 
 
5
,

 
 
3
5
5
,

 
 
1
1
,

 
 
1
3
5
,

 
 
6
6
0
3
,

 
 
1
0
5
6
,

 
 
2
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
1
4
1
7
9
,

 
 
1
,

 
 
3
2
8
0
,

 
 
1
6
8
3
,

 
 
5
,

 
 
4
0
,

 
 
7
1
,

 
 
8
3
0
5
,

 
 
3
2
,

 
 
4
1
0
,

 
 
1
7
,

 
 
2
4
4
8
2
,

 
 
8
,

 
 
1
,

 
 
2
1
2
,

 
 
3
,

 
 
6
0
,

 
 
3
,

 
 
3
0
,

 
 
1
2
9
,

 
 
9
1
5
,

 
 
1
0
,

 
 
2
8
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
,

 
 
7
7
,

 
 
1
0
7
,

 
 
2
9
2
,

 
 
3
1
,

 
 
1
4
4
4
,

 
 
3
,

 
 
2
9
0
0
,

 
 
2
5
,

 
 
2
1
,

 
 
3
2
8
0
,

 
 
1
6
0
6
,

 
 
9
,

 
 
4
2
,

 
 
1
,

 
 
1
3
9
,

 
 
7
5
1
,

 
 
1
2
,

 
 
1
3
,

 
 
3
5
7
6
,

 
 
4
9
9
4
,

 
 
1
3
4
4
,

 
 
9
,

 
 
2
3
7
,

 
 
8
,

 
 
2
0
6
7
2
,

 
 
1
0
,

 
 
1
,

 
 
3
2
8
0
,

 
 
8
3
,

 
 
6
,

 
 
3
9
,

 
 
9
2
3
,

 
 
1
,

 
 
4
1
4
,

 
 
3
,

 
 
9
4
7
,

 
 
4
1
4
,

 
 
2
4
4
8
2
,

 
 
5
,

 
 
6
3
,

 
 
9
,

 
 
5
8
,

 
 
9
3
,

 
 
9
9
1
,

 
 
3
,

 
 
6
8
,

 
 
9
1
5
,

 
 
1
8
,

 
 
1
1
1
3
7
,

 
 
1
0
,

 
 
2
8
6
7
1
,

 
 
1
,

 
 
3
2
8
0
,

 
 
1
6
8
3
,

 
 
5
,

 
 
1
0
4
,

 
 
8
3
0
5
]
,

 
[
3
3
,

 
 
1
0
6
6
7
2
,

 
 
2
4
3
,

 
 
7
,

 
 
2
9
1
,

 
 
2
8
6
7
2
,

 
 
1
9
4
3
,

 
 
1
0
,

 
 
2
6
7
7
,

 
 
1
9
5
1
,

 
 
6
6
8
2
,

 
 
3
,

 
 
6
4
3
3
,

 
 
9
8
0
1
,

 
 
1
6
0
9
5
4
,

 
 
3
0
4
3
,

 
 
1
6
0
9
5
5
,

 
 
2
8
0
3
,

 
 
7
4
7
8
,

 
 
4
5
5
7
4
,

 
 
1
0
4
3
3
,

 
 
4
7
7
6
,

 
 
1
0
6
6
7
2
]
,

 
[
4
9
,

 
 
2
,

 
 
1
8
4
3
,

 
 
3
8
,

 
 
7
2
,

 
 
1
2
7
6
,

 
 
2
,

 
 
1
0
,

 
 
6
4
6
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
5
1
6
,

 
 
2
,

 
 
2
9
7
,

 
 
9
,

 
 
4
9
4
8
1
,

 
 
8
,

 
 
9
7
4
,

 
 
2
9
4
,

 
 
4
6
]
,

 
[
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
8
1
1
,

 
 
2
1
,

 
 
2
8
,

 
 
2
0
,

 
 
7
9
7
,

 
 
8
6
1
,

 
 
5
,

 
 
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
3
6
8
,

 
 
2
5
,

 
 
1
8
7
,

 
 
5
0
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
2
,

 
 
5
5
,

 
 
6
1
,

 
 
1
4
5
6
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
4
,

 
 
1
5
9
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
9
6
,

 
 
2
9
,

 
 
2
,

 
 
5
9
5
,

 
 
5
8
,

 
 
3
5
,

 
 
8
2
1
,

 
 
2
,

 
 
1
7
5
,

 
 
3
8
4
,

 
 
4
7
3
1
,

 
 
4
6
,

 
 
1
0
6
6
7
3
]
,

 
[
1
,

 
 
2
3
,

 
 
4
9
4
8
2
,

 
 
1
6
0
9
5
6
,

 
 
4
2
,

 
 
5
7
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
2
4
,

 
 
2
0
7
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
1
6
6
8
,

 
 
2
,

 
 
1
6
,

 
 
3
5
,

 
 
4
,

 
 
2
2
2
,

 
 
4
3
8
,

 
 
3
,

 
 
7
5
,

 
 
7
4
6
,

 
 
1
1
9
3
,

 
 
6
7
2
,

 
 
2
5
,

 
 
5
8
6
,

 
 
1
7
4
,

 
 
2
6
,

 
 
1
1
,

 
 
9
0
,

 
 
1
4
,

 
 
9
2
0
,

 
 
7
4
,

 
 
2
5
,

 
 
7
8
,

 
 
1
,

 
 
2
5
7
,

 
 
8
,

 
 
3
4
2
,

 
 
9
,

 
 
8
,

 
 
7
8
,

 
 
2
7
,

 
 
2
3
,

 
 
3
5
,

 
 
9
,

 
 
2
5
7
,

 
 
5
6
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
2
8
,

 
 
1
8
2
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
8
3
,

 
 
9
,

 
 
3
4
,

 
 
1
4
,

 
 
2
0
1
1
,

 
 
5
0
3
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
3
3
,

 
 
5
5
,

 
 
8
5
,

 
 
2
2
,

 
 
6
,

 
 
3
9
,

 
 
9
2
0
,

 
 
7
8
,

 
 
1
,

 
 
2
5
7
,

 
 
8
,

 
 
1
2
6
,

 
 
3
4
2
,

 
 
6
,

 
 
1
8
,

 
 
2
0
0
,

 
 
2
,

 
 
3
5
7
,

 
 
4
7
1
,

 
 
1
,

 
 
2
3
,

 
 
2
9
0
,

 
 
1
8
6
,

 
 
2
,

 
 
7
2
5
,

 
 
5
5
,

 
 
1
2
1
5
,

 
 
1
0
6
,

 
 
5
0
,

 
 
6
3
,

 
 
1
,

 
 
4
2
7
,

 
 
1
2
,

 
 
3
8
,

 
 
8
,

 
 
7
0
1
,

 
 
9
0
4
,

 
 
1
7
,

 
 
3
4
2
,

 
 
5
,

 
 
1
2
,

 
 
4
9
4
,

 
 
1
3
6
9
,

 
 
3
,

 
 
8
3
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
7
5
,

 
 
4
3
4
,

 
 
1
2
,

 
 
1
3
9
5
,

 
 
1
2
,

 
 
5
8
6
,

 
 
8
3
0
,

 
 
1
2
,

 
 
1
7
2
8
,

 
 
2
5
,

 
 
1
2
,

 
 
1
5
2
8
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
1
7
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
2
5
4
,

 
 
3
5
,

 
 
1
3
,

 
 
4
6
,

 
 
2
,

 
 
3
7
]
,

 
[
3
9
7
3
1
,

 
 
1
3
7
,

 
 
2
9
1
,

 
 
7
6
,

 
 
4
,

 
 
5
6
6
,

 
 
1
2
6
4
,

 
 
2
1
9
5
,

 
 
4
0
7
,

 
 
3
,

 
 
1
3
,

 
 
2
4
,

 
 
1
2
8
6
,

 
 
3
9
5
,

 
 
4
4
,

 
 
3
9
2
,

 
 
3
,

 
 
1
1
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
7
,

 
 
5
3
,

 
 
7
0
,

 
 
1
,

 
 
4
2
4
,

 
 
1
7
7
7
4
,

 
 
1
8
1
,

 
 
1
9
,

 
 
9
0
6
,

 
 
2
,

 
 
1
3
,

 
 
8
0
2
,

 
 
1
0
5
,

 
 
8
7
,

 
 
1
6
,

 
 
1
8
7
3
8
]
,

 
[
7
7
4
,

 
 
4
6
0
,

 
 
6
0
8
2
1
,

 
 
1
6
4
0
7
,

 
 
1
0
9
6
,

 
 
2
1
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
7
4
4
9
,

 
 
1
3
,

 
 
1
3
8
,

 
 
2
3
4
7
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
1
4
9
0
1
,

 
 
1
0
9
6
,

 
 
6
0
8
2
1
,

 
 
1
0
3
1
,

 
 
6
2
7
9
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
1
4
9
0
1
,

 
 
1
0
9
6
,

 
 
2
3
4
7
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
1
4
9
0
1
,

 
 
1
0
9
6
,

 
 
1
5
9
0
5
,

 
 
2
5
9
6
4
,

 
 
1
0
1
6
9
,

 
 
5
2
4
,

 
 
2
1
0
,

 
 
7
0
9
2
,

 
 
8
9
,

 
 
1
9
,

 
 
1
,

 
 
1
3
9
,

 
 
1
0
9
,

 
 
1
0
4
1
9
,

 
 
9
9
3
8
,

 
 
3
9
7
3
2
]
,

 
[
4
4
,

 
 
1
2
2
,

 
 
2
,

 
 
7
1
1
,

 
 
1
3
,

 
 
2
3
0
,

 
 
2
3
8
4
0
,

 
 
3
8
2
,

 
 
3
,

 
 
4
9
,

 
 
4
5
1
,

 
 
1
,

 
 
3
1
3
,

 
 
5
8
,

 
 
3
9
3
,

 
 
2
3
0
,

 
 
3
,

 
 
1
1
3
,

 
 
6
8
1
,

 
 
1
4
2
5
,

 
 
5
1
6
,

 
 
4
1
,

 
 
8
,

 
 
2
7
,

 
 
9
7
7
,

 
 
6
7
6
,

 
 
1
4
8
,

 
 
1
3
,

 
 
8
1
1
2
,

 
 
1
0
9
,

 
 
5
,

 
 
7
5
1
3
,

 
 
8
,

 
 
1
3
3
,

 
 
3
2
,

 
 
1
3
0
,

 
 
2
3
7
2
,

 
 
3
2
9
9
,

 
 
7
8
,

 
 
5
6
,

 
 
2
8
,

 
 
9
4
1
8
,

 
 
7
1
,

 
 
1
2
0
0
,

 
 
1
4
4
,

 
 
1
1
,

 
 
8
,

 
 
5
2
9
6
,

 
 
1
3
3
,

 
 
2
,

 
 
1
2
2
6
,

 
 
1
,

 
 
2
9
7
,

 
 
3
,

 
 
1
7
4
6
5
,

 
 
5
4
3
,

 
 
1
0
,

 
 
8
3
,

 
 
9
3
5
,

 
 
4
7
0
,

 
 
2
,

 
 
9
3
2
,

 
 
9
,

 
 
8
2
,

 
 
1
,

 
 
7
5
1
3
,

 
 
1
0
9
,

 
 
2
,

 
 
9
0
2
,

 
 
2
,

 
 
1
1
]
,

 
[
1
,

 
 
1
4
9
,

 
 
4
2
3
,

 
 
2
1
8
,

 
 
4
3
,

 
 
1
6
,

 
 
7
1
7
,

 
 
2
,

 
 
1
6
5
1
,

 
 
9
,

 
 
1
1
,

 
 
2
4
,

 
 
6
0
8
2
2
,

 
 
1
0
,

 
 
1
,

 
 
4
9
0
4
,

 
 
4
7
,

 
 
2
6
1
,

 
 
8
3
0
,

 
 
1
0
,

 
 
2
5
1
,

 
 
4
9
,

 
 
1
1
7
,

 
 
3
2
1
9
6
,

 
 
2
8
9
8
,

 
 
2
6
,

 
 
1
4
4
,

 
 
6
,

 
 
1
9
,

 
 
1
,

 
 
4
7
,

 
 
9
,

 
 
2
8
3
6
,

 
 
3
7
4
3
7
,

 
 
9
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
3
,

 
 
2
,

 
 
1
9
3
,

 
 
8
0
,

 
 
1
1
,

 
 
5
1
3
,

 
 
3
7
4
3
7
,

 
 
2
2
,

 
 
5
1
,

 
 
3
9
2
,

 
 
4
1
,

 
 
9
,

 
 
1
0
4
,

 
 
4
,

 
 
8
7
4
2
,

 
 
3
1
,

 
 
1
,

 
 
4
7
,

 
 
1
7
1
7
,

 
 
2
2
6
9
,

 
 
6
9
,

 
 
7
,

 
 
2
2
9
,

 
 
1
3
6
,

 
 
5
5
,

 
 
1
3
8
2
,

 
 
1
2
9
7
,

 
 
2
5
,

 
 
2
5
1
,

 
 
9
1
0
,

 
 
9
,

 
 
5
5
1
4
,

 
 
9
,

 
 
1
,

 
 
6
1
,

 
 
8
,

 
 
1
6
0
9
5
7
,

 
 
2
1
2
,

 
 
1
2
,

 
 
3
1
0
,

 
 
6
0
5
1
,

 
 
8
0
4
6
,

 
 
4
8
7
,

 
 
1
5
,

 
 
1
,

 
 
2
8
7
9
,

 
 
3
5
,

 
 
3
8
,

 
 
1
1
,

 
 
2
4
,

 
 
4
0
1
,

 
 
1
5
,

 
 
2
2
,

 
 
1
0
4
,

 
 
4
4
5
,

 
 
8
,

 
 
4
0
,

 
 
9
,

 
 
8
,

 
 
1
2
6
,

 
 
6
6
3
,

 
 
1
2
,

 
 
1
,

 
 
4
3
2
,

 
 
2
3
,

 
 
2
6
,

 
 
1
0
3
,

 
 
1
2
6
,

 
 
1
2
1
,

 
 
1
,

 
 
2
8
7
9
,

 
 
2
3
,

 
 
5
4
0
,

 
 
6
0
8
2
3
]
,

 
[
4
3
9
,
 
4
6
,
 
2
1
0
9
7
,
 
8
6
1
4
,
 
1
7
7
7
5
]
,

 
[
4
4
,

 
 
2
4
1
,

 
 
4
8
,

 
 
9
,

 
 
7
,

 
 
4
9
,

 
 
5
7
7
,

 
 
2
,

 
 
1
5
3
8
,

 
 
7
6
,

 
 
1
,

 
 
7
4
7
4
,

 
 
4
1
,

 
 
8
6
,

 
 
4
,

 
 
3
4
8
,

 
 
3
,

 
 
1
1
3
7
,

 
 
2
3
4
,

 
 
4
,

 
 
1
9
6
,

 
 
3
7
7
,

 
 
1
2
,

 
 
3
0
,

 
 
3
4
3
,

 
 
7
1
2
,

 
 
5
,

 
 
3
6
,

 
 
1
5
,

 
 
7
,

 
 
1
0
3
,

 
 
1
9
,

 
 
2
8
3
5
,

 
 
1
1
,

 
 
7
,

 
 
1
6
4
3
,

 
 
2
6
,

 
 
7
,

 
 
2
3
9
,

 
 
6
5
,

 
 
4
1
,

 
 
2
4
,

 
 
2
1
5
,

 
 
1
5
,

 
 
4
1
,

 
 
9
,

 
 
2
4
,

 
 
1
0
0
6
,

 
 
9
9
6
,

 
 
5
3
1
3
,

 
 
1
2
,

 
 
1
,

 
 
3
5
8
2
]
,

 
[
7
8
,

 
 
2
0
,

 
 
2
3
,

 
 
2
8
2
,

 
 
6
4
5
1
,

 
 
1
5
,

 
 
1
7
8
,

 
 
7
2
,

 
 
2
8
0
,

 
 
2
,

 
 
2
8
9
8
,

 
 
1
5
,

 
 
2
0
,

 
 
1
3
5
8
,

 
 
1
,

 
 
1
1
6
4
,

 
 
6
,

 
 
2
0
4
,

 
 
1
1
,

 
 
1
0
,

 
 
2
6
,

 
 
1
,

 
 
1
4
0
0
,

 
 
8
,

 
 
1
1
,

 
 
8
,

 
 
3
0
9
,

 
 
1
4
,

 
 
1
,

 
 
7
0
8
,

 
 
3
,

 
 
2
2
8
,

 
 
2
8
,

 
 
8
,

 
 
1
2
,

 
 
1
1
2
,

 
 
2
2
4
,

 
 
1
8
,

 
 
4
0
,

 
 
1
0
,

 
 
4
7
,

 
 
2
5
,

 
 
6
1
,

 
 
3
,

 
 
1
,

 
 
3
7
0
,

 
 
2
7
6
9
,

 
 
2
5
5
,

 
 
2
6
,

 
 
2
,

 
 
2
0
4
,

 
 
8
8
,

 
 
4
0
,

 
 
1
0
,

 
 
4
7
,

 
 
2
0
2
,

 
 
1
,

 
 
6
5
2
,

 
 
2
0
,

 
 
2
3
,

 
 
8
,

 
 
9
1
,

 
 
1
3
2
2
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
8
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
8
1
2
,

 
 
8
3
,

 
 
1
5
,

 
 
1
8
3
6
8
,

 
 
1
2
2
,

 
 
1
1
9
7
,

 
 
3
8
9
,

 
 
9
,

 
 
1
,

 
 
3
5
3
,

 
 
8
,

 
 
1
7
1
5
,

 
 
1
3
3
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
1
2
,

 
 
2
1
8
,

 
 
1
3
1
,

 
 
7
3
,

 
 
4
7
,

 
 
3
0
3
,

 
 
5
8
,

 
 
1
1
2
2
,

 
 
1
5
,

 
 
1
6
0
9
5
8
,

 
 
1
0
,

 
 
1
,

 
 
2
2
4
,

 
 
3
1
,

 
 
1
,

 
 
1
9
6
,

 
 
6
0
0
,

 
 
2
5
5
,

 
 
1
,

 
 
1
6
1
,

 
 
3
,

 
 
3
6
6
,

 
 
2
3
,

 
 
1
2
6
8
,

 
 
8
,

 
 
9
9
6
,

 
 
4
9
1
,

 
 
3
3
,

 
 
1
5
5
,

 
 
6
4
7
]
,

 
[
6
0
7
,

 
 
7
,

 
 
2
4
,

 
 
7
3
7
,

 
 
2
1
7
,

 
 
5
4
,

 
 
8
,

 
 
2
7
,

 
 
2
6
6
8
,

 
 
2
,

 
 
1
,

 
 
4
2
0
,

 
 
7
9
,

 
 
7
2
3
,

 
 
1
7
,

 
 
4
4
5
,

 
 
1
5
,

 
 
1
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
2
9
]
,

 
[
1
0
7
,

 
 
2
2
9
3
,

 
 
3
7
,

 
 
1
0
7
,

 
 
1
6
0
9
5
9
,

 
 
1
8
2
8
,

 
 
7
3
7
,

 
 
1
4
0
,

 
 
1
7
7
,

 
 
3
1
9
,

 
 
2
5
,

 
 
1
0
5
1
,

 
 
2
1
2
,

 
 
5
2
,

 
 
4
2
,

 
 
6
6
,

 
 
3
5
9
2
,

 
 
1
4
9
7
,

 
 
3
7
4
3
8
,

 
 
1
0
,

 
 
3
0
,

 
 
2
3
3
1
,

 
 
5
0
,

 
 
1
2
1
]
,

 
[
1
4
,
 
2
2
6
4
4
,
 
5
2
1
,
 
7
5
0
,
 
1
6
0
,
 
5
6
9
,
 
2
7
4
,
 
5
0
4
]
,

 
[
7
2
8
,

 
 
1
6
6
5
3
,

 
 
7
,

 
 
1
6
4
1
,

 
 
8
1
,

 
 
1
3
7
,

 
 
5
7
,

 
 
6
4
,

 
 
4
,

 
 
8
9
7
,

 
 
3
,

 
 
1
3
2
4
,

 
 
5
,

 
 
6
,

 
 
4
1
1
,

 
 
3
7
,

 
 
2
,

 
 
1
6
,

 
 
2
7
,

 
 
1
2
7
1
,

 
 
1
0
7
,

 
 
5
0
,

 
 
5
9
,

 
 
4
6
,

 
 
3
5
,

 
 
3
7
,

 
 
1
0
5
7
,

 
 
3
0
,

 
 
1
5
7
,

 
 
4
8
,

 
 
2
3
5
,

 
 
4
8
0
,

 
 
1
0
1
4
]
,

 
[
1
6
0
9
6
0
,
 
7
,
 
6
5
,
 
1
,
 
2
3
,
 
1
0
9
,
 
5
6
,
 
1
6
,
 
6
9
2
,
 
2
,
 
1
6
0
9
6
1
]
,

 
[
5
0
1
,
 
2
8
3
,
 
1
8
,
 
6
,
 
4
,
 
5
0
7
,
 
1
5
6
9
7
]
,

 
[
4
5
5
7
5
,

 
 
7
2
,

 
 
2
8
0
,

 
 
9
0
,

 
 
7
,

 
 
2
5
5
6
,

 
 
2
0
,

 
 
2
3
5
,

 
 
2
7
9
4
,

 
 
8
5
6
,

 
 
4
0
,

 
 
7
2
2
5
,

 
 
4
,

 
 
8
9
7
,

 
 
9
2
6
3
,

 
 
8
4
0
,

 
 
5
8
3
,

 
 
3
8
,

 
 
4
,

 
 
1
2
7
5
,

 
 
7
,

 
 
2
5
4
0
,

 
 
6
,

 
 
2
1
1
,

 
 
5
2
1
,

 
 
3
9
3
,

 
 
1
6
5
7
,

 
 
2
3
5
,

 
 
2
8
,

 
 
4
2
9
0
,

 
 
1
9
,

 
 
1
1
5
6
,

 
 
8
0
9
,

 
 
1
0
,

 
 
2
0
,

 
 
5
9
9
9
,

 
 
6
8
1
5
,

 
 
4
5
8
4
,

 
 
3
6
4
0
,

 
 
5
9
0
,

 
 
1
1
6
6
0
]
,

 
[
1
1
5
,

 
 
1
2
3
,

 
 
6
7
8
,

 
 
6
,

 
 
1
2
7
,

 
 
7
4
4
,

 
 
4
3
0
,

 
 
3
4
4
,

 
 
2
1
,

 
 
2
9
6
2
,

 
 
2
7
2
,

 
 
5
3
8
,

 
 
6
,

 
 
1
6
7
,

 
 
5
1
,

 
 
8
6
,

 
 
3
1
,

 
 
2
7
9
3
,

 
 
1
7
0
9
,

 
 
5
,

 
 
2
6
1
4
,

 
 
1
8
2
,

 
 
1
,

 
 
2
3
4
0
,

 
 
3
8
,

 
 
1
3
1
,

 
 
6
,

 
 
6
5
,

 
 
1
,

 
 
2
7
9
3
,

 
 
1
0
7
1
6
,

 
 
3
4
4
,

 
 
1
8
2
,

 
 
1
,

 
 
2
3
4
0
,

 
 
2
2
,

 
 
6
,

 
 
3
0
9
,

 
 
3
2
2
6
,

 
 
9
,

 
 
1
1
5
7
,

 
 
1
0
,

 
 
5
2
7
,

 
 
2
,

 
 
1
9
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
1
4
6
0
,

 
 
1
,

 
 
3
4
4
,

 
 
6
4
,

 
 
8
4
,

 
 
5
0
,

 
 
1
1
7
,

 
 
3
6
,

 
 
8
9
,

 
 
3
6
,

 
 
7
,

 
 
3
9
,

 
 
1
7
3
3
,

 
 
3
5
6
,

 
 
8
8
,

 
 
2
2
,

 
 
1
4
,

 
 
7
,

 
 
1
2
2
0
,

 
 
6
,

 
 
4
5
,

 
 
4
9
8
,

 
 
9
4
6
,

 
 
5
5
6
,

 
 
1
,

 
 
4
9
0
,

 
 
5
8
1
,

 
 
4
9
6
,

 
 
1
4
3
8
,

 
 
1
2
5
,

 
 
5
,

 
 
7
4
,

 
 
9
,

 
 
1
7
0
9
,

 
 
6
6
8
,

 
 
1
,

 
 
3
4
4
,

 
 
1
8
2
,

 
 
9
,

 
 
1
1
5
7
,

 
 
2
2
,

 
 
6
,

 
 
3
4
,

 
 
1
0
5
4
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
1
2
8
4
2
]
,

 
[
2
3
1
8
2
,

 
 
3
3
6
,

 
 
6
,

 
 
5
0
,

 
 
4
1
2
0
,

 
 
3
9
8
,

 
 
1
0
6
5
,

 
 
2
3
1
8
2
,

 
 
7
,

 
 
5
6
3
2
,

 
 
2
1
9
,

 
 
6
,

 
 
2
,

 
 
5
0
,

 
 
1
7
1
,

 
 
2
0
,

 
 
6
2
6
0
,

 
 
1
5
9
9
,

 
 
1
5
,

 
 
3
0
,

 
 
1
4
0
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
4
,

 
 
2
4
9
,

 
 
2
1
,

 
 
5
5
,

 
 
3
,

 
 
3
0
,

 
 
1
4
0
,

 
 
8
4
,

 
 
3
4
,

 
 
3
6
,

 
 
3
1
,

 
 
7
4
8
,

 
 
2
6
,

 
 
9
5
8
,

 
 
3
8
,

 
 
8
,

 
 
2
4
7
,

 
 
3
5
,

 
 
1
,

 
 
7
7
5
,

 
 
2
4
5
2
,

 
 
5
,

 
 
1
4
0
,

 
 
2
6
4
,

 
 
9
3
,

 
 
2
9
0
,

 
 
2
8
1
4
,

 
 
8
6
3
,

 
 
2
4
1
2
,

 
 
2
,

 
 
1
0
7
2
,

 
 
6
,

 
 
2
,

 
 
3
9
8
,

 
 
1
2
,

 
 
4
4
,

 
 
2
1
2
,

 
 
5
,

 
 
1
2
7
,

 
 
5
0
,

 
 
7
2
5
,

 
 
2
0
,

 
 
1
0
6
,

 
 
6
,

 
 
3
6
4
,

 
 
2
,

 
 
1
4
,

 
 
1
6
,

 
 
5
5
9
,

 
 
2
,

 
 
7
2
5
,

 
 
2
1
5
,

 
 
9
,

 
 
4
3
,

 
 
1
5
7
,

 
 
7
3
,

 
 
2
0
,

 
 
6
2
6
0
,

 
 
1
5
9
9
,

 
 
5
,

 
 
2
1
6
0
5
,

 
 
1
5
1
1
,

 
 
1
3
4
6
,

 
 
2
8
7
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
7
3
7
,

 
 
8
0
,

 
 
6
,

 
 
1
9
,

 
 
1
3
1
,

 
 
4
3
0
,

 
 
6
2
6
0
,

 
 
1
5
9
9
,

 
 
2
1
,

 
 
4
4
,

 
 
1
5
1
0
1
,

 
 
1
5
,

 
 
1
,

 
 
7
9
,

 
 
2
5
,

 
 
1
7
3
,

 
 
1
2
0
,

 
 
5
0
,

 
 
4
1
2
0
,

 
 
1
3
,

 
 
5
,

 
 
7
2
5
,

 
 
2
0
,

 
 
1
0
6
,

 
 
7
9
,

 
 
1
,

 
 
2
4
5
2
,

 
 
5
7
9
,

 
 
2
,

 
 
1
7
0
5
,

 
 
1
6
4
0
8
,

 
 
6
8
1
,

 
 
5
,

 
 
9
7
,

 
 
1
8
6
,

 
 
2
0
,

 
 
1
0
6
,

 
 
1
8
,

 
 
1
2
1
5
,

 
 
1
5
0
,

 
 
2
0
,

 
 
1
5
9
9
,

 
 
9
5
]
,

 
[
5
,
 
8
3
5
,
 
1
,
 
2
4
9
,
 
2
1
,
 
3
0
7
5
,
 
1
2
4
7
,
 
1
2
4
7
,
 
1
2
4
7
,
 
1
2
4
7
]
,

 
[
1
4
1
8
,

 
 
4
2
3
,

 
 
4
0
0
,

 
 
6
4
,

 
 
2
2
9
,

 
 
1
5
9
,

 
 
4
,

 
 
2
3
5
,

 
 
8
9
5
,

 
 
5
,

 
 
8
,

 
 
2
9
2
2
,

 
 
3
5
,

 
 
6
8
,

 
 
2
7
0
3
,

 
 
2
,

 
 
6
6
1
,

 
 
2
7
,

 
 
4
1
8
,

 
 
3
6
,

 
 
3
8
,

 
 
1
0
0
,

 
 
5
2
,

 
 
3
4
,

 
 
5
2
6
,

 
 
1
2
,

 
 
1
,

 
 
6
5
5
6
,

 
 
2
2
2
,

 
 
2
,

 
 
8
8
1
,

 
 
2
,

 
 
6
0
,

 
 
4
1
8
,

 
 
1
5
,

 
 
2
8
,

 
 
1
0
1
,

 
 
1
5
3
4
,

 
 
6
9
8
8
0
,

 
 
4
5
5
,

 
 
2
2
,

 
 
7
2
,

 
 
1
8
8
,

 
 
3
7
1
8
,

 
 
1
6
,

 
 
4
6
2
,

 
 
4
0
2
,

 
 
5
0
5
,

 
 
5
7
,

 
 
5
,

 
 
1
2
,

 
 
3
1
3
,

 
 
2
0
1
,

 
 
6
5
2
,

 
 
4
1
5
,

 
 
3
0
,

 
 
5
3
7
,

 
 
6
0
,

 
 
1
6
4
0
,

 
 
2
4
,

 
 
4
9
1
,

 
 
3
3
,

 
 
2
8
,

 
 
1
2
,

 
 
1
7
2
,

 
 
1
2
8
1
,

 
 
5
,

 
 
7
,

 
 
2
3
9
,

 
 
6
3
,

 
 
1
,

 
 
3
2
9
8
,

 
 
3
6
,

 
 
7
,

 
 
1
2
4
5
,

 
 
2
7
7
1
2
,

 
 
3
6
,

 
 
7
,

 
 
6
5
1
,

 
 
1
7
0
8
,

 
 
1
0
,

 
 
2
,

 
 
3
0
,

 
 
1
7
0
,

 
 
2
0
8
9
,

 
 
7
,

 
 
6
6
,

 
 
1
2
4
5
,

 
 
1
2
1
,

 
 
4
5
4
,

 
 
7
4
,

 
 
1
5
5
5
,

 
 
1
1
,

 
 
8
,

 
 
9
,

 
 
6
,

 
 
3
6
,

 
 
1
7
3
3
,

 
 
6
5
8
,

 
 
3
0
,

 
 
4
2
4
6
,

 
 
3
4
,

 
 
6
,

 
 
4
9
,

 
 
2
8
5
1
,

 
 
9
2
,

 
 
3
3
,

 
 
2
0
,

 
 
1
0
0
5
,

 
 
2
0
6
4
,

 
 
1
2
,

 
 
2
7
,

 
 
1
3
5
1
,

 
 
5
0
,

 
 
3
7
3
,

 
 
3
7
,

 
 
6
,

 
 
2
3
9
,

 
 
2
5
8
1
,

 
 
1
3
,

 
 
2
9
,

 
 
6
,

 
 
9
0
,

 
 
2
3
9
,

 
 
6
,

 
 
4
0
,

 
 
1
0
,

 
 
4
0
,

 
 
5
8
0
,

 
 
3
9
,

 
 
1
6
,

 
 
1
3
0
9
0
,

 
 
7
3
,

 
 
2
1
,

 
 
4
,

 
 
7
5
0
,

 
 
3
5
8
]
,

 
[
1
0
5
1
0
,
 
8
,
 
1
2
5
6
,
 
1
0
5
1
0
,
 
8
,
 
1
1
1
,
 
4
,
 
1
2
5
6
,
 
1
7
4
6
6
,
 
5
,
 
2
8
0
5
,
 
9
1
,
 
5
7
3
,
 
6
1
3
]
,

 
[
1
7
1
8
4
,
 
1
4
,
 
4
2
7
8
,
 
1
6
4
4
]
,

 
[
8
3
6
8
6
,

 
 
1
,

 
 
1
0
9
,

 
 
1
1
5
7
3
,

 
 
3
1
,

 
 
8
3
6
8
6
,

 
 
4
,

 
 
2
4
4
8
4
,

 
 
3
5
3
,

 
 
1
2
,

 
 
2
5
0
,

 
 
3
2
1
9
7
,

 
 
1
0
6
6
7
4
,

 
 
1
2
0
,

 
 
3
,

 
 
1
7
5
,

 
 
7
4
8
,

 
 
3
5
,

 
 
1
3
,

 
 
6
6
8
0
,

 
 
8
,

 
 
1
4
4
,

 
 
1
,

 
 
1
5
3
7
,

 
 
1
0
5
0
,

 
 
1
0
6
6
7
5
,

 
 
1
6
9
0
5
,

 
 
3
8
8
5
,

 
 
1
0
5
6
,

 
 
2
7
6
2
,

 
 
8
9
,

 
 
1
2
2
8
7
,

 
 
3
3
,

 
 
6
8
0
,

 
 
9
3
0
8
,

 
 
3
0
5
0
,

 
 
3
,

 
 
1
0
4
3
4
,

 
 
1
1
4
8
1
,

 
 
1
,

 
 
1
2
7
3
4
,

 
 
1
1
5
9
,

 
 
3
2
9
,

 
 
7
0
4
1
,

 
 
5
,

 
 
1
6
0
9
6
2
,

 
 
1
2
5
,

 
 
1
0
5
0
,

 
 
1
6
0
9
6
3
,

 
 
8
,

 
 
9
1
,

 
 
1
5
3
4
,

 
 
3
2
,

 
 
4
,

 
 
2
5
9
6
5
,

 
 
1
9
4
3
4
,

 
 
1
5
,

 
 
4
,

 
 
1
0
9
7
,

 
 
6
8
0
,

 
 
9
3
0
8
,

 
 
3
0
5
0
,

 
 
3
,

 
 
1
0
4
3
4
,

 
 
2
6
5
,

 
 
3
3
7
,

 
 
3
2
,

 
 
1
6
0
9
6
4
,

 
 
1
9
1
0
,

 
 
5
0
1
,

 
 
3
5
4
1
2
,

 
 
1
0
6
6
7
4
,

 
 
1
9
,

 
 
5
7
,

 
 
6
9
3
,

 
 
1
0
,

 
 
1
5
3
7
,

 
 
2
6
9
2
,

 
 
6
0
8
2
4
,

 
 
1
,

 
 
1
1
4
,

 
 
2
4
7
1
,

 
 
1
0
,

 
 
2
6
9
2
,

 
 
5
1
,

 
 
8
6
,

 
 
6
6
,

 
 
6
9
3
,

 
 
1
0
,

 
 
1
3
9
1
9
,

 
 
1
4
4
,

 
 
1
,

 
 
2
8
6
7
3
,

 
 
2
4
8
2
,

 
 
2
5
,

 
 
1
,

 
 
7
8
2
,

 
 
1
1
2
8
9
,

 
 
6
2
0
6
]
,

 
[
7
,

 
 
8
8
9
,

 
 
2
0
,

 
 
2
0
6
,

 
 
1
0
,

 
 
1
,

 
 
2
4
5
4
,

 
 
1
0
,

 
 
5
4
,

 
 
1
1
,

 
 
8
,

 
 
2
7
7
5
,

 
 
3
1
5
4
,

 
 
1
7
0
8
,

 
 
5
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
5
5
2
,

 
 
2
,

 
 
1
3
6
,

 
 
1
,

 
 
3
7
4
,

 
 
2
7
0
,

 
 
1
1
,

 
 
2
4
,

 
 
1
8
3
,

 
 
2
9
2
,

 
 
6
2
,

 
 
4
8
8
8
,

 
 
2
,

 
 
4
2
5
4
,

 
 
1
6
4
0
9
,

 
 
1
6
0
8
,

 
 
3
1
,

 
 
9
,

 
 
3
,

 
 
4
2
3
1
,

 
 
3
0
,

 
 
1
4
5
,

 
 
2
4
,

 
 
9
,

 
 
9
6
,

 
 
2
2
,

 
 
4
7
,

 
 
9
0
4
7
,

 
 
1
1
1
,

 
 
4
,

 
 
2
6
2
2
,

 
 
2
8
1
,

 
 
4
2
3
1
,

 
 
1
9
,

 
 
2
9
9
1
,

 
 
1
9
0
6
8
,

 
 
6
3
2
,

 
 
8
3
4
6
,

 
 
1
0
,

 
 
8
1
3
,

 
 
7
,

 
 
1
0
3
,

 
 
1
9
,

 
 
1
6
5
3
,

 
 
2
,

 
 
1
,

 
 
1
8
3
9
0
,

 
 
3
1
0
2
,

 
 
1
7
,

 
 
4
,

 
 
5
7
4
,

 
 
1
5
,

 
 
1
4
5
,

 
 
3
1
1
,

 
 
3
,

 
 
4
,

 
 
6
9
8
8
1
,

 
 
9
,

 
 
5
9
4
8
,

 
 
1
7
5
,

 
 
1
6
9
6
,

 
 
1
0
9
3
,

 
 
9
2
5
,

 
 
1
,

 
 
4
6
2
,

 
 
2
1
0
,

 
 
9
9
3
9
,

 
 
9
7
0
0
,

 
 
5
,

 
 
9
9
3
9
,

 
 
4
2
8
,

 
 
4
2
3
1
,

 
 
9
9
,

 
 
2
5
,

 
 
1
9
,

 
 
1
4
3
7
4
,

 
 
3
2
,

 
 
5
5
,

 
 
1
2
2
5
,

 
 
6
6
0
]
,

 
[
4
4
,

 
 
7
,

 
 
4
7
6
,

 
 
2
6
3
,

 
 
3
0
,

 
 
4
8
7
,

 
 
4
5
,

 
 
1
6
,

 
 
3
5
8
,

 
 
7
3
,

 
 
1
4
4
,

 
 
6
,

 
 
1
8
,

 
 
1
0
,

 
 
1
1
1
,

 
 
4
,

 
 
7
7
1
1
,

 
 
2
,

 
 
7
9
,

 
 
1
,

 
 
2
9
,

 
 
7
8
,

 
 
4
7
6
,

 
 
6
,

 
 
8
8
2
,

 
 
1
,

 
 
4
8
7
,

 
 
9
,

 
 
1
9
,

 
 
6
,

 
 
1
9
,

 
 
7
7
5
,

 
 
2
1
,

 
 
4
,

 
 
2
1
5
4
,

 
 
1
6
9
]
,

 
[
7
,

 
 
3
3
2
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
8
6
,

 
 
1
9
6
,

 
 
1
7
,

 
 
2
5
0
,

 
 
1
7
,

 
 
6
,

 
 
3
9
8
,

 
 
8
8
,

 
 
2
2
5
,

 
 
5
,

 
 
7
,

 
 
3
3
2
,

 
 
3
7
6
8
,

 
 
1
7
5
2
,

 
 
8
8
,

 
 
2
4
,

 
 
2
5
3
2
,

 
 
1
2
,

 
 
2
7
,

 
 
5
7
7
1
,

 
 
2
1
3
,

 
 
1
0
3
,

 
 
1
7
5
,

 
 
5
3
4
2
,

 
 
2
4
3
0
,

 
 
4
1
8
,

 
 
1
9
,

 
 
6
9
8
8
2
,

 
 
3
7
,

 
 
7
,

 
 
1
9
,

 
 
4
6
3
1
,

 
 
4
9
,

 
 
1
0
,

 
 
8
5
]
,

 
[
3
8
1
3
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
7
9
,

 
 
5
6
7
,

 
 
1
3
,

 
 
1
9
3
,

 
 
1
,

 
 
4
4
2
,

 
 
3
9
7
2
1
,

 
 
1
1
6
,

 
 
4
5
,

 
 
6
9
8
4
,

 
 
1
2
7
,

 
 
4
0
8
,

 
 
7
,

 
 
8
1
,

 
 
5
5
9
,

 
 
2
,

 
 
3
4
5
,

 
 
1
5
,

 
 
1
,

 
 
2
3
,

 
 
4
6
,

 
 
2
9
,

 
 
1
3
,

 
 
1
4
9
0
,

 
 
6
,

 
 
5
6
8
7
,

 
 
9
9
,

 
 
6
,

 
 
1
4
,

 
 
1
8
8
,

 
 
3
7
,

 
 
7
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
5
5
9
,

 
 
2
,

 
 
2
0
2
,

 
 
3
0
,

 
 
2
3
3
8
,

 
 
4
1
,

 
 
1
3
,

 
 
4
5
,

 
 
6
9
8
4
,

 
 
2
3
2
1
,

 
 
3
6
,

 
 
6
,

 
 
3
9
,

 
 
2
0
4
,

 
 
2
1
,

 
 
1
1
,

 
 
3
8
8
,

 
 
8
4
,

 
 
6
9
,

 
 
5
6
8
7
,

 
 
4
6
1
4
,

 
 
1
8
8
,

 
 
3
7
,

 
 
7
,

 
 
4
3
1
,

 
 
1
5
6
7
,

 
 
3
0
,

 
 
4
5
2
6
,

 
 
1
5
,

 
 
4
,

 
 
7
2
0
,

 
 
2
3
,

 
 
4
6
,

 
 
2
9
,

 
 
1
5
6
5
,

 
 
7
,

 
 
4
5
,

 
 
1
5
6
7
,

 
 
1
,

 
 
7
2
7
,

 
 
2
9
,

 
 
8
9
8
7
,

 
 
1
,

 
 
2
8
3
5
,

 
 
8
4
3
,

 
 
6
4
,

 
 
4
1
3
,

 
 
1
1
0
0
,

 
 
7
2
8
,

 
 
1
8
4
9
,

 
 
1
3
,

 
 
2
3
,

 
 
2
8
5
,

 
 
9
1
,

 
 
3
1
6
,

 
 
5
6
1
,

 
 
1
5
9
0
6
,

 
 
6
9
,

 
 
7
1
,

 
 
4
2
,

 
 
4
,

 
 
2
6
0
,

 
 
1
1
8
5
7
,

 
 
3
,

 
 
2
1
6
8
,

 
 
6
9
1
7
,

 
 
1
0
,

 
 
1
1
,

 
 
6
,

 
 
7
0
,

 
 
1
7
,

 
 
1
6
8
2
,

 
 
2
,

 
 
9
1
,

 
 
4
,

 
 
7
2
6
,

 
 
3
,

 
 
4
7
8
7
,

 
 
1
3
4
4
,

 
 
9
1
,

 
 
2
1
3
0
,

 
 
1
9
2
,

 
 
1
7
,

 
 
3
0
2
,

 
 
5
,

 
 
2
8
4
7
,

 
 
1
3
,

 
 
7
2
7
,

 
 
2
3
,

 
 
8
,

 
 
5
1
0
,

 
 
3
,

 
 
5
4
9
4
,

 
 
8
4
1
,

 
 
1
3
4
4
,

 
 
1
1
,

 
 
8
,

 
 
1
0
1
,

 
 
2
4
1
5
,

 
 
1
,

 
 
2
2
1
2
1
,

 
 
2
5
1
6
6
,

 
 
8
6
,

 
 
6
7
8
0
,

 
 
1
2
,

 
 
1
2
6
1
7
,

 
 
9
,

 
 
8
,

 
 
3
8
,

 
 
1
8
0
7
7
,

 
 
8
8
,

 
 
1
,

 
 
6
9
6
,

 
 
7
5
1
7
,

 
 
9
,

 
 
5
1
,

 
 
1
0
8
1
2
,

 
 
1
2
6
1
7
,

 
 
1
,

 
 
1
6
0
9
6
5
,

 
 
5
,

 
 
6
1
,

 
 
4
1
3
5
,

 
 
1
,

 
 
1
8
0
6
,

 
 
3
7
1
9
,

 
 
2
4
8
,

 
 
8
6
,

 
 
4
1
8
8
,

 
 
4
4
2
6
,

 
 
6
2
,

 
 
8
6
,

 
 
2
6
7
7
4
,

 
 
8
8
,

 
 
3
1
,

 
 
1
,

 
 
4
2
6
,

 
 
2
6
,

 
 
1
,

 
 
2
5
1
6
6
,

 
 
2
1
6
7
,

 
 
4
,

 
 
1
7
4
6
,

 
 
4
6
5
1
,

 
 
8
4
,

 
 
3
3
1
7
,

 
 
1
1
,

 
 
3
2
,

 
 
1
9
8
3
4
,

 
 
1
,

 
 
3
5
2
3
,

 
 
1
3
,

 
 
2
3
,

 
 
1
5
7
6
,

 
 
1
0
1
7
0
,

 
 
1
2
8
,

 
 
8
4
1
,

 
 
1
3
4
4
,

 
 
9
,

 
 
1
1
0
2
,

 
 
6
5
,

 
 
5
1
,

 
 
8
6
,

 
 
6
7
8
0
,

 
 
1
2
,

 
 
4
4
,

 
 
2
1
2
,

 
 
5
4
,

 
 
4
4
,

 
 
8
9
3
,

 
 
8
,

 
 
9
2
,

 
 
3
8
8
2
,

 
 
6
4
,

 
 
8
,

 
 
4
,

 
 
2
8
4
,

 
 
3
1
1
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
3
,

 
 
7
1
7
,

 
 
5
7
9
,

 
 
2
,

 
 
2
3
8
4
1
,

 
 
3
1
4
2
,

 
 
2
6
1
9
,

 
 
2
7
7
1
3
,

 
 
7
8
5
5
,

 
 
6
9
8
8
3
,

 
 
3
6
,

 
 
1
7
,

 
 
1
4
,

 
 
2
,

 
 
6
9
7
9
,

 
 
1
,

 
 
3
5
1
0
,

 
 
8
2
9
,

 
 
1
5
1
,

 
 
1
,

 
 
1
4
1
8
0
,

 
 
5
2
,

 
 
9
9
,

 
 
7
0
7
,

 
 
2
1
,

 
 
1
,

 
 
2
2
1
2
1
,

 
 
6
9
8
8
4
,

 
 
5
,

 
 
1
,

 
 
2
2
1
2
1
,

 
 
3
3
7
1
3
,

 
 
2
2
8
8
,

 
 
3
9
6
,

 
 
6
5
1
,

 
 
1
,

 
 
4
4
9
1
,

 
 
5
,

 
 
9
3
6
0
,

 
 
1
,

 
 
3
5
5
2
,

 
 
6
0
4
2
,

 
 
2
,

 
 
6
9
6
,

 
 
5
,

 
 
1
,

 
 
2
6
7
7
5
,

 
 
9
9
2
,

 
 
5
,

 
 
1
0
1
4
,

 
 
2
,

 
 
4
0
3
6
,

 
 
1
7
2
1
,

 
 
2
3
8
4
1
,

 
 
2
6
7
7
6
,

 
 
3
1
,

 
 
7
6
4
1
,

 
 
6
9
8
8
5
,

 
 
9
7
5
1
,

 
 
9
,

 
 
3
1
4
2
,

 
 
9
9
,

 
 
1
0
7
8
,

 
 
1
,

 
 
6
3
1
2
,

 
 
3
,

 
 
1
,

 
 
2
5
1
6
6
,

 
 
9
6
,

 
 
1
5
0
,

 
 
9
2
,

 
 
8
1
8
0
,

 
 
1
3
,

 
 
8
3
1
,

 
 
8
,

 
 
6
0
2
7
,

 
 
4
,

 
 
2
3
8
4
1
,

 
 
4
,

 
 
4
7
8
7
,

 
 
9
9
4
,

 
 
6
2
,

 
 
8
,

 
 
1
0
2
,

 
 
8
9
9
,

 
 
7
8
,

 
 
8
,

 
 
5
2
,

 
 
9
1
,

 
 
1
3
3
,

 
 
1
7
,

 
 
4
,

 
 
5
8
2
,

 
 
1
0
,

 
 
2
7
,

 
 
2
1
6
8
,

 
 
2
3
,

 
 
5
,

 
 
3
9
9
,

 
 
5
8
,

 
 
7
8
,

 
 
8
,

 
 
6
8
,

 
 
5
4
9
4
,

 
 
7
7
1
2
,

 
 
8
1
9
,

 
 
2
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
7
,

 
 
2
2
,

 
 
7
1
,

 
 
4
,

 
 
1
6
6
,

 
 
4
1
,

 
 
1
8
,

 
 
8
3
,

 
 
1
2
,

 
 
2
6
2
8
,

 
 
3
,

 
 
1
5
1
2
,

 
 
1
2
5
,

 
 
1
,

 
 
7
2
1
,

 
 
5
,

 
 
2
8
7
,

 
 
3
9
,

 
 
3
5
0
,

 
 
6
1
7
,

 
 
5
1
,

 
 
1
0
8
,

 
 
2
6
,

 
 
5
1
,

 
 
5
6
,

 
 
1
9
,

 
 
4
4
,

 
 
7
4
1
,

 
 
1
0
,

 
 
1
2
9
,

 
 
2
1
6
8
,

 
 
8
3
,

 
 
6
9
,

 
 
7
,

 
 
1
0
3
2
,

 
 
7
3
,

 
 
1
,

 
 
8
4
1
,

 
 
8
3
,

 
 
5
,

 
 
7
,

 
 
6
5
8
,

 
 
5
1
,

 
 
4
7
6
,

 
 
1
0
7
2
,

 
 
9
1
5
1
,

 
 
4
1
,

 
 
6
,

 
 
1
6
9
4
,

 
 
2
0
4
,

 
 
4
,

 
 
1
6
2
1
,

 
 
1
9
0
5
,

 
 
1
5
,

 
 
1
5
4
1
,

 
 
2
3
0
1
,

 
 
1
0
8
1
2
,

 
 
3
2
,

 
 
7
2
1
,

 
 
1
7
7
,

 
 
1
1
,

 
 
1
5
9
0
7
,

 
 
7
6
7
7
,

 
 
3
6
,

 
 
1
,

 
 
1
3
9
,

 
 
7
7
6
,

 
 
2
4
5
,

 
 
1
6
,

 
 
2
0
0
6
,

 
 
2
,

 
 
2
1
6
8
,

 
 
8
3
,

 
 
2
1
6
8
,

 
 
8
3
,

 
 
2
4
5
,

 
 
1
6
,

 
 
3
9
1
,

 
 
3
1
,

 
 
1
,

 
 
2
1
6
8
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
5
,

 
 
1
,

 
 
7
2
1
,

 
 
3
9
,

 
 
3
5
0
,

 
 
9
2
,

 
 
3
0
1
9
,

 
 
1
0
,

 
 
4
8
1
,

 
 
2
6
2
8
,

 
 
3
,

 
 
1
5
1
2
,

 
 
8
3
,

 
 
2
2
,

 
 
1
4
,

 
 
7
,

 
 
4
5
,

 
 
8
7
3
,

 
 
7
9
,

 
 
1
,

 
 
8
4
1
,

 
 
8
3
,

 
 
5
,

 
 
1
9
0
8
,

 
 
8
8
,

 
 
2
1
,

 
 
3
0
,

 
 
3
9
7
3
3
,

 
 
3
5
,

 
 
9
2
,

 
 
1
7
9
,

 
 
5
,

 
 
7
,

 
 
4
5
,

 
 
1
3
6
,

 
 
4
,

 
 
2
8
1
,

 
 
8
4
1
,

 
 
4
1
8
,

 
 
2
,

 
 
2
9
7
1
3
,

 
 
1
4
8
,

 
 
1
,

 
 
2
1
6
8
,

 
 
8
3
,

 
 
9
8
,

 
 
3
0
3
,

 
 
5
0
,

 
 
1
5
6
,

 
 
1
3
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
2
,

 
 
4
0
,

 
 
3
,

 
 
1
,

 
 
1
2
4
0
,

 
 
1
2
5
,

 
 
1
2
6
1
7
,

 
 
2
5
,

 
 
2
0
1
6
,

 
 
8
,

 
 
4
4
5
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
1
5
3
,

 
 
2
2
0
,

 
 
9
,

 
 
5
3
,

 
 
1
2
2
,

 
 
2
,

 
 
3
9
2
,

 
 
1
2
6
1
7
,

 
 
4
9
8
,

 
 
6
0
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
5
,

 
 
5
3
,

 
 
3
9
,

 
 
5
6
3
,

 
 
1
1
,

 
 
1
1
,

 
 
8
,

 
 
1
1
3
3
,

 
 
1
2
,

 
 
1
7
5
,

 
 
2
3
,

 
 
2
,

 
 
1
6
,

 
 
5
1
6
,

 
 
5
,

 
 
3
9
2
,

 
 
4
0
,

 
 
8
5
6
0
,

 
 
2
6
,

 
 
1
1
,

 
 
1
0
0
,

 
 
1
6
7
5
,

 
 
9
,

 
 
7
5
,

 
 
4
8
,

 
 
2
2
5
,

 
 
1
6
7
7
,

 
 
5
3
,

 
 
1
4
2
,

 
 
3
1
,

 
 
1
3
7
2
,

 
 
1
0
6
,

 
 
1
4
,

 
 
2
4
2
,

 
 
7
7
1
2
,

 
 
4
2
2
,

 
 
3
2
,

 
 
1
0
6
6
7
6
,

 
 
5
,

 
 
4
6
4
,

 
 
2
1
,

 
 
8
8
,

 
 
1
1
7
8
,

 
 
1
0
6
6
7
6
,

 
 
7
,

 
 
1
9
,

 
 
1
5
3
,

 
 
4
6
4
,

 
 
2
1
,

 
 
2
0
,

 
 
4
2
2
,

 
 
5
8
7
4
,

 
 
6
0
8
2
5
,

 
 
5
,

 
 
2
6
7
7
7
,

 
 
2
0
8
,

 
 
7
,

 
 
6
8
5
,

 
 
9
,

 
 
6
,

 
 
5
9
,

 
 
2
8
9
,

 
 
6
,

 
 
5
4
7
0
,

 
 
1
,

 
 
2
2
6
0
,

 
 
5
3
0
,

 
 
4
,

 
 
3
3
7
,

 
 
3
1
,

 
 
4
3
3
,

 
 
6
5
4
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
2
6
3
,

 
 
2
1
,

 
 
2
0
,

 
 
1
1
2
9
,

 
 
5
8
7
4
,

 
 
6
0
8
2
5
,

 
 
8
,

 
 
2
7
,

 
 
1
3
7
2
,

 
 
2
8
5
6
,

 
 
5
,

 
 
2
3
8
,

 
 
1
7
2
,

 
 
5
9
0
,

 
 
1
8
,

 
 
1
1
9
5
,

 
 
1
8
9
,

 
 
8
,

 
 
1
4
,

 
 
1
2
7
0
,

 
 
1
,

 
 
1
0
5
9
0
,

 
 
5
3
4
,

 
 
1
8
9
,

 
 
1
8
1
,

 
 
2
4
7
3
,

 
 
1
7
,

 
 
4
,

 
 
2
7
3
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
2
6
,

 
 
2
2
,

 
 
1
8
9
,

 
 
9
0
,

 
 
1
,

 
 
1
2
5
5
,

 
 
4
3
,

 
 
1
6
,

 
 
1
2
2
8
,

 
 
1
7
,

 
 
1
2
,

 
 
2
6
7
7
7
,

 
 
7
,

 
 
1
9
,

 
 
4
6
4
,

 
 
2
1
,

 
 
1
5
4
,

 
 
1
7
,

 
 
1
0
1
,

 
 
2
6
,

 
 
2
2
,

 
 
5
3
,

 
 
2
5
6
,

 
 
1
5
4
,

 
 
3
1
,

 
 
1
,

 
 
1
9
4
6
,

 
 
1
1
6
,

 
 
5
3
,

 
 
4
3
,

 
 
1
9
,

 
 
2
,

 
 
2
5
6
,

 
 
1
5
4
,

 
 
3
1
,

 
 
1
,

 
 
2
3
,

 
 
1
5
5
,

 
 
1
0
,

 
 
5
4
,

 
 
5
2
,

 
 
3
7
1
0
,

 
 
1
7
,

 
 
4
,

 
 
2
7
3
,

 
 
1
3
,

 
 
8
,

 
 
5
9
6
,

 
 
2
,

 
 
1
,

 
 
7
9
7
5
,

 
 
3
,

 
 
1
0
7
,

 
 
7
3
6
0
,

 
 
9
6
4
0
,

 
 
5
2
,

 
 
4
5
,

 
 
5
5
1
,

 
 
1
4
,

 
 
4
8
,

 
 
1
1
1
,

 
 
4
,

 
 
1
1
2
9
,

 
 
5
3
,

 
 
4
3
1
,

 
 
2
5
6
,

 
 
1
5
4
,

 
 
3
1
,

 
 
1
,

 
 
1
9
4
6
,

 
 
1
1
6
,

 
 
2
0
8
,

 
 
1
1
2
9
0
,

 
 
1
5
4
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
2
0
8
,

 
 
2
0
,

 
 
1
1
4
,

 
 
4
0
7
,

 
 
2
4
,

 
 
9
9
9
8
,

 
 
1
5
4
8
6
,

 
 
1
1
,

 
 
8
,

 
 
2
,

 
 
1
6
,

 
 
1
2
2
8
,

 
 
9
,

 
 
1
,

 
 
1
1
5
,

 
 
4
7
,

 
 
2
1
0
9
8
,

 
 
9
,

 
 
3
3
5
,

 
 
3
2
,

 
 
1
0
6
6
7
7
,

 
 
1
6
9
0
6
,

 
 
1
,

 
 
2
3
,

 
 
8
9
,

 
 
2
8
6
,

 
 
9
,

 
 
1
,

 
 
4
2
3
9
5
,

 
 
8
6
,

 
 
1
4
,

 
 
1
0
8
7
,

 
 
1
2
,

 
 
1
1
8
4
,

 
 
6
5
2
,

 
 
9
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
6
6
,

 
 
1
4
4
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
9
8
,

 
 
1
9
8
,

 
 
9
,

 
 
1
,

 
 
4
4
2
,

 
 
8
0
1
,

 
 
2
4
,

 
 
1
8
8
4
,

 
 
3
2
,

 
 
1
1
8
4
,

 
 
2
2
0
6
,

 
 
6
6
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
1
0
8
,

 
 
2
,

 
 
1
9
0
4
,

 
 
2
1
8
,

 
 
9
,

 
 
1
9
,

 
 
2
3
7
,

 
 
5
7
,

 
 
1
6
7
,

 
 
1
0
,

 
 
1
,

 
 
1
4
9
8
,

 
 
3
,

 
 
1
,

 
 
8
4
7
3
,

 
 
5
,

 
 
1
1
5
7
4
,

 
 
2
6
5
,

 
 
6
0
8
,

 
 
1
,

 
 
4
0
3
,

 
 
3
5
,

 
 
2
2
9
3
,

 
 
7
6
3
,

 
 
1
0
,

 
 
1
,

 
 
9
7
0
1
,

 
 
6
6
,

 
 
5
0
,

 
 
5
5
5
6
,

 
 
3
2
,

 
 
1
,

 
 
4
7
,

 
 
2
3
2
6
,

 
 
8
0
1
,

 
 
5
3
,

 
 
3
7
1
9
,

 
 
5
5
2
,

 
 
5
,

 
 
2
5
0
,

 
 
3
5
,

 
 
4
0
9
,

 
 
4
8
,

 
 
3
1
0
2
,

 
 
5
,

 
 
7
0
4
0
,

 
 
5
,

 
 
1
0
5
4
,

 
 
5
6
,

 
 
7
5
4
,

 
 
5
6
5
,

 
 
1
8
0
6
2
,

 
 
1
,

 
 
5
2
3
,

 
 
1
3
3
9
,

 
 
2
2
8
,

 
 
8
,

 
 
2
7
0
6
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
2
8
3
]
,

 
[
4
6
3
,

 
 
3
2
3
0
,

 
 
2
,

 
 
1
6
,

 
 
1
7
1
0
,

 
 
7
,

 
 
1
2
6
,

 
 
4
8
,

 
 
1
,

 
 
6
9
3
,

 
 
6
4
1
,

 
 
3
6
,

 
 
7
,

 
 
5
9
,

 
 
1
9
,

 
 
5
5
,

 
 
2
6
7
,

 
 
2
1
,

 
 
1
,

 
 
6
9
3
,

 
 
4
7
]
,

 
[
3
2
0
,

 
 
1
0
2
4
,

 
 
8
6
4
,

 
 
7
1
4
,

 
 
6
,

 
 
2
4
6
,

 
 
1
9
1
1
,

 
 
8
3
,

 
 
2
0
8
,

 
 
3
1
0
,

 
 
1
5
6
8
,

 
 
7
9
,

 
 
1
8
1
8
,

 
 
5
0
,

 
 
1
7
1
,

 
 
2
9
8
,

 
 
1
3
,

 
 
1
1
,

 
 
1
8
1
,

 
 
1
2
1
,

 
 
1
9
9
2
,

 
 
2
7
,

 
 
3
8
4
,

 
 
5
,

 
 
1
4
3
7
7
,

 
 
6
1
,

 
 
1
9
2
6
,

 
 
8
5
,

 
 
1
4
4
,

 
 
6
,

 
 
1
5
1
0
,

 
 
5
,

 
 
9
8
7
2
,

 
 
2
5
6
,

 
 
9
8
9
,

 
 
3
1
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
7
4
,

 
 
1
3
0
,

 
 
1
4
0
7
,

 
 
6
,

 
 
1
9
,

 
 
2
3
7
,

 
 
1
3
7
5
,

 
 
7
,

 
 
4
5
,

 
 
7
7
2
,

 
 
4
1
1
,

 
 
1
3
,

 
 
2
,

 
 
1
6
,

 
 
2
0
,

 
 
7
8
2
,

 
 
5
8
7
,

 
 
5
,

 
 
5
7
6
,

 
 
6
,

 
 
4
9
0
,

 
 
8
5
,

 
 
6
,

 
 
6
7
1
,

 
 
2
7
,

 
 
2
3
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
1
1
1
6
,

 
 
4
6
]
,

 
[
7
,

 
 
6
5
,

 
 
1
1
,

 
 
3
7
4
4
,

 
 
1
5
,

 
 
1
,

 
 
2
9
9
4
,

 
 
2
2
,

 
 
1
5
8
,

 
 
1
8
5
0
,

 
 
4
,

 
 
2
6
2
9
,

 
 
5
1
4
2
,

 
 
3
3
,

 
 
4
,

 
 
4
0
9
5
,

 
 
1
,

 
 
8
7
4
3
,

 
 
9
5
2
0
,

 
 
4
3
,

 
 
1
6
,

 
 
4
8
1
,

 
 
2
6
4
,

 
 
9
3
,

 
 
4
5
5
7
6
,

 
 
1
5
6
7
,

 
 
1
,

 
 
8
3
6
8
7
]
,

 
[
5
7
2
,

 
 
3
3
,

 
 
1
1
,

 
 
1
2
7
,

 
 
5
2
,

 
 
1
9
5
,

 
 
1
9
0
6
9
,

 
 
1
5
,

 
 
3
1
0
,

 
 
2
5
9
7
,

 
 
9
0
4
8
,

 
 
1
5
,

 
 
7
4
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
2
8
5
,

 
 
4
,

 
 
1
5
4
8
,

 
 
4
9
,

 
 
3
6
,

 
 
5
2
,

 
 
3
9
,

 
 
9
7
,

 
 
4
,

 
 
1
2
1
9
,

 
 
3
3
,

 
 
3
7
,

 
 
1
7
6
,

 
 
4
7
4
,

 
 
2
8
,

 
 
4
0
6
,

 
 
8
1
5
,

 
 
1
2
9
9
,

 
 
1
3
6
4
,

 
 
3
3
8
,

 
 
4
6
,

 
 
1
6
0
9
6
6
,

 
 
6
3
9
0
,

 
 
1
4
2
1
,

 
 
1
6
0
9
6
7
,

 
 
2
5
5
9
,

 
 
1
6
0
9
6
8
,

 
 
5
2
,

 
 
1
8
2
8
,

 
 
7
3
7
,

 
 
3
0
,

 
 
1
1
2
9
,

 
 
3
,

 
 
1
1
]
,

 
[
3
6
,

 
 
7
,

 
 
6
5
0
,

 
 
2
0
,

 
 
7
3
3
,

 
 
3
,

 
 
1
1
3
,

 
 
2
9
1
8
,

 
 
1
6
6
5
4
,

 
 
8
,

 
 
1
5
3
,

 
 
2
0
7
9
,

 
 
4
0
8
,

 
 
1
2
7
,

 
 
6
,

 
 
1
9
,

 
 
1
4
3
3
,

 
 
2
,

 
 
5
2
0
,

 
 
7
8
,

 
 
4
,

 
 
2
9
,

 
 
1
6
0
9
6
9
,

 
 
1
4
6
,

 
 
1
8
2
,

 
 
1
1
3
,

 
 
2
9
1
8
,

 
 
1
6
6
5
4
,

 
 
5
,

 
 
8
4
,

 
 
3
9
9
0
,

 
 
1
,

 
 
2
1
0
9
9
,

 
 
2
1
,

 
 
4
,

 
 
2
1
3
,

 
 
1
0
6
3
,

 
 
6
4
1
,

 
 
1
4
1
7
,

 
 
1
0
6
3
,

 
 
6
4
1
]
,

 
[
3
6
,
 
9
,
 
1
,
 
2
2
6
4
5
,
 
5
4
0
,
 
1
0
0
4
3
,
 
5
4
3
8
,
 
3
2
4
1
]
,

 
[
6
2
0
7
,

 
 
2
7
7
1
4
,

 
 
4
9
,

 
 
6
9
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
5
6
2
,

 
 
1
0
,

 
 
6
2
0
7
,

 
 
2
7
7
1
4
,

 
 
2
5
,

 
 
9
2
,

 
 
1
4
0
5
7
,

 
 
1
8
1
,

 
 
2
7
6
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
1
4
,

 
 
3
4
2
,

 
 
5
,

 
 
5
0
,

 
 
5
9
,

 
 
1
1
8
,

 
 
2
6
8
,

 
 
2
,

 
 
3
5
6
,

 
 
5
3
6
,

 
 
8
0
,

 
 
6
,

 
 
1
8
,

 
 
1
6
7
2
,

 
 
3
5
,

 
 
1
,

 
 
4
4
7
,

 
 
6
,

 
 
1
8
,

 
 
1
9
5
5
,

 
 
2
1
,

 
 
7
,

 
 
1
0
3
8
,

 
 
2
,

 
 
6
5
,

 
 
4
1
,

 
 
1
8
,

 
 
4
7
8
1
,

 
 
3
,

 
 
8
3
,

 
 
1
5
,

 
 
6
4
,

 
 
9
,

 
 
3
4
,

 
 
1
4
,

 
 
1
0
9
2
,

 
 
5
0
8
,

 
 
1
1
2
8
,

 
 
5
,

 
 
9
,

 
 
3
4
,

 
 
1
4
,

 
 
1
9
,

 
 
1
1
1
4
,

 
 
2
7
7
4
,

 
 
1
0
0
6
,

 
 
1
4
1
,

 
 
3
5
,

 
 
3
8
9
8
,

 
 
3
2
1
,

 
 
2
6
,

 
 
7
,

 
 
8
1
,

 
 
3
4
1
4
,

 
 
3
0
5
,

 
 
2
,

 
 
7
0
,

 
 
9
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
1
6
4
1
,

 
 
2
7
5
,

 
 
9
2
,

 
 
1
8
6
9
,

 
 
5
,

 
 
3
6
,

 
 
7
,

 
 
3
1
7
,

 
 
1
1
,

 
 
7
5
7
,

 
 
4
,

 
 
1
2
8
,

 
 
5
8
,

 
 
1
3
4
6
8
,

 
 
6
2
5
2
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
2
,

 
 
1
0
1
8
,

 
 
2
0
,

 
 
4
6
4
,

 
 
2
,

 
 
1
,

 
 
4
8
1
,

 
 
6
4
5
,

 
 
6
4
5
,

 
 
6
2
0
7
,

 
 
2
7
7
1
4
,

 
 
5
,

 
 
2
,

 
 
4
5
9
,

 
 
4
5
5
7
7
,

 
 
1
1
0
0
,

 
 
4
1
,

 
 
1
0
,

 
 
1
,

 
 
1
1
4
,

 
 
1
3
8
6
,

 
 
4
7
,

 
 
3
1
1
,

 
 
1
,

 
 
1
1
7
5
4
,

 
 
8
2
,

 
 
3
,

 
 
1
,

 
 
3
5
3
,

 
 
1
7
6
3
,

 
 
2
,

 
 
1
2
2
6
,

 
 
8
8
,

 
 
1
7
,

 
 
4
2
,

 
 
5
7
,

 
 
1
3
3
,

 
 
3
2
,

 
 
2
2
5
,

 
 
5
,

 
 
4
7
,

 
 
6
1
,

 
 
2
9
2
,

 
 
8
,

 
 
2
1
0
,

 
 
9
7
4
,

 
 
5
,

 
 
1
5
3
0
,

 
 
1
3
0
9
1
]
,

 
[
1
5
,

 
 
6
2
3
4
,

 
 
1
0
1
7
,

 
 
1
0
6
6
7
8
,

 
 
7
5
6
9
,

 
 
2
1
,

 
 
6
4
7
,

 
 
2
,

 
 
1
,

 
 
1
4
0
,

 
 
1
4
8
,

 
 
1
,

 
 
6
2
9
,

 
 
3
0
3
,

 
 
7
,

 
 
6
5
,

 
 
9
,

 
 
2
0
8
,

 
 
6
2
3
4
,

 
 
1
0
1
7
,

 
 
1
0
6
6
7
8
,

 
 
7
5
6
9
,

 
 
1
8
,

 
 
1
7
7
7
6
,

 
 
5
1
1
,

 
 
1
,

 
 
9
8
0
,

 
 
3
,

 
 
1
,

 
 
2
5
3
,

 
 
1
7
,

 
 
5
1
,

 
 
1
8
,

 
 
6
6
8
,

 
 
1
4
3
,

 
 
8
9
,

 
 
8
,

 
 
2
,

 
 
9
8
4
,

 
 
9
,

 
 
6
2
3
4
,

 
 
1
0
1
7
,

 
 
1
0
6
6
7
9
,

 
 
8
,

 
 
1
4
,

 
 
3
7
0
1
,

 
 
2
,

 
 
3
7
9
,

 
 
1
,

 
 
1
7
1
8
5
,

 
 
5
7
6
,

 
 
1
3
,

 
 
7
,

 
 
6
5
,

 
 
2
8
4
1
,

 
 
6
8
1
,

 
 
2
2
,

 
 
1
,

 
 
7
5
6
9
,

 
 
1
8
,

 
 
2
,

 
 
1
6
,

 
 
5
0
2
,

 
 
5
1
,

 
 
5
6
,

 
 
2
6
9
,

 
 
1
8
2
,

 
 
1
,

 
 
8
9
5
,

 
 
5
,

 
 
1
2
5
5
,

 
 
1
1
6
,

 
 
1
8
2
4
,

 
 
3
2
,

 
 
2
1
3
9
,

 
 
1
1
,

 
 
8
,

 
 
9
,

 
 
1
6
7
0
,

 
 
6
2
3
4
,

 
 
1
0
1
7
,

 
 
1
0
6
6
7
9
,

 
 
3
,

 
 
1
4
,

 
 
9
1
,

 
 
3
7
0
1
,

 
 
2
,

 
 
3
7
9
,

 
 
1
,

 
 
1
7
1
8
5
,

 
 
5
7
6
,

 
 
8
,

 
 
6
9
5
,

 
 
2
2
,

 
 
1
1
0
4
,

 
 
1
3
1
,

 
 
1
,

 
 
1
4
7
2
,

 
 
8
4
,

 
 
1
3
,

 
 
8
,

 
 
2
9
9
,

 
 
3
6
9
7
,

 
 
5
,

 
 
5
6
,

 
 
1
2
7
,

 
 
1
6
,

 
 
1
8
7
]
,

 
[
4
4
,

 
 
2
1
2
,

 
 
2
,

 
 
1
7
6
6
,

 
 
4
1
,

 
 
8
,

 
 
1
0
7
6
,

 
 
4
4
,

 
 
2
1
2
,

 
 
7
8
,

 
 
2
8
6
7
4
,

 
 
7
2
6
5
,

 
 
2
3
1
8
3
,

 
 
5
6
,

 
 
1
6
,

 
 
1
7
6
6
,

 
 
3
1
,

 
 
2
8
6
7
4
,

 
 
7
2
6
5
,

 
 
9
,

 
 
1
6
1
,

 
 
8
,

 
 
4
,

 
 
1
3
3
2
,

 
 
9
,

 
 
8
,

 
 
7
7
,

 
 
1
0
6
6
8
0
,

 
 
2
5
0
,

 
 
1
,

 
 
4
3
2
,

 
 
2
3
,

 
 
8
,

 
 
1
6
0
9
7
0
,

 
 
2
5
0
,

 
 
1
2
8
,

 
 
3
,

 
 
5
4
,

 
 
8
,

 
 
3
0
3
2
,

 
 
5
,

 
 
1
1
0
7
,

 
 
1
0
1
,

 
 
5
5
6
,

 
 
1
,

 
 
3
5
1
9
,

 
 
3
,

 
 
1
1
3
,

 
 
9
6
2
,

 
 
4
,

 
 
5
2
8
,

 
 
2
3
,

 
 
8
,

 
 
7
7
,

 
 
1
6
0
9
7
1
,

 
 
2
5
0
,

 
 
5
4
,

 
 
8
,

 
 
3
4
6
6
,

 
 
3
6
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
2
1
2
,

 
 
7
8
,

 
 
1
,

 
 
2
3
,

 
 
5
6
,

 
 
1
6
,

 
 
1
7
6
6
,

 
 
4
6
]
,

 
[
5
0
,
 
5
1
7
,
 
2
0
,
 
2
3
4
,
 
9
5
]
,

 
[
3
9
7
3
4
,

 
 
6
1
5
7
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
3
,

 
 
5
5
3
,

 
 
1
3
,

 
 
1
6
0
9
7
2
,

 
 
9
1
0
4
,

 
 
2
3
6
2
,

 
 
6
7
5
2
,

 
 
8
,

 
 
9
8
3
,

 
 
7
3
,

 
 
5
,

 
 
1
7
1
8
6
,

 
 
1
6
,

 
 
3
7
8
9
,

 
 
4
7
,

 
 
3
9
7
3
4
,

 
 
6
1
5
7
,

 
 
1
9
3
,

 
 
7
,

 
 
1
8
4
,

 
 
1
6
,

 
 
1
3
3
1
,

 
 
3
9
7
3
4
,

 
 
2
4
7
,

 
 
7
,

 
 
6
3
,

 
 
1
7
2
,

 
 
2
7
6
1
,

 
 
1
5
,

 
 
1
,

 
 
1
6
1
,

 
 
7
0
4
,

 
 
6
0
4
8
,

 
 
9
1
2
,

 
 
5
0
1
2
]
,

 
[
1
0
5
1
1
,

 
 
7
5
,

 
 
1
0
,

 
 
5
2
7
1
,

 
 
6
2
2
,

 
 
4
5
2
,

 
 
1
,

 
 
9
4
1
9
,

 
 
1
1
9
6
,

 
 
5
,

 
 
2
3
6
3
,

 
 
9
4
0
,

 
 
3
,

 
 
1
,

 
 
1
0
5
1
1
,

 
 
6
2
,

 
 
3
8
7
,

 
 
1
2
,

 
 
3
2
9
,

 
 
6
2
2
,

 
 
5
,

 
 
4
5
2
,

 
 
4
4
7
7
,

 
 
3
,

 
 
3
5
4
1
3
,

 
 
4
5
2
,

 
 
9
9
7
,

 
 
7
5
,

 
 
9
,

 
 
4
2
5
,

 
 
5
6
0
0
,

 
 
5
6
9
,

 
 
1
6
2
,

 
 
5
6
9
,

 
 
5
6
9
]
,

 
[
6
7
,
 
1
9
2
,
 
6
,
 
1
2
6
3
0
,
 
3
1
6
2
]
,

 
[
1
0
,

 
 
8
1
3
,

 
 
7
,

 
 
8
1
,

 
 
9
7
0
,

 
 
9
,

 
 
6
,

 
 
5
0
,

 
 
1
7
1
,

 
 
2
3
2
7
,

 
 
3
7
,

 
 
3
,

 
 
2
1
8
,

 
 
7
,

 
 
5
1
8
2
,

 
 
2
0
7
,

 
 
7
,

 
 
3
4
,

 
 
1
4
,

 
 
3
8
,

 
 
3
8
,

 
 
9
2
7
,

 
 
2
1
6
0
6
,

 
 
8
,

 
 
5
,

 
 
7
,

 
 
6
5
,

 
 
2
0
,

 
 
7
0
3
,

 
 
1
3
,

 
 
3
5
4
,

 
 
8
7
3
,

 
 
5
,

 
 
3
0
7
3
,

 
 
2
0
,

 
 
6
6
2
]
,

 
[
1
5
1
,
 
3
1
0
,
 
1
,
 
4
0
9
4
,
 
7
,
 
1
9
,
 
2
,
 
2
5
6
,
 
1
,
 
2
7
7
]
,

 
[
1
4
1
8
,
 
7
,
 
6
5
0
,
 
2
0
,
 
4
9
,
 
4
7
,
 
3
,
 
1
4
1
,
 
7
4
2
,
 
8
4
,
 
5
3
7
,
 
9
7
4
2
,
 
4
7
,
 
4
7
7
,
 
8
4
]
,

 
[
1
1
,

 
 
4
2
,

 
 
5
7
,

 
 
7
3
,

 
 
1
5
0
,

 
 
2
6
,

 
 
6
4
,

 
 
1
1
,

 
 
8
,

 
 
1
2
7
,

 
 
5
4
5
5
,

 
 
2
9
7
1
4
,

 
 
1
4
4
5
,

 
 
1
0
,

 
 
4
,

 
 
1
8
1
7
,

 
 
1
4
5
4
,

 
 
2
1
,

 
 
2
4
7
9
,

 
 
4
2
3
9
6
,

 
 
9
,

 
 
4
0
,

 
 
1
0
6
4
9
,

 
 
2
1
1
0
0
,

 
 
6
2
,

 
 
4
2
,

 
 
3
4
9
,

 
 
1
0
8
6
,

 
 
1
3
5
,

 
 
8
3
6
,

 
 
4
2
,

 
 
5
7
,

 
 
3
3
0
,

 
 
1
,

 
 
2
7
1
6
,

 
 
6
1
3
7
,

 
 
2
0
6
6
8
,

 
 
3
3
,

 
 
5
5
8
,

 
 
9
2
6
4
,

 
 
1
7
6
,

 
 
3
1
2
,

 
 
1
6
0
5
,

 
 
2
4
3
,

 
 
9
2
3
,

 
 
8
5
2
,

 
 
1
0
6
6
8
1
,

 
 
2
2
,

 
 
1
2
8
0
,

 
 
1
4
,

 
 
1
5
6
8
,

 
 
1
3
4
4
,

 
 
7
,

 
 
6
3
0
2
,

 
 
3
8
,

 
 
8
,

 
 
6
8
,

 
 
4
2
1
,

 
 
5
6
,

 
 
1
6
,

 
 
1
8
7
,

 
 
1
7
,

 
 
4
,

 
 
1
2
0
,

 
 
1
5
8
2
,

 
 
4
8
3
2
,

 
 
8
1
6
,

 
 
5
1
4
0
]
,

 
[
1
6
0
9
7
3
,

 
 
1
6
0
9
7
4
,

 
 
1
7
8
,

 
 
2
8
6
7
5
,

 
 
1
1
4
,

 
 
1
9
2
,

 
 
3
6
7
,

 
 
4
8
,

 
 
2
,

 
 
3
7
3
,

 
 
6
,

 
 
9
,

 
 
2
0
,

 
 
4
1
4
,

 
 
1
8
,

 
 
1
5
2
9
0
,

 
 
6
,

 
 
1
8
,

 
 
3
8
4
6
,

 
 
6
3
5
,

 
 
7
3
3
0
,

 
 
1
7
1
2
,

 
 
9
9
2
9
,

 
 
1
2
,

 
 
9
,

 
 
7
,

 
 
6
3
,

 
 
6
,

 
 
1
9
,

 
 
5
1
3
,

 
 
1
,

 
 
6
9
6
4
,

 
 
2
3
,

 
 
7
,

 
 
2
3
9
,

 
 
1
9
,

 
 
1
1
,

 
 
1
5
,

 
 
3
0
,

 
 
2
5
8
1
,

 
 
3
5
1
,

 
 
3
6
,

 
 
7
,

 
 
2
3
9
,

 
 
7
0
,

 
 
4
1
,

 
 
2
4
,

 
 
4
,

 
 
1
0
9
0
,

 
 
6
,

 
 
2
4
5
,

 
 
1
5
9
,

 
 
4
5
4
,

 
 
3
,

 
 
6
0
,

 
 
4
7
5
,

 
 
1
5
,

 
 
1
1
3
,

 
 
3
6
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
1
3
,

 
 
5
0
3
,

 
 
3
6
,

 
 
6
,

 
 
7
0
,

 
 
7
4
,

 
 
2
,

 
 
2
0
1
,

 
 
1
7
9
2
,

 
 
1
,

 
 
2
4
5
2
,

 
 
6
,

 
 
1
5
2
,

 
 
2
4
8
,

 
 
3
9
0
2
,

 
 
1
1
7
5
5
,

 
 
6
6
9
]
,

 
[
7
,
 
2
3
9
,
 
2
7
3
7
,
 
5
5
,
 
1
2
8
5
0
]
,

 
[
7
,

 
 
1
5
9
,

 
 
3
4
0
6
,

 
 
7
,

 
 
1
5
9
,

 
 
2
8
4
,

 
 
3
4
0
6
,

 
 
9
,

 
 
6
0
,

 
 
7
6
7
8
,

 
 
1
9
8
3
5
,

 
 
1
3
9
2
0
,

 
 
1
5
9
5
,

 
 
9
,

 
 
4
4
,

 
 
4
7
,

 
 
5
6
,

 
 
1
6
,

 
 
8
1
9
,

 
 
2
,

 
 
2
2
3
4
,

 
 
7
2
3
0
,

 
 
1
2
,

 
 
9
9
2
,

 
 
4
8
,

 
 
1
,

 
 
8
1
1
3
,

 
 
1
6
4
0
,

 
 
1
7
,

 
 
1
,

 
 
6
6
5
,

 
 
1
0
4
7
,

 
 
5
,

 
 
8
3
6
8
8
,

 
 
3
1
6
9
,

 
 
7
3
8
5
,

 
 
9
,

 
 
5
1
,

 
 
1
8
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
3
8
,

 
 
4
4
9
,

 
 
3
,

 
 
8
6
5
5
,

 
 
6
9
8
8
6
,

 
 
6
0
8
2
6
,

 
 
1
7
0
2
,

 
 
6
,

 
 
1
8
,

 
 
2
6
8
,

 
 
2
,

 
 
3
5
4
1
4
,

 
 
1
5
,

 
 
7
5
,

 
 
2
6
,

 
 
5
9
,

 
 
3
4
,

 
 
1
1
,

 
 
6
4
,

 
 
1
3
,

 
 
3
8
4
,

 
 
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
2
0
0
,

 
 
1
7
0
1
,

 
 
5
,

 
 
4
,

 
 
2
0
0
,

 
 
3
3
1
3
,

 
 
3
,

 
 
1
0
5
,

 
 
1
4
,

 
 
4
5
4
9
,

 
 
6
1
4
,

 
 
7
1
4
8
,

 
 
5
,

 
 
1
0
6
6
8
2
,

 
 
3
3
2
,

 
 
1
1
2
1
1
,

 
 
2
3
1
,

 
 
1
5
9
,

 
 
4
,

 
 
8
1
1
3
,

 
 
1
6
4
0
,

 
 
1
4
8
,

 
 
6
,

 
 
4
2
3
9
7
]
,

 
[
2
9
7
1
5
,

 
 
1
0
7
,

 
 
2
7
7
,

 
 
1
5
8
,

 
 
5
6
,

 
 
1
8
6
1
,

 
 
4
,

 
 
2
9
7
1
5
,

 
 
1
2
4
2
,

 
 
1
0
7
,

 
 
2
7
7
,

 
 
1
2
8
,

 
 
4
8
,

 
 
1
,

 
 
4
5
1
,

 
 
4
7
,

 
 
1
2
,

 
 
1
,

 
 
6
9
8
8
7
,

 
 
1
0
,

 
 
2
9
7
,

 
 
3
,

 
 
1
6
0
6
,

 
 
8
0
0
,

 
 
1
3
9
9
,

 
 
1
6
0
,

 
 
8
5
0
,

 
 
7
1
0
,

 
 
2
1
6
]
,

 
[
1
2
3
9
7
,
 
6
0
8
,
 
1
6
0
9
7
5
,
 
4
6
,
 
1
8
9
2
,
 
1
8
7
2
,
 
9
1
2
,
 
1
0
2
6
,
 
9
6
9
]
,

 
[
6
,

 
 
1
9
4
,

 
 
1
6
8
4
,

 
 
7
,

 
 
7
0
,

 
 
1
2
5
,

 
 
6
,

 
 
5
9
7
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
5
9
8
8
,

 
 
2
0
,

 
 
8
9
6
,

 
 
1
9
2
,

 
 
8
4
,

 
 
7
,

 
 
8
1
,

 
 
2
,

 
 
1
6
5
,

 
 
2
,

 
 
2
0
9
5
,

 
 
6
,

 
 
2
,

 
 
4
,

 
 
1
8
0
7
5
,

 
 
6
,

 
 
2
6
8
5
,

 
 
6
0
8
2
7
]
,

 
[
4
6
3
,

 
 
5
7
9
4
,

 
 
1
7
5
6
,

 
 
9
5
,

 
 
1
2
,

 
 
1
3
4
6
,

 
 
3
7
,

 
 
7
,

 
 
2
4
,

 
 
7
0
3
,

 
 
1
3
,

 
 
4
,

 
 
3
5
9
,

 
 
1
1
0
,

 
 
1
5
5
,

 
 
8
5
8
,

 
 
1
9
9
1
,

 
 
1
6
,

 
 
1
7
7
4
,

 
 
1
2
,

 
 
1
3
,

 
 
8
5
,

 
 
3
0
1
,

 
 
4
6
7
6
]
,

 
[
9
,
 
1
1
0
,
 
7
,
 
1
8
4
,
 
9
6
,
 
7
0
,
 
5
4
,
 
2
3
,
 
6
,
 
1
8
,
 
6
0
9
,
 
3
5
]
,

 
[
1
,

 
 
1
8
,

 
 
6
7
8
,

 
 
2
1
,

 
 
1
,

 
 
6
9
8
8
8
,

 
 
5
0
6
,

 
 
8
8
6
,

 
 
4
1
,

 
 
1
8
,

 
 
4
4
,

 
 
2
2
0
2
,

 
 
8
1
8
1
,

 
 
7
1
4
9
,

 
 
2
,

 
 
1
1
,

 
 
1
3
,

 
 
1
1
5
,

 
 
1
1
6
,

 
 
8
,

 
 
1
9
0
6
8
,

 
 
1
9
1
,

 
 
7
3
2
5
,

 
 
1
1
,

 
 
4
3
1
,

 
 
9
9
3
,

 
 
1
1
6
7
,

 
 
1
7
,

 
 
1
1
,

 
 
1
1
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
1
7
0
3
,

 
 
8
8
6
,

 
 
9
9
0
,

 
 
6
0
9
,

 
 
3
5
,

 
 
6
,

 
 
1
2
2
,

 
 
6
0
,

 
 
2
2
0
2
,

 
 
1
0
6
1
,

 
 
2
5
2
4
,

 
 
1
4
,

 
 
1
0
5
3
,

 
 
3
,

 
 
3
7
3
5
,

 
 
1
7
,

 
 
3
1
3
,

 
 
1
7
,

 
 
7
,

 
 
7
0
,

 
 
1
,

 
 
1
6
0
9
7
6
,

 
 
5
3
6
,

 
 
4
2
,

 
 
1
1
3
1
,

 
 
2
4
1
5
,

 
 
6
7
8
,

 
 
2
1
,

 
 
6
0
,

 
 
1
9
1
3
,

 
 
1
0
6
6
8
3
,

 
 
5
,

 
 
4
5
1
1
,

 
 
3
2
1
,

 
 
4
1
,

 
 
8
,

 
 
1
4
,

 
 
9
6
,

 
 
1
,

 
 
1
4
1
2
,

 
 
3
,

 
 
2
7
,

 
 
9
0
3
,

 
 
3
3
,

 
 
5
4
3
8
0
,

 
 
3
8
,

 
 
1
9
0
3
,

 
 
1
4
6
5
,

 
 
2
5
,

 
 
8
9
8
7
,

 
 
1
3
,

 
 
1
8
4
,

 
 
1
9
,

 
 
1
5
,

 
 
1
,

 
 
8
8
6
,

 
 
2
2
,

 
 
1
6
4
,

 
 
5
5
4
,

 
 
4
1
,

 
 
1
8
,

 
 
2
5
2
4
,

 
 
3
5
,

 
 
1
,

 
 
2
3
5
4
,

 
 
3
,

 
 
7
8
5
6
,

 
 
3
1
,

 
 
1
0
3
1
,

 
 
2
5
0
2
,

 
 
1
1
6
6
1
,

 
 
2
,

 
 
1
8
7
3
9
,

 
 
1
1
6
6
1
,

 
 
8
3
6
8
9
,

 
 
5
4
3
8
1
,

 
 
1
0
,

 
 
2
0
6
9
,

 
 
3
2
1
,

 
 
3
2
1
]
,

 
[
1
0
3
,

 
 
6
,

 
 
5
0
,

 
 
2
0
6
,

 
 
1
5
,

 
 
4
6
,

 
 
3
3
2
,

 
 
5
6
6
9
,

 
 
3
5
7
,

 
 
7
6
9
,

 
 
1
0
6
6
8
4
,

 
 
5
,

 
 
1
7
4
6
7
,

 
 
2
7
6
3
,

 
 
7
2
,

 
 
6
3
8
6
,

 
 
4
9
9
,

 
 
2
6
8
,

 
 
2
,

 
 
1
3
5
1
,

 
 
1
0
5
,

 
 
9
,

 
 
7
,

 
 
2
2
0
,

 
 
2
,

 
 
1
6
,

 
 
1
0
2
,

 
 
9
7
0
2
,

 
 
1
1
,

 
 
5
2
6
,

 
 
2
,

 
 
3
7
,

 
 
4
8
,

 
 
4
3
0
,

 
 
4
1
0
,

 
 
6
2
,

 
 
4
0
7
6
,

 
 
7
6
,

 
 
3
3
,

 
 
1
4
7
3
,

 
 
2
0
1
8
,

 
 
1
8
,

 
 
6
3
0
,

 
 
8
4
0
,

 
 
2
,

 
 
2
5
6
,

 
 
1
0
1
,

 
 
7
7
5
,

 
 
8
7
0
,

 
 
1
5
,

 
 
4
4
7
,

 
 
3
4
6
,

 
 
5
4
,

 
 
6
9
7
,

 
 
1
,

 
 
2
9
7
,

 
 
3
,

 
 
9
7
1
,

 
 
3
9
4
,

 
 
1
3
5
,

 
 
3
3
2
,

 
 
5
6
6
9
,

 
 
9
8
5
,

 
 
2
3
4
,

 
 
4
3
,

 
 
1
6
,

 
 
2
7
0
0
,

 
 
1
3
4
7
,

 
 
9
5
]
,

 
[
2
0
2
2
,

 
 
3
2
0
,

 
 
7
,

 
 
8
1
,

 
 
1
0
6
6
8
5
,

 
 
5
,

 
 
7
,

 
 
1
9
,

 
 
1
4
7
2
4
,

 
 
2
,

 
 
1
5
9
,

 
 
1
5
,

 
 
2
0
,

 
 
2
0
2
2
,

 
 
1
9
8
,

 
 
5
4
7
,

 
 
1
3
,

 
 
1
3
8
,

 
 
7
,

 
 
4
5
,

 
 
1
4
2
5
,

 
 
5
1
6
,

 
 
2
1
,

 
 
2
1
0
,

 
 
1
9
5
9
,

 
 
3
,

 
 
1
3
,

 
 
6
2
7
,

 
 
5
,

 
 
4
5
,

 
 
1
1
6
6
2
,

 
 
2
,

 
 
3
4
3
6
,

 
 
2
0
,

 
 
6
7
6
,

 
 
1
5
1
,

 
 
3
5
5
,

 
 
4
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
3
8
,

 
 
2
5
5
,

 
 
1
3
,

 
 
8
,

 
 
3
8
,

 
 
7
,

 
 
1
9
,

 
 
2
9
1
,

 
 
1
6
0
9
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
3
1
0
,

 
 
1
,

 
 
4
6
5
,

 
 
5
7
9
,

 
 
2
,

 
 
6
9
8
8
9
,

 
 
1
,

 
 
1
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
9
8
7
3
,

 
 
1
5
1
0
,

 
 
3
6
6
2
,

 
 
2
,

 
 
1
2
1
,

 
 
1
7
2
,

 
 
3
1
7
,

 
 
1
,

 
 
5
4
6
,

 
 
1
7
,

 
 
5
1
,

 
 
4
4
,

 
 
8
0
6
,

 
 
2
2
7
1
,

 
 
1
7
2
,

 
 
1
7
,

 
 
4
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
3
4
9
8
,

 
 
8
3
6
9
0
,

 
 
4
2
,

 
 
5
7
,

 
 
7
3
7
,

 
 
1
3
,

 
 
1
5
7
,

 
 
2
,

 
 
1
8
9
,

 
 
1
6
0
3
,

 
 
9
,

 
 
1
,

 
 
1
6
8
,

 
 
2
8
3
,

 
 
9
8
7
3
,

 
 
1
5
1
0
,

 
 
3
6
6
2
,

 
 
2
,

 
 
1
2
1
,

 
 
1
7
2
,

 
 
3
1
7
,

 
 
1
,

 
 
5
4
6
,

 
 
8
3
6
9
0
,

 
 
3
2
0
7
,

 
 
2
,

 
 
1
6
0
9
7
8
,

 
 
4
6
5
,

 
 
1
7
,

 
 
5
2
,

 
 
1
8
9
,

 
 
1
5
9
5
,

 
 
9
,

 
 
1
,

 
 
1
2
0
,

 
 
8
,

 
 
9
7
4
,

 
 
1
7
,

 
 
1
,

 
 
8
4
7
4
,

 
 
4
3
,

 
 
1
9
,

 
 
8
1
9
,

 
 
6
9
8
8
9
,

 
 
1
3
5
,

 
 
1
,

 
 
9
8
7
3
,

 
 
5
,

 
 
1
1
4
,

 
 
7
4
1
,

 
 
1
2
3
5
,

 
 
3
1
,

 
 
6
9
8
8
9
,

 
 
3
1
0
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
2
7
0
4
,

 
 
1
7
,

 
 
4
,

 
 
2
6
1
,

 
 
1
2
0
,

 
 
2
3
8
4
2
,

 
 
3
2
0
7
,

 
 
3
5
8
,

 
 
9
,

 
 
3
5
2
,

 
 
1
0
,

 
 
1
,

 
 
7
0
3
9
,

 
 
1
9
1
,

 
 
4
4
5
1
,

 
 
1
0
3
,

 
 
1
9
,

 
 
5
7
,

 
 
8
2
1
8
,

 
 
3
2
,

 
 
1
,

 
 
1
9
1
,

 
 
5
4
3
8
2
,

 
 
6
2
0
,

 
 
3
3
,

 
 
9
,

 
 
8
5
,

 
 
5
,

 
 
3
7
5
,

 
 
1
0
,

 
 
1
,

 
 
6
2
9
,

 
 
1
,

 
 
8
4
7
4
,

 
 
8
7
,

 
 
1
9
,

 
 
3
5
6
3
,

 
 
6
0
1
,

 
 
5
,

 
 
9
,

 
 
1
7
2
,

 
 
4
0
3
,

 
 
5
6
,

 
 
1
9
,

 
 
5
7
,

 
 
1
0
2
3
5
,

 
 
3
8
0
,

 
 
3
8
8
,

 
 
1
9
8
4
,

 
 
6
7
9
,

 
 
8
3
6
9
0
,

 
 
1
4
5
5
2
,

 
 
9
,

 
 
1
,

 
 
7
1
7
,

 
 
2
1
1
3
,

 
 
2
3
8
4
2
,

 
 
2
4
,

 
 
1
2
7
6
,

 
 
2
,

 
 
8
,

 
 
1
4
,

 
 
1
,

 
 
4
7
,

 
 
9
,

 
 
2
4
,

 
 
6
9
5
,

 
 
2
3
8
4
2
,

 
 
3
8
6
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
3
8
9
,

 
 
2
3
8
4
3
,

 
 
1
7
2
,

 
 
5
3
8
,

 
 
3
6
,

 
 
5
1
,

 
 
1
8
,

 
 
8
7
0
,

 
 
1
0
3
,

 
 
1
,

 
 
6
2
6
,

 
 
4
1
0
,

 
 
5
0
,

 
 
2
0
2
,

 
 
5
6
7
,

 
 
2
,

 
 
1
6
5
1
,

 
 
9
,

 
 
1
3
,

 
 
4
5
7
,

 
 
8
,

 
 
3
7
4
,

 
 
2
5
,

 
 
4
6
8
,

 
 
7
8
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
3
7
4
,

 
 
5
7
0
5
,

 
 
3
4
2
7
,

 
 
9
9
4
0
]
,

 
[
1
0
1
,

 
 
4
5
5
0
,

 
 
7
,

 
 
1
9
,

 
 
3
3
6
6
,

 
 
1
,

 
 
1
2
8
1
,

 
 
5
,

 
 
1
,

 
 
3
3
7
4
,

 
 
8
,

 
 
1
0
,

 
 
1
6
6
,

 
 
3
8
,

 
 
6
0
0
0
,

 
 
6
6
2
,

 
 
2
8
6
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
2
0
,

 
 
3
4
6
3
,

 
 
1
1
,

 
 
1
9
5
,

 
 
9
,

 
 
1
,

 
 
1
2
8
1
,

 
 
8
,

 
 
1
4
,

 
 
9
7
4
,

 
 
2
6
,

 
 
2
6
4
,

 
 
3
7
4
,

 
 
5
,

 
 
2
5
9
7
,

 
 
6
,

 
 
1
9
,

 
 
2
3
7
,

 
 
2
5
4
6
,

 
 
1
,

 
 
1
8
3
5
,

 
 
2
4
9
,

 
 
1
,

 
 
7
8
2
,

 
 
3
3
7
4
,

 
 
1
6
7
1
,

 
 
1
6
0
9
7
9
,

 
 
3
,

 
 
5
1
2
,

 
 
3
3
,

 
 
4
0
,

 
 
1
5
9
0
8
,

 
 
3
2
8
7
,

 
 
1
9
7
,

 
 
1
3
,

 
 
2
4
9
,

 
 
1
5
1
0
2
,

 
 
2
2
,

 
 
5
3
,

 
 
4
1
1
,

 
 
7
7
,

 
 
1
,

 
 
9
4
7
,

 
 
1
9
8
,

 
 
4
,

 
 
2
6
5
,

 
 
3
6
,

 
 
8
5
6
,

 
 
3
4
,

 
 
9
,

 
 
5
3
,

 
 
1
0
8
,

 
 
4
,

 
 
2
4
2
6
,

 
 
5
1
2
,

 
 
1
3
4
6
9
,

 
 
5
1
2
,

 
 
1
6
2
,

 
 
2
6
5
,

 
 
5
,

 
 
5
1
2
,

 
 
7
8
7
,

 
 
1
6
2
,

 
 
2
1
6
0
7
,

 
 
5
1
2
,

 
 
7
8
7
,

 
 
1
7
8
7
,

 
 
1
7
,

 
 
1
7
1
5
,

 
 
1
7
,

 
 
4
4
1
,

 
 
5
3
,

 
 
6
6
9
9
,

 
 
9
,

 
 
7
8
7
,

 
 
4
6
1
,

 
 
5
,

 
 
7
8
7
,

 
 
1
6
2
,

 
 
6
9
3
,

 
 
4
4
,

 
 
6
7
8
,

 
 
5
1
2
,

 
 
4
6
1
,

 
 
1
6
2
,

 
 
5
,

 
 
5
1
2
,

 
 
1
6
2
,

 
 
4
6
1
,

 
 
2
,

 
 
5
1
7
3
,

 
 
5
1
2
,

 
 
2
,

 
 
4
0
,

 
 
1
5
0
4
,

 
 
3
2
5
,

 
 
1
0
1
1
,

 
 
1
1
,

 
 
8
,

 
 
3
8
3
,

 
 
1
8
2
1
,

 
 
2
,

 
 
2
4
7
4
,

 
 
5
1
2
,

 
 
1
5
,

 
 
2
7
,

 
 
9
8
7
4
,

 
 
3
,

 
 
1
8
0
8
,

 
 
1
6
2
,

 
 
1
1
1
,

 
 
1
7
,

 
 
4
6
1
,

 
 
1
6
2
,

 
 
5
,

 
 
5
3
,

 
 
1
0
8
,

 
 
5
1
2
,

 
 
2
,

 
 
1
6
,

 
 
6
5
2
5
,

 
 
3
7
4
3
9
,

 
 
1
,

 
 
1
2
8
1
,

 
 
7
7
,

 
 
1
6
7
1
,

 
 
5
1
2
,

 
 
2
,

 
 
1
6
,

 
 
6
5
2
5
,

 
 
3
7
4
3
9
,

 
 
1
5
,

 
 
4
6
1
,

 
 
1
6
2
,

 
 
2
5
,

 
 
5
4
3
8
3
,

 
 
1
5
,

 
 
1
6
2
,

 
 
4
6
1
,

 
 
1
3
,

 
 
8
,

 
 
6
0
5
,

 
 
1
0
6
6
8
6
,

 
 
2
6
,

 
 
5
3
,

 
 
1
7
4
6
8
,

 
 
1
9
9
4
,

 
 
3
5
,

 
 
1
3
,

 
 
6
9
,

 
 
4
,

 
 
2
6
5
,

 
 
4
9
0
,

 
 
1
2
,

 
 
4
4
,

 
 
7
5
5
,

 
 
2
5
,

 
 
1
2
2
4
,

 
 
2
1
2
,

 
 
5
3
,

 
 
1
6
7
5
,

 
 
9
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
8
,

 
 
8
3
6
9
1
,

 
 
1
5
,

 
 
1
,

 
 
9
8
7
4
,

 
 
4
6
1
,

 
 
1
6
2
,

 
 
3
1
,

 
 
1
,

 
 
8
2
1
6
,

 
 
5
5
4
2
,

 
 
5
1
2
,

 
 
7
8
8
,

 
 
1
7
4
6
9
,

 
 
5
1
2
,

 
 
7
8
8
,

 
 
1
6
2
,

 
 
5
3
,

 
 
9
4
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
7
8
8
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
7
8
8
,

 
 
1
6
2
,

 
 
5
1
2
,

 
 
7
8
8
,

 
 
1
6
2
,

 
 
1
5
6
5
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
1
6
2
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
4
6
1
,

 
 
5
1
2
,

 
 
4
6
1
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
4
6
1
,

 
 
3
6
,

 
 
5
1
2
,

 
 
7
9
9
,

 
 
2
4
5
,

 
 
1
6
,

 
 
2
9
2
7
,

 
 
1
5
,

 
 
4
6
1
,

 
 
1
6
2
,

 
 
1
4
,

 
 
1
5
5
,

 
 
8
8
3
7
,

 
 
1
,

 
 
2
4
2
6
,

 
 
5
3
,

 
 
9
4
,

 
 
1
0
,

 
 
1
3
,

 
 
1
1
0
,

 
 
8
,

 
 
3
7
4
4
0
,

 
 
8
4
0
,

 
 
3
1
,

 
 
2
7
8
2
,

 
 
2
9
4
1
,

 
 
1
0
,

 
 
4
,

 
 
2
6
9
6
,

 
 
1
6
9
0
7
,

 
 
1
1
0
,

 
 
5
1
2
,

 
 
7
8
8
,

 
 
2
1
6
0
7
,

 
 
7
8
8
,

 
 
2
1
6
0
7
,

 
 
7
8
8
,

 
 
7
8
8
,

 
 
7
7
2
,

 
 
3
8
,

 
 
7
,

 
 
2
2
7
3
,

 
 
3
1
,

 
 
1
,

 
 
1
2
8
1
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
3
7
4
,

 
 
1
7
3
4
,

 
 
2
,

 
 
1
,

 
 
2
4
9
,

 
 
2
8
8
,

 
 
4
2
,

 
 
4
,

 
 
2
9
7
0
,

 
 
3
,

 
 
1
0
4
,

 
 
7
7
1
3
,

 
 
3
2
9
,

 
 
1
6
2
,

 
 
5
,

 
 
4
6
1
]
,

 
[
1
,

 
 
6
0
3
0
,

 
 
4
5
3
5
,

 
 
1
3
,

 
 
5
6
,

 
 
1
6
,

 
 
1
,

 
 
1
0
9
,

 
 
3
,

 
 
1
,

 
 
5
4
3
8
4
,

 
 
6
0
3
0
,

 
 
2
8
,

 
 
2
9
,

 
 
8
9
,

 
 
1
7
,

 
 
5
1
,

 
 
1
8
,

 
 
3
1
6
,

 
 
1
,

 
 
6
0
3
0
,

 
 
4
5
3
5
,

 
 
2
2
9
7
,

 
 
1
5
,

 
 
1
,

 
 
8
3
6
9
2
,

 
 
3
3
7
1
4
,

 
 
2
9
7
1
6
,

 
 
2
1
5
1
,

 
 
3
2
1
,

 
 
1
4
3
9
,

 
 
5
,

 
 
1
0
,

 
 
1
7
4
7
,

 
 
3
0
3
2
,

 
 
5
,

 
 
1
5
,

 
 
1
0
0
4
,

 
 
5
1
,

 
 
2
4
5
,

 
 
1
9
,

 
 
2
4
7
6
,

 
 
2
,

 
 
8
2
,

 
 
1
,

 
 
6
0
3
0
,

 
 
4
5
3
5
,

 
 
2
,

 
 
8
0
4
7
,

 
 
3
2
9
,

 
 
7
5
9
,

 
 
5
,

 
 
6
0
3
0
,

 
 
4
5
3
5
,

 
 
6
2
,

 
 
1
5
3
,

 
 
1
9
,

 
 
2
9
7
1
6
,

 
 
4
0
1
0
]
,

 
[
2
8
,

 
 
1
2
0
7
,

 
 
1
2
,

 
 
1
3
8
,

 
 
1
3
5
2
,

 
 
8
4
4
,

 
 
1
0
2
8
,

 
 
1
1
8
3
,

 
 
2
8
,

 
 
5
9
0
,

 
 
4
5
1
,

 
 
1
,

 
 
9
5
2
1
,

 
 
7
0
7
6
,

 
 
3
,

 
 
1
0
2
8
,

 
 
5
8
1
,

 
 
1
3
7
,

 
 
3
2
1
9
8
,

 
 
2
1
8
,

 
 
1
2
,

 
 
1
3
8
,

 
 
4
6
,

 
 
7
9
2
,

 
 
2
3
1
1
,

 
 
5
9
0
]
,

 
[
1
0
6
6
8
7
,

 
 
2
6
7
9
,

 
 
6
4
9
,

 
 
4
9
,

 
 
4
,

 
 
2
0
6
,

 
 
6
4
,

 
 
3
6
7
,

 
 
1
6
,

 
 
5
5
4
,

 
 
1
0
,

 
 
1
2
3
7
,

 
 
2
7
,

 
 
2
7
4
7
,

 
 
3
,

 
 
1
3
,

 
 
1
4
1
8
1
,

 
 
4
5
6
,

 
 
2
,

 
 
1
,

 
 
2
6
7
9
,

 
 
4
3
0
2
,

 
 
1
0
6
6
8
7
,

 
 
1
2
3
5
]
,

 
[
4
4
,
 
2
4
9
,
 
3
3
,
 
4
0
,
 
6
3
1
,
 
4
6
]
,

 
[
2
2
,

 
 
5
3
,

 
 
3
4
,

 
 
1
7
8
6
,

 
 
5
,

 
 
9
4
,

 
 
1
1
2
,

 
 
1
5
4
1
,

 
 
7
5
,

 
 
7
6
,

 
 
3
,

 
 
1
,

 
 
6
2
0
,

 
 
5
,

 
 
9
2
,

 
 
1
7
0
7
,

 
 
1
9
7
0
,

 
 
1
7
,

 
 
1
0
1
,

 
 
8
4
,

 
 
3
7
5
,

 
 
4
1
,

 
 
6
2
4
,

 
 
1
6
,

 
 
5
5
,

 
 
2
9
7
5
,

 
 
3
2
1
9
9
,

 
 
1
0
8
0
,

 
 
1
,

 
 
1
9
1
,

 
 
5
,

 
 
1
3
7
8
,

 
 
1
2
0
6
,

 
 
2
2
,

 
 
3
5
4
2
,

 
 
8
,

 
 
1
2
6
,

 
 
2
1
,

 
 
1
2
1
8
9
,

 
 
7
8
,

 
 
8
,

 
 
5
2
,

 
 
1
5
,

 
 
2
8
]
,

 
[
1
3
7
,
 
4
9
,
 
4
4
6
,
 
9
]
,

 
[
1
0
6
6
8
8
,

 
 
3
5
4
1
5
,

 
 
1
0
1
7
,

 
 
4
2
3
9
8
,

 
 
7
,

 
 
4
6
8
,

 
 
1
4
,

 
 
2
,

 
 
8
2
,

 
 
6
0
0
,

 
 
2
2
1
2
2
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
0
6
6
8
8
,

 
 
3
5
4
1
5
,

 
 
1
0
1
7
,

 
 
4
2
3
9
8
,

 
 
5
4
,

 
 
1
9
,

 
 
7
1
3
,

 
 
3
3
3
,

 
 
2
,

 
 
2
0
1
5
,

 
 
4
,

 
 
5
8
,

 
 
1
5
3
3
,

 
 
4
9
1
,

 
 
2
9
,

 
 
4
8
2
,

 
 
8
1
7
7
]
,

 
[
5
8
3
,

 
 
6
,

 
 
7
0
,

 
 
3
8
,

 
 
7
,

 
 
9
4
1
,

 
 
8
6
9
1
,

 
 
1
2
6
6
,

 
 
5
8
5
,

 
 
1
5
0
,

 
 
3
9
7
3
5
,

 
 
7
,

 
 
4
9
,

 
 
1
1
5
,

 
 
5
2
,

 
 
2
4
,

 
 
1
2
6
6
,

 
 
1
5
0
,

 
 
3
2
9
0
,

 
 
4
2
,

 
 
4
3
3
9
,

 
 
4
9
4
8
3
,

 
 
3
,

 
 
3
4
7
,

 
 
1
0
,

 
 
5
4
,

 
 
6
8
,

 
 
2
4
4
9
,

 
 
4
3
,

 
 
1
9
,

 
 
3
2
2
0
0
,

 
 
7
6
,

 
 
6
9
,

 
 
3
,

 
 
1
,

 
 
6
2
7
7
,

 
 
5
1
,

 
 
4
3
,

 
 
1
9
,

 
 
1
4
4
5
,

 
 
1
5
4
6
8
,

 
 
4
3
,

 
 
7
8
5
7
,

 
 
1
7
,

 
 
2
2
1
2
3
,

 
 
3
1
7
0
,

 
 
1
8
,

 
 
2
6
8
,

 
 
2
,

 
 
8
2
,

 
 
1
0
,

 
 
9
2
,

 
 
2
7
7
0
,

 
 
3
8
,

 
 
7
,

 
 
8
1
,

 
 
2
6
8
,

 
 
2
,

 
 
1
1
7
,

 
 
8
,

 
 
9
,

 
 
5
0
0
,

 
 
4
5
5
3
8
,

 
 
3
2
9
0
,

 
 
9
9
,

 
 
9
8
,

 
 
2
3
6
3
,

 
 
5
,

 
 
9
7
7
,

 
 
5
7
0
,

 
 
1
2
,

 
 
4
2
7
6
,

 
 
6
,

 
 
5
6
,

 
 
1
4
,

 
 
2
3
8
6
,

 
 
4
,

 
 
2
8
1
,

 
 
6
0
8
2
8
,

 
 
3
3
0
0
,

 
 
9
1
,

 
 
3
9
1
6
,

 
 
3
9
7
3
6
,

 
 
2
3
6
3
,

 
 
5
,

 
 
9
7
7
,

 
 
5
7
0
,

 
 
6
2
4
,

 
 
2
3
6
,

 
 
2
2
1
8
,

 
 
4
3
,

 
 
1
5
3
,

 
 
1
6
,

 
 
4
,

 
 
6
6
4
,

 
 
3
1
6
6
,

 
 
1
0
,

 
 
5
2
2
8
,

 
 
3
0
0
,

 
 
1
3
8
0
,

 
 
1
,

 
 
1
8
3
9
1
,

 
 
4
6
9
0
,

 
 
1
9
8
3
6
,

 
 
5
,

 
 
1
8
8
0
,

 
 
1
1
7
5
6
,

 
 
1
,

 
 
7
7
,

 
 
1
3
,

 
 
9
,

 
 
4
3
,

 
 
2
3
6
,

 
 
1
8
,

 
 
1
1
9
6
,

 
 
1
2
9
6
4
,

 
 
5
,

 
 
1
2
,

 
 
1
,

 
 
2
0
1
,

 
 
6
6
,

 
 
3
0
6
,

 
 
5
4
6
,

 
 
9
9
,

 
 
4
,

 
 
3
1
7
1
,

 
 
5
,

 
 
5
1
,

 
 
1
8
,

 
 
1
5
3
,

 
 
2
9
1
6
,

 
 
6
2
3
,

 
 
1
,

 
 
1
6
2
1
,

 
 
1
0
3
0
0
,

 
 
1
0
,

 
 
4
2
7
6
,

 
 
8
,

 
 
2
6
0
7
,

 
 
9
6
,

 
 
1
1
7
5
7
,

 
 
9
3
,

 
 
1
,

 
 
8
0
7
5
,

 
 
8
3
6
9
3
,

 
 
1
0
,

 
 
9
2
6
5
,

 
 
1
,

 
 
6
5
8
2
,

 
 
1
0
,

 
 
9
2
6
5
,

 
 
9
9
,

 
 
2
1
2
1
,

 
 
2
0
1
4
,

 
 
3
4
7
,

 
 
1
7
,

 
 
5
3
,

 
 
6
3
,

 
 
8
9
,

 
 
5
,

 
 
3
5
1
,

 
 
1
0
3
,

 
 
1
6
9
0
,

 
 
1
5
9
,

 
 
1
0
0
7
,

 
 
1
7
7
,

 
 
7
6
3
2
,

 
 
3
8
,

 
 
1
1
0
5
,

 
 
1
0
0
,

 
 
1
,

 
 
5
2
2
8
,

 
 
1
6
2
1
,

 
 
1
0
3
0
0
,

 
 
1
9
,

 
 
9
2
5
,

 
 
2
2
,

 
 
2
1
5
,

 
 
3
7
4
4
1
,

 
 
5
2
3
7
,

 
 
2
3
1
8
4
,

 
 
1
,

 
 
2
3
8
4
,

 
 
3
,

 
 
1
,

 
 
1
6
2
1
,

 
 
1
0
3
0
0
,

 
 
2
9
0
,

 
 
8
8
,

 
 
4
6
2
,

 
 
3
,

 
 
2
7
,

 
 
1
9
0
3
,

 
 
1
0
,

 
 
1
,

 
 
4
2
9
9
,

 
 
3
0
0
,

 
 
3
,

 
 
1
8
3
9
2
,

 
 
1
7
,

 
 
6
,

 
 
7
0
,

 
 
7
,

 
 
8
1
,

 
 
1
0
0
3
,

 
 
4
2
7
6
,

 
 
5
,

 
 
5
5
7
1
,

 
 
4
9
,

 
 
1
4
,

 
 
1
0
0
3
,

 
 
3
2
9
0
,

 
 
2
2
9
0
,

 
 
5
5
7
1
,

 
 
1
2
5
,

 
 
7
5
,

 
 
4
8
,

 
 
1
6
0
9
8
0
,

 
 
5
,

 
 
1
6
0
9
8
1
,

 
 
8
6
,

 
 
2
0
2
2
1
,

 
 
3
9
1
6
,

 
 
3
2
9
0
,

 
 
2
4
,

 
 
1
4
,

 
 
4
4
,

 
 
4
7
,

 
 
3
1
6
8
,

 
 
2
4
8
,

 
 
1
5
4
,

 
 
6
9
,

 
 
5
1
,

 
 
8
6
,

 
 
1
4
,

 
 
8
1
9
]
,

 
[
1
9
4
2
7
,

 
 
8
,

 
 
4
,

 
 
1
5
5
8
,

 
 
8
8
7
,

 
 
1
2
0
,

 
 
1
,

 
 
2
1
9
7
,

 
 
1
5
,

 
 
1
8
4
8
,

 
 
2
7
0
2
,

 
 
1
9
4
2
7
,

 
 
4
0
6
,

 
 
8
,

 
 
4
,

 
 
2
2
7
1
,

 
 
1
5
7
0
,

 
 
6
5
,

 
 
5
3
0
6
,

 
 
9
,

 
 
1
6
0
2
,

 
 
9
7
7
,

 
 
5
4
3
8
5
,

 
 
1
2
,

 
 
1
,

 
 
6
4
3
,

 
 
8
3
6
9
4
,

 
 
8
0
7
6
,

 
 
2
,

 
 
4
0
3
,

 
 
5
1
,

 
 
1
8
,

 
 
1
4
,

 
 
2
2
0
2
,

 
 
8
,

 
 
3
1
3
7
,

 
 
5
1
,

 
 
1
8
,

 
 
1
7
,

 
 
1
5
7
0
,

 
 
1
7
,

 
 
5
5
,

 
 
9
1
0
,

 
 
1
7
0
9
,

 
 
2
5
,

 
 
6
1
,

 
 
1
2
0
,

 
 
5
1
,

 
 
1
9
,

 
 
4
3
1
8
,

 
 
1
8
2
6
,

 
 
1
5
9
1
,

 
 
5
,

 
 
1
6
0
9
8
2
,

 
 
4
,

 
 
1
6
1
,

 
 
3
,

 
 
3
5
4
1
6
,

 
 
3
0
8
4
5
,

 
 
1
0
8
7
,

 
 
3
2
,

 
 
1
,

 
 
6
7
0
7
,

 
 
3
9
7
3
7
,

 
 
5
,

 
 
4
1
1
3
,

 
 
7
5
7
0
,

 
 
1
1
2
,

 
 
4
7
9
,

 
 
1
8
,

 
 
9
8
,

 
 
5
,

 
 
4
5
,

 
 
1
6
,

 
 
5
0
2
,

 
 
1
0
,

 
 
1
,

 
 
2
3
]
,

 
[
5
1
4
,

 
 
8
3
5
,

 
 
4
1
,

 
 
8
9
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
5
1
5
,

 
 
1
8
1
8
,

 
 
1
8
,

 
 
9
7
2
,

 
 
2
,

 
 
1
6
,

 
 
3
1
7
9
,

 
 
4
1
7
3
,

 
 
9
3
,

 
 
1
,

 
 
2
5
3
,

 
 
5
1
,

 
 
4
4
3
9
,

 
 
5
4
,

 
 
1
,

 
 
1
9
8
,

 
 
3
3
,

 
 
2
7
7
1
5
,

 
 
6
9
8
9
0
,

 
 
8
,

 
 
1
4
,

 
 
1
1
,

 
 
3
0
9
,

 
 
3
7
4
8
,

 
 
4
4
2
,

 
 
2
7
7
1
6
,

 
 
3
1
,

 
 
1
,

 
 
1
0
4
4
,

 
 
2
5
3
,

 
 
1
7
,

 
 
2
7
,

 
 
2
9
2
,

 
 
5
3
,

 
 
1
9
,

 
 
2
,

 
 
6
8
1
6
,

 
 
1
,

 
 
2
3
,

 
 
1
7
,

 
 
1
1
,

 
 
5
3
4
,

 
 
1
8
8
8
,

 
 
5
,

 
 
1
4
,

 
 
5
5
,

 
 
7
6
4
2
,

 
 
6
0
2
,

 
 
3
8
9
2
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
9
3
5
5
,

 
 
8
4
,

 
 
1
,

 
 
5
1
4
,

 
 
3
9
,

 
 
1
6
,

 
 
8
9
4
1
,

 
 
3
1
8
3
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
1
,

 
 
5
1
4
,

 
 
1
1
6
,

 
 
7
,

 
 
1
2
9
6
5
,

 
 
1
0
0
,

 
 
7
3
4
,

 
 
4
4
3
9
,

 
 
1
,

 
 
1
3
2
,

 
 
3
9
3
,

 
 
2
2
3
,

 
 
1
,

 
 
4
5
5
7
8
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
9
0
,

 
 
6
,

 
 
1
5
6
,

 
 
1
1
3
,

 
 
5
1
4
,

 
 
1
,

 
 
5
1
4
,

 
 
3
,

 
 
4
,

 
 
1
4
3
2
,

 
 
8
,

 
 
1
4
,

 
 
1
8
8
3
,

 
 
9
7
2
,

 
 
2
,

 
 
4
4
3
9
,

 
 
1
,

 
 
3
0
0
,

 
 
6
9
0
,

 
 
3
,

 
 
1
,

 
 
2
5
7
,

 
 
2
6
,

 
 
2
0
1
1
,

 
 
7
3
2
3
,

 
 
4
0
3
,

 
 
2
,

 
 
5
0
3
,

 
 
1
,

 
 
1
4
9
,

 
 
2
7
7
1
6
,

 
 
7
,

 
 
1
2
9
6
5
,

 
 
5
8
,

 
 
9
3
,

 
 
3
4
,

 
 
9
,

 
 
1
7
7
,

 
 
9
1
,

 
 
4
2
6
9
,

 
 
9
0
9
7
,

 
 
6
0
8
2
9
]
,

 
[
9
6
8
,

 
 
2
3
1
,

 
 
9
7
,

 
 
4
,

 
 
1
0
8
9
9
,

 
 
1
2
9
1
,

 
 
1
4
,

 
 
2
,

 
 
2
5
8
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
2
6
,

 
 
3
,

 
 
4
4
3
,

 
 
7
,

 
 
3
4
,

 
 
1
9
,

 
 
6
0
,

 
 
2
5
4
,

 
 
3
5
,

 
 
1
3
,

 
 
6
5
2
0
,

 
 
2
3
1
8
5
,

 
 
1
7
,

 
 
6
,

 
 
1
8
4
,

 
 
1
0
1
,

 
 
1
8
9
7
,

 
 
1
6
2
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
3
3
4
,

 
 
2
0
5
,

 
 
2
0
7
6
,

 
 
2
,

 
 
9
4
,

 
 
1
,

 
 
4
4
5
2
,

 
 
3
1
9
5
,

 
 
3
,

 
 
1
,

 
 
8
2
2
,

 
 
9
,

 
 
6
,

 
 
6
4
0
,

 
 
2
0
7
6
,

 
 
2
,

 
 
1
0
1
7
1
,

 
 
1
1
1
5
,

 
 
1
,

 
 
6
5
4
,

 
 
3
,

 
 
1
5
8
,

 
 
2
3
9
2
,

 
 
1
2
9
,

 
 
2
1
,

 
 
2
7
,

 
 
3
8
7
,

 
 
1
4
8
,

 
 
1
5
8
,

 
 
2
3
9
2
,

 
 
1
2
9
,

 
 
1
7
7
,

 
 
4
7
,

 
 
5
4
3
,

 
 
1
0
,

 
 
1
,

 
 
7
0
0
,

 
 
3
,

 
 
3
8
,

 
 
6
,

 
 
1
9
3
4
,

 
 
1
7
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
2
5
,

 
 
2
0
7
0
,

 
 
8
0
,

 
 
3
3
9
,

 
 
3
2
,

 
 
1
,

 
 
3
3
4
,

 
 
2
9
2
,

 
 
2
6
,

 
 
1
4
,

 
 
3
6
,

 
 
1
2
8
,

 
 
8
0
,

 
 
1
,

 
 
1
0
6
9
,

 
 
2
9
2
,

 
 
1
0
0
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
1
6
0
,

 
 
1
2
,

 
 
1
6
0
9
8
3
,

 
 
1
3
,

 
 
8
,

 
 
4
6
0
8
,

 
 
3
5
2
,

 
 
6
,

 
 
1
0
1
6
7
,

 
 
1
1
,

 
 
2
1
4
,

 
 
1
6
0
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
3
4
7
2
,

 
 
9
3
7
,

 
 
5
7
9
,

 
 
2
,

 
 
6
,

 
 
1
2
,

 
 
1
5
8
,

 
 
2
1
,

 
 
4
,

 
 
1
0
9
,

 
 
4
8
,

 
 
1
1
7
,

 
 
5
6
0
1
,

 
 
8
0
7
0
,

 
 
2
,

 
 
8
5
6
5
,

 
 
7
6
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
2
6
,

 
 
1
4
,

 
 
1
2
,

 
 
3
7
,

 
 
2
,

 
 
2
5
8
,

 
 
1
5
4
,

 
 
4
7
,

 
 
1
5
7
,

 
 
6
9
,

 
 
7
2
,

 
 
4
9
,

 
 
4
,

 
 
1
8
0
7
8
,

 
 
3
3
4
,

 
 
2
9
2
,

 
 
9
5
2
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
3
4
7
2
,

 
 
9
3
7
,

 
 
1
2
,

 
 
1
5
4
,

 
 
2
,

 
 
2
5
8
,

 
 
3
7
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
3
2
,

 
 
1
0
2
5
,

 
 
6
7
9
,

 
 
5
3
6
,

 
 
1
5
,

 
 
3
0
,

 
 
6
2
3
2
,

 
 
3
2
,

 
 
2
9
0
,

 
 
1
,

 
 
5
7
9
3
,

 
 
4
0
3
,

 
 
9
,

 
 
3
0
,

 
 
2
1
2
,

 
 
1
2
,

 
 
3
0
7
4
,

 
 
1
,

 
 
3
4
3
,

 
 
1
9
0
,

 
 
3
,

 
 
9
5
2
2
,

 
 
1
9
6
1
,

 
 
2
,

 
 
1
1
8
,

 
 
4
9
0
,

 
 
2
,

 
 
1
,

 
 
4
2
4
,

 
 
4
7
,

 
 
9
5
2
2
,

 
 
1
0
,

 
 
1
,

 
 
5
1
4
,

 
 
8
,

 
 
6
9
,

 
 
7
,

 
 
5
7
7
,

 
 
1
1
,

 
 
1
0
,

 
 
4
1
,

 
 
9
6
,

 
 
2
3
8
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
1
1
9
4
,

 
 
1
4
2
2
,

 
 
2
6
,

 
 
7
1
,

 
 
3
4
7
2
,

 
 
1
4
,

 
 
9
3
7
,

 
 
1
2
,

 
 
3
7
,

 
 
2
,

 
 
4
5
8
,

 
 
9
,

 
 
4
4
9
,

 
 
3
,

 
 
4
7
8
2
,

 
 
3
0
1
,

 
 
2
3
3
,

 
 
1
4
4
2
,

 
 
1
8
3
,

 
 
4
7
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
3
4
7
2
,

 
 
9
3
7
,

 
 
1
2
,

 
 
1
5
4
,

 
 
5
,

 
 
1
2
7
3
5
,

 
 
1
6
4
0
,

 
 
4
1
,

 
 
2
,

 
 
4
6
1
4
,

 
 
2
4
4
6
,

 
 
3
0
,

 
 
1
4
0
,

 
 
3
,

 
 
9
1
,

 
 
2
1
7
,

 
 
4
9
,

 
 
6
9
,

 
 
5
1
,

 
 
2
4
4
8
5
,

 
 
3
1
,

 
 
3
8
,

 
 
1
1
2
,

 
 
7
4
2
,

 
 
2
9
5
8
,

 
 
2
6
,

 
 
8
4
,

 
 
8
0
,

 
 
7
,

 
 
1
1
7
,

 
 
9
2
,

 
 
4
0
8
6
,

 
 
1
8
,

 
 
2
1
7
,

 
 
7
,

 
 
9
4
,

 
 
1
0
,

 
 
1
4
0
0
,

 
 
1
2
,

 
 
1
1
,

 
 
1
7
,

 
 
2
2
,

 
 
1
1
,

 
 
8
6
,

 
 
4
,

 
 
2
4
2
,

 
 
5
1
8
,

 
 
4
9
,

 
 
6
9
,

 
 
7
2
,

 
 
2
7
,

 
 
3
3
4
,

 
 
7
7
,

 
 
2
9
2
,

 
 
3
6
5
,

 
 
1
9
4
8
,

 
 
1
2
,

 
 
4
7
,

 
 
5
8
,

 
 
8
4
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
6
6
5
,

 
 
1
2
,

 
 
5
5
,

 
 
3
,

 
 
6
,

 
 
1
0
6
9
,

 
 
2
0
5
,

 
 
2
,

 
 
2
5
8
,

 
 
4
7
,

 
 
3
,

 
 
1
9
1
,

 
 
3
3
4
,

 
 
2
0
5
,

 
 
4
,

 
 
5
8
7
,

 
 
3
7
0
,

 
 
2
6
,

 
 
8
0
,

 
 
7
,

 
 
1
7
,

 
 
2
7
,

 
 
1
6
0
9
8
4
,

 
 
3
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
2
,

 
 
4
,

 
 
1
0
6
9
,

 
 
2
9
2
,

 
 
4
8
,

 
 
7
,

 
 
9
0
,

 
 
2
,

 
 
4
9
0
8
,

 
 
1
2
7
3
5
,

 
 
1
6
4
0
,

 
 
7
,

 
 
9
4
,

 
 
6
9
8
9
1
,

 
 
2
1
,

 
 
4
1
5
,

 
 
6
,

 
 
2
2
9
,

 
 
3
4
,

 
 
9
,

 
 
8
1
4
2
,

 
 
1
8
5
,

 
 
4
,

 
 
1
5
6
7
6
,

 
 
2
7
7
1
7
,

 
 
2
5
,

 
 
4
1
5
,

 
 
1
8
5
,

 
 
3
6
6
,

 
 
6
9
,

 
 
1
8
5
,

 
 
8
3
6
9
5
,

 
 
3
6
3
,

 
 
4
1
5
,

 
 
7
6
0
,

 
 
1
4
4
2
,

 
 
4
7
,

 
 
5
8
,

 
 
5
8
4
,

 
 
1
,

 
 
7
2
3
,

 
 
3
5
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
4
9
,

 
 
1
0
,

 
 
4
3
6
,

 
 
7
9
1
,

 
 
9
,

 
 
1
1
,

 
 
1
8
1
,

 
 
9
6
,

 
 
1
9
,

 
 
2
,

 
 
1
6
,

 
 
2
7
8
5
,

 
 
1
4
9
1
,

 
 
9
,

 
 
2
8
6
,

 
 
9
,

 
 
4
5
5
7
9
,

 
 
7
,

 
 
2
4
,

 
 
1
4
3
,

 
 
3
6
,

 
 
7
,

 
 
2
4
,

 
 
1
4
,

 
 
7
9
,

 
 
1
0
6
6
8
9
,

 
 
8
,

 
 
4
4
,

 
 
2
7
7
0
,

 
 
1
0
1
,

 
 
8
4
,

 
 
1
8
1
,

 
 
9
,

 
 
1
3
6
6
,

 
 
2
,

 
 
2
9
4
9
,

 
 
6
0
,

 
 
3
6
,

 
 
3
1
6
,

 
 
3
1
9
,

 
 
1
5
5
,

 
 
1
4
4
,

 
 
6
0
,

 
 
2
1
8
,

 
 
7
6
7
,

 
 
9
6
1
,

 
 
3
,

 
 
5
0
7
6
,

 
 
7
1
4
8
,

 
 
2
6
,

 
 
1
8
,

 
 
4
9
,

 
 
4
0
1
,

 
 
5
8
,

 
 
1
5
,

 
 
3
8
5
,

 
 
5
1
,

 
 
1
7
8
8
,

 
 
3
8
,

 
 
9
,

 
 
3
6
,

 
 
3
1
6
,

 
 
3
1
9
,

 
 
5
7
7
,

 
 
1
,

 
 
2
2
8
,

 
 
2
,

 
 
1
1
7
,

 
 
1
0
1
,

 
 
8
4
,

 
 
7
8
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
4
9
,

 
 
6
9
,

 
 
2
0
,

 
 
1
0
6
9
,

 
 
1
0
1
2
,

 
 
1
2
7
3
5
,

 
 
4
1
,

 
 
1
0
0
,

 
 
6
0
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
2
4
8
,

 
 
3
7
,

 
 
2
,

 
 
2
0
4
,

 
 
1
,

 
 
2
2
8
,

 
 
1
5
7
,

 
 
2
,

 
 
3
8
,

 
 
2
0
,

 
 
4
3
5
4
,

 
 
4
4
9
2
,

 
 
3
1
9
,

 
 
1
0
7
7
,

 
 
1
1
,

 
 
2
,

 
 
1
1
7
,

 
 
5
,

 
 
1
4
4
,

 
 
3
0
,

 
 
1
2
9
,

 
 
9
9
,

 
 
2
3
7
,

 
 
5
7
,

 
 
1
2
7
1
,

 
 
1
7
,

 
 
1
4
,

 
 
2
1
7
,

 
 
9
6
,

 
 
2
3
8
,

 
 
1
1
,

 
 
4
4
0
9
,

 
 
6
,

 
 
1
2
8
4
,

 
 
9
,

 
 
2
5
5
,

 
 
4
4
5
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
7
2
3
,

 
 
5
,

 
 
2
5
8
,

 
 
1
7
2
,

 
 
1
5
4
,

 
 
4
,

 
 
1
6
6
2
,

 
 
4
9
5
,

 
 
2
6
,

 
 
8
0
,

 
 
7
,

 
 
2
7
,

 
 
3
3
4
,

 
 
7
7
,

 
 
2
9
2
,

 
 
2
3
9
2
,

 
 
2
4
8
,

 
 
2
0
,

 
 
4
3
5
4
,

 
 
3
1
9
,

 
 
3
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
7
1
,

 
 
7
9
,

 
 
1
0
6
5
,

 
 
9
6
,

 
 
2
3
8
,

 
 
1
1
,

 
 
2
4
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
8
,

 
 
1
7
,

 
 
3
8
,

 
 
8
3
6
9
6
,

 
 
2
9
8
,

 
 
5
8
4
,

 
 
1
,

 
 
9
1
,

 
 
1
4
3
,

 
 
9
8
7
5
,

 
 
3
1
9
,

 
 
8
,

 
 
4
4
,

 
 
2
7
7
0
,

 
 
7
2
3
,

 
 
2
2
8
3
,

 
 
5
6
3
6
,

 
 
6
3
7
5
,

 
 
3
4
8
8
]
,

 
[
2
2
,

 
 
2
5
2
7
,

 
 
1
0
0
,

 
 
3
8
8
4
,

 
 
1
6
1
5
9
,

 
 
5
,

 
 
8
8
3
,

 
 
1
0
3
0
1
,

 
 
8
4
,

 
 
7
,

 
 
7
5
6
,

 
 
1
6
,

 
 
3
3
,

 
 
4
0
,

 
 
1
8
4
9
,

 
 
2
2
,

 
 
3
8
3
5
,

 
 
2
0
2
1
1
,

 
 
3
2
9
5
,

 
 
1
0
,

 
 
1
0
7
2
7
]
,

 
[
1
,
 
1
3
2
,
 
5
6
5
3
,
 
2
5
4
,
 
5
1
,
 
9
9
3
,
 
1
0
3
]
,

 
[
2
6
8
,

 
 
2
,

 
 
3
2
7
1
,

 
 
1
,

 
 
3
7
2
,

 
 
3
,

 
 
2
5
9
6
6
,

 
 
1
3
,

 
 
8
,

 
 
4
7
,

 
 
3
,

 
 
1
4
1
,

 
 
1
2
4
0
,

 
 
1
2
5
,

 
 
7
,

 
 
8
1
,

 
 
3
6
,

 
 
4
9
0
5
,

 
 
3
2
,

 
 
5
0
8
,

 
 
8
1
8
,

 
 
1
5
,

 
 
2
9
9
,

 
 
3
9
4
,

 
 
1
,

 
 
2
3
,

 
 
4
2
,

 
 
1
,

 
 
1
9
0
6
8
,

 
 
1
2
1
2
,

 
 
3
3
,

 
 
3
0
8
,

 
 
1
7
0
0
,

 
 
2
5
9
6
6
,

 
 
1
5
,

 
 
1
,

 
 
7
6
0
6
,

 
 
2
5
,

 
 
1
0
4
,

 
 
6
9
8
9
2
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
1
2
5
,

 
 
9
,

 
 
3
7
2
,

 
 
7
9
0
,

 
 
3
1
,

 
 
6
2
1
,

 
 
3
8
,

 
 
5
1
,

 
 
4
1
1
,

 
 
4
,

 
 
1
0
5
1
2
,

 
 
2
6
,

 
 
1
1
,

 
 
1
9
5
,

 
 
2
,

 
 
3
7
,

 
 
9
,

 
 
1
0
1
,

 
 
5
5
6
,

 
 
5
5
,

 
 
1
2
2
5
,

 
 
6
6
0
,

 
 
1
,

 
 
2
6
0
2
,

 
 
1
4
9
0
,

 
 
2
1
6
0
8
,

 
 
1
0
5
1
2
,

 
 
1
0
0
4
7
,

 
 
1
,

 
 
2
9
9
,

 
 
4
2
3
9
9
,

 
 
1
5
,

 
 
2
7
,

 
 
1
5
4
8
7
,

 
 
4
9
5
0
,

 
 
2
,

 
 
1
,

 
 
7
6
0
6
,

 
 
5
2
9
4
,

 
 
1
0
4
,

 
 
4
3
7
,

 
 
1
8
5
1
,

 
 
1
0
,

 
 
1
,

 
 
1
2
4
2
,

 
 
1
9
4
3
5
,

 
 
6
6
,

 
 
3
8
4
8
,

 
 
1
,

 
 
1
8
5
4
,

 
 
1
6
1
6
0
,

 
 
9
7
6
,

 
 
2
1
3
,

 
 
1
9
2
,

 
 
1
,

 
 
1
0
5
1
2
,

 
 
3
3
,

 
 
1
,

 
 
4
5
2
1
,

 
 
3
,

 
 
3
9
7
3
8
,

 
 
9
,

 
 
1
3
3
,

 
 
2
,

 
 
1
6
,

 
 
1
,

 
 
1
0
5
1
1
,

 
 
2
6
,

 
 
7
,

 
 
2
2
9
,

 
 
2
3
4
6
,

 
 
1
0
4
,

 
 
1
1
5
,

 
 
1
0
9
,

 
 
1
6
0
9
8
5
,

 
 
1
,

 
 
6
8
5
5
,

 
 
1
6
0
9
8
6
,

 
 
1
6
0
9
8
7
,

 
 
1
4
1
8
,

 
 
9
3
6
1
,

 
 
3
2
9
1
,

 
 
1
6
0
9
8
8
,

 
 
3
2
9
1
,

 
 
6
7
2
,

 
 
1
6
0
9
8
9
,

 
 
9
3
6
1
,

 
 
3
2
9
1
,

 
 
1
6
0
9
9
0
,

 
 
3
2
9
1
,

 
 
1
6
0
9
9
1
,

 
 
3
2
9
1
,

 
 
9
9
8
,

 
 
1
6
0
9
9
2
,

 
 
1
5
2
6
5
,

 
 
4
9
4
8
4
,

 
 
4
7
,

 
 
2
1
3
,

 
 
1
9
2
,

 
 
1
5
3
,

 
 
3
0
0
,

 
 
1
5
,

 
 
1
,

 
 
7
6
0
6
,

 
 
3
3
,

 
 
1
,

 
 
2
1
6
4
,

 
 
8
6
1
0
,

 
 
2
6
0
4
,

 
 
1
,

 
 
9
5
8
2
,

 
 
8
,

 
 
3
1
5
,

 
 
1
,

 
 
4
5
2
1
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
3
8
3
,

 
 
3
5
1
7
,

 
 
1
5
,

 
 
1
,

 
 
7
6
0
6
,

 
 
1
3
,

 
 
1
8
1
,

 
 
9
6
,

 
 
1
3
5
7
,

 
 
8
3
6
9
7
,

 
 
9
,

 
 
1
8
,

 
 
2
1
8
7
,

 
 
8
3
8
1
,

 
 
2
5
,

 
 
1
0
4
3
5
,

 
 
2
5
,

 
 
1
6
0
9
9
3
,

 
 
1
8
4
7
,

 
 
2
3
8
3
9
,

 
 
6
2
1
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
3
5
7
,

 
 
2
1
8
,

 
 
4
8
,

 
 
1
6
8
,

 
 
2
7
7
1
8
,

 
 
5
,

 
 
2
0
6
7
3
,

 
 
4
8
4
,

 
 
2
1
0
,

 
 
3
,

 
 
5
4
,

 
 
1
9
,

 
 
1
9
3
3
,

 
 
2
2
6
4
6
,

 
 
4
2
3
3
,

 
 
6
2
1
,

 
 
1
0
0
,

 
 
1
1
,

 
 
1
3
5
7
,

 
 
2
9
6
7
,

 
 
6
8
5
1
,

 
 
1
8
8
8
,

 
 
5
,

 
 
7
2
,

 
 
1
8
6
,

 
 
7
2
,

 
 
1
1
3
8
,

 
 
1
6
3
,

 
 
1
3
,

 
 
8
,

 
 
4
0
,

 
 
4
9
,

 
 
1
6
6
5
5
,

 
 
4
6
]
,

 
[
2
0
3
,

 
 
2
1
1
9
,

 
 
1
2
6
2
,

 
 
3
9
,

 
 
6
6
,

 
 
1
1
1
7
,

 
 
1
0
,

 
 
2
0
7
9
,

 
 
1
2
6
2
,

 
 
1
7
,

 
 
1
1
,

 
 
8
,

 
 
1
,

 
 
4
4
2
,

 
 
2
6
7
,

 
 
8
,

 
 
2
0
6
7
4
,

 
 
5
,

 
 
2
5
9
6
7
,

 
 
3
,

 
 
3
3
9
,

 
 
1
1
1
1
,

 
 
4
9
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
1
8
1
,

 
 
4
1
8
8
,

 
 
1
1
7
,

 
 
9
,

 
 
8
8
8
7
,

 
 
8
,

 
 
1
,

 
 
1
4
4
8
,

 
 
6
9
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
1
4
4
8
,

 
 
4
4
0
,

 
 
1
1
,

 
 
8
,

 
 
3
7
1
,

 
 
3
8
1
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
2
3
0
9
,

 
 
8
9
,

 
 
2
0
5
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
3
7
,

 
 
4
1
1
,

 
 
3
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
2
8
6
7
6
,

 
 
1
0
5
1
3
,

 
 
5
,

 
 
1
6
0
9
9
4
,

 
 
4
5
6
,

 
 
6
0
6
7
,

 
 
5
,

 
 
5
2
1
0
,

 
 
3
6
,

 
 
3
0
,

 
 
2
5
5
0
,

 
 
2
,

 
 
1
3
,

 
 
8
,

 
 
3
8
3
,

 
 
1
4
,

 
 
4
,

 
 
3
9
0
4
,

 
 
1
4
5
,

 
 
3
,

 
 
3
3
5
,

 
 
9
,

 
 
1
6
7
,

 
 
1
3
,

 
 
8
,

 
 
1
0
,

 
 
9
2
1
,

 
 
3
,

 
 
4
3
0
,

 
 
1
1
3
,

 
 
5
7
0
]
,

 
[
7
,

 
 
2
9
1
,

 
 
1
1
,

 
 
1
8
2
,

 
 
6
5
8
3
,

 
 
1
6
1
,

 
 
3
,

 
 
3
7
0
2
,

 
 
2
5
4
1
,

 
 
1
1
3
9
,

 
 
7
,

 
 
3
3
2
,

 
 
1
,

 
 
9
6
0
,

 
 
1
5
7
7
,

 
 
1
5
,

 
 
9
,

 
 
2
9
,

 
 
8
6
,

 
 
1
2
,

 
 
1
8
2
2
,

 
 
1
4
4
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
3
7
9
5
,

 
 
1
6
1
,

 
 
3
,

 
 
1
0
6
6
9
0
,

 
 
8
1
6
,

 
 
1
1
3
9
,

 
 
1
,

 
 
2
3
6
,

 
 
6
,

 
 
1
3
1
,

 
 
8
,

 
 
4
6
3
,

 
 
2
3
8
,

 
 
1
4
4
,

 
 
7
,

 
 
6
3
,

 
 
1
0
5
9
1
,

 
 
4
2
,

 
 
1
1
,

 
 
4
4
0
,

 
 
9
,

 
 
1
1
0
]
,

 
[
7
,

 
 
2
6
3
,

 
 
4
7
3
8
,

 
 
3
8
5
,

 
 
6
,

 
 
1
5
9
,

 
 
1
1
,

 
 
1
7
,

 
 
4
,

 
 
1
3
0
9
2
,

 
 
2
5
,

 
 
3
3
0
,

 
 
4
,

 
 
1
1
7
5
8
,

 
 
2
5
,

 
 
4
,

 
 
3
4
7
1
,

 
 
1
,

 
 
1
8
3
8
,

 
 
8
,

 
 
9
,

 
 
7
1
,

 
 
3
0
8
4
6
,

 
 
3
6
,

 
 
9
,

 
 
5
6
,

 
 
1
6
,

 
 
1
,

 
 
4
3
2
,

 
 
2
3
,

 
 
3
3
,

 
 
9
,

 
 
1
4
5
,

 
 
5
8
3
4
,

 
 
4
9
4
8
5
,

 
 
5
6
,

 
 
3
0
4
,

 
 
4
3
9
,

 
 
2
,

 
 
1
6
0
9
9
5
,

 
 
2
7
7
1
9
,

 
 
4
9
4
8
6
,

 
 
4
1
,

 
 
8
,

 
 
1
8
2
1
,

 
 
3
4
6
,

 
 
2
,

 
 
2
0
0
1
,

 
 
1
0
4
,

 
 
1
6
9
2
]
,

 
[
9
,

 
 
2
4
,

 
 
3
6
,

 
 
1
6
0
9
9
6
,

 
 
6
9
,

 
 
3
,

 
 
8
0
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
3
4
,

 
 
4
,

 
 
4
9
3
,

 
 
1
0
,

 
 
4
8
0
,

 
 
7
,

 
 
9
9
,

 
 
2
,

 
 
5
2
0
,

 
 
1
1
,

 
 
5
5
3
4
,

 
 
1
6
7
6
,

 
 
8
6
9
2
,

 
 
3
1
,

 
 
6
0
3
,

 
 
2
7
4
,

 
 
6
3
3
]
,

 
[
1
,
 
1
2
0
,
 
2
4
,
 
4
,
 
1
1
6
1
,
 
1
1
9
0
,
 
3
3
7
,
 
7
4
,
 
3
4
,
 
5
3
,
 
1
2
0
,
 
9
]
,

 
[
7
1
5
0
,
 
7
6
,
 
1
6
0
9
9
7
,
 
3
0
,
 
3
1
3
9
]
,

 
[
4
,

 
 
7
0
9
3
,

 
 
3
,

 
 
4
,

 
 
1
7
4
7
0
,

 
 
1
5
,

 
 
1
,

 
 
4
3
2
,

 
 
2
9
,

 
 
4
5
5
,

 
 
1
9
4
3
6
,

 
 
3
2
8
,

 
 
1
1
,

 
 
7
6
,

 
 
9
0
,

 
 
6
,

 
 
7
0
,

 
 
9
,

 
 
4
,

 
 
7
0
9
3
,

 
 
3
,

 
 
4
,

 
 
1
7
4
7
0
,

 
 
4
5
,

 
 
1
6
,

 
 
1
0
4
7
,

 
 
1
5
,

 
 
1
,

 
 
4
3
2
,

 
 
2
9
,

 
 
1
5
,

 
 
4
0
7
2
,

 
 
4
6
,

 
 
9
5
5
,

 
 
6
0
3
,

 
 
6
4
8
,

 
 
3
6
3
8
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
1
7
3
,
 
3
7
6
,
 
5
9
8
,
 
7
,
 
4
3
,
 
4
8
,
 
2
,
 
1
5
2
,
 
5
0
7
,
 
5
9
8
,
 
2
6
,
 
2
5
4
,
 
1
5
9
8
,
 
1
0
,
 
4
6
,
 
2
9
]
,

 
[
4
4
,
 
2
4
9
,
 
9
5
,
 
1
2
,
 
2
3
6
5
,
 
3
7
,
 
7
0
,
 
4
6
]
,

 
[
5
5
3
2
,
 
7
,
 
8
1
,
 
5
5
3
2
,
 
6
,
 
1
8
,
 
2
1
6
0
9
,
 
7
,
 
1
7
8
6
]
,

 
[
8
2
0
6
,

 
 
3
,

 
 
4
7
7
,

 
 
9
8
,

 
 
3
0
3
,

 
 
3
9
,

 
 
6
,

 
 
6
3
8
,

 
 
6
0
,

 
 
1
0
6
,

 
 
1
2
,

 
 
2
3
,

 
 
8
2
0
6
,

 
 
3
,

 
 
4
7
7
,

 
 
2
8
8
,

 
 
1
3
,

 
 
2
3
,

 
 
1
7
5
7
,

 
 
7
4
0
,

 
 
1
6
6
,

 
 
1
2
,

 
 
1
9
4
5
]
,

 
[
6
3
4
,
 
7
,
 
1
8
7
,
 
1
,
 
1
1
6
,
 
1
2
7
,
 
1
5
0
,
 
7
,
 
6
5
8
,
 
1
3
,
 
1
1
6
2
,
 
4
2
4
0
0
]
,

 
[
5
0
,

 
 
9
6
8
,

 
 
5
,

 
 
3
5
6
,

 
 
2
9
,

 
 
7
,

 
 
3
3
6
,

 
 
9
,

 
 
6
,

 
 
9
6
8
,

 
 
3
0
,

 
 
4
6
,

 
 
2
9
,

 
 
5
,

 
 
1
2
9
2
,

 
 
5
,

 
 
4
1
5
5
,

 
 
3
5
6
,

 
 
1
,

 
 
1
6
3
9
,

 
 
3
,

 
 
1
1
,

 
 
6
,

 
 
1
8
,

 
 
2
0
0
,

 
 
2
,

 
 
4
1
5
5
,

 
 
2
1
3
,

 
 
3
7
,

 
 
3
1
,

 
 
8
2
1
,

 
 
2
,

 
 
2
8
,

 
 
1
7
,

 
 
7
,

 
 
1
9
,

 
 
4
4
,

 
 
2
0
7
8
,

 
 
3
,

 
 
2
9
8
,

 
 
3
6
,

 
 
1
0
,

 
 
5
5
,

 
 
1
9
8
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
4
,

 
 
2
1
2
,

 
 
2
,

 
 
2
1
3
,

 
 
3
7
,

 
 
2
5
,

 
 
9
8
4
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
2
9
6
1
,

 
 
1
,

 
 
4
7
5
,

 
 
6
,

 
 
1
2
2
,

 
 
1
4
,

 
 
6
2
3
0
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
6
4
,

 
 
8
,

 
 
1
8
3
,

 
 
4
5
9
5
,

 
 
4
2
7
8
,

 
 
9
0
4
9
,

 
 
9
2
1
,

 
 
3
,

 
 
1
,

 
 
4
7
5
,

 
 
2
7
,

 
 
3
4
3
,

 
 
4
8
0
,

 
 
2
4
2
,

 
 
2
0
2
8
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
3
9
7
3
9
,

 
 
1
9
8
3
5
,

 
 
5
1
5
4
,

 
 
1
6
7
2
,

 
 
1
3
9
2
0
,

 
 
2
2
,

 
 
6
,

 
 
8
6
,

 
 
1
0
,

 
 
2
9
7
,

 
 
3
,

 
 
3
2
2
0
1
,

 
 
1
4
5
5
3
,

 
 
7
,

 
 
4
3
,

 
 
1
4
,

 
 
1
5
9
,

 
 
1
,

 
 
1
4
0
0
,

 
 
2
,

 
 
3
0
8
4
1
,

 
 
1
,

 
 
1
0
5
9
2
,

 
 
3
2
,

 
 
4
2
4
0
1
,

 
 
1
5
,

 
 
8
8
,

 
 
7
,

 
 
2
2
6
,

 
 
9
,

 
 
8
,

 
 
8
6
9
3
]
,

 
[
9
,
 
8
,
 
3
8
0
,
 
2
1
,
 
1
,
 
1
1
4
,
 
7
9
,
 
1
9
7
,
 
1
,
 
4
3
7
,
 
4
7
,
 
2
4
,
 
2
7
,
 
1
7
1
0
,
 
1
0
9
0
]
,

 
[
1
8
5
,

 
 
5
7
,

 
 
1
,

 
 
2
4
9
,

 
 
6
3
5
4
,

 
 
1
3
,

 
 
2
3
,

 
 
1
7
,

 
 
1
0
1
,

 
 
3
6
7
,

 
 
4
7
7
,

 
 
2
,

 
 
6
3
,

 
 
1
3
,

 
 
9
4
,

 
 
2
,

 
 
1
0
4
7
,

 
 
2
3
,

 
 
6
9
1
,

 
 
2
6
,

 
 
7
,

 
 
2
4
6
,

 
 
1
5
6
0
,

 
 
1
3
5
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
4
1
,

 
 
2
8
5
,

 
 
1
2
6
,

 
 
4
,

 
 
4
4
2
,

 
 
3
4
8
,

 
 
3
,

 
 
9
8
,

 
 
1
2
1
5
,

 
 
4
8
7
,

 
 
7
6
,

 
 
4
1
,

 
 
9
,

 
 
8
,

 
 
1
1
8
5
,

 
 
8
4
2
,

 
 
6
2
1
,

 
 
8
,

 
 
1
1
,

 
 
1
1
3
3
,

 
 
2
,

 
 
2
6
9
,

 
 
3
2
,

 
 
4
,

 
 
4
8
6
,

 
 
9
,

 
 
8
,

 
 
7
0
9
4
,

 
 
2
3
8
,

 
 
7
,

 
 
1
5
8
0
,

 
 
1
,

 
 
4
7
,

 
 
2
5
,

 
 
1
4
9
,

 
 
4
6
7
,

 
 
3
4
4
,

 
 
3
,

 
 
1
5
4
,

 
 
4
3
,

 
 
1
7
9
4
,

 
 
1
8
2
,

 
 
3
0
2
,

 
 
8
2
,

 
 
4
1
,

 
 
1
8
,

 
 
4
,

 
 
8
9
7
,

 
 
3
,

 
 
1
4
3
9
,

 
 
7
6
,

 
 
4
1
,

 
 
9
,

 
 
1
2
3
2
,

 
 
3
2
2
0
2
,

 
 
8
4
3
,

 
 
3
1
,

 
 
1
0
6
6
9
1
,

 
 
3
3
7
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
7
2
0
,

 
 
6
3
1
3
,

 
 
1
0
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
4
,

 
 
6
1
3
,

 
 
6
2
,

 
 
3
7
4
4
2
,

 
 
1
0
,

 
 
1
2
3
6
,

 
 
5
4
3
8
6
,

 
 
1
3
2
,

 
 
3
,

 
 
6
8
,

 
 
3
0
0
,

 
 
1
5
,

 
 
4
,

 
 
4
9
3
,

 
 
5
2
,

 
 
2
9
2
9
,

 
 
2
1
1
0
1
,

 
 
1
4
8
4
,

 
 
4
5
5
8
0
,

 
 
5
,

 
 
8
,

 
 
1
4
,

 
 
2
9
0
,

 
 
4
3
0
,

 
 
6
1
,

 
 
7
5
,

 
 
2
6
4
,

 
 
9
8
0
2
]
,

 
[
6
,
 
1
8
,
 
4
,
 
1
0
6
6
9
2
,
 
4
0
0
]
,

 
[
1
7
2
1
,

 
 
5
5
,

 
 
1
8
1
3
,

 
 
1
3
1
,

 
 
2
,

 
 
2
1
3
,

 
 
1
9
1
2
,

 
 
3
1
0
,

 
 
5
,

 
 
2
5
,

 
 
1
2
9
,

 
 
1
0
1
,

 
 
4
9
3
1
,

 
 
1
0
5
,

 
 
4
3
,

 
 
9
3
5
,

 
 
1
4
1
7
9
,

 
 
1
,

 
 
3
6
2
6
,

 
 
2
0
7
8
,

 
 
3
,

 
 
2
8
,

 
 
5
4
0
]
,

 
[
2
8
,

 
 
8
,

 
 
5
1
0
,

 
 
3
,

 
 
4
2
8
5
,

 
 
6
2
,

 
 
1
1
0
9
,

 
 
1
0
8
5
,

 
 
5
,

 
 
3
9
7
,

 
 
7
5
,

 
 
1
4
2
,

 
 
1
2
,

 
 
2
0
0
,

 
 
2
8
,

 
 
6
,

 
 
1
8
4
,

 
 
1
7
,

 
 
1
0
1
,

 
 
8
1
8
,

 
 
3
7
,

 
 
6
,

 
 
1
5
4
4
,

 
 
8
3
5
,

 
 
7
0
3
,

 
 
3
6
,

 
 
2
5
0
,

 
 
1
8
0
,

 
 
8
,

 
 
4
,

 
 
3
0
1
,

 
 
2
0
2
,

 
 
7
1
,

 
 
9
9
9
9
,

 
 
3
0
7
6
]
,

 
[
5
1
,

 
 
3
6
4
,

 
 
2
,

 
 
1
6
,

 
 
2
6
1
,

 
 
3
0
5
,

 
 
1
2
,

 
 
1
3
,

 
 
4
4
7
,

 
 
2
6
6
9
,

 
 
7
1
,

 
 
1
4
,

 
 
4
8
,

 
 
1
3
0
,

 
 
6
6
4
,

 
 
4
8
4
,

 
 
1
0
6
,

 
 
1
8
,

 
 
1
6
5
,

 
 
2
,

 
 
1
6
,

 
 
4
1
2
1
,

 
 
1
,

 
 
2
1
8
,

 
 
9
,

 
 
1
1
2
,

 
 
8
3
0
,

 
 
1
1
4
0
,

 
 
4
5
2
3
,

 
 
6
8
1
7
,

 
 
3
1
8
6
,

 
 
6
2
3
5
]
,

 
[
1
0
,

 
 
6
3
9
,

 
 
2
,

 
 
2
0
,

 
 
1
8
6
0
,

 
 
1
6
0
9
9
8
,

 
 
3
9
,

 
 
1
4
,

 
 
3
4
,

 
 
1
1
,

 
 
3
2
,

 
 
2
2
5
,

 
 
6
3
,

 
 
2
8
,

 
 
9
4
4
,

 
 
7
1
2
,

 
 
6
3
1
]
,

 
[
9
,

 
 
8
,

 
 
2
0
,

 
 
3
2
7
,

 
 
5
,

 
 
3
8
,

 
 
8
,

 
 
2
0
,

 
 
9
4
6
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
5
6
1
,

 
 
8
3
6
9
8
,

 
 
3
8
5
,

 
 
6
,

 
 
3
4
7
,

 
 
1
5
4
,

 
 
2
5
,

 
 
1
4
,

 
 
5
2
,

 
 
9
0
,

 
 
1
9
,

 
 
4
,

 
 
1
9
4
,

 
 
1
6
4
5
,

 
 
3
0
3
,

 
 
5
,

 
 
2
9
6
1
,

 
 
2
9
7
,

 
 
6
4
9
,

 
 
3
2
,

 
 
9
2
5
6
,

 
 
1
9
4
,

 
 
2
4
9
5
,

 
 
7
3
9
7
,

 
 
1
0
,

 
 
4
9
6
2
,

 
 
2
,

 
 
2
9
7
,

 
 
6
4
9
,

 
 
1
1
2
,

 
 
1
8
,

 
 
4
7
9
,

 
 
1
4
,

 
 
4
7
8
2
,

 
 
2
5
,

 
 
2
4
4
0
]
,

 
[
9
,

 
 
6
7
5
3
,

 
 
1
6
1
6
1
,

 
 
1
,

 
 
2
1
4
,

 
 
8
,

 
 
1
1
,

 
 
2
0
1
,

 
 
2
,

 
 
8
6
1
2
,

 
 
1
2
9
6
6
,

 
 
2
4
2
8
,

 
 
2
2
,

 
 
5
1
,

 
 
1
8
,

 
 
1
6
5
,

 
 
2
,

 
 
2
3
8
7
,

 
 
1
0
,

 
 
4
1
2
7
,

 
 
1
6
0
8
,

 
 
6
4
,

 
 
2
5
,

 
 
5
1
7
3
,

 
 
8
8
,

 
 
1
9
6
,

 
 
4
6
]
,

 
[
1
0
2
1
,

 
 
3
1
0
8
,

 
 
5
,

 
 
3
3
2
6
,

 
 
3
9
,

 
 
1
6
3
7
,

 
 
5
2
0
,

 
 
1
3
,

 
 
1
0
2
1
,

 
 
3
1
0
8
,

 
 
6
9
9
3
,

 
 
3
1
1
2
,

 
 
1
5
,

 
 
1
8
8
0
,

 
 
3
0
0
,

 
 
1
0
,

 
 
3
3
2
6
,

 
 
3
8
,

 
 
1
0
0
,

 
 
1
1
,

 
 
2
7
6
,

 
 
9
1
2
,

 
 
1
9
2
0
,

 
 
5
4
7
9
,

 
 
1
3
9
9
,

 
 
1
0
0
1
,

 
 
2
1
6
]
,

 
[
7
8
,

 
 
1
8
,

 
 
6
,

 
 
9
4
4
,

 
 
1
,

 
 
1
3
0
9
3
,

 
 
7
5
,

 
 
1
8
0
,

 
 
7
8
0
,

 
 
9
,

 
 
2
9
,

 
 
8
,

 
 
8
9
9
,

 
 
2
,

 
 
4
7
,

 
 
5
2
8
7
,

 
 
7
,

 
 
1
7
3
,

 
 
4
,

 
 
5
8
,

 
 
6
8
7
8
,

 
 
3
1
7
4
,

 
 
3
,

 
 
1
3
0
9
3
,

 
 
7
5
,

 
 
6
,

 
 
3
0
1
,

 
 
2
4
0
5
]
,

 
[
6
0
8
3
0
,

 
 
7
,

 
 
2
6
3
,

 
 
2
1
,

 
 
6
,

 
 
2
6
,

 
 
4
3
,

 
 
4
6
8
,

 
 
9
,

 
 
6
,

 
 
5
9
,

 
 
5
6
3
,

 
 
1
1
,

 
 
2
5
,

 
 
3
5
4
1
7
,

 
 
6
9
,

 
 
6
,

 
 
7
0
,

 
 
5
2
,

 
 
4
5
,

 
 
6
7
4
,

 
 
2
6
9
,

 
 
1
5
7
,

 
 
5
,

 
 
4
2
6
,

 
 
3
5
2
1
,

 
 
1
6
0
9
9
9
,

 
 
9
2
8
,

 
 
4
9
,

 
 
4
,

 
 
2
6
0
,

 
 
8
6
7
,

 
 
1
5
1
,

 
 
5
2
,

 
 
4
1
6
,

 
 
1
5
8
,

 
 
3
5
9
,

 
 
6
8
,

 
 
8
1
0
,

 
 
1
9
2
,

 
 
1
5
,

 
 
6
8
,

 
 
4
6
,

 
 
2
9
,

 
 
3
5
,

 
 
4
,

 
 
2
0
6
,

 
 
5
2
,

 
 
4
1
6
,

 
 
1
0
,

 
 
2
7
,

 
 
2
3
]
,

 
[
9
5
,

 
 
9
5
,

 
 
1
2
,

 
 
1
,

 
 
4
6
9
1
,

 
 
3
7
3
6
,

 
 
4
5
5
8
1
,

 
 
1
6
8
9
6
,

 
 
1
9
0
7
0
,

 
 
5
4
8
4
,

 
 
2
9
,

 
 
7
2
,

 
 
5
3
4
,

 
 
3
1
4
8
,

 
 
7
3
,

 
 
1
,

 
 
2
9
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
7
9
,

 
 
1
1
,

 
 
9
5
,

 
 
8
5
6
,

 
 
1
1
8
,

 
 
2
3
8
4
4
,

 
 
3
5
7
8
,

 
 
2
0
,

 
 
1
1
4
,

 
 
1
1
4
1
,

 
 
1
9
0
,

 
 
6
8
2
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
2
6
3
3
,

 
 
4
5
0
,

 
 
4
1
7
,

 
 
3
3
5
5
,

 
 
2
1
4
1
,

 
 
1
6
0
,

 
 
3
0
3
3
,

 
 
7
2
9
,

 
 
2
1
4
1
,

 
 
1
6
0
,

 
 
1
9
0
,

 
 
1
8
0
0
,

 
 
9
6
2
,

 
 
7
8
8
,

 
 
6
3
2
,

 
 
1
1
0
6
,

 
 
4
6
1
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
7
2
9
,

 
 
2
0
4
1
,

 
 
1
6
2
,

 
 
4
0
1
3
,

 
 
1
,

 
 
9
6
4
1
,

 
 
2
1
2
3
,

 
 
1
1
4
1
,

 
 
1
9
0
,

 
 
7
2
4
,

 
 
5
3
2
,

 
 
7
2
9
,

 
 
6
8
2
,

 
 
2
7
9
,

 
 
1
0
9
8
,

 
 
8
0
4
,

 
 
2
6
3
3
,

 
 
7
,

 
 
6
3
0
1
,

 
 
1
5
8
5
,

 
 
1
6
1
0
0
0
,

 
 
1
,

 
 
9
6
4
1
,

 
 
2
1
2
3
,

 
 
1
1
4
1
,

 
 
5
9
6
,

 
 
2
,

 
 
6
8
,

 
 
6
6
8
3
,

 
 
1
2
7
2
,

 
 
3
,

 
 
5
6
4
,

 
 
9
1
8
,

 
 
1
4
0
,

 
 
4
5
5
8
2
]
,

 
[
1
8
0
7
9
,

 
 
1
,

 
 
1
8
0
7
9
,

 
 
2
9
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
9
,

 
 
4
,

 
 
2
5
4
9
,

 
 
3
,

 
 
2
5
5
2
,

 
 
1
1
6
,

 
 
6
9
,

 
 
4
,

 
 
1
,

 
 
1
0
4
3
6
,

 
 
7
0
,

 
 
3
5
,

 
 
1
1
,

 
 
2
6
,

 
 
5
9
,

 
 
1
0
8
,

 
 
2
,

 
 
1
5
8
4
,

 
 
1
1
,

 
 
5
0
7
,

 
 
5
1
,

 
 
4
9
,

 
 
5
9
,

 
 
7
0
,

 
 
7
4
,

 
 
1
1
,

 
 
7
5
2
,

 
 
7
,

 
 
2
4
,

 
 
9
5
0
,

 
 
3
5
,

 
 
1
1
,

 
 
5
,

 
 
5
8
5
,

 
 
7
3
,

 
 
2
1
,

 
 
4
,

 
 
1
5
1
5
,

 
 
2
8
7
3
,

 
 
1
2
9
0
,

 
 
3
,

 
 
7
4
,

 
 
1
1
,

 
 
7
5
2
,

 
 
7
,

 
 
2
0
4
,

 
 
1
1
,

 
 
1
5
,

 
 
1
8
0
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
7
4
2
,

 
 
2
8
2
,

 
 
7
6
4
3
,

 
 
5
,

 
 
6
4
,

 
 
7
,

 
 
8
1
,

 
 
1
3
0
4
,

 
 
5
2
1
,

 
 
1
2
8
,

 
 
2
4
1
,

 
 
1
9
9
3
,

 
 
5
,

 
 
3
0
,

 
 
3
6
1
,

 
 
8
,

 
 
1
6
5
7
,

 
 
6
,

 
 
8
3
9
0
,

 
 
8
3
9
0
,

 
 
1
2
6
4
,

 
 
2
3
1
,

 
 
9
6
4
,

 
 
6
]
,

 
[
7
,
 
4
8
,
 
2
,
 
6
3
,
 
1
1
,
 
1
0
,
 
2
8
5
3
,
 
1
4
4
,
 
7
1
,
 
5
7
,
 
4
4
0
,
 
1
2
,
 
4
9
6
,
 
8
9
,
 
1
7
7
,
 
2
7
,
 
2
6
0
5
]
,

 
[
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
5
9
9
,

 
 
6
9
,

 
 
3
,

 
 
1
,

 
 
4
5
1
,

 
 
1
3
6
3
,

 
 
2
8
,

 
 
5
6
,

 
 
1
4
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
7
,

 
 
4
,

 
 
2
0
2
,

 
 
1
2
,

 
 
6
3
9
1
,

 
 
2
5
,

 
 
4
,

 
 
3
4
7
3
,

 
 
3
3
0
,

 
 
4
0
,

 
 
4
1
4
,

 
 
1
8
,

 
 
1
3
4
7
,

 
 
2
6
,

 
 
1
3
,

 
 
2
3
,

 
 
8
7
,

 
 
1
4
,

 
 
2
9
4
8
,

 
 
5
0
8
,

 
 
4
3
4
,

 
 
1
2
,

 
 
9
7
5
,

 
 
5
,

 
 
1
,

 
 
1
1
9
,

 
 
4
5
4
,

 
 
5
6
,

 
 
5
2
0
,

 
 
7
8
,

 
 
6
3
,

 
 
6
6
,

 
 
3
8
,

 
 
2
8
,

 
 
8
,

 
 
1
4
,

 
 
5
,

 
 
5
0
8
,

 
 
1
1
9
,

 
 
2
3
0
,

 
 
6
,

 
 
8
7
,

 
 
1
5
2
9
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
3
2
,

 
 
5
3
0
,

 
 
1
,

 
 
4
5
4
,

 
 
2
6
,

 
 
5
0
,

 
 
5
2
0
,

 
 
7
8
,

 
 
6
,

 
 
7
8
9
,

 
 
2
1
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
1
0
,

 
 
2
0
,

 
 
7
9
,

 
 
5
1
5
,

 
 
2
5
,

 
 
1
5
,

 
 
1
0
4
,

 
 
4
6
,

 
 
2
9
,

 
 
5
0
,

 
 
4
1
1
,

 
 
1
6
8
1
,

 
 
1
,

 
 
2
3
,

 
 
2
,

 
 
4
5
9
,

 
 
1
,

 
 
4
6
4
,

 
 
1
5
9
8
,

 
 
6
9
,

 
 
9
6
,

 
 
2
3
8
,

 
 
5
3
0
,

 
 
1
,

 
 
1
1
9
,

 
 
4
5
4
,

 
 
4
5
,

 
 
1
5
2
9
,

 
 
1
1
9
,

 
 
3
3
0
,

 
 
1
,

 
 
7
7
4
,

 
 
1
1
9
,

 
 
5
9
9
,

 
 
1
,

 
 
2
3
,

 
 
8
7
,

 
 
1
5
3
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
2
,

 
 
1
1
,

 
 
2
9
1
1
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
4
3
4
,

 
 
2
5
,

 
 
1
1
,

 
 
3
9
,

 
 
1
6
,

 
 
1
2
2
7
,

 
 
2
,

 
 
8
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
2
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
2
2
,

 
 
3
1
9
,

 
 
2
,

 
 
3
5
6
,

 
 
8
,

 
 
1
6
5
5
]
,

 
[
5
3
6
0
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
1
1
0
,

 
 
2
,

 
 
3
4
,

 
 
1
3
,

 
 
2
3
1
,

 
 
6
3
,

 
 
2
2
,

 
 
7
,

 
 
3
9
,

 
 
5
8
4
,

 
 
3
8
,

 
 
1
,

 
 
1
3
8
7
,

 
 
8
,

 
 
1
2
1
9
0
]
,

 
[
1
3
,
 
2
3
,
 
2
3
7
,
 
1
3
8
1
,
 
6
3
,
 
5
4
3
8
7
,
 
1
0
0
3
]
,

 
[
1
5
6
9
8
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
7
1
7
,

 
 
1
7
,

 
 
2
,

 
 
7
4
,

 
 
4
,

 
 
3
7
4
4
3
,

 
 
1
0
3
2
,

 
 
1
0
,

 
 
1
,

 
 
6
2
9
,

 
 
6
0
7
,

 
 
1
1
,

 
 
8
,

 
 
3
2
7
,

 
 
7
7
]
,

 
[
1
0
6
6
9
3
,

 
 
7
8
,

 
 
8
,

 
 
1
0
6
6
9
4
,

 
 
1
0
6
6
9
3
,

 
 
9
6
,

 
 
4
4
5
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
4
0
1
,

 
 
1
5
,

 
 
1
,

 
 
3
1
1
6
,

 
 
1
0
0
4
8
,

 
 
3
,

 
 
1
1
6
6
3
,

 
 
5
4
,

 
 
8
,

 
 
6
9
5
,

 
 
1
7
,

 
 
4
,

 
 
1
2
0
,

 
 
1
0
,

 
 
1
3
,

 
 
2
3
,

 
 
1
9
8
1
,

 
 
2
4
1
,

 
 
2
6
,

 
 
4
,

 
 
1
3
9
2
1
,

 
 
1
2
,

 
 
1
1
1
3
8
,

 
 
5
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
9
1
0
5
,

 
 
3
6
6
8
,

 
 
1
0
,

 
 
9
,

 
 
1
0
0
4
8
,

 
 
1
8
9
,

 
 
1
4
,

 
 
7
7
,

 
 
6
9
7
,

 
 
9
1
0
6
,

 
 
1
0
0
3
,

 
 
2
1
3
7
,

 
 
8
7
1
,

 
 
2
6
,

 
 
1
8
1
,

 
 
9
6
,

 
 
1
6
2
5
,

 
 
2
,

 
 
3
2
8
,

 
 
1
,

 
 
4
7
9
,

 
 
1
2
8
,

 
 
4
6
2
,

 
 
1
4
7
,

 
 
3
3
,

 
 
1
,

 
 
2
7
9
6
,

 
 
3
,

 
 
1
,

 
 
8
3
6
9
9
,

 
 
8
2
4
8
,

 
 
2
5
,

 
 
9
6
,

 
 
7
2
5
,

 
 
2
6
1
,

 
 
8
8
5
,

 
 
1
0
6
,

 
 
1
5
,

 
 
9
,

 
 
2
5
7
,

 
 
1
8
9
,

 
 
6
6
,

 
 
2
7
7
2
0
,

 
 
3
1
0
1
,

 
 
2
1
,

 
 
2
8
1
5
,

 
 
1
4
7
2
,

 
 
3
,

 
 
4
,

 
 
5
7
8
,

 
 
1
8
3
3
,

 
 
2
,

 
 
1
4
3
7
8
,

 
 
1
,

 
 
1
8
0
9
,

 
 
6
2
0
,

 
 
5
,

 
 
9
6
,

 
 
3
,

 
 
1
,

 
 
8
2
4
8
,

 
 
9
1
,

 
 
4
1
5
2
,

 
 
3
2
,

 
 
5
6
1
,

 
 
3
3
0
1
,

 
 
2
1
2
8
,

 
 
9
7
3
,

 
 
1
,

 
 
1
7
7
7
7
,

 
 
1
7
2
1
,

 
 
4
0
,

 
 
1
,

 
 
5
3
8
,

 
 
1
3
1
,

 
 
1
0
,

 
 
9
,

 
 
1
0
0
4
8
,

 
 
1
8
,

 
 
4
0
1
,

 
 
1
5
,

 
 
4
,

 
 
1
9
8
,

 
 
3
,

 
 
9
2
0
9
,

 
 
1
,

 
 
2
1
4
,

 
 
9
,

 
 
8
,

 
 
1
4
4
,

 
 
2
1
6
1
0
,

 
 
2
1
3
7
,

 
 
3
7
4
7
,

 
 
2
4
,

 
 
9
8
,

 
 
6
6
4
,

 
 
6
4
4
9
,

 
 
5
,

 
 
1
,

 
 
8
3
6
9
9
,

 
 
8
2
4
8
,

 
 
1
7
4
7
1
,

 
 
1
6
7
,

 
 
3
7
4
7
,

 
 
1
1
1
0
,

 
 
6
4
4
9
,

 
 
1
1
7
5
9
,

 
 
1
,

 
 
8
2
4
8
,

 
 
2
4
,

 
 
2
7
5
2
,

 
 
2
6
2
,

 
 
2
6
,

 
 
1
4
,

 
 
3
0
8
,

 
 
1
,

 
 
2
6
7
3
,

 
 
1
6
6
,

 
 
9
,

 
 
1
,

 
 
6
9
6
4
,

 
 
1
0
0
4
8
,

 
 
2
4
,

 
 
1
1
4
,

 
 
5
9
2
,

 
 
3
2
,

 
 
4
,

 
 
5
7
1
,

 
 
3
3
7
0
,

 
 
3
0
6
0
,

 
 
6
0
4
,

 
 
3
2
,

 
 
6
6
0
,

 
 
4
2
5
,

 
 
9
,

 
 
1
3
,

 
 
1
2
0
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
0
9
2
,

 
 
3
0
4
,

 
 
1
1
3
,

 
 
6
8
1
,

 
 
2
5
,

 
 
1
1
3
,

 
 
1
3
8
2
,

 
 
2
2
,

 
 
1
1
1
,

 
 
1
0
6
,

 
 
3
0
7
,

 
 
2
,

 
 
1
6
,

 
 
1
3
3
,

 
 
1
0
,

 
 
2
8
,

 
 
8
3
,

 
 
1
,

 
 
4
4
2
,

 
 
4
9
3
,

 
 
4
5
,

 
 
7
3
0
,

 
 
1
3
7
7
,

 
 
1
3
5
,

 
 
8
3
7
0
0
,

 
 
3
0
9
5
,

 
 
6
8
2
8
,

 
 
5
1
4
0
,

 
 
6
0
3
1
]
,

 
[
9
8
9
,

 
 
1
5
,

 
 
4
6
,

 
 
1
2
4
,

 
 
5
4
7
,

 
 
2
7
,

 
 
8
6
0
,

 
 
3
5
7
7
,

 
 
9
8
9
,

 
 
1
5
,

 
 
4
1
0
,

 
 
4
6
,

 
 
1
2
4
,

 
 
1
1
1
,

 
 
1
7
,

 
 
5
,

 
 
1
0
,

 
 
1
,

 
 
2
2
6
,

 
 
3
,

 
 
9
3
0
9
,

 
 
3
4
7
,

 
 
8
,

 
 
2
7
,

 
 
2
7
0
6
,

 
 
1
3
3
9
,

 
 
5
4
,

 
 
3
5
4
1
8
,

 
 
3
2
2
0
3
,

 
 
1
,

 
 
8
6
0
,

 
 
5
9
9
]
,

 
[
2
5
1
1
,

 
 
3
6
7
,

 
 
2
7
3
3
,

 
 
6
,

 
 
2
,

 
 
1
4
7
,

 
 
1
,

 
 
2
7
0
,

 
 
7
3
,

 
 
1
0
,

 
 
4
,

 
 
9
8
,

 
 
1
8
1
2
,

 
 
4
2
4
0
,

 
 
7
9
8
,

 
 
1
0
6
6
9
5
,

 
 
2
4
9
5
,

 
 
1
3
5
,

 
 
2
7
,

 
 
3
9
3
,

 
 
1
0
1
3
,

 
 
4
3
5
7
,

 
 
8
,

 
 
6
0
5
,

 
 
4
2
1
1
,

 
 
5
4
,

 
 
8
,

 
 
7
8
,

 
 
7
1
,

 
 
1
2
2
8
,

 
 
8
5
1
3
,

 
 
1
0
,

 
 
1
,

 
 
2
3
,

 
 
1
0
0
2
,

 
 
2
,

 
 
6
6
9
]
,

 
[
1
8
4
,

 
 
7
,

 
 
3
6
5
9
,

 
 
6
,

 
 
9
,

 
 
1
3
,

 
 
8
,

 
 
1
,

 
 
2
5
1
,

 
 
3
6
1
,

 
 
2
8
,

 
 
5
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
1
8
5
6
,

 
 
8
6
1
5
,

 
 
6
4
,

 
 
9
3
,

 
 
7
,

 
 
3
4
,

 
 
3
7
5
,

 
 
6
,

 
 
5
6
,

 
 
6
5
,

 
 
3
,

 
 
1
6
5
,

 
 
2
,

 
 
7
9
,

 
 
1
,

 
 
4
8
7
8
,

 
 
2
8
,

 
 
5
,

 
 
7
0
3
,

 
 
2
0
,

 
 
3
7
5
9
,

 
 
1
9
5
4
,

 
 
2
1
,

 
 
6
,

 
 
5
4
3
,

 
 
1
4
4
,

 
 
2
0
,

 
 
7
7
,

 
 
2
4
9
,

 
 
8
,

 
 
2
1
,

 
 
1
,

 
 
3
1
1
,

 
 
5
4
2
,

 
 
5
4
,

 
 
1
8
,

 
 
1
1
8
5
,

 
 
1
1
7
6
,

 
 
1
6
4
,

 
 
3
8
3
,

 
 
7
2
6
6
,

 
 
3
,

 
 
2
8
6
7
7
,

 
 
1
,

 
 
3
1
0
0
,

 
 
7
,

 
 
1
3
1
,

 
 
1
0
,

 
 
2
5
1
,

 
 
3
6
,

 
 
3
7
5
,

 
 
1
6
4
,

 
 
1
4
,

 
 
1
,

 
 
2
2
1
,

 
 
2
2
2
,

 
 
2
,

 
 
2
2
2
9
,

 
 
3
4
8
8
,

 
 
6
2
8
4
,

 
 
7
3
3
1
,

 
 
5
9
5
6
]
,

 
[
2
9
3
,

 
 
1
1
9
,

 
 
3
,

 
 
1
2
6
5
,

 
 
5
6
8
2
,

 
 
4
,

 
 
2
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
8
,

 
 
1
5
,

 
 
1
2
6
5
,

 
 
5
6
8
2
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
7
,

 
 
1
8
2
,

 
 
1
1
6
,

 
 
6
6
2
2
,

 
 
3
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
6
9
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
1
0
2
,

 
 
6
7
3
,

 
 
2
3
,

 
 
1
7
8
3
,

 
 
2
3
5
,

 
 
2
5
,

 
 
4
4
,

 
 
7
3
2
,

 
 
2
,

 
 
1
,

 
 
1
0
6
8
,

 
 
5
0
,

 
 
6
3
,

 
 
2
8
,

 
 
1
3
3
2
,

 
 
1
2
,

 
 
1
7
5
,

 
 
2
9
7
0
,

 
 
1
0
5
,

 
 
1
1
2
8
,

 
 
1
2
,

 
 
6
7
3
,

 
 
8
3
,

 
 
6
6
,

 
 
5
0
,

 
 
1
9
3
,

 
 
9
,

 
 
8
3
,

 
 
2
4
5
,

 
 
1
6
,

 
 
1
5
,

 
 
3
4
2
,

 
 
1
7
1
2
,

 
 
5
,

 
 
5
6
,

 
 
4
9
8
,

 
 
2
9
5
,

 
 
2
,

 
 
2
6
1
,

 
 
1
0
6
,

 
 
9
,

 
 
1
6
5
1
,

 
 
9
2
,

 
 
1
7
4
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
1
3
,

 
 
4
5
4
,

 
 
2
4
,

 
 
6
6
8
,

 
 
6
4
,

 
 
1
0
,

 
 
1
0
0
9
,

 
 
6
,

 
 
8
7
,

 
 
1
1
5
9
,

 
 
1
,

 
 
1
1
9
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
4
9
,

 
 
5
6
7
,

 
 
1
,

 
 
9
8
6
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
5
,

 
 
1
7
7
6
,

 
 
2
7
7
,

 
 
2
5
5
7
,

 
 
2
1
,

 
 
3
1
0
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
2
6
,

 
 
1
6
,

 
 
7
4
9
,

 
 
9
,

 
 
4
0
8
,

 
 
9
1
7
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
1
3
5
9
,

 
 
1
,

 
 
1
7
7
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
1
7
7
,

 
 
2
1
9
0
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
7
7
,

 
 
2
2
5
,

 
 
2
6
,

 
 
5
9
,

 
 
1
5
2
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
4
3
,

 
 
4
3
,

 
 
2
8
9
4
,

 
 
1
1
,

 
 
5
8
,

 
 
1
0
,

 
 
3
4
0
7
,

 
 
2
1
,

 
 
5
0
8
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
,

 
 
3
8
,

 
 
3
4
,

 
 
1
6
8
,

 
 
1
0
8
]
,

 
[
2
0
,

 
 
1
2
5
7
,

 
 
3
,

 
 
1
2
9
,

 
 
1
,

 
 
2
3
,

 
 
8
,

 
 
5
7
4
,

 
 
1
8
7
4
0
,

 
 
5
,

 
 
2
4
,

 
 
6
3
0
,

 
 
1
7
,

 
 
4
9
7
,

 
 
2
8
,

 
 
4
2
7
,

 
 
3
8
8
,

 
 
7
8
4
5
,

 
 
5
,

 
 
7
7
3
9
,

 
 
5
1
3
,

 
 
7
1
8
,

 
 
6
3
2
,

 
 
5
1
1
,

 
 
1
0
9
7
5
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
5
,

 
 
7
3
7
,

 
 
1
1
,

 
 
2
,

 
 
3
8
,

 
 
5
3
,

 
 
1
9
,

 
 
8
9
,

 
 
1
7
,

 
 
1
0
9
0
0
,

 
 
1
8
0
8
0
,

 
 
2
2
,

 
 
5
3
,

 
 
3
9
,

 
 
4
0
,

 
 
2
6
3
,

 
 
2
,

 
 
6
9
9
3
,

 
 
1
5
,

 
 
2
9
0
,

 
 
1
,

 
 
2
3
,

 
 
2
0
1
,

 
 
3
8
2
,

 
 
3
,

 
 
1
8
7
4
1
,

 
 
4
3
3
,

 
 
6
1
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
2
1
2
,

 
 
1
,

 
 
2
3
,

 
 
4
2
,

 
 
2
,

 
 
1
6
,

 
 
3
2
6
5
,

 
 
7
,

 
 
2
6
3
,

 
 
9
,

 
 
5
3
,

 
 
5
6
,

 
 
4
2
6
,

 
 
2
1
,

 
 
2
7
,

 
 
1
4
1
7
,

 
 
1
8
7
4
2
,

 
 
6
6
0
,

 
 
2
1
6
1
1
,

 
 
4
5
7
,

 
 
5
3
,

 
 
3
9
,

 
 
4
0
,

 
 
2
6
3
,

 
 
1
5
,

 
 
1
9
7
,

 
 
4
,

 
 
6
6
0
,

 
 
1
8
1
,

 
 
3
4
,

 
 
2
5
9
,

 
 
5
5
,

 
 
9
8
,

 
 
5
6
5
,

 
 
1
1
,

 
 
1
1
6
6
4
,

 
 
6
0
,

 
 
7
0
8
,

 
 
3
,

 
 
1
0
5
,

 
 
2
2
,

 
 
4
1
,

 
 
8
6
,

 
 
4
9
,

 
 
4
7
,

 
 
2
7
0
,

 
 
9
,

 
 
5
3
,

 
 
1
0
3
,

 
 
4
0
,

 
 
2
6
3
,

 
 
8
,

 
 
1
6
2
3
,

 
 
2
1
,

 
 
2
3
1
6
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
2
0
1
,

 
 
9
3
,

 
 
4
4
,

 
 
6
6
0
,

 
 
3
3
,

 
 
4
0
,

 
 
1
0
7
2
8
,

 
 
1
2
,

 
 
1
3
8
6
]
,

 
[
1
2
8
3
,

 
 
1
7
7
,

 
 
2
2
9
4
,

 
 
3
8
,

 
 
7
2
,

 
 
6
0
9
,

 
 
3
5
,

 
 
4
6
3
,

 
 
7
4
,

 
 
1
3
7
6
0
,

 
 
1
3
,

 
 
1
,

 
 
2
9
9
,

 
 
2
0
6
,

 
 
7
,

 
 
1
3
1
,

 
 
3
5
,

 
 
4
5
5
8
3
,

 
 
6
0
1
,

 
 
2
4
7
0
,

 
 
9
1
,

 
 
2
6
4
1
,

 
 
3
2
,

 
 
8
8
3
8
,

 
 
2
0
0
4
,

 
 
2
4
,

 
 
3
9
1
,

 
 
4
,

 
 
1
2
4
3
,

 
 
6
3
3
,

 
 
1
5
0
,

 
 
2
0
,

 
 
1
2
4
4
,

 
 
3
4
0
,

 
 
2
8
2
,

 
 
6
2
6
,

 
 
2
1
,

 
 
1
,

 
 
3
4
1
,

 
 
1
,

 
 
1
0
1
7
2
,

 
 
5
1
3
,

 
 
2
1
,

 
 
1
,

 
 
4
5
5
8
4
,

 
 
2
4
0
6
,

 
 
1
7
4
5
,

 
 
1
8
5
,

 
 
7
8
,

 
 
7
,

 
 
2
5
9
3
,

 
 
9
,

 
 
1
,

 
 
5
2
2
9
,

 
 
2
6
7
7
8
,

 
 
2
2
6
5
,

 
 
5
6
,

 
 
1
6
,

 
 
1
0
,

 
 
4
1
,

 
 
5
,

 
 
1
5
3
,

 
 
3
4
,

 
 
1
,

 
 
2
8
6
7
8
,

 
 
5
5
5
,

 
 
1
5
7
,

 
 
5
,

 
 
2
5
7
5
,

 
 
1
5
1
,

 
 
9
,

 
 
1
8
9
3
,

 
 
4
,

 
 
6
7
8
6
,

 
 
7
7
,

 
 
2
0
,

 
 
3
1
3
7
,

 
 
2
3
5
,

 
 
2
0
6
,

 
 
3
5
,

 
 
9
6
7
,

 
 
2
5
3
7
,

 
 
2
4
,

 
 
4
0
7
0
,

 
 
5
,

 
 
2
0
0
5
,

 
 
1
1
,

 
 
1
7
9
8
,

 
 
1
0
,

 
 
4
1
,

 
 
4
4
,

 
 
5
8
,

 
 
9
3
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
5
4
5
,

 
 
6
2
,

 
 
1
0
8
4
,

 
 
2
1
0
,

 
 
2
7
4
8
,

 
 
4
0
0
6
,

 
 
9
,

 
 
2
2
,

 
 
5
1
,

 
 
3
4
9
,

 
 
2
8
2
,

 
 
1
3
5
,

 
 
1
1
,

 
 
2
6
7
7
8
,

 
 
4
3
,

 
 
5
5
1
5
,

 
 
1
,

 
 
8
0
9
,

 
 
2
2
7
,

 
 
1
1
2
9
1
,

 
 
8
8
3
8
,

 
 
5
,

 
 
9
,

 
 
5
8
5
,

 
 
1
9
2
,

 
 
2
7
,

 
 
8
8
3
8
,

 
 
1
2
5
2
,

 
 
3
4
1
]
,

 
[
1
7
5
,
 
4
6
,
 
1
9
5
7
,
 
1
6
2
,
 
1
6
0
,
 
2
3
3
,
 
3
6
5
,
 
3
6
3
,
 
5
5
8
,
 
5
8
1
]
,

 
[
2
9
3
,

 
 
1
1
9
,

 
 
3
,

 
 
1
0
6
6
9
6
,

 
 
4
,

 
 
2
7
7
,

 
 
4
2
,

 
 
5
7
,

 
 
6
6
8
,

 
 
1
5
,

 
 
1
0
6
6
9
6
,

 
 
1
1
8
9
,

 
 
9
,

 
 
1
1
,

 
 
1
6
,

 
 
1
3
6
0
,

 
 
1
4
6
,

 
 
3
1
,

 
 
2
8
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
2
0
7
,

 
 
1
8
2
,

 
 
1
1
6
,

 
 
1
3
3
3
9
,

 
 
3
,

 
 
1
,

 
 
4
3
4
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
6
9
,

 
 
1
,

 
 
2
3
,

 
 
5
5
7
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
6
0
6
6
,

 
 
3
,

 
 
3
4
6
,

 
 
9
,

 
 
2
4
,

 
 
1
3
3
0
,

 
 
1
4
6
,

 
 
4
5
1
,

 
 
4
,

 
 
1
1
9
,

 
 
8
6
6
,

 
 
1
1
1
,

 
 
1
7
,

 
 
3
3
,

 
 
8
3
,

 
 
1
2
,

 
 
1
1
9
,

 
 
1
8
2
,

 
 
1
,

 
 
2
1
4
6
,

 
 
4
3
4
,

 
 
1
2
5
,

 
 
2
7
,

 
 
2
3
,

 
 
4
2
,

 
 
3
1
7
9
,

 
 
3
4
5
8
,

 
 
1
7
4
,

 
 
2
,

 
 
9
,

 
 
3
,

 
 
2
7
,

 
 
2
3
,

 
 
1
4
6
,

 
 
1
5
1
,

 
 
8
6
6
,

 
 
5
,

 
 
5
5
,

 
 
4
2
2
,

 
 
1
0
,

 
 
1
,

 
 
1
7
4
,

 
 
3
4
,

 
 
1
4
,

 
 
4
5
9
,

 
 
1
,

 
 
6
5
2
,

 
 
1
2
,

 
 
5
4
,

 
 
1
,

 
 
3
4
6
,

 
 
2
4
,

 
 
1
3
3
0
,

 
 
1
4
6
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
3
3
,

 
 
5
5
,

 
 
8
5
,

 
 
2
2
,

 
 
6
,

 
 
6
5
,

 
 
9
,

 
 
1
3
,

 
 
4
5
4
,

 
 
2
4
,

 
 
6
6
8
,

 
 
6
4
,

 
 
1
0
,

 
 
1
0
0
9
,

 
 
6
,

 
 
8
7
,

 
 
1
1
5
9
,

 
 
1
,

 
 
1
1
9
,

 
 
3
2
,

 
 
3
1
0
,

 
 
2
,

 
 
1
,

 
 
2
7
9
,

 
 
3
,

 
 
1
,

 
 
2
9
,

 
 
4
9
,

 
 
5
6
7
,

 
 
1
,

 
 
9
8
6
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
5
,

 
 
1
7
7
6
,

 
 
2
7
7
,

 
 
2
5
5
7
,

 
 
2
1
,

 
 
3
1
0
,

 
 
4
,

 
 
1
9
3
,

 
 
1
5
,

 
 
1
,

 
 
8
1
7
,

 
 
4
6
,

 
 
2
9
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
2
6
,

 
 
1
6
,

 
 
7
4
9
,

 
 
9
,

 
 
4
0
8
,

 
 
9
1
7
,

 
 
1
2
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
2
,

 
 
1
,

 
 
2
3
,

 
 
1
3
5
9
,

 
 
1
,

 
 
1
7
7
5
,

 
 
1
1
,

 
 
8
7
,

 
 
1
6
,

 
 
1
4
6
,

 
 
1
7
7
,

 
 
2
1
9
0
,

 
 
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
,

 
 
2
9
3
,

 
 
1
1
9
,

 
 
2
7
7
,

 
 
2
2
5
,

 
 
2
6
,

 
 
5
9
,

 
 
1
5
2
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
0
5
,

 
 
2
,

 
 
1
,

 
 
2
3
,

 
 
9
,

 
 
4
3
,

 
 
4
3
,

 
 
2
8
9
4
,

 
 
1
1
,

 
 
5
8
,

 
 
1
0
,

 
 
3
4
0
7
,

 
 
2
1
,

 
 
5
0
8
,

 
 
5
7
0
,

 
 
5
,

 
 
4
2
7
,

 
 
4
6
]
,

 
[
1
4
6
5
,

 
 
6
,

 
 
1
9
,

 
 
2
,

 
 
1
6
,

 
 
4
,

 
 
1
8
5
3
,

 
 
9
0
8
,

 
 
3
4
9
8
,

 
 
5
4
,

 
 
7
2
,

 
 
1
6
5
,

 
 
2
,

 
 
8
5
9
,

 
 
8
,

 
 
1
4
,

 
 
2
6
,

 
 
6
2
,

 
 
2
4
9
4
,

 
 
4
9
5
]
,

 
[
2
2
6
3
,

 
 
1
2
,

 
 
1
,

 
 
2
6
2
,

 
 
8
5
,

 
 
4
6
3
,

 
 
8
9
,

 
 
5
9
,

 
 
6
7
,

 
 
7
3
,

 
 
7
,

 
 
2
7
6
,

 
 
9
,

 
 
1
0
,

 
 
1
,

 
 
2
2
1
,

 
 
4
4
1
,

 
 
1
1
0
,

 
 
9
8
,

 
 
1
4
5
1
,

 
 
5
,

 
 
9
8
,

 
 
1
1
6
6
]
,

 
[
7
,

 
 
2
7
5
,

 
 
2
0
,

 
 
5
7
5
,

 
 
5
,

 
 
6
5
,

 
 
9
,

 
 
2
0
,

 
 
1
4
5
,

 
 
8
,

 
 
1
5
5
8
,

 
 
8
7
0
,

 
 
1
9
7
,

 
 
7
,

 
 
5
9
,

 
 
8
9
8
8
,

 
 
6
9
8
9
3
,

 
 
6
9
8
9
4
,

 
 
4
,

 
 
1
0
2
7
,

 
 
3
,

 
 
2
8
,

 
 
9
6
,

 
 
2
1
,

 
 
1
,

 
 
9
2
6
,

 
 
3
,

 
 
8
8
5
,

 
 
1
0
6
,

 
 
1
2
,

 
 
9
,

 
 
1
2
1
7
,

 
 
1
0
,

 
 
1
,

 
 
2
5
1
,

 
 
3
6
1
,

 
 
2
3
1
,

 
 
6
5
,

 
 
5
8
,

 
 
3
5
,

 
 
1
3
,

 
 
2
3
2
1
,

 
 
1
3
4
,

 
 
6
,

 
 
1
2
,

 
 
9
5
8
,

 
 
2
0
,

 
 
5
7
5
,

 
 
2
,

 
 
3
7
,

 
 
2
1
,

 
 
1
1
1
,

 
 
8
8
7
,

 
 
1
1
7
7
,

 
 
2
2
1
,

 
 
6
4
7
,

 
 
8
0
7
7
]
,

 
[
6
,

 
 
1
6
1
0
0
1
,

 
 
5
8
9
,

 
 
7
0
1
4
,

 
 
1
6
8
,

 
 
1
7
1
,

 
 
4
2
4
0
2
,

 
 
3
7
,

 
 
4
6
3
,

 
 
1
0
4
,

 
 
4
,

 
 
3
0
5
5
,

 
 
1
5
1
0
3
,

 
 
4
9
4
8
7
,

 
 
1
,

 
 
1
0
6
5
0
,

 
 
1
1
5
7
5
,

 
 
4
9
4
8
8
,

 
 
2
0
,

 
 
1
1
5
7
6
,

 
 
1
1
1
3
,

 
 
6
,

 
 
2
4
0
,

 
 
6
9
8
9
5
,

 
 
1
3
9
2
,

 
 
7
,

 
 
6
9
8
9
5
]
,

 
[
9
5
,
 
1
0
7
,
 
4
6
,
 
1
6
1
0
0
2
,
 
1
8
,
 
4
1
,
 
5
5
,
 
1
5
9
3
,
 
1
4
0
,
 
5
7
7
1
,
 
2
1
3
,
 
3
7
5
,
 
3
9
7
4
0
]
,

 
[
1
2
,

 
 
2
5
9
,

 
 
5
5
4
,

 
 
1
0
,

 
 
8
8
7
,

 
 
1
4
,

 
 
2
8
7
0
,

 
 
1
5
6
8
,

 
 
1
0
5
,

 
 
3
5
,

 
 
1
,

 
 
1
9
3
0
,

 
 
3
4
1
5
,

 
 
3
7
7
0
,

 
 
7
,

 
 
2
6
5
,

 
 
1
4
,

 
 
1
,

 
 
2
4
6
3
,

 
 
9
,

 
 
4
5
,

 
 
4
4
,

 
 
8
9
3
,

 
 
7
3
0
,

 
 
1
6
,

 
 
1
3
3
6
,

 
 
6
4
,

 
 
6
3
,

 
 
3
1
2
,

 
 
3
8
3
2
,

 
 
2
4
3
,

 
 
4
5
5
8
5
,

 
 
1
0
6
6
9
7
,

 
 
3
0
,

 
 
3
9
0
5
,

 
 
3
4
1
,

 
 
4
2
,

 
 
8
9
,

 
 
5
7
,

 
 
2
9
6
3
,

 
 
1
8
7
,

 
 
3
1
,

 
 
6
1
5
,

 
 
6
3
8
,

 
 
5
9
1
8
,

 
 
3
2
,

 
 
6
0
,

 
 
1
4
1
8
2
,

 
 
1
2
8
5
1
,

 
 
1
,

 
 
6
5
6
,

 
 
4
5
,

 
 
8
7
4
4
]
,

 
[
6
,

 
 
1
6
7
,

 
 
7
,

 
 
8
1
,

 
 
2
6
5
6
,

 
 
9
,

 
 
1
,

 
 
2
9
,

 
 
4
5
,

 
 
1
4
,

 
 
5
4
3
8
8
,

 
 
2
,

 
 
1
3
,

 
 
1
2
7
,

 
 
5
,

 
 
7
,

 
 
4
5
,

 
 
3
5
6
,

 
 
2
1
5
,

 
 
1
1
3
5
,

 
 
9
,

 
 
1
0
6
6
9
8
,

 
 
1
,

 
 
9
8
,

 
 
6
0
8
3
1
,

 
 
9
,

 
 
8
,

 
 
8
9
,

 
 
9
1
,

 
 
1
3
1
,

 
 
4
,

 
 
5
7
4
,

 
 
1
1
3
5
,

 
 
3
4
5
,

 
 
1
0
,

 
 
1
,

 
 
7
2
9
,

 
 
3
,

 
 
4
,

 
 
4
2
8
4
,

 
 
1
3
8
,

 
 
1
2
7
3
0
,

 
 
2
,

 
 
3
4
,

 
 
4
9
,

 
 
9
,

 
 
1
,

 
 
2
4
9
,

 
 
8
,

 
 
9
,

 
 
6
,

 
 
1
8
,

 
 
1
4
,

 
 
1
,

 
 
3
6
2
6
,

 
 
1
7
7
7
8
,

 
 
3
,

 
 
1
3
,

 
 
2
5
,

 
 
5
5
,

 
 
4
6
,

 
 
2
9
,

 
 
1
,

 
 
3
4
5
,

 
 
2
4
,

 
 
1
8
7
4
2
,

 
 
5
,

 
 
9
0
,

 
 
1
4
,

 
 
2
1
5
5
,

 
 
1
,

 
 
2
8
0
6
,

 
 
3
,

 
 
1
,

 
 
1
4
6
1
,

 
 
1
1
5
1
,

 
 
6
2
1
,

 
 
9
0
,

 
 
1
1
,

 
 
3
7
7
6
,

 
 
1
,

 
 
3
0
9
1
,

 
 
3
,

 
 
1
3
8
,

 
 
1
5
,

 
 
1
,

 
 
2
9
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
,

 
 
1
3
2
,

 
 
4
8
1
,

 
 
6
3
9
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
2
,

 
 
4
9
,

 
 
1
2
8
4
,

 
 
1
1
,

 
 
3
2
,

 
 
5
3
0
,

 
 
1
1
,

 
 
6
,

 
 
4
9
,

 
 
2
4
3
8
,

 
 
4
,

 
 
2
6
1
3
,

 
 
6
,

 
 
2
4
4
6
,

 
 
3
7
,

 
 
3
,

 
 
1
0
1
7
3
,

 
 
5
4
,

 
 
8
,

 
 
2
8
1
5
,

 
 
1
,

 
 
4
2
7
,

 
 
1
8
,

 
 
4
1
,

 
 
2
,

 
 
1
2
1
,

 
 
1
9
1
,

 
 
4
0
,

 
 
1
9
7
,

 
 
1
4
,

 
 
7
7
,

 
 
3
4
,

 
 
6
,

 
 
2
1
5
5
,

 
 
9
,

 
 
1
2
1
8
,

 
 
2
6
,

 
 
6
6
,

 
 
4
3
0
,

 
 
5
7
0
,

 
 
1
1
,

 
 
8
,

 
 
1
3
,

 
 
4
4
9
,

 
 
3
,

 
 
2
3
3
4
,

 
 
4
6
8
9
,

 
 
8
5
1
,

 
 
9
,

 
 
7
7
4
3
,

 
 
7
5
,

 
 
2
,

 
 
6
4
0
9
,

 
 
2
1
,

 
 
2
4
9
,

 
 
1
4
0
,

 
 
1
1
,

 
 
8
,

 
 
4
,

 
 
2
5
0
,

 
 
2
6
0
6
,

 
 
2
6
4
7
,

 
 
9
,

 
 
5
3
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
6
1
,

 
 
4
1
0
,

 
 
1
2
1
3
,

 
 
5
,

 
 
1
0
,

 
 
3
0
,

 
 
4
2
0
,

 
 
2
7
4
,

 
 
6
4
,

 
 
7
,

 
 
1
9
,

 
 
1
9
9
,

 
 
4
4
6
,

 
 
1
1
,

 
 
2
0
7
,

 
 
8
0
,

 
 
1
1
,

 
 
5
9
3
,

 
 
2
1
7
,

 
 
5
6
5
,

 
 
6
,

 
 
3
9
,

 
 
2
5
8
,

 
 
3
7
,

 
 
4
,

 
 
1
2
8
,

 
 
2
0
1
,

 
 
2
1
2
,

 
 
1
2
,

 
 
1
4
,

 
 
2
9
8
,

 
 
3
6
,

 
 
7
,

 
 
8
1
,

 
 
1
6
5
,

 
 
2
,

 
 
7
6
7
9
,

 
 
1
,

 
 
1
4
6
,

 
 
2
5
3
]
,

 
[
1
,

 
 
1
6
1
0
0
3
,

 
 
1
9
2
6
,

 
 
1
4
4
4
,

 
 
3
,

 
 
1
2
0
1
,

 
 
4
2
,

 
 
3
4
8
4
,

 
 
7
6
,

 
 
4
,

 
 
2
8
4
2
,

 
 
3
,

 
 
1
,

 
 
2
8
4
,

 
 
2
5
0
2
,

 
 
1
1
,

 
 
8
,

 
 
4
4
,

 
 
3
8
6
1
,

 
 
9
,

 
 
1
1
6
3
,

 
 
1
0
7
2
0
,

 
 
1
1
1
,

 
 
1
7
,

 
 
1
,

 
 
2
5
0
2
,

 
 
8
3
4
,

 
 
2
,

 
 
1
3
,

 
 
3
0
3
,

 
 
4
7
,

 
 
3
0
3
,

 
 
1
7
5
,

 
 
2
8
4
,

 
 
2
5
0
2
,

 
 
4
5
,

 
 
6
3
8
8
,

 
 
4
0
,

 
 
1
,

 
 
1
1
0
,

 
 
3
1
5
,

 
 
1
,

 
 
2
4
4
,

 
 
4
9
5
,

 
 
8
5
6
,

 
 
1
5
2
,

 
 
8
7
7
,

 
 
3
,

 
 
1
7
5
,

 
 
1
1
7
8
,

 
 
9
9
3
3
,

 
 
2
8
4
2
]
,

 
[
1
4
7
1
5
,

 
 
4
3
,

 
 
6
,

 
 
2
6
7
1
,

 
 
1
7
1
,

 
 
4
5
1
,

 
 
3
0
,

 
 
3
0
6
,

 
 
4
6
0
,

 
 
5
,

 
 
7
1
8
,

 
 
2
1
8
,

 
 
1
9
2
,

 
 
3
0
,

 
 
1
0
7
,

 
 
2
9
,

 
 
5
1
8
2
,

 
 
6
,

 
 
2
8
2
,

 
 
2
1
5
,

 
 
2
0
1
,

 
 
2
,

 
 
3
4
,

 
 
9
3
,

 
 
2
3
3
6
,

 
 
7
5
,

 
 
1
9
2
,

 
 
1
5
,

 
 
2
8
]
,

 
[
3
6
,

 
 
2
7
2
0
,

 
 
1
1
9
6
3
,

 
 
1
2
5
0
,

 
 
1
3
7
6
1
,

 
 
4
4
4
,

 
 
7
,

 
 
6
3
,

 
 
6
,

 
 
1
8
,

 
 
1
5
3
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
2
,

 
 
3
5
1
,

 
 
1
8
3
,

 
 
3
0
3
,

 
 
2
9
0
,

 
 
4
,

 
 
1
1
9
4
,

 
 
2
0
2
2
2
,

 
 
7
6
,

 
 
3
,

 
 
2
2
5
,

 
 
1
7
,

 
 
2
2
8
4
,

 
 
7
,

 
 
5
9
,

 
 
7
0
,

 
 
3
8
,

 
 
8
,

 
 
3
2
2
0
4
,

 
 
6
4
,

 
 
6
,

 
 
2
5
,

 
 
1
,

 
 
2
2
1
0
,

 
 
5
1
5
4
,

 
 
6
4
0
5
,

 
 
6
,

 
 
3
1
4
,

 
 
3
2
,

 
 
1
5
6
9
9
,

 
 
1
,

 
 
2
4
4
,

 
 
3
5
,

 
 
6
2
5
8
,

 
 
3
1
0
9
,

 
 
1
2
,

 
 
2
0
,

 
 
1
4
4
5
,

 
 
9
0
6
,

 
 
2
,

 
 
1
0
9
5
,

 
 
1
7
5
,

 
 
1
0
1
4
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
6
2
5
8
,

 
 
3
1
0
9
,

 
 
2
,

 
 
1
5
6
7
,

 
 
2
0
,

 
 
3
0
0
,

 
 
2
6
,

 
 
7
1
,

 
 
6
3
4
,

 
 
1
7
,

 
 
1
,

 
 
1
7
1
3
,

 
 
7
5
0
3
,

 
 
1
6
7
,

 
 
2
8
5
,

 
 
1
1
,

 
 
1
,

 
 
6
0
8
3
2
,

 
 
2
5
9
6
8
,

 
 
3
6
9
,

 
 
2
6
7
7
9
,

 
 
1
,

 
 
4
2
4
0
3
,

 
 
4
5
,

 
 
6
,

 
 
3
4
9
,

 
 
1
5
7
9
,

 
 
9
3
1
,

 
 
5
3
,

 
 
1
8
4
,

 
 
4
0
,

 
 
1
1
6
6
5
,

 
 
4
,

 
 
2
3
5
,

 
 
1
6
6
0
,

 
 
1
2
,

 
 
1
7
5
,

 
 
1
6
6
6
,

 
 
2
0
8
2
,

 
 
6
,

 
 
1
6
4
1
,

 
 
9
6
4
2
,

 
 
3
7
,

 
 
2
1
,

 
 
3
0
6
,

 
 
2
7
0
,

 
 
6
,

 
 
3
5
0
]
,

 
[
3
5
5
,

 
 
1
5
6
,

 
 
4
5
,

 
 
1
7
4
7
2
,

 
 
7
,

 
 
2
3
7
,

 
 
4
8
5
,

 
 
1
,

 
 
1
6
8
7
,

 
 
8
8
4
,

 
 
3
3
9
6
,

 
 
3
3
5
,

 
 
1
4
8
,

 
 
1
5
4
,

 
 
1
3
5
,

 
 
8
8
4
,

 
 
1
1
6
,

 
 
7
,

 
 
4
6
8
,

 
 
3
9
9
,

 
 
1
3
0
9
4
,

 
 
1
9
6
,

 
 
5
,

 
 
8
7
7
,

 
 
4
9
7
,

 
 
1
1
6
,

 
 
5
1
9
]
,

 
[
7
8
2
0
,
 
1
,
 
4
2
,
 
1
5
7
0
0
,
 
1
4
1
,
 
1
3
9
2
2
,
 
2
8
0
,
 
1
2
,
 
1
,
 
1
6
2
5
,
 
3
0
0
9
,
 
5
3
6
1
]
,

 
[
7
,

 
 
1
1
7
6
,

 
 
1
,

 
 
1
6
9
,

 
 
1
1
,

 
 
6
5
1
,

 
 
4
0
,

 
 
3
,

 
 
3
5
,

 
 
2
3
3
,

 
 
3
3
4
6
,

 
 
8
9
,

 
 
3
1
7
,

 
 
1
1
,

 
 
2
5
,

 
 
7
,

 
 
4
5
,

 
 
5
7
6
,

 
 
6
,

 
 
2
,

 
 
1
,

 
 
1
2
5
3
]
,

 
[
1
7
,

 
 
7
,

 
 
1
9
,

 
 
7
7
8
,

 
 
5
1
,

 
 
8
6
,

 
 
1
4
,

 
 
4
5
9
5
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
1
0
,

 
 
3
0
,

 
 
2
0
6
5
,

 
 
3
0
,

 
 
9
8
9
,

 
 
1
9
,

 
 
5
7
,

 
 
4
1
9
8
,

 
 
5
3
7
9
,

 
 
5
0
0
,

 
 
7
,

 
 
1
6
1
0
0
4
,

 
 
9
8
,

 
 
5
8
8
,

 
 
1
0
,

 
 
1
1
6
2
,

 
 
8
8
,

 
 
1
7
,

 
 
7
,

 
 
1
9
,

 
 
4
4
5
,

 
 
9
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
2
5
6
,

 
 
1
7
4
,

 
 
3
1
,

 
 
1
2
4
,

 
 
1
7
7
,

 
 
7
3
3
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
8
3
7
0
1
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
2
0
4
5
,

 
 
1
1
5
2
]
,

 
[
1
4
6
,

 
 
4
2
8
,

 
 
2
4
0
5
,

 
 
4
7
8
,

 
 
7
1
,

 
 
5
9
3
5
,

 
 
2
,

 
 
3
7
,

 
 
9
,

 
 
1
,

 
 
4
7
9
,

 
 
3
,

 
 
1
3
,

 
 
2
3
,

 
 
1
8
4
,

 
 
5
1
4
,

 
 
6
0
,

 
 
6
6
5
7
,

 
 
3
7
7
7
,

 
 
2
,

 
 
6
5
,

 
 
1
3
,

 
 
8
,

 
 
3
8
,

 
 
1
,

 
 
4
2
8
,

 
 
2
4
0
5
,

 
 
4
7
8
,

 
 
8
,

 
 
1
2
,

 
 
3
9
5
,

 
 
4
,

 
 
1
6
1
6
2
,

 
 
1
3
8
,

 
 
3
3
,

 
 
1
,

 
 
9
8
0
3
,

 
 
4
6
,

 
 
2
9
,

 
 
3
5
,

 
 
3
8
,

 
 
5
6
,

 
 
1
6
,

 
 
1
0
,

 
 
1
,

 
 
4
7
8
,

 
 
2
6
,

 
 
9
6
,

 
 
1
,

 
 
1
3
2
,

 
 
2
3
1
8
6
,

 
 
5
9
1
,

 
 
3
,

 
 
1
,

 
 
4
7
8
,

 
 
1
8
1
,

 
 
3
9
7
4
1
,

 
 
1
3
]
,

 
[
1
0
6
6
9
9
,

 
 
3
,

 
 
2
8
6
7
9
,

 
 
4
9
1
,

 
 
3
3
,

 
 
2
8
6
7
9
,

 
 
3
7
0
,

 
 
1
4
,

 
 
4
9
,

 
 
3
7
,

 
 
6
1
,

 
 
2
8
6
7
9
,

 
 
4
5
,

 
 
1
4
0
1
,

 
 
1
5
7
,

 
 
2
0
,

 
 
1
2
9
0
,

 
 
3
,

 
 
1
3
5
6
,

 
 
3
9
5
0
,

 
 
3
,

 
 
2
2
7
,

 
 
2
2
5
3
,

 
 
5
7
4
7
,

 
 
3
9
0
6
,

 
 
6
1
6
,

 
 
8
3
7
0
2
,

 
 
5
,

 
 
3
8
,

 
 
1
5
5
0
,

 
 
4
0
0
]
,

 
[
4
9
,

 
 
2
,

 
 
1
5
2
,

 
 
5
5
8
4
,

 
 
2
5
3
0
,

 
 
8
0
,

 
 
7
,

 
 
1
6
7
,

 
 
6
,

 
 
1
3
1
,

 
 
1
,

 
 
8
3
7
0
3
,

 
 
1
0
9
0
,

 
 
3
,

 
 
8
2
5
,

 
 
1
1
,

 
 
4
,

 
 
4
6
5
1
,

 
 
8
0
,

 
 
1
1
,

 
 
2
4
,

 
 
1
0
,

 
 
1
6
6
,

 
 
4
,

 
 
8
3
7
0
4
,

 
 
8
,

 
 
6
9
,

 
 
1
7
,

 
 
6
,

 
 
4
1
6
,

 
 
7
6
,

 
 
1
7
,

 
 
2
2
8
4
,

 
 
3
0
,

 
 
3
4
5
,

 
 
1
0
,

 
 
5
4
,

 
 
6
,

 
 
2
9
3
7
,

 
 
1
,

 
 
4
2
0
,

 
 
8
3
7
0
5
,

 
 
1
7
,

 
 
3
5
5
,

 
 
5
7
,

 
 
6
9
8
9
6
,

 
 
3
3
,

 
 
1
,

 
 
4
6
5
1
,

 
 
6
9
4
,

 
 
5
4
3
8
9
,

 
 
2
1
,

 
 
1
2
9
6
7
,

 
 
1
6
1
0
0
5
,

 
 
1
,

 
 
4
6
5
1
,

 
 
3
,

 
 
5
4
3
8
9
,

 
 
2
4
,

 
 
4
,

 
 
1
7
0
7
,

 
 
4
6
5
1
,

 
 
7
7
,

 
 
3
2
9
,

 
 
1
,

 
 
8
3
7
0
5
,

 
 
3
,

 
 
3
0
8
4
7
,

 
 
5
,

 
 
1
6
9
7
,

 
 
5
,

 
 
1
3
1
,

 
 
4
,

 
 
9
7
1
,

 
 
5
2
6
8
,

 
 
1
0
,

 
 
1
0
6
7
0
0
,

 
 
1
2
7
,

 
 
5
3
,

 
 
1
8
,

 
 
1
0
6
7
0
1
,

 
 
1
5
,

 
 
1
,

 
 
5
4
3
9
0
,

 
 
3
0
1
2
,

 
 
1
7
1
,

 
 
9
4
4
,

 
 
1
,

 
 
2
5
7
,

 
 
6
,

 
 
3
8
3
,

 
 
1
8
,

 
 
1
0
5
1
,

 
 
1
0
6
7
0
2
,

 
 
8
6
3
,

 
 
5
,

 
 
7
,

 
 
2
1
1
,

 
 
2
0
,

 
 
1
2
1
3
,

 
 
1
8
,

 
 
3
5
7
9
,

 
 
2
9
2
3
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
8
8
,

 
 
2
,

 
 
1
9
4
3
7
,

 
 
4
,

 
 
1
2
4
3
,

 
 
6
3
3
,

 
 
5
3
,

 
 
2
1
0
,

 
 
1
3
0
1
,

 
 
1
,

 
 
8
3
7
0
4
,

 
 
5
,

 
 
4
6
5
1
,

 
 
3
,

 
 
5
4
3
8
9
,

 
 
8
6
,

 
 
2
7
1
,

 
 
7
,

 
 
1
9
9
5
,

 
 
2
0
,

 
 
4
5
7
,

 
 
8
0
,

 
 
6
,

 
 
2
9
3
7
,

 
 
1
,

 
 
4
2
0
,

 
 
8
3
7
0
5
,

 
 
1
7
,

 
 
6
0
8
3
3
,

 
 
6
9
8
9
6
,

 
 
3
3
,

 
 
1
,

 
 
4
6
5
1
,

 
 
3
,

 
 
5
4
3
8
9
,

 
 
5
0
1
,

 
 
2
8
3
,

 
 
1
7
1
,

 
 
2
1
,

 
 
2
0
,

 
 
3
3
5
4
,

 
 
2
4
2
,

 
 
6
1
9
,

 
 
7
,

 
 
1
6
1
0
0
6
,

 
 
6
,

 
 
2
,

 
 
2
5
8
,

 
 
1
0
6
,

 
 
4
5
6
,

 
 
9
,

 
 
3
0
8
4
7
,

 
 
2
6
4
2
,

 
 
2
5
1
8
,

 
 
3
2
5
7
,

 
 
1
7
,

 
 
1
1
3
0
,

 
 
3
,

 
 
1
6
9
7
,

 
 
2
6
,

 
 
6
,

 
 
2
5
8
,

 
 
2
4
6
2
,

 
 
4
5
6
,

 
 
1
,

 
 
4
6
5
1
,

 
 
3
,

 
 
5
4
3
8
9
,

 
 
5
,

 
 
7
3
3
2
,

 
 
7
3
,

 
 
1
,

 
 
1
2
1
3
,

 
 
2
2
,

 
 
6
,

 
 
1
6
9
4
,

 
 
2
6
2
6
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
3
0
8
4
7
,

 
 
4
5
2
4
,

 
 
3
2
5
7
,

 
 
1
7
,

 
 
1
1
3
0
,

 
 
3
,

 
 
1
6
9
7
,

 
 
8
4
,

 
 
7
,

 
 
1
9
,

 
 
2
3
7
,

 
 
3
6
8
,

 
 
6
,

 
 
1
5
,

 
 
1
,

 
 
6
7
8
7
,

 
 
6
8
5
0
,

 
 
2
3
,

 
 
6
,

 
 
5
6
,

 
 
1
6
,

 
 
4
5
7
2
,

 
 
3
,

 
 
2
0
,

 
 
1
0
6
7
0
2
,

 
 
2
1
9
8
,

 
 
8
0
7
7
,

 
 
3
5
7
9
,

 
 
2
9
2
3
,

 
 
1
2
5
9
,

 
 
4
7
9
]
,

 
[
3
0
0
7
,

 
 
1
6
2
,

 
 
2
0
9
,

 
 
1
4
9
,

 
 
6
4
5
4
,

 
 
2
,

 
 
9
0
9
,

 
 
5
8
,

 
 
9
3
,

 
 
4
0
8
,

 
 
1
0
,

 
 
4
,

 
 
2
6
3
7
,

 
 
7
,

 
 
1
9
,

 
 
4
4
,

 
 
4
0
5
,

 
 
3
8
,

 
 
6
,

 
 
1
8
,

 
 
6
0
9
,

 
 
3
5
,

 
 
7
,

 
 
1
9
,

 
 
1
4
,

 
 
1
3
3
,

 
 
2
7
,

 
 
6
4
5
4
,

 
 
5
,

 
 
7
,

 
 
1
9
,

 
 
1
9
9
,

 
 
2
8
3
2
,

 
 
1
0
,

 
 
5
5
,

 
 
2
6
3
7
,

 
 
1
6
0
,

 
 
7
,

 
 
3
9
,

 
 
1
4
,

 
 
1
6
,

 
 
4
,

 
 
8
1
1
,

 
 
1
7
,

 
 
7
,

 
 
1
9
,

 
 
1
4
,

 
 
4
6
0
5
,

 
 
2
1
5
,

 
 
7
,

 
 
8
7
,

 
 
1
9
,

 
 
1
7
3
,

 
 
1
7
4
,

 
 
5
4
,

 
 
6
,

 
 
2
5
,

 
 
1
5
8
,

 
 
3
3
1
,

 
 
9
0
,

 
 
1
4
,

 
 
2
6
3
,

 
 
1
3
,

 
 
8
,

 
 
1
4
,

 
 
2
1
7
,

 
 
1
,

 
 
3
7
4
,

 
 
2
5
1
6
7
,

 
 
8
,

 
 
1
3
8
,

 
 
5
,

 
 
8
6
6
,

 
 
2
,

 
 
3
4
0
3
,

 
 
4
,

 
 
8
3
7
0
6
,

 
 
2
3
3
,

 
 
1
2
7
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
4
,

 
 
1
2
5
4
,

 
 
2
5
,

 
 
4
,

 
 
2
5
1
6
8
,

 
 
7
,

 
 
1
9
,

 
 
5
7
,

 
 
1
3
0
2
,

 
 
7
0
9
,

 
 
9
,

 
 
7
,

 
 
8
1
,

 
 
1
,

 
 
1
3
9
,

 
 
2
2
2
,

 
 
3
2
,

 
 
5
0
8
,

 
 
1
7
7
7
9
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
4
,

 
 
1
2
5
4
,

 
 
2
5
,

 
 
1
6
1
0
0
7
,

 
 
6
,

 
 
8
7
,

 
 
4
2
4
0
4
,

 
 
2
,

 
 
8
2
,

 
 
4
,

 
 
2
7
1
,

 
 
1
7
7
7
9
,

 
 
2
6
,

 
 
9
,

 
 
8
,

 
 
4
9
,

 
 
2
0
,

 
 
3
2
7
,

 
 
5
,

 
 
3
7
4
3
8
,

 
 
1
6
9
0
,

 
 
4
8
1
,

 
 
1
2
,

 
 
2
7
,

 
 
7
5
3
]
,

 
[
8
3
7
0
7
,

 
 
3
3
6
,

 
 
1
2
,

 
 
4
,

 
 
3
8
9
6
,

 
 
2
0
8
,

 
 
9
1
,

 
 
4
2
4
0
5
,

 
 
1
5
,

 
 
3
6
3
8
,

 
 
3
6
3
,

 
 
2
4
,

 
 
3
6
6
2
,

 
 
1
7
,

 
 
2
4
,

 
 
6
8
,

 
 
3
3
6
,

 
 
9
,

 
 
5
2
,

 
 
1
6
,

 
 
8
1
9
,

 
 
2
,

 
 
4
5
8
,

 
 
6
8
,

 
 
1
4
4
8
,

 
 
2
9
,

 
 
5
5
8
5
,

 
 
9
3
6
2
,

 
 
2
4
,

 
 
3
5
6
3
,

 
 
1
8
4
7
,

 
 
1
3
8
3
,

 
 
1
1
0
6
3
,

 
 
4
9
9
7
,

 
 
5
,

 
 
1
0
6
7
0
3
,

 
 
5
4
7
,

 
 
1
,

 
 
4
0
,

 
 
1
1
6
6
,

 
 
2
2
1
2
4
,

 
 
1
5
,

 
 
3
6
3
8
,

 
 
3
6
3
,

 
 
5
5
8
,

 
 
2
9
,

 
 
7
3
8
9
,

 
 
4
9
4
8
9
,

 
 
2
0
3
,

 
 
8
9
,

 
 
4
9
1
,

 
 
3
3
,

 
 
1
8
1
9
,

 
 
1
0
,

 
 
3
3
5
6
,

 
 
7
,

 
 
6
3
,

 
 
9
,

 
 
4
1
,

 
 
8
,

 
 
4
,

 
 
6
2
0
8
,

 
 
3
,

 
 
1
3
8
4
,

 
 
1
0
5
,

 
 
3
5
,

 
 
2
1
0
,

 
 
9
3
6
2
,

 
 
5
,

 
 
8
3
7
0
7
,

 
 
6
9
8
9
7
,

 
 
9
,

 
 
1
0
3
,

 
 
1
6
,

 
 
5
0
2
,

 
 
3
6
,

 
 
7
,

 
 
4
5
,

 
 
1
4
2
,

 
 
1
5
,

 
 
1
6
9
3
,

 
 
4
0
,

 
 
9
,

 
 
1
0
,

 
 
5
8
,

 
 
1
1
7
7
,

 
 
2
3
2
1
]
,

 
[
2
9
6
,

 
 
7
,

 
 
4
8
,

 
 
1
,

 
 
1
2
5
7
,

 
 
6
6
,

 
 
1
1
,

 
 
5
2
6
,

 
 
5
2
1
,

 
 
9
8
,

 
 
5
,

 
 
3
2
,

 
 
2
3
1
0
,

 
 
1
3
5
,

 
 
1
,

 
 
4
9
0
,

 
 
4
6
5
,

 
 
3
5
,

 
 
1
,

 
 
2
6
7
8
0
,

 
 
1
2
7
3
6
,

 
 
7
6
8
0
,

 
 
1
1
,

 
 
1
2
6
1
4
,

 
 
2
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
,

 
 
2
3
,

 
 
1
4
4
,

 
 
5
1
9
,

 
 
1
5
,

 
 
5
3
,

 
 
9
4
,

 
 
5
8
,

 
 
8
7
7
,

 
 
1
5
,

 
 
1
,

 
 
1
1
7
3
9
,

 
 
1
6
1
0
0
8
,

 
 
2
3
1
,

 
 
4
9
,

 
 
7
9
,

 
 
1
0
6
7
0
4
,

 
 
1
2
5
7
,

 
 
1
0
]
,

 
[
7
8
0
,

 
 
3
9
2
3
,

 
 
2
0
,

 
 
2
3
,

 
 
8
,

 
 
1
5
,

 
 
1
,

 
 
4
2
2
0
,

 
 
3
,

 
 
9
1
,

 
 
1
4
6
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
4
7
,

 
 
3
3
,

 
 
1
,

 
 
1
1
9
,

 
 
1
3
8
,

 
 
2
0
3
3
,

 
 
1
2
,

 
 
1
0
4
,

 
 
9
1
,

 
 
1
3
9
8
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
5
5
,

 
 
2
2
6
,

 
 
3
,

 
 
1
5
2
4
,

 
 
1
3
,

 
 
2
3
,

 
 
9
1
0
,

 
 
3
8
2
,

 
 
3
,

 
 
4
1
1
0
,

 
 
2
0
,

 
 
8
5
,

 
 
1
2
9
,

 
 
1
,

 
 
4
6
,

 
 
2
9
,

 
 
1
4
2
6
,

 
 
1
5
,

 
 
1
3
,

 
 
1
6
9
,

 
 
2
,

 
 
1
1
8
,

 
 
2
,

 
 
1
,

 
 
1
1
9
,

 
 
1
3
8
,

 
 
5
,

 
 
9
7
,

 
 
2
0
,

 
 
1
0
2
0
]
,

 
[
4
7
0
3
,
 
4
2
3
4
,
 
4
5
6
2
,
 
1
6
1
0
0
9
]
,

 
[
6
0
,

 
 
3
0
3
,

 
 
6
,

 
 
5
,

 
 
7
,

 
 
1
8
,

 
 
1
6
5
,

 
 
2
,

 
 
5
8
4
,

 
 
1
3
,

 
 
5
,

 
 
2
8
9
3
,

 
 
1
3
0
9
,

 
 
1
3
0
9
,

 
 
1
3
0
9
,

 
 
1
3
0
9
,

 
 
1
3
0
9
,

 
 
1
9
9
,

 
 
1
6
8
9
,

 
 
7
,

 
 
1
9
,

 
 
5
9
3
5
,

 
 
6
6
2
,

 
 
7
,

 
 
8
1
,

 
 
5
8
,

 
 
3
1
5
3
,

 
 
9
3
,

 
 
6
,

 
 
3
9
,

 
 
9
9
3
,

 
 
1
8
9
7
,

 
 
2
7
8
,

 
 
3
7
,

 
 
4
9
,

 
 
8
7
4
,

 
 
1
3
,

 
 
2
0
2
4
,

 
 
3
2
,

 
 
1
9
4
3
8
,

 
 
6
,

 
 
4
,

 
 
9
3
5
7
,

 
 
1
6
6
5
6
,

 
 
5
4
2
7
]
,

 
[
5
0
5
,

 
 
2
8
8
,

 
 
6
5
8
,

 
 
1
,

 
 
9
0
7
,

 
 
1
2
8
5
2
,

 
 
1
5
9
0
,

 
 
2
2
,

 
 
6
,

 
 
1
0
3
,

 
 
2
4
6
,

 
 
2
7
,

 
 
1
5
8
9
,

 
 
7
6
,

 
 
1
2
,

 
 
5
8
,

 
 
5
6
6
,

 
 
1
5
3
5
,

 
 
1
0
5
,

 
 
1
5
,

 
 
1
0
,

 
 
5
6
6
,

 
 
1
2
8
5
2
,

 
 
5
,

 
 
8
4
,

 
 
1
3
5
1
,

 
 
1
,

 
 
9
0
7
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
2
8
4
,

 
 
7
2
,

 
 
9
4
2
0
,

 
 
1
1
,

 
 
1
9
2
,

 
 
3
,

 
 
4
,

 
 
6
1
8
,

 
 
9
0
7
,

 
 
1
0
,

 
 
1
,

 
 
4
,

 
 
5
9
8
,

 
 
1
1
0
3
,

 
 
3
,

 
 
1
0
7
2
9
,

 
 
3
3
3
0
,

 
 
5
4
,

 
 
6
9
7
,

 
 
1
,

 
 
7
0
8
,

 
 
3
,

 
 
1
0
5
,

 
 
2
,

 
 
1
1
8
,

 
 
1
2
,

 
 
1
7
7
,

 
 
5
3
7
7
,

 
 
1
3
5
,

 
 
1
,

 
 
3
7
4
4
4
,

 
 
8
2
9
5
]
,

 
[
5
1
2
7
,

 
 
1
5
4
8
8
,

 
 
1
6
8
,

 
 
1
0
3
0
2
,

 
 
4
0
9
6
,

 
 
4
,

 
 
1
1
0
,

 
 
4
8
,

 
 
2
5
0
,

 
 
8
5
,

 
 
4
8
,

 
 
8
5
,

 
 
4
9
4
8
8
,

 
 
4
8
9
,

 
 
2
5
0
,

 
 
6
9
8
9
8
,

 
 
2
2
7
,

 
 
2
6
,

 
 
3
3
7
1
5
,

 
 
1
0
6
7
0
5
,

 
 
2
7
,

 
 
5
7
4
2
,

 
 
7
3
0
,

 
 
1
0
9
8
2
,

 
 
1
6
8
6
,

 
 
1
6
1
0
1
0
,

 
 
1
5
7
,

 
 
3
5
4
1
9
,

 
 
4
1
7
8
,

 
 
4
,

 
 
5
4
4
,

 
 
1
0
6
7
0
6
,

 
 
1
9
0
7
1
,

 
 
1
0
6
7
0
7
,

 
 
1
8
7
4
3
,

 
 
8
3
7
0
8
,

 
 
9
3
1
,

 
 
2
5
,

 
 
2
9
1
6
,

 
 
9
9
0
,

 
 
3
5
,

 
 
2
,

 
 
1
4
8
3
,

 
 
4
,

 
 
1
2
2
8
9
,

 
 
1
1
6
5
0
,

 
 
2
,

 
 
3
2
8
,

 
 
1
5
,

 
 
6
8
,

 
 
3
3
7
4
,

 
 
1
6
8
6
,

 
 
1
8
7
4
3
,

 
 
1
1
5
7
7
,

 
 
1
9
3
9
,

 
 
3
7
,

 
 
6
0
8
3
4
,

 
 
1
5
4
,

 
 
4
,

 
 
3
9
7
4
2
,

 
 
7
2
0
3
,

 
 
3
7
,

 
 
1
0
6
7
0
8
,

 
 
5
7
4
3
,

 
 
5
4
4
,

 
 
1
2
2
8
9
,

 
 
1
6
1
0
1
1
,

 
 
1
6
,

 
 
5
7
5
3
,

 
 
5
7
4
2
,

 
 
3
4
,

 
 
1
3
2
,

 
 
2
9
7
1
7
,

 
 
5
4
4
,

 
 
6
0
8
3
5
,

 
 
2
7
7
2
1
,

 
 
1
6
1
0
1
2
,

 
 
1
4
,

 
 
4
0
,

 
 
2
6
,

 
 
1
3
2
,

 
 
5
4
4
,

 
 
2
5
0
2
,

 
 
6
0
8
3
5
,

 
 
1
6
3
2
,

 
 
2
3
1
8
7
,

 
 
1
5
6
6
,

 
 
3
4
,

 
 
7
3
9
,

 
 
5
7
4
3
,

 
 
4
4
,

 
 
2
8
8
0
,

 
 
5
2
,

 
 
4
9
4
9
0
,

 
 
1
6
,

 
 
1
6
1
0
1
3
,

 
 
6
7
0
5
,

 
 
2
1
8
3
,

 
 
3
6
,

 
 
4
,

 
 
1
0
5
1
4
,

 
 
1
6
1
0
1
4
,

 
 
3
0
8
4
8
,

 
 
1
6
1
0
1
5
,

 
 
1
6
8
,

 
 
1
6
,

 
 
5
4
3
9
1
,

 
 
1
4
2
8
,

 
 
4
,

 
 
1
6
1
0
1
6
,

 
 
5
4
3
9
2
,

 
 
4
,

 
 
7
2
0
3
,

 
 
1
9
0
7
1
,

 
 
5
7
4
2
,

 
 
1
1
8
,

 
 
3
2
2
,

 
 
9
8
,

 
 
6
0
8
3
6
,

 
 
1
6
1
0
1
7
,

 
 
2
,

 
 
1
2
1
9
,

 
 
4
1
7
8
,

 
 
4
9
4
9
1
,

 
 
1
6
1
0
1
8
,

 
 
4
,

 
 
9
1
0
7
,

 
 
4
,

 
 
5
4
3
9
2
,

 
 
3
1
6
3
,

 
 
9
8
,

 
 
1
9
0
7
1
,

 
 
6
0
8
3
6
,

 
 
1
0
6
7
0
9
,

 
 
5
3
2
8
,

 
 
3
5
8
4
,

 
 
1
0
6
7
1
0
,

 
 
1
8
4
,

 
 
3
0
8
4
8
,

 
 
4
9
4
9
0
,

 
 
5
3
2
8
,

 
 
1
6
1
0
1
9
,

 
 
4
0
,

 
 
1
0
6
7
1
1
,

 
 
1
0
6
7
1
2
,

 
 
1
9
4
3
9
,

 
 
7
2
0
4
,

 
 
3
8
4
1
,

 
 
1
9
0
7
1
,

 
 
4
,

 
 
1
6
1
0
2
0
,

 
 
1
6
1
0
2
1
,

 
 
1
6
1
0
2
2
,

 
 
3
8
,

 
 
5
3
,

 
 
5
4
3
9
3
,

 
 
2
4
4
7
8
,

 
 
1
0
6
7
0
5
,

 
 
2
5
1
6
9
,

 
 
5
7
4
3
]
,

 
[
6
,

 
 
9
0
,

 
 
1
4
,

 
 
4
5
8
,

 
 
3
7
,

 
 
1
0
5
4
,

 
 
3
5
2
,

 
 
5
3
,

 
 
1
9
2
9
,

 
 
1
,

 
 
4
0
8
,

 
 
1
0
,

 
 
4
,

 
 
5
4
3
9
,

 
 
1
1
0
5
,

 
 
2
,

 
 
6
3
,

 
 
1
9
1
,

 
 
4
6
]
,

 
[
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
,

 
 
1
,

 
 
3
2
5
7
,

 
 
1
2
6
5
,

 
 
6
0
8
3
7
,

 
 
2
9
,

 
 
1
1
,

 
 
8
,

 
 
4
1
9
,

 
 
2
1
7
,

 
 
2
2
,

 
 
6
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
1
2
2
9
,

 
 
8
2
,

 
 
1
,

 
 
6
1
2
,

 
 
1
3
4
,

 
 
6
]
,

 
[
2
6
4
,

 
 
8
6
5
6
,

 
 
8
9
4
2
,

 
 
3
,

 
 
1
,

 
 
9
7
4
5
,

 
 
1
,

 
 
1
2
0
,

 
 
8
,

 
 
4
,

 
 
1
4
3
2
,

 
 
3
,

 
 
4
2
5
1
,

 
 
1
4
3
7
9
,

 
 
4
2
5
1
,

 
 
1
4
3
7
9
,

 
 
3
2
1
6
,

 
 
1
6
1
6
3
,

 
 
1
6
1
0
2
3
,

 
 
5
7
2
2
,

 
 
5
4
4
,

 
 
1
6
1
0
2
4
,

 
 
1
5
,

 
 
1
,

 
 
7
8
3
,

 
 
5
,

 
 
6
3
5
,

 
 
5
2
7
2
,

 
 
5
2
9
8
,

 
 
3
,

 
 
1
,

 
 
1
0
2
1
,

 
 
6
2
0
,

 
 
1
4
5
5
,

 
 
2
,

 
 
1
,

 
 
3
1
7
1
,

 
 
1
2
5
,

 
 
4
,

 
 
1
1
6
,

 
 
8
,

 
 
4
4
8
0
,

 
 
2
,

 
 
1
,

 
 
1
6
1
0
2
5
,

 
 
3
,

 
 
1
,

 
 
2
0
4
5
,

 
 
7
1
9
,

 
 
5
,

 
 
3
9
7
,

 
 
1
9
3
,

 
 
3
,

 
 
7
4
,

 
 
1
,

 
 
1
0
6
7
1
3
,

 
 
3
,

 
 
1
6
1
0
2
6
,

 
 
3
7
4
4
5
,

 
 
9
9
,

 
 
1
7
7
8
0
,

 
 
1
3
3
4
0
,

 
 
2
,

 
 
3
4
,

 
 
1
1
,

 
 
3
3
0
,

 
 
6
8
,

 
 
3
1
9
1
,

 
 
5
,

 
 
7
4
,

 
 
1
1
,

 
 
2
4
,

 
 
5
1
9
,

 
 
1
3
3
,

 
 
3
2
,

 
 
2
1
9
9
,

 
 
1
5
,

 
 
6
8
,

 
 
6
8
5
5
,

 
 
1
3
1
1
,

 
 
1
,

 
 
6
5
6
,

 
 
5
2
,

 
 
2
0
3
,

 
 
1
4
8
4
,

 
 
1
5
,

 
 
1
1
1
2
,

 
 
1
5
8
2
,

 
 
1
1
,

 
 
9
6
,

 
 
2
8
6
,

 
 
3
6
,

 
 
1
0
,

 
 
4
,

 
 
3
3
7
,

 
 
9
,

 
 
7
,

 
 
1
9
,

 
 
4
7
9
,

 
 
3
5
,

 
 
1
4
7
7
,

 
 
2
1
9
9
,

 
 
1
6
2
,

 
 
1
4
7
7
,

 
 
2
1
9
9
,

 
 
3
0
4
7
,

 
 
1
4
8
,

 
 
2
3
9
3
,

 
 
5
6
9
,

 
 
1
2
7
3
7
,

 
 
3
,

 
 
1
4
7
9
,

 
 
1
6
0
,

 
 
2
1
9
9
,

 
 
2
1
4
0
,

 
 
1
0
,

 
 
1
1
5
,

 
 
1
2
4
6
,

 
 
5
,

 
 
1
0
6
7
1
4
,

 
 
5
4
7
,

 
 
6
8
,

 
 
1
6
1
0
2
7
,

 
 
5
7
0
1
,

 
 
2
1
4
3
,

 
 
9
7
9
,

 
 
2
0
6
,

 
 
2
4
,

 
 
1
7
3
,

 
 
3
2
,

 
 
2
3
6
7
,

 
 
7
8
4
7
,

 
 
6
8
0
8
,

 
 
5
6
6
8
,

 
 
1
1
2
4
,

 
 
1
0
,

 
 
1
4
3
8
0
,

 
 
2
8
,

 
 
5
0
,

 
 
1
5
2
,

 
 
1
6
9
,

 
 
1
1
2
4
,

 
 
1
4
3
8
0
,

 
 
1
0
,

 
 
7
0
2
1
,

 
 
1
1
6
,

 
 
9
5
]
,

 
[
1
,

 
 
7
9
7
6
,

 
 
5
6
5
4
,

 
 
3
4
6
,

 
 
1
,

 
 
6
1
5
8
,

 
 
9
0
2
,

 
 
2
,

 
 
4
,

 
 
1
2
5
5
,

 
 
1
0
,

 
 
2
9
7
1
8
,

 
 
1
8
7
9
,

 
 
1
0
,

 
 
1
,

 
 
8
9
8
,

 
 
6
6
2
9
,

 
 
4
3
0
2
,

 
 
4
,

 
 
8
0
2
,

 
 
3
,

 
 
7
2
6
7
,

 
 
3
1
6
,

 
 
1
2
5
2
1
,

 
 
5
1
,

 
 
6
6
,

 
 
3
0
5
9
,

 
 
6
0
,

 
 
4
0
2
5
,

 
 
9
,

 
 
6
0
,

 
 
2
0
6
7
,

 
 
2
5
9
3
,

 
 
1
0
4
7
,

 
 
6
3
3
5
,

 
 
3
,

 
 
1
,

 
 
1
4
0
5
8
,

 
 
1
4
9
0
2
,

 
 
2
4
6
9
,

 
 
5
,

 
 
9
2
6
6
,

 
 
1
2
,

 
 
1
7
7
8
1
,

 
 
1
4
7
5
,

 
 
7
9
9
,

 
 
6
4
,

 
 
8
,

 
 
4
,

 
 
1
3
8
,

 
 
3
,

 
 
4
7
,

 
 
3
,

 
 
1
,

 
 
6
5
5
7
,

 
 
2
9
4
1
,

 
 
4
,

 
 
5
4
3
9
4
,

 
 
3
1
6
,

 
 
4
,

 
 
2
9
7
1
9
,

 
 
7
8
1
3
,

 
 
1
0
,

 
 
4
,

 
 
1
4
7
2
5
,

 
 
2
6
9
4
,

 
 
5
4
,

 
 
8
,

 
 
4
,

 
 
4
4
9
,

 
 
3
,

 
 
4
,

 
 
1
6
1
0
2
8
,

 
 
3
,

 
 
3
6
6
3
,

 
 
7
2
0
5
,

 
 
4
9
6
,

 
 
3
,

 
 
1
0
6
7
1
5
,

 
 
2
6
,

 
 
2
1
,

 
 
8
5
1
9
,

 
 
1
0
6
7
1
6
,

 
 
5
,

 
 
1
7
4
7
3
,

 
 
5
,

 
 
9
8
0
4
,

 
 
5
,

 
 
5
3
6
,

 
 
4
,

 
 
2
9
7
1
9
,

 
 
7
8
1
3
,

 
 
1
0
,

 
 
4
,

 
 
1
4
7
2
5
,

 
 
2
6
9
4
,

 
 
7
,

 
 
1
2
1
0
,

 
 
3
8
,

 
 
6
0
8
3
8
,

 
 
3
8
9
2
,

 
 
1
5
,

 
 
3
4
0
9
,

 
 
6
6
0
6
,

 
 
5
,

 
 
1
0
6
7
1
7
,

 
 
8
]
,

 
[
4
4
,

 
 
7
,

 
 
2
3
9
,

 
 
2
7
6
,

 
 
1
4
5
,

 
 
3
7
,

 
 
3
3
,

 
 
4
,

 
 
3
5
2
4
,

 
 
2
3
,

 
 
2
3
8
,

 
 
9
,

 
 
4
3
,

 
 
1
6
,

 
 
9
8
,

 
 
1
5
5
,

 
 
7
,

 
 
2
7
6
,

 
 
5
2
5
,

 
 
1
4
3
,

 
 
6
4
,

 
 
1
5
,

 
 
1
,

 
 
1
3
8
,

 
 
2
9
,

 
 
3
8
,

 
 
1
6
0
7
,

 
 
8
6
,

 
 
6
,

 
 
9
0
8
,

 
 
1
0
,

 
 
5
4
,

 
 
1
8
7
9
,

 
 
9
0
,

 
 
6
,

 
 
1
1
8
,

 
 
2
,

 
 
6
6
,

 
 
4
5
6
,

 
 
1
4
8
,

 
 
1
,

 
 
2
7
9
,

 
 
7
,

 
 
7
8
9
,

 
 
7
,

 
 
6
5
,

 
 
1
,

 
 
2
3
,

 
 
1
0
3
,

 
 
3
4
,

 
 
2
1
,

 
 
3
7
1
,

 
 
4
,

 
 
3
5
9
,

 
 
5
8
,

 
 
2
7
4
7
,

 
 
1
7
,

 
 
1
0
3
,

 
 
1
,

 
 
8
3
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
1
9
1
2
,

 
 
6
,

 
 
4
4
5
,

 
 
1
7
,

 
 
1
2
,

 
 
2
7
8
4
,

 
 
8
0
9
,

 
 
2
8
6
8
0
,

 
 
7
,

 
 
1
9
,

 
 
2
,

 
 
1
5
6
2
,

 
 
3
6
7
,

 
 
1
9
9
,

 
 
8
2
0
,

 
 
1
4
1
,

 
 
5
4
2
,

 
 
7
4
,

 
 
1
8
,

 
 
6
,

 
 
4
4
1
7
,

 
 
9
,

 
 
1
1
7
,

 
 
4
4
1
0
,

 
 
8
3
7
0
9
,

 
 
8
,

 
 
2
0
1
,

 
 
9
3
,

 
 
4
,

 
 
1
2
6
5
,

 
 
8
3
7
1
0
,

 
 
8
,

 
 
1
1
,

 
 
3
2
,

 
 
2
1
1
6
,

 
 
2
0
5
5
,

 
 
1
0
7
9
,

 
 
2
5
,

 
 
4
9
,

 
 
2
4
2
,

 
 
3
2
7
,

 
 
3
,

 
 
9
2
,

 
 
4
7
5
7
]
,

 
[
9
3
7
,

 
 
2
6
,

 
 
7
7
,

 
 
2
2
,

 
 
5
1
,

 
 
1
8
,

 
 
1
6
4
1
,

 
 
1
4
,

 
 
6
6
3
,

 
 
1
3
9
,

 
 
7
0
8
,

 
 
3
,

 
 
8
9
5
,

 
 
4
7
9
7
,

 
 
4
4
,

 
 
1
2
8
8
,

 
 
3
2
1
,

 
 
1
3
4
,

 
 
6
,

 
 
4
6
]
,

 
[
2
8
0
9
,

 
 
1
6
4
,

 
 
6
6
5
,

 
 
7
,

 
 
2
7
6
,

 
 
1
6
4
,

 
 
8
1
9
,

 
 
2
,

 
 
3
4
,

 
 
1
1
,

 
 
2
6
,

 
 
7
2
,

 
 
4
9
,

 
 
9
3
1
0
,

 
 
7
,

 
 
6
5
0
,

 
 
7
,

 
 
1
2
6
,

 
 
6
8
5
,

 
 
2
0
,

 
 
7
9
3
5
,

 
 
2
3
8
,

 
 
5
,

 
 
7
,

 
 
1
2
6
,

 
 
8
7
6
,

 
 
9
,

 
 
6
,

 
 
6
3
6
,

 
 
6
9
,

 
 
8
0
,

 
 
6
1
,

 
 
8
0
4
8
,

 
 
9
,

 
 
8
6
,

 
 
4
5
1
0
,

 
 
4
4
,

 
 
4
7
,

 
 
2
7
8
,

 
 
3
7
,

 
 
7
0
,

 
 
2
5
,

 
 
1
0
3
5
,

 
 
3
7
,

 
 
5
5
,

 
 
2
1
7
3
,

 
 
3
6
,

 
 
7
,

 
 
2
1
1
,

 
 
3
1
3
2
,

 
 
9
,

 
 
1
4
4
,

 
 
6
,

 
 
6
3
6
,

 
 
1
1
0
2
,

 
 
2
1
1
,

 
 
1
2
6
,

 
 
3
1
3
2
,

 
 
3
5
,

 
 
2
9
8
,

 
 
1
1
,

 
 
8
9
,

 
 
2
8
0
9
,

 
 
2
6
,

 
 
7
,

 
 
3
9
,

 
 
1
2
1
,

 
 
6
,

 
 
1
0
4
0
,

 
 
7
6
,

 
 
4
,

 
 
5
7
3
,

 
 
4
7
,

 
 
2
5
,

 
 
2
0
9
6
,

 
 
7
6
,

 
 
6
0
,

 
 
1
1
5
6
,

 
 
3
9
1
7
,

 
 
1
9
,

 
 
4
,

 
 
2
8
4
,

 
 
3
0
3
,

 
 
5
,

 
 
4
8
2
,

 
 
1
6
1
0
2
9
,

 
 
2
6
7
4
1
]
,

 
[
3
1
7
,

 
 
3
7
,

 
 
7
5
7
,

 
 
7
,

 
 
7
7
8
,

 
 
6
,

 
 
2
3
7
,

 
 
2
,

 
 
3
1
7
,

 
 
3
7
,

 
 
7
5
7
,

 
 
7
8
,

 
 
2
2
9
,

 
 
6
,

 
 
6
7
,

 
 
1
9
2
,

 
 
5
,

 
 
3
4
,

 
 
2
0
,

 
 
1
7
0
,

 
 
2
4
0
,

 
 
2
2
8
,

 
 
2
5
,

 
 
3
4
,

 
 
6
,

 
 
1
3
6
,

 
 
9
,

 
 
8
7
9
0
,

 
 
3
7
,

 
 
8
,

 
 
5
1
1
4
,

 
 
1
4
2
8
,

 
 
1
6
8
,

 
 
3
4
,

 
 
8
4
,

 
 
6
,

 
 
1
8
,

 
 
4
,

 
 
8
3
7
1
1
,

 
 
8
4
7
,

 
 
5
,

 
 
7
,

 
 
4
5
,

 
 
8
1
8
,

 
 
6
]
,

 
[
1
1
9
5
7
,

 
 
2
5
7
1
,

 
 
9
3
2
,

 
 
2
1
,

 
 
6
3
2
,

 
 
5
1
3
5
,

 
 
3
,

 
 
2
8
1
,

 
 
1
5
2
9
1
,

 
 
8
7
,

 
 
1
9
,

 
 
9
2
,

 
 
1
0
6
7
1
8
,

 
 
3
8
6
6
,

 
 
6
5
5
5
,

 
 
1
3
,

 
 
4
2
,

 
 
5
7
,

 
 
6
9
5
,

 
 
1
7
,

 
 
1
,

 
 
2
1
2
,

 
 
1
2
,

 
 
2
5
8
4
,

 
 
1
1
9
5
7
,

 
 
2
5
7
1
,

 
 
1
0
,

 
 
1
,

 
 
7
6
0
7
,

 
 
9
3
2
,

 
 
3
,

 
 
1
,

 
 
1
1
6
0
,

 
 
5
7
5
0
,

 
 
4
4
0
8
,

 
 
1
3
,

 
 
8
,

 
 
5
1
0
,

 
 
8
1
0
9
,

 
 
2
1
4
5
,

 
 
3
8
,

 
 
1
0
0
,

 
 
2
8
1
,

 
 
1
5
2
9
1
,

 
 
2
7
6
,

 
 
1
1
2
,

 
 
9
3
2
,

 
 
1
9
,

 
 
6
1
8
,

 
 
5
0
8
2
,

 
 
5
,

 
 
9
8
2
,

 
 
1
,

 
 
1
3
9
,

 
 
1
3
8
8
,

 
 
1
,

 
 
3
3
0
4
,

 
 
1
0
,

 
 
4
1
6
0
,

 
 
1
8
,

 
 
1
2
0
8
,

 
 
1
0
,

 
 
2
5
2
7
,

 
 
5
,

 
 
4
1
1
3
,

 
 
7
5
7
0
,

 
 
7
5
,

 
 
1
8
,

 
 
1
5
2
9
1
,

 
 
3
,

 
 
9
2
,

 
 
9
3
2
,

 
 
1
0
,

 
 
1
,

 
 
1
9
8
8
,

 
 
5
6
8
8
,

 
 
1
0
,

 
 
4
3
3
,

 
 
3
,

 
 
1
4
1
,

 
 
9
3
2
,

 
 
4
1
,

 
 
1
8
,

 
 
6
0
,

 
 
9
0
5
0
,

 
 
1
0
,

 
 
4
3
3
,

 
 
3
,

 
 
1
4
1
,

 
 
9
3
2
,

 
 
2
6
,

 
 
9
,

 
 
1
8
1
,

 
 
1
2
6
,

 
 
5
2
0
,

 
 
7
8
,

 
 
4
1
6
0
,

 
 
4
3
,

 
 
3
6
9
,

 
 
2
5
8
,

 
 
1
,

 
 
2
8
2
8
,

 
 
4
4
,

 
 
3
,

 
 
3
2
2
0
5
,

 
 
2
,

 
 
2
5
2
7
,

 
 
2
5
,

 
 
2
9
0
0
,

 
 
2
,

 
 
2
5
2
7
,

 
 
1
2
5
,

 
 
4
1
,

 
 
2
4
,

 
 
4
4
,

 
 
8
0
1
,

 
 
2
,

 
 
9
8
2
,

 
 
3
,

 
 
1
2
,

 
 
3
1
1
,

 
 
7
2
,

 
 
4
,

 
 
6
1
5
9
,

 
 
4
8
4
7
,

 
 
5
,

 
 
3
7
,

 
 
2
5
7
1
,

 
 
1
2
,

 
 
4
,

 
 
3
2
6
6
,

 
 
2
5
,

 
 
4
,

 
 
2
6
8
0
,

 
 
9
0
5
,

 
 
8
,

 
 
1
4
,

 
 
4
0
2
6
,

 
 
2
6
,

 
 
7
2
,

 
 
1
4
,

 
 
4
,

 
 
6
1
5
9
,

 
 
2
8
1
,

 
 
6
8
0
,

 
 
7
,

 
 
1
9
,

 
 
1
,

 
 
7
7
4
4
,

 
 
3
,

 
 
1
0
5
9
3
,

 
 
5
,

 
 
3
0
,

 
 
7
1
9
,

 
 
4
2
,

 
 
1
9
9
,

 
 
2
1
4
0
,

 
 
1
0
,

 
 
2
5
2
7
,

 
 
1
0
,

 
 
1
7
9
,

 
 
7
1
,

 
 
1
2
6
,

 
 
3
5
,

 
 
6
3
5
5
,

 
 
2
6
7
8
1
,

 
 
5
4
,

 
 
8
,

 
 
7
8
,

 
 
1
3
3
4
1
,

 
 
1
1
9
5
7
,

 
 
2
0
2
6
,

 
 
1
2
,

 
 
4
3
3
,

 
 
6
1
,

 
 
4
0
,

 
 
1
,

 
 
8
5
,

 
 
7
1
,

 
 
1
,

 
 
3
6
1
,

 
 
5
,

 
 
2
3
8
4
5
]
,

 
[
1
0
5
1
5
,
 
8
,
 
1
4
,
 
4
,
 
5
7
1
,
 
5
9
2
,
 
1
2
0
,
 
5
0
,
 
5
2
0
,
 
7
4
,
 
1
,
 
1
0
5
1
5
,
 
4
2
1
,
 
8
,
 
1
4
,
 
5
7
1
,
 
5
9
2
]
,

 
[
5
0
,

 
 
3
4
,

 
 
1
4
,

 
 
6
7
1
,

 
 
1
2
4
,

 
 
1
7
,

 
 
6
,

 
 
9
0
,

 
 
2
1
,

 
 
1
3
,

 
 
7
9
,

 
 
2
,

 
 
2
6
7
4
9
,

 
 
2
2
,

 
 
6
,

 
 
3
0
7
,

 
 
2
,

 
 
3
4
,

 
 
3
6
,

 
 
6
,

 
 
4
5
,

 
 
1
6
,

 
 
1
8
8
,

 
 
3
1
,

 
 
1
2
9
,

 
 
4
2
4
0
6
,

 
 
8
3
8
]
,

 
[
7
0
4
,

 
 
9
8
1
,

 
 
7
1
0
,

 
 
2
1
6
,

 
 
4
1
,

 
 
8
,

 
 
4
4
,

 
 
1
1
3
,

 
 
1
3
8
2
,

 
 
2
,

 
 
1
4
3
8
1
,

 
 
1
,

 
 
9
7
0
3
,

 
 
3
,

 
 
1
9
0
7
2
,

 
 
7
8
5
4
,

 
 
4
0
3
,

 
 
3
0
4
,

 
 
9
,

 
 
8
,

 
 
6
,

 
 
1
9
,

 
 
4
4
,

 
 
1
1
3
,

 
 
1
3
8
2
,

 
 
3
0
4
,

 
 
1
1
0
,

 
 
6
0
7
,

 
 
1
1
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
2
1
5
,

 
 
1
6
6
,

 
 
9
,

 
 
2
8
6
8
1
,

 
 
2
5
,

 
 
5
5
,

 
 
3
,

 
 
1
,

 
 
6
1
,

 
 
5
2
9
0
,

 
 
2
9
9
,

 
 
2
0
2
2
3
,

 
 
2
6
7
8
2
,

 
 
2
,

 
 
2
5
,

 
 
1
3
0
1
,

 
 
2
1
,

 
 
1
,

 
 
1
9
0
7
2
,

 
 
5
9
2
,

 
 
1
7
2
3
,

 
 
2
5
,

 
 
6
1
4
,

 
 
5
7
5
,

 
 
8
5
2
0
,

 
 
4
,

 
 
8
5
2
0
,

 
 
8
1
1
4
,

 
 
2
5
,

 
 
5
5
,

 
 
6
1
,

 
 
3
3
9
8
,

 
 
6
1
4
,

 
 
9
8
0
,

 
 
4
5
6
,

 
 
3
8
,

 
 
5
6
,

 
 
2
5
,

 
 
8
0
7
,

 
 
1
6
,

 
 
3
5
6
9
,

 
 
1
0
,

 
 
4
8
0
,

 
 
4
0
,

 
 
6
,

 
 
1
9
,

 
 
1
5
,

 
 
1
2
1
5
,

 
 
8
8
6
,

 
 
8
,

 
 
9
,

 
 
1
,

 
 
5
2
9
0
,

 
 
2
9
9
,

 
 
2
0
2
2
3
,

 
 
3
1
6
,

 
 
1
2
,

 
 
7
5
3
5
,

 
 
7
3
3
3
,

 
 
3
,

 
 
1
,

 
 
3
8
9
,

 
 
1
2
,

 
 
1
0
6
1
,

 
 
1
7
4
0
,

 
 
1
9
0
7
2
,

 
 
7
2
6
8
,

 
 
4
0
3
,

 
 
5
4
,

 
 
3
0
8
4
9
,

 
 
2
1
6
1
2
,

 
 
9
,

 
 
1
3
5
,

 
 
1
0
9
0
1
,

 
 
1
9
6
7
,

 
 
2
5
,

 
 
3
4
7
,

 
 
1
2
,

 
 
9
2
,

 
 
1
7
2
3
,

 
 
2
5
,

 
 
6
1
4
,

 
 
1
7
0
2
,

 
 
8
,

 
 
1
4
,

 
 
4
,

 
 
1
6
6
,

 
 
1
8
2
,

 
 
1
,

 
 
4
7
5
,

 
 
3
,

 
 
2
8
,

 
 
4
0
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
1
9
0
7
2
,

 
 
1
3
4
4
,

 
 
8
,

 
 
3
9
9
1
,

 
 
2
0
6
7
5
,

 
 
3
0
8
4
9
,

 
 
1
3
4
7
0
,

 
 
3
2
,

 
 
1
,

 
 
3
0
4
4
,

 
 
1
7
7
,

 
 
1
,

 
 
1
5
4
8
1
,

 
 
3
7
4
2
,

 
 
4
8
0
0
,

 
 
3
,

 
 
1
,

 
 
2
9
9
,

 
 
5
2
9
0
,

 
 
1
9
1
2
,

 
 
1
0
,

 
 
3
3
5
,

 
 
3
,

 
 
1
,

 
 
1
1
3
,

 
 
1
4
0
3
,

 
 
3
4
,

 
 
4
4
,

 
 
2
8
8
0
,

 
 
5
4
1
8
,

 
 
1
,

 
 
7
6
4
4
,

 
 
4
0
3
,

 
 
3
,

 
 
1
,

 
 
3
0
4
4
,

 
 
2
4
5
,

 
 
1
4
,

 
 
1
6
,

 
 
3
4
4
9
,

 
 
2
,

 
 
1
6
6
,

 
 
5
,

 
 
5
5
,

 
 
1
7
4
,

 
 
2
,

 
 
9
,

 
 
1
2
1
7
,

 
 
2
4
5
,

 
 
1
6
,

 
 
1
2
9
2
,

 
 
1
9
4
4
0
,

 
 
4
9
7
,

 
 
1
,

 
 
1
1
3
,

 
 
1
4
0
3
,

 
 
8
1
6
,

 
 
6
1
6
]
,

 
[
7
9
4
,

 
 
9
5
,

 
 
1
2
,

 
 
2
0
,

 
 
7
9
4
,

 
 
3
5
,

 
 
1
,

 
 
3
7
7
,

 
 
6
,

 
 
1
3
7
5
,

 
 
3
1
,

 
 
1
0
6
7
1
9
,

 
 
7
,

 
 
1
3
7
5
,

 
 
4
,

 
 
6
1
8
,

 
 
2
3
8
,

 
 
1
4
,

 
 
4
6
2
6
,

 
 
3
1
5
7
,

 
 
7
9
4
,

 
 
3
1
,

 
 
1
0
6
7
1
9
,

 
 
1
7
,

 
 
1
0
1
]
,

 
[
1
1
,

 
 
8
,

 
 
4
,

 
 
9
9
9
6
,

 
 
2
1
,

 
 
2
3
0
9
,

 
 
2
,

 
 
1
2
4
9
8
,

 
 
9
,

 
 
8
,

 
 
1
4
,

 
 
1
,

 
 
1
4
5
,

 
 
6
4
,

 
 
1
1
,

 
 
1
7
9
8
,

 
 
1
0
,

 
 
1
,

 
 
3
2
2
9
,

 
 
8
3
4
5
,

 
 
2
3
]
,

 
[
3
7
5
,

 
 
7
3
3
0
,

 
 
1
0
,

 
 
1
,

 
 
1
3
8
,

 
 
3
,

 
 
3
2
3
0
,

 
 
1
6
1
0
3
0
,

 
 
5
9
9
8
,

 
 
8
,

 
 
1
8
3
,

 
 
2
7
8
6
,

 
 
3
,

 
 
1
,

 
 
1
5
9
0
9
,

 
 
2
3
,

 
 
3
2
,

 
 
3
5
8
,

 
 
9
,

 
 
1
0
6
7
2
0
,

 
 
3
1
7
0
,

 
 
1
9
,

 
 
2
5
5
6
,

 
 
1
7
2
,

 
 
3
2
,

 
 
5
0
7
9
,

 
 
9
2
,

 
 
8
5
7
,

 
 
1
6
1
0
3
1
,

 
 
4
2
,

 
 
3
5
1
7
,

 
 
7
1
6
,

 
 
9
,

 
 
1
,

 
 
3
2
4
6
,

 
 
3
,

 
 
1
,

 
 
2
1
1
2
,

 
 
1
1
5
2
,

 
 
4
5
,

 
 
1
6
,

 
 
2
5
,

 
 
1
9
,

 
 
5
7
,

 
 
3
8
6
6
,

 
 
3
2
,

 
 
4
5
5
1
,

 
 
5
,

 
 
5
6
1
,

 
 
4
2
8
,

 
 
6
3
7
6
,

 
 
2
6
4
,

 
 
9
3
,

 
 
1
,

 
 
3
8
9
,

 
 
7
5
7
,

 
 
7
,

 
 
2
9
3
4
,

 
 
7
0
,

 
 
2
2
,

 
 
1
6
1
0
3
2
,

 
 
1
1
3
2
,

 
 
1
0
,

 
 
3
3
5
6
,

 
 
3
9
4
4
,

 
 
1
7
2
,

 
 
2
,

 
 
9
7
,

 
 
1
1
1
,

 
 
2
7
,

 
 
2
8
9
9
,

 
 
2
6
,

 
 
7
0
3
,

 
 
1
7
2
,

 
 
1
7
,

 
 
4
,

 
 
1
3
8
2
,

 
 
2
,

 
 
9
7
,

 
 
9
,

 
 
4
5
7
,

 
 
4
3
,

 
 
1
6
,

 
 
1
7
,

 
 
2
8
4
,

 
 
2
7
,

 
 
2
0
2
8
,

 
 
2
,

 
 
2
1
1
2
,

 
 
2
0
2
2
4
,

 
 
1
7
,

 
 
2
1
5
,

 
 
1
0
6
7
2
0
,

 
 
3
1
7
0
,

 
 
1
9
,

 
 
1
6
7
,

 
 
7
,

 
 
5
8
3
6
,

 
 
5
9
1
9
,

 
 
2
1
,

 
 
1
6
1
0
3
3
,

 
 
3
2
7
,

 
 
9
,

 
 
1
,

 
 
7
2
6
,

 
 
4
2
,

 
 
4
4
,

 
 
2
0
2
,

 
 
1
0
,

 
 
1
,

 
 
2
3
]
,

 
[
6
1
,
 
1
4
3
8
2
,
 
3
8
,
 
8
,
 
4
,
 
1
3
8
3
,
 
2
0
2
,
 
5
,
 
2
3
6
6
,
 
2
0
2
]
,

 
[
7
,

 
 
2
3
8
6
,

 
 
1
1
6
6
6
,

 
 
8
7
,

 
 
1
6
,

 
 
3
7
4
,

 
 
2
2
,

 
 
1
0
7
3
0
,

 
 
6
2
,

 
 
1
2
0
6
,

 
 
1
4
8
4
,

 
 
1
0
,

 
 
5
8
9
5
,

 
 
1
6
7
,

 
 
1
3
,

 
 
3
5
,

 
 
1
0
0
4
9
,

 
 
5
2
,

 
 
2
8
8
,

 
 
9
4
1
,

 
 
1
1
,

 
 
1
7
,

 
 
4
7
9
7
,

 
 
7
,

 
 
2
6
5
,

 
 
1
,

 
 
3
1
1
5
,

 
 
4
3
,

 
 
1
9
,

 
 
5
7
,

 
 
1
5
,

 
 
6
9
1
8
,

 
 
4
4
1
7
,

 
 
3
1
,

 
 
3
0
,

 
 
7
4
8
,

 
 
3
,

 
 
6
9
8
9
9
,

 
 
6
0
8
3
9
,

 
 
5
2
,

 
 
2
4
,

 
 
2
6
4
,

 
 
5
6
1
,

 
 
3
4
8
7
,

 
 
8
2
9
,

 
 
2
6
7
8
3
]
,

 
[
2
5
9
6
9
,

 
 
1
0
1
,

 
 
3
9
,

 
 
6
,

 
 
8
8
2
,

 
 
1
1
,

 
 
6
9
,

 
 
1
1
,

 
 
5
2
6
,

 
 
4
,

 
 
1
7
6
4
,

 
 
1
4
3
,

 
 
8
9
,

 
 
5
,

 
 
7
,

 
 
5
9
,

 
 
6
5
,

 
 
1
1
,

 
 
2
4
,

 
 
6
9
9
4
,

 
 
1
0
,

 
 
6
9
9
5
,

 
 
3
5
1
,

 
 
3
6
,

 
 
1
1
5
,

 
 
4
0
8
7
,

 
 
5
,

 
 
1
7
1
1
,

 
 
5
6
,

 
 
4
9
,

 
 
1
6
,

 
 
4
1
]
,

 
[
4
3
6
4
,
 
7
,
 
4
7
7
,
 
1
0
6
7
2
1
,
 
6
2
,
 
1
8
1
,
 
7
,
 
4
7
7
,
 
1
3
2
2
0
,
 
2
3
3
2
]
,

 
[
1
3
7
,
 
1
8
7
,
 
1
1
,
 
1
1
,
 
9
3
6
3
,
 
2
4
1
,
 
2
,
 
1
,
 
2
3
]
,

 
[
1
7
8
,

 
 
1
6
1
0
3
4
,

 
 
1
9
6
,

 
 
2
,

 
 
2
8
,

 
 
7
,

 
 
2
2
6
,

 
 
6
,

 
 
4
8
,

 
 
1
3
,

 
 
2
0
2
,

 
 
2
9
4
,

 
 
7
,

 
 
1
8
6
,

 
 
3
4
,

 
 
2
9
4
,

 
 
5
,

 
 
1
0
8
,

 
 
2
,

 
 
6
0
6
,

 
 
1
5
0
,

 
 
4
0
4
,

 
 
1
5
5
,

 
 
1
0
,

 
 
3
2
1
0
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
1
5
6
,

 
 
3
5
,

 
 
1
,

 
 
6
6
6
,

 
 
1
0
3
0
,

 
 
3
,

 
 
2
8
,

 
 
5
,

 
 
3
8
0
9
,

 
 
7
0
7
7
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
1
5
,

 
 
7
4
,

 
 
2
,

 
 
3
3
8
,

 
 
1
1
5
,

 
 
8
3
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
,

 
 
1
6
3
4
,

 
 
2
5
8
5
,

 
 
5
,

 
 
1
2
,

 
 
1
2
1
,

 
 
1
5
,

 
 
2
4
0
4
,

 
 
1
,

 
 
1
2
4
,

 
 
1
8
7
7
,

 
 
1
,

 
 
8
7
2
,

 
 
3
,

 
 
1
9
0
,

 
 
2
2
,

 
 
6
,

 
 
1
2
2
,

 
 
1
2
1
,

 
 
1
4
7
,

 
 
3
3
,

 
 
2
8
,

 
 
1
2
1
,

 
 
5
,

 
 
1
,

 
 
4
8
1
6
,

 
 
1
4
6
5
,

 
 
2
2
,

 
 
6
,

 
 
2
2
9
,

 
 
1
3
6
,

 
 
2
0
,

 
 
5
2
5
,

 
 
4
1
,

 
 
3
2
8
,

 
 
1
,

 
 
1
9
1
4
,

 
 
3
3
8
3
,

 
 
1
2
,

 
 
2
8
,

 
 
4
7
0
,

 
 
2
5
4
,

 
 
2
5
,

 
 
1
,

 
 
2
7
3
,

 
 
2
1
3
1
,

 
 
1
2
,

 
 
4
3
6
,

 
 
2
5
4
,

 
 
3
9
5
,

 
 
1
5
3
,

 
 
5
8
,

 
 
1
2
1
,

 
 
3
3
,

 
 
1
,

 
 
1
0
5
5
,

 
 
5
,

 
 
2
3
0
,

 
 
1
8
4
1
,

 
 
1
4
6
5
,

 
 
5
9
,

 
 
1
6
8
9
,

 
 
2
,

 
 
1
8
7
7
,

 
 
1
,

 
 
5
3
9
,

 
 
2
2
6
6
,

 
 
5
,

 
 
2
2
,

 
 
6
,

 
 
1
9
,

 
 
5
5
,

 
 
5
8
,

 
 
2
5
4
,

 
 
1
5
1
,

 
 
9
,

 
 
2
1
1
,

 
 
2
0
0
,

 
 
2
,

 
 
3
4
5
,

 
 
8
8
,

 
 
1
5
,

 
 
3
0
,

 
 
1
0
7
,

 
 
4
6
,

 
 
2
9
,

 
 
2
5
,

 
 
2
0
2
,

 
 
1
6
2
8
,

 
 
1
5
,

 
 
2
0
,

 
 
4
6
,

 
 
2
9
,

 
 
5
,

 
 
1
5
8
,

 
 
4
5
,

 
 
1
6
,

 
 
3
2
,

 
 
2
,

 
 
1
2
1
,

 
 
6
,

 
 
1
7
4
1
,

 
 
2
5
4
4
,

 
 
1
3
8
4
,

 
 
2
7
6
4
,

 
 
9
2
5
4
,

 
 
1
4
4
2
,

 
 
6
0
,

 
 
2
0
8
3
,

 
 
2
7
6
4
,

 
 
2
,

 
 
1
2
1
,

 
 
6
,

 
 
9
4
,

 
 
3
1
5
,

 
 
1
0
,

 
 
1
,

 
 
1
3
7
6
2
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
8
7
9
,

 
 
3
1
5
,

 
 
2
1
,

 
 
2
0
,

 
 
1
1
5
,

 
 
1
8
0
,

 
 
2
4
9
6
,

 
 
1
,

 
 
6
1
2
,

 
 
8
,

 
 
1
2
,

 
 
6
,

 
 
2
5
4
4
,

 
 
6
,

 
 
3
9
,

 
 
5
1
7
,

 
 
2
0
,

 
 
1
0
9
,

 
 
2
0
9
,

 
 
4
2
0
,

 
 
9
0
0
,

 
 
2
2
,

 
 
6
,

 
 
8
2
,

 
 
4
9
2
,

 
 
6
,

 
 
3
9
,

 
 
1
5
2
,

 
 
4
,

 
 
1
3
4
7
1
,

 
 
1
5
5
,

 
 
6
6
6
,

 
 
4
5
,

 
 
9
4
,

 
 
6
,

 
 
1
,

 
 
1
3
4
7
1
,

 
 
7
7
,

 
 
6
,

 
 
8
7
,

 
 
1
0
8
,

 
 
2
,

 
 
1
5
2
,

 
 
2
2
5
,

 
 
2
,

 
 
1
,

 
 
1
1
5
,

 
 
1
0
7
,

 
 
1
3
5
2
,

 
 
2
5
4
4
,

 
 
2
2
,

 
 
6
,

 
 
3
4
9
,

 
 
6
5
,

 
 
4
,

 
 
2
9
,

 
 
2
5
,

 
 
1
2
3
,

 
 
5
6
,

 
 
1
6
,

 
 
1
4
6
,

 
 
5
0
,

 
 
1
6
1
,

 
 
1
1
,

 
 
3
3
,

 
 
1
,

 
 
2
0
2
6
,

 
 
1
2
,

 
 
1
1
9
,

 
 
2
9
,

 
 
4
1
,

 
 
8
,

 
 
6
6
,

 
 
4
,

 
 
2
0
2
6
,

 
 
1
2
,

 
 
1
0
5
0
4
,

 
 
2
9
,

 
 
2
2
,

 
 
6
,

 
 
1
0
8
,

 
 
2
,

 
 
1
0
0
0
0
,

 
 
1
6
3
,

 
 
9
,

 
 
6
,

 
 
6
5
,

 
 
5
6
,

 
 
1
4
,

 
 
1
9
,

 
 
5
7
,

 
 
1
4
6
,

 
 
2
2
,

 
 
1
6
4
,

 
 
1
5
3
,

 
 
1
0
5
9
,

 
 
1
5
0
3
,

 
 
2
5
,

 
 
4
3
,

 
 
4
8
,

 
 
2
,

 
 
9
4
,

 
 
4
,

 
 
2
0
1
,

 
 
4
8
5
4
,

 
 
3
,

 
 
2
0
,

 
 
2
8
,

 
 
2
4
9
6
,

 
 
5
,

 
 
6
,

 
 
1
9
,

 
 
2
7
,

 
 
3
4
6
5
,

 
 
5
6
5
5
,

 
 
2
5
,

 
 
5
9
,

 
 
4
8
9
,

 
 
4
0
4
,

 
 
4
7
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
,

 
 
2
3
1
8
8
,

 
 
7
1
,

 
 
1
4
,

 
 
3
8
,

 
 
1
1
,

 
 
1
0
8
2
,

 
 
4
8
,

 
 
2
6
,

 
 
1
1
,

 
 
8
,

 
 
1
1
5
6
,

 
 
5
,

 
 
3
9
,

 
 
1
2
1
,

 
 
6
,

 
 
2
1
,

 
 
2
0
,

 
 
1
2
9
,

 
 
2
4
9
6
,

 
 
2
2
,

 
 
1
6
4
,

 
 
4
5
2
7
,

 
 
5
,

 
 
1
0
8
,

 
 
2
,

 
 
1
3
6
,

 
 
1
6
3
,

 
 
2
,

 
 
3
4
,

 
 
2
8
9
,

 
 
1
,

 
 
1
4
1
4
,

 
 
2
9
,

 
 
2
2
8
2
,

 
 
1
0
,

 
 
1
,

 
 
8
7
4
5
,

 
 
2
5
,

 
 
3
2
8
,

 
 
7
6
,

 
 
1
,

 
 
7
0
9
,

 
 
2
3
6
8
,

 
 
3
7
7
,

 
 
1
0
,

 
 
1
,

 
 
5
3
9
,

 
 
2
2
6
6
,

 
 
4
8
2
,

 
 
1
8
0
,

 
 
4
5
6
2
,

 
 
2
9
4
,

 
 
4
6
,

 
 
7
9
2
,

 
 
1
4
2
6
,

 
 
6
4
,

 
 
2
,

 
 
1
1
2
0
,

 
 
2
,

 
 
1
3
,

 
 
3
7
7
]
,

 
[
1
1
,

 
 
8
,

 
 
5
2
3
,

 
 
7
4
8
,

 
 
9
,

 
 
1
0
6
7
2
2
,

 
 
2
6
,

 
 
1
4
,

 
 
5
4
3
9
5
,

 
 
7
2
1
,

 
 
1
9
8
3
7
,

 
 
3
9
2
4
,

 
 
3
1
,

 
 
3
5
3
9
8
,

 
 
2
6
,

 
 
3
8
,

 
 
5
1
,

 
 
3
4
,

 
 
1
4
,

 
 
1
4
7
8
,

 
 
8
,

 
 
9
,

 
 
5
3
,

 
 
2
2
0
,

 
 
1
,

 
 
2
6
7
8
4
,

 
 
1
6
1
0
3
5
,

 
 
1
5
,

 
 
1
9
8
3
8
,

 
 
2
2
6
4
7
,

 
 
5
8
5
,

 
 
7
3
3
2
,

 
 
2
1
,

 
 
1
6
1
0
3
6
,

 
 
1
9
4
4
1
,

 
 
3
1
,

 
 
6
9
9
0
0
,

 
 
5
,

 
 
1
6
1
0
3
7
,

 
 
1
7
5
,

 
 
3
0
8
5
0
,

 
 
4
8
4
5
,

 
 
8
6
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
,

 
 
2
8
6
8
2
,

 
 
3
,

 
 
1
,

 
 
1
0
6
0
,

 
 
1
9
3
0
,

 
 
4
1
3
5
,

 
 
3
,

 
 
1
0
1
6
,

 
 
6
2
,

 
 
3
0
9
0
,

 
 
1
7
5
,

 
 
1
7
7
8
2
,

 
 
1
1
,

 
 
8
,

 
 
3
0
6
8
,

 
 
1
2
,

 
 
1
3
,

 
 
2
1
2
,

 
 
9
,

 
 
5
4
3
9
5
,

 
 
8
4
1
,

 
 
1
9
5
8
,

 
 
4
8
,

 
 
7
2
3
1
,

 
 
2
1
8
3
,

 
 
5
4
3
9
6
,

 
 
3
,

 
 
1
6
1
0
3
8
,

 
 
5
,

 
 
1
6
1
0
3
9
,

 
 
2
1
8
3
,

 
 
3
3
8
0
,

 
 
2
5
,

 
 
6
0
8
4
0
,

 
 
2
1
8
3
,

 
 
1
8
3
9
3
,

 
 
4
5
8
,

 
 
1
9
1
,

 
 
3
3
0
8
,

 
 
1
0
,

 
 
9
2
,

 
 
4
0
2
5
,

 
 
1
,

 
 
4
5
1
,

 
 
2
9
2
]
,

 
[
6
4
8
,

 
 
1
0
2
8
,

 
 
6
5
5
,

 
 
2
1
6
,

 
 
8
4
,

 
 
2
0
5
2
,

 
 
5
,

 
 
1
9
7
3
,

 
 
1
,

 
 
2
3
,

 
 
3
6
7
,

 
 
1
2
8
,

 
 
2
6
4
,

 
 
1
9
,

 
 
4
,

 
 
5
1
0
,

 
 
2
3
,

 
 
9
3
,

 
 
4
,

 
 
3
6
6
,

 
 
2
3
,

 
 
2
1
,

 
 
4
,

 
 
5
1
0
,

 
 
3
7
0
,

 
 
1
7
,

 
 
1
2
,

 
 
2
3
1
8
9
,

 
 
1
4
0
,

 
 
7
2
,

 
 
1
4
,

 
 
1
6
5
,

 
 
2
,

 
 
9
0
9
,

 
 
1
5
,

 
 
4
,

 
 
1
7
4
,

 
 
3
5
4
,

 
 
3
3
,

 
 
1
3
,

 
 
8
5
,

 
 
7
,

 
 
1
9
,

 
 
1
9
9
,

 
 
1
0
3
2
,

 
 
3
3
,

 
 
1
3
,

 
 
2
3
,

 
 
1
5
0
,

 
 
6
,

 
 
1
2
2
7
,

 
 
3
7
,

 
 
1
,

 
 
1
6
9
,

 
 
3
6
,

 
 
7
,

 
 
8
1
,

 
 
1
4
,

 
 
1
1
9
6
4
,

 
 
2
,

 
 
1
5
2
7
,

 
 
4
7
,

 
 
4
0
7
,

 
 
1
4
8
,

 
 
1
8
3
,

 
 
3
0
,

 
 
9
0
9
,

 
 
8
,

 
 
3
1
7
3
,

 
 
1
5
,

 
 
1
,

 
 
3
5
5
3
,

 
 
1
4
9
0
3
,

 
 
3
,

 
 
4
7
3
,

 
 
1
,

 
 
3
7
0
,

 
 
3
5
2
,

 
 
5
1
9
,

 
 
8
0
,

 
 
1
3
7
,

 
 
1
9
5
0
,

 
 
5
8
,

 
 
8
5
,

 
 
2
1
,

 
 
2
7
,

 
 
5
9
2
0
,

 
 
2
3
,

 
 
7
,

 
 
3
9
,

 
 
9
7
,

 
 
4
,

 
 
4
5
7
,

 
 
3
5
,

 
 
1
,

 
 
1
7
4
,

 
 
8
1
6
,

 
 
1
7
5
3
]
,

 
[
7
,

 
 
2
4
,

 
 
2
6
8
,

 
 
2
,

 
 
1
5
2
9
2
,

 
 
6
0
,

 
 
6
4
7
1
,

 
 
1
7
,

 
 
8
2
9
6
,

 
 
3
2
,

 
 
3
0
,

 
 
4
5
5
8
6
,

 
 
8
9
6
,

 
 
1
0
,

 
 
1
3
,

 
 
1
2
0
4
,

 
 
1
9
0
7
3
,

 
 
5
,

 
 
6
9
3
9
,

 
 
7
4
2
4
,

 
 
9
4
0
,

 
 
2
2
,

 
 
6
,

 
 
6
5
1
,

 
 
1
,

 
 
8
5
,

 
 
2
,

 
 
9
7
5
2
,

 
 
2
2
5
,

 
 
2
1
,

 
 
1
,

 
 
9
4
0
,

 
 
6
,

 
 
4
3
,

 
 
6
3
,

 
 
9
,

 
 
1
,

 
 
2
2
2
,

 
 
7
,

 
 
4
8
3
3
,

 
 
2
4
,

 
 
2
2
9
3
,

 
 
3
0
,

 
 
6
9
5
,

 
 
5
,

 
 
1
4
5
3
,

 
 
4
1
4
,

 
 
3
2
,

 
 
4
3
2
3
,

 
 
5
6
2
2
,

 
 
8
8
,

 
 
4
4
,

 
 
7
3
3
,

 
 
5
4
,

 
 
7
,

 
 
2
7
7
2
2
,

 
 
2
1
,

 
 
3
2
,

 
 
2
5
5
4
,

 
 
1
5
4
,

 
 
7
,

 
 
3
3
2
,

 
 
9
,

 
 
6
8
,

 
 
2
2
5
7
,

 
 
2
4
,

 
 
2
0
2
8
,

 
 
2
4
1
4
,

 
 
3
3
,

 
 
1
,

 
 
8
5
,

 
 
1
7
,

 
 
4
3
,

 
 
5
5
,

 
 
8
9
8
9
,

 
 
1
1
1
4
,

 
 
6
2
,

 
 
2
4
,

 
 
1
4
,

 
 
1
5
1
7
,

 
 
2
1
,

 
 
5
0
8
,

 
 
4
4
,

 
 
2
0
2
8
,

 
 
7
2
3
,

 
 
1
9
7
,

 
 
7
,

 
 
1
9
,

 
 
1
4
4
,

 
 
2
8
5
7
,

 
 
9
,

 
 
3
8
,

 
 
7
,

 
 
9
0
,

 
 
2
4
,

 
 
2
4
7
,

 
 
6
9
,

 
 
1
3
,

 
 
3
4
1
,

 
 
1
0
0
,

 
 
1
4
,

 
 
1
0
7
2
,

 
 
1
2
,

 
 
4
5
6
8
,

 
 
4
0
9
,

 
 
5
4
,

 
 
8
,

 
 
7
8
,

 
 
7
,

 
 
4
5
,

 
 
1
4
,

 
 
8
2
,

 
 
8
8
,

 
 
1
2
7
,

 
 
9
6
,

 
 
2
2
,

 
 
5
1
,

 
 
1
8
,

 
 
1
3
3
,

 
 
2
4
8
,

 
 
3
7
,

 
 
5
4
,

 
 
5
1
,

 
 
8
6
,

 
 
5
4
7
,

 
 
1
3
,

 
 
2
3
1
9
0
,

 
 
2
8
,

 
 
8
,

 
 
1
,

 
 
2
0
2
,

 
 
1
2
,

 
 
3
7
,

 
 
6
9
,

 
 
3
0
,

 
 
7
9
,

 
 
2
4
,

 
 
1
5
9
3
,

 
 
5
,

 
 
1
3
7
3
,

 
 
4
,

 
 
1
8
5
6
,

 
 
7
4
8
,

 
 
2
,

 
 
1
,

 
 
1
9
0
7
,

 
 
4
4
7
,

 
 
2
6
,

 
 
1
,

 
 
1
6
6
,

 
 
9
,

 
 
7
,

 
 
4
8
3
3
,

 
 
1
8
3
,

 
 
1
0
7
,

 
 
1
0
,

 
 
1
,

 
 
7
9
,

 
 
5
1
5
,

 
 
8
,

 
 
2
1
1
0
2
,

 
 
5
,

 
 
7
,

 
 
7
0
,

 
 
9
,

 
 
8
9
,

 
 
2
2
,

 
 
6
,

 
 
7
8
0
,

 
 
6
5
,

 
 
1
,

 
 
7
9
,

 
 
1
0
0
2
,

 
 
2
5
5
,

 
 
2
7
3
2
,

 
 
4
,

 
 
2
0
1
,

 
 
2
0
2
8
]
,

 
[
1
3
,

 
 
3
3
8
,

 
 
5
6
,

 
 
4
3
9
,

 
 
2
,

 
 
1
6
1
0
4
0
,

 
 
1
9
8
3
9
,

 
 
7
,

 
 
1
6
1
0
4
1
,

 
 
2
3
6
,

 
 
1
1
,

 
 
2
6
,

 
 
3
3
,

 
 
1
,

 
 
1
1
6
4
,

 
 
4
1
,

 
 
1
8
,

 
 
1
5
5
,

 
 
1
3
0
,

 
 
2
2
4
,

 
 
1
2
,

 
 
3
7
,

 
 
2
,

 
 
1
6
2
5
]
,

 
.
.
.
]
</pre>

```python
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
```

<pre>
3
9
4
7
8
7
</pre>

```python
p
r
i
n
t
(
t
e
x
t
[
0
]
)
```

<pre>
[
7
3
3
,
 
7
8
,
 
1
,
 
1
4
0
,
 
1
3
1
,
 
1
8
2
,
 
3
0
,
 
7
1
2
,
 
4
4
3
8
,
 
1
0
2
8
4
,
 
1
2
5
2
,
 
8
6
,
 
3
6
8
,
 
5
1
,
 
2
2
3
0
,
 
1
4
0
3
9
,
 
4
9
,
 
6
7
4
4
,
 
1
5
,
 
6
0
,
 
2
6
2
4
,
 
1
5
1
,
 
7
,
 
2
8
3
2
,
 
3
3
,
 
1
1
5
,
 
1
2
4
6
,
 
1
6
1
2
9
,
 
2
5
1
7
,
 
5
,
 
5
0
,
 
5
9
,
 
2
5
6
,
 
1
,
 
3
7
0
,
 
3
1
,
 
1
,
 
4
6
,
 
2
9
,
 
1
4
4
,
 
7
2
,
 
3
9
3
1
,
 
8
9
,
 
4
2
0
8
,
 
6
3
6
8
,
 
2
6
8
7
,
 
1
1
8
3
]

</pre>

```python
p
d
.
S
e
r
i
e
s
(
t
e
x
t
)
```

<pre>
0
 
 
 
 
 
 
 
 
 
[
7
3
3
,
 
7
8
,
 
1
,
 
1
4
0
,
 
1
3
1
,
 
1
8
2
,
 
3
0
,
 
7
1
2
,
 
4
4
3
8
,
 
1
0
2
.
.
.

1
 
 
 
 
 
 
 
 
 
[
1
6
0
3
6
6
,
 
5
2
,
 
2
9
1
1
,
 
1
3
,
 
4
5
0
,
 
3
7
8
2
,
 
7
2
,
 
4
8
7
1
,
 
2
6
.
.
.

2
 
 
 
 
 
 
 
 
 
[
4
5
5
,
 
4
0
0
,
 
7
2
,
 
1
2
6
,
 
1
4
,
 
2
6
8
,
 
2
,
 
7
9
,
 
3
2
6
,
 
7
1
,
 
4
.
.
.

3
 
 
 
 
 
 
 
 
 
[
5
8
,
 
7
,
 
2
2
9
,
 
9
7
,
 
5
5
,
 
3
2
5
,
 
1
4
0
8
,
 
1
5
,
 
2
1
2
0
,
 
7
,
 
5
.
.
.

4
 
 
 
 
 
 
 
 
 
[
6
,
 
1
7
4
4
,
 
1
8
,
 
3
0
,
 
3
5
9
8
,
 
5
5
,
 
1
1
0
5
,
 
6
,
 
5
8
4
,
 
3
8
,
 
.
.
.

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

3
1
2
7
3
0
 
 
 
 
[
7
,
 
1
0
7
1
,
 
2
6
3
,
 
1
3
,
 
5
3
6
,
 
8
,
 
2
4
1
,
 
2
6
,
 
1
5
5
,
 
2
5
0
,
 
.
.
.

3
1
2
7
3
1
 
 
 
 
[
2
5
7
4
,
 
3
1
,
 
7
6
,
 
9
9
5
,
 
2
,
 
1
0
4
2
,
 
6
2
5
5
,
 
1
0
0
,
 
1
1
,
 
9
4
.
.
.

3
1
2
7
3
2
 
 
 
 
[
1
0
6
4
6
0
,
 
1
2
0
7
,
 
7
,
 
6
3
,
 
2
0
,
 
4
2
2
,
 
5
,
 
2
6
3
,
 
1
3
,
 
8
,
 
.
.
.

3
1
2
7
3
3
 
 
 
 
[
4
7
,
 
3
,
 
1
,
 
5
9
5
9
,
 
2
1
7
8
,
 
3
,
 
1
,
 
2
8
2
9
,
 
1
4
1
1
,
 
4
2
,
 
4
.
.
.

3
1
2
7
3
4
 
 
 
 
[
1
7
1
,
 
2
3
7
,
 
2
0
,
 
8
3
7
,
 
8
,
 
1
4
,
 
1
9
6
,
 
6
4
,
 
7
2
,
 
4
4
,
 
1
5
.
.
.

L
e
n
g
t
h
:
 
3
1
2
7
3
5
,
 
d
t
y
p
e
:
 
o
b
j
e
c
t
</pre>

```python
p
d
.
S
e
r
i
e
s
(
t
e
x
t
)
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
.
m
a
x
(
)
```

<pre>
2
1
4
2
</pre>

```python
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

s
n
s
.
d
i
s
p
l
o
t
(
p
d
.
S
e
r
i
e
s
(
t
e
x
t
)
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
0
,
3
0
0
)
```

<pre>
(
0
.
0
,
 
3
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
 
3
6
0
x
3
6
0
 
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
t
e
x
t
의
 
숫
자
 
갯
수
를
 
보
았
을
때
,
 
2
5
0
 
이
상
이
 
많
지
 
않
으
므
로
 
모
든
 
행
의
 
v
a
l
u
e
 
갯
수
를
 
2
5
0
으
로
 
변
경
합
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
s
e
q
u
e
n
c
e
 
i
m
p
o
r
t
 
p
a
d
_
s
e
q
u
e
n
c
e
s

p
a
d
_
t
e
x
t
=
p
a
d
_
s
e
q
u
e
n
c
e
s
(
t
e
x
t
,
 
m
a
x
l
e
n
=
2
5
0
)

p
a
d
_
t
e
x
t

p
a
d
_
t
e
x
t
.
s
h
a
p
e
```

<pre>
(
3
1
2
7
3
5
,
 
2
5
0
)
</pre>

```python
t
r
a
i
n
2
=
p
a
d
_
t
e
x
t
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
p
a
d
_
t
e
x
t
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
```

사
이
킷
런
의
 
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
 
:
 
원
본
 
데
이
터
 
세
트
에
서
 
학
습
 
및
 
테
스
트
 
데
이
터
 
세
트
를
 
쉽
게
 
분
리
할
 
수
 
있
습
니
다
.




t
e
s
t
 
s
i
z
e
 
:
 
전
체
 
데
이
터
에
서
 
테
스
트
 
데
이
터
 
세
트
 
크
기
를
 
얼
마
로
 
샘
플
링
할
 
것
인
가
 
결
정
 
(
2
0
%
로
 
설
정
)




t
r
a
i
n
 
s
i
z
e
 
:
 
전
체
 
데
이
터
에
서
 
학
습
 
데
이
터
 
세
트
 
크
기
를
 
얼
마
로
 
샘
플
링
할
 
것
인
가
 
결
정
,
 
대
부
분
 
t
e
s
t
 
s
i
z
e
만
 
사
용




s
h
u
f
f
l
e
 
:
 
데
이
터
 
분
리
 
전
에
 
섞
는
 
작
업
,
 
d
e
f
a
u
l
t
는
 
T
r
u
e




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
 
:
 
호
출
할
 
때
마
다
 
동
일
한
 
학
습
/
테
스
트
용
 
데
이
터
 
세
트
를
 
생
성
하
기
 
위
해
 
주
어
지
는
 
난
수
 
값
.
 
지
정
하
지
 
않
으
면
 
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
 
호
출
 
시
 
무
작
위
로
 
데
이
터
를
 
분
리
하
므
로
 
수
행
할
 
때
마
다
 
다
른
 
학
습
/
테
스
트
용
 
데
이
터
를
 
생
성
할
 
수
 
있
습
니
다
.
 
(
일
정
한
 
값
 
4
2
로
 
설
정
)




s
t
r
a
t
i
f
y
 
:
 
d
e
f
a
u
l
t
는
 
n
o
n
e
,
 
s
t
r
a
t
i
f
y
 
값
을
 
t
a
r
g
e
t
으
로
 
지
정
해
주
면
 
각
각
의
 
c
l
a
s
s
 
비
율
(
r
a
t
i
o
)
을
 
t
r
a
i
n
 
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
에
 
유
지
해
 
줍
니
다
.
 
한
 
쪽
에
 
쏠
려
서
 
분
배
되
는
 
것
을
 
방
지
합
니
다



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
t
r
a
i
n
[
"
정
답
 
c
o
l
u
m
n
"
]

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
t
r
a
i
n
[
"
t
o
x
i
c
"
]
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
"
t
o
x
i
c
"
]
)
```

m
o
d
e
l
 
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
을
 
이
용
하
여
 
순
차
 
학
습
을
 
진
행
합
니
다




*
E
m
b
e
d
d
i
n
g
(
v
o
c
a
b
_
s
i
z
e
,
 
e
m
b
e
d
d
i
n
g
_
d
i
m
,
 
i
n
p
u
t
_
l
e
n
g
t
h
)




v
o
c
a
b
s
i
z
e
 
:
 
총
 
단
어
의
 
갯
수




e
m
b
e
d
d
i
n
g
_
d
i
m
 
:
 
결
과
로
 
출
력
되
는
 
임
베
딩
 
벡
터
의
 
크
기
 
(
왜
 
3
?
?
?
?
?
?
?
?
?
?
?
)




i
n
p
u
t
_
l
e
n
g
t
h
 
:
 
입
력
 
시
퀀
스
의
 
길
이






L
S
T
M
과
 
D
E
N
S
E
 
L
A
Y
E
R
를
 
이
용
하
여
 
순
차
적
으
로
 
학
습
합
니
다
.






*
L
S
T
M


L
S
T
M
에
서
는
 
출
력
,
 
입
력
,
 
삭
제
 
게
이
트
라
는
 
3
개
의
 
게
이
트
가
 
존
재




L
S
T
M
 
(
L
o
n
g
 
S
h
o
r
t
 
T
e
r
m
 
M
e
m
o
r
y
)
는
 
기
존
의
 
R
N
N
이
 
출
력
과
 
먼
 
위
치
에
 
있
는
 
정
보
를
 
기
억
할
 
수
 
없
다
는
 
단
점
을
 
보
완
하
여
 
장
/
단
기
 
기
억
을
 
가
능
하
게
 
설
계
한
 
신
경
망
의
 
구
조




*
D
E
N
S
E
 
L
A
Y
E
R


입
력
과
 
출
력
을
 
모
두
 
연
결
해
 
주
며
,
 
입
력
과
 
출
력
을
 
각
각
 
연
결
해
주
는
 
가
중
치
를
 
포
함
하
고
 
있
다
.








v
e
r
b
o
s
e
 
=
 
학
습
 
중
 
출
력
되
는
 
문
구
를
 
설
정
합
니
다
.


-
 
0
 
:
 
아
무
 
것
도
 
출
력
하
지
 
않
습
니
다
.


-
 
1
 
:
 
훈
련
의
 
진
행
도
를
 
보
여
주
는
 
진
행
 
막
대
를
 
보
여
줍
니
다
.


-
 
2
 
:
 
미
니
 
배
치
마
다
 
손
실
 
정
보
를
 
출
력
합
니
다
.


[
r
m
s
p
r
o
p
]




A
d
a
g
r
a
d
는
 
실
제
로
 
무
한
히
 
계
속
 
학
습
하
다
보
면
 
어
느
 
순
간
 
갱
신
량
이
 
0
이
 
되
는
 
문
제
를
 
해
결
.




과
거
의
 
기
울
기
를
 
균
일
하
게
 
더
해
가
는
 
것
이
 
아
니
라
 
먼
 
과
거
의
 
기
울
기
는
 
서
서
히
 
잊
고
 
새
로
운
 
기
울
기
 
정
보
를
 
크
게
 
반
영
하
는
 
방
법
이
다
.
 
이
를
 
지
수
이
동
평
균
이
라
 
한
다
.
 




학
습
률
이
 
크
면
 
학
습
은
 
빠
르
나
 
최
적
의
 
가
중
치
를
 
지
나
칠
 
수
 
있
고
,
 
학
습
률
이
 
작
으
면
 
학
습
시
간
이
 
오
래
걸
려
 
기
울
기
에
 
따
라
 
학
습
률
을
 
조
정
하
여
 
최
적
의
 
해
 
부
근
에
서
 
학
습
률
이
 
작
아
지
도
록
 
하
는
 
방
법




알
엠
에
스
프
롭
은
 
아
다
그
라
드
의
 
G
(
i
)
 
값
이
 
무
한
히
 
커
지
는
 
것
을
 
방
지
하
고
자
 
제
안
된
 
방
법
으
로
 
아
다
그
라
드
 
함
수
에
 
감
마
 
값
을
 
추
가
하
여
 
사
용
자
가
 
감
마
값
을
 
이
용
하
여
 
학
습
률
 
크
기
를
 
비
율
로
 
조
정
할
 
수
 
있
도
록
 
했
습
니
다
.




​




알
엠
에
스
프
롭
은
 
일
반
적
으
로
 
순
환
 
신
경
망
(
R
e
c
u
r
r
e
n
t
 
N
e
r
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
s
)
의
 
옵
티
마
이
저
로
 
많
이
 
사
용
되
며
,
 
사
용
할
 
때
는
 
학
습
률
을
 
제
외
한
 
모
든
 
인
자
의
 
기
본
값
을
 
사
용
하
는
 
것
이
 
권
장
됩
니
다
.




F
o
r
 
a
 
m
u
l
t
i
-
c
l
a
s
s
 
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
 
p
r
o
b
l
e
m


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
r
m
s
p
r
o
p
'
,


 
 
 
 
 
 
 
 
 
 
 
 
 
 
l
o
s
s
=
'
s
p
a
r
s
e
_
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
,


 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
e
t
r
i
c
s
=
[
'
a
c
c
u
r
a
c
y
'
]
)




F
o
r
 
a
 
b
i
n
a
r
y
 
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
 
p
r
o
b
l
e
m


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
r
m
s
p
r
o
p
'
,


 
 
 
 
 
 
 
 
 
 
 
 
 
 
l
o
s
s
=
'
b
i
n
a
r
y
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
,


 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
e
t
r
i
c
s
=
[
'
a
c
c
u
r
a
c
y
'
]
)




F
o
r
 
a
 
m
e
a
n
 
s
q
u
a
r
e
d
 
e
r
r
o
r
 
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
 
p
r
o
b
l
e
m


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
r
m
s
p
r
o
p
'
,


 
 
 
 
 
 
 
 
 
 
 
 
 
 
l
o
s
s
=
'
m
s
e
'
)




#
 
데
이
터
가
 
m
u
l
t
i
-
c
l
a
s
s
 
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
 
p
r
o
b
l
e
m
에
 
해
당
 
하
므
로
,
 
손
실
 
함
수
는
 
'
s
p
a
r
s
e
_
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
를
 
사
용
하
는
 
것
이
 
적
합
합
니
다
.



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
r
m
s
p
r
o
p
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
l
o
s
s
=
'
s
p
a
r
s
e
_
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
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
e
t
r
i
c
s
=
[
'
a
c
c
u
r
a
c
y
'
]
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
2
0
2
2
-
0
3
-
3
0
 
0
3
:
1
8
:
2
5
.
3
6
9
3
1
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
3
8
6
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
4
5
9
3
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
5
7
2
5
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
7
3
1
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
7
9
8
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
3
-
3
0
 
0
3
:
1
8
:
2
5
.
4
4
8
5
8
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
3
-
3
0
 
0
3
:
1
8
:
2
7
.
3
7
3
2
5
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
3
-
3
0
 
0
3
:
1
8
:
2
7
.
3
7
4
1
7
3
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
3
-
3
0
 
0
3
:
1
8
:
2
7
.
3
7
4
8
9
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
3
-
3
0
 
0
3
:
1
8
:
2
7
.
3
7
5
6
0
2
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

2
0
2
2
-
0
3
-
3
0
 
0
3
:
1
8
:
2
8
.
1
2
0
6
0
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
5

</pre>
<pre>
2
0
2
2
-
0
3
-
3
0
 
0
3
:
1
8
:
3
0
.
5
2
3
2
7
2
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
9
9
8
/
9
9
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
6
s
 
1
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
 
n
a
n
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
9
0
3
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
 
n
a
n
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
9
0
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
9
0
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
 
n
a
n
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
9
0
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
9
0
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
 
n
a
n
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
9
0
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
9
0
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
 
n
a
n
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
9
0
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
9
0
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
 
n
a
n
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
9
0
4
2

</pre>
#
 
m
u
l
t
i
p
l
e
 
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
이
므
로
 
컴
파
일
의
 
l
o
s
s
를
 
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
로
 
지
정
하
면
 
a
c
c
u
r
a
c
y
가
 
현
저
히
 
낮
아
지
는
 
것
을
 
볼
 
수
 
있
습
니
다
.




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
는
 
이
진
분
류
에
 
적
합
하
므
로
 
데
이
터
를
 
o
n
e
-
h
o
t
 
e
n
c
o
d
i
n
g
 
처
리
한
 
경
우
 
사
용
 
가
능
하
다



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
r
m
s
p
r
o
p
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
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
e
t
r
i
c
s
=
[
'
a
c
c
u
r
a
c
y
'
]
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
4
s
 
1
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
0
0
e
+
0
0
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
0
0
0
e
+
0
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
0
0
e
+
0
0
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
0
0
0
e
+
0
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
0
0
e
+
0
0
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
0
0
0
e
+
0
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
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
0
0
0
e
+
0
0
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
0
0
0
e
+
0
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
0
0
e
+
0
0
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
0
0
0
e
+
0
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
r
m
s
p
r
o
p
'
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
l
o
s
s
=
'
b
i
n
a
r
y
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
,

 
 
 
 
 
 
 
 
 
 
 
 
 
 
m
e
t
r
i
c
s
=
[
'
a
c
c
u
r
a
c
y
'
]
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
6
s
 
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
2
0
4
1
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
4
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
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
2
6
9
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
0
3
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
0
 
-
 
v
a
l
_
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
4
s
 
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
1
0
4
4
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
u
r
a
c
y
:
 
0
.
0
9
5
8

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
0
3
1
 
-
 
a
c
c
u
r
a
c
y
:
 
0
.
0
9
5
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
u
r
a
c
y
:
 
0
.
0
9
5
8

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
r
m
s
p
r
o
p
'
,
 
l
o
s
s
=
'
m
s
e
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
4
s
 
1
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
9
0
4
2
 
-
 
a
c
c
:
 
0
.
0
9
5
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
9
0
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
0
9
5
8

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
9
0
4
2
 
-
 
a
c
c
:
 
0
.
0
9
5
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
9
0
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
0
9
5
8

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
9
0
4
2
 
-
 
a
c
c
:
 
0
.
0
9
5
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
9
0
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
0
9
5
8

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
1
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
9
0
4
2
 
-
 
a
c
c
:
 
0
.
0
9
5
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
9
0
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
0
9
5
8

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
9
0
4
2
 
-
 
a
c
c
:
 
0
.
0
9
5
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
9
0
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
0
9
5
8

</pre>
*
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


-
 
s
i
g
m
o
i
d
 
:
 
이
진
 
분
류
 
문
제
에
서
 
출
력
층
에
 
주
로
 
사
용
되
는
 
활
성
화
 
함
수
.


-
 
l
i
n
e
a
r
 
:
 
디
폴
트
 
값
으
로
 
별
도
 
활
성
화
 
함
수
 
없
이
 
입
력
 
뉴
런
과
 
가
중
치
의
 
계
산
 
결
과
 
그
대
로
 
출
력
.


-
 
s
o
f
t
m
a
x
 
:
 
셋
 
이
상
의
 
선
택
지
 
중
 
하
나
를
 
택
하
는
 
다
중
 
클
래
스
 
분
류
 
문
제
에
서
 
출
력
층
에
 
주
로
 
사
용
되
는
 
활
성
화
 
함
수
.


-
 
r
e
l
u
 
:
 
은
닉
층
에
 
주
로
 
사
용
되
는
 
활
성
화
 
함
수
.






#
 
데
이
터
를
 
사
용
하
여
 
예
측
 
할
 
때
,


#
 
초
기
 
속
도
(
l
i
n
e
a
r
>
r
e
l
u
>
s
o
f
t
m
a
x
)
 
최
종
속
도
(
s
o
f
t
m
a
x
>
r
e
l
u
>
l
i
n
e
a
r
)
 
의
 
경
향
을
 
보
여
 
학
습
이
 
복
잡
하
고
 
데
이
터
가
 
방
대
할
 
수
록
 
s
o
f
t
m
a
x
가
 
유
리
할
 
것
으
로
 
보
입
니
다
.






#
 
초
기
 
A
C
C
R
A
C
Y
(
l
i
n
e
a
r
>
r
e
l
u
>
s
o
f
t
m
a
x
)
 
이
나
,
 
학
습
을
 
진
행
하
면
서
 
a
c
c
u
r
a
c
y
의
 
차
이
는
 
줄
어
드
는
 
것
으
로
 
보
입
니
다
.


[
a
d
a
m
]




R
M
S
P
r
o
p
과
 
모
멘
텀
의
 
개
념
을
 
합
친
 
것
.


학
습
률
은
 
기
울
기
에
 
따
라
 
조
정
하
되
 
관
성
을
 
통
해
 
지
역
 
최
솟
값
에
 
갇
히
지
 
않
도
록
 
하
여
 
가
장
 
많
이
 
사
용
.




아
담
은
 
모
멘
텀
과
 
알
엠
에
스
프
롭
의
 
장
점
을
 
결
합
한
 
경
사
 
하
강
법
입
니
다
.
 
알
엠
에
스
프
롭
의
 
특
징
인
 
기
울
기
 
제
곱
을
 
지
수
 
평
균
한
 
값
과
 
모
멘
텀
의
 
특
징
을
 
수
식
에
 
활
용
하
는
데
 
알
엠
에
스
프
롭
의
 
G
함
수
와
 
모
멘
텀
을
 
이
용
하
여
 
가
중
치
를
 
업
데
이
트
합
니
다
.






​




아
담
은
 
두
 
개
의
 
모
멘
텀
을
 
활
용
하
는
데
 
m
(
F
i
r
s
t
 
m
o
m
e
n
t
u
m
)
과
 
v
(
S
e
c
o
n
d
 
m
o
m
e
n
t
u
m
)
이
 
그
것
입
니
다
.
 
m
은
 
기
존
의
 
모
멘
텀
과
 
동
일
하
게
 
G
r
a
d
i
e
n
t
 
값
을
 
좀
 
더
 
빠
르
게
 
계
산
할
 
수
 
있
도
록
 
돕
는
 
역
할
을
 
하
고
 
v
는
 
데
이
터
의
 
분
포
가
 
띄
엄
띄
엄
한
 
영
역
에
서
 
영
향
력
을
 
극
대
화
시
켜
 
해
당
 
영
역
을
 
벗
어
날
 
수
 
있
도
록
 
돕
는
 
역
할
을
 
합
니
다
.
 
아
담
은
 
각
기
 
다
른
 
분
야
의
 
장
점
을
 
합
쳐
 
우
수
한
 
성
능
으
로
 
보
편
적
으
로
 
많
이
 
사
용
되
는
 
옵
티
마
이
저
 
중
 
하
나
입
니
다
.



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
l
i
n
e
a
r
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
2
0
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
2
0

9
9
8
/
9
9
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
5
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
1
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
2
0
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
2
0

9
9
8
/
9
9
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
5
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
3
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
1
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
8
/
2
0

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
r
e
l
u
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
2
0
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
2
0

9
9
8
/
9
9
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
4
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
1
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
5
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
G
R
U
]




G
R
U
는
 
L
S
T
M
의
 
장
기
 
의
존
성
 
문
제
에
 
대
한
 
해
결
책
을
 
유
지
하
면
서
,
 
은
닉
 
상
태
를
 
업
데
이
트
하
는
 
계
산
을
 
줄
였
습
니
다
.
 
다
시
 
말
해
서
,
 
G
R
U
는
 
성
능
은
 
L
S
T
M
과
 
유
사
하
면
서
 
복
잡
했
던
 
L
S
T
M
의
 
구
조
를
 
간
단
화
 
시
켰
습
니
다
.




G
R
U
와
 
L
S
T
M
 
중
 
어
떤
 
것
이
 
모
델
의
 
성
능
면
에
서
 
더
 
낫
다
라
고
 
단
정
지
어
 
말
할
 
수
 
없
으
며
,
 
기
존
에
 
L
S
T
M
을
 
사
용
하
면
서
 
최
적
의
 
하
이
퍼
파
라
미
터
를
 
찾
아
낸
 
상
황
이
라
면
 
굳
이
 
G
R
U
로
 
바
꿔
서
 
사
용
할
 
필
요
는
 
없
습
니
다
.




경
험
적
으
로
 
데
이
터
 
양
이
 
적
을
 
때
는
 
매
개
 
변
수
의
 
양
이
 
적
은
 
G
R
U
가
 
조
금
 
더
 
낫
고
,
 
데
이
터
 
양
이
 
더
 
많
으
면
 
L
S
T
M
이
 
더
 
낫
다
고
도
 
합
니
다
.
 
G
R
U
보
다
 
L
S
T
M
에
 
대
한
 
연
구
나
 
사
용
량
이
 
더
 
많
은
데
,
 
이
는
 
L
S
T
M
이
 
더
 
먼
저
 
나
온
 
구
조
이
기
 
때
문
입
니
다
.




#
 
데
이
터
에
 
적
용
하
였
을
 
때
,
 
L
S
T
M
과
 
G
R
U
의
 
A
C
C
U
R
A
C
Y
와
 
학
습
 
시
간
의
 
차
이
는
 
거
의
 
없
습
니
다
.



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
G
R
U
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
2
0
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
 
```

<pre>
E
p
o
c
h
 
1
/
2
0

9
9
8
/
9
9
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
5
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
2
0

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
0
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
1
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
2
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
3
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
4
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
5
/
2
0

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
6
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
7
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
8
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
1
9
/
2
0

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
0
/
2
0

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
S
G
D
]


일
부
의
 
데
이
터
 
샘
플
만
 
무
작
위
로
 
추
출
하
여
 
경
사
 
하
강
법
에
 
사
용
,
 
학
습
 
속
도
 
개
선



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
S
G
D
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
4
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
A
d
a
d
e
l
t
a
]




훈
련
 
전
반
에
 
걸
쳐
 
학
습
률
이
 
지
속
적
으
로
 
감
소
.




과
거
의
 
모
든
 
그
래
디
언
트
를
 
누
적
하
는
 
대
신
 
그
래
디
언
트
 
업
데
이
트
의
 
이
동
 
창
을
 
기
반
으
로
 
학
습
률
을
 
조
정
.
 
많
은
 
업
데
이
트
가
 
수
행
된
 
경
우
에
도
 
계
속
 
학
습
.




A
d
a
g
r
a
d
에
 
비
해
 
A
d
a
d
e
l
t
a
는
 
초
기
 
학
습
률
을
 
설
정
할
 
필
요
가
 
없
음




아
다
델
타
는
 
학
습
률
이
 
0
에
 
가
까
워
지
는
 
문
제
를
 
해
결
하
기
 
위
해
 
모
든
 
그
래
디
언
트
의
 
제
곱
합
인
 
G
값
 
대
신
에
 
이
전
 
개
수
 
만
큼
을
 
제
곱
하
여
 
더
한
 
값
의
 
평
균
을
 
사
용
하
여
 
학
습
을
 
진
행
합
니
다
.
 
아
다
델
타
는
 
아
다
그
라
드
의
 
수
식
에
서
 
학
습
률
을
 
가
중
치
의
 
변
화
량
 
크
기
를
 
누
적
한
 
값
으
로
 
변
환
했
기
 
때
문
에
 
학
습
률
에
 
대
한
 
하
이
퍼
 
파
라
미
터
가
 
필
요
하
지
 
않
습
니
다
.



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
A
d
a
d
e
l
t
a
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
4
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
3
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
A
d
a
g
r
a
d
]




A
d
a
p
t
i
v
e
 
G
r
a
d
i
e
n
t
의
 
합
성
 
단
어
로
 
이
 
o
p
t
i
m
i
z
e
r
에
서
는
 
학
습
률
이
 
매
우
 
중
요
한
 
역
할
을
 
한
다
.
 
기
존
의
 
o
p
t
i
m
i
z
e
r
들
에
서
는
 
학
습
률
은
 
따
로
 
건
드
리
지
 
않
았
었
는
데
 
a
d
a
g
r
a
d
는
 
학
습
을
 
진
행
하
면
서
 
학
습
률
을
 
점
차
 
줄
여
가
는
 
방
법
을
 
사
용
한
다
.
 
처
음
에
는
 
크
게
 
학
습
하
다
가
 
조
금
씩
 
작
게
 
학
습
한
다
는
 
얘
기
로
,
 
실
제
 
신
경
망
에
서
 
많
이
 
쓰
이
는
 
방
식
이
다
.
 




​




많
이
 
변
화
하
지
 
않
은
 
변
수
들
은
 
학
습
률
(
s
t
e
p
 
s
i
z
e
)
를
 
크
게
하
고
,
 
반
대
로
 
많
이
 
변
화
한
 
변
수
들
에
 
대
해
서
는
 
학
습
률
을
 
적
게
합
니
다
.
 
이
는
 
많
이
 
변
화
한
 
변
수
는
 
최
적
값
에
 
근
접
했
을
 
것
이
라
는
 
가
정
하
에
 
작
은
 
크
기
로
 
이
동
하
면
서
 
세
밀
한
 
값
을
 
조
정
하
고
,
 
반
대
로
 
적
게
 
변
화
한
 
변
수
들
은
 
학
습
률
을
 
크
게
하
여
 
빠
르
게
 
l
o
s
s
값
을
 
줄
입
니
다
.






‘
A
d
a
’
p
t
i
v
e
와
 
‘
G
r
a
d
’
i
e
n
t
의
 
합
성
어
인
 
아
다
그
라
드
는
 
적
응
형
 
경
사
하
강
법
으
로
 
업
데
이
트
 
횟
수
에
 
따
라
 
학
습
률
을
 
조
정
하
는
 
옵
티
마
이
저
입
니
다
.
 
아
다
그
라
드
는
 
많
이
 
변
화
하
지
 
않
는
 
변
수
들
의
 
학
습
률
은
 
크
게
 
하
고
,
 
많
이
 
변
화
하
는
 
변
수
들
의
 
학
습
률
은
 
작
게
 
합
니
다
.
 
자
세
하
게
 
살
펴
보
면
 
기
울
기
 
크
기
가
 
누
적
되
는
 
변
수
값
 
G
(
i
)
에
 
따
라
 
파
라
미
터
가
 
변
하
는
데
 
파
라
미
터
가
 
많
이
 
학
습
되
었
으
면
 
작
은
 
학
습
률
로
 
업
데
이
터
하
고
,
 
학
습
이
 
덜
 
되
었
으
면
 
개
선
이
 
더
 
필
요
하
기
 
때
문
에
 
높
은
 
학
습
률
로
 
업
데
이
트
되
는
 
원
리
입
니
다
.






​




아
다
그
라
드
는
 
학
습
률
을
 
조
정
해
주
지
 
않
아
도
 
적
절
한
 
학
습
률
을
 
적
용
한
다
는
 
장
점
이
 
있
지
만
 
학
습
률
이
 
점
점
 
줄
어
들
다
가
 
반
복
 
학
습
 
이
후
에
는
 
파
라
미
터
가
 
갱
신
되
지
 
않
는
 
문
제
가
 
있
습
니
다
.



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
A
d
a
g
r
a
d
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
4
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
2
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
A
d
a
m
a
x
]




a
d
a
m
 
모
델
에
서
 
무
한
대
로
 
진
행
하
는
 
것
을
 
기
반
.




임
베
딩
 
모
델
에
서
 
a
d
a
m
보
다
 
성
능
이
 
우
수
한
 
경
우
 
빈
번



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
A
d
a
m
a
x
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
5
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
3
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
[
N
a
d
a
m
]


n
a
d
a
m
은
 
아
담
의
 
두
 
결
합
 
요
소
중
 
하
나
인
 
모
멘
텀
 
대
신
에
 
네
스
테
로
프
 
모
멘
텀
을
 
결
합
한
 
옵
티
마
이
저
입
니
다
.
 
아
담
과
 
다
르
게
 
N
a
d
a
m
은
 
현
재
 
위
치
에
서
 
G
r
a
d
i
e
n
t
 
값
을
 
계
산
하
는
 
것
이
 
아
닌
 
모
멘
텀
 
방
향
으
로
 
이
동
한
 
뒤
 
새
로
운
 
위
치
에
서
 
G
r
a
d
i
e
n
t
 
값
을
 
계
산
하
게
 
됩
니
다
.
 
(
N
a
d
a
m
을
 
사
용
할
 
때
는
 
모
든
 
인
자
의
 
기
본
값
 
사
용
이
 
권
장
됩
니
다
.
)







```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
N
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
6
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
3
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
#
 
초
기
 
속
도


#
 
S
G
D
>
A
D
A
D
E
L
T
A
=
A
D
A
M
>
A
D
A
G
R
A
D
>
A
D
A
M
A
X
>
N
A
D
A
M


#
 


#
 
초
기
 
A
C
C
U
R
A
C
Y


#
 
N
A
D
A
M
=
S
G
D
>
A
D
A
D
E
L
T
A
=
A
D
A
G
R
A
D
=
A
D
A
M
A
X
=
A
D
A
M


#
 


#
 
전
체
 
속
도


#
 
S
G
D
>
A
D
A
D
E
L
T
A
=
A
D
A
G
R
A
D
>
A
D
A
M
>
A
D
A
M
A
X
>
N
A
D
A
M


#
 


#
 
속
도
에
서
는
 
S
G
D
가
 
우
수
한
 
것
으
로
 
보
이
는
데
,
 
방
대
한
 
데
이
터
를
 
빠
르
게
 
처
리
할
 
경
우
 
S
G
D
가
 
필
요
할
 
것
 
같
습
니
다
.


#
 


#
 
A
C
C
U
R
A
C
Y
 
면
에
서
 
초
기
에
는
 
S
G
D
와
 
N
A
D
A
M
이
 
우
수
해
 
보
이
나
,
 
학
습
이
 
반
복
되
면
서
 
차
이
가
 
작
아
집
니
다
.


[
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
]




정
규
화
 
하
여
 
오
차
 
적
게
 
나
올
 
수
 
있
도
록
 
사
용



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
 
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
5
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
 
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
6
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
3
s
 
1
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>

```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
L
S
T
M
(
3
2
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
 
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
6
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
4
s
 
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
 
n
a
n
 
-
 
a
c
c
:
 
0
.
9
0
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
 
n
a
n
 
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
4
2

</pre>
#
 
e
m
b
e
d
d
i
n
g
 
l
a
y
e
r
,
 
L
S
T
M
 
l
a
y
e
r
,
 
D
e
n
s
e
 
l
a
y
e
r
 
에
서
 
정
규
화
의
 
시
기
는
 
이
 
데
이
터
에
서
 
a
c
c
u
r
a
c
y
에
 
크
게
 
영
향
을
 
주
지
 
않
아
 
시
간
이
 
비
교
적
 
유
리
한
 
e
m
b
e
d
d
i
n
g
 
직
후
가
 
적
합
할
 
것
으
로
 
보
입
니
다



```python
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
m
b
e
d
d
i
n
g
(
l
e
n
(
T
K
.
w
o
r
d
_
i
n
d
e
x
)
+
1
,
3
,
i
n
p
u
t
_
l
e
n
g
t
h
=
2
5
0
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
,
i
n
p
u
t
_
d
i
m
=
6
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
"
s
o
f
t
m
a
x
"
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
"
a
d
a
m
"
,
 
l
o
s
s
=
"
s
p
a
r
s
e
_
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
"
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
x
_
t
r
a
i
n
,
 
y
_
t
r
a
i
n
,
 
e
p
o
c
h
s
=
5
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
2
8
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
(
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
v
a
l
i
d
)
)

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
2
)
 
```

<pre>
E
p
o
c
h
 
1
/
5

9
9
8
/
9
9
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
s
 
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
 
5
.
5
2
1
5
 
-
 
a
c
c
:
 
0
.
0
9
5
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
 
5
.
5
2
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
0
9
5
8

E
p
o
c
h
 
2
/
5

9
9
8
/
9
9
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
s
 
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
 
5
.
5
2
1
5
 
-
 
a
c
c
:
 
0
.
0
9
5
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
 
5
.
5
2
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
0
9
5
8

E
p
o
c
h
 
3
/
5

9
9
8
/
9
9
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
s
 
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
 
5
.
5
2
1
5
 
-
 
a
c
c
:
 
0
.
0
9
5
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
 
5
.
5
2
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
0
9
5
8

E
p
o
c
h
 
4
/
5

9
9
8
/
9
9
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
s
 
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
 
5
.
5
2
1
5
 
-
 
a
c
c
:
 
0
.
0
9
5
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
 
5
.
5
2
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
0
9
5
8

E
p
o
c
h
 
5
/
5

9
9
8
/
9
9
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
s
 
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
 
5
.
5
2
1
5
 
-
 
a
c
c
:
 
0
.
0
9
5
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
 
5
.
5
2
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
0
9
5
8

</pre>
위
 
c
a
s
e
를
 
적
용
하
였
을
 
때
,
 
2
번
 
c
a
s
e
에
서
 
s
c
o
r
e
 
0
.
5
7
4
5
0
 
나
머
지
 
c
a
s
e
는
 
s
c
o
r
e
 
0
.
5
0
0
0
으
로
 
동
일
하
였
습
니
다




#
 
L
S
T
M
 
l
a
y
e
r
를
 
삭
제
할
 
경
우
,
 
이
외
의
 
조
건
이
 
동
일
할
 
때
 
보
다
 
a
c
c
u
r
a
c
y
가
 
크
게
 
저
하
되
는
데
 
이
는
 
앞
서
 
학
습
한
 
것
에
 
대
한
 
기
억
을
 
잃
었
기
 
때
문
입
니
다
.


#
 
따
라
서
 
L
S
T
M
 
l
a
y
e
r
를
 
사
용
하
는
 
것
이
 
적
합
합
니
다
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
j
i
g
s
a
w
-
t
o
x
i
c
-
c
o
m
m
e
n
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
t
o
x
i
c
 
 
s
e
v
e
r
e
_
t
o
x
i
c
 
 
o
b
s
c
e
n
e
 
 
t
h
r
e
a
t
 
 
i
n
s
u
l
t
 
 
\

0
 
 
 
 
 
 
 
0
0
0
0
1
c
e
e
3
4
1
f
d
b
1
2
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

1
 
 
 
 
 
 
 
0
0
0
0
2
4
7
8
6
7
8
2
3
e
f
7
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

2
 
 
 
 
 
 
 
0
0
0
1
3
b
1
7
a
d
2
2
0
c
4
6
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

3
 
 
 
 
 
 
 
0
0
0
1
7
5
6
3
c
3
f
7
9
1
9
a
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

4
 
 
 
 
 
 
 
0
0
0
1
7
6
9
5
a
d
8
9
9
7
e
b
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
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
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
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
3
1
5
9
 
 
f
f
f
c
d
0
9
6
0
e
e
3
0
9
b
5
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

1
5
3
1
6
0
 
 
f
f
f
d
7
a
9
a
6
e
b
3
2
c
1
6
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

1
5
3
1
6
1
 
 
f
f
f
d
a
9
e
8
d
6
f
a
f
a
9
e
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

1
5
3
1
6
2
 
 
f
f
f
e
8
f
1
3
4
0
a
7
9
f
c
2
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 

1
5
3
1
6
3
 
 
f
f
f
f
c
e
3
f
b
1
8
3
e
e
8
0
 
 
 
 
0
.
5
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 
 
 
0
.
5
 
 
 


 
 
 
 
 
 
 
 
i
d
e
n
t
i
t
y
_
h
a
t
e
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 

1
5
3
1
5
9
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

1
5
3
1
6
0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

1
5
3
1
6
1
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

1
5
3
1
6
2
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 

1
5
3
1
6
3
 
 
 
 
 
 
 
 
 
 
 
 
0
.
5
 
 


[
1
5
3
1
6
4
 
r
o
w
s
 
x
 
7
 
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
]
,

 
 
 
 
 
 
 
[
0
]
,

 
 
 
 
 
 
 
[
0
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
0
]
,

 
 
 
 
 
 
 
[
0
]
,

 
 
 
 
 
 
 
[
0
]
]
)
</pre>

```python
s
u
b
[
"
T
o
x
i
c
"
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
0
)
```

E
R
R
O
R
:
 
C
o
u
l
d
 
n
o
t
 
p
a
r
s
e
 
'
'
 
i
n
t
o
 
e
x
p
e
c
t
e
d
 
t
y
p
e
 
o
f
 
D
o
u
b
l
e
 
(
L
i
n
e
 
2
,
 
C
o
l
u
m
n
 
1
8
)


와
 
같
은
 
E
R
R
를
 
해
결
 
하
고
자
 
s
u
b
[
'
t
o
x
i
c
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
로
 
수
정
하
였
습
니
다
.

