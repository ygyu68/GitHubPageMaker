---
layout: post
current: post
cover:  assets/built/images/developer.jpg
navigation: True
title: 파이썬 내포 함수(Comprehension)
date: 2021-05-07 16:40:00
tags: [python]
class: post-template
subclass: 'post tag-python'
author: ygyu68
---
{% include python-table-of-contents.html %}

---

# <span style="color:blue">내포함수(Comprehension)</span>

---
파이썬에서는 각종 <span style="color:red">내포함수</span>를 사용할 수 있다. 예를 들어,

```python
list1 = []
for x in range(5):
    list1.append(x**2)
list1
```

와 같은 코드블록을 아래와 같이 표현하는 것이다.

```python
list1 = [x**2 for x in range(5)]
list1
```

위 2개의 코드블록의 결과는 모두 `[0, 1, 4, 9, 16]`이 된다. 또한 함수 `sum()`을 통해 주어진 리스트(llist)의 합을 구할 수 있다. 즉, `sum([x**2 for x in range(5)])`  의 결과는 30이 된다.

