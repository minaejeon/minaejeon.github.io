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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
1
.
 
t
r
a
i
n
.
c
s
v
 
:
 
학
습
 
데
이
터




i
d
 
:
 
샘
플
 
아
이
디




G
e
n
d
e
r
 
:
 
전
복
 
성
별




L
e
n
g
h
t
 
:
 
전
복
 
길
이




D
i
a
m
e
t
e
r
 
:
 
전
복
 
둘
레




H
e
i
g
h
t
 
:
 
전
복
 
키
 




W
h
o
l
e
 
:
 
W
e
i
g
h
t
 
:
 
전
복
 
전
체
 
무
게




S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
:
 
껍
질
을
 
제
외
한
 
무
게




V
i
s
c
r
a
 
W
e
i
g
h
t
 
:
 
내
장
 
무
게




S
h
e
l
l
 
W
e
i
g
h
t
 
:
 
껍
질
 
무
게




T
a
r
g
e
t
 
:
 
전
복
 
나
이






2
.
 
t
e
s
t
.
c
s
v
 
:
 
테
스
트
 
데
이
터




i
d
 
:
 
샘
플
 
아
이
디




G
e
n
d
e
r
 
:
 
전
복
 
성
별




L
e
n
g
h
t
 
:
 
전
복
 
길
이




D
i
a
m
e
t
e
r
 
:
 
전
복
 
둘
레




H
e
i
g
h
t
 
:
 
전
복
 
키
 




W
h
o
l
e
 
:
 
W
e
i
g
h
t
 
:
 
전
복
 
전
체
 
무
게




S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
:
 
껍
질
을
 
제
외
한
 
무
게




V
i
s
c
r
a
 
W
e
i
g
h
t
 
:
 
내
장
 
무
게




S
h
e
l
l
 
W
e
i
g
h
t
 
:
 
껍
질
 
무
게






3
.
 
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
 
:
 
제
출
 
양
식




i
d
 
:
 
샘
플
 
아
이
디




T
a
r
g
e
t
 
:
 
전
복
 
나
이


[
학
습
 
스
케
줄
링
]




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
는
 
신
경
망
 
학
습
하
는
데
 
중
요
 
요
소




학
습
률
이
 
충
분
치
 
못
하
면
 
L
o
c
a
l
 
M
i
n
i
n
u
m
에
 
빠
질
 
수
 
있
고
 
수
렴
이
 
어
려
움




학
습
률
이
 
크
면
 
G
l
o
b
a
l
 
M
i
n
i
m
u
m
을
 
지
나
칠
 
수
 
있
고
 
수
렴
이
 
어
려
움




적
절
한
 
학
습
률
이
 
중
요
 
:
 
큰
 
학
습
률
로
 
시
작
하
고
 
신
경
망
이
 
훈
련
하
는
 
동
안
 
학
습
률
을
 
감
소
시
키
는
 
전
략
 
필
요
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
c
0
b
2
1
f
f
3
-
8
a
4
4
-
4
4
d
2
-
8
f
c
6
-
e
5
1
7
2
8
c
4
2
5
7
3
.
p
n
g
)


1
.
 
거
듭
 
제
곱
 
기
반
 
스
케
줄
링




학
습
률
은
 
각
 
스
텝
마
다
 
감
소
하
며
 
s
번
 
스
텝
 
학
습
 
이
후
 
초
기
 
학
습
률
/
2
,
 
s
번
 
스
텝
 
이
후
 
초
기
학
습
률
/
3
.
.
 
처
음
에
는
 
빠
르
게
 
감
소
하
다
가
 
점
차
 
느
리
게
 
감
소




t
는
 
반
복
 
횟
수
 
(
e
p
o
c
h
)




s
는
 
스
텝
 
횟
수




d
e
c
a
y
는
 
s
t
e
p
(
s
)
의
 
역
수




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
k
e
r
a
s
.
o
p
t
i
m
i
z
e
r
s
.
S
G
D
(
l
r
=
1
e
-
3
,
d
e
c
a
y
=
1
e
-
4
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
3
a
4
e
b
a
d
4
-
a
f
6
8
-
4
b
3
4
-
a
6
2
5
-
3
a
8
6
1
b
5
7
2
f
b
5
.
p
n
g
)


2
.
 
지
수
 
기
반
 
스
케
줄
링




s
번
 
스
텝
마
다
 
1
0
배
씩
 
감
소




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
c
4
9
6
c
3
f
6
-
e
f
b
8
-
4
b
0
a
-
b
a
9
f
-
b
8
6
8
7
c
3
6
8
e
8
a
.
p
n
g
)


3
.
 
구
간
 
별
 
고
정
 
스
케
줄
링




일
정
 
횟
수
의
 
에
포
크
 
동
안
 
일
정
한
 
학
습
률
을
 
사
용
하
고
,
 
또
 
다
른
 
횟
수
의
 
에
포
크
 
동
안
 
작
은
 
학
습
률
을
 
사
용
하
는
 
방
식




직
접
 
구
간
별
 
학
습
률
 
지
정
 
필
요




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
c
8
0
d
0
1
4
7
-
d
a
0
6
-
4
7
c
b
-
b
1
e
a
-
0
a
2
e
1
2
c
f
7
a
4
7
.
p
n
g
)


4
.
 
성
능
 
기
반
 
학
습
 
스
케
줄
링




매
 
N
 
스
텝
마
다
 
(
조
기
 
종
료
처
럼
)
 
검
증
 
오
차
를
 
측
정
하
고
 
오
차
가
 
줄
어
들
지
 
않
으
면
 
람
다
배
 
만
큼
 
학
습
률
을
 
감
소




(
데
이
터
의
 
패
턴
을
 
학
습
할
 
수
 
있
도
록
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
5
8
0
c
2
0
7
0
-
0
8
5
f
-
4
0
8
a
-
8
9
d
f
-
3
f
d
7
8
6
5
1
5
1
8
6
.
p
n
g
)


5
.
1
 
사
이
클
 
스
케
줄
링




훈
련
 
절
반
 
동
안
 
초
기
 
학
습
률
을
 
선
형
적
으
로
 
증
가
시
킨
 
뒤
,
 
나
머
지
 
절
반
 
동
안
 
선
형
적
으
로
 
학
습
률
을
 
초
기
 
학
습
률
까
지
 
다
시
 
감
소
시
키
며
 
학
습




보
통
 
초
기
 
학
습
률
 
*
 
1
0
 
=
 
증
가
시
킨
 
학
습
률
 




[
l
1
 
l
2
 
규
제
]




신
경
망
의
 
연
결
 
가
중
치
를
 
제
한
하
기
 
위
해
 
l
2
규
제
를
 
사
용
하
거
나
,
 
희
소
 
모
델
을
 
만
들
기
 
위
해
 
l
1
 
규
제
를
 
사
용




규
제
항
 
l
2
 
적
용
 
심
층
신
경
망
 
생
성




k
e
r
a
s
.
r
e
g
u
l
a
r
i
z
e
r
s
.
l
1
(
)


k
e
r
a
s
.
r
e
g
u
l
a
r
i
z
e
r
s
.
l
2
(
)


k
e
r
a
s
.
r
e
g
u
l
a
r
i
z
e
r
s
.
l
1
_
l
2
(
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
8
4
0
4
e
b
f
1
-
9
4
7
0
-
4
b
5
b
-
b
a
5
8
-
4
4
9
2
f
f
e
4
6
3
6
8
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
4
f
3
f
a
c
e
4
-
7
e
b
e
-
4
8
0
c
-
b
0
b
7
-
3
2
c
7
d
4
3
2
1
4
7
e
.
p
n
g
)


각
 
훈
련
 
반
복
에
서
 
(
출
력
 
층
 
제
외
)
 
하
나
 
이
상
의
 
층
에
 
있
는
 
모
든
 
뉴
런
의
 
일
부
를
 
확
률
적
으
로
 
제
거
하
고
 
훈
련




매
 
훈
련
 
스
텝
에
서
 
각
 
뉴
련
(
입
력
 
뉴
런
 
포
함
 
가
능
,
 
출
력
 
층
 
포
함
 
불
가
)
은
 
임
시
적
으
로
 
드
롭
아
웃
 
될
 
확
률
 
p
를
 
가
짐




일
반
적
으
로
 
0
.
1
 
~
 
0
.
5
 
지
정
(
0
.
5
 
지
정
시
 
그
 
층
의
 
반
은
 
드
롭
아
웃
 
되
고
 
훈
련
진
행
)




-
 
장
점




1
)
 
드
롭
아
웃
으
로
 
훈
련
된
 
뉴
런
은
 
이
웃
한
 
뉴
런
에
 
맞
춰
 
적
응
될
 
수
 
없
어
 
자
기
 
자
신
이
 
유
용
해
져
야
함




2
)
 
몇
 
개
의
 
입
력
 
뉴
런
에
만
 
지
나
치
게
 
의
존
할
 
수
 
없
어
 
모
든
 
입
력
 
뉴
런
에
 
주
의
를
 
기
울
여
야
 
함




3
)
 
입
력
값
의
 
작
은
 
변
화
에
 
덜
 
민
감
해
져
서
 
일
반
화
 
성
능
 
좋
아
짐




4
)
 
2
*
*
n
개
의
 
네
트
워
크
 
생
성
이
 
가
능
해
져
,
 
여
러
번
의
 
훈
련
을
 
통
해
 
만
들
어
진
 
신
경
망
은
 
이
 
모
든
 
신
경
망
을
 
평
균
한
 
앙
상
블
과
 
같
은
 
모
델
이
 
됨
(
n
은
 
드
롭
아
웃
이
 
가
능
한
 
뉴
런
 
수
)




5
)
 
시
간
이
 
오
래
 
걸
리
지
만
 
적
절
한
 
튜
닝
 
시
 
좋
은
 
성
능
을
 
갖
는
 
모
델
을
 
생
성
할
 
수
 
있
음




6
)
 
T
e
s
t
시
 
보
존
 
확
률
 
(
1
-
p
)
를
 
각
 
입
력
의
 
연
결
 
가
중
치
에
 
곱
해
줘
야
 
함




[
맥
스
-
노
름
 
규
제
]




각
각
의
 
뉴
런
에
 
대
해
 
입
력
의
 
연
결
 
가
중
치
 
w
가
 
|
|
w
|
|
2
 
<
=
 
r
이
 
되
도
록
 
제
한
하
는
 
것




전
체
 
손
실
 
함
수
에
 
규
제
 
손
실
 
항
을
 
추
가
하
지
 
않
고
,
 
w
의
 
스
케
일
을
 
조
정
함
 
(
w
<
-
w
*
r
/
|
|
w
|
|
2
)




r
의
 
값
이
 
작
을
 
수
록
 
규
제
의
 
양
이
 
증
가
하
여
 
과
대
적
합
을
 
방
지
할
 
수
 
있
음




불
안
정
한
 
G
r
a
d
i
e
n
t
 
문
제
를
 
완
화
하
는
데
 
도
움



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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
a
b
a
l
o
n
e
-
a
g
e
-
p
r
e
d
i
c
t
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
 
G
e
n
d
e
r
 
 
L
e
n
g
h
t
 
 
D
i
a
m
e
t
e
r
 
 
H
e
i
g
h
t
 
 
W
h
o
l
e
 
W
e
i
g
h
t
 
 
S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
 
\

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
M
 
 
 
0
.
6
0
5
 
 
 
 
 
0
.
4
7
0
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
1
.
1
1
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
9
2
5
 
 
 

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
I
 
 
 
0
.
4
3
0
 
 
 
 
 
0
.
3
1
5
 
 
 
0
.
0
9
5
 
 
 
 
 
 
 
 
0
.
3
7
8
0
 
 
 
 
 
 
 
 
 
 
0
.
1
7
5
0
 
 
 

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
I
 
 
 
0
.
5
8
0
 
 
 
 
 
0
.
4
9
0
 
 
 
0
.
1
9
5
 
 
 
 
 
 
 
 
1
.
3
1
6
5
 
 
 
 
 
 
 
 
 
 
0
.
5
3
0
5
 
 
 

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
M
 
 
 
0
.
5
3
5
 
 
 
 
 
0
.
4
0
5
 
 
 
0
.
1
7
5
 
 
 
 
 
 
 
 
1
.
2
7
0
5
 
 
 
 
 
 
 
 
 
 
0
.
5
4
8
0
 
 
 

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
I
 
 
 
0
.
3
1
0
 
 
 
 
 
0
.
2
3
5
 
 
 
0
.
0
9
0
 
 
 
 
 
 
 
 
0
.
1
2
7
0
 
 
 
 
 
 
 
 
 
 
0
.
0
4
8
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
 
 
 

