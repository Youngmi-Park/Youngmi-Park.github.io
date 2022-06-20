---
title:  "[BOJ] 1439번 뒤집기 (Python)"
excerpt: ""
strapline: ""
toc: true
comments: true
mathjax: true
toc_sticky: true
header:
  overlay_image: /assets/img/02.jpg
categories:
  - Python
tags:
  - python
  - 코딩테스트
  - codingtest
  - BOJ
  - 백준
  - Baekjoon
last_modified_at: 2022-06-19
---

# [BOJ] 1439번 뒤집기 (Python)

[1439번: 뒤집기](https://www.acmicpc.net/problem/1439)

**풀이 아이디어1**

연속된 숫자는 1개로 처리할 수 있다.

00011100 → 010 으로 봤을 때 가운데 1 한번만 뒤집어도 모든 숫자를 같게 만들 수 있다.

즉 전체 문자열을 확인하면서 0과 1이 시작하는 지점의 개수를 세고 둘 중 작은 것을 뒤집으면 최소 횟수로 숫자를 같게 만들 수 있다.

 

```python
n = str(input())
zero = 0
one = 0
state = ''
for i in n:
    if i == '0' and state != '0':
        zero += 1
        state = '0'
    elif i == '1' and state != '1':
        one += 1
        state = '1'
print(min(zero,one))
```

**풀이 아이디어2**

1. 숫자가 바뀐 횟수를 체크한다.

- 000011100 = 3

- 0000000 = 1

- 0011001001110 = 7

2. 횟수를 2로 나눈 몫을 구하고 int로 바꿔서 소수점은 버린다.

- 3//2=1.5 → 1

- 1//2=0.5 → 0

- 7//2=3.5 → 3

```python
n = input()
change = 0
prev = ''
for i in n:
    if i != prev:
        prev = i
        change += 1

print(change//2)
```

![image](https://user-images.githubusercontent.com/53163222/174517517-87c1c733-e01b-4fc9-b597-de802c3a4d5a.png)


둘 다 for문으로 전체를 확인하는 방법이라 실행 시간은 똑같이 나왔다