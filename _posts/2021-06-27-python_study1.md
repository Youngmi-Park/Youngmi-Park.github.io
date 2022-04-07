---
title:  "[Python 기초] 파이썬 자료형 - 문자열(String)"
excerpt: "파이썬의 기본이자 핵심단위인 자료형을 알아보자"
toc: true
toc_sticky: true
header:
  teaser: /assets/images/python_logo.jpg

categories:
  - data_handling
tags:
  - python
  - 데이터
  - 기초
  - 데이터 분석
  - 파이썬 독학
  - 자료형
  - type
  - 문자열
  - 문자형
  - string
  - str
  - 인덱싱
  - 슬라이싱
  - indexing
  - slice
  - slicing
  - format
  - 포멧
  - 포멧팅
  - count
  - find
  - join
  - upper
  - lower
  - strip
  - lstrip
  - rstrip
  - replace
  - split


last_modified_at: 2019-06-27T08:20:00-20:30
---

# 개요  

![jpg](/assets/images/python_logo.jpg){: .align-center}{: width="70%" height="70%"}  

파이썬의 기본이자 핵심단위인 자료형에는 숫자형, 문자형, 리스트, 튜플, 딕셔너리가 있다. 숫자형은 일반적으로 알고 있는 부분이 많으므로 문자형(string)에 대해 공부해보자.  

  
<br/>
# 1. 문자열 생성  
먼저 문자형(string)은 말그대로 문자들의 집합을 의미한다.  

```python
"Python is smart"
"a"
"123"
```

이와 같이 큰따옴표로 둘러싸인 모든 문자를 문자열이라고 할 수 있다.  
문자열을 생성하려면 ```''```나 ```""```, ```"""``` 으로 문자를 감싸서 만들 수 있다.  
이처럼 생성방식이 다양한 이유는 문자열 안에 ```'```나 ```"```가 포함되어야 할 경우가 있기 때문이다.  

```python
print('"Python is very easy." he says')
```
    [Output] "Python is very easy." he says
    
예를들면 위와 같다.  


  
<br/>
# 2. 줄바꿈  
다음은 문자열이 너무 길어 작업에 어려움이 있을 경우 유용한 줄바꿈이다.  


```python
multiline="Life is too short\nYou need python"
print(multiline)
```

    [Output] Life is too short
    	 You need python
    

