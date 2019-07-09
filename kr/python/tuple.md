# tuple 자료형

여러 개의 요소를 하나의 변수로 관리하고 싶을 때 사용한다. Wikipedia에는「tuple은 용도와 타입이 다른 오브젝트를 하나로 모을 때 사용한다」고 적혀있다

-  소괄호를 사용하여 만든다

- **만든 후에 값을 바꿀 수 없다** = 읽기 전용!



### 만들기

```python
t = ()
t = tuple()
t = (1,)
t = (1, 2, 3)
t = ("start", "end")
t = ("play", ("pause", "record"))
```

1개의 요소만을 가질 때에는 `,`를 반드시 붙여야 한다!



### 인덱싱하기

````python
>>> t = ("play", "pause", "record")
>>> print(t[3])
"pause"
````



### 슬라이싱하기

```python
>>> t = ("play", "pause", "record", "next")
>>> print(t[3:])
("record", "next")
```



### 연결하기

```
>>> t1 = (1, 2, 3)
>>> t2 = ('a', 'b', 'c')
>>> print(t1 + t2)
(1, 2, 3,'a', 'b', 'c')
```



### 특정 값을 가지고 있는지 확인하기

```python
>>> t = ("play", "pause", "record")
>>> print("play" in t)
true
```

