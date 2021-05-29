---
layout: single
title: "python lambda"
---


# Python - 람다(lambda)



함수를 딱 한 줄만으로 만들 수 있게 해주는 애. 아래처럼 사용한다.

```python
lambda 인자 : 표현식
```





### sort()

다중 조건에 대하여 정렬할 때, 람다를 사용하면 훨씬 간편. 이번에 lambda를 찾아보게 된 이유.

```python
# 글자수 내림차순, 같다면 사전 순으로 정렬하기
arr = ['banana', 'pineapple', 'vienna', 'coffee', 'house']
```

```python
# 그동안의 내 코드
temp = []
for i in range(len(arr)):
    temp.append((-len(arr[i]), arr[i]))    
temp.sort()

result = []
for i in range(len(arr)):
    result.append(temp[i][1])    
```

```python
# lambda 활용한다면 한 줄 끝
result = sorted(arr, key=lambda x: (-len(x), x))
```





그 밖에 람다를 같이 사용하면 좋은 함수들.



### map()

우선 map 함수는 함수와 리스트를 인자로 받아, 리스트로부터 원소 하나씩 꺼내 함수를 적용시킨 다음, 그 결과를 새로운 리스트에 담아 리턴한다.

```python
>>> list(map(lambda x : x ** 2, range(5)))
[0, 1, 4, 9, 16]
```





### reduce()

`reduce(집계함수, 순회 가능한 데이터[, 초기값])` 

```python
>>> from functools import reduce
>>> reduce(lambda x, y: x + y, [0, 1, 2, 3, 4])
10

>>> reduce(lambda x, y: y + x, 'abcde')
'edcba'
```





### filter()

`filter(함수, 리스트)` 원소들을 함수에 적용시켜, 참인 값들을 담은 리스트를 리턴.

```python
>>> list(filter(lambda x: x % 2, range(10)))
[1, 3, 5, 7, 9]
```