위에서 사용된 ```\n```은 줄바꿈을 위한 [이스케이프 코드](http://python-ds.com/python-3-escape-sequences)이다. 


```python
multiline='''
Life is too short
You need python
'''
print(multiline)
```

    
    [Output] Life is too short
    	 You need python
    
    
다른 방법으로는 ```"""```나 ```'''```를 사용한 방법이 있다.  


  
<br/>
# 3. 문자열 연산  

문자열도 숫자형처럼 사칙연산(덧셈과 곱셈)이 가능하다.  


```python
a = "python"
print(a*2)
print("="*50)
```

    [Output] pythonpython
        	 ==================================================
    

```python
a = "my"
b = "name"
c = "is"
d = "YG analyst"
print(a+b+c+d)
```

    [Output] "mynameisYG analyst"
    

위와 같이 연산자를 이용하면 문자열 자체를 더하거나 곱하는 것이 가능하다.  
띄어쓰기를 적절히 포함시켜주지 않아 그대로 붙여져버린 모습이다.  
이후에 알아볼 공백, 삽입, 인덱싱 등의 함수를 통해 보완할 수 있다.  

  
<br/>
# 4. 문자열 인덱싱(Indexing), 슬라이싱(Slicing)  

'인덱싱'은 어떤 것을 가리키는 의미, '슬라이싱'은 무엇인가를 잘라낸다는 의미이다.  

```python
a = "python"
a[0]
```

    [Output] 'p'

이와 같이 a문자열의 0(첫번째)인덱스의 문자를 가져와준다.  


```python
a[0]+a[1]+a[2:]
```




    [Output] 'python'

앞의 문자열 연산과 인덱싱을 함께 사용해 볼 수 있다.  
결국 인덱싱을 통해 슬라이싱을 할 수 있고 방법 또한 마찬가지라 할 수 있다.  

  
<br/>
# 5. 문자열 포멧팅(Formating)  

필자도 이 기능은 정확하게 몰랐으나 기초부터 다시 공부하면서 알게된 포멧팅이다. 쉽게 말해 문자열에 어떤 것을 대입해주는 기능이다.  

- **숫자 format**  


```python
"I eat %d apples." % 3
```

    [Output] 'I eat 3 apples.'



- **문자 format**  


```python
"I eat %s apples." % "five"
```

    [Output] 'I eat five apples.'

- **변수를 이용한 format**  


```python
number = 3
"I eat %d apples." % number
```

    [Output] 'I eat 3 apples.'

- **2개의 변수를 이용한 format**  


```python
number = 10
day = "three"
"I ate %d apples. so I was sick for %s days." % (number, day)
```

    [Output] 'I ate 10 apples. so I was sick for three days.'

이와 같이 문자열 내의 숫자나 특정 문자가 업데이트 되어야 하거나 변경의 여지가 있을 경우, format을 이용한 작업을 수행할 수 있다.  

| 코드 | 설명 |
|:---:|:---:|
| %s | 문자열(String) |
| %c | 문자 1개(character) |
| %d | 정수(integer) |
| %f | 부동 소수(floating-point) |
| %o | 8진수 |
| %x | 16진수 |
| %% | Literal % (문자 '%' 자체) |

특히 ```%s```의 경우 어떤 형태의 값이든 변환이 가능한 코드이므로 매우 유용하다.  


```python
"Error is %d%%." % 98
```


    [Output] 'Error is 98%.'


마지막의 ```%%```는 위의 결과처럼 ```%```가 코드가 아닌 문자로 쓸 필요가 있을 경우 사용한다.  

  
<br/>
# 6. 문자열 관련 함수  

문자열과 관련해 유용하게 쓰이는 함수를 소개한다.  

- **count()**  

```python
a = "python is good"
a.count('o')
```
    [Output] 3


해당 문자가 문자열에 포함된 개수를 반환한다.  


- **find() & index()** 

```python
a = "python is good"
a.find('o')
```
    [Output] 4
    
```python
a = "python is good"
a.find('x')
```
    [Output] -1

해당 문자가 처음나온 위치를, 포함된게 없으면 ```-1```을 반환한다.  


```python
a = "python is good"
a.index('t')
```

    [Output] 2

해당 문자가 처음나온 위치를, 포함된게 없으면 오류가 난다.  
두 함수는 앞의 문자열 인덱싱과 똑같이 사용된다.  

- **Join()** 

```python
a = ","
a.join('abcd')
```

    [Output] 'a,b,c,d'

abcd의 각각의 문자 사이에 ```,```를 삽입한다.  


- **upper() & lower()** 

```python
a = "hellow world"
a.upper()
```

    [Output] 'HELLOW WORLD'


```python
a.lower()
```

    [Output] 'hellow world'

대소문자를 변경해주는 함수이다.  
텍스트 전처리에 유용하게 사용했던 경험이 있다.  

- **strip() & lstrip() & rstrip()** 

```python
a = " hi "
a.strip()
```

    [Output] 'hi'

```python
a.lstrip()
```

    [Output] 'hi '

```python
a.rstrip()
```

    [Output] ' hi'


strip()은 문자열에 포함된 공백을 제거해주는 함수로 lstrip은 왼쪽공백, rstrip은 오른쪽 공백이다.  
문자열의 양끝의 공백들만을 처리하기 때문에 크게 유용하진 않다.  


- replace()

```python
a = "That's too bad"
a.replace("too","not")
```

    [Output] "That's not bad"

이 함수는 ```replace("old","new")```처럼 이전 문자열을 대체하는 역할을 한다.  
```python
a = "hi my name is YG analyst"
a.replace(" ","")
```
    [Output] 'himynameisYGanalyst'
    

이처럼 중간중간 위치한 공백을 지우기 위해서는 ```strip()```함수로는 불가능하고,  
```replace()```를 써서 활용이 가능하다.


- split()

```python
### 문자열 나누기
a = "That's to bad"
a.split()
```

    [Output] ["That's", 'to', 'bad']


```python
a = "a.b.c.d.e"
a.split('.')
```

    [Output] ['a', 'b', 'c', 'd', 'e']

이 함수는 ```split('기준 문자')``` 처럼, 특정 값을 기준으로 문자열을 나누어 주는 기능이다. 아무 값도 넣어주지 않으면 공백을 기준으로 나누어 준다.  



  
<br/>
# Reference  

도서 [**[점프 투 파이썬](https://wikidocs.net/book/1)**] 를 공부하며 작성하였습니다.  

