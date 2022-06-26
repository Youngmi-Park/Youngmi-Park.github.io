---
title:  "[BOJ] 1260번 DFS와 BFS (Python)"
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
last_modified_at: 2021-11-14
---

# [BOJ] 1260번 DFS와 BFS (Python)

[1260번: DFS와 BFS](https://www.acmicpc.net/problem/1260)

그래프를 DFS로 탐색한 결과와 BFS로 탐색한 결과를 출력

단, 방문할 수 있는 정점이 여러 개인 경우에는 정점 번호가 작은 것을 먼저 방문

더 이상 방문할 수 있는 점이 없는 경우 종료

정점 번호는 1번부터 N번까지.

```python
from collections import deque

n, m, v = map(int, input().split())

graph = [[] for _ in range(n+1)]

for i in range(m):
  a, b = map(int, input().split())
  graph[a].append(b)
  graph[b].append(a)
  graph[a].sort()
  graph[b].sort()
print(graph)

def dfs(graph, visited, v):
  visited[v] = True
  print(v, end=' ')
  for i in graph[v]:
    if not visited[i]:
      dfs(graph, visited, i)
  
def bfs(graph, visited, v):
  queue = deque([v])
  visited[v] = True
  while queue:
    now = queue.popleft()
    print(now, end=' ')
    for i in graph[now]:
      if not visited[i]:
        queue.append(i)
        visited[i] = True

visited = [False] * (n+1)
dfs(graph, visited, v)
print()
visited = [False] * (n+1)
bfs(graph, visited, v)
```

```python
from collections import deque

n, m, v = map(int, input().split())

graph = [[] for _ in range(n+1)]

for i in range(m):
  a, b = map(int, input().split())
  graph[a].append(b)
  graph[b].append(a)

for i in graph:
  i.sort()
  
def dfs(graph, visited, v):
  visited[v] = True
  result1.append(v)
  for i in graph[v]:
    if not visited[i]:
      dfs(graph, visited, i)
  return result1
  
def bfs(graph, visited, v):
  queue = deque([v])
  visited[v] = True
  while queue:
    now = queue.popleft()
    result2.append(now)
    for i in graph[now]:
      if not visited[i]:
        queue.append(i)
        visited[i] = True
  return result2

result1 = []
visited = [False] * (n+1)
print(*dfs(graph, visited, v))
result2 = []
visited = [False] * (n+1)
print(*bfs(graph, visited, v))
```

![image](https://user-images.githubusercontent.com/53163222/175795850-34b7c77b-943d-458d-bb83-198f32dd83b0.png)