1
2
4
8
 
 
1
2
4
9
 
 
 
 
 
 
I
 
 
 
0
.
1
9
0
 
 
 
 
 
0
.
1
4
5
 
 
 
0
.
0
4
0
 
 
 
 
 
 
 
 
0
.
0
3
8
0
 
 
 
 
 
 
 
 
 
 
0
.
0
1
6
5
 
 
 

1
2
4
9
 
 
1
2
5
0
 
 
 
 
 
 
I
 
 
 
0
.
3
9
5
 
 
 
 
 
0
.
3
1
0
 
 
 
0
.
0
8
5
 
 
 
 
 
 
 
 
0
.
3
1
7
0
 
 
 
 
 
 
 
 
 
 
0
.
1
5
3
0
 
 
 

1
2
5
0
 
 
1
2
5
1
 
 
 
 
 
 
F
 
 
 
0
.
5
2
5
 
 
 
 
 
0
.
4
1
0
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
0
.
7
7
4
5
 
 
 
 
 
 
 
 
 
 
0
.
4
1
6
0
 
 
 

1
2
5
1
 
 
1
2
5
2
 
 
 
 
 
 
F
 
 
 
0
.
4
4
5
 
 
 
 
 
0
.
3
3
5
 
 
 
0
.
1
1
0
 
 
 
 
 
 
 
 
0
.
4
3
5
5
 
 
 
 
 
 
 
 
 
 
0
.
2
0
2
5
 
 
 

1
2
5
2
 
 
1
2
5
3
 
 
 
 
 
 
F
 
 
 
0
.
7
5
0
 
 
 
 
 
0
.
5
5
0
 
 
 
0
.
1
9
5
 
 
 
 
 
 
 
 
1
.
8
3
2
5
 
 
 
 
 
 
 
 
 
 
0
.
8
3
0
0
 
 
 


 
 
 
 
 
 
V
i
s
c
r
a
 
W
e
i
g
h
t
 
 
S
h
e
l
l
 
W
e
i
g
h
t
 
 
T
a
r
g
e
t
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
9
1
0
 
 
 
 
 
 
 
 
0
.
3
1
0
0
 
 
 
 
 
 
1
5
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
8
0
0
 
 
 
 
 
 
 
 
0
.
1
0
4
5
 
 
 
 
 
 
 
8
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
5
4
0
 
 
 
 
 
 
 
 
0
.
4
1
0
0
 
 
 
 
 
 
1
8
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
.
3
2
6
5
 
 
 
 
 
 
 
 
0
.
3
3
7
0
 
 
 
 
 
 
1
3
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
1
0
 
 
 
 
 
 
 
 
0
.
0
4
0
0
 
 
 
 
 
 
 
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
8
 
 
 
 
 
 
 
 
 
0
.
0
0
6
5
 
 
 
 
 
 
 
 
0
.
0
1
5
0
 
 
 
 
 
 
 
4
 
 

1
2
4
9
 
 
 
 
 
 
 
 
 
0
.
0
5
0
5
 
 
 
 
 
 
 
 
0
.
0
9
3
5
 
 
 
 
 
 
 
7
 
 

1
2
5
0
 
 
 
 
 
 
 
 
 
0
.
1
6
3
0
 
 
 
 
 
 
 
 
0
.
1
8
0
0
 
 
 
 
 
 
 
7
 
 

1
2
5
1
 
 
 
 
 
 
 
 
 
0
.
1
0
9
5
 
 
 
 
 
 
 
 
0
.
1
1
9
5
 
 
 
 
 
 
 
6
 
 

1
2
5
2
 
 
 
 
 
 
 
 
 
0
.
3
6
6
0
 
 
 
 
 
 
 
 
0
.
4
4
0
0
 
 
 
 
 
 
1
1
 
 


