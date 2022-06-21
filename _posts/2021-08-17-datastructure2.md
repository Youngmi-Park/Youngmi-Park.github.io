---
title:  "[Data Structure] Stack / Queue / Deque"
excerpt: "Stack / Queue / Deque"
strapline: "Stack / Queue / Deque"
toc: true
comments: true
mathjax: true
toc_sticky: true
header:
  overlay_image: /assets/img/02.jpg
categories:
  - Data Structure
tags:
  - datastructure
  - stack
  - queue
  - deque
  - 자료구조
  last_modified_at: 2021-08-17
---

# Stack / Queue / Deque 

## 1) Stack (스택)
<p align="center">
<img width="50%" src="https://user-images.githubusercontent.com/53163222/116805512-fd9c7a00-ab61-11eb-8c11-96e37b2942d2.png">
</p>

차곡차곡 쌓아 올린 형태의 자료구조로 입구와 출구가 동일한 형태로 시각화 할 수 있다.
후입선출(LIFO, Last-in First-out)
시간 순서에 따라 자료가 쌓여서 가장 마지막에 삽입된 자료가 가장 먼저 삭제되는 구조  
 
### 특징
- 같은 구조와 크기의 자료를 정해진 방향으로만 쌓을 수 있다.
- top은 가장 위에 있는 최근에 들어온 자료를 가리키고 있다.
- top으로 정한 곳을 통해서만 접근하고 연산할 수 있다.


- push: top을 통해 데이터를 삽입하는 연산
- pop: top을 통해 데이터를 삭제하는 연산
  
- stack underflow: 비어있는 스택에서 원소를 추출하려고 할때 
- stack overflow: 스택이 넘치는 경우

<br>
*stack을 배열 또는 연결리스트 혹은 그 외의 것을 이용하여 구현할 수 있다.
stack 자체는 정의이기 때문에 다양한 자료구조를 통해 구현 가능하다!*

### 시간 복잡도
- 삽입 : O(1)
- 삭제 : O(1)
- 탐색 : O(N)

### 사용
- 웹 브라우저 방문기록 (뒤로 가기) : 가장 나중에 열린 페이지부터 다시 보여준다.
- 역순 문자열 만들기 : 가장 나중에 입력된 문자부터 출력한다.
- 실행 취소 (undo) : 가장 나중에 실행된 것부터 실행을 취소한다.
- 후위 표기법 계산
- 수식의 괄호 검사 (연산자 우선순위 표현을 위한 괄호 검사)
- 깊이 우선 탐색(DFS, Depth-First Search) 구현 - 내가 현재 있는 위치에서 이동할 수 있는 위치를 stack에 모두 넣고 꺼내는 식으로 풀이 가능


## 2) Queue (큐)
<p align="center">
<img width="50%" src="https://user-images.githubusercontent.com/53163222/116805527-14db6780-ab62-11eb-891d-db6f490c9012.png">
</p>

### 특징
선입선출(FIFO, First-in First-out)
입구와 출구가 모두 뚫려 있는 터널의 형태로 시각화 할 수 있다.
rear, front가 존재

### 시간 복잡도
- 삽입 : O(1)
- 삭제 : O(1)
- 탐색 : O(N)

### 사용
- 주로 데이터가 입력된 시간 순서대로 처리해야 할 필요가 있는 상황에 이용
- 우선순위가 같은 작업 (프린터의 인쇄 대기열)
- 은행 업무, 콜센터 업무
- 프로세스 관리
- 캐시(Cache) 구현
- 너비 우선 탐색(BFS, Breadth-First Search) 구현 - 내가 현재 있는 위치에서 이동할 수 있는 위치를 queue에 모두 넣고 꺼내는 식으로 풀이 가능


## 3) Deque (데크)
double-ended queue 의 줄임말로, 앞과 뒤에서 즉, 양방햐에서 데이터를 처리할 수 있는 queue형 자료구조를 의미한다.
<p align="center">
<img width="50%" src="https://user-images.githubusercontent.com/53163222/116805516-00976a80-ab62-11eb-8bbf-accd184a6eed.png">
</p>

python의 collections에서 deque를 제공하고 있는데, 여기서 deque는 list와 일부 유사하다.
자세한 메소드 활용 코드는 [여기](python/deque.py)에서 확인할 수 있다.
deque의 전체 메소드는 [여기](docs.python.org)에서 확인할 수 있다.
