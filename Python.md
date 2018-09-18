# Python for PS
코딩테스트 기초 문법

## Table of Contents  
1. [입력](#1.입력)
2. [문자열](#2.문자열)
3. [배열](#3.배열)
4. [계산](#4.계산)
5. [그래프](#5.그래프)


## 1.입력

(python의 버전이 3.0 이하인 경우, input = raw_input)

- 테스트케이스 갯수(T)가 정해진 경우

인풋

```
4
1 2 3 4
```

코드

```
T = input()
arr = [int(v) for v in input().split(' ')]
```

인풋

;첫째 줄에 갯수 나머지 열에는 갯수만큼 반복되는 배열

```
5
4
3 5
1 3 8
2 5 3 4
3 6 6 8 2
```
코드 

```
arr = []
T = input()
for i in range(T):
    arr.append([int(v) for v in input().split(' ')])
```

인풋

```
0110100
0110101
1110101
0000111
0100000
0111110
0111000
```
코드 

```
n = int(input())
a = []
for i in range(n):
    b = input()
    b = [int(v) for v in b]
    a.append(b)
```
인풋

```
2 3 4

```
코드

```
a, b, c = map(int, input().split())
```

enumerate

```
```


## 2.문자열

대소문자

```
x.isupper()
x.upper()
x.lower()
```

아스키 변환

```
ord('z')
chr(96)
```

스트링 체크

```
import string

string.ascii_lowercase
string.digits
```

## 3.배열


존재하니?

```
if x in arr
if not x in arr
```


배열 뒤에 더하고 빼기

```
arr.append("a")
arr.pop()
```


중복제거

```
b = list(set(a))
```


## 4.계산

나눈 몫만 가져오기

`result = n//2`


swap 하기

```
a,b = b,a
```

무한대

```
import math
math.inf
```

3씩 증가하는 for loop

```
for i in range(0, len(arr), 3):
```


i 이전까지 더한 값

```
sum(arr[0:i])
```



## 5.그래프
False로 초기화된 1차원 배열 생성하기

```
visited = [False for j in range(n)]
```

False로 초기화된 2차원 배열
생성하기

```
visited = [[False for j in range(n)] for i in range(m)]
```

상하좌우로 탐색

```
dxdy = [(0,1), (0,-1), (1,0),(-1,0)]
for dx, dy in dxdy:
	xx = x+dx
	yy = y+dy
	findPath(xx, yy)
```



# 끝
틀린 부분이나 추가할 부분이 있다면 PR or 이슈 남겨주세요

*JAVA, C++이 빈약하니 많이 참여해주세요*

# 나중에 정리

```
띄어쓰기 두개 값
    rows, cols = map(int, read().split())

2차원 배열 만드는 더 쉬운 방법
    l = [[0]*cols for _ in range(rows)]
```