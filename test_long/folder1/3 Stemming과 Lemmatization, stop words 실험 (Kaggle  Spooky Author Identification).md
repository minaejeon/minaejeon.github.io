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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
 
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
t
e
x
t
 
a
u
t
h
o
r

0
 
 
 
 
 
 
i
d
2
6
3
0
5
 
 
T
h
i
s
 
p
r
o
c
e
s
s
,
 
h
o
w
e
v
e
r
,
 
a
f
f
o
r
d
e
d
 
m
e
 
n
o
 
m
e
a
n
s
 
o
f
.
.
.
 
 
 
 
E
A
P

1
 
 
 
 
 
 
i
d
1
7
5
6
9
 
 
I
t
 
n
e
v
e
r
 
o
n
c
e
 
o
c
c
u
r
r
e
d
 
t
o
 
m
e
 
t
h
a
t
 
t
h
e
 
f
u
m
b
l
i
n
g
.
.
.
 
 
 
 
H
P
L

2
 
 
 
 
 
 
i
d
1
1
0
0
8
 
 
I
n
 
h
i
s
 
l
e
f
t
 
h
a
n
d
 
w
a
s
 
a
 
g
o
l
d
 
s
n
u
f
f
 
b
o
x
,
 
f
r
o
m
 
w
h
.
.
.
 
 
 
 
E
A
P

3
 
 
 
 
 
 
i
d
2
7
7
6
3
 
 
H
o
w
 
l
o
v
e
l
y
 
i
s
 
s
p
r
i
n
g
 
A
s
 
w
e
 
l
o
o
k
e
d
 
f
r
o
m
 
W
i
n
d
s
o
r
.
.
.
 
 
 
 
M
W
S

4
 
 
 
 
 
 
i
d
1
2
9
5
8
 
 
F
i
n
d
i
n
g
 
n
o
t
h
i
n
g
 
e
l
s
e
,
 
n
o
t
 
e
v
e
n
 
g
o
l
d
,
 
t
h
e
 
S
u
p
e
r
.
.
.
 
 
 
 
H
P
L

.
.
.
 
 
 
 
 
 
 
 
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
9
5
7
4
 
 
i
d
1
7
7
1
8
 
 
I
 
c
o
u
l
d
 
h
a
v
e
 
f
a
n
c
i
e
d
,
 
w
h
i
l
e
 
I
 
l
o
o
k
e
d
 
a
t
 
i
t
,
 
t
h
.
.
.
 
 
 
 
E
A
P

1
9
5
7
5
 
 
i
d
0
8
9
7
3
 
 
T
h
e
 
l
i
d
s
 
c
l
e
n
c
h
e
d
 
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
 
t
o
g
e
t
h
e
r
 
a
s
 
i
f
 
i
n
.
.
.
 
 
 
 
E
A
P

1
9
5
7
6
 
 
i
d
0
5
2
6
7
 
 
M
a
i
s
 
i
l
 
f
a
u
t
 
a
g
i
r
 
t
h
a
t
 
i
s
 
t
o
 
s
a
y
,
 
a
 
F
r
e
n
c
h
m
a
n
 
.
.
.
 
 
 
 
E
A
P

1
9
5
7
7
 
 
i
d
1
7
5
1
3
 
 
F
o
r
 
a
n
 
i
t
e
m
 
o
f
 
n
e
w
s
 
l
i
k
e
 
t
h
i
s
,
 
i
t
 
s
t
r
i
k
e
s
 
u
s
 
i
.
.
.
 
 
 
 
E
A
P

1
9
5
7
8
 
 
i
d
0
0
3
9
3
 
 
H
e
 
l
a
i
d
 
a
 
g
n
a
r
l
e
d
 
c
l
a
w
 
o
n
 
m
y
 
s
h
o
u
l
d
e
r
,
 
a
n
d
 
i
t
 
.
.
.
 
 
 
 
H
P
L


[
1
9
5
7
9
 
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
<pre>
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
t
e
x
t

0
 
 
 
 
 
i
d
0
2
3
1
0
 
 
S
t
i
l
l
,
 
a
s
 
I
 
u
r
g
e
d
 
o
u
r
 
l
e
a
v
i
n
g
 
I
r
e
l
a
n
d
 
w
i
t
h
 
s
u
c
.
.
.

1
 
 
 
 
 
i
d
2
4
5
4
1
 
 
I
f
 
a
 
f
i
r
e
 
w
a
n
t
e
d
 
f
a
n
n
i
n
g
,
 
i
t
 
c
o
u
l
d
 
r
e
a
d
i
l
y
 
b
e
 
.
.
.

2
 
 
 
 
 
i
d
0
0
1
3
4
 
 
A
n
d
 
w
h
e
n
 
t
h
e
y
 
h
a
d
 
b
r
o
k
e
n
 
d
o
w
n
 
t
h
e
 
f
r
a
i
l
 
d
o
o
r
 
t
.
.
.

3
 
 
 
 
 
i
d
2
7
7
5
7
 
 
W
h
i
l
e
 
I
 
w
a
s
 
t
h
i
n
k
i
n
g
 
h
o
w
 
I
 
s
h
o
u
l
d
 
p
o
s
s
i
b
l
y
 
m
a
n
.
.
.

4
 
 
 
 
 
i
d
0
4
0
8
1
 
 
I
 
a
m
 
n
o
t
 
s
u
r
e
 
t
o
 
w
h
a
t
 
l
i
m
i
t
 
h
i
s
 
k
n
o
w
l
e
d
g
e
 
m
a
y
 
.
.
.

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
3
8
7
 
 
i
d
1
1
7
4
9
 
 
 
 
 
 
 
 
 
A
l
l
 
t
h
i
s
 
i
s
 
n
o
w
 
t
h
e
 
f
i
t
t
e
r
 
f
o
r
 
m
y
 
p
u
r
p
o
s
e
.

8
3
8
8
 
 
i
d
1
0
5
2
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
I
 
f
i
x
e
d
 
m
y
s
e
l
f
 
o
n
 
a
 
w
i
d
e
 
s
o
l
i
t
u
d
e
.

8
3
8
9
 
 
i
d
1
3
4
7
7
 
 
I
t
 
i
s
 
e
a
s
i
l
y
 
u
n
d
e
r
s
t
o
o
d
 
t
h
a
t
 
w
h
a
t
 
m
i
g
h
t
 
i
m
p
r
o
v
.
.
.

8
3
9
0
 
 
i
d
1
3
7
6
1
 
 
B
e
 
t
h
i
s
 
a
s
 
i
t
 
m
a
y
,
 
I
 
n
o
w
 
b
e
g
a
n
 
t
o
 
f
e
e
l
 
t
h
e
 
i
n
s
.
.
.

8
3
9
1
 
 
i
d
0
4
2
8
2
 
 
L
o
n
g
 
w
i
n
d
e
d
,
 
s
t
a
t
i
s
t
i
c
a
l
,
 
a
n
d
 
d
r
e
a
r
i
l
y
 
g
e
n
e
a
l
o
.
.
.


[
8
3
9
2
 
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
t
e
x
t
'
]
[
0
]
```

<pre>
'
T
h
i
s
 
p
r
o
c
e
s
s
,
 
h
o
w
e
v
e
r
,
 
a
f
f
o
r
d
e
d
 
m
e
 
n
o
 
m
e
a
n
s
 
o
f
 
a
s
c
e
r
t
a
i
n
i
n
g
 
t
h
e
 
d
i
m
e
n
s
i
o
n
s
 
o
f
 
m
y
 
d
u
n
g
e
o
n
;
 
a
s
 
I
 
m
i
g
h
t
 
m
a
k
e
 
i
t
s
 
c
i
r
c
u
i
t
,
 
a
n
d
 
r
e
t
u
r
n
 
t
o
 
t
h
e
 
p
o
i
n
t
 
w
h
e
n
c
e
 
I
 
s
e
t
 
o
u
t
,
 
w
i
t
h
o
u
t
 
b
e
i
n
g
 
a
w
a
r
e
 
o
f
 
t
h
e
 
f
a
c
t
;
 
s
o
 
p
e
r
f
e
c
t
l
y
 
u
n
i
f
o
r
m
 
s
e
e
m
e
d
 
t
h
e
 
w
a
l
l
.
'
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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
t
e
x
t
 
a
u
t
h
o
r

0
 
 
 
 
 
i
d
2
6
3
0
5
 
 
T
h
i
s
 
p
r
o
c
e
s
s
,
 
h
o
w
e
v
e
r
,
 
a
f
f
o
r
d
e
d
 
m
e
 
n
o
 
m
e
a
n
s
 
o
f
.
.
.
 
 
 
 
E
A
P

1
 
 
 
 
 
i
d
1
7
5
6
9
 
 
I
t
 
n
e
v
e
r
 
o
n
c
e
 
o
c
c
u
r
r
e
d
 
t
o
 
m
e
 
t
h
a
t
 
t
h
e
 
f
u
m
b
l
i
n
g
.
.
.
 
 
 
 
H
P
L

2
 
 
 
 
 
i
d
1
1
0
0
8
 
 
I
n
 
h
i
s
 
l
e
f
t
 
h
a
n
d
 
w
a
s
 
a
 
g
o
l
d
 
s
n
u
f
f
 
b
o
x
,
 
f
r
o
m
 
w
h
.
.
.
 
 
 
 
E
A
P

3
 
 
 
 
 
i
d
2
7
7
6
3
 
 
H
o
w
 
l
o
v
e
l
y
 
i
s
 
s
p
r
i
n
g
 
A
s
 
w
e
 
l
o
o
k
e
d
 
f
r
o
m
 
W
i
n
d
s
o
r
.
.
.
 
 
 
 
M
W
S

4
 
 
 
 
 
i
d
1
2
9
5
8
 
 
F
i
n
d
i
n
g
 
n
o
t
h
i
n
g
 
e
l
s
e
,
 
n
o
t
 
e
v
e
n
 
g
o
l
d
,
 
t
h
e
 
S
u
p
e
r
.
.
.
 
 
 
 
H
P
L

.
.
.
 
 
 
 
 
 
 
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
3
8
7
 
 
i
d
1
1
7
4
9
 
 
 
 
 
 
 
 
 
A
l
l
 
t
h
i
s
 
i
s
 
n
o
w
 
t
h
e
 
f
i
t
t
e
r
 
f
o
r
 
m
y
 
p
u
r
p
o
s
e
.
 
 
 
 
N
a
N

8
3
8
8
 
 
i
d
1
0
5
2
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
I
 
f
i
x
e
d
 
m
y
s
e
l
f
 
o
n
 
a
 
w
i
d
e
 
s
o
l
i
t
u
d
e
.
 
 
 
 
N
a
N

8
3
8
9
 
 
i
d
1
3
4
7
7
 
 
I
t
 
i
s
 
e
a
s
i
l
y
 
u
n
d
e
r
s
t
o
o
d
 
t
h
a
t
 
w
h
a
t
 
m
i
g
h
t
 
i
m
p
r
o
v
.
.
.
 
 
 
 
N
a
N

8
3
9
0
 
 
i
d
1
3
7
6
1
 
 
B
e
 
t
h
i
s
 
a
s
 
i
t
 
m
a
y
,
 
I
 
n
o
w
 
b
e
g
a
n
 
t
o
 
f
e
e
l
 
t
h
e
 
i
n
s
.
.
.
 
 
 
 
N
a
N

8
3
9
1
 
 
i
d
0
4
2
8
2
 
 
L
o
n
g
 
w
i
n
d
e
d
,
 
s
t
a
t
i
s
t
i
c
a
l
,
 
a
n
d
 
d
r
e
a
r
i
l
y
 
g
e
n
e
a
l
o
.
.
.
 
 
 
 
N
a
N


[
2
7
9
7
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
a
u
t
h
o
r
'
]
.
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
a
r
r
a
y
(
[
'
E
A
P
'
,
 
'
H
P
L
'
,
 
'
M
W
S
'
,
 
n
a
n
]
,
 
d
t
y
p
e
=
o
b
j
e
c
t
)
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
t
e
x
t
'
]
```

<pre>
0
 
 
 
 
 
 
 
T
h
i
s
 
p
r
o
c
e
s
s
,
 
h
o
w
e
v
e
r
,
 
a
f
f
o
r
d
e
d
 
m
e
 
n
o
 
m
e
a
n
s
 
o
f
.
.
.

1
 
 
 
 
 
 
 
I
t
 
n
e
v
e
r
 
o
n
c
e
 
o
c
c
u
r
r
e
d
 
t
o
 
m
e
 
t
h
a
t
 
t
h
e
 
f
u
m
b
l
i
n
g
.
.
.

2
 
 
 
 
 
 
 
I
n
 
h
i
s
 
l
e
f
t
 
h
a
n
d
 
w
a
s
 
a
 
g
o
l
d
 
s
n
u
f
f
 
b
o
x
,
 
f
r
o
m
 
w
h
.
.
.

3
 
 
 
 
 
 
 
H
o
w
 
l
o
v
e
l
y
 
i
s
 
s
p
r
i
n
g
 
A
s
 
w
e
 
l
o
o
k
e
d
 
f
r
o
m
 
W
i
n
d
s
o
r
.
.
.

4
 
 
 
 
 
 
 
F
i
n
d
i
n
g
 
n
o
t
h
i
n
g
 
e
l
s
e
,
 
n
o
t
 
e
v
e
n
 
g
o
l
d
,
 
t
h
e
 
S
u
p
e
r
.
.
.

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

8
3
8
7
 
 
 
 
 
 
 
 
 
 
 
A
l
l
 
t
h
i
s
 
i
s
 
n
o
w
 
t
h
e
 
f
i
t
t
e
r
 
f
o
r
 
m
y
 
p
u
r
p
o
s
e
.

8
3
8
8
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
I
 
f
i
x
e
d
 
m
y
s
e
l
f
 
o
n
 
a
 
w
i
d
e
 
s
o
l
i
t
u
d
e
.

8
3
8
9
 
 
 
 
I
t
 
i
s
 
e
a
s
i
l
y
 
u
n
d
e
r
s
t
o
o
d
 
t
h
a
t
 
w
h
a
t
 
m
i
g
h
t
 
i
m
p
r
o
v
.
.
.

8
3
9
0
 
 
 
 
B
e
 
t
h
i
s
 
a
s
 
i
t
 
m
a
y
,
 
I
 
n
o
w
 
b
e
g
a
n
 
t
o
 
f
e
e
l
 
t
h
e
 
i
n
s
.
.
.

8
3
9
1
 
 
 
 
L
o
n
g
 
w
i
n
d
e
d
,
 
s
t
a
t
i
s
t
i
c
a
l
,
 
a
n
d
 
d
r
e
a
r
i
l
y
 
g
e
n
e
a
l
o
.
.
.

N
a
m
e
:
 
t
e
x
t
,
 
L
e
n
g
t
h
:
 
2
7
9
7
1
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
*
S
t
e
m
m
i
n
g
과
 
L
e
m
m
a
t
i
z
a
t
i
o
n
*




영
어
의
 
경
우
 
과
거
/
현
재
,
 
3
인
칭
 
단
수
 
여
부
,
 
진
행
형
 
등
 
많
은
 
조
건
에
 
따
라
 
원
래
 
단
어
가
 
변
화
 
>
 
문
법
적
 
또
는
 
의
미
적
으
로
 
변
화
하
는
 
단
어
의
 
원
형
을
 
찾
는
 
것
.




L
e
m
m
a
t
i
z
a
t
i
o
n
이
 
S
t
e
m
m
i
n
g
보
다
 
정
교
하
며
 
의
미
론
적
인
 
기
반
에
서
 
단
어
의
 
원
형
을
 
찾
습
니
다
.




S
t
e
m
m
i
n
g
은
 
원
형
 
단
어
로
 
변
환
 
시
 
일
반
적
인
 
방
법
을
 
적
용
하
거
나
 
더
 
단
순
화
된
 
방
법
을
 
적
용
해
 
원
래
 
단
어
에
서
 
일
부
 
철
자
가
 
훼
손
된
 
어
근
 
단
어
를
 
추
출
하
는
 
경
향




L
e
m
m
a
t
i
z
a
t
i
o
n
은
 
품
사
와
 
같
은
 
문
법
적
인
 
요
소
와
 
더
 
의
미
적
인
 
부
분
을
 
감
안
해
 
정
확
한
 
철
자
로
 
된
 
어
근
 
단
어
를
 
찾
아
줌
.




L
e
m
m
z
a
t
i
n
z
a
t
i
o
n
이
 
S
t
e
m
m
i
n
g
보
다
 
변
환
에
 
더
 
오
랜
 
시
간
을
 
필
요
.


L
e
m
m
a
t
i
z
a
t
i
o
n
은
 
정
확
한
 
원
형
 
단
어
 
추
출
을
 
위
해
 
단
어
의
 
'
품
사
'
를
 
입
력
해
 
주
어
야
함
.




a
l
l
d
a
t
a
의
 
t
e
x
t
는
 
s
e
n
t
e
n
c
e
로
 
되
어
 
있
어
 
하
나
씩
 
품
사
를
 
지
정
하
는
 
것
이
 
어
려
우
므
로
 
S
t
e
m
m
i
n
g
을
 
이
용
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
 
n
l
t
k
.
s
t
e
m
 
i
m
p
o
r
t
 
L
a
n
c
a
s
t
e
r
S
t
e
m
m
e
r

L
S
 
=
 
 
L
a
n
c
a
s
t
e
r
S
t
e
m
m
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
t
e
x
t
'
]
 
=
 
[
L
S
.
s
t
e
m
(
w
)
 
f
o
r
 
w
 
i
n
 
a
l
l
d
a
t
a
[
'
t
e
x
t
'
]
]
```


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
t
e
x
t
'
]
```

<pre>
0
 
 
 
 
 
 
 
t
h
i
s
 
p
r
o
c
e
s
s
,
 
h
o
w
e
v
e
r
,
 
a
f
f
o
r
d
e
d
 
m
e
 
n
o
 
m
e
a
n
s
 
o
f
.
.
.

1
 
 
 
 
 
 
 
i
t
 
n
e
v
e
r
 
o
n
c
e
 
o
c
c
u
r
r
e
d
 
t
o
 
m
e
 
t
h
a
t
 
t
h
e
 
f
u
m
b
l
i
n
g
.
.
.

2
 
 
 
 
 
 
 
i
n
 
h
i
s
 
l
e
f
t
 
h
a
n
d
 
w
a
s
 
a
 
g
o
l
d
 
s
n
u
f
f
 
b
o
x
,
 
f
r
o
m
 
w
h
.
.
.

3
 
 
 
 
 
 
 
h
o
w
 
l
o
v
e
l
y
 
i
s
 
s
p
r
i
n
g
 
a
s
 
w
e
 
l
o
o
k
e
d
 
f
r
o
m
 
w
i
n
d
s
o
r
.
.
.

4
 
 
 
 
 
 
 
f
i
n
d
i
n
g
 
n
o
t
h
i
n
g
 
e
l
s
e
,
 
n
o
t
 
e
v
e
n
 
g
o
l
d
,
 
t
h
e
 
s
u
p
e
r
.
.
.

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

8
3
8
7
 
 
 
 
 
 
 
 
 
 
 
a
l
l
 
t
h
i
s
 
i
s
 
n
o
w
 
t
h
e
 
f
i
t
t
e
r
 
f
o
r
 
m
y
 
p
u
r
p
o
s
e
.

8
3
8
8
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
i
 
f
i
x
e
d
 
m
y
s
e
l
f
 
o
n
 
a
 
w
i
d
e
 
s
o
l
i
t
u
d
e
.

8
3
8
9
 
 
 
 
i
t
 
i
s
 
e
a
s
i
l
y
 
u
n
d
e
r
s
t
o
o
d
 
t
h
a
t
 
w
h
a
t
 
m
i
g
h
t
 
i
m
p
r
o
v
.
.
.

8
3
9
0
 
 
 
 
b
e
 
t
h
i
s
 
a
s
 
i
t
 
m
a
y
,
 
i
 
n
o
w
 
b
e
g
a
n
 
t
o
 
f
e
e
l
 
t
h
e
 
i
n
s
.
.
.

8
3
9
1
 
 
 
 
l
o
n
g
 
w
i
n
d
e
d
,
 
s
t
a
t
i
s
t
i
c
a
l
,
 
a
n
d
 
d
r
e
a
r
i
l
y
 
g
e
n
e
a
l
o
.
.
.

N
a
m
e
:
 
t
e
x
t
,
 
L
e
n
g
t
h
:
 
2
7
9
7
1
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
'
t
e
x
t
'
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
o
f
'
:
 
2
,

 
'
a
n
d
'
:
 
3
,

 
'
t
o
'
:
 
4
,

 
'
i
'
:
 
5
,

 
'
a
'
:
 
6
,

 
'
i
n
'
:
 
7
,

 
'
w
a
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
m
y
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
h
a
d
'
:
 
1
2
,

 
'
w
i
t
h
'
:
 
1
3
,

 
'
h
e
'
:
 
1
4
,

 
'
h
i
s
'
:
 
1
5
,

 
'
a
s
'
:
 
1
6
,

 
'
f
o
r
'
:
 
1
7
,

 
'
b
u
t
'
:
 
1
8
,

 
'
w
h
i
c
h
'
:
 
1
9
,

 
'
n
o
t
'
:
 
2
0
,

 
'
a
t
'
:
 
2
1
,

 
'
m
e
'
:
 
2
2
,

 
'
b
y
'
:
 
2
3
,

 
'
f
r
o
m
'
:
 
2
4
,

 
'
i
s
'
:
 
2
5
,

 
'
t
h
i
s
'
:
 
2
6
,

 
'
o
n
'
:
 
2
7
,

 
'
b
e
'
:
 
2
8
,

 
'
w
e
r
e
'
:
 
2
9
,

 
'
h
e
r
'
:
 
3
0
,

 
'
h
a
v
e
'
:
 
3
1
,

 
'
a
l
l
'
:
 
3
2
,

 
'
y
o
u
'
:
 
3
3
,

 
'
w
e
'
:
 
3
4
,

 
'
o
r
'
:
 
3
5
,

 
'
n
o
'
:
 
3
6
,

 
'
a
n
'
:
 
3
7
,

 
'
o
n
e
'
:
 
3
8
,

 
'
h
i
m
'
:
 
3
9
,

 
'
s
o
'
:
 
4
0
,

 
'
w
h
e
n
'
:
 
4
1
,

 
'
t
h
e
y
'
:
 
4
2
,

 
'
b
e
e
n
'
:
 
4
3
,

 
'
u
p
o
n
'
:
 
4
4
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
5
,

 
'
c
o
u
l
d
'
:
 
4
6
,

 
'
i
t
s
'
:
 
4
7
,

 
'
s
h
e
'
:
 
4
8
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
9
,

 
'
m
o
r
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
i
r
'
:
 
5
1
,

 
'
n
o
w
'
:
 
5
2
,

 
'
w
h
a
t
'
:
 
5
3
,

 
'
s
o
m
e
'
:
 
5
4
,

 
'
o
u
r
'
:
 
5
5
,

 
'
a
r
e
'
:
 
5
6
,

 
'
i
n
t
o
'
:
 
5
7
,

 
'
w
h
o
'
:
 
5
8
,

 
'
t
h
a
n
'
:
 
5
9
,

 
'
i
f
'
:
 
6
0
,

 
'
v
e
r
y
'
:
 
6
1
,

 
'
w
i
l
l
'
:
 
6
2
,

 
'
t
h
e
m
'
:
 
6
3
,

 
'
o
n
l
y
'
:
 
6
4
,

 
'
t
h
e
n
'
:
 
6
5
,

 
'
u
p
'
:
 
6
6
,

 
'
t
h
e
s
e
'
:
 
6
7
,

 
'
a
b
o
u
t
'
:
 
6
8
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
 
6
9
,

 
'
a
n
y
'
:
 
7
0
,

 
'
m
a
n
'
:
 
7
1
,

 
'
t
i
m
e
'
:
 
7
2
,

 
'
d
i
d
'
:
 
7
3
,

 
'
o
u
t
'
:
 
7
4
,

 
'
e
v
e
n
'
:
 
7
5
,

 
'
y
e
t
'
:
 
7
6
,

 
'
s
a
i
d
'
:
 
7
7
,

 
'
y
o
u
r
'
:
 
7
8
,

 
'
o
l
d
'
:
 
7
9
,

 
'
m
i
g
h
t
'
:
 
8
0
,

 
'
l
i
k
e
'
:
 
8
1
,

 
'
a
f
t
e
r
'
:
 
8
2
,

 
'
f
i
r
s
t
'
:
 
8
3
,

 
'
m
u
s
t
'
:
 
8
4
,

 
'
u
s
'
:
 
8
5
,

 
'
m
o
s
t
'
:
 
8
6
,

 
'
o
v
e
r
'
:
 
8
7
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
 
8
8
,

 
'
s
u
c
h
'
:
 
8
9
,

 
'
n
e
v
e
r
'
:
 
9
0
,

 
'
l
i
f
e
'
:
 
9
1
,

 
'
m
a
d
e
'
:
 
9
2
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
 
9
3
,

 
'
d
o
'
:
 
9
4
,

 
'
o
t
h
e
r
'
:
 
9
5
,

 
'
f
o
u
n
d
'
:
 
9
6
,

 
'
t
h
o
s
e
'
:
 
9
7
,

 
'
s
e
e
m
e
d
'
:
 
9
8
,

 
'
e
y
e
s
'
:
 
9
9
,

 
'
w
h
i
l
e
'
:
 
1
0
0
,

 
'
e
v
e
r
y
'
:
 
1
0
1
,

 
'
g
r
e
a
t
'
:
 
1
0
2
,

 
'
n
i
g
h
t
'
:
 
1
0
3
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
 
1
0
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
0
5
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
0
6
,

 
'
s
a
w
'
:
 
1
0
7
,

 
'
h
a
s
'
:
 
1
0
8
,

 
'
l
o
n
g
'
:
 
1
0
9
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
 
1
1
0
,

 
'
o
w
n
'
:
 
1
1
1
,

 
'
d
a
y
'
:
 
1
1
2
,

 
'
m
a
n
y
'
:
 
1
1
3
,

 
'
m
u
c
h
'
:
 
1
1
4
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
1
5
,

 
'
w
e
l
l
'
:
 
1
1
6
,

 
'
c
a
m
e
'
:
 
1
1
7
,

 
'
c
a
n
'
:
 
1
1
8
,

 
'
d
o
w
n
'
:
 
1
1
9
,

 
'
h
o
w
'
:
 
1
2
0
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
 
1
2
1
,

 
'
t
w
o
'
:
 
1
2
2
,

 
'
m
a
y
'
:
 
1
2
3
,

 
'
h
e
r
e
'
:
 
1
2
4
,

 
'
s
a
y
'
:
 
1
2
5
,

 
'
s
e
e
'
:
 
1
2
6
,

 
'
b
e
i
n
g
'
:
 
1
2
7
,

 
'
o
n
c
e
'
:
 
1
2
8
,

 
'
e
v
e
r
'
:
 
1
2
9
,

 
'
w
h
o
s
e
'
:
 
1
3
0
,

 
'
t
h
u
s
'
:
 
1
3
1
,

 
'
t
o
o
'
:
 
1
3
2
,

 
'
a
m
'
:
 
1
3
3
,

 
'
d
e
a
t
h
'
:
 
1
3
4
,

 
'
h
e
a
r
t
'
:
 
1
3
5
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
3
6
,

 
'
f
a
r
'
:
 
1
3
7
,

 
'
m
i
n
d
'
:
 
1
3
8
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
3
9
,

 
'
s
h
a
l
l
'
:
 
1
4
0
,

 
'
h
o
u
s
e
'
:
 
1
4
1
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
 
1
4
2
,

 
'
h
e
a
r
d
'
:
 
1
4
3
,

 
'
k
n
o
w
'
:
 
1
4
4
,

 
'
f
e
l
t
'
:
 
1
4
5
,

 
'
t
h
i
n
g
'
:
 
1
4
6
,

 
'
m
e
n
'
:
 
1
4
7
,

 
'
y
e
a
r
s
'
:
 
1
4
8
,

 
'
p
l
a
c
e
'
:
 
1
4
9
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
 
1
5
0
,

 
'
l
a
s
t
'
:
 
1
5
1
,

 
'
l
o
v
e
'
:
 
1
5
2
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
 
1
5
3
,

 
'
l
e
f
t
'
:
 
1
5
4
,

 
'
e
a
r
t
h
'
:
 
1
5
5
,

 
'
f
e
w
'
:
 
1
5
6
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
 
1
5
7
,

 
'
l
i
g
h
t
'
:
 
1
5
8
,

 
'
w
o
r
l
d
'
:
 
1
5
9
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
 
1
6
0
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
 
1
6
1
,

 
'
b
e
c
a
m
e
'
:
 
1
6
2
,

 
'
w
o
r
d
s
'
:
 
1
6
3
,

 
'
c
o
m
e
'
:
 
1
6
4
,

 
'
w
h
o
l
e
'
:
 
1
6
5
,

 
'
w
a
y
'
:
 
1
6
6
,

 
'
h
e
a
d
'
:
 
1
6
7
,

 
'
b
a
c
k
'
:
 
1
6
8
,

 
'
a
m
o
n
g
'
:
 
1
6
9
,

 
'
s
e
e
n
'
:
 
1
7
0
,

 
'
d
o
o
r
'
:
 
1
7
1
,

 
'
n
a
t
u
r
e
'
:
 
1
7
2
,

 
'
h
a
n
d
'
:
 
1
7
3
,

 
'
r
o
o
m
'
:
 
1
7
4
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
7
5
,

 
'
s
t
r
a
n
g
e
'
:
 
1
7
6
,

 
'
s
a
m
e
'
:
 
1
7
7
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
 
1
7
8
,

 
'
a
w
a
y
'
:
 
1
7
9
,

 
'
l
e
t
'
:
 
1
8
0
,

 
'
h
u
m
a
n
'
:
 
1
8
1
,

 
'
k
n
e
w
'
:
 
1
8
2
,

 
'
n
o
r
'
:
 
1
8
3
,

 
'
n
e
w
'
:
 
1
8
4
,

 
'
h
a
l
f
'
:
 
1
8
5
,

 
'
e
a
c
h
'
:
 
1
8
6
,

 
'
m
a
k
e
'
:
 
1
8
7
,

 
'
p
a
r
t
'
:
 
1
8
8
,

 
'
g
o
o
d
'
:
 
1
8
9
,

 
'
s
o
o
n
'
:
 
1
9
0
,

 
'
l
e
n
g
t
h
'
:
 
1
9
1
,

 
'
f
r
i
e
n
d
'
:
 
1
9
2
,

 
"
'
"
:
 
1
9
3
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
 
1
9
4
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
 
1
9
5
,

 
'
l
e
s
s
'
:
 
1
9
6
,

 
'
t
h
r
e
e
'
:
 
1
9
7
,

 
'
j
u
s
t
'
:
 
1
9
8
,

 
'
m
o
m
e
n
t
'
:
 
1
9
9
,

 
'
v
o
i
c
e
'
:
 
2
0
0
,

 
'
s
i
n
c
e
'
:
 
2
0
1
,

 
'
b
e
y
o
n
d
'
:
 
2
0
2
,

 
'
a
i
r
'
:
 
2
0
3
,

 
'
s
e
a
'
:
 
2
0
4
,

 
'
o
f
f
'
:
 
2
0
5
,

 
'
a
l
o
n
e
'
:
 
2
0
6
,

 
'
g
a
v
e
'
:
 
2
0
7
,

 
'
r
a
y
m
o
n
d
'
:
 
2
0
8
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
 
2
0
9
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
 
2
1
0
,

 
'
f
a
t
h
e
r
'
:
 
2
1
1
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
 
2
1
2
,

 
'
f
e
a
r
'
:
 
2
1
3
,

 
'
t
o
o
k
'
:
 
2
1
4
,

 
'
d
a
r
k
'
:
 
2
1
5
,

 
'
l
o
o
k
e
d
'
:
 
2
1
6
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
 
2
1
7
,

 
'
s
m
a
l
l
'
:
 
2
1
8
,

 
'
s
o
u
l
'
:
 
2
1
9
,

 
'
n
e
a
r
'
:
 
2
2
0
,

 
'
p
a
s
s
e
d
'
:
 
2
2
1
,

 
'
f
u
l
l
'
:
 
2
2
2
,

 
'
a
p
p
e
a
r
e
d
'
:
 
2
2
3
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
2
4
,

 
'
b
o
d
y
'
:
 
2
2
5
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
 
2
2
6
,

 
'
c
i
t
y
'
:
 
2
2
7
,

 
'
t
o
l
d
'
:
 
2
2
8
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
 
2
2
9
,

 
'
w
h
o
m
'
:
 
2
3
0
,

 
'
d
a
y
s
'
:
 
2
3
1
,

 
'
f
i
n
d
'
:
 
2
3
2
,

 
'
w
e
n
t
'
:
 
2
3
3
,

 
'
t
a
k
e
'
:
 
2
3
4
,

 
'
f
a
c
e
'
:
 
2
3
5
,

 
'
a
l
s
o
'
:
 
2
3
6
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
 
2
3
7
,

 
'
y
o
u
n
g
'
:
 
2
3
8
,

 
'
w
h
y
'
:
 
2
3
9
,

 
'
l
a
y
'
:
 
2
4
0
,

 
'
s
p
i
r
i
t
'
:
 
2
4
1
,

 
'
t
h
i
n
k
'
:
 
2
4
2
,

 
'
h
o
r
r
o
r
'
:
 
2
4
3
,

 
'
e
n
d
'
:
 
2
4
4
,

 
'
h
i
g
h
'
:
 
2
4
5
,

 
'
d
e
a
d
'
:
 
2
4
6
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
 
2
4
7
,

 
'
o
p
e
n
'
:
 
2
4
8
,

 
'
i
d
e
a
'
:
 
2
4
9
,

 
'
u
n
t
i
l
'
:
 
2
5
0
,

 
'
h
o
p
e
'
:
 
2
5
1
,

 
'
m
r
'
:
 
2
5
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
 
2
5
3
,

 
'
f
o
r
m
'
:
 
2
5
4
,

 
'
n
a
m
e
'
:
 
2
5
5
,

 
'
m
a
n
n
e
r
'
:
 
2
5
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
 
2
5
7
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
 
2
5
8
,

 
'
l
o
o
k
'
:
 
2
5
9
,

 
"
a
n
'
"
:
 
2
6
0
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
 
2
6
1
,

 
'
d
e
e
p
'
:
 
2
6
2
,

 
'
p
o
i
n
t
'
:
 
2
6
3
,

 
'
l
e
a
s
t
'
:
 
2
6
4
,

 
'
s
t
r
e
e
t
'
:
 
2
6
5
,

 
'
k
i
n
d
'
:
 
2
6
6
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
 
2
6
7
,

 
'
g
o
'
:
 
2
6
8
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
 
2
6
9
,

 
'
f
e
e
t
'
:
 
2
7
0
,

 
'
w
a
t
e
r
'
:
 
2
7
1
,

 
'
o
f
t
e
n
'
:
 
2
7
2
,

 
'
b
e
g
a
n
'
:
 
2
7
3
,

 
'
b
r
o
u
g
h
t
'
:
 
2
7
4
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
 
2
7
5
,

 
'
t
u
r
n
e
d
'
:
 
2
7
6
,

 
'
r
i
g
h
t
'
:
 
2
7
7
,

 
'
t
e
l
l
'
:
 
2
7
8
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
 
2
7
9
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
8
0
,

 
'
m
o
r
n
i
n
g
'
:
 
2
8
1
,

 
'
s
o
u
n
d
'
:
 
2
8
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
 
2
8
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
8
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
 
2
8
5
,

 
'
p
o
w
e
r
'
:
 
2
8
6
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
 
2
8
7
,

 
'
b
o
t
h
'
:
 
2
8
8
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
 
2
8
9
,

 
'
l
o
s
t
'
:
 
2
9
0
,

 
'
m
o
o
n
'
:
 
2
9
1
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
 
2
9
2
,

 
'
s
u
n
'
:
 
2
9
3
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
 
2
9
4
,

 
'
w
i
l
d
'
:
 
2
9
5
,

 
'
n
e
a
r
l
y
'
:
 
2
9
6
,

 
'
f
e
e
l
'
:
 
2
9
7
,

 
'
s
p
o
k
e
'
:
 
2
9
8
,

 
'
f
e
l
l
'
:
 
2
9
9
,

 
'
a
n
c
i
e
n
t
'
:
 
3
0
0
,

 
'
s
i
d
e
'
:
 
3
0
1
,

 
'
h
o
m
e
'
:
 
3
0
2
,

 
'
r
e
t
u
r
n
'
:
 
3
0
3
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
 
3
0
4
,

 
'
h
o
u
r
'
:
 
3
0
5
,

 
'
f
a
c
t
'
:
 
3
0
6
,

 
'
d
o
u
b
t
'
:
 
3
0
7
,

 
'
h
o
u
r
s
'
:
 
3
0
8
,

 
'
s
c
e
n
e
'
:
 
3
0
9
,

 
'
t
a
k
e
n
'
:
 
3
1
0
,

 
'
e
y
e
'
:
 
3
1
1
,

 
'
s
t
o
o
d
'
:
 
3
1
2
,

 
'
l
a
r
g
e
'
:
 
3
1
3
,

 
'
t
o
w
a
r
d
s
'
:
 
3
1
4
,

 
'
e
n
t
e
r
e
d
'
:
 
3
1
5
,

 
'
b
e
a
u
t
y
'
:
 
3
1
6
,

 
'
o
b
j
e
c
t
'
:
 
3
1
7
,

 
'
p
u
t
'
:
 
3
1
8
,

 
'
s
i
g
h
t
'
:
 
3
1
9
,

 
'
s
e
t
'
:
 
3
2
0
,

 
'
h
a
n
d
s
'
:
 
3
2
1
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
 
3
2
2
,

 
'
s
u
d
d
e
n
l
y
'
:
 
3
2
3
,

 
'
g
r
e
w
'
:
 
3
2
4
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
 
3
2
5
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
 
3
2
6
,

 
'
d
r
e
a
m
s
'
:
 
3
2
7
,

 
'
t
o
w
n
'
:
 
3
2
8
,

 
'
s
t
a
t
e
'
:
 
3
2
9
,

 
'
d
e
'
:
 
3
3
0
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
d
'
:
 
3
3
1
,

 
'
t
r
u
e
'
:
 
3
3
2
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
 
3
3
3
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
 
3
3
4
,

 
'
t
e
r
r
i
b
l
e
'
:
 
3
3
5
,

 
'
t
h
o
u
g
h
t
s
'
:
 
3
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
 
3
3
7
,

 
'
p
e
r
d
i
t
a
'
:
 
3
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
 
3
3
9
,

 
'
w
o
r
k
'
:
 
3
4
0
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
 
3
4
1
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
 
3
4
2
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
 
3
4
3
,

 
'
w
h
i
t
e
'
:
 
3
4
4
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
 
3
4
5
,

 
'
t
o
w
a
r
d
'
:
 
3
4
6
,

 
'
g
i
v
e
'
:
 
3
4
7
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
 
3
4
8
,

 
'
f
l
o
o
r
'
:
 
3
4
9
,

 
'
t
h
o
u
s
a
n
d
'
:
 
3
5
0
,

 
'
b
e
n
e
a
t
h
'
:
 
3
5
1
,

 
'
d
r
e
a
m
'
:
 
3
5
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
e
'
:
 
3
5
3
,

 
'
n
o
n
e
'
:
 
3
5
4
,

 
'
s
p
e
a
k
'
:
 
3
5
5
,

 
'
a
d
r
i
a
n
'
:
 
3
5
6
,

 
'
d
o
n
e
'
:
 
3
5
7
,

 
'
a
p
p
e
a
r
a
n
c
e
'
:
 
3
5
8
,

 
'
w
o
r
d
'
:
 
3
5
9
,

 
'
s
l
e
e
p
'
:
 
3
6
0
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
6
1
,

 
'
w
i
n
d
'
:
 
3
6
2
,

 
'
t
r
u
t
h
'
:
 
3
6
3
,

 
'
t
i
m
e
s
'
:
 
3
6
4
,

 
'
w
i
n
d
o
w
'
:
 
3
6
5
,

 
'
s
e
n
s
e
'
:
 
3
6
6
,

 
'
p
o
o
r
'
:
 
3
6
7
,

 
'
d
e
a
r
'
:
 
3
6
8
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
6
9
,

 
'
r
e
a
d
'
:
 
3
7
0
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
 
3
7
1
,

 
'
g
o
d
'
:
 
3
7
2
,

 
'
t
r
e
e
s
'
:
 
3
7
3
,

 
'
v
i
e
w
'
:
 
3
7
4
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
 
3
7
5
,

 
'
c
l
o
s
e
'
:
 
3
7
6
,

 
'
g
r
o
u
n
d
'
:
 
3
7
7
,

 
'
s
t
o
n
e
'
:
 
3
7
8
,

 
'
r
e
m
a
i
n
e
d
'
:
 
3
7
9
,

 
'
d
e
s
p
a
i
r
'
:
 
3
8
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
 
3
8
1
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
 
3
8
2
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
3
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
8
4
,

 
'
v
a
s
t
'
:
 
3
8
5
,

 
'
c
a
s
e
'
:
 
3
8
6
,

 
'
p
a
s
t
'
:
 
3
8
7
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
 
3
8
8
,

 
'
w
e
s
t
'
:
 
3
8
9
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
9
0
,

 
'
d
i
e
d
'
:
 
3
9
1
,

 
'
u
n
k
n
o
w
n
'
:
 
3
9
2
,

 
'
f
i
v
e
'
:
 
3
9
3
,

 
'
f
e
e
l
i
n
g
'
:
 
3
9
4
,

 
'
w
a
l
l
s
'
:
 
3
9
5
,

 
'
c
h
a
r
a
c
t
e
r
'
:
 
3
9
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
 
3
9
7
,

 
'
f
e
e
l
i
n
g
s
'
:
 
3
9
8
,

 
'
c
o
u
n
t
e
n
a
n
c
e
'
:
 
3
9
9
,

 
'
i
m
m
e
d
i
a
t
e
l
y
'
:
 
4
0
0
,

 
'
l
o
w
'
:
 
4
0
1
,

 
'
n
e
x
t
'
:
 
4
0
2
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
 
4
0
3
,

 
'
h
a
p
p
i
n
e
s
s
'
:
 
4
0
4
,

 
'
t
i
l
l
'
:
 
4
0
5
,

 
'
e
n
g
l
a
n
d
'
:
 
4
0
6
,

 
'
e
v
i
l
'
:
 
4
0
7
,

 
'
h
i
d
e
o
u
s
'
:
 
4
0
8
,

 
'
o
h
'
:
 
4
0
9
,

 
'
m
e
r
e
l
y
'
:
 
4
1
0
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
1
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
 
4
1
2
,

 
'
a
g
e
'
:
 
4
1
3
,

 
'
c
a
l
l
'
:
 
4
1
4
,

 
'
s
u
r
e
'
:
 
4
1
5
,

 
'
c
o
l
d
'
:
 
4
1
6
,

 
'
r
e
p
l
i
e
d
'
:
 
4
1
7
,

 
'
t
e
a
r
s
'
:
 
4
1
8
,

 
'
l
e
d
'
:
 
4
1
9
,

 
'
b
e
s
t
'
:
 
4
2
0
,

 
'
g
e
t
'
:
 
4
2
1
,

 
'
h
e
a
r
'
:
 
4
2
2
,

 
'
h
e
l
d
'
:
 
4
2
3
,

 
'
l
a
n
d
'
:
 
4
2
4
,

 
'
e
v
e
n
i
n
g
'
:
 
4
2
5
,

 
'
n
a
t
u
r
a
l
'
:
 
4
2
6
,

 
'
b
l
o
o
d
'
:
 
4
2
7
,

 
'
b
e
h
i
n
d
'
:
 
4
2
8
,

 
'
g
o
n
e
'
:
 
4
2
9
,

 
'
c
h
i
l
d
'
:
 
4
3
0
,

 
'
l
a
t
e
'
:
 
4
3
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
3
2
,

 
'
s
a
t
'
:
 
4
3
3
,

 
'
w
o
n
d
e
r
'
:
 
4
3
4
,

 
'
r
i
v
e
r
'
:
 
4
3
5
,

 
'
r
e
s
t
'
:
 
4
3
6
,

 
'
f
e
l
l
o
w
'
:
 
4
3
7
,

 
'
s
k
y
'
:
 
4
3
8
,

 
'
s
p
a
c
e
'
:
 
4
3
9
,

 
'
f
i
r
e
'
:
 
4
4
0
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
 
4
4
1
,

 
'
c
a
r
e
'
:
 
4
4
2
,

 
'
w
a
l
l
'
:
 
4
4
3
,

 
'
i
d
r
i
s
'
:
 
4
4
4
,

 
'
d
i
s
c
o
v
e
r
e
d
'
:
 
4
4
5
,

 
'
f
i
l
l
e
d
'
:
 
4
4
6
,

 
'
r
e
t
u
r
n
e
d
'
:
 
4
4
7
,

 
'
m
e
m
o
r
y
'
:
 
4
4
8
,

 
'
s
h
o
r
t
'
:
 
4
4
9
,

 
'
m
e
r
e
'
:
 
4
5
0
,

 
'
f
r
i
e
n
d
s
'
:
 
4
5
1
,

 
'
l
e
a
v
e
'
:
 
4
5
2
,

 
'
g
e
n
t
l
e
'
:
 
4
5
3
,

 
'
l
a
t
t
e
r
'
:
 
4
5
4
,

 
'
w
i
s
h
'
:
 
4
5
5
,

 
'
y
o
u
t
h
'
:
 
4
5
6
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
 
4
5
7
,

 
'
f
o
l
l
o
w
e
d
'
:
 
4
5
8
,

 
'
s
p
o
t
'
:
 
4
5
9
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
 
4
6
0
,

 
'
t
e
r
r
o
r
'
:
 
4
6
1
,

 
'
e
x
i
s
t
e
n
c
e
'
:
 
4
6
2
,

 
'
d
i
e
'
:
 
4
6
3
,

 
'
c
h
a
m
b
e
r
'
:
 
4
6
4
,

 
'
a
l
o
n
g
'
:
 
4
6
5
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
 
4
6
6
,

 
'
m
i
s
e
r
y
'
:
 
4
6
7
,

 
'
c
a
u
s
e
'
:
 
4
6
8
,

 
'
a
l
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
 
4
6
9
,

 
'
s
e
c
r
e
t
'
:
 
4
7
0
,

 
'
y
e
a
r
'
:
 
4
7
1
,

 
'
b
e
d
'
:
 
4
7
2
,

 
'
r
e
a
c
h
e
d
'
:
 
4
7
3
,

 
'
g
r
e
e
n
'
:
 
4
7
4
,

 
'
f
o
r
t
h
'
:
 
4
7
5
,

 
'
w
i
n
d
o
w
s
'
:
 
4
7
6
,

 
'
h
e
r
s
e
l
f
'
:
 
4
7
7
,

 
'
g
r
e
a
t
e
r
'
:
 
4
7
8
,

 
'
l
e
t
t
e
r
'
:
 
4
7
9
,

 
'
i
m
a
g
i
n
a
t
i
o
n
'
:
 
4
8
0
,

 
'
l
i
p
s
'
:
 
4
8
1
,

 
'
o
b
s
e
r
v
e
d
'
:
 
4
8
2
,

 
'
h
e
a
v
e
n
'
:
 
4
8
3
,

 
'
n
e
i
t
h
e
r
'
:
 
4
8
4
,

 
'
c
h
i
l
d
r
e
n
'
:
 
4
8
5
,

 
'
t
a
b
l
e
'
:
 
4
8
6
,

 
'
s
i
l
e
n
c
e
'
:
 
4
8
7
,

 
'
e
x
p
r
e
s
s
i
o
n
'
:
 
4
8
8
,

 
'
s
a
v
e
'
:
 
4
8
9
,

 
'
j
o
y
'
:
 
4
9
0
,

 
'
p
o
r
t
i
o
n
'
:
 
4
9
1
,

 
'
f
o
r
m
e
d
'
:
 
4
9
2
,

 
'
e
a
r
l
y
'
:
 
4
9
3
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
 
4
9
4
,

 
'
d
i
f
f
i
c
u
l
t
y
'
:
 
4
9
5
,

 
'
s
h
a
d
o
w
'
:
 
4
9
6
,

 
'
l
o
v
e
d
'
:
 
4
9
7
,

 
'
a
r
m
s
'
:
 
4
9
8
,

 
'
d
e
g
r
e
e
'
:
 
4
9
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
 
5
0
0
,

 
'
g
r
i
e
f
'
:
 
5
0
1
,

 
'
c
i
r
c
u
m
s
t
a
n
c
e
s
'
:
 
5
0
2
,

 
'
d
i
s
t
a
n
c
e
'
:
 
5
0
3
,

 
'
f
i
n
a
l
l
y
'
:
 
5
0
4
,

 
'
b
e
a
u
t
i
f
u
l
'
:
 
5
0
5
,

 
'
p
l
e
a
s
u
r
e
'
:
 
5
0
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
0
7
,

 
'
l
a
d
y
'
:
 
5
0
8
,

 
'
s
w
e
e
t
'
:
 
5
0
9
,

 
'
s
c
a
r
c
e
l
y
'
:
 
5
1
0
,

 
'
u
s
e
'
:
 
5
1
1
,

 
'
p
e
c
u
l
i
a
r
'
:
 
5
1
2
,

 
'
h
i
l
l
'
:
 
5
1
3
,

 
'
a
c
r
o
s
s
'
:
 
5
1
4
,

 
'
i
l
l
'
:
 
5
1
5
,

 
'
l
o
n
d
o
n
'
:
 
5
1
6
,

 
'
a
r
m
'
:
 
5
1
7
,

 
'
p
o
s
s
e
s
s
e
d
'
:
 
5
1
8
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
1
9
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
 
5
2
0
,

 
'
s
o
m
e
w
h
a
t
'
:
 
5
2
1
,

 
'
l
i
v
e
d
'
:
 
5
2
2
,

 
'
r
e
c
e
i
v
e
d
'
:
 
5
2
3
,

 
'
h
o
u
s
e
s
'
:
 
5
2
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
 
5
2
5
,

 
'
s
e
l
f
'
:
 
5
2
6
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
 
5
2
7
,

 
'
s
t
e
p
s
'
:
 
5
2
8
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
2
9
,

 
'
s
i
r
'
:
 
5
3
0
,

 
'
d
e
l
i
g
h
t
'
:
 
5
3
1
,

 
'
k
e
p
t
'
:
 
5
3
2
,

 
'
u
s
u
a
l
'
:
 
5
3
3
,

 
'
c
a
s
t
'
:
 
5
3
4
,

 
'
i
m
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
 
5
3
5
,

 
'
l
i
n
e
'
:
 
5
3
6
,

 
'
g
r
a
v
e
'
:
 
5
3
7
,

 
'
f
i
g
u
r
e
'
:
 
5
3
8
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
 
5
3
9
,

 
'
s
o
u
g
h
t
'
:
 
5
4
0
,

 
'
e
f
f
e
c
t
'
:
 
5
4
1
,

 
'
h
e
a
v
y
'
:
 
5
4
2
,

 
'
o
p
e
n
e
d
'
:
 
5
4
3
,

 
'
f
a
n
c
y
'
:
 
5
4
4
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
 
5
4
5
,

 
"
o
'
"
:
 
5
4
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
4
7
,

 
'
y
e
'
:
 
5
4
8
,

 
'
n
o
r
t
h
'
:
 
5
4
9
,

 
'
m
a
d
'
:
 
5
5
0
,

 
'
d
i
s
t
a
n
t
'
:
 
5
5
1
,

 
'
a
f
f
e
c
t
i
o
n
'
:
 
5
5
2
,

 
'
w
i
f
e
'
:
 
5
5
3
,

 
'
c
o
r
p
s
e
'
:
 
5
5
4
,

 
'
d
e
s
i
r
e
'
:
 
5
5
5
,

 
'
b
e
h
e
l
d
'
:
 
5
5
6
,

 
'
t
w
e
n
t
y
'
:
 
5
5
7
,

 
'
s
u
r
f
a
c
e
'
:
 
5
5
8
,

 
'
p
a
i
n
'
:
 
5
5
9
,

 
'
b
o
x
'
:
 
5
6
0
,

 
'
p
r
e
s
e
n
c
e
'
:
 
5
6
1
,

 
'
m
o
u
n
t
a
i
n
'
:
 
5
6
2
,

 
'
m
e
t
'
:
 
5
6
3
,

 
'
e
v
e
n
t
s
'
:
 
5
6
4
,

 
'
f
o
r
c
e
'
:
 
5
6
5
,

 
'
s
i
n
g
u
l
a
r
'
:
 
5
6
6
,

 
'
m
i
n
u
t
e
s
'
:
 
5
6
7
,

 
'
l
o
v
e
l
y
'
:
 
5
6
8
,

 
'
e
x
t
r
e
m
e
'
:
 
5
6
9
,

 
'
d
a
r
k
n
e
s
s
'
:
 
5
7
0
,

 
'
w
o
m
a
n
'
:
 
5
7
1
,

 
'
h
o
l
d
'
:
 
5
7
2
,

 
'
r
o
s
e
'
:
 
5
7
3
,

 
'
w
i
d
e
'
:
 
5
7
4
,

 
'
s
t
r
u
c
k
'
:
 
5
7
5
,

 
'
r
o
u
n
d
'
:
 
5
7
6
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
 
5
7
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
7
8
,

 
'
e
n
t
i
r
e
l
y
'
:
 
5
7
9
,

 
'
c
l
e
a
r
'
:
 
5
8
0
,

 
'
m
i
n
e
'
:
 
5
8
1
,

 
'
p
a
p
e
r
'
:
 
5
8
2
,

 
'
h
u
n
d
r
e
d
'
:
 
5
8
3
,

 
'
a
r
r
i
v
e
d
'
:
 
5
8
4
,

 
'
d
r
'
:
 
5
8
5
,

 
'
v
i
s
i
b
l
e
'
:
 
5
8
6
,

 
'
m
e
a
n
'
:
 
5
8
7
,

 
'
a
r
o
s
e
'
:
 
5
8
8
,

 
'
m
'
:
 
5
8
9
,

 
'
s
o
u
n
d
s
'
:
 
5
9
0
,

 
'
p
l
a
g
u
e
'
:
 
5
9
1
,

 
'
s
i
l
e
n
t
'
:
 
5
9
2
,

 
'
b
r
o
k
e
n
'
:
 
5
9
3
,

 
'
t
e
n
'
:
 
5
9
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
 
5
9
5
,

 
'
b
e
l
o
v
e
d
'
:
 
5
9
6
,

 
'
c
o
t
t
a
g
e
'
:
 
5
9
7
,

 
'
r
e
s
o
l
v
e
d
'
:
 
5
9
8
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
9
9
,

 
'
s
t
r
e
n
g
t
h
'
:
 
6
0
0
,

 
'
t
u
r
n
'
:
 
6
0
1
,

 
'
o
r
d
i
n
a
r
y
'
:
 
6
0
2
,

 
'
o
d
d
'
:
 
6
0
3
,

 
'
f
o
r
m
e
r
'
:
 
6
0
4
,

 
'
r
e
g
a
r
d
'
:
 
6
0
5
,

 
'
h
o
r
r
i
b
l
e
'
:
 
6
0
6
,

 
'
s
i
x
'
:
 
6
0
7
,

 
'
d
o
e
s
'
:
 
6
0
8
,

 
'
h
a
i
r
'
:
 
6
0
9
,

 
'
t
h
r
o
w
n
'
:
 
6
1
0
,

 
'
d
i
r
e
c
t
i
o
n
'
:
 
6
1
1
,

 
'
l
a
t
e
r
'
:
 
6
1
2
,

 
'
e
s
c
a
p
e
'
:
 
6
1
3
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
 
6
1
4
,

 
'
h
i
l
l
s
'
:
 
6
1
5
,

 
'
r
e
a
l
'
:
 
6
1
6
,

 
'
f
a
i
n
t
'
:
 
6
1
7
,

 
'
h
o
p
e
s
'
:
 
6
1
8
,

 
'
s
l
i
g
h
t
'
:
 
6
1
9
,

 
'
p
e
r
c
e
i
v
e
d
'
:
 
6
2
0
,

 
'
g
i
r
l
'
:
 
6
2
1
,

 
'
e
x
c
i
t
e
d
'
:
 
6
2
2
,

 
'
p
a
l
e
'
:
 
6
2
3
,

 
'
t
h
o
u
'
:
 
6
2
4
,

 
'
b
o
o
k
'
:
 
6
2
5
,

 
'
s
u
f
f
i
c
i
e
n
t
'
:
 
6
2
6
,

 
'
b
o
o
k
s
'
:
 
6
2
7
,

 
'
s
o
r
r
o
w
'
:
 
6
2
8
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
2
9
,

 
'
b
u
s
i
n
e
s
s
'
:
 
6
3
0
,

 
'
a
r
t
'
:
 
6
3
1
,

 
'
i
n
s
t
a
n
t
'
:
 
6
3
2
,

 
'
b
o
a
t
'
:
 
6
3
3
,

 
'
p
r
o
c
e
e
d
e
d
'
:
 
6
3
4
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
 
6
3
5
,

 
'
k
e
e
p
'
:
 
6
3
6
,

 
'
v
a
i
n
'
:
 
6
3
7
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
 
6
3
8
,

 
'
g
o
t
'
:
 
6
3
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
 
6
4
0
,

 
'
y
e
s
'
:
 
6
4
1
,

 
'
n
a
r
r
o
w
'
:
 
6
4
2
,

 
'
f
u
l
l
y
'
:
 
6
4
3
,

 
'
a
g
o
'
:
 
6
4
4
,

 
'
c
o
n
d
i
t
i
o
n
'
:
 
6
4
5
,

 
'
c
o
m
p
a
n
i
o
n
'
:
 
6
4
6
,

 
'
b
a
l
l
o
o
n
'
:
 
6
4
7
,

 
'
e
x
t
e
n
t
'
:
 
6
4
8
,

 
'
t
a
l
e
'
:
 
6
4
9
,

 
'
s
i
s
t
e
r
'
:
 
6
5
0
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
'
:
 
6
5
1
,

 
'
c
r
i
e
d
'
:
 
6
5
2
,

 
'
o
'
:
 
6
5
3
,

 
'
s
t
a
r
s
'
:
 
6
5
4
,

 
'
m
i
s
e
r
a
b
l
e
'
:
 
6
5
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
5
6
,

 
'
s
t
r
e
e
t
s
'
:
 
6
5
7
,

 
'
h
a
r
d
l
y
'
:
 
6
5
8
,

 
'
b
r
i
n
g
'
:
 
6
5
9
,

 
'
c
l
o
s
e
d
'
:
 
6
6
0
,

 
'
a
l
a
s
'
:
 
6
6
1
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
 
6
6
2
,

 
'
r
e
d
'
:
 
6
6
3
,

 
'
s
o
c
i
e
t
y
'
:
 
6
6
4
,

 
'
i
n
f
l
u
e
n
c
e
'
:
 
6
6
5
,

 
'
v
i
s
i
t
'
:
 
6
6
6
,

 
'
e
a
r
s
'
:
 
6
6
7
,

 
'
f
r
e
e
'
:
 
6
6
8
,

 
'
f
a
t
e
'
:
 
6
6
9
,

 
'
p
a
s
s
i
o
n
'
:
 
6
7
0
,

 
'
s
e
e
k
'
:
 
6
7
1
,

 
'
e
a
s
i
l
y
'
:
 
6
7
2
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
 
6
7
3
,

 
'
s
a
y
s
'
:
 
6
7
4
,

 
'
b
o
r
n
'
:
 
6
7
5
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
 
6
7
6
,

 
'
l
o
r
d
'
:
 
6
7
7
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
7
8
,

 
'
w
a
t
e
r
s
'
:
 
6
7
9
,

 
'
f
r
e
s
h
'
:
 
6
8
0
,

 
'
c
a
u
s
e
d
'
:
 
6
8
1
,

 
'
m
o
t
i
o
n
'
:
 
6
8
2
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
 
6
8
3
,

 
'
t
r
e
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
e
a
r
'
:
 
6
8
5
,

 
'
h
e
l
p
'
:
 
6
8
6
,

 
'
s
o
u
t
h
'
:
 
6
8
7
,

 
'
a
b
l
e
'
:
 
6
8
8
,

 
'
o
c
e
a
n
'
:
 
6
8
9
,

 
'
d
e
s
e
r
t
e
d
'
:
 
6
9
0
,

 
'
t
h
y
'
:
 
6
9
1
,

 
'
m
a
c
h
i
n
e
'
:
 
6
9
2
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
 
6
9
3
,

 
'
g
o
l
d
'
:
 
6
9
4
,

 
'
c
r
e
a
t
u
r
e
'
:
 
6
9
5
,

 
'
c
a
l
m
'
:
 
6
9
6
,

 
'
c
o
v
e
r
e
d
'
:
 
6
9
7
,

 
'
h
u
n
g
'
:
 
6
9
8
,

 
'
e
x
p
e
c
t
e
d
'
:
 
6
9
9
,

 
'
c
u
t
'
:
 
7
0
0
,

 
'
d
a
r
e
d
'
:
 
7
0
1
,

 
'
f
r
a
m
e
'
:
 
7
0
2
,

 
'
f
o
r
g
o
t
t
e
n
'
:
 
7
0
3
,

 
'
b
l
u
e
'
:
 
7
0
4
,

 
'
m
a
d
n
e
s
s
'
:
 
7
0
5
,

 
'
b
o
r
e
'
:
 
7
0
6
,

 
'
d
r
e
w
'
:
 
7
0
7
,

 
'
r
o
a
d
'
:
 
7
0
8
,

 
'
a
t
m
o
s
p
h
e
r
e
'
:
 
7
0
9
,

 
'
e
v
i
d
e
n
t
l
y
'
:
 
7
1
0
,

 
'
t
h
r
e
w
'
:
 
7
1
1
,

 
'
u
n
c
l
e
'
:
 
7
1
2
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
 
7
1
3
,

 
'
r
e
m
a
i
n
'
:
 
7
1
4
,

 
'
f
a
l
l
'
:
 
7
1
5
,

 
'
n
a
t
i
v
e
'
:
 
7
1
6
,

 
'
o
b
j
e
c
t
s
'
:
 
7
1
7
,

 
'
p
a
s
s
'
:
 
7
1
8
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
 
7
1
9
,

 
'
m
u
s
i
c
'
:
 
7
2
0
,

 
'
g
i
l
m
a
n
'
:
 
7
2
1
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
 
7
2
2
,

 
'
v
i
l
l
a
g
e
'
:
 
7
2
3
,

 
"
d
o
n
'
t
"
:
 
7
2
4
,

 
'
o
c
c
u
r
r
e
d
'
:
 
7
2
5
,

 
'
s
h
i
p
'
:
 
7
2
6
,

 
'
d
e
s
i
g
n
'
:
 
7
2
7
,

 
'
e
a
s
t
'
:
 
7
2
8
,

 
'
m
a
d
a
m
e
'
:
 
7
2
9
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
3
0
,

 
'
u
t
t
e
r
l
y
'
:
 
7
3
1
,

 
'
v
a
l
l
e
y
'
:
 
7
3
2
,

 
'
f
a
l
l
e
n
'
:
 
7
3
3
,

 
'
p
r
e
p
a
r
e
d
'
:
 
7
3
4
,

 
'
e
l
s
e
'
:
 
7
3
5
,

 
'
v
a
g
u
e
'
:
 
7
3
6
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
 
7
3
7
,

 
'
a
l
i
v
e
'
:
 
7
3
8
,

 
'
h
e
a
l
t
h
'
:
 
7
3
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
t
'
:
 
7
4
0
,

 
'
g
o
i
n
g
'
:
 
7
4
1
,

 
'
s
t
r
o
n
g
'
:
 
7
4
2
,

 
'
s
t
'
:
 
7
4
3
,

 
'
t
o
p
'
:
 
7
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
 
7
4
5
,

 
'
r
e
n
d
e
r
e
d
'
:
 
7
4
6
,

 
'
p
a
s
s
a
g
e
'
:
 
7
4
7
,

 
'
s
h
o
r
e
'
:
 
7
4
8
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
4
9
,

 
'
s
e
i
z
e
d
'
:
 
7
5
0
,

 
'
t
o
m
b
'
:
 
7
5
1
,

 
'
w
o
o
d
'
:
 
7
5
2
,

 
'
s
o
n
'
:
 
7
5
3
,

 
'
w
i
n
d
s
o
r
'
:
 
7
5
4
,

 
'
s
t
e
p
'
:
 
7
5
5
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
 
7
5
6
,

 
'
q
u
e
e
r
'
:
 
7
5
7
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
 
7
5
8
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
 
7
5
9
,

 
'
b
o
y
'
:
 
7
6
0
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
6
1
,

 
'
h
e
i
g
h
t
'
:
 
7
6
2
,

 
'
s
y
m
p
a
t
h
y
'
:
 
7
6
3
,

 
'
p
a
t
h
'
:
 
7
6
4
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
 
7
6
5
,

 
'
s
p
r
i
n
g
'
:
 
7
6
6
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
 
7
6
7
,

 
'
b
e
i
n
g
s
'
:
 
7
6
8
,

 
'
s
u
p
p
o
s
e
'
:
 
7
6
9
,

 
'
p
e
r
c
e
i
v
e
'
:
 
7
7
0
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
 
7
7
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
e
d
'
:
 
7
7
2
,

 
'
m
o
v
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
g
r
e
s
s
'
:
 
7
7
4
,

 
'
s
e
n
t
'
:
 
7
7
5
,

 
'
g
e
n
t
l
e
m
a
n
'
:
 
7
7
6
,

 
'
m
a
i
n
'
:
 
7
7
7
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
 
7
7
8
,

 
'
m
o
u
n
t
a
i
n
s
'
:
 
7
7
9
,

 
'
c
i
r
c
u
m
s
t
a
n
c
e
'
:
 
7
8
0
,

 
'
s
u
f
f
e
r
e
d
'
:
 
7
8
1
,

 
'
d
a
n
g
e
r
'
:
 
7
8
2
,

 
'
a
b
s
e
n
c
e
'
:
 
7
8
3
,

 
'
w
i
s
h
e
d
'
:
 
7
8
4
,

 
'
s
u
m
m
e
r
'
:
 
7
8
5
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
 
7
8
6
,

 
'
g
r
e
a
t
e
s
t
'
:
 
7
8
7
,

 
'
m
o
u
t
h
'
:
 
7
8
8
,

 
'
b
e
h
o
l
d
'
:
 
7
8
9
,

 
'
m
i
l
e
s
'
:
 
7
9
0
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
 
7
9
1
,

 
'
c
r
e
a
t
u
r
e
s
'
:
 
7
9
2
,

 
'
i
n
t
e
n
s
e
'
:
 
7
9
3
,

 
'
g
o
d
s
'
:
 
7
9
4
,

 
'
s
u
c
c
e
e
d
e
d
'
:
 
7
9
5
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
 
7
9
6
,

 
'
r
e
a
c
h
'
:
 
7
9
7
,

 
'
p
l
a
i
n
'
:
 
7
9
8
,

 
'
b
o
t
t
o
m
'
:
 
7
9
9
,

 
'
p
e
a
c
e
'
:
 
8
0
0
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
:
 
8
0
1
,

 
'
t
a
s
k
'
:
 
8
0
2
,

 
'
s
p
e
n
t
'
:
 
8
0
3
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
'
:
 
8
0
4
,

 
'
c
a
s
t
l
e
'
:
 
8
0
5
,

 
'
f
o
r
e
v
e
r
'
:
 
8
0
6
,

 
'
o
c
c
u
p
i
e
d
'
:
 
8
0
7
,

 
'
l
e
a
v
i
n
g
'
:
 
8
0
8
,

 
'
i
s
l
a
n
d
'
:
 
8
0
9
,

 
'
r
o
c
k
'
:
 
8
1
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
 
8
1
1
,

 
'
m
e
l
a
n
c
h
o
l
y
'
:
 
8
1
2
,

 
'
e
l
i
z
a
b
e
t
h
'
:
 
8
1
3
,

 
'
c
a
r
r
i
e
d
'
:
 
8
1
4
,

 
'
h
a
r
d
'
:
 
8
1
5
,

 
'
b
r
a
i
n
'
:
 
8
1
6
,

 
'
s
o
l
i
t
u
d
e
'
:
 
8
1
7
,

 
'
r
a
i
n
'
:
 
8
1
8
,

 
'
b
e
s
i
d
e
s
'
:
 
8
1
9
,

 
'
d
e
t
e
r
m
i
n
e
d
'
:
 
8
2
0
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
e
d
'
:
 
8
2
1
,

 
'
s
h
e
w
e
d
'
:
 
8
2
2
,

 
'
c
u
r
i
o
s
i
t
y
'
:
 
8
2
3
,

 
'
f
i
n
e
'
:
 
8
2
4
,

 
'
f
l
o
w
e
r
s
'
:
 
8
2
5
,

 
'
b
r
i
e
f
'
:
 
8
2
6
,

 
'
a
c
t
'
:
 
8
2
7
,

 
'
f
o
o
t
'
:
 
8
2
8
,

 
'
q
u
i
c
k
l
y
'
:
 
8
2
9
,

 
'
s
o
l
e
'
:
 
8
3
0
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
 
8
3
1
,

 
'
f
o
r
e
s
t
'
:
 
8
3
2
,

 
'
c
u
r
i
o
u
s
'
:
 
8
3
3
,

 
'
c
o
n
v
e
r
s
a
t
i
o
n
'
:
 
8
3
4
,

 
'
w
a
l
k
e
d
'
:
 
8
3
5
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
 
8
3
6
,

 
'
i
n
n
s
m
o
u
t
h
'
:
 
8
3
7
,

 
'
p
l
a
c
e
s
'
:
 
8
3
8
,

 
'
a
r
k
h
a
m
'
:
 
8
3
9
,

 
'
h
u
g
e
'
:
 
8
4
0
,

 
'
d
i
s
c
o
v
e
r
y
'
:
 
8
4
1
,

 
'
c
e
a
s
e
d
'
:
 
8
4
2
,

 
'
n
e
e
d
'
:
 
8
4
3
,

 
'
c
a
r
'
:
 
8
4
4
,

 
'
t
a
l
l
'
:
 
8
4
5
,

 
'
a
g
o
n
y
'
:
 
8
4
6
,

 
'
m
i
n
u
t
e
'
:
 
8
4
7
,

 
'
s
p
r
e
a
d
'
:
 
8
4
8
,

 
'
f
a
i
r
'
:
 
8
4
9
,

 
'
i
m
m
e
d
i
a
t
e
'
:
 
8
5
0
,

 
'
c
o
u
r
a
g
e
'
:
 
8
5
1
,

 
'
w
a
t
c
h
'
:
 
8
5
2
,

 
'
f
r
i
g
h
t
f
u
l
'
:
 
8
5
3
,

 
'
b
e
a
r
'
:
 
8
5
4
,

 
'
d
a
u
g
h
t
e
r
'
:
 
8
5
5
,

 
'
s
o
r
t
'
:
 
8
5
6
,

 
'
o
n
e
s
'
:
 
8
5
7
,

 
'
a
n
i
m
a
l
'
:
 
8
5
8
,

 
'
m
i
d
n
i
g
h
t
'
:
 
8
5
9
,

 
'
s
m
i
l
e
'
:
 
8
6
0
,

 
'
i
c
e
'
:
 
8
6
1
,

 
'
g
o
l
d
e
n
'
:
 
8
6
2
,

 
'
g
e
n
i
u
s
'
:
 
8
6
3
,

 
'
u
s
e
d
'
:
 
8
6
4
,

 
'
c
r
o
w
d
'
:
 
8
6
5
,

 
'
b
e
l
i
e
v
e
d
'
:
 
8
6
6
,

 
'
r
e
m
a
r
k
a
b
l
e
'
:
 
8
6
7
,

 
'
p
e
r
s
o
n
s
'
:
 
8
6
8
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
 
8
6
9
,

 
'
w
i
n
t
e
r
'
:
 
8
7
0
,

 
'
b
r
e
a
t
h
'
:
 
8
7
1
,

 
'
l
e
a
r
n
e
d
'
:
 
8
7
2
,

 
'
r
i
s
e
'
:
 
8
7
3
,

 
'
m
e
e
t
'
:
 
8
7
4
,

 
'
f
a
r
t
h
e
r
'
:
 
8
7
5
,

 
'
w
o
o
d
s
'
:
 
8
7
6
,

 
'
p
e
r
f
e
c
t
'
:
 
8
7
7
,

 
'
e
x
c
e
e
d
i
n
g
l
y
'
:
 
8
7
8
,

 
'
m
u
r
d
e
r
'
:
 
8
7
9
,

 
'
b
o
d
i
e
s
'
:
 
8
8
0
,

 
'
s
u
f
f
i
c
i
e
n
t
l
y
'
:
 
8
8
1
,

 
'
g
r
e
y
'
:
 
8
8
2
,

 
'
f
o
r
m
s
'
:
 
8
8
3
,

 
'
w
h
i
l
s
t
'
:
 
8
8
4
,

 
'
s
e
n
s
e
s
'
:
 
8
8
5
,

 
'
s
p
i
r
i
t
s
'
:
 
8
8
6
,

 
'
w
a
n
t
'
:
 
8
8
7
,

 
'
a
d
d
e
d
'
:
 
8
8
8
,

 
'
f
a
i
l
e
d
'
:
 
8
8
9
,

 
'
r
e
l
i
e
f
'
:
 
8
9
0
,

 
'
f
e
a
r
s
'
:
 
8
9
1
,

 
'
g
l
a
s
s
'
:
 
8
9
2
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
 
8
9
3
,

 
'
t
a
l
k
'
:
 
8
9
4
,

 
'
r
e
a
l
i
t
y
'
:
 
8
9
5
,

 
'
s
e
n
s
a
t
i
o
n
s
'
:
 
8
9
6
,

 
'
a
i
d
'
:
 
8
9
7
,

 
'
u
n
u
s
u
a
l
'
:
 
8
9
8
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
9
9
,

 
'
c
l
o
u
d
s
'
:
 
9
0
0
,

 
'
l
i
s
t
e
n
e
d
'
:
 
9
0
1
,

 
'
m
a
r
b
l
e
'
:
 
9
0
2
,

 
'
f
o
r
c
e
d
'
:
 
9
0
3
,

 
'
i
d
e
a
s
'
:
 
9
0
4
,

 
'
f
e
a
r
f
u
l
'
:
 
9
0
5
,

 
'
w
a
t
c
h
e
d
'
:
 
9
0
6
,

 
'
a
p
p
r
o
a
c
h
e
d
'
:
 
9
0
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
 
9
0
8
,

 
'
c
o
r
n
e
r
'
:
 
9
0
9
,

 
'
s
e
e
m
s
'
:
 
9
1
0
,

 
'
j
o
u
r
n
e
y
'
:
 
9
1
1
,

 
'
p
o
s
s
e
s
s
i
o
n
'
:
 
9
1
2
,

 
'
g
r
a
s
s
'
:
 
9
1
3
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
 
9
1
4
,

 
'
s
e
n
t
i
m
e
n
t
'
:
 
9
1
5
,

 
'
s
o
f
t
'
:
 
9
1
6
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
1
7
,

 
'
s
e
v
e
n
'
:
 
9
1
8
,

 
'
p
r
e
s
e
n
t
e
d
'
:
 
9
1
9
,

 
'
p
r
o
v
e
d
'
:
 
9
2
0
,

 
'
m
o
v
e
'
:
 
9
2
1
,

 
'
a
w
a
r
e
'
:
 
9
2
2
,

 
'
d
a
r
e
'
:
 
9
2
3
,

 
'
o
b
t
a
i
n
e
d
'
:
 
9
2
4
,

 
'
w
e
i
g
h
t
'
:
 
9
2
5
,

 
'
u
t
t
e
r
'
:
 
9
2
6
,

 
'
s
l
o
w
l
y
'
:
 
9
2
7
,

 
'
f
e
a
r
e
d
'
:
 
9
2
8
,

 
'
v
i
s
i
o
n
'
:
 
9
2
9
,

 
'
s
u
d
d
e
n
'
:
 
9
3
0
,

 
'
s
e
e
m
'
:
 
9
3
1
,

 
'
e
x
p
e
r
i
e
n
c
e
'
:
 
9
3
2
,

 
'
b
i
t
t
e
r
'
:
 
9
3
3
,

 
'
s
h
u
t
'
:
 
9
3
4
,

 
'
s
t
u
d
y
'
:
 
9
3
5
,

 
'
b
e
n
t
'
:
 
9
3
6
,

 
'
n
o
b
l
e
'
:
 
9
3
7
,

 
'
c
o
n
c
e
r
n
i
n
g
'
:
 
9
3
8
,

 
'
a
f
t
e
r
w
a
r
d
'
:
 
9
3
9
,

 
'
s
t
o
r
m
'
:
 
9
4
0
,

 
'
f
o
r
w
a
r
d
'
:
 
9
4
1
,

 
'
p
o
l
i
c
e
'
:
 
9
4
2
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
 
9
4
3
,

 
'
p
h
y
s
i
c
a
l
'
:
 
9
4
4
,

 
'
i
m
a
g
i
n
e
'
:
 
9
4
5
,

 
'
b
e
s
i
d
e
'
:
 
9
4
6
,

 
'
i
m
a
g
e
'
:
 
9
4
7
,

 
'
v
i
s
i
t
e
d
'
:
 
9
4
8
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
 
9
4
9
,

 
'
t
a
l
k
e
d
'
:
 
9
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
'
:
 
9
5
1
,

 
'
t
h
e
e
'
:
 
9
5
2
,

 
'
d
i
s
e
a
s
e
'
:
 
9
5
3
,

 
'
t
r
a
c
e
'
:
 
9
5
4
,

 
"
o
'
c
l
o
c
k
"
:
 
9
5
5
,

 
'
s
h
a
p
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
p
a
r
t
e
d
'
:
 
9
5
7
,

 
'
m
y
s
t
e
r
y
'
:
 
9
5
8
,

 
'
m
i
g
h
t
y
'
:
 
9
5
9
,

 
'
s
l
e
p
t
'
:
 
9
6
0
,

 
'
a
c
c
i
d
e
n
t
'
:
 
9
6
1
,

 
'
a
p
a
r
t
m
e
n
t
'
:
 
9
6
2
,

 
'
g
a
z
e
d
'
:
 
9
6
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
 
9
6
4
,

 
'
s
u
c
c
e
s
s
'
:
 
9
6
5
,

 
'
a
m
i
d
s
t
'
:
 
9
6
6
,

 
'
r
e
m
o
t
e
'
:
 
9
6
7
,

 
'
w
e
e
k
'
:
 
9
6
8
,

 
'
u
n
a
b
l
e
'
:
 
9
6
9
,

 
'
d
e
p
a
r
t
u
r
e
'
:
 
9
7
0
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
'
:
 
9
7
1
,

 
'
a
s
s
u
r
e
d
'
:
 
9
7
2
,

 
'
p
o
c
k
e
t
'
:
 
9
7
3
,

 
'
d
i
s
t
i
n
c
t
'
:
 
9
7
4
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
 
9
7
5
,

 
'
k
e
y
'
:
 
9
7
6
,

 
'
t
o
n
e
'
:
 
9
7
7
,

 
'
i
n
c
r
e
a
s
e
d
'
:
 
9
7
8
,

 
'
r
e
f
l
e
c
t
i
o
n
'
:
 
9
7
9
,

 
'
m
a
r
k
e
d
'
:
 
9
8
0
,

 
'
i
n
d
i
v
i
d
u
a
l
'
:
 
9
8
1
,

 
'
l
i
m
b
s
'
:
 
9
8
2
,

 
'
b
u
r
s
t
'
:
 
9
8
3
,

 
'
l
a
k
e
'
:
 
9
8
4
,

 
'
g
i
g
a
n
t
i
c
'
:
 
9
8
5
,

 
'
r
a
n
'
:
 
9
8
6
,

 
'
y
e
l
l
o
w
'
:
 
9
8
7
,

 
'
e
n
t
e
r
'
:
 
9
8
8
,

 
'
g
i
v
i
n
g
'
:
 
9
8
9
,

 
'
e
n
d
e
a
v
o
u
r
e
d
'
:
 
9
9
0
,

 
'
i
r
o
n
'
:
 
9
9
1
,

 
'
p
i
e
c
e
'
:
 
9
9
2
,

 
'
b
r
o
t
h
e
r
'
:
 
9
9
3
,

 
'
p
o
w
e
r
s
'
:
 
9
9
4
,

 
'
c
a
r
e
f
u
l
l
y
'
:
 
9
9
5
,

 
'
l
e
a
d
'
:
 
9
9
6
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
 
9
9
7
,

 
'
d
y
i
n
g
'
:
 
9
9
8
,

 
'
m
a
n
k
i
n
d
'
:
 
9
9
9
,

 
'
b
o
s
o
m
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
*
G
r
i
d
S
e
a
r
c
h
C
V
*






S
e
a
r
c
h
C
V
는
 
교
차
 
검
증
을
 
기
반
으
로
 
이
 
하
이
퍼
 
파
라
미
터
의
 
최
적
 
값
을
 
찾
게
 
해
줍
니
다
.
 
즉
,
 
데
이
터
 
세
트
를
 
c
r
o
s
s
-
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
을
 
위
한
 
학
습
/
테
스
트
 
세
트
로
 
자
동
 
분
할
한
 
뒤
에
 
하
이
퍼
 
파
라
미
터
 
그
리
드
에
 
기
술
된
 
모
든
 
파
라
미
터
를
 
순
차
적
으
로
 
적
용
해
 
최
적
의
 
파
라
미
터
를
 
찾
을
 
수
 
있
게
 
해
줍
니
다
.




G
r
i
d
S
e
a
r
c
h
C
V
는
 
사
용
자
가
 
튜
닝
하
고
자
 
하
는
 
여
러
 
종
류
의
 
하
이
퍼
 
파
라
미
터
를
 
다
양
하
게
 
테
스
트
하
면
서
 
최
적
의
 
파
라
미
터
를
 
편
리
하
게
 
찾
게
 
해
주
지
만
 
동
시
에
 
순
차
적
으
로
 
파
라
미
터
를
 
테
스
트
하
므
로
 
수
행
시
간
이
 
상
대
적
으
로
 
오
래
 
걸
리
는
 
것
에
 
유
념
해
야
 
합
니
다
.




e
s
t
i
m
a
t
o
r
 
:
 
c
l
a
s
s
i
f
i
e
r
,
 
r
e
g
r
e
s
s
o
r
,
 
p
i
p
e
l
i
n
e
이
 
사
용
 
될
 
수
 
있
습
니
다
.




p
a
r
a
m
_
g
r
i
d
 
:
 
k
e
y
 
+
 
리
스
트
 
값
을
 
가
지
는
 
딕
셔
너
리
가
 
주
어
집
니
다
.
 
e
s
t
i
m
a
t
o
r
의
 
튜
닝
을
 
위
해
 
파
라
미
터
명
과
 
사
용
될
 
여
러
 
파
라
미
터
 
값
을
 
지
정
합
니
다
.




s
c
o
r
i
n
g
 
:
 
예
측
 
성
능
을
 
측
정
할
 
평
가
 
방
법
을
 
지
정
합
니
다
.
 
보
통
은
 
사
이
킷
런
의
 
성
능
 
평
가
 
지
표
를
 
지
정
하
는
 
문
자
열
 
(
예
:
 
정
확
도
의
 
경
우
 
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
)
로
 
지
정
하
나
 
별
도
의
 
성
능
 
평
가
 
지
표
 
함
수
도
 
지
정
할
 
수
 
있
습
니
다
.




c
v
 
:
 
교
차
 
검
증
을
 
위
해
 
분
할
되
는
 
학
습
/
테
스
트
 
세
트
의
 
개
수
를
 
지
정
합
니
다
.




r
e
f
i
t
 
:
 
디
폴
트
가
 
T
r
u
e
이
며
 
T
r
u
e
로
 
생
성
 
시
 
가
장
 
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
은
 
뒤
 
입
력
된
 
e
s
t
i
m
a
t
o
r
 
객
체
를
 
해
당
 
하
이
퍼
파
라
미
터
로
 
재
학
습
시
킵
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
 
G
r
i
d
S
e
a
r
c
h
C
V

p
a
r
a
m
e
t
e
r
s
=
{
'
m
a
x
_
d
e
p
t
h
'
:
[
1
,
2
,
3
]
,
 
'
m
i
n
_
s
a
m
p
l
e
s
_
s
p
l
i
t
'
:
[
2
,
3
]
}

g
r
i
d
_
T
K
=
G
r
i
d
S
e
a
r
c
h
C
V
(
T
o
k
e
n
i
z
e
r
,
 
p
a
r
a
m
_
g
r
i
d
=
p
a
r
a
m
e
t
e
r
s
,
 
c
v
=
3
,
 
s
c
o
r
i
n
g
=
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
 
r
e
f
i
t
=
T
r
u
e
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

t
r
a
i
n
[
'
a
u
t
h
o
r
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
t
r
a
i
n
[
'
a
u
t
h
o
r
'
]
)

t
r
a
i
n
[
'
a
u
t
h
o
r
'
]
[
0
]
```

<pre>
0
</pre>

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
'
t
e
x
t
'
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
2
6
,

 
 
3
3
3
4
,

 
 
1
3
9
,

 
 
1
2
9
5
,

 
 
2
2
,

 
 
3
6
,

 
 
2
8
5
,

 
 
2
,

 
 
6
4
2
6
,

 
 
1
,

 
 
2
3
4
1
,

 
 
2
,

 
 
1
0
,

 
 
4
4
0
0
,

 
 
1
6
,

 
 
5
,

 
 
8
0
,

 
 
1
8
7
,

 
 
4
7
,

 
 
3
8
0
5
,

 
 
3
,

 
 
3
0
3
,

 
 
4
,

 
 
1
,

 
 
2
6
3
,

 
 
2
2
0
8
,

 
 
5
,

 
 
3
2
0
,

 
 
7
4
,

 
 
1
3
6
,

 
 
1
2
7
,

 
 
9
2
2
,

 
 
2
,

 
 
1
,

 
 
3
0
6
,

 
 
4
0
,

 
 
1
4
8
8
,

 
 
4
1
7
5
,

 
 
9
8
,

 
 
1
,

 
 
4
4
3
]
,

 
[
1
1
,
 
9
0
,
 
1
2
8
,
 
7
2
5
,
 
4
,
 
2
2
,
 
9
,
 
1
,
 
5
9
6
6
,
 
8
0
,
 
2
8
,
 
6
,
 
4
5
0
,
 
2
4
5
3
]
,

 
[
7
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
3
,

 
 
8
,

 
 
6
,

 
 
6
9
4
,

 
 
5
9
6
7
,

 
 
5
6
0
,

 
 
2
4
,

 
 
1
9
,

 
 
1
6
,

 
 
1
4
,

 
 
1
4
6
6
0
,

 
 
1
1
9
,

 
 
1
,

 
 
5
1
3
,

 
 
4
6
4
3
,

 
 
3
2
,

 
 
2
5
6
,

 
 
2
,

 
 
1
4
0
7
,

 
 
5
2
8
,

 
 
1
4
,

 
 
2
1
4
,

 
 
5
9
6
7
,

 
 
6
9
3
8
,

 
 
1
3
,

 
 
3
7
,

 
 
2
0
3
,

 
 
2
,

 
 
1
,

 
 
7
8
7
,

 
 
3
5
3
,

 
 
5
2
6
,

 
 
3
1
0
1
]
,

 
[
1
2
0
,

 
 
5
6
8
,

 
 
2
5
,

 
 
7
6
6
,

 
 
1
6
,

 
 
3
4
,

 
 
2
1
6
,

 
 
2
4
,

 
 
7
5
4
,

 
 
4
1
7
6
,

 
 
2
7
,

 
 
1
,

 
 
2
9
9
3
,

 
 
3
2
2
1
,

 
 
9
3
6
1
,

 
 
8
4
8
,

 
 
3
5
1
,

 
 
1
0
6
1
2
,

 
 
2
3
,

 
 
4
1
1
,

 
 
5
5
8
1
,

 
 
3
,

 
 
1
4
6
6
1
,

 
 
2
2
0
9
,

 
 
3
2
,

 
 
2
1
6
,

 
 
1
6
,

 
 
7
,

 
 
6
0
4
,

 
 
1
4
8
,

 
 
1
3
5
,

 
 
9
3
6
2
,

 
 
3
,

 
 
8
4
9
]
,

 
[
1
2
2
9
,

 
 
1
6
0
,

 
 
7
3
5
,

 
 
2
0
,

 
 
7
5
,

 
 
6
9
4
,

 
 
1
,

 
 
5
2
1
4
,

 
 
1
4
6
4
,

 
 
1
5
,

 
 
2
2
1
0
,

 
 
1
8
,

 
 
6
,

 
 
5
5
8
2
,

 
 
2
5
9
,

 
 
1
6
8
8
,

 
 
1
4
6
6
2
,

 
 
8
7
,

 
 
1
5
,

 
 
3
9
9
,

 
 
1
6
,

 
 
1
4
,

 
 
5
9
6
8
,

 
 
1
3
5
4
,

 
 
2
1
,

 
 
1
5
,

 
 
5
5
8
3
]
,

 
[
6
,

 
 
4
5
6
,

 
 
2
2
1
,

 
 
7
,

 
 
8
1
7
,

 
 
1
0
,

 
 
4
2
0
,

 
 
1
4
8
,

 
 
8
0
3
,

 
 
1
7
5
,

 
 
7
8
,

 
 
4
5
3
,

 
 
3
,

 
 
7
6
0
7
,

 
 
1
8
8
4
3
,

 
 
1
0
8
,

 
 
4
0
,

 
 
3
8
0
6
,

 
 
1
,

 
 
1
4
6
6
3
,

 
 
2
,

 
 
1
0
,

 
 
3
9
6
,

 
 
9
,

 
 
5
,

 
 
2
6
9
,

 
 
1
7
2
8
,

 
 
3
7
,

 
 
7
9
3
,

 
 
6
9
3
9
,

 
 
4
,

 
 
1
,

 
 
5
3
3
,

 
 
1
2
1
9
4
,

 
 
5
2
1
5
,

 
 
2
7
,

 
 
1
1
0
3
,

 
 
7
2
6
,

 
 
5
,

 
 
3
1
,

 
 
9
0
,

 
 
8
6
6
,

 
 
1
1
,

 
 
4
,

 
 
2
8
,

 
 
4
5
7
,

 
 
3
,

 
 
4
1
,

 
 
5
,

 
 
1
4
3
,

 
 
2
,

 
 
6
,

 
 
9
3
6
3
,

 
 
1
8
8
3
,

 
 
2
5
9
1
,

 
 
1
7
,

 
 
1
5
,

 
 
1
8
8
4
4
,

 
 
2
,

 
 
1
3
5
,

 
 
3
,

 
 
1
,

 
 
8
9
9
,

 
 
3
,

 
 
5
9
6
9
,

 
 
1
5
8
3
,

 
 
4
,

 
 
3
9
,

 
 
2
3
,

 
 
1
5
,

 
 
1
9
9
0
,

 
 
5
,

 
 
1
4
5
,

 
 
1
1
0
,

 
 
2
2
1
1
,

 
 
3
9
7
2
,

 
 
7
,

 
 
1
2
7
,

 
 
6
8
8
,

 
 
4
,

 
 
1
6
5
7
,

 
 
1
5
,

 
 
3
9
7
3
]
,

 
[
1
,

 
 
8
4
1
6
,

 
 
2
3
7
,

 
 
2
1
,

 
 
2
6
,

 
 
2
6
3
,

 
 
2
1
4
,

 
 
3
1
0
2
,

 
 
7
,

 
 
1
,

 
 
1
6
5
8
,

 
 
2
,

 
 
2
1
5
0
,

 
 
7
6
0
8
,

 
 
3
,

 
 
1
2
4
,

 
 
5
5
8
4
,

 
 
8
,

 
 
3
2
3
,

 
 
1
8
0
,

 
 
7
1
5
]
,

 
[
1
,
 
9
3
6
4
,
 
6
9
8
,
 
7
,
 
1
8
8
4
5
,
 
2
4
,
 
1
0
,
 
2
2
5
]
,

 
[
5
,

 
 
1
8
2
,

 
 
9
,

 
 
3
3
,

 
 
4
6
,

 
 
2
0
,

 
 
1
2
5
,

 
 
4
,

 
 
7
7
1
,

 
 
1
8
8
4
6
,

 
 
1
3
6
,

 
 
1
2
7
,

 
 
2
7
4
,

 
 
4
,

 
 
2
4
2
,

 
 
2
,

 
 
1
8
8
4
7
,

 
 
3
,

 
 
1
3
1
,

 
 
2
,

 
 
1
,

 
 
2
5
0
8
,

 
 
2
,

 
 
1
4
6
6
4
,

 
 
3
,

 
 
2
0
1
,

 
 
4
1
,

 
 
3
4
,

 
 
3
1
0
3
,

 
 
2
6
,

 
 
4
9
4
,

 
 
2
0
,

 
 
6
1
,

 
 
1
0
9
,

 
 
6
4
4
,

 
 
5
,

 
 
7
7
2
,

 
 
4
,

 
 
3
3
,

 
 
1
2
0
,

 
 
2
0
4
8
,

 
 
7
6
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
4
,

 
 
1
0
0
6
,

 
 
1
,

 
 
7
3
6
,

 
 
7
6
0
9
,

 
 
2
,

 
 
9
,

 
 
9
3
7
,

 
 
1
2
0
2
,

 
 
1
2
,

 
 
5
6
3
,

 
 
1
3
,

 
 
5
5
8
5
,

 
 
7
,

 
 
1
,

 
 
4
3
1
,

 
 
1
8
8
4
8
,

 
 
1
8
8
4
9
,

 
 
5
,

 
 
1
4
5
,

 
 
9
,

 
 
3
3
,

 
 
4
6
,

 
 
2
0
,

 
 
1
8
2
6
,

 
 
4
1
7
7
,

 
 
7
8
,

 
 
9
9
,

 
 
1
8
2
7
,

 
 
4
,

 
 
1
,

 
 
1
0
2
,

 
 
1
8
8
5
0
,

 
 
7
,

 
 
8
4
1
7
,

 
 
3
,

 
 
5
,

 
 
7
6
7
,

 
 
6
9
9
,

 
 
9
,

 
 
3
3
,

 
 
4
9
,

 
 
9
4
,

 
 
4
0
]
,

 
[
5
,

 
 
1
6
8
9
,

 
 
9
,

 
 
4
8
4
,

 
 
1
,

 
 
2
5
9
2
,

 
 
2
,

 
 
4
6
4
4
,

 
 
1
8
3
,

 
 
1
,

 
 
9
3
6
5
,

 
 
2
,

 
 
1
2
1
9
5
,

 
 
1
8
3
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
4
5
,

 
 
5
5
8
6
,

 
 
5
1
8
,

 
 
8
4
1
9
,

 
 
1
7
,

 
 
2
2
]
,

 
[
1
4
,

 
 
1
4
0
,

 
 
2
3
2
,

 
 
9
,

 
 
5
,

 
 
1
1
8
,

 
 
2
9
7
,

 
 
1
0
,

 
 
5
9
7
0
,

 
 
1
4
,

 
 
1
4
0
,

 
 
1
6
1
6
,

 
 
4
,

 
 
1
1
0
4
,

 
 
1
0
,

 
 
1
6
9
0
,

 
 
6
,

 
 
1
5
6
,

 
 
2
3
1
,

 
 
8
2
,

 
 
1
4
,

 
 
5
8
4
]
,

 
[
1
2
4
,
 
3
4
,
 
1
4
6
6
5
,
 
1
0
2
3
,
 
3
,
 
1
7
,
 
1
,
 
2
7
9
,
 
2
9
,
 
1
6
5
7
]
,

 
[
3
4
6
9
,
 
3
8
9
,
 
2
8
7
7
,
 
6
8
0
,
 
8
8
0
,
 
2
7
5
,
 
1
5
,
 
9
1
,
 
3
4
0
,
 
8
,
 
1
,
 
4
8
9
9
,
 
2
,
 
1
,
 
2
4
6
]
,

 
[
1
,
 
6
9
4
0
,
 
8
1
,
 
2
6
9
4
,
 
1
8
2
8
,
 
1
6
8
,
 
6
1
,
 
1
1
2
8
,
 
6
6
,
 
1
,
 
5
1
3
,
 
2
0
9
,
 
4
,
 
1
8
8
5
1
,
 
2
6
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
0
0
7
,
 
6
2
,
 
1
6
5
9
,
 
1
,
 
1
4
6
6
6
,
 
2
,
 
2
6
,
 
2
4
9
]
,

 
[
1
4
,

 
 
1
2
,

 
 
1
1
4
1
,

 
 
2
2
,

 
 
3
,

 
 
5
,

 
 
8
4
,

 
 
2
6
9
5
,

 
 
6
,

 
 
5
5
8
7
,

 
 
3
,

 
 
2
0
9
,

 
 
2
5
9
3
,

 
 
9
1
1
,

 
 
5
1
4
,

 
 
1
,

 
 
5
2
1
6
,

 
 
1
2
1
9
6
,

 
 
2
,

 
 
1
,

 
 
6
8
9
,

 
 
9
6
6
,

 
 
4
1
6
,

 
 
9
,

 
 
1
5
6
,

 
 
2
,

 
 
1
,

 
 
1
0
0
8
,

 
 
4
6
,

 
 
1
0
9
,

 
 
1
7
2
9
,

 
 
3
,

 
 
1
9
,

 
 
5
,

 
 
1
,

 
 
7
1
6
,

 
 
2
,

 
 
6
,

 
 
6
4
2
7
,

 
 
3
,

 
 
6
9
4
1
,

 
 
5
9
7
1
,

 
 
4
6
,

 
 
2
0
,

 
 
2
5
1
,

 
 
4
,

 
 
3
3
3
5
]
,

 
[
4
,

 
 
6
7
,

 
 
5
9
7
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
,

 
 
2
4
7
,

 
 
5
1
,

 
 
1
1
1
,

 
 
6
4
2
8
,

 
 
4
9
0
0
,

 
 
3
6
,

 
 
3
0
7
,

 
 
9
,

 
 
2
1
,

 
 
3
2
,

 
 
5
6
4
,

 
 
5
,

 
 
9
3
,

 
 
1
6
4
,

 
 
5
7
,

 
 
9
1
2
,

 
 
2
,

 
 
3
8
5
,

 
 
1
0
6
1
3
,

 
 
2
,

 
 
1
0
8
3
,

 
 
1
1
4
2
,

 
 
3
,

 
 
2
3
4
2
,

 
 
5
,

 
 
1
5
8
3
,

 
 
6
3
,

 
 
3
2
,

 
 
5
,

 
 
6
4
2
9
,

 
 
3
,

 
 
6
,

 
 
3
8
0
7
,

 
 
5
0
,

 
 
7
,

 
 
1
4
3
9
,

 
 
2
,

 
 
5
1
,

 
 
3
9
7
3
,

 
 
5
,

 
 
9
2
3
,

 
 
1
2
5
,

 
 
4
2
,

 
 
9
3
6
6
,

 
 
6
1
,

 
 
1
0
4
,

 
 
5
3
,

 
 
1
6
2
,

 
 
2
,

 
 
3
6
1
,

 
 
1
0
,

 
 
2
1
9
,

 
 
3
5
,

 
 
1
0
,

 
 
8
4
2
0
]
,

 
[
3
0
,

 
 
7
1
6
,

 
 
1
8
8
5
2
,

 
 
2
8
7
7
,

 
 
3
6
,

 
 
6
4
3
0
,

 
 
1
1
5
7
,

 
 
3
,

 
 
3
0
,

 
 
2
1
5
1
,

 
 
1
3
5
,

 
 
3
4
7
0
,

 
 
4
9
0
1
,

 
 
2
7
,

 
 
1
0
,

 
 
1
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
2
7
,

 
 
2
,

 
 
3
0
,

 
 
4
8
5
,

 
 
3
,

 
 
1
,

 
 
3
1
6
,

 
 
2
,

 
 
2
8
7
8
,

 
 
1
7
2
]
,

 
[
5
,

 
 
7
5
,

 
 
2
3
3
,

 
 
4
0
,

 
 
1
3
7
,

 
 
1
6
,

 
 
4
,

 
 
3
5
5
,

 
 
2
,

 
 
6
,

 
 
1
6
1
7
,

 
 
7
6
1
0
,

 
 
8
4
2
1
,

 
 
1
3
,

 
 
1
9
,

 
 
2
1
,

 
 
3
8
,

 
 
7
2
,

 
 
5
,

 
 
1
2
,

 
 
4
3
,

 
 
2
4
0
0
,

 
 
2
,

 
 
6
,

 
 
1
2
1
9
7
,

 
 
1
8
8
5
3
,

 
 
2
,

 
 
6
,

 
 
1
8
8
5
4
,

 
 
2
,

 
 
4
1
7
8
,

 
 
1
2
1
9
8
,

 
 
3
,

 
 
7
,

 
 
1
3
5
5
,

 
 
2
,

 
 
1
,

 
 
7
6
1
1
,

 
 
3
,

 
 
8
4
2
2
,

 
 
1
8
,

 
 
1
0
8
4
,

 
 
9
9
5
,

 
 
1
4
4
0
,

 
 
1
7
3
0
,

 
 
2
,

 
 
1
0
,

 
 
9
9
]
,

 
[
1
5
,

 
 
7
6
1
2
,

 
 
1
0
8
5
,

 
 
1
3
2
,

 
 
8
,

 
 
8
6
7
,

 
 
1
7
,

 
 
4
7
,

 
 
3
4
7
1
,

 
 
1
7
,

 
 
1
5
7
,

 
 
1
4
,

 
 
3
9
7
4
,

 
 
1
5
,

 
 
1
7
3
1
,

 
 
3
,

 
 
8
4
2
3
,

 
 
1
8
8
5
5
,

 
 
1
5
,

 
 
1
4
6
5
,

 
 
3
,

 
 
1
8
8
5
6
,

 
 
2
9
9
4
,

 
 
1
0
2
4
,

 
 
1
9
9
1
,

 
 
1
3
,

 
 
1
,

 
 
4
8
8
,

 
 
2
,

 
 
1
5
,

 
 
3
1
3
,

 
 
2
1
5
,

 
 
2
0
9
,

 
 
2
8
7
9
,

 
 
9
9
,

 
 
4
,

 
 
3
4
7
,

 
 
3
9
,

 
 
3
7
,

 
 
2
0
3
,

 
 
2
,

 
 
5
9
7
3
,

 
 
1
8
8
5
7
,

 
 
3
,

 
 
1
1
6
,

 
 
3
6
3
4
,

 
 
8
4
2
4
,

 
 
1
4
6
6
]
,

 
[
5
2
,

 
 
1
,

 
 
4
9
0
2
,

 
 
3
4
0
,

 
 
8
,

 
 
2
0
,

 
 
7
6
1
3
,

 
 
2
1
5
2
,

 
 
4
,

 
 
1
,

 
 
4
9
0
3
,

 
 
1
8
,

 
 
2
2
1
2
,

 
 
2
3
,

 
 
6
,

 
 
1
5
1
0
,

 
 
2
,

 
 
2
3
4
3
,

 
 
8
4
2
5
,

 
 
3
5
,

 
 
1
4
6
6
7
]
,

 
[
1
1
,

 
 
8
,

 
 
2
0
,

 
 
9
,

 
 
1
,

 
 
5
9
0
,

 
 
2
9
,

 
 
4
0
8
,

 
 
1
7
,

 
 
4
2
,

 
 
2
9
,

 
 
2
0
,

 
 
1
8
,

 
 
9
,

 
 
4
2
,

 
 
4
2
3
,

 
 
6
4
3
1
,

 
 
8
4
2
6
,

 
 
1
6
0
,

 
 
2
7
,

 
 
2
6
,

 
 
2
6
9
6
,

 
 
2
,

 
 
1
5
5
,

 
 
3
,

 
 
9
,

 
 
2
1
,

 
 
2
1
2
,

 
 
1
2
9
6
,

 
 
4
2
,

 
 
1
2
3
0
,

 
 
6
,

 
 
1
8
8
5
8
,

 
 
1
7
8
0
,

 
 
1
9
,

 
 
5
,

 
 
4
6
,

 
 
6
5
8
,

 
 
1
4
0
8
,

 
 
1
6
,

 
 
1
1
0
5
,

 
 
2
3
,

 
 
3
8
,

 
 
1
8
2
9
]
,

 
[
2
7
,

 
 
1
0
1
,

 
 
1
7
3
,

 
 
8
,

 
 
6
,

 
 
3
4
7
2
,

 
 
2
,

 
 
1
4
6
6
8
,

 
 
2
,

 
 
1
8
8
5
9
,

 
 
2
,

 
 
7
6
1
4
,

 
 
2
,

 
 
6
9
4
2
,

 
 
3
,

 
 
5
9
7
4
,

 
 
2
6
9
7
,

 
 
1
2
1
9
9
]
,

 
[
1
3
,

 
 
1
2
0
,

 
 
2
6
2
,

 
 
6
,

 
 
2
4
1
,

 
 
2
,

 
 
4
3
4
,

 
 
3
,

 
 
8
4
2
7
,

 
 
8
,

 
 
5
,

 
 
3
9
7
5
,

 
 
4
,

 
 
6
0
5
,

 
 
3
9
,

 
 
2
4
,

 
 
5
5
,

 
 
9
6
7
,

 
 
1
2
2
0
0
,

 
 
7
,

 
 
1
,

 
 
6
4
3
2
,

 
 
1
6
,

 
 
1
3
,

 
 
7
5
5
,

 
 
1
2
6
5
,

 
 
3
,

 
 
1
2
6
6
,

 
 
1
4
,

 
 
2
4
5
4
,

 
 
1
,

 
 
8
4
2
8
,

 
 
2
6
,

 
 
1
0
6
1
4
,

 
 
7
1
,

 
 
1
3
,

 
 
3
9
9
,

 
 
4
0
,

 
 
1
4
6
6
9
,

 
 
8
4
2
9
,

 
 
1
3
,

 
 
6
4
3
3
,

 
 
4
0
,

 
 
6
9
4
3
,

 
 
3
,

 
 
4
0
,

 
 
1
8
8
6
0
,

 
 
3
9
7
6
,

 
 
1
3
,

 
 
5
5
8
8
,

 
 
4
0
,

 
 
4
6
4
5
,

 
 
1
4
6
7
0
,

 
 
4
0
,

 
 
2
5
0
9
,

 
 
3
,

 
 
4
0
,

 
 
3
8
5
,

 
 
4
6
,

 
 
2
6
,

 
 
2
8
,

 
 
1
4
,

 
 
5
8
,

 
 
2
,

 
 
4
3
1
,

 
 
1
3
,

 
 
1
2
2
0
1
,

 
 
5
2
1
7
,

 
 
3
,

 
 
7
,

 
 
1
8
8
6
1
,

 
 
9
3
6
7
,

 
 
8
4
3
0
,

 
 
1
8
8
6
2
,

 
 
7
,

 
 
1
7
3
,

 
 
1
,

 
 
1
8
8
6
3
,

 
 
1
2
0
3
,

 
 
2
,

 
 
1
,

 
 
5
2
1
8
]
,

 
[
6
7
,
 
2
6
9
8
,
 
2
2
1
0
,
 
2
1
,
 
1
6
1
8
,
 
2
9
,
 
4
5
8
,
 
2
3
,
 
3
4
1
,
 
1
8
8
3
,
 
2
6
9
8
]
,

 
[
1
7
,

 
 
1
1
3
,

 
 
7
6
1
5
,

 
 
3
,

 
 
1
3
5
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
4
9
,

 
 
3
,

 
 
1
3
7
,

 
 
3
,

 
 
5
7
4
,

 
 
8
7
,

 
 
2
0
4
,

 
 
3
,

 
 
4
2
4
,

 
 
1
,

 
 
2
5
3
,

 
 
1
3
2
3
,

 
 
2
,

 
 
1
,

 
 
1
5
4
9
,

 
 
2
9
,

 
 
8
4
8
,

 
 
2
4
0
1
]
,

 
[
3
2
,

 
 
9
,

 
 
1
6
,

 
 
7
6
,

 
 
1
1
8
,

 
 
1
5
5
0
,

 
 
2
8
,

 
 
7
7
,

 
 
4
,

 
 
2
8
,

 
 
2
5
7
,

 
 
2
5
,

 
 
9
,

 
 
1
8
8
6
4
,

 
 
6
9
4
,

 
 
1
1
8
,

 
 
2
8
,

 
 
9
2
,

 
 
2
1
,

 
 
6
2
,

 
 
3
,

 
 
6
1
,

 
 
1
5
1
1
,

 
 
2
4
,

 
 
9
9
6
,

 
 
7
,

 
 
3
9
7
7
,

 
 
1
3
,

 
 
2
1
2
,

 
 
9
5
,

 
 
8
4
3
1
,

 
 
7
,

 
 
2
6
6
,

 
 
3
,

 
 
7
,

 
 
3
6
3
5
,

 
 
3
9
2
,

 
 
1
9
3
,

 
 
3
2
2
2
,

 
 
2
,

 
 
2
4
7
,

 
 
2
5
,

 
 
1
5
1
2
,

 
 
1
6
,

 
 
4
,

 
 
1
,

 
 
8
5
0
,

 
 
3
,

 
 
1
6
1
9
,

 
 
1
4
4
1
,

 
 
2
,

 
 
2
6
,

 
 
8
4
1
,

 
 
6
,

 
 
8
4
1
,

 
 
1
9
,

 
 
1
5
6
,

 
 
1
3
5
4
,

 
 
8
6
8
,

 
 
6
2
,

 
 
3
8
0
8
,

 
 
7
,

 
 
6
9
4
4
,

 
 
4
,

 
 
3
7
,

 
 
9
7
8
,

 
 
4
1
2
,

 
 
7
,

 
 
1
,

 
 
2
6
1
,

 
 
2
,

 
 
6
9
4
,

 
 
1
1
5
8
,

 
 
2
3
,

 
 
1
,

 
 
4
3
1
,

 
 
1
0
6
1
5
,

 
 
7
,

 
 
9
3
6
8
,

 
 
3
,

 
 
2
6
,

 
 
9
7
9
,

 
 
4
1
7
9
,

 
 
8
5
,

 
 
3
9
7
8
,

 
 
4
,

 
 
2
1
0
,

 
 
1
,

 
 
3
8
0
9
,

 
 
1
8
8
6
5
,

 
 
2
,

 
 
1
4
4
2
,

 
 
1
2
2
0
2
,

 
 
2
4
5
5
]
,

 
[
5
,

 
 
9
8
,

 
 
4
,

 
 
2
8
,

 
 
4
4
,

 
 
1
,

 
 
3
8
1
0
,

 
 
2
,

 
 
3
3
3
6
,

 
 
1
3
6
,

 
 
2
8
6
,

 
 
4
,

 
 
1
5
8
4
,

 
 
1
4
7
,

 
 
2
1
,

 
 
3
6
4
,

 
 
2
3
2
,

 
 
3
4
5
,

 
 
4
4
,

 
 
1
,

 
 
2
6
9
9
,

 
 
2
,

 
 
2
4
0
2
,

 
 
1
3
6
,

 
 
1
2
7
,

 
 
6
8
8
,

 
 
7
,

 
 
1
,

 
 
2
4
4
,

 
 
4
,

 
 
4
6
0
]
,

 
[
5
5
,

 
 
1
8
8
6
6
,

 
 
1
8
3
0
,

 
 
1
8
8
6
7
,

 
 
3
,

 
 
9
5
,

 
 
1
3
2
4
,

 
 
1
5
8
5
,

 
 
2
9
,

 
 
2
3
4
4
,

 
 
4
0
,

 
 
9
,

 
 
1
4
6
7
1
,

 
 
5
5
,

 
 
6
4
,

 
 
9
3
6
9
,

 
 
4
9
,

 
 
2
8
,

 
 
1
8
8
6
8
,

 
 
5
9
7
5
,

 
 
2
7
,

 
 
5
5
,

 
 
4
4
0
1
,

 
 
1
,

 
 
1
4
6
7
2
,

 
 
3
,

 
 
5
5
,

 
 
6
5
1
,

 
 
8
4
3
2
,

 
 
1
6
,

 
 
3
9
7
9
,

 
 
2
3
,

 
 
7
0
,

 
 
7
1
7
,

 
 
3
4
,

 
 
8
0
,

 
 
5
2
1
9
,

 
 
8
8
,

 
 
1
,

 
 
1
2
2
0
3
,

 
 
3
5
,

 
 
2
4
,

 
 
1
,

 
 
8
4
3
3
,

 
 
1
5
8
6
]
,

 
[
2
6
,

 
 
1
,

 
 
2
3
8
,

 
 
1
2
2
0
4
,

 
 
2
1
4
,

 
 
1
6
8
,

 
 
1
3
,

 
 
6
3
,

 
 
4
,

 
 
2
5
1
0
,

 
 
1
6
,

 
 
6
,

 
 
4
9
0
4
,

 
 
2
,

 
 
6
9
4
5
,

 
 
8
7
,

 
 
1
,

 
 
7
9
,

 
 
7
9
4
,

 
 
3
,

 
 
7
6
8
,

 
 
2
,

 
 
4
6
4
6
,

 
 
3
,

 
 
6
,

 
 
1
9
3
6
,

 
 
2
,

 
 
1
2
2
0
5
,

 
 
7
,

 
 
4
6
4
7
]
,

 
[
1
0
5
1
,
 
1
,
 
1
6
5
,
 
2
1
5
3
,
 
2
,
 
1
0
6
1
6
,
 
1
0
6
1
7
,
 
4
4
,
 
1
,
 
3
7
4
]
,

 
[
5
,

 
 
8
,

 
 
1
0
5
2
,

 
 
3
,

 
 
2
3
8
,

 
 
3
,

 
 
1
2
,

 
 
6
,

 
 
3
9
8
0
,

 
 
4
1
8
0
,

 
 
1
7
,

 
 
2
2
,

 
 
3
,

 
 
3
2
,

 
 
6
8
,

 
 
2
2
,

 
 
4
9
,

 
 
8
2
7
,

 
 
1
6
,

 
 
6
0
,

 
 
5
,

 
 
2
9
,

 
 
3
8
,

 
 
2
,

 
 
5
1
,

 
 
1
0
2
,

 
 
6
6
4
,

 
 
1
0
0
,

 
 
5
,

 
 
8
4
,

 
 
6
3
6
,

 
 
1
,

 
 
4
7
0
,

 
 
9
,

 
 
5
,

 
 
5
2
7
,

 
 
8
,

 
 
7
0
0
,

 
 
2
0
5
,

 
 
2
4
,

 
 
6
3
,

 
 
1
7
,

 
 
1
2
9
]
,

 
[
3
4
,

 
 
4
6
,

 
 
1
8
7
,

 
 
7
4
,

 
 
1
0
4
,

 
 
2
3
,

 
 
1
,

 
 
1
0
2
5
,

 
 
1
5
8
,

 
 
1
8
,

 
 
4
2
,

 
 
9
8
,

 
 
4
,

 
 
3
8
1
1
,

 
 
6
9
4
6
,

 
 
2
7
8
5
,

 
 
3
4
7
3
,

 
 
2
,

 
 
5
6
4
,

 
 
1
8
,

 
 
1
5
1
3
,

 
 
2
2
1
,

 
 
1
6
6
0
,

 
 
5
2
,

 
 
1
1
6
,

 
 
2
5
7
,

 
 
1
8
,

 
 
2
,

 
 
1
2
3
1
,

 
 
1
7
8
1
,

 
 
3
,

 
 
2
7
2
,

 
 
6
4
3
4
,

 
 
2
,

 
 
3
9
8
1
,

 
 
3
5
,

 
 
2
4
0
3
,

 
 
2
,

 
 
2
3
4
5
,

 
 
3
5
,

 
 
3
2
2
3
,

 
 
2
9
,

 
 
2
7
0
0
,

 
 
2
7
,

 
 
5
1
,

 
 
1
0
0
9
,

 
 
7
6
1
6
,

 
 
2
3
4
6
]
,

 
[
7
5
,
 
5
2
,
 
4
2
,
 
9
5
0
,
 
7
,
 
5
1
,
 
3
4
7
4
]
,

 
[
9
3
7
0
,

 
 
5
1
9
,

 
 
7
3
,

 
 
4
2
,

 
 
1
2
2
0
6
,

 
 
1
3
,

 
 
2
2
6
4
,

 
 
7
6
,

 
 
1
3
6
,

 
 
1
8
8
6
9
,

 
 
7
0
,

 
 
1
2
9
7
,

 
 
2
,

 
 
1
8
3
1
,

 
 
9
3
8
,

 
 
7
9
,

 
 
4
4
0
2
]
,

 
[
1
4
,

 
 
6
5
2
,

 
 
1
5
1
4
,

 
 
1
2
8
,

 
 
3
,

 
 
6
,

 
 
1
0
4
,

 
 
6
1
2
,

 
 
2
0
7
,

 
 
6
,

 
 
9
3
7
1
,

 
 
9
,

 
 
8
,

 
 
5
0
,

 
 
3
3
5
,

 
 
5
9
,

 
 
6
,

 
 
1
4
8
9
]
,

 
[
1
,

 
 
7
9
,

 
 
3
8
1
2
,

 
 
1
2
6
7
,

 
 
4
3
5
,

 
 
2
6
5
,

 
 
2
1
,

 
 
8
4
3
4
,

 
 
3
,

 
 
2
1
,

 
 
1
2
8
,

 
 
9
3
7
2
,

 
 
2
0
5
,

 
 
5
7
,

 
 
6
,

 
 
1
0
5
3
,

 
 
5
9
7
6
,

 
 
5
5
8
9
,

 
 
3
,

 
 
1
3
,

 
 
1
9
6
,

 
 
3
,

 
 
1
9
6
,

 
 
2
,

 
 
1
2
2
0
7
,

 
 
5
5
9
0
,

 
 
3
9
8
2
,

 
 
2
2
1
3
]
,

 
[
1
5
,

 
 
2
1
9
,

 
 
1
0
6
1
8
,

 
 
1
3
,

 
 
2
2
6
5
,

 
 
1
7
8
2
,

 
 
3
,

 
 
1
5
,

 
 
1
5
5
1
,

 
 
8
,

 
 
2
,

 
 
9
,

 
 
1
5
1
5
,

 
 
3
,

 
 
3
8
1
3
,

 
 
1
7
2
,

 
 
9
,

 
 
1
,

 
 
1
5
9
,

 
 
4
4
0
3
,

 
 
6
4
3
5
,

 
 
8
5
,

 
 
4
,

 
 
2
5
9
,

 
 
1
7
,

 
 
6
4
,

 
 
7
,

 
 
1
,

 
 
4
8
0
]
,

 
[
8
2
,

 
 
1
,

 
 
8
3
,

 
 
2
5
9
4
,

 
 
1
4
,

 
 
4
1
8
1
,

 
 
1
,

 
 
4
9
0
5
,

 
 
1
0
6
1
9
,

 
 
2
1
7
,

 
 
1
,

 
 
3
8
1
4
,

 
 
1
6
,

 
 
6
0
,

 
 
4
,

 
 
4
9
0
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
8
8
7
0
,

 
 
2
,

 
 
1
,

 
 
1
4
9
]
,

 
[
1
,

 
 
2
7
9
,

 
 
5
1
2
,

 
 
6
4
5
,

 
 
2
,

 
 
2
3
4
7
,

 
 
2
1
,

 
 
1
8
3
2
,

 
 
3
,

 
 
5
1
9
,

 
 
2
,

 
 
9
7
,

 
 
9
3
7
3
,

 
 
7
,

 
 
1
9
,

 
 
1
1
7
9
,

 
 
2
5
,

 
 
2
5
7
,

 
 
4
,

 
 
2
8
,

 
 
2
5
9
5
,

 
 
4
9
,

 
 
1
6
9
1
,

 
 
1
,

 
 
6
3
2
,

 
 
1
2
2
0
8
,

 
 
2
,

 
 
1
,

 
 
4
1
8
2
,

 
 
4
7
,

 
 
6
9
4
7
,

 
 
2
,

 
 
1
2
7
,

 
 
1
1
0
5
,

 
 
2
1
,

 
 
6
,

 
 
6
9
4
8
,

 
 
1
0
0
6
,

 
 
6
,

 
 
2
6
3
,

 
 
2
,

 
 
2
9
6
,

 
 
1
1
8
0
,

 
 
1
6
2
0
,

 
 
1
3
,

 
 
4
7
,

 
 
9
1
2
]
,

 
[
7
6
1
7
,

 
 
2
5
9
6
,

 
 
8
,

 
 
1
5
3
,

 
 
1
4
6
7
3
,

 
 
1
7
,

 
 
1
6
1
,

 
 
1
9
7
,

 
 
5
2
0
,

 
 
2
,

 
 
1
5
,

 
 
1
1
5
9
,

 
 
1
4
,

 
 
1
2
,

 
 
1
3
7
3
,

 
 
6
,

 
 
1
0
3
7
,

 
 
3
,

 
 
5
2
2
0
,

 
 
2
8
6
,

 
 
2
0
,

 
 
1
2
9
8
,

 
 
9
6
,

 
 
7
,

 
 
1
4
6
7
4
,

 
 
1
7
5
,

 
 
6
,

 
 
2
2
2
,

 
 
4
7
1
,

 
 
2
,

 
 
4
1
3
]
,

 
[
4
1
8
3
,

 
 
5
,

 
 
7
9
5
,

 
 
1
3
,

 
 
4
9
5
,

 
 
7
,

 
 
3
6
3
6
,

 
 
1
1
,

 
 
6
9
4
9
,

 
 
4
5
,

 
 
8
,

 
 
2
5
1
1
,

 
 
6
,

 
 
2
5
3
,

 
 
2
4
5
6
,

 
 
1
8
8
7
1
,

 
 
4
4
0
4
,

 
 
5
5
9
1
,

 
 
1
9
,

 
 
6
8
1
,

 
 
1
0
,

 
 
3
8
1
5
,

 
 
4
,

 
 
1
0
6
2
0
,

 
 
3
,

 
 
6
4
3
6
,

 
 
7
,

 
 
1
,

 
 
8
4
3
5
,

 
 
2
2
1
4
,

 
 
1
,

 
 
7
4
4
,

 
 
2
,

 
 
6
,

 
 
1
9
3
7
,

 
 
2
,

 
 
3
7
8
,

 
 
5
2
8
]
,

 
[
1
1
,

 
 
8
,

 
 
3
2
,

 
 
2
9
9
5
,

 
 
2
6
0
,

 
 
2
7
1
,

 
 
2
6
0
,

 
 
1
,

 
 
4
3
8
,

 
 
8
,

 
 
2
1
5
,

 
 
2
6
0
,

 
 
1
,

 
 
8
1
8
,

 
 
8
,

 
 
1
4
6
7
5
,

 
 
1
4
6
7
,

 
 
3
2
,

 
 
3
8
1
2
,

 
 
2
7
0
1
,

 
 
1
6
,

 
 
2
0
9
1
,

 
 
1
6
,

 
 
4
6
,

 
 
2
8
,

 
 
1
8
,

 
 
1
4
6
7
6
,

 
 
2
1
,

 
 
1
,

 
 
2
7
0
2
,

 
 
1
4
6
7
7
,

 
 
3
8
1
6
,

 
 
1
,

 
 
3
7
3
,

 
 
1
2
,

 
 
7
7
3
,

 
 
4
2
,

 
 
8
,

 
 
1
0
6
,

 
 
5
4
,

 
 
5
4
6
,

 
 
6
3
,

 
 
1
1
2
9
,

 
 
3
2
2
4
,

 
 
1
0
8
6
,

 
 
1
6
,

 
 
1
8
8
7
2
,

 
 
8
1
,

 
 
1
4
,

 
 
1
7
0
,

 
 
4
9
0
7
]
,

 
[
1
,
 
2
9
9
6
,
 
2
,
 
5
2
2
1
,
 
4
,
 
7
5
4
,
 
6
9
,
 
1
1
0
6
,
 
1
2
,
 
3
2
3
,
 
8
4
2
]
,

 
[
1
1
,

 
 
2
5
,

 
 
2
0
,

 
 
4
,

 
 
2
8
,

 
 
7
5
6
,

 
 
1
3
9
,

 
 
9
,

 
 
1
,

 
 
1
0
2
,

 
 
7
6
1
8
,

 
 
7
8
1
,

 
 
2
6
,

 
 
1
0
6
2
1
,

 
 
2
7
,

 
 
1
,

 
 
1
8
8
,

 
 
2
,

 
 
1
,

 
 
1
0
4
,

 
 
7
9
,

 
 
7
1
,

 
 
4
,

 
 
7
1
8
,

 
 
2
0
5
,

 
 
1
3
,

 
 
6
9
5
0
]
,

 
[
5
,

 
 
8
4
3
,

 
 
2
0
,

 
 
2
7
8
,

 
 
3
3
,

 
 
1
2
0
,

 
 
7
6
1
9
,

 
 
5
,

 
 
3
1
,

 
 
1
0
8
4
,

 
 
4
3
,

 
 
2
7
,

 
 
1
,

 
 
2
2
1
5
,

 
 
2
,

 
 
1
,

 
 
6
9
5
1
,

 
 
5
2
2
2
]
,

 
[
5
,

 
 
2
7
2
,

 
 
2
7
8
6
,

 
 
1
1
0
,

 
 
4
,

 
 
6
3
,

 
 
3
,

 
 
1
2
2
9
,

 
 
9
,

 
 
1
0
,

 
 
1
1
8
1
,

 
 
4
9
0
8
,

 
 
3
2
2
5
,

 
 
7
,

 
 
2
8
6
,

 
 
5
,

 
 
1
9
0
,

 
 
2
7
8
7
,

 
 
1
1
0
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
7
,

 
 
2
8
6
,

 
 
6
4
,

 
 
9
,

 
 
5
,

 
 
8
,

 
 
4
6
4
8
,

 
 
4
,

 
 
1
,

 
 
1
0
6
2
2
,

 
 
1
8
8
7
3
,

 
 
2
,

 
 
1
,

 
 
1
5
5
]
,

 
[
3
,
 
1
,
 
1
2
2
0
9
,
 
4
8
5
,
 
3
,
 
1
,
 
1
8
8
7
4
,
 
4
8
5
,
 
3
2
4
,
 
6
6
]
,

 
[
5
8
5
,

 
 
3
8
1
7
,

 
 
1
6
,

 
 
5
,

 
 
5
5
6
,

 
 
3
9
,

 
 
8
,

 
 
6
,

 
 
2
2
2
,

 
 
1
4
6
7
8
,

 
 
7
1
,

 
 
6
1
,

 
 
5
1
5
,

 
 
1
8
8
7
5
,

 
 
3
,

 
 
2
,

 
 
1
4
6
7
9
,

 
 
1
0
8
5
]
,

 
[
1
2
4
9
,

 
 
1
,

 
 
2
9
9
7
,

 
 
2
,

 
 
2
7
1
,

 
 
2
9
9
,

 
 
1
5
5
2
,

 
 
4
4
,

 
 
1
0
,

 
 
1
2
9
9
,

 
 
3
,

 
 
7
,

 
 
6
,

 
 
1
5
6
,

 
 
1
0
3
8
,

 
 
9
3
9
,

 
 
1
6
,

 
 
5
,

 
 
2
7
6
,

 
 
1
3
,

 
 
1
,

 
 
7
0
8
,

 
 
5
2
1
,

 
 
5
0
,

 
 
2
3
4
8
,

 
 
5
9
,

 
 
1
0
8
4
,

 
 
5
,

 
 
1
6
2
,

 
 
9
2
2
,

 
 
9
,

 
 
6
,

 
 
8
0
4
,

 
 
2
,

 
 
5
4
,

 
 
2
6
6
,

 
 
2
4
0
,

 
 
2
1
,

 
 
1
,

 
 
8
2
8
,

 
 
2
,

 
 
6
,

 
 
4
5
3
,

 
 
6
9
5
2
,

 
 
1
9
8
,

 
 
6
9
,

 
 
2
2
]
,

 
[
2
2
6
6
,
 
8
,
 
8
6
7
,
 
7
,
 
1
,
 
2
9
9
8
,
 
4
4
0
5
,
 
2
,
 
1
8
9
,
 
6
4
3
7
,
 
1
0
6
2
3
,
 
4
4
,
 
3
9
,
 
2
3
,
 
1
0
8
7
]
,

 
[
5
,
 
1
0
6
,
 
3
3
1
,
 
7
,
 
1
,
 
4
4
0
6
,
 
2
,
 
1
,
 
1
4
6
8
0
,
 
1
8
,
 
9
2
,
 
1
0
4
,
 
7
7
4
,
 
4
,
 
1
,
 
3
2
2
6
]
,

 
[
1
1
,
 
8
,
 
1
9
3
8
,
 
4
,
 
6
9
5
3
,
 
1
1
3
,
 
1
4
2
,
 
1
7
,
 
3
4
,
 
9
3
,
 
2
3
2
,
 
6
9
5
4
,
 
9
3
7
4
,
 
7
,
 
1
0
1
,
 
3
2
8
]
,

 
[
4
2
,

 
 
1
3
2
5
,

 
 
8
2
9
,

 
 
8
7
,

 
 
1
,

 
 
1
2
6
8
,

 
 
7
,

 
 
5
1
,

 
 
1
8
8
7
6
,

 
 
1
,

 
 
6
8
2
,

 
 
2
5
,

 
 
1
6
6
1
,

 
 
3
,

 
 
7
,

 
 
1
0
,

 
 
1
0
1
0
,

 
 
1
3
7
,

 
 
5
0
,

 
 
5
5
9
2
,

 
 
5
9
,

 
 
9
,

 
 
2
,

 
 
3
7
,

 
 
8
6
9
,

 
 
1
8
8
7
7
]
,

 
[
5
,

 
 
1
6
6
2
,

 
 
4
,

 
 
1
,

 
 
4
5
9
,

 
 
1
0
5
,

 
 
1
4
,

 
 
1
2
,

 
 
1
1
8
2
,

 
 
3
,

 
 
3
4
,

 
 
4
5
8
,

 
 
1
,

 
 
2
5
9
7
,

 
 
1
3
,

 
 
5
5
9
3
,

 
 
1
4
6
8
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
,

 
 
7
,

 
 
6
3
7
]
,

 
[
5
,

 
 
3
1
,

 
 
3
3
3
7
,

 
 
2
3
4
9
,

 
 
2
,

 
 
6
,

 
 
1
0
2
,

 
 
9
4
0
,

 
 
5
4
,

 
 
7
2
,

 
 
8
2
,

 
 
5
,

 
 
4
7
3
,

 
 
1
,

 
 
6
3
3
,

 
 
2
1
,

 
 
7
0
,

 
 
2
4
5
7
,

 
 
5
,

 
 
1
4
4
,

 
 
9
,

 
 
5
,

 
 
1
4
3
,

 
 
1
2
2
1
0
,

 
 
2
,

 
 
1
3
0
0
,

 
 
3
,

 
 
9
5
,

 
 
2
0
9
2
,

 
 
1
9
,

 
 
1
7
2
,

 
 
1
8
8
7
8
,

 
 
6
4
,

 
 
7
,

 
 
3
0
,

 
 
2
0
9
3
,

 
 
3
9
8
3
]
,

 
[
4
5
,

 
 
1
2
,

 
 
9
8
,

 
 
4
,

 
 
2
8
,

 
 
3
6
,

 
 
3
8
,

 
 
7
,

 
 
1
,

 
 
4
1
8
4
,

 
 
5
2
9
,

 
 
3
,

 
 
5
,

 
 
1
8
8
4
,

 
 
4
5
,

 
 
4
9
,

 
 
2
8
,

 
 
6
,

 
 
1
1
0
7
,

 
 
4
,

 
 
4
2
1
,

 
 
1
7
9
,

 
 
6
9
,

 
 
1
,

 
 
4
6
4
9
,

 
 
2
,

 
 
6
,

 
 
3
2
5
,

 
 
2
4
5
8
]
,

 
[
6
9
5
5
,

 
 
9
3
7
5
,

 
 
9
4
,

 
 
3
3
,

 
 
2
3
4
,

 
 
2
2
,

 
 
5
9
7
7
,

 
 
6
,

 
 
1
4
6
8
2
,

 
 
3
6
,

 
 
4
0
9
,

 
 
3
6
,

 
 
5
,

 
 
4
1
7
,

 
 
1
1
4
,

 
 
2
8
8
0
,

 
 
3
3
,

 
 
5
6
,

 
 
3
6
,

 
 
4
6
5
0
,

 
 
7
6
7
,

 
 
2
0
]
,

 
[
2
2
1
6
,
 
2
1
3
,
 
1
2
,
 
1
8
8
7
9
,
 
1
5
,
 
3
6
3
7
,
 
3
,
 
5
2
2
3
,
 
1
5
,
 
1
6
5
,
 
3
0
4
]
,

 
[
1
,
 
2
9
3
,
 
3
2
0
,
 
1
,
 
7
0
9
,
 
3
2
4
,
 
1
0
2
5
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
1
4
3
,
 
3
6
,
 
3
3
3
,
 
1
3
5
7
,
 
1
2
2
1
1
]
,

 
[
1
,

 
 
8
1
8
,

 
 
8
4
2
,

 
 
1
,

 
 
9
0
0
,

 
 
1
6
2
1
,

 
 
4
2
8
,

 
 
1
,

 
 
1
2
0
4
,

 
 
1
1
,

 
 
8
,

 
 
5
2
,

 
 
4
2
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
2
6
9
,

 
 
3
2
2
7
,

 
 
1
,

 
 
2
5
9
8
,

 
 
4
3
8
]
,

 
[
1
6
0
,

 
 
1
3
9
,

 
 
7
2
5
,

 
 
7
4
5
,

 
 
5
4
,

 
 
5
1
3
,

 
 
2
3
5
0
,

 
 
3
,

 
 
4
1
,

 
 
1
,

 
 
1
1
2
,

 
 
1
1
7
,

 
 
4
5
,

 
 
2
9
,

 
 
1
1
3
,

 
 
5
8
,

 
 
1
8
8
4
,

 
 
9
,

 
 
1
,

 
 
1
8
4
,

 
 
2
4
3
,

 
 
1
2
,

 
 
4
2
9
,

 
 
1
6
,

 
 
3
2
2
7
,

 
 
1
6
,

 
 
1
1
,

 
 
1
2
,

 
 
1
6
4
]
,

 
[
1
,
 
3
2
9
,
 
1
3
7
4
,
 
2
9
,
 
8
8
1
,
 
1
8
8
8
0
,
 
3
,
 
1
8
6
,
 
1
2
,
 
1
2
2
,
 
1
0
6
2
4
,
 
3
8
,
 
2
2
4
,
 
1
,
 
9
5
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
0
5
,

 
 
2
1
5
,

 
 
3
,

 
 
1
,

 
 
3
0
0
,

 
 
1
5
5
3
,

 
 
3
,

 
 
2
0
9
4
,

 
 
7
6
2
0
,

 
 
7
3
7
,

 
 
2
1
6
,

 
 
6
1
,

 
 
7
5
7
,

 
 
8
8
,

 
 
1
,

 
 
1
0
6
2
5
,

 
 
3
1
1
,

 
 
3
6
5
,

 
 
2
7
0
3
]
,

 
[
4
2
,

 
 
2
9
,

 
 
8
4
3
6
,

 
 
4
,

 
 
5
4
5
,

 
 
1
3
2
6
,

 
 
2
,

 
 
1
,

 
 
2
2
1
7
,

 
 
9
3
6
1
,

 
 
1
4
6
8
3
,

 
 
7
,

 
 
6
9
0
,

 
 
6
4
3
8
,

 
 
6
,

 
 
1
8
8
,

 
 
2
9
,

 
 
7
7
5
,

 
 
1
6
8
,

 
 
4
,

 
 
5
1
,

 
 
1
1
1
,

 
 
8
0
9
,

 
 
1
0
0
,

 
 
1
,

 
 
1
9
9
2
,

 
 
2
,

 
 
8
7
0
,

 
 
4
0
,

 
 
1
3
7
,

 
 
3
1
0
4
,

 
 
5
5
,

 
 
1
3
2
7
,

 
 
9
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

 
 
1
,

 
 
2
9
2
,

 
 
2
9
,

 
 
9
3
7
6
,

 
 
3
,

 
 
7
0
,

 
 
1
5
1
6
,

 
 
2
,

 
 
1
9
9
3
,

 
 
1
0
6
2
6
]
,

 
[
3
4
,

 
 
7
8
1
,

 
 
3
6
,

 
 
1
0
4
,

 
 
2
4
,

 
 
4
1
6
,

 
 
3
,

 
 
1
,

 
 
5
9
7
8
,

 
 
2
,

 
 
1
,

 
 
7
0
9
,

 
 
8
,

 
 
8
6
,

 
 
4
9
0
9
,

 
 
1
8
,

 
 
1
,

 
 
4
1
8
5
,

 
 
4
3
9
,

 
 
7
,

 
 
1
,

 
 
8
4
4
,

 
 
1
6
9
2
,

 
 
8
5
,

 
 
4
,

 
 
1
1
0
8
,

 
 
1
1
9
,

 
 
3
,

 
 
2
3
,

 
 
2
8
5
,

 
 
2
,

 
 
6
9
5
6
,

 
 
3
,

 
 
6
,

 
 
1
5
6
,

 
 
1
2
2
1
2
,

 
 
3
4
,

 
 
7
3
,

 
 
8
8
1
,

 
 
1
1
6
]
,

 
[
5
,

 
 
7
0
1
,

 
 
5
,

 
 
2
9
9
9
,

 
 
6
3
,

 
 
3
2
,

 
 
4
0
5
,

 
 
5
2
,

 
 
5
,

 
 
3
1
,

 
 
5
2
2
4
,

 
 
1
1
0
,

 
 
4
,

 
 
1
3
4
,

 
 
1
3
,

 
 
1
,

 
 
8
3
0
,

 
 
6
4
5
,

 
 
9
,

 
 
6
2
4
,

 
 
1
0
6
2
7
,

 
 
9
5
1
,

 
 
2
2
,

 
 
4
4
0
,

 
 
3
,

 
 
1
0
2
6
,

 
 
3
,

 
 
5
9
1
,

 
 
5
5
9
4
,

 
 
1
7
,

 
 
6
9
1
,

 
 
1
0
6
7
,

 
 
6
5
3
,

 
 
1
0
,

 
 
2
0
8
,

 
 
4
5
,

 
 
2
5
,

 
 
3
6
,

 
 
1
6
2
2
,

 
 
1
7
,

 
 
9
5
2
,

 
 
1
3
,

 
 
3
7
,

 
 
5
4
2
,

 
 
1
3
5
,

 
 
5
,

 
 
9
0
1
,

 
 
4
,

 
 
1
,

 
 
1
8
3
3
,

 
 
2
,

 
 
3
0
,

 
 
2
2
1
8
,

 
 
5
,

 
 
9
2
,

 
 
3
0
,

 
 
6
,

 
 
4
7
2
,

 
 
2
,

 
 
6
9
5
6
,

 
 
3
0
,

 
 
1
0
1
1
,

 
 
8
4
3
7
,

 
 
3
,

 
 
6
,

 
 
1
0
6
2
8
,

 
 
3
1
0
5
,

 
 
3
1
2
,

 
 
2
7
,

 
 
3
0
,

 
 
1
1
6
0
,

 
 
1
6
,

 
 
1
,

 
 
1
2
2
1
3
,

 
 
2
,

 
 
1
3
4
,

 
 
7
9
5
,

 
 
4
,

 
 
1
,

 
 
3
6
3
8
,

 
 
2
,

 
 
1
0
1
2
,

 
 
5
,

 
 
5
3
9
,

 
 
3
0
,

 
 
2
7
,

 
 
1
,

 
 
6
9
5
6
]
,

 
[
1
1
5
,

 
 
1
4
,

 
 
9
8
,

 
 
4
,

 
 
2
8
,

 
 
7
,

 
 
1
,

 
 
1
4
4
3
,

 
 
2
,

 
 
6
,

 
 
1
4
1
,

 
 
3
7
,

 
 
7
9
,

 
 
1
4
1
,

 
 
5
7
7
,

 
 
1
8
,

 
 
1
,

 
 
1
3
0
1
,

 
 
3
,

 
 
1
0
0
8
,

 
 
2
9
,

 
 
2
7
8
8
,

 
 
4
4
0
7
,

 
 
3
,

 
 
1
4
,

 
 
4
6
,

 
 
9
0
,

 
 
2
8
,

 
 
2
1
2
,

 
 
2
,

 
 
1
,

 
 
1
1
6
1
,

 
 
3
5
,

 
 
1
,

 
 
1
6
2
3
,

 
 
3
5
,

 
 
7
5
,

 
 
2
,

 
 
1
,

 
 
1
7
4
,

 
 
2
2
9
,

 
 
2
0
1
,

 
 
1
4
0
9
,

 
 
3
,

 
 
4
7
6
,

 
 
9
8
,

 
 
7
,

 
 
1
9
8
,

 
 
1
6
,

 
 
1
0
2
,

 
 
6
,

 
 
3
2
9
,

 
 
2
,

 
 
1
2
2
1
4
,

 
 
1
6
,

 
 
1
,

 
 
5
0
,

 
 
7
6
2
1
,

 
 
1
2
2
1
5
,

 
 
7
1
7
]
,

 
[
2
6
,

 
 
7
7
6
,

 
 
8
,

 
 
3
4
7
5
,

 
 
2
4
,

 
 
1
6
7
,

 
 
4
,

 
 
8
2
8
,

 
 
7
,

 
 
6
,

 
 
5
9
7
9
,

 
 
8
4
3
8
,

 
 
2
5
3
,

 
 
2
7
0
4
,

 
 
5
2
2
5
,

 
 
6
9
5
7
,

 
 
3
4
7
6
,

 
 
1
4
6
8
4
,

 
 
2
1
7
,

 
 
1
5
,

 
 
2
5
4
,

 
 
8
2
,

 
 
1
,

 
 
1
0
6
8
,

 
 
2
,

 
 
6
,

 
 
3
3
3
9
,

 
 
3
4
7
7
]
,

 
[
1
,

 
 
8
4
3
9
,

 
 
2
2
3
,

 
 
1
0
6
2
9
,

 
 
7
,

 
 
1
,

 
 
5
6
9
,

 
 
3
,

 
 
1
9
9
4
,

 
 
4
,

 
 
6
1
3
,

 
 
1
0
0
,

 
 
1
,

 
 
1
6
9
3
,

 
 
1
8
8
8
1
,

 
 
1
2
2
1
6
,

 
 
3
,

 
 
1
3
,

 
 
3
0
,

 
 
1
4
9
0
,

 
 
3
1
0
6
,

 
 
7
4
,

 
 
2
,

 
 
3
0
,

 
 
7
8
8
,

 
 
3
0
0
0
,

 
 
4
,

 
 
3
,

 
 
2
0
9
5
,

 
 
7
,

 
 
1
,

 
 
8
4
4
,

 
 
1
6
,

 
 
6
0
,

 
 
1
7
5
,

 
 
1
,

 
 
6
6
5
,

 
 
2
,

 
 
2
8
8
1
]
,

 
[
3
,
 
5
3
,
 
6
8
,
 
1
,
 
3
6
5
,
 
2
7
0
3
,
 
4
2
,
 
2
9
,
 
3
2
,
 
4
2
9
]
,

 
[
5
,

 
 
8
4
4
0
,

 
 
5
,

 
 
3
1
0
7
,

 
 
1
7
,

 
 
8
7
1
,

 
 
4
5
,

 
 
4
6
,

 
 
2
8
,

 
 
3
6
,

 
 
3
0
7
,

 
 
2
,

 
 
1
,

 
 
7
2
7
,

 
 
2
,

 
 
1
0
,

 
 
1
8
8
8
2
,

 
 
4
0
9
,

 
 
8
6
,

 
 
1
4
6
8
5
,

 
 
4
0
9
,

 
 
8
6
,

 
 
1
8
8
8
3
,

 
 
2
,

 
 
1
4
7
,

 
 
5
,

 
 
4
1
8
6
,

 
 
2
4
,

 
 
1
,

 
 
2
2
1
9
,

 
 
2
0
9
6
,

 
 
4
,

 
 
1
,

 
 
1
1
4
4
,

 
 
2
,

 
 
1
,

 
 
3
1
0
8
]
,

 
[
1
3
,

 
 
1
0
2
,

 
 
4
9
5
,

 
 
5
,

 
 
1
6
2
4
,

 
 
1
0
,

 
 
2
7
0
,

 
 
3
,

 
 
3
8
1
,

 
 
7
6
2
2
,

 
 
2
1
7
,

 
 
8
,

 
 
2
1
,

 
 
8
3
,

 
 
5
7
5
,

 
 
1
3
,

 
 
1
,

 
 
2
4
9
,

 
 
2
,

 
 
5
5
,

 
 
1
2
7
,

 
 
1
6
9
,

 
 
9
3
7
7
,

 
 
4
0
,

 
 
1
9
3
9
,

 
 
2
0
2
,

 
 
1
,

 
 
2
0
9
3
,

 
 
4
8
0
,

 
 
8
,

 
 
1
,

 
 
6
9
5
8
,

 
 
2
,

 
 
5
2
1
6
,

 
 
3
,

 
 
8
4
4
1
,

 
 
6
8
9
,

 
 
1
6
1
,

 
 
1
9
,

 
 
3
4
,

 
 
2
9
,

 
 
6
9
5
9
]
,

 
[
1
,

 
 
4
0
2
,

 
 
2
8
1
,

 
 
5
,

 
 
4
1
8
7
,

 
 
1
0
,

 
 
1
1
0
9
,

 
 
2
,

 
 
3
4
7
8
,

 
 
3
,

 
 
1
5
8
3
,

 
 
6
,

 
 
6
6
6
,

 
 
4
,

 
 
5
4
,

 
 
2
,

 
 
1
,

 
 
2
4
0
4
,

 
 
4
9
1
0
]
,

 
[
1
8
3
,

 
 
7
3
,

 
 
2
0
8
,

 
 
1
8
7
,

 
 
3
7
,

 
 
2
4
4
,

 
 
1
3
6
,

 
 
1
1
1
0
,

 
 
7
,

 
 
1
6
2
5
,

 
 
3
,

 
 
2
2
1
9
,

 
 
2
7
0
5
,

 
 
1
,

 
 
2
5
9
9
,

 
 
2
,

 
 
6
,

 
 
3
3
4
0
,

 
 
7
,

 
 
4
6
5
1
,

 
 
4
,

 
 
1
,

 
 
4
6
5
2
,

 
 
2
4
1
,

 
 
2
,

 
 
1
4
6
8
6
]
,

 
[
1
2
0
,

 
 
2
6
,

 
 
2
2
6
7
,

 
 
4
1
8
8
,

 
 
1
1
8
,

 
 
3
3
4
1
,

 
 
4
7
,

 
 
7
1
0
,

 
 
2
0
9
7
,

 
 
1
0
6
3
0
,

 
 
2
5
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
8
,

 
 
6
1
4
]
,

 
[
7
,

 
 
6
,

 
 
9
6
8
,

 
 
3
5
,

 
 
1
2
2
,

 
 
1
1
,

 
 
1
2
,

 
 
4
9
1
1
,

 
 
2
2
6
8
,

 
 
3
,

 
 
7
,

 
 
1
,

 
 
2
4
7
,

 
 
2
,

 
 
6
,

 
 
1
5
6
,

 
 
5
2
0
,

 
 
1
1
,

 
 
8
,

 
 
6
5
8
,

 
 
4
1
8
9
,

 
 
1
3
,

 
 
1
,

 
 
4
6
5
3
,

 
 
3
1
1
]
,

 
[
1
,

 
 
1
1
1
1
,

 
 
8
7
2
,

 
 
6
8
,

 
 
5
5
7
,

 
 
1
6
3
,

 
 
2
1
,

 
 
1
,

 
 
8
3
,

 
 
4
4
0
8
,

 
 
8
6
,

 
 
2
,

 
 
6
3
,

 
 
1
5
3
,

 
 
2
9
,

 
 
9
7
,

 
 
1
9
,

 
 
5
,

 
 
1
2
,

 
 
6
9
,

 
 
1
1
1
2
,

 
 
1
8
,

 
 
5
,

 
 
1
0
6
3
1
,

 
 
2
3
,

 
 
1
,

 
 
3
4
1
]
,

 
[
1
8
6
,

 
 
2
8
7
,

 
 
2
1
6
,

 
 
2
7
,

 
 
1
,

 
 
6
3
8
,

 
 
1
4
4
4
,

 
 
1
6
,

 
 
9
,

 
 
1
9
,

 
 
4
9
,

 
 
2
8
,

 
 
4
,

 
 
6
,

 
 
1
0
2
,

 
 
4
9
9
,

 
 
5
2
2
6
,

 
 
1
6
,

 
 
7
,

 
 
3
8
6
,

 
 
2
,

 
 
2
3
4
5
,

 
 
1
,

 
 
4
0
2
,

 
 
7
5
5
,

 
 
4
9
,

 
 
2
8
,

 
 
1
,

 
 
5
2
2
7
,

 
 
2
,

 
 
2
7
0
6
,

 
 
2
3
,

 
 
1
,

 
 
3
4
7
9
]
,

 
[
1
8
,
 
4
6
,
 
2
0
,
 
1
,
 
9
3
7
8
,
 
2
8
,
 
5
2
2
8
,
 
2
3
,
 
5
9
8
0
]
,

 
[
1
0
,

 
 
5
5
9
5
,

 
 
1
7
,

 
 
1
2
7
0
,

 
 
2
5
,

 
 
6
,

 
 
7
1
,

 
 
2
,

 
 
1
4
9
1
,

 
 
8
5
1
,

 
 
3
,

 
 
4
4
0
9
,

 
 
1
4
,

 
 
2
5
,

 
 
3
2
2
8
,

 
 
4
9
1
2
,

 
 
2
,

 
 
1
2
5
0
,

 
 
3
5
,

 
 
2
8
4
,

 
 
4
,

 
 
3
5
9
,

 
 
1
0
,

 
 
2
8
8
2
,

 
 
5
0
,

 
 
1
4
6
8
7
,

 
 
2
,

 
 
9
3
7
9
,

 
 
7
,

 
 
1
5
,

 
 
3
8
1
8
]
,

 
[
1
6
1
,

 
 
5
5
7
,

 
 
4
3
2
,

 
 
3
0
8
,

 
 
9
,

 
 
6
9
2
,

 
 
2
2
0
,

 
 
1
,

 
 
4
8
6
,

 
 
6
2
,

 
 
1
0
6
3
2
,

 
 
1
0
7
6
,

 
 
5
5
9
6
,

 
 
2
7
,

 
 
1
4
6
8
8
,

 
 
3
6
6
,

 
 
2
6
0
0
,

 
 
9
,

 
 
1
3
7
5
,

 
 
7
,

 
 
8
5
,

 
 
1
6
,

 
 
1
8
8
8
4
,

 
 
3
5
,

 
 
1
2
2
1
7
,

 
 
1
2
2
1
8
]
,

 
[
3
3
4
2
,

 
 
6
3
9
,

 
 
1
4
6
7
,

 
 
5
4
6
,

 
 
1
,

 
 
1
4
6
8
9
,

 
 
5
4
6
,

 
 
1
2
2
1
9
,

 
 
1
2
2
2
0
,

 
 
7
,

 
 
7
6
2
3
,

 
 
8
4
4
2
,

 
 
1
3
,

 
 
1
,

 
 
9
5
,

 
 
9
3
8
0
,

 
 
3
5
,

 
 
1
6
,

 
 
6
9
6
0
,

 
 
4
,

 
 
1
,

 
 
2
0
4
,

 
 
7
9
4
,

 
 
2
8
8
3
,

 
 
5
2
9
,

 
 
3
5
,

 
 
2
4
,

 
 
5
9
8
1
,

 
 
5
9
8
2
,

 
 
3
5
,

 
 
5
9
1
,

 
 
3
5
,

 
 
1
4
1
0
,

 
 
1
8
8
8
5
,

 
 
1
8
8
8
6
,

 
 
3
5
,

 
 
8
4
4
3
,

 
 
5
5
9
7
,

 
 
4
2
,

 
 
4
1
9
0
,

 
 
2
3
4
,

 
 
4
,

 
 
1
,

 
 
2
7
1
,

 
 
1
8
,

 
 
2
6
0
1
,

 
 
2
1
6
,

 
 
1
8
8
8
7
,

 
 
4
,

 
 
6
,

 
 
2
6
6
,

 
 
5
4
6
,

 
 
3
7
1
,

 
 
9
,

 
 
4
6
5
4
,

 
 
6
,

 
 
1
6
9
4
,

 
 
6
0
6
,

 
 
3
6
3
9
,

 
 
6
,

 
 
1
0
0
]
,

 
[
1
,
 
4
8
1
,
 
2
9
,
 
2
,
 
1
,
 
5
3
3
,
 
9
0
2
,
 
5
9
8
3
]
,

 
[
9
,
 
2
5
,
 
1
2
3
2
,
 
3
6
4
0
,
 
4
1
7
,
 
2
6
0
2
]
,

 
[
1
2
7
1
,

 
 
2
4
0
,

 
 
8
4
4
4
,

 
 
9
1
3
,

 
 
3
,

 
 
1
4
6
9
0
,

 
 
1
8
8
8
8
,

 
 
4
1
9
1
,

 
 
3
,

 
 
2
0
2
,

 
 
6
3
,

 
 
1
,

 
 
4
6
5
3
,

 
 
8
1
0
,

 
 
2
,

 
 
1
,

 
 
4
4
1
0
,

 
 
3
,

 
 
1
,

 
 
1
0
0
9
,

 
 
3
0
0
1
,

 
 
2
,

 
 
1
,

 
 
1
2
7
2
,

 
 
8
8
2
,

 
 
5
9
7
]
,

 
[
4
,

 
 
2
8
,

 
 
2
2
0
,

 
 
3
9
,

 
 
4
,

 
 
2
8
,

 
 
4
9
7
,

 
 
2
3
,

 
 
3
9
,

 
 
4
,

 
 
2
9
7
,

 
 
3
9
,

 
 
1
1
5
,

 
 
3
0
,

 
 
1
1
1
,

 
 
8
,

 
 
1
,

 
 
3
4
8
0
,

 
 
2
,

 
 
3
0
,

 
 
3
0
0
2
]
,

 
[
1
,

 
 
4
3
8
,

 
 
8
,

 
 
3
8
1
9
,

 
 
3
,

 
 
1
6
,

 
 
5
,

 
 
8
,

 
 
9
6
9
,

 
 
4
,

 
 
4
3
6
,

 
 
5
,

 
 
5
9
8
,

 
 
4
,

 
 
6
6
6
,

 
 
1
,

 
 
4
5
9
,

 
 
1
0
5
,

 
 
1
0
,

 
 
3
6
7
,

 
 
1
5
5
4
,

 
 
1
2
,

 
 
4
3
,

 
 
2
4
5
9
]
,

 
[
5
,
 
1
2
5
,
 
1
4
6
,
 
2
8
,
 
1
1
,
 
4
8
2
,
 
1
7
,
 
4
2
,
 
2
7
8
,
 
2
2
,
 
1
,
 
2
8
7
9
,
 
1
7
,
 
1
1
,
 
2
5
,
 
1
8
8
8
9
]
,

 
[
3
2
,

 
 
9
,

 
 
1
4
,

 
 
7
7
,

 
 
7
1
1
,

 
 
1
0
5
4
,

 
 
5
7
,

 
 
1
,

 
 
2
2
6
9
,

 
 
5
9
8
4
,

 
 
6
9
6
1
,

 
 
1
0
6
3
3
,

 
 
7
6
2
4
,

 
 
3
,

 
 
9
3
8
1
,

 
 
1
,

 
 
7
6
2
5
,

 
 
2
,

 
 
1
0
,

 
 
4
8
0
,

 
 
1
8
,

 
 
2
3
,

 
 
5
4
,

 
 
8
4
4
5
,

 
 
1
,

 
 
5
9
8
5
,

 
 
2
,

 
 
6
7
,

 
 
1
4
7
,

 
 
1
0
6
3
4
,

 
 
2
2
,

 
 
4
,

 
 
2
2
7
0
,

 
 
1
0
,

 
 
1
4
1
1
,

 
 
1
6
9
5
]
,

 
[
1
,

 
 
3
8
2
0
,

 
 
2
6
0
3
,

 
 
2
4
0
5
,

 
 
2
2
,

 
 
4
4
4
,

 
 
3
5
6
,

 
 
2
5
,

 
 
2
8
8
4
,

 
 
1
0
6
3
5
,

 
 
4
,

 
 
3
4
8
1
,

 
 
4
,

 
 
1
,

 
 
9
3
8
2
,

 
 
3
,

 
 
9
,

 
 
9
3
8
2
,

 
 
7
,

 
 
1
0
,

 
 
3
2
1
,

 
 
2
3
5
1
,

 
 
6
,

 
 
3
3
4
0
]
,

 
[
1
,

 
 
9
3
8
3
,

 
 
1
3
2
,

 
 
4
4
,

 
 
7
0
,

 
 
1
4
6
9
1
,

 
 
3
5
,

 
 
6
4
3
9
,

 
 
2
,

 
 
1
5
8
,

 
 
9
3
8
4
,

 
 
1
8
8
9
0
,

 
 
3
5
,

 
 
1
4
6
9
2
,

 
 
1
9
8
,

 
 
8
9
,

 
 
1
6
,

 
 
2
5
,

 
 
4
8
2
,

 
 
7
,

 
 
1
,

 
 
1
8
8
9
1
,

 
 
4
6
5
5
]
,

 
[
6
3
6
,
 
6
6
,
 
1
,
 
5
2
2
9
,
 
3
1
0
9
,
 
1
,
 
3
8
,
 
2
7
,
 
2
6
,
 
3
0
1
,
 
7
7
,
 
1
6
6
3
]
,

 
[
3
,

 
 
3
1
1
0
,

 
 
3
8
2
1
,

 
 
1
6
9
,

 
 
1
,

 
 
3
8
2
2
,

 
 
2
,

 
 
1
,

 
 
1
7
4
,

 
 
1
1
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
6
6
4
,

 
 
7
,

 
 
2
2
2
,

 
 
3
7
4
,

 
 
4
4
,

 
 
1
,

 
 
5
5
8
,

 
 
2
,

 
 
1
,

 
 
1
7
1
,

 
 
2
,

 
 
3
4
8
2
]
,

 
[
5
5
9
8
,

 
 
5
5
2
,

 
 
1
2
,

 
 
2
0
,

 
 
7
4
6
,

 
 
4
4
4
,

 
 
3
9
8
4
,

 
 
2
1
,

 
 
1
,

 
 
1
2
3
3
,

 
 
2
,

 
 
5
5
,

 
 
2
5
1
2
,

 
 
4
8
,

 
 
1
2
,

 
 
1
3
,

 
 
6
9
6
2
,

 
 
1
3
5
8
,

 
 
1
5
1
5
,

 
 
4
7
7
,

 
 
4
,

 
 
1
,

 
 
4
4
2
,

 
 
2
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

 
 
3
4
8
3
]
,

 
[
1
4
,

 
 
1
1
7
,

 
 
8
1
,

 
 
6
,

 
 
1
2
2
2
1
,

 
 
2
4
1
,

 
 
4
,

 
 
1
,

 
 
3
6
7
,

 
 
6
2
1
,

 
 
5
8
,

 
 
1
2
0
6
,

 
 
4
7
7
,

 
 
4
,

 
 
1
5
,

 
 
4
4
2
,

 
 
3
,

 
 
8
2
,

 
 
1
,

 
 
5
9
8
6
,

 
 
2
,

 
 
1
5
,

 
 
1
9
2
,

 
 
1
4
,

 
 
4
1
9
2
,

 
 
3
0
,

 
 
4
,

 
 
2
2
2
0
,

 
 
3
,

 
 
5
3
9
,

 
 
3
0
,

 
 
1
7
5
,

 
 
1
,

 
 
3
3
4
3
,

 
 
2
,

 
 
6
,

 
 
1
6
9
6
]
,

 
[
5
,

 
 
1
2
,

 
 
6
9
9
,

 
 
5
4
,

 
 
4
1
9
3
,

 
 
3
6
4
1
,

 
 
3
,

 
 
3
7
9
,

 
 
5
9
2
,

 
 
3
8
2
1
,

 
 
4
4
1
1
,

 
 
1
0
,

 
 
3
3
6
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
1
,

 
 
3
3
4
,

 
 
3
9
8
5
,

 
 
3
0
,

 
 
3
8
2
3
,

 
 
3
1
1
1
]
,

 
[
1
2
5
1
,

 
 
1
2
,

 
 
5
2
,

 
 
1
2
3
0
,

 
 
6
,

 
 
5
2
7
,

 
 
1
6
6
5
,

 
 
1
0
8
5
,

 
 
3
,

 
 
5
,

 
 
5
9
8
,

 
 
4
,

 
 
4
1
4
,

 
 
2
1
,

 
 
1
2
8
,

 
 
4
4
,

 
 
1
0
,

 
 
1
0
2
7
,

 
 
1
9
2
,

 
 
2
5
2
,

 
 
1
4
6
9
3
,

 
 
1
2
2
2
2
,

 
 
1
7
,

 
 
5
,

 
 
1
8
2
,

 
 
9
,

 
 
1
2
4
,

 
 
2
1
,

 
 
2
6
4
,

 
 
5
,

 
 
9
3
,

 
 
4
2
1
,

 
 
2
2
6
,

 
 
8
1
,

 
 
1
9
9
5
,

 
 
1
2
9
7
]
,

 
[
1
,
 
1
0
3
9
,
 
1
2
,
 
4
7
,
 
1
4
6
9
4
,
 
3
,
 
7
5
,
 
4
7
,
 
4
1
9
4
]
,

 
[
3
6
4
2
,
 
9
8
,
 
2
2
7
1
,
 
4
,
 
2
8
,
 
5
9
2
,
 
5
2
,
 
1
6
,
 
1
5
7
,
 
2
2
7
2
,
 
6
,
 
4
7
0
,
 
2
1
3
]
,

 
[
4
2
,
 
1
0
6
,
 
2
2
3
,
 
7
,
 
6
4
0
,
 
4
0
3
,
 
3
,
 
5
2
2
,
 
1
7
5
,
 
1
,
 
1
7
7
,
 
1
0
8
8
]
,

 
[
1
8
,

 
 
1
0
,

 
 
3
6
8
,

 
 
4
3
7
,

 
 
3
3
,

 
 
5
6
,

 
 
1
8
8
9
2
,

 
 
6
5
,

 
 
7
7
,

 
 
5
,

 
 
2
6
,

 
 
2
5
,

 
 
6
,

 
 
6
1
,

 
 
1
4
6
9
5
,

 
 
1
2
3
4
,

 
 
1
5
3
,

 
 
5
,

 
 
1
2
3
,

 
 
1
2
5
,

 
 
9
,

 
 
1
1
,

 
 
2
5
,

 
 
6
,

 
 
6
1
,

 
 
1
1
6
2
,

 
 
1
2
3
4
,

 
 
2
1
5
4
,

 
 
4
,

 
 
1
,

 
 
3
9
8
6
,

 
 
3
2
2
9
,

 
 
6
8
,

 
 
8
9
,

 
 
2
0
4
9
,

 
 
2
,

 
 
1
2
2
2
3
,

 
 
3
,

 
 
7
8
,

 
 
3
9
8
7
,

 
 
8
4
,

 
 
2
8
,

 
 
1
,

 
 
8
4
4
6
,

 
 
3
9
8
7
,

 
 
7
,

 
 
1
,

 
 
1
5
9
,

 
 
6
0
,

 
 
1
1
,

 
 
6
4
4
0
,

 
 
1
1
]
,

 
[
5
,

 
 
1
4
6
9
6
,

 
 
1
2
2
2
4
,

 
 
4
6
5
6
,

 
 
5
,

 
 
3
8
2
4
,

 
 
1
4
4
,

 
 
5
3
,

 
 
1
4
,

 
 
3
0
0
3
,

 
 
1
8
3
,

 
 
5
3
,

 
 
2
8
8
5
,

 
 
6
,

 
 
1
8
8
9
3
,

 
 
4
,

 
 
3
1
0
5
]
,

 
[
1
4
,

 
 
2
7
3
,

 
 
4
,

 
 
7
9
6
,

 
 
1
3
,

 
 
1
0
1
1
,

 
 
6
4
1
,

 
 
6
4
1
,

 
 
5
,

 
 
1
7
8
3
,

 
 
3
3
,

 
 
3
3
,

 
 
5
6
,

 
 
1
0
,

 
 
1
0
6
3
6
,

 
 
1
0
,

 
 
2
8
8
1
,

 
 
1
0
,

 
 
2
4
6
0
,

 
 
4
0
9
,

 
 
3
6
,

 
 
3
,

 
 
6
5
,

 
 
1
5
,

 
 
2
5
6
,

 
 
6
8
3
,

 
 
3
,

 
 
7
6
2
6
,

 
 
1
5
,

 
 
9
9
,

 
 
2
7
,

 
 
2
2
,

 
 
1
3
,

 
 
3
7
,

 
 
4
8
8
,

 
 
9
,

 
 
4
4
1
2
,

 
 
1
0
1
,

 
 
2
7
0
7
,

 
 
3
,

 
 
3
4
8
4
,

 
 
2
,

 
 
1
0
,

 
 
7
0
2
,

 
 
3
3
,

 
 
5
6
,

 
 
3
5
4
,

 
 
2
,

 
 
3
2
,

 
 
6
7
,

 
 
3
3
,

 
 
5
6
,

 
 
1
0
,

 
 
1
5
8
,

 
 
1
0
,

 
 
6
4
,

 
 
3
8
,

 
 
1
0
,

 
 
9
1
]
,

 
[
5
,

 
 
4
4
1
3
,

 
 
1
6
,

 
 
5
,

 
 
1
1
8
3
,

 
 
2
3
9
,

 
 
5
,

 
 
7
3
,

 
 
2
0
,

 
 
7
9
7
,

 
 
1
,

 
 
1
5
8
,

 
 
3
,

 
 
4
9
,

 
 
3
1
,

 
 
2
1
6
,

 
 
1
1
9
,

 
 
1
2
,

 
 
5
,

 
 
7
0
1
]
,

 
[
1
,

 
 
1
2
6
6
,

 
 
4
9
1
3
,

 
 
2
,

 
 
9
5
3
,

 
 
5
6
,

 
 
2
0
,

 
 
1
6
6
1
,

 
 
4
,

 
 
8
5
2
,

 
 
1
8
,

 
 
7
,

 
 
1
0
,

 
 
3
8
6
,

 
 
4
5
,

 
 
8
,

 
 
2
2
6
,

 
 
1
2
2
2
5
,

 
 
3
,

 
 
5
0
,

 
 
7
6
2
7
,

 
 
7
,

 
 
1
,

 
 
4
4
1
4
]
,

 
[
1
6
,

 
 
1
,

 
 
7
6
2
8
,

 
 
3
,

 
 
1
5
,

 
 
4
9
1
4
,

 
 
2
7
6
,

 
 
1
7
9
,

 
 
2
4
,

 
 
1
,

 
 
4
4
1
5
,

 
 
1
4
6
8
,

 
 
2
,

 
 
1
,

 
 
1
0
6
3
7
,

 
 
1
,

 
 
2
5
4
,

 
 
2
,

 
 
3
8
2
5
,

 
 
1
1
6
3
,

 
 
5
9
8
7
,

 
 
2
2
3
,

 
 
8
8
,

 
 
1
,

 
 
3
7
3
]
,

 
[
1
6
,

 
 
5
,

 
 
3
1
,

 
 
7
7
,

 
 
1
1
,

 
 
9
1
4
,

 
 
4
1
,

 
 
3
4
,

 
 
2
9
,

 
 
7
,

 
 
1
,

 
 
1
8
8
5
,

 
 
1
3
2
8
,

 
 
1
0
5
,

 
 
3
8
9
,

 
 
1
2
,

 
 
3
3
7
,

 
 
9
2
,

 
 
1
5
0
,

 
 
5
9
8
8
,

 
 
8
8
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
0
8
,

 
 
2
7
,

 
 
1
,

 
 
1
7
2
,

 
 
2
,

 
 
1
3
4
,

 
 
3
,

 
 
1
,

 
 
2
4
6
1
,

 
 
2
,

 
 
1
8
8
9
4
,

 
 
1
1
,

 
 
1
4
6
9
7
]
,

 
[
8
1
9
,

 
 
3
3
8
,

 
 
8
,

 
 
1
3
,

 
 
3
9
,

 
 
7
,

 
 
1
5
,

 
 
6
9
6
3
,

 
 
4
8
,

 
 
1
0
7
,

 
 
1
,

 
 
1
0
6
3
8
,

 
 
9
,

 
 
7
9
5
,

 
 
4
,

 
 
2
6
,

 
 
9
0
3
,

 
 
4
9
1
5
,

 
 
4
8
,

 
 
9
8
0
,

 
 
1
5
,

 
 
1
2
0
7
,

 
 
3
6
0
,

 
 
1
5
,

 
 
1
1
4
5
,

 
 
1
2
2
2
6
,

 
 
1
2
8
,

 
 
4
8
,

 
 
1
2
,

 
 
1
7
0
,

 
 
1
5
,

 
 
4
1
8
,

 
 
2
8
8
6
,

 
 
1
2
,

 
 
3
6
4
3
,

 
 
8
4
2
,

 
 
4
,

 
 
2
6
0
4
,

 
 
2
0
1
,

 
 
4
8
,

 
 
1
2
,

 
 
5
5
6
,

 
 
1
,

 
 
1
0
8
6
,

 
 
4
9
1
6
,

 
 
1
9
,

 
 
3
3
4
4
,

 
 
1
1
4
6
,

 
 
1
2
,

 
 
6
8
1
,

 
 
4
,

 
 
3
4
8
5
,

 
 
7
,

 
 
1
5
,

 
 
3
1
1
,

 
 
1
8
,

 
 
1
9
,

 
 
1
1
4
6
,

 
 
8
,

 
 
9
6
9
,

 
 
4
,

 
 
6
4
4
1
]
,

 
[
5
,

 
 
6
4
4
2
,

 
 
6
6
,

 
 
1
0
,

 
 
3
4
8
6
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

 
 
2
7
8
9
,

 
 
5
,

 
 
1
2
,

 
 
2
2
2
1
,

 
 
7
6
2
9
,

 
 
4
,

 
 
8
4
4
7
,

 
 
1
0
,

 
 
1
9
4
1
,

 
 
7
,

 
 
5
4
,

 
 
1
5
5
5
,

 
 
6
4
4
3
,

 
 
7
,

 
 
1
,

 
 
2
2
7
3
,

 
 
1
2
2
2
7
,

 
 
2
,

 
 
5
2
3
0
]
,

 
[
1
,
 
9
0
4
,
 
2
,
 
1
0
,
 
1
9
2
,
 
1
2
3
,
 
2
8
,
 
1
4
6
9
8
,
 
6
6
,
 
7
,
 
6
,
 
1
5
6
,
 
1
6
3
]
,

 
[
6
,
 
1
9
9
5
,
 
2
6
3
,
 
1
6
9
,
 
1
,
 
6
5
4
,
 
1
2
,
 
6
,
 
2
6
0
5
,
 
2
7
,
 
3
9
,
 
3
,
 
8
,
 
1
6
9
7
,
 
3
9
]
,

 
[
5
,
 
3
2
6
,
 
5
,
 
1
4
0
,
 
2
8
,
 
9
0
3
,
 
4
,
 
4
1
4
,
 
6
3
,
 
2
8
8
,
 
7
4
]
,

 
[
3
7
2
,

 
 
1
5
1
7
,

 
 
5
3
,

 
 
9
,

 
 
1
5
9
,

 
 
1
1
8
,

 
 
3
1
,

 
 
4
3
,

 
 
3
5
,

 
 
1
0
5
,

 
 
1
4
,

 
 
1
2
9
,

 
 
3
1
1
2
,

 
 
1
,

 
 
3
3
4
5
,

 
 
1
5
1
8
,

 
 
9
,

 
 
1
8
8
9
5
,

 
 
3
,

 
 
1
4
6
9
9
,

 
 
3
,

 
 
4
6
5
7
,

 
 
8
8
,

 
 
1
1
,

 
 
1
8
,

 
 
7
5
8
,

 
 
1
,

 
 
5
9
8
9
,

 
 
1
0
8
9
,

 
 
2
,

 
 
1
5
,

 
 
1
8
3
4
,

 
 
3
8
,

 
 
1
4
6
,

 
 
8
,

 
 
7
9
8
]
,

 
[
7
6
,

 
 
3
2
,

 
 
6
7
,

 
 
4
4
1
6
,

 
 
3
1
,

 
 
4
3
,

 
 
3
9
0
,

 
 
5
,

 
 
4
6
5
8
,

 
 
1
7
8
4
,

 
 
6
2
,

 
 
2
8
,

 
 
3
9
0
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

 
 
2
,

 
 
7
5
9
,

 
 
1
8
3
5
,

 
 
4
,

 
 
1
,

 
 
1
2
2
2
8
,

 
 
2
,

 
 
1
,

 
 
1
2
2
2
9
]
,

 
[
1
0
,
 
2
7
9
0
,
 
8
,
 
1
8
8
9
6
,
 
2
3
,
 
1
,
 
2
9
3
,
 
1
0
,
 
7
5
5
,
 
8
,
 
1
4
6
5
,
 
1
3
,
 
1
9
9
6
,
 
2
8
6
]
,

 
[
1
1
,

 
 
8
,

 
 
7
,

 
 
6
7
,

 
 
9
3
8
5
,

 
 
4
6
5
,

 
 
7
7
7
,

 
 
2
6
5
,

 
 
9
,

 
 
5
,

 
 
4
9
,

 
 
2
3
2
,

 
 
1
,

 
 
7
9
,

 
 
5
9
9
0
,

 
 
3
9
8
8
,

 
 
1
8
,

 
 
4
2
,

 
 
2
9
,

 
 
3
2
,

 
 
1
0
9
,

 
 
1
4
6
4
]
,

 
[
5
,
 
3
2
6
,
 
5
3
0
,
 
3
3
,
 
3
1
,
 
7
0
3
,
 
4
,
 
1
5
8
7
,
 
1
7
,
 
7
8
,
 
6
9
6
4
,
 
3
,
 
2
7
1
]
,

 
[
5
,

 
 
1
1
4
7
,

 
 
9
4
1
,

 
 
3
,

 
 
1
1
8
4
,

 
 
4
9
1
7
,

 
 
6
9
,

 
 
3
3
,

 
 
1
9
3
6
,

 
 
1
0
,

 
 
1
3
4
,

 
 
7
6
3
0
,

 
 
2
8
,

 
 
4
1
5
,

 
 
9
,

 
 
3
3
,

 
 
5
6
,

 
 
7
7
1
,

 
 
1
7
8
5
]
,

 
[
6
4
,

 
 
1
5
,

 
 
9
9
,

 
 
4
6
5
9
,

 
 
1
6
5
,

 
 
3
,

 
 
4
2
,

 
 
5
5
9
9
,

 
 
1
3
,

 
 
6
,

 
 
1
8
8
9
7
,

 
 
1
0
6
3
9
,

 
 
1
8
8
9
8
,

 
 
1
9
,

 
 
3
2
4
,

 
 
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
7
,

 
 
6
3
,

 
 
8
4
4
8
,

 
 
3
,

 
 
7
6
3
1
]
,

 
[
1
4
,

 
 
8
2
0
,

 
 
4
,

 
 
4
9
1
8
,

 
 
3
,

 
 
1
2
2
3
0
,

 
 
3
2
,

 
 
2
,

 
 
1
2
5
0
,

 
 
2
8
6
,

 
 
3
,

 
 
1
0
6
4
0
,

 
 
1
9
,

 
 
8
0
,

 
 
3
1
,

 
 
4
9
1
9
,

 
 
2
4
,

 
 
6
,

 
 
1
0
9
,

 
 
4
4
1
7
,

 
 
5
7
,

 
 
1
,

 
 
1
9
7
,

 
 
1
4
8
,

 
 
2
,

 
 
1
5
,

 
 
4
6
6
0
]
,

 
[
4
5
,
 
8
,
 
3
6
,
 
5
2
3
1
,
 
2
,
 
1
,
 
7
6
3
2
,
 
6
6
,
 
2
,
 
2
6
,
 
6
3
3
]
,

 
[
6
4
4
4
,

 
 
1
,

 
 
1
8
8
9
9
,

 
 
5
4
0
,

 
 
6
,

 
 
5
9
9
1
,

 
 
1
3
,

 
 
1
,

 
 
5
2
1
4
,

 
 
5
8
,

 
 
2
6
0
6
,

 
 
1
0
2
,

 
 
1
4
7
0
0
,

 
 
2
,

 
 
1
7
8
6
,

 
 
4
,

 
 
2
8
,

 
 
3
1
0
,

 
 
4
,

 
 
1
,

 
 
2
4
0
6
,

 
 
3
,

 
 
1
8
9
0
0
,

 
 
3
,

 
 
6
9
6
5
,

 
 
1
3
6
,

 
 
5
2
3
2
,

 
 
4
0
5
,

 
 
6
,

 
 
7
9
9
,

 
 
8
0
,

 
 
2
8
,

 
 
4
4
5
]
,

 
[
4
2
,

 
 
1
2
,

 
 
5
2
3
,

 
 
4
1
9
5
,

 
 
9
,

 
 
6
0
,

 
 
5
,

 
 
2
9
,

 
 
1
1
5
,

 
 
3
1
0
,

 
 
5
,

 
 
9
3
,

 
 
2
8
,

 
 
2
7
4
,

 
 
4
,

 
 
1
,

 
 
2
2
7
4
,

 
 
3
,

 
 
1
5
,

 
 
1
8
9
0
1
,

 
 
9
2
,

 
 
6
3
,

 
 
1
6
9
8
,

 
 
6
,

 
 
1
3
5
5
,

 
 
1
9
,

 
 
4
2
,

 
 
7
7
8
,

 
 
5
1
5
,

 
 
7
6
3
3
,

 
 
1
0
,

 
 
1
4
1
2
]
,

 
[
6
5
,

 
 
1
,

 
 
3
1
1
3
,

 
 
1
2
2
3
1
,

 
 
3
9
8
9
,

 
 
9
,

 
 
3
6
,

 
 
3
8
,

 
 
1
2
,

 
 
1
7
0
,

 
 
1
,

 
 
7
9
,

 
 
7
1
,

 
 
3
5
,

 
 
1
5
,

 
 
5
5
3
,

 
 
2
0
1
,

 
 
1
,

 
 
1
0
3
,

 
 
1
,

 
 
2
6
0
7
,

 
 
2
9
,

 
 
1
7
9
]
,

 
[
6
0
7
,

 
 
1
4
8
,

 
 
1
2
,

 
 
2
4
0
7
,

 
 
2
2
1
,

 
 
7
,

 
 
6
,

 
 
3
5
2
,

 
 
1
8
,

 
 
1
7
,

 
 
3
8
,

 
 
1
0
6
4
1
,

 
 
9
5
4
,

 
 
3
,

 
 
5
,

 
 
3
1
2
,

 
 
7
,

 
 
1
,

 
 
1
7
7
,

 
 
1
4
9
,

 
 
1
0
5
,

 
 
5
,

 
 
1
2
,

 
 
1
5
1
,

 
 
4
9
2
0
,

 
 
1
0
,

 
 
2
1
1
,

 
 
6
9
,

 
 
1
0
,

 
 
9
7
0
,

 
 
1
7
,

 
 
4
1
9
6
]
,

 
[
1
8
,
 
9
,
 
1
8
9
0
2
,
 
1
2
2
3
2
,
 
2
9
,
 
1
4
1
3
,
 
2
5
,
 
1
1
6
,
 
2
5
7
]
,

 
[
3
,

 
 
1
6
,

 
 
5
,

 
 
2
1
6
,

 
 
5
,

 
 
5
5
6
,

 
 
1
,

 
 
1
6
7
,

 
 
8
7
3
,

 
 
1
,

 
 
2
5
3
,

 
 
3
8
2
6
,

 
 
3
,

 
 
2
6
2
,

 
 
2
6
0
8
,

 
 
9
9
,

 
 
2
4
8
,

 
 
7
,

 
 
4
6
1
,

 
 
3
,

 
 
1
,

 
 
1
0
0
9
,

 
 
3
4
8
7
,

 
 
4
8
1
,

 
 
1
8
8
,

 
 
1
6
,

 
 
6
0
,

 
 
1
7
,

 
 
6
,

 
 
1
8
8
6
,

 
 
1
3
2
,

 
 
8
5
3
,

 
 
4
,

 
 
2
8
,

 
 
1
3
2
9
]
,

 
[
3
,
 
2
4
,
 
5
1
,
 
2
4
5
,
 
5
2
3
3
,
 
3
8
,
 
2
3
,
 
3
8
,
 
1
8
8
7
,
 
4
1
9
7
,
 
1
0
6
4
2
]
,

 
[
5
,

 
 
1
2
,

 
 
5
2
,

 
 
8
0
3
,

 
 
1
1
3
,

 
 
3
0
8
,

 
 
7
,

 
 
4
1
8
,

 
 
3
,

 
 
3
6
4
4
,

 
 
2
6
0
9
,

 
 
1
1
,

 
 
8
,

 
 
3
8
7
,

 
 
2
1
5
5
,

 
 
9
5
5
,

 
 
3
2
,

 
 
8
,

 
 
2
1
,

 
 
8
0
0
,

 
 
7
,

 
 
1
,

 
 
1
4
1
,

 
 
3
,

 
 
1
,

 
 
4
5
3
,

 
 
2
0
3
,

 
 
9
,

 
 
4
9
2
1
,

 
 
7
,

 
 
2
1
,

 
 
1
0
,

 
 
3
6
5
,

 
 
7
3
,

 
 
2
0
,

 
 
1
4
7
0
1
,

 
 
1
,

 
 
1
0
4
0
,

 
 
2
,

 
 
1
,

 
 
1
4
7
0
2
,

 
 
6
9
6
6
,

 
 
9
,

 
 
3
4
8
7
,

 
 
1
1
]
,

 
[
1
3
,

 
 
1
,

 
 
1
2
2
3
3
,

 
 
1
4
7
0
3
,

 
 
6
6
7
,

 
 
2
,

 
 
1
,

 
 
2
1
8
,

 
 
7
6
0
,

 
 
5
,

 
 
8
7
2
,

 
 
1
1
4
,

 
 
1
5
7
,

 
 
3
7
,

 
 
3
6
4
5
,

 
 
1
2
2
3
4
,

 
 
6
8
1
,

 
 
2
2
,

 
 
4
,

 
 
2
7
8
,

 
 
3
6
,

 
 
3
8
,

 
 
2
,

 
 
1
0
,

 
 
1
2
9
7
,

 
 
3
5
,

 
 
1
0
,

 
 
3
4
8
8
]
,

 
[
1
4
,

 
 
7
3
,

 
 
2
0
,

 
 
1
5
0
,

 
 
6
1
4
,

 
 
6
7
,

 
 
1
6
3
,

 
 
3
5
,

 
 
1
4
4
,

 
 
2
3
9
,

 
 
2
1
2
,

 
 
1
4
2
,

 
 
9
2
,

 
 
3
9
,

 
 
2
9
7
,

 
 
2
1
2
,

 
 
1
7
3
2
,

 
 
1
8
,

 
 
1
0
5
5
,

 
 
9
,

 
 
5
4
,

 
 
1
0
6
4
3
,

 
 
3
5
2
,

 
 
8
4
,

 
 
2
8
,

 
 
6
9
6
7
]
,

 
[
2
5
9
,
 
5
,
 
1
9
4
2
,
 
1
7
,
 
5
0
,
 
5
9
,
 
1
2
2
,
 
1
4
8
,
 
5
,
 
3
1
,
 
9
0
,
 
1
7
3
3
,
 
3
8
,
 
1
9
9
,
 
6
6
8
,
 
2
4
,
 
1
2
0
8
]
,

 
[
1
1
,

 
 
2
5
,

 
 
1
5
3
,

 
 
1
4
7
0
4
,

 
 
9
,

 
 
1
0
1
,

 
 
8
9
,

 
 
1
6
9
9
,

 
 
3
9
0
,

 
 
1
,

 
 
2
0
3
,

 
 
8
4
,

 
 
7
,

 
 
1
,

 
 
2
4
4
,

 
 
3
4
8
9
,

 
 
1
0
1
,

 
 
9
8
1
,

 
 
1
4
6
,

 
 
9
,

 
 
3
9
9
0
,

 
 
1
6
1
,

 
 
1
,

 
 
1
1
3
0
,

 
 
3
,

 
 
1
,

 
 
1
2
7
,

 
 
2
,

 
 
1
8
8
8
,

 
 
1
2
7
3
,

 
 
1
,

 
 
1
2
7
,

 
 
2
3
0
,

 
 
3
4
,

 
 
3
1
,

 
 
1
0
6
9
,

 
 
8
0
,

 
 
9
5
4
,

 
 
1
,

 
 
9
6
7
,

 
 
7
6
3
4
,

 
 
2
,

 
 
1
,

 
 
1
6
9
9
,

 
 
9
5
4
,

 
 
6
3
,

 
 
1
8
2
7
,

 
 
3
,

 
 
3
6
4
6
,

 
 
7
,

 
 
5
1
,

 
 
6
9
6
8
,

 
 
4
4
,

 
 
3
2
,

 
 
8
4
4
9
,

 
 
2
,

 
 
3
7
,

 
 
2
6
1
,

 
 
1
8
2
7
,

 
 
3
,

 
 
3
6
4
6
,

 
 
1
7
,

 
 
1
2
9
,

 
 
7
,

 
 
5
1
,

 
 
6
4
4
5
,

 
 
2
,

 
 
7
9
,

 
 
8
8
3
,

 
 
3
5
,

 
 
7
,

 
 
9
5
,

 
 
1
6
3
,

 
 
7
,

 
 
5
1
,

 
 
1
2
7
4
,

 
 
2
,

 
 
1
8
4
,

 
 
2
5
0
,

 
 
1
4
,

 
 
9
6
,

 
 
6
3
,

 
 
1
1
1
3
,

 
 
1
4
7
0
5
,

 
 
2
1
,

 
 
1
5
1
,

 
 
1
6
8
,

 
 
2
4
,

 
 
1
,

 
 
2
6
1
0
,

 
 
2
,

 
 
1
,

 
 
1
8
9
0
3
]
,

 
[
1
4
1
4
,
 
8
,
 
2
8
9
,
 
2
7
,
 
1
7
,
 
3
0
,
 
3
1
1
4
]
,

 
[
1
5
,

 
 
5
9
9
2
,

 
 
5
9
3
,

 
 
1
0
6
4
4
,

 
 
7
7
3
,

 
 
7
2
8
,

 
 
4
,

 
 
1
8
3
6
,

 
 
9
1
,

 
 
4
6
6
1
,

 
 
1
8
,

 
 
6
9
,

 
 
1
0
9
,

 
 
1
8
9
0
4
,

 
 
1
4
3
,

 
 
2
,

 
 
1
5
,

 
 
1
8
9
0
5
,

 
 
7
,

 
 
4
6
6
2
,

 
 
2
4
,

 
 
1
8
4
,

 
 
2
6
1
1
,

 
 
1
5
1
9
,

 
 
1
0
5
,

 
 
1
4
,

 
 
1
2
,

 
 
9
2
4
,

 
 
3
7
,

 
 
1
8
9
0
6
,

 
 
7
,

 
 
8
6
9
]
,

 
[
1
4
,

 
 
1
2
,

 
 
6
,

 
 
6
4
2
,

 
 
1
6
7
,

 
 
5
9
9
3
,

 
 
4
4
1
8
,

 
 
7
0
4
,

 
 
9
9
,

 
 
9
,

 
 
9
8
,

 
 
9
0
,

 
 
4
,

 
 
1
0
6
4
5
,

 
 
6
,

 
 
3
1
1
5
,

 
 
1
0
2
4
,

 
 
6
,

 
 
1
0
6
4
6
,

 
 
1
7
3
4
,

 
 
3
,

 
 
3
4
9
0
,

 
 
3
,

 
 
2
0
4
8
,

 
 
1
4
7
0
6
,

 
 
6
6
7
]
,

 
[
1
1
,

 
 
6
2
,

 
 
2
8
,

 
 
8
2
1
,

 
 
9
,

 
 
7
,

 
 
1
,

 
 
3
3
4
6
,

 
 
1
6
2
6
,

 
 
2
,

 
 
1
0
,

 
 
3
6
4
7
,

 
 
4
4
,

 
 
1
,

 
 
2
4
6
1
,

 
 
2
,

 
 
6
,

 
 
7
4
7
,

 
 
4
,

 
 
1
,

 
 
2
9
1
,

 
 
1
,

 
 
4
6
2
,

 
 
7
,

 
 
4
7
,

 
 
1
8
8
9
,

 
 
2
,

 
 
3
7
,

 
 
7
0
9
,

 
 
2
3
5
2
,

 
 
7
,

 
 
1
3
7
6
,

 
 
4
,

 
 
1
,

 
 
2
5
1
3
,

 
 
2
,

 
 
1
,

 
 
2
8
8
7
,

 
 
1
2
,

 
 
3
1
5
,

 
 
3
3
4
7
,

 
 
5
7
,

 
 
1
0
,

 
 
5
9
9
4
,

 
 
2
6
,

 
 
1
3
2
,

 
 
7
,

 
 
1
4
9
2
,

 
 
2
,

 
 
1
1
3
,

 
 
2
5
0
8
,

 
 
4
,

 
 
1
,

 
 
2
2
2
2
,

 
 
3
,

 
 
1
1
,

 
 
1
2
3
,

 
 
2
8
,

 
 
8
8
8
,

 
 
7
,

 
 
1
4
9
2
,

 
 
2
,

 
 
6
,

 
 
3
2
5
,

 
 
8
4
5
0
,

 
 
7
,

 
 
1
,

 
 
4
6
2
,

 
 
2
,

 
 
7
0
,

 
 
6
9
6
9
,

 
 
7
0
9
,

 
 
2
1
,

 
 
3
2
]
,

 
[
1
0
,
 
1
6
3
,
 
2
8
8
8
,
 
1
4
7
0
7
,
 
1
0
,
 
3
0
0
4
,
 
8
,
 
1
4
6
5
,
 
3
,
 
1
3
0
2
]
,

 
[
6
4
,

 
 
6
,

 
 
6
1
,

 
 
1
4
4
5
,

 
 
7
6
3
5
,

 
 
2
,

 
 
2
4
7
,

 
 
4
6
,

 
 
6
5
9
,

 
 
6
8
,

 
 
8
9
,

 
 
3
8
5
,

 
 
3
,

 
 
5
9
9
5
,

 
 
1
0
6
4
7
,

 
 
1
8
3
3
,

 
 
7
,

 
 
6
,

 
 
5
7
8
,

 
 
9
8
1
,

 
 
8
2
,

 
 
3
4
7
1
,

 
 
1
8
3
3
,

 
 
7
6
3
6
,

 
 
1
0
6
4
8
,

 
 
1
8
9
0
7
,

 
 
1
6
,

 
 
1
4
7
0
8
,

 
 
1
6
,

 
 
1
,

 
 
9
5
6
,

 
 
2
,

 
 
1
,

 
 
1
2
3
4
,

 
 
1
8
,

 
 
6
5
,

 
 
7
5
,

 
 
2
6
,

 
 
1
0
8
5
,

 
 
8
,

 
 
3
6
,

 
 
5
0
,

 
 
5
9
8
9
,

 
 
3
,

 
 
4
1
9
8
,

 
 
2
,

 
 
5
9
,

 
 
1
,

 
 
5
8
6
,

 
 
8
0
1
,

 
 
2
,

 
 
1
,

 
 
3
8
2
7
,

 
 
1
6
,

 
 
6
,

 
 
1
6
5
]
,

 
[
1
6
,

 
 
5
,

 
 
1
0
7
7
,

 
 
2
4
,

 
 
9
,

 
 
1
5
2
0
,

 
 
8
0
5
,

 
 
4
6
5
,

 
 
1
,

 
 
1
8
9
0
8
,

 
 
1
1
4
8
,

 
 
5
,

 
 
1
4
3
,

 
 
6
,

 
 
1
8
4
,

 
 
2
8
2
,

 
 
5
9
9
,

 
 
7
6
,

 
 
2
3
5
3
,

 
 
7
0
,

 
 
5
,

 
 
1
2
,

 
 
1
4
3
,

 
 
6
9
,

 
 
2
1
,

 
 
4
4
1
9
]
,

 
[
1
4
,

 
 
7
3
,

 
 
2
0
,

 
 
1
0
4
1
,

 
 
4
,

 
 
1
4
7
0
9
,

 
 
8
2
,

 
 
1
,

 
 
8
3
,

 
 
2
5
1
4
,

 
 
1
9
3
7
,

 
 
1
7
,

 
 
1
,

 
 
8
4
5
1
,

 
 
1
2
,

 
 
3
1
0
,

 
 
2
2
6
,

 
 
7
4
,

 
 
2
,

 
 
1
5
,

 
 
2
1
9
]
,

 
[
6
,

 
 
8
5
4
,

 
 
1
2
8
,

 
 
3
9
9
1
,

 
 
4
,

 
 
9
3
8
6
,

 
 
2
4
,

 
 
5
9
9
6
,

 
 
4
,

 
 
3
8
2
8
,

 
 
8
,

 
 
1
1
6
4
,

 
 
2
3
,

 
 
1
,

 
 
1
3
3
0
,

 
 
3
,

 
 
1
8
3
7
,

 
 
1
1
9
,

 
 
1
0
0
,

 
 
1
4
,

 
 
3
9
9
2
,

 
 
6
4
4
6
,

 
 
4
0
,

 
 
1
6
,

 
 
4
,

 
 
2
8
,

 
 
1
4
3
,

 
 
2
7
,

 
 
7
4
8
]
,

 
[
1
4
,
 
4
6
6
3
,
 
3
0
,
 
1
4
7
1
0
,
 
3
,
 
2
2
1
,
 
6
,
 
4
7
1
,
 
7
,
 
5
6
0
0
,
 
7
,
 
5
2
3
4
]
,

 
[
1
4
,
 
8
4
5
2
,
 
4
,
 
1
5
,
 
3
8
7
,
 
9
1
,
 
1
5
,
 
1
4
7
1
1
,
 
7
,
 
1
2
3
5
,
 
1
5
,
 
2
7
0
8
,
 
2
1
,
 
3
0
2
]
,

 
[
4
9
2
2
,
 
4
1
7
7
,
 
1
1
,
 
7
,
 
4
9
,
 
2
0
,
 
3
1
,
 
8
8
9
,
 
4
,
 
7
6
3
7
,
 
6
,
 
9
2
5
]
,

 
[
8
2
,

 
 
1
8
6
,

 
 
4
4
9
,

 
 
3
,

 
 
3
2
3
0
,

 
 
3
6
0
,

 
 
5
,

 
 
9
8
,

 
 
1
5
8
8
,

 
 
8
8
4
,

 
 
1
0
,

 
 
1
9
2
,

 
 
1
2
5
2
,

 
 
1
3
,

 
 
6
,

 
 
3
1
1
6
,

 
 
2
0
9
,

 
 
1
7
0
0
]
,

 
[
5
,

 
 
2
5
9
,

 
 
2
7
,

 
 
1
,

 
 
3
2
1
,

 
 
1
9
,

 
 
4
6
6
4
,

 
 
1
,

 
 
2
2
2
3
,

 
 
5
,

 
 
2
4
2
,

 
 
2
7
,

 
 
1
,

 
 
1
3
5
,

 
 
7
,

 
 
1
9
,

 
 
1
,

 
 
4
8
0
,

 
 
2
,

 
 
1
1
,

 
 
8
,

 
 
1
5
2
1
,

 
 
3
,

 
 
1
0
9
,

 
 
1
7
,

 
 
1
,

 
 
1
9
9
,

 
 
4
1
,

 
 
6
7
,

 
 
3
2
1
,

 
 
6
2
,

 
 
8
7
4
,

 
 
1
0
,

 
 
9
9
,

 
 
4
1
,

 
 
9
,

 
 
4
8
0
,

 
 
6
2
,

 
 
3
8
2
9
,

 
 
1
0
,

 
 
3
3
6
,

 
 
3
6
,

 
 
5
0
]
,

 
[
6
0
6
,

 
 
2
4
0
8
,

 
 
2
9
,

 
 
2
9
9
4
,

 
 
4
,

 
 
2
2
,

 
 
7
,

 
 
1
,

 
 
8
4
5
3
,

 
 
1
0
1
3
,

 
 
9
,

 
 
3
1
1
7
,

 
 
8
7
,

 
 
1
,

 
 
2
2
7
,

 
 
3
,

 
 
1
0
,

 
 
6
4
,

 
 
8
9
0
,

 
 
8
,

 
 
3
6
4
8
,

 
 
2
4
,

 
 
1
,

 
 
1
9
9
7
,

 
 
5
,

 
 
9
2
,

 
 
4
,

 
 
1
5
8
9
,

 
 
1
,

 
 
1
1
6
5
]
,

 
[
7
,

 
 
5
4
7
,

 
 
4
,

 
 
7
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

 
 
1
4
,

 
 
4
9
,

 
 
1
0
6
4
9
,

 
 
8
8
,

 
 
1
9
4
3
,

 
 
2
,

 
 
9
3
8
7
,

 
 
1
0
2
8
,

 
 
1
0
1
,

 
 
4
6
6
5
,

 
 
9
,

 
 
3
1
2
,

 
 
7
,

 
 
1
5
,

 
 
1
6
6
]
,

 
[
6
9
7
0
,

 
 
1
8
9
0
9
,

 
 
1
8
9
1
0
,

 
 
5
9
9
7
,

 
 
9
,

 
 
1
4
,

 
 
1
0
8
,

 
 
4
3
,

 
 
7
,

 
 
1
,

 
 
1
9
9
8
,

 
 
2
,

 
 
1
0
6
5
0
,

 
 
2
1
8
,

 
 
1
0
6
1
3
,

 
 
2
,

 
 
6
4
4
7
,

 
 
3
,

 
 
5
9
6
7
,

 
 
4
,

 
 
7
2
9
,

 
 
3
2
3
1
,

 
 
1
7
,

 
 
2
9
6
,

 
 
4
3
2
,

 
 
1
4
8
]
,

 
[
5
,
 
1
0
6
,
 
1
2
2
3
5
,
 
1
0
,
 
4
4
2
0
]
,

 
[
5
,

 
 
5
9
8
,

 
 
4
,

 
 
1
3
2
5
,

 
 
1
3
7
,

 
 
2
4
,

 
 
1
,

 
 
3
0
9
,

 
 
2
,

 
 
1
0
,

 
 
2
5
1
5
,

 
 
1
8
,

 
 
4
,

 
 
2
2
,

 
 
3
2
3
2
,

 
 
3
,

 
 
4
6
6
6
,

 
 
1
0
1
,

 
 
2
9
2
,

 
 
8
4
,

 
 
2
8
,

 
 
1
8
8
3
,

 
 
6
0
6
]
,

 
[
1
1
,

 
 
8
,

 
 
7
,

 
 
1
,

 
 
2
4
1
,

 
 
2
,

 
 
2
6
,

 
 
1
5
2
2
,

 
 
9
,

 
 
1
6
9
,

 
 
1
,

 
 
3
0
0
,

 
 
1
4
7
1
2
,

 
 
1
1
,

 
 
8
,

 
 
8
6
6
,

 
 
1
,

 
 
2
7
0
9
,

 
 
2
,

 
 
4
8
3
,

 
 
4
9
,

 
 
2
8
,

 
 
3
9
7
8
,

 
 
5
4
3
,

 
 
4
,

 
 
9
,

 
 
1
4
7
1
3
,

 
 
3
5
,

 
 
5
2
3
5
,

 
 
5
8
,

 
 
1
3
,

 
 
1
8
9
,

 
 
4
9
2
3
,

 
 
3
,

 
 
9
3
8
8
,

 
 
1
4
9
3
,

 
 
9
3
,

 
 
1
8
9
1
1
,

 
 
1
,

 
 
3
5
9
,

 
 
1
8
9
1
2
,

 
 
1
1
,

 
 
8
,

 
 
7
,

 
 
1
,

 
 
2
4
1
,

 
 
2
,

 
 
2
6
,

 
 
1
5
2
2
,

 
 
9
,

 
 
4
1
,

 
 
6
,

 
 
1
0
2
,

 
 
5
9
1
,

 
 
7
6
3
8
,

 
 
2
1
,

 
 
2
7
1
0
,

 
 
3
,

 
 
1
0
1
,

 
 
2
8
5
,

 
 
1
2
,

 
 
4
3
,

 
 
7
,

 
 
6
3
7
,

 
 
2
4
6
2
,

 
 
1
7
,

 
 
4
7
,

 
 
3
8
3
0
,

 
 
1
8
9
1
3
,

 
 
1
6
,

 
 
1
8
9
1
4
,

 
 
7
6
3
9
,

 
 
7
,

 
 
1
5
,

 
 
3
4
8
,

 
 
6
2
5
,

 
 
2
,

 
 
9
,

 
 
6
4
4
8
,

 
 
5
2
3
6
,

 
 
1
,

 
 
1
4
7
1
4
,

 
 
2
,

 
 
6
,

 
 
4
9
2
4
,

 
 
3
,

 
 
1
1
6
6
,

 
 
4
,

 
 
1
,

 
 
9
9
7
,

 
 
3
7
2
,

 
 
1
8
9
1
5
,

 
 
3
4
9
1
]
,

 
[
5
,

 
 
2
9
7
,

 
 
9
3
8
9
,

 
 
1
4
,

 
 
9
0
,

 
 
4
9
,

 
 
3
1
,

 
 
1
9
4
4
,

 
 
2
,

 
 
7
4
9
,

 
 
6
6
,

 
 
1
5
,

 
 
1
9
4
5
,

 
 
7
,

 
 
6
4
4
9
,

 
 
1
,

 
 
1
0
2
,

 
 
6
5
3
,

 
 
6
9
7
1
,

 
 
1
2
,

 
 
1
4
,

 
 
4
3
,

 
 
9
2
2
,

 
 
9
,

 
 
7
,

 
 
6
4
4
9
,

 
 
1
,

 
 
1
0
2
,

 
 
6
5
3
,

 
 
6
9
7
1
,

 
 
4
5
,

 
 
5
2
2
,

 
 
6
,

 
 
7
7
6
,

 
 
2
1
5
6
,

 
 
1
5
9
0
,

 
 
1
9
9
9
,

 
 
6
0
,

 
 
5
,

 
 
6
4
5
0
,

 
 
4
6
0
,

 
 
5
8
,

 
 
1
7
,

 
 
1
1
3
,

 
 
1
4
8
,

 
 
1
2
,

 
 
4
5
,

 
 
2
2
2
4
,

 
 
1
0
7
0
,

 
 
3
2
3
3
,

 
 
7
,

 
 
1
8
9
1
6
,

 
 
3
,

 
 
1
2
2
3
6
,

 
 
1
,

 
 
1
8
9
1
7
,

 
 
1
,

 
 
1
0
2
,

 
 
6
5
3
,

 
 
6
9
7
1
,

 
 
5
2
3
7
,

 
 
1
9
3
]
,

 
[
5
,
 
6
2
,
 
4
1
9
9
,
 
1
,
 
8
3
,
 
1
,
 
4
5
4
,
 
5
,
 
4
2
0
0
,
 
4
,
 
7
8
,
 
1
4
6
9
]
,

 
[
6
5
5
,
 
1
5
0
,
 
9
,
 
1
4
,
 
1
2
3
,
 
1
6
9
1
,
 
3
6
,
 
9
5
,
 
1
5
5
6
,
 
1
4
,
 
1
1
3
1
,
 
4
,
 
4
6
3
]
,

 
[
1
,

 
 
9
4
2
,

 
 
1
4
3
,

 
 
6
,

 
 
1
4
9
4
,

 
 
7
,

 
 
1
,

 
 
7
9
,

 
 
3
2
3
4
,

 
 
1
4
1
,

 
 
3
,

 
 
9
6
,

 
 
8
5
,

 
 
4
5
,

 
 
3
2
3
4
,

 
 
2
4
6
,

 
 
3
,

 
 
2
2
,

 
 
2
7
1
1
]
,

 
[
1
1
,

 
 
2
5
,

 
 
7
5
,

 
 
3
5
3
,

 
 
9
,

 
 
1
,

 
 
1
7
3
5
,

 
 
2
,

 
 
1
0
,

 
 
9
0
4
,

 
 
4
9
,

 
 
9
0
,

 
 
3
1
,

 
 
5
2
3
,

 
 
1
,

 
 
1
8
9
0
,

 
 
1
6
9
9
,

 
 
9
,

 
 
4
1
9
,

 
 
4
,

 
 
1
0
,

 
 
1
1
8
5
]
,

 
[
5
,

 
 
1
2
,

 
 
2
0
,

 
 
3
1
5
,

 
 
1
,

 
 
2
1
5
7
,

 
 
2
7
,

 
 
1
0
,

 
 
1
1
1
,

 
 
1
2
2
3
7
,

 
 
1
8
,

 
 
2
8
4
,

 
 
1
6
,

 
 
6
,

 
 
4
2
6
,

 
 
7
3
0
,

 
 
2
,

 
 
1
,

 
 
1
8
9
1
8
,

 
 
2
,

 
 
1
,

 
 
7
1
,

 
 
1
3
0
,

 
 
6
4
5
1
,

 
 
7
6
4
0
,

 
 
5
,

 
 
8
,

 
 
1
,

 
 
2
2
6
7
,

 
 
3
0
0
5
,

 
 
1
8
9
1
9
,

 
 
7
6
4
1
,

 
 
5
8
5
,

 
 
3
4
6
9
,

 
 
3
8
9
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
,
 
1
5
1
,
 
3
3
4
8
,
 
1
3
,
 
6
,
 
1
5
9
1
,
 
2
,
 
9
1
,
 
8
0
6
,
 
6
6
0
,
 
3
,
 
5
,
 
7
6
4
2
,
 
1
1
,
 
1
4
4
6
]
,

 
[
1
,
 
3
3
3
,
 
5
,
 
1
2
2
3
8
,
 
4
4
,
 
6
7
,
 
1
,
 
5
0
,
 
7
9
3
,
 
3
2
4
,
 
1
,
 
4
1
2
,
 
1
9
,
 
1
2
,
 
4
3
,
 
6
2
2
,
 
1
6
1
,
 
2
2
]
,

 
[
4
8
,

 
 
2
7
2
,

 
 
1
0
6
5
1
,

 
 
1
8
,

 
 
3
0
,

 
 
2
0
0
0
,

 
 
7
,

 
 
1
,

 
 
1
4
7
1
5
,

 
 
2
,

 
 
1
5
,

 
 
5
5
2
,

 
 
8
,

 
 
3
9
9
3
,

 
 
3
,

 
 
4
1
,

 
 
4
2
,

 
 
2
9
,

 
 
4
0
3
,

 
 
7
6
4
3
,

 
 
2
3
,

 
 
2
1
3
,

 
 
4
8
,

 
 
5
4
3
,

 
 
3
0
,

 
 
1
3
5
,

 
 
4
,

 
 
1
,

 
 
3
9
9
4
,

 
 
5
3
1
]
,

 
[
4
,

 
 
2
2
,

 
 
4
5
,

 
 
8
,

 
 
1
6
0
,

 
 
1
4
4
7
,

 
 
7
,

 
 
1
,

 
 
1
8
3
8
,

 
 
3
,

 
 
6
9
7
2
,

 
 
9
,

 
 
1
8
9
2
0
,

 
 
5
4
,

 
 
2
,

 
 
1
,

 
 
3
7
8
,

 
 
1
2
2
3
9
,

 
 
2
6
2
,

 
 
1
1
9
,

 
 
1
6
9
,

 
 
1
,

 
 
3
8
3
1
]
,

 
[
1
4
,

 
 
8
,

 
 
2
2
2
,

 
 
2
,

 
 
1
2
1
,

 
 
3
,

 
 
3
7
9
,

 
 
5
9
2
,

 
 
1
9
5
,

 
 
6
,

 
 
2
0
5
0
,

 
 
1
8
8
,

 
 
2
,

 
 
5
5
,

 
 
2
8
8
9
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
4
,

 
 
7
7
,

 
 
5
,

 
 
8
4
,

 
 
1
2
2
4
0
,

 
 
4
,

 
 
3
3
,

 
 
1
7
,

 
 
1
0
,

 
 
6
9
7
3
,

 
 
1
,

 
 
3
6
3
,

 
 
2
5
,

 
 
8
4
5
4
,

 
 
6
8
2
,

 
 
2
0
9
8
,

 
 
2
7
,

 
 
4
,

 
 
1
0
3
,

 
 
3
,

 
 
5
,

 
 
1
3
3
,

 
 
4
6
6
7
,

 
 
1
0
,

 
 
1
0
7
1
]
,

 
[
1
,

 
 
1
4
6
,

 
 
2
6
9
,

 
 
2
8
,

 
 
1
2
0
9
,

 
 
4
5
,

 
 
2
5
,

 
 
3
6
,

 
 
8
1
1
,

 
 
1
7
,

 
 
8
9
,

 
 
1
4
7
1
6
,

 
 
2
,

 
 
3
0
0
6
,

 
 
3
,

 
 
4
9
2
5
,

 
 
9
3
9
0
,

 
 
8
9
,

 
 
6
4
5
2
,

 
 
1
0
6
5
2
,

 
 
2
,

 
 
3
2
,

 
 
2
6
1
,

 
 
5
6
5
,

 
 
3
,

 
 
3
2
3
5
,

 
 
5
4
7
]
,

 
[
4
,
 
2
4
0
9
,
 
4
,
 
5
5
,
 
8
4
5
5
,
 
3
4
,
 
9
6
,
 
1
,
 
6
9
7
4
,
 
2
5
1
6
,
 
3
,
 
2
9
6
,
 
1
9
3
8
]
,

 
[
2
3
,

 
 
6
7
,

 
 
2
8
5
,

 
 
1
7
,

 
 
4
2
,

 
 
2
9
,

 
 
1
8
9
1
,

 
 
1
4
7
,

 
 
5
,

 
 
9
6
,

 
 
1
0
4
,

 
 
4
9
5
,

 
 
7
,

 
 
6
9
7
5
,

 
 
6
3
,

 
 
8
7
,

 
 
4
,

 
 
1
0
,

 
 
5
0
0
]
,

 
[
1
1
,

 
 
8
,

 
 
7
5
7
,

 
 
7
6
4
4
,

 
 
7
5
7
,

 
 
3
,

 
 
1
0
,

 
 
7
1
2
,

 
 
2
9
8
,

 
 
2
0
9
,

 
 
1
8
9
2
1
,

 
 
1
6
,

 
 
6
0
,

 
 
1
8
5
,

 
 
8
4
5
6
,

 
 
2
0
,

 
 
4
,

 
 
2
8
,

 
 
8
6
6
,

 
 
4
1
,

 
 
1
4
,

 
 
2
0
9
9
,

 
 
9
,

 
 
2
,

 
 
1
,

 
 
1
7
6
,

 
 
1
1
6
1
,

 
 
1
1
3
,

 
 
1
2
,

 
 
5
6
0
1
,

 
 
1
8
3
7
,

 
 
1
,

 
 
8
0
1
,

 
 
2
,

 
 
1
,

 
 
2
4
1
0
,

 
 
3
7
5
]
,

 
[
1
7
,

 
 
1
9
7
,

 
 
5
2
0
,

 
 
6
,

 
 
1
0
3
,

 
 
1
0
8
,

 
 
2
0
,

 
 
2
2
1
,

 
 
1
9
5
,

 
 
1
,

 
 
4
7
8
,

 
 
1
8
8
,

 
 
2
,

 
 
1
9
,

 
 
5
,

 
 
3
1
,

 
 
2
0
,

 
 
4
3
,

 
 
1
3
3
1
,

 
 
5
2
3
8
,

 
 
7
,

 
 
1
4
7
1
7
,

 
 
1
,

 
 
1
1
7
9
,

 
 
2
2
7
5
]
,

 
[
2
0
8
,

 
 
7
3
,

 
 
2
0
,

 
 
4
3
4
,

 
 
9
,

 
 
1
3
1
,

 
 
2
6
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

 
 
1
2
,

 
 
6
4
5
3
,

 
 
2
4
,

 
 
1
0
0
6
,

 
 
1
8
,

 
 
1
4
,

 
 
7
3
,

 
 
2
0
,

 
 
1
7
,

 
 
2
6
,

 
 
3
6
4
9
,

 
 
1
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
0
,

 
 
7
0
,

 
 
5
0
,

 
 
6
0
8
,

 
 
1
4
,

 
 
1
0
9
,

 
 
1
7
,

 
 
1
,

 
 
1
7
0
1
,

 
 
2
,

 
 
8
7
5
,

 
 
6
1
5
,

 
 
3
5
,

 
 
2
5
1
7
,

 
 
1
7
,

 
 
1
4
9
5
,

 
 
9
,

 
 
4
9
2
6
,

 
 
8
1
,

 
 
4
7
4
,

 
 
1
8
9
2
2
,

 
 
2
4
,

 
 
6
,

 
 
1
4
7
1
8
,

 
 
2
0
4
]
,

 
[
1
8
,

 
 
1
0
0
,

 
 
5
,

 
 
1
5
5
7
,

 
 
5
9
9
8
,

 
 
3
,

 
 
5
5
9
,

 
 
7
,

 
 
5
1
,

 
 
3
1
1
4
,

 
 
1
3
,

 
 
1
,

 
 
2
4
1
,

 
 
2
,

 
 
3
7
,

 
 
2
7
9
1
,

 
 
5
,

 
 
3
4
9
2
,

 
 
1
6
,

 
 
1
0
,

 
 
1
7
8
7
,

 
 
5
1
,

 
 
3
3
4
9
,

 
 
3
,

 
 
5
9
6
9
]
,

 
[
5
,
 
8
4
,
 
4
9
2
7
,
 
1
0
,
 
3
3
6
]
,

 
[
9
0
,
 
8
4
5
7
,
 
4
4
,
 
7
0
,
 
3
8
,
 
1
1
0
,
 
5
,
 
7
8
1
,
 
3
6
,
 
3
8
,
 
4
,
 
1
1
3
2
,
 
1
,
 
1
8
9
2
3
,
 
1
3
,
 
2
2
]
,

 
[
2
0
,

 
 
4
0
,

 
 
7
7
,

 
 
5
,

 
 
1
5
7
,

 
 
5
,

 
 
1
6
8
9
,

 
 
9
,

 
 
1
0
,

 
 
3
3
6
,

 
 
5
6
,

 
 
2
0
,

 
 
8
0
7
,

 
 
1
6
,

 
 
1
0
6
5
3
,

 
 
1
6
,

 
 
3
1
1
8
,

 
 
5
6
]
,

 
[
6
5
,

 
 
1
6
,

 
 
5
,

 
 
3
7
9
,

 
 
6
4
5
4
,

 
 
1
3
,

 
 
2
1
3
,

 
 
1
4
,

 
 
9
6
,

 
 
1
5
,

 
 
2
0
0
,

 
 
3
,

 
 
7
,

 
 
1
5
,

 
 
9
9
8
,

 
 
8
7
1
,

 
 
2
4
6
3
,

 
 
4
7
5
,

 
 
9
7
,

 
 
1
6
3
,

 
 
1
9
,

 
 
3
1
,

 
 
1
2
9
,

 
 
9
3
9
,

 
 
1
2
1
0
,

 
 
1
0
,

 
 
2
3
1
,

 
 
3
,

 
 
1
0
,

 
 
1
9
4
6
]
,

 
[
1
0
9
0
,
 
1
1
,
 
2
5
,
 
2
0
,
 
1
,
 
2
3
5
4
,
 
2
,
 
1
0
6
5
4
,
 
4
,
 
1
7
3
6
,
 
2
4
6
4
,
 
4
0
,
 
1
8
9
2
4
]
,

 
[
4
2
,

 
 
3
7
9
,

 
 
1
9
4
7
,

 
 
1
7
,

 
 
3
9
3
,

 
 
5
2
0
,

 
 
6
9
,

 
 
1
,

 
 
2
8
9
0
,

 
 
2
1
4
,

 
 
1
4
9
,

 
 
1
,

 
 
7
3
0
,

 
 
2
,

 
 
1
9
,

 
 
2
4
1
1
,

 
 
6
3
,

 
 
2
,

 
 
5
1
,

 
 
1
0
8
7
,

 
 
3
,

 
 
3
4
9
3
,

 
 
6
3
,

 
 
4
,

 
 
6
,

 
 
2
2
1
6
,

 
 
5
6
0
0
,

 
 
2
4
,

 
 
5
1
,

 
 
7
1
6
,

 
 
2
9
2
]
,

 
[
4
2
,

 
 
9
0
,

 
 
1
5
5
8
,

 
 
1
4
7
1
9
,

 
 
7
,

 
 
2
6
0
,

 
 
1
4
6
7
,

 
 
5
4
6
,

 
 
1
,

 
 
4
3
5
,

 
 
2
4
,

 
 
9
,

 
 
1
7
8
8
,

 
 
2
2
2
5
,

 
 
5
4
6
,

 
 
7
6
4
5
,

 
 
2
6
0
,

 
 
5
0
,

 
 
2
6
0
,

 
 
5
0
,

 
 
1
9
4
8
,

 
 
1
4
7
2
0
,

 
 
6
3
9
,

 
 
6
,

 
 
3
9
9
5
,

 
 
6
6
,

 
 
2
6
0
,

 
 
5
0
,

 
 
2
6
0
,

 
 
5
0
,

 
 
2
3
5
0
,

 
 
8
,

 
 
3
2
3
6
,

 
 
7
,

 
 
1
2
2
4
1
,

 
 
1
6
,

 
 
4
6
5
4
,

 
 
1
8
9
2
5
,

 
 
4
,

 
 
5
2
3
9
,

 
 
1
8
9
2
,

 
 
7
,

 
 
1
3
7
7
]
,

 
[
2
1
,

 
 
8
4
5
8
,

 
 
1
4
,

 
 
1
2
,

 
 
4
3
,

 
 
4
9
2
8
,

 
 
7
,

 
 
1
,

 
 
5
2
4
0
,

 
 
1
0
6
5
5
,

 
 
2
,

 
 
1
4
7
2
1
,

 
 
1
4
7
2
1
,

 
 
7
6
4
6
,

 
 
1
0
5
,

 
 
1
4
,

 
 
8
,

 
 
1
,

 
 
2
0
9
3
,

 
 
3
,

 
 
1
8
9
2
6
,

 
 
2
,

 
 
1
,

 
 
2
9
5
,

 
 
3
,

 
 
4
4
2
1
,

 
 
2
3
8
,

 
 
1
4
7
2
2
,

 
 
1
8
,

 
 
2
6
,

 
 
1
0
6
5
6
,

 
 
1
8
9
2
7
,

 
 
1
0
6
5
7
,

 
 
7
3
,

 
 
2
0
,

 
 
2
7
9
2
,

 
 
3
9
]
,

 
[
1
,

 
 
9
8
2
,

 
 
4
8
9
,

 
 
1
7
,

 
 
5
1
,

 
 
2
5
3
,

 
 
5
2
4
1
,

 
 
4
6
6
8
,

 
 
3
3
5
0
,

 
 
1
,

 
 
9
3
9
1
,

 
 
1
3
7
8
,

 
 
2
,

 
 
5
9
9
9
,

 
 
1
3
5
9
,

 
 
2
5
1
8
,

 
 
1
8
9
2
8
,

 
 
3
,

 
 
6
0
0
0
,

 
 
7
,

 
 
1
8
9
2
9
,

 
 
7
6
4
7
,

 
 
1
8
9
3
0
,

 
 
9
,

 
 
2
9
,

 
 
4
8
4
,

 
 
1
2
2
4
2
,

 
 
1
8
3
,

 
 
3
3
5
1
]
,

 
[
6
7
,

 
 
5
6
,

 
 
1
0
,

 
 
1
4
7
2
3
,

 
 
3
,

 
 
4
2
,

 
 
5
6
,

 
 
6
2
6
,

 
 
4
,

 
 
4
9
2
9
,

 
 
3
2
,

 
 
2
1
3
,

 
 
2
,

 
 
7
8
2
,

 
 
3
5
,

 
 
1
3
4
,

 
 
3
,

 
 
4
,

 
 
4
9
3
0
,

 
 
2
2
,

 
 
4
,

 
 
2
6
9
5
,

 
 
2
6
,

 
 
8
4
5
9
,

 
 
1
2
1
1
,

 
 
1
3
,

 
 
1
,

 
 
4
9
0
,

 
 
6
,

 
 
4
3
0
,

 
 
4
4
2
2
,

 
 
4
1
,

 
 
1
4
,

 
 
1
8
9
3
1
,

 
 
7
,

 
 
6
,

 
 
1
0
4
,

 
 
6
3
3
,

 
 
1
3
,

 
 
1
5
,

 
 
1
4
7
2
4
,

 
 
9
3
9
2
,

 
 
2
7
,

 
 
3
7
,

 
 
3
1
1
9
,

 
 
2
,

 
 
8
4
1
,

 
 
6
6
,

 
 
1
5
,

 
 
7
1
6
,

 
 
4
3
5
]
,

 
[
4
5
,

 
 
2
9
,

 
 
5
2
4
2
,

 
 
6
4
5
5
,

 
 
2
7
,

 
 
1
,

 
 
1
2
2
,

 
 
6
0
0
1
,

 
 
1
4
0
9
,

 
 
4
,

 
 
3
6
5
0
,

 
 
1
3
7
4
,

 
 
3
,

 
 
6
7
,

 
 
5
,

 
 
6
3
4
,

 
 
4
,

 
 
9
3
9
3
]
,

 
[
1
5
,

 
 
2
8
9
1
,

 
 
8
,

 
 
9
,

 
 
6
,

 
 
1
1
6
,

 
 
1
9
4
9
,

 
 
7
6
0
,

 
 
6
1
,

 
 
1
0
0
9
,

 
 
3
,

 
 
8
4
5
,

 
 
2
,

 
 
1
5
,

 
 
4
1
3
,

 
 
8
8
1
,

 
 
4
0
,

 
 
9
,

 
 
1
4
,

 
 
4
6
,

 
 
2
8
,

 
 
1
4
4
0
,

 
 
7
,

 
 
6
,

 
 
1
8
3
9
,

 
 
2
0
9
,

 
 
4
0
0
,

 
 
1
7
5
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
3
,

 
 
1
4
1
5
,

 
 
1
,

 
 
1
3
6
0
,

 
 
2
,

 
 
1
4
4
8
,

 
 
3
,

 
 
2
4
1
2
,

 
 
3
2
,

 
 
1
,

 
 
9
3
9
4
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
5
6
0
2
,

 
 
6
8
,

 
 
1
,

 
 
1
7
4
,

 
 
3
0
0
7
,

 
 
3
,

 
 
1
8
9
3
2
,

 
 
7
,

 
 
2
5
9
3
,

 
 
6
9
7
6
,

 
 
2
9
,

 
 
2
1
0
0
,

 
 
9
3
9
5
,

 
 
3
,

 
 
1
8
9
3
3
,

 
 
2
5
3
,

 
 
3
0
0
,

 
 
3
,

 
 
7
2
,

 
 
1
6
6
7
,

 
 
4
4
2
3
,

 
 
3
6
5
1
,

 
 
1
3
,

 
 
1
1
4
,

 
 
1
8
9
3
4
,

 
 
6
2
7
,

 
 
3
,

 
 
4
0
,

 
 
1
8
9
3
5
,

 
 
1
3
,

 
 
1
2
2
4
3
,

 
 
1
1
0
9
,

 
 
1
6
6
0
,

 
 
2
1
,

 
 
2
2
2
,

 
 
1
9
1
,

 
 
1
4
4
7
,

 
 
1
3
0
3
,

 
 
3
,

 
 
9
5
,

 
 
5
2
4
3
,

 
 
2
1
5
8
,

 
 
2
,

 
 
1
,

 
 
4
2
0
1
,

 
 
1
6
,

 
 
4
,

 
 
3
1
,

 
 
5
7
9
,

 
 
2
9
0
,

 
 
5
3
,

 
 
1
0
4
,

 
 
2
,

 
 
9
4
3
,

 
 
2
5
4
,

 
 
8
0
,

 
 
3
1
,

 
 
4
3
,

 
 
5
1
,

 
 
4
9
1
,

 
 
7
,

 
 
2
3
1
,

 
 
1
0
9
,

 
 
9
5
7
]
,

 
[
6
0
,
 
5
2
4
4
,
 
8
5
1
,
 
3
,
 
2
7
1
2
,
 
1
1
8
,
 
4
8
9
,
 
8
5
,
 
3
4
,
 
6
2
,
 
2
8
,
 
2
5
1
9
]
,

 
[
1
,

 
 
1
3
7
9
,

 
 
6
0
9
,

 
 
3
,

 
 
2
8
9
2
,

 
 
3
9
9
,

 
 
2
,

 
 
1
,

 
 
1
2
5
2
,

 
 
1
4
7
2
5
,

 
 
3
9
9
6
,

 
 
1
0
,

 
 
4
9
3
1
,

 
 
1
0
0
,

 
 
1
,

 
 
4
5
3
,

 
 
1
8
9
3
,

 
 
2
,

 
 
1
,

 
 
6
2
1
,

 
 
1
8
9
3
6
,

 
 
1
0
,

 
 
1
5
2
]
,

 
[
5
,
 
1
3
0
4
,
 
2
3
,
 
1
8
9
3
7
,
 
1
0
,
 
2
2
5
,
 
4
,
 
7
6
4
8
]
,

 
[
1
8
,
 
6
7
,
 
1
0
6
5
8
,
 
5
,
 
8
4
,
 
2
0
,
 
1
3
8
0
,
 
4
,
 
1
4
1
6
]
,

 
[
5
,
 
3
3
5
2
,
 
6
4
,
 
2
1
,
 
1
0
3
,
 
9
0
5
,
 
2
,
 
7
6
4
9
,
 
1
,
 
5
2
1
7
,
 
2
,
 
6
,
 
1
8
1
,
 
1
2
7
]
,

 
[
5
1
0
,

 
 
1
2
,

 
 
3
4
,

 
 
1
3
6
1
,

 
 
5
5
,

 
 
8
8
5
,

 
 
6
9
,

 
 
1
,

 
 
1
4
7
2
6
,

 
 
2
3
3
,

 
 
5
7
,

 
 
7
6
5
0
,

 
 
4
1
,

 
 
3
4
,

 
 
6
3
9
,

 
 
6
6
,

 
 
6
,

 
 
9
4
0
,

 
 
1
5
9
2
,

 
 
1
7
0
2
,

 
 
3
,

 
 
1
3
,

 
 
2
6
,

 
 
7
3
,

 
 
1
8
4
0
,

 
 
1
1
6
,

 
 
1
7
,

 
 
5
4
,

 
 
3
0
8
,

 
 
1
,

 
 
7
2
6
,

 
 
1
0
6
5
9
,

 
 
1
,

 
 
2
0
4
,

 
 
1
1
4
,

 
 
5
0
,

 
 
1
5
2
3
,

 
 
5
9
,

 
 
6
9
]
,

 
[
1
,

 
 
1
0
4
2
,

 
 
4
9
1
,

 
 
2
,

 
 
1
,

 
 
9
5
,

 
 
2
5
,

 
 
1
0
2
9
,

 
 
2
4
,

 
 
3
7
4
,

 
 
2
3
,

 
 
1
,

 
 
1
6
7
,

 
 
2
,

 
 
1
,

 
 
8
4
6
0
,

 
 
5
2
4
5
,

 
 
1
9
,

 
 
2
5
,

 
 
2
2
7
6
,

 
 
3
7
6
,

 
 
6
6
,

 
 
2
8
0
,

 
 
1
1
]
,

 
[
3
5
6
,

 
 
1
2
,

 
 
2
7
9
3
,

 
 
7
6
5
1
,

 
 
3
8
3
2
,

 
 
2
,

 
 
2
7
1
3
,

 
 
7
,

 
 
1
,

 
 
3
9
9
7
,

 
 
1
9
,

 
 
1
0
0
,

 
 
4
2
,

 
 
2
9
,

 
 
9
6
9
,

 
 
4
,

 
 
1
7
8
9
,

 
 
1
,

 
 
7
7
4
,

 
 
2
,

 
 
1
3
4
,

 
 
7
6
,

 
 
1
7
0
3
,

 
 
9
5
,

 
 
3
0
0
8
,

 
 
2
4
6
5
,

 
 
3
,

 
 
2
0
0
1
,

 
 
2
4
,

 
 
5
6
0
3
,

 
 
1
,

 
 
1
1
2
9
,

 
 
6
6
9
,

 
 
2
,

 
 
1
,

 
 
3
0
5
,

 
 
1
0
6
,

 
 
5
0
,

 
 
2
0
9
7
]
,

 
[
2
1
,

 
 
6
,

 
 
1
9
5
0
,

 
 
3
8
7
,

 
 
1
0
1
4
,

 
 
1
2
7
,

 
 
3
6
,

 
 
3
3
3
,

 
 
6
8
8
,

 
 
4
,

 
 
2
0
0
2
,

 
 
8
7
1
,

 
 
1
3
6
,

 
 
1
,

 
 
8
6
,

 
 
2
2
7
7
,

 
 
5
5
9
,

 
 
5
,

 
 
6
3
4
,

 
 
2
0
5
1
,

 
 
4
,

 
 
1
0
6
6
0
,

 
 
2
1
7
,

 
 
1
,

 
 
8
4
4
,

 
 
1
,

 
 
2
7
9
4
,

 
 
2
7
9
5
,

 
 
4
,

 
 
1
,

 
 
6
4
5
6
]
,

 
[
1
,

 
 
1
2
5
4
,

 
 
1
2
,

 
 
4
3
,

 
 
1
8
9
4
,

 
 
8
8
4
,

 
 
1
9
5
1
,

 
 
2
4
,

 
 
1
,

 
 
1
4
7
2
7
,

 
 
6
3
3
,

 
 
1
2
7
5
,

 
 
3
2
3
,

 
 
1
6
,

 
 
3
0
0
9
,

 
 
7
7
,

 
 
8
2
,

 
 
1
7
8
,

 
 
4
3
,

 
 
1
4
7
2
8
,

 
 
2
3
,

 
 
6
,

 
 
1
8
9
3
8
,

 
 
3
8
1
,

 
 
2
5
2
0
,

 
 
5
8
,

 
 
1
2
,

 
 
1
6
4
,

 
 
2
4
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
7
5
7
,

 
 
2
1
5
,

 
 
7
6
5
2
,

 
 
2
7
,

 
 
1
,

 
 
3
8
3
3
,

 
 
3
0
1
0
,

 
 
1
9
,

 
 
4
9
2
,

 
 
6
,

 
 
4
4
9
,

 
 
7
0
0
,

 
 
2
4
,

 
 
1
,

 
 
4
4
2
4
,

 
 
4
,

 
 
1
,

 
 
1
2
2
4
4
,

 
 
3
0
2
,

 
 
7
,

 
 
6
0
0
2
,

 
 
2
6
5
]
,

 
[
3
2
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
2
7
8
,

 
 
1
3
,

 
 
1
5
,

 
 
1
5
1
,

 
 
9
8
3
,

 
 
2
,

 
 
6
0
0
,

 
 
1
2
7
6
,

 
 
1
5
,

 
 
4
0
8
,

 
 
1
6
7
,

 
 
2
4
,

 
 
1
,

 
 
1
7
0
4
,

 
 
3
,

 
 
2
6
0
8
,

 
 
4
4
2
5
]
,

 
[
1
7
0
5
,

 
 
1
7
0
5
,

 
 
1
7
0
5
,

 
 
7
7
,

 
 
9
,

 
 
7
7
6
,

 
 
1
4
,

 
 
1
4
,

 
 
1
4
,

 
 
6
9
7
7
,

 
 
6
9
7
7
,

 
 
6
9
7
7
,

 
 
6
0
0
3
,

 
 
6
0
0
3
,

 
 
6
0
0
3
,

 
 
6
0
0
4
,

 
 
6
0
0
4
,

 
 
6
0
0
4
,

 
 
6
0
0
4
,

 
 
6
1
,

 
 
1
8
9
,

 
 
1
5
3
,

 
 
3
3
,

 
 
8
4
,

 
 
2
0
,

 
 
2
8
,

 
 
2
1
5
9
,

 
 
6
0
0
5
,

 
 
6
9
7
8
,

 
 
5
5
,

 
 
1
9
2
,

 
 
1
2
4
,

 
 
2
5
,

 
 
6
,

 
 
2
5
2
1
,

 
 
6
,

 
 
1
8
9
3
9
,

 
 
3
3
,

 
 
8
4
,

 
 
2
0
,

 
 
6
1
4
,

 
 
3
9
,

 
 
4
,

 
 
1
,

 
 
4
7
9
]
,

 
[
1
1
,

 
 
2
5
,

 
 
3
3
2
,

 
 
9
,

 
 
5
,

 
 
1
2
3
,

 
 
2
0
,

 
 
2
3
2
,

 
 
3
7
,

 
 
1
7
3
7
,

 
 
2
,

 
 
1
4
7
2
9
,

 
 
1
1
,

 
 
4
,

 
 
1
,

 
 
1
5
9
,

 
 
1
8
,

 
 
5
,

 
 
6
2
,

 
 
2
0
,

 
 
7
1
5
,

 
 
4
,

 
 
1
8
7
,

 
 
1
,

 
 
1
7
3
8
]
,

 
[
5
,

 
 
1
5
5
9
,

 
 
9
,

 
 
7
,

 
 
1
8
9
5
,

 
 
2
7
9
6
,

 
 
3
5
,

 
 
1
8
9
4
0
,

 
 
2
0
6
,

 
 
2
5
,

 
 
1
,

 
 
9
4
4
,

 
 
1
7
2
,

 
 
2
8
9
3
,

 
 
2
,

 
 
6
0
0
6
,

 
 
3
,

 
 
9
,

 
 
3
9
7
,

 
 
3
0
,

 
 
6
9
4
7
,

 
 
2
,

 
 
2
8
9
4
,

 
 
2
1
,

 
 
2
6
,

 
 
3
8
,

 
 
2
6
3
,

 
 
8
,

 
 
6
,

 
 
9
5
8
,

 
 
1
9
,

 
 
1
0
8
4
,

 
 
5
,

 
 
1
2
,

 
 
4
3
,

 
 
9
6
9
,

 
 
4
,

 
 
8
4
6
1
]
,

 
[
1
4
,

 
 
2
3
6
,

 
 
7
0
0
,

 
 
6
9
7
9
,

 
 
3
,

 
 
2
7
3
,

 
 
4
,

 
 
6
4
5
7
,

 
 
1
,

 
 
9
3
9
6
,

 
 
1
3
2
6
,

 
 
2
,

 
 
1
5
,

 
 
1
4
1
,

 
 
6
,

 
 
6
9
8
0
,

 
 
3
4
9
4
,

 
 
4
9
3
2
,

 
 
1
7
0
6
,

 
 
1
3
0
,

 
 
2
1
6
0
,

 
 
2
4
4
,

 
 
8
,

 
 
1
0
3
0
,

 
 
5
7
9
,

 
 
7
,

 
 
1
,

 
 
3
1
2
0
,

 
 
3
0
1
0
,

 
 
3
,

 
 
1
3
0
,

 
 
1
9
7
,

 
 
2
6
4
,

 
 
2
3
4
4
,

 
 
3
7
7
,

 
 
3
4
9
,

 
 
1
3
7
4
,

 
 
1
2
,

 
 
2
6
7
,

 
 
4
3
,

 
 
6
2
6
,

 
 
1
7
,

 
 
1
5
0
,

 
 
3
,

 
 
1
5
,

 
 
8
5
5
]
,

 
[
7
,
 
1
,
 
1
0
5
1
,
 
1
1
,
 
8
,
 
2
0
0
1
,
 
4
,
 
6
4
5
8
,
 
3
5
,
 
4
,
 
2
4
2
]
,

 
[
1
,

 
 
5
6
9
,

 
 
5
7
0
,

 
 
2
,

 
 
1
,

 
 
1
6
2
6
,

 
 
1
3
0
,

 
 
6
4
,

 
 
1
5
8
,

 
 
8
,

 
 
5
2
3
,

 
 
2
4
,

 
 
1
,

 
 
4
4
0
,

 
 
1
7
5
,

 
 
1
,

 
 
1
2
2
4
5
,

 
 
1
2
5
5
,

 
 
4
,

 
 
6
,

 
 
2
6
6
,

 
 
2
,

 
 
1
5
9
3
,

 
 
9
,

 
 
1
5
9
4
,

 
 
6
8
,

 
 
1
1
,

 
 
7
4
6
,

 
 
1
,

 
 
3
6
5
2
,

 
 
1
5
1
8
,

 
 
2
,

 
 
1
,

 
 
8
4
6
2
,

 
 
1
5
5
5
,

 
 
3
,

 
 
2
1
6
1
]
,

 
[
5
6
0
4
,

 
 
2
5
,

 
 
1
,

 
 
4
9
3
3
,

 
 
1
1
4
4
,

 
 
4
,

 
 
1
4
7
3
0
,

 
 
5
6
0
5
,

 
 
1
4
7
3
1
,

 
 
7
,

 
 
5
2
4
6
,

 
 
3
,

 
 
1
8
9
4
1
,

 
 
3
,

 
 
1
6
,

 
 
8
9
,

 
 
1
0
8
,

 
 
6
,

 
 
2
1
2
,

 
 
1
8
9
6
,

 
 
1
9
,

 
 
8
4
6
3
,

 
 
7
5
,

 
 
4
,

 
 
1
,

 
 
6
4
5
9
,

 
 
1
8
9
4
2
,

 
 
2
,

 
 
1
,

 
 
1
4
9
,

 
 
1
8
,

 
 
4
5
,

 
 
8
,

 
 
2
5
0
,

 
 
1
5
1
3
,

 
 
3
8
,

 
 
5
8
,

 
 
2
4
0
,

 
 
7
3
7
,

 
 
1
,

 
 
6
2
3
,

 
 
2
,

 
 
9
,

 
 
1
8
9
6
,

 
 
3
8
,

 
 
5
8
,

 
 
3
9
7
4
,

 
 
1
,

 
 
8
4
6
4
,

 
 
3
,

 
 
1
4
7
3
2
,

 
 
1
8
,

 
 
2
0
,

 
 
1
,

 
 
1
6
2
0
,

 
 
2
,

 
 
5
6
0
4
]
,

 
[
2
3
7
,

 
 
1
,

 
 
6
9
8
1
,

 
 
2
,

 
 
1
5
,

 
 
2
4
6
6
,

 
 
7
4
6
,

 
 
1
1
,

 
 
2
0
,

 
 
4
0
,

 
 
1
5
1
1
,

 
 
2
6
1
3
,

 
 
3
5
,

 
 
5
0
,

 
 
1
4
7
0
,

 
 
5
,

 
 
6
4
2
9
,

 
 
1
0
,

 
 
3
3
5
3
,

 
 
4
,

 
 
1
,

 
 
1
3
0
5
,

 
 
2
0
3
,

 
 
2
,

 
 
1
,

 
 
1
8
9
4
3
,

 
 
5
8
,

 
 
1
8
9
4
4
,

 
 
1
,

 
 
4
7
9
,

 
 
1
9
,

 
 
7
,

 
 
6
,

 
 
3
6
5
3
,

 
 
2
5
,

 
 
3
2
,

 
 
1
,

 
 
6
4
6
0
,

 
 
1
1
8
,

 
 
1
2
6
,

 
 
2
0
7
,

 
 
1
8
,

 
 
1
,

 
 
2
2
2
,

 
 
2
4
1
,

 
 
2
,

 
 
1
5
,

 
 
9
4
3
,

 
 
1
7
,

 
 
1
0
,

 
 
9
8
1
,

 
 
2
1
0
1
,

 
 
3
,

 
 
8
4
6
5
]
,

 
[
1
1
,
 
8
,
 
2
3
7
,
 
3
7
,
 
5
4
1
,
 
2
,
 
8
9
,
 
6
9
8
2
,
 
9
,
 
1
0
,
 
1
3
8
,
 
4
9
3
,
 
1
8
9
7
,
 
6
,
 
2
2
6
9
,
 
2
,
 
8
1
2
]
,

 
[
3
3
,

 
 
1
1
3
1
,

 
 
4
,

 
 
4
2
2
,

 
 
1
5
7
,

 
 
5
3
,

 
 
5
4
,

 
 
2
,

 
 
1
,

 
 
7
9
,

 
 
1
8
9
4
5
,

 
 
2
7
8
,

 
 
6
8
,

 
 
1
,

 
 
2
5
3
,

 
 
2
2
2
5
,

 
 
2
0
5
,

 
 
1
,

 
 
1
8
9
8
,

 
 
1
2
7
7
,

 
 
2
2
2
5
,

 
 
4
2
,

 
 
4
1
4
,

 
 
1
1
]
,

 
[
1
,
 
3
0
1
1
,
 
1
2
,
 
2
3
4
2
,
 
3
2
,
 
1
,
 
1
2
2
4
6
,
 
2
,
 
5
0
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
6
8
,

 
 
5
,

 
 
1
2
2
4
7
,

 
 
4
,

 
 
1
,

 
 
2
2
2
,

 
 
1
,

 
 
5
6
0
6
,

 
 
2
,

 
 
9
,

 
 
2
8
9
5
,

 
 
1
8
9
4
6
,

 
 
1
9
,

 
 
5
,

 
 
8
4
,

 
 
2
0
,

 
 
9
7
1
,

 
 
4
1
,

 
 
1
,

 
 
1
4
6
,

 
 
9
1
4
,

 
 
3
,

 
 
5
,

 
 
8
,

 
 
1
8
3
7
,

 
 
1
7
9
,

 
 
4
,

 
 
2
6
,

 
 
1
5
2
0
,

 
 
1
4
6
8
,

 
 
2
,

 
 
6
2
8
,

 
 
3
,

 
 
8
4
6
6
]
,

 
[
1
4
,

 
 
1
2
6
,

 
 
3
8
4
,

 
 
5
,

 
 
2
7
8
,

 
 
5
4
8
,

 
 
6
9
8
3
,

 
 
5
2
4
7
,

 
 
2
6
,

 
 
3
8
2
4
,

 
 
5
8
7
,

 
 
3
6
,

 
 
1
8
9
,

 
 
2
6
0
,

 
 
5
,

 
 
2
4
2
,

 
 
1
6
,

 
 
3
2
,

 
 
1
,

 
 
1
4
7
,

 
 
1
3
0
6
,

 
 
1
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

 
 
6
6
,

 
 
6
,

 
 
6
2
9
,

 
 
2
6
0
,

 
 
9
4
,

 
 
6
0
0
7
]
,

 
[
3
6
,

 
 
2
4
1
3
,

 
 
1
3
2
8
,

 
 
2
,

 
 
5
2
4
8
,

 
 
1
2
,

 
 
2
2
7
8
,

 
 
2
6
,

 
 
3
3
5
,

 
 
3
1
7
,

 
 
7
6
,

 
 
1
6
2
7
,

 
 
3
,

 
 
7
5
,

 
 
2
7
1
4
,

 
 
2
,

 
 
1
4
8
,

 
 
9
8
,

 
 
3
2
3
7
,

 
 
7
,

 
 
4
7
,

 
 
1
0
2
5
,

 
 
3
,

 
 
4
9
3
4
,

 
 
5
5
8
,

 
 
2
,

 
 
1
4
7
3
3
,

 
 
3
7
8
]
,

 
[
1
7
,

 
 
6
,

 
 
1
0
9
,

 
 
7
2
,

 
 
5
,

 
 
7
0
1
,

 
 
2
0
,

 
 
2
5
1
,

 
 
1
8
,

 
 
4
1
,

 
 
1
5
,

 
 
9
3
9
7
,

 
 
1
7
0
7
,

 
 
3
,

 
 
1
,

 
 
6
0
0
8
,

 
 
9
,

 
 
1
2
2
4
8
,

 
 
1
5
,

 
 
1
7
3
4
,

 
 
2
9
,

 
 
6
9
8
4
,

 
 
3
6
,

 
 
3
3
3
,

 
 
4
,

 
 
2
8
,

 
 
1
7
3
9
,

 
 
2
,

 
 
1
,

 
 
9
7
0
,

 
 
2
,

 
 
1
2
7
8
,

 
 
3
8
2
7
,

 
 
5
,

 
 
2
0
5
2
,

 
 
4
,

 
 
2
0
5
3
,

 
 
1
,

 
 
2
7
9
7
,

 
 
2
,

 
 
1
,

 
 
3
7
1
,

 
 
4
,

 
 
4
4
4
,

 
 
3
,

 
 
2
1
,

 
 
1
9
1
,

 
 
7
9
5
,

 
 
7
,

 
 
6
9
8
5
,

 
 
3
0
,

 
 
9
,

 
 
5
,

 
 
2
9
8
,

 
 
3
6
3
]
,

 
[
1
4
,

 
 
5
2
4
9
,

 
 
2
2
2
6
,

 
 
1
,

 
 
3
3
2
,

 
 
3
9
6
,

 
 
1
,

 
 
2
0
5
4
,

 
 
1
0
6
6
1
,

 
 
1
,

 
 
2
1
0
2
,

 
 
1
7
4
0
,

 
 
3
,

 
 
1
8
9
6
,

 
 
2
,

 
 
1
,

 
 
3
6
5
4
,

 
 
9
1
5
]
,

 
[
7
3
5
,
 
4
5
,
 
2
5
,
 
3
6
,
 
5
2
2
2
,
 
1
7
,
 
7
1
]
,

 
[
5
,

 
 
1
2
3
6
,

 
 
1
,

 
 
3
4
8
,

 
 
9
3
9
8
,

 
 
3
,

 
 
1
,

 
 
7
6
1
,

 
 
3
,

 
 
1
,

 
 
1
3
3
2
,

 
 
3
,

 
 
6
5
,

 
 
5
,

 
 
1
4
3
,

 
 
1
,

 
 
3
9
9
8
,

 
 
6
4
3
1
,

 
 
2
,

 
 
1
,

 
 
2
1
0
3
]
,

 
[
3
2
,

 
 
7
,

 
 
3
2
,

 
 
1
4
,

 
 
1
6
2
,

 
 
6
,

 
 
1
0
6
6
2
,

 
 
3
,

 
 
7
5
,

 
 
5
6
0
7
,

 
 
6
4
6
,

 
 
7
6
,

 
 
7
,

 
 
1
0
,

 
 
2
4
6
7
,

 
 
1
7
,

 
 
1
5
,

 
 
1
2
2
4
9
,

 
 
5
,

 
 
4
6
,

 
 
2
0
,

 
 
1
1
6
,

 
 
4
2
0
2
,

 
 
3
9
,

 
 
4
,

 
 
1
,

 
 
2
4
6
4
,

 
 
2
1
7
,

 
 
3
9
,

 
 
3
,

 
 
8
,

 
 
2
5
2
2
,

 
 
4
,

 
 
1
8
4
1
,

 
 
1
5
,

 
 
1
7
4
,

 
 
3
,

 
 
2
1
0
4
,

 
 
4
,

 
 
1
5
,

 
 
5
2
5
0
,

 
 
1
8
6
,

 
 
1
1
2
,

 
 
2
8
9
6
,

 
 
7
,

 
 
6
,

 
 
5
4
2
,

 
 
1
8
9
4
7
,

 
 
1
9
,

 
 
5
,

 
 
3
0
1
2
,

 
 
5
1
9
,

 
 
1
7
,

 
 
1
,

 
 
5
0
0
]
,

 
[
5
,
 
2
4
6
8
,
 
1
7
,
 
1
,
 
1
5
2
,
 
1
9
,
 
1
2
,
 
6
9
,
 
4
4
6
,
 
1
1
,
 
4
,
 
3
8
3
4
]
,

 
[
1
1
,

 
 
8
,

 
 
6
,

 
 
1
2
2
5
0
,

 
 
1
5
6
0
,

 
 
2
,

 
 
2
6
,

 
 
8
5
6
,

 
 
1
9
,

 
 
2
6
7
,

 
 
1
4
1
5
,

 
 
6
8
,

 
 
1
,

 
 
7
9
,

 
 
5
7
1
,

 
 
3
,

 
 
1
,

 
 
2
1
8
,

 
 
3
9
9
9
,

 
 
1
4
6
,

 
 
7
,

 
 
9
7
,

 
 
4
2
0
3
,

 
 
1
2
2
5
1
,

 
 
3
2
7
,

 
 
1
9
,

 
 
1
4
7
3
4
,

 
 
1
5
,

 
 
2
5
2
3
,

 
 
5
7
,

 
 
3
9
2
,

 
 
1
9
4
3
,

 
 
3
,

 
 
1
,

 
 
1
2
1
,

 
 
9
,

 
 
6
,

 
 
9
3
9
9
,

 
 
3
4
8
,

 
 
3
0
4
,

 
 
4
6
,

 
 
1
2
6
,

 
 
1
,

 
 
3
5
2
,

 
 
1
8
9
4
8
,

 
 
8
,

 
 
7
3
1
,

 
 
2
0
2
,

 
 
2
8
9
7
,

 
 
1
4
7
3
5
]
,

 
[
1
0
,

 
 
8
3
,

 
 
1
2
1
,

 
 
8
,

 
 
3
3
8
,

 
 
4
,

 
 
3
0
,

 
 
5
,

 
 
8
4
,

 
 
3
0
3
,

 
 
3
0
,

 
 
5
,

 
 
8
4
,

 
 
1
8
4
2
,

 
 
1
1
1
0
,

 
 
8
9
,

 
 
1
0
5
6
,

 
 
2
4
,

 
 
3
8
0
,

 
 
1
6
,

 
 
8
0
,

 
 
4
2
0
,

 
 
3
3
4
1
,

 
 
3
0
,

 
 
3
4
9
5
,

 
 
1
3
5
,

 
 
6
4
6
1
,

 
 
3
0
,

 
 
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
0
6
6
3
,

 
 
2
,

 
 
5
0
1
,

 
 
2
3
,

 
 
1
,

 
 
8
4
6
7
,

 
 
1
2
0
3
,

 
 
2
,

 
 
1
1
6
7
,

 
 
3
,

 
 
1
,

 
 
9
1
6
,

 
 
1
7
4
1
,

 
 
2
,

 
 
1
7
9
0
]
,

 
[
1
4
,

 
 
8
4
6
8
,

 
 
5
6
0
8
,

 
 
2
0
,

 
 
6
4
,

 
 
1
3
,

 
 
9
9
9
,

 
 
1
8
,

 
 
3
2
,

 
 
1
7
2
,

 
 
8
,

 
 
3
2
3
8
,

 
 
4
,

 
 
3
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

 
 
4
3
8
,

 
 
2
9
,

 
 
1
5
,

 
 
4
5
1
,

 
 
1
,

 
 
1
2
7
9
,

 
 
2
,

 
 
4
8
3
,

 
 
3
,

 
 
1
,

 
 
2
7
9
8
,

 
 
2
,

 
 
1
5
5
,

 
 
1
5
,

 
 
1
2
2
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
,

 
 
6
0
0
9
,

 
 
6
4
,

 
 
2
,

 
 
2
6
,

 
 
9
5
9
,

 
 
1
8
9
9
,

 
 
1
4
5
,

 
 
1
5
,

 
 
9
1
,

 
 
4
6
6
9
,

 
 
1
3
,

 
 
1
,

 
 
1
1
3
0
,

 
 
2
,

 
 
4
6
2
]
,

 
[
1
8
9
4
9
,

 
 
2
4
1
4
,

 
 
1
8
0
,

 
 
2
6
,

 
 
2
7
1
5
,

 
 
7
1
8
,

 
 
1
6
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
4
9
3
5
,

 
 
1
4
7
3
6
,

 
 
7
,

 
 
6
,

 
 
7
6
5
3
,

 
 
1
0
2
6
,

 
 
2
7
,

 
 
5
2
4
6
]
,

 
[
1
,

 
 
1
0
6
6
4
,

 
 
8
,

 
 
9
6
,

 
 
4
,

 
 
2
8
,

 
 
5
1
5
,

 
 
1
9
5
2
,

 
 
3
,

 
 
1
0
5
4
,

 
 
4
6
7
0
,

 
 
3
,

 
 
2
7
,

 
 
1
,

 
 
7
6
1
,

 
 
1
1
2
,

 
 
2
,

 
 
1
,

 
 
2
2
7
9
,

 
 
6
8
,

 
 
3
9
3
,

 
 
7
,

 
 
1
,

 
 
1
0
7
2
,

 
 
5
5
,

 
 
1
8
9
5
0
,

 
 
9
4
0
0
,

 
 
7
,

 
 
6
,

 
 
5
4
2
,

 
 
1
0
6
6
5
,

 
 
4
,

 
 
1
4
7
3
7
,

 
 
2
3
3
,

 
 
2
3
,

 
 
1
,

 
 
1
1
0
3
]
,

 
[
3
6
5
5
,
 
3
1
2
,
 
1
2
2
5
3
,
 
6
9
,
 
3
9
,
 
1
5
,
 
1
6
5
,
 
3
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
2
0
2
,

 
 
1
1
,

 
 
1
,

 
 
6
4
6
2
,

 
 
4
4
2
6
,

 
 
3
,

 
 
1
,

 
 
5
2
5
1
,

 
 
7
0
8
,

 
 
4
1
9
,

 
 
2
0
5
,

 
 
8
8
,

 
 
6
,

 
 
3
1
1
5
,

 
 
8
4
6
9
,

 
 
1
4
7
3
8
,

 
 
1
0
6
6
6
,

 
 
1
3
,

 
 
1
8
9
5
1
,

 
 
2
,

 
 
1
2
5
6
,

 
 
3
,

 
 
1
8
9
5
2
,

 
 
1
4
6
9
0
,

 
 
1
0
7
0
,

 
 
4
2
4
]
,

 
[
1
2
2
5
4
,

 
 
3
4
9
6
,

 
 
3
,

 
 
6
4
6
3
,

 
 
2
9
,

 
 
3
3
5
4
,

 
 
7
,

 
 
6
4
6
4
,

 
 
2
3
,

 
 
1
0
,

 
 
2
4
6
9
,

 
 
1
5
7
,

 
 
1
7
,

 
 
7
6
5
4
,

 
 
8
3
1
,

 
 
5
,

 
 
1
2
,

 
 
4
,

 
 
5
6
0
9
,

 
 
2
7
,

 
 
1
0
,

 
 
7
1
2
,

 
 
9
4
0
1
,

 
 
5
8
,

 
 
3
1
8
,

 
 
2
1
,

 
 
1
0
,

 
 
5
2
5
2
,

 
 
1
,

 
 
1
9
5
4
,

 
 
2
,

 
 
3
2
,

 
 
1
5
,

 
 
1
2
2
5
5
,

 
 
3
6
5
6
,

 
 
1
4
7
1
,

 
 
1
1
0
9
,

 
 
6
0
1
0
,

 
 
1
8
9
5
3
,

 
 
1
4
7
3
9
,

 
 
3
,

 
 
1
8
9
5
4
]
,

 
[
6
,

 
 
2
1
0
5
,

 
 
2
8
9
8
,

 
 
1
3
9
,

 
 
1
0
7
3
,

 
 
2
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
7
0
8
,

 
 
1
7
,

 
 
6
,

 
 
9
4
0
2
,

 
 
1
7
0
5
,

 
 
1
7
0
5
,

 
 
7
7
,

 
 
5
,

 
 
4
,

 
 
2
8
,

 
 
4
1
5
,

 
 
5
,

 
 
3
1
,

 
 
3
6
,

 
 
2
7
7
,

 
 
4
,

 
 
2
0
5
5
,

 
 
2
1
,

 
 
3
3
,

 
 
6
,

 
 
5
2
5
3
,

 
 
3
,

 
 
6
,

 
 
1
8
5
,

 
 
2
,

 
 
1
1
4
2
,

 
 
2
5
,

 
 
1
3
2
,

 
 
1
6
6
5
,

 
 
6
,

 
 
2
6
1
,

 
 
1
7
,

 
 
6
0
1
1
,

 
 
1
8
,

 
 
3
3
,

 
 
5
6
,

 
 
2
0
,

 
 
6
8
,

 
 
4
,

 
 
4
4
2
7
,

 
 
6
,

 
 
7
6
1
,

 
 
3
3
4
8
,

 
 
7
,

 
 
7
8
,

 
 
2
1
0
3
,

 
 
3
3
,

 
 
6
2
,

 
 
2
0
,

 
 
2
3
2
,

 
 
7
0
,

 
 
2
7
1
6
,

 
 
2
6
1
4
,

 
 
2
5
8
,

 
 
7
8
,

 
 
1
0
6
6
7
,

 
 
3
,

 
 
6
,

 
 
6
9
8
6
,

 
 
1
0
6
6
7
,

 
 
3
3
,

 
 
1
4
4
,

 
 
3
1
,

 
 
1
6
0
,

 
 
4
,

 
 
9
4
,

 
 
1
3
,

 
 
1
4
7
4
0
,

 
 
4
2
,

 
 
1
4
7
4
1
,

 
 
4
,

 
 
1
,

 
 
1
8
9
5
5
,

 
 
4
1
2
]
,

 
[
1
1
,

 
 
2
5
,

 
 
3
6
,

 
 
4
6
8
,

 
 
1
7
,

 
 
4
3
4
,

 
 
1
0
9
0
,

 
 
9
,

 
 
7
5
,

 
 
6
,

 
 
2
7
1
7
,

 
 
2
,

 
 
8
4
7
0
,

 
 
9
3
,

 
 
1
8
7
,

 
 
2
2
8
0
,

 
 
4
,

 
 
4
2
1
,

 
 
3
0
2
,

 
 
4
1
,

 
 
6
,

 
 
5
7
4
,

 
 
4
3
5
,

 
 
2
5
,

 
 
4
,

 
 
2
8
,

 
 
1
2
6
7
,

 
 
7
,

 
 
2
1
8
,

 
 
5
5
9
3
,

 
 
4
1
,

 
 
9
4
0
,

 
 
1
8
9
5
6
,

 
 
3
,

 
 
4
1
,

 
 
1
0
3
,

 
 
6
0
1
2
]
,

 
[
1
,

 
 
2
6
1
4
,

 
 
2
,

 
 
1
,

 
 
1
2
2
,

 
 
5
6
4
,

 
 
1
2
,

 
 
6
8
,

 
 
1
1
,

 
 
4
0
,

 
 
1
1
4
,

 
 
2
,

 
 
1
,

 
 
4
6
7
1
,

 
 
9
,

 
 
1
,

 
 
3
3
2
,

 
 
4
3
4
,

 
 
4
9
,

 
 
3
1
,

 
 
4
3
,

 
 
6
,

 
 
2
7
9
9
,

 
 
2
,

 
 
1
,

 
 
4
4
2
8
,

 
 
4
,

 
 
6
0
1
3
,

 
 
3
,

 
 
4
,

 
 
3
8
3
5
,

 
 
1
1
]
,

 
[
4
1
,

 
 
5
,

 
 
1
4
3
,

 
 
1
,

 
 
8
9
1
,

 
 
1
9
,

 
 
1
2
,

 
 
1
7
0
9
,

 
 
1
,

 
 
2
8
7
,

 
 
2
4
,

 
 
4
4
1
9
,

 
 
5
,

 
 
1
6
2
8
,

 
 
1
6
,

 
 
4
9
3
6
,

 
 
1
6
,

 
 
1
0
,

 
 
1
9
2
,

 
 
1
2
,

 
 
1
6
2
8
,

 
 
1
7
,

 
 
6
7
,

 
 
8
9
1
,

 
 
2
9
,

 
 
2
,

 
 
1
,

 
 
1
4
7
4
2
,

 
 
2
0
9
3
,

 
 
3
,

 
 
8
6
,

 
 
2
4
7
0
,

 
 
3
9
6
]
,

 
[
4
5
2
,
 
2
2
,
 
5
,
 
1
3
3
,
 
1
0
6
6
8
]
,

 
[
5
,
 
9
0
1
,
 
4
,
 
1
0
,
 
2
1
1
,
 
7
,
 
4
8
7
,
 
3
,
 
3
7
9
,
 
1
7
,
 
5
4
,
 
7
2
,
 
3
2
3
9
,
 
2
,
 
4
0
0
0
,
 
7
0
,
 
1
0
7
1
]
,

 
[
3
3
,
 
1
7
8
3
,
 
2
2
,
 
1
8
,
 
7
8
,
 
5
6
1
0
,
 
2
6
9
,
 
1
1
8
0
,
 
9
,
 
1
3
,
 
1
9
,
 
5
,
 
6
0
5
,
 
1
1
0
]
,

 
[
5
,

 
 
1
2
,

 
 
4
3
,

 
 
1
2
2
5
6
,

 
 
1
3
6
,

 
 
1
9
9
5
,

 
 
3
4
3
,

 
 
4
0
0
1
,

 
 
2
7
,

 
 
1
0
,

 
 
2
8
0
0
,

 
 
3
,

 
 
9
,

 
 
8
,

 
 
4
,

 
 
1
0
,

 
 
2
4
7
1
,

 
 
7
,

 
 
1
,

 
 
1
8
4
,

 
 
3
,

 
 
6
1
6
,

 
 
5
6
1
1
,

 
 
7
5
8
,

 
 
1
1
,

 
 
8
0
,

 
 
6
0
1
,

 
 
7
4
,

 
 
4
,

 
 
2
8
]
,

 
[
5
,

 
 
9
7
2
,

 
 
1
0
,

 
 
9
4
0
3
,

 
 
9
,

 
 
6
0
,

 
 
2
6
,

 
 
8
,

 
 
3
2
,

 
 
5
,

 
 
8
,

 
 
1
4
8
8
,

 
 
4
9
3
7
,

 
 
4
,

 
 
1
,

 
 
8
0
2
,

 
 
2
,

 
 
2
0
0
3
,

 
 
2
8
0
1
,

 
 
5
2
5
4
]
,

 
[
6
,

 
 
3
1
3
,

 
 
1
8
9
5
7
,

 
 
8
,

 
 
4
4
5
,

 
 
4
4
,

 
 
1
,

 
 
2
4
0
6
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

 
 
1
1
0
5
,

 
 
5
7
7
,

 
 
2
3
,

 
 
1
,

 
 
2
2
2
7
,

 
 
2
,

 
 
6
,

 
 
5
6
1
2
]
,

 
[
1
0
6
6
9
,
 
1
0
6
7
0
,
 
7
9
6
,
 
1
3
2
]
,

 
[
1
8
0
,

 
 
6
,

 
 
3
0
1
3
,

 
 
2
8
,

 
 
8
4
7
1
,

 
 
1
8
0
,

 
 
3
7
,

 
 
7
6
5
5
,

 
 
2
8
,

 
 
2
0
5
6
,

 
 
7
,

 
 
4
7
,

 
 
4
5
0
,

 
 
2
2
8
1
,

 
 
2
,

 
 
2
5
4
,

 
 
1
8
0
,

 
 
2
6
,

 
 
7
6
5
5
,

 
 
2
8
,

 
 
5
2
5
5
,

 
 
4
,

 
 
1
0
1
,

 
 
1
6
6
6
,

 
 
7
,

 
 
1
,

 
 
1
5
9
,

 
 
2
3
,

 
 
1
8
6
,

 
 
6
2
,

 
 
4
7
,

 
 
1
1
4
9
,

 
 
2
8
,

 
 
1
3
3
3
]
,

 
[
1
,
 
1
0
6
7
1
,
 
1
3
9
,
 
6
9
8
8
,
 
1
,
 
1
0
6
7
2
,
 
6
8
,
 
1
0
,
 
1
2
1
2
]
,

 
[
6
5
,
 
1
3
,
 
9
2
6
,
 
3
,
 
1
8
9
5
8
,
 
5
6
1
3
,
 
3
4
,
 
1
4
3
,
 
6
,
 
8
5
3
,
 
2
8
2
,
 
2
4
,
 
5
2
9
]
,

 
[
1
,
 
6
3
3
,
 
1
3
9
,
 
8
4
,
 
2
0
,
 
2
8
,
 
5
6
1
4
]
,

 
[
3
4
,
 
1
1
4
7
,
 
6
8
,
 
4
3
2
,
 
9
5
5
,
 
1
6
6
3
,
 
1
4
9
7
,
 
1
,
 
1
1
3
3
,
 
3
,
 
1
1
0
]
,

 
[
5
3
,

 
 
9
4
,

 
 
6
9
8
9
,

 
 
3
,

 
 
3
4
9
6
,

 
 
3
,

 
 
1
5
9
5
,

 
 
6
2
7
,

 
 
5
2
7
,

 
 
2
7
8
,

 
 
2
,

 
 
1
,

 
 
5
4
9
,

 
 
2
4
4
,

 
 
1
8
9
5
9
,

 
 
2
1
,

 
 
6
,

 
 
1
1
1
4
,

 
 
2
8
9
9
,

 
 
1
2
2
5
7
,

 
 
4
,

 
 
9
9
6
,

 
 
3
3
,

 
 
4
,

 
 
1
4
1
7
,

 
 
3
5
,

 
 
1
7
4
2
,

 
 
4
2
0
4
,

 
 
3
,

 
 
1
8
9
6
0
,

 
 
2
,

 
 
4
2
0
4
,

 
 
5
4
9
,

 
 
2
,

 
 
3
0
1
1
,

 
 
2
6
5
,

 
 
9
,

 
 
1
0
6
7
3
,

 
 
1
7
4
3
,

 
 
2
3
,

 
 
5
9
4
,

 
 
4
6
6
,

 
 
7
6
8
,

 
 
7
3
7
,

 
 
2
,

 
 
1
,

 
 
6
0
1
4
,

 
 
9
,

 
 
1
0
6
7
4
,

 
 
6
3
]
,

 
[
1
1
,
 
4
9
,
 
2
8
,
 
1
9
3
8
,
 
4
,
 
9
7
1
,
 
1
,
 
2
0
0
3
,
 
2
,
 
6
9
9
0
,
 
4
0
0
2
,
 
2
7
,
 
9
,
 
1
4
9
8
,
 
1
0
3
]
,

 
[
7
,

 
 
2
6
,

 
 
1
0
2
7
,

 
 
1
2
7
0
,

 
 
1
1
,

 
 
6
2
,

 
 
2
8
,

 
 
1
1
1
2
,

 
 
1
6
,

 
 
8
6
,

 
 
1
8
4
3
,

 
 
9
,

 
 
4
8
,

 
 
6
3
4
,

 
 
4
4
,

 
 
6
,

 
 
2
2
8
2
,

 
 
2
,

 
 
5
0
,

 
 
5
9
,

 
 
4
2
0
5
,

 
 
1
4
7
4
3
,

 
 
2
4
,

 
 
3
0
,

 
 
1
4
1
1
,

 
 
8
5
7
]
,

 
[
1
7
8
,

 
 
1
0
4
3
,

 
 
6
7
,

 
 
2
4
1
5
,

 
 
3
,

 
 
5
4
,

 
 
3
4
1
,

 
 
5
,

 
 
1
1
5
,

 
 
2
7
6
,

 
 
1
0
,

 
 
9
9
,

 
 
4
4
,

 
 
1
,

 
 
1
7
9
1
,

 
 
1
7
4
4
,

 
 
5
2
9
,

 
 
3
,

 
 
1
9
0
,

 
 
1
6
2
,

 
 
1
9
5
3
,

 
 
7
,

 
 
2
1
0
1
]
,

 
[
1
1
3
,

 
 
2
,

 
 
1
,

 
 
3
4
9
7
,

 
 
5
2
5
6
,

 
 
3
6
5
7
,

 
 
1
0
6
7
5
,

 
 
3
,

 
 
7
,

 
 
3
2
,

 
 
3
4
,

 
 
2
9
,

 
 
7
6
5
6
,

 
 
1
3
,

 
 
1
1
6
8
,

 
 
1
2
2
5
8
,

 
 
1
9
,

 
 
3
4
,

 
 
1
4
3
,

 
 
1
3
,

 
 
5
2
5
7
,

 
 
3
8
3
6
,

 
 
3
,

 
 
1
,

 
 
4
2
0
6
,

 
 
2
,

 
 
1
2
2
5
9
,

 
 
3
,

 
 
9
4
0
4
]
,

 
[
1
,
 
6
2
9
,
 
8
4
8
,
 
3
4
5
,
 
3
,
 
1
4
1
8
,
 
2
4
,
 
1
7
4
,
 
4
,
 
1
7
4
]
,

 
[
1
4
,

 
 
9
2
,

 
 
6
,

 
 
4
0
0
3
,

 
 
2
8
0
,

 
 
1
5
2
,

 
 
3
,

 
 
4
7
,

 
 
1
7
3
5
,

 
 
2
,

 
 
1
9
9
7
,

 
 
1
9
0
0
,

 
 
3
,

 
 
1
7
1
0
,

 
 
3
,

 
 
5
4
0
,

 
 
7
,

 
 
4
5
0
,

 
 
8
4
7
2
,

 
 
2
0
0
4
,

 
 
6
,

 
 
3
6
5
8
,

 
 
1
7
,

 
 
1
,

 
 
1
0
6
7
6
,

 
 
1
0
6
7
7
,

 
 
2
,

 
 
6
7
0
]
,

 
[
8
2
,

 
 
9
,

 
 
3
1
2
1
,

 
 
6
4
,

 
 
4
4
2
9
,

 
 
8
7
,

 
 
1
,

 
 
2
9
0
0
,

 
 
7
,

 
 
1
,

 
 
2
2
2
8
,

 
 
3
,

 
 
1
1
8
6
,

 
 
4
,

 
 
6
,

 
 
1
5
6
,

 
 
1
2
5
1
,

 
 
2
,

 
 
1
0
5
6
,

 
 
1
7
,

 
 
1
5
0
,

 
 
3
,

 
 
1
,

 
 
3
2
4
0
,

 
 
4
0
0
4
,

 
 
2
3
,

 
 
1
5
,

 
 
3
0
1
]
,

 
[
1
,

 
 
4
5
4
,

 
 
1
7
1
1
,

 
 
1
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
0
6
,

 
 
1
1
,

 
 
7
,

 
 
1
5
,

 
 
9
7
3
,

 
 
6
2
5
,

 
 
6
5
,

 
 
1
2
2
6
0
,

 
 
3
7
,

 
 
1
4
7
4
4
,

 
 
2
1
4
,

 
 
2
1
0
7
,

 
 
6
,

 
 
4
7
9
,

 
 
3
,

 
 
2
0
7
,

 
 
1
1
,

 
 
4
,

 
 
1
,

 
 
1
8
4
4
]
,

 
[
5
,

 
 
1
6
2
9
,

 
 
4
9
3
,

 
 
3
,

 
 
2
2
2
,

 
 
2
,

 
 
1
1
0
4
,

 
 
3
,

 
 
1
7
,

 
 
6
,

 
 
1
0
9
,

 
 
7
2
,

 
 
4
6
,

 
 
2
0
,

 
 
3
6
0
,

 
 
7
,

 
 
1
,

 
 
3
1
2
2
,

 
 
4
8
7
,

 
 
2
,

 
 
1
,

 
 
1
5
8
6
]
,

 
[
5
,

 
 
2
3
4
2
,

 
 
1
1
0
,

 
 
1
3
,

 
 
6
,

 
 
2
0
0
5
,

 
 
2
,

 
 
1
1
4
2
,

 
 
4
0
3
,

 
 
1
3
,

 
 
6
,

 
 
1
5
6
,

 
 
4
0
0
5
,

 
 
1
9
,

 
 
1
2
,

 
 
2
8
0
2
,

 
 
4
,

 
 
1
0
,

 
 
3
8
2
,

 
 
3
,

 
 
9
5
7
]
,

 
[
5
,

 
 
1
1
8
7
,

 
 
3
1
4
,

 
 
1
,

 
 
3
6
5
,

 
 
3
,

 
 
1
1
1
0
,

 
 
6
,

 
 
6
0
1
5
,

 
 
2
4
,

 
 
1
0
,

 
 
1
0
0
0
,

 
 
5
2
5
6
,

 
 
1
8
,

 
 
1
4
,

 
 
9
4
0
5
,

 
 
2
2
,

 
 
2
4
1
6
,

 
 
2
4
,

 
 
1
5
,

 
 
1
3
3
4
,

 
 
3
,

 
 
2
3
4
3
,

 
 
1
3
,

 
 
1
,

 
 
9
4
0
6
,

 
 
2
,

 
 
1
2
8
0
,

 
 
2
5
2
4
,

 
 
5
7
,

 
 
1
,

 
 
9
8
4
]
,

 
[
1
2
2
6
1
,

 
 
1
4
7
4
5
,

 
 
1
4
7
4
5
,

 
 
7
6
5
7
,

 
 
7
6
5
8
,

 
 
1
2
2
6
2
,

 
 
7
6
5
9
,

 
 
1
8
9
6
1
,

 
 
1
8
9
6
2
,

 
 
1
0
6
7
8
,

 
 
6
9
9
1
,

 
 
5
6
1
5
,

 
 
9
4
0
7
,

 
 
7
6
5
9
,

 
 
6
9
9
1
,

 
 
2
1
,

 
 
1
4
7
4
6
,

 
 
3
,

 
 
7
6
5
8
,

 
 
6
9
9
1
,

 
 
1
8
9
6
3
,

 
 
1
4
7
4
7
,

 
 
1
4
7
4
8
,

 
 
1
8
9
6
4
,

 
 
5
6
1
5
,

 
 
1
2
4
,

 
 
5
6
1
5
,

 
 
9
4
0
7
]
,

 
[
3
3
,
 
4
9
,
 
3
1
,
 
7
6
6
0
,
 
9
,
 
1
,
 
2
8
0
3
,
 
1
2
,
 
4
3
,
 
6
7
5
,
 
3
,
 
2
7
4
,
 
6
6
,
 
7
,
 
6
,
 
1
3
6
2
]
,

 
[
4
5
,
 
5
6
,
 
6
,
 
2
0
0
6
,
 
7
1
9
,
 
2
,
 
2
9
0
1
,
 
3
0
1
4
]
,

 
[
4
8
,

 
 
8
0
,

 
 
3
1
,

 
 
1
4
3
,

 
 
2
,

 
 
1
0
,

 
 
3
0
3
,

 
 
2
4
,

 
 
5
1
6
,

 
 
3
,

 
 
1
0
,

 
 
6
6
6
,

 
 
4
,

 
 
1
4
7
4
9
,

 
 
2
8
0
4
,

 
 
1
9
,

 
 
1
1
1
5
,

 
 
1
3
,

 
 
1
0
,

 
 
3
3
1
,

 
 
7
8
3
,

 
 
8
0
,

 
 
8
4
7
3
,

 
 
1
0
5
4
,

 
 
4
,

 
 
2
4
5
8
,

 
 
3
0
]
,

 
[
2
6
,

 
 
7
1
,

 
 
1
3
0
,

 
 
2
5
5
,

 
 
8
,

 
 
8
4
7
4
,

 
 
8
,

 
 
2
,

 
 
6
,

 
 
2
6
1
5
,

 
 
3
,

 
 
1
0
6
7
9
,

 
 
1
4
4
9
,

 
 
3
,

 
 
4
6
,

 
 
2
0
,

 
 
8
5
4
,

 
 
4
,

 
 
5
0
7
,

 
 
7
,

 
 
1
8
4
5
,

 
 
3
,

 
 
5
6
1
6
,

 
 
7
,

 
 
1
,

 
 
1
7
7
,

 
 
2
9
2
,

 
 
1
0
5
,

 
 
1
4
,

 
 
1
2
,

 
 
2
5
2
5
,

 
 
4
3
,

 
 
1
5
2
4
,

 
 
1
7
,

 
 
1
5
,

 
 
1
4
1
9
,

 
 
3
,

 
 
3
3
5
5
]
,

 
[
3
4
,
 
9
6
,
 
2
7
,
 
1
8
6
,
 
3
0
1
,
 
2
,
 
1
,
 
8
4
7
5
,
 
7
6
6
1
,
 
2
6
1
6
,
 
4
2
4
,
 
1
7
,
 
1
,
 
8
3
0
,
 
2
,
 
1
,
 
8
2
8
]
,

 
[
5
,

 
 
9
2
3
,

 
 
2
0
,

 
 
1
0
1
5
,

 
 
3
3
,

 
 
4
,

 
 
9
4
,

 
 
5
3
,

 
 
5
,

 
 
2
4
2
,

 
 
2
7
7
,

 
 
1
7
,

 
 
5
,

 
 
1
2
3
,

 
 
1
0
6
,

 
 
2
8
,

 
 
9
4
0
8
,

 
 
2
3
,

 
 
6
7
0
]
,

 
[
6
9
9
2
,

 
 
4
,

 
 
6
4
6
5
,

 
 
5
,

 
 
9
0
6
,

 
 
1
1
,

 
 
4
9
3
8
,

 
 
3
,

 
 
1
6
,

 
 
5
,

 
 
9
0
6
,

 
 
5
,

 
 
1
4
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
,

 
 
6
0
1
,

 
 
1
3
6
3
,

 
 
2
2
,

 
 
9
4
0
9
,

 
 
1
3
,

 
 
9
9
,

 
 
5
0
,

 
 
1
2
2
6
3
,

 
 
5
9
,

 
 
5
8
6
]
,

 
[
6
5
,

 
 
6
6
,

 
 
1
3
,

 
 
3
3
,

 
 
1
6
,

 
 
1
9
0
,

 
 
1
6
,

 
 
3
5
3
,

 
 
1
7
,

 
 
1
1
,

 
 
6
2
,

 
 
1
9
0
,

 
 
2
8
,

 
 
1
3
2
,

 
 
2
1
5
,

 
 
4
,

 
 
1
2
6
,

 
 
5
3
,

 
 
3
4
,

 
 
5
6
,

 
 
6
8
]
,

 
[
2
0
1
,

 
 
6
5
,

 
 
5
,

 
 
8
4
,

 
 
2
8
,

 
 
3
7
,

 
 
3
1
7
,

 
 
2
,

 
 
1
0
6
8
0
,

 
 
3
5
,

 
 
2
1
0
8
,

 
 
4
,

 
 
3
0
,

 
 
3
3
4
,

 
 
1
3
7
,

 
 
3
3
4
,

 
 
1
8
2
6
,

 
 
3
0
,

 
 
1
8
3
,

 
 
9
4
1
0
,

 
 
1
1
0
,

 
 
6
9
,

 
 
3
0
,

 
 
3
,

 
 
1
,

 
 
1
8
9
6
5
,

 
 
1
5
9
,

 
 
4
,

 
 
1
,

 
 
1
1
0
7
,

 
 
2
,

 
 
2
0
0
3
,

 
 
1
,

 
 
5
5
0
,

 
 
1
3
6
0
,

 
 
2
,

 
 
6
,

 
 
3
1
2
3
,

 
 
4
0
0
6
,

 
 
1
8
9
6
6
]
,

 
[
5
,

 
 
8
2
2
,

 
 
3
0
,

 
 
1
,

 
 
4
1
9
4
,

 
 
1
9
,

 
 
3
0
,

 
 
4
8
5
,

 
 
9
4
1
1
,

 
 
1
9
5
,

 
 
3
0
,

 
 
7
8
3
,

 
 
3
,

 
 
4
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
5
9
6
,

 
 
2
0
,

 
 
4
,

 
 
2
6
8
,

 
 
2
0
2
,

 
 
1
,

 
 
1
8
9
6
7
,

 
 
2
,

 
 
1
,

 
 
8
3
2
]
,

 
[
1
,

 
 
6
7
6
,

 
 
5
5
8
,

 
 
2
,

 
 
2
6
,

 
 
9
4
1
2
,

 
 
4
6
7
2
,

 
 
8
,

 
 
8
4
7
6
,

 
 
1
4
7
5
0
,

 
 
7
,

 
 
3
2
,

 
 
1
,

 
 
4
0
8
,

 
 
3
,

 
 
4
6
7
3
,

 
 
4
9
3
9
,

 
 
4
,

 
 
1
9
,

 
 
1
,

 
 
2
8
9
5
,

 
 
2
8
0
5
,

 
 
2
,

 
 
1
,

 
 
1
4
7
5
1
,

 
 
1
0
8
,

 
 
3
9
0
,

 
 
8
7
3
]
,

 
[
9
,

 
 
3
0
9
,

 
 
2
2
9
,

 
 
8
4
,

 
 
3
1
,

 
 
1
2
2
6
4
,

 
 
4
,

 
 
1
,

 
 
2
9
0
2
,

 
 
4
4
3
0
,

 
 
2
0
0
7
,

 
 
1
9
,

 
 
1
2
,

 
 
1
4
2
0
,

 
 
4
,

 
 
3
6
5
9
,

 
 
1
5
,

 
 
4
8
0
,

 
 
4
0
,

 
 
1
7
9
2
,

 
 
1
8
,

 
 
6
1
2
,

 
 
1
6
6
8
,

 
 
2
9
,

 
 
6
1
7
,

 
 
3
,

 
 
1
0
6
8
1
]
,

 
[
4
0
0
7
,
 
1
8
9
6
8
,
 
4
6
7
4
,
 
1
,
 
3
0
1
1
,
 
3
3
0
,
 
1
8
9
6
9
]
,

 
[
1
,

 
 
1
2
8
1
,

 
 
2
,

 
 
1
,

 
 
1
8
5
,

 
 
2
0
0
8
,

 
 
6
9
5
,

 
 
2
3
0
,

 
 
5
,

 
 
1
2
,

 
 
1
1
1
6
,

 
 
2
4
0
,

 
 
1
3
8
1
,

 
 
2
7
,

 
 
1
,

 
 
3
4
9
,

 
 
3
,

 
 
5
,

 
 
2
0
9
,

 
 
1
4
5
,

 
 
1
6
,

 
 
6
0
,

 
 
5
,

 
 
1
2
,

 
 
5
6
1
7
,

 
 
1
,

 
 
4
6
6
,

 
 
1
6
3
0
,

 
 
2
,

 
 
6
,

 
 
1
8
1
,

 
 
1
2
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
9
8
,

 
 
9
,

 
 
1
,

 
 
3
8
3
7
,

 
 
1
2
,

 
 
1
6
4
,

 
 
3
0
2
,

 
 
1
8
,

 
 
1
4
,

 
 
1
2
,

 
 
2
0
,

 
 
1
6
4
,

 
 
2
4
,

 
 
1
,

 
 
4
2
4
,

 
 
1
8
3
,

 
 
2
4
,

 
 
7
0
,

 
 
6
4
7
,

 
 
3
5
,

 
 
1
8
9
7
0
,

 
 
9
,

 
 
4
6
,

 
 
2
8
,

 
 
1
0
6
9
]
,

 
[
3
4
1
,
 
1
2
1
,
 
3
,
 
1
0
6
,
 
2
4
2
,
 
6
0
1
6
,
 
9
6
,
 
3
7
,
 
7
9
,
 
6
9
9
3
,
 
1
8
9
7
1
,
 
7
4
,
 
2
7
,
 
1
2
7
7
,
 
2
2
2
5
]
,

 
[
2
6
,

 
 
2
5
,

 
 
5
3
,

 
 
5
,

 
 
1
0
7
,

 
 
7
,

 
 
1
,

 
 
8
9
2
,

 
 
6
,

 
 
1
0
0
9
,

 
 
2
1
5
,

 
 
7
1
,

 
 
2
,

 
 
3
2
4
1
,

 
 
2
9
0
3
,

 
 
8
4
7
7
,

 
 
7
,

 
 
1
,

 
 
9
4
1
3
,

 
 
5
2
5
8
,

 
 
2
,

 
 
1
,

 
 
1
4
7
5
2
,

 
 
1
3
3
5
,

 
 
5
7
7
,

 
 
6
8
,

 
 
1
4
1
7
,

 
 
3
,

 
 
1
3
,

 
 
1
4
7
5
3
,

 
 
2
9
0
4
,

 
 
3
6
6
0
,

 
 
3
6
6
1
,

 
 
7
6
6
2
,

 
 
3
5
1
,

 
 
6
,

 
 
9
4
1
4
,

 
 
3
6
6
2
,

 
 
1
7
3
4
,

 
 
2
,

 
 
2
2
2
9
,

 
 
7
6
2
]
,

 
[
6
5
,

 
 
1
1
5
,

 
 
1
,

 
 
3
6
6
3
,

 
 
6
6
5
,

 
 
8
4
2
,

 
 
4
,

 
 
8
2
7
,

 
 
5
,

 
 
9
6
,

 
 
1
1
0
,

 
 
1
2
2
6
5
,

 
 
1
1
5
,

 
 
4
,

 
 
5
0
1
,

 
 
3
,

 
 
9
4
1
5
,

 
 
7
,

 
 
3
2
,

 
 
1
,

 
 
4
6
7
,

 
 
2
,

 
 
9
7
9
]
,

 
[
1
6
,

 
 
1
,

 
 
3
1
2
4
,

 
 
2
1
6
,

 
 
7
,

 
 
1
,

 
 
9
8
5
,

 
 
8
5
8
,

 
 
1
2
,

 
 
7
5
0
,

 
 
7
2
9
,

 
 
3
2
3
1
,

 
 
2
3
,

 
 
1
,

 
 
6
0
9
,

 
 
1
9
,

 
 
8
,

 
 
1
5
9
7
,

 
 
1
6
,

 
 
4
8
,

 
 
1
2
,

 
 
4
3
,

 
 
1
8
9
7
2
,

 
 
1
1
,

 
 
3
,

 
 
8
,

 
 
8
4
7
8
,

 
 
1
,

 
 
6
9
9
4
,

 
 
6
8
,

 
 
3
0
,

 
 
2
3
5
,

 
 
7
,

 
 
4
2
0
7
,

 
 
2
,

 
 
1
,

 
 
1
5
6
1
,

 
 
2
,

 
 
6
,

 
 
1
2
2
6
6
]
,

 
[
1
5
,

 
 
3
9
8
,

 
 
5
6
,

 
 
8
0
6
,

 
 
2
7
,

 
 
1
,

 
 
4
4
3
1
,

 
 
3
,

 
 
4
1
,

 
 
1
4
,

 
 
7
6
6
3
,

 
 
4
,

 
 
2
5
2
6
,

 
 
5
7
,

 
 
1
5
2
5
,

 
 
1
4
,

 
 
4
4
3
2
,

 
 
1
5
0
,

 
 
1
7
1
2
,

 
 
4
,

 
 
1
7
4
5
,

 
 
9
,

 
 
2
7
,

 
 
1
9
,

 
 
1
4
,

 
 
6
9
9
5
,

 
 
7
,

 
 
5
0
6
,

 
 
1
7
,

 
 
2
2
6
,

 
 
1
8
4
,

 
 
1
9
,

 
 
1
1
5
,

 
 
1
8
9
7
3
,

 
 
1
5
,

 
 
3
4
2
,

 
 
3
,

 
 
1
9
,

 
 
2
3
6
,

 
 
1
4
,

 
 
1
8
9
7
4
,

 
 
1
7
,

 
 
9
5
,

 
 
1
4
7
5
4
]
,

 
[
1
,
 
2
1
1
,
 
2
,
 
2
9
0
5
,
 
1
2
,
 
4
3
,
 
1
,
 
4
6
8
,
 
2
,
 
5
1
,
 
1
1
8
5
]
,

 
[
1
,
 
2
6
1
,
 
8
,
 
5
3
5
]
,

 
[
3
6
,

 
 
7
7
,

 
 
1
,

 
 
1
7
4
6
,

 
 
1
3
8
2
,

 
 
2
3
4
8
,

 
 
3
4
6
,

 
 
1
,

 
 
3
1
2
5
,

 
 
2
4
6
,

 
 
1
2
5
,

 
 
3
3
,

 
 
1
1
,

 
 
2
5
,

 
 
1
5
3
,

 
 
3
3
2
,

 
 
1
0
,

 
 
6
7
7
,

 
 
3
,

 
 
4
,

 
 
6
,

 
 
9
3
7
,

 
 
2
,

 
 
7
8
,

 
 
2
5
5
,

 
 
6
2
,

 
 
2
8
,

 
 
5
,

 
 
9
4
5
,

 
 
3
6
,

 
 
8
4
7
9
,

 
 
1
4
6
6
]
,

 
[
2
1
,
 
1
9
1
,
 
3
8
,
 
4
6
7
5
,
 
8
8
,
 
6
,
 
1
8
9
7
5
,
 
2
0
7
,
 
1
9
0
1
,
 
4
,
 
3
2
,
 
1
,
 
4
3
6
]
,

 
[
1
0
,

 
 
4
8
5
,

 
 
4
8
,

 
 
7
7
,

 
 
1
0
,

 
 
1
8
9
7
6
,

 
 
6
1
8
,

 
 
2
,

 
 
7
5
9
,

 
 
4
0
4
,

 
 
2
9
,

 
 
5
3
9
,

 
 
2
7
,

 
 
1
,

 
 
1
7
4
4
,

 
 
2
,

 
 
7
8
,

 
 
1
9
5
5
]
,

 
[
5
,
 
5
8
7
,
 
1
,
 
5
3
6
,
 
1
8
9
7
7
,
 
1
8
9
7
8
,
 
1
8
9
7
9
,
 
1
8
9
8
0
]
,

 
[
7
,
 
1
0
6
8
2
,
 
2
0
0
9
,
 
4
0
0
8
,
 
1
2
2
6
7
,
 
1
4
,
 
6
9
9
,
 
4
,
 
3
1
,
 
1
,
 
1
1
3
4
,
 
3
2
,
 
4
,
 
1
5
0
]
,

 
[
4
2
,

 
 
4
9
,

 
 
3
1
,

 
 
1
5
4
,

 
 
1
6
0
,

 
 
4
2
8
,

 
 
6
3
,

 
 
1
7
,

 
 
5
1
,

 
 
7
1
9
,

 
 
4
9
,

 
 
3
1
,

 
 
1
6
9
2
,

 
 
6
3
,

 
 
4
,

 
 
2
8
0
6
,

 
 
3
2
,

 
 
2
1
,

 
 
1
2
8
]
,

 
[
7
2
,
 
1
4
9
,
 
3
,
 
5
0
2
,
 
7
4
6
,
 
1
1
,
 
6
,
 
2
6
1
,
 
2
0
2
,
 
3
8
8
]
,

 
[
1
4
,

 
 
3
4
9
8
,

 
 
1
7
6
,

 
 
7
6
6
4
,

 
 
7
6
6
5
,

 
 
6
,

 
 
7
6
6
6
,

 
 
1
7
,

 
 
4
9
4
0
,

 
 
8
4
8
0
,

 
 
3
,

 
 
9
4
1
6
,

 
 
9
4
1
7
,

 
 
4
0
5
,

 
 
1
5
,

 
 
1
7
4
,

 
 
7
6
6
7
,

 
 
8
1
,

 
 
1
,

 
 
1
5
9
8
,

 
 
2
,

 
 
6
,

 
 
1
8
9
8
1
,

 
 
1
4
7
5
5
,

 
 
7
,

 
 
1
,

 
 
7
3
2
,

 
 
2
,

 
 
3
4
9
9
]
,

 
[
4
2
,

 
 
9
2
,

 
 
1
,

 
 
4
4
3
3
,

 
 
1
3
3
6
,

 
 
1
5
3
,

 
 
2
0
5
6
,

 
 
7
,

 
 
1
,

 
 
5
6
1
8
,

 
 
2
3
,

 
 
4
4
3
3
,

 
 
3
6
6
4
,

 
 
1
,

 
 
4
9
4
,

 
 
2
,

 
 
1
9
0
2
,

 
 
6
4
6
6
,

 
 
4
0
,

 
 
9
,

 
 
1
1
,

 
 
1
6
2
,

 
 
1
4
2
1
,

 
 
4
,

 
 
3
6
6
5
,

 
 
7
,

 
 
5
3
,

 
 
2
7
1
8
,

 
 
3
3
9
,

 
 
3
7
,

 
 
1
6
9
9
,

 
 
2
,

 
 
3
9
0
,

 
 
6
4
8
,

 
 
4
9
,

 
 
1
8
9
8
2
,

 
 
1
,

 
 
3
6
6
6
,

 
 
3
,

 
 
3
4
8
9
,

 
 
1
7
,

 
 
1
2
9
,

 
 
1
0
1
,

 
 
1
2
2
6
8
,

 
 
2
,

 
 
1
,

 
 
7
0
9
,

 
 
1
4
7
5
6
]
,

 
[
6
5
3
,
 
6
4
1
,
 
3
,
 
1
7
,
 
2
6
,
 
3
4
3
,
 
5
,
 
7
3
,
 
2
0
,
 
3
8
0
]
,

 
[
1
0
6
8
3
,

 
 
5
4
8
,

 
 
8
1
,

 
 
4
,

 
 
4
2
2
,

 
 
5
3
,

 
 
2
0
9
8
,

 
 
2
4
,

 
 
9
,

 
 
1
1
2
9
,

 
 
2
2
2
5
,

 
 
1
0
1
,

 
 
1
2
3
,

 
 
2
8
0
7
,

 
 
2
6
0
,

 
 
9
4
1
8
]
,

 
[
1
,

 
 
1
2
2
6
9
,

 
 
9
0
1
,

 
 
1
3
,

 
 
3
1
2
6
,

 
 
3
4
2
,

 
 
4
,

 
 
1
5
,

 
 
1
6
3
,

 
 
2
0
1
,

 
 
5
1
,

 
 
8
2
3
,

 
 
1
2
,

 
 
4
3
,

 
 
1
6
3
1
,

 
 
4
,

 
 
6
,

 
 
2
4
5
,

 
 
4
2
0
8
,

 
 
2
3
,

 
 
1
,

 
 
5
6
1
9
,

 
 
7
6
,

 
 
3
0
1
5
,

 
 
6
4
6
7
,

 
 
3
,

 
 
4
4
3
4
,

 
 
2
2
8
3
,

 
 
2
,

 
 
1
5
,

 
 
3
7
5
,

 
 
3
,

 
 
4
4
3
5
]
,

 
[
1
1
,
 
8
4
,
 
3
1
,
 
4
3
,
 
8
5
9
,
 
2
1
,
 
2
6
4
,
 
4
1
,
 
2
5
2
7
,
 
1
2
5
7
,
 
1
4
,
 
4
6
,
 
4
2
1
,
 
8
8
,
 
1
,
 
6
4
6
8
]
,

 
[
5
,

 
 
6
2
,

 
 
3
3
5
6
,

 
 
3
9
,

 
 
4
,

 
 
2
2
,

 
 
1
4
,

 
 
1
4
0
,

 
 
2
0
,

 
 
2
7
1
9
,

 
 
1
5
,

 
 
5
0
1
,

 
 
4
,

 
 
2
2
,

 
 
3
,

 
 
4
1
,

 
 
5
,

 
 
1
4
4
,

 
 
1
5
,

 
 
4
7
0
,

 
 
6
5
,

 
 
6
2
,

 
 
5
,

 
 
3
5
0
0
,

 
 
6
,

 
 
5
6
2
0
,

 
 
5
7
,

 
 
1
5
,

 
 
2
1
9
,

 
 
3
,

 
 
1
1
5
,

 
 
5
,

 
 
1
4
0
,

 
 
2
1
0
9
,

 
 
1
,

 
 
1
2
2
7
0
,

 
 
5
3
1
,

 
 
2
,

 
 
5
2
5
9
,

 
 
1
5
,

 
 
8
6
0
,

 
 
3
,

 
 
2
,

 
 
1
1
5
,

 
 
1
3
0
7
,

 
 
1
5
,

 
 
9
9
,

 
 
3
6
6
7
,

 
 
6
0
,

 
 
2
0
,

 
 
1
3
,

 
 
5
0
6
,

 
 
2
1
,

 
 
2
6
4
,

 
 
1
3
,

 
 
4
5
3
,

 
 
1
5
2
,

 
 
3
,

 
 
9
4
1
9
]
,

 
[
3
3
,
 
8
4
,
 
2
8
,
 
2
5
2
2
,
 
3
,
 
3
4
7
,
 
1
,
 
1
4
6
,
 
1
3
,
 
6
,
 
1
0
6
8
4
,
 
1
8
9
8
3
,
 
2
0
3
]
,

 
[
1
6
,

 
 
1
0
,

 
 
7
1
2
,

 
 
2
7
3
,

 
 
9
2
7
,

 
 
3
,

 
 
1
4
7
5
7
,

 
 
4
,

 
 
1
4
7
5
8
,

 
 
1
,

 
 
1
4
2
,

 
 
1
4
,

 
 
1
3
3
7
,

 
 
2
2
,

 
 
2
0
,

 
 
4
,

 
 
2
8
,

 
 
5
6
2
1
,

 
 
2
3
,

 
 
1
,

 
 
3
1
2
7
,

 
 
3
,

 
 
1
1
0
6
,

 
 
6
9
9
6
,

 
 
2
,

 
 
1
,

 
 
2
9
0
6
]
,

 
[
1
6
,

 
 
5
,

 
 
2
1
6
,

 
 
6
,

 
 
6
9
9
7
,

 
 
8
3
3
,

 
 
3
6
6
,

 
 
2
,

 
 
6
4
6
9
,

 
 
9
8
,

 
 
1
4
7
5
9
,

 
 
4
,

 
 
1
,

 
 
3
6
6
8
,

 
 
6
4
7
0
,

 
 
3
,

 
 
2
2
8
4
,

 
 
3
8
4
,

 
 
5
,

 
 
9
6
,

 
 
2
6
,

 
 
1
8
9
8
4
,

 
 
5
0
,

 
 
3
6
6
9
,

 
 
5
9
,

 
 
1
,

 
 
6
4
7
1
,

 
 
1
0
4
4
]
,

 
[
1
1
,

 
 
2
5
,

 
 
8
3
3
,

 
 
9
,

 
 
1
9
4
,

 
 
1
4
,

 
 
6
4
7
2
,

 
 
4
0
,

 
 
3
6
7
0
,

 
 
2
4
,

 
 
1
,

 
 
1
3
3
8
,

 
 
2
,

 
 
1
8
9
8
5
,

 
 
3
,

 
 
1
4
7
6
0
,

 
 
5
2
6
0
,

 
 
3
6
7
1
,

 
 
2
0
7
,

 
 
2
0
,

 
 
1
,

 
 
2
6
4
,

 
 
1
0
4
4
,

 
 
2
,

 
 
1
2
2
7
1
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
 
8
,
 
1
8
9
8
6
,
 
1
8
9
8
7
,
 
1
8
9
8
8
,
 
1
8
9
8
9
]
,

 
[
2
1
,

 
 
1
,

 
 
4
9
4
1
,

 
 
2
,

 
 
2
6
,

 
 
2
2
8
5
,

 
 
5
,

 
 
1
1
4
7
,

 
 
3
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
1
1
3
5
,

 
 
1
7
,

 
 
1
1
,

 
 
2
2
3
,

 
 
4
,

 
 
2
2
,

 
 
1
9
4
,

 
 
5
,

 
 
2
1
,

 
 
1
2
8
,

 
 
2
1
1
0
,

 
 
9
,

 
 
1
0
,

 
 
6
2
2
,

 
 
5
4
4
,

 
 
1
2
,

 
 
2
9
0
7
,

 
 
2
2
,

 
 
1
1
,

 
 
2
2
3
,

 
 
4
,

 
 
2
2
,

 
 
9
,

 
 
2
4
,

 
 
5
4
,

 
 
6
1
,

 
 
9
6
7
,

 
 
4
9
1
,

 
 
2
,

 
 
1
,

 
 
1
1
8
8
,

 
 
4
5
,

 
 
1
1
7
,

 
 
6
0
1
7
,

 
 
4
,

 
 
1
0
,

 
 
6
6
7
,

 
 
5
3
,

 
 
8
0
,

 
 
3
1
,

 
 
4
3
,

 
 
7
,

 
 
4
7
,

 
 
1
9
0
2
,

 
 
5
6
2
2
,

 
 
2
,

 
 
3
9
6
,

 
 
1
,

 
 
3
8
3
8
,

 
 
1
8
,

 
 
6
,

 
 
6
4
7
3
,

 
 
3
,

 
 
1
7
4
7
,

 
 
3
8
,

 
 
7
6
7
,

 
 
2
,

 
 
1
,

 
 
6
1
,

 
 
1
2
2
7
2
,

 
 
3
,

 
 
1
8
9
9
0
,

 
 
2
8
2
,

 
 
1
9
,

 
 
5
3
0
,

 
 
1
2
2
7
3
,

 
 
1
2
,

 
 
4
0
,

 
 
1
9
5
6
,

 
 
1
2
0
9
]
,

 
[
2
4
,

 
 
5
2
6
1
,

 
 
1
2
9
5
,

 
 
2
3
,

 
 
1
,

 
 
6
9
9
8
,

 
 
3
4
,

 
 
2
3
2
,

 
 
9
,

 
 
7
,

 
 
1
2
2
7
4
,

 
 
2
4
,

 
 
1
,

 
 
5
5
8
,

 
 
2
,

 
 
1
,

 
 
1
5
5
,

 
 
3
4
,

 
 
3
1
,

 
 
2
1
,

 
 
1
,

 
 
7
6
2
,

 
 
2
,

 
 
2
7
0
,

 
 
1
5
4
,

 
 
5
2
9
,

 
 
8
5
,

 
 
6
8
,

 
 
3
8
,

 
 
1
8
9
9
1
,

 
 
2
,

 
 
1
,

 
 
6
7
6
,

 
 
1
3
3
8
,

 
 
2
,

 
 
4
9
4
2
,

 
 
2
0
3
,

 
 
9
,

 
 
2
1
,

 
 
3
4
,

 
 
3
1
,

 
 
2
4
5
4
,

 
 
8
8
,

 
 
2
9
6
,

 
 
3
8
,

 
 
7
6
1
,

 
 
3
,

 
 
9
,

 
 
2
1
,

 
 
1
9
,

 
 
2
5
,

 
 
2
0
,

 
 
1
3
7
,

 
 
2
4
,

 
 
1
,

 
 
1
5
9
9
,

 
 
2
,

 
 
1
4
7
6
1
,

 
 
3
4
,

 
 
3
1
,

 
 
4
6
7
6
,

 
 
3
8
,

 
 
1
8
5
,

 
 
1
,

 
 
8
3
1
,

 
 
3
5
,

 
 
2
1
,

 
 
3
2
,

 
 
5
6
4
,

 
 
3
8
,

 
 
1
8
5
,

 
 
1
,

 
 
1
4
7
6
2
,

 
 
2
2
5
,

 
 
2
,

 
 
2
0
3
,

 
 
8
4
8
1
,

 
 
4
4
,

 
 
5
5
,

 
 
2
6
9
6
]
,

 
[
1
,

 
 
8
0
2
,

 
 
9
8
,

 
 
5
6
2
3
,

 
 
3
,

 
 
5
,

 
 
7
6
3
8
,

 
 
2
0
9
,

 
 
1
6
,

 
 
1
7
9
2
,

 
 
1
6
,

 
 
1
,

 
 
7
6
6
8
,

 
 
4
1
,

 
 
5
,

 
 
1
0
7
,

 
 
1
,

 
 
3
0
8
,

 
 
5
6
2
4
,

 
 
2
3
,

 
 
7
,

 
 
6
,

 
 
3
8
3
9
,

 
 
1
8
9
9
2
,

 
 
5
7
6
,

 
 
2
,

 
 
6
3
7
,

 
 
1
2
2
7
5
,

 
 
3
,

 
 
6
,

 
 
7
6
1
0
,

 
 
2
4
7
2
,

 
 
2
4
,

 
 
1
4
9
,

 
 
4
,

 
 
1
4
9
,

 
 
4
0
0
9
,

 
 
3
,

 
 
2
5
2
8
,

 
 
2
3
,

 
 
7
6
6
9
,

 
 
3
,

 
 
5
5
8
,

 
 
8
4
4
]
,

 
[
5
,
 
1
9
0
,
 
5
8
4
,
 
2
1
,
 
1
,
 
3
1
2
8
,
 
1
,
 
1
7
1
,
 
8
,
 
6
0
1
8
]
,

 
[
5
8
,
 
3
5
,
 
5
3
,
 
6
5
,
 
8
,
 
1
0
,
 
1
0
2
,
 
1
0
2
,
 
3
0
1
6
]
,

 
[
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
5
,

 
 
8
,

 
 
2
0
9
,

 
 
1
8
9
9
3
,

 
 
2
3
,

 
 
2
1
3
,

 
 
1
8
,

 
 
1
0
,

 
 
1
3
2
7
,

 
 
4
4
7
,

 
 
3
,

 
 
5
,

 
 
2
4
7
3
,

 
 
6
,

 
 
1
5
9
5
,

 
 
4
,

 
 
2
1
1
1
,

 
 
2
2
,

 
 
7
,

 
 
8
9
3
,

 
 
1
5
,

 
 
5
2
8
]
,

 
[
5
,

 
 
4
6
,

 
 
1
3
,

 
 
5
0
6
,

 
 
3
1
,

 
 
1
1
1
6
,

 
 
1
,

 
 
5
9
7
,

 
 
3
,

 
 
4
7
,

 
 
1
0
0
8
,

 
 
3
,

 
 
3
1
,

 
 
1
8
9
9
4
,

 
 
1
1
0
,

 
 
1
3
,

 
 
5
1
,

 
 
2
8
0
8
,

 
 
3
,

 
 
4
6
7
]
,

 
[
5
,
 
1
9
5
7
,
 
3
6
,
 
3
3
3
]
,

 
[
3
5
0
1
,
 
6
8
,
 
1
,
 
2
9
1
]
,

 
[
4
8
,
 
2
,
 
1
,
 
3
6
7
2
,
 
1
6
7
,
 
3
,
 
1
,
 
4
9
4
3
,
 
6
0
9
]
,

 
[
1
8
3
,
 
8
,
 
7
0
,
 
4
3
0
,
 
4
,
 
2
8
,
 
6
7
5
,
 
7
3
8
,
 
7
,
 
9
,
 
1
4
1
,
 
1
7
,
 
6
,
 
1
2
3
7
,
 
3
,
 
6
,
 
1
8
5
]
,

 
[
6
5
,
 
1
6
,
 
2
8
0
9
,
 
9
0
7
,
 
1
,
 
9
0
0
,
 
2
7
3
,
 
4
,
 
5
8
0
]
,

 
[
5
,

 
 
8
2
1
,

 
 
7
,

 
 
3
8
,

 
 
2
,

 
 
3
0
,

 
 
1
8
9
9
5
,

 
 
1
0
3
8
,

 
 
6
,

 
 
1
4
7
6
3
,

 
 
2
,

 
 
5
8
1
,

 
 
1
2
,

 
 
2
7
2
0
,

 
 
3
0
,

 
 
4
,

 
 
2
1
1
2
,

 
 
3
,

 
 
3
6
7
3
]
,

 
[
4
7
,
 
8
4
8
2
,
 
4
,
 
1
,
 
9
9
,
 
1
9
,
 
2
9
,
 
4
,
 
7
8
9
,
 
1
1
,
 
4
4
,
 
1
5
5
]
,

 
[
2
1
,

 
 
3
6
4
,

 
 
3
0
,

 
 
2
3
5
6
,

 
 
1
6
2
,

 
 
1
0
6
8
5
,

 
 
3
,

 
 
1
7
,

 
 
1
0
9
,

 
 
4
2
0
9
,

 
 
4
8
,

 
 
4
9
,

 
 
9
2
6
,

 
 
3
0
0
6
,

 
 
1
3
8
3
,

 
 
1
9
,

 
 
1
2
2
7
6
,

 
 
3
0
,

 
 
1
0
6
8
6
,

 
 
3
5
0
2
,

 
 
1
9
4
5
,

 
 
1
3
,

 
 
1
5
,

 
 
1
8
4
6
,

 
 
1
4
7
6
4
,

 
 
2
4
1
0
,

 
 
7
,

 
 
1
8
9
9
6
,

 
 
4
4
3
6
,

 
 
2
2
0
,

 
 
1
,

 
 
1
8
4
,

 
 
1
3
3
9
,

 
 
8
0
4
]
,

 
[
4
5
,
 
1
2
,
 
4
3
,
 
1
6
0
,
 
8
1
,
 
5
4
7
,
 
3
5
,
 
2
2
8
1
]
,

 
[
1
1
,
 
8
,
 
1
,
 
6
4
7
4
,
 
1
0
6
8
7
,
 
1
3
9
,
 
9
,
 
7
3
,
 
8
6
,
 
4
,
 
5
7
2
,
 
2
2
,
 
1
8
9
9
7
]
,

 
[
1
,

 
 
5
3
7
,

 
 
8
,

 
 
2
0
,

 
 
6
1
,

 
 
2
6
2
,

 
 
1
8
,

 
 
6
4
3
,

 
 
1
6
,

 
 
1
8
9
,

 
 
1
6
,

 
 
9
,

 
 
2
,

 
 
1
,

 
 
2
2
3
0
,

 
 
2
6
1
7
,

 
 
1
,

 
 
1
4
6
,

 
 
1
9
,

 
 
1
2
,

 
 
3
1
2
9
,

 
 
2
,

 
 
2
2
9
,

 
 
3
,

 
 
1
3
2
9
,

 
 
6
,

 
 
2
8
2
]
,

 
[
6
8
,

 
 
1
2
2
,

 
 
3
0
8
,

 
 
8
2
,

 
 
2
6
,

 
 
2
7
1
5
,

 
 
3
4
,

 
 
1
4
3
,

 
 
1
,

 
 
3
7
7
,

 
 
2
0
4
,

 
 
3
,

 
 
6
9
,

 
 
1
0
3
,

 
 
1
,

 
 
8
6
1
,

 
 
1
2
5
8
,

 
 
3
,

 
 
6
9
9
9
,

 
 
5
5
,

 
 
7
2
6
]
,

 
[
1
7
4
8
,

 
 
5
,

 
 
8
,

 
 
3
6
,

 
 
2
3
5
7
,

 
 
1
7
4
9
,

 
 
2
1
,

 
 
1
,

 
 
6
4
7
5
,

 
 
4
8
6
,

 
 
1
3
,

 
 
1
0
,

 
 
1
8
4
0
,

 
 
1
2
2
7
7
,

 
 
1
7
,

 
 
6
,

 
 
1
2
2
7
8
,

 
 
6
4
7
6
,

 
 
1
2
2
7
8
,

 
 
5
9
,

 
 
5
,

 
 
1
2
2
7
9
,

 
 
9
7
,

 
 
1
5
2
6
,

 
 
1
,

 
 
1
2
5
9
,

 
 
2
,

 
 
1
9
,

 
 
1
2
,

 
 
2
9
4
,

 
 
6
,

 
 
2
6
1
,

 
 
4
0
,

 
 
7
0
0
0
,

 
 
4
,

 
 
1
0
,

 
 
8
0
0
]
,

 
[
1
,
 
7
1
3
,
 
4
5
8
,
 
5
5
,
 
1
0
7
4
,
 
1
3
6
,
 
1
8
9
9
8
]
,

 
[
5
,

 
 
6
2
,

 
 
2
0
,

 
 
2
2
7
0
,

 
 
6
7
,

 
 
7
6
0
9
,

 
 
1
7
,

 
 
5
,

 
 
3
1
,

 
 
3
6
,

 
 
2
7
7
,

 
 
4
,

 
 
4
1
4
,

 
 
6
3
,

 
 
5
0
,

 
 
2
0
1
,

 
 
1
,

 
 
3
6
7
4
,

 
 
2
,

 
 
9
7
9
,

 
 
4
4
,

 
 
1
9
,

 
 
4
2
,

 
 
5
6
,

 
 
5
9
7
5
,

 
 
5
6
,

 
 
5
1
0
,

 
 
2
,

 
 
6
2
6
,

 
 
1
8
3
0
,

 
 
4
,

 
 
2
8
,

 
 
7
6
7
0
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
,

 
 
1
2
1
3
,

 
 
3
,

 
 
2
0
1
,

 
 
5
,

 
 
4
6
,

 
 
2
0
,

 
 
4
0
1
0
,

 
 
4
,

 
 
1
8
7
,

 
 
6
3
,

 
 
5
2
6
2
,

 
 
4
,

 
 
1
,

 
 
1
2
7
3
,

 
 
2
,

 
 
2
1
0
]
,

 
[
1
,
 
8
5
5
,
 
2
4
0
,
 
4
0
1
1
,
 
3
,
 
2
1
6
2
,
 
4
8
,
 
1
2
,
 
8
4
8
3
]
,

 
[
1
,

 
 
1
9
4
3
,

 
 
2
9
,

 
 
2
3
,

 
 
3
6
,

 
 
2
8
5
,

 
 
1
9
0
3
,

 
 
1
2
7
,

 
 
1
6
3
2
,

 
 
1
3
,

 
 
1
2
2
8
0
,

 
 
7
0
0
1
,

 
 
3
1
3
0
,

 
 
2
,

 
 
2
7
2
1
,

 
 
1
4
7
6
5
,

 
 
1
5
2
7
,

 
 
5
4
,

 
 
2
,

 
 
1
9
,

 
 
2
2
3
,

 
 
4
,

 
 
2
8
,

 
 
2
4
1
7
,

 
 
1
0
0
,

 
 
3
4
1
,

 
 
9
8
,

 
 
6
0
1
9
]
,

 
[
3
8
7
,

 
 
1
,

 
 
4
6
7
7
,

 
 
1
0
5
,

 
 
4
5
,

 
 
2
9
,

 
 
3
6
,

 
 
5
2
4
,

 
 
5
,

 
 
4
6
,

 
 
1
2
6
,

 
 
8
7
,

 
 
1
,

 
 
1
2
2
8
1
,

 
 
1
3
6
4
,

 
 
3
,

 
 
8
5
2
,

 
 
1
,

 
 
9
4
2
0
,

 
 
2
,

 
 
6
5
4
,

 
 
2
7
,

 
 
1
,

 
 
2
1
1
3
,

 
 
1
5
7
,

 
 
1
,

 
 
3
2
8
,

 
 
8
,

 
 
2
6
1
8
,

 
 
7
,

 
 
1
,

 
 
2
1
5
]
,

 
[
2
0
5
7
,

 
 
1
1
,

 
 
2
9
9
,

 
 
4
4
,

 
 
2
2
,

 
 
1
0
,

 
 
4
2
7
,

 
 
9
8
6
,

 
 
4
1
6
,

 
 
3
,

 
 
4
0
,

 
 
2
3
,

 
 
1
0
3
1
,

 
 
6
1
,

 
 
1
0
3
2
,

 
 
5
,

 
 
9
2
,

 
 
6
6
,

 
 
1
0
,

 
 
1
3
8
,

 
 
4
,

 
 
2
3
4
,

 
 
1
,

 
 
9
1
,

 
 
2
,

 
 
1
,

 
 
7
9
,

 
 
7
1
,

 
 
3
,

 
 
1
3
1
,

 
 
3
0
1
7
,

 
 
1
1
0
,

 
 
2
,

 
 
1
,

 
 
3
1
1
,

 
 
8
0
6
]
,

 
[
4
4
,

 
 
2
6
,

 
 
1
0
9
1
,

 
 
3
4
,

 
 
9
3
,

 
 
3
1
,

 
 
4
3
,

 
 
1
7
0
9
,

 
 
7
4
,

 
 
4
,

 
 
2
0
4
,

 
 
7
,

 
 
1
4
9
2
,

 
 
2
,

 
 
1
5
6
2
,

 
 
1
7
,

 
 
1
,

 
 
1
2
2
8
2
,

 
 
7
1
1
,

 
 
8
5
,

 
 
5
7
6
,

 
 
3
,

 
 
5
7
6
,

 
 
4
0
,

 
 
1
7
9
2
,

 
 
9
,

 
 
2
1
,

 
 
1
9
1
,

 
 
3
4
,

 
 
1
8
9
9
9
,

 
 
5
5
,

 
 
5
6
2
5
,

 
 
3
,

 
 
2
1
1
4
,

 
 
1
1
,

 
 
6
0
,

 
 
1
1
,

 
 
1
2
,

 
 
2
0
,

 
 
4
3
,

 
 
9
,

 
 
3
4
,

 
 
4
2
1
0
,

 
 
5
7
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
2
1
0
0
,

 
 
2
1
1
5
,

 
 
7
0
0
2
,

 
 
1
2
4
,

 
 
4
,

 
 
1
1
2
,

 
 
3
,

 
 
4
2
9
,

 
 
4
,

 
 
1
6
3
3
,

 
 
1
9
,

 
 
2
5
2
9
,

 
 
8
5
,

 
 
1
7
5
,

 
 
1
,

 
 
5
2
6
3
,

 
 
2
,

 
 
1
4
7
6
6
,

 
 
1
0
5
,

 
 
2
3
,

 
 
1
8
9
,

 
 
5
2
6
4
,

 
 
3
4
,

 
 
2
7
4
,

 
 
6
6
]
,

 
[
1
9
0
0
,

 
 
3
,

 
 
3
0
1
8
,

 
 
3
1
,

 
 
1
0
8
4
,

 
 
4
2
3
,

 
 
4
0
1
2
,

 
 
8
7
,

 
 
2
2
,

 
 
9
4
2
1
,

 
 
6
7
5
,

 
 
1
3
,

 
 
2
2
,

 
 
1
0
,

 
 
4
9
,

 
 
8
,

 
 
1
7
,

 
 
1
2
9
,

 
 
7
6
7
1
,

 
 
2
3
,

 
 
1
,

 
 
1
4
0
,

 
 
2
0
,

 
 
2
,

 
 
6
7
,

 
 
1
0
,

 
 
1
4
7
6
7
]
,

 
[
1
,
 
5
6
2
6
,
 
7
,
 
1
0
,
 
4
9
4
4
,
 
3
9
1
,
 
1
7
9
]
,

 
[
3
5
6
,
 
4
1
9
,
 
1
,
 
2
9
0
8
]
,

 
[
1
,
 
8
4
8
4
,
 
2
7
,
 
5
5
,
 
1
8
8
,
 
1
6
2
,
 
6
1
,
 
1
0
2
]
,

 
[
7
6
,

 
 
4
8
,

 
 
2
1
1
6
,

 
 
2
7
,

 
 
3
,

 
 
1
0
6
,

 
 
2
7
,

 
 
1
4
7
6
8
,

 
 
2
7
5
,

 
 
4
8
,

 
 
1
0
7
,

 
 
9
,

 
 
1
,

 
 
4
0
1
3
,

 
 
5
8
,

 
 
1
2
,

 
 
2
4
5
,

 
 
5
6
2
7
,

 
 
2
1
4
,

 
 
6
,

 
 
8
4
8
5
,

 
 
3
,

 
 
1
0
2
8
,

 
 
5
0
6
,

 
 
7
,

 
 
1
5
,

 
 
8
0
2
,

 
 
3
,

 
 
2
0
5
6
,

 
 
1
1
2
,

 
 
3
,

 
 
1
0
3
,

 
 
4
,

 
 
7
6
7
2
,

 
 
3
0
,

 
 
5
8
,

 
 
4
0
,

 
 
4
9
7
,

 
 
3
9
,

 
 
7
6
,

 
 
5
8
,

 
 
3
2
4
,

 
 
1
2
8
2
,

 
 
5
0
,

 
 
1
0
6
8
8
,

 
 
3
,

 
 
1
3
0
8
]
,

 
[
3
3
,

 
 
2
7
,

 
 
1
5
5
,

 
 
3
1
,

 
 
7
6
7
3
,

 
 
1
4
5
,

 
 
4
7
,

 
 
5
5
1
,

 
 
5
6
1
,

 
 
3
3
,

 
 
5
8
,

 
 
1
3
6
,

 
 
1
4
7
2
,

 
 
7
6
7
4
,

 
 
2
0
7
,

 
 
4
,

 
 
4
7
,

 
 
1
0
6
8
9
,

 
 
7
6
7
5
,

 
 
1
,

 
 
2
5
5
,

 
 
2
,

 
 
1
4
7
6
9
,

 
 
1
,

 
 
1
7
1
3
,

 
 
1
1
4
3
]
,

 
[
2
3
9
,
 
5
6
2
8
,
 
1
0
,
 
2
0
1
0
,
 
3
,
 
6
0
2
0
,
 
1
0
,
 
4
6
7
8
,
 
2
1
5
8
,
 
1
4
7
3
,
 
2
3
9
]
,

 
[
1
1
5
,
 
6
,
 
3
1
3
1
,
 
3
6
7
5
,
 
2
,
 
6
,
 
7
0
0
3
,
 
3
6
5
0
,
 
1
7
1
,
 
3
,
 
1
1
5
,
 
6
,
 
1
0
6
4
6
,
 
2
9
0
9
]
,

 
[
1
,

 
 
2
9
3
,

 
 
5
8
8
,

 
 
1
3
,

 
 
6
,

 
 
4
6
7
9
,

 
 
9
8
7
,

 
 
2
3
5
8
,

 
 
3
,

 
 
5
2
6
5
,

 
 
6
,

 
 
6
1
,

 
 
1
5
6
,

 
 
1
0
3
1
,

 
 
2
2
4
,

 
 
1
,

 
 
1
2
0
4
,

 
 
6
4
7
7
,

 
 
3
6
,

 
 
5
2
2
6
,

 
 
1
5
8
]
,

 
[
1
,

 
 
1
4
5
0
,

 
 
8
,

 
 
4
1
6
,

 
 
3
,

 
 
4
4
,

 
 
3
8
4
0
,

 
 
1
0
,

 
 
1
1
1
,

 
 
1
7
4
,

 
 
5
,

 
 
1
2
,

 
 
6
1
0
,

 
 
6
,

 
 
3
4
7
7
,

 
 
8
7
,

 
 
1
0
,

 
 
7
0
0
4
,

 
 
9
4
2
2
,

 
 
2
0
5
8
,

 
 
1
1
,

 
 
2
0
5
,

 
 
4
4
,

 
 
2
5
3
0
,

 
 
1
,

 
 
3
0
9
,

 
 
2
,

 
 
1
1
3
2
]
,

 
[
1
2
0
,
 
1
1
4
,
 
8
,
 
1
,
 
1
7
8
7
,
 
1
6
6
9
,
 
7
3
,
 
3
3
,
 
1
2
5
,
 
6
5
6
,
 
1
0
5
7
]
,

 
[
5
,

 
 
8
,

 
 
1
0
6
,

 
 
2
0
6
,

 
 
1
7
,

 
 
1
6
,

 
 
1
1
4
,

 
 
1
6
,

 
 
5
,

 
 
9
2
8
,

 
 
1
,

 
 
3
9
2
,

 
 
2
4
3
,

 
 
5
,

 
 
5
4
0
,

 
 
4
5
,

 
 
8
,

 
 
5
0
,

 
 
2
1
3
,

 
 
7
,

 
 
1
,

 
 
1
2
1
,

 
 
2
,

 
 
2
5
3
1
,

 
 
4
9
4
5
]
,

 
[
5
,

 
 
9
4
,

 
 
2
0
,

 
 
1
9
4
2
,

 
 
3
5
,

 
 
2
5
1
7
,

 
 
1
8
,

 
 
5
,

 
 
8
4
,

 
 
3
4
3
,

 
 
1
3
,

 
 
1
1
0
,

 
 
3
,

 
 
5
6
5
,

 
 
1
1
0
,

 
 
4
,

 
 
2
9
7
,

 
 
6
2
8
,

 
 
3
,

 
 
3
8
0
]
,

 
[
5
5
,
 
8
3
4
,
 
8
,
 
5
2
,
 
1
0
9
,
 
1
3
8
4
,
 
7
6
7
6
,
 
3
,
 
2
8
8
4
,
 
1
4
7
7
0
]
,

 
[
1
4
,

 
 
1
8
2
,

 
 
1
4
2
,

 
 
1
4
,

 
 
1
8
4
7
,

 
 
9
2
3
,

 
 
3
1
8
,

 
 
5
7
,

 
 
9
,

 
 
4
4
3
7
,

 
 
1
2
2
8
3
,

 
 
3
5
,

 
 
9
,

 
 
9
4
2
3
,

 
 
2
4
1
8
,

 
 
2
,

 
 
1
,

 
 
2
6
1
8
,

 
 
1
5
9
]
,

 
[
1
0
6
9
0
,

 
 
2
1
6
,

 
 
1
6
8
,

 
 
3
,

 
 
2
3
3
,

 
 
5
5
0
,

 
 
3
2
4
0
,

 
 
8
4
8
6
,

 
 
1
6
,

 
 
1
4
,

 
 
5
3
2
,

 
 
2
7
,

 
 
3
2
4
0
,

 
 
2
1
,

 
 
1
2
9
6
,

 
 
4
0
5
,

 
 
1
3
4
,

 
 
9
6
,

 
 
3
9
,

 
 
3
8
,

 
 
1
0
3
,

 
 
7
,

 
 
1
,

 
 
2
2
2
8
,

 
 
8
8
4
,

 
 
3
1
2
1
,

 
 
8
,

 
 
2
8
1
0
,

 
 
1
9
0
0
0
]
,

 
[
2
2
2
6
,

 
 
1
0
,

 
 
2
1
6
3
,

 
 
3
1
,

 
 
4
3
,

 
 
2
6
7
,

 
 
9
2
,

 
 
4
,

 
 
1
0
6
9
1
,

 
 
7
,

 
 
1
3
,

 
 
1
,

 
 
6
0
2
,

 
 
1
9
0
0
1
,

 
 
2
,

 
 
1
0
,

 
 
1
9
0
0
2
]
,

 
[
4
,

 
 
2
6
,

 
 
7
1
,

 
 
2
2
8
6
,

 
 
2
9
8
,

 
 
1
6
,

 
 
4
,

 
 
4
0
,

 
 
1
1
3
,

 
 
3
4
1
,

 
 
8
4
8
7
,

 
 
6
2
4
,

 
 
2
7
8
,

 
 
2
2
,

 
 
1
0
5
,

 
 
5
,

 
 
1
2
3
,

 
 
2
3
2
,

 
 
3
0
1
9
,

 
 
1
,

 
 
2
2
7
,

 
 
2
,

 
 
9
0
2
,

 
 
3
,

 
 
8
4
8
8
,

 
 
1
0
5
,

 
 
8
4
8
9
,

 
 
1
,

 
 
1
2
2
8
4
,

 
 
9
4
2
4
,

 
 
3
,

 
 
1
0
5
,

 
 
1
,

 
 
3
0
2
0
,

 
 
2
,

 
 
1
,

 
 
2
9
1
0
,

 
 
1
2
2
8
5
,

 
 
3
0
2
1
,

 
 
4
,

 
 
4
4
3
8
,

 
 
4
2
1
1
,

 
 
3
,

 
 
6
1
5
,

 
 
1
9
0
0
3
,

 
 
1
3
,

 
 
1
4
7
7
1
,

 
 
3
7
3
]
,

 
[
2
9
,
 
5
,
 
1
4
7
7
2
,
 
1
4
,
 
7
7
,
 
8
9
,
 
6
,
 
1
9
0
0
4
,
 
4
9
,
 
4
4
3
9
,
 
2
2
]
,

 
[
7
,

 
 
1
0
,

 
 
2
0
5
9
,

 
 
1
,

 
 
2
1
1
7
,

 
 
1
4
1
,

 
 
8
,

 
 
1
9
0
3
,

 
 
1
3
,

 
 
2
8
1
1
,

 
 
5
2
6
6
,

 
 
3
,

 
 
3
3
5
,

 
 
7
9
,

 
 
3
7
3
,

 
 
1
0
9
,

 
 
4
2
1
2
,

 
 
6
2
3
,

 
 
9
1
3
,

 
 
3
,

 
 
1
9
0
0
5
,

 
 
1
0
6
9
2
,

 
 
3
5
0
3
,

 
 
7
,

 
 
1
,

 
 
2
4
5
,

 
 
1
2
2
8
6
,

 
 
2
1
1
8
,

 
 
1
0
5
,

 
 
1
4
2
2
,

 
 
9
0
,

 
 
3
3
5
7
]
,

 
[
1
4
,

 
 
9
6
,

 
 
1
0
,

 
 
2
5
5
,

 
 
6
,

 
 
1
8
9
,

 
 
1
9
0
0
6
,

 
 
4
,

 
 
1
4
7
7
3
,

 
 
3
,

 
 
1
4
,

 
 
1
2
,

 
 
3
2
4
2
,

 
 
1
7
,

 
 
2
2
,

 
 
1
,

 
 
9
1
7
,

 
 
2
,

 
 
2
2
8
7
,

 
 
1
0
6
9
3
,

 
 
4
,

 
 
1
,

 
 
9
4
2
5
,

 
 
2
1
,

 
 
7
0
0
5
,

 
 
1
0
5
,

 
 
5
,

 
 
9
3
,

 
 
9
8
8
,

 
 
2
7
,

 
 
1
0
,

 
 
2
6
1
9
,

 
 
1
7
5
,

 
 
1
,

 
 
4
2
0
,

 
 
9
4
2
6
]
,

 
[
4
5
,

 
 
2
9
,

 
 
2
4
1
9
,

 
 
2
3
9
,

 
 
5
,

 
 
4
9
,

 
 
3
1
,

 
 
4
3
,

 
 
1
3
0
9
,

 
 
4
,

 
 
1
8
0
,

 
 
1
,

 
 
1
0
2
6
,

 
 
2
4
7
4
,

 
 
8
5
,

 
 
2
4
1
9
,

 
 
2
3
9
,

 
 
5
,

 
 
9
6
,

 
 
1
,

 
 
2
4
7
5
,

 
 
2
,

 
 
4
4
4
0
,

 
 
3
,

 
 
1
,

 
 
4
4
4
1
,

 
 
2
,

 
 
3
8
9
,

 
 
5
0
,

 
 
3
,

 
 
5
0
,

 
 
1
2
2
8
7
,

 
 
1
8
,

 
 
4
1
,

 
 
1
4
,

 
 
1
2
,

 
 
4
2
9
,

 
 
4
,

 
 
1
9
0
0
7
,

 
 
3
,

 
 
8
8
,

 
 
6
,

 
 
1
4
7
7
4
,

 
 
6
6
5
,

 
 
2
0
1
1
,

 
 
6
,

 
 
1
8
8
5
,

 
 
5
6
2
9
,

 
 
1
6
,

 
 
4
9
3
5
,

 
 
5
,

 
 
4
6
,

 
 
2
0
,

 
 
3
0
2
2
,

 
 
1
,

 
 
7
0
0
6
,

 
 
3
6
7
6
,

 
 
2
,

 
 
3
8
,

 
 
8
2
0
,

 
 
9
,

 
 
5
,

 
 
9
3
,

 
 
2
1
1
1
,

 
 
3
9
,

 
 
7
,

 
 
1
0
,

 
 
5
3
3
,

 
 
2
7
2
2
]
,

 
[
1
8
,

 
 
2
7
,

 
 
3
3
,

 
 
6
4
,

 
 
1
2
,

 
 
5
,

 
 
7
0
,

 
 
2
6
0
5
,

 
 
1
7
,

 
 
1
8
4
8
,

 
 
3
,

 
 
1
9
0
0
8
,

 
 
3
,

 
 
2
4
,

 
 
3
3
,

 
 
5
,

 
 
8
2
0
,

 
 
4
,

 
 
6
7
1
,

 
 
9
,

 
 
2
2
3
1
,

 
 
1
9
,

 
 
5
,

 
 
3
0
2
3
,

 
 
2
4
6
2
,

 
 
4
,

 
 
2
0
6
0
,

 
 
2
4
,

 
 
7
0
,

 
 
9
5
,

 
 
1
2
7
,

 
 
9
,

 
 
1
3
8
5
,

 
 
1
,

 
 
1
8
1
,

 
 
2
5
4
]
,

 
[
5
,

 
 
2
4
2
0
,

 
 
4
,

 
 
2
4
2
,

 
 
9
,

 
 
3
2
,

 
 
2
6
,

 
 
3
6
7
7
,

 
 
8
,

 
 
1
8
,

 
 
5
0
,

 
 
4
9
4
6
,

 
 
9
4
2
7
,

 
 
3
,

 
 
9
,

 
 
2
3
,

 
 
1
9
0
0
9
,

 
 
1
5
,

 
 
6
9
4
,

 
 
1
4
7
7
5
,

 
 
7
6
7
7
,

 
 
9
4
6
,

 
 
1
0
,

 
 
7
0
0
7
,

 
 
3
,

 
 
5
6
3
0
,

 
 
1
2
2
8
8
,

 
 
1
4
,

 
 
1
2
2
8
9
,

 
 
2
0
,

 
 
1
5
,

 
 
4
9
0
8
,

 
 
1
8
,

 
 
1
5
,

 
 
1
2
2
9
0
]
,

 
[
5
,
 
6
2
,
 
2
0
,
 
1
9
0
4
,
 
3
3
3
,
 
5
9
,
 
5
,
 
8
4
3
,
 
2
7
,
 
6
7
,
 
4
9
4
7
,
 
5
0
2
]
,

 
[
1
4
7
7
6
,

 
 
1
1
,

 
 
2
4
0
,

 
 
6
8
,

 
 
1
2
2
,

 
 
7
9
0
,

 
 
8
4
9
0
,

 
 
2
,

 
 
1
,

 
 
1
4
7
4
,

 
 
2
,

 
 
1
2
6
0
,

 
 
5
6
2
,

 
 
3
,

 
 
1
9
7
,

 
 
7
9
0
,

 
 
2
4
,

 
 
1
,

 
 
3
0
2
4
,

 
 
1
0
6
9
4
,

 
 
1
1
8
8
]
,

 
[
1
1
7
9
,
 
4
1
7
,
 
1
0
5
7
,
 
2
5
,
 
6
,
 
2
6
2
0
,
 
7
1
,
 
3
,
 
6
,
 
7
1
,
 
2
,
 
2
7
0
7
]
,

 
[
4
4
,
 
2
2
8
8
,
 
7
7
,
 
5
,
 
1
0
2
4
,
 
3
,
 
3
2
,
 
4
8
,
 
6
5
6
]
,

 
[
5
,

 
 
1
4
3
,

 
 
1
,

 
 
4
0
2
,

 
 
2
8
1
,

 
 
2
4
,

 
 
1
,

 
 
1
0
6
9
5
,

 
 
9
,

 
 
4
4
,

 
 
1
5
,

 
 
1
4
7
5
,

 
 
1
4
,

 
 
1
2
,

 
 
4
3
,

 
 
7
,

 
 
6
,

 
 
8
6
,

 
 
3
3
5
,

 
 
3
2
9
,

 
 
2
,

 
 
1
3
8
,

 
 
1
4
,

 
 
1
2
,

 
 
2
2
1
,

 
 
1
,

 
 
8
3
,

 
 
1
0
3
,

 
 
7
,

 
 
1
,

 
 
1
3
8
6
,

 
 
1
5
2
8
,

 
 
2
7
,

 
 
1
,

 
 
1
7
0
4
,

 
 
9
1
3
,

 
 
1
4
,

 
 
7
3
,

 
 
2
0
,

 
 
3
6
0
,

 
 
1
8
,

 
 
7
0
0
8
,

 
 
3
0
2
5
]
,

 
[
6
5
,
 
1
,
 
2
8
0
4
,
 
2
,
 
1
,
 
3
6
5
0
,
 
1
7
1
,
 
4
,
 
1
0
,
 
1
7
4
,
 
8
,
 
3
1
3
2
,
 
5
9
5
]
,

 
[
2
6
,
 
1
2
,
 
9
0
8
,
 
4
3
,
 
3
5
7
,
 
1
3
,
 
1
,
 
3
7
4
,
 
2
,
 
6
4
7
8
,
 
2
2
,
 
2
4
,
 
3
6
0
]
,

 
[
1
1
,

 
 
8
,

 
 
2
1
,

 
 
2
6
,

 
 
1
9
9
,

 
 
9
,

 
 
1
5
,

 
 
9
9
,

 
 
3
,

 
 
5
8
1
,

 
 
2
3
6
,

 
 
2
9
9
,

 
 
4
4
,

 
 
1
,

 
 
7
0
0
9
,

 
 
2
,

 
 
2
3
5
9
,

 
 
1
9
,

 
 
5
,

 
 
6
5
,

 
 
7
5
6
,

 
 
4
,

 
 
2
8
,

 
 
5
8
2
]
,

 
[
2
7
,

 
 
1
5
,

 
 
1
7
1
4
,

 
 
2
9
,

 
 
1
,

 
 
2
8
1
2
,

 
 
2
,

 
 
7
6
7
8
,

 
 
3
2
1
,

 
 
3
,

 
 
2
7
,

 
 
1
5
,

 
 
1
5
4
,

 
 
7
6
7
9
,

 
 
8
,

 
 
6
,

 
 
5
6
3
1
,

 
 
2
1
6
4
,

 
 
5
9
8
2
]
,

 
[
1
5
6
2
,

 
 
2
5
,

 
 
1
7
5
0
,

 
 
7
,

 
 
6
3
,

 
 
1
9
,

 
 
4
4
4
2
,

 
 
1
9
0
5
,

 
 
4
,

 
 
1
0
,

 
 
1
5
2
0
,

 
 
1
5
6
3
,

 
 
1
,

 
 
1
6
5
,

 
 
1
4
1
6
,

 
 
2
,

 
 
9
,

 
 
1
5
1
0
,

 
 
2
,

 
 
4
6
8
0
,

 
 
5
0
2
,

 
 
1
9
,

 
 
1
1
0
5
,

 
 
1
1
,

 
 
2
5
,

 
 
3
2
0
,

 
 
7
,

 
 
3
7
4
,

 
 
1
,

 
 
7
6
8
0
,

 
 
1
6
3
4
,

 
 
2
,

 
 
1
0
,

 
 
4
9
4
8
,

 
 
3
,

 
 
2
2
8
9
,

 
 
3
0
4
,

 
 
2
5
,

 
 
3
9
0
,

 
 
7
,

 
 
8
1
1
,

 
 
1
9
,

 
 
1
7
5
1
,

 
 
7
8
,

 
 
1
1
1
,

 
 
1
3
8
3
,

 
 
3
,

 
 
7
4
6
,

 
 
5
8
1
,

 
 
1
0
6
4
1
]
,

 
[
4
1
,

 
 
3
4
,

 
 
4
7
3
,

 
 
2
6
,

 
 
6
8
4
,

 
 
1
6
6
3
,

 
 
2
7
6
,

 
 
4
,

 
 
1
4
9
7
,

 
 
3
,

 
 
6
5
6
,

 
 
3
9
,

 
 
6
0
,

 
 
1
4
,

 
 
1
2
1
,

 
 
1
4
,

 
 
4
6
,

 
 
2
9
1
1
,

 
 
1
1
]
,

 
[
5
,

 
 
2
0
7
,

 
 
3
9
,

 
 
1
8
4
0
,

 
 
2
9
6
,

 
 
1
,

 
 
1
7
7
,

 
 
3
8
3
,

 
 
2
,

 
 
1
0
,

 
 
6
0
4
,

 
 
2
9
1
2
,

 
 
1
6
,

 
 
5
,

 
 
1
2
,

 
 
3
9
0
,

 
 
4
,

 
 
1
5
,

 
 
4
3
7
,

 
 
1
2
5
4
]
,

 
[
1
3
1
,

 
 
8
,

 
 
5
,

 
 
1
5
4
,

 
 
4
,

 
 
6
4
7
9
,

 
 
2
7
,

 
 
1
1
0
,

 
 
1
6
,

 
 
1
,

 
 
6
4
,

 
 
1
8
1
,

 
 
6
9
5
,

 
 
1
6
1
,

 
 
1
,

 
 
1
0
2
,

 
 
1
2
2
9
1
,

 
 
3
,

 
 
7
,

 
 
1
0
,

 
 
9
2
6
,

 
 
8
1
7
,

 
 
1
0
,

 
 
1
3
8
,

 
 
2
7
3
,

 
 
4
,

 
 
2
3
6
0
,

 
 
4
7
,

 
 
6
3
7
,

 
 
1
4
7
7
7
,

 
 
2
8
0
,

 
 
1
,

 
 
4
9
4
9
,

 
 
3
3
5
8
,

 
 
4
,

 
 
2
9
4
,

 
 
2
0
9
,

 
 
8
4
9
1
,

 
 
4
,

 
 
1
,

 
 
6
6
9
,

 
 
1
9
,

 
 
4
0
,

 
 
1
1
3
,

 
 
2
,

 
 
1
0
,

 
 
3
2
4
3
,

 
 
1
2
,

 
 
5
6
3
]
,

 
[
1
6
,

 
 
1
,

 
 
7
2
0
,

 
 
2
3
3
,

 
 
2
7
,

 
 
1
0
,

 
 
9
0
4
,

 
 
9
8
,

 
 
4
,

 
 
1
7
4
5
,

 
 
5
1
,

 
 
1
2
7
8
,

 
 
1
3
4
0
,

 
 
1
4
1
,

 
 
4
2
,

 
 
1
5
2
9
,

 
 
5
1
,

 
 
9
4
2
8
,

 
 
3
,

 
 
2
7
3
,

 
 
6
,

 
 
1
9
3
7
,

 
 
7
6
8
1
,

 
 
2
7
,

 
 
1
,

 
 
2
1
5
1
,

 
 
1
6
3
5
,

 
 
2
,

 
 
1
2
1
,

 
 
4
9
5
0
,

 
 
1
,

 
 
1
2
7
4
,

 
 
1
3
,

 
 
1
8
4
,

 
 
1
2
5
0
,

 
 
3
,

 
 
1
0
6
9
6
,

 
 
3
2
4
4
,

 
 
1
0
6
9
7
,

 
 
9
,

 
 
7
3
5
,

 
 
1
2
,

 
 
9
6
0
,

 
 
4
9
5
1
]
,

 
[
5
,

 
 
1
4
7
6
,

 
 
1
7
,

 
 
1
0
,

 
 
1
1
0
9
,

 
 
1
3
,

 
 
4
0
1
4
,

 
 
2
8
1
3
,

 
 
6
0
,

 
 
4
2
,

 
 
2
9
,

 
 
6
4
8
0
,

 
 
5
,

 
 
8
,

 
 
6
5
5
,

 
 
3
,

 
 
1
7
2
8
,

 
 
2
3
,

 
 
6
,

 
 
3
5
0
,

 
 
8
9
1
,

 
 
3
,

 
 
4
1
,

 
 
4
2
,

 
 
5
8
4
,

 
 
3
,

 
 
5
,

 
 
1
0
7
,

 
 
1
,

 
 
1
4
7
7
8
,

 
 
2
,

 
 
8
1
3
,

 
 
3
5
,

 
 
1
0
,

 
 
2
1
1
,

 
 
5
,

 
 
6
5
8
,

 
 
7
0
1
,

 
 
4
,

 
 
3
7
0
,

 
 
3
,

 
 
3
6
7
8
,

 
 
1
0
,

 
 
6
6
9
]
,

 
[
1
1
,
 
2
5
,
 
5
2
,
 
7
0
5
,
 
3
5
,
 
1
4
7
7
9
,
 
4
,
 
3
0
7
]
,

 
[
1
8
,

 
 
7
5
,

 
 
7
,

 
 
2
6
,

 
 
1
9
0
6
,

 
 
1
9
9
,

 
 
1
0
,

 
 
1
1
8
1
,

 
 
2
4
3
,

 
 
8
,

 
 
2
2
6
,

 
 
1
9
0
7
,

 
 
2
4
,

 
 
1
,

 
 
8
5
0
,

 
 
1
7
3
0
,

 
 
2
,

 
 
1
0
,

 
 
1
9
0
1
0
]
,

 
[
2
4
7
6
,

 
 
1
9
0
1
1
,

 
 
2
0
5
,

 
 
8
4
9
2
,

 
 
1
9
0
1
2
,

 
 
6
3
0
,

 
 
7
5
,

 
 
1
,

 
 
1
8
4
,

 
 
8
5
7
,

 
 
2
6
0
,

 
 
1
,

 
 
4
2
0
,

 
 
2
,

 
 
5
5
,

 
 
1
4
7
8
0
,

 
 
8
4
9
3
,

 
 
6
,

 
 
1
9
0
1
3
,

 
 
7
,

 
 
1
,

 
 
1
0
2
6
,

 
 
2
,

 
 
3
5
,

 
 
2
9
0
,

 
 
1
3
,

 
 
1
,

 
 
1
9
0
1
4
,

 
 
1
0
6
9
8
,

 
 
2
6
0
,

 
 
1
,

 
 
1
9
0
1
5
,

 
 
1
2
6
8
,

 
 
2
8
8
,

 
 
2
,

 
 
1
3
7
7
,

 
 
7
2
1
,

 
 
1
9
0
1
6
]
,

 
[
3
8
,

 
 
8
2
4
,

 
 
5
2
6
7
,

 
 
1
1
2
,

 
 
4
1
,

 
 
1
,

 
 
2
9
3
,

 
 
1
2
,

 
 
1
4
7
8
1
,

 
 
5
4
,

 
 
2
,

 
 
4
7
,

 
 
6
4
2
7
,

 
 
2
8
6
,

 
 
5
,

 
 
8
3
5
,

 
 
7
,

 
 
1
,

 
 
8
3
2
,

 
 
1
3
,

 
 
1
0
,

 
 
3
7
5
]
,

 
[
2
9
1
3
,
 
7
8
,
 
2
6
2
1
,
 
2
5
,
 
3
2
4
5
]
,

 
[
3
2
,
 
8
7
,
 
1
,
 
2
2
2
5
,
 
2
6
0
,
 
1
4
7
1
9
,
 
6
6
,
 
1
,
 
2
1
1
3
,
 
5
7
,
 
1
,
 
8
4
9
4
]
,

 
[
2
1
,
 
2
6
,
 
7
2
,
 
6
7
7
,
 
2
0
8
,
 
4
4
7
,
 
2
4
,
 
1
2
3
5
]
,

 
[
5
6
3
2
,

 
 
3
,

 
 
2
7
1
,

 
 
7
3
,

 
 
2
0
,

 
 
4
0
1
5
,

 
 
1
0
,

 
 
4
2
7
,

 
 
1
8
3
,

 
 
1
2
8
3
,

 
 
5
6
3
3
,

 
 
3
1
3
3
,

 
 
2
2
,

 
 
1
3
,

 
 
4
5
3
,

 
 
3
3
6
]
,

 
[
1
,
 
6
0
2
1
,
 
5
0
3
,
 
2
4
,
 
1
,
 
1
5
5
,
 
2
5
,
 
7
,
 
5
7
6
,
 
1
9
9
3
,
 
7
9
0
]
,

 
[
5
,

 
 
8
1
4
,

 
 
8
4
9
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
9
,

 
 
2
7
8
8
,

 
 
6
8
,

 
 
2
2
,

 
 
3
,

 
 
8
,

 
 
1
2
9
,

 
 
2
7
,

 
 
1
,

 
 
8
5
2
,

 
 
4
,

 
 
1
3
4
1
,

 
 
8
4
9
6
,

 
 
3
,

 
 
2
3
,

 
 
6
7
,

 
 
2
8
5
,

 
 
1
6
2
4
,

 
 
6
,

 
 
4
7
8
,

 
 
4
9
9
,

 
 
2
,

 
 
2
2
9
0
]
,

 
[
2
6
,

 
 
9
6
1
,

 
 
1
3
,

 
 
1
,

 
 
1
4
2
3
,

 
 
2
,

 
 
1
0
,

 
 
9
4
2
9
,

 
 
3
,

 
 
1
3
,

 
 
1
,

 
 
5
0
,

 
 
1
6
6
5
,

 
 
1
4
2
3
,

 
 
2
,

 
 
1
0
,

 
 
6
0
9
,

 
 
1
,

 
 
1
6
5
,

 
 
2
,

 
 
1
9
,

 
 
1
2
,

 
 
4
3
,

 
 
1
4
7
8
2
,

 
 
2
0
5
,

 
 
2
3
,

 
 
1
,

 
 
4
4
0
,

 
 
1
4
7
8
3
,

 
 
2
2
,

 
 
4
,

 
 
1
6
6
5
,

 
 
1
6
6
8
,

 
 
4
0
,

 
 
9
,

 
 
5
0
4
,

 
 
5
,

 
 
9
2
,

 
 
6
6
,

 
 
1
0
,

 
 
1
3
8
,

 
 
4
,

 
 
2
3
4
,

 
 
6
,

 
 
5
5
3
]
,

 
[
1
6
,

 
 
6
7
,

 
 
1
2
6
7
,

 
 
1
,

 
 
1
6
3
6
,

 
 
5
3
6
,

 
 
2
,

 
 
1
0
,

 
 
9
2
9
,

 
 
4
2
,

 
 
2
0
1
2
,

 
 
2
2
,

 
 
1
6
,

 
 
8
8
3
,

 
 
1
8
,

 
 
4
4
,

 
 
1
1
3
6
,

 
 
4
,

 
 
1
0
,

 
 
3
0
1
,

 
 
5
1
,

 
 
1
8
3
4
,

 
 
1
5
3
0
,

 
 
2
2
,

 
 
1
3
,

 
 
1
,

 
 
2
4
9
,

 
 
2
,

 
 
2
8
0
8
,

 
 
4
6
8
1
,

 
 
3
,

 
 
9
5
,

 
 
3
6
7
9
,

 
 
2
4
7
7
,

 
 
2
,

 
 
4
6
1
,

 
 
2
,

 
 
2
4
3
,

 
 
3
5
,

 
 
2
,

 
 
1
0
7
0
0
]
,

 
[
4
0
,

 
 
5
7
9
,

 
 
3
5
0
4
,

 
 
3
,

 
 
7
,

 
 
3
0
6
,

 
 
3
5
0
5
,

 
 
7
4
5
,

 
 
8
8
,

 
 
6
,

 
 
1
5
1
0
,

 
 
2
,

 
 
4
0
1
6
,

 
 
2
5
,

 
 
1
,

 
 
1
8
4
9
,

 
 
2
,

 
 
1
,

 
 
4
2
1
3
,

 
 
9
,

 
 
1
1
,

 
 
2
5
,

 
 
2
3
,

 
 
3
6
,

 
 
2
8
5
,

 
 
5
3
5
,

 
 
9
,

 
 
5
,

 
 
8
,

 
 
1
5
3
,

 
 
1
,

 
 
8
3
,

 
 
9
4
3
0
,

 
 
1
,

 
 
6
1
,

 
 
8
3
,

 
 
3
,

 
 
8
3
0
,

 
 
9
4
3
0
,

 
 
5
8
,

 
 
1
2
,

 
 
1
2
9
,

 
 
4
9
5
2
,

 
 
4
7
,

 
 
2
1
1
9
]
,

 
[
7
,
 
6
4
8
1
,
 
1
4
,
 
9
5
7
,
 
2
1
,
 
1
2
8
,
 
3
,
 
1
6
,
 
2
3
4
8
,
 
1
6
,
 
1
4
,
 
1
2
,
 
3
1
5
]
,

 
[
3
,

 
 
3
8
,

 
 
5
8
,

 
 
4
1
9
,

 
 
1
,

 
 
1
6
6
,

 
 
8
,

 
 
3
3
5
9
,

 
 
7
,

 
 
6
,

 
 
1
2
2
9
2
,

 
 
1
4
7
8
4
,

 
 
2
5
3
,

 
 
3
2
4
6
,

 
 
3
,

 
 
1
0
7
0
1
,

 
 
1
2
2
9
3
,

 
 
3
,

 
 
1
2
,

 
 
6
,

 
 
1
0
7
8
,

 
 
1
4
5
,

 
 
3
8
4
1
,

 
 
8
4
9
7
,

 
 
2
7
,

 
 
1
,

 
 
5
2
6
8
,

 
 
1
4
6
,

 
 
9
,

 
 
1
4
5
1
,

 
 
1
7
,

 
 
6
,

 
 
1
6
7
]
,

 
[
3
4
,

 
 
4
6
,

 
 
2
0
,

 
 
6
1
4
,

 
 
9
,

 
 
2
5
,

 
 
4
,

 
 
1
2
5
,

 
 
3
4
,

 
 
4
6
,

 
 
2
0
,

 
 
3
1
,

 
 
1
1
1
2
,

 
 
1
2
,

 
 
1
,

 
 
3
5
0
6
,

 
 
2
,

 
 
2
6
,

 
 
1
9
0
1
7
,

 
 
1
2
2
1
5
,

 
 
1
2
9
,

 
 
1
9
0
1
8
,

 
 
2
2
9
,

 
 
3
4
,

 
 
4
6
,

 
 
2
0
,

 
 
3
1
,

 
 
1
1
1
2
,

 
 
7
,

 
 
5
3
,

 
 
2
5
6
,

 
 
1
1
,

 
 
8
0
,

 
 
2
8
,

 
 
9
2
,

 
 
4
,

 
 
1
6
3
7
,

 
 
1
,

 
 
7
1
7
,

 
 
2
,

 
 
1
4
2
4
,

 
 
3
6
1
,

 
 
1
0
7
0
2
,

 
 
3
5
,

 
 
1
4
7
7
]
,

 
[
1
,

 
 
1
0
5
8
,

 
 
1
7
5
,

 
 
1
,

 
 
5
0
2
,

 
 
8
,

 
 
2
0
9
7
,

 
 
1
7
,

 
 
7
,

 
 
1
,

 
 
4
6
2
,

 
 
2
,

 
 
6
,

 
 
5
6
0
5
,

 
 
4
3
9
,

 
 
1
2
4
,

 
 
1
0
,

 
 
5
5
0
,

 
 
2
5
0
8
,

 
 
1
2
,

 
 
3
3
5
,

 
 
5
5
8
5
]
,

 
[
1
,
 
4
5
3
,
 
1
6
3
,
 
2
,
 
3
3
6
0
,
 
3
,
 
1
,
 
2
2
7
8
,
 
1
7
1
5
,
 
2
,
 
1
,
 
1
2
2
9
4
,
 
3
6
8
0
,
 
2
9
,
 
2
0
,
 
1
7
,
 
2
2
]
,

 
[
6
6
1
,
 
9
1
,
 
2
5
,
 
6
0
2
2
,
 
3
,
 
1
0
7
0
3
,
 
6
4
8
2
,
 
1
0
5
,
 
1
1
,
 
2
5
,
 
8
6
,
 
3
2
3
2
]
,

 
[
1
,

 
 
2
0
0
,

 
 
1
3
9
,

 
 
1
0
6
,

 
 
2
6
2
2
,

 
 
2
2
,

 
 
3
6
,

 
 
1
0
4
,

 
 
1
8
,

 
 
7
5
,

 
 
2
6
,

 
 
6
5
1
,

 
 
9
5
8
,

 
 
8
,

 
 
3
8
4
2
,

 
 
4
4
4
3
,

 
 
6
6
]
,

 
[
3
5
0
7
,

 
 
3
2
7
,

 
 
3
2
2
5
,

 
 
3
3
4
7
,

 
 
7
,

 
 
1
2
2
9
5
,

 
 
8
8
,

 
 
5
6
3
4
,

 
 
1
9
4
3
,

 
 
2
,

 
 
7
6
8
2
,

 
 
5
6
3
5
,

 
 
1
5
3
1
,

 
 
3
,

 
 
1
9
0
1
9
,

 
 
3
8
4
3
,

 
 
2
8
2
,

 
 
1
9
4
3
,

 
 
1
3
0
,

 
 
8
3
1
,

 
 
3
,

 
 
1
9
0
2
0
,

 
 
4
2
1
4
,

 
 
3
,

 
 
1
3
0
,

 
 
1
6
9
6
,

 
 
4
,

 
 
1
5
,

 
 
1
1
1
,

 
 
2
9
1
4
,

 
 
1
4
,

 
 
4
6
,

 
 
2
0
,

 
 
7
5
,

 
 
1
8
3
6
,

 
 
4
,

 
 
1
8
5
0
]
,

 
[
5
,
 
8
,
 
5
7
5
,
 
2
3
,
 
1
,
 
2
8
9
4
,
 
9
,
 
2
2
3
,
 
7
,
 
1
,
 
7
3
9
,
 
2
,
 
3
5
6
]
,

 
[
5
6
,
 
3
3
,
 
3
3
4
,
 
5
2
,
 
5
3
0
,
 
7
7
,
 
4
8
]
,

 
[
2
1
0
,

 
 
5
7
1
,

 
 
3
1
3
4
,

 
 
1
,

 
 
3
8
3
,

 
 
2
,

 
 
1
,

 
 
5
6
3
6
,

 
 
1
7
8
,

 
 
2
7
4
,

 
 
1
,

 
 
2
2
5
,

 
 
5
7
,

 
 
3
0
,

 
 
1
4
1
,

 
 
1
1
,

 
 
8
,

 
 
2
0
,

 
 
4
1
6
]
,

 
[
5
,

 
 
4
6
,

 
 
5
2
,

 
 
2
3
2
,

 
 
1
7
4
,

 
 
4
,

 
 
3
0
7
,

 
 
1
,

 
 
7
9
1
,

 
 
2
,

 
 
1
0
,

 
 
8
8
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
8
9
,

 
 
6
6
,

 
 
1
,

 
 
4
9
4
,

 
 
2
1
,

 
 
3
2
,

 
 
1
8
,

 
 
1
3
,

 
 
4
3
4
,

 
 
2
1
,

 
 
6
4
8
,

 
 
2
,

 
 
1
8
1
,

 
 
1
9
0
2
1
,

 
 
3
,

 
 
6
,

 
 
8
6
0
,

 
 
2
1
,

 
 
1
,

 
 
1
6
2
5
,

 
 
5
6
5
,

 
 
2
,

 
 
1
,

 
 
4
8
0
,

 
 
1
9
,

 
 
5
,

 
 
1
9
0
2
2
,

 
 
5
1
8
]
,

 
[
1
5
,
 
3
5
8
,
 
7
4
0
,
 
2
4
,
 
7
0
,
 
5
,
 
1
2
,
 
1
2
9
,
 
6
9
,
 
1
7
0
,
 
3
,
 
1
5
,
 
1
9
3
7
,
 
5
2
1
,
 
1
7
5
2
,
 
2
2
]
,

 
[
5
,

 
 
1
3
3
,

 
 
6
9
1
,

 
 
6
9
5
,

 
 
3
,

 
 
5
,

 
 
6
2
,

 
 
2
8
,

 
 
7
5
,

 
 
3
5
0
8
,

 
 
3
,

 
 
9
4
3
1
,

 
 
4
,

 
 
1
0
,

 
 
4
2
6
,

 
 
6
7
7
,

 
 
3
,

 
 
1
0
0
1
,

 
 
6
0
,

 
 
6
2
4
,

 
 
1
0
7
0
4
,

 
 
2
3
6
,

 
 
3
2
4
7
,

 
 
6
9
1
,

 
 
1
8
8
,

 
 
1
,

 
 
1
9
,

 
 
6
2
4
,

 
 
1
9
0
2
3
,

 
 
2
2
]
,

 
[
1
,

 
 
3
1
3
5
,

 
 
1
4
7
8
5
,

 
 
5
,

 
 
1
2
,

 
 
1
4
3
,

 
 
2
4
,

 
 
1
,

 
 
1
2
5
2
,

 
 
9
4
3
2
,

 
 
7
3
,

 
 
2
0
,

 
 
1
0
1
6
,

 
 
6
1
,

 
 
1
6
6
1
,

 
 
3
2
7
,

 
 
3
,

 
 
5
,

 
 
1
4
5
,

 
 
5
,

 
 
8
4
,

 
 
6
3
6
,

 
 
1
,

 
 
9
4
7
,

 
 
2
,

 
 
1
5
,

 
 
2
9
5
,

 
 
4
4
1
8
,

 
 
9
9
,

 
 
1
6
,

 
 
1
3
7
,

 
 
1
6
,

 
 
3
5
3
,

 
 
2
4
,

 
 
1
0
,

 
 
4
8
0
]
,

 
[
1
2
4
,

 
 
1
9
0
2
4
,

 
 
1
1
0
,

 
 
2
,

 
 
1
0
,

 
 
2
1
2
0
,

 
 
1
7
,

 
 
4
5
,

 
 
2
5
,

 
 
3
6
,

 
 
3
4
3
,

 
 
2
3
9
,

 
 
3
4
,

 
 
2
6
9
,

 
 
4
6
3
,

 
 
1
6
,

 
 
3
4
,

 
 
2
9
,

 
 
6
7
5
,

 
 
5
,

 
 
7
1
1
,

 
 
1
1
0
,

 
 
3
8
4
4
,

 
 
5
7
,

 
 
1
,

 
 
1
6
3
5
,

 
 
1
,

 
 
8
3
0
,

 
 
2
1
6
5
,

 
 
2
,

 
 
1
0
,

 
 
6
6
9
,

 
 
1
2
7
,

 
 
6
,

 
 
1
2
8
3
,

 
 
7
0
1
0
,

 
 
9
,

 
 
1
2
,

 
 
4
3
,

 
 
1
0
7
0
5
,

 
 
5
7
,

 
 
1
,

 
 
5
2
6
9
,

 
 
2
,

 
 
6
9
6
4
,

 
 
1
9
0
2
5
,

 
 
4
0
1
7
,

 
 
3
,

 
 
4
0
,

 
 
1
2
,

 
 
3
0
0
0
,

 
 
1
7
9
,

 
 
2
4
,

 
 
1
5
,

 
 
2
2
3
2
]
,

 
[
2
1
,
 
6
,
 
2
6
2
3
,
 
2
,
 
1
0
,
 
1
7
3
,
 
1
0
,
 
1
9
0
2
6
,
 
1
4
1
8
,
 
1
4
7
8
6
,
 
1
7
9
]
,

 
[
3
3
,
 
9
3
,
 
3
1
,
 
1
7
0
,
 
2
2
,
 
3
3
,
 
9
3
]
,

 
[
3
,
 
7
,
 
1
,
 
1
9
0
8
,
 
2
,
 
3
2
,
 
2
6
,
 
1
,
 
2
9
9
8
,
 
1
4
7
8
7
,
 
2
,
 
6
,
 
1
2
2
9
6
,
 
5
8
8
,
 
8
7
,
 
3
2
]
,

 
[
4
5
,

 
 
8
,

 
 
3
5
4
,

 
 
2
,

 
 
1
,

 
 
4
9
4
0
,

 
 
9
4
3
3
,

 
 
3
3
,

 
 
1
2
6
,

 
 
7
,

 
 
1
4
7
8
8
,

 
 
1
4
7
8
9
,

 
 
3
5
4
,

 
 
2
,

 
 
1
,

 
 
1
0
7
0
6
,

 
 
1
4
7
9
0
,

 
 
1
2
2
9
7
,

 
 
3
,

 
 
6
9
6
9
,

 
 
5
2
7
0
,

 
 
9
,

 
 
9
4
3
4
,

 
 
1
4
7
9
1
,

 
 
1
9
9
9
,

 
 
6
0
2
3
,

 
 
4
,

 
 
1
2
2
9
8
,

 
 
1
,

 
 
4
2
7
]
,

 
[
1
7
,
 
2
1
6
6
,
 
5
6
3
7
,
 
8
,
 
2
4
6
]
,

 
[
1
8
3
,

 
 
7
3
,

 
 
5
,

 
 
3
0
7
,

 
 
9
,

 
 
7
,

 
 
1
,

 
 
2
2
9
0
,

 
 
2
,

 
 
5
5
,

 
 
3
7
5
,

 
 
1
4
9
9
,

 
 
2
1
,

 
 
7
5
4
,

 
 
4
8
,

 
 
4
9
,

 
 
4
6
8
2
,

 
 
5
4
,

 
 
4
9
9
,

 
 
2
,

 
 
4
2
1
5
,

 
 
3
,

 
 
7
,

 
 
1
,

 
 
2
4
4
,

 
 
2
,

 
 
4
0
4
]
,

 
[
6
7
,
 
1
0
2
,
 
7
9
,
 
8
5
7
,
 
6
4
8
3
,
 
3
3
1
,
 
2
9
,
 
2
0
,
 
2
1
6
7
,
 
4
6
9
,
 
2
,
 
1
6
3
0
,
 
3
,
 
4
2
7
]
,

 
[
1
7
8
,

 
 
1
3
1
,

 
 
1
2
2
9
9
,

 
 
4
,

 
 
1
5
,

 
 
3
1
0
1
,

 
 
1
,

 
 
4
6
8
3
,

 
 
2
,

 
 
1
4
7
9
2
,

 
 
7
4
,

 
 
2
,

 
 
6
7
,

 
 
4
6
8
3
,

 
 
1
4
,

 
 
1
2
1
4
,

 
 
1
5
,

 
 
2
1
0
0
,

 
 
8
4
9
8
,

 
 
2
,

 
 
1
3
8
]
,

 
[
3
6
,

 
 
7
1
,

 
 
4
6
,

 
 
7
0
1
1
,

 
 
6
,

 
 
1
0
7
0
7
,

 
 
2
7
,

 
 
1
,

 
 
4
0
1
8
,

 
 
1
3
,

 
 
3
3
4
,

 
 
5
4
1
,

 
 
3
6
,

 
 
7
1
,

 
 
3
3
4
,

 
 
2
9
1
5
,

 
 
6
,

 
 
4
4
4
4
,

 
 
2
9
1
6
,

 
 
2
4
,

 
 
6
,

 
 
1
7
9
3
,

 
 
5
2
7
1
]
,

 
[
7
,
 
3
0
6
,
 
4
,
 
1
1
1
7
,
 
4
4
,
 
8
9
,
 
6
,
 
3
0
2
6
,
 
1
1
,
 
2
5
,
 
4
5
7
,
 
4
,
 
3
1
,
 
4
3
,
 
7
6
8
3
]
,

 
[
5
1
,

 
 
1
0
6
,

 
 
6
5
1
,

 
 
1
9
5
5
,

 
 
1
1
9
0
,

 
 
3
0
,

 
 
4
,

 
 
9
4
,

 
 
1
1
4
,

 
 
1
8
,

 
 
3
6
,

 
 
5
7
1
,

 
 
4
6
,

 
 
7
,

 
 
1
,

 
 
2
4
4
,

 
 
2
7
9
,

 
 
6
,

 
 
3
6
5
8
,

 
 
4
,

 
 
1
,

 
 
8
4
9
9
,

 
 
1
0
7
0
8
,

 
 
2
,

 
 
1
,

 
 
1
9
5
8
,

 
 
5
8
,

 
 
1
6
,

 
 
6
0
,

 
 
7
5
0
,

 
 
1
3
,

 
 
6
,

 
 
9
4
3
5
,

 
 
2
,

 
 
3
2
4
8
,

 
 
6
4
8
4
,

 
 
2
7
,

 
 
3
2
,

 
 
4
9
5
3
,

 
 
3
2
,

 
 
5
4
7
,

 
 
3
2
,

 
 
1
1
6
7
,

 
 
3
,

 
 
2
0
7
,

 
 
1
5
0
,

 
 
6
6
,

 
 
4
,

 
 
1
0
7
0
9
]
,

 
[
4
1
,

 
 
1
,

 
 
7
9
,

 
 
5
7
1
,

 
 
2
7
3
,

 
 
4
,

 
 
6
0
1
,

 
 
3
4
6
,

 
 
3
9
,

 
 
1
4
,

 
 
1
0
7
7
,

 
 
9
4
3
6
,

 
 
2
0
5
,

 
 
1
,

 
 
1
6
7
0
,

 
 
3
,

 
 
5
7
,

 
 
1
,

 
 
2
8
1
4
,

 
 
2
,

 
 
1
,

 
 
7
0
1
2
,

 
 
1
4
7
9
3
,

 
 
4
4
2
4
,

 
 
4
2
0
4
]
,

 
[
1
,

 
 
1
4
7
9
4
,

 
 
1
9
0
2
7
,

 
 
4
9
3
6
,

 
 
7
,

 
 
1
,

 
 
3
7
3
,

 
 
2
2
4
,

 
 
1
9
5
9
,

 
 
1
3
,

 
 
5
1
,

 
 
5
2
7
2
,

 
 
2
2
3
3
,

 
 
5
,

 
 
1
4
3
,

 
 
6
,

 
 
4
0
1
9
,

 
 
2
8
1
5
,

 
 
2
,

 
 
7
2
0
]
,

 
[
5
,

 
 
2
1
4
,

 
 
1
1
,

 
 
2
7
5
,

 
 
2
,

 
 
1
,

 
 
7
5
7
,

 
 
7
9
,

 
 
1
7
5
3
,

 
 
1
1
6
,

 
 
7
,

 
 
1
,

 
 
1
2
1
5
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
8
5
6
,

 
 
5
,

 
 
2
2
8
,

 
 
3
3
,

 
 
6
8
]
,

 
[
3
6
,
 
7
6
3
,
 
1
2
3
,
 
5
,
 
1
2
9
,
 
2
3
2
]
,

 
[
9
4
3
7
,

 
 
7
,

 
 
4
6
7
,

 
 
1
6
,

 
 
5
,

 
 
1
3
3
,

 
 
4
6
7
,

 
 
6
6
1
,

 
 
6
4
,

 
 
1
3
2
,

 
 
6
1
6
,

 
 
5
,

 
 
1
4
0
,

 
 
2
8
,

 
 
9
4
3
8
,

 
 
1
7
,

 
 
2
1
2
1
,

 
 
8
9
0
,

 
 
1
3
9
,

 
 
6
1
9
,

 
 
3
,

 
 
3
5
0
2
,

 
 
7
,

 
 
1
,

 
 
1
7
3
0
,

 
 
2
,

 
 
6
,

 
 
1
5
6
,

 
 
6
0
2
4
,

 
 
1
3
0
1
]
,

 
[
5
,

 
 
7
6
9
,

 
 
5
4
,

 
 
1
2
8
4
,

 
 
8
,

 
 
3
3
6
1
,

 
 
7
,

 
 
1
0
,

 
 
3
9
9
,

 
 
1
7
,

 
 
2
5
2
,

 
 
5
6
3
8
,

 
 
1
6
7
1
,

 
 
4
,

 
 
1
2
5
,

 
 
4
0
0
,

 
 
4
4
,

 
 
7
8
,

 
 
1
2
7
,

 
 
3
1
0
,

 
 
5
1
5
,

 
 
3
2
,

 
 
1
,

 
 
1
3
6
5
,

 
 
9
,

 
 
2
9
,

 
 
2
7
,

 
 
7
8
,

 
 
3
0
4
,

 
 
2
9
,

 
 
2
7
4
,

 
 
2
2
,

 
 
3
,

 
 
5
,

 
 
1
7
1
1
,

 
 
6
3
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
1
3
4
2
,

 
 
5
4
,

 
 
9
5
4
,

 
 
2
3
,

 
 
1
9
,

 
 
5
,

 
 
4
6
,

 
 
3
1
3
6
,

 
 
4
,

 
 
7
8
,

 
 
3
4
7
3
,

 
 
3
7
,

 
 
3
8
3
,

 
 
2
,

 
 
7
8
,

 
 
2
5
3
2
,

 
 
3
,

 
 
2
5
3
3
]
,

 
[
1
4
,
 
1
8
2
,
 
1
7
5
4
,
 
8
5
0
0
,
 
8
8
,
 
6
2
7
,
 
3
,
 
1
4
,
 
5
2
,
 
2
4
6
8
,
 
4
,
 
1
4
4
,
 
6
3
,
 
2
1
,
 
8
3
,
 
1
7
3
]
,

 
[
1
6
,

 
 
1
9
0
,

 
 
1
6
,

 
 
2
8
1
,

 
 
5
6
3
9
,

 
 
5
,

 
 
2
4
2
1
,

 
 
2
4
,

 
 
1
0
,

 
 
1
4
7
9
5
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
3
7
4
,

 
 
1
,

 
 
4
9
5
4
,

 
 
5
9
7
,

 
 
3
,

 
 
1
3
4
2
,

 
 
6
0
,

 
 
5
,

 
 
4
6
,

 
 
7
1
4
,

 
 
7
,

 
 
1
,

 
 
3
0
2
7
,

 
 
5
,

 
 
1
2
,

 
 
9
6
]
,

 
[
7
6
8
4
,
 
7
7
,
 
1
,
 
1
3
3
2
]
,

 
[
4
9
5
5
,
 
4
6
3
,
 
2
6
,
 
2
5
,
 
4
0
2
0
,
 
3
,
 
1
,
 
8
6
,
 
6
5
5
,
 
3
8
0
,
 
3
3
,
 
2
6
9
,
 
4
6
3
,
 
1
0
0
,
 
5
,
 
1
3
3
,
 
2
2
0
]
,

 
[
6
5
,

 
 
1
3
2
,

 
 
3
4
,

 
 
1
2
,

 
 
1
1
9
1
,

 
 
4
,

 
 
3
9
,

 
 
7
,

 
 
1
9
6
0
,

 
 
2
,

 
 
5
5
,

 
 
2
4
7
2
,

 
 
3
,

 
 
5
,

 
 
1
4
5
,

 
 
8
2
,

 
 
1
0
,

 
 
3
6
8
1
,

 
 
7
4
1
,

 
 
9
,

 
 
1
4
,

 
 
4
9
,

 
 
6
1
4
,

 
 
3
,

 
 
3
3
6
2
,

 
 
2
2
,

 
 
7
,

 
 
5
4
,

 
 
1
4
7
9
6
,

 
 
4
5
7
,

 
 
6
4
0
,

 
 
6
0
2
5
]
,

 
[
5
5
,

 
 
8
9
4
,

 
 
8
,

 
 
2
7
,

 
 
2
2
9
1
,

 
 
9
4
3
9
,

 
 
1
3
,

 
 
1
,

 
 
1
7
3
2
,

 
 
9
,

 
 
7
1
0
,

 
 
8
0
7
,

 
 
1
8
6
,

 
 
1
8
,

 
 
3
4
,

 
 
1
8
6
,

 
 
1
9
0
2
8
,

 
 
1
,

 
 
5
6
4
0
,

 
 
1
2
1
,

 
 
3
,

 
 
1
6
,

 
 
5
5
,

 
 
1
0
3
3
,

 
 
2
9
8
,

 
 
2
,

 
 
6
0
2
6
,

 
 
1
2
5
1
,

 
 
5
5
,

 
 
9
9
,

 
 
7
,

 
 
3
1
3
7
,

 
 
8
1
1
,

 
 
2
2
8
,

 
 
6
,

 
 
3
5
0
,

 
 
1
4
2
,

 
 
3
6
,

 
 
1
4
9
0
,

 
 
4
6
,

 
 
3
1
,

 
 
1
3
2
9
]
,

 
[
5
,

 
 
8
,

 
 
6
1
,

 
 
2
4
7
8
,

 
 
1
7
,

 
 
3
9
,

 
 
1
7
,

 
 
5
,

 
 
4
2
1
6
,

 
 
4
,

 
 
1
2
6
,

 
 
6
,

 
 
2
0
6
1
,

 
 
1
6
0
0
,

 
 
1
8
,

 
 
1
4
,

 
 
8
,

 
 
2
0
,

 
 
6
,

 
 
1
8
9
,

 
 
7
1
,

 
 
4
,

 
 
4
6
3
,

 
 
1
3
]
,

 
[
2
6
0
,
 
1
,
 
2
6
2
4
,
 
8
,
 
1
1
2
9
,
 
8
1
,
 
5
3
,
 
1
1
,
 
2
5
,
 
8
5
0
1
,
 
4
6
8
4
,
 
3
3
6
3
,
 
7
0
1
3
,
 
5
2
7
3
]
,

 
[
1
8
3
,
 
7
3
,
 
3
5
6
,
 
9
4
4
0
,
 
2
2
,
 
6
4
,
 
7
,
 
1
,
 
4
1
6
,
 
5
2
7
4
,
 
2
,
 
1
0
1
7
,
 
3
,
 
1
3
8
7
]
,

 
[
2
6
,

 
 
1
4
7
9
7
,

 
 
8
5
,

 
 
2
,

 
 
3
2
,

 
 
3
0
7
,

 
 
4
4
,

 
 
1
,

 
 
3
8
8
,

 
 
5
2
5
,

 
 
1
,

 
 
7
9
,

 
 
5
0
8
,

 
 
4
6
,

 
 
3
1
,

 
 
8
3
,

 
 
1
1
1
6
,

 
 
1
,

 
 
8
5
5
,

 
 
3
,

 
 
9
3
9
,

 
 
3
1
,

 
 
1
2
0
6
,

 
 
4
4
4
5
]
,

 
[
2
7
,

 
 
6
,

 
 
2
1
2
,

 
 
7
6
8
5
,

 
 
1
0
7
2
,

 
 
4
1
,

 
 
2
6
,

 
 
4
9
5
6
,

 
 
9
8
,

 
 
1
4
7
9
8
,

 
 
7
4
2
,

 
 
3
,

 
 
4
1
,

 
 
7
,

 
 
3
6
8
2
,

 
 
5
,

 
 
1
2
,

 
 
1
0
5
5
,

 
 
5
,

 
 
3
1
1
2
,

 
 
6
,

 
 
2
6
6
,

 
 
2
,

 
 
1
0
0
9
,

 
 
6
0
2
7
,

 
 
1
0
7
1
0
,

 
 
1
0
7
1
1
,

 
 
1
2
1
6
,

 
 
2
4
,

 
 
1
,

 
 
8
5
0
2
,

 
 
6
0
2
8
,

 
 
3
4
6
,

 
 
1
,

 
 
5
2
7
5
,

 
 
3
2
4
9
,

 
 
5
,

 
 
2
9
8
,

 
 
4
,

 
 
1
0
,

 
 
7
1
2
,

 
 
6
8
,

 
 
1
,

 
 
2
6
1
]
,

 
[
1
9
0
2
9
,

 
 
2
2
,

 
 
2
6
8
,

 
 
1
9
3
,

 
 
1
4
,

 
 
6
5
2
,

 
 
1
9
0
3
0
,

 
 
4
2
1
7
,

 
 
1
4
9
6
,

 
 
3
3
,

 
 
4
5
5
,

 
 
4
,

 
 
5
6
4
1
,

 
 
2
2
,

 
 
3
,

 
 
2
6
2
5
,

 
 
2
2
,

 
 
4
,

 
 
1
9
0
9
]
,

 
[
7
,

 
 
1
,

 
 
2
4
8
,

 
 
2
0
3
,

 
 
2
0
6
,

 
 
5
,

 
 
9
6
,

 
 
8
9
0
,

 
 
1
6
9
,

 
 
7
0
1
4
,

 
 
5
2
7
6
,

 
 
2
0
6
2
,

 
 
3
0
,

 
 
3
7
2
,

 
 
1
4
7
8
1
,

 
 
1
5
,

 
 
4
6
8
5
,

 
 
2
,

 
 
3
1
3
8
,

 
 
3
,

 
 
1
1
5
,

 
 
5
,

 
 
4
6
,

 
 
2
0
0
0
,

 
 
9
,

 
 
1
4
,

 
 
5
8
,

 
 
1
2
1
4
,

 
 
6
6
,

 
 
1
,

 
 
7
7
9
,

 
 
7
6
8
6
,

 
 
1
,

 
 
4
9
5
7
,

 
 
3
,

 
 
1
7
5
5
,

 
 
7
4
,

 
 
1
,

 
 
3
5
0
9
,

 
 
4
9
,

 
 
3
3
6
4
,

 
 
2
1
0
,

 
 
3
2
9
,

 
 
1
7
,

 
 
2
9
0
,

 
 
1
4
2
4
,

 
 
1
0
5
,

 
 
3
4
,

 
 
8
0
,

 
 
2
9
1
7
,

 
 
1
1
5
,

 
 
4
,

 
 
5
5
,

 
 
1
7
8
2
,

 
 
5
5
,

 
 
4
0
4
,

 
 
3
,

 
 
5
5
,

 
 
2
1
2
2
]
,

 
[
1
7
4
8
,

 
 
5
,

 
 
5
3
2
,

 
 
5
4
9
,

 
 
4
6
5
,

 
 
7
7
7
,

 
 
4
,

 
 
1
4
7
9
9
,

 
 
6
5
,

 
 
1
3
8
2
,

 
 
5
2
7
7
,

 
 
3
0
0
7
,

 
 
8
5
0
3
,

 
 
2
6
5
,

 
 
5
6
4
2
,

 
 
5
4
9
,

 
 
2
,

 
 
1
,

 
 
4
7
4
,

 
 
3
,

 
 
2
1
2
3
,

 
 
1
,

 
 
4
0
2
1
,

 
 
1
4
8
0
0
,

 
 
3
1
3
9
,

 
 
2
,

 
 
2
2
7
3
,

 
 
1
6
7
2
,

 
 
3
5
1
0
,

 
 
7
0
1
5
,

 
 
3
,

 
 
1
0
7
1
2
,

 
 
6
5
7
]
,

 
[
7
,

 
 
5
2
7
8
,

 
 
1
,

 
 
7
6
8
7
,

 
 
2
4
1
,

 
 
2
,

 
 
1
4
8
0
1
,

 
 
1
2
,

 
 
1
9
0
3
1
,

 
 
1
,

 
 
4
9
5
8
,

 
 
2
,

 
 
1
4
8
0
2
,

 
 
1
3
,

 
 
1
,

 
 
5
3
3
,

 
 
7
3
0
]
,

 
[
5
,
 
2
3
3
,
 
1
1
9
,
 
4
,
 
2
4
8
,
 
1
1
,
 
1
3
,
 
6
,
 
1
5
8
,
 
1
3
5
,
 
1
7
,
 
5
3
,
 
1
2
,
 
5
,
 
5
2
,
 
4
,
 
2
1
3
]
,

 
[
5
,
 
3
4
3
,
 
6
,
 
9
4
4
1
,
 
3
,
 
6
,
 
2
6
2
6
,
 
4
9
,
 
2
8
,
 
3
6
,
 
2
6
2
6
,
 
1
3
6
,
 
6
,
 
5
6
4
3
]
,

 
[
7
0
1
6
,
 
1
3
3
,
 
5
,
 
4
8
,
 
1
2
1
,
 
7
0
1
6
,
 
1
2
3
0
0
,
 
2
,
 
1
9
0
3
2
,
 
1
2
3
0
1
,
 
3
5
1
1
]
,

 
[
1
4
,

 
 
3
6
8
3
,

 
 
4
,

 
 
3
5
6
,

 
 
3
,

 
 
2
9
8
,

 
 
2
,

 
 
3
9
,

 
 
1
3
,

 
 
9
,

 
 
1
9
0
3
3
,

 
 
9
,

 
 
1
,

 
 
4
0
2
2
,

 
 
1
1
5
0
,

 
 
2
6
7
,

 
 
7
6
3
7
,

 
 
4
,

 
 
1
3
5
8
]
,

 
[
5
,
 
7
6
8
8
,
 
1
0
,
 
4
6
8
6
,
 
3
,
 
5
9
8
,
 
9
,
 
1
1
,
 
9
3
,
 
2
8
,
 
1
6
7
3
]
,

 
[
2
0
8
,

 
 
1
2
,

 
 
7
1
0
,

 
 
1
2
3
0
2
,

 
 
1
9
5
,

 
 
1
5
,

 
 
9
1
1
,

 
 
3
,

 
 
8
5
0
4
,

 
 
8
,

 
 
9
8
0
,

 
 
7
,

 
 
1
0
1
,

 
 
3
3
6
5
,

 
 
1
6
,

 
 
3
4
,

 
 
3
1
5
,

 
 
3
8
4
5
,

 
 
5
9
7
]
,

 
[
4
8
,
 
2
9
8
,
 
3
6
,
 
3
5
9
,
 
3
,
 
5
,
 
2
0
,
 
1
7
,
 
3
0
2
8
,
 
4
6
,
 
5
,
 
3
1
,
 
1
3
2
9
,
 
6
,
 
4
4
4
6
]
,

 
[
2
6
,

 
 
2
5
,

 
 
5
2
1
,

 
 
1
0
7
9
,

 
 
3
,

 
 
4
0
,

 
 
5
6
,

 
 
3
0
,

 
 
6
0
2
9
,

 
 
1
8
,

 
 
4
8
,

 
 
1
0
8
,

 
 
6
,

 
 
8
2
4
,

 
 
1
9
1
0
,

 
 
2
,

 
 
4
7
4
,

 
 
1
0
7
1
3
,

 
 
4
,

 
 
2
9
1
5
,

 
 
6
3
]
,

 
[
1
3
1
,
 
1
5
3
2
,
 
1
4
8
0
3
,
 
2
1
6
7
,
 
6
,
 
4
6
8
7
,
 
4
4
,
 
1
2
0
5
,
 
3
8
4
6
]
,

 
[
7
6
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
 
4
3
7
,
 
6
3
9
,
 
8
9
,
 
3
7
,
 
6
0
3
,
 
3
5
0
6
]
,

 
[
2
1
,
 
1
0
3
,
 
1
4
,
 
4
9
,
 
2
0
,
 
2
8
,
 
2
0
6
,
 
1
8
3
,
 
4
9
,
 
1
,
 
7
1
3
,
 
2
,
 
6
,
 
1
5
6
,
 
8
6
8
,
 
6
9
6
,
 
3
9
]
,

 
[
1
6
0
1
,
 
5
,
 
9
4
,
 
2
0
,
 
1
5
8
4
]
,

 
[
4
1
,

 
 
1
0
,

 
 
2
1
1
,

 
 
1
2
,

 
 
5
8
4
,

 
 
1
,

 
 
9
4
0
,

 
 
1
2
,

 
 
3
3
7
,

 
 
1
4
2
0
,

 
 
1
8
,

 
 
1
4
,

 
 
1
2
,

 
 
1
7
9
4
,

 
 
4
,

 
 
1
7
8
9
,

 
 
3
,

 
 
8
0
8
,

 
 
1
5
,

 
 
1
0
9
2
,

 
 
4
5
,

 
 
1
4
,

 
 
8
3
5
,

 
 
2
7
,

 
 
3
1
4
,

 
 
1
,

 
 
2
0
4
]
,

 
[
4
7
,

 
 
1
2
3
0
3
,

 
 
1
6
9
,

 
 
6
,

 
 
6
6
2
,

 
 
2
8
7
,

 
 
8
,

 
 
3
6
9
,

 
 
4
2
6
,

 
 
7
,

 
 
3
7
4
,

 
 
2
,

 
 
1
,

 
 
9
3
0
,

 
 
3
,

 
 
4
0
2
3
,

 
 
3
0
3
,

 
 
2
,

 
 
9
4
4
2
,

 
 
8
2
4
,

 
 
4
2
1
8
,

 
 
3
,

 
 
1
1
,

 
 
1
9
0
,

 
 
1
1
7
,

 
 
4
,

 
 
2
8
,

 
 
1
,

 
 
7
8
7
,

 
 
6
6
5
,

 
 
2
7
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
1
4
,

 
 
1
9
0
3
4
,

 
 
4
6
9
,

 
 
3
,

 
 
7
4
9
,

 
 
6
6
,

 
 
8
5
0
5
,

 
 
7
,

 
 
1
,

 
 
7
9
,

 
 
1
2
3
0
4
,

 
 
1
1
1
8
,

 
 
2
7
,

 
 
1
8
4
,

 
 
1
3
3
5
,

 
 
4
7
4
]
,

 
[
3
4
,
 
2
8
8
,
 
5
6
4
4
,
 
1
,
 
1
6
5
,
 
8
5
0
6
,
 
3
3
6
6
,
 
5
6
0
,
 
6
6
0
,
 
1
,
 
1
7
1
,
 
3
,
 
1
1
4
7
,
 
1
,
 
4
9
5
9
]
,

 
[
1
,

 
 
2
5
3
4
,

 
 
2
9
,

 
 
3
6
,

 
 
3
3
3
,

 
 
5
8
6
,

 
 
5
2
5
,

 
 
4
2
,

 
 
1
2
,

 
 
2
2
1
,

 
 
1
1
9
,

 
 
1
,

 
 
1
2
0
4
,

 
 
4
,

 
 
1
,

 
 
8
5
0
7
,

 
 
3
5
,

 
 
5
2
5
,

 
 
1
0
,

 
 
2
4
7
9
,

 
 
1
5
9
9
,

 
 
1
2
,

 
 
1
5
4
,

 
 
6
3
,

 
 
7
4
,

 
 
2
,

 
 
3
1
9
,

 
 
1
1
,

 
 
2
5
,

 
 
5
3
5
,

 
 
4
,

 
 
1
2
5
]
,

 
[
1
5
,

 
 
3
2
7
,

 
 
2
9
,

 
 
1
7
9
5
,

 
 
2
4
7
9
,

 
 
7
,

 
 
5
2
7
9
,

 
 
3
,

 
 
1
5
7
,

 
 
3
1
4
0
,

 
 
3
9
,

 
 
3
5
4
,

 
 
2
,

 
 
1
,

 
 
1
7
6
,

 
 
1
4
5
2
,

 
 
3
,

 
 
2
9
1
8
,

 
 
1
4
5
3
,

 
 
2
,

 
 
1
,

 
 
7
9
,

 
 
2
3
1
,

 
 
2
9
,

 
 
4
4
4
7
,

 
 
6
,

 
 
1
9
9
5
,

 
 
5
3
4
,

 
 
1
3
0
,

 
 
5
0
0
,

 
 
4
6
,

 
 
2
0
,

 
 
2
8
,

 
 
1
7
3
9
]
,

 
[
6
6
1
,
 
5
3
,
 
6
2
,
 
2
9
4
,
 
2
,
 
8
5
]
,

 
[
1
,

 
 
2
7
2
3
,

 
 
2
,

 
 
1
,

 
 
2
2
7
4
,

 
 
2
,

 
 
7
5
4
,

 
 
7
7
,

 
 
4
8
,

 
 
1
0
7
1
5
,

 
 
3
0
2
9
,

 
 
2
4
2
,

 
 
9
,

 
 
5
,

 
 
5
2
8
0
,

 
 
3
9
,

 
 
2
3
7
,

 
 
1
,

 
 
2
2
7
4
,

 
 
1
5
0
,

 
 
4
9
,

 
 
2
8
,

 
 
1
,

 
 
8
3
,

 
 
4
,

 
 
1
2
3
0
5
,

 
 
2
2
,

 
 
1
8
,

 
 
9
0
8
,

 
 
5
,

 
 
9
4
,

 
 
2
0
,

 
 
7
0
1
7
,

 
 
1
4
8
0
4
]
,

 
[
5
2
,

 
 
1
6
,

 
 
1
,

 
 
3
6
8
4
,

 
 
2
,

 
 
9
,

 
 
2
4
6
,

 
 
1
9
0
3
5
,

 
 
5
2
8
1
,

 
 
4
6
8
8
,

 
 
1
9
6
1
,

 
 
3
,

 
 
1
9
6
1
,

 
 
3
,

 
 
1
,

 
 
7
0
1
8
,

 
 
8
5
0
8
,

 
 
3
,

 
 
8
5
0
9
,

 
 
2
,

 
 
9
7
,

 
 
1
5
2
0
,

 
 
5
2
8
2
,

 
 
1
3
2
3
,

 
 
3
5
1
2
,

 
 
2
1
0
5
,

 
 
3
,

 
 
2
1
0
5
,

 
 
5
,

 
 
1
4
0
,

 
 
6
7
1
,

 
 
1
3
,

 
 
1
0
,

 
 
4
6
8
9
,

 
 
1
,

 
 
5
6
1
6
,

 
 
1
9
,

 
 
2
5
,

 
 
1
0
,

 
 
6
4
,

 
 
3
1
0
2
,

 
 
2
4
,

 
 
1
,

 
 
1
2
3
0
6
,

 
 
3
,

 
 
4
2
1
9
]
,

 
[
6
0
,

 
 
3
4
,

 
 
1
3
4
2
,

 
 
9
4
4
3
,

 
 
2
,

 
 
8
9
,

 
 
1
1
0
9
,

 
 
4
0
,

 
 
1
7
5
6
,

 
 
4
2
,

 
 
6
2
,

 
 
8
6
,

 
 
9
0
8
,

 
 
5
6
4
5
,

 
 
1
,

 
 
3
5
9
,

 
 
2
0
0
9
,

 
 
1
9
3
,

 
 
4
4
,

 
 
4
0
2
4
,

 
 
3
4
,

 
 
2
3
2
,

 
 
3
6
,

 
 
1
9
6
,

 
 
5
9
,

 
 
9
1
8
,

 
 
8
9
,

 
 
2
7
9
6
,

 
 
1
,

 
 
1
4
2
5
,

 
 
1
2
7
]
,

 
[
3
4
,

 
 
1
4
8
0
5
,

 
 
5
7
6
,

 
 
3
,

 
 
5
7
6
,

 
 
1
7
,

 
 
2
3
7
,

 
 
3
7
,

 
 
3
0
5
,

 
 
2
7
2
4
,

 
 
2
8
4
,

 
 
5
9
,

 
 
2
7
2
5
,

 
 
1
2
0
5
,

 
 
1
0
3
2
,

 
 
5
0
,

 
 
3
,

 
 
5
0
,

 
 
5
7
,

 
 
1
,

 
 
1
1
9
2
,

 
 
2
,

 
 
1
,

 
 
9
4
4
4
,

 
 
3
,

 
 
6
5
,

 
 
1
6
0
2
,

 
 
3
,

 
 
1
6
0
2
,

 
 
4
,

 
 
4
7
,

 
 
6
0
6
,

 
 
2
8
1
6
,

 
 
1
1
4
8
]
,

 
[
1
5
,

 
 
5
2
8
3
,

 
 
8
,

 
 
1
0
3
4
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
1
4
,

 
 
2
2
3
,

 
 
1
3
0
9
,

 
 
4
,

 
 
1
2
6
,

 
 
2
2
,

 
 
3
,

 
 
6
5
,

 
 
1
4
,

 
 
3
5
1
3
,

 
 
1
5
0
,

 
 
1
6
,

 
 
6
0
,

 
 
4
2
2
0
,

 
 
4
,

 
 
6
4
8
5
,

 
 
1
5
,

 
 
3
9
8
]
,

 
[
1
,
 
2
1
2
4
,
 
3
,
 
5
2
8
4
,
 
4
4
4
8
,
 
2
,
 
1
2
3
0
7
,
 
6
8
1
,
 
2
0
8
,
 
4
,
 
2
8
,
 
1
,
 
8
3
,
 
7
,
 
1
7
5
7
]
,

 
[
2
1
,
 
1
9
1
,
 
3
4
,
 
3
5
1
4
,
 
1
7
9
]
,

 
[
1
8
,

 
 
1
1
,

 
 
2
5
,

 
 
2
0
,

 
 
9
,

 
 
1
,

 
 
5
5
4
,

 
 
8
,

 
 
9
6
,

 
 
4
,

 
 
3
1
,

 
 
1
,

 
 
7
6
8
9
,

 
 
2
,

 
 
1
,

 
 
3
0
3
0
,

 
 
6
2
1
,

 
 
3
5
,

 
 
9
6
,

 
 
4
,

 
 
3
1
,

 
 
3
0
,

 
 
4
4
4
9
,

 
 
3
5
,

 
 
3
0
,

 
 
7
0
1
9
,

 
 
3
5
,

 
 
1
,

 
 
8
2
5
,

 
 
2
,

 
 
3
0
,

 
 
7
0
1
9
,

 
 
3
5
,

 
 
3
0
,

 
 
2
7
0
,

 
 
3
5
,

 
 
6
,

 
 
5
1
2
,

 
 
1
5
3
2
,

 
 
4
4
,

 
 
1
,

 
 
5
1
7
,

 
 
3
5
,

 
 
3
0
,

 
 
3
2
5
,

 
 
1
0
3
7
,

 
 
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
5
,

 
 
9
,

 
 
1
,

 
 
5
5
4
,

 
 
1
2
,

 
 
1
8
6
,

 
 
3
,

 
 
3
2
,

 
 
1
9
0
3
6
]
,

 
[
5
8
5
,
 
2
8
1
7
,
 
8
5
1
0
,
 
2
0
4
9
,
 
2
9
,
 
2
0
,
 
1
9
1
1
,
 
1
7
,
 
1
0
9
,
 
4
6
2
,
 
3
5
,
 
6
,
 
3
1
3
,
 
4
2
2
1
]
,

 
[
5
,

 
 
2
7
2
,

 
 
7
8
4
,

 
 
9
,

 
 
5
,

 
 
1
2
,

 
 
1
1
9
0
,

 
 
3
0
,

 
 
4
,

 
 
2
3
4
,

 
 
3
0
,

 
 
1
1
1
,

 
 
2
4
7
,

 
 
3
,

 
 
7
6
9
0
,

 
 
4
7
7
,

 
 
7
,

 
 
8
9
,

 
 
1
9
4
1
,

 
 
1
7
,

 
 
1
,

 
 
4
2
2
2
,

 
 
2
,

 
 
3
4
1
,

 
 
1
6
,

 
 
8
0
,

 
 
3
1
,

 
 
5
2
8
5
,

 
 
3
0
,

 
 
3
3
6
]
,

 
[
3
4
,

 
 
6
9
6
5
,

 
 
1
1
,

 
 
1
3
6
,

 
 
4
9
5
,

 
 
1
9
4
,

 
 
1
1
,

 
 
8
,

 
 
6
4
,

 
 
2
3
,

 
 
6
,

 
 
4
6
9
0
,

 
 
9
,

 
 
3
4
,

 
 
1
7
0
3
,

 
 
1
1
,

 
 
2
4
,

 
 
1
9
0
3
7
,

 
 
1
6
,

 
 
1
1
,

 
 
1
7
9
6
,

 
 
1
,

 
 
2
7
1
]
,

 
[
7
3
,
 
2
0
,
 
1
3
8
8
,
 
6
6
,
 
1
3
1
0
]
,

 
[
1
,

 
 
7
9
,

 
 
5
7
1
,

 
 
2
6
7
,

 
 
2
2
3
,

 
 
7
4
,

 
 
2
,

 
 
1
0
0
9
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
,

 
 
9
0
9
,

 
 
1
0
5
,

 
 
1
,

 
 
3
2
5
0
,

 
 
6
4
8
6
,

 
 
5
6
3
,

 
 
1
,

 
 
4
6
9
1
,

 
 
6
4
8
6
]
,

 
[
1
8
,
 
1
1
,
 
8
,
 
2
0
,
 
7
,
 
6
7
,
 
6
4
8
7
,
 
2
,
 
1
2
1
7
,
 
6
0
3
0
,
 
9
,
 
1
4
,
 
1
0
7
,
 
1
9
6
2
,
 
3
6
8
5
]
,

 
[
5
2
,
 
8
5
1
1
,
 
2
8
,
 
5
9
2
,
 
9
4
,
 
2
0
,
 
6
0
3
1
,
 
2
2
,
 
4
,
 
7
8
,
 
1
0
6
7
]
,

 
[
1
,
 
2
4
8
,
 
6
2
5
,
 
2
4
0
,
 
3
1
1
5
,
 
2
5
8
,
 
8
5
,
 
1
3
,
 
1
,
 
1
0
5
9
,
 
3
5
1
5
,
 
1
0
7
1
6
,
 
1
8
2
7
]
,

 
[
5
,
 
5
2
8
6
,
 
4
,
 
3
9
,
 
4
,
 
1
6
3
8
,
 
1
9
,
 
1
4
,
 
7
3
,
 
1
3
,
 
2
8
1
8
,
 
1
3
5
6
,
 
2
,
 
5
6
4
6
]
,

 
[
3
4
,
 
2
3
3
,
 
7
4
,
 
1
3
,
 
1
,
 
2
1
6
8
,
 
2
,
 
1
4
8
0
6
,
 
1
3
,
 
5
5
,
 
3
8
4
7
]
,

 
[
1
1
,

 
 
6
2
,

 
 
2
8
,

 
 
1
7
0
,

 
 
2
1
,

 
 
1
2
3
0
8
,

 
 
3
,

 
 
9
,

 
 
2
6
,

 
 
2
7
2
6
,

 
 
1
2
3
0
9
,

 
 
1
2
,

 
 
2
0
,

 
 
6
4
,

 
 
1
5
2
1
,

 
 
1
,

 
 
2
4
9
,

 
 
5
2
,

 
 
7
,

 
 
3
8
8
,

 
 
1
8
,

 
 
1
2
,

 
 
8
3
6
,

 
 
9
2
,

 
 
3
6
,

 
 
7
6
9
1
,

 
 
7
7
4
,

 
 
1
9
0
3
8
,

 
 
7
,

 
 
1
,

 
 
6
1
,

 
 
4
4
5
0
,

 
 
2
4
5
5
,

 
 
5
2
,

 
 
4
0
,

 
 
9
4
4
5
,

 
 
2
7
4
,

 
 
4
,

 
 
3
7
,

 
 
6
0
3
2
,

 
 
2
3
,

 
 
1
4
4
2
,

 
 
3
6
8
6
,

 
 
5
8
,

 
 
1
9
4
,

 
 
1
4
,

 
 
1
5
0
0
,

 
 
2
0
,

 
 
1
,

 
 
1
5
3
3
,

 
 
4
9
6
0
,

 
 
4
,

 
 
1
1
,

 
 
2
5
,

 
 
1
3
6
,

 
 
3
0
7
,

 
 
5
,

 
 
1
2
5
,

 
 
1
1
,

 
 
9
4
4
6
,

 
 
3
,

 
 
1
1
8
,

 
 
1
3
4
3
,

 
 
1
1
,

 
 
6
0
,

 
 
2
1
2
5
,

 
 
6
0
3
3
,

 
 
4
,

 
 
1
,

 
 
1
2
3
1
0
,

 
 
1
7
,

 
 
2
1
,

 
 
2
6
4
,

 
 
1
,

 
 
8
3
,

 
 
2
0
1
3
,

 
 
2
,

 
 
1
5
,

 
 
1
1
1
,

 
 
3
6
8
7
]
,

 
[
1
4
,
 
1
0
7
1
7
,
 
1
8
2
,
 
1
1
6
9
,
 
3
,
 
4
6
,
 
2
0
,
 
2
8
,
 
1
7
3
9
,
 
7
,
 
3
0
,
 
2
0
6
3
]
,

 
[
3
4
,
 
6
2
,
 
3
6
8
8
,
 
1
,
 
1
0
9
3
,
 
4
,
 
1
,
 
1
5
1
]
,

 
[
5
,
 
1
5
5
9
,
 
6
5
,
 
9
,
 
5
,
 
6
4
,
 
1
8
5
,
 
1
4
5
,
 
3
,
 
9
0
,
 
1
4
8
0
7
,
 
8
6
6
]
,

 
[
1
4
,

 
 
8
,

 
 
4
1
0
,

 
 
1
9
0
3
9
,

 
 
2
,

 
 
7
0
2
0
,

 
 
3
,

 
 
1
2
3
1
1
,

 
 
6
9
6
2
,

 
 
2
6
2
7
,

 
 
3
,

 
 
1
2
3
1
2
,

 
 
1
6
,

 
 
1
5
,

 
 
6
7
2
,

 
 
1
9
0
4
0
,

 
 
9
6
1
,

 
 
7
6
9
2
,

 
 
3
,

 
 
1
3
6
,

 
 
9
,

 
 
1
9
0
4
1
,

 
 
2
,

 
 
4
8
0
,

 
 
1
9
,

 
 
4
0
2
5
,

 
 
1
,

 
 
4
2
0
5
,

 
 
6
0
3
4
,

 
 
1
6
1
,

 
 
2
1
2
,

 
 
2
9
1
9
,

 
 
1
0
4
5
,

 
 
2
3
,

 
 
1
6
7
4
]
,

 
[
6
2
,
 
1
8
9
2
,
 
9
4
4
7
,
 
6
,
 
5
0
,
 
1
4
8
0
8
,
 
1
1
7
0
,
 
2
,
 
7
7
4
]
,

 
[
5
,
 
2
9
8
,
 
1
3
6
,
 
1
1
4
,
 
7
6
9
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
3
5
5
,
 
2
,
 
5
3
,
 
5
,
 
7
7
,
 
2
7
4
,
 
1
3
,
 
1
1
,
 
9
5
,
 
3
3
6
]
,

 
[
2
6
,

 
 
1
9
1
2
,

 
 
8
,

 
 
9
6
,

 
 
7
,

 
 
1
,

 
 
3
0
4
,

 
 
2
,

 
 
6
,

 
 
4
2
2
3
,

 
 
5
8
,

 
 
1
9
4
,

 
 
3
6
,

 
 
1
6
9
6
,

 
 
7
0
6
,

 
 
1
,

 
 
1
7
7
,

 
 
5
2
8
7
,

 
 
3
,

 
 
1
2
3
1
3
,

 
 
1
6
,

 
 
1
1
0
,

 
 
6
,

 
 
7
8
0
,

 
 
7
,

 
 
3
0
6
,

 
 
1
0
4
,

 
 
8
6
7
,

 
 
1
7
,

 
 
1
9
6
3
,

 
 
6
,

 
 
9
3
7
,

 
 
1
1
9
3
,

 
 
5
8
1
,

 
 
8
,

 
 
3
8
,

 
 
2
,

 
 
9
7
,

 
 
9
4
4
8
,

 
 
1
2
3
1
4
,

 
 
1
9
,

 
 
9
3
1
,

 
 
2
3
,

 
 
1
9
0
4
2
,

 
 
2
7
7
,

 
 
4
,

 
 
3
1
,

 
 
4
3
,

 
 
7
2
,

 
 
7
4
,

 
 
2
,

 
 
1
3
8
,

 
 
1
,

 
 
5
9
9
,

 
 
2
6
2
8
,

 
 
2
,

 
 
1
,

 
 
7
0
2
1
]
,

 
[
4
8
,

 
 
3
4
7
0
,

 
 
9
4
6
,

 
 
3
0
,

 
 
5
9
6
,

 
 
3
,

 
 
1
,

 
 
7
5
1
,

 
 
2
2
4
,

 
 
8
,

 
 
9
4
4
9
,

 
 
1
3
,

 
 
1
,

 
 
1
9
9
1
,

 
 
1
6
6
0
,

 
 
2
,

 
 
2
0
8
,

 
 
3
,

 
 
3
3
8
]
,

 
[
5
3
,
 
2
6
,
 
1
9
1
1
,
 
3
6
,
 
3
8
,
 
4
6
,
 
3
6
9
,
 
2
8
,
 
2
1
2
,
 
4
0
5
,
 
6
1
2
]
,

 
[
3
0
,

 
 
6
7
8
,

 
 
8
,

 
 
7
9
8
,

 
 
4
,

 
 
3
9
,

 
 
7
9
8
,

 
 
3
,

 
 
9
7
4
,

 
 
1
6
,

 
 
1
,

 
 
1
7
1
0
,

 
 
3
,

 
 
2
4
3
,

 
 
9
,

 
 
4
6
9
2
,

 
 
5
1
,

 
 
3
6
8
9
,

 
 
5
7
,

 
 
3
9
]
,

 
[
5
,
 
8
,
 
2
3
6
,
 
2
4
7
8
,
 
9
,
 
5
,
 
1
2
,
 
3
6
,
 
3
8
,
 
1
3
,
 
2
3
0
,
 
4
,
 
3
0
3
1
]
,

 
[
5
3
,
 
5
,
 
1
0
7
,
 
6
4
8
8
,
 
2
2
,
 
8
6
,
 
7
0
2
2
,
 
4
6
6
7
,
 
4
7
,
 
2
9
2
0
,
 
1
9
0
4
3
]
,

 
[
5
3
0
,
 
8
8
,
 
5
5
,
 
5
9
9
,
 
1
9
2
,
 
2
5
2
,
 
1
6
0
1
,
 
5
,
 
3
1
,
 
5
2
3
,
 
7
8
,
 
1
4
2
6
,
 
2
,
 
2
6
,
 
4
2
5
]
,

 
[
6
0
,

 
 
5
,

 
 
1
2
6
1
,

 
 
1
4
,

 
 
4
9
,

 
 
1
6
7
5
,

 
 
2
7
,

 
 
2
2
,

 
 
7
,

 
 
4
8
7
,

 
 
1
8
,

 
 
1
4
,

 
 
8
,

 
 
3
6
,

 
 
3
3
3
,

 
 
2
7
2
7
,

 
 
3
,

 
 
1
9
4
,

 
 
1
4
,

 
 
8
5
1
2
,

 
 
1
0
1
,

 
 
1
0
7
1
8
,

 
 
7
6
,

 
 
1
1
,

 
 
8
,

 
 
1
3
,

 
 
3
0
3
2
]
,

 
[
1
1
,

 
 
2
5
,

 
 
1
5
3
,

 
 
4
9
3
,

 
 
1
4
,

 
 
3
3
1
,

 
 
8
5
1
3
,

 
 
1
6
,

 
 
6
,

 
 
1
0
7
1
9
,

 
 
1
3
,

 
 
6
,

 
 
5
4
2
,

 
 
8
6
2
,

 
 
7
0
2
3
,

 
 
9
2
,

 
 
1
,

 
 
9
6
2
,

 
 
1
5
6
4
,

 
 
1
3
,

 
 
1
,

 
 
8
3
,

 
 
3
0
5
,

 
 
8
2
,

 
 
5
6
4
7
,

 
 
1
1
,

 
 
2
5
,

 
 
1
5
3
,

 
 
4
9
3
,

 
 
1
8
,

 
 
5
3
,

 
 
1
2
5
1
,

 
 
1
1
]
,

 
[
6
7
,

 
 
5
9
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
3
,

 
 
1
,

 
 
4
2
2
4
,

 
 
2
,

 
 
1
,

 
 
2
0
4
,

 
 
1
,

 
 
8
5
1
4
,

 
 
2
,

 
 
1
,

 
 
7
0
2
4
,

 
 
1
0
7
2
0
,

 
 
5
7
6
,

 
 
1
,

 
 
1
2
3
1
5
,

 
 
1
2
3
8
,

 
 
3
,

 
 
1
,

 
 
1
4
8
0
9
,

 
 
6
6
,

 
 
2
,

 
 
1
,

 
 
2
7
1
,

 
 
7
,

 
 
1
,

 
 
5
7
2
]
,

 
[
5
,

 
 
1
2
,

 
 
3
1
5
,

 
 
1
,

 
 
6
4
8
9
,

 
 
1
0
7
0
,

 
 
7
0
0
,

 
 
3
,

 
 
8
,

 
 
2
5
3
5
,

 
 
4
6
5
,

 
 
2
1
,

 
 
6
,

 
 
6
1
,

 
 
1
2
6
6
,

 
 
4
4
2
0
,

 
 
4
1
,

 
 
9
,

 
 
4
9
6
1
,

 
 
3
9
8
2
,

 
 
2
2
1
3
,

 
 
1
1
5
,

 
 
5
6
4
8
,

 
 
1
2
3
1
6
]
,

 
[
1
8
,

 
 
5
,

 
 
4
6
,

 
 
1
3
4
2
,

 
 
9
6
6
,

 
 
3
2
,

 
 
3
0
,

 
 
1
9
0
4
4
,

 
 
2
6
2
,

 
 
4
4
5
1
,

 
 
3
1
4
,

 
 
2
0
8
,

 
 
3
,

 
 
3
7
,

 
 
1
9
0
4
5
,

 
 
3
6
6
,

 
 
2
,

 
 
2
4
8
0
,

 
 
9
,

 
 
1
9
0
4
6
,

 
 
2
4
,

 
 
2
2
,

 
 
1
0
,

 
 
2
5
1
,

 
 
4
1
,

 
 
5
,

 
 
2
2
3
,

 
 
1
9
6
4
,

 
 
4
,

 
 
4
7
,

 
 
3
3
6
7
]
,

 
[
8
2
,
 
3
2
,
 
5
3
,
 
2
5
,
 
1
1
]
,

 
[
1
4
,

 
 
2
2
9
2
,

 
 
8
8
,

 
 
1
,

 
 
3
2
8
,

 
 
5
6
4
9
,

 
 
1
,

 
 
3
4
9
5
,

 
 
3
,

 
 
9
8
9
,

 
 
8
9
,

 
 
4
1
9
5
,

 
 
1
6
,

 
 
2
9
,

 
 
4
5
7
,

 
 
1
7
,

 
 
1
,

 
 
5
2
2
7
,

 
 
1
4
,

 
 
1
2
2
3
8
]
,

 
[
2
6
,

 
 
5
6
0
,

 
 
8
,

 
 
1
9
7
,

 
 
2
7
0
,

 
 
3
,

 
 
6
,

 
 
1
8
5
,

 
 
1
0
9
,

 
 
1
9
7
,

 
 
2
7
0
,

 
 
1
6
7
2
,

 
 
3
,

 
 
1
2
2
,

 
 
3
,

 
 
6
,

 
 
1
8
5
,

 
 
2
7
0
,

 
 
2
6
2
]
,

 
[
1
0
,
 
1
0
1
,
 
6
8
2
,
 
8
,
 
2
0
6
4
,
 
9
0
6
]
,

 
[
8
2
,

 
 
9
,

 
 
9
3
2
,

 
 
3
8
9
,

 
 
1
2
,

 
 
1
3
8
9
,

 
 
1
5
,

 
 
4
0
2
6
,

 
 
1
7
,

 
 
5
4
,

 
 
7
2
,

 
 
1
8
,

 
 
1
6
,

 
 
1
,

 
 
3
0
3
3
,

 
 
2
,

 
 
1
,

 
 
6
7
5
,

 
 
7
6
9
4
,

 
 
9
2
7
,

 
 
4
4
7
,

 
 
1
4
,

 
 
1
1
5
,

 
 
1
6
2
,

 
 
1
2
3
1
7
,

 
 
1
3
,

 
 
1
,

 
 
1
3
3
9
,

 
 
4
4
5
2
,

 
 
1
4
8
1
0
,

 
 
1
7
,

 
 
1
,

 
 
5
1
1
,

 
 
2
,

 
 
1
,

 
 
8
5
1
5
,

 
 
1
7
4
,

 
 
3
,

 
 
2
,

 
 
6
8
0
,

 
 
1
8
1
,

 
 
2
0
4
9
,

 
 
1
7
,

 
 
1
,

 
 
3
4
0
,

 
 
1
4
,

 
 
1
0
1
8
,

 
 
1
6
,

 
 
4
0
,

 
 
1
4
8
1
1
,

 
 
1
4
7
8
]
,

 
[
1
4
7
7
,

 
 
1
0
3
,

 
 
3
3
1
,

 
 
4
,

 
 
1
2
3
1
8
,

 
 
8
5
,

 
 
3
2
,

 
 
1
2
3
1
9
,

 
 
2
3
,

 
 
1
,

 
 
1
2
3
2
0
,

 
 
2
0
4
,

 
 
3
6
9
0
,

 
 
4
,

 
 
1
9
,

 
 
3
4
,

 
 
1
2
,

 
 
4
3
,

 
 
1
4
1
1
,

 
 
7
,

 
 
1
,

 
 
1
0
7
2
1
]
,

 
[
1
7
0
0
,
 
7
7
,
 
1
,
 
4
5
6
,
 
4
6
9
3
,
 
3
,
 
2
7
6
,
 
2
2
2
4
,
 
5
7
,
 
1
,
 
4
4
5
3
]
,

 
[
2
6
,

 
 
8
,

 
 
2
0
,

 
 
4
6
9
,

 
 
1
,

 
 
3
0
6
,

 
 
1
8
,

 
 
6
0
3
5
,

 
 
5
2
6
,

 
 
6
2
,

 
 
1
2
3
0
,

 
 
1
,

 
 
4
9
8
,

 
 
3
,

 
 
1
4
8
1
2
,

 
 
2
,

 
 
7
0
2
5
,

 
 
3
9
4
,

 
 
3
,

 
 
1
,

 
 
3
5
1
6
,

 
 
5
0
8
,

 
 
7
6
9
5
,

 
 
4
,

 
 
6
4
9
0
,

 
 
7
0
,

 
 
6
4
9
1
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

 
 
4
8
,

 
 
1
5
5
7
,

 
 
1
0
0
,

 
 
1
,

 
 
2
7
2
8
,

 
 
2
,

 
 
1
1
4
6
,

 
 
4
8
,

 
 
1
0
5
5
,

 
 
9
,

 
 
4
8
,

 
 
4
9
6
2
,

 
 
3
0
,

 
 
4
0
4
,

 
 
4
,

 
 
9
4
5
0
,

 
 
1
1
3
7
]
,

 
[
1
,

 
 
9
4
2
,

 
 
3
1
,

 
 
1
2
3
6
,

 
 
2
2
9
3
,

 
 
1
,

 
 
4
6
9
4
,

 
 
1
,

 
 
9
4
5
1
,

 
 
3
,

 
 
1
,

 
 
3
2
5
1
,

 
 
2
,

 
 
1
,

 
 
3
9
5
,

 
 
7
,

 
 
1
0
1
,

 
 
6
1
1
]
,

 
[
1
9
0
4
7
,

 
 
3
4
5
,

 
 
7
,

 
 
8
4
5
,

 
 
3
2
5
2
,

 
 
1
3
4
4
,

 
 
2
,

 
 
1
5
8
,

 
 
4
2
,

 
 
1
3
1
,

 
 
3
7
9
,

 
 
1
0
2
8
,

 
 
3
2
,

 
 
3
3
6
8
,

 
 
3
,

 
 
2
1
6
2
,

 
 
3
,

 
 
7
,

 
 
1
,

 
 
1
8
9
9
,

 
 
1
9
,

 
 
5
1
,

 
 
2
3
5
8
,

 
 
4
9
2
,

 
 
4
4
,

 
 
1
,

 
 
5
7
6
,

 
 
4
8
6
,

 
 
2
,

 
 
3
2
5
3
,

 
 
2
1
,

 
 
1
9
,

 
 
3
4
,

 
 
4
3
3
,

 
 
1
8
6
,

 
 
2
,

 
 
8
5
,

 
 
4
5
,

 
 
2
3
6
1
,

 
 
5
5
6
,

 
 
1
,

 
 
5
9
8
3
,

 
 
2
,

 
 
1
5
,

 
 
1
1
1
,

 
 
3
9
9
,

 
 
3
,

 
 
1
,

 
 
5
6
5
0
,

 
 
2
2
1
4
,

 
 
7
,

 
 
1
,

 
 
9
4
5
2
,

 
 
9
9
,

 
 
2
,

 
 
1
5
,

 
 
1
0
6
0
]
,

 
[
7
1
0
,

 
 
1
,

 
 
9
4
5
3
,

 
 
4
0
2
7
,

 
 
1
2
,

 
 
2
0
,

 
 
4
6
9
5
,

 
 
1
,

 
 
4
2
1
6
,

 
 
1
9
,

 
 
2
0
6
5
,

 
 
2
8
7
,

 
 
7
0
6
,

 
 
3
4
6
,

 
 
8
3
7
,

 
 
3
,

 
 
4
7
,

 
 
6
0
3
6
]
,

 
[
5
,

 
 
8
,

 
 
5
2
,

 
 
7
,

 
 
1
4
8
1
3
,

 
 
3
,

 
 
2
2
1
,

 
 
2
3
,

 
 
6
,

 
 
6
4
0
,

 
 
1
4
1
,

 
 
4
4
6
,

 
 
1
3
,

 
 
1
9
0
4
8
,

 
 
1
0
6
0
,

 
 
1
3
0
,

 
 
2
5
3
6
,

 
 
2
1
6
9
,

 
 
3
,

 
 
5
2
8
8
,

 
 
2
9
,

 
 
5
0
,

 
 
5
6
5
1
,

 
 
5
9
,

 
 
1
,

 
 
6
2
3
,

 
 
1
3
1
1
,

 
 
3
,

 
 
4
8
7
,

 
 
2
,

 
 
1
,

 
 
9
4
5
4
]
,

 
[
6
0
,
 
5
,
 
2
9
,
 
1
6
3
9
,
 
5
,
 
9
3
,
 
8
1
,
 
4
,
 
4
6
3
,
 
1
8
,
 
5
2
,
 
1
1
,
 
2
5
,
 
3
6
,
 
2
6
1
]
,

 
[
5
,

 
 
6
4
9
2
,

 
 
2
7
,

 
 
2
2
3
4
,

 
 
5
2
8
5
,

 
 
2
3
,

 
 
1
1
4
5
,

 
 
1
7
3
2
,

 
 
3
2
3
,

 
 
5
,

 
 
9
6
,

 
 
1
1
0
,

 
 
6
9
,

 
 
1
9
0
4
9
,

 
 
4
4
3
6
,

 
 
3
6
9
1
]
,

 
[
1
4
,

 
 
9
4
5
5
,

 
 
9
,

 
 
1
2
,

 
 
2
6
,

 
 
4
3
,

 
 
1
,

 
 
3
8
6
,

 
 
1
1
,

 
 
8
0
,

 
 
3
1
,

 
 
2
2
3
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

 
 
2
7
,

 
 
1
,

 
 
7
0
2
6
,

 
 
3
,

 
 
5
2
8
9
,

 
 
9
,

 
 
6
4
,

 
 
1
7
5
,

 
 
8
9
,

 
 
5
0
2
,

 
 
1
1
,

 
 
4
6
,

 
 
4
0
,

 
 
3
1
,

 
 
2
2
3
]
,

 
[
6
5
,

 
 
1
1
7
,

 
 
1
,

 
 
8
5
1
6
,

 
 
2
0
9
2
,

 
 
1
1
5
,

 
 
2
2
3
5
,

 
 
1
5
3
4
,

 
 
3
3
5
,

 
 
1
0
6
1
,

 
 
4
6
9
6
,

 
 
2
6
,

 
 
7
2
,

 
 
1
0
,

 
 
2
0
0
,

 
 
7
3
,

 
 
2
0
,

 
 
1
1
9
4
,

 
 
2
2
,

 
 
3
,

 
 
5
,

 
 
1
7
5
5
,

 
 
5
7
,

 
 
1
,

 
 
1
4
8
1
4
,

 
 
6
,

 
 
3
1
4
1
,

 
 
2
,

 
 
6
2
2
,

 
 
1
5
2
6
]
,

 
[
1
1
6
2
,

 
 
1
9
2
,

 
 
1
2
0
,

 
 
4
2
2
5
,

 
 
3
3
,

 
 
7
3
,

 
 
1
5
2
,

 
 
2
2
,

 
 
3
,

 
 
1
7
3
8
,

 
 
4
,

 
 
9
4
5
6
,

 
 
1
0
,

 
 
1
3
8
,

 
 
2
5
0
,

 
 
1
1
,

 
 
8
,

 
 
2
7
,

 
 
6
,

 
 
1
5
3
5
,

 
 
1
3
,

 
 
7
8
,

 
 
1
1
1
]
,

 
[
1
0
0
,

 
 
7
,

 
 
5
1
6
,

 
 
6
7
,

 
 
3
,

 
 
1
1
3
,

 
 
9
5
,

 
 
1
4
9
8
,

 
 
3
3
6
,

 
 
1
3
2
,

 
 
6
4
9
3
,

 
 
1
7
,

 
 
1
6
3
,

 
 
2
9
,

 
 
1
0
,

 
 
4
9
1
,

 
 
5
,

 
 
2
9
0
,

 
 
3
2
,

 
 
2
6
,

 
 
1
2
8
5
,

 
 
4
1
,

 
 
5
,

 
 
8
,

 
 
6
6
8
,

 
 
4
1
,

 
 
5
,

 
 
1
0
7
,

 
 
1
,

 
 
2
9
5
,

 
 
3
6
9
2
,

 
 
2
1
7
,

 
 
2
2
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
1
4
3
,

 
 
7
,

 
 
1
,

 
 
3
8
9
,

 
 
6
5
,

 
 
5
,

 
 
4
6
,

 
 
1
9
4
2
,

 
 
1
5
5
2
,

 
 
1
9
4
2
,

 
 
3
,

 
 
2
8
,

 
 
2
1
,

 
 
8
0
0
]
,

 
[
3
,

 
 
7
6
,

 
 
1
6
,

 
 
1
,

 
 
2
3
6
2
,

 
 
1
9
0
5
0
,

 
 
1
5
2
9
,

 
 
5
1
,

 
 
1
8
5
1
,

 
 
3
,

 
 
4
4
5
4
,

 
 
3
2
2
3
,

 
 
2
1
,

 
 
1
,

 
 
1
4
8
1
5
,

 
 
6
0
3
7
,

 
 
4
5
,

 
 
8
,

 
 
3
8
,

 
 
7
1
,

 
 
7
,

 
 
9
,

 
 
3
2
5
4
,

 
 
5
8
,

 
 
1
7
4
3
,

 
 
6
,

 
 
1
1
7
1
,

 
 
2
,

 
 
2
6
9
8
,

 
 
7
6
9
6
,

 
 
7
,

 
 
1
,

 
 
1
0
6
1
,

 
 
9
5
6
,

 
 
3
,

 
 
1
7
5
8
,

 
 
3
,

 
 
5
8
,

 
 
1
2
4
9
,

 
 
2
2
8
,

 
 
1
3
,

 
 
5
4
,

 
 
1
4
8
1
6
,

 
 
2
,

 
 
1
,

 
 
6
0
3
,

 
 
3
8
0
7
,

 
 
1
4
,

 
 
1
8
2
]
,

 
[
5
3
,

 
 
1
1
8
,

 
 
5
,

 
 
9
4
,

 
 
4
8
,

 
 
6
5
2
,

 
 
5
,

 
 
1
3
3
,

 
 
2
9
0
,

 
 
3
4
,

 
 
5
6
,

 
 
2
8
8
,

 
 
1
7
,

 
 
1
2
9
,

 
 
2
9
0
,

 
 
1
8
,

 
 
1
6
4
,

 
 
1
6
4
,

 
 
1
3
,

 
 
2
2
,

 
 
2
3
6
3
,

 
 
1
2
4
,

 
 
5
,

 
 
8
4
,

 
 
2
0
,

 
 
1
5
9
2
,

 
 
3
4
,

 
 
1
1
8
,

 
 
4
2
1
,

 
 
6
,

 
 
6
0
3
8
,

 
 
2
1
,

 
 
1
,

 
 
1
9
6
4
,

 
 
2
1
2
6
,

 
 
1
4
1
,

 
 
7
6
,

 
 
2
3
7
,

 
 
3
4
,

 
 
3
1
,

 
 
7
2
,

 
 
1
6
4
,

 
 
6
5
3
,

 
 
1
6
4
,

 
 
1
3
,

 
 
2
2
,

 
 
4
,

 
 
4
8
9
,

 
 
3
,

 
 
4
1
9
9
,

 
 
2
2
,

 
 
4
1
,

 
 
5
,

 
 
1
4
3
,

 
 
3
0
,

 
 
1
0
7
2
2
,

 
 
6
0
3
9
,

 
 
1
0
0
,

 
 
1
3
,

 
 
3
8
4
3
,

 
 
1
3
1
2
,

 
 
9
4
5
7
,

 
 
6
0
9
,

 
 
3
,

 
 
3
2
5
5
,

 
 
1
3
1
1
,

 
 
4
8
,

 
 
1
0
7
2
3
,

 
 
3
0
,

 
 
3
2
1
,

 
 
1
,

 
 
2
4
9
,

 
 
1
4
9
4
,

 
 
5
1
4
,

 
 
2
2
,

 
 
2
5
,

 
 
4
8
,

 
 
2
3
6
,

 
 
5
5
0
,

 
 
5
0
9
,

 
 
3
8
,

 
 
3
,

 
 
5
,

 
 
3
8
4
8
,

 
 
3
0
,

 
 
4
,

 
 
1
0
,

 
 
1
3
5
,

 
 
3
3
4
,

 
 
1
5
2
5
,

 
 
5
9
,

 
 
3
0
3
4
,

 
 
1
6
3
7
,

 
 
4
3
6
,

 
 
1
0
,

 
 
5
9
6
,

 
 
5
,

 
 
6
2
,

 
 
1
8
7
,

 
 
6
,

 
 
4
4
0
,

 
 
3
3
,

 
 
5
6
,

 
 
2
7
2
9
]
,

 
[
1
0
,

 
 
7
0
2
7
,

 
 
1
3
9
,

 
 
2
9
,

 
 
8
8
1
,

 
 
1
2
3
2
1
,

 
 
4
2
,

 
 
2
9
,

 
 
1
9
4
7
,

 
 
4
,

 
 
1
,

 
 
1
4
8
1
7
,

 
 
2
,

 
 
1
6
7
6
,

 
 
4
6
9
7
,

 
 
1
4
2
5
,

 
 
5
1
9
,

 
 
9
7
,

 
 
2
3
0
,

 
 
5
,

 
 
8
6
6
,

 
 
4
,

 
 
3
1
,

 
 
4
3
,

 
 
1
9
0
5
1
,

 
 
3
5
,

 
 
6
8
,

 
 
2
3
0
,

 
 
2
1
2
7
,

 
 
5
2
9
0
,

 
 
3
,

 
 
3
0
7
]
,

 
[
1
8
,

 
 
5
,

 
 
8
,

 
 
4
6
9
8
,

 
 
2
3
,

 
 
1
,

 
 
3
5
8
,

 
 
2
,

 
 
1
,

 
 
3
1
2
8
,

 
 
1
2
4
,

 
 
1
,

 
 
1
2
6
8
,

 
 
3
,

 
 
8
1
8
,

 
 
4
6
,

 
 
2
0
,

 
 
3
3
6
9
,

 
 
1
,

 
 
3
7
7
,

 
 
8
,

 
 
2
6
1
6
,

 
 
3
,

 
 
1
1
,

 
 
9
1
9
,

 
 
4
,

 
 
2
2
,

 
 
6
5
,

 
 
1
6
,

 
 
2
1
7
0
,

 
 
3
,

 
 
1
2
8
6
,

 
 
6
,

 
 
2
9
1
6
,

 
 
1
6
,

 
 
5
2
9
1
,

 
 
2
2
3
,

 
 
4
,

 
 
1
,

 
 
7
0
2
8
,

 
 
2
,

 
 
1
5
6
6
,

 
 
8
2
,

 
 
5
1
,

 
 
2
9
2
1
,

 
 
7
,

 
 
1
,

 
 
9
8
4
,

 
 
2
,

 
 
4
4
0
]
,

 
[
3
,
 
1
1
,
 
8
,
 
1
7
5
,
 
6
,
 
9
4
5
8
,
 
3
6
9
3
,
 
2
9
1
,
 
9
,
 
5
,
 
1
0
7
,
 
1
,
 
2
2
7
,
 
1
7
,
 
1
,
 
8
3
,
 
7
2
]
,

 
[
5
,
 
8
2
0
,
 
4
,
 
9
5
1
,
 
1
0
,
 
1
0
2
4
]
,

 
[
4
8
,

 
 
5
2
3
,

 
 
6
7
,

 
 
6
9
8
4
,

 
 
2
,

 
 
1
9
5
1
,

 
 
1
5
2
,

 
 
1
3
,

 
 
3
0
3
2
,

 
 
4
8
,

 
 
7
3
,

 
 
2
0
,

 
 
7
0
2
9
,

 
 
1
5
,

 
 
7
1
3
,

 
 
1
8
,

 
 
4
8
,

 
 
9
9
0
,

 
 
4
,

 
 
1
4
9
,

 
 
6
,

 
 
3
0
3
5
,

 
 
7
,

 
 
1
,

 
 
1
6
6
,

 
 
2
,

 
 
1
0
6
2
,

 
 
2
2
9
4
,

 
 
3
5
,

 
 
1
1
4
5
,

 
 
2
4
2
2
,

 
 
1
9
,

 
 
1
5
6
5
,

 
 
1
1
4
6
,

 
 
3
,

 
 
2
7
3
0
,

 
 
1
7
0
3
,

 
 
2
0
8
,

 
 
2
4
,

 
 
1
0
7
2
4
]
,

 
[
1
6
1
,

 
 
1
,

 
 
4
4
3
,

 
 
1
3
1
,

 
 
3
6
9
4
,

 
 
2
3
,

 
 
1
,

 
 
1
4
8
1
8
,

 
 
2
,

 
 
1
,

 
 
1
8
3
8
,

 
 
3
4
,

 
 
6
2
0
,

 
 
6
,

 
 
1
0
6
,

 
 
1
4
4
3
,

 
 
3
8
4
9
,

 
 
7
,

 
 
1
8
3
0
,

 
 
6
8
,

 
 
4
3
2
,

 
 
2
7
0
,

 
 
7
,

 
 
6
0
4
0
,

 
 
1
9
7
,

 
 
7
,

 
 
7
6
2
,

 
 
6
0
7
,

 
 
3
5
,

 
 
9
1
8
]
,

 
[
1
2
4
,

 
 
2
9
,

 
 
1
,

 
 
7
5
9
,

 
 
1
9
0
5
2
,

 
 
2
,

 
 
4
0
6
,

 
 
1
,

 
 
1
4
7
,

 
 
5
8
,

 
 
4
1
,

 
 
5
5
,

 
 
3
2
5
6
,

 
 
8
,

 
 
4
1
6
,

 
 
3
,

 
 
5
5
,

 
 
5
6
5
2
,

 
 
3
0
3
6
,

 
 
3
5
,

 
 
1
1
1
6
,

 
 
1
7
,

 
 
1
2
9
,

 
 
4
1
,

 
 
5
5
,

 
 
3
8
5
0
,

 
 
2
2
3
6
,

 
 
3
4
,

 
 
1
2
3
2
2
,

 
 
1
,

 
 
5
2
5
8
,

 
 
2
,

 
 
1
,

 
 
3
0
5
,

 
 
3
,

 
 
1
2
3
0
,

 
 
1
,

 
 
4
1
7
5
,

 
 
2
,

 
 
4
1
3
,

 
 
3
5
,

 
 
2
,

 
 
5
0
,

 
 
1
9
0
5
3
,

 
 
1
3
4
,

 
 
1
2
4
,

 
 
2
9
,

 
 
1
,

 
 
7
6
8
,

 
 
5
8
,

 
 
2
9
,

 
 
4
,

 
 
2
8
0
6
,

 
 
2
7
,

 
 
1
,

 
 
3
8
5
,

 
 
6
9
2
,

 
 
2
,

 
 
6
6
4
,

 
 
1
2
4
,

 
 
2
9
,

 
 
1
,

 
 
5
6
5
3
,

 
 
9
4
5
9
,

 
 
3
2
5
7
,

 
 
1
2
4
,

 
 
1
,

 
 
4
4
5
5
,

 
 
1
,

 
 
1
2
3
2
3
,

 
 
1
,

 
 
4
4
5
6
,

 
 
5
4
,

 
 
1
0
5
5
,

 
 
9
,

 
 
4
2
,

 
 
2
9
,

 
 
7
5
,

 
 
5
2
,

 
 
1
0
8
3
,

 
 
4
,

 
 
6
8
5
,

 
 
2
7
,

 
 
1
,

 
 
1
6
2
6
,

 
 
1
4
2
7
,

 
 
4
,

 
 
1
8
7
,

 
 
3
8
,

 
 
1
6
9
,

 
 
1
,

 
 
1
9
0
5
4
,

 
 
1
9
0
5
5
,

 
 
2
,

 
 
2
3
6
4
,

 
 
9
1
]
,

 
[
2
3
7
,

 
 
1
1
,

 
 
2
5
,

 
 
7
0
5
,

 
 
9
,

 
 
2
5
,

 
 
1
9
0
5
6
,

 
 
2
2
,

 
 
7
6
,

 
 
2
3
7
,

 
 
6
,

 
 
4
7
8
,

 
 
2
4
3
,

 
 
3
5
,

 
 
6
,

 
 
4
7
8
,

 
 
6
4
9
4
,

 
 
2
5
,

 
 
2
5
3
0
,

 
 
7
4
]
,

 
[
2
6
,
 
1
8
2
8
,
 
1
8
,
 
1
0
4
,
 
5
2
9
,
 
1
,
 
5
6
5
4
]
,

 
[
1
2
4
,
 
1
2
3
9
,
 
8
,
 
1
,
 
1
2
3
2
4
,
 
2
,
 
1
,
 
4
2
1
9
]
,

 
[
1
4
,

 
 
1
2
,

 
 
4
3
,

 
 
1
6
4
0
,

 
 
4
,

 
 
1
5
0
,

 
 
1
1
,

 
 
2
5
,

 
 
1
6
0
,

 
 
1
8
,

 
 
1
,

 
 
3
6
2
,

 
 
7
,

 
 
1
,

 
 
2
0
9
4
,

 
 
1
1
,

 
 
2
5
,

 
 
6
4
,

 
 
6
,

 
 
1
4
8
1
9
,

 
 
3
0
0
7
,

 
 
1
,

 
 
3
4
9
,

 
 
3
5
,

 
 
1
1
,

 
 
2
5
,

 
 
4
1
0
,

 
 
6
,

 
 
1
9
0
5
7
,

 
 
1
9
,

 
 
1
0
8
,

 
 
9
2
,

 
 
6
,

 
 
5
7
8
,

 
 
1
2
3
2
5
]
,

 
[
1
3
1
,

 
 
1
1
,

 
 
9
8
,

 
 
4
,

 
 
2
2
,

 
 
1
0
0
2
,

 
 
9
,

 
 
1
0
,

 
 
2
4
5
7
,

 
 
2
,

 
 
2
3
6
5
,

 
 
8
,

 
 
2
0
,

 
 
6
4
,

 
 
2
7
,

 
 
1
,

 
 
1
5
1
6
,

 
 
1
8
,

 
 
9
,

 
 
1
,

 
 
7
6
9
7
,

 
 
4
9
,

 
 
3
1
,

 
 
4
3
,

 
 
6
5
1
,

 
 
7
,

 
 
6
,

 
 
6
1
9
,

 
 
4
9
9
,

 
 
7
5
,

 
 
1
2
,

 
 
5
,

 
 
2
0
,

 
 
7
0
3
0
,

 
 
1
,

 
 
3
1
4
2
,

 
 
1
9
,

 
 
5
,

 
 
7
3
]
,

 
[
6
,

 
 
4
0
1
,

 
 
2
9
9
8
,

 
 
2
9
9
7
,

 
 
8
1
,

 
 
9
,

 
 
2
6
2
9
,

 
 
2
4
,

 
 
6
,

 
 
2
2
2
,

 
 
1
8
,

 
 
1
5
5
2
,

 
 
3
9
7
6
,

 
 
4
3
5
,

 
 
1
1
7
,

 
 
4
,

 
 
1
0
,

 
 
6
6
7
,

 
 
9
4
6
0
,

 
 
1
3
,

 
 
1
,

 
 
5
1
2
,

 
 
5
2
9
2
,

 
 
2
,

 
 
7
0
3
1
,

 
 
1
8
1
,

 
 
1
0
3
3
]
,

 
[
5
,

 
 
1
5
5
9
,

 
 
9
,

 
 
1
,

 
 
1
1
3
7
,

 
 
1
2
4
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
2
3
2
6
,

 
 
1
8
,

 
 
4
5
,

 
 
1
2
3
,

 
 
2
8
,

 
 
2
2
6
,

 
 
7
5
,

 
 
2
0
2
,

 
 
1
1
]
,

 
[
1
3
6
6
,

 
 
1
2
8
,

 
 
1
,

 
 
2
9
0
0
,

 
 
2
,

 
 
3
0
3
7
,

 
 
1
7
8
2
,

 
 
3
,

 
 
5
8
,

 
 
1
7
,

 
 
1
,

 
 
1
2
4
0
,

 
 
2
,

 
 
3
0
,

 
 
2
7
9
,

 
 
3
6
9
5
,

 
 
1
2
,

 
 
7
6
9
5
,

 
 
1
,

 
 
9
3
7
,

 
 
4
5
6
,

 
 
3
,

 
 
6
5
,

 
 
1
7
9
7
,

 
 
2
3
,

 
 
3
9
,

 
 
4
8
,

 
 
4
9
7
,

 
 
1
3
,

 
 
4
0
2
8
,

 
 
6
1
8
,

 
 
3
,

 
 
6
,

 
 
1
2
3
2
7
,

 
 
3
6
6
,

 
 
2
,

 
 
4
6
7
,

 
 
1
2
,

 
 
4
4
7
,

 
 
4
,

 
 
3
0
,

 
 
7
1
6
,

 
 
1
2
3
5
]
,

 
[
2
3
,

 
 
2
4
8
1
,

 
 
1
6
,

 
 
5
,

 
 
1
2
5
,

 
 
1
,

 
 
1
2
3
2
8
,

 
 
1
0
3
9
,

 
 
7
,

 
 
3
2
,

 
 
1
0
,

 
 
1
2
3
2
9
,

 
 
3
,

 
 
1
9
6
5
,

 
 
6
,

 
 
1
1
6
,

 
 
4
9
6
3
,

 
 
3
2
0
,

 
 
2
,

 
 
6
2
7
,

 
 
5
,

 
 
8
,

 
 
1
6
9
2
,

 
 
4
,

 
 
4
2
1
,

 
 
8
7
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

 
 
4
0
2
9
,

 
 
3
,

 
 
7
,

 
 
1
,

 
 
2
4
4
,

 
 
4
,

 
 
4
4
2
7
,

 
 
1
1
0
,

 
 
6
1
,

 
 
1
2
3
3
0
,

 
 
7
,

 
 
1
,

 
 
3
8
1
8
]
,

 
[
1
8
,

 
 
5
,

 
 
8
,

 
 
2
3
6
6
,

 
 
5
5
8
2
,

 
 
3
,

 
 
9
6
9
,

 
 
4
,

 
 
4
6
9
9
,

 
 
1
0
,

 
 
9
0
4
,

 
 
8
8
1
,

 
 
4
,

 
 
6
1
4
,

 
 
1
,

 
 
2
2
2
,

 
 
6
4
8
,

 
 
2
,

 
 
1
5
,

 
 
3
6
4
1
]
,

 
[
1
8
,

 
 
2
6
,

 
 
1
2
1
,

 
 
1
9
,

 
 
3
6
9
6
,

 
 
2
2
,

 
 
7
,

 
 
1
,

 
 
3
5
1
7
,

 
 
2
,

 
 
1
0
,

 
 
2
6
1
9
,

 
 
5
2
,

 
 
1
4
8
2
0
,

 
 
6
4
,

 
 
4
,

 
 
2
5
2
3
,

 
 
2
2
,

 
 
1
0
4
2
,

 
 
7
,

 
 
1
,

 
 
1
8
4
1
]
,

 
[
1
0
2
,

 
 
3
7
2
,

 
 
6
0
,

 
 
1
7
,

 
 
3
8
,

 
 
6
3
2
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

 
 
5
3
,

 
 
8
0
,

 
 
2
8
,

 
 
1
,

 
 
1
7
9
8
,

 
 
2
2
9
5
,

 
 
2
,

 
 
1
0
,

 
 
3
2
5
8
,

 
 
5
2
7
1
,

 
 
5
,

 
 
4
9
,

 
 
2
8
4
,

 
 
3
1
,

 
 
5
6
5
5
,

 
 
1
1
0
,

 
 
8
0
6
,

 
 
2
4
,

 
 
1
0
,

 
 
7
1
6
,

 
 
2
9
2
,

 
 
3
,

 
 
1
3
1
3
,

 
 
6
,

 
 
9
4
6
1
,

 
 
7
0
3
2
,

 
 
8
7
,

 
 
1
,

 
 
1
5
5
,

 
 
5
9
,

 
 
3
1
,

 
 
3
5
1
8
,

 
 
4
,

 
 
2
6
,

 
 
6
5
5
,

 
 
1
6
4
1
]
,

 
[
9
7
,

 
 
5
8
,

 
 
3
1
,

 
 
9
0
6
,

 
 
1
,

 
 
8
4
5
,

 
 
3
1
1
3
,

 
 
3
3
5
,

 
 
7
9
,

 
 
7
1
,

 
 
7
,

 
 
6
7
,

 
 
5
1
2
,

 
 
7
0
3
3
,

 
 
9
4
,

 
 
2
0
,

 
 
8
5
2
,

 
 
3
9
,

 
 
1
1
5
]
,

 
[
2
6
,

 
 
2
4
9
,

 
 
1
7
8
,

 
 
1
2
8
,

 
 
7
5
0
,

 
 
4
4
,

 
 
1
0
,

 
 
5
4
4
,

 
 
1
0
5
4
,

 
 
6
2
2
,

 
 
1
1
,

 
 
3
,

 
 
5
,

 
 
2
9
0
,

 
 
1
1
0
,

 
 
2
0
5
1
,

 
 
7
,

 
 
1
4
8
2
1
]
,

 
[
2
2
7
2
,

 
 
6
,

 
 
1
8
5
2
,

 
 
2
1
2
8
,

 
 
2
1
,

 
 
2
6
,

 
 
1
7
1
,

 
 
3
,

 
 
4
0
3
0
,

 
 
1
,

 
 
6
9
3
,

 
 
2
,

 
 
1
,

 
 
1
6
5
,

 
 
6
9
2
,

 
 
4
7
0
0
,

 
 
2
1
,

 
 
1
,

 
 
1
7
7
,

 
 
7
2
,

 
 
6
,

 
 
1
2
1
8
,

 
 
1
5
8
,

 
 
2
5
,

 
 
6
1
0
,

 
 
5
7
9
,

 
 
8
8
,

 
 
1
,

 
 
3
3
7
0
,

 
 
1
9
,

 
 
2
5
,

 
 
5
2
,

 
 
1
4
5
4
,

 
 
1
7
0
,

 
 
4
,

 
 
2
8
,

 
 
2
2
2
,

 
 
1
7
1
6
,

 
 
2
2
2
,

 
 
2
,

 
 
1
7
5
9
]
,

 
[
1
,

 
 
3
3
7
1
,

 
 
2
,

 
 
1
,

 
 
5
2
9
3
,

 
 
2
9
,

 
 
7
0
3
4
,

 
 
5
7
,

 
 
4
0
,

 
 
1
1
3
,

 
 
4
0
3
1
,

 
 
5
2
4
,

 
 
3
,

 
 
4
5
,

 
 
8
,

 
 
3
6
,

 
 
4
0
3
1
,

 
 
1
4
1
,

 
 
2
,

 
 
6
3
,

 
 
3
2
,

 
 
5
0
,

 
 
7
0
3
5
,

 
 
3
5
,

 
 
5
0
,

 
 
6
4
9
5
,

 
 
5
9
,

 
 
9
,

 
 
2
,

 
 
1
,

 
 
1
7
4
6
]
,

 
[
3
8
9
,

 
 
2
3
8
,

 
 
1
0
9
4
,

 
 
1
5
,

 
 
2
9
2
2
,

 
 
2
2
3
7
,

 
 
1
4
8
2
2
,

 
 
1
2
,

 
 
7
6
1
6
,

 
 
2
9
2
3
,

 
 
1
3
,

 
 
1
8
9
,

 
 
5
8
5
,

 
 
7
0
3
6
,

 
 
3
,

 
 
1
5
,

 
 
1
2
3
3
1
,

 
 
6
0
4
1
,

 
 
3
,

 
 
3
6
9
7
,

 
 
3
7
,

 
 
2
4
7
9
,

 
 
4
4
5
1
,

 
 
8
5
1
7
,

 
 
1
3
,

 
 
6
,

 
 
5
5
5
,

 
 
4
,

 
 
1
3
4
3
,

 
 
1
5
,

 
 
2
5
0
8
,

 
 
4
,

 
 
6
7
,

 
 
6
4
6
0
,

 
 
1
9
0
5
8
,

 
 
7
,

 
 
5
4
,

 
 
2
8
1
9
,

 
 
3
,

 
 
1
0
7
2
5
,

 
 
1
0
6
8
]
,

 
[
3
1
4
3
,
 
9
4
,
 
3
3
,
 
1
0
6
,
 
3
6
0
]
,

 
[
5
4
,

 
 
7
2
,

 
 
6
9
,

 
 
1
3
9
0
,

 
 
1
5
,

 
 
2
1
2
9
,

 
 
5
8
5
,

 
 
1
2
3
3
2
,

 
 
2
8
9
,

 
 
4
,

 
 
1
2
6
,

 
 
3
9
,

 
 
3
,

 
 
2
8
2
0
,

 
 
9
,

 
 
1
4
,

 
 
2
3
6
0
,

 
 
3
4
0
]
,

 
[
7
,

 
 
2
6
,

 
 
2
5
6
,

 
 
5
,

 
 
1
2
3
3
3
,

 
 
1
0
,

 
 
2
1
6
3
,

 
 
4
1
,

 
 
5
,

 
 
8
3
,

 
 
5
8
4
,

 
 
1
8
,

 
 
1
6
,

 
 
5
,

 
 
6
3
4
,

 
 
7
,

 
 
1
0
,

 
 
1
6
0
3
,

 
 
1
1
,

 
 
1
6
2
,

 
 
1
0
1
,

 
 
1
1
2
,

 
 
5
0
,

 
 
6
0
6
,

 
 
3
,

 
 
4
9
6
4
,

 
 
4
,

 
 
2
2
]
,

 
[
8
9
,

 
 
6
,

 
 
1
1
9
5
,

 
 
1
0
8
,

 
 
6
5
,

 
 
5
2
7
,

 
 
4
6
2
,

 
 
5
,

 
 
2
6
9
,

 
 
3
0
7
,

 
 
1
1
,

 
 
7
6
,

 
 
5
,

 
 
1
3
3
,

 
 
2
9
0
,

 
 
7
,

 
 
1
4
7
9
,

 
 
3
,

 
 
1
2
1
9
]
,

 
[
2
3
,

 
 
1
,

 
 
2
8
2
1
,

 
 
2
,

 
 
2
6
,

 
 
7
6
6
,

 
 
1
,

 
 
4
4
5
7
,

 
 
2
5
,

 
 
9
2
,

 
 
4
,

 
 
1
2
3
3
4
,

 
 
1
3
,

 
 
1
0
2
,

 
 
3
1
1
6
,

 
 
7
6
9
8
,

 
 
6
,

 
 
8
5
1
8
,

 
 
6
8
2
,

 
 
4
,

 
 
1
,

 
 
1
6
5
]
,

 
[
1
,
 
5
2
9
4
,
 
1
2
,
 
9
0
,
 
1
7
,
 
3
7
,
 
6
3
2
,
 
4
3
,
 
2
9
0
]
,

 
[
1
9
6
6
,

 
 
1
,

 
 
7
6
9
9
,

 
 
6
8
,

 
 
1
5
,

 
 
4
7
0
1
,

 
 
1
1
,

 
 
8
,

 
 
1
8
,

 
 
1
,

 
 
3
4
0
,

 
 
2
,

 
 
6
,

 
 
1
5
6
,

 
 
3
5
1
9
,

 
 
4
,

 
 
1
6
5
7
,

 
 
1
1
]
,

 
[
1
1
,
 
8
,
 
2
4
8
,
 
5
7
4
,
 
5
7
4
,
 
2
4
8
,
 
3
,
 
5
,
 
3
2
4
,
 
3
9
9
8
,
 
1
6
,
 
5
,
 
9
6
3
,
 
4
4
,
 
1
1
]
,

 
[
7
2
1
,

 
 
4
6
,

 
 
2
0
,

 
 
2
8
,

 
 
6
1
,

 
 
5
8
0
,

 
 
6
8
,

 
 
1
5
,

 
 
2
4
1
9
,

 
 
1
7
,

 
 
2
6
,

 
 
1
5
1
,

 
 
6
4
9
6
,

 
 
1
8
,

 
 
1
5
,

 
 
1
9
0
5
9
,

 
 
1
2
4
,

 
 
8
,

 
 
5
0
,

 
 
5
9
,

 
 
1
9
0
6
0
,

 
 
2
3
,

 
 
1
5
,

 
 
5
6
5
6
,

 
 
2
7
,

 
 
9
5
,

 
 
4
4
5
8
,

 
 
9
7
5
]
,

 
[
3
3
,

 
 
9
3
,

 
 
3
1
,

 
 
1
7
0
,

 
 
1
2
0
,

 
 
9
4
6
2
,

 
 
5
,

 
 
6
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
5
2
0
,

 
 
1
3
,

 
 
5
3
,

 
 
1
0
7
2
6
,

 
 
1
3
,

 
 
5
3
,

 
 
1
9
0
6
1
,

 
 
5
,

 
 
2
3
3
,

 
 
4
,

 
 
3
4
0
,

 
 
5
,

 
 
8
,

 
 
9
0
,

 
 
5
2
9
5
,

 
 
4
,

 
 
1
,

 
 
7
9
,

 
 
7
1
,

 
 
5
9
,

 
 
1
9
5
,

 
 
1
,

 
 
1
6
5
,

 
 
9
6
8
,

 
 
6
9
,

 
 
5
,

 
 
2
2
9
6
,

 
 
3
9
]
,

 
[
1
1
,

 
 
2
5
,

 
 
8
1
5
,

 
 
1
7
,

 
 
3
8
,

 
 
4
0
,

 
 
2
3
8
,

 
 
5
8
,

 
 
8
,

 
 
1
2
8
,

 
 
4
0
,

 
 
4
1
1
,

 
 
1
6
,

 
 
5
,

 
 
8
,

 
 
2
5
3
7
,

 
 
7
7
0
0
,

 
 
4
,

 
 
9
4
6
3
,

 
 
3
4
5
,

 
 
2
,

 
 
3
2
,

 
 
1
1
9
6
,

 
 
3
,

 
 
4
,

 
 
2
6
8
,

 
 
2
0
6
,

 
 
4
,

 
 
1
,

 
 
2
3
6
7
,

 
 
5
3
7
,

 
 
5
,

 
 
9
2
3
,

 
 
2
0
]
,

 
[
1
,

 
 
1
0
8
5
,

 
 
2
,

 
 
9
,

 
 
1
1
8
5
,

 
 
5
,

 
 
2
6
9
,

 
 
9
7
1
,

 
 
5
,

 
 
8
4
,

 
 
3
1
,

 
 
4
3
,

 
 
5
5
0
,

 
 
1
7
,

 
 
1
1
,

 
 
9
8
,

 
 
4
,

 
 
8
7
3
,

 
 
2
5
3
8
,

 
 
3
,

 
 
8
5
1
9
,

 
 
3
0
3
8
,

 
 
3
,

 
 
3
1
4
4
,

 
 
1
4
8
2
3
,

 
 
1
,

 
 
1
6
4
2
,

 
 
4
4
5
9
,

 
 
9
0
2
,

 
 
2
,

 
 
4
7
,

 
 
1
2
3
3
5
,

 
 
4
9
6
5
,

 
 
1
,

 
 
4
3
8
,

 
 
8
1
,

 
 
1
,

 
 
7
0
3
7
,

 
 
2
,

 
 
6
,

 
 
1
1
6
6
,

 
 
2
7
,

 
 
6
,

 
 
5
6
2
,

 
 
7
4
4
]
,

 
[
3
,
 
4
1
,
 
7
3
,
 
1
,
 
2
2
9
7
,
 
4
4
6
0
,
 
1
0
1
5
,
 
6
7
3
,
 
2
,
 
3
0
,
 
8
5
2
0
,
 
7
,
 
6
3
7
]
,

 
[
7
,

 
 
3
0
,

 
 
1
2
3
3
6
,

 
 
3
3
7
2
,

 
 
6
7
,

 
 
2
4
7
7
,

 
 
1
2
,

 
 
4
3
,

 
 
8
2
1
,

 
 
1
3
,

 
 
1
9
0
6
2
,

 
 
3
,

 
 
3
6
7
3
,

 
 
4
2
,

 
 
9
4
8
,

 
 
3
0
,

 
 
7
,

 
 
3
0
,

 
 
2
7
3
1
,

 
 
3
0
5
,

 
 
7
4
9
,

 
 
3
6
0
,

 
 
2
4
,

 
 
3
0
,

 
 
9
9
,

 
 
3
2
,

 
 
2
5
1
,

 
 
2
,

 
 
4
3
6
,

 
 
2
4
,

 
 
3
0
,

 
 
2
6
3
0
,

 
 
1
3
8
]
,

 
[
3
7
2
,
 
1
4
8
2
4
,
 
1
0
,
 
1
7
3
0
,
 
3
,
 
2
4
0
5
,
 
2
2
,
 
8
5
1
,
 
4
,
 
1
7
2
9
,
 
1
,
 
1
6
4
3
]
,

 
[
4
7
6
,
 
4
5
,
 
2
9
,
 
3
5
4
]
,

 
[
1
5
,

 
 
1
1
1
,

 
 
2
3
5
,

 
 
8
,

 
 
7
,

 
 
4
9
6
,

 
 
3
,

 
 
1
4
,

 
 
1
3
8
5
,

 
 
6
,

 
 
5
7
4
,

 
 
1
4
8
2
5
,

 
 
3
8
4
1
,

 
 
1
9
,

 
 
2
6
3
1
,

 
 
7
7
0
1
,

 
 
1
4
8
8
,

 
 
1
3
,

 
 
1
,

 
 
7
4
,

 
 
2
,

 
 
1
7
8
1
,

 
 
3
4
7
7
,

 
 
1
4
,

 
 
2
0
1
2
,

 
 
1
8
,

 
 
5
,

 
 
8
,

 
 
5
6
5
7
,

 
 
1
2
3
3
7
,

 
 
7
5
,

 
 
6
9
,

 
 
1
4
,

 
 
1
8
5
3
,

 
 
2
2
]
,

 
[
5
3
,
 
9
5
,
 
3
5
3
,
 
3
4
3
,
 
4
6
,
 
4
5
,
 
3
1
,
 
4
3
,
 
1
7
,
 
3
0
,
 
4
0
,
 
1
2
3
3
8
]
,

 
[
5
,
 
4
6
,
 
2
0
,
 
3
1
,
 
4
3
,
 
5
0
,
 
1
7
5
2
,
 
2
1
,
 
1
,
 
2
8
2
,
 
2
,
 
1
,
 
9
4
6
4
,
 
2
,
 
1
,
 
7
7
0
2
]
,

 
[
3
,

 
 
1
2
4
,

 
 
1
2
0
,

 
 
2
0
4
8
,

 
 
5
9
0
,

 
 
9
,

 
 
3
5
9
,

 
 
1
9
,

 
 
2
,

 
 
7
9
,

 
 
8
,

 
 
3
9
7
5
,

 
 
4
,

 
 
6
5
9
,

 
 
4
6
1
,

 
 
4
,

 
 
3
2
,

 
 
1
5
3
6
,

 
 
1
9
6
6
,

 
 
6
,

 
 
7
7
0
3
,

 
 
4
4
,

 
 
3
2
,

 
 
2
8
2
2
,

 
 
4
4
6
0
]
,

 
[
1
3
5
4
,

 
 
3
8
5
1
,

 
 
4
4
,

 
 
6
7
,

 
 
9
7
5
,

 
 
5
,

 
 
3
7
9
,

 
 
1
7
,

 
 
3
7
,

 
 
3
0
5
,

 
 
2
3
7
,

 
 
1
8
5
,

 
 
1
9
1
3
,

 
 
1
8
5
,

 
 
1
4
8
2
6
,

 
 
1
3
,

 
 
1
0
,

 
 
9
2
9
,

 
 
4
0
3
2
,

 
 
4
4
,

 
 
1
,

 
 
3
8
1
4
]
,

 
[
4
4
,
 
1
0
,
 
3
5
9
,
 
2
,
 
2
2
8
8
,
 
2
6
,
 
8
,
 
2
0
,
 
3
7
,
 
6
0
4
2
,
 
3
1
4
5
,
 
1
7
,
 
9
,
 
1
2
3
3
9
]
,

 
[
3
4
7
,

 
 
2
2
,

 
 
1
,

 
 
2
5
5
,

 
 
2
,

 
 
1
9
2
,

 
 
5
,

 
 
6
2
,

 
 
1
4
8
2
7
,

 
 
4
7
,

 
 
1
7
6
0
,

 
 
3
,

 
 
6
0
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
7
7
0
4
,

 
 
3
,

 
 
6
2
8
,

 
 
4
9
,

 
 
9
5
6
,

 
 
3
4
5
,

 
 
5
7
,

 
 
1
6
3
,

 
 
1
8
0
,

 
 
2
2
,

 
 
2
8
,

 
 
2
2
0
,

 
 
4
,

 
 
3
5
5
,

 
 
8
0
0
,

 
 
4
,

 
 
7
8
,

 
 
1
9
0
6
3
,

 
 
2
1
9
]
,

 
[
1
,
 
2
2
1
4
,
 
2
4
,
 
1
,
 
9
4
6
5
,
 
1
0
8
8
,
 
6
4
9
7
,
 
4
7
,
 
5
6
5
8
,
 
2
1
1
9
]
,

 
[
1
,

 
 
1
0
0
1
,

 
 
1
0
8
,

 
 
2
6
0
6
,

 
 
5
4
,

 
 
2
5
3
9
,

 
 
3
3
7
3
,

 
 
5
4
,

 
 
1
9
0
6
4
,

 
 
3
2
5
9
,

 
 
2
1
,

 
 
1
,

 
 
8
5
2
1
,

 
 
3
5
,

 
 
2
3
7
,

 
 
1
,

 
 
7
0
3
8
,

 
 
2
,

 
 
1
,

 
 
1
9
0
6
5
,

 
 
4
7
0
2
,

 
 
3
5
,

 
 
1
,

 
 
1
0
7
2
7
,

 
 
2
,

 
 
1
5
,

 
 
1
8
4
,

 
 
1
1
5
1
,

 
 
3
5
,

 
 
1
,

 
 
7
0
3
9
,

 
 
1
1
9
,

 
 
2
,

 
 
6
,

 
 
4
0
3
3
,

 
 
1
1
6
6
,

 
 
3
5
,

 
 
1
5
3
,

 
 
6
,

 
 
1
4
8
2
8
,

 
 
2
,

 
 
6
,

 
 
1
5
6
,

 
 
1
2
3
4
0
]
,

 
[
5
,

 
 
8
0
,

 
 
1
6
,

 
 
1
1
6
,

 
 
3
1
,

 
 
2
4
6
2
,

 
 
4
,

 
 
5
2
9
6
,

 
 
3
7
,

 
 
5
6
5
9
,

 
 
1
1
9
,

 
 
1
0
6
,

 
 
9
4
6
6
,

 
 
1
0
6
,

 
 
3
9
7
8
,

 
 
1
1
9
,

 
 
5
,

 
 
3
1
0
7
,

 
 
3
,

 
 
1
9
9
4
,

 
 
2
1
,

 
 
1
8
6
,

 
 
6
0
4
3
]
,

 
[
4
2
,

 
 
5
8
,

 
 
3
5
2
,

 
 
2
3
,

 
 
1
1
2
,

 
 
5
6
,

 
 
4
9
6
6
,

 
 
2
,

 
 
1
1
3
,

 
 
1
4
2
,

 
 
1
9
,

 
 
6
1
3
,

 
 
9
7
,

 
 
5
8
,

 
 
3
5
2
,

 
 
6
4
,

 
 
2
3
,

 
 
1
0
3
]
,

 
[
1
0
9
,

 
 
3
,

 
 
3
8
5
1
,

 
 
7
3
,

 
 
5
,

 
 
1
6
3
8
,

 
 
1
,

 
 
1
9
6
7
,

 
 
1
8
,

 
 
1
,

 
 
6
0
4
4
,

 
 
1
7
8
7
,

 
 
2
,

 
 
1
0
,

 
 
6
0
4
5
,

 
 
3
,

 
 
5
6
6
0
,

 
 
9
2
0
,

 
 
4
,

 
 
2
8
,

 
 
6
4
,

 
 
6
,

 
 
3
2
0
,

 
 
2
,

 
 
2
0
1
4
,

 
 
1
1
3
8
,

 
 
1
2
2
,

 
 
1
9
1
0
,

 
 
2
,

 
 
1
4
8
2
9
,

 
 
3
7
,

 
 
3
1
1
,

 
 
3
,

 
 
6
,

 
 
5
2
9
7
,

 
 
2
,

 
 
1
4
8
3
0
,

 
 
1
4
8
3
1
,

 
 
2
4
,

 
 
2
5
2
,

 
 
9
4
6
7
,

 
 
4
,

 
 
1
0
,

 
 
5
5
3
]
,

 
[
8
2
,

 
 
1
0
2
,

 
 
1
0
6
3
,

 
 
1
1
5
2
,

 
 
2
3
,

 
 
1
,

 
 
1
4
8
3
2
,

 
 
7
0
4
0
,

 
 
2
,

 
 
1
5
,

 
 
1
0
7
2
8
,

 
 
1
9
5
,

 
 
1
,

 
 
3
0
2
,

 
 
1
2
1
1
,

 
 
1
4
,

 
 
2
1
,

 
 
1
9
1
,

 
 
7
9
5
,

 
 
7
,

 
 
1
2
3
4
1
,

 
 
1
1
,

 
 
5
6
4
2
,

 
 
2
1
,

 
 
1
5
,

 
 
1
1
1
,

 
 
1
9
4
5
,

 
 
7
,

 
 
1
1
2
0
,

 
 
1
0
5
,

 
 
2
0
,

 
 
4
,

 
 
5
6
6
1
,

 
 
3
4
6
,

 
 
1
5
0
,

 
 
1
,

 
 
4
9
0
9
,

 
 
8
2
3
,

 
 
2
,

 
 
1
5
,

 
 
8
5
2
2
,

 
 
1
4
,

 
 
5
3
2
,

 
 
1
1
,

 
 
9
9
5
,

 
 
3
5
0
4
,

 
 
2
5
0
,

 
 
8
9
,

 
 
7
2
,

 
 
1
6
,

 
 
1
1
,

 
 
9
3
,

 
 
4
6
8
2
,

 
 
2
4
,

 
 
6
,

 
 
2
1
2
4
,

 
 
7
,

 
 
1
,

 
 
8
2
8
,

 
 
5
2
3
,

 
 
2
4
,

 
 
6
,

 
 
1
4
8
3
3
,

 
 
2
7
,

 
 
1
1
0
3
,

 
 
7
2
6
]
,

 
[
1
1
,

 
 
8
,

 
 
3
7
,

 
 
6
0
3
,

 
 
3
0
9
,

 
 
3
,

 
 
2
7
5
,

 
 
5
,

 
 
8
,

 
 
1
7
6
,

 
 
4
,

 
 
1
8
4
,

 
 
4
0
6
,

 
 
5
,

 
 
1
2
,

 
 
9
0
,

 
 
2
5
7
,

 
 
4
7
,

 
 
8
1
,

 
 
6
9
]
,

 
[
1
1
,

 
 
8
,

 
 
6
,

 
 
9
7
6
,

 
 
6
,

 
 
1
5
9
5
,

 
 
4
,

 
 
2
1
2
,

 
 
1
2
3
4
2
,

 
 
3
,

 
 
1
9
0
6
6
,

 
 
2
,

 
 
1
9
,

 
 
1
9
0
6
7
,

 
 
3
1
,

 
 
1
9
4
4
,

 
 
3
,

 
 
1
1
7
2
,

 
 
2
0
1
,

 
 
1
,

 
 
1
1
3
9
,

 
 
8
,

 
 
2
3
8
,

 
 
3
,

 
 
1
9
,

 
 
9
9
6
,

 
 
4
,

 
 
1
4
8
3
4
,

 
 
3
,

 
 
2
9
2
4
,

 
 
2
0
2
,

 
 
1
,

 
 
1
9
7
,

 
 
2
3
4
1
,

 
 
3
,

 
 
3
8
5
2
,

 
 
2
,

 
 
9
1
,

 
 
3
,

 
 
2
6
1
,

 
 
9
,

 
 
3
4
,

 
 
1
4
4
]
,

 
[
1
6
,

 
 
1
,

 
 
3
0
5
,

 
 
1
7
,

 
 
4
7
,

 
 
1
4
7
5
,

 
 
7
0
7
,

 
 
2
2
0
,

 
 
5
,

 
 
1
0
4
3
,

 
 
6
,

 
 
3
2
5
,

 
 
8
4
3
2
,

 
 
2
,

 
 
1
,

 
 
8
5
2
3
,

 
 
4
,

 
 
9
5
,

 
 
8
3
8
,

 
 
6
6
,

 
 
1
,

 
 
2
6
5
,

 
 
3
5
,

 
 
4
,

 
 
1
,

 
 
5
2
9
8
,

 
 
7
7
0
5
,

 
 
5
1
4
,

 
 
1
,

 
 
1
3
1
4
]
,

 
[
1
1
,

 
 
9
1
0
,

 
 
4
,

 
 
2
2
,

 
 
2
8
4
,

 
 
4
0
3
4
,

 
 
9
,

 
 
5
,

 
 
9
4
,

 
 
2
0
,

 
 
1
7
,

 
 
4
2
,

 
 
2
9
,

 
 
3
3
5
,

 
 
1
6
9
5
,

 
 
1
9
,

 
 
5
,

 
 
1
8
5
4
,

 
 
5
0
,

 
 
8
8
,

 
 
5
2
9
9
,

 
 
4
2
2
6
,

 
 
5
9
,

 
 
8
8
,

 
 
1
5
6
7
,

 
 
6
4
9
8
]
,

 
[
3
0
,
 
1
8
9
3
,
 
2
9
,
 
4
1
6
,
 
3
,
 
4
6
7
3
]
,

 
[
3
2
,
 
9
2
,
 
5
4
6
,
 
1
9
0
6
8
,
 
6
4
9
9
]
,

 
[
4
8
,

 
 
2
5
,

 
 
6
1
,

 
 
7
0
4
1
,

 
 
3
,

 
 
4
5
3
,

 
 
3
,

 
 
3
8
5
3
,

 
 
1
8
4
0
,

 
 
1
6
,

 
 
5
,

 
 
7
7
2
,

 
 
6
9
,

 
 
3
0
,

 
 
4
2
2
7
,

 
 
3
,

 
 
3
0
,

 
 
4
8
8
,

 
 
2
0
1
5
,

 
 
5
3
0
0
,

 
 
2
2
,

 
 
2
,

 
 
1
0
,

 
 
3
6
8
,

 
 
2
0
1
6
]
,

 
[
1
9
0
,
 
8
2
,
 
3
4
,
 
1
4
3
,
 
9
,
 
1
,
 
3
6
7
,
 
1
0
3
5
,
 
1
2
,
 
1
1
1
9
,
 
6
,
 
5
5
5
,
 
4
,
 
1
2
6
,
 
1
0
,
 
1
8
4
6
]
,

 
[
3
8
1
,

 
 
6
8
,

 
 
5
,

 
 
1
0
7
,

 
 
9
,

 
 
1
,

 
 
2
5
4
0
,

 
 
8
,

 
 
3
3
7
4
,

 
 
3
,

 
 
3
5
2
1
,

 
 
1
,

 
 
1
4
8
3
5
,

 
 
5
7
7
,

 
 
2
7
1
3
,

 
 
2
4
,

 
 
6
,

 
 
9
0
9
,

 
 
2
7
,

 
 
1
,

 
 
3
0
1
,

 
 
3
4
6
,

 
 
1
,

 
 
2
6
5
]
,

 
[
9
4
6
8
,
 
2
7
,
 
1
,
 
2
2
2
2
,
 
8
,
 
3
2
3
9
,
 
2
,
 
6
5
0
0
,
 
3
6
1
,
 
8
5
8
,
 
9
1
,
 
3
5
,
 
1
6
4
2
]
,

 
[
3
4
,

 
 
3
7
0
,

 
 
2
,

 
 
1
1
4
4
,

 
 
3
,

 
 
2
7
3
2
,

 
 
7
,

 
 
1
2
0
2
,

 
 
3
,

 
 
2
1
7
1
,

 
 
1
0
1
7
,

 
 
3
4
,

 
 
5
4
4
,

 
 
6
,

 
 
4
5
9
,

 
 
7
9
8
,

 
 
1
6
,

 
 
6
,

 
 
4
8
6
,

 
 
3
,

 
 
2
1
7
2
,

 
 
2
1
8
,

 
 
1
6
,

 
 
1
4
8
3
6
,

 
 
3
,

 
 
1
0
1
9
,

 
 
4
7
5
,

 
 
4
0
,

 
 
9
,

 
 
1
,

 
 
8
6
,

 
 
1
8
9
1
,

 
 
2
,

 
 
1
,

 
 
1
3
6
0
,

 
 
1
1
8
,

 
 
1
3
4
2
,

 
 
9
6
4
,

 
 
3
,

 
 
5
4
7
,

 
 
7
,

 
 
1
,

 
 
1
4
4
9
,

 
 
2
,

 
 
1
,

 
 
3
2
6
0
]
,

 
[
1
3
3
1
,

 
 
7
,

 
 
4
0
2
6
,

 
 
1
9
,

 
 
1
9
5
3
,

 
 
5
5
,

 
 
1
6
5
,

 
 
3
4
2
,

 
 
1
1
,

 
 
1
2
,

 
 
4
3
,

 
 
2
9
6
,

 
 
6
,

 
 
1
1
2
1
,

 
 
2
0
1
,

 
 
3
6
1
,

 
 
2
,

 
 
8
5
,

 
 
1
2
,

 
 
4
2
9
,

 
 
2
4
0
1
,

 
 
3
5
,

 
 
5
2
3
,

 
 
6
,

 
 
6
0
4
6
,

 
 
3
5
,

 
 
5
0
,

 
 
5
9
,

 
 
3
6
9
8
,

 
 
2
1
,

 
 
1
,

 
 
1
0
9
5
,

 
 
4
0
3
5
,

 
 
1
7
1
7
,

 
 
7
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
1
2
8
2
,

 
 
1
3
6
5
]
,

 
[
2
0
5
3
,

 
 
1
1
,

 
 
2
0
,

 
 
1
8
0
,

 
 
1
,

 
 
7
0
2
8
,

 
 
4
2
2
,

 
 
3
,

 
 
6
0
4
7
,

 
 
1
,

 
 
1
9
6
8
,

 
 
2
5
,

 
 
1
3
,

 
 
8
5
,

 
 
1
8
0
,

 
 
8
5
,

 
 
6
2
,

 
 
1
1
,

 
 
3
,

 
 
5
5
,

 
 
3
0
2
7
,

 
 
2
3
5
1
,

 
 
6
,

 
 
2
1
5
3
]
,

 
[
3
0
,
 
1
0
4
2
,
 
2
0
9
2
,
 
2
9
,
 
1
2
3
2
,
 
4
9
6
7
]
,

 
[
2
7
,

 
 
4
9
0
7
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
1
9
0
6
9
,

 
 
1
1
1
5
,

 
 
1
3
,

 
 
1
,

 
 
1
4
8
3
7
,

 
 
3
2
6
1
,

 
 
1
0
7
,

 
 
6
,

 
 
1
2
8
7
,

 
 
6
3
3
,

 
 
2
7
2
5
,

 
 
1
1
9
,

 
 
1
,

 
 
7
0
4
2
]
,

 
[
5
,

 
 
1
3
3
,

 
 
6
,

 
 
1
2
3
4
3
,

 
 
3
,

 
 
1
1
3
2
,

 
 
4
,

 
 
3
9
,

 
 
1
8
,

 
 
4
,

 
 
2
2
,

 
 
2
6
,

 
 
2
5
,

 
 
3
2
,

 
 
2
3
6
7
,

 
 
8
9
5
,

 
 
1
4
,

 
 
3
5
2
2
,

 
 
3
2
,

 
 
1
,

 
 
6
0
4
8
,

 
 
3
,

 
 
5
,

 
 
8
5
4
,

 
 
3
2
,

 
 
1
,

 
 
3
3
7
5
]
,

 
[
3
4
,

 
 
3
1
,

 
 
3
3
7
,

 
 
4
7
3
,

 
 
6
,

 
 
6
1
,

 
 
2
4
5
,

 
 
5
6
6
2
,

 
 
1
8
,

 
 
1
1
,

 
 
2
5
,

 
 
1
,

 
 
7
6
2
,

 
 
2
,

 
 
7
8
5
,

 
 
3
,

 
 
1
9
4
,

 
 
2
0
,

 
 
4
0
,

 
 
1
2
6
2
,

 
 
1
6
,

 
 
7
,

 
 
4
0
6
,

 
 
1
,

 
 
2
2
1
7
,

 
 
1
0
7
2
9
,

 
 
1
9
,

 
 
2
2
7
9
,

 
 
8
5
,

 
 
3
8
4
2
,

 
 
3
1
4
,

 
 
9
7
,

 
 
2
4
8
2
,

 
 
1
9
,

 
 
5
,

 
 
4
0
,

 
 
4
9
6
8
,

 
 
5
5
5
,

 
 
4
,

 
 
4
7
0
3
,

 
 
3
6
9
9
,

 
 
6
,

 
 
4
9
9
,

 
 
2
,

 
 
1
9
0
7
0
,

 
 
2
2
9
8
,

 
 
1
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

 
 
6
9
9
]
,

 
[
1
4
,
 
8
,
 
2
9
6
,
 
2
2
9
6
,
 
1
3
,
 
1
3
9
1
]
,

 
[
3
8
,

 
 
1
0
7
2
,

 
 
4
5
,

 
 
8
,

 
 
6
,

 
 
2
4
2
2
,

 
 
2
,

 
 
3
5
3
,

 
 
1
4
8
3
8
,

 
 
1
9
0
7
1
,

 
 
7
,

 
 
4
3
9
,

 
 
3
,

 
 
2
,

 
 
1
9
0
7
2
,

 
 
9
7
5
,

 
 
2
,

 
 
1
5
8
9
,

 
 
3
5
,

 
 
7
5
,

 
 
3
7
0
0
,

 
 
2
5
8
,

 
 
5
5
,

 
 
1
8
8
,

 
 
2
,

 
 
1
,

 
 
4
4
6
1
,

 
 
3
,

 
 
5
4
5
,

 
 
9
5
,

 
 
1
4
8
0
,

 
 
1
6
,

 
 
5
5
1
,

 
 
1
6
,

 
 
1
,

 
 
4
0
3
6
,

 
 
6
5
4
,

 
 
3
5
,

 
 
1
,

 
 
1
0
7
0
6
,

 
 
1
9
0
7
3
,

 
 
4
9
6
9
,

 
 
3
4
5
,

 
 
3
5
,

 
 
7
5
,

 
 
1
6
,

 
 
1
9
0
7
4
,

 
 
9
6
7
,

 
 
1
6
,

 
 
1
,

 
 
1
4
8
3
9
,

 
 
5
3
0
1
,

 
 
3
2
3
5
,

 
 
1
2
3
4
4
,

 
 
2
0
2
,

 
 
1
,

 
 
1
6
5
,

 
 
1
9
0
7
5
,

 
 
4
3
9
,

 
 
7
2
,

 
 
1
4
8
4
0
]
,

 
[
5
,

 
 
9
0
1
,

 
 
4
,

 
 
1
5
,

 
 
8
5
2
4
,

 
 
1
9
,

 
 
8
,

 
 
4
1
8
7
,

 
 
1
3
6
,

 
 
7
0
,

 
 
7
7
0
6
,

 
 
3
5
,

 
 
5
6
6
3
,

 
 
3
,

 
 
6
5
,

 
 
8
8
8
,

 
 
9
,

 
 
1
5
,

 
 
7
0
4
3
,

 
 
1
2
,

 
 
1
3
6
7
,

 
 
1
0
,

 
 
6
0
4
9
,

 
 
2
8
0
,

 
 
1
2
3
1
,

 
 
1
9
0
7
6
,

 
 
5
,

 
 
1
1
1
9
,

 
 
1
1
0
,

 
 
7
,

 
 
4
4
6
2
,

 
 
1
7
9
9
,

 
 
1
3
,

 
 
1
,

 
 
7
0
4
4
,

 
 
3
,

 
 
1
4
8
4
1
,

 
 
1
9
6
9
,

 
 
2
4
,

 
 
6
,

 
 
4
5
6
,

 
 
4
,

 
 
1
5
,

 
 
1
9
0
7
7
,

 
 
1
3
6
,

 
 
4
7
0
4
,

 
 
6
1
3
,

 
 
7
7
0
7
,

 
 
7
,

 
 
9
1
,

 
 
4
9
,

 
 
3
1
,

 
 
9
2
,

 
 
2
2
,

 
 
4
4
6
3
,

 
 
7
0
,

 
 
2
,

 
 
1
,

 
 
1
3
5
8
,

 
 
1
9
,

 
 
9
4
6
9
,

 
 
1
0
,

 
 
1
7
0
8
,

 
 
1
9
4
1
]
,

 
[
1
7
,
 
1
0
7
4
,
 
5
,
 
3
0
1
2
,
 
2
5
4
1
,
 
7
0
4
5
,
 
3
,
 
5
8
2
,
 
3
,
 
3
1
8
,
 
6
3
,
 
5
7
,
 
3
9
9
8
,
 
3
1
4
6
]
,

 
[
5
8
,

 
 
1
5
3
,

 
 
1
6
9
,

 
 
1
0
,

 
 
8
6
,

 
 
1
4
6
4
,

 
 
4
9
1
4
,

 
 
4
9
,

 
 
2
0
,

 
 
2
8
4
,

 
 
3
1
,

 
 
9
4
7
0
,

 
 
1
,

 
 
1
9
0
7
8
,

 
 
7
9
1
,

 
 
2
,

 
 
1
5
,

 
 
8
8
5
,

 
 
5
9
,

 
 
3
1
,

 
 
1
7
4
3
,

 
 
2
,

 
 
8
9
,

 
 
8
5
2
5
,

 
 
1
,

 
 
1
3
4
5
,

 
 
1
,

 
 
3
5
2
3
,

 
 
1
,

 
 
2
4
8
3
,

 
 
1
5
5
4
,

 
 
3
5
2
4
,

 
 
1
,

 
 
7
7
0
8
,

 
 
3
,

 
 
8
6
,

 
 
4
9
7
0
,

 
 
1
2
3
4
5
,

 
 
2
1
,

 
 
4
9
7
1
,

 
 
3
9
,

 
 
1
3
0
,

 
 
7
0
4
6
,

 
 
7
7
,

 
 
1
5
,

 
 
1
9
0
7
9
,

 
 
2
9
,

 
 
1
8
,

 
 
1
,

 
 
7
0
4
6
,

 
 
2
,

 
 
4
5
6
,

 
 
3
,

 
 
1
0
7
3
0
,

 
 
5
4
4
,

 
 
1
3
0
,

 
 
4
7
0
5
,

 
 
1
8
,

 
 
7
7
0
9
,

 
 
7
0
4
7
,

 
 
1
3
0
,

 
 
6
5
0
1
,

 
 
2
4
6
5
,

 
 
1
8
,

 
 
6
,

 
 
2
6
2
7
,

 
 
3
,

 
 
6
0
5
0
,

 
 
5
6
6
4
]
,

 
[
5
,

 
 
3
1
,

 
 
1
9
0
8
0
,

 
 
1
0
9
,

 
 
1
3
,

 
 
5
0
1
,

 
 
3
1
5
,

 
 
1
,

 
 
1
8
0
0
,

 
 
6
0
5
1
,

 
 
2
,

 
 
7
0
5
,

 
 
3
,

 
 
4
2
2
8
,

 
 
1
8
,

 
 
1
8
5
,

 
 
7
3
8
]
,

 
[
6
0
5
2
,

 
 
5
,

 
 
9
4
7
1
,

 
 
2
2
,

 
 
2
,

 
 
3
8
1
,

 
 
4
0
0
,

 
 
6
9
,

 
 
1
0
,

 
 
1
0
2
4
,

 
 
3
,

 
 
4
5
,

 
 
4
1
5
,

 
 
3
8
4
,

 
 
9
4
7
2
,

 
 
2
2
,

 
 
2
1
,

 
 
1
,

 
 
4
8
6
,

 
 
4
3
3
,

 
 
6
,

 
 
4
0
3
7
,

 
 
8
5
2
6
,

 
 
1
9
4
,

 
 
2
0
,

 
 
4
6
9
,

 
 
3
0
3
9
]
,

 
[
5
,

 
 
7
0
1
,

 
 
2
0
,

 
 
1
8
7
,

 
 
1
,

 
 
1
0
4
6
,

 
 
1
9
,

 
 
8
,

 
 
4
,

 
 
2
7
9
2
,

 
 
2
2
,

 
 
2
,

 
 
1
0
,

 
 
6
6
9
,

 
 
3
,

 
 
7
6
,

 
 
4
5
,

 
 
8
,

 
 
2
2
6
,

 
 
2
1
,

 
 
1
0
,

 
 
1
3
5
,

 
 
1
9
,

 
 
1
1
7
2
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
1
5
]
,

 
[
7
6
7
,

 
 
1
1
,

 
 
5
9
0
,

 
 
2
4
7
0
,

 
 
4
,

 
 
4
2
2
,

 
 
9
,

 
 
6
,

 
 
5
7
1
,

 
 
4
9
7
2
,

 
 
6
4
,

 
 
7
,

 
 
1
,

 
 
1
4
8
4
2
,

 
 
2
,

 
 
1
5
6
8
,

 
 
2
7
2
,

 
 
4
4
6
4
,

 
 
1
7
,

 
 
3
0
8
,

 
 
7
,

 
 
6
,

 
 
3
3
7
6
,

 
 
3
,

 
 
1
9
0
8
1
,

 
 
2
5
4
,

 
 
2
,

 
 
9
,

 
 
8
1
1
,

 
 
3
5
,

 
 
9
,

 
 
1
,

 
 
1
7
7
,

 
 
3
0
4
,

 
 
2
0
6
,

 
 
3
,

 
 
4
2
2
9
,

 
 
4
9
7
3
,

 
 
1
9
7
0
,

 
 
2
,

 
 
6
,

 
 
3
5
1
5
,

 
 
1
4
6
,

 
 
1
9
,

 
 
1
6
9
4
,

 
 
3
,

 
 
1
0
7
3
1
,

 
 
2
1
,

 
 
3
0
]
,

 
[
1
0
,

 
 
9
1
,

 
 
8
0
,

 
 
3
1
,

 
 
4
3
,

 
 
2
2
1
,

 
 
7
,

 
 
2
1
3
0
,

 
 
3
,

 
 
2
3
6
8
,

 
 
1
8
,

 
 
5
,

 
 
3
7
0
1
,

 
 
1
2
5
0
,

 
 
4
,

 
 
1
0
1
,

 
 
1
9
0
8
2
,

 
 
9
,

 
 
1
3
4
6
,

 
 
5
3
9
,

 
 
7
,

 
 
1
0
,

 
 
7
6
4
]
,

 
[
5
,

 
 
4
6
0
,

 
 
1
0
6
,

 
 
5
0
,

 
 
1
8
0
1
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

 
 
8
,

 
 
2
8
2
3
,

 
 
2
3
,

 
 
3
2
,

 
 
4
2
3
0
,

 
 
2
1
,

 
 
8
3
,

 
 
3
1
9
,

 
 
1
,

 
 
8
6
,

 
 
8
6
7
,

 
 
7
1
,

 
 
7
,

 
 
1
,

 
 
1
5
9
,

 
 
3
6
,

 
 
3
0
4
,

 
 
9
2
,

 
 
7
0
,

 
 
6
3
5
,

 
 
2
1
,

 
 
8
5
2
7
,

 
 
1
7
,

 
 
1
5
,

 
 
1
0
1
0
]
,

 
[
1
4
7
,

 
 
3
1
,

 
 
1
4
5
,

 
 
1
,

 
 
4
1
8
,

 
 
2
,

 
 
1
,

 
 
7
9
4
,

 
 
2
7
,

 
 
3
4
4
,

 
 
1
2
3
4
6
,

 
 
1
9
0
8
3
,

 
 
1
5
7
,

 
 
4
2
,

 
 
3
1
,

 
 
1
2
1
,

 
 
1
1
,

 
 
8
1
8
,

 
 
3
,

 
 
3
1
,

 
 
1
4
3
,

 
 
1
,

 
 
4
4
6
5
,

 
 
2
,

 
 
1
,

 
 
7
9
4
,

 
 
7
,

 
 
1
,

 
 
1
2
3
4
7
,

 
 
1
3
4
7
,

 
 
1
2
7
9
,

 
 
2
,

 
 
1
9
0
8
4
]
,

 
[
5
4
,

 
 
9
7
9
,

 
 
9
8
,

 
 
4
,

 
 
3
2
6
2
,

 
 
3
9
,

 
 
3
,

 
 
1
,

 
 
7
7
1
0
,

 
 
2
,

 
 
5
5
9
,

 
 
9
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
4
4
1
2
,

 
 
1
5
,

 
 
3
9
9
,

 
 
3
5
1
3
,

 
 
1
0
,

 
 
3
2
6
3
]
,

 
[
3
6
,
 
3
7
3
,
 
2
,
 
7
0
,
 
4
2
3
1
,
 
5
6
,
 
4
,
 
2
8
,
 
1
7
0
]
,

 
[
1
,
 
4
4
6
6
,
 
2
,
 
1
,
 
5
3
0
2
,
 
1
2
,
 
9
7
8
,
 
7
,
 
6
4
8
,
 
2
3
,
 
2
9
6
,
 
6
,
 
2
1
1
8
]
,

 
[
8
1
9
,
 
1
,
 
2
2
5
,
 
4
9
,
 
2
0
,
 
2
8
,
 
7
5
,
 
1
2
3
4
8
,
 
6
8
0
,
 
1
,
 
4
0
2
,
 
1
0
3
]
,

 
[
1
,

 
 
4
6
4
,

 
 
8
,

 
 
2
2
2
,

 
 
1
8
,

 
 
4
5
,

 
 
8
,

 
 
3
6
,

 
 
1
9
5
8
,

 
 
3
,

 
 
4
5
,

 
 
8
,

 
 
3
7
,

 
 
8
4
6
7
,

 
 
9
4
7
3
,

 
 
4
2
3
2
,

 
 
2
7
,

 
 
1
,

 
 
4
7
0
6
,

 
 
2
,

 
 
1
,

 
 
7
7
1
1
,

 
 
3
,

 
 
6
,

 
 
4
7
0
7
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
3
4
9
,

 
 
1
6
9
,

 
 
1
,

 
 
1
9
0
8
5
,

 
 
2
0
,

 
 
1
9
6
,

 
 
3
0
4
0
]
,

 
[
8
2
,
 
1
6
4
1
,
 
1
3
9
,
 
2
6
,
 
7
7
6
,
 
1
7
9
7
,
 
3
,
 
2
3
7
,
 
7
5
,
 
5
0
,
 
2
2
3
8
,
 
5
1
5
,
 
3
5
2
5
,
 
3
0
]
,

 
[
7
2
1
,

 
 
1
0
7
3
2
,

 
 
1
1
8
6
,

 
 
3
3
7
7
,

 
 
9
,

 
 
2
8
1
,

 
 
1
8
,

 
 
8
,

 
 
1
0
8
0
,

 
 
9
6
9
,

 
 
4
,

 
 
7
0
4
8
,

 
 
1
5
,

 
 
1
3
8
,

 
 
2
7
,

 
 
1
5
,

 
 
1
6
9
5
]
,

 
[
5
,

 
 
2
3
3
,

 
 
4
0
,

 
 
1
3
7
,

 
 
1
6
,

 
 
4
,

 
 
1
2
5
,

 
 
9
,

 
 
5
,

 
 
1
4
5
,

 
 
9
7
2
,

 
 
2
,

 
 
3
0
,

 
 
1
5
2
,

 
 
1
0
0
,

 
 
5
,

 
 
1
6
6
9
,

 
 
2
6
,

 
 
5
3
0
3
,

 
 
3
,

 
 
1
0
,

 
 
1
1
1
,

 
 
1
9
7
1
,

 
 
2
,

 
 
2
4
2
3
,

 
 
1
6
,

 
 
1
2
2
,

 
 
9
4
7
4
,

 
 
1
7
,

 
 
1
0
,

 
 
1
1
9
7
,

 
 
1
0
7
3
3
,

 
 
1
2
8
8
]
,

 
[
5
,

 
 
1
2
,

 
 
1
9
8
,

 
 
9
4
7
5
,

 
 
3
7
,

 
 
3
3
7
8
,

 
 
7
7
1
2
,

 
 
3
5
2
6
,

 
 
2
,

 
 
1
9
,

 
 
1
,

 
 
1
4
8
4
3
,

 
 
1
9
0
8
6
,

 
 
4
9
2
,

 
 
2
0
,

 
 
1
,

 
 
2
6
4
,

 
 
1
4
7
8
,

 
 
4
9
7
4
,

 
 
3
,

 
 
8
,

 
 
1
9
1
3
,

 
 
2
0
6
,

 
 
7
,

 
 
1
,

 
 
7
0
4
9
,

 
 
1
7
4
,

 
 
1
3
,

 
 
1
0
,

 
 
2
7
0
,

 
 
4
4
,

 
 
1
,

 
 
1
9
0
8
7
,

 
 
3
,

 
 
2
1
,

 
 
1
0
,

 
 
5
6
5
4
,

 
 
6
,

 
 
2
1
8
,

 
 
4
8
6
,

 
 
1
9
,

 
 
5
,

 
 
1
2
,

 
 
1
5
6
9
,

 
 
6
6
,

 
 
4
,

 
 
1
,

 
 
4
4
0
,

 
 
3
,

 
 
4
4
,

 
 
1
9
,

 
 
2
9
,

 
 
5
4
,

 
 
1
4
8
4
4
,

 
 
1
7
,

 
 
1
0
7
3
4
,

 
 
1
3
,

 
 
5
4
,

 
 
8
5
2
8
,

 
 
3
0
4
1
,

 
 
2
,

 
 
1
5
0
1
,

 
 
2
4
1
,

 
 
3
,

 
 
1
2
3
5
0
]
,

 
[
3
8
,
 
7
0
5
0
,
 
3
,
 
2
4
6
,
 
7
1
,
 
9
6
,
 
1
0
7
3
5
]
,

 
[
2
0
,

 
 
2
4
,

 
 
1
8
6
,

 
 
9
5
,

 
 
7
3
,

 
 
3
0
4
2
,

 
 
3
,

 
 
2
7
3
3
,

 
 
2
0
1
7
,

 
 
5
1
,

 
 
3
4
0
,

 
 
1
8
,

 
 
1
,

 
 
3
1
9
,

 
 
8
,

 
 
1
7
,

 
 
6
3
,

 
 
2
0
6
]
,

 
[
1
4
1
4
,
 
1
2
3
0
,
 
3
7
,
 
2
0
3
,
 
2
,
 
6
0
5
3
,
 
1
0
0
,
 
4
8
,
 
1
3
,
 
4
9
5
,
 
1
4
8
4
5
,
 
3
0
,
 
9
3
3
,
 
4
1
8
]
,

 
[
4
2
,

 
 
2
9
,

 
 
8
9
6
,

 
 
7
6
,

 
 
1
6
1
,

 
 
6
3
,

 
 
2
4
0
,

 
 
4
6
9
6
,

 
 
2
2
3
9
,

 
 
2
,

 
 
7
2
,

 
 
3
,

 
 
4
3
9
,

 
 
1
4
2
,

 
 
1
9
,

 
 
2
1
,

 
 
7
9
9
,

 
 
1
8
0
2
,

 
 
3
6
,

 
 
9
7
4
,

 
 
3
,

 
 
1
9
9
5
,

 
 
4
6
2
]
,

 
[
4
1
,
 
2
2
3
5
,
 
1
5
4
,
 
1
4
,
 
1
2
,
 
7
7
,
 
1
4
,
 
8
,
 
7
4
1
,
 
4
,
 
6
6
6
,
 
1
5
,
 
7
9
,
 
5
6
6
5
,
 
2
9
2
,
 
2
1
7
,
 
8
3
9
]
,

 
[
1
,
 
4
9
7
5
,
 
5
6
3
,
 
3
0
,
 
7
,
 
1
,
 
7
4
7
,
 
1
,
 
3
6
7
,
 
6
9
5
,
 
6
5
6
,
 
2
5
,
 
1
0
,
 
1
5
3
7
,
 
1
2
4
]
,

 
[
1
8
,

 
 
5
2
,

 
 
1
5
,

 
 
1
4
8
4
6
,

 
 
6
6
7
,

 
 
1
1
6
4
,

 
 
2
2
6
,

 
 
4
2
8
,

 
 
3
9
,

 
 
3
,

 
 
1
4
,

 
 
2
1
6
,

 
 
1
6
8
,

 
 
5
1
4
,

 
 
1
,

 
 
1
5
3
5
,

 
 
4
1
7
6
]
,

 
[
2
3
,

 
 
3
,

 
 
2
3
,

 
 
6
7
,

 
 
5
6
,

 
 
1
9
4
9
,

 
 
4
,

 
 
2
8
0
6
,

 
 
1
9
0
8
8
,

 
 
2
,

 
 
5
4
,

 
 
9
2
5
,

 
 
3
,

 
 
2
6
,

 
 
9
2
5
,

 
 
2
5
,

 
 
1
0
3
2
,

 
 
9
7
8
]
,

 
[
6
5
,

 
 
4
0
3
8
,

 
 
1
4
8
4
7
,

 
 
4
7
3
,

 
 
4
7
5
,

 
 
6
,

 
 
1
4
8
4
8
,

 
 
1
7
3
,

 
 
3
,

 
 
4
7
0
8
,

 
 
3
3
7
9
,

 
 
3
,

 
 
1
5
,

 
 
1
5
7
0
,

 
 
5
7
,

 
 
1
,

 
 
3
8
5
,

 
 
4
4
6
7
,

 
 
1
9
0
8
9
,

 
 
1
,

 
 
1
0
7
3
6
,

 
 
3
,

 
 
1
,

 
 
1
4
8
4
9
,

 
 
3
2
0
,

 
 
6
6
,

 
 
6
,

 
 
2
9
5
,

 
 
3
,

 
 
5
3
0
4
,

 
 
5
6
6
6
]
,

 
[
1
4
,
 
7
7
,
 
1
0
4
,
 
3
,
 
9
,
 
1
2
3
5
1
,
 
3
,
 
1
3
,
 
1
0
0
2
,
 
1
0
4
6
]
,

 
[
6
,
 
8
5
2
9
,
 
2
,
 
2
1
3
,
 
6
4
7
3
,
 
3
2
,
 
2
2
1
0
,
 
4
,
 
1
4
8
9
,
 
7
4
]
,

 
[
5
,
 
1
2
5
,
 
9
,
 
1
4
,
 
6
2
,
 
9
0
,
 
2
8
,
 
1
2
3
5
2
]
,

 
[
2
0
1
4
,

 
 
8
,

 
 
3
2
,

 
 
2
6
,

 
 
2
0
1
4
,

 
 
3
2
,

 
 
1
8
,

 
 
1
,

 
 
1
7
8
2
,

 
 
2
,

 
 
5
5
,

 
 
1
7
2
,

 
 
3
,

 
 
1
,

 
 
7
6
9
9
,

 
 
2
,

 
 
7
6
3
,

 
 
1
3
,

 
 
5
0
6
,

 
 
3
5
,

 
 
5
5
9
]
,

 
[
7
,

 
 
1
,

 
 
8
6
,

 
 
4
7
0
9
,

 
 
2
,

 
 
1
2
3
5
3
,

 
 
7
,

 
 
1
,

 
 
8
6
,

 
 
2
1
7
3
,

 
 
2
,

 
 
1
,

 
 
1
2
2
0
,

 
 
2
,

 
 
1
0
9
6
,

 
 
1
7
2
,

 
 
4
5
,

 
 
2
5
,

 
 
6
5
1
,

 
 
1
,

 
 
6
3
1
,

 
 
2
,

 
 
6
,

 
 
2
2
9
9
,

 
 
7
6
,

 
 
2
6
,

 
 
6
3
1
,

 
 
2
5
,

 
 
6
5
1
,

 
 
4
,

 
 
9
7
9
,

 
 
6
4
,

 
 
7
,

 
 
3
6
,

 
 
8
9
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
,

 
 
1
3
9
2
,

 
 
5
6
5
,

 
 
2
,

 
 
6
,

 
 
3
9
4
]
,

 
[
5
,
 
2
1
4
,
 
3
9
,
 
6
6
,
 
2
1
,
 
1
5
1
,
 
3
,
 
7
1
1
,
 
3
9
,
 
4
,
 
6
8
,
 
1
8
5
,
 
6
,
 
3
1
4
7
,
 
2
3
0
0
,
 
2
4
,
 
1
,
 
6
4
7
]
,

 
[
3
,

 
 
1
,

 
 
3
8
8
,

 
 
4
,

 
 
2
8
,

 
 
7
0
5
1
,

 
 
5
3
0
5
,

 
 
3
5
,

 
 
9
3
,

 
 
1
3
8
8
,

 
 
4
,

 
 
4
7
,

 
 
1
5
3
8
,

 
 
2
1
7
4
,

 
 
2
3
,

 
 
6
,

 
 
2
3
6
9
,

 
 
2
,

 
 
1
0
7
3
7
,

 
 
5
2
8
,

 
 
6
0
5
4
,

 
 
4
,

 
 
3
6
,

 
 
3
7
1
,

 
 
3
,

 
 
4
9
4
,

 
 
4
,

 
 
3
6
,

 
 
6
0
5
5
]
,

 
[
5
3
,
 
7
7
,
 
1
4
,
 
5
4
,
 
5
9
3
,
 
7
0
5
2
,
 
5
,
 
1
4
3
]
,

 
[
1
,

 
 
4
0
3
9
,

 
 
2
4
0
,

 
 
1
8
0
3
,

 
 
6
8
,

 
 
1
,

 
 
7
8
8
,

 
 
1
8
,

 
 
6
5
,

 
 
8
0
,

 
 
1
1
,

 
 
2
0
,

 
 
2
8
,

 
 
1
,

 
 
7
8
8
,

 
 
2
,

 
 
1
,

 
 
1
7
0
7
,

 
 
5
0
8
,

 
 
2
,

 
 
9
4
7
6
]
,

 
[
6
5
,

 
 
3
8
,

 
 
1
0
3
,

 
 
4
1
,

 
 
1
,

 
 
2
9
1
,

 
 
8
,

 
 
2
2
2
,

 
 
1
,

 
 
3
1
4
8
,

 
 
1
1
7
,

 
 
4
,

 
 
6
,

 
 
5
6
2
,

 
 
5
6
6
7
,

 
 
3
,

 
 
2
1
6
,

 
 
1
1
9
,

 
 
4
4
,

 
 
1
,

 
 
6
0
5
6
,

 
 
1
1
2
2
,

 
 
2
,

 
 
4
4
6
8
]
,

 
[
1
,

 
 
1
4
8
5
0
,

 
 
2
,

 
 
1
,

 
 
5
6
6
8
,

 
 
1
3
2
8
,

 
 
5
8
,

 
 
8
8
,

 
 
4
4
4
8
,

 
 
4
,

 
 
3
1
4
9
,

 
 
3
1
,

 
 
1
2
3
5
4
,

 
 
2
1
,

 
 
1
2
7
4
,

 
 
5
6
,

 
 
5
2
,

 
 
9
6
,

 
 
1
,

 
 
1
0
7
3
8
,

 
 
7
,

 
 
6
0
5
7
]
,

 
[
3
4
,
 
1
2
3
5
5
,
 
1
,
 
8
8
0
,
 
8
8
,
 
1
,
 
1
8
5
5
,
 
1
0
7
3
9
,
 
3
,
 
2
9
,
 
2
0
6
,
 
7
,
 
1
,
 
3
2
6
4
]
,

 
[
1
2
3
5
6
,

 
 
4
1
,

 
 
5
,

 
 
3
1
,

 
 
9
0
1
,

 
 
1
3
,

 
 
6
0
5
8
,

 
 
3
4
2
,

 
 
1
7
,

 
 
1
,

 
 
2
8
2
,

 
 
2
,

 
 
1
,

 
 
6
8
9
,

 
 
1
5
6
5
,

 
 
1
3
,

 
 
1
0
,

 
 
1
2
2
1
,

 
 
4
6
8
1
,

 
 
3
,

 
 
6
5
,

 
 
1
2
6
1
,

 
 
2
6
3
2
,

 
 
1
0
,

 
 
6
0
0
,

 
 
8
,

 
 
4
2
9
,

 
 
3
,

 
 
5
,

 
 
8
,

 
 
6
9
6
,

 
 
3
,

 
 
6
1
7
,

 
 
4
1
,

 
 
5
,

 
 
3
1
,

 
 
7
6
8
8
,

 
 
3
2
,

 
 
2
6
,

 
 
5
,

 
 
3
1
,

 
 
6
5
6
,

 
 
1
1
0
,

 
 
6
0
,

 
 
2
6
,

 
 
2
9
,

 
 
2
0
,

 
 
7
0
5
]
,

 
[
1
3
9
3
,
 
1
9
0
9
0
,
 
1
0
7
4
0
,
 
2
,
 
1
,
 
1
1
2
3
]
,

 
[
5
,
 
1
4
3
,
 
1
1
3
,
 
1
4
2
,
 
7
,
 
1
5
6
6
]
,

 
[
6
5
,

 
 
4
5
,

 
 
8
,

 
 
2
0
0
9
,

 
 
7
0
5
3
,

 
 
1
4
8
5
1
,

 
 
1
9
3
,

 
 
3
2
,

 
 
6
8
,

 
 
6
,

 
 
7
7
6
,

 
 
5
8
,

 
 
6
3
9
,

 
 
1
9
0
9
1
,

 
 
7
,

 
 
3
7
,

 
 
1
0
7
4
1
,

 
 
3
,

 
 
1
1
7
,

 
 
7
4
,

 
 
7
3
8
,

 
 
3
,

 
 
1
1
6
,

 
 
1
9
4
,

 
 
7
6
7
,

 
 
3
5
7
,

 
 
4
,

 
 
6
,

 
 
6
0
1
]
,

 
[
4
8
,

 
 
1
1
3
5
,

 
 
3
5
2
7
,

 
 
3
,

 
 
6
5
,

 
 
3
3
1
,

 
 
5
,

 
 
1
2
1
,

 
 
1
3
,

 
 
2
4
3
,

 
 
1
0
,

 
 
5
0
9
,

 
 
5
0
8
,

 
 
9
,

 
 
3
3
,

 
 
9
3
,

 
 
3
2
6
,

 
 
7
8
,

 
 
1
4
1
4
,

 
 
2
3
0
,

 
 
7
8
,

 
 
2
8
2
4
,

 
 
2
0
1
6
,

 
 
1
2
,

 
 
4
0
,

 
 
1
4
4
6
,

 
 
1
0
7
4
2
,

 
 
3
,

 
 
2
3
0
,

 
 
3
3
,

 
 
4
9
7
,

 
 
8
,

 
 
6
,

 
 
6
9
5
,

 
 
1
6
4
4
,

 
 
2
,

 
 
6
,

 
 
1
4
1
2
,

 
 
1
9
,

 
 
3
5
4
,

 
 
1
8
,

 
 
1
,

 
 
1
2
7
7
,

 
 
1
5
0
,

 
 
4
6
,

 
 
3
1
,

 
 
8
5
3
0
]
,

 
[
5
,

 
 
1
4
0
,

 
 
9
4
,

 
 
1
6
0
,

 
 
1
2
3
5
7
,

 
 
3
3
,

 
 
1
4
4
,

 
 
2
2
,

 
 
8
8
1
,

 
 
4
,

 
 
6
0
5
9
,

 
 
7
,

 
 
1
0
,

 
 
4
7
1
0
,

 
 
3
,

 
 
1
9
0
9
2
,

 
 
2
0
5
7
,

 
 
1
,

 
 
1
6
2
2
,

 
 
2
,

 
 
3
4
1
,

 
 
2
5
,

 
 
1
2
0
6
,

 
 
4
,

 
 
1
0
,

 
 
4
4
2
]
,

 
[
2
7
2
,

 
 
1
3
,

 
 
5
5
9
8
,

 
 
5
5
2
,

 
 
4
8
,

 
 
1
2
,

 
 
9
4
7
7
,

 
 
5
1
,

 
 
4
0
4
0
,

 
 
3
,

 
 
3
1
5
0
,

 
 
3
8
5
4
,

 
 
2
7
,

 
 
7
0
5
4
,

 
 
5
7
4
,

 
 
1
6
2
6
]
,

 
[
1
9
1
4
,

 
 
5
,

 
 
7
7
,

 
 
2
1
,

 
 
1
5
1
,

 
 
1
6
,

 
 
1
,

 
 
6
2
9
,

 
 
2
4
5
4
,

 
 
1
,

 
 
5
2
8
,

 
 
5
,

 
 
5
3
1
,

 
 
4
,

 
 
3
1
,

 
 
1
2
3
5
8
,

 
 
7
8
,

 
 
5
3
0
6
]
,

 
[
1
6
,
 
1
,
 
1
5
1
,
 
3
8
3
8
,
 
8
4
2
,
 
5
,
 
2
1
7
5
,
 
5
7
,
 
1
8
0
4
,
 
5
6
6
9
,
 
3
,
 
3
8
5
5
,
 
1
7
,
 
3
2
6
5
]
,

 
[
2
3
9
,
 
1
1
,
 
7
3
,
 
2
0
,
 
9
3
1
,
 
4
6
9
,
 
2
7
7
,
 
4
,
 
4
5
2
,
 
1
,
 
1
4
4
3
,
 
3
0
4
3
,
 
9
,
 
4
9
,
 
3
1
,
 
4
3
,
 
1
9
0
9
3
]
,

 
[
1
6
0
,
 
7
,
 
1
8
1
,
 
9
5
6
,
 
4
6
,
 
3
1
,
 
1
1
1
6
,
 
1
,
 
8
4
9
,
 
4
3
0
]
,

 
[
5
,

 
 
6
0
6
0
,

 
 
2
1
,

 
 
1
0
7
4
3
,

 
 
3
,

 
 
1
5
7
,

 
 
1
1
4
,

 
 
6
5
0
2
,

 
 
2
3
,

 
 
6
,

 
 
2
3
7
0
,

 
 
8
5
3
1
,

 
 
4
,

 
 
1
,

 
 
2
0
3
,

 
 
1
7
,

 
 
1
1
3
,

 
 
3
0
8
,

 
 
5
,

 
 
4
9
,

 
 
2
0
,

 
 
4
3
6
,

 
 
1
8
,

 
 
4
1
0
,

 
 
9
4
7
8
,

 
 
1
0
,

 
 
1
1
7
0
,

 
 
2
,

 
 
1
4
8
5
2
,

 
 
5
,

 
 
2
3
3
,

 
 
2
3
,

 
 
4
2
4
,

 
 
1
0
9
7
,

 
 
2
,

 
 
2
0
3
,

 
 
4
,

 
 
9
4
7
9
]
,

 
[
4
1
,

 
 
4
,

 
 
7
7
1
3
,

 
 
1
3
,

 
 
3
9
,

 
 
5
,

 
 
7
7
,

 
 
5
,

 
 
8
,

 
 
1
9
0
9
4
,

 
 
2
,

 
 
1
,

 
 
1
4
8
5
3
,

 
 
2
,

 
 
1
9
0
9
5
,

 
 
4
9
7
6
,

 
 
2
5
2
,

 
 
3
8
1
7
,

 
 
7
7
,

 
 
9
,

 
 
5
3
0
,

 
 
6
0
8
,

 
 
2
0
,

 
 
9
4
,

 
 
7
8
,

 
 
1
2
7
3
,

 
 
1
0
2
7
,

 
 
3
3
8
0
,

 
 
1
7
,

 
 
5
3
,

 
 
3
2
,

 
 
1
,

 
 
3
2
8
,

 
 
2
5
,

 
 
4
2
3
3
,

 
 
2
,

 
 
2
5
,

 
 
3
6
,

 
 
1
0
2
,

 
 
8
4
1
,

 
 
1
7
,

 
 
6
,

 
 
1
9
0
9
6
,

 
 
2
6
5
,

 
 
1
2
3
5
9
,

 
 
4
,

 
 
1
8
7
]
,

 
[
2
9
0
5
,

 
 
3
6
9
7
,

 
 
3
0
,

 
 
1
3
,

 
 
1
,

 
 
8
6
,

 
 
1
5
1
5
,

 
 
5
5
2
,

 
 
1
8
,

 
 
1
,

 
 
3
6
7
,

 
 
6
2
1
,

 
 
3
9
1
,

 
 
3
,

 
 
1
,

 
 
3
6
8
0
,

 
 
8
,

 
 
1
5
4
,

 
 
2
0
6
,

 
 
1
0
7
4
4
,

 
 
1
3
,

 
 
1
,

 
 
8
1
1
,

 
 
2
,

 
 
1
,

 
 
2
9
2
,

 
 
3
,

 
 
7
3
1
,

 
 
1
8
9
1
,

 
 
2
,

 
 
1
,

 
 
5
6
7
0
,

 
 
2
,

 
 
1
,

 
 
1
5
9
]
,

 
[
5
,

 
 
2
1
6
,

 
 
3
1
4
,

 
 
4
7
,

 
 
6
5
0
3
,

 
 
1
3
,

 
 
6
,

 
 
4
7
1
1
,

 
 
3
,

 
 
1
4
2
7
,

 
 
2
5
1
,

 
 
1
9
,

 
 
5
,

 
 
7
0
1
,

 
 
2
0
,

 
 
2
0
0
0
,

 
 
1
1
0
,

 
 
4
,

 
 
3
8
8
,

 
 
1
8
,

 
 
1
9
,

 
 
8
,

 
 
1
4
8
5
4
,

 
 
1
3
,

 
 
1
5
5
5
,

 
 
1
2
3
6
0
,

 
 
2
,

 
 
4
0
7
,

 
 
9
,

 
 
9
2
,

 
 
1
0
,

 
 
1
3
5
,

 
 
9
4
8
0
,

 
 
7
,

 
 
1
0
,

 
 
1
0
0
0
]
,

 
[
1
,
 
8
3
,
 
7
0
5
5
,
 
1
9
4
,
 
9
8
0
,
 
5
6
,
 
9
4
8
1
]
,

 
[
1
6
8
,

 
 
4
0
4
1
,

 
 
6
0
6
1
,

 
 
3
0
0
5
,

 
 
1
1
,

 
 
6
0
6
1
,

 
 
6
7
3
,

 
 
7
6
,

 
 
2
7
5
,

 
 
1
5
3
4
,

 
 
1
2
,

 
 
3
6
,

 
 
7
2
,

 
 
4
,

 
 
8
5
3
2
,

 
 
6
6
,

 
 
1
6
0
4
,

 
 
3
,

 
 
5
6
6
1
,

 
 
2
0
6
5
,

 
 
8
8
6
]
,

 
[
1
8
,

 
 
5
,

 
 
1
3
3
,

 
 
1
0
7
4
5
,

 
 
6
,

 
 
2
1
0
3
,

 
 
2
,

 
 
2
0
6
6
,

 
 
3
,

 
 
4
5
5
,

 
 
2
0
,

 
 
4
,

 
 
4
5
2
,

 
 
7
5
,

 
 
6
,

 
 
3
5
3
,

 
 
3
3
4
8
,

 
 
4
2
3
4
]
,

 
[
5
,
 
4
0
4
2
,
 
1
,
 
6
5
7
,
 
1
3
6
,
 
7
0
,
 
5
8
0
,
 
2
0
1
8
,
 
2
,
 
1
0
5
,
 
5
,
 
8
,
 
3
5
,
 
5
3
,
 
5
,
 
8
,
 
1
2
8
9
]
,

 
[
7
,

 
 
1
,

 
 
2
7
9
,

 
 
1
2
7
0
,

 
 
1
2
,

 
 
1
,

 
 
6
9
4
,

 
 
4
3
,

 
 
4
2
9
,

 
 
1
,

 
 
3
0
6
,

 
 
2
,

 
 
4
7
,

 
 
9
4
8
2
,

 
 
1
9
7
,

 
 
2
3
1
,

 
 
6
9
,

 
 
4
9
,

 
 
3
1
,

 
 
4
9
2
,

 
 
2
2
6
,

 
 
5
0
,

 
 
5
9
,

 
 
6
,

 
 
3
7
0
2
]
,

 
[
1
2
3
6
1
,
 
6
4
7
6
,
 
1
4
8
5
5
,
 
6
4
7
6
,
 
1
9
0
9
7
,
 
7
7
,
 
1
5
,
 
1
7
4
0
,
 
4
6
4
3
]
,

 
[
5
,

 
 
8
,

 
 
2
7
3
4
,

 
 
1
3
,

 
 
1
3
6
3
,

 
 
3
,

 
 
1
7
,

 
 
5
4
,

 
 
7
2
,

 
 
5
,

 
 
1
2
,

 
 
1
9
0
9
8
,

 
 
1
3
,

 
 
1
,

 
 
5
4
2
,

 
 
3
6
0
,

 
 
9
,

 
 
3
2
6
6
,

 
 
1
1
9
,

 
 
1
0
,

 
 
5
3
0
7
,

 
 
1
8
,

 
 
5
2
,

 
 
3
6
,

 
 
3
3
3
,

 
 
9
0
5
,

 
 
5
,

 
 
7
1
1
,

 
 
1
1
0
,

 
 
2
7
,

 
 
1
0
,

 
 
4
7
2
]
,

 
[
1
2
2
2
,

 
 
2
3
6
9
,

 
 
6
0
6
2
,

 
 
1
3
1
,

 
 
6
,

 
 
6
5
3
,

 
 
5
,

 
 
1
1
7
9
,

 
 
5
6
7
1
,

 
 
3
7
0
3
,

 
 
5
6
7
2
,

 
 
2
6
3
3
,

 
 
3
0
4
4
,

 
 
3
2
6
4
,

 
 
4
9
7
7
,

 
 
1
3
9
3
,

 
 
5
3
0
8
,

 
 
2
6
0
2
,

 
 
1
8
5
6
,

 
 
5
8
9
,

 
 
3
1
5
1
,

 
 
1
8
0
4
,

 
 
9
4
8
3
,

 
 
1
6
0
1
,

 
 
1
2
3
6
2
,

 
 
3
5
2
8
,

 
 
1
4
8
5
6
]
,

 
[
1
8
,

 
 
7
,

 
 
2
6
,

 
 
4
6
2
,

 
 
5
,

 
 
1
9
4
4
,

 
 
9
,

 
 
5
,

 
 
9
3
,

 
 
2
8
,

 
 
2
1
,

 
 
1
2
8
,

 
 
4
9
6
6
,

 
 
2
,

 
 
3
2
,

 
 
1
4
2
,

 
 
3
,

 
 
1
3
1
,

 
 
2
1
,

 
 
1
2
8
,

 
 
2
8
,

 
 
4
1
1
,

 
 
7
,

 
 
1
2
7
,

 
 
4
9
6
6
,

 
 
2
,

 
 
3
2
]
,

 
[
1
,

 
 
1
0
0
8
,

 
 
2
,

 
 
5
5
,

 
 
3
0
1
,

 
 
2
,

 
 
1
,

 
 
2
9
1
,

 
 
3
1
,

 
 
7
1
0
,

 
 
3
6
,

 
 
5
7
0
,

 
 
2
1
,

 
 
3
2
,

 
 
4
0
,

 
 
4
5
,

 
 
1
1
8
,

 
 
2
8
,

 
 
1
6
0
,

 
 
2
,

 
 
1
,

 
 
6
5
0
4
,

 
 
7
7
2
]
,

 
[
5
,

 
 
2
1
4
,

 
 
6
,

 
 
1
2
3
6
3
,

 
 
7
6
4
,

 
 
4
4
6
9
,

 
 
1
7
,

 
 
1
,

 
 
1
2
4
0
,

 
 
2
,

 
 
7
4
1
,

 
 
4
,

 
 
1
,

 
 
7
4
4
,

 
 
2
,

 
 
1
,

 
 
5
6
7
3
,

 
 
6
9
,

 
 
7
7
2
,

 
 
1
9
,

 
 
4
4
7
0
,

 
 
6
,

 
 
3
7
4
,

 
 
2
,

 
 
1
,

 
 
2
2
7
]
,

 
[
4
1
,

 
 
1
2
8
,

 
 
9
5
3
,

 
 
8
,

 
 
2
7
9
3
,

 
 
5
7
,

 
 
1
,

 
 
5
5
8
9
,

 
 
9
4
8
4
,

 
 
4
7
,

 
 
1
3
3
6
,

 
 
2
2
3
,

 
 
5
0
,

 
 
6
0
6
,

 
 
5
0
,

 
 
1
9
0
9
9
,

 
 
3
,

 
 
5
0
,

 
 
1
3
9
4
,

 
 
4
,

 
 
8
5
3
3
,

 
 
5
9
,

 
 
7
,

 
 
2
2
0
9
]
,

 
[
5
1
9
,

 
 
8
,

 
 
1
4
,

 
 
1
7
6
1
,

 
 
4
,

 
 
2
8
,

 
 
7
4
,

 
 
2
,

 
 
1
4
0
9
,

 
 
2
0
6
,

 
 
4
1
,

 
 
1
,

 
 
6
5
4
,

 
 
2
9
,

 
 
2
1
7
6
,

 
 
3
,

 
 
6
0
,

 
 
9
0
3
,

 
 
4
,

 
 
2
6
,

 
 
6
4
5
,

 
 
1
4
,

 
 
4
9
,

 
 
2
7
2
,

 
 
1
0
0
7
,

 
 
7
7
1
4
,

 
 
2
1
,

 
 
1
,

 
 
4
3
8
,

 
 
1
6
,

 
 
6
0
,

 
 
7
7
1
5
,

 
 
2
3
,

 
 
5
4
,

 
 
1
0
6
1
,

 
 
1
4
6
,

 
 
2
9
2
5
]
,

 
[
2
6
,
 
1
1
2
,
 
8
,
 
2
2
1
,
 
7
,
 
1
,
 
1
7
7
,
 
3
8
5
6
,
 
1
6
,
 
9
,
 
1
9
,
 
6
0
6
3
,
 
1
1
]
,

 
[
1
6
,

 
 
1
,

 
 
1
0
7
2
,

 
 
1
2
2
3
,

 
 
1
1
,

 
 
1
6
2
,

 
 
5
9
7
6
,

 
 
1
3
9
4
,

 
 
4
,

 
 
1
2
6
,

 
 
3
,

 
 
3
4
,

 
 
1
4
3
,

 
 
1
,

 
 
1
4
8
5
7
,

 
 
2
,

 
 
6
,

 
 
8
5
3
4
,

 
 
3
2
5
4
,

 
 
8
7
,

 
 
1
2
6
0
,

 
 
5
6
2
]
,

 
[
7
,

 
 
1
,

 
 
2
5
6
,

 
 
2
,

 
 
1
0
,

 
 
1
9
2
,

 
 
5
,

 
 
8
,

 
 
2
1
,

 
 
1
2
8
,

 
 
5
7
5
,

 
 
1
3
,

 
 
3
7
,

 
 
1
0
7
4
6
,

 
 
3
7
,

 
 
9
4
8
5
,

 
 
3
,

 
 
5
,

 
 
1
9
0
,

 
 
9
6
,

 
 
2
6
,

 
 
4
,

 
 
2
3
0
1
,

 
 
2
4
,

 
 
6
,

 
 
1
5
1
0
,

 
 
2
,

 
 
1
0
2
0
,

 
 
3
,

 
 
3
7
0
4
,

 
 
1
9
9
7
,

 
 
4
,

 
 
1
7
2
8
,

 
 
3
7
,

 
 
3
6
4
5
,

 
 
1
9
1
0
0
,

 
 
3
7
,

 
 
2
1
7
7
,

 
 
1
1
2
4
,

 
 
1
3
9
5
]
,

 
[
7
,

 
 
2
6
,

 
 
2
5
6
,

 
 
1
1
3
,

 
 
2
6
3
4
,

 
 
3
0
8
,

 
 
2
2
1
,

 
 
3
2
2
,

 
 
2
,

 
 
1
0
,

 
 
1
7
1
8
,

 
 
3
9
1
,

 
 
3
,

 
 
5
,

 
 
1
1
0
,

 
 
8
,

 
 
6
8
,

 
 
4
,

 
 
2
5
2
6
,

 
 
1
7
5
,

 
 
1
,

 
 
1
4
8
5
8
,

 
 
2
,

 
 
3
7
0
5
,

 
 
4
1
,

 
 
5
,

 
 
1
0
7
,

 
 
7
8
,

 
 
1
1
7
3
,

 
 
5
3
0
9
,

 
 
2
1
,

 
 
5
6
2
5
,

 
 
3
,

 
 
2
2
7
2
,

 
 
4
7
5
,

 
 
4
,

 
 
2
2
,

 
 
6
1
8
,

 
 
2
,

 
 
6
0
6
4
,

 
 
3
,

 
 
9
1
]
,

 
[
1
0
,

 
 
7
0
5
6
,

 
 
4
9
,

 
 
2
8
,

 
 
4
,

 
 
1
8
2
6
,

 
 
7
7
1
6
,

 
 
2
0
1
,

 
 
1
,

 
 
4
4
0
,

 
 
1
3
3
4
,

 
 
4
5
,

 
 
8
0
,

 
 
2
8
,

 
 
2
4
8
,

 
 
3
2
,

 
 
1
0
3
]
,

 
[
8
5
3
5
,

 
 
6
4
3
1
,

 
 
3
,

 
 
1
9
1
0
1
,

 
 
8
5
3
6
,

 
 
2
7
3
5
,

 
 
4
7
1
2
,

 
 
2
7
,

 
 
1
0
1
,

 
 
1
7
3
,

 
 
1
0
0
,

 
 
2
7
,

 
 
1
0
,

 
 
1
4
8
5
9
,

 
 
3
1
9
,

 
 
9
8
3
,

 
 
1
,

 
 
2
9
2
6
,

 
 
3
3
7
3
,

 
 
2
,

 
 
1
6
1
9
,

 
 
3
1
6
]
,

 
[
3
,

 
 
1
,

 
 
1
0
8
8
,

 
 
2
5
,

 
 
2
,

 
 
1
0
9
6
,

 
 
6
9
4
,

 
 
3
2
0
,

 
 
4
4
,

 
 
8
4
5
,

 
 
3
2
6
7
,

 
 
2
,

 
 
6
5
0
5
,

 
 
3
,

 
 
6
0
6
5
,

 
 
3
,

 
 
1
7
8
,

 
 
8
9
,

 
 
3
1
5
2
,

 
 
1
3
0
3
,

 
 
2
,

 
 
7
9
4
,

 
 
3
,

 
 
5
3
1
0
,

 
 
9
,

 
 
1
4
,

 
 
5
8
,

 
 
1
3
1
1
,

 
 
6
6
,

 
 
4
,

 
 
9
7
,

 
 
7
0
5
7
,

 
 
9
1
0
,

 
 
4
,

 
 
1
6
7
5
,

 
 
4
4
,

 
 
1
,

 
 
4
6
6
,

 
 
1
4
8
6
0
]
,

 
[
3
6
,

 
 
3
8
,

 
 
2
0
5
2
,

 
 
2
7
,

 
 
1
1
0
3
,

 
 
1
,

 
 
1
1
7
3
,

 
 
3
,

 
 
1
7
6
,

 
 
2
4
0
8
,

 
 
2
9
,

 
 
6
5
0
6
,

 
 
4
,

 
 
2
8
,

 
 
1
7
0
,

 
 
2
1
,

 
 
1
0
3
,

 
 
1
6
4
5
,

 
 
1
,

 
 
2
0
1
9
,

 
 
3
,

 
 
3
1
0
6
,

 
 
2
7
,

 
 
1
,

 
 
7
7
1
7
,

 
 
3
,

 
 
9
4
8
6
]
,

 
[
5
,
 
8
4
,
 
2
0
,
 
1
0
9
8
,
 
3
8
,
 
2
5
4
2
,
 
9
,
 
7
2
5
,
 
1
9
5
,
 
2
6
,
 
6
6
6
,
 
4
,
 
5
1
6
]
,

 
[
3
4
,
 
3
1
,
 
7
0
3
,
 
5
3
,
 
3
4
,
 
7
3
,
 
4
1
,
 
4
8
,
 
8
,
 
2
0
]
,

 
[
2
0
,

 
 
6
,

 
 
9
4
8
7
,

 
 
2
7
,

 
 
5
1
,

 
 
5
5
8
,

 
 
2
0
,

 
 
6
,

 
 
2
2
6
9
,

 
 
2
7
,

 
 
5
1
,

 
 
1
9
1
0
2
,

 
 
2
0
,

 
 
3
7
,

 
 
1
9
1
0
3
,

 
 
7
,

 
 
5
1
,

 
 
3
8
5
7
,

 
 
1
8
,

 
 
5
3
,

 
 
9
,

 
 
3
3
9
,

 
 
2
,

 
 
3
0
,

 
 
8
6
0
,

 
 
1
2
,

 
 
4
9
7
8
,

 
 
4
,

 
 
1
4
8
6
1
,

 
 
7
,

 
 
4
4
,

 
 
1
0
,

 
 
4
4
8
]
,

 
[
1
,

 
 
1
4
9
,

 
 
8
,

 
 
2
4
8
4
,

 
 
1
3
,

 
 
4
4
7
1
,

 
 
1
9
1
0
4
,

 
 
3
,

 
 
4
9
7
9
,

 
 
1
3
,

 
 
1
0
1
,

 
 
1
1
7
2
,

 
 
6
0
6
6
,

 
 
4
2
3
5
,

 
 
4
6
,

 
 
2
4
8
5
]
,

 
[
2
2
4
,
 
3
2
,
 
8
,
 
1
,
 
3
6
6
,
 
2
,
 
1
9
1
5
,
 
1
9
0
6
]
,

 
[
1
1
,

 
 
9
1
0
,

 
 
9
,

 
 
2
7
,

 
 
9
,

 
 
1
5
1
,

 
 
4
0
8
,

 
 
1
0
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

 
 
7
7
1
8
,

 
 
4
,

 
 
2
5
9
,

 
 
2
1
,

 
 
1
,

 
 
3
6
3
8
,

 
 
2
1
6
4
,

 
 
3
8
1
2
,

 
 
1
9
,

 
 
4
1
9
,

 
 
2
4
,

 
 
3
5
0
7
,

 
 
2
4
2
4
,

 
 
4
,

 
 
1
,

 
 
7
7
1
9
,

 
 
1
1
7
4
]
,

 
[
3
4
,

 
 
1
2
3
,

 
 
2
8
,

 
 
5
6
7
4
,

 
 
4
,

 
 
4
9
8
0
,

 
 
3
7
,

 
 
1
9
1
0
5
,

 
 
1
8
,

 
 
1
1
,

 
 
2
5
,

 
 
7
,

 
 
6
3
7
,

 
 
9
,

 
 
3
4
,

 
 
5
6
,

 
 
2
2
8
,

 
 
1
2
0
,

 
 
4
,

 
 
1
4
0
8
,

 
 
6
,

 
 
1
9
1
0
6
,

 
 
1
9
3
,

 
 
3
7
,

 
 
1
9
1
0
7
,

 
 
1
9
3
,

 
 
6
,

 
 
1
9
1
0
8
,

 
 
1
1
7
5
,

 
 
1
9
3
,

 
 
6
,

 
 
1
9
1
0
9
,

 
 
1
9
3
,

 
 
8
9
,

 
 
1
6
,

 
 
9
,

 
 
2
,

 
 
1
4
8
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
1
1
0
,

 
 
1
9
1
1
1
,

 
 
2
]
,

 
[
5
3
1
1
,

 
 
1
9
3
,

 
 
4
0
4
3
,

 
 
1
4
,

 
 
2
5
,

 
 
2
5
,

 
 
5
7
9
,

 
 
4
9
8
1
,

 
 
2
,

 
 
4
8
0
,

 
 
3
,

 
 
4
8
0
,

 
 
7
,

 
 
5
5
,

 
 
3
5
2
9
,

 
 
1
0
1
0
,

 
 
2
5
,

 
 
2
0
,

 
 
6
4
,

 
 
1
,

 
 
2
1
9
,

 
 
2
,

 
 
1
2
3
6
4
,

 
 
1
8
,

 
 
2
3
6
,

 
 
4
7
,

 
 
6
1
,

 
 
1
3
5
]
,

 
[
1
4
,

 
 
6
2
,

 
 
2
7
8
,

 
 
2
2
,

 
 
8
5
3
7
,

 
 
2
6
9
,

 
 
2
7
8
,

 
 
4
0
4
4
,

 
 
2
4
,

 
 
1
2
3
6
5
,

 
 
3
,

 
 
7
6
,

 
 
5
4
,

 
 
3
8
5
8
,

 
 
6
2
,

 
 
3
1
,

 
 
1
1
,

 
 
9
,

 
 
1
5
,

 
 
1
6
7
4
,

 
 
2
5
,

 
 
6
,

 
 
3
3
8
1
,

 
 
1
7
,

 
 
7
8
,

 
 
1
1
1
,

 
 
1
6
4
,

 
 
1
8
0
,

 
 
8
5
,

 
 
2
6
8
,

 
 
2
2
4
0
]
,

 
[
5
,

 
 
2
2
2
1
,

 
 
1
8
3
8
,

 
 
2
4
,

 
 
2
8
9
5
,

 
 
5
2
4
,

 
 
3
,

 
 
1
2
0
7
,

 
 
1
3
,

 
 
1
0
7
4
7
,

 
 
1
6
0
5
,

 
 
1
,

 
 
2
0
9
7
,

 
 
1
4
9
5
,

 
 
2
,

 
 
1
,

 
 
1
8
1
,

 
 
7
0
2
]
,

 
[
2
6
,

 
 
9
8
3
,

 
 
2
,

 
 
1
9
7
2
,

 
 
3
9
4
,

 
 
8
7
,

 
 
1
3
,

 
 
6
5
0
7
,

 
 
3
3
6
,

 
 
3
4
,

 
 
4
3
3
,

 
 
4
0
3
,

 
 
2
4
2
5
,

 
 
2
,

 
 
1
,

 
 
3
8
7
,

 
 
3
,

 
 
2
7
9
]
,

 
[
4
2
3
6
,

 
 
2
,

 
 
4
7
,

 
 
1
1
1
,

 
 
7
7
2
0
,

 
 
4
4
,

 
 
1
5
,

 
 
1
2
3
6
6
,

 
 
3
5
,

 
 
2
3
7
,

 
 
9
4
8
8
,

 
 
6
6
0
,

 
 
1
1
,

 
 
1
2
,

 
 
2
9
4
,

 
 
2
1
5
2
,

 
 
2
3
,

 
 
1
,

 
 
7
6
6
,

 
 
3
,

 
 
1
1
,

 
 
8
,

 
 
1
,

 
 
1
9
1
1
2
,

 
 
2
,

 
 
2
6
,

 
 
7
6
6
,

 
 
1
9
,

 
 
1
2
,

 
 
4
3
,

 
 
1
7
3
9
,

 
 
2
3
,

 
 
1
,

 
 
9
4
2
,

 
 
1
7
,

 
 
9
,

 
 
2
,

 
 
1
,

 
 
3
8
5
9
,

 
 
8
7
5
,

 
 
3
0
4
5
,

 
 
1
2
7
,

 
 
1
3
1
,

 
 
7
7
8
,

 
 
5
3
1
2
]
,

 
[
1
1
6
,

 
 
6
0
,

 
 
3
3
,

 
 
8
4
,

 
 
3
1
,

 
 
1
1
,

 
 
4
0
,

 
 
5
,

 
 
6
2
,

 
 
2
3
4
,

 
 
6
,

 
 
2
1
8
,

 
 
1
7
8
7
,

 
 
1
9
8
,

 
 
4
,

 
 
2
7
9
2
,

 
 
7
8
,

 
 
9
4
8
9
]
,

 
[
5
,

 
 
7
3
,

 
 
1
8
,

 
 
1
,

 
 
6
0
6
7
,

 
 
2
4
1
,

 
 
2
1
2
7
,

 
 
4
,

 
 
4
7
,

 
 
7
0
5
8
,

 
 
2
,

 
 
5
3
1
3
,

 
 
1
7
,

 
 
1
1
3
,

 
 
2
3
1
,

 
 
1
7
,

 
 
1
1
3
,

 
 
1
1
2
5
,

 
 
3
,

 
 
4
9
6
4
,

 
 
5
2
0
,

 
 
2
5
0
,

 
 
1
0
,

 
 
4
4
7
2
,

 
 
2
0
1
0
,

 
 
9
2
4
,

 
 
1
,

 
 
1
2
3
6
7
,

 
 
8
7
,

 
 
1
0
,

 
 
1
3
8
,

 
 
3
,

 
 
5
,

 
 
3
2
4
,

 
 
3
9
9
8
,

 
 
8
8
,

 
 
1
8
5
7
,

 
 
3
,

 
 
1
3
,

 
 
1
,

 
 
1
3
5
,

 
 
2
,

 
 
6
,

 
 
1
2
2
4
,

 
 
1
7
8
8
,

 
 
1
,

 
 
2
3
1
,

 
 
3
,

 
 
1
,

 
 
3
0
8
,

 
 
3
,

 
 
1
,

 
 
9
3
3
,

 
 
1
0
3
8
,

 
 
1
9
,

 
 
9
8
,

 
 
4
,

 
 
1
4
8
6
3
,

 
 
3
,

 
 
1
4
8
6
3
,

 
 
1
6
,

 
 
3
0
,

 
 
4
5
3
,

 
 
9
1
,

 
 
3
5
3
0
,

 
 
8
1
,

 
 
1
0
0
3
,

 
 
7
,

 
 
1
,

 
 
9
9
8
,

 
 
2
,

 
 
1
,

 
 
1
1
2
]
,

 
[
1
2
4
,
 
1
1
,
 
2
5
,
 
2
1
,
 
8
3
,
 
1
3
9
4
,
 
4
,
 
7
7
0
,
 
1
,
 
2
2
9
5
,
 
2
,
 
1
,
 
7
7
2
1
]
,

 
[
4
,

 
 
2
8
0
6
,

 
 
7
4
,

 
 
1
5
,

 
 
2
8
2
5
,

 
 
1
4
,

 
 
9
4
9
0
,

 
 
3
,

 
 
9
2
4
,

 
 
1
,

 
 
1
2
3
6
8
,

 
 
2
,

 
 
5
3
0
,

 
 
1
0
7
4
8
,

 
 
1
2
3
6
9
,

 
 
3
,

 
 
2
5
2
,

 
 
8
5
3
8
,

 
 
1
2
2
,

 
 
1
9
1
4
,

 
 
1
1
6
,

 
 
2
5
7
,

 
 
1
7
,

 
 
2
2
3
7
,

 
 
8
5
3
9
,

 
 
3
,

 
 
5
1
9
,

 
 
1
7
,

 
 
1
,

 
 
4
1
2
,

 
 
4
2
,

 
 
3
1
,

 
 
3
3
6
1
,

 
 
7
,

 
 
1
,

 
 
7
7
4
,

 
 
2
,

 
 
1
9
1
1
3
]
,

 
[
1
7
,

 
 
1
3
6
,

 
 
4
0
4
5
,

 
 
7
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
2
1
8
,

 
 
3
0
8
,

 
 
2
0
2
,

 
 
8
5
9
,

 
 
3
2
,

 
 
1
,

 
 
4
9
1
3
,

 
 
2
,

 
 
1
,

 
 
1
4
8
,

 
 
3
,

 
 
1
,

 
 
6
0
6
8
,

 
 
3
,

 
 
1
,

 
 
6
0
6
9
,

 
 
1
1
7
,

 
 
4
,

 
 
6
,

 
 
2
0
9
7
,

 
 
5
6
7
5
,

 
 
3
,

 
 
8
2
,

 
 
1
,

 
 
7
0
5
9
,

 
 
4
5
,

 
 
8
,

 
 
1
6
0
,

 
 
1
5
4
,

 
 
1
8
0
5
,

 
 
7
,

 
 
1
,

 
 
2
6
5
,

 
 
4
8
9
,

 
 
1
2
2
,

 
 
3
0
0
,

 
 
5
6
7
6
,

 
 
3
,

 
 
1
8
8
,

 
 
2
,

 
 
6
,

 
 
3
3
8
2
,

 
 
1
7
5
3
,

 
 
4
4
3
]
,

 
[
5
,

 
 
3
1
,

 
 
1
0
4
,

 
 
4
,

 
 
1
4
2
8
,

 
 
7
4
5
,

 
 
1
,

 
 
3
0
6
,

 
 
4
,

 
 
2
2
,

 
 
3
6
9
,

 
 
6
,

 
 
5
2
5
7
,

 
 
3
8
,

 
 
9
,

 
 
2
1
,

 
 
3
7
,

 
 
1
5
9
9
,

 
 
1
1
8
0
,

 
 
4
,

 
 
9
,

 
 
2
,

 
 
1
4
7
6
1
,

 
 
5
,

 
 
1
2
4
1
,

 
 
4
8
4
,

 
 
6
1
,

 
 
7
9
3
,

 
 
4
1
6
,

 
 
1
8
3
,

 
 
1
2
3
7
0
,

 
 
1
8
3
,

 
 
4
9
5
,

 
 
2
,

 
 
1
7
0
7
,

 
 
4
8
4
,

 
 
5
,

 
 
2
3
2
,

 
 
7
3
,

 
 
2
5
2
,

 
 
4
2
3
7
,

 
 
1
8
3
,

 
 
2
5
2
,

 
 
4
7
1
3
,

 
 
1
8
3
,

 
 
5
3
0
,

 
 
1
0
7
4
8
]
,

 
[
1
1
,

 
 
8
,

 
 
2
9
6
,

 
 
2
4
6
,

 
 
6
9
6
,

 
 
4
1
,

 
 
1
,

 
 
1
4
8
6
4
,

 
 
8
3
,

 
 
1
1
7
,

 
 
7
,

 
 
3
7
4
,

 
 
2
,

 
 
1
,

 
 
1
8
9
8
,

 
 
1
9
,

 
 
8
,

 
 
4
0
0
,

 
 
2
9
2
7
,

 
 
2
3
,

 
 
2
8
8
,

 
 
1
,

 
 
3
3
8
3
,

 
 
3
,

 
 
2
3
,

 
 
2
5
2
,

 
 
8
5
3
8
]
,

 
[
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
 
4
1
5
,
 
3
,
 
4
6
,
 
1
3
4
8
,
 
1
8
,
 
6
,
 
5
7
8
,
 
7
3
0
]
,

 
[
5
3
,

 
 
8
,

 
 
1
1
,

 
 
5
,

 
 
1
1
3
5
,

 
 
4
,

 
 
2
4
2
,

 
 
5
3
,

 
 
8
,

 
 
1
1
,

 
 
9
,

 
 
4
0
,

 
 
6
4
8
8
,

 
 
2
2
,

 
 
7
,

 
 
1
,

 
 
2
1
0
1
,

 
 
2
,

 
 
1
,

 
 
1
4
1
,

 
 
2
,

 
 
3
2
6
8
]
,

 
[
1
,

 
 
1
6
5
,

 
 
1
4
1
,

 
 
1
3
,

 
 
4
7
,

 
 
1
3
2
3
,

 
 
8
,

 
 
3
5
3
1
,

 
 
2
,

 
 
1
,

 
 
7
9
,

 
 
2
5
4
3
,

 
 
4
4
7
3
,

 
 
1
0
7
4
9
,

 
 
1
6
7
2
,

 
 
3
,

 
 
1
3
,

 
 
1
9
1
1
4
,

 
 
4
4
7
4
]
,

 
[
6
,
 
3
7
1
,
 
2
9
9
,
 
4
4
,
 
3
2
,
 
1
4
2
]
,

 
[
3
,

 
 
6
5
,

 
 
8
1
,

 
 
1
0
7
5
0
,

 
 
5
,

 
 
4
9
,

 
 
1
0
4
1
,

 
 
7
2
0
,

 
 
4
,

 
 
3
3
5
6
,

 
 
1
,

 
 
4
0
7
,

 
 
2
4
1
,

 
 
2
4
,

 
 
3
9
,

 
 
3
,

 
 
1
2
8
,

 
 
1
0
0
,

 
 
3
5
3
2
,

 
 
5
,

 
 
2
3
0
2
,

 
 
1
0
,

 
 
9
9
,

 
 
3
1
4
,

 
 
3
9
,

 
 
3
,

 
 
1
0
7
,

 
 
1
5
,

 
 
1
0
4
5
,

 
 
2
7
,

 
 
2
2
,

 
 
3
,

 
 
4
4
6
,

 
 
1
3
,

 
 
4
1
8
,

 
 
3
2
,

 
 
1
5
,

 
 
3
7
0
6
,

 
 
9
8
,

 
 
5
3
1
4
,

 
 
4
,

 
 
7
0
6
0
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
0
2
,

 
 
9
,

 
 
1
0
,

 
 
7
7
2
2
,

 
 
1
9
2
,

 
 
6
0
7
0
,

 
 
1
4
8
6
5
,

 
 
1
2
,

 
 
3
6
9
,

 
 
7
0
3
,

 
 
1
5
,

 
 
8
5
4
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
2
,

 
 
7
0
3
,

 
 
1
1
,

 
 
1
6
,

 
 
1
9
0
,

 
 
1
6
,

 
 
1
1
,

 
 
8
,

 
 
9
2
]
,

 
[
4
9
8
2
,
 
8
,
 
3
2
6
9
,
 
2
3
,
 
1
9
7
,
 
1
9
1
1
5
,
 
1
0
7
5
1
,
 
1
9
1
1
6
,
 
3
,
 
1
2
3
7
1
]
,

 
[
1
8
,

 
 
6
0
,

 
 
1
,

 
 
9
1
5
,

 
 
2
7
,

 
 
1
9
,

 
 
1
,

 
 
4
4
7
5
,

 
 
2
,

 
 
3
0
,

 
 
4
6
2
,

 
 
8
,

 
 
3
1
5
3
,

 
 
1
6
2
,

 
 
5
9
9
,

 
 
1
4
9
,

 
 
8
8
,

 
 
9
4
9
1
,

 
 
1
,

 
 
2
5
9
3
,

 
 
2
3
6
9
,

 
 
2
,

 
 
4
7
1
4
,

 
 
3
,

 
 
1
6
4
6
,

 
 
7
6
5
,

 
 
1
4
8
6
6
,

 
 
2
3
,

 
 
7
7
2
3
,

 
 
1
5
,

 
 
1
1
3
0
,

 
 
2
,

 
 
1
5
2
,

 
 
1
4
8
6
7
,

 
 
2
4
,

 
 
3
0
,

 
 
4
0
4
,

 
 
8
4
,

 
 
2
3
0
3
,

 
 
3
,

 
 
6
5
,

 
 
2
8
,

 
 
3
1
5
4
,

 
 
1
7
,

 
 
4
7
,

 
 
1
1
7
6
]
,

 
[
1
1
,

 
 
8
,

 
 
1
,

 
 
1
2
3
7
2
,

 
 
6
5
0
6
,

 
 
6
,

 
 
8
6
,

 
 
1
1
5
3
,

 
 
3
1
7
,

 
 
3
7
,

 
 
3
1
7
,

 
 
3
6
9
,

 
 
2
0
2
,

 
 
1
,

 
 
2
8
6
,

 
 
2
,

 
 
6
,

 
 
1
4
8
6
8
,

 
 
4
,

 
 
8
5
4
1
]
,

 
[
5
,

 
 
7
3
,

 
 
2
0
,

 
 
8
1
,

 
 
1
,

 
 
1
6
6
,

 
 
1
4
,

 
 
2
1
6
,

 
 
2
1
,

 
 
6
0
7
1
,

 
 
4
6
6
,

 
 
8
8
0
,

 
 
3
,

 
 
6
5
,

 
 
4
5
,

 
 
1
1
7
,

 
 
6
,

 
 
1
4
8
6
9
,

 
 
9
4
9
2
,

 
 
7
,

 
 
1
,

 
 
1
2
1
5
,

 
 
2
1
3
2
,

 
 
4
1
,

 
 
5
,

 
 
8
7
2
,

 
 
9
,

 
 
6
,

 
 
2
1
2
,

 
 
2
6
1
7
,

 
 
1
2
,

 
 
4
3
,

 
 
6
,

 
 
4
6
6
,

 
 
2
2
5
,

 
 
4
1
,

 
 
1
4
,

 
 
2
0
1
1
,

 
 
1
1
]
,

 
[
5
,

 
 
7
7
,

 
 
1
1
,

 
 
2
1
,

 
 
8
3
,

 
 
3
,

 
 
5
,

 
 
1
2
5
,

 
 
1
1
,

 
 
1
0
6
,

 
 
3
,

 
 
5
,

 
 
9
0
,

 
 
1
9
1
1
7
,

 
 
3
7
,

 
 
3
1
5
5
,

 
 
3
6
1
,

 
 
4
1
,

 
 
1
4
,

 
 
8
2
2
,

 
 
9
,

 
 
1
2
3
7
3
,

 
 
1
0
7
5
2
]
,

 
[
5
1
,

 
 
2
7
3
6
,

 
 
2
1
,

 
 
2
7
0
6
,

 
 
8
,

 
 
1
3
3
7
,

 
 
4
,

 
 
1
8
7
,

 
 
1
,

 
 
4
5
7
,

 
 
1
9
1
1
8
,

 
 
3
,

 
 
9
3
,

 
 
1
5
,

 
 
4
6
2
,

 
 
2
8
,

 
 
3
0
4
6
,

 
 
4
,

 
 
2
3
0
4
,

 
 
1
5
,

 
 
5
6
7
7
]
,

 
[
5
,

 
 
3
9
7
,

 
 
1
2
3
7
4
,

 
 
6
4
,

 
 
6
,

 
 
1
5
6
,

 
 
2
,

 
 
6
7
,

 
 
8
4
2
5
,

 
 
2
1
,

 
 
3
8
,

 
 
7
2
,

 
 
8
0
8
,

 
 
1
,

 
 
8
4
4
,

 
 
2
9
2
8
,

 
 
2
3
,

 
 
1
,

 
 
5
6
7
8
]
,

 
[
8
8
4
,

 
 
4
2
,

 
 
2
4
2
0
,

 
 
4
,

 
 
5
6
7
9
,

 
 
2
4
,

 
 
9
1
,

 
 
4
7
,

 
 
8
4
3
8
,

 
 
6
4
3
3
,

 
 
2
,

 
 
6
0
6
6
,

 
 
3
,

 
 
4
,

 
 
1
5
0
2
,

 
 
7
,

 
 
4
6
5
3
,

 
 
8
5
4
2
,

 
 
1
,

 
 
4
9
8
3
,

 
 
1
4
6
,

 
 
9
,

 
 
2
5
,

 
 
8
9
5
,

 
 
2
8
2
6
,

 
 
5
4
0
,

 
 
1
7
,

 
 
3
1
6
,

 
 
2
0
6
]
,

 
[
4
0
4
6
,

 
 
2
3
4
9
,

 
 
2
,

 
 
1
4
2
,

 
 
7
,

 
 
1
,

 
 
3
3
8
4
,

 
 
3
,

 
 
1
,

 
 
2
5
3
,

 
 
6
2
5
,

 
 
8
5
4
3
,

 
 
6
6
,

 
 
3
,

 
 
1
4
,

 
 
9
6
,

 
 
1
5
0
,

 
 
5
6
8
0
,

 
 
4
,

 
 
1
9
1
1
9
,

 
 
1
2
3
7
5
,

 
 
7
7
,

 
 
4
,

 
 
1
9
1
2
0
,

 
 
4
,

 
 
1
,

 
 
5
6
8
1
,

 
 
9
4
9
3
,

 
 
2
,

 
 
1
,

 
 
6
5
0
8
,

 
 
3
,

 
 
4
,

 
 
3
1
,

 
 
3
7
,

 
 
1
5
6
3
,

 
 
7
3
7
,

 
 
1
,

 
 
7
2
,

 
 
3
,

 
 
4
3
9
,

 
 
3
4
,

 
 
1
5
8
4
]
,

 
[
4
4
4
,

 
 
8
,

 
 
1
3
2
,

 
 
1
1
4
,

 
 
3
1
0
,

 
 
6
6
,

 
 
2
3
,

 
 
3
0
,

 
 
1
1
1
,

 
 
1
4
9
8
,

 
 
8
9
1
,

 
 
4
,

 
 
2
8
,

 
 
2
3
0
5
,

 
 
6
5
8
,

 
 
4
9
8
4
,

 
 
1
7
,

 
 
4
8
,

 
 
3
9
7
9
,

 
 
9
,

 
 
7
7
2
4
,

 
 
8
4
,

 
 
2
8
,

 
 
1
,

 
 
1
0
8
9
,

 
 
2
,

 
 
2
6
,

 
 
3
3
1
,

 
 
1
9
1
2
1
]
,

 
[
1
,
 
6
0
7
2
,
 
1
9
,
 
6
0
7
3
,
 
9
1
,
 
2
4
,
 
1
3
4
,
 
5
6
,
 
2
1
,
 
4
2
0
,
 
2
1
6
1
,
 
3
,
 
7
3
6
]
,

 
[
3
2
,

 
 
3
8
6
0
,

 
 
6
,

 
 
1
8
8
,

 
 
7
,

 
 
1
,

 
 
5
3
1
5
,

 
 
6
5
0
9
,

 
 
3
,

 
 
6
5
0
6
,

 
 
9
,

 
 
1
,

 
 
5
3
1
6
,

 
 
1
2
,

 
 
4
3
,

 
 
3
5
7
,

 
 
2
3
,

 
 
2
5
3
,

 
 
3
0
4
7
,

 
 
8
5
7
,

 
 
1
9
,

 
 
1
2
,

 
 
1
6
4
,

 
 
4
,

 
 
6
3
,

 
 
2
4
,

 
 
5
1
,

 
 
4
9
2
5
,

 
 
1
8
5
8
,

 
 
1
4
9
,

 
 
7
,

 
 
1
,

 
 
1
2
1
0
,

 
 
7
5
2
]
,

 
[
3
6
,
 
5
7
1
,
 
4
6
,
 
3
1
,
 
4
9
8
5
,
 
1
,
 
4
2
3
8
,
 
1
3
,
 
7
0
,
 
7
0
6
1
]
,

 
[
4
2
,
 
2
9
,
 
9
,
 
2
6
6
,
 
1
,
 
7
9
,
 
7
7
2
5
,
 
4
7
6
,
 
9
,
 
2
3
3
,
 
7
4
,
 
2
,
 
5
1
1
,
 
6
9
]
,

 
[
5
1
,
 
4
0
4
,
 
8
,
 
2
0
,
 
8
4
3
7
,
 
2
3
,
 
1
,
 
7
8
3
,
 
2
,
 
7
8
5
]
,

 
[
1
,

 
 
1
5
8
,

 
 
7
0
6
2
,

 
 
1
0
7
6
,

 
 
7
0
6
,

 
 
8
5
,

 
 
3
6
4
6
,

 
 
3
,

 
 
7
9
,

 
 
6
8
9
,

 
 
2
1
1
6
,

 
 
2
1
,

 
 
1
,

 
 
1
0
7
5
3
,

 
 
2
,

 
 
1
5
2
,

 
 
3
,

 
 
2
5
1
,

 
 
1
2
0
6
,

 
 
4
,

 
 
1
5
,

 
 
1
4
6
9
,

 
 
1
1
,

 
 
1
9
1
2
2
,

 
 
1
5
5
2
,

 
 
4
7
,

 
 
8
5
4
4
,

 
 
2
7
3
7
,

 
 
3
,

 
 
1
,

 
 
7
6
4
,

 
 
8
,

 
 
1
0
7
5
4
,

 
 
1
7
,

 
 
8
5
]
,

 
[
1
,

 
 
3
5
3
3
,

 
 
1
2
,

 
 
8
8
9
,

 
 
7
,

 
 
2
6
,

 
 
7
2
7
,

 
 
1
3
,

 
 
6
0
5
,

 
 
4
,

 
 
3
0
,

 
 
4
8
5
,

 
 
2
3
7
,

 
 
4
8
,

 
 
1
8
8
4
,

 
 
4
,

 
 
2
3
2
,

 
 
1
,

 
 
4
0
2
,

 
 
3
0
4
8
,

 
 
7
,

 
 
1
1
5
9
,

 
 
5
0
,

 
 
1
2
3
7
6
]
,

 
[
1
,

 
 
1
8
3
8
,

 
 
2
,

 
 
1
,

 
 
2
9
1
0
,

 
 
7
7
2
6
,

 
 
1
1
,

 
 
2
5
,

 
 
9
4
9
4
,

 
 
5
3
1
7
,

 
 
1
9
1
2
3
,

 
 
9
4
9
5
,

 
 
5
0
,

 
 
7
7
2
7
,

 
 
2
,

 
 
6
,

 
 
3
6
7
2
,

 
 
8
5
4
5
,

 
 
5
9
,

 
 
2
,

 
 
6
,

 
 
2
1
6
4
,

 
 
1
0
0
,

 
 
1
,

 
 
2
1
8
,

 
 
1
2
3
4
,

 
 
1
3
,

 
 
4
7
,

 
 
2
1
7
3
,

 
 
9
8
7
,

 
 
3
6
8
9
,

 
 
2
5
,

 
 
2
,

 
 
1
,

 
 
2
4
8
6
,

 
 
1
9
1
2
4
,

 
 
7
0
6
3
,

 
 
2
4
,

 
 
2
1
2
,

 
 
1
9
7
3
,

 
 
8
1
,

 
 
6
,

 
 
4
7
1
5
,

 
 
9
4
9
6
,

 
 
4
2
3
9
,

 
 
1
4
8
7
0
,

 
 
2
,

 
 
6
,

 
 
1
8
1
,

 
 
1
2
3
4
]
,

 
[
1
5
,

 
 
1
2
1
3
,

 
 
9
6
,

 
 
6
2
6
,

 
 
1
1
3
4
,

 
 
1
7
,

 
 
2
2
4
1
,

 
 
7
,

 
 
1
5
,

 
 
4
7
1
6
,

 
 
1
4
9
9
,

 
 
1
3
0
,

 
 
2
3
6
2
,

 
 
3
2
,

 
 
3
8
6
1
,

 
 
2
3
,

 
 
7
7
2
8
,

 
 
3
,

 
 
5
6
8
2
,

 
 
2
9
,

 
 
1
1
3
,

 
 
2
,

 
 
6
3
,

 
 
8
1
,

 
 
1
5
0
,

 
 
1
5
2
4
,

 
 
2
3
,

 
 
8
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

 
 
1
5
3
,

 
 
6
,

 
 
8
5
4
4
,

 
 
7
6
,

 
 
1
4
8
7
1
,

 
 
5
0
5
,

 
 
1
0
3
,

 
 
3
,

 
 
3
8
,

 
 
1
9
7
0
,

 
 
5
6
6
,

 
 
7
,

 
 
4
7
,

 
 
4
6
1
,

 
 
3
,

 
 
4
7
,

 
 
3
1
6
]
,

 
[
1
4
,

 
 
2
7
2
,

 
 
1
5
4
,

 
 
8
5
,

 
 
3
,

 
 
1
3
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
,

 
 
8
7
6
,

 
 
3
5
,

 
 
2
6
3
5
,

 
 
7
,

 
 
1
5
,

 
 
1
0
4
,

 
 
7
7
2
9
,

 
 
1
5
,

 
 
6
2
7
,

 
 
1
5
,

 
 
6
4
,

 
 
1
0
6
0
]
,

 
[
2
3
0
6
,

 
 
6
3
1
,

 
 
8
5
4
6
,

 
 
1
9
7
4
,

 
 
2
2
,

 
 
3
,

 
 
4
1
,

 
 
6
,

 
 
7
1
,

 
 
1
0
8
,

 
 
1
,

 
 
8
6
3
,

 
 
2
1
7
8
,

 
 
1
2
,

 
 
5
,

 
 
2
9
7
,

 
 
1
1
,

 
 
3
7
,

 
 
1
3
4
9
,

 
 
4
,

 
 
1
4
4
,

 
 
3
9
,

 
 
3
6
,

 
 
2
6
1
,

 
 
5
3
,

 
 
6
1
1
,

 
 
1
5
,

 
 
3
4
0
,

 
 
3
5
2
2
]
,

 
[
3
0
3
,
 
1
4
5
5
,
 
3
8
,
 
3
3
,
 
1
4
2
9
,
 
2
2
,
 
2
6
,
 
6
5
1
0
,
 
9
,
 
5
,
 
9
3
,
 
6
5
9
,
 
3
3
,
 
7
3
9
]
,

 
[
5
,

 
 
6
5
,

 
 
2
1
4
,

 
 
6
5
1
1
,

 
 
2
,

 
 
1
0
7
5
5
,

 
 
2
3
,

 
 
1
0
3
,

 
 
4
,

 
 
6
,

 
 
1
6
2
9
,

 
 
9
1
7
,

 
 
7
2
8
,

 
 
2
,

 
 
2
4
8
7
,

 
 
3
9
3
,

 
 
9
9
1
,

 
 
1
1
7
5
,

 
 
9
4
9
7
,

 
 
4
,

 
 
3
8
1
1
,

 
 
6
8
,

 
 
1
0
7
5
,

 
 
1
0
7
5
6
,

 
 
1
8
6
,

 
 
3
,

 
 
3
8
,

 
 
2
,

 
 
6
,

 
 
2
4
2
6
,

 
 
1
0
3
7
,

 
 
6
0
7
,

 
 
1
4
8
7
2
,

 
 
1
4
8
7
3
,

 
 
1
2
3
7
7
,

 
 
1
9
7
,

 
 
1
3
9
6
,

 
 
7
,

 
 
2
3
7
1
,

 
 
1
5
3
9
,

 
 
2
9
9
4
,

 
 
3
,

 
 
5
9
4
,

 
 
2
7
0
,

 
 
7
,

 
 
1
9
1
,

 
 
6
,

 
 
1
7
1
9
,

 
 
2
,

 
 
6
,

 
 
1
0
2
7
,

 
 
9
4
1
2
,

 
 
1
5
2
7
,

 
 
3
5
,

 
 
3
8
6
2
,

 
 
2
0
9
6
,

 
 
1
9
,

 
 
5
,

 
 
1
4
0
,

 
 
2
0
,

 
 
2
5
5
,

 
 
3
,

 
 
6
,

 
 
3
1
4
7
,

 
 
1
9
1
2
5
,

 
 
2
,

 
 
6
,

 
 
6
1
,

 
 
5
9
9
,

 
 
9
4
9
8
]
,

 
[
1
1
9
,

 
 
2
6
,

 
 
1
8
4
,

 
 
1
0
9
9
,

 
 
1
,

 
 
3
1
1
,

 
 
2
6
9
,

 
 
3
3
6
9
,

 
 
6
1
,

 
 
1
3
7
,

 
 
1
7
,

 
 
1
,

 
 
1
3
3
0
,

 
 
1
8
0
6
,

 
 
2
3
,

 
 
1
,

 
 
4
4
3
,

 
 
1
0
6
,

 
 
1
9
1
2
6
,

 
 
4
,

 
 
1
,

 
 
1
5
4
,

 
 
2
5
0
,

 
 
2
8
8
,

 
 
5
6
,

 
 
2
6
3
6
,

 
 
6
6
,

 
 
2
3
,

 
 
1
,

 
 
1
0
4
0
]
,

 
[
5
4
8
,

 
 
7
9
4
,

 
 
3
,

 
 
5
3
,

 
 
9
4
,

 
 
5
,

 
 
7
8
9
,

 
 
2
5
,

 
 
9
,

 
 
1
,

 
 
9
5
7
,

 
 
2
4
1
,

 
 
1
,

 
 
2
2
6
9
,

 
 
1
,

 
 
3
1
5
6
,

 
 
2
,

 
 
1
0
,

 
 
5
9
6
,

 
 
9
4
9
9
,

 
 
1
9
,

 
 
5
,

 
 
7
7
0
,

 
 
1
9
1
3
,

 
 
1
3
,

 
 
6
,

 
 
1
3
9
7
,

 
 
4
0
,

 
 
8
1
2
,

 
 
7
,

 
 
1
,

 
 
9
0
9
]
,

 
[
2
4
,
 
9
7
,
 
6
5
1
2
,
 
3
,
 
1
2
3
7
8
,
 
1
6
0
4
,
 
3
4
,
 
1
2
3
,
 
1
9
1
2
7
,
 
1
1
4
,
 
7
6
,
 
1
3
4
3
,
 
1
0
4
]
,

 
[
6
5
,

 
 
1
1
5
,

 
 
4
8
,

 
 
4
2
4
0
,

 
 
5
6
8
3
,

 
 
3
0
,

 
 
8
1
5
,

 
 
6
6
9
,

 
 
9
,

 
 
6
,

 
 
5
7
1
,

 
 
1
3
,

 
 
6
,

 
 
4
7
1
7
,

 
 
1
3
5
,

 
 
3
,

 
 
2
5
4
4
,

 
 
9
3
,

 
 
2
8
,

 
 
1
7
0
9
,

 
 
2
3
,

 
 
3
7
0
7
,

 
 
1
5
2
,

 
 
3
,

 
 
1
9
0
3
,

 
 
6
1
8
,

 
 
4
,

 
 
2
3
4
,

 
 
6
6
,

 
 
1
,

 
 
2
4
7
6
,

 
 
2
,

 
 
4
9
8
,

 
 
3
,

 
 
1
6
0
0
,

 
 
2
0
2
,

 
 
1
,

 
 
4
4
7
6
,

 
 
2
,

 
 
7
1
,

 
 
1
2
3
7
9
,

 
 
1
6
0
3
,

 
 
3
,

 
 
5
5
9
,

 
 
1
,

 
 
1
0
0
,

 
 
3
0
,

 
 
2
6
1
6
,

 
 
3
0
4
9
,

 
 
1
7
3
,

 
 
1
8
5
9
,

 
 
5
8
1
,

 
 
3
,

 
 
3
0
,

 
 
1
1
6
0
,

 
 
3
,

 
 
4
8
1
,

 
 
1
9
1
6
,

 
 
1
3
,

 
 
6
0
7
4
,

 
 
4
4
0
]
,

 
[
4
8
,

 
 
1
2
,

 
 
4
2
9
,

 
 
4
,

 
 
2
9
2
9
,

 
 
3
0
,

 
 
1
7
3
0
,

 
 
4
6
7
5
,

 
 
2
4
,

 
 
1
,

 
 
8
0
5
,

 
 
4
8
,

 
 
1
2
,

 
 
1
2
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
,

 
 
2
3
7
2
,

 
 
3
,

 
 
5
4
0
,

 
 
8
1
7
,

 
 
9
,

 
 
4
8
,

 
 
8
0
,

 
 
4
5
,

 
 
5
6
8
4
,

 
 
3
0
,

 
 
4
1
8
,

 
 
5
,

 
 
9
6
,

 
 
3
0
,

 
 
4
0
4
7
,

 
 
5
7
6
,

 
 
3
7
,

 
 
7
9
,

 
 
3
0
2
4
,

 
 
5
3
1
8
,

 
 
4
7
,

 
 
1
5
7
1
,

 
 
2
5
4
5
,

 
 
1
3
,

 
 
3
0
,

 
 
8
5
4
7
,

 
 
4
8
1
,

 
 
1
6
,

 
 
3
0
,

 
 
4
1
8
,

 
 
2
9
9
,

 
 
1
9
1
2
8
,

 
 
3
,

 
 
3
0
,

 
 
5
3
1
9
,

 
 
3
,

 
 
5
9
3
,

 
 
6
4
3
4
,

 
 
4
6
,

 
 
2
0
,

 
 
2
8
,

 
 
8
5
4
8
,

 
 
1
3
,

 
 
3
1
5
7
,

 
 
5
0
1
,

 
 
5
,

 
 
5
5
6
,

 
 
2
6
,

 
 
4
9
7
,

 
 
3
8
,

 
 
2
,

 
 
1
0
,

 
 
1
3
5
,

 
 
1
3
1
,

 
 
2
9
0
,

 
 
7
,

 
 
6
2
8
,

 
 
5
,

 
 
7
0
7
,

 
 
3
0
,

 
 
3
1
4
,

 
 
2
2
,

 
 
3
,

 
 
1
6
,

 
 
4
8
,

 
 
1
4
5
,

 
 
1
0
,

 
 
1
0
7
5
7
,

 
 
2
7
,

 
 
3
0
,

 
 
5
3
0
7
,

 
 
1
6
,

 
 
4
8
,

 
 
1
4
5
,

 
 
1
0
,

 
 
4
9
8
,

 
 
2
6
3
7
,

 
 
3
0
,

 
 
4
8
,

 
 
3
1
0
4
,

 
 
4
,

 
 
1
,

 
 
4
4
1
,

 
 
2
,

 
 
5
3
,

 
 
3
7
9
,

 
 
4
,

 
 
3
0
,

 
 
3
3
,

 
 
5
6
,

 
 
6
1
,

 
 
2
6
6
,

 
 
2
0
,

 
 
4
,

 
 
4
0
4
8
,

 
 
2
2
,

 
 
4
8
,

 
 
7
7
,

 
 
5
,

 
 
1
9
4
2
,

 
 
3
,

 
 
6
,

 
 
9
3
3
,

 
 
7
0
6
4
,

 
 
2
,

 
 
2
2
7
7
,

 
 
6
2
8
,

 
 
4
1
8
,

 
 
1
0
,

 
 
1
3
5
]
,

 
[
3
3
8
,

 
 
2
1
6
,

 
 
2
1
,

 
 
3
9
,

 
 
8
1
,

 
 
3
8
,

 
 
6
5
1
3
,

 
 
3
0
,

 
 
4
2
4
1
,

 
 
3
9
9
,

 
 
1
3
5
7
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
1
3
,

 
 
1
7
4
1
,

 
 
4
,

 
 
1
2
6
,

 
 
3
9
,

 
 
6
4
,

 
 
8
,

 
 
4
0
4
]
,

 
[
1
0
0
,

 
 
1
4
,

 
 
2
9
8
,

 
 
4
0
,

 
 
1
1
7
7
,

 
 
8
,

 
 
1
,

 
 
4
4
7
7
,

 
 
9
,

 
 
3
8
,

 
 
8
0
,

 
 
3
1
,

 
 
1
4
3
,

 
 
6
,

 
 
1
9
1
2
9
,

 
 
1
8
8
7
,

 
 
4
4
,

 
 
1
,

 
 
3
4
9
]
,

 
[
2
,

 
 
1
0
,

 
 
1
9
0
2
,

 
 
4
1
3
,

 
 
7
5
,

 
 
1
1
9
,

 
 
4
,

 
 
2
3
1
,

 
 
3
,

 
 
3
0
8
,

 
 
5
,

 
 
5
3
2
,

 
 
6
,

 
 
8
6
,

 
 
2
5
2
2
,

 
 
1
4
2
8
,

 
 
1
7
,

 
 
1
8
6
,

 
 
1
8
6
0
,

 
 
2
,

 
 
1
,

 
 
5
3
0
2
,

 
 
2
,

 
 
1
,

 
 
4
9
8
6
,

 
 
1
5
7
2
,

 
 
7
,

 
 
1
,

 
 
1
7
6
2
,

 
 
2
2
8
,

 
 
2
0
5
,

 
 
4
0
,

 
 
1
1
4
,

 
 
5
0
,

 
 
2
,

 
 
1
0
,

 
 
4
2
4
2
,

 
 
4
6
2
]
,

 
[
4
2
,
 
2
9
,
 
1
1
6
8
,
 
3
,
 
1
3
0
2
,
 
5
6
8
5
,
 
1
1
9
1
,
 
5
7
7
,
 
7
,
 
2
1
3
,
 
1
6
,
 
1
1
6
,
 
1
6
,
 
7
,
 
2
1
1
2
]
,

 
[
5
3
,
 
1
4
,
 
7
7
,
 
8
,
 
5
3
2
0
,
 
1
8
,
 
1
6
3
,
 
2
9
,
 
1
3
2
9
,
 
1
,
 
9
5
0
0
,
 
8
,
 
9
7
4
]
,

 
[
1
8
,

 
 
4
1
,

 
 
5
,

 
 
1
0
7
,

 
 
3
3
,

 
 
2
9
4
,

 
 
1
,

 
 
3
1
7
,

 
 
2
,

 
 
8
5
4
9
,

 
 
1
5
2
,

 
 
4
1
,

 
 
5
,

 
 
1
0
6
9
,

 
 
9
,

 
 
3
3
,

 
 
8
0
,

 
 
2
8
,

 
 
4
9
7
,

 
 
1
1
9
7
,

 
 
5
9
,

 
 
1
6
,

 
 
6
,

 
 
2
4
2
7
,

 
 
3
0
5
0
,

 
 
3
,

 
 
9
4
7
,

 
 
2
,

 
 
1
6
7
7
,

 
 
3
,

 
 
2
5
4
6
,

 
 
3
5
,

 
 
9
,

 
 
3
3
,

 
 
8
0
,

 
 
1
5
2
,

 
 
2
1
0
,

 
 
1
3
,

 
 
6
,

 
 
5
0
,

 
 
2
2
6
5
,

 
 
5
5
2
,

 
 
5
9
,

 
 
9
,

 
 
1
9
,

 
 
3
3
,

 
 
7
0
6
,

 
 
4
,

 
 
2
2
,

 
 
6
5
,

 
 
1
,

 
 
1
2
2
4
,

 
 
1
4
3
0
,

 
 
1
6
1
,

 
 
2
2
,

 
 
5
,

 
 
4
0
4
9
,

 
 
7
8
,

 
 
1
9
1
7
,

 
 
3
,

 
 
2
4
,

 
 
9
,

 
 
1
9
9
,

 
 
5
,

 
 
3
1
,

 
 
2
5
7
,

 
 
3
6
,

 
 
8
0
0
]
,

 
[
1
9
1
3
0
,

 
 
1
3
0
,

 
 
8
5
5
0
,

 
 
8
,

 
 
3
7
0
8
,

 
 
2
3
,

 
 
1
,

 
 
1
4
8
7
4
,

 
 
2
,

 
 
4
3
2
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
0
,

 
 
2
9
0
,

 
 
1
5
,

 
 
6
6
5
,

 
 
7
5
,

 
 
2
1
,

 
 
2
6
,

 
 
1
1
0
4
,

 
 
3
3
9
,

 
 
1
8
,

 
 
8
,

 
 
1
0
6
,

 
 
1
9
1
3
1
,

 
 
1
9
1
3
2
,

 
 
1
,

 
 
4
6
8
4
,

 
 
4
,

 
 
1
8
0
7
,

 
 
5
5
,

 
 
1
5
3
6
,

 
 
3
,

 
 
9
5
0
1
,

 
 
5
5
,

 
 
6
0
7
5
]
,

 
[
1
7
,

 
 
6
8
,

 
 
1
8
5
,

 
 
3
7
,

 
 
3
0
5
,

 
 
1
,

 
 
8
3
4
,

 
 
9
8
6
,

 
 
4
4
,

 
 
6
0
2
,

 
 
4
4
7
8
,

 
 
1
8
,

 
 
2
1
,

 
 
1
5
1
,

 
 
3
4
,

 
 
2
4
2
8
,

 
 
3
6
9
,

 
 
1
5
4
0
,

 
 
4
,

 
 
3
4
7
,

 
 
1
1
,

 
 
1
,

 
 
8
9
3
,

 
 
6
0
1
,

 
 
8
5
5
1
]
,

 
[
7
,
 
2
0
5
4
,
 
1
,
 
5
9
1
,
 
1
2
,
 
2
2
3
,
 
7
,
 
1
,
 
2
9
2
,
 
2
,
 
4
0
6
,
 
3
,
 
1
9
5
,
 
2
8
0
9
,
 
1
1
,
 
9
2
,
 
4
7
,
 
4
9
1
3
]
,

 
[
1
,
 
2
8
0
3
,
 
1
2
3
8
0
,
 
4
,
 
3
1
,
 
9
5
0
2
,
 
1
5
,
 
3
4
0
,
 
2
4
,
 
1
,
 
8
6
9
,
 
2
,
 
3
8
,
 
2
5
2
,
 
1
4
8
7
5
,
 
1
9
1
3
3
]
,

 
[
1
4
,
 
1
6
2
,
 
3
7
,
 
9
4
3
0
,
 
7
,
 
1
,
 
1
2
0
2
,
 
8
4
4
2
]
,

 
[
1
8
,

 
 
6
0
,

 
 
1
,

 
 
4
2
4
3
,

 
 
3
1
,

 
 
6
3
4
,

 
 
1
3
1
,

 
 
1
3
7
,

 
 
1
1
,

 
 
2
5
,

 
 
1
,

 
 
4
9
6
,

 
 
1
9
,

 
 
1
4
8
7
6
,

 
 
3
4
,

 
 
1
4
4
4
,

 
 
7
,

 
 
6
3
7
]
,

 
[
1
,

 
 
3
5
,

 
 
1
9
1
3
4
,

 
 
1
,

 
 
4
2
6
,

 
 
1
1
0
9
,

 
 
1
0
5
,

 
 
2
5
7
,

 
 
1
1
,

 
 
1
2
3
8
1
,

 
 
1
3
1
,

 
 
1
,

 
 
6
8
4
,

 
 
1
4
8
7
7
,

 
 
5
6
7
1
,

 
 
1
]
,

 
[
1
2
,
 
1
,
 
2
2
5
,
 
4
3
,
 
7
,
 
7
0
,
 
8
9
9
,
 
8
5
5
2
]
,

 
[
1
1
,

 
 
1
2
,

 
 
3
3
7
,

 
 
1
0
3
0
,

 
 
4
7
,

 
 
1
4
1
0
,

 
 
1
1
4
8
,

 
 
6
,

 
 
2
2
2
,

 
 
3
1
5
5
,

 
 
7
,

 
 
1
0
,

 
 
1
6
3
0
,

 
 
3
,

 
 
1
0
,

 
 
8
9
6
,

 
 
3
2
4
,

 
 
3
3
3
7
,

 
 
3
,

 
 
2
3
0
7
]
,

 
[
3
6
,

 
 
5
4
4
,

 
 
1
2
3
,

 
 
1
0
5
9
,

 
 
1
,

 
 
1
0
7
5
8
,

 
 
1
9
,

 
 
8
0
,

 
 
3
1
,

 
 
4
3
,

 
 
3
3
6
1
,

 
 
2
3
,

 
 
6
,

 
 
7
8
6
,

 
 
3
5
3
4
,

 
 
7
4
9
,

 
 
1
4
9
,

 
 
1
2
9
0
,

 
 
1
,

 
 
5
7
0
,

 
 
2
,

 
 
1
,

 
 
1
0
3
]
,

 
[
3
8
1
,

 
 
2
1
7
,

 
 
2
2
,

 
 
1
9
5
,

 
 
6
,

 
 
1
3
8
0
,

 
 
7
,

 
 
1
,

 
 
1
2
3
8
2
,

 
 
2
3
0
8
,

 
 
2
,

 
 
1
9
,

 
 
1
0
,

 
 
3
2
7
0
,

 
 
1
2
3
,

 
 
3
4
8
5
,

 
 
5
4
,

 
 
6
1
7
,

 
 
2
4
9
,

 
 
4
1
,

 
 
5
,

 
 
1
2
5
,

 
 
9
,

 
 
1
1
,

 
 
7
0
6
,

 
 
2
0
6
7
,

 
 
4
,

 
 
1
,

 
 
8
4
8
5
,

 
 
6
5
1
4
,

 
 
3
5
3
5
,

 
 
7
6
,

 
 
2
7
3
8
,

 
 
1
4
8
7
8
,

 
 
2
5
6
,

 
 
2
,

 
 
1
2
3
8
3
,

 
 
5
,

 
 
6
2
0
,

 
 
3
8
6
3
,

 
 
2
,

 
 
7
5
,

 
 
5
0
,

 
 
5
9
,

 
 
1
,

 
 
3
2
5
,

 
 
4
1
2
,

 
 
7
,

 
 
1
,

 
 
3
9
9
,

 
 
2
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
6
2
9
]
,

 
[
4
9
8
7
,
 
9
4
,
 
5
,
 
2
9
7
,
 
1
3
1
]
,

 
[
5
,
 
4
1
7
,
 
4
,
 
1
,
 
6
5
1
5
,
 
2
,
 
3
9
,
 
5
8
,
 
1
9
1
3
5
]
,

 
[
2
1
,

 
 
8
3
,

 
 
1
1
,

 
 
2
2
8
,

 
 
4
,

 
 
2
2
,

 
 
6
4
,

 
 
1
,

 
 
7
9
8
,

 
 
1
0
4
,

 
 
1
0
8
1
,

 
 
2
,

 
 
6
9
6
,

 
 
1
4
8
7
9
,

 
 
3
,

 
 
2
2
0
,

 
 
7
7
3
0
,

 
 
1
8
,

 
 
1
3
,

 
 
1
,

 
 
1
4
8
,

 
 
1
1
,

 
 
3
2
4
,

 
 
5
0
,

 
 
6
0
7
6
,

 
 
3
,

 
 
2
9
8
,

 
 
2
,

 
 
9
5
,

 
 
1
4
2
,

 
 
2
,

 
 
1
4
2
,

 
 
5
0
,

 
 
1
7
6
,

 
 
3
,

 
 
5
0
,

 
 
5
5
1
,

 
 
7
,

 
 
4
3
9
,

 
 
3
,

 
 
7
,

 
 
7
2
]
,

 
[
1
0
,

 
 
2
3
1
,

 
 
2
9
,

 
 
8
0
3
,

 
 
7
,

 
 
3
7
6
,

 
 
3
4
2
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
5
0
,

 
 
3
8
4
2
,

 
 
1
3
0
5
,

 
 
1
,

 
 
8
1
1
,

 
 
3
,

 
 
5
,

 
 
1
2
3
,

 
 
8
5
5
3
,

 
 
9
,

 
 
5
,

 
 
5
3
2
1
,

 
 
5
0
,

 
 
1
0
4
7
,

 
 
5
9
,

 
 
1
,

 
 
3
6
8
0
,

 
 
5
8
,

 
 
1
1
1
2
,

 
 
6
1
,

 
 
1
0
4
,

 
 
3
,

 
 
3
8
6
4
,

 
 
7
,

 
 
5
9
3
,

 
 
2
8
2
7
,

 
 
8
8
4
,

 
 
5
,

 
 
5
2
4
9
,

 
 
3
,

 
 
4
6
,

 
 
7
0
6
5
,

 
 
2
0
9
,

 
 
1
0
1
,

 
 
3
5
9
,

 
 
9
,

 
 
8
,

 
 
1
1
9
1
]
,

 
[
1
2
4
,
 
6
5
,
 
3
4
,
 
4
5
2
,
 
7
,
 
1
,
 
6
1
,
 
1
2
3
3
,
 
1
,
 
1
4
6
6
3
,
 
1
7
,
 
2
2
6
,
 
5
0
,
 
5
9
,
 
6
,
 
4
5
0
,
 
1
1
1
4
]
,

 
[
5
2
,
 
1
4
,
 
1
1
1
3
,
 
9
7
,
 
1
1
2
4
,
 
8
9
1
,
 
2
9
,
 
1
2
7
,
 
1
2
3
8
4
,
 
7
,
 
1
5
,
 
3
8
4
3
,
 
3
2
7
]
,

 
[
1
8
,
 
8
7
7
,
 
4
0
4
,
 
2
5
,
 
3
7
,
 
4
6
8
5
,
 
2
,
 
2
9
3
0
,
 
3
,
 
9
7
,
 
5
8
,
 
1
8
0
2
,
 
1
1
,
 
6
8
5
,
 
4
9
8
8
]
,

 
[
1
1
,
 
8
,
 
6
,
 
1
8
9
,
 
7
0
6
6
]
,

 
[
5
,

 
 
1
2
3
8
5
,

 
 
4
,

 
 
5
3
,

 
 
3
5
6
,

 
 
1
2
,

 
 
3
3
7
,

 
 
3
5
7
,

 
 
5
,

 
 
1
4
2
9
,

 
 
1
,

 
 
1
7
7
,

 
 
7
0
6
7
,

 
 
7
,

 
 
1
0
7
5
9
,

 
 
3
2
,

 
 
1
5
,

 
 
2
8
2
5
]
,

 
[
1
1
,

 
 
8
,

 
 
9
5
0
3
,

 
 
9
,

 
 
1
,

 
 
6
0
7
7
,

 
 
2
,

 
 
1
,

 
 
8
5
5
4
,

 
 
6
5
1
6
,

 
 
8
,

 
 
1
3
7
,

 
 
1
9
6
,

 
 
5
9
,

 
 
9
,

 
 
2
,

 
 
5
5
,

 
 
9
5
0
4
,

 
 
2
0
6
8
,

 
 
3
,

 
 
1
,

 
 
3
8
6
5
,

 
 
7
4
7
,

 
 
2
,

 
 
6
,

 
 
7
8
6
,

 
 
3
6
9
5
,

 
 
1
6
9
,

 
 
1
,

 
 
1
0
7
6
0
,

 
 
2
,

 
 
1
4
9
7
,

 
 
8
,

 
 
6
,

 
 
2
6
3
,

 
 
2
2
4
2
,

 
 
2
8
2
0
,

 
 
4
4
,

 
 
3
,

 
 
1
9
,

 
 
1
7
2
0
,

 
 
1
0
5
4
,

 
 
4
,

 
 
8
5
5
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

 
 
1
5
1
,

 
 
2
3
7
3
,

 
 
2
,

 
 
1
,

 
 
2
9
6
,

 
 
2
6
0
8
,

 
 
2
9
3
,

 
 
1
4
9
4
,

 
 
6
6
,

 
 
2
4
,

 
 
4
2
8
,

 
 
1
,

 
 
1
3
7
,

 
 
1
3
6
4
,

 
 
2
,

 
 
5
6
7
3
,

 
 
1
4
8
8
0
,

 
 
1
,

 
 
2
0
4
,

 
 
2
,

 
 
1
2
3
8
6
,

 
 
1
0
6
,

 
 
6
5
1
7
,

 
 
3
5
1
,

 
 
4
7
,

 
 
1
3
1
5
,

 
 
1
0
0
,

 
 
1
,

 
 
7
7
3
1
,

 
 
1
8
9
8
,

 
 
2
0
2
,

 
 
8
,

 
 
1
8
5
,

 
 
2
5
4
7
,

 
 
7
,

 
 
6
,

 
 
9
5
0
5
,

 
 
2
,

 
 
4
0
1
,

 
 
1
0
1
3
]
,

 
[
3
3
2
,
 
5
,
 
4
8
2
,
 
1
,
 
5
8
2
,
 
2
5
,
 
1
4
5
4
,
 
6
5
,
 
4
4
,
 
1
,
 
3
0
5
1
]
,

 
[
1
9
1
3
6
,

 
 
4
2
4
4
,

 
 
3
1
1
,

 
 
2
2
4
3
,

 
 
3
3
0
,

 
 
6
0
7
8
,

 
 
3
1
1
,

 
 
1
9
1
3
7
,

 
 
1
6
,

 
 
3
3
,

 
 
2
7
8
,

 
 
2
2
,

 
 
3
,

 
 
1
2
4
,

 
 
1
1
,

 
 
8
,

 
 
1
5
,

 
 
2
7
7
,

 
 
3
1
1
,

 
 
9
,

 
 
1
,

 
 
2
5
2
0
,

 
 
5
3
2
2
]
,

 
[
1
6
,

 
 
1
0
9
,

 
 
1
6
,

 
 
5
1
,

 
 
1
2
3
8
7
,

 
 
3
7
9
,

 
 
6
,

 
 
4
7
0
,

 
 
1
4
,

 
 
2
8
2
8
,

 
 
3
7
,

 
 
1
5
4
1
,

 
 
2
,

 
 
1
1
5
4
,

 
 
3
7
0
9
,

 
 
3
8
7
,

 
 
1
7
4
1
,

 
 
7
,

 
 
3
0
,

 
 
1
0
0
0
,

 
 
5
2
,

 
 
9
,

 
 
3
4
,

 
 
2
9
,

 
 
3
2
,

 
 
9
2
,

 
 
1
7
2
1
,

 
 
1
3
,

 
 
6
7
,

 
 
4
4
7
9
,

 
 
3
,

 
 
9
,

 
 
3
3
8
,

 
 
2
3
,

 
 
7
7
3
2
,

 
 
3
0
,

 
 
1
0
7
6
1
,

 
 
4
,

 
 
3
4
1
,

 
 
7
,

 
 
6
,

 
 
2
5
6
,

 
 
1
9
1
3
8
,

 
 
4
7
7
,

 
 
4
,

 
 
5
1
,

 
 
3
5
3
6
,

 
 
1
4
,

 
 
2
0
7
,

 
 
6
6
,

 
 
1
,

 
 
2
4
9
,

 
 
2
,

 
 
1
1
5
4
,

 
 
1
9
5
5
,

 
 
1
6
,

 
 
3
7
0
4
,

 
 
3
,

 
 
5
4
0
,

 
 
6
4
,

 
 
2
0
1
,

 
 
1
4
,

 
 
8
,

 
 
9
6
9
,

 
 
4
,

 
 
6
6
5
,

 
 
3
0
,

 
 
4
,

 
 
3
7
1
,

 
 
4
,

 
 
7
0
6
8
,

 
 
1
5
0
,

 
 
4
,

 
 
1
,

 
 
2
7
9
,

 
 
3
2
9
,

 
 
2
,

 
 
1
4
2
]
,

 
[
4
2
4
5
,
 
1
1
,
 
3
,
 
5
9
5
,
 
1
1
5
,
 
3
6
,
 
2
6
8
]
,

 
[
1
2
0
,

 
 
3
9
1
,

 
 
1
4
,

 
 
7
,

 
 
1
5
,

 
 
5
3
2
3
,

 
 
2
3
0
9
,

 
 
4
,

 
 
4
7
1
8
,

 
 
6
,

 
 
4
4
8
0
,

 
 
4
9
1
,

 
 
2
,

 
 
1
5
,

 
 
9
5
0
6
,

 
 
1
2
3
8
8
,

 
 
1
4
,

 
 
1
0
8
,

 
 
1
5
0
,

 
 
3
3
8
5
,

 
 
6
0
7
9
,

 
 
7
,

 
 
1
,

 
 
2
2
4
4
]
,

 
[
2
0
0
9
,

 
 
1
4
2
,

 
 
1
2
,

 
 
3
2
,

 
 
7
1
0
,

 
 
4
3
,

 
 
4
5
,

 
 
1
9
3
,

 
 
1
4
,

 
 
6
7
4
,

 
 
1
4
8
8
1
,

 
 
2
6
4
,

 
 
1
9
7
,

 
 
3
5
,

 
 
4
3
2
,

 
 
1
1
2
5
,

 
 
3
,

 
 
4
5
,

 
 
1
1
8
,

 
 
2
8
,

 
 
3
6
,

 
 
3
0
7
,

 
 
9
,

 
 
1
,

 
 
4
5
9
,

 
 
2
,

 
 
2
6
,

 
 
2
6
3
4
,

 
 
4
0
5
0
,

 
 
1
0
8
,

 
 
4
3
,

 
 
4
4
5
,

 
 
1
9
3
]
,

 
[
1
,
 
2
6
2
1
,
 
6
0
1
2
,
 
1
,
 
5
3
2
4
,
 
2
,
 
6
,
 
8
5
5
6
,
 
3
,
 
6
0
3
9
,
 
6
,
 
3
5
3
7
,
 
2
,
 
1
4
8
8
2
,
 
2
,
 
6
4
4
7
]
,

 
[
2
4
8
,

 
 
6
6
,

 
 
1
,

 
 
2
7
0
9
,

 
 
4
,

 
 
5
3
2
5
,

 
 
5
3
2
6
,

 
 
1
3
,

 
 
1
,

 
 
1
0
9
,

 
 
5
3
2
7
,

 
 
9
,

 
 
1
4
8
8
3
,

 
 
2
3
2
,

 
 
2
7
,

 
 
2
3
7
4
,

 
 
2
,

 
 
1
,

 
 
1
2
1
7
,

 
 
6
5
1
8
,

 
 
2
6
0
,

 
 
6
5
,

 
 
3
1
8
,

 
 
6
,

 
 
3
3
8
1
,

 
 
4
,

 
 
1
,

 
 
1
7
6
3
]
,

 
[
1
4
,
 
7
7
,
 
5
,
 
1
9
1
3
9
,
 
1
0
1
,
 
1
0
7
6
2
,
 
2
0
5
,
 
1
,
 
3
7
1
0
,
 
2
,
 
1
2
3
8
9
]
,

 
[
1
0
8
,
 
5
2
2
,
 
7
,
 
1
1
2
0
,
 
1
2
2
,
 
1
4
8
]
,

 
[
5
,
 
7
3
,
 
4
0
,
 
1
8
,
 
4
,
 
1
0
4
,
 
5
0
0
,
 
2
0
,
 
1
2
7
,
 
6
8
8
,
 
4
,
 
3
4
8
5
,
 
1
,
 
2
6
4
,
 
5
3
2
8
,
 
2
,
 
1
0
2
1
]
,

 
[
3
4
,

 
 
2
3
3
,

 
 
6
6
,

 
 
1
3
1
0
,

 
 
5
7
,

 
 
1
,

 
 
4
6
4
,

 
 
1
0
5
,

 
 
1
,

 
 
2
2
5
,

 
 
2
,

 
 
3
2
7
1
,

 
 
3
2
3
1
,

 
 
1
2
,

 
 
4
3
,

 
 
9
6
,

 
 
3
,

 
 
1
0
5
,

 
 
2
8
8
,

 
 
1
,

 
 
2
6
3
8
,

 
 
1
0
6
,

 
 
2
4
0
]
,

 
[
6
,
 
3
9
8
6
,
 
7
1
,
 
9
,
 
2
8
3
,
 
1
8
,
 
2
8
8
5
,
 
2
6
2
]
,

 
[
1
,

 
 
7
0
6
9
,

 
 
5
8
,

 
 
7
9
5
,

 
 
4
,

 
 
1
1
,

 
 
7
,

 
 
1
9
1
8
,

 
 
7
0
7
0
,

 
 
3
3
8
6
,

 
 
3
,

 
 
9
2
,

 
 
7
0
7
0
,

 
 
2
9
2
4
,

 
 
3
2
,

 
 
1
1
1
5
,

 
 
1
3
,

 
 
6
9
6
8
,

 
 
8
5
5
7
,

 
 
7
,

 
 
2
6
,

 
 
1
0
2
7
,

 
 
9
5
0
7
,

 
 
2
,

 
 
3
7
7
,

 
 
3
,

 
 
7
7
3
3
,

 
 
1
9
1
4
0
,

 
 
2
,

 
 
1
,

 
 
6
5
1
9
,

 
 
9
5
0
8
]
,

 
[
1
9
5
,

 
 
2
6
,

 
 
3
3
9
,

 
 
5
,

 
 
1
6
2
,

 
 
9
2
2
,

 
 
1
7
,

 
 
1
,

 
 
8
3
,

 
 
7
2
,

 
 
2
,

 
 
1
,

 
 
1
5
6
3
,

 
 
2
,

 
 
1
,

 
 
1
2
3
9
0
,

 
 
1
5
8
,

 
 
1
9
,

 
 
6
4
9
7
,

 
 
1
,

 
 
3
1
0
8
]
,

 
[
7
,

 
 
1
6
9
6
,

 
 
4
,

 
 
1
,

 
 
3
4
8
,

 
 
1
1
,

 
 
2
5
,

 
 
6
4
,

 
 
4
5
7
,

 
 
4
,

 
 
1
5
5
9
,

 
 
5
3
,

 
 
3
4
,

 
 
3
1
,

 
 
6
9
,

 
 
2
6
3
9
,

 
 
9
,

 
 
1
,

 
 
6
9
2
,

 
 
2
5
,

 
 
1
5
6
9
,

 
 
6
8
,

 
 
2
7
,

 
 
1
2
3
9
1
,

 
 
3
,

 
 
6
2
,

 
 
2
1
,

 
 
1
,

 
 
1
8
0
8
,

 
 
2
,

 
 
6
,

 
 
5
6
8
6
,

 
 
2
8
,

 
 
7
7
3
,

 
 
4
,

 
 
3
,

 
 
2
0
9
5
,

 
 
4
,

 
 
7
0
,

 
 
4
9
1
,

 
 
2
,

 
 
1
,

 
 
1
7
4
,

 
 
7
5
,

 
 
1
9
5
,

 
 
1
,

 
 
7
7
4
,

 
 
2
,

 
 
6
,

 
 
1
3
6
0
]
,

 
[
1
0
,

 
 
1
5
7
0
,

 
 
5
2
,

 
 
2
1
4
,

 
 
1
0
,

 
 
1
7
3
,

 
 
4
,

 
 
2
0
0
2
,

 
 
2
2
,

 
 
4
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
1
2
2
,

 
 
4
7
6
,

 
 
2
7
,

 
 
1
,

 
 
1
0
9
,

 
 
3
0
1
,

 
 
2
,

 
 
1
,

 
 
9
5
0
9
,

 
 
1
7
4
,

 
 
3
,

 
 
2
1
,

 
 
1
,

 
 
8
3
,

 
 
1
1
7
1
,

 
 
2
,

 
 
1
5
,

 
 
1
9
1
4
1
,

 
 
1
6
0
5
,

 
 
5
,

 
 
2
7
6
,

 
 
4
1
6
]
,

 
[
5
,

 
 
9
4
,

 
 
2
0
,

 
 
1
4
4
,

 
 
1
2
0
,

 
 
5
,

 
 
1
1
7
,

 
 
4
,

 
 
5
0
7
,

 
 
2
7
,

 
 
8
9
,

 
 
6
,

 
 
2
6
5
,

 
 
1
8
,

 
 
5
,

 
 
8
,

 
 
2
0
,

 
 
1
1
0
,

 
 
4
1
,

 
 
5
,

 
 
7
7
3
,

 
 
4
5
]
,

 
[
2
6
,

 
 
2
4
9
,

 
 
1
8
5
4
,

 
 
2
2
,

 
 
3
,

 
 
5
3
2
9
,

 
 
2
2
,

 
 
2
1
,

 
 
1
0
1
,

 
 
1
9
9
,

 
 
2
4
,

 
 
1
9
,

 
 
5
,

 
 
8
0
,

 
 
1
1
9
7
,

 
 
3
1
,

 
 
4
2
4
6
,

 
 
1
5
2
5
,

 
 
3
,

 
 
8
0
0
]
,

 
[
1
4
9
1
,
 
3
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
4
5
3
,
 
9
2
,
 
2
3
,
 
1
2
3
9
2
,
 
1
,
 
4
0
5
1
,
 
1
0
0
1
]
,

 
[
3
6
,

 
 
2
6
4
0
,

 
 
1
2
3
9
3
,

 
 
2
,

 
 
4
9
8
9
,

 
 
4
4
8
1
,

 
 
2
3
1
0
,

 
 
4
7
1
9
,

 
 
1
,

 
 
4
4
8
2
,

 
 
2
,

 
 
1
,

 
 
1
3
3
9
,

 
 
1
0
3
4
,

 
 
4
8
7
,

 
 
4
7
2
0
,

 
 
1
,

 
 
1
5
1
2
,

 
 
1
3
2
8
,

 
 
1
7
4
,

 
 
3
,

 
 
7
0
7
1
,

 
 
1
9
1
4
2
]
,

 
[
5
,

 
 
6
2
,

 
 
1
9
0
,

 
 
1
8
5
0
,

 
 
4
,

 
 
5
3
,

 
 
6
7
,

 
 
3
9
8
,

 
 
4
2
4
7
,

 
 
1
8
,

 
 
1
9
7
5
,

 
 
2
2
,

 
 
5
2
,

 
 
4
,

 
 
3
0
3
,

 
 
4
,

 
 
1
,

 
 
2
7
3
9
,

 
 
1
3
0
,

 
 
6
7
8
,

 
 
6
2
2
,

 
 
7
,

 
 
2
2
,

 
 
8
9
,

 
 
5
4
5
,

 
 
3
9
8
,

 
 
2
,

 
 
3
2
6
3
,

 
 
5
3
1
,

 
 
3
,

 
 
4
3
4
,

 
 
1
8
,

 
 
1
9
,

 
 
3
2
,

 
 
6
0
0
0
,

 
 
7
,

 
 
3
5
3
8
,

 
 
1
5
2
,

 
 
3
,

 
 
4
9
3
1
,

 
 
1
7
,

 
 
1
0
,

 
 
4
2
4
8
,

 
 
1
7
,

 
 
4
0
,

 
 
5
,

 
 
4
9
7
,

 
 
7
,

 
 
3
7
,

 
 
1
6
4
7
,

 
 
1
8
5
,

 
 
1
1
4
5
,

 
 
5
2
6
,

 
 
5
3
3
0
,

 
 
4
,

 
 
4
1
4
,

 
 
6
3
]
,

 
[
1
8
,
 
5
,
 
1
2
,
 
3
6
,
 
2
1
3
3
,
 
3
6
,
 
5
8
6
,
 
4
7
2
1
,
 
3
5
,
 
4
6
7
1
,
 
5
6
1
]
,

 
[
5
3
2
5
,
 
5
3
2
6
,
 
2
5
,
 
1
,
 
9
7
6
,
 
3
,
 
3
9
8
0
,
 
2
,
 
1
,
 
1
1
6
5
]
,

 
[
4
1
,

 
 
9
5
1
0
,

 
 
7
3
,

 
 
3
2
7
2
,

 
 
4
2
,

 
 
2
9
,

 
 
3
0
1
5
,

 
 
8
6
8
,

 
 
1
3
,

 
 
3
6
,

 
 
9
5
4
,

 
 
2
,

 
 
1
9
1
4
3
,

 
 
8
1
,

 
 
1
,

 
 
7
9
,

 
 
6
5
2
0
,

 
 
2
1
,

 
 
1
,

 
 
2
2
7
5
]
,

 
[
1
2
0
,

 
 
1
4
8
8
4
,

 
 
5
6
,

 
 
5
5
,

 
 
3
9
8
,

 
 
3
,

 
 
1
2
0
,

 
 
1
7
6
,

 
 
2
5
,

 
 
9
,

 
 
4
0
4
7
,

 
 
1
5
2
,

 
 
3
4
,

 
 
3
1
,

 
 
2
,

 
 
9
1
,

 
 
7
5
,

 
 
7
,

 
 
1
,

 
 
1
7
6
4
,

 
 
2
,

 
 
4
6
7
,

 
 
5
,

 
 
3
5
3
1
,

 
 
2
1
0
,

 
 
1
7
0
2
,

 
 
1
3
,

 
 
6
,

 
 
1
8
8
,

 
 
2
,

 
 
1
0
,

 
 
1
3
1
2
,

 
 
3
,

 
 
2
6
4
1
,

 
 
1
0
7
6
3
,

 
 
1
0
,

 
 
2
4
7
,

 
 
3
1
4
,

 
 
1
,

 
 
4
2
4
]
,

 
[
7
3
3
,
 
5
2
4
,
 
2
5
1
6
,
 
6
6
,
 
1
,
 
6
5
7
]
,

 
[
5
,

 
 
8
,

 
 
7
,

 
 
1
,

 
 
3
2
6
1
,

 
 
2
,

 
 
6
,

 
 
7
7
3
4
,

 
 
3
,

 
 
1
3
,

 
 
1
4
8
8
5
,

 
 
7
,

 
 
1
7
3
,

 
 
1
0
,

 
 
1
1
3
3
,

 
 
2
1
,

 
 
1
0
,

 
 
3
0
1
,

 
 
5
,

 
 
1
9
1
4
4
,

 
 
6
,

 
 
1
4
5
6
,

 
 
4
7
2
2
,

 
 
2
7
,

 
 
1
,

 
 
2
2
0
,

 
 
1
0
7
6
4
]
,

 
[
8
2
,

 
 
1
4
8
,

 
 
1
4
,

 
 
2
7
3
,

 
 
4
,

 
 
4
1
4
,

 
 
1
,

 
 
1
2
6
6
,

 
 
7
6
8
1
,

 
 
6
5
4
,

 
 
2
3
,

 
 
2
5
5
,

 
 
3
,

 
 
4
,

 
 
9
5
1
,

 
 
6
3
,

 
 
7
,

 
 
5
4
4
,

 
 
4
1
,

 
 
4
2
,

 
 
4
7
2
3
,

 
 
1
9
1
4
5
,

 
 
7
4
,

 
 
2
,

 
 
3
1
9
,

 
 
4
0
5
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
5
,

 
 
9
2
9
,

 
 
5
4
3
,

 
 
4
,

 
 
1
1
3
,

 
 
4
7
0
,

 
 
4
7
2
4
,

 
 
1
3
0
,

 
 
4
6
2
,

 
 
3
6
,

 
 
5
9
9
,

 
 
3
1
1
,

 
 
1
4
8
8
6
]
,

 
[
3
0
,

 
 
1
3
2
7
,

 
 
2
,

 
 
3
9
6
,

 
 
1
5
4
2
,

 
 
3
0
,

 
 
1
0
6
,

 
 
4
,

 
 
3
9
8
5
,

 
 
1
3
,

 
 
1
,

 
 
7
7
3
5
,

 
 
2
,

 
 
9
1
,

 
 
7
5
,

 
 
9
7
,

 
 
3
1
5
8
,

 
 
2
7
,

 
 
3
7
0
7
,

 
 
1
5
2
,

 
 
9
1
9
,

 
 
3
4
5
,

 
 
2
8
4
,

 
 
7
,

 
 
1
,

 
 
9
5
6
,

 
 
2
,

 
 
3
7
,

 
 
5
2
7
1
,

 
 
4
,

 
 
2
8
,

 
 
1
7
2
8
,

 
 
5
9
,

 
 
2
,

 
 
6
,

 
 
2
3
1
1
,

 
 
4
,

 
 
2
3
0
,

 
 
4
8
,

 
 
8
4
,

 
 
3
5
3
9
]
,

 
[
6
,

 
 
5
3
6
,

 
 
2
,

 
 
1
9
1
4
6
,

 
 
1
9
1
4
7
,

 
 
3
7
1
1
,

 
 
6
,

 
 
1
8
9
,

 
 
4
3
7
,

 
 
3
,

 
 
7
0
7
2
,

 
 
2
4
8
,

 
 
1
4
1
,

 
 
5
7
5
,

 
 
2
2
,

 
 
2
1
,

 
 
9
,

 
 
1
9
9
,

 
 
1
6
,

 
 
6
,

 
 
4
6
7
1
,

 
 
1
1
0
8
]
,

 
[
3
4
,

 
 
1
1
5
2
,

 
 
1
,

 
 
7
8
7
,

 
 
1
1
5
7
,

 
 
2
7
,

 
 
1
1
0
3
,

 
 
3
2
,

 
 
3
7
,

 
 
1
1
5
7
,

 
 
1
0
5
4
,

 
 
9
5
1
1
,

 
 
2
3
,

 
 
1
0
2
3
,

 
 
3
,

 
 
5
1
9
,

 
 
2
3
,

 
 
5
5
,

 
 
1
2
2
,

 
 
1
4
7
,

 
 
5
8
,

 
 
5
2
,

 
 
1
7
5
,

 
 
1
,

 
 
6
6
5
,

 
 
2
,

 
 
6
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
2
2
0
,

 
 
9
8
,

 
 
5
9
8
,

 
 
4
,

 
 
3
4
7
,

 
 
3
2
,

 
 
7
0
7
3
,

 
 
3
5
,

 
 
2
1
3
,

 
 
4
,

 
 
1
,

 
 
3
6
2
]
,

 
[
1
1
,

 
 
8
,

 
 
1
4
,

 
 
5
8
,

 
 
1
2
,

 
 
3
9
0
,

 
 
2
2
,

 
 
3
2
,

 
 
1
,

 
 
1
2
9
7
,

 
 
5
,

 
 
1
2
,

 
 
2
,

 
 
3
2
3
4
,

 
 
8
2
,

 
 
5
,

 
 
8
,

 
 
8
5
1
2
,

 
 
7
,

 
 
1
2
9
1
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
3
,
 
3
,
 
1
,
 
8
1
8
,
 
2
9
9
,
 
3
,
 
1
2
7
5
,
 
1
1
,
 
8
,
 
8
1
8
,
 
1
8
,
 
1
7
8
,
 
7
3
3
,
 
1
1
,
 
8
,
 
4
2
7
]
,

 
[
4
1
,

 
 
7
2
1
,

 
 
2
6
4
2
,

 
 
6
6
,

 
 
6
,

 
 
5
3
3
1
,

 
 
4
,

 
 
1
,

 
 
1
2
3
9
4
,

 
 
1
5
3
5
,

 
 
4
4
3
0
,

 
 
2
2
4
,

 
 
1
,

 
 
4
3
6
,

 
 
2
,

 
 
1
,

 
 
1
9
4
8
,

 
 
1
4
,

 
 
9
6
,

 
 
1
2
2
1
8
,

 
 
2
,

 
 
6
,

 
 
5
3
3
2
,

 
 
2
4
5
6
,

 
 
4
2
4
9
,

 
 
3
,

 
 
1
8
0
3
,

 
 
6
9
7
,

 
 
1
3
,

 
 
3
0
0
,

 
 
1
9
1
4
8
,

 
 
3
,

 
 
2
0
1
1
,

 
 
2
3
,

 
 
1
,

 
 
3
3
8
2
,

 
 
3
3
6
6
,

 
 
1
4
8
8
8
,

 
 
5
9
9
,

 
 
7
,

 
 
5
6
8
7
,

 
 
1
0
7
6
5
]
,

 
[
1
,
 
4
0
0
4
,
 
1
6
2
,
 
2
1
6
7
,
 
1
5
,
 
3
0
4
,
 
5
7
3
,
 
1
2
5
6
,
 
3
0
5
2
,
 
7
0
7
4
,
 
2
4
,
 
1
5
,
 
3
9
9
]
,

 
[
1
,
 
9
9
,
 
4
2
5
0
,
 
8
5
5
8
,
 
7
,
 
1
,
 
1
6
7
,
 
1
3
6
,
 
7
0
,
 
4
7
2
5
,
 
1
5
6
1
,
 
2
,
 
1
,
 
3
0
5
3
,
 
3
5
,
 
4
9
9
0
]
,

 
[
1
1
3
,

 
 
2
9
,

 
 
1
,

 
 
7
7
3
6
,

 
 
7
,

 
 
5
1
,

 
 
8
5
2
5
,

 
 
3
,

 
 
1
1
3
,

 
 
2
9
,

 
 
1
,

 
 
1
9
1
4
9
,

 
 
1
2
3
9
5
,

 
 
5
7
,

 
 
1
9
,

 
 
4
2
,

 
 
6
0
8
0
]
,

 
[
6
2
3
,

 
 
1
6
,

 
 
9
0
2
,

 
 
5
8
0
,

 
 
3
,

 
 
6
5
2
1
,

 
 
1
6
,

 
 
9
,

 
 
4
8
,

 
 
1
4
3
,

 
 
1
0
,

 
 
6
4
9
,

 
 
3
,

 
 
1
0
7
6
6
,

 
 
9
3
8
,

 
 
1
,

 
 
4
5
9
,

 
 
1
0
5
,

 
 
1
4
,

 
 
1
2
,

 
 
4
3
,

 
 
2
1
0
6
]
,

 
[
3
8
1
,

 
 
5
2
,

 
 
8
5
5
9
,

 
 
8
8
,

 
 
1
,

 
 
5
6
8
8
,

 
 
1
7
,

 
 
4
9
9
1
,

 
 
2
,

 
 
2
5
7
,

 
 
1
4
2
5
,

 
 
3
4
,

 
 
2
3
2
,

 
 
2
0
,

 
 
6
1
,

 
 
1
3
7
,

 
 
2
4
,

 
 
1
,

 
 
1
2
3
3
,

 
 
2
6
,

 
 
2
2
8
1
,

 
 
3
5
,

 
 
1
9
1
5
0
,

 
 
1
9
,

 
 
2
1
3
4
,

 
 
2
5
,

 
 
1
,

 
 
1
3
5
5
,

 
 
2
,

 
 
1
,

 
 
3
5
9
,

 
 
1
4
8
8
9
,

 
 
1
9
3
,

 
 
3
,

 
 
2
4
0
5
,

 
 
8
5
,

 
 
2
1
0
,

 
 
4
7
9
,

 
 
1
1
7
9
,

 
 
2
6
4
3
,

 
 
2
3
]
,

 
[
1
8
3
,
 
4
6
,
 
5
,
 
1
2
9
,
 
8
2
,
 
1
2
6
,
 
1
,
 
1
5
9
,
 
1
6
,
 
5
,
 
1
2
,
 
2
5
7
,
 
1
1
]
,

 
[
3
2
,
 
9
5
,
 
1
2
5
1
,
 
3
,
 
3
2
,
 
7
4
0
,
 
4
4
8
3
,
 
1
6
2
,
 
1
9
5
3
,
 
7
,
 
5
1
,
 
5
7
8
,
 
2
1
0
1
]
,

 
[
1
0
0
,

 
 
5
,

 
 
8
,

 
 
1
6
3
9
,

 
 
5
,

 
 
1
8
2
,

 
 
5
3
,

 
 
3
3
,

 
 
1
9
1
1
,

 
 
2
3
,

 
 
2
4
1
,

 
 
1
8
,

 
 
5
2
,

 
 
1
1
,

 
 
9
1
0
,

 
 
6
4
,

 
 
6
,

 
 
3
5
9
,

 
 
8
9
,

 
 
1
7
,

 
 
1
2
7
0
,

 
 
1
6
,

 
 
3
6
3
,

 
 
3
1
6
,

 
 
6
,

 
 
1
7
8
0
,

 
 
5
,

 
 
5
8
7
]
,

 
[
7
,

 
 
1
,

 
 
1
7
5
4
,

 
 
3
2
7
,

 
 
1
5
6
2
,

 
 
8
,

 
 
3
3
8
7
,

 
 
5
0
,

 
 
9
7
4
,

 
 
3
,

 
 
7
2
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
5
3
1
,

 
 
1
9
4
3
,

 
 
2
1
7
,

 
 
3
9
,

 
 
2
9
,

 
 
9
7
,

 
 
2
,

 
 
1
,

 
 
1
3
3
2
,

 
 
6
5
2
2
]
,

 
[
1
,

 
 
1
0
9
2
,

 
 
2
2
9
,

 
 
7
,

 
 
1
,

 
 
1
2
3
9
6
,

 
 
2
,

 
 
1
,

 
 
7
2
7
,

 
 
3
1
2
,

 
 
2
1
6
2
,

 
 
3
,

 
 
3
8
6
6
,

 
 
8
1
,

 
 
1
0
0
,

 
 
8
7
5
,

 
 
1
6
8
,

 
 
4
7
,

 
 
1
9
1
5
1
,

 
 
6
5
2
3
,

 
 
3
3
8
5
,

 
 
2
3
,

 
 
1
,

 
 
1
0
6
9
9
,

 
 
2
,

 
 
6
,

 
 
3
8
6
7
]
,

 
[
4
1
,

 
 
4
2
,

 
 
1
2
,

 
 
1
6
2
9
,

 
 
4
,

 
 
4
3
6
,

 
 
6
0
,

 
 
4
5
,

 
 
8
,

 
 
7
0
,

 
 
2
9
1
,

 
 
3
5
,

 
 
1
,

 
 
1
0
3
,

 
 
8
,

 
 
1
1
4
3
,

 
 
1
5
8
,

 
 
5
,

 
 
2
3
3
,

 
 
5
7
,

 
 
1
,

 
 
8
7
6
,

 
 
3
,

 
 
2
2
2
1
,

 
 
1
0
,

 
 
1
1
1
,

 
 
1
0
5
6
,

 
 
3
,

 
 
7
7
3
7
,

 
 
1
7
,

 
 
1
,

 
 
5
9
7
]
,

 
[
2
6
,
 
7
3
,
 
1
0
7
6
7
,
 
1
1
6
,
 
1
7
,
 
6
,
 
7
2
,
 
7
,
 
3
0
6
,
 
5
,
 
8
,
 
2
0
,
 
1
9
1
5
2
,
 
1
8
,
 
1
0
,
 
1
1
3
3
,
 
8
]
,

 
[
2
6
,
 
8
,
 
3
2
,
 
3
3
2
,
 
1
8
,
 
1
1
,
 
8
,
 
2
0
,
 
1
9
6
,
 
4
7
2
6
,
 
4
,
 
2
3
4
,
 
1
,
 
1
2
3
9
7
,
 
3
0
2
]
,

 
[
4
2
,

 
 
9
5
0
,

 
 
2
,

 
 
5
1
,

 
 
2
7
2
6
,

 
 
6
0
8
1
,

 
 
3
,

 
 
2
,

 
 
1
,

 
 
2
5
9
9
,

 
 
2
,

 
 
1
5
,

 
 
2
5
4
8
,

 
 
3
,

 
 
1
4
8
9
0
,

 
 
7
,

 
 
1
,

 
 
1
2
5
0
,

 
 
2
,

 
 
1
,

 
 
3
8
6
6
,

 
 
1
9
,

 
 
2
7
3
3
,

 
 
1
2
,

 
 
2
0
5
6
,

 
 
1
7
,

 
 
3
9
]
,

 
[
5
3
4
,

 
 
2
0
5
,

 
 
1
,

 
 
6
4
,

 
 
3
8
6
8
,

 
 
9
,

 
 
5
,

 
 
3
1
,

 
 
1
8
0
9
,

 
 
4
4
,

 
 
3
3
,

 
 
7
8
,

 
 
5
0
1
,

 
 
3
,

 
 
8
7
3
,

 
 
2
4
,

 
 
1
7
5
,

 
 
1
0
,

 
 
1
9
1
5
3
,

 
 
6
6
5
,

 
 
1
6
,

 
 
3
6
,

 
 
2
1
3
5
,

 
 
4
0
,

 
 
5
0
9
,

 
 
1
2
9
,

 
 
7
3
,

 
 
8
7
3
,

 
 
2
4
,

 
 
3
5
1
,

 
 
4
0
,

 
 
1
1
4
,

 
 
4
0
7
]
,

 
[
1
8
,

 
 
1
4
,

 
 
8
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
0
,

 
 
1
9
1
5
4
,

 
 
7
,

 
 
1
9
1
5
5
,

 
 
3
1
,

 
 
4
2
2
,

 
 
2
,

 
 
1
2
3
9
8
,

 
 
3
,

 
 
6
4
,

 
 
1
9
1
5
6
,

 
 
5
2
,

 
 
1
4
,

 
 
1
9
1
5
7
,

 
 
6
,

 
 
5
1
7
,

 
 
2
,

 
 
1
,

 
 
1
9
1
5
8
,

 
 
9
,

 
 
4
2
1
,

 
 
4
0
5
2
,

 
 
2
,

 
 
9
3
0
]
,

 
[
1
,
 
5
4
1
,
 
1
1
0
5
,
 
2
3
,
 
1
,
 
7
7
3
8
,
 
2
,
 
6
,
 
4
7
2
7
,
 
2
5
,
 
9
,
 
2
,
 
6
6
2
,
 
6
0
4
3
]
,

 
[
6
6
1
,

 
 
5
,

 
 
1
8
2
,

 
 
2
0
,

 
 
1
,

 
 
4
7
2
8
,

 
 
1
1
,

 
 
8
,

 
 
6
8
,

 
 
4
,

 
 
7
9
7
,

 
 
1
,

 
 
2
0
2
0
,

 
 
9
,

 
 
4
9
,

 
 
2
6
2
5
,

 
 
4
7
,

 
 
6
7
9
,

 
 
3
,

 
 
1
,

 
 
4
0
8
,

 
 
3
0
9
,

 
 
9
,

 
 
4
9
,

 
 
2
8
,

 
 
1
1
1
3
,

 
 
7
,

 
 
6
,

 
 
5
0
,

 
 
2
6
4
4
,

 
 
2
5
6
,

 
 
7
,

 
 
4
7
,

 
 
1
0
7
6
]
,

 
[
1
0
,

 
 
1
3
5
,

 
 
1
3
9
8
,

 
 
1
3
0
2
,

 
 
1
6
,

 
 
5
,

 
 
9
0
7
,

 
 
1
,

 
 
1
2
3
9
9
,

 
 
1
0
,

 
 
1
7
3
,

 
 
8
,

 
 
2
7
,

 
 
3
8
,

 
 
2
,

 
 
6
3
,

 
 
6
,

 
 
5
6
8
9
,

 
 
4
9
,

 
 
2
3
4
,

 
 
2
2
,

 
 
4
,

 
 
1
,

 
 
9
5
,

 
 
3
0
1
,

 
 
4
1
,

 
 
1
2
2
,

 
 
6
0
8
2
,

 
 
2
6
4
5
,

 
 
2
4
,

 
 
3
7
,

 
 
9
5
1
2
,

 
 
4
4
,

 
 
2
2
,

 
 
3
8
,

 
 
2
3
1
2
,

 
 
2
2
,

 
 
1
1
9
,

 
 
3
,

 
 
6
3
4
,

 
 
4
,

 
 
7
7
3
9
,

 
 
6
,

 
 
3
0
5
4
,

 
 
1
0
9
2
,

 
 
1
9
1
5
9
]
,

 
[
1
,

 
 
2
2
4
5
,

 
 
1
4
8
9
1
,

 
 
1
1
,

 
 
2
3
,

 
 
6
,

 
 
4
9
9
2
,

 
 
2
4
,

 
 
1
,

 
 
2
5
4
0
,

 
 
3
,

 
 
2
1
0
9
,

 
 
4
7
,

 
 
8
5
6
0
,

 
 
1
7
,

 
 
1
4
8
,

 
 
1
9
3
]
,

 
[
1
0
,

 
 
4
0
7
,

 
 
1
3
5
0
,

 
 
6
2
,

 
 
3
1
,

 
 
1
0
7
7
,

 
 
1
7
,

 
 
5
,

 
 
1
4
0
,

 
 
8
7
4
,

 
 
1
3
,

 
 
7
6
3
,

 
 
1
0
,

 
 
9
1
,

 
 
6
2
,

 
 
2
6
0
4
,

 
 
2
2
2
4
,

 
 
1
7
9
,

 
 
3
,

 
 
7
,

 
 
1
0
,

 
 
9
9
8
,

 
 
1
0
3
8
,

 
 
5
,

 
 
1
4
0
,

 
 
2
0
,

 
 
1
5
7
3
,

 
 
1
0
,

 
 
7
0
7
5
]
,

 
[
6
,

 
 
4
5
3
,

 
 
1
8
1
0
,

 
 
1
3
9
,

 
 
5
2
,

 
 
5
8
8
,

 
 
1
6
,

 
 
1
,

 
 
2
9
3
,

 
 
8
,

 
 
6
8
,

 
 
3
2
7
3
,

 
 
3
,

 
 
1
0
0
,

 
 
5
,

 
 
3
7
9
,

 
 
1
8
0
5
,

 
 
2
7
,

 
 
1
,

 
 
1
1
6
0
,

 
 
2
,

 
 
1
,

 
 
2
0
2
1
,

 
 
1
,

 
 
5
6
9
0
,

 
 
1
0
3
2
,

 
 
1
6
2
,

 
 
6
5
2
4
,

 
 
5
7
,

 
 
1
0
7
6
8
,

 
 
3
,

 
 
4
0
,

 
 
1
5
9
4
,

 
 
8
7
,

 
 
1
,

 
 
3
0
9
]
,

 
[
1
9
0
,

 
 
8
2
,

 
 
1
,

 
 
9
7
0
,

 
 
2
,

 
 
1
,

 
 
3
5
3
7
,

 
 
6
,

 
 
2
7
1
7
,

 
 
2
,

 
 
1
4
8
9
2
,

 
 
9
2
,

 
 
5
1
,

 
 
3
5
8
,

 
 
6
5
2
5
,

 
 
1
2
4
0
0
,

 
 
3
2
7
4
,

 
 
3
,

 
 
3
3
8
8
,

 
 
1
3
6
,

 
 
7
2
2
,

 
 
9
5
1
3
,

 
 
4
5
8
,

 
 
7
,

 
 
1
,

 
 
2
2
8
2
,

 
 
2
,

 
 
1
,

 
 
2
3
8
,

 
 
7
1
,

 
 
3
,

 
 
6
2
1
,

 
 
4
4
7
,

 
 
4
,

 
 
1
,

 
 
2
6
4
6
,

 
 
6
8
,

 
 
3
0
5
5
,

 
 
3
,

 
 
1
1
5
4
,

 
 
1
2
6
7
,

 
 
1
,

 
 
4
3
5
,

 
 
1
6
,

 
 
6
0
,

 
 
7
,

 
 
1
0
2
,

 
 
2
2
8
0
]
,

 
[
1
,

 
 
6
9
3
,

 
 
2
,

 
 
1
,

 
 
9
5
1
4
,

 
 
1
0
7
6
9
,

 
 
2
2
,

 
 
3
,

 
 
1
9
1
6
0
,

 
 
1
0
,

 
 
1
7
3
,

 
 
1
3
,

 
 
4
9
5
,

 
 
2
8
4
,

 
 
5
9
,

 
 
2
8
2
9
,

 
 
1
0
,

 
 
9
5
1
5
,

 
 
5
3
3
3
,

 
 
5
,

 
 
5
3
9
,

 
 
1
1
,

 
 
4
0
,

 
 
1
6
,

 
 
4
,

 
 
1
4
5
7
,

 
 
4
7
,

 
 
1
3
1
5
,

 
 
5
0
,

 
 
6
4
3
,

 
 
4
4
,

 
 
1
,

 
 
6
2
5
]
,

 
[
8
1
3
,

 
 
1
0
7
7
0
,

 
 
2
2
2
0
,

 
 
1
2
3
,

 
 
1
3
9
9
,

 
 
2
6
,

 
 
4
7
9
,

 
 
3
1
0
4
,

 
 
7
,

 
 
1
0
,

 
 
4
4
8
,

 
 
5
3
,

 
 
5
,

 
 
1
2
,

 
 
6
9
,

 
 
7
0
3
,

 
 
1
,

 
 
4
6
8
6
,

 
 
2
,

 
 
1
,

 
 
1
2
2
4
,

 
 
5
,

 
 
6
2
,

 
 
2
8
,

 
 
1
3
,

 
 
3
3
,

 
 
2
7
,

 
 
7
8
,

 
 
7
0
7
6
,

 
 
1
0
3
,

 
 
8
9
,

 
 
8
,

 
 
1
0
,

 
 
2
2
8
5
,

 
 
3
,

 
 
2
7
,

 
 
9
,

 
 
1
0
3
,

 
 
4
9
,

 
 
1
,

 
 
1
7
1
3
,

 
 
3
2
7
5
,

 
 
1
0
1
,

 
 
6
3
1
,

 
 
4
,

 
 
1
6
7
8
,

 
 
2
2
,

 
 
3
,

 
 
2
6
2
5
,

 
 
2
2
,

 
 
2
4
,

 
 
1
,

 
 
1
8
6
1
,

 
 
2
,

 
 
4
0
4
,

 
 
1
9
,

 
 
1
4
2
9
,

 
 
1
3
5
1
,

 
 
4
,

 
 
3
8
6
9
,

 
 
1
0
,

 
 
2
9
2
1
]
,

 
[
1
4
,

 
 
8
0
,

 
 
3
1
,

 
 
1
1
9
1
,

 
 
1
8
,

 
 
5
,

 
 
7
3
,

 
 
2
0
,

 
 
4
2
2
,

 
 
3
8
,

 
 
1
7
3
,

 
 
8
,

 
 
1
5
0
3
,

 
 
7
4
,

 
 
2
1
7
9
,

 
 
4
,

 
 
8
5
6
1
,

 
 
2
2
,

 
 
1
8
,

 
 
5
,

 
 
1
1
4
1
,

 
 
3
,

 
 
1
1
8
7
,

 
 
8
5
6
2
]
,

 
[
3
0
,

 
 
2
3
5
,

 
 
8
,

 
 
8
7
8
,

 
 
5
7
6
,

 
 
6
6
3
,

 
 
3
,

 
 
2
2
2
,

 
 
3
,

 
 
1
,

 
 
1
7
7
,

 
 
3
1
5
9
,

 
 
3
5
,

 
 
2
8
4
,

 
 
8
8
7
,

 
 
2
,

 
 
3
1
5
9
,

 
 
2
2
1
2
,

 
 
2
2
9
,

 
 
4
,

 
 
3
0
,

 
 
3
9
9
,

 
 
1
9
,

 
 
5
,

 
 
6
9
,

 
 
7
7
2
,

 
 
7
,

 
 
1
,

 
 
3
8
6
,

 
 
2
,

 
 
1
,

 
 
4
9
9
3
,

 
 
9
,

 
 
2
5
,

 
 
4
,

 
 
1
2
5
,

 
 
6
4
,

 
 
3
8
,

 
 
3
3
8
9
,

 
 
2
,

 
 
3
0
,

 
 
2
3
5
,

 
 
8
,

 
 
8
8
1
,

 
 
1
5
2
4
,

 
 
4
,

 
 
8
4
3
,

 
 
6
,

 
 
2
4
7
4
,

 
 
1
9
1
6
1
,

 
 
1
5
3
,

 
 
1
,

 
 
1
9
0
6
,

 
 
4
7
2
9
,

 
 
4
0
0
,

 
 
4
8
2
,

 
 
9
,

 
 
1
,

 
 
1
7
7
,

 
 
2
5
4
9
,

 
 
8
0
,

 
 
3
1
,

 
 
1
7
2
2
,

 
 
4
,

 
 
1
8
6
,

 
 
9
8
1
,

 
 
3
0
4
,

 
 
2
,

 
 
1
,

 
 
6
2
9
,

 
 
1
0
1
,

 
 
3
8
,

 
 
2
,

 
 
2
3
0
,

 
 
9
8
,

 
 
4
,

 
 
1
8
0
2
,

 
 
6
,

 
 
1
9
1
6
2
,

 
 
2
,

 
 
5
4
,

 
 
1
0
2
7
,

 
 
4
9
1
,

 
 
2
,

 
 
6
5
2
6
]
,

 
[
3
,

 
 
1
,

 
 
1
2
1
8
,

 
 
9
9
,

 
 
2
,

 
 
4
9
9
4
,

 
 
3
2
4
,

 
 
5
6
9
1
,

 
 
2
1
,

 
 
1
0
,

 
 
1
6
3
,

 
 
3
,

 
 
4
8
,

 
 
6
5
2
7
,

 
 
1
6
,

 
 
6
0
,

 
 
6
,

 
 
2
2
4
6
,

 
 
3
3
7
5
,

 
 
1
2
,

 
 
4
3
,

 
 
3
1
0
,

 
 
2
4
,

 
 
3
0
,

 
 
1
8
1
1
,

 
 
3
,

 
 
4
8
,

 
 
1
5
4
3
,

 
 
3
,

 
 
6
1
,

 
 
2
3
1
3
,

 
 
1
2
6
1
,

 
 
1
8
,

 
 
4
8
,

 
 
9
2
,

 
 
1
0
7
7
1
,

 
 
2
,

 
 
1
,

 
 
4
0
0
3
,

 
 
1
7
,

 
 
5
3
,

 
 
8
,

 
 
4
8
,

 
 
1
8
,

 
 
6
,

 
 
4
3
0
]
,

 
[
5
,
 
2
7
6
,
 
2
1
3
6
,
 
1
1
0
]
,

 
[
7
7
4
0
,

 
 
8
,

 
 
2
5
5
0
,

 
 
1
7
8
,

 
 
5
7
7
,

 
 
1
4
5
,

 
 
1
,

 
 
1
7
7
,

 
 
7
0
7
7
,

 
 
6
5
2
8
,

 
 
1
9
,

 
 
2
0
1
2
,

 
 
2
2
,

 
 
4
0
,

 
 
5
,

 
 
4
9
9
5
,

 
 
6
0
8
3
,

 
 
1
7
,

 
 
1
,

 
 
4
0
2
,

 
 
8
5
2
,

 
 
1
9
4
,

 
 
7
5
,

 
 
1
4
,

 
 
8
,

 
 
1
2
4
0
1
]
,

 
[
5
,

 
 
2
4
2
8
,

 
 
1
3
9
,

 
 
4
,

 
 
1
9
1
6
3
,

 
 
6
3
,

 
 
2
3
,

 
 
4
7
3
0
,

 
 
2
,

 
 
9
5
1
3
,

 
 
2
,

 
 
3
2
,

 
 
9
5
1
6
,

 
 
7
,

 
 
2
2
2
,

 
 
1
6
,

 
 
1
9
0
,

 
 
1
6
,

 
 
5
,

 
 
4
6
,

 
 
6
5
9
,

 
 
1
,

 
 
2
7
9
,

 
 
6
3
0
,

 
 
4
,

 
 
6
,

 
 
4
9
4
1
]
,

 
[
5
4
,
 
5
8
,
 
1
8
2
,
 
3
9
,
 
9
4
,
 
2
0
,
 
1
5
0
4
,
 
9
,
 
1
4
,
 
1
2
9
,
 
1
2
4
2
]
,

 
[
1
1
,

 
 
8
,

 
 
2
1
0
5
,

 
 
4
,

 
 
6
0
8
4
,

 
 
5
1
3
,

 
 
5
9
,

 
 
4
,

 
 
8
5
6
3
,

 
 
5
6
2
,

 
 
5
4
,

 
 
2
,

 
 
1
,

 
 
2
8
3
0
,

 
 
7
7
4
1
,

 
 
1
5
3
,

 
 
1
2
7
,

 
 
1
9
1
6
4
,

 
 
2
7
,

 
 
1
,

 
 
3
0
1
,

 
 
2
,

 
 
1
,

 
 
6
0
4
,

 
 
6
0
8
5
]
,

 
[
1
,
 
2
8
3
1
,
 
1
5
9
,
 
4
6
,
 
2
3
4
,
 
4
4
2
,
 
2
,
 
2
2
9
]
,

 
[
1
,

 
 
1
2
4
0
2
,

 
 
2
,

 
 
2
4
2
9
,

 
 
1
2
,

 
 
9
2
,

 
 
5
,

 
 
8
4
,

 
 
1
6
8
9
,

 
 
6
,

 
 
6
1
,

 
 
2
8
1
9
,

 
 
1
6
4
8
,

 
 
7
,

 
 
1
,

 
 
3
5
8
,

 
 
2
,

 
 
1
,

 
 
1
0
3
6
,

 
 
7
1
]
,

 
[
6
5
,

 
 
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
7
3
,

 
 
2
2
8
6
,

 
 
3
2
6
,

 
 
1
4
,

 
 
1
2
,

 
 
9
6
,

 
 
9
7
,

 
 
5
8
,

 
 
1
2
1
,

 
 
3
,

 
 
1
4
5
,

 
 
7
5
,

 
 
1
6
,

 
 
1
4
,

 
 
1
5
7
,

 
 
1
,

 
 
3
2
8
,

 
 
8
,

 
 
2
0
,

 
 
3
7
,

 
 
7
7
4
2
,

 
 
1
6
,

 
 
8
4
9
,

 
 
1
6
,

 
 
3
0
1
9
]
,

 
[
6
5
,
 
7
,
 
3
5
4
0
,
 
4
,
 
9
4
,
 
1
0
1
1
,
 
4
,
 
1
0
,
 
1
1
1
,
 
1
4
4
9
,
 
5
,
 
9
2
,
 
3
2
,
 
1
7
2
3
,
 
5
9
,
 
6
9
]
,

 
[
1
5
,
 
1
6
4
6
,
 
1
9
1
6
5
,
 
7
6
7
1
,
 
1
,
 
8
8
5
,
 
2
,
 
1
5
,
 
7
7
4
3
]
,

 
[
1
,
 
2
1
8
,
 
1
4
5
0
,
 
1
6
6
7
,
 
5
6
9
2
,
 
5
6
9
3
,
 
8
1
4
,
 
6
4
,
 
1
2
2
,
 
7
7
4
4
]
,

 
[
4
7
3
1
,

 
 
2
5
,

 
 
3
6
,

 
 
5
0
,

 
 
3
1
6
0
,

 
 
3
,

 
 
1
2
4
3
,

 
 
3
,

 
 
1
5
2
,

 
 
5
6
,

 
 
1
6
3
,

 
 
3
2
7
6
,

 
 
2
,

 
 
1
0
2
1
,

 
 
7
5
,

 
 
1
6
,

 
 
1
,

 
 
3
5
4
1
,

 
 
9
,

 
 
1
9
1
6
6
,

 
 
7
,

 
 
1
,

 
 
1
1
3
4
,

 
 
9
4
,

 
 
6
2
4
,

 
 
6
5
3
,

 
 
6
9
0
,

 
 
3
8
,

 
 
1
1
0
8
,

 
 
1
1
9
,

 
 
2
1
,

 
 
4
2
5
,

 
 
2
0
2
2
,

 
 
8
5
6
4
,

 
 
2
,

 
 
1
,

 
 
3
8
7
,

 
 
2
6
2
7
,

 
 
2
,

 
 
1
,

 
 
7
5
9
,

 
 
1
7
,

 
 
2
4
,

 
 
8
9
,

 
 
3
1
2
3
,

 
 
2
0
6
9
,

 
 
2
0
6
,

 
 
8
4
8
7
,

 
 
6
2
4
,

 
 
2
5
1
,

 
 
1
7
,

 
 
2
1
3
0
,

 
 
4
9
0
,

 
 
1
4
8
9
3
,

 
 
1
3
,

 
 
4
7
,

 
 
1
1
1
,

 
 
2
7
0
5
,

 
 
1
0
1
,

 
 
8
2
7
,

 
 
3
,

 
 
1
2
1
]
,

 
[
2
5
2
,
 
1
8
0
4
,
 
4
1
0
,
 
7
0
7
8
,
 
7
4
,
 
3
,
 
1
9
1
6
7
]
,

 
[
1
8
,
 
7
,
 
3
0
6
,
 
2
6
,
 
2
5
,
 
6
,
 
2
6
3
,
 
2
,
 
6
0
8
6
,
 
1
6
2
0
]
,

 
[
3
8
,

 
 
4
6
8
0
,

 
 
3
0
5
6
,

 
 
9
8
,

 
 
4
,

 
 
7
6
7
2
,

 
 
6
,

 
 
3
8
5
,

 
 
2
1
1
5
,

 
 
5
3
3
4
,

 
 
2
,

 
 
7
6
7
5
,

 
 
5
1
3
,

 
 
1
3
,

 
 
1
4
8
9
4
,

 
 
8
1
,

 
 
7
0
7
9
,

 
 
2
,

 
 
1
,

 
 
1
9
1
6
8
,

 
 
4
7
3
2
,

 
 
1
9
1
6
9
,

 
 
3
4
5
,

 
 
8
8
,

 
 
8
5
6
5
,

 
 
9
,

 
 
1
4
8
9
5
,

 
 
1
,

 
 
3
7
7
]
,

 
[
1
,
 
3
6
9
1
,
 
8
,
 
4
9
9
6
,
 
1
1
6
,
 
4
4
6
]
,

 
[
5
,

 
 
4
8
4
,

 
 
1
8
2
,

 
 
1
8
3
,

 
 
9
3
6
6
,

 
 
5
2
5
,

 
 
1
0
,

 
 
9
3
2
,

 
 
8
,

 
 
3
2
4
8
,

 
 
3
3
9
0
,

 
 
3
5
,

 
 
1
7
0
1
,

 
 
1
8
,

 
 
8
,

 
 
8
2
0
,

 
 
4
,

 
 
1
6
7
5
,

 
 
2
7
,

 
 
1
9
1
7
0
,

 
 
3
,

 
 
3
7
1
2
,

 
 
2
1
,

 
 
7
0
,

 
 
4
2
5
1
]
,

 
[
4
2
,
 
5
6
,
 
1
0
6
2
,
 
4
,
 
1
,
 
1
5
9
]
,

 
[
4
8
,

 
 
8
,

 
 
2
9
6
,

 
 
1
9
7
6
,

 
 
1
4
8
,

 
 
1
5
8
8
,

 
 
5
9
,

 
 
1
4
,

 
 
3
,

 
 
8
,

 
 
1
,

 
 
2
7
9
8
,

 
 
2
,

 
 
6
,

 
 
6
0
4
,

 
 
1
6
4
1
,

 
 
2
,

 
 
1
5
,

 
 
2
1
1
]
,

 
[
5
,

 
 
3
2
4
,

 
 
2
9
3
1
,

 
 
5
5
0
,

 
 
3
,

 
 
1
9
9
4
,

 
 
4
,

 
 
5
6
5
,

 
 
1
1
0
,

 
 
1
8
2
7
,

 
 
2
8
0
,

 
 
1
,

 
 
4
4
6
6
,

 
 
2
,

 
 
1
,

 
 
9
0
5
,

 
 
1
4
8
9
6
]
,

 
[
5
8
9
,

 
 
7
4
3
,

 
 
4
2
5
2
,

 
 
1
,

 
 
1
9
1
7
,

 
 
3
,

 
 
1
7
0
8
,

 
 
1
5
3
7
,

 
 
2
,

 
 
1
1
6
9
,

 
 
5
8
,

 
 
3
9
9
5
,

 
 
7
,

 
 
3
0
,

 
 
1
7
3
1
,

 
 
1
4
1
,

 
 
5
9
9
7
,

 
 
9
,

 
 
1
4
,

 
 
7
3
,

 
 
2
0
,

 
 
4
2
2
,

 
 
2
,

 
 
1
,

 
 
8
4
1
,

 
 
2
,

 
 
1
,

 
 
2
2
5
,

 
 
2
,

 
 
1
5
,

 
 
1
7
0
8
,

 
 
2
5
0
,

 
 
1
,

 
 
4
0
2
,

 
 
2
8
1
,

 
 
4
1
,

 
 
5
8
9
,

 
 
3
3
9
1
,

 
 
1
1
7
,

 
 
5
7
,

 
 
1
5
,

 
 
4
6
4
,

 
 
3
,

 
 
2
2
8
,

 
 
3
9
,

 
 
2
,

 
 
1
1
]
,

 
[
5
,
 
1
5
5
8
,
 
1
0
7
7
2
,
 
1
5
7
,
 
6
5
2
9
,
 
1
,
 
8
1
6
,
 
4
,
 
2
9
1
6
]
,

 
[
4
1
,

 
 
1
5
,

 
 
1
9
1
7
1
,

 
 
2
9
,

 
 
8
7
,

 
 
5
,

 
 
2
1
6
,

 
 
2
1
,

 
 
1
,

 
 
5
8
2
,

 
 
3
,

 
 
4
,

 
 
3
5
5
,

 
 
1
,

 
 
3
6
3
,

 
 
9
6
,

 
 
1
1
0
,

 
 
2
0
,

 
 
6
,

 
 
1
0
4
,

 
 
2
6
2
2
,

 
 
2
1
,

 
 
5
3
,

 
 
1
0
,

 
 
1
9
2
,

 
 
1
2
,

 
 
8
5
6
6
]
,

 
[
1
0
0
,

 
 
8
9
,

 
 
1
2
4
0
3
,

 
 
2
9
,

 
 
7
4
1
,

 
 
2
7
,

 
 
5
1
,

 
 
4
9
4
,

 
 
1
0
3
2
,

 
 
9
0
7
,

 
 
1
4
8
1
,

 
 
2
4
2
6
,

 
 
7
,

 
 
6
5
1
,

 
 
2
3
7
1
,

 
 
3
,

 
 
2
,

 
 
6
,

 
 
5
0
,

 
 
2
0
2
3
,

 
 
2
3
5
8
]
,

 
[
4
2
,

 
 
4
9
2
1
,

 
 
2
0
5
,

 
 
2
1
,

 
 
8
3
,

 
 
2
3
,

 
 
8
5
7
,

 
 
3
,

 
 
1
2
4
0
4
,

 
 
6
5
,

 
 
7
,

 
 
2
4
2
6
,

 
 
8
5
6
7
,

 
 
2
5
0
,

 
 
8
5
6
8
,

 
 
2
3
,

 
 
1
,

 
 
2
9
3
2
,

 
 
1
6
5
,

 
 
1
4
8
9
7
,

 
 
5
4
0
,

 
 
1
,

 
 
7
0
8
,

 
 
9
,

 
 
4
1
9
,

 
 
4
,

 
 
7
7
4
5
]
,

 
[
1
,

 
 
2
6
4
7
,

 
 
3
9
7
9
,

 
 
2
3
,

 
 
7
0
,

 
 
6
0
2
,

 
 
7
0
8
0
,

 
 
1
9
1
7
2
,

 
 
2
5
,

 
 
5
0
,

 
 
5
9
,

 
 
7
0
8
1
,

 
 
5
0
5
,

 
 
7
6
,

 
 
4
5
,

 
 
2
5
,

 
 
3
6
,

 
 
1
4
8
9
8
,

 
 
2
,

 
 
6
0
8
7
,

 
 
3
5
,

 
 
7
8
5
,

 
 
1
9
1
7
3
]
,

 
[
5
,

 
 
1
3
3
,

 
 
1
3
0
9
,

 
 
9
,

 
 
5
,

 
 
3
1
,

 
 
4
9
7
,

 
 
3
,

 
 
3
1
,

 
 
1
2
4
1
,

 
 
7
0
8
2
,

 
 
4
9
0
,

 
 
3
,

 
 
6
2
8
,

 
 
1
3
,

 
 
1
0
,

 
 
4
3
7
,

 
 
7
9
2
]
,

 
[
1
,

 
 
3
7
3
,

 
 
2
9
,

 
 
1
9
1
7
4
,

 
 
1
2
4
0
5
,

 
 
3
3
6
4
,

 
 
1
2
1
8
,

 
 
3
2
5
2
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
6
4
9
,

 
 
5
3
8
,

 
 
3
,

 
 
3
1
6
1
,

 
 
1
3
,

 
 
3
5
4
2
,

 
 
4
0
5
3
,

 
 
6
9
4
3
,

 
 
3
,

 
 
1
0
7
7
3
,

 
 
3
0
5
7
]
,

 
[
5
1
0
,

 
 
1
9
6
,

 
 
2
1
7
3
,

 
 
8
,

 
 
1
,

 
 
3
8
7
0
,

 
 
1
9
,

 
 
1
3
1
,

 
 
6
0
8
8
,

 
 
5
4
,

 
 
9
8
1
,

 
 
5
8
,

 
 
1
9
1
7
5
,

 
 
7
,

 
 
1
,

 
 
5
3
3
5
,

 
 
5
3
1
1
,

 
 
1
9
3
,

 
 
4
,

 
 
5
3
,

 
 
4
0
1
,

 
 
6
0
2
3
,

 
 
5
6
,

 
 
1
,

 
 
1
6
6
0
,

 
 
2
,

 
 
1
,

 
 
2
7
2
6
,

 
 
2
4
6
,

 
 
1
3
2
,

 
 
2
7
2
,

 
 
1
7
2
2
,

 
 
1
0
8
,

 
 
7
7
4
6
,

 
 
8
5
,

 
 
5
4
,

 
 
1
0
7
5
,

 
 
3
5
,

 
 
4
0
5
4
,

 
 
4
9
9
7
,

 
 
9
5
1
7
,

 
 
8
2
,

 
 
2
6
,

 
 
1
0
6
8
,

 
 
1
2
4
0
6
,

 
 
3
8
7
1
,

 
 
4
,

 
 
1
2
3
5
,

 
 
1
,

 
 
1
2
4
0
7
,

 
 
7
6
6
,

 
 
2
,

 
 
1
0
7
7
4
,

 
 
7
7
4
7
,

 
 
1
3
9
3
,

 
 
1
3
9
3
,

 
 
1
3
9
3
,

 
 
1
3
9
3
,

 
 
5
3
1
1
,

 
 
1
9
3
,

 
 
4
0
4
3
,

 
 
1
4
,

 
 
2
5
,

 
 
2
5
,

 
 
1
0
7
7
5
,

 
 
2
5
5
1
,

 
 
9
,

 
 
4
5
,

 
 
2
5
,

 
 
2
0
,

 
 
6
,

 
 
1
9
1
7
6
,

 
 
1
2
7
7
,

 
 
7
,

 
 
5
5
,

 
 
1
5
4
4
,

 
 
5
8
,

 
 
2
5
,

 
 
2
0
,

 
 
7
,

 
 
1
,

 
 
1
2
8
2
,

 
 
1
9
9
8
,

 
 
2
,

 
 
8
5
6
9
,

 
 
3
3
4
,

 
 
1
3
4
4
]
,

 
[
1
4
,

 
 
8
,

 
 
1
0
8
0
,

 
 
2
0
6
,

 
 
3
,

 
 
1
5
,

 
 
8
3
,

 
 
8
2
7
,

 
 
8
,

 
 
4
,

 
 
1
0
6
4
,

 
 
4
,

 
 
1
,

 
 
6
0
8
9
,

 
 
3
,

 
 
2
5
9
,

 
 
7
6
2
2
,

 
 
1
1
9
,

 
 
2
1
,

 
 
1
,

 
 
2
5
9
3
,

 
 
4
2
5
3
,

 
 
2
2
7
,

 
 
2
0
9
,

 
 
1
2
2
,

 
 
3
5
0
,

 
 
2
7
0
,

 
 
5
2
9
]
,

 
[
5
,
 
2
3
3
,
 
6
6
,
 
4
,
 
3
0
,
 
3
,
 
1
6
6
9
,
 
1
0
,
 
3
9
7
3
]
,

 
[
9
7
,

 
 
5
8
,

 
 
1
2
,

 
 
9
5
1
8
,

 
 
2
2
6
,

 
 
9
5
1
8
,

 
 
1
1
,

 
 
3
6
,

 
 
3
3
3
,

 
 
7
6
,

 
 
7
3
,

 
 
2
1
3
,

 
 
3
,

 
 
2
1
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

 
 
1
0
6
,

 
 
8
5
7
0
,

 
 
8
7
,

 
 
1
,

 
 
2
6
5
,

 
 
1
7
,

 
 
1
1
3
,

 
 
1
2
,

 
 
4
6
5
9
,

 
 
4
2
8
,

 
 
3
,

 
 
1
1
3
,

 
 
2
4
6
4
,

 
 
1
2
,

 
 
1
6
4
,

 
 
2
4
,

 
 
5
5
1
,

 
 
8
3
8
,

 
 
4
,

 
 
1
,

 
 
3
0
0
,

 
 
5
2
4
]
,

 
[
2
6
,

 
 
5
,

 
 
6
2
0
,

 
 
1
3
,

 
 
7
0
8
3
,

 
 
1
0
7
7
6
,

 
 
1
0
9
4
,

 
 
1
,

 
 
3
0
6
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
0
,

 
 
9
5
,

 
 
8
8
5
,

 
 
2
9
,

 
 
1
7
9
2
,

 
 
7
0
8
4
]
,

 
[
1
4
,

 
 
1
3
3
3
,

 
 
9
,

 
 
1
,

 
 
2
7
4
0
,

 
 
9
,

 
 
5
,

 
 
1
2
3
6
,

 
 
1
1
9
,

 
 
2
9
,

 
 
1
,

 
 
4
2
0
,

 
 
1
8
,

 
 
1
4
,

 
 
3
8
6
0
,

 
 
9
,

 
 
4
2
,

 
 
2
9
,

 
 
1
,

 
 
6
4
,

 
 
8
5
7
]
,

 
[
4
2
,

 
 
2
9
,

 
 
3
3
9
2
,

 
 
4
2
,

 
 
2
9
,

 
 
1
2
4
0
8
,

 
 
4
0
8
,

 
 
1
8
,

 
 
7
4
,

 
 
2
,

 
 
4
0
7
,

 
 
6
3
4
,

 
 
1
8
9
,

 
 
1
7
,

 
 
5
1
,

 
 
6
1
,

 
 
1
7
6
4
,

 
 
2
0
5
6
,

 
 
7
,

 
 
1
0
,

 
 
2
4
1
,

 
 
3
7
,

 
 
3
2
3
0
,

 
 
9
5
1
9
]
,

 
[
3
,

 
 
4
1
,

 
 
7
2
,

 
 
1
4
0
,

 
 
3
1
,

 
 
2
7
3
1
,

 
 
7
8
,

 
 
3
8
0
,

 
 
1
8
4
,

 
 
3
,

 
 
3
6
8
,

 
 
7
1
7
,

 
 
2
,

 
 
4
4
2
,

 
 
6
2
,

 
 
2
8
,

 
 
6
7
5
,

 
 
4
,

 
 
1
2
4
0
9
,

 
 
9
7
,

 
 
2
,

 
 
2
3
0
,

 
 
3
4
,

 
 
3
1
,

 
 
4
3
,

 
 
4
0
,

 
 
7
0
8
5
,

 
 
2
4
1
1
]
,

 
[
1
2
0
,
 
4
6
,
 
5
,
 
3
1
,
 
1
7
4
3
,
 
1
,
 
1
4
6
,
 
5
,
 
8
,
 
4
,
 
7
8
9
]
,

 
[
3
8
,

 
 
2
,

 
 
6
7
,

 
 
6
0
6
7
,

 
 
8
5
7
1
,

 
 
9
,

 
 
1
2
9
,

 
 
1
2
4
1
0
,

 
 
2
7
,

 
 
4
7
3
3
,

 
 
9
4
7
,

 
 
2
5
,

 
 
6
8
,

 
 
4
,

 
 
2
8
,

 
 
5
9
3
,

 
 
8
5
7
2
,

 
 
4
,

 
 
1
8
4
1
]
,

 
[
5
,

 
 
1
1
9
8
,

 
 
9
,

 
 
5
,

 
 
7
3
,

 
 
2
0
,

 
 
6
0
5
,

 
 
1
1
,

 
 
1
6
,

 
 
6
,

 
 
5
9
9
,

 
 
4
2
5
4
,

 
 
1
5
3
,

 
 
5
,

 
 
1
2
,

 
 
6
,

 
 
5
9
9
,

 
 
4
2
5
4
,

 
 
7
,

 
 
2
1
0
,

 
 
9
7
3
]
,

 
[
3
8
,

 
 
2
,

 
 
1
,

 
 
8
6
,

 
 
2
4
8
8
,

 
 
1
9
0
9
,

 
 
2
,

 
 
1
9
1
9
,

 
 
1
9
,

 
 
3
4
,

 
 
3
1
,

 
 
1
7
0
,

 
 
2
5
,

 
 
1
,

 
 
6
5
3
0
,

 
 
3
5
3
1
,

 
 
2
3
,

 
 
5
8
9
,

 
 
1
4
8
9
9
,

 
 
1
7
,

 
 
1
,

 
 
5
0
0
,

 
 
2
,

 
 
8
5
7
3
,

 
 
2
1
2
,

 
 
3
9
0
,

 
 
1
5
2
6
]
,

 
[
1
4
,

 
 
8
,

 
 
6
,

 
 
1
7
6
,

 
 
3
1
3
1
,

 
 
6
9
5
,

 
 
5
8
,

 
 
2
7
8
8
,

 
 
2
1
6
,

 
 
8
7
,

 
 
1
5
,

 
 
1
7
6
5
,

 
 
1
6
,

 
 
6
0
,

 
 
1
7
6
1
,

 
 
2
,

 
 
2
2
6
,

 
 
3
,

 
 
4
1
,

 
 
2
8
3
2
,

 
 
4
6
,

 
 
2
0
,

 
 
2
8
,

 
 
2
7
8
7
,

 
 
4
,

 
 
8
9
4
,

 
 
2
1
,

 
 
3
2
,

 
 
1
3
,

 
 
2
4
6
4
]
,

 
[
1
9
1
7
7
,
 
3
3
0
,
 
1
9
2
0
,
 
1
9
1
7
8
]
,

 
[
5
,

 
 
7
3
,

 
 
2
0
,

 
 
1
6
9
8
,

 
 
1
1
,

 
 
3
6
1
,

 
 
1
7
,

 
 
5
,

 
 
1
2
1
,

 
 
5
,

 
 
8
,

 
 
1
6
0
6
,

 
 
1
9
1
7
9
,

 
 
2
8
3
3
,

 
 
5
3
,

 
 
1
,

 
 
8
5
7
4
,

 
 
4
9
,

 
 
6
0
1
,

 
 
7
4
,

 
 
4
,

 
 
2
8
]
,

 
[
1
4
,
 
8
,
 
5
6
1
4
,
 
1
9
7
,
 
2
3
1
,
 
3
3
3
,
 
3
,
 
6
5
,
 
1
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
]
,

 
[
3
,
 
2
3
9
,
 
9
3
,
 
5
,
 
9
7
1
,
 
6
,
 
6
2
8
,
 
1
9
,
 
3
2
,
 
3
1
,
 
1
4
5
,
 
3
,
 
8
4
,
 
2
9
7
]
,

 
[
1
8
,
 
5
,
 
1
1
3
5
,
 
4
1
,
 
5
,
 
1
1
1
3
,
 
2
7
,
 
1
,
 
6
7
8
,
 
9
,
 
5
,
 
1
2
,
 
4
,
 
2
7
8
]
,

 
[
2
3
4
4
,

 
 
7
0
8
6
,

 
 
3
1
0
6
,

 
 
2
7
,

 
 
1
,

 
 
6
5
3
1
,

 
 
2
,

 
 
1
4
9
0
0
,

 
 
7
7
9
,

 
 
1
,

 
 
4
9
9
8
,

 
 
1
2
4
1
1
,

 
 
3
,

 
 
5
5
8
1
,

 
 
1
0
1
,

 
 
1
2
4
,

 
 
3
,

 
 
4
5
,

 
 
1
4
9
0
1
,

 
 
4
7
5
,

 
 
2
4
,

 
 
1
6
9
,

 
 
1
,

 
 
3
7
3
,

 
 
4
9
2
,

 
 
6
,

 
 
3
0
9
,

 
 
2
,

 
 
5
6
6
,

 
 
3
1
6
]
,

 
[
5
,

 
 
7
3
,

 
 
2
0
,

 
 
1
9
4
2
,

 
 
1
8
,

 
 
5
,

 
 
6
0
9
0
,

 
 
1
,

 
 
6
5
3
2
,

 
 
2
4
,

 
 
1
0
,

 
 
1
1
6
0
,

 
 
3
,

 
 
5
9
5
,

 
 
4
,

 
 
1
0
6
,

 
 
1
0
,

 
 
8
1
6
,

 
 
3
,

 
 
1
3
5
,

 
 
2
4
8
9
,

 
 
2
0
9
,

 
 
4
,

 
 
7
0
5
]
,

 
[
1
,

 
 
5
2
8
,

 
 
2
9
,

 
 
1
1
3
,

 
 
3
,

 
 
4
1
9
,

 
 
4
,

 
 
6
,

 
 
6
4
2
,

 
 
3
7
8
,

 
 
1
2
4
1
2
,

 
 
7
4
7
,

 
 
1
9
,

 
 
5
,

 
 
1
8
2
,

 
 
8
4
,

 
 
2
8
,

 
 
1
3
7
,

 
 
4
7
3
4
]
,

 
[
5
,

 
 
1
2
,

 
 
3
3
7
,

 
 
1
2
5
7
,

 
 
2
0
,

 
 
4
,

 
 
4
2
0
2
,

 
 
1
,

 
 
2
4
7
2
,

 
 
1
7
,

 
 
1
,

 
 
3
1
6
2
,

 
 
2
1
3
,

 
 
1
7
,

 
 
7
,

 
 
1
0
,

 
 
5
3
2
3
,

 
 
2
0
6
9
,

 
 
1
1
,

 
 
9
8
,

 
 
4
,

 
 
2
2
,

 
 
9
,

 
 
7
7
4
8
,

 
 
8
,

 
 
1
7
2
3
,

 
 
5
9
,

 
 
1
2
4
1
3
,

 
 
1
3
9
,

 
 
3
3
5
,

 
 
1
,

 
 
4
5
4
,

 
 
8
0
,

 
 
1
3
4
3
,

 
 
4
,

 
 
2
8
]
,

 
[
1
1
,

 
 
1
2
,

 
 
2
9
0
,

 
 
7
,

 
 
6
,

 
 
1
0
2
,

 
 
1
2
4
4
,

 
 
1
,

 
 
2
6
2
,

 
 
4
9
9
9
,

 
 
2
,

 
 
7
0
4
,

 
 
1
1
,

 
 
1
2
,

 
 
1
0
8
4
,

 
 
1
6
6
7
,

 
 
1
2
7
,

 
 
5
2
,

 
 
2
,

 
 
6
,

 
 
1
9
1
8
0
,

 
 
3
4
4
,

 
 
3
,

 
 
2
,

 
 
6
,

 
 
2
3
5
8
,

 
 
3
1
6
3
,

 
 
4
,

 
 
1
,

 
 
3
1
1
]
,

 
[
1
8
,

 
 
5
2
,

 
 
5
,

 
 
2
3
3
,

 
 
4
,

 
 
1
1
,

 
 
7
,

 
 
4
1
6
,

 
 
4
2
7
,

 
 
3
,

 
 
1
0
,

 
 
1
3
5
,

 
 
2
7
2
,

 
 
4
0
5
5
,

 
 
2
1
,

 
 
1
,

 
 
3
4
0
,

 
 
2
,

 
 
1
0
,

 
 
3
2
1
]
,

 
[
1
,
 
1
7
1
,
 
9
8
0
,
 
5
,
 
1
1
,
 
6
2
,
 
2
8
,
 
8
2
1
,
 
2
5
,
 
1
0
6
,
 
2
4
8
]
,

 
[
3
4
,
 
4
0
5
6
,
 
6
,
 
6
0
3
8
,
 
1
2
4
,
 
3
,
 
1
3
,
 
4
3
2
,
 
1
8
1
2
,
 
2
5
2
9
,
 
1
3
,
 
2
3
1
4
,
 
8
8
,
 
1
,
 
9
4
0
]
,

 
[
4
6
0
,
 
1
4
9
0
2
,
 
8
5
7
5
,
 
1
3
,
 
6
,
 
4
0
8
,
 
1
5
9
,
 
7
,
 
1
9
,
 
3
4
,
 
5
6
,
 
1
0
7
7
7
,
 
3
4
8
3
]
,

 
[
2
,
 
1
,
 
5
4
5
,
 
1
0
8
1
,
 
9
,
 
2
,
 
1
2
5
2
,
 
1
4
9
0
3
,
 
1
,
 
3
7
5
,
 
1
9
1
8
1
,
 
2
5
,
 
8
6
,
 
4
1
8
5
,
 
3
,
 
8
5
7
6
]
,

 
[
1
1
,

 
 
8
,

 
 
2
1
,

 
 
3
2
7
7
,

 
 
1
9
5
,

 
 
1
,

 
 
1
0
7
7
8
,

 
 
2
,

 
 
9
,

 
 
5
,

 
 
1
1
8
6
,

 
 
6
,

 
 
9
5
2
0
,

 
 
7
,

 
 
1
,

 
 
9
5
2
1
,

 
 
2
,

 
 
1
,

 
 
1
4
9
0
4
,

 
 
3
8
7
2
,

 
 
8
5
7
7
,

 
 
1
4
9
0
5
]
,

 
[
1
3
1
,
 
3
4
,
 
9
5
0
,
 
2
,
 
6
3
,
 
3
,
 
1
9
1
8
2
,
 
1
6
,
 
1
3
,
 
2
3
7
5
,
 
1
9
9
3
,
 
3
4
,
 
4
4
7
,
 
4
,
 
7
5
4
,
 
8
0
5
]
,

 
[
3
,

 
 
1
1
,

 
 
8
,

 
 
1
,

 
 
3
6
4
4
,

 
 
6
6
5
,

 
 
2
,

 
 
1
,

 
 
6
0
9
1
,

 
 
4
9
6
,

 
 
9
,

 
 
6
8
1
,

 
 
3
9
,

 
 
4
,

 
 
2
9
7
,

 
 
1
9
4
,

 
 
1
4
,

 
 
4
8
4
,

 
 
1
0
7
,

 
 
1
8
3
,

 
 
1
4
3
,

 
 
4
,

 
 
2
9
7
,

 
 
1
,

 
 
5
6
1
,

 
 
2
,

 
 
1
0
,

 
 
1
6
7
,

 
 
1
6
1
,

 
 
1
,

 
 
1
7
4
]
,

 
[
6
,

 
 
1
2
1
8
,

 
 
1
5
8
,

 
 
6
5
,

 
 
1
0
7
7
9
,

 
 
1
,

 
 
3
3
7
0
,

 
 
3
,

 
 
1
,

 
 
2
2
5
,

 
 
2
,

 
 
1
,

 
 
7
1
,

 
 
4
9
,

 
 
2
8
,

 
 
4
4
5
,

 
 
6
0
,

 
 
1
1
,

 
 
2
9
,

 
 
4
5
]
,

 
[
8
8
,

 
 
4
4
8
4
,

 
 
2
4
,

 
 
1
,

 
 
2
0
2
4
,

 
 
2
,

 
 
1
,

 
 
9
5
2
2
,

 
 
4
,

 
 
1
,

 
 
2
4
8
2
,

 
 
2
,

 
 
1
,

 
 
1
9
1
8
3
,

 
 
2
4
,

 
 
1
,

 
 
1
9
1
8
4
,

 
 
7
5
,

 
 
4
,

 
 
1
,

 
 
2
0
4
,

 
 
2
,

 
 
1
9
1
8
5
,

 
 
6
,

 
 
9
3
0
,

 
 
2
4
9
0
,

 
 
8
,

 
 
1
7
0
9
]
,

 
[
1
1
,

 
 
8
,

 
 
2
0
,

 
 
6
,

 
 
5
0
0
0
,

 
 
1
8
9
5
,

 
 
8
2
,

 
 
2
1
5
,

 
 
3
,

 
 
5
,

 
 
3
2
6
,

 
 
5
,

 
 
4
9
,

 
 
3
1
,

 
 
1
0
4
3
,

 
 
4
7
,

 
 
6
0
9
2
,

 
 
7
5
,

 
 
1
2
,

 
 
5
,

 
 
4
3
,

 
 
1
8
9
1
,

 
 
2
,

 
 
1
,

 
 
4
6
1
,

 
 
9
,

 
 
5
0
0
1
,

 
 
4
5
]
,

 
[
5
,

 
 
2
6
7
,

 
 
1
8
2
,

 
 
3
3
,

 
 
2
9
,

 
 
3
6
,

 
 
7
6
9
4
,

 
 
1
4
3
1
,

 
 
2
9
3
3
,

 
 
1
4
3
1
,

 
 
1
3
,

 
 
1
0
4
8
,

 
 
4
,

 
 
1
2
6
,

 
 
1
,

 
 
1
6
1
9
,

 
 
1
4
2
,

 
 
5
,

 
 
3
1
,

 
 
4
4
5
]
,

 
[
9
3
,

 
 
5
,

 
 
2
3
1
5
,

 
 
4
,

 
 
7
8
,

 
 
6
0
9
3
,

 
 
3
,

 
 
5
,

 
 
1
2
3
,

 
 
2
4
0
9
,

 
 
4
,

 
 
1
,

 
 
1
4
9
0
6
,

 
 
2
,

 
 
1
0
,

 
 
1
1
1
,

 
 
1
0
0
0
,

 
 
4
9
,

 
 
5
,

 
 
2
0
,

 
 
2
8
,

 
 
3
8
7
3
,

 
 
4
,

 
 
2
3
0
4
,

 
 
2
,

 
 
3
3
,

 
 
6
,

 
 
6
1
,

 
 
6
,

 
 
6
1
,

 
 
1
0
4
,

 
 
6
5
1
0
,

 
 
7
,

 
 
3
0
3
]
,

 
[
5
,

 
 
7
3
,

 
 
2
0
,

 
 
1
0
8
0
,

 
 
1
9
1
8
6
,

 
 
1
3
,

 
 
3
9
,

 
 
1
4
9
0
7
,

 
 
7
6
,

 
 
4
2
3
,

 
 
7
3
6
,

 
 
6
5
3
3
,

 
 
5
6
9
4
,

 
 
2
,

 
 
1
,

 
 
3
3
9
3
,

 
 
2
1
2
2
,

 
 
2
,

 
 
1
0
,

 
 
5
3
3
6
,

 
 
4
0
,

 
 
9
,

 
 
5
,

 
 
4
6
,

 
 
2
0
,

 
 
6
8
6
,

 
 
7
7
4
9
,

 
 
1
,

 
 
5
5
4
,

 
 
1
3
,

 
 
6
,

 
 
2
1
2
,

 
 
2
0
2
5
,

 
 
2
,

 
 
1
8
1
3
,

 
 
3
,

 
 
3
3
5
,

 
 
1
5
4
1
]
,

 
[
4
4
4
,
 
1
,
 
8
6
,
 
2
7
4
1
,
 
5
5
3
,
 
6
5
0
,
 
3
,
 
1
9
2
,
 
8
,
 
6
,
 
2
7
4
2
,
 
3
,
 
4
0
5
7
,
 
3
8
2
]
,

 
[
6
5
,
 
3
2
,
 
6
8
2
,
 
2
,
 
7
5
8
,
 
1
7
2
,
 
1
0
7
8
0
]
,

 
[
1
,
 
4
0
2
,
 
1
0
3
,
 
1
3
6
,
 
3
7
1
3
,
 
4
,
 
1
0
1
5
,
 
1
7
,
 
1
,
 
4
0
5
8
,
 
1
4
,
 
1
4
9
0
8
,
 
1
1
]
,

 
[
1
8
,

 
 
1
0
,

 
 
3
6
8
,

 
 
2
9
3
4
,

 
 
3
3
1
,

 
 
1
4
,

 
 
8
5
7
8
,

 
 
4
4
9
,

 
 
3
,

 
 
2
7
4
3
,

 
 
2
2
2
,

 
 
7
,

 
 
1
0
,

 
 
2
3
5
,

 
 
5
,

 
 
7
3
,

 
 
2
0
,

 
 
6
9
,

 
 
2
5
4
9
,

 
 
1
2
0
,

 
 
6
1
,

 
 
5
1
5
,

 
 
3
3
,

 
 
6
8
5
,

 
 
4
0
,

 
 
1
0
0
9
,

 
 
3
,

 
 
6
2
3
,

 
 
3
3
,

 
 
2
5
9
,

 
 
1
6
,

 
 
6
0
,

 
 
3
3
,

 
 
1
2
,

 
 
4
3
,

 
 
1
3
6
3
,

 
 
1
7
,

 
 
3
2
2
,

 
 
1
9
4
6
]
,

 
[
1
4
,
 
2
4
9
1
,
 
1
2
8
,
 
1
2
8
,
 
6
4
]
,

 
[
4
8
,

 
 
8
3
,

 
 
9
7
2
,

 
 
3
9
,

 
 
2
,

 
 
3
0
,

 
 
5
0
0
2
,

 
 
1
4
9
3
,

 
 
2
,

 
 
2
6
,

 
 
1
4
,

 
 
8
4
,

 
 
2
8
,

 
 
1
9
9
6
,

 
 
2
0
1
,

 
 
1
8
,

 
 
1
7
,

 
 
9
,

 
 
4
8
,

 
 
4
9
,

 
 
2
0
,

 
 
6
7
1
,

 
 
4
,

 
 
8
5
6
1
,

 
 
3
9
]
,

 
[
2
9
5
,
 
1
3
6
8
,
 
5
3
3
7
,
 
7
7
5
0
,
 
4
7
3
5
,
 
4
9
6
,
 
8
1
,
 
6
9
,
 
2
2
]
,

 
[
4
4
,
 
2
1
2
3
,
 
5
,
 
2
2
7
6
,
 
3
9
,
 
5
3
3
8
,
 
2
4
,
 
2
2
]
,

 
[
1
,

 
 
4
4
8
5
,

 
 
8
,

 
 
5
4
2
,

 
 
7
6
,

 
 
9
8
,

 
 
4
,

 
 
3
8
1
1
,

 
 
6
,

 
 
8
3
3
,

 
 
1
7
8
0
,

 
 
2
,

 
 
1
9
1
8
7
,

 
 
6
,

 
 
1
7
8
0
,

 
 
1
9
,

 
 
5
,

 
 
4
4
8
6
,

 
 
1
,

 
 
5
0
,

 
 
2
7
5
,

 
 
1
,

 
 
4
4
8
5
,

 
 
8
,

 
 
5
4
2
]
,

 
[
8
1
9
,

 
 
1
,

 
 
8
5
7
9
,

 
 
1
9
,

 
 
2
9
,

 
 
1
4
9
0
9
,

 
 
1
2
,

 
 
1
0
9
,

 
 
5
2
1
5
,

 
 
6
,

 
 
4
0
5
9
,

 
 
6
6
5
,

 
 
7
,

 
 
1
,

 
 
2
3
4
7
,

 
 
2
,

 
 
6
,

 
 
1
5
1
2
,

 
 
1
8
6
2
]
,

 
[
4
8
,

 
 
1
2
,

 
 
4
3
,

 
 
7
,

 
 
1
5
,

 
 
3
2
7
5
,

 
 
6
8
,

 
 
6
,

 
 
4
7
1
,

 
 
4
1
,

 
 
3
0
,

 
 
1
0
7
8
1
,

 
 
2
9
,

 
 
6
1
0
,

 
 
1
9
1
8
8
,

 
 
1
9
7
7
,

 
 
2
3
,

 
 
3
0
,

 
 
9
3
0
,

 
 
2
8
3
4
,

 
 
2
4
,

 
 
1
,

 
 
2
9
3
5
]
,

 
[
1
4
,

 
 
1
2
,

 
 
5
7
7
,

 
 
4
3
,

 
 
9
5
2
3
,

 
 
1
7
,

 
 
4
5
,

 
 
8
,

 
 
3
6
,

 
 
1
9
3
6
,

 
 
2
,

 
 
7
0
,

 
 
1
0
1
1
,

 
 
7
4
5
,

 
 
1
,

 
 
2
5
3
,

 
 
1
5
3
2
,

 
 
2
,

 
 
1
6
0
5
,

 
 
2
7
,

 
 
1
5
,

 
 
1
2
1
2
]
,

 
[
8
,
 
9
,
 
6
,
 
2
1
6
4
,
 
5
,
 
1
0
7
,
 
1
4
9
1
0
,
 
5
7
,
 
1
5
,
 
1
1
7
4
]
,

 
[
4
2
5
5
,

 
 
1
1
9
5
,

 
 
1
2
2
4
,

 
 
9
,

 
 
6
2
4
,

 
 
6
3
1
,

 
 
1
,

 
 
5
3
3
9
,

 
 
2
,

 
 
1
5
6
6
,

 
 
5
6
,

 
 
1
3
2
,

 
 
3
5
0
8
,

 
 
6
,

 
 
2
3
7
6
,

 
 
1
7
,

 
 
6
9
1
,

 
 
3
2
7
8
]
,

 
[
6
9
9
4
,

 
 
7
,

 
 
1
7
3
,

 
 
3
,

 
 
6
4
3
,

 
 
1
9
1
8
9
,

 
 
1
1
,

 
 
8
,

 
 
1
9
1
3
,

 
 
6
9
,

 
 
6
,

 
 
3
8
1
,

 
 
8
9
2
,

 
 
3
9
9
1
,

 
 
1
,

 
 
2
8
2
1
,

 
 
2
,

 
 
1
9
1
9
0
,

 
 
7
,

 
 
1
9
,

 
 
1
1
,

 
 
1
2
,

 
 
3
6
,

 
 
3
0
7
,

 
 
2
3
7
7
,

 
 
9
0
6
,

 
 
4
7
,

 
 
1
3
0
5
,

 
 
8
8
,

 
 
1
,

 
 
9
7
6
,

 
 
1
1
7
4
,

 
 
2
,

 
 
1
,

 
 
5
0
0
3
]
,

 
[
3
4
,

 
 
6
2
,

 
 
6
5
3
4
,

 
 
2
6
,

 
 
3
8
8
,

 
 
2
3
,

 
 
4
5
0
,

 
 
4
9
6
0
,

 
 
4
,

 
 
1
,

 
 
1
0
7
8
2
,

 
 
1
3
0
1
,

 
 
2
,

 
 
1
,

 
 
5
6
9
5
,

 
 
1
7
1
1
,

 
 
2
1
,

 
 
1
,

 
 
1
9
1
9
1
]
,

 
[
1
4
7
3
,

 
 
1
8
0
,

 
 
2
2
,

 
 
1
2
6
,

 
 
1
8
0
,

 
 
2
2
,

 
 
4
6
0
,

 
 
6
4
1
,

 
 
2
2
2
,

 
 
6
7
2
,

 
 
9
4
,

 
 
5
,

 
 
4
1
4
,

 
 
4
,

 
 
1
3
8
,

 
 
1
,

 
 
2
7
1
8
,

 
 
1
6
3
,

 
 
2
,

 
 
1
,

 
 
3
6
8
,

 
 
1
0
1
6
,

 
 
3
3
,

 
 
9
2
,

 
 
4
,

 
 
5
0
0
4
,

 
 
1
5
1
,

 
 
1
0
3
]
,

 
[
4
2
,
 
5
0
0
5
,
 
1
9
6
,
 
2
,
 
4
0
6
0
,
 
3
,
 
5
0
,
 
2
,
 
6
9
6
,
 
1
3
5
8
,
 
2
,
 
3
2
7
9
,
 
1
5
2
5
]
,

 
[
3
,

 
 
5
2
,

 
 
1
3
2
,

 
 
1
9
1
5
,

 
 
3
7
,

 
 
2
9
1
8
,

 
 
1
4
9
1
1
,

 
 
3
,

 
 
1
4
9
1
2
,

 
 
2
,

 
 
1
0
7
8
3
,

 
 
5
,

 
 
4
4
5
,

 
 
2
1
,

 
 
1
9
1
,

 
 
9
,

 
 
1
1
,

 
 
6
3
4
,

 
 
2
4
,

 
 
1
,

 
 
3
0
4
,

 
 
5
8
,

 
 
2
0
7
0
,

 
 
1
,

 
 
2
9
3
6
,

 
 
2
,

 
 
9
,

 
 
1
3
2
4
,

 
 
2
0
7
1
,

 
 
1
9
5
,

 
 
3
5
2
6
]
,

 
[
1
,

 
 
1
4
9
1
3
,

 
 
1
5
0
5
,

 
 
7
5
,

 
 
4
1
,

 
 
1
9
1
9
2
,

 
 
4
,

 
 
7
7
2
0
,

 
 
1
3
,

 
 
1
9
1
9
3
,

 
 
6
9
6
9
,

 
 
6
5
3
5
,

 
 
2
5
,

 
 
5
7
9
,

 
 
2
1
,

 
 
6
5
3
6
,

 
 
1
3
,

 
 
9
,

 
 
3
5
,

 
 
7
0
,

 
 
9
5
,

 
 
6
9
6
9
,

 
 
6
5
3
5
,

 
 
3
,

 
 
7
5
,

 
 
8
5
8
0
,

 
 
2
1
,

 
 
6
5
3
6
,

 
 
1
3
,

 
 
2
2
9
]
,

 
[
9
5
2
4
,

 
 
1
3
1
6
,

 
 
7
7
,

 
 
4
8
,

 
 
8
2
,

 
 
7
7
5
1
,

 
 
2
2
,

 
 
7
,

 
 
1
0
2
,

 
 
6
5
1
,

 
 
1
2
8
4
,

 
 
1
7
,

 
 
5
4
,

 
 
1
0
3
8
,

 
 
9
5
2
4
,

 
 
1
3
1
6
]
,

 
[
3
6
,
 
3
2
,
 
8
4
,
 
2
8
,
 
6
8
3
]
,

 
[
3
3
6
0
,

 
 
9
0
1
,

 
 
1
3
,

 
 
8
9
9
,

 
 
3
0
,

 
 
9
9
,

 
 
2
8
3
,

 
 
4
4
6
,

 
 
1
3
,

 
 
4
1
8
,

 
 
1
9
,

 
 
4
8
,

 
 
9
9
0
,

 
 
4
,

 
 
8
5
8
1
,

 
 
1
7
9
,

 
 
6
0
9
1
,

 
 
1
8
,

 
 
5
,

 
 
1
1
5
8
,

 
 
9
6
,

 
 
9
,

 
 
3
0
,

 
 
3
9
9
,

 
 
3
,

 
 
9
7
7
,

 
 
2
9
,

 
 
5
0
,

 
 
2
7
4
4
,

 
 
8
2
,

 
 
1
7
8
,

 
 
9
0
1
,

 
 
4
,

 
 
1
,

 
 
1
4
9
1
4
,

 
 
2
,

 
 
3
0
,

 
 
2
1
1
]
,

 
[
7
0
5
,
 
9
5
2
5
,
 
1
,
 
1
1
4
3
,
 
3
6
2
]
,

 
[
1
6
0
,
 
4
6
,
 
2
8
,
 
5
0
,
 
1
4
0
0
]
,

 
[
1
1
,

 
 
8
,

 
 
6
,

 
 
6
1
,

 
 
2
5
4
8
,

 
 
1
0
3
9
,

 
 
1
5
3
,

 
 
6
6
2
,

 
 
5
6
9
6
,

 
 
3
6
,

 
 
1
0
6
3
,

 
 
2
1
,

 
 
3
2
,

 
 
7
,

 
 
3
0
6
,

 
 
1
1
,

 
 
8
,

 
 
4
0
6
1
,

 
 
1
1
,

 
 
8
]
,

 
[
1
0
6
,

 
 
4
8
,

 
 
1
4
5
,

 
 
4
1
5
,

 
 
9
,

 
 
1
4
,

 
 
4
9
,

 
 
1
6
4
,

 
 
2
1
,

 
 
1
5
1
,

 
 
3
,

 
 
1
,

 
 
7
7
5
2
,

 
 
1
,

 
 
7
0
8
7
,

 
 
8
0
,

 
 
6
8
5
,

 
 
2
1
,

 
 
2
6
,

 
 
5
6
1
1
,

 
 
1
,

 
 
5
0
,

 
 
1
6
5
7
,

 
 
4
8
,

 
 
8
,

 
 
2
,

 
 
3
0
5
8
,

 
 
1
1
,

 
 
1
7
,

 
 
1
2
9
]
,

 
[
1
1
6
,
 
6
5
,
 
8
5
8
2
,
 
1
0
,
 
7
6
0
,
 
4
7
3
6
,
 
6
,
 
8
2
4
,
 
4
3
7
,
 
1
0
6
7
3
,
 
3
3
]
,

 
[
2
6
,

 
 
8
,

 
 
1
,

 
 
3
5
2
,

 
 
7
,

 
 
1
9
,

 
 
5
,

 
 
1
0
7
,

 
 
6
,

 
 
1
4
9
1
5
,

 
 
1
7
,

 
 
1
,

 
 
8
3
,

 
 
7
2
,

 
 
3
,

 
 
1
,

 
 
3
1
9
,

 
 
3
2
0
,

 
 
2
2
,

 
 
1
6
3
9
,

 
 
7
,

 
 
6
,

 
 
4
0
2
0
,

 
 
2
,

 
 
2
3
1
6
]
,

 
[
1
,
 
1
0
7
4
1
,
 
1
7
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
 
6
,
 
1
8
9
,
 
6
0
9
4
]
,

 
[
7
6
,
 
1
4
,
 
8
,
 
9
0
,
 
7
,
 
3
3
4
,
 
7
3
9
]
,

 
[
1
1
,
 
8
,
 
1
5
9
6
,
 
4
,
 
4
1
4
,
 
1
,
 
1
6
5
,
 
1
4
6
,
 
6
,
 
3
4
8
6
,
 
2
1
3
2
,
 
6
0
,
 
8
4
1
,
 
9
3
,
 
3
2
7
2
]
,

 
[
5
,

 
 
1
5
4
,

 
 
2
1
,

 
 
1
2
8
,

 
 
1
,

 
 
3
8
7
4
,

 
 
2
,

 
 
5
3
4
0
,

 
 
7
0
0
,

 
 
1
2
4
1
4
,

 
 
3
,

 
 
3
2
0
,

 
 
6
6
,

 
 
7
,

 
 
1
,

 
 
3
1
1
,

 
 
8
5
8
3
,

 
 
5
3
6
,

 
 
2
3
,

 
 
1
1
0
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
8
6
,

 
 
1
2
4
1
5
,

 
 
3
5
4
3
,

 
 
3
,

 
 
6
5
3
7
,

 
 
2
,

 
 
1
,

 
 
6
0
2
,

 
 
2
1
6
3
]
,

 
[
5
,

 
 
1
2
,

 
 
1
0
6
9
,

 
 
9
,

 
 
1
,

 
 
3
6
4
5
,

 
 
4
4
7
6
,

 
 
2
,

 
 
1
,

 
 
4
9
4
2
,

 
 
2
2
2
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

 
 
2
,

 
 
1
,

 
 
1
5
5
,

 
 
8
,

 
 
1
,

 
 
4
6
8
,

 
 
3
5
,

 
 
2
9
6
,

 
 
4
0
,

 
 
2
,

 
 
1
,

 
 
5
5
9
,

 
 
2
4
9
2
,

 
 
8
5
8
,

 
 
4
6
2
,

 
 
2
1
,

 
 
6
,

 
 
5
0
3
,

 
 
2
2
4
,

 
 
1
,

 
 
5
5
8
]
,

 
[
5
,
 
8
,
 
2
0
2
,
 
1
2
4
4
,
 
1
2
0
7
,
 
2
3
,
 
2
6
,
 
1
4
6
6
]
,

 
[
1
,

 
 
1
7
6
6
,

 
 
2
5
2
,

 
 
1
2
4
1
6
,

 
 
1
4
9
1
6
,

 
 
1
2
,

 
 
3
9
1
,

 
 
5
7
7
,

 
 
2
,

 
 
1
2
4
1
7
,

 
 
1
0
1
2
,

 
 
1
8
0
6
,

 
 
1
3
,

 
 
5
4
,

 
 
7
0
7
7
,

 
 
3
8
6
3
,

 
 
1
9
,

 
 
1
2
,

 
 
6
2
2
,

 
 
1
,

 
 
8
2
3
,

 
 
2
,

 
 
1
5
,

 
 
1
8
8
5
,

 
 
3
8
7
5
]
,

 
[
4
4
2
4
,

 
 
1
9
1
9
4
,

 
 
8
,

 
 
1
3
7
,

 
 
1
3
2
,

 
 
5
9
9
,

 
 
1
7
,

 
 
4
4
3
3
,

 
 
1
8
1
4
,

 
 
1
5
7
,

 
 
4
5
,

 
 
8
,

 
 
7
3
6
,

 
 
8
9
4
,

 
 
6
8
,

 
 
3
8
,

 
 
5
2
7
7
,

 
 
4
4
8
7
,

 
 
6
7
,

 
 
1
0
7
8
4
,

 
 
1
2
,

 
 
9
2
,

 
 
1
9
5
,

 
 
1
9
,

 
 
6
1
7
,

 
 
1
0
7
8
5
,

 
 
3
,

 
 
6
6
3
,

 
 
1
6
4
2
,

 
 
2
9
,

 
 
2
5
9
1
,

 
 
2
7
,

 
 
1
,

 
 
5
5
1
,

 
 
6
1
5
]
,

 
[
2
7
,

 
 
1
9
1
9
5
,

 
 
5
0
0
6
,

 
 
5
8
8
,

 
 
6
,

 
 
3
2
5
8
,

 
 
4
8
8
,

 
 
1
6
,

 
 
1
4
,

 
 
1
6
2
,

 
 
9
2
2
,

 
 
2
,

 
 
1
,

 
 
6
1
1
,

 
 
1
9
,

 
 
1
5
,

 
 
1
0
0
7
,

 
 
1
2
,

 
 
1
3
6
,

 
 
1
5
,

 
 
1
4
3
2
,

 
 
1
2
3
0
]
,

 
[
2
6
,
 
8
,
 
7
,
 
3
0
6
,
 
3
8
,
 
2
,
 
1
5
,
 
1
4
9
1
7
]
,

 
[
1
,
 
5
6
2
,
 
4
4
,
 
1
3
0
,
 
7
4
4
,
 
3
4
,
 
1
8
1
5
,
 
2
5
,
 
9
5
2
6
,
 
1
,
 
3
7
1
4
]
,

 
[
1
2
5
1
,

 
 
2
,

 
 
1
0
4
,

 
 
1
9
9
,

 
 
5
6
,

 
 
5
3
4
1
,

 
 
7
0
8
8
,

 
 
4
,

 
 
2
3
5
9
,

 
 
2
0
1
,

 
 
1
7
,

 
 
1
,

 
 
4
5
0
,

 
 
6
0
2
,

 
 
2
0
7
2
,

 
 
2
,

 
 
1
1
1
0
,

 
 
3
5
,

 
 
1
7
5
8
,

 
 
1
1
,

 
 
2
5
,

 
 
2
0
,

 
 
2
9
6
,

 
 
4
0
,

 
 
1
1
6
,

 
 
2
3
7
8
,

 
 
1
6
,

 
 
5
8
2
]
,

 
[
1
2
4
,

 
 
1
4
,

 
 
1
8
2
,

 
 
1
7
6
,

 
 
1
4
2
,

 
 
1
2
,

 
 
9
1
4
,

 
 
1
2
8
,

 
 
3
,

 
 
4
5
,

 
 
8
,

 
 
6
,

 
 
6
1
7
,

 
 
1
6
5
8
,

 
 
4
2
8
,

 
 
1
,

 
 
5
5
8
,

 
 
9
,

 
 
1
5
6
2
,

 
 
2
,

 
 
9
,

 
 
1
0
6
1
,

 
 
3
8
7
,

 
 
8
0
,

 
 
2
0
,

 
 
2
1
,

 
 
2
6
4
,

 
 
7
,

 
 
1
,

 
 
6
5
0
1
,

 
 
1
9
1
9
6
,

 
 
3
,

 
 
8
6
,

 
 
1
9
1
9
7
,

 
 
6
5
3
8
,

 
 
4
2
0
4
,

 
 
3
1
,

 
 
7
3
1
,

 
 
3
3
8
5
]
,

 
[
1
8
9
2
,
 
1
8
,
 
1
0
,
 
3
0
5
9
,
 
1
2
9
,
 
3
7
1
5
,
 
2
2
,
 
1
0
7
8
6
,
 
7
7
5
3
]
,

 
[
7
8
,
 
1
4
7
5
,
 
1
0
,
 
3
6
8
,
 
1
8
4
6
,
 
7
7
,
 
4
8
,
 
7
0
8
9
,
 
2
2
,
 
1
3
,
 
2
5
1
]
,

 
[
5
3
,
 
6
0
,
 
7
8
0
,
 
9
3
,
 
9
9
6
,
 
3
3
8
,
 
4
,
 
2
6
4
8
,
 
3
,
 
1
0
7
8
7
,
 
4
,
 
2
8
,
 
5
9
8
]
,

 
[
2
,

 
 
5
5
9
,

 
 
4
5
,

 
 
8
,

 
 
5
4
,

 
 
1
0
4
,

 
 
2
,

 
 
5
0
6
,

 
 
4
5
,

 
 
8
,

 
 
1
1
4
,

 
 
1
8
,

 
 
2
,

 
 
1
6
5
0
,

 
 
5
5
9
,

 
 
3
5
,

 
 
5
0
6
,

 
 
3
5
4
,

 
 
2
1
,

 
 
3
2
]
,

 
[
5
,

 
 
1
4
5
,

 
 
5
,

 
 
1
2
,

 
 
2
5
7
,

 
 
1
1
,

 
 
6
9
,

 
 
7
,

 
 
6
,

 
 
3
8
7
,

 
 
9
6
7
,

 
 
2
0
2
,

 
 
3
2
,

 
 
1
9
2
1
,

 
 
2
0
2
,

 
 
7
5
,

 
 
1
0
,

 
 
1
9
1
9
8
,

 
 
2
,

 
 
1
,

 
 
2
2
5
,

 
 
5
,

 
 
5
2
,

 
 
1
8
0
2
]
,

 
[
1
9
7
,

 
 
1
3
6
2
,

 
 
7
0
5
7
,

 
 
1
4
,

 
 
1
2
4
1
8
,

 
 
4
9
,

 
 
2
0
2
6
,

 
 
3
9
,

 
 
4
,

 
 
7
9
7
,

 
 
1
,

 
 
6
4
6
8
,

 
 
1
8
,

 
 
1
4
,

 
 
4
6
,

 
 
9
4
,

 
 
3
3
4
,

 
 
1
3
,

 
 
4
3
2
]
,

 
[
2
3
,

 
 
2
6
,

 
 
7
2
,

 
 
6
5
3
9
,

 
 
9
5
2
7
,

 
 
8
5
8
4
,

 
 
3
5
4
4
,

 
 
3
,

 
 
1
,

 
 
7
4
4
,

 
 
3
4
9
,

 
 
1
4
9
1
8
,

 
 
2
9
,

 
 
3
2
,

 
 
8
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
7
4
5
,

 
 
3
,

 
 
1
,

 
 
4
4
5
5
,

 
 
1
2
,

 
 
7
7
5
,

 
 
1
5
,

 
 
5
5
3
,

 
 
1
6
8
,

 
 
4
,

 
 
5
6
9
2
,

 
 
1
7
,

 
 
5
8
5
,

 
 
1
2
4
1
9
]
,

 
[
1
,

 
 
3
6
2
,

 
 
3
0
1
1
,

 
 
2
,

 
 
2
0
3
,

 
 
7
6
3
8
,

 
 
8
8
,

 
 
1
5
,

 
 
3
3
4
0
,

 
 
1
9
1
9
9
,

 
 
1
,

 
 
2
0
4
,

 
 
5
7
,

 
 
1
3
1
7
,

 
 
3
,

 
 
1
2
4
2
0
,

 
 
1
,

 
 
1
2
4
2
1
,

 
 
1
5
5
,

 
 
5
7
,

 
 
5
4
,

 
 
8
5
6
,

 
 
2
,

 
 
5
9
6
9
]
,

 
[
1
,
 
1
9
9
2
,
 
2
,
 
1
,
 
1
9
2
0
0
,
 
9
0
7
]
,

 
[
3
5
4
,

 
 
2
,

 
 
1
,

 
 
2
1
5
0
,

 
 
2
2
4
5
,

 
 
1
2
9
,

 
 
4
6
5
9
,

 
 
7
4
,

 
 
4
3
1
,

 
 
2
1
,

 
 
1
0
3
,

 
 
4
5
,

 
 
1
2
7
,

 
 
6
,

 
 
1
0
7
8
8
,

 
 
1
0
4
4
,

 
 
9
,

 
 
1
1
,

 
 
8
,

 
 
2
0
,

 
 
1
1
5
0
,

 
 
4
,

 
 
9
4
,

 
 
4
0
]
,

 
[
1
8
,

 
 
2
5
,

 
 
1
1
,

 
 
2
0
,

 
 
3
5
3
,

 
 
5
,

 
 
1
2
6
3
,

 
 
9
,

 
 
1
9
4
,

 
 
1
,

 
 
4
7
9
,

 
 
1
2
3
,

 
 
2
8
,

 
 
7
,

 
 
9
1
2
,

 
 
2
,

 
 
1
,

 
 
2
7
3
6
,

 
 
1
6
,

 
 
1
1
,

 
 
6
0
9
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
3
,

 
 
3
1
,

 
 
1
4
4
0
,

 
 
1
1
,

 
 
3
7
1
6
,

 
 
5
9
,

 
 
4
4
,

 
 
1
5
,

 
 
1
1
1
,

 
 
3
0
5
1
]
,

 
[
1
4
,

 
 
1
2
,

 
 
2
9
3
7
,

 
 
4
,

 
 
2
3
2
,

 
 
1
5
0
,

 
 
1
8
0
5
,

 
 
7
7
5
4
,

 
 
2
7
4
6
,

 
 
7
,

 
 
1
,

 
 
1
2
6
8
,

 
 
6
9
,

 
 
1
5
,

 
 
2
2
2
8
,

 
 
1
,

 
 
5
6
1
7
,

 
 
5
5
4
,

 
 
2
,

 
 
1
5
,

 
 
7
7
5
5
,

 
 
9
5
2
8
,

 
 
1
9
2
0
1
,

 
 
2
1
,

 
 
1
5
,

 
 
2
7
0
]
,

 
[
1
,

 
 
8
5
8
6
,

 
 
2
,

 
 
1
5
6
8
,

 
 
6
8
3
,

 
 
4
,

 
 
6
,

 
 
1
4
8
9
,

 
 
7
,

 
 
8
6
9
,

 
 
3
,

 
 
1
,

 
 
5
2
7
2
,

 
 
2
0
0
,

 
 
4
4
6
4
,

 
 
1
2
4
2
2
,

 
 
1
0
,

 
 
8
7
1
,

 
 
1
0
,

 
 
8
7
1
,

 
 
6
5
,

 
 
1
,

 
 
3
7
0
9
,

 
 
1
6
2
,

 
 
1
2
1
7
,

 
 
3
,

 
 
1
3
,

 
 
6
,

 
 
1
2
4
2
3
,

 
 
2
,

 
 
7
6
1
2
,

 
 
4
8
8
,

 
 
4
,

 
 
1
,

 
 
2
4
3
0
,

 
 
3
2
9
,

 
 
1
0
,

 
 
7
1
2
,

 
 
7
5
0
,

 
 
1
0
,

 
 
1
7
3
,

 
 
3
,

 
 
2
7
3
,

 
 
4
,

 
 
1
8
1
6
,

 
 
6
,

 
 
3
5
2
,

 
 
1
3
0
,

 
 
6
5
1
6
,

 
 
2
,

 
 
3
7
1
7
,

 
 
5
,

 
 
4
6
,

 
 
6
4
,

 
 
1
4
9
1
9
,

 
 
1
3
,

 
 
6
,

 
 
2
6
6
,

 
 
2
,

 
 
1
8
1
3
]
,

 
[
3
,

 
 
1
,

 
 
7
5
7
,

 
 
1
8
8
,

 
 
8
,

 
 
9
,

 
 
2
1
7
8
,

 
 
6
3
9
,

 
 
3
5
4
,

 
 
2
,

 
 
1
5
,

 
 
2
8
6
,

 
 
2
4
,

 
 
1
,

 
 
5
1
1
,

 
 
2
,

 
 
1
9
2
0
2
,

 
 
3
5
,

 
 
1
4
9
2
0
]
,

 
[
1
9
2
0
3
,

 
 
7
8
,

 
 
8
1
1
,

 
 
1
1
1
1
,

 
 
5
,

 
 
7
6
9
,

 
 
3
3
,

 
 
5
6
,

 
 
1
0
,

 
 
1
2
4
2
4
,

 
 
5
6
,

 
 
3
3
,

 
 
1
5
6
8
,

 
 
1
9
3
,

 
 
1
2
4
2
5
,

 
 
1
8
,

 
 
5
,

 
 
8
,

 
 
4
9
7
2
,

 
 
2
3
,

 
 
6
,

 
 
1
5
6
8
,

 
 
3
7
5
,

 
 
3
,

 
 
6
1
4
,

 
 
9
,

 
 
8
1
1
,

 
 
6
4
]
,

 
[
3
4
,

 
 
1
0
4
7
,

 
 
7
0
7
,

 
 
2
2
0
,

 
 
4
0
,

 
 
9
,

 
 
2
1
,

 
 
1
9
1
,

 
 
1
,

 
 
7
1
9
,

 
 
3
,

 
 
8
8
3
,

 
 
2
,

 
 
9
7
,

 
 
1
6
1
,

 
 
4
6
,

 
 
2
8
,

 
 
4
2
5
6
,

 
 
4
7
,

 
 
2
1
5
,

 
 
1
2
3
8
,

 
 
3
2
4
,

 
 
1
0
8
6
,

 
 
3
,

 
 
1
,

 
 
8
5
1
4
,

 
 
2
,

 
 
4
7
,

 
 
7
7
5
6
,

 
 
1
6
2
,

 
 
4
7
2
1
,

 
 
5
,

 
 
4
6
,

 
 
2
3
1
7
,

 
 
1
,

 
 
7
7
5
7
,

 
 
2
5
4
,

 
 
2
,

 
 
1
0
,

 
 
1
9
2
,

 
 
1
6
,

 
 
1
4
,

 
 
1
8
5
,

 
 
1
2
7
6
,

 
 
1
5
0
,

 
 
2
1
,

 
 
5
5
,

 
 
1
5
8
9
]
,

 
[
1
1
,
 
8
,
 
7
6
7
,
 
1
1
2
4
,
 
3
3
9
4
,
 
3
,
 
1
,
 
3
3
4
5
,
 
6
2
5
,
 
7
,
 
1
0
,
 
3
2
1
,
 
9
2
,
 
1
1
,
 
2
9
3
8
,
 
4
0
]
,

 
[
3
3
8
,
 
8
,
 
1
0
6
,
 
4
,
 
6
,
 
1
0
2
,
 
4
9
9
,
 
9
5
2
9
]
,

 
[
1
1
,
 
8
,
 
1
,
 
5
9
2
,
 
8
3
,
 
1
0
7
8
9
,
 
5
8
,
 
1
2
,
 
1
9
1
6
,
 
1
5
,
 
6
2
7
]
,

 
[
4
,

 
 
3
5
2
,

 
 
1
4
,

 
 
3
3
1
,

 
 
1
2
4
2
6
,

 
 
1
,

 
 
9
7
7
,

 
 
2
,

 
 
1
5
,

 
 
1
2
4
2
7
,

 
 
8
3
4
,

 
 
1
6
,

 
 
1
4
,

 
 
4
2
3
,

 
 
6
6
,

 
 
4
,

 
 
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
,

 
 
2
,

 
 
6
,

 
 
8
5
8
7
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
1
4
0
0
,

 
 
1
2
4
2
8
,

 
 
4
,

 
 
3
5
2
,

 
 
1
0
8
,

 
 
4
3
,

 
 
1
,

 
 
6
3
0
,

 
 
2
,

 
 
1
0
,

 
 
9
1
]
,

 
[
1
1
,

 
 
8
,

 
 
8
4
6
8
,

 
 
2
3
,

 
 
6
,

 
 
8
3
3
,

 
 
2
4
3
1
,

 
 
2
,

 
 
1
8
5
,

 
 
1
2
4
2
9
,

 
 
1
3
0
,

 
 
1
1
0
6
,

 
 
6
5
4
0
,

 
 
3
,

 
 
1
0
3
,

 
 
8
5
8
8
,

 
 
4
,

 
 
1
,

 
 
8
7
6
,

 
 
2
1
8
1
,

 
 
3
6
,

 
 
1
0
4
,

 
 
8
2
3
,

 
 
3
,

 
 
1
1
,

 
 
1
2
,

 
 
3
2
0
,

 
 
1
7
0
2
,

 
 
7
,

 
 
1
0
2
,

 
 
2
2
8
0
,

 
 
1
9
8
,

 
 
8
2
,

 
 
1
,

 
 
9
4
0
,

 
 
3
,

 
 
1
5
5
,

 
 
1
4
9
2
1
,

 
 
2
,

 
 
2
1
8
2
,

 
 
7
4
3
]
,

 
[
2
5
,
 
1
1
,
 
7
0
,
 
4
3
4
,
 
6
5
,
 
9
,
 
5
,
 
5
0
0
7
,
 
1
1
]
,

 
[
3
2
,
 
2
6
,
 
7
2
,
 
5
,
 
1
2
,
 
9
0
,
 
1
8
0
,
 
2
6
8
,
 
2
,
 
1
,
 
1
5
6
4
,
 
2
5
5
2
]
,

 
[
5
,

 
 
9
2
8
,

 
 
4
,

 
 
3
0
3
4
,

 
 
2
4
,

 
 
1
,

 
 
3
1
9
,

 
 
2
,

 
 
1
0
,

 
 
4
3
7
,

 
 
7
9
2
,

 
 
1
8
1
7
,

 
 
4
1
,

 
 
2
0
6
,

 
 
1
4
,

 
 
9
3
,

 
 
1
6
4
,

 
 
4
,

 
 
2
6
0
5
,

 
 
1
5
,

 
 
6
4
6
]
,

 
[
5
,

 
 
3
1
,

 
 
7
7
,

 
 
9
,

 
 
1
,

 
 
8
3
0
,

 
 
5
4
1
,

 
 
2
,

 
 
1
0
,

 
 
5
2
1
,

 
 
2
4
3
2
,

 
 
2
0
7
3
,

 
 
9
,

 
 
2
,

 
 
3
8
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

 
 
1
,

 
 
6
5
4
1
,

 
 
1
2
,

 
 
4
3
,

 
 
4
,

 
 
1
4
9
2
2
,

 
 
1
,

 
 
8
3
,

 
 
5
6
6
,

 
 
1
0
4
4
]
,

 
[
3
3
7
9
,

 
 
6
0
8
,

 
 
2
0
,

 
 
1
1
9
8
,

 
 
1
1
3
,

 
 
2
,

 
 
1
,

 
 
2
4
1
8
,

 
 
1
4
,

 
 
2
2
8
,

 
 
3
5
,

 
 
7
5
,

 
 
5
8
,

 
 
1
4
,

 
 
8
,

 
 
1
8
,

 
 
6
7
4
,

 
 
9
,

 
 
1
4
,

 
 
8
,

 
 
1
7
6
,

 
 
3
,

 
 
3
6
6
3
,

 
 
3
,

 
 
4
4
6
,

 
 
1
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
,

 
 
1
0
7
9
0
,

 
 
1
0
7
9
1
,

 
 
2
,

 
 
7
2
,

 
 
3
,

 
 
4
3
9
]
,

 
[
8
2
,
 
3
2
,
 
3
4
,
 
1
9
2
0
4
]
,

 
[
1
5
,

 
 
7
3
9
,

 
 
8
,

 
 
1
0
7
9
2
,

 
 
2
0
2
,

 
 
2
5
1
,

 
 
2
,

 
 
8
5
3
3
,

 
 
3
,

 
 
1
1
,

 
 
1
6
2
,

 
 
1
5
,

 
 
1
3
8
4
,

 
 
4
5
5
,

 
 
6
9
,

 
 
1
4
,

 
 
3
9
1
,

 
 
4
,

 
 
2
8
3
5
,

 
 
1
5
,

 
 
8
5
5
,

 
 
2
4
,

 
 
1
,

 
 
1
8
4
5
,

 
 
1
9
,

 
 
4
9
,

 
 
2
8
,

 
 
1
,

 
 
4
9
1
,

 
 
2
,

 
 
3
0
,

 
 
5
6
9
7
,

 
 
3
2
9
]
,

 
[
4
0
,

 
 
5
2
,

 
 
5
,

 
 
1
3
3
,

 
 
4
,

 
 
2
4
4
,

 
 
1
1
,

 
 
3
2
,

 
 
1
7
8
,

 
 
1
1
0
0
,

 
 
6
,

 
 
2
2
2
,

 
 
3
8
3
,

 
 
1
7
,

 
 
1
,

 
 
1
2
9
7
,

 
 
3
5
,

 
 
1
,

 
 
1
4
9
2
3
,

 
 
2
6
4
9
,

 
 
2
,

 
 
1
0
,

 
 
4
3
7
,

 
 
1
4
7
]
,

 
[
2
3
8
,

 
 
1
4
7
,

 
 
9
3
,

 
 
2
8
,

 
 
1
4
9
2
4
,

 
 
2
,

 
 
3
4
5
,

 
 
3
3
,

 
 
1
4
4
,

 
 
5
8
9
,

 
 
1
2
6
4
,

 
 
5
,

 
 
8
,

 
 
1
1
0
,

 
 
4
1
,

 
 
2
3
8
,

 
 
1
8
,

 
 
9
,

 
 
7
0
9
0
,

 
 
7
4
,

 
 
7
,

 
 
6
,

 
 
6
1
,

 
 
4
4
9
,

 
 
7
2
]
,

 
[
5
,

 
 
8
5
8
9
,

 
 
1
7
,

 
 
1
0
7
4
,

 
 
1
3
1
,

 
 
4
1
,

 
 
5
,

 
 
7
0
7
,

 
 
1
,

 
 
3
9
8
7
,

 
 
4
5
,

 
 
8
,

 
 
3
6
,

 
 
1
2
3
4
,

 
 
6
5
1
,

 
 
4
4
,

 
 
1
,

 
 
2
3
5
9
]
,

 
[
1
2
,

 
 
5
,

 
 
9
0
,

 
 
1
4
8
2
,

 
 
7
5
4
,

 
 
6
7
,

 
 
1
7
3
2
,

 
 
4
9
,

 
 
2
0
,

 
 
3
1
,

 
 
4
3
,

 
 
4
0
,

 
 
7
9
3
,

 
 
1
8
,

 
 
5
,

 
 
1
2
,

 
 
7
,

 
 
1
2
3
5
,

 
 
4
3
,

 
 
1
,

 
 
2
0
2
7
,

 
 
2
,

 
 
2
1
3
,

 
 
3
,

 
 
1
2
4
3
0
,

 
 
3
7
1
,

 
 
7
,

 
 
1
2
3
5
,

 
 
8
2
,

 
 
6
,

 
 
3
3
9
,

 
 
2
,

 
 
1
0
4
8
,

 
 
3
,

 
 
6
2
8
,

 
 
5
,

 
 
1
2
,

 
 
1
7
0
,

 
 
2
3
0
3
,

 
 
1
2
2
,

 
 
1
3
0
,

 
 
6
1
,

 
 
1
6
6
0
,

 
 
2
9
,

 
 
1
,

 
 
4
9
0
4
,

 
 
2
,

 
 
6
5
4
2
,

 
 
3
,

 
 
2
0
7
4
]
,

 
[
1
9
4
,

 
 
3
6
,

 
 
1
2
2
,

 
 
2
,

 
 
1
,

 
 
7
2
,

 
 
1
9
0
9
,

 
 
7
,

 
 
1
,

 
 
4
6
4
,

 
 
5
7
5
,

 
 
1
,

 
 
9
8
1
,

 
 
3
5
1
9
,

 
 
5
3
4
2
,

 
 
4
0
3
,

 
 
7
6
,

 
 
5
,

 
 
1
2
,

 
 
3
6
,

 
 
4
9
5
,

 
 
7
,

 
 
2
2
7
2
,

 
 
1
5
2
3
,

 
 
7
,

 
 
1
3
8
,

 
 
1
,

 
 
2
0
9
2
,

 
 
3
,

 
 
1
,

 
 
7
0
9
1
,

 
 
3
3
9
5
,

 
 
4
7
0
5
,

 
 
2
,

 
 
1
8
6
]
,

 
[
2
8
3
6
,
 
2
5
4
8
,
 
9
,
 
6
2
,
 
9
4
,
 
1
7
,
 
1
,
 
9
5
3
0
]
,

 
[
4
0
9
,

 
 
2
0
,

 
 
1
,

 
 
5
9
4
,

 
 
1
4
9
2
5
,

 
 
4
9
1
,

 
 
2
,

 
 
1
,

 
 
1
2
0
8
,

 
 
9
,

 
 
8
,

 
 
5
8
1
,

 
 
1
9
5
,

 
 
1
,

 
 
7
0
9
2
,

 
 
1
4
1
6
,

 
 
2
,

 
 
4
7
,

 
 
2
9
3
9
]
,

 
[
5
2
,

 
 
3
,

 
 
6
5
,

 
 
3
5
1
,

 
 
1
,

 
 
1
9
6
2
,

 
 
6
9
5
7
,

 
 
2
,

 
 
1
0
4
0
,

 
 
9
,

 
 
7
7
5
8
,

 
 
3
,

 
 
1
9
2
0
5
,

 
 
7
,

 
 
1
,

 
 
8
5
9
0
,

 
 
8
3
2
,

 
 
5
7
0
,

 
 
5
,

 
 
4
6
,

 
 
9
5
4
,

 
 
1
,

 
 
1
1
0
1
,

 
 
3
5
4
5
,

 
 
2
,

 
 
5
4
,

 
 
2
,

 
 
9
7
,

 
 
4
0
1
,

 
 
5
6
9
8
,

 
 
1
9
,

 
 
1
9
2
0
6
,

 
 
1
,

 
 
1
2
8
0
,

 
 
5
3
4
3
,

 
 
1
0
5
3
]
,

 
[
3
,
 
9
4
,
 
3
3
,
 
3
5
2
,
 
7
7
,
 
1
,
 
1
7
1
3
]
,

 
[
5
,
 
1
1
9
0
,
 
1
1
,
 
4
,
 
9
4
,
 
4
0
,
 
1
6
8
8
,
 
6
5
4
3
,
 
3
,
 
1
9
2
0
7
,
 
1
1
,
 
1
6
,
 
5
,
 
6
3
4
]
,

 
[
5
,

 
 
5
2
2
,

 
 
7
,

 
 
6
,

 
 
1
1
6
6
,

 
 
1
2
4
3
1
,

 
 
2
3
,

 
 
1
4
9
2
6
,

 
 
3
6
6
,

 
 
2
,

 
 
2
4
2
3
,

 
 
3
,

 
 
4
4
8
8
,

 
 
5
,

 
 
8
3
5
,

 
 
6
,

 
 
7
7
5
9
,

 
 
1
2
7
,

 
 
1
2
4
3
2
,

 
 
6
4
,

 
 
7
8
,

 
 
2
8
6
,

 
 
7
8
,

 
 
2
5
4
6
,

 
 
1
7
,

 
 
6
5
3
,

 
 
3
3
,

 
 
3
1
2
,

 
 
9
4
6
,

 
 
2
2
,

 
 
8
1
,

 
 
1
0
,

 
 
4
5
6
,

 
 
8
5
9
1
,

 
 
1
7
,

 
 
2
2
,

 
 
1
,

 
 
6
1
6
,

 
 
4
,

 
 
6
,

 
 
3
5
2
,

 
 
1
4
9
2
7
,

 
 
1
,

 
 
4
6
7
1
,

 
 
3
,

 
 
1
0
6
2
,

 
 
1
3
,

 
 
8
6
2
,

 
 
9
5
3
1
,

 
 
2
,

 
 
1
,

 
 
1
3
4
7
]
,

 
[
1
1
3
,

 
 
2
3
3
,

 
 
6
6
,

 
 
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

 
 
1
9
2
0
8
,

 
 
4
,

 
 
6
5
4
4
,

 
 
6
,

 
 
6
5
4
5
,

 
 
7
4
7
,

 
 
3
,

 
 
6
5
,

 
 
1
2
4
3
3
,

 
 
6
8
7
,

 
 
8
8
,

 
 
5
2
3
0
,

 
 
4
2
,

 
 
2
9
,

 
 
1
2
5
5
,

 
 
2
3
,

 
 
1
,

 
 
1
2
4
3
4
,

 
 
2
2
4
5
,

 
 
2
,

 
 
9
,

 
 
2
9
2
,

 
 
3
,

 
 
3
2
,

 
 
1
7
5
5
,

 
 
1
3
,

 
 
3
8
,

 
 
2
0
7
5
,

 
 
5
7
,

 
 
4
0
6
]
,

 
[
1
4
9
2
8
,

 
 
6
,

 
 
1
2
4
3
5
,

 
 
4
9
,

 
 
3
1
,

 
 
2
7
4
,

 
 
1
0
7
9
3
,

 
 
4
,

 
 
1
5
0
4
,

 
 
1
6
,

 
 
3
7
,

 
 
1
2
4
3
6
,

 
 
3
,

 
 
3
3
9
3
,

 
 
1
1
3
7
,

 
 
2
,

 
 
1
8
1
,

 
 
7
6
5
,

 
 
6
,

 
 
9
5
3
2
,

 
 
2
2
6
,

 
 
1
9
,

 
 
3
4
,

 
 
1
2
3
,

 
 
4
1
4
,

 
 
8
5
9
2
,

 
 
1
7
,

 
 
8
8
7
,

 
 
2
,

 
 
6
,

 
 
5
0
,

 
 
4
2
5
7
,

 
 
1
5
4
5
]
,

 
[
1
8
,
 
1
1
,
 
9
2
,
 
1
4
7
,
 
3
5
2
,
 
3
,
 
4
0
,
 
4
2
,
 
1
8
2
,
 
3
8
4
,
 
4
,
 
6
3
6
,
 
1
7
9
]
,

 
[
7
,

 
 
3
6
3
,

 
 
1
1
4
,

 
 
1
6
,

 
 
1
,

 
 
8
5
9
3
,

 
 
2
,

 
 
2
6
0
7
,

 
 
3
2
3
2
,

 
 
6
7
,

 
 
6
0
3
,

 
 
1
4
5
8
,

 
 
4
2
,

 
 
9
2
8
,

 
 
6
3
,

 
 
5
0
,

 
 
3
,

 
 
1
0
9
7
,

 
 
2
,

 
 
1
9
2
0
9
,

 
 
6
3
,

 
 
1
6
,

 
 
8
5
9
4
,

 
 
5
0
0
8
,

 
 
4
1
0
,

 
 
2
1
4
,

 
 
4
4
2
,

 
 
9
,

 
 
3
6
,

 
 
2
8
2
8
,

 
 
9
5
3
3
,

 
 
3
5
,

 
 
1
4
9
2
9
,

 
 
9
3
,

 
 
5
3
4
4
,

 
 
3
4
6
,

 
 
1
,

 
 
9
6
7
,

 
 
4
0
6
2
,

 
 
1
7
5
,

 
 
1
,

 
 
2
1
5
,

 
 
3
7
3
]
,

 
[
1
3
,
 
1
,
 
5
0
8
,
 
7
,
 
3
8
8
,
 
2
6
,
 
4
9
1
,
 
9
2
0
,
 
4
,
 
2
8
,
 
1
,
 
7
8
8
]
,

 
[
1
8
,

 
 
1
1
,

 
 
8
,

 
 
2
0
,

 
 
4
0
,

 
 
6
2
4
,

 
 
9
5
3
4
,

 
 
6
7
1
,

 
 
1
0
,

 
 
6
5
4
6
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
2
0
,

 
 
4
6
8
,

 
 
4
7
8
,

 
 
2
0
7
6
,

 
 
3
,

 
 
6
0
,

 
 
7
6
,

 
 
7
,

 
 
5
4
,

 
 
1
1
7
0
,

 
 
3
9
2
,

 
 
4
,

 
 
2
2
,

 
 
6
2
4
,

 
 
1
4
9
3
0
,

 
 
2
0
,

 
 
8
4
2
,

 
 
4
,

 
 
2
4
2
,

 
 
3
,

 
 
2
9
7
,

 
 
6
2
4
,

 
 
1
4
9
3
1
,

 
 
2
0
,

 
 
5
5
5
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

 
 
2
3
7
6
,

 
 
4
7
8
,

 
 
5
9
,

 
 
9
,

 
 
1
9
,

 
 
5
,

 
 
2
9
7
]
,

 
[
6
,
 
2
5
1
4
,
 
2
6
2
6
,
 
2
5
,
 
2
6
]
,

 
[
1
3
,
 
2
4
3
3
,
 
2
,
 
1
1
7
7
,
 
8
9
9
,
 
7
8
,
 
8
6
,
 
7
7
6
0
,
 
1
1
7
8
,
 
1
4
4
2
,
 
6
0
9
6
]
,

 
[
1
,

 
 
6
4
6
0
,

 
 
3
0
6
0
,

 
 
8
,

 
 
1
4
5
4
,

 
 
1
,

 
 
3
7
8
,

 
 
4
4
2
5
,

 
 
7
,

 
 
1
,

 
 
2
1
1
8
,

 
 
4
4
,

 
 
1
9
,

 
 
1
,

 
 
1
0
3
5
,

 
 
1
2
,

 
 
7
3
3
,

 
 
2
4
,

 
 
1
,

 
 
3
6
5
,

 
 
1
9
,

 
 
2
1
6
,

 
 
7
,

 
 
4
4
,

 
 
1
,

 
 
4
7
2
]
,

 
[
7
,
 
1
,
 
4
0
6
3
,
 
3
,
 
1
0
7
9
4
,
 
2
,
 
1
,
 
4
6
4
,
 
1
,
 
1
0
0
2
,
 
7
2
7
,
 
1
2
,
 
4
3
,
 
4
,
 
1
9
2
1
0
,
 
3
,
 
1
9
2
1
1
]
,

 
[
1
6
9
,

 
 
6
7
,

 
 
3
,

 
 
1
4
4
6
,

 
 
1
5
2
4
,

 
 
2
3
,

 
 
3
0
,

 
 
8
,

 
 
3
0
1
1
,

 
 
1
0
7
9
5
,

 
 
9
4
2
5
,

 
 
4
,

 
 
4
0
6
,

 
 
2
4
,

 
 
1
,

 
 
6
6
8
,

 
 
5
5
8
6
,

 
 
2
,

 
 
1
2
3
5
,

 
 
3
,

 
 
1
5
,

 
 
8
5
5
,

 
 
1
,

 
 
2
3
8
,

 
 
5
0
0
9
,

 
 
1
3
6
6
,

 
 
2
2
1
,

 
 
1
1
4
,

 
 
2
,

 
 
3
0
,

 
 
7
2
,

 
 
2
1
,

 
 
7
5
4
,

 
 
8
0
5
]
,

 
[
2
1
0
,
 
7
8
0
,
 
8
5
9
5
,
 
3
,
 
3
1
3
4
,
 
6
7
,
 
3
9
8
]
,

 
[
6
5
4
7
,

 
 
1
7
8
,

 
 
1
7
6
7
,

 
 
1
1
,

 
 
4
,

 
 
2
8
,

 
 
4
4
8
9
,

 
 
6
2
,

 
 
9
,

 
 
7
1
,

 
 
9
3
,

 
 
1
6
3
8
,

 
 
1
5
,

 
 
1
0
0
4
,

 
 
3
4
,

 
 
4
4
5
,

 
 
3
7
,

 
 
5
0
1
0
,

 
 
2
,

 
 
1
9
2
1
2
,

 
 
2
0
5
1
]
,

 
[
2
1
,

 
 
8
3
,

 
 
5
,

 
 
1
2
,

 
 
1
1
9
1
,

 
 
6
4
,

 
 
4
,

 
 
9
7
,

 
 
1
9
6
4
,

 
 
2
2
,

 
 
1
8
,

 
 
1
,

 
 
1
6
5
,

 
 
4
0
6
4
,

 
 
1
6
7
9
,

 
 
6
8
,

 
 
2
2
,

 
 
3
,

 
 
5
,

 
 
9
6
,

 
 
9
,

 
 
5
,

 
 
8
,

 
 
9
0
1
,

 
 
4
,

 
 
2
3
,

 
 
3
2
]
,

 
[
2
,

 
 
5
6
9
9
,

 
 
1
9
2
2
,

 
 
1
9
2
1
3
,

 
 
9
0
2
,

 
 
2
9
,

 
 
4
7
,

 
 
3
9
5
,

 
 
7
,

 
 
7
6
2
,

 
 
1
0
7
9
6
,

 
 
3
,

 
 
7
,

 
 
3
2
8
0
,

 
 
4
0
,

 
 
9
,

 
 
1
9
2
1
4
,

 
 
8
0
,

 
 
7
1
8
,

 
 
1
8
6
,

 
 
9
5
,

 
 
1
6
,

 
 
1
4
7
,

 
 
1
2
4
3
7
,

 
 
6
3
,

 
 
4
6
5
,

 
 
1
,

 
 
7
4
4
]
,

 
[
3
3
,

 
 
3
1
,

 
 
7
8
,

 
 
1
0
8
7
,

 
 
4
,

 
 
1
8
7
,

 
 
4
2
5
8
,

 
 
2
6
5
0
,

 
 
2
5
2
,

 
 
2
9
4
0
,

 
 
3
,

 
 
9
,

 
 
1
0
7
9
7
,

 
 
2
,

 
 
3
1
1
8
,

 
 
2
5
,

 
 
6
,

 
 
1
9
2
1
5
,

 
 
6
8
,

 
 
7
8
,

 
 
1
2
1
2
]
,

 
[
1
5
,
 
1
7
2
4
,
 
5
6
,
 
2
3
,
 
3
6
,
 
2
8
5
,
 
1
4
5
6
]
,

 
[
2
7
3
0
,

 
 
9
8
,

 
 
4
,

 
 
5
7
2
,

 
 
3
9
,

 
 
1
6
8
,

 
 
7
6
,

 
 
1
4
,

 
 
7
1
0
,

 
 
7
8
4
,

 
 
4
,

 
 
4
4
2
7
,

 
 
6
,

 
 
7
0
9
3
,

 
 
2
,

 
 
1
4
9
3
,

 
 
3
,

 
 
5
5
2
]
,

 
[
5
,
 
9
2
4
,
 
2
4
,
 
1
0
,
 
2
1
1
,
 
6
,
 
6
0
9
7
,
 
2
,
 
5
4
,
 
1
1
2
5
]
,

 
[
3
4
,

 
 
2
9
,

 
 
7
,

 
 
1
,

 
 
8
6
,

 
 
7
7
6
1
,

 
 
2
9
4
1
,

 
 
1
8
,

 
 
1
6
,

 
 
3
4
,

 
 
4
6
,

 
 
6
4
,

 
 
7
1
4
,

 
 
7
0
9
4
,

 
 
1
0
,

 
 
1
1
8
1
,

 
 
3
4
2
,

 
 
8
,

 
 
8
0
7
,

 
 
2
3
,

 
 
1
0
,

 
 
1
6
5
1
,

 
 
4
4
9
0
,

 
 
1
3
0
,

 
 
2
5
3
3
,

 
 
9
7
8
,

 
 
7
,

 
 
8
9
,

 
 
6
,

 
 
4
9
9
,

 
 
9
,

 
 
1
4
,

 
 
8
,

 
 
5
7
9
,

 
 
1
9
4
7
,

 
 
4
,

 
 
1
5
,

 
 
4
7
2
]
,

 
[
9
,

 
 
3
1
7
,

 
 
3
6
,

 
 
2
4
2
6
,

 
 
5
9
,

 
 
6
,

 
 
1
8
9
,

 
 
1
0
7
9
8
,

 
 
2
1
6
4
,

 
 
3
,

 
 
1
4
9
3
2
,

 
 
2
8
9
,

 
 
2
3
,

 
 
1
,

 
 
1
9
2
1
6
,

 
 
1
9
6
2
,

 
 
3
6
8
5
,

 
 
9
8
,

 
 
4
,

 
 
3
1
,

 
 
4
3
,

 
 
1
,

 
 
4
2
5
9
,

 
 
2
,

 
 
6
,

 
 
8
6
7
,

 
 
3
8
6
,

 
 
2
,

 
 
7
0
8
2
,

 
 
5
3
4
5
,

 
 
4
0
6
5
,

 
 
1
7
,

 
 
7
,

 
 
3
6
,

 
 
1
9
6
,

 
 
5
9
,

 
 
2
9
4
2
,

 
 
8
6
8
,

 
 
1
2
,

 
 
1
0
7
9
9
,

 
 
4
,

 
 
1
9
2
1
7
,

 
 
1
1
]
,

 
[
2
6
,
 
1
2
3
,
 
2
0
,
 
2
8
,
 
2
3
6
0
,
 
4
,
 
7
0
9
5
,
 
1
,
 
2
6
3
,
 
1
7
,
 
5
,
 
2
6
9
,
 
2
0
7
5
]
,

 
[
1
4
,

 
 
8
,

 
 
1
4
8
8
,

 
 
5
2
6
,

 
 
5
1
8
,

 
 
1
4
,

 
 
5
7
0
0
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

 
 
5
0
1
1
,

 
 
9
8
,

 
 
4
0
0
,

 
 
4
,

 
 
9
8
8
,

 
 
5
7
,

 
 
5
5
,

 
 
3
9
8
,

 
 
3
,

 
 
4
,

 
 
1
8
7
,

 
 
3
8
,

 
 
1
3
,

 
 
8
5
]
,

 
[
1
4
,
 
1
1
5
,
 
2
1
4
,
 
1
0
,
 
5
1
7
,
 
3
,
 
3
4
,
 
6
3
4
]
,

 
[
2
6
,
 
9
2
7
,
 
1
6
2
,
 
6
5
4
8
,
 
7
,
 
6
,
 
3
6
6
,
 
2
,
 
6
9
6
3
,
 
2
6
,
 
1
1
5
,
 
7
,
 
6
,
 
1
4
3
2
,
 
2
,
 
8
1
7
]
,

 
[
1
,
 
5
6
0
,
 
7
3
,
 
2
0
,
 
2
6
8
,
 
5
7
,
 
1
,
 
6
0
9
8
,
 
3
2
9
,
 
1
7
4
]
,

 
[
1
,

 
 
3
5
0
,

 
 
5
9
7
0
,

 
 
2
,

 
 
4
7
3
7
,

 
 
5
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
6
,

 
 
5
,

 
 
4
2
0
,

 
 
4
6
,

 
 
1
8
,

 
 
4
1
,

 
 
1
4
,

 
 
2
0
5
2
,

 
 
4
4
,

 
 
4
7
3
8
,

 
 
5
,

 
 
4
0
6
6
,

 
 
1
6
9
0
]
,

 
[
2
6
,
 
3
4
8
,
 
3
1
9
,
 
2
5
,
 
6
1
,
 
1
9
2
1
8
,
 
4
1
,
 
1
5
3
9
,
 
2
7
4
7
]
,

 
[
1
7
,

 
 
6
,

 
 
1
9
9
,

 
 
1
0
,

 
 
2
1
9
,

 
 
8
,

 
 
2
3
1
8
,

 
 
2
4
,

 
 
4
7
,

 
 
1
9
2
1
9
,

 
 
3
,

 
 
6
5
5
,

 
 
8
9
1
,

 
 
4
,

 
 
6
5
4
9
,

 
 
1
,

 
 
1
2
8
6
,

 
 
9
0
4
,

 
 
2
,

 
 
1
8
6
3
,

 
 
3
,

 
 
5
2
6
,

 
 
2
5
5
3
,

 
 
2
,

 
 
1
9
,

 
 
6
7
,

 
 
2
4
0
8
,

 
 
2
9
,

 
 
1
,

 
 
9
5
3
5
,

 
 
3
,

 
 
1
,

 
 
1
9
2
2
0
]
,

 
[
5
,

 
 
5
2
,

 
 
2
7
3
,

 
 
4
,

 
 
9
3
2
,

 
 
2
1
,

 
 
1
2
9
6
,

 
 
3
0
5
4
,

 
 
5
5
9
,

 
 
7
,

 
 
1
,

 
 
1
6
7
,

 
 
5
1
9
,

 
 
6
8
,

 
 
1
,

 
 
6
6
7
,

 
 
1
0
6
,

 
 
1
3
9
,

 
 
1
7
0
7
,

 
 
1
3
,

 
 
7
7
6
2
,

 
 
1
9
0
1
]
,

 
[
6
4
,

 
 
1
,

 
 
5
9
2
,

 
 
8
5
9
6
,

 
 
3
5
1
5
,

 
 
5
2
4
,

 
 
7
,

 
 
1
,

 
 
8
5
9
7
,

 
 
1
1
8
,

 
 
2
7
8
,

 
 
3
2
,

 
 
9
,

 
 
1
0
8
,

 
 
5
0
1
2
,

 
 
1
0
2
9
,

 
 
2
0
1
,

 
 
1
,

 
 
4
9
3
,

 
 
2
3
1
,

 
 
3
,

 
 
4
2
,

 
 
5
6
,

 
 
2
0
,

 
 
1
4
9
3
3
,

 
 
1
2
7
,

 
 
1
4
9
3
4
,

 
 
4
,

 
 
2
5
5
4
,

 
 
2
0
5
,

 
 
1
,

 
 
6
5
2
8
,

 
 
1
9
,

 
 
1
0
8
0
0
,

 
 
6
3
,

 
 
1
0
9
8
]
,

 
[
7
,

 
 
8
9
,

 
 
3
8
6
,

 
 
5
,

 
 
9
3
,

 
 
3
1
,

 
 
1
3
0
4
,

 
 
1
3
,

 
 
6
,

 
 
1
2
4
3
8
,

 
 
3
,

 
 
2
4
5
5
,

 
 
2
,

 
 
1
,

 
 
6
5
4
5
,

 
 
1
6
3
,

 
 
3
,

 
 
1
2
,

 
 
6
,

 
 
3
5
9
,

 
 
2
,

 
 
6
,

 
 
5
7
8
,

 
 
4
7
9
,

 
 
7
2
5
,

 
 
1
6
,

 
 
2
5
,

 
 
8
6
,

 
 
3
0
6
1
,

 
 
6
,

 
 
3
5
,

 
 
5
,

 
 
1
7
,

 
 
1
0
7
4
,

 
 
5
,

 
 
9
3
,

 
 
3
1
,

 
 
7
7
8
,

 
 
1
,

 
 
1
2
5
9
,

 
 
1
6
,

 
 
9
7
2
]
,

 
[
6
0
7
,
 
1
4
8
,
 
3
1
,
 
2
2
1
,
 
2
0
1
,
 
5
,
 
5
9
8
,
 
2
7
,
 
1
0
,
 
2
7
9
,
 
3
6
8
7
]
,

 
[
7
,

 
 
6
,

 
 
6
1
,

 
 
4
4
9
,

 
 
7
2
,

 
 
1
4
,

 
 
8
,

 
 
7
4
,

 
 
2
,

 
 
3
1
9
,

 
 
3
,

 
 
5
,

 
 
3
1
,

 
 
3
6
,

 
 
3
0
7
,

 
 
1
4
,

 
 
4
7
3
,

 
 
3
0
2
,

 
 
7
,

 
 
1
6
2
2
]
,

 
[
1
,

 
 
6
1
,

 
 
8
5
9
8
,

 
 
2
,

 
 
1
5
,

 
 
8
1
1
,

 
 
2
0
7
,

 
 
3
9
,

 
 
9
2
5
,

 
 
1
8
6
,

 
 
1
8
2
,

 
 
9
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
3
,

 
 
6
,

 
 
3
6
3
,

 
 
2
5
7
,

 
 
1
8
,

 
 
2
0
,

 
 
4
9
3
3
]
,

 
[
2
1
,

 
 
1
0
8
0
1
,

 
 
2
6
5
,

 
 
5
,

 
 
7
0
7
,

 
 
5
7
,

 
 
6
,

 
 
5
2
7
5
,

 
 
6
5
5
0
,

 
 
1
0
0
,

 
 
1
2
2
,

 
 
6
0
9
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
7
,

 
 
7
,

 
 
1
0
2
2
,

 
 
2
,

 
 
2
2
,

 
 
1
8
,

 
 
8
,

 
 
1
9
0
,

 
 
2
7
,

 
 
1
0
,

 
 
1
6
6
,

 
 
1
1
5
,

 
 
3
,

 
 
1
5
7
4
,

 
 
1
,

 
 
2
4
8
,

 
 
4
3
9
,

 
 
1
0
5
,

 
 
3
5
4
6
,

 
 
2
6
5
,

 
 
1
2
4
3
9
,

 
 
1
4
9
3
5
,

 
 
3
5
1
0
,

 
 
2
1
,

 
 
1
,

 
 
1
4
9
3
6
,

 
 
2
,

 
 
6
8
7
]
,

 
[
3
4
,
 
2
3
6
1
,
 
1
1
5
,
 
3
1
4
,
 
4
2
5
,
 
3
,
 
3
3
8
,
 
2
8
2
0
,
 
2
7
,
 
5
5
,
 
1
7
8
,
 
5
7
0
1
,
 
4
,
 
7
2
0
]
,

 
[
6
5
,

 
 
3
2
3
,

 
 
3
2
,

 
 
1
,

 
 
6
5
4
,

 
 
2
9
,

 
 
8
5
9
9
,

 
 
2
4
,

 
 
1
,

 
 
4
3
8
,

 
 
7
5
,

 
 
1
2
1
8
,

 
 
1
9
2
2
1
,

 
 
3
,

 
 
1
9
2
2
2
,

 
 
1
2
7
1
,

 
 
3
,

 
 
1
,

 
 
2
5
5
5
,

 
 
1
9
2
2
3
,

 
 
3
,

 
 
1
9
2
2
4
,

 
 
4
2
8
,

 
 
8
5
]
,

 
[
5
,
 
7
6
9
,
 
3
3
,
 
3
1
,
 
2
8
9
,
 
6
8
,
 
1
,
 
4
4
9
1
,
 
4
7
3
9
]
,

 
[
3
3
,

 
 
1
1
6
,

 
 
1
4
4
,

 
 
9
,

 
 
2
7
,

 
 
1
,

 
 
1
6
5
,

 
 
1
5
5
,

 
 
4
5
,

 
 
2
5
,

 
 
3
6
,

 
 
1
4
9
3
7
,

 
 
9
,

 
 
5
,

 
 
4
9
,

 
 
2
0
,

 
 
1
8
7
,

 
 
3
6
,

 
 
1
6
0
3
,

 
 
9
,

 
 
5
,

 
 
4
9
,

 
 
2
0
,

 
 
6
5
5
1
,

 
 
1
3
,

 
 
1
,

 
 
4
5
0
,

 
 
2
5
1
,

 
 
9
,

 
 
5
,

 
 
8
0
,

 
 
6
5
9
,

 
 
3
3
,

 
 
2
1
3
0
]
,

 
[
1
1
,
 
8
,
 
4
9
2
,
 
2
,
 
6
,
 
5
7
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
0
7
9
,
 
7
0
9
6
,
 
2
,
 
1
,
 
6
5
5
2
,
 
7
5
2
]
,

 
[
1
2
4
,

 
 
1
,

 
 
2
8
3
7
,

 
 
3
7
1
0
,

 
 
1
8
2
7
,

 
 
2
4
,

 
 
1
,

 
 
1
3
3
0
,

 
 
7
,

 
 
6
,

 
 
6
1
,

 
 
4
5
3
,

 
 
2
3
6
5
,

 
 
2
4
3
4
,

 
 
6
,

 
 
1
6
7
2
,

 
 
1
4
9
3
8
,

 
 
2
,

 
 
9
1
3
,

 
 
2
,

 
 
6
,

 
 
7
0
9
7
,

 
 
2
9
4
3
,

 
 
1
6
0
,

 
 
4
0
,

 
 
1
1
4
,

 
 
1
6
,

 
 
5
2
2
5
,

 
 
3
,

 
 
2
,

 
 
6
,

 
 
3
6
9
0
,

 
 
2
,

 
 
4
7
4
,

 
 
1
9
,

 
 
4
9
,

 
 
8
5
4
,

 
 
2
8
3
8
,

 
 
1
3
,

 
 
1
,

 
 
4
9
9
9
,

 
 
2
,

 
 
1
,

 
 
7
0
9
8
,

 
 
1
0
8
0
2
]
,

 
[
7
,

 
 
1
,

 
 
1
3
5
,

 
 
2
,

 
 
3
8
,

 
 
8
1
,

 
 
2
2
,

 
 
4
5
,

 
 
5
6
,

 
 
4
7
0
,

 
 
3
3
6
,

 
 
3
5
4
7
,

 
 
3
,

 
 
4
7
0
,

 
 
5
3
3
9
,

 
 
1
9
,

 
 
3
3
,

 
 
1
1
3
1
,

 
 
2
0
,

 
 
4
,

 
 
6
7
1
,

 
 
4
,

 
 
1
3
4
2
]
,

 
[
6
5
0
0
,

 
 
3
0
,

 
 
1
6
,

 
 
5
,

 
 
7
3
,

 
 
1
0
6
,

 
 
4
8
,

 
 
1
9
2
2
5
,

 
 
3
,

 
 
2
1
,

 
 
1
,

 
 
5
0
3
,

 
 
2
,

 
 
1
8
5
,

 
 
6
,

 
 
2
7
4
8
,

 
 
8
2
,

 
 
1
1
3
,

 
 
1
4
9
3
9
,

 
 
6
1
0
0
,

 
 
4
4
9
2
,

 
 
3
,

 
 
1
8
5
,

 
 
1
2
4
4
0
,

 
 
4
8
,

 
 
1
4
9
4
0
,

 
 
2
4
,

 
 
1
0
,

 
 
6
5
0
0
,

 
 
5
1
7
,

 
 
2
7
,

 
 
1
,

 
 
1
2
6
8
,

 
 
3
,

 
 
1
3
,

 
 
6
,

 
 
6
1
0
1
,

 
 
2
,

 
 
4
1
8
,

 
 
6
5
0
6
,

 
 
9
,

 
 
4
8
,

 
 
8
4
,

 
 
2
8
,

 
 
3
1
0
,

 
 
1
7
,

 
 
9
,

 
 
4
8
,

 
 
4
6
,

 
 
2
0
,

 
 
1
3
8
8
]
,

 
[
7
,

 
 
1
,

 
 
5
9
9
5
,

 
 
2
4
3
5
,

 
 
2
,

 
 
4
8
9
9
,

 
 
4
2
,

 
 
1
0
7
,

 
 
1
6
0
,

 
 
1
8
,

 
 
1
,

 
 
1
0
6
5
6
,

 
 
7
7
6
3
,

 
 
2
,

 
 
6
,

 
 
2
6
4
0
,

 
 
1
2
4
4
1
,

 
 
1
3
0
,

 
 
6
1
9
,

 
 
2
5
4
,

 
 
9
8
7
,

 
 
6
0
9
,

 
 
8
6
0
0
,

 
 
7
0
4
,

 
 
9
9
,

 
 
3
,

 
 
9
1
6
,

 
 
2
0
0
,

 
 
2
0
7
,

 
 
3
6
,

 
 
2
0
1
3
,

 
 
2
,

 
 
1
,

 
 
1
9
2
2
6
,

 
 
2
0
9
,

 
 
1
2
4
4
2
,

 
 
2
8
6
,

 
 
2
,

 
 
1
,

 
 
4
1
6
,

 
 
8
1
6
,

 
 
1
6
1
]
,

 
[
1
4
,
 
3
5
4
8
,
 
1
2
2
,
 
9
7
5
,
 
3
,
 
1
3
,
 
6
,
 
1
3
9
7
,
 
7
7
0
9
,
 
6
5
5
3
,
 
1
5
,
 
1
7
4
0
,
 
1
,
 
1
9
6
8
]
,

 
[
7
,

 
 
2
7
1
6
,

 
 
1
,

 
 
1
5
3
3
,

 
 
3
5
8
,

 
 
2
,

 
 
9
5
8
,

 
 
2
,

 
 
7
0
,

 
 
2
6
3
,

 
 
5
,

 
 
2
6
9
,

 
 
1
8
1
8
,

 
 
1
5
8
4
,

 
 
7
7
6
4
,

 
 
2
2
,

 
 
2
1
,

 
 
1
2
8
,

 
 
5
7
,

 
 
6
,

 
 
7
7
6
5
,

 
 
3
2
9
,

 
 
2
,

 
 
1
3
9
5
]
,

 
[
8
1
,

 
 
1
1
3
,

 
 
1
1
6
2
,

 
 
2
8
7
,

 
 
1
4
,

 
 
9
8
,

 
 
5
1
8
,

 
 
1
3
,

 
 
6
,

 
 
2
4
1
,

 
 
2
,

 
 
1
9
2
2
7
,

 
 
1
9
,

 
 
8
0
,

 
 
6
7
2
,

 
 
2
1
,

 
 
6
,

 
 
3
5
4
9
,

 
 
1
0
0
7
,

 
 
3
1
,

 
 
4
3
,

 
 
1
7
3
9
,

 
 
1
7
,

 
 
7
7
6
6
]
,

 
[
4
4
,
 
1
,
 
7
0
9
9
,
 
1
0
3
,
 
5
,
 
8
,
 
5
0
,
 
5
9
,
 
1
2
9
8
,
 
3
7
1
8
,
 
7
,
 
1
0
9
9
,
 
1
,
 
1
7
1
]
,

 
[
1
4
8
3
,

 
 
4
7
4
0
,

 
 
3
8
7
6
,

 
 
1
2
2
7
5
,

 
 
1
,

 
 
4
4
3
5
,

 
 
3
,

 
 
9
5
3
6
,

 
 
8
,

 
 
6
8
,

 
 
4
,

 
 
7
7
1
3
,

 
 
4
1
,

 
 
1
,

 
 
1
4
3
3
,

 
 
2
,

 
 
1
2
4
4
3
,

 
 
7
5
2
,

 
 
9
8
3
,

 
 
7
,

 
 
4
4
,

 
 
5
1
,

 
 
1
4
9
4
1
]
,

 
[
5
,
 
8
,
 
6
1
7
,
 
7
5
,
 
7
7
6
7
,
 
5
9
,
 
1
,
 
3
8
7
7
,
 
1
9
2
2
8
,
 
2
,
 
9
,
 
1
5
2
0
,
 
2
2
7
,
 
1
2
,
 
9
2
,
 
2
2
]
,

 
[
5
1
,

 
 
8
7
5
,

 
 
4
6
8
3
,

 
 
2
9
,

 
 
2
0
,

 
 
3
0
4
6
,

 
 
1
8
,

 
 
3
4
,

 
 
1
1
8
,

 
 
5
6
4
2
,

 
 
1
0
1
6
,

 
 
5
5
,

 
 
3
2
7
0
,

 
 
5
4
,

 
 
3
5
3
8
,

 
 
1
2
9
7
,

 
 
3
6
1
,

 
 
2
7
,

 
 
4
9
0
7
,

 
 
3
5
,

 
 
7
,

 
 
1
,

 
 
2
4
7
,

 
 
2
,

 
 
1
,

 
 
4
0
2
,

 
 
1
1
2
,

 
 
2
1
,

 
 
4
0
3
6
]
,

 
[
7
,
 
6
,
 
1
5
6
,
 
4
0
6
7
,
 
4
2
,
 
5
6
,
 
7
5
,
 
5
0
1
3
,
 
2
,
 
1
6
6
5
,
 
1
2
4
4
4
]
,

 
[
7
6
,
 
1
2
0
,
 
4
6
,
 
5
,
 
2
3
2
,
 
2
6
]
,

 
[
5
8
5
,

 
 
1
4
9
4
2
,

 
 
5
8
,

 
 
1
2
,

 
 
4
3
,

 
 
1
3
6
3
,

 
 
1
,

 
 
1
7
6
6
,

 
 
1
2
1
,

 
 
1
4
,

 
 
1
0
4
3
,

 
 
7
,

 
 
1
,

 
 
6
2
3
,

 
 
7
0
4
,

 
 
9
9
,

 
 
6
,

 
 
2
1
2
,

 
 
7
7
6
8
,

 
 
2
,

 
 
5
1
2
,

 
 
1
7
8
0
,

 
 
3
,

 
 
7
,

 
 
1
,

 
 
1
4
9
4
3
,

 
 
4
8
1
,

 
 
3
7
,

 
 
3
2
,

 
 
1
8
,

 
 
5
7
0
2
,

 
 
1
4
9
4
4
,

 
 
1
6
,

 
 
6
0
,

 
 
2
,

 
 
3
7
1
9
,

 
 
2
1
7
4
]
,

 
[
2
7
4
9
,

 
 
4
4
,

 
 
1
,

 
 
5
1
7
,

 
 
2
,

 
 
1
,

 
 
4
9
8
9
,

 
 
2
4
2
9
,

 
 
3
,

 
 
1
1
8
6
,

 
 
2
1
,

 
 
6
,

 
 
3
5
4
3
,

 
 
5
0
3
,

 
 
2
3
,

 
 
2
9
4
4
,

 
 
5
,

 
 
6
3
4
,

 
 
1
1
9
,

 
 
3
8
,

 
 
2
,

 
 
1
,

 
 
5
7
0
3
,

 
 
3
,

 
 
6
1
,

 
 
1
6
6
1
,

 
 
6
5
7
,

 
 
2
,

 
 
1
,

 
 
5
2
,

 
 
6
9
0
,

 
 
1
0
8
0
3
]
,

 
[
1
,

 
 
2
8
0
3
,

 
 
2
9
8
,

 
 
2
,

 
 
1
9
0
6
,

 
 
2
1
3
3
,

 
 
2
5
3
3
,

 
 
2
,

 
 
6
,

 
 
1
0
0
5
,

 
 
1
9
7
8
,

 
 
1
9
,

 
 
2
2
3
4
,

 
 
3
9
,

 
 
3
,

 
 
2
,

 
 
3
7
,

 
 
1
3
8
4
,

 
 
5
5
5
,

 
 
4
,

 
 
1
2
6
,

 
 
2
2
,

 
 
1
6
,

 
 
1
5
,

 
 
4
2
0
,

 
 
3
,

 
 
1
5
3
,

 
 
1
5
,

 
 
6
4
,

 
 
1
0
3
6
,

 
 
1
9
2
,

 
 
1
3
,

 
 
6
,

 
 
3
7
4
,

 
 
2
,

 
 
3
9
9
1
,

 
 
2
3
,

 
 
1
,

 
 
6
0
5
3
,

 
 
2
,

 
 
1
0
,

 
 
6
6
4
,

 
 
5
4
,

 
 
7
7
6
9
,

 
 
2
,

 
 
1
5
,

 
 
3
8
2
7
]
,

 
[
4
0
0
,

 
 
4
4
,

 
 
6
5
5
4
,

 
 
2
6
,

 
 
6
8
2
,

 
 
3
,

 
 
6
9
,

 
 
1
,

 
 
5
1
7
,

 
 
2
2
9
,

 
 
7
6
6
3
,

 
 
4
,

 
 
9
2
1
,

 
 
1
8
0
,

 
 
3
9
,

 
 
7
1
0
0
,

 
 
1
5
,

 
 
9
9
2
,

 
 
1
6
,

 
 
6
0
,

 
 
2
5
5
6
,

 
 
3
7
,

 
 
2
1
8
3
,

 
 
7
,

 
 
1
5
,

 
 
8
6
0
1
]
,

 
[
3
4
,
 
5
3
2
,
 
2
5
9
7
,
 
2
,
 
3
2
,
 
1
,
 
2
8
3
9
,
 
3
,
 
5
1
,
 
5
0
2
,
 
1
3
,
 
7
6
5
1
,
 
4
4
2
]
,

 
[
8
2
,
 
1
1
4
,
 
2
4
3
6
,
 
5
,
 
9
6
,
 
1
1
]
,

 
[
2
1
,

 
 
1
9
1
,

 
 
5
0
1
4
,

 
 
9
9
5
,

 
 
1
5
,

 
 
1
0
8
0
4
,

 
 
2
4
,

 
 
1
,

 
 
2
7
7
,

 
 
4
,

 
 
1
,

 
 
1
5
4
,

 
 
9
0
9
,

 
 
2
,

 
 
1
5
,

 
 
7
8
8
,

 
 
1
4
,

 
 
1
4
9
4
5
,

 
 
4
,

 
 
3
5
5
]
,

 
[
1
8
,

 
 
7
7
7
0
,

 
 
1
3
,

 
 
6
7
,

 
 
8
5
6
,

 
 
2
,

 
 
2
8
7
,

 
 
2
5
,

 
 
5
,

 
 
3
2
6
,

 
 
6
,

 
 
3
2
5
,

 
 
1
5
4
5
,

 
 
1
7
,

 
 
3
2
,

 
 
1
2
5
1
,

 
 
2
2
4
,

 
 
5
1
,

 
 
3
3
3
6
]
,

 
[
4
8
,
 
2
0
6
,
 
1
8
2
,
 
1
,
 
9
2
5
,
 
1
9
,
 
2
0
8
,
 
2
2
1
2
,
 
4
,
 
1
5
,
 
9
6
5
]
,

 
[
1
,

 
 
3
2
8
,

 
 
8
,

 
 
5
2
,

 
 
6
,

 
 
2
2
7
,

 
 
3
,

 
 
3
8
,

 
 
2
3
,

 
 
3
8
,

 
 
1
,

 
 
7
7
7
1
,

 
 
2
0
7
,

 
 
1
4
9
,

 
 
4
,

 
 
5
2
4
,

 
 
6
6
2
,

 
 
5
0
5
,

 
 
5
2
4
,

 
 
2
,

 
 
1
7
5
3
,

 
 
3
,

 
 
7
5
2
,

 
 
1
3
,

 
 
3
7
8
,

 
 
5
2
8
,

 
 
3
,

 
 
9
9
1
,

 
 
1
4
9
4
6
,

 
 
3
,

 
 
1
2
4
4
5
,

 
 
8
7
,

 
 
1
,

 
 
1
4
0
9
]
,

 
.
.
.
]
</pre>
*
s
t
o
p
 
w
o
r
d
*




분
석
에
 
큰
 
의
미
가
 
없
는
 
단
어
를
 
지
칭
.
 
영
어
에
서
 
i
s
,
 
t
h
e
,
 
a
,
 
w
i
l
l
등
 
문
장
을
 
구
성
하
는
 
필
수
 
문
법
 
요
소
이
나
 
문
맥
적
으
로
 
큰
 
의
미
가
 
없
는
 
단
어
.




텍
스
트
에
 
빈
번
하
게
 
나
타
나
 
중
요
한
 
단
어
로
 
인
지
되
는
 
오
류
 
우
려
.
 
의
미
 
없
는
 
단
어
를
 
제
거
하
는
 
전
처
리
 
작
업
.



```python
#
 
i
m
p
o
r
t
 
n
l
t
k


#
 
s
t
o
p
w
o
r
d
s
 
=
 
n
l
t
k
.
c
o
r
p
u
s
.
s
t
o
p
w
o
r
d
s
.
w
o
r
d
s
(
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


#
 
f
o
r
 
s
e
n
t
e
n
c
e
 
i
n
 
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
:

#
 
 
 
 
 
f
i
l
t
e
r
e
d
_
w
o
r
d
s
=
[
]

 
 
 
 

#
 
 
 
 
 
f
o
r
 
w
o
r
d
 
i
n
 
s
e
n
t
e
n
c
e
:

#
 
 
 
 
 
 
 
 
 
w
o
r
d
=
w
o
r
d
.
l
o
w
e
r
(
)

#
 
 
 
 
 
i
f
 
w
o
r
d
 
n
o
t
 
i
n
 
s
t
o
p
w
o
r
d
s
:

#
 
 
 
 
 
 
 
 
 
f
i
l
t
e
r
e
d
_
w
o
r
d
s
.
a
p
p
e
n
d
(
w
o
r
d
)

 
 
 
 
 
 
 
 

#
 
t
e
x
t
.
a
p
p
e
n
d
(
f
i
l
t
e
r
e
d
_
w
o
r
d
s
)
```


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
2
6
,
 
3
3
3
4
,
 
1
3
9
,
 
1
2
9
5
,
 
2
2
,
 
3
6
,
 
2
8
5
,
 
2
,
 
6
4
2
6
,
 
1
,
.
.
.

1
 
 
 
 
 
 
 
 
[
1
1
,
 
9
0
,
 
1
2
8
,
 
7
2
5
,
 
4
,
 
2
2
,
 
9
,
 
1
,
 
5
9
6
6
,
 
8
0
,
 
2
8
,
 
.
.
.

2
 
 
 
 
 
 
 
 
[
7
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
3
,
 
8
,
 
6
,
 
6
9
4
,
 
5
9
6
7
,
 
5
6
0
,
 
2
4
,
 
1
9
.
.
.

3
 
 
 
 
 
 
 
 
[
1
2
0
,
 
5
6
8
,
 
2
5
,
 
7
6
6
,
 
1
6
,
 
3
4
,
 
2
1
6
,
 
2
4
,
 
7
5
4
,
 
4
1
7
6
.
.
.

4
 
 
 
 
 
 
 
 
[
1
2
2
9
,
 
1
6
0
,
 
7
3
5
,
 
2
0
,
 
7
5
,
 
6
9
4
,
 
1
,
 
5
2
1
4
,
 
1
4
6
4
,
 
1
.
.
.

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

2
7
9
6
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
3
2
,
 
2
6
,
 
2
5
,
 
5
2
,
 
1
,
 
1
8
6
0
3
,
 
1
7
,
 
1
0
,
 
5
0
0
]

2
7
9
6
7
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
5
,
 
1
0
4
5
,
 
1
1
0
,
 
2
7
,
 
6
,
 
5
7
4
,
 
8
1
7
]

2
7
9
6
8
 
 
 
 
[
1
1
,
 
2
5
,
 
6
7
2
,
 
1
1
1
2
,
 
9
,
 
5
3
,
 
8
0
,
 
7
2
0
8
,
 
6
,
 
1
4
0
2
,
 
.
.
.

2
7
9
6
9
 
 
 
 
[
2
8
,
 
2
6
,
 
1
6
,
 
1
1
,
 
1
2
3
,
 
5
,
 
5
2
,
 
2
7
3
,
 
4
,
 
2
9
7
,
 
1
,
 
6
.
.
.

2
7
9
7
0
 
 
 
 
[
1
0
9
,
 
1
8
5
6
3
,
 
2
9
4
5
0
,
 
3
,
 
2
9
4
5
1
,
 
6
6
4
7
,
 
1
6
,
 
5
4
,
 
2
,
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
 
2
7
9
7
1
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
2
9
4
5
1
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
8
6
1
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
```

<pre>
<
s
e
a
b
o
r
n
.
a
x
i
s
g
r
i
d
.
F
a
c
e
t
G
r
i
d
 
a
t
 
0
x
7
f
9
1
5
d
7
7
5
e
5
0
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
2
6
,
 
3
3
3
4
,
 
1
3
9
,
 
1
2
9
5
,
 
2
2
,
 
3
6
,
 
2
8
5
,
 
2
,
 
6
4
2
6
,
 
1
,
.
.
.

1
 
 
 
 
 
 
 
 
[
1
1
,
 
9
0
,
 
1
2
8
,
 
7
2
5
,
 
4
,
 
2
2
,
 
9
,
 
1
,
 
5
9
6
6
,
 
8
0
,
 
2
8
,
 
.
.
.

2
 
 
 
 
 
 
 
 
[
7
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
3
,
 
8
,
 
6
,
 
6
9
4
,
 
5
9
6
7
,
 
5
6
0
,
 
2
4
,
 
1
9
.
.
.

3
 
 
 
 
 
 
 
 
[
1
2
0
,
 
5
6
8
,
 
2
5
,
 
7
6
6
,
 
1
6
,
 
3
4
,
 
2
1
6
,
 
2
4
,
 
7
5
4
,
 
4
1
7
6
.
.
.

4
 
 
 
 
 
 
 
 
[
1
2
2
9
,
 
1
6
0
,
 
7
3
5
,
 
2
0
,
 
7
5
,
 
6
9
4
,
 
1
,
 
5
2
1
4
,
 
1
4
6
4
,
 
1
.
.
.

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

2
7
9
6
6
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
3
2
,
 
2
6
,
 
2
5
,
 
5
2
,
 
1
,
 
1
8
6
0
3
,
 
1
7
,
 
1
0
,
 
5
0
0
]

2
7
9
6
7
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
[
5
,
 
1
0
4
5
,
 
1
1
0
,
 
2
7
,
 
6
,
 
5
7
4
,
 
8
1
7
]

2
7
9
6
8
 
 
 
 
[
1
1
,
 
2
5
,
 
6
7
2
,
 
1
1
1
2
,
 
9
,
 
5
3
,
 
8
0
,
 
7
2
0
8
,
 
6
,
 
1
4
0
2
,
 
.
.
.

2
7
9
6
9
 
 
 
 
[
2
8
,
 
2
6
,
 
1
6
,
 
1
1
,
 
1
2
3
,
 
5
,
 
5
2
,
 
2
7
3
,
 
4
,
 
2
9
7
,
 
1
,
 
6
.
.
.

2
7
9
7
0
 
 
 
 
[
1
0
9
,
 
1
8
5
6
3
,
 
2
9
4
5
0
,
 
3
,
 
2
9
4
5
1
,
 
6
6
4
7
,
 
1
6
,
 
5
4
,
 
2
,
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
 
2
7
9
7
1
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
1
0
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
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
9
8
,
 
 
 
 
 
1
,
 
 
 
4
4
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
6
,
 
 
 
4
5
0
,
 
 
2
4
5
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
3
5
3
,
 
 
 
5
2
6
,
 
 
3
1
0
1
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
1
3
7
8
7
,
 
 
 
4
8
2
,
 
 
 
5
4
1
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
4
,
 
 
 
 
2
8
,
 
1
6
7
4
8
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
1
,
 
 
 
1
8
9
,
 
 
1
5
8
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
i
n
t
3
2
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
2
,
t
e
s
t
2
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
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
9
8
,
 
 
 
 
 
1
,
 
 
 
4
4
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
6
,
 
 
 
4
5
0
,
 
 
2
4
5
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
3
5
3
,
 
 
 
5
2
6
,
 
 
3
1
0
1
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
9
0
,
 
1
8
1
0
1
,
 
1
2
0
5
5
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
6
1
,
 
 
8
0
6
9
,
 
 
 
5
2
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
9
,
 
 
 
 
 
2
,
 
 
6
0
1
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
i
n
t
3
2
)
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
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
4
2
0
,
 
 
 
 
 
4
,
 
 
2
3
1
5
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
2
,
 
 
 
 
 
6
,
 
 
7
0
2
3
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
1
,
 
 
2
1
6
1
,
 
 
4
4
7
4
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
1
3
7
8
7
,
 
 
 
4
8
2
,
 
 
 
5
4
1
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
4
,
 
 
 
 
2
8
,
 
1
6
7
4
8
]
,

 
 
 
 
 
 
 
[
 
 
 
 
0
,
 
 
 
 
 
0
,
 
 
 
 
 
0
,
 
.
.
.
,
 
 
 
 
 
1
,
 
 
 
1
8
9
,
 
 
1
5
8
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
i
n
t
3
2
)
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
a
u
t
h
o
r
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
a
u
t
h
o
r
"
]
)
```

*
c
a
l
l
b
a
c
k




미
니
 
배
치
의
 
처
리
별
 
또
는
 
에
폭
별
로
 
지
정
한
 
처
리
를
 
빠
르
게
 
진
행
 
가
능




조
기
 
종
료




모
델
의
 
정
기
적
인
 
저
장
(
검
증
 
데
이
터
에
서
의
 
평
가
가
 
가
장
 
좋
은
 
모
델
을
 
남
길
 
수
도
 
있
음
)




학
습
률
 
스
케
줄
링
(
연
산
 
진
행
에
 
따
른
 
학
습
률
 
조
정
)




로
그
 
및
 
가
시
화
 
가
능




교
차
 
검
증
의
 
조
기
 
종
료
를
 
위
해
 
c
a
l
l
b
a
c
k
의
 
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
을
 
이
용
하
였
습
니
다
.




p
a
t
i
e
n
c
e
를
 
3
/
5
/
8
의
 
경
우
로
 
나
누
어
 
정
확
도
 
향
상
과
의
 
관
계
를
 
알
아
 
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
2
4
)

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
2
,
t
r
a
i
n
[
'
a
u
t
h
o
r
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
2
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
2
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

 
 
 
 
y
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
[
'
a
u
t
h
o
r
'
]
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
[
'
a
u
t
h
o
r
'
]
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
3
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
1
0
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
3
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
1
0
0
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
]
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
2
)
/
5
```

<pre>
2
0
2
2
-
0
4
-
1
1
 
0
7
:
4
6
:
2
0
.
9
1
5
6
2
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
0
8
5
7
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
0
9
3
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
1
0
5
5
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
1
1
6
6
1
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
1
2
3
5
1
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
4
-
1
1
 
0
7
:
4
6
:
2
1
.
0
1
2
9
9
1
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
4
-
1
1
 
0
7
:
4
6
:
2
2
.
7
7
5
4
2
1
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
4
-
1
1
 
0
7
:
4
6
:
2
2
.
7
7
6
3
3
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
4
-
1
1
 
0
7
:
4
6
:
2
2
.
7
7
7
0
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
4
-
1
1
 
0
7
:
4
6
:
2
2
.
7
7
7
6
7
1
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
4
-
1
1
 
0
7
:
4
6
:
2
3
.
4
1
7
4
8
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
4
-
1
1
 
0
7
:
4
6
:
2
5
.
5
2
0
8
4
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
2
3
/
1
2
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
 
5
s
 
1
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
 
1
.
0
5
5
9
 
-
 
a
c
c
:
 
0
.
4
4
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
9
6
1
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
4
9
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

1
2
3
/
1
2
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
 
1
s
 
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
8
2
7
7
 
-
 
a
c
c
:
 
0
.
6
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
7
7
7
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
2
2
1

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
2
3
/
1
2
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
 
1
s
 
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
6
1
2
4
 
-
 
a
c
c
:
 
0
.
7
4
1
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
6
8
0
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
0
9
4

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
2
3
/
1
2
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
 
1
s
 
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
4
5
1
9
 
-
 
a
c
c
:
 
0
.
8
3
3
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
7
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
7
6
1
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

1
2
3
/
1
2
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
 
1
s
 
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
4
6
4
5
 
-
 
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
 
-
 
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
0
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
7
5
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
2
3
/
1
2
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
 
1
s
 
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
2
7
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
1
3
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
5
3
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
7
8
7
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

1
2
3
/
1
2
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
 
1
s
 
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
9
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
3
9
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
5
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
7
9
9
3

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
2
3
/
1
2
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
 
1
s
 
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
4
6
7
 
-
 
a
c
c
:
 
0
.
9
5
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
5
8
3
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
5
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

1
2
3
/
1
2
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
 
1
s
 
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
6
6
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
7
9
9
3

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
6
0
2
 
-
 
a
c
c
:
 
0
.
4
4
2
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
9
6
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
5
3
4
5

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
2
3
/
1
2
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
 
1
s
 
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
8
2
4
5
 
-
 
a
c
c
:
 
0
.
6
0
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
7
7
2
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
6
2
5
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
2
3
/
1
2
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
 
1
s
 
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
6
6
5
9
 
-
 
a
c
c
:
 
0
.
6
9
9
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
7
2
4
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
6
5
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
2
3
/
1
2
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
 
1
s
 
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
5
1
0
9
 
-
 
a
c
c
:
 
0
.
7
8
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
6
8
8
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
6
8
7
4

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
2
3
/
1
2
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
 
1
s
 
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
3
7
1
3
 
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
7
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
7
2
2
2

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
2
3
/
1
2
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
 
1
s
 
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
2
7
6
5
 
-
 
a
c
c
:
 
0
.
8
9
7
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
7
2
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
7
1
9
6

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
2
3
/
1
2
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
 
1
s
 
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
2
1
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
2
4
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
7
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
7
3
8
3

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
6
3
0
 
-
 
a
c
c
:
 
0
.
4
4
2
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
9
4
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
5
4
9
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

1
2
3
/
1
2
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
 
1
s
 
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
7
9
6
7
 
-
 
a
c
c
:
 
0
.
6
4
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
7
2
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
6
9
2
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

1
2
3
/
1
2
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
 
1
s
 
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
5
3
7
8
 
-
 
a
c
c
:
 
0
.
7
8
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
6
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
:
 
0
.
7
4
4
1

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
2
3
/
1
2
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
 
1
s
 
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
7
8
3
 
-
 
a
c
c
:
 
0
.
8
6
1
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
5
4
9
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
7
6
0

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
2
3
/
1
2
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
 
1
s
 
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
5
7
3
 
-
 
a
c
c
:
 
0
.
8
6
9
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
6
8
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
7
1
0
9

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
2
3
/
1
2
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
 
1
s
 
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
3
1
2
4
 
-
 
a
c
c
:
 
0
.
8
9
9
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
9
9
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
7
7
6
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

1
2
3
/
1
2
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
 
1
s
 
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
9
2
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
5
1
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
8
0
6
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

1
2
3
/
1
2
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
 
1
s
 
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
4
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
5
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
 
0
.
5
6
6
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
0
1
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

1
2
3
/
1
2
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
 
1
s
 
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
1
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
6
3
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
5
6
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
7
9
9
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

1
2
3
/
1
2
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
 
1
s
 
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
9
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
6
1
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
7
9
9
0

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
6
1
8
 
-
 
a
c
c
:
 
0
.
4
3
8
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
9
9
3
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
5
1
7
1

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
2
3
/
1
2
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
 
1
s
 
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
8
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
5
8
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
7
9
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
6
1
1
8

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
2
3
/
1
2
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
 
1
s
 
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
6
7
0
1
 
-
 
a
c
c
:
 
0
.
6
8
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
7
2
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
6
5
8
3

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
2
3
/
1
2
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
 
1
s
 
1
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
5
2
2
3
 
-
 
a
c
c
:
 
0
.
7
8
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
6
7
7
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
0
8
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

1
2
3
/
1
2
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
 
1
s
 
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
9
3
7
 
-
 
a
c
c
:
 
0
.
8
4
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
6
7
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
7
3
2
1

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
2
3
/
1
2
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
 
1
s
 
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
2
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
8
9
9
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
6
2
0
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
5
7
2

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
2
3
/
1
2
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
 
1
s
 
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
7
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
6
0
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
6
7
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
7
1
4
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

1
2
3
/
1
2
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
 
1
s
 
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
2
7
9
9
 
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
6
3
0
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
6
1
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

1
2
3
/
1
2
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
 
1
s
 
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
7
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
4
7
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
6
6
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
5
9
7

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

1
2
3
/
1
2
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
 
1
.
0
6
3
2
 
-
 
a
c
c
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
l
o
s
s
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
a
c
c
:
 
0
.
5
5
9
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

1
2
3
/
1
2
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
 
1
s
 
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
8
7
2
7
 
-
 
a
c
c
:
 
0
.
6
2
6
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
1
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
6
4
3
9

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
2
3
/
1
2
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
 
1
s
 
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
6
6
6
3
 
-
 
a
c
c
:
 
0
.
7
3
3
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
6
9
5
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
9
7

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
2
3
/
1
2
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
 
1
s
 
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
4
5
5
7
 
-
 
a
c
c
:
 
0
.
8
3
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
5
5
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
2
1

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
2
3
/
1
2
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
 
1
s
 
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
2
9
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
0
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
5
0
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
8
1
2
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

1
2
3
/
1
2
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
 
1
s
 
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
2
0
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
3
3
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
5
1
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
8
0
2
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

1
2
3
/
1
2
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
 
1
s
 
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
5
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
5
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
1
7
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
2
0
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

1
2
3
/
1
2
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
 
1
s
 
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
6
4
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
7
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
8
1
5
3

</pre>

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
2
4
)

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
2
,
t
r
a
i
n
[
'
a
u
t
h
o
r
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
2
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
2
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

 
 
 
 
y
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
[
'
a
u
t
h
o
r
'
]
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
[
'
a
u
t
h
o
r
'
]
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
5
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
1
0
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
3
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
1
0
0
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
]
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
2
)
/
5
```

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
6
8
1
 
-
 
a
c
c
:
 
0
.
4
2
1
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
 
1
.
0
1
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
5
6
1
8

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
2
3
/
1
2
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
 
1
s
 
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
8
5
2
6
 
-
 
a
c
c
:
 
0
.
6
1
9
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
7
8
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
6
6
1
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

1
2
3
/
1
2
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
 
1
s
 
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
5
8
7
5
 
-
 
a
c
c
:
 
0
.
7
7
2
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
5
8
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
7
6
2
0

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
2
3
/
1
2
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
 
1
s
 
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
6
7
0
 
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
5
2
0
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
8
9
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
2
3
/
1
2
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
 
1
s
 
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
2
4
7
7
 
-
 
a
c
c
:
 
0
.
9
1
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
 
0
.
4
7
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
1
8
4

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
2
3
/
1
2
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
 
1
s
 
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
7
7
0
 
-
 
a
c
c
:
 
0
.
9
4
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
4
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
8
1
4
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

1
2
3
/
1
2
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
 
1
s
 
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
3
5
7
 
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
5
2
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
8
2
2
3

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
2
3
/
1
2
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
 
1
s
 
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
0
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
6
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
6
2
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
1
5
6

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

1
2
3
/
1
2
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
 
1
s
 
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
0
5
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
5
7
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
1
9
2

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

1
2
3
/
1
2
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
 
1
s
 
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
6
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
7
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
5
8
3
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
1
7
7

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

1
2
3
/
1
2
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
 
1
.
0
6
9
8
 
-
 
a
c
c
:
 
0
.
4
3
1
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
 
1
.
0
2
4
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
5
0
5
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
2
3
/
1
2
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
 
1
s
 
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
8
6
5
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
7
7
3
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
2
6
9

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
2
3
/
1
2
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
 
1
s
 
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
6
6
0
3
 
-
 
a
c
c
:
 
0
.
6
7
6
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
7
1
0
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
6
6
3
7

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
2
3
/
1
2
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
 
1
s
 
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
5
8
1
9
 
-
 
a
c
c
:
 
0
.
7
4
7
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
6
2
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
7
3
9
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
2
3
/
1
2
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
 
1
s
 
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
7
5
7
 
-
 
a
c
c
:
 
0
.
8
5
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
5
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
7
8
4
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
2
3
/
1
2
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
 
1
s
 
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
2
5
7
6
 
-
 
a
c
c
:
 
0
.
9
0
8
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
5
3
6
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
0
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

1
2
3
/
1
2
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
 
1
s
 
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
8
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
3
7
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
5
2
9
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
1
8
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

1
2
3
/
1
2
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
 
1
s
 
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
5
7
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
0
5
9

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

1
2
3
/
1
2
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
 
1
s
 
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
0
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
6
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
 
0
.
6
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
7
9
5
2

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

1
2
3
/
1
2
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
 
1
s
 
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
8
2
5
 
-
 
a
c
c
:
 
0
.
9
7
4
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
6
1
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
8
1
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

1
2
3
/
1
2
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
 
1
s
 
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
6
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
6
1
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
7
8
1
4

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

1
2
3
/
1
2
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
 
1
s
 
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
7
7
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
6
2
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
8
1
5
4

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
5
5
6
 
-
 
a
c
c
:
 
0
.
4
4
6
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
9
4
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
5
3
0
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

1
2
3
/
1
2
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
 
1
s
 
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
8
1
0
2
 
-
 
a
c
c
:
 
0
.
6
0
8
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
7
8
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
6
3
0
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

1
2
3
/
1
2
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
 
1
s
 
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
6
9
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
8
3
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
7
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
6
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

1
2
3
/
1
2
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
 
1
s
 
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
5
2
2
0
 
-
 
a
c
c
:
 
0
.
7
8
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
6
9
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
6
9
5
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

1
2
3
/
1
2
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
 
1
s
 
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
4
0
2
0
 
-
 
a
c
c
:
 
0
.
8
4
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
7
2
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
6
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

1
2
3
/
1
2
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
 
1
s
 
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
1
1
1
 
-
 
a
c
c
:
 
0
.
8
8
3
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
7
4
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
7
1
0
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

1
2
3
/
1
2
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
 
1
s
 
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
2
3
7
6
 
-
 
a
c
c
:
 
0
.
9
1
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
7
5
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
7
2
4
5

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
2
3
/
1
2
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
 
1
s
 
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
3
4
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
8
0
0
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
2
7
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

1
2
3
/
1
2
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
 
1
s
 
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
5
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
4
6
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
8
2
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
7
3
7
7

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
5
7
2
 
-
 
a
c
c
:
 
0
.
4
4
0
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
2
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
5
7
3
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

1
2
3
/
1
2
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
 
1
s
 
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
8
7
0
9
 
-
 
a
c
c
:
 
0
.
6
2
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
7
9
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
6
5
9
1

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
2
3
/
1
2
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
 
1
s
 
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
6
2
2
1
 
-
 
a
c
c
:
 
0
.
7
5
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
6
4
5
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
2
1
7

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
2
3
/
1
2
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
 
1
s
 
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
4
4
9
6
 
-
 
a
c
c
:
 
0
.
8
3
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
6
7
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
7
1
1
4

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
2
3
/
1
2
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
 
1
s
 
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
3
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
8
8
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
5
6
8
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
8
5
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

1
2
3
/
1
2
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
 
1
s
 
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
2
4
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
1
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
5
6
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
7
8
7
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

1
2
3
/
1
2
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
 
1
s
 
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
2
0
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
3
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
5
9
4
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
7
5
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

1
2
3
/
1
2
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
 
1
s
 
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
5
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
4
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
6
2
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
7
8
2
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

1
2
3
/
1
2
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
 
1
s
 
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
1
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
6
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
6
5
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
7
8
2
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

1
2
3
/
1
2
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
 
1
s
 
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
0
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
6
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
 
0
.
7
0
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
7
5
8
7

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

1
2
3
/
1
2
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
 
1
.
0
4
0
4
 
-
 
a
c
c
:
 
0
.
4
5
3
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
2
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
5
3
6
1

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
2
3
/
1
2
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
 
1
s
 
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
7
8
4
4
 
-
 
a
c
c
:
 
0
.
5
9
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
7
7
8
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
6
1
3
0

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
2
3
/
1
2
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
 
1
s
 
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
6
7
2
5
 
-
 
a
c
c
:
 
0
.
6
6
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
9
3
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
5
6
1
7

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
2
3
/
1
2
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
 
1
s
 
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
8
4
1
5
 
-
 
a
c
c
:
 
0
.
5
9
9
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
1
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
6
0
0
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

1
2
3
/
1
2
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
 
1
s
 
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
5
9
1
0
 
-
 
a
c
c
:
 
0
.
7
0
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
7
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
6
4
2
1

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
2
3
/
1
2
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
 
1
s
 
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
4
9
2
5
 
-
 
a
c
c
:
 
0
.
7
8
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
7
5
3
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
6
6
8
2

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
2
3
/
1
2
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
 
1
s
 
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
4
7
9
9
 
-
 
a
c
c
:
 
0
.
8
0
3
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
2
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
6
0
9
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

1
2
3
/
1
2
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
 
1
s
 
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
4
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
8
3
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
8
1
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
6
7
7
1

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

1
2
3
/
1
2
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
 
1
s
 
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
3
2
3
4
 
-
 
a
c
c
:
 
0
.
8
7
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
8
9
0
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
6
7
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

1
2
3
/
1
2
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
 
1
s
 
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
2
7
3
1
 
-
 
a
c
c
:
 
0
.
8
9
4
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
:
 
0
.
6
7
0
5

</pre>

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
2
4
)

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
2
,
t
r
a
i
n
[
'
a
u
t
h
o
r
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
2
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
2
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

 
 
 
 
y
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
[
'
a
u
t
h
o
r
'
]
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
[
'
a
u
t
h
o
r
'
]
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
8
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
1
0
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
3
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
1
0
0
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
]
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
2
)
/
5
```

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
6
7
5
 
-
 
a
c
c
:
 
0
.
4
2
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
9
8
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
5
2
8
1

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
2
3
/
1
2
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
 
1
s
 
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
8
4
2
3
 
-
 
a
c
c
:
 
0
.
5
7
9
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
7
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
5
8
9
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
2
3
/
1
2
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
 
1
s
 
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
6
8
1
2
 
-
 
a
c
c
:
 
0
.
6
4
7
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
7
8
9
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
0
7
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

1
2
3
/
1
2
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
 
1
s
 
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
5
7
9
5
 
-
 
a
c
c
:
 
0
.
7
0
8
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
7
2
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
6
5
4
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

1
2
3
/
1
2
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
 
1
s
 
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
4
9
4
9
 
-
 
a
c
c
:
 
0
.
7
8
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
7
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
6
9
5
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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
8
4
0
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
7
1
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
6
9
0
2

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
2
3
/
1
2
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
 
1
s
 
1
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
2
3
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
1
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
6
4
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
7
4
7
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

1
2
3
/
1
2
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
 
1
s
 
1
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
9
5
9
 
-
 
a
c
c
:
 
0
.
9
3
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
6
3
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
7
9
1

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
5
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
6
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
7
8
6
5

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

1
2
3
/
1
2
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
 
1
s
 
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
0
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
6
7
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
7
0
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
9
2
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

1
2
3
/
1
2
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
 
1
s
 
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
7
6
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
7
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
7
9
9
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

1
2
3
/
1
2
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
 
1
s
 
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
6
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
8
1
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
7
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
7
9
7
5

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

1
2
3
/
1
2
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
 
1
s
 
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
8
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
8
1
8
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
9
8
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

1
2
3
/
1
2
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
 
1
s
 
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
0
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
5
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
7
9
2
1

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
9
0
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
9
0
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
7
9
3
4

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
9
6
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
9
2
4

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

1
2
3
/
1
2
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
 
1
.
0
5
6
8
 
-
 
a
c
c
:
 
0
.
4
3
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
9
3
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
5
4
3
7

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
2
3
/
1
2
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
 
1
s
 
1
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
8
4
0
3
 
-
 
a
c
c
:
 
0
.
5
7
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
7
9
9
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
5
8
2
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

1
2
3
/
1
2
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
 
1
s
 
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
6
6
0
9
 
-
 
a
c
c
:
 
0
.
6
4
7
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
7
3
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
6
3
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

1
2
3
/
1
2
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
 
1
s
 
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
5
8
0
0
 
-
 
a
c
c
:
 
0
.
6
9
0
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
7
4
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
5
0
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

1
2
3
/
1
2
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
 
1
s
 
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
5
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
7
4
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
7
7
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
6
6
1
1

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
2
3
/
1
2
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
 
1
s
 
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
6
2
4
7
 
-
 
a
c
c
:
 
0
.
7
1
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
7
6
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
6
5
3
2

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
2
3
/
1
2
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
 
1
s
 
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
4
2
6
4
 
-
 
a
c
c
:
 
0
.
8
2
2
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
8
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
6
7
7
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

1
2
3
/
1
2
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
 
1
s
 
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
4
9
6
 
-
 
a
c
c
:
 
0
.
8
5
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
6
9
1
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

1
2
3
/
1
2
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
 
1
s
 
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
2
7
4
4
 
-
 
a
c
c
:
 
0
.
8
9
2
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
9
0
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
6
9
4
6

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

1
2
3
/
1
2
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
 
1
s
 
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
2
1
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
1
9
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
9
0
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
7
0
3
3

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

1
2
3
/
1
2
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
 
1
s
 
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
7
3
6
 
-
 
a
c
c
:
 
0
.
9
3
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
9
3
9
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
7
1
8
3

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
5
8
0
 
-
 
a
c
c
:
 
0
.
4
4
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
9
5
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
5
3
9
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

1
2
3
/
1
2
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
 
1
s
 
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
8
2
7
5
 
-
 
a
c
c
:
 
0
.
5
9
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
7
8
5
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
6
0
7
0

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
2
3
/
1
2
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
 
1
s
 
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
6
6
5
3
 
-
 
a
c
c
:
 
0
.
6
6
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
7
5
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
6
2
9
5

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
2
3
/
1
2
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
 
1
s
 
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
5
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
7
4
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
7
0
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
6
8
0
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
2
3
/
1
2
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
 
1
s
 
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
4
9
3
7
 
-
 
a
c
c
:
 
0
.
8
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
 
0
.
7
1
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
6
7
5
4

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
2
3
/
1
2
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
 
1
s
 
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
7
5
5
 
-
 
a
c
c
:
 
0
.
8
5
9
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
6
6
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
8
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

1
2
3
/
1
2
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
 
1
s
 
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
2
5
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
0
7
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
6
5
4
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
5
3
6

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
2
3
/
1
2
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
 
1
s
 
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
8
3
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
6
7
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
7
6
8
1

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

1
2
3
/
1
2
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
 
1
s
 
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
3
7
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
7
1
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
7
7
0
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

1
2
3
/
1
2
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
 
1
s
 
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
6
5
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
7
6
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
7
6
2
8

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

1
2
3
/
1
2
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
 
1
s
 
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
0
2
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
6
9
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
7
3
5
4

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
7
1
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
6
6
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

1
2
3
/
1
2
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
 
1
s
 
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
8
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
7
6
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
7
7
0
2

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

1
2
3
/
1
2
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
 
1
s
 
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
6
3
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
3
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
1
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
7
7
4
3

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

1
2
3
/
1
2
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
 
1
s
 
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
8
7
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
8
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
7
7
2
0

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

1
2
3
/
1
2
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
s
 
1
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
 
1
.
0
7
3
7
 
-
 
a
c
c
:
 
0
.
4
2
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
0
6
5
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
4
2
0
8

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
2
3
/
1
2
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
 
1
s
 
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
8
7
4
1
 
-
 
a
c
c
:
 
0
.
5
7
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
7
6
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
6
6
8
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

1
2
3
/
1
2
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
 
1
s
 
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
5
5
0
4
 
-
 
a
c
c
:
 
0
.
7
8
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
5
8
1
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
7
8
9

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
2
3
/
1
2
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
 
1
s
 
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
4
4
5
 
-
 
a
c
c
:
 
0
.
8
7
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
 
0
.
5
0
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
8
1
5
1

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
2
3
/
1
2
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
 
1
s
 
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
2
5
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
1
1
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
5
0
1
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
1
7
2

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
2
3
/
1
2
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
 
1
s
 
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
7
6
4
 
-
 
a
c
c
:
 
0
.
9
4
0
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
8
1
8
4

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
2
3
/
1
2
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
 
1
s
 
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
3
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
5
6
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
5
3
3
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
1
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
2
3
/
1
2
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
 
1
s
 
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
5
8
4
 
-
 
a
c
c
:
 
0
.
9
4
8
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
6
4
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
4
3
4

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

1
2
3
/
1
2
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
 
1
s
 
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
4
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
5
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
 
0
.
5
5
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
8
1
7
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

1
2
3
/
1
2
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
 
1
s
 
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
7
5
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
6
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
6
8
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
8
1
8
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

1
2
3
/
1
2
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
 
1
s
 
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
8
2
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
6
4
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
8
0
9
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

1
2
3
/
1
2
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
 
1
s
 
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
6
1
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
6
5
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
8
1
6
1

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
8
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
6
8
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
8
1
2
8

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

1
2
3
/
1
2
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
 
1
.
0
6
3
2
 
-
 
a
c
c
:
 
0
.
4
3
4
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
9
9
4
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
5
2
0
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

1
2
3
/
1
2
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
 
1
s
 
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
8
3
9
3
 
-
 
a
c
c
:
 
0
.
5
9
1
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
7
8
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
6
0
5
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
2
3
/
1
2
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
 
1
s
 
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
6
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
7
2
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
6
3
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
7
3
4
1

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
2
3
/
1
2
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
 
1
s
 
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
3
9
5
2
 
-
 
a
c
c
:
 
0
.
8
5
0
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
5
6
5
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
7
5
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

1
2
3
/
1
2
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
 
1
s
 
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
2
7
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
0
1
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
5
6
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
7
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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
5
8
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
9
5
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

1
2
3
/
1
2
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
 
1
s
 
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
5
1
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
6
0
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
7
9
8
5

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
2
3
/
1
2
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
 
1
s
 
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
1
3
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
3
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
6
8
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
7
9
1
6

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

1
2
3
/
1
2
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
 
1
s
 
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
8
7
7
 
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
6
8
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
7
9
8
0

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

1
2
3
/
1
2
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
 
1
s
 
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
6
8
1
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
0
2
3

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

1
2
3
/
1
2
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
 
1
s
 
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
6
2
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
7
7
9
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
9
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

1
2
3
/
1
2
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
 
1
s
 
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
3
8
8
0
 
-
 
a
c
c
:
 
0
.
8
5
5
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
4
9
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
1
2
5

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

1
2
3
/
1
2
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
 
1
s
 
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
9
8
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
5
6
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
8
1
8
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

1
2
3
/
1
2
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
 
1
s
 
1
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
8
6
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
2
9
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
1
0
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

1
2
3
/
1
2
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
 
1
s
 
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
4
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
8
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
6
5
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
8
1
1
7

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

1
2
3
/
1
2
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
 
1
s
 
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
3
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
1
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
6
9
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
8
0
4
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

1
2
3
/
1
2
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
 
1
s
 
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
2
8
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
7
9
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
8
0
6
1

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

1
2
3
/
1
2
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
 
1
s
 
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
 
0
.
8
7
5
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
5
7

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

1
2
3
/
1
2
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
 
1
s
 
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
9
4
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
9
3
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
7
9
0
0

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

1
2
3
/
1
2
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
 
1
s
 
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
 
0
.
8
4
5
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
0
1
8

</pre>
S
T
O
P
 
W
O
R
D
를
 
사
용
하
는
 
경
우
 
결
과
를
 
r
e
s
u
l
t
의
 
r
o
w
수
가
 
증
가
하
는
 
것
을
 
감
안
하
여
 




a
 
=
 
n
p
.
d
e
l
e
t
e
(
r
e
s
u
l
t
,
 
8
3
9
2
,
 
0
)


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
 
a




로
 
바
꾸
어
 
주
어
야
 
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
s
p
o
o
k
y
-
a
u
t
h
o
r
-
i
d
e
n
t
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
z
i
p
'
)

s
u
b
```

<pre>
 
 
 
 
 
 
 
 
 
 
 
i
d
 
 
 
 
 
 
 
E
A
P
 
 
 
 
 
 
 
H
P
L
 
 
 
 
 
 
 
M
W
S

0
 
 
 
 
 
i
d
0
2
3
1
0
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

1
 
 
 
 
 
i
d
2
4
5
4
1
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

2
 
 
 
 
 
i
d
0
0
1
3
4
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

3
 
 
 
 
 
i
d
2
7
7
5
7
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

4
 
 
 
 
 
i
d
0
4
0
8
1
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
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
 
 
 
 
 
 
 
.
.
.
 
 
 
 
 
 
 
.
.
.

8
3
8
7
 
 
i
d
1
1
7
4
9
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

8
3
8
8
 
 
i
d
1
0
5
2
6
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

8
3
8
9
 
 
i
d
1
3
4
7
7
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

8
3
9
0
 
 
i
d
1
3
7
6
1
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8

8
3
9
1
 
 
i
d
0
4
2
8
2
 
 
0
.
4
0
3
4
9
4
 
 
0
.
2
8
7
8
0
8
 
 
0
.
3
0
8
6
9
8


[
8
3
9
2
 
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
 
 
 
 
 
 
 
E
A
P
 
 
 
 
 
 
 
H
P
L
 
 
 
 
 
 
 
M
W
S

0
 
 
 
 
 
i
d
0
2
3
1
0
 
 
0
.
0
0
8
7
2
8
 
 
0
.
1
1
8
5
0
0
 
 
0
.
8
7
2
7
7
2

1
 
 
 
 
 
i
d
2
4
5
4
1
 
 
0
.
9
9
6
6
1
4
 
 
0
.
0
0
1
2
0
9
 
 
0
.
0
0
2
1
7
8

2
 
 
 
 
 
i
d
0
0
1
3
4
 
 
0
.
0
1
5
5
8
3
 
 
0
.
9
6
1
5
6
4
 
 
0
.
0
2
2
8
5
3

3
 
 
 
 
 
i
d
2
7
7
5
7
 
 
0
.
9
4
7
6
9
4
 
 
0
.
0
3
3
0
8
6
 
 
0
.
0
1
9
2
1
9

4
 
 
 
 
 
i
d
0
4
0
8
1
 
 
0
.
9
8
1
2
5
4
 
 
0
.
0
0
3
7
1
4
 
 
0
.
0
1
5
0
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

8
3
8
7
 
 
i
d
1
1
7
4
9
 
 
0
.
7
3
9
2
6
0
 
 
0
.
0
2
5
4
3
4
 
 
0
.
2
3
5
3
0
6

8
3
8
8
 
 
i
d
1
0
5
2
6
 
 
0
.
0
0
2
9
2
0
 
 
0
.
0
2
7
6
6
3
 
 
0
.
9
6
9
4
1
7

8
3
8
9
 
 
i
d
1
3
4
7
7
 
 
0
.
2
7
3
6
1
7
 
 
0
.
0
5
4
5
0
6
 
 
0
.
6
7
1
8
7
7

8
3
9
0
 
 
i
d
1
3
7
6
1
 
 
0
.
0
9
7
4
3
6
 
 
0
.
0
1
2
2
3
7
 
 
0
.
8
9
0
3
2
7

8
3
9
1
 
 
i
d
0
4
2
8
2
 
 
0
.
0
0
9
0
4
3
 
 
0
.
9
8
1
5
1
8
 
 
0
.
0
0
9
4
3
9


[
8
3
9
2
 
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

총
 
6
가
지
의
 
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
 
s
c
o
r
e
 
개
선
 
순
위
는
 
다
음
과
 
같
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
 
낮
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




동
일
 
조
건
의
 
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
5
)
 
:
 
0
.
4
1
4
4
6
 
 
>
 
 
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
3
)
 
:
 
0
.
4
4
4
3
9
 
 
>
 
 
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
8
)
 
:
 
0
.
4
9
8
6
9




p
a
t
i
e
n
c
e
의
 
횟
수
를
 
늘
리
면
 
교
차
 
검
증
의
 
정
확
도
가
 
높
아
지
나
,
 
일
정
 
기
준
을
 
넘
으
면
 
s
c
o
r
e
가
 
미
개
선
 
되
는
 
것
으
로
 
보
아
 
과
대
 
적
합
이
 
발
생
했
음
을
 
예
상
할
 
수
 
있
습
니
다
.




동
일
 
조
건
,
 
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
의
 
p
a
t
i
e
n
c
e
를
 
5
로
 
고
정
하
였
을
 
때
,
 
S
T
O
P
 
W
O
R
D
S
 
:
 
0
.
5
4
5
6
5
 
>
 
S
t
e
m
m
i
n
g
 
:
 
0
.
5
7
5
0
2
 
>
 
G
r
i
d
S
e
a
r
c
h
C
V
 
:
 
0
.
6
9
0
3
4
 
의
 
결
과
를
 
얻
었
습
니
다
.




그
러
나
 
모
두
 
적
용
하
지
 
않
았
을
 
때
 
보
다
 
S
C
O
R
E
가
 
미
개
선
 
되
었
습
니
다
.




S
T
O
P
 
W
O
R
D
S
의
 
경
우
 
미
개
선
 
이
유
는
 
i
s
,
 
t
h
e
,
 
a
,
 
w
i
l
l
등
 
문
장
을
 
구
성
하
는
 
문
법
 
등
이
 
t
r
a
i
n
 
d
a
t
a
의
 
t
e
x
t
 
c
o
l
u
m
n
의
 
의
미
를
 
조
금
씩
 
변
화
시
켜
 
정
확
도
를
 
향
상
하
는
데
 
도
움
이
 
되
었
던
 
것
으
로
 
보
입
니
다
.




S
t
e
m
m
i
n
g
의
 
경
우
 
미
개
선
 
이
유
는
 
역
시
 
단
어
의
 
원
형
을
 
찾
을
 
때
 
t
r
a
i
n
 
d
a
t
a
의
 
t
e
x
t
 
c
o
l
u
m
n
의
 
의
미
를
 
조
금
씩
 
변
화
시
켜
 
정
확
도
를
 
향
상
하
는
데
 
도
움
이
 
되
었
던
 
것
으
로
 
보
입
니
다
.




G
r
i
d
S
e
a
r
c
h
C
V
의
 
경
우
 
미
개
선
 
폭
이
 
가
장
 
컸
는
데
,
 
이
는
 
적
용
된
 
조
건
이
 
최
적
이
 
아
니
며
 
개
선
이
 
필
요
함
을
 
생
각
하
였
습
니
다
.

