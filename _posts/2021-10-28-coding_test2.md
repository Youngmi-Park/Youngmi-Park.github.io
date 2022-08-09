---
title:  "[Coding Test] 이코데 그리디 알고리즘 "
excerpt: "이코테 그리디 알고리즘 예제와 실전문제"
strapline: "이코테 그리디 알고리즘 예제와 실전문제"
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
last_modified_at: 2021-10-28
---


# Greedy Algorithm

 
탐욕법, 현재 상황에서 가장 좋아 보이는 것만을 선택하는 알고리즘

시간상으로 매우 효율적이지만, 순간마다 최선의 선택을 하는 방법으로 항상 최적화되지 않음으로 최종 답이 최적이 아닐 가능성이 있다. 그 때문에 순간의 최적해가 전체 문제의 최적해가 되어야 사용할 수 있다.

사전에 외우고 있지 않아도 풀 가능성이 높은 문제 유형이지만, 많은 유형을 접해보고 훈련해야 한다.

창의력, 문제를 풀기 위한 최소한의 아이디어를 떠올릴 수 있는 능력이 필요!

그 대상이 무엇인지 고민해보고 푸는 것이 중요하다.

ex) 가장 큰 순서대로, 가장 작은 순서대로 등...
 
## 3장 그리디 실전문제2 - 큰 수의 법칙

난이도: ★☆☆

풀이시간:30분

시간제한: 1초

메모리제한: 128MB

기출: 2019 국가 교육기관 코딩 테스트

**문제설명** 

다양한 수의 배열에서 주어진 수들을 M번 더해서 가장 큰수를 만드는 법칙이다. 단, 특정 인덱스의 수가 연속해서 k번을 초과하여 더해질 수 없는 것이 이 법칙의 특징이다.

**풀이 아이디어** 

일단 입력받은 배열을 정렬해서 가장 큰 수와 가장 작은 수로만 큰 수를 만든다. 가장 큰 수를 k번, 그 다음 두 번째로큰 수를 1번, 다시 가장 큰 수 k번 ... (k+1)이 반복된다.

[ first first … first(k번) second ] [ first first … first(k번) second ][ first first ] m번 더해지면 종료한다.

m//(k+1)  가장 큰 수 k번과 두 번째로 큰 수 1번이 반복되는 횟수

m%(k+1) (k+1)로 나누어지지않은 경우 가장 큰 수가 더해지는 횟수

```python
n,m,k = map(int, input().split())
num_list = list(map(int, input().split()))
answer = 0

num_list.sort() # 입력받은 리스트 정렬
first = num_list[-1] # 가장 큰 수
second = num_list[-2] # 두번 째로 큰수

count = m // (k+1)
remain = m % (k+1)

answer = (first * k * count) + (second * count) + (first * reamin)

print(answer)
```

## 3장 그리디 실전문제2 - 큰 수의 법칙

난이도: ★☆☆

풀이시간:30분

시간제한: 1초

메모리제한: 128MB

기출: 2019 국가 교육기관 코딩 테스트

**문제설명** 

여러개의 숫자 카드 중에서 가장 높은 숫자가 쓰인 카드 한장을 뽑는 게임. 단, 게임의 룰을 지켜야 한다. <게임의 룰>

1. 숫자가 쓰인 카드들이 N*M형태로 놓여있다. N: 행의 개수 M: 열의 개수
2. 먼저 뽑고자하는 카드가 포함되어 있는 행을 선택한다.
3. 선택된 행에 포함된 카드들 중 가장 숫자가 낮은 카드를 뽑아야한다.
4. 따라서 처음에 카드를 골라낼 행을 선택할 때, 이후에 해당 행에서 가장 숫자가 낮은 카드를 뽑을 것을 고려하여 최종적으로 가장 높은 숫자의 카드를 뽑을 수 있도록 전략을 세워야한다.

**풀이 아이디어**

for문을 n번 돌면서 각 행마다 가장 작은 수(min 함수)를 찾고 그 중에서 가장 큰 수(max함수)를 찾는다.

```python
n,m = map(int, input().split())
result = 0

for i in range(n):
  a = list(map(int, input().split()))
  min_val = min(a)
  result = max(result, min_val)

print(result)
```