[
1
2
5
3
 
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
<pre>
 
 
 
 
 
 
 
 
i
d
 
G
e
n
d
e
r
 
 
L
e
n
g
h
t
 
 
D
i
a
m
e
t
e
r
 
 
H
e
i
g
h
t
 
 
W
h
o
l
e
 
W
e
i
g
h
t
 
 
S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
 
\

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
F
 
 
 
0
.
5
9
5
 
 
 
 
 
0
.
4
7
0
 
 
 
0
.
1
5
5
 
 
 
 
 
 
 
 
1
.
1
2
1
0
 
 
 
 
 
 
 
 
 
 
0
.
4
5
1
5
 
 
 

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
M
 
 
 
0
.
5
8
0
 
 
 
 
 
0
.
4
5
0
 
 
 
0
.
1
5
0
 
 
 
 
 
 
 
 
0
.
9
2
7
0
 
 
 
 
 
 
 
 
 
 
0
.
2
7
6
0
 
 
 

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
I
 
 
 
0
.
2
6
0
 
 
 
 
 
0
.
2
0
5
 
 
 
0
.
0
7
0
 
 
 
 
 
 
 
 
0
.
0
9
7
0
 
 
 
 
 
 
 
 
 
 
0
.
0
4
1
5
 
 
 

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
M
 
 
 
0
.
5
9
0
 
 
 
 
 
0
.
4
6
0
 
 
 
0
.
1
3
0
 
 
 
 
 
 
 
 
1
.
1
0
2
0
 
 
 
 
 
 
 
 
 
 
0
.
4
5
5
0
 
 
 

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
F
 
 
 
0
.
5
9
5
 
 
 
 
 
0
.
4
6
5
 
 
 
0
.
1
4
0
 
 
 
 
 
 
 
 
1
.
1
1
3
0
 
 
 
 
 
 
 
 
 
 
0
.
5
1
7
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
 
 
 

2
9
1
9
 
 
2
9
2
0
 
 
 
 
 
 
I
 
 
 
0
.
1
7
0
 
 
 
 
 
0
.
1
0
5
 
 
 
0
.
0
3
5
 
 
 
 
 
 
 
 
0
.
0
3
4
0
 
 
 
 
 
 
 
 
 
 
0
.
0
1
2
0
 
 
 

2
9
2
0
 
 
2
9
2
1
 
 
 
 
 
 
I
 
 
 
0
.
4
3
5
 
 
 
 
 
0
.
3
4
5
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
0
.
4
1
8
0
 
 
 
 
 
 
 
 
 
 
0
.
2
2
2
0
 
 
 

2
9
2
1
 
 
2
9
2
2
 
 
 
 
 
 
I
 
 
 
0
.
5
7
0
 
 
 
 
 
0
.
4
5
0
 
 
 
0
.
1
3
5
 
 
 
 
 
 
 
 
0
.
7
9
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
8
1
5
 
 
 

2
9
2
2
 
 
2
9
2
3
 
 
 
 
 
 
I
 
 
 
0
.
4
6
0
 
 
 
 
 
0
.
3
5
0
 
 
 
0
.
1
2
0
 
 
 
 
 
 
 
 
0
.
4
8
8
5
 
 
 
 
 
 
 
 
 
 
0
.
1
9
3
0
 
 
 

2
9
2
3
 
 
2
9
2
4
 
 
 
 
 
 
F
 
 
 
0
.
5
6
5
 
 
 
 
 
0
.
4
4
0
 
 
 
0
.
1
6
0
 
 
 
 
 
 
 
 
0
.
9
1
5
0
 
 
 
 
 
 
 
 
 
 
0
.
3
5
4
0
 
 
 


 
 
 
 
 
 
V
i
s
c
r
a
 
W
e
i
g
h
t
 
 
S
h
e
l
l
 
W
e
i
g
h
t
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
1
7
8
0
 
 
 
 
 
 
 
 
0
.
1
5
5
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
.
1
8
1
5
 
 
 
 
 
 
 
 
0
.
3
6
0
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
1
9
0
 
 
 
 
 
 
 
 
0
.
0
3
0
5
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
0
5
5
 
 
 
 
 
 
 
 
0
.
3
3
0
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
4
4
0
 
 
 
 
 
 
 
 
0
.
3
0
5
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
 
 

2
9
1
9
 
 
 
 
 
 
 
 
 
0
.
0
0
8
5
 
 
 
 
 
 
 
 
0
.
0
0
5
0
 
 

2
9
2
0
 
 
 
 
 
 
 
 
 
0
.
0
7
3
5
 
 
 
 
 
 
 
 
0
.
1
0
6
0
 
 

2
9
2
1
 
 
 
 
 
 
 
 
 
0
.
1
4
1
5
 
 
 
 
 
 
 
 
0
.
2
4
5
0
 
 

2
9
2
2
 
 
 
 
 
 
 
 
 
0
.
1
0
5
0
 
 
 
 
 
 
 
 
0
.
1
5
5
0
 
 

2
9
2
3
 
 
 
 
 
 
 
 
 
0
.
1
9
3
5
 
 
 
 
 
 
 
 
0
.
3
2
0
0
 
 


[
2
9
2
4
 
r
o
w
s
 
x
 
9
 
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
 
 
 
 
 
 
 
 
i
d
 
G
e
n
d
e
r
 
 
L
e
n
g
h
t
 
 
D
i
a
m
e
t
e
r
 
 
H
e
i
g
h
t
 
 
W
h
o
l
e
 
W
e
i
g
h
t
 
 
S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
 
\

0
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
M
 
 
 
0
.
6
0
5
 
 
 
 
 
0
.
4
7
0
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
1
.
1
1
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
9
2
5
 
 
 

1
 
 
 
 
 
 
 
 
2
 
 
 
 
 
 
I
 
 
 
0
.
4
3
0
 
 
 
 
 
0
.
3
1
5
 
 
 
0
.
0
9
5
 
 
 
 
 
 
 
 
0
.
3
7
8
0
 
 
 
 
 
 
 
 
 
 
0
.
1
7
5
0
 
 
 

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
 
I
 
 
 
0
.
5
8
0
 
 
 
 
 
0
.
4
9
0
 
 
 
0
.
1
9
5
 
 
 
 
 
 
 
 
1
.
3
1
6
5
 
 
 
 
 
 
 
 
 
 
0
.
5
3
0
5
 
 
 

3
 
 
 
 
 
 
 
 
4
 
 
 
 
 
 
M
 
 
 
0
.
5
3
5
 
 
 
 
 
0
.
4
0
5
 
 
 
0
.
1
7
5
 
 
 
 
 
 
 
 
1
.
2
7
0
5
 
 
 
 
 
 
 
 
 
 
0
.
5
4
8
0
 
 
 

4
 
 
 
 
 
 
 
 
5
 
 
 
 
 
 
I
 
 
 
0
.
3
1
0
 
 
 
 
 
0
.
2
3
5
 
 
 
0
.
0
9
0
 
 
 
 
 
 
 
 
0
.
1
2
7
0
 
 
 
 
 
 
 
 
 
 
0
.
0
4
8
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
 
 
 

2
9
1
9
 
 
2
9
2
0
 
 
 
 
 
 
I
 
 
 
0
.
1
7
0
 
 
 
 
 
0
.
1
0
5
 
 
 
0
.
0
3
5
 
 
 
 
 
 
 
 
0
.
0
3
4
0
 
 
 
 
 
 
 
 
 
 
0
.
0
1
2
0
 
 
 

2
9
2
0
 
 
2
9
2
1
 
 
 
 
 
 
I
 
 
 
0
.
4
3
5
 
 
 
 
 
0
.
3
4
5
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
0
.
4
1
8
0
 
 
 
 
 
 
 
 
 
 
0
.
2
2
2
0
 
 
 

2
9
2
1
 
 
2
9
2
2
 
 
 
 
 
 
I
 
 
 
0
.
5
7
0
 
 
 
 
 
0
.
4
5
0
 
 
 
0
.
1
3
5
 
 
 
 
 
 
 
 
0
.
7
9
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
8
1
5
 
 
 

2
9
2
2
 
 
2
9
2
3
 
 
 
 
 
 
I
 
 
 
0
.
4
6
0
 
 
 
 
 
0
.
3
5
0
 
 
 
0
.
1
2
0
 
 
 
 
 
 
 
 
0
.
4
8
8
5
 
 
 
 
 
 
 
 
 
 
0
.
1
9
3
0
 
 
 

2
9
2
3
 
 
2
9
2
4
 
 
 
 
 
 
F
 
 
 
0
.
5
6
5
 
 
 
 
 
0
.
4
4
0
 
 
 
0
.
1
6
0
 
 
 
 
 
 
 
 
0
.
9
1
5
0
 
 
 
 
 
 
 
 
 
 
0
.
3
5
4
0
 
 
 


 
 
 
 
 
 
V
i
s
c
r
a
 
W
e
i
g
h
t
 
 
S
h
e
l
l
 
W
e
i
g
h
t
 
 
T
a
r
g
e
t
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
9
1
0
 
 
 
 
 
 
 
 
0
.
3
1
0
0
 
 
 
 
1
5
.
0
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
8
0
0
 
 
 
 
 
 
 
 
0
.
1
0
4
5
 
 
 
 
 
8
.
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
5
4
0
 
 
 
 
 
 
 
 
0
.
4
1
0
0
 
 
 
 
1
8
.
0
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
.
3
2
6
5
 
 
 
 
 
 
 
 
0
.
3
3
7
0
 
 
 
 
1
3
.
0
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
1
0
 
 
 
 
 
 
 
 
0
.
0
4
0
0
 
 
 
 
 
6
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
 
 

2
9
1
9
 
 
 
 
 
 
 
 
 
0
.
0
0
8
5
 
 
 
 
 
 
 
 
0
.
0
0
5
0
 
 
 
 
 
N
a
N
 
 

2
9
2
0
 
 
 
 
 
 
 
 
 
0
.
0
7
3
5
 
 
 
 
 
 
 
 
0
.
1
0
6
0
 
 
 
 
 
N
a
N
 
 

2
9
2
1
 
 
 
 
 
 
 
 
 
0
.
1
4
1
5
 
 
 
 
 
 
 
 
0
.
2
4
5
0
 
 
 
 
 
N
a
N
 
 

2
9
2
2
 
 
 
 
 
 
 
 
 
0
.
1
0
5
0
 
 
 
 
 
 
 
 
0
.
1
5
5
0
 
 
 
 
 
N
a
N
 
 

2
9
2
3
 
 
 
 
 
 
 
 
 
0
.
1
9
3
5
 
 
 
 
 
 
 
 
0
.
3
2
0
0
 
 
 
 
 
N
a
N
 
 


[
4
1
7
7
 
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
[
'
w
e
i
g
h
t
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
W
h
o
l
e
 
W
e
i
g
h
t
'
]
-
a
l
l
d
a
t
a
[
'
S
h
u
c
k
e
d
 
W
e
i
g
h
t
'
]
-
a
l
l
d
a
t
a
[
'
V
i
s
c
r
a
 
W
e
i
g
h
t
'
]
-
a
l
l
d
a
t
a
[
'
S
h
e
l
l
 
W
e
i
g
h
t
'
]

a
l
l
d
a
t
a
[
'
r
a
t
i
o
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
D
i
a
m
e
t
e
r
'
]
/
a
l
l
d
a
t
a
[
'
H
e
i
g
h
t
'
]

a
l
l
d
a
t
a
[
'
r
a
t
i
o
2
'
]
=
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
L
e
n
g
h
t
'
]
*
a
l
l
d
a
t
a
[
'
H
e
i
g
h
t
'
]
)
/
a
l
l
d
a
t
a
[
'
D
i
a
m
e
t
e
r
'
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
T
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
 
 
 
 
 
G
e
n
d
e
r
 
 
L
e
n
g
h
t
 
 
D
i
a
m
e
t
e
r
 
 
H
e
i
g
h
t
 
 
W
h
o
l
e
 
W
e
i
g
h
t
 
 
S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
 
\

0
 
 
 
 
 
 
 
 
 
M
 
 
 
0
.
6
0
5
 
 
 
 
 
0
.
4
7
0
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
1
.
1
1
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
9
2
5
 
 
 

1
 
 
 
 
 
 
 
 
 
I
 
 
 
0
.
4
3
0
 
 
 
 
 
0
.
3
1
5
 
 
 
0
.
0
9
5
 
 
 
 
 
 
 
 
0
.
3
7
8
0
 
 
 
 
 
 
 
 
 
 
0
.
1
7
5
0
 
 
 

2
 
 
 
 
 
 
 
 
 
I
 
 
 
0
.
5
8
0
 
 
 
 
 
0
.
4
9
0
 
 
 
0
.
1
9
5
 
 
 
 
 
 
 
 
1
.
3
1
6
5
 
 
 
 
 
 
 
 
 
 
0
.
5
3
0
5
 
 
 

3
 
 
 
 
 
 
 
 
 
M
 
 
 
0
.
5
3
5
 
 
 
 
 
0
.
4
0
5
 
 
 
0
.
1
7
5
 
 
 
 
 
 
 
 
1
.
2
7
0
5
 
 
 
 
 
 
 
 
 
 
0
.
5
4
8
0
 
 
 

4
 
 
 
 
 
 
 
 
 
I
 
 
 
0
.
3
1
0
 
 
 
 
 
0
.
2
3
5
 
 
 
0
.
0
9
0
 
 
 
 
 
 
 
 
0
.
1
2
7
0
 
 
 
 
 
 
 
 
 
 
0
.
0
4
8
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
 
 
 

2
9
1
9
 
 
 
 
 
 
I
 
 
 
0
.
1
7
0
 
 
 
 
 
0
.
1
0
5
 
 
 
0
.
0
3
5
 
 
 
 
 
 
 
 
0
.
0
3
4
0
 
 
 
 
 
 
 
 
 
 
0
.
0
1
2
0
 
 
 

2
9
2
0
 
 
 
 
 
 
I
 
 
 
0
.
4
3
5
 
 
 
 
 
0
.
3
4
5
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
0
.
4
1
8
0
 
 
 
 
 
 
 
 
 
 
0
.
2
2
2
0
 
 
 

2
9
2
1
 
 
 
 
 
 
I
 
 
 
0
.
5
7
0
 
 
 
 
 
0
.
4
5
0
 
 
 
0
.
1
3
5
 
 
 
 
 
 
 
 
0
.
7
9
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
8
1
5
 
 
 

2
9
2
2
 
 
 
 
 
 
I
 
 
 
0
.
4
6
0
 
 
 
 
 
0
.
3
5
0
 
 
 
0
.
1
2
0
 
 
 
 
 
 
 
 
0
.
4
8
8
5
 
 
 
 
 
 
 
 
 
 
0
.
1
9
3
0
 
 
 

2
9
2
3
 
 
 
 
 
 
F
 
 
 
0
.
5
6
5
 
 
 
 
 
0
.
4
4
0
 
 
 
0
.
1
6
0
 
 
 
 
 
 
 
 
0
.
9
1
5
0
 
 
 
 
 
 
 
 
 
 
0
.
3
5
4
0
 
 
 


 
 
 
 
 
 
V
i
s
c
r
a
 
W
e
i
g
h
t
 
 
S
h
e
l
l
 
W
e
i
g
h
t
 
 
w
e
i
g
h
t
 
 
 
 
 
r
a
t
i
o
 
 
 
 
r
a
t
i
o
2
 
 

0
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
9
1
0
 
 
 
 
 
 
 
 
0
.
3
1
0
0
 
 
0
.
1
2
0
5
 
 
4
.
0
8
6
9
5
7
 
 
0
.
1
4
8
0
3
2
 
 

1
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
8
0
0
 
 
 
 
 
 
 
 
0
.
1
0
4
5
 
 
0
.
0
1
8
5
 
 
3
.
3
1
5
7
8
9
 
 
0
.
1
2
9
6
8
3
 
 

2
 
 
 
 
 
 
 
 
 
 
 
 
0
.
2
5
4
0
 
 
 
 
 
 
 
 
0
.
4
1
0
0
 
 
0
.
1
2
2
0
 
 
2
.
5
1
2
8
2
1
 
 
0
.
2
3
0
8
1
6
 
 

3
 
 
 
 
 
 
 
 
 
 
 
 
0
.
3
2
6
5
 
 
 
 
 
 
 
 
0
.
3
3
7
0
 
 
0
.
0
5
9
0
 
 
2
.
3
1
4
2
8
6
 
 
0
.
2
3
1
1
7
3
 
 

4
 
 
 
 
 
 
 
 
 
 
 
 
0
.
0
3
1
0
 
 
 
 
 
 
 
 
0
.
0
4
0
0
 
 
0
.
0
0
8
0
 
 
2
.
6
1
1
1
1
1
 
 
0
.
1
1
8
7
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
 
 
 
 
 
 
 
.
.
.
 
 

2
9
1
9
 
 
 
 
 
 
 
 
 
0
.
0
0
8
5
 
 
 
 
 
 
 
 
0
.
0
0
5
0
 
 
0
.
0
0
8
5
 
 
3
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
6
6
6
7
 
 

2
9
2
0
 
 
 
 
 
 
 
 
 
0
.
0
7
3
5
 
 
 
 
 
 
 
 
0
.
1
0
6
0
 
 
0
.
0
1
6
5
 
 
3
.
0
0
0
0
0
0
 
 
0
.
1
4
5
0
0
0
 
 

2
9
2
1
 
 
 
 
 
 
 
 
 
0
.
1
4
1
5
 
 
 
 
 
 
 
 
0
.
2
4
5
0
 
 
0
.
0
2
6
0
 
 
3
.
3
3
3
3
3
3
 
 
0
.
1
7
1
0
0
0
 
 

2
9
2
2
 
 
 
 
 
 
 
 
 
0
.
1
0
5
0
 
 
 
 
 
 
 
 
0
.
1
5
5
0
 
 
0
.
0
3
5
5
 
 
2
.
9
1
6
6
6
7
 
 
0
.
1
5
7
7
1
4
 
 

2
9
2
3
 
 
 
 
 
 
 
 
 
0
.
1
9
3
5
 
 
 
 
 
 
 
 
0
.
3
2
0
0
 
 
0
.
0
4
7
5
 
 
2
.
7
5
0
0
0
0
 
 
0
.
2
0
5
4
5
5
 
 


[
4
1
7
7
 
r
o
w
s
 
x
 
1
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
G
e
n
d
e
r
 
c
o
l
u
m
n
(
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
 
:
 
M
,
F
,
I
)
을
 
제
외
한
 
c
o
l
u
m
n
은
 
연
속
형
 
변
수
 
d
a
t
a
 
입
니
다
.




따
라
서
 
g
e
t
_
d
u
m
m
i
e
s
를
 
사
용
하
여
 
G
e
n
d
e
r
 
c
o
l
u
m
n
을
 
3
가
지
의
 
c
o
l
u
m
n
으
로
 
나
눠
준
 
후
 
T
r
u
e
,
 
F
a
l
s
e
의
 
형
식
으
로
 
바
꾸
어
 
줍
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
p
d
.
g
e
t
_
d
u
m
m
i
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
2
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
 
 
 
 
 
 
L
e
n
g
h
t
 
 
D
i
a
m
e
t
e
r
 
 
H
e
i
g
h
t
 
 
W
h
o
l
e
 
W
e
i
g
h
t
 
 
S
h
u
c
k
e
d
 
W
e
i
g
h
t
 
 
V
i
s
c
r
a
 
W
e
i
g
h
t
 
 
\

0
 
 
 
 
 
 
0
.
6
0
5
 
 
 
 
 
0
.
4
7
0
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
1
.
1
1
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
9
2
5
 
 
 
 
 
 
 
 
 
0
.
2
9
1
0
 
 
 

1
 
 
 
 
 
 
0
.
4
3
0
 
 
 
 
 
0
.
3
1
5
 
 
 
0
.
0
9
5
 
 
 
 
 
 
 
 
0
.
3
7
8
0
 
 
 
 
 
 
 
 
 
 
0
.
1
7
5
0
 
 
 
 
 
 
 
 
 
0
.
0
8
0
0
 
 
 

2
 
 
 
 
 
 
0
.
5
8
0
 
 
 
 
 
0
.
4
9
0
 
 
 
0
.
1
9
5
 
 
 
 
 
 
 
 
1
.
3
1
6
5
 
 
 
 
 
 
 
 
 
 
0
.
5
3
0
5
 
 
 
 
 
 
 
 
 
0
.
2
5
4
0
 
 
 

3
 
 
 
 
 
 
0
.
5
3
5
 
 
 
 
 
0
.
4
0
5
 
 
 
0
.
1
7
5
 
 
 
 
 
 
 
 
1
.
2
7
0
5
 
 
 
 
 
 
 
 
 
 
0
.
5
4
8
0
 
 
 
 
 
 
 
 
 
0
.
3
2
6
5
 
 
 

4
 
 
 
 
 
 
0
.
3
1
0
 
 
 
 
 
0
.
2
3
5
 
 
 
0
.
0
9
0
 
 
 
 
 
 
 
 
0
.
1
2
7
0
 
 
 
 
 
 
 
 
 
 
0
.
0
4
8
0
 
 
 
 
 
 
 
 
 
0
.
0
3
1
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
 
 
 

2
9
1
9
 
 
 
0
.
1
7
0
 
 
 
 
 
0
.
1
0
5
 
 
 
0
.
0
3
5
 
 
 
 
 
 
 
 
0
.
0
3
4
0
 
 
 
 
 
 
 
 
 
 
0
.
0
1
2
0
 
 
 
 
 
 
 
 
 
0
.
0
0
8
5
 
 
 

2
9
2
0
 
 
 
0
.
4
3
5
 
 
 
 
 
0
.
3
4
5
 
 
 
0
.
1
1
5
 
 
 
 
 
 
 
 
0
.
4
1
8
0
 
 
 
 
 
 
 
 
 
 
0
.
2
2
2
0
 
 
 
 
 
 
 
 
 
0
.
0
7
3
5
 
 
 

2
9
2
1
 
 
 
0
.
5
7
0
 
 
 
 
 
0
.
4
5
0
 
 
 
0
.
1
3
5
 
 
 
 
 
 
 
 
0
.
7
9
4
0
 
 
 
 
 
 
 
 
 
 
0
.
3
8
1
5
 
 
 
 
 
 
 
 
 
0
.
1
4
1
5
 
 
 

2
9
2
2
 
 
 
0
.
4
6
0
 
 
 
 
 
0
.
3
5
0
 
 
 
0
.
1
2
0
 
 
 
 
 
 
 
 
0
.
4
8
8
5
 
 
 
 
 
 
 
 
 
 
0
.
1
9
3
0
 
 
 
 
 
 
 
 
 
0
.
1
0
5
0
 
 
 

2
9
2
3
 
 
 
0
.
5
6
5
 
 
 
 
 
0
.
4
4
0
 
 
 
0
.
1
6
0
 
 
 
 
 
 
 
 
0
.
9
1
5
0
 
 
 
 
 
 
 
 
 
 
0
.
3
5
4
0
 
 
 
 
 
 
 
 
 
0
.
1
9
3
5
 
 
 


 
 
 
 
 
 
S
h
e
l
l
 
W
e
i
g
h
t
 
 
w
e
i
g
h
t
 
 
 
 
 
r
a
t
i
o
 
 
 
 
r
a
t
i
o
2
 
 
G
e
n
d
e
r
_
F
 
 
G
e
n
d
e
r
_
I
 
 
G
e
n
d
e
r
_
M
 
 

0
 
 
 
 
 
 
 
 
 
 
 
0
.
3
1
0
0
 
 
0
.
1
2
0
5
 
 
4
.
0
8
6
9
5
7
 
 
0
.
1
4
8
0
3
2
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 

1
 
 
 
 
 
 
 
 
 
 
 
0
.
1
0
4
5
 
 
0
.
0
1
8
5
 
 
3
.
3
1
5
7
8
9
 
 
0
.
1
2
9
6
8
3
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

2
 
 
 
 
 
 
 
 
 
 
 
0
.
4
1
0
0
 
 
0
.
1
2
2
0
 
 
2
.
5
1
2
8
2
1
 
 
0
.
2
3
0
8
1
6
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

3
 
 
 
 
 
 
 
 
 
 
 
0
.
3
3
7
0
 
 
0
.
0
5
9
0
 
 
2
.
3
1
4
2
8
6
 
 
0
.
2
3
1
1
7
3
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 

4
 
 
 
 
 
 
 
 
 
 
 
0
.
0
4
0
0
 
 
0
.
0
0
8
0
 
 
2
.
6
1
1
1
1
1
 
 
0
.
1
1
8
7
2
3
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
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
 
 

2
9
1
9
 
 
 
 
 
 
 
 
0
.
0
0
5
0
 
 
0
.
0
0
8
5
 
 
3
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
6
6
6
7
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

2
9
2
0
 
 
 
 
 
 
 
 
0
.
1
0
6
0
 
 
0
.
0
1
6
5
 
 
3
.
0
0
0
0
0
0
 
 
0
.
1
4
5
0
0
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

2
9
2
1
 
 
 
 
 
 
 
 
0
.
2
4
5
0
 
 
0
.
0
2
6
0
 
 
3
.
3
3
3
3
3
3
 
 
0
.
1
7
1
0
0
0
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

2
9
2
2
 
 
 
 
 
 
 
 
0
.
1
5
5
0
 
 
0
.
0
3
5
5
 
 
2
.
9
1
6
6
6
7
 
 
0
.
1
5
7
7
1
4
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 

2
9
2
3
 
 
 
 
 
 
 
 
0
.
3
2
0
0
 
 
0
.
0
4
7
5
 
 
2
.
7
5
0
0
0
0
 
 
0
.
2
0
5
4
5
5
 
 
 
 
 
 
 
 
 
1
 
 
 
 
 
 
 
 
 
0
 
 
 
 
 
 
 
 
 
0
 
 


[
4
1
7
7
 
r
o
w
s
 
x
 
1
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

#
 
*
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
*




모
델
을
 
더
 
이
상
 
학
습
하
지
 
못
할
 
경
우
 
(
l
o
s
s
,
 
m
e
t
r
i
c
 
등
의
 
개
선
이
 
없
는
 
경
우
)
,
 
학
습
 
도
중
 
미
리
 
학
습
을
 
종
료
시
키
는
 
콜
백
 
함
수




t
f
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
.
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
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
'
,
 
m
i
n
_
d
e
l
t
a
=
0
,
 
p
a
t
i
e
n
c
e
=
0
,
 
v
e
r
b
o
s
e
=
0
,
 
m
o
d
e
=
'
a
u
t
o
'
,
 
b
a
s
e
l
i
n
e
=
N
o
n
e
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
=
F
a
l
s
e
)




1
.
 
m
o
n
i
t
o
r
 
:
 
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
 
기
준
이
 
되
는
 
값
을
 
입
력
합
니
다
.




만
약
 
'
v
a
l
_
l
o
s
s
'
를
 
입
력
하
면
 
v
a
l
_
l
o
s
s
가
 
더
 
이
상
 
감
소
되
지
 
않
을
 
경
우
 
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
 
적
용
합
니
다
.
 
이
외
에
도
 
다
양
한
 
값
을
 
입
력
할
 
수
 
있
습
니
다
.




2
.
 
m
i
n
_
d
e
l
t
a
 
:
 
개
선
된
 
것
으
로
 
간
주
하
기
 
위
한
 
최
소
한
의
 
변
화
량
 
입
니
다
.
 




예
를
 
들
어
,
 
m
i
n
_
d
e
l
t
a
가
 
0
.
0
1
이
고
 
3
0
 
에
폭
에
 
정
확
도
가
 
0
.
8
5
3
2
라
고
 
할
 
때
,
 
만
약
 
3
1
 
에
폭
에
 
정
확
도
가
 
0
.
8
5
3
7
이
라
고
 
하
면
 
이
는
 
0
.
0
0
0
5
의
 
개
선
이
 
있
었
지
만
 
m
i
n
_
d
e
l
t
a
값
 
0
.
0
1
에
는
 
미
치
지
 
못
했
으
므
로
 
개
선
 
된
 
것
으
로
 
보
이
지
 
않
습
니
다
.




3
.
 
p
a
t
i
e
n
c
e
 
:
 
t
r
a
i
n
i
n
g
이
 
진
행
됨
에
도
 
더
 
이
상
 
m
o
n
i
t
o
r
 
되
는
 
값
의
 
개
선
이
 
없
는
 
경
우
,
 
최
적
의
 
m
o
n
i
t
o
r
 
값
을
 
기
준
으
로
 
몇
 
번
의
 
e
p
o
c
h
를
 
할
지
 
정
하
는
 
값
.




예
를
 
들
어
,
 
p
a
t
i
e
n
c
e
가
 
3
이
고
 
3
0
에
폭
에
 
정
확
도
가
 
9
9
%
였
을
 
때
,
 
3
1
번
째
에
 
정
확
도
 
9
8
%
 
3
2
번
에
 
9
8
.
5
%
 
3
3
번
에
 
9
8
%
라
면
 
더
 
이
상
 
t
r
a
i
n
i
n
g
을
 
하
지
 
않
고
 
종
료
시
킵
니
다
.




4
.
 
v
e
r
b
o
s
e
 
:
 
0
 
또
는
 
1




1
일
 
경
우
 
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
이
 
적
용
될
 
때
 
화
면
에
 
적
용
되
었
다
고
 
나
타
납
니
다
.
 
 
0
일
 
경
우
 
화
면
에
 
나
타
냄
 
없
이
 
종
료
합
니
다
.




5
.
 
m
o
d
e
 
:
 
'
a
u
t
o
'
 
또
는
 
'
m
i
n
'
 
또
는
 
'
m
a
x
'




m
o
n
i
t
o
r
되
는
 
값
이
 
최
소
가
 
되
어
야
 
하
는
지
,
 
최
대
가
 
되
어
야
 
하
는
지
 
알
려
주
는
 
인
자
입
니
다
.




m
o
n
i
t
o
r
하
는
 
값
이
 
v
a
l
_
a
c
c
 
즉
 
정
확
도
일
 
경
우
 
값
이
 
클
 
수
록
 
좋
기
 
때
문
에
 
'
m
a
x
'
를
 
입
력
하
고
 
v
a
l
_
l
o
s
s
일
 
경
우
 
작
을
 
수
록
 
좋
기
 
때
문
에
 
'
m
i
n
'
을
 
입
력
합
니
다
.
 
'
a
u
t
o
'
는
 
모
델
이
 
알
아
서
 
판
단
합
니
다
.




6
.
 
b
a
s
e
l
i
n
e
 
:
 
모
델
이
 
달
성
해
야
 
하
는
 
최
소
한
의
 
기
준
 
값
을
 
설
정
합
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
 
이
내
에
 
모
델
이
 
b
a
s
e
l
i
n
e
 
보
다
 
개
선
됨
이
 
보
이
지
 
않
으
면
 
t
r
a
i
n
i
n
g
을
 
중
단
 
시
킵
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
가
 
3
이
고
 
b
a
s
e
l
i
n
e
이
 
정
확
도
 
기
준
 
0
.
9
8
 
이
라
면
,
 
3
번
의
 
t
r
a
i
n
i
n
g
안
에
 
0
.
9
8
의
 
정
확
도
를
 
달
성
하
지
 
못
하
면
 
t
r
a
i
n
i
n
g
이
 
종
료
됩
니
다
.




7
.
 
r
e
s
o
t
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
 
:
 
T
r
u
e
 
o
r
 
F
a
l
s
e




t
r
u
e
라
면
 
t
r
a
i
n
i
n
g
이
 
끝
난
 
후
 
,
 
m
o
d
e
l
의
 
w
e
i
g
h
t
를
 
m
o
n
i
t
o
r
하
고
 
있
던
 
값
이
 
가
장
 
좋
았
을
 
때
의
 
w
e
i
g
h
t
로
 
복
원
합
니
다
.




f
a
l
s
e
라
면
,
 
마
지
막
 
t
r
a
i
n
i
n
g
이
 
끝
난
 
후
의
 
w
e
i
g
h
t
로
 
놔
둡
니
다
.


#
 
d
r
o
p
 
o
u
t
을
 
0
.
1
/
0
.
3
/
0
.
5
로
 
변
경
하
여
 
r
e
s
u
l
t
 
변
화
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
1
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
2
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

r
e
s
u
l
t
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
2
3
 
2
2
:
0
4
:
5
7
.
5
3
4
6
7
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
2
3
 
2
2
:
0
4
:
5
7
.
6
3
7
2
8
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
2
3
 
2
2
:
0
4
:
5
7
.
6
3
8
0
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
4
-
2
3
 
2
2
:
0
4
:
5
7
.
6
3
9
5
5
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
2
3
 
2
2
:
0
4
:
5
7
.
6
4
0
6
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
4
-
2
3
 
2
2
:
0
4
:
5
7
.
6
4
1
3
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
2
3
 
2
2
:
0
4
:
5
7
.
6
4
1
9
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
2
3
 
2
2
:
0
4
:
5
9
.
4
8
0
9
5
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
4
-
2
3
 
2
2
:
0
4
:
5
9
.
4
8
1
8
1
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
2
3
 
2
2
:
0
4
:
5
9
.
4
8
2
4
6
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
2
3
 
2
2
:
0
4
:
5
9
.
4
8
3
0
8
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
2
3
 
2
2
:
0
4
:
5
9
.
9
1
7
0
3
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
 
0
.
4
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
2
5
3
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
1
7
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
2
1
4
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
2
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
2
4
1
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
1
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
2
2
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
0
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
9
8
5

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
9
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
2
3
4
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
9
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
1
9
7
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
8
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
2
1
6
1

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
8
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
1
8
6
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
5
3

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
9
6

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
1
1
3

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
1
3
0

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
2
2

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
1
2
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
 
0
.
1
9
6
2

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
2
3
6
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
7
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
 
0
.
2
1
4
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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
7
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
1
8
8
6

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
3
8

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
7
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
1
8
9
7

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
6
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
8
1
4

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
7
8
3

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

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
8
7

E
p
o
c
h
 
2
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
7
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
8
7
0

E
p
o
c
h
 
2
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
2
5
1
5

E
p
o
c
h
 
2
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
8
1
3

E
p
o
c
h
 
2
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
9
1
8

E
p
o
c
h
 
3
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
2
4
6
3

E
p
o
c
h
 
3
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
7
9
6

E
p
o
c
h
 
3
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
8
1
6

E
p
o
c
h
 
3
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
7
6
8

E
p
o
c
h
 
3
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
2
3
1
6

E
p
o
c
h
 
3
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
9
0
0

E
p
o
c
h
 
3
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
9
3
0

E
p
o
c
h
 
3
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
7
4
7

E
p
o
c
h
 
3
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
2
3
6
1

E
p
o
c
h
 
3
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
6
6

E
p
o
c
h
 
4
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
2
2
6
8

E
p
o
c
h
 
4
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
7
5
5

E
p
o
c
h
 
4
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
5
3

E
p
o
c
h
 
4
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
4
7

E
p
o
c
h
 
4
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
4
8

E
p
o
c
h
 
4
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
2
1
8
4

E
p
o
c
h
 
4
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
6
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
8
4
9

E
p
o
c
h
 
4
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
9
6

E
p
o
c
h
 
4
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
7
4
1

E
p
o
c
h
 
4
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
7
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
7
3
6

E
p
o
c
h
 
5
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
4
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
0
3
8

E
p
o
c
h
 
5
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
6
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
1
8
3
1

E
p
o
c
h
 
5
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
8
4
6

E
p
o
c
h
 
5
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
9

E
p
o
c
h
 
5
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
0
0

E
p
o
c
h
 
5
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
9
6
4

E
p
o
c
h
 
5
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
2
2
2
3

E
p
o
c
h
 
5
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
6
4

E
p
o
c
h
 
5
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
0
4
0

E
p
o
c
h
 
5
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
0
2
5

E
p
o
c
h
 
6
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
 
0
.
1
8
3
9

E
p
o
c
h
 
6
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
3
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
7
4
1

E
p
o
c
h
 
6
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
8
7
7

E
p
o
c
h
 
6
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
 
0
.
2
2
7
2

E
p
o
c
h
 
6
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
2
4
0
9

E
p
o
c
h
 
6
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
8
6

E
p
o
c
h
 
6
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
5
8

E
p
o
c
h
 
6
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
2
0

E
p
o
c
h
 
6
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
 
0
.
1
9
9
1

E
p
o
c
h
 
6
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
3
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
7
7
0

E
p
o
c
h
 
7
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
7
8

E
p
o
c
h
 
7
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
4
2

E
p
o
c
h
 
7
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
8
6
1

E
p
o
c
h
 
7
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
8
0
2

E
p
o
c
h
 
7
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
0

E
p
o
c
h
 
7
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
8
3

E
p
o
c
h
 
7
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
0
6

E
p
o
c
h
 
7
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
3
1

E
p
o
c
h
 
7
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
6
1

E
p
o
c
h
 
7
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
5
6

E
p
o
c
h
 
8
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
2
6

E
p
o
c
h
 
8
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
8

E
p
o
c
h
 
8
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
6
0

E
p
o
c
h
 
8
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
3
9

E
p
o
c
h
 
8
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
6
6

E
p
o
c
h
 
8
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
0
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
1
8

E
p
o
c
h
 
8
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
7
2
4

E
p
o
c
h
 
8
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
3
0

E
p
o
c
h
 
8
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
7
0

E
p
o
c
h
 
8
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
0
0

E
p
o
c
h
 
9
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
3
3

E
p
o
c
h
 
9
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
8
3

E
p
o
c
h
 
9
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
9
1
9

E
p
o
c
h
 
9
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
1
2

E
p
o
c
h
 
9
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
6

E
p
o
c
h
 
9
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
1
2

E
p
o
c
h
 
9
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
0
5

E
p
o
c
h
 
9
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
9

E
p
o
c
h
 
9
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
7
7
2

E
p
o
c
h
 
9
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
1
8

E
p
o
c
h
 
1
0
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
9
6

E
p
o
c
h
 
1
0
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
9
1
8

E
p
o
c
h
 
1
0
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
5
4

E
p
o
c
h
 
1
0
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
8
8

E
p
o
c
h
 
1
0
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
7

E
p
o
c
h
 
1
0
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
0
5

E
p
o
c
h
 
1
0
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
5

E
p
o
c
h
 
1
0
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
6
4

E
p
o
c
h
 
1
0
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
6
0

E
p
o
c
h
 
1
0
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
0
5

E
p
o
c
h
 
1
1
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
6
3

E
p
o
c
h
 
1
1
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
6
8

E
p
o
c
h
 
1
1
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
8
4

E
p
o
c
h
 
1
1
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
8
3

E
p
o
c
h
 
1
1
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
4
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
1
5

E
p
o
c
h
 
1
1
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
9

E
p
o
c
h
 
1
1
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
5
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
1
7
7
6

E
p
o
c
h
 
1
1
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
7
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
6
8
3

E
p
o
c
h
 
1
1
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
5
6

E
p
o
c
h
 
1
1
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
7
3

E
p
o
c
h
 
1
2
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
3
1

E
p
o
c
h
 
1
2
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
7
4

E
p
o
c
h
 
1
2
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
8
5
9

E
p
o
c
h
 
1
2
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
6
4

E
p
o
c
h
 
1
2
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
5
7

E
p
o
c
h
 
1
2
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
9
3
6

E
p
o
c
h
 
1
2
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
9
1
3

E
p
o
c
h
 
1
2
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
0
4

E
p
o
c
h
 
1
2
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
5
9

E
p
o
c
h
 
1
2
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
3

E
p
o
c
h
 
1
3
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
3
8

E
p
o
c
h
 
1
3
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
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
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
7
5

E
p
o
c
h
 
1
3
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
7
1

E
p
o
c
h
 
1
3
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
0
0

E
p
o
c
h
 
1
3
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
2
9

E
p
o
c
h
 
1
3
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
8
8
3

E
p
o
c
h
 
1
3
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
3
0

E
p
o
c
h
 
1
3
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
8
6
1

E
p
o
c
h
 
1
3
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
9
5
1

E
p
o
c
h
 
1
4
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
3

E
p
o
c
h
 
1
4
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
3
6

E
p
o
c
h
 
1
4
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
1
8

E
p
o
c
h
 
1
4
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
5
1

E
p
o
c
h
 
1
4
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
7
0

E
p
o
c
h
 
1
4
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
5
6

E
p
o
c
h
 
1
4
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
5
1

E
p
o
c
h
 
1
4
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
6

E
p
o
c
h
 
1
4
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
8

E
p
o
c
h
 
1
4
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
9
5

E
p
o
c
h
 
1
5
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
7
0

E
p
o
c
h
 
1
5
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
2
5

E
p
o
c
h
 
1
5
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
6

E
p
o
c
h
 
1
5
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
7

E
p
o
c
h
 
1
5
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
3
8

E
p
o
c
h
 
1
5
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
5
8

E
p
o
c
h
 
1
5
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
5

E
p
o
c
h
 
1
5
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
3

E
p
o
c
h
 
1
5
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
0

E
p
o
c
h
 
1
5
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
7
7

E
p
o
c
h
 
1
6
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
8

E
p
o
c
h
 
1
6
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
4

E
p
o
c
h
 
1
6
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
9
5

E
p
o
c
h
 
1
6
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
7

E
p
o
c
h
 
1
6
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
7

E
p
o
c
h
 
1
6
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
8
9

E
p
o
c
h
 
1
6
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
 
0
.
1
8
8
0

E
p
o
c
h
 
1
6
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
1
3

E
p
o
c
h
 
1
6
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
 
0
.
1
7
7
0

E
p
o
c
h
 
1
6
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
0

E
p
o
c
h
 
1
7
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
1
5

E
p
o
c
h
 
1
7
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
6
2

E
p
o
c
h
 
1
7
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
2

E
p
o
c
h
 
1
7
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
8
5
0

E
p
o
c
h
 
1
7
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
6

E
p
o
c
h
 
1
7
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
7

E
p
o
c
h
 
1
7
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
2
7

E
p
o
c
h
 
1
7
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
9

E
p
o
c
h
 
1
7
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
9

E
p
o
c
h
 
1
7
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
3
9

E
p
o
c
h
 
1
8
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
5
8

E
p
o
c
h
 
1
8
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
4
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
5
6

E
p
o
c
h
 
1
8
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
1
7

E
p
o
c
h
 
1
8
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
1

E
p
o
c
h
 
1
8
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
0
4

E
p
o
c
h
 
1
8
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
7

E
p
o
c
h
 
1
8
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
4

E
p
o
c
h
 
1
8
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
6

E
p
o
c
h
 
1
8
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
8
2
6

E
p
o
c
h
 
1
8
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
3

E
p
o
c
h
 
1
9
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
3

E
p
o
c
h
 
1
9
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
5
6

E
p
o
c
h
 
1
9
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
3

E
p
o
c
h
 
1
9
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
 
0
.
1
6
8
3

E
p
o
c
h
 
1
9
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
5
8

E
p
o
c
h
 
1
9
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
3

E
p
o
c
h
 
1
9
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
0
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
1
2

E
p
o
c
h
 
1
9
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
9
7

E
p
o
c
h
 
1
9
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
4

E
p
o
c
h
 
1
9
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
0
7

E
p
o
c
h
 
2
0
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
4

E
p
o
c
h
 
2
0
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
0
2

E
p
o
c
h
 
2
0
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
3
8

E
p
o
c
h
 
2
0
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
6
6

E
p
o
c
h
 
2
0
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
2
7

E
p
o
c
h
 
2
0
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
3

E
p
o
c
h
 
2
0
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
4

E
p
o
c
h
 
2
0
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
1
7

E
p
o
c
h
 
2
0
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
4
8

E
p
o
c
h
 
2
0
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
4
0

E
p
o
c
h
 
2
1
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
9
7

E
p
o
c
h
 
2
1
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
0
0

E
p
o
c
h
 
2
1
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
4
8

E
p
o
c
h
 
2
1
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
8
1
1

E
p
o
c
h
 
2
1
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
0

E
p
o
c
h
 
2
1
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
1
8

E
p
o
c
h
 
2
1
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
5
6

E
p
o
c
h
 
2
1
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
0
4

E
p
o
c
h
 
2
1
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
6
7

E
p
o
c
h
 
2
1
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
4
6

E
p
o
c
h
 
2
2
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
7

E
p
o
c
h
 
2
2
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
4
9

E
p
o
c
h
 
2
2
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
5
2

E
p
o
c
h
 
2
2
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
7

E
p
o
c
h
 
2
2
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
1

E
p
o
c
h
 
2
2
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
2
0

E
p
o
c
h
 
2
2
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
4

E
p
o
c
h
 
2
2
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
9

E
p
o
c
h
 
2
2
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
0
5

E
p
o
c
h
 
2
2
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
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
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
5

E
p
o
c
h
 
2
3
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
3

E
p
o
c
h
 
2
3
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
0
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
2
2

E
p
o
c
h
 
2
3
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
6
6

E
p
o
c
h
 
2
3
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
1
1

E
p
o
c
h
 
2
3
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
1

E
p
o
c
h
 
2
3
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
4
3

E
p
o
c
h
 
2
3
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
2
1

E
p
o
c
h
 
2
3
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
1
3

E
p
o
c
h
 
2
3
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
7
4

E
p
o
c
h
 
2
4
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
5
9
4

E
p
o
c
h
 
2
4
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
3

E
p
o
c
h
 
2
4
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
9
3

E
p
o
c
h
 
2
4
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
5
9
5

E
p
o
c
h
 
2
4
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
8

E
p
o
c
h
 
2
4
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
6
1

E
p
o
c
h
 
2
4
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
9
3

E
p
o
c
h
 
2
4
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
5

E
p
o
c
h
 
2
4
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
5

E
p
o
c
h
 
2
4
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
8
5

E
p
o
c
h
 
2
5
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
0
0

E
p
o
c
h
 
2
5
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
0
7

E
p
o
c
h
 
2
5
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
5
4

E
p
o
c
h
 
2
5
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
8
5

E
p
o
c
h
 
2
5
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
1

E
p
o
c
h
 
2
5
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
7
0
6

E
p
o
c
h
 
2
5
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
7

E
p
o
c
h
 
2
5
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
8
7

E
p
o
c
h
 
2
5
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
9

E
p
o
c
h
 
2
5
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
7

E
p
o
c
h
 
2
6
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
9

E
p
o
c
h
 
2
6
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
7
7

E
p
o
c
h
 
2
6
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
0

E
p
o
c
h
 
2
6
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
1
2

E
p
o
c
h
 
2
6
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
0
7

E
p
o
c
h
 
2
6
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
6
4

E
p
o
c
h
 
2
6
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
9

E
p
o
c
h
 
2
6
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
7
4
5

E
p
o
c
h
 
2
6
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
1
1

E
p
o
c
h
 
2
6
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
3
0

E
p
o
c
h
 
2
7
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
6

E
p
o
c
h
 
2
7
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
6

E
p
o
c
h
 
2
7
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
9
9

E
p
o
c
h
 
2
7
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
4

E
p
o
c
h
 
2
7
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
8

E
p
o
c
h
 
2
7
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
5
8
4

E
p
o
c
h
 
2
7
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
0

E
p
o
c
h
 
2
7
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
6
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
6
1
0

E
p
o
c
h
 
2
7
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
2

E
p
o
c
h
 
2
7
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
0
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
0

E
p
o
c
h
 
2
8
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
7
6

E
p
o
c
h
 
2
8
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
0
5

E
p
o
c
h
 
2
8
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
3
1

E
p
o
c
h
 
2
8
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
0

E
p
o
c
h
 
2
8
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
5
9
7

E
p
o
c
h
 
2
8
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
5

E
p
o
c
h
 
2
8
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
6
5
1

E
p
o
c
h
 
2
8
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
8

E
p
o
c
h
 
2
8
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
6

E
p
o
c
h
 
2
8
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
5

E
p
o
c
h
 
2
9
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
5
2

E
p
o
c
h
 
2
9
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
1
1

E
p
o
c
h
 
2
9
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
8

E
p
o
c
h
 
2
9
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
3

E
p
o
c
h
 
2
9
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
8
4

E
p
o
c
h
 
2
9
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
9

E
p
o
c
h
 
2
9
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
2

E
p
o
c
h
 
2
9
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
5

E
p
o
c
h
 
2
9
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
1
7

E
p
o
c
h
 
2
9
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
6
0
2

E
p
o
c
h
 
3
0
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
7

E
p
o
c
h
 
3
0
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
2

E
p
o
c
h
 
3
0
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
5

E
p
o
c
h
 
3
0
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
9
6

E
p
o
c
h
 
3
0
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
0
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
4
6

E
p
o
c
h
 
3
0
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
7
0
3

E
p
o
c
h
 
3
0
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
7
5
1

E
p
o
c
h
 
3
0
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
4
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
1
7
1
4

E
p
o
c
h
 
3
0
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
3
4

E
p
o
c
h
 
3
0
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
2
7

E
p
o
c
h
 
3
1
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
5

E
p
o
c
h
 
3
1
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
0
0

E
p
o
c
h
 
3
1
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
2

E
p
o
c
h
 
3
1
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
8
8

E
p
o
c
h
 
3
1
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
2
1

E
p
o
c
h
 
3
1
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
 
0
.
1
6
2
2

E
p
o
c
h
 
3
1
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
8
8

E
p
o
c
h
 
3
1
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
1

E
p
o
c
h
 
3
1
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
7

E
p
o
c
h
 
3
1
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
5

E
p
o
c
h
 
3
2
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
6
0
6

E
p
o
c
h
 
3
2
1
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
7
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
6
4
6

E
p
o
c
h
 
3
2
2
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
0
5

E
p
o
c
h
 
3
2
3
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
2

E
p
o
c
h
 
3
2
4
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
6
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
6
5
7

E
p
o
c
h
 
3
2
5
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
7
5

E
p
o
c
h
 
3
2
6
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
1
1

E
p
o
c
h
 
3
2
7
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
4
8

E
p
o
c
h
 
3
2
8
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
1
6
1
4

E
p
o
c
h
 
3
2
9
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
6
3
0

E
p
o
c
h
 
3
3
0
/
1
0
0
0

3
2
/
3
2
 
[
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
=
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
3
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
1
5
9
9

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
2
.
2
6
2
7
1
0
8
]
,

 
 
 
 
 
 
 
[
2
.
7
1
9
8
9
8
5
]
,

 
 
 
 
 
 
 
[
1
.
7
1
3
5
1
4
6
]
,

 
 
 
 
 
 
 
.
.
.
,

 
 
 
 
 
 
 
[
2
.
1
9
6
4
7
9
 
]
,

 
 
 
 
 
 
 
[
2
.
1
1
8
7
3
5
3
]
,

 
 
 
 
 
 
 
[
2
.
4
4
3
2
2
1
8
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
v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
9
4
5
0
1
3
8




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
2
1
3
6
7
7
2
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
5
8
3
0
3
6
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
9
5
7
7
1
5
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
1
6
3
6
3
7
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
2
4
7
5
5
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
3
2
4
0
6
 
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
3
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
2
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
6
5
5
5
2
7
6




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
2
2
7
3
2
9
3
]
,
	
	


 
 
 
 
 
 
 
[
2
.
6
9
0
2
9
2
4
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
8
9
0
6
8
 
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
1
9
5
3
6
6
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
2
7
8
1
5
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
6
9
8
1
2
9
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
2
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
5
5
6
7
1
5
4




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
2
2
2
1
1
9
 
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
3
5
6
1
8
4
]
,
	
	


 
 
 
 
 
 
 
[
1
.
7
0
2
6
1
8
1
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
1
9
7
0
0
6
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
2
9
9
8
 
 
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
9
0
7
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


#
 
같
은
 
조
건
에
서
 
D
r
o
p
o
u
t
의
 
크
기
가
 
클
 
수
록
 
(
0
.
5
 
>
 
0
.
4
 
>
 
0
.
3
)
 
v
a
l
_
l
o
s
s
의
 
평
균
이
 
낮
아
짐
 
확
인
하
였
습
니
다




#
 
드
롭
아
웃
으
로
 
훈
련
된
 
뉴
런
은
 
이
웃
한
 
뉴
런
에
 
맞
춰
 
적
응
될
 
수
 
없
어
 
자
기
 
자
신
이
 
유
용
해
져
야
하
기
 
때
문
으
로
 
보
입
니
다


#
 
*
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
*




모
델
의
 
개
선
이
 
없
을
 
경
우
 
L
e
a
r
n
i
n
g
 
R
a
t
e
를
 
조
절
해
 
모
델
의
 
개
선
을
 
유
도
하
는
 
콜
백
 
함
수




t
f
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
.
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
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
'
,
 
f
a
c
t
o
r
=
0
.
1
,
 
p
a
t
i
e
n
c
e
=
1
0
,
 
v
e
r
b
o
s
e
=
0
,
 
m
o
d
e
=
'
a
u
t
o
'
,
 
m
i
n
_
d
e
l
t
a
=
0
.
0
0
0
1
,
 
c
o
o
l
d
o
w
n
=
0
,
 
m
i
n
_
l
r
=
0
,
 
*
*
k
w
a
r
g
s
)




1
.
 
m
o
n
i
t
o
r




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
의
 
기
준
이
 
되
는
 
값
,
 
'
v
a
l
_
l
o
s
s
'
를
 
입
력
하
면
 
v
a
l
_
l
o
s
s
가
 
더
 
이
상
 
감
소
 
되
지
 
않
을
 
경
우
 
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
을
 
적
용
.
 
이
외
에
도
 
다
양
한
 
값
 
입
력
 
가
능




2
.
 
f
a
c
t
o
r




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
를
 
얼
마
나
 
감
소
시
킬
지
 
정
하
는
 
인
자
값




새
로
운
 
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
는
 
기
존
 
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
*
f
a
c
t
o
r
 
입
니
다




현
재
 
l
r
이
 
0
.
0
1
이
고
 
f
a
c
t
o
r
가
 
0
.
8
 
일
 
때
 
콜
백
함
수
가
 
실
행
된
다
면
 
그
 
다
음
 
l
r
은
 
0
.
0
0
8
이
 
됩
니
다
.




l
r
이
 
0
.
3
이
고
 
f
a
c
t
o
r
가
 
0
.
1
일
때
 
콜
백
함
수
가
 
실
행
된
다
면
 
그
 
다
음
 
l
r
은
 
0
.
0
3
이
 
됩
니
다
.




3
.
 
p
a
t
i
e
n
c
e




t
r
a
i
n
i
n
g
이
 
진
행
됨
에
도
 
더
 
이
상
 
m
o
n
i
t
o
r
 
되
는
 
값
의
 
개
선
이
 
없
을
 
경
우
,
 




4
.
 
v
e
r
b
o
s
e




0
 
또
는
 
1




1
일
 
경
우
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
이
 
적
용
될
 
때
,
 
화
면
에
 
적
용
되
었
다
고
 
나
타
냅
니
다
.




0
일
 
경
우
,
 
화
면
에
 
나
타
냄
 
없
이
 
종
료
합
니
다
.




5
.
 
m
o
d
e




"
a
u
t
o
"
 
또
는
 
"
m
i
n
"
 
또
는
 
"
m
a
x
"




m
o
n
i
t
o
r
되
는
 
값
이
 
최
소
가
 
되
어
야
 
하
는
지
,
 
최
대
가
 
되
어
야
 
하
는
지
 
알
려
주
는
 
인
자
입
니
다
.




예
를
 
들
어
,
 
m
o
n
i
t
o
r
하
는
 
값
이
 
v
a
l
_
a
c
c
 
즉
 
정
확
도
일
 
경
우
,
 
값
이
 
클
수
록
 
좋
기
때
문
에
 
"
m
a
x
"
를
 
입
력
하
고
,
 
v
a
l
_
l
o
s
s
일
 
경
우
 
작
을
수
록
 
좋
기
 
때
문
에
 
"
m
i
n
"
을
 
입
력
합
니
다
.




"
a
u
t
o
"
는
 
모
델
이
 
알
아
서
 
판
단
합
니
다




6
.
 
m
i
n
_
d
e
l
t
a




개
선
된
 
것
으
로
 
간
주
하
기
 
위
한
 
최
소
한
의
 
변
화
량
입
니
다
.
 
예
시
로
 
이
해
하
는
 
게
 
좋
을
 
것
 
같
습
니
다
.




예
를
 
들
어
,
 
m
i
n
_
d
e
l
t
a
가
 
0
.
0
1
이
고
,
 
3
0
에
폭
에
 
정
확
도
가
 
0
.
8
5
3
2
라
고
 
할
 
때
,




만
약
 
3
1
에
폭
에
 
정
확
도
가
 
0
.
8
5
3
7
라
고
 
하
면
 
이
는
 
0
.
0
0
5
의
 
개
선
이
 
있
었
지
만
 
m
i
n
_
d
e
l
t
a
 
값
 
0
.
0
1
에
는
 
미
치
지
 
못
했
으
므
로
 
개
선
된
 
것
으
로
 
보
지
 
않
습
니
다
.




7
.
 
c
o
o
l
d
o
w
n




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
가
 
감
소
한
 
후
,
 
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
 
콜
백
함
수
를
 
다
시
 
실
행
하
기
 
전
에
 
대
기
 
할
 
E
p
o
c
h
 
수
 
입
니
다
.




f
a
c
t
o
r
가
 
3
이
고
 
c
o
o
l
d
o
w
n
이
 
5
 
일
 
때
,
 
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
이
 
적
용
되
어
 
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
가
 
감
소
 
되
었
다
고
 
가
정
.




감
소
 
된
 
이
후
에
도
 
3
 
에
폭
 
연
속
 
m
o
n
i
t
o
r
 
값
의
 
개
선
이
 
없
었
다
고
 
하
더
라
도
 
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
는
 
실
행
되
지
 
않
습
니
다
.




c
o
o
l
d
o
w
n
이
 
적
용
되
고
 
있
기
 
때
문
입
니
다
.
 
c
o
o
l
 
d
o
w
n
 
값
인
 
5
 
에
폭
 
실
행
 
후
,
 
3
번
 
연
속
 
m
o
n
i
t
o
r
값
의
 
개
선
이
 
없
을
 
시
,
 
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
이
 
다
시
 
적
용
됩
니
다
.




8
.
 
m
i
n
_
l
r




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
의
 
하
한
선
을
 
지
정
합
니
다
.




현
재
 
l
r
이
 
0
.
1
,
 
f
a
c
t
o
r
가
 
5
,
 
m
i
n
_
l
r
이
 
0
.
0
3
일
 
때




첫
 
번
째
 
콜
백
 
함
수
가
 
적
용
될
 
시
 
l
r
은
 
0
.
0
5
(
0
.
1
*
0
.
5
)
이
 
됩
니
다
.




두
 
번
째
로
 
콜
백
 
함
수
가
 
적
용
되
면
 
0
.
0
2
5
(
0
.
1
*
0
.
5
*
0
.
5
)
이
지
만
 
m
i
n
_
l
r
이
 
0
.
0
3
이
기
 
때
문
에
 
새
로
운
 
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
는
 
0
.
0
2
5
가
 
아
닌
 
0
.
0
3
이
 
됩
니
다
.


#
 
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
s
p
l
i
t
의
 
값
을
 
0
.
2
 
/
 
0
.
3
 
/
 
0
.
4
 
로
 
나
누
어
 
적
용
하
고
,
 
결
과
를
 
확
인
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
2
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
r
l
]
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
1
3
3
4
7
8
3




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
2
4
1
6
0
0
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
4
4
7
5
8
4
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
8
2
1
4
6
1
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
0
2
4
5
6
 
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
4
5
6
0
2
2
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
7
0
5
0
8
6
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
3
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
r
l
]
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
5
4
3
5
0
8
9
5




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
3
0
5
9
9
0
7
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
0
9
6
3
3
6
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
7
1
8
7
1
7
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
1
8
0
3
9
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
5
2
1
5
1
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
7
4
1
1
0
8
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
4
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
r
l
]
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

r
e
s
u
l
t

```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
5
1
0
0
1
3
8
8




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
2
5
9
6
9
3
1
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
6
3
0
6
8
2
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
7
4
4
9
5
8
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
0
4
6
9
7
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
4
9
7
6
6
2
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
5
3
5
3
5
 
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


#
 
같
은
 
조
건
에
서
 
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
s
p
l
i
t
의
 
값
이
 
높
을
 
수
록
 
(
0
.
4
 
>
 
0
.
3
 
>
 
0
.
2
)
 
v
a
l
_
l
o
s
s
 
평
균
이
 
낮
아
짐
 
확
인
하
였
습
니
다
.




#
 
d
r
o
p
 
o
u
t
과
 
마
찬
가
지
로
 
이
웃
한
 
뉴
런
에
 
맞
춰
 
적
응
될
 
수
 
없
어
 
자
기
 
자
신
이
 
유
용
해
져
야
하
기
 
때
문
으
로
 
보
입
니
다




#
 
이
번
에
는
 
같
은
 
조
건
에
서
 
콜
백
함
수
의
 
p
a
t
i
e
n
c
e
 
값
을
 
5
5
 
/
 
8
0
 
/
 
1
0
0
으
로
 
나
누
어
 
v
a
l
_
l
o
s
s
의
 
변
화
를
 
확
인
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
5
5
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
4
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
r
l
]
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

r
e
s
u
l
t

```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
5
1
0
0
1
3
8
8




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
2
5
9
6
9
3
1
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
6
3
0
6
8
2
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
7
4
4
9
5
8
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
0
4
6
9
7
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
4
9
7
6
6
2
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
5
3
5
3
5
 
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
8
0
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
4
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
r
l
]
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

r
e
s
u
l
t

```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
5
2
7
2
9
2
5
4




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
2
9
4
8
1
1
7
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
1
5
4
9
9
2
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
7
2
8
8
8
6
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
0
9
2
5
7
 
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
4
8
2
5
0
3
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
6
1
6
0
7
5
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
D
e
n
s
e
(
3
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
e
l
u
'
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
 
t
r
a
i
n
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
l
o
s
s
 
=
 
"
m
a
e
"
,
 
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
n
a
d
a
m
"
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
 
1
0
0
,
 
f
a
c
t
o
r
 
=
 
0
.
1
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
n
p
.
l
o
g
(
t
r
a
i
n
[
"
T
a
r
g
e
t
"
]
)
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
s
p
l
i
t
 
=
 
0
.
4
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
r
l
]
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
5
2
4
5
2
0
9
6




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
3
1
0
7
6
3
6
]
,
	
	


 
 
 
 
 
 
 
[
2
.
6
9
8
7
6
9
6
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
9
5
4
8
3
4
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
0
9
4
9
6
3
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
3
4
0
7
2
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
6
4
9
1
5
8
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




#
 
P
a
t
i
e
n
c
e
 
5
5
일
 
때
 
>
 
1
0
0
일
 
때
 
>
 
8
0
일
 
때
 
순
으
로
 
v
a
l
_
l
o
s
s
 
평
균
이
 
낮
아
짐
을
 
확
인
하
였
습
니
다
.




#
 
e
p
c
o
h
s
는
 
절
대
 
적
으
로
 
P
a
t
i
e
n
c
e
값
이
 
올
라
감
에
 
따
라
 
증
가
하
므
로
 
v
a
l
_
l
o
s
s
 
평
균
이
 
높
아
질
 
수
 
밖
에
 
없
습
니
다
.




#
 
그
러
나
 
P
a
t
i
e
n
c
e
가
 
1
0
0
일
 
때
 
P
a
t
i
e
n
c
e
가
 
8
0
일
 
때
보
다
 
v
a
l
_
l
o
s
s
 
평
균
이
 
낮
은
 
이
유
는
 
P
a
t
i
e
n
c
e
 
8
0
 
~
 
1
0
0
 
사
이
에
서
 
가
장
 
적
합
한
 
학
습
이
 
추
가
로
 
나
왔
을
 
것
으
로
 
예
상
됩
니
다
.


#
 
*
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
*




모
델
을
 
저
장
할
 
때
 
사
용
하
는
 
콜
백
 
함
수




t
f
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
.
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
(
f
i
l
e
p
a
t
h
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
0
,
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
F
a
l
s
e
,
 
s
a
v
e
_
w
e
i
g
h
t
s
_
o
n
l
y
=
F
a
l
s
e
,
 
m
o
d
e
=
'
a
u
t
o
'
,
 
s
a
v
e
_
f
r
e
q
=
'
e
p
o
c
h
,
 
o
p
t
i
o
n
s
=
N
o
n
e
,
 
*
k
w
a
r
g
s




1
.
 
f
i
l
e
p
a
t
h




모
델
을
 
저
장
할
 
경
로
를
 
입
력
합
니
다
.




만
약
 
m
o
n
i
t
o
r
가
 
v
a
l
_
l
o
s
s
 
일
 
때
,
 
모
델
 
경
로
를
 
'
{
e
p
o
c
h
:
0
2
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'
라
고
 
입
력
하
면
 
에
폭
-
해
당
에
폭
에
서
의
 
v
a
l
_
l
o
s
s
.
h
5
로
 
모
델
이
 
저
장
됩
니
다
.




2
.
 
m
o
n
i
t
o
r




모
델
을
 
저
장
할
 
때
,
 
기
준
이
 
되
는
 
값
을
 
지
정
합
니
다
.




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
 
s
e
t
의
 
l
o
s
s
가
 
가
장
 
작
을
 
때
를
 
저
장
하
고
 
싶
으
면
 
'
v
a
l
_
l
o
s
s
'
를
 
입
력
하
고
 
t
r
a
i
n
 
s
e
t
의
 
l
o
s
s
가
 
가
장
 
적
을
 
때
를
 
저
장
하
고
 
싶
으
면
 
'
l
o
s
s
'
를
 
입
력
합
니
다
.
 
이
 
외
에
도
 
다
양
한
 
값
을
 
기
준
으
로
 
삼
을
 
수
 
있
습
니
다
.




3
.
 
v
e
r
b
o
s
e




1
일
 
경
우
 
모
델
이
 
저
장
될
 
때
,
 
'
저
장
되
었
습
니
다
'
라
고
 
화
면
에
 
표
시
되
고
,
 
0
일
 
경
우
 
화
면
에
 
표
시
 
되
는
 
것
 
없
이
 
바
로
 
모
델
이
 
저
장
됩
니
다
.




4
.
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y




T
r
u
e
인
 
경
우
 
m
o
n
i
t
o
r
 
되
고
 
있
는
 
값
을
 
기
준
으
로
 
가
장
 
좋
은
 
값
으
로
 
모
델
이
 
저
장
됩
니
다
.




F
a
l
s
e
인
 
경
우
 
매
 
에
폭
마
다
 
모
델
이
 
f
i
l
e
p
a
t
h
{
e
p
o
c
h
}
으
로
 
저
장
됩
니
다
.
(
m
o
d
e
l
0
,
 
m
o
d
e
l
1
,
 
m
o
d
e
l
2
.
.
.
.
)




5
.
 
s
a
v
e
_
w
e
i
g
h
t
s
_
o
n
l
y




T
r
u
e
인
 
경
우
 
모
델
의
 
w
e
i
g
h
t
s
만
 
저
장
됩
니
다
.




F
a
l
s
e
인
 
경
우
 
모
델
 
레
이
어
 
및
 
w
e
i
g
h
t
s
 
모
두
 
저
장
됩
니
다
.




6
.
 
m
o
d
e




'
a
u
t
o
'
,
 
'
m
i
n
'
,
 
'
m
a
x
'




v
a
l
_
a
c
c
인
 
경
우
 
정
확
도
가
 
클
수
록
 
좋
습
니
다
.
 
이
때
는
 
m
a
x
값
을
 
입
력
해
 
줘
야
 
하
고
 
,
 
v
a
l
_
l
o
s
s
 
인
 
경
우
 
작
을
수
록
 
좋
으
므
로
 
m
i
n
을
 
입
력
해
야
 
합
니
다
.




a
u
t
o
로
 
할
 
경
우
 
모
델
이
 
m
i
n
,
m
a
x
 
모
델
을
 
판
단
하
여
 
저
장
합
니
다
.




7
.
 
s
a
v
e
_
f
r
e
q




'
e
p
o
c
h
'
 
혹
은
 
i
n
t
i
g
e
r
(
정
수
형
 
숫
자
)




'
e
p
o
c
h
'
을
 
사
용
할
 
경
우
 
매
 
에
폭
마
다
 
모
델
이
 
저
장
됩
니
다
.
 
i
n
t
e
g
e
r
를
 
입
력
한
 
경
우
 
숫
자
만
큼
의
 
배
치
를
 
진
행
하
면
 
모
델
이
 
저
장
됩
니
다
.




숫
자
 
8
을
 
입
력
하
면
,
 
8
번
째
 
배
치
가
 
t
r
a
i
n
된
 
이
후
 
1
6
번
째
 
배
치
가
 
t
r
a
i
n
된
 
이
후
 
모
델
이
 
저
장
됩
니
다
.




8
.
 
o
p
t
i
o
n
s




t
f
.
t
r
a
i
n
.
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
O
p
t
i
o
n
s
를
 
옵
션
으
로
 
줄
 
수
 
있
습
니
다
.
 
분
산
환
경
에
서
 
다
른
 
디
렉
토
리
에
 
모
델
을
 
저
장
하
고
 
싶
을
 
경
우
 
사
용
합
니
다
.






#
 
같
은
 
조
건
에
서
 
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
s
p
l
i
t
 
값
을
 
0
.
2
 
/
 
0
.
6
 
/
 
0
.
8
 
로
 
나
누
어
 
결
과
를
 
확
인
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
'
{
e
p
o
c
h
:
0
2
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
2
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
m
c
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
9
6
8




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
2
6
6
3
6
4
3
,
 
2
.
2
6
4
8
4
4
 
,
 
2
.
2
6
6
0
2
4
 
,
 
.
.
.
,
 
2
.
2
6
5
0
5
2
8
,
 
2
.
2
6
5
5
1
8
7
,




 
 
 
 
 
 
 
 
2
.
2
6
6
0
1
9
8
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
6
4
4
2
1
6
5
,
 
2
.
6
4
1
3
2
7
6
,
 
2
.
6
4
4
3
3
0
7
,
 
.
.
.
,
 
2
.
6
4
1
6
4
1
9
,
 
2
.
6
4
5
0
2
8
4
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
6
4
2
4
1
9
3
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
1
.
6
9
8
8
0
8
2
,
 
1
.
7
0
0
5
5
0
8
,
 
1
.
6
9
7
3
5
4
7
,
 
.
.
.
,
 
1
.
7
0
1
5
5
9
5
,
 
1
.
6
9
8
1
1
9
4
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
1
.
7
0
0
5
7
9
6
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
.
.
.
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
2
2
2
4
9
9
1
,
 
2
.
2
2
1
7
6
8
6
,
 
2
.
2
2
2
0
4
4
7
,
 
.
.
.
,
 
2
.
2
2
3
1
4
4
8
,
 
2
.
2
2
2
6
2
7
 
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
2
2
3
1
0
3
8
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
1
4
6
4
3
4
3
,
 
2
.
1
4
6
0
6
8
 
,
 
2
.
1
4
5
9
6
9
 
,
 
.
.
.
,
 
2
.
1
4
7
2
6
5
 
,
 
2
.
1
4
6
5
6
4
5
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
1
4
6
8
6
1
3
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
4
2
3
8
2
3
4
,
 
2
.
4
2
1
5
4
8
6
,
 
2
.
4
2
3
3
 
 
 
,
 
.
.
.
,
 
2
.
4
2
2
5
0
0
8
,
 
2
.
4
2
3
4
4
1
6
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
4
2
2
7
1
4
2
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
'
{
e
p
o
c
h
:
0
2
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
6
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
m
c
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
3
1
9
7
1




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
1
7
5
4
2
7
4
,
 
2
.
1
7
4
9
4
5
6
,
 
2
.
1
7
5
5
0
1
3
,
 
.
.
.
,
 
2
.
1
7
5
3
2
1
 
,
 
2
.
1
7
6
5
4
9
2
,




 
 
 
 
 
 
 
 
2
.
1
7
5
7
1
2
6
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
6
3
6
3
9
4
 
,
 
2
.
6
3
6
4
8
5
3
,
 
2
.
6
3
5
8
4
1
 
,
 
.
.
.
,
 
2
.
6
3
6
4
6
5
 
,
 
2
.
6
3
6
7
0
7
5
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
6
3
6
4
8
4
 
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
1
.
6
6
1
5
0
1
4
,
 
1
.
6
6
2
0
7
6
5
,
 
1
.
6
6
3
1
6
2
1
,
 
.
.
.
,
 
1
.
6
6
1
5
1
4
4
,
 
1
.
6
6
3
0
4
9
5
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
1
.
6
6
2
0
6
1
2
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
.
.
.
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
2
2
3
0
4
1
 
,
 
2
.
2
2
3
2
9
7
4
,
 
2
.
2
2
3
3
6
6
7
,
 
.
.
.
,
 
2
.
2
2
2
7
2
2
8
,
 
2
.
2
2
3
1
9
2
2
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
2
2
3
3
4
5
3
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
1
3
5
6
4
6
 
,
 
2
.
1
3
6
0
2
5
 
,
 
2
.
1
3
6
1
8
9
 
,
 
.
.
.
,
 
2
.
1
3
5
4
5
5
8
,
 
2
.
1
3
6
1
3
6
8
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
1
3
6
0
1
4
2
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
4
1
0
0
9
1
2
,
 
2
.
4
0
9
9
5
1
4
,
 
2
.
4
1
0
2
0
9
 
,
 
.
.
.
,
 
2
.
4
1
0
2
1
3
5
,
 
2
.
4
1
0
5
2
6
8
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
4
1
0
4
8
2
 
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
'
{
e
p
o
c
h
:
0
2
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
8
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
m
c
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

r
e
s
u
l
t
```

v
a
l
 
l
o
s
s
 
평
균
 
:
 
0
.
1
7
0
5
4
5
7




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
2
3
8
8
6
0
6
,
 
2
.
2
3
8
6
0
4
5
,
 
2
.
2
3
9
4
2
9
5
,
 
.
.
.
,
 
2
.
2
3
9
6
2
4
5
,
 
2
.
2
3
9
6
5
2
4
,




 
 
 
 
 
 
 
 
2
.
2
3
9
9
9
3
8
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
6
0
3
6
7
7
3
,
 
2
.
6
0
3
4
5
9
4
,
 
2
.
6
0
3
9
1
1
4
,
 
.
.
.
,
 
2
.
6
0
5
8
2
3
5
,
 
2
.
6
0
4
2
9
0
2
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
6
0
4
9
3
3
 
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
1
.
6
4
7
6
0
0
9
,
 
1
.
6
4
8
2
1
5
8
,
 
1
.
6
4
8
1
9
3
4
,
 
.
.
.
,
 
1
.
6
4
7
1
7
7
1
,
 
1
.
6
4
8
5
9
0
1
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
1
.
6
4
8
0
5
3
 
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
.
.
.
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
1
7
5
0
4
6
2
,
 
2
.
1
7
4
5
5
3
 
,
 
2
.
1
7
4
9
2
6
5
,
 
.
.
.
,
 
2
.
1
7
5
6
1
5
 
,
 
2
.
1
7
4
9
5
4
4
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
1
7
5
4
2
6
5
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
0
9
7
9
3
9
5
,
 
2
.
0
9
7
7
3
2
8
,
 
2
.
0
9
8
0
7
1
 
,
 
.
.
.
,
 
2
.
0
9
8
4
6
9
7
,
 
2
.
0
9
8
2
1
0
8
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
0
9
8
4
3
8
3
]
,


 
 
 
 
 
 
 
 


 
 
 
 
 
 
 
[
2
.
3
7
8
2
7
3
7
,
 
2
.
3
7
7
6
3
4
5
,
 
2
.
3
7
8
2
6
4
 
,
 
.
.
.
,
 
2
.
3
7
9
4
9
2
8
,
 
2
.
3
7
8
1
5
6
 
,


 
 
 
 
 
 
 


 
 
 
 
 
 
 
 
2
.
3
7
9
0
9
0
3
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


#
 
같
은
 
조
건
에
서
 
v
a
l
_
l
o
s
s
 
값
은
 
(
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
s
p
l
i
t
 
기
준
)
 
0
.
6
 
>
 
0
.
2
 
>
 
0
.
8
 
순
으
로
 
낮
아
졌
습
니
다
.




#
 
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
s
p
l
i
t
 
값
을
 
높
이
게
 
되
면
 
t
e
s
t
 
과
정
에
서
 
자
기
 
자
신
의
 
유
용
성
을
 
높
여
야
 
하
지
만
 
0
.
8
까
지
 
높
이
게
 
되
면
 
오
히
려
 
t
r
a
i
n
과
 
v
a
l
i
d
 
d
a
t
a
간
의
 
불
균
형
이
 
심
화
되
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


#
 
에
폭
 
저
장
 
회
차
를
 
2
 
/
 
4
 
/
 
8
로
 
변
경
하
여
 
확
인
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
 
'
{
e
p
o
c
h
:
0
2
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
2
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
m
c
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
1
4
1
6
4




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
2
0
0
7
9
3
 
]
,
	
	


 
 
 
 
 
 
 
[
2
.
5
6
4
3
9
4
7
]
,
	
	


 
 
 
 
 
 
 
[
1
.
7
7
4
0
0
6
2
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
4
0
6
1
0
4
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
4
6
7
5
5
7
]
,
	
	


 
 
 
 
 
 
 
[
2
.
4
3
9
3
5
9
4
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
 
'
{
e
p
o
c
h
:
0
4
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
2
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
m
c
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
2
1
9
7
5




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
2
8
2
4
1
1
3
]
,
	
	


 
 
 
 
 
 
 
[
2
.
6
3
4
9
5
2
 
]
,
	
	


 
 
 
 
 
 
 
[
1
.
7
2
2
3
5
5
4
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
8
7
7
6
5
5
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
7
1
5
9
3
2
]
,
	
	


 
 
 
 
 
 
 
[
2
.
5
2
3
4
9
8
 
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
D
e
n
s
e
(
3
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
e
l
u
'
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
a
l
l
d
a
t
a
2
.
s
h
a
p
e
[
1
]
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
6
4
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
e
l
u
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
r
o
p
o
u
t
(
0
.
5
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
e
l
u
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
n
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
m
a
e
'
)


f
i
l
e
n
a
m
e
=
 
'
{
e
p
o
c
h
:
0
8
d
}
-
{
v
a
l
_
l
o
s
s
:
.
5
f
}
.
h
5
'

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
f
i
l
e
n
a
m
e
,
 
m
o
n
i
t
o
r
=
'
v
a
l
_
l
o
s
s
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
 
s
a
v
e
_
b
e
s
t
_
o
n
l
y
=
T
r
u
e
,
 
m
o
d
e
=
'
a
u
t
o
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
2
,
n
p
.
l
o
g
(
t
r
a
i
n
[
'
T
a
r
g
e
t
'
]
)
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
s
p
l
i
t
=
0
.
2
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
m
c
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

r
e
s
u
l
t
```

v
a
l
_
l
o
s
s
 
평
균
 
:
 
0
.
1
6
3
9
9
7
2




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
2
4
7
9
6
8
4
]
,
	
	


 
 
 
 
 
 
 
[
2
.
7
1
1
1
9
7
1
]
,
	
	


 
 
 
 
 
 
 
[
1
.
6
5
2
1
2
0
4
]
,
	
	


 
 
 
 
 
 
 
.
.
.
,
	
	


 
 
 
 
 
 
 
[
2
.
2
2
1
5
5
1
7
]
,
	
	


 
 
 
 
 
 
 
[
2
.
1
3
4
7
4
4
4
]
,
	
	


 
 
 
 
 
 
 
[
2
.
5
1
5
7
2
5
9
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
	
	


#
 
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
의
 
에
폭
 
저
장
 
회
차
를
 
달
리
하
고
,
 
이
외
 
같
은
 
조
건
을
 
사
용
하
였
을
 
때


#
 
에
폭
 
저
장
 
회
차
 
2
 
>
 
4
 
>
 
8
 
순
으
로
 
v
a
l
_
l
o
s
s
 
평
균
이
 
낮
아
졌
습
니
다
.


#
 
이
는
 
에
폭
 
저
장
 
회
차
를
 
적
게
 
할
 
수
록
,
 
저
장
되
는
 
데
이
터
 
값
이
 
많
아
지
므
로
 
v
a
l
_
l
o
s
s
의
 
값
이
 
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


#
 
또
한
 
같
은
 
조
건
을
 
사
용
하
였
을
 
때
,
 
콜
백
함
수
는
 
 
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
f
a
c
t
o
r
=
0
.
1
추
가
,
 
0
.
1
6
1
3
3
4
7
8
3
)
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
0
.
1
6
5
5
6
7
1
5
4
)
 
순
으
로
 
v
a
l
_
l
o
s
s
 
가
 
작
아
졌
습
니
다
.




#
 
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
는
 
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
과
 
달
리
 
f
a
c
t
o
r
=
0
.
1
을
 
적
용
하
여
 
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
를
 
지
속
 
줄
여
나
갔
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




#
 
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
의
 
저
장
 
회
차
를
 
적
게
하
여
 
저
장
 
주
기
를
 
빨
리
하
는
 
것
도
 
v
a
l
_
l
o
s
s
 
향
상
에
 
도
움
이
 
될
 
수
 
있
으
나
,
 
이
는
 
처
리
 
시
간
을
 
늘
리
게
 
되
는
 
단
점
이
 
있
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
2
.
s
h
a
p
e
```

<pre>
(
1
2
5
3
,
 
1
3
)
</pre>
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
의
 
l
o
g
값
으
로
 
학
습
을
 
진
행
했
으
므
로
 
r
e
s
u
l
t
값
에
 
e
x
p
으
로
 
반
환
하
고
,
 
소
수
점
 
첫
째
자
리
까
지
 
반
환
하
기
 
위
하
여
 
n
p
.
r
o
u
n
d
를
 
사
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
T
a
r
g
e
t
'
]
=
n
p
.
r
o
u
n
d
(
n
p
.
e
x
p
(
r
e
s
u
l
t
)
)

s
u
b
```

<pre>
 
 
 
 
 
 
 
 
i
d
 
 
T
a
r
g
e
t

0
 
 
 
 
 
 
 
 
1
 
 
 
 
1
0
.
0

1
 
 
 
 
 
 
 
 
2
 
 
 
 
1
5
.
0

2
 
 
 
 
 
 
 
 
3
 
 
 
 
 
6
.
0

3
 
 
 
 
 
 
 
 
4
 
 
 
 
1
0
.
0

4
 
 
 
 
 
 
 
 
5
 
 
 
 
1
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

2
9
1
9
 
 
2
9
2
0
 
 
 
 
 
4
.
0

2
9
2
0
 
 
2
9
2
1
 
 
 
 
 
7
.
0

2
9
2
1
 
 
2
9
2
2
 
 
 
 
 
9
.
0

2
9
2
2
 
 
2
9
2
3
 
 
 
 
 
8
.
0

2
9
2
3
 
 
2
9
2
4
 
 
 
 
1
2
.
0


[
2
9
2
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
