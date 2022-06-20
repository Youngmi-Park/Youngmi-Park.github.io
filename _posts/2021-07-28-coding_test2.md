---
title:  "[Python 기초] 파이썬 Join, Split 함수"
excerpt: "리스트를 문자열로, 문자열을 리스트로"
strapline: "리스트를 문자열로, 문자열을 리스트로"
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
  - 데이터
  - 기초
  - 파이썬 독학
  - 자료형
  - type
  - 문자열
  - string
  - str
  - join
  - split 
last_modified_at: 2021-07-16
---


## Join

파이썬 내장 함수 join을 이용하면 리스트를 문자열로 만들 수 있다.

join 함수는 리스트(list)를 특정 구분자(separator)로 구분하여 문자열(string)의 형태로 변환해주는 함수다.

 

\* 이 때, 문자열(str) 타입이 아닌 다른 타입의 데이터가 리스트에 있다면 에러가 발생한다.

 

### 사용 방법

```python
'구분자'.join(리스트명)
```

위와 같은 형태로 리스트를 문자열로 만들 수 있다.

 

 

### 예시

```python
array = ['apple','banana','grape','cherry']
 
' '.join(array) # 빈칸으로 리스트를 연결
# apple banana grape cherry
 
'-'.join(array) # -로 리스트를 연결
# apple-banana-grape-cherry
```

## Split


 
split함수는 리스트를 특정 구분자로 구분하여 문자열로 변환해주는 join 함수와는 반대의 기능을 한다고 할 수 있다.

문자열을 일정한 규칙으로 잘라서 리스트로 만들어 주는 함수이다.
 

### 사용 방법

```python
문자열.split()
문자열.split('구분자')
문자열.split('구분자', 분할횟수)
문자열.split(sep='구분자', maxsplit=분할횟수)
```

 

위와 같이 다양한 형태가 있는데, 흔히 첫번째 형태를 가장 많이 사용한다. 그리고 네 번째가 가장 정확한 형태라고 할 수 있는데 이는 어떤 문자열을 구분자를 기준으로 분할횟수만큼 잘라서 리스트로 만들어 주는 것을 말한다.

각 파라미터에 대해 자세히 설명하면,

**sep**

- 'sep=' 생략 가능
-    e.g. 문자열.split() 

- default: none (' ' 공백, '\t' 탭, '\n' 엔터)
-    e.g. 문자열.split(sep='-') → 문자열에서 '-' 를 기준으로 자른다.

**maxsplit**

- sep 파라미터가 있어야 생략 가능하다.
-    e.g. 문자열.split(1) X     문자열.split('-', 1) O    문자열.split(maxsplit=1) O 

- default: -1 (자를 수 있을 때 까지. 즉, 문자열 전체)
-    e.g. 문자열.split(maxsplit=1) → 문자열을 한번만 자른다.

 

### 예시

\1) 파라미터가 없는 예시

```python
s = "h e l l o"
print(s) # h e l l o
 
result = s.split()
print(result) # ['h', 'e', 'l', 'l', 'o']
```

이 예시에서는 띄어쓰기를 기준으로 문자열을 구분했고 maxsplit 파라미터도 지정하지 않았으므로 문자열 전체를 나누었다.

 
\2) 파라미터를 지정한 예시

```python
s = "h-i-h-e-l-l-o"
print(s)
 
result1 = s.split()
result2 = s.split('-')
result3 = s.split('-', 4)
result4 = s.split(sep='-')
result5 = s.split(sep='-', maxsplit=4)
result6 = s.split('-', maxsplit=4)
 
print(result1) # ['h-i-h-e-l-l-o']
print(result2) # ['h', 'i', 'h', 'e', 'l', 'l', 'o']
print(result3) # ['h', 'i', 'h', 'e', 'l-l-o']
print(result4) # ['h', 'i', 'h', 'e', 'l', 'l', 'o']
print(result5) # ['h', 'i', 'h', 'e', 'l-l-o']
print(result6) # ['h', 'i', 'h', 'e', 'l-l-o']
```

 