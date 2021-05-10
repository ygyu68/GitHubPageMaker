---
layout: post
current: post
cover:  assets/built/images/developer.jpg
navigation: True
title: 파이썬 메모이제이션(Memoization)
date: 2021-05-09 16:40:00
tags: [python]
class: post-template
subclass: 'post tag-python'
author: ygyu68
---
{% include python-table-of-contents.html %}

---

# <span style="color:blue">메모이제이션(Memoization)</span>

---
## 개요

동일한 계산을 여러 번 반복해야 하는 경우, 한 번 계산한 결과를 메모리에 저장해 두었다가 필요한 경우 꺼내서 사용함으로써 중복 계산을 방지하는 기법.

동적 계획법의 핵심이 되는 기술로, 메모리라는 공간 비용을 투입해서 계산에 소요되는 시간 비용을 줄이는 방법이다.

[메모이제이션]: https://namu.wiki/w/%EB%A9%94%EB%AA%A8%EC%9D%B4%EC%A0%9C%EC%9D%B4%EC%85%98	"메모이제이션"

## 예시

피보나치 수열을 일반적인 방법과 메모이제이션을 활용한 방법으로 구해보자.

(1) 일반적인 방법

```python
def fibonacci(a):
    if a < 2:
        return a
    return fibonacci(a-2) + fibonacci(a-1)
```

(2) 메모이제이션을 활용한 방법

```python
max_value=int(input())
m=[0]*max_value

def fibonacci(a):
    if a < 2:
        return a
    elif m[a]:
        return m[a]
    m[a] = fibonacci(a-1)+fibonacci(a-2)
    return m[a]
        
```

아래와 같이 메모이제이션을 활용하면 `m`이라는 리스트에 이미 계산한 피보나치 값을 넣어 두고 그 값을 필요로 하는 경우 바로 가져올 수 있도록 한다.