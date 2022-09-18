---
title:  "[Coding Test] 2차원 리스트 90도 회전"
excerpt: "2차원 리스트를 시계방향으로 90도 회전시키는 방법"
strapline: "문제에서 입력 받는 다양한 방법 정리"
toc: true
comments: true
mathjax: true
toc_sticky: true
header:
  overlay_image: /assets/img/02.jpg
categories:
  - Coding Test
tags:
  - python
  - 코딩테스트
  - codingtest
  - 이것이코딩테스트다
  - 이코테
  - 백준
  - 프로그래머스
last_modified_at: 2021-10-05
---

<p align="center">
<img  width="50%" src="https://user-images.githubusercontent.com/53163222/190881548-6f62eb86-481e-4de1-a29a-bfc00b4e95b5.png"/>
</p>

# 2차원 리스트 90도 회전

90도 회전했을 때 행, 열이 변하는 규칙을 정리하면 다음과 같다.
- 회전한 후 행 번호 = 회전하기 전 열 번호
- 회전한 후 열 번호 = N - 1 - 회전하기 전 행 번호
 
 
이러한 규칙을 코드로 나타내면 다음 코드와 같다.
 
## 리스트를 시계방향으로 90도 회전하는 일반적인 방법
```python
def rotated(array_2d):
    n = len(array_2d) # 행 길이
    m = len(array_2d[0]) # 열 길이 
    result = [[0] * n for _ in range(m)] # 회전한 결과를 표시하는 배열

    for i in range(n):
        for j in range(m):
            result[j][n-i-1] = array_2d[i][j]
    return result
```

리스트 회전은 zip함수를 사용하여 구현할 수도 있다.

## zip함수를 사용하는 방법
```python
def rotated(array_2d):
    list_of_tuples = zip(*array_2d[::-1])
    return [list(e) for e in list_of_tuples]
```

위 코드의 자세한 동작과정은 다음과 같다. 

1.  배열을 역순으로 바꾼다.
```python
array_2d = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

reversed_ = array_2d[::-1]
print(reversed_)
>>> [[7, 8, 9], [4, 5, 6], [1, 2, 3]]
```

2. 2차원 배열의 인자를 별표(*, Asterisk)로 unpacking하고 zip()으로 묶어준다.
- unpacking은 괄호 안에 있던 데이터들을 풀어 각각으로 만들어 준다.
- zip()은 각 인자들을 tuple로 묶어 zip object로 반환한다.

```python
list_of_tuples = zip(*array_2d[::-1])
print(list_of_tuples)
>>> <zip object at 0x7f16a09c1540>
```

3. tuple로 반환되는 요소를 리스트로 바꾸어준다.
```python
return [list(e) for e in list_of_tuples]
>>> [[7, 4, 1], [8, 5, 2], [9, 6, 3]]
```

===

## 180도 회전
```python
def rotated(list_2d):
    n = len(list_2d)
    m = len(list_2d[0]) 
    result = [[0] * n for _ in range(m)]
    for i in range(n):
        for j in range(m):
            result[m-j-1][n-i-1] = list_2d[i][j]
    return result
```

## 270도 회전
-90도 회전하는 것과도 같다. 또는 180 + 90도 회전으로 이해할 수 있다.
```python
def rotated(list_2d):
    n = len(list_2d) 
    m = len(list_2d[0])
    result = [[0] * n for _ in range(m)]
    for i in range(n):
        for j in range(m):
            result[m-j-1][i] = list_2d[i][j]
    return result
```

# 리스트 회전을 이용하는 문제
[2020 KAKAO BLIND RECRUITMENT 자물쇠와 열쇠](https://school.programmers.co.kr/learn/courses/30/lessons/60059)
[백준 18808번 스티커 붙이기](https://www.acmicpc.net/problem/18808)