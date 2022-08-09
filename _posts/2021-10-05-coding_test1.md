---
title:  "[Coding Test] 노트 "
excerpt: "유용한 표현 정리"
strapline: "유용한 표현 정리"
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

# 변수 값 입력받기

```python
a, b = map(int, input().split())
```

코딩테스트에서 조건을 입력받을 때 map함수를 이용해 변수 a, b 에 값을 할당해준다.

# 한줄을 리스트로 입력받기
```python
a = list(map(int, input().split()))
```
2 7 8 3 1 → [2, 7, 8, 3, 1]
 

# n개 줄을 리스트로 입력으로 받기
```python
a = []
for i in range(n):
     a.append(int(input()))
```
     
```python
a = [int(input()) for _ in range(n)]
```

# 0이 n개 있는 1차원 리스트
```python
a = [0] * n
a = [0 for _ in range(n)]
```