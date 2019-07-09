# tuple 組み込み型

複数の要素を一つの変数で管理したいときに使う。Wikipediaによると、「タプルは用途や型が異なるオブジェクトを一つにまとめるために使われる」と書いてある。

-  小括弧を使って生成する

- **作成後に値を変更できない** = 読み取り専用!



### 作成する

```python
t = ()
t = tuple()
t = (1,)
t = (1, 2, 3)
t = ("start", "end")
t = ("play", ("pause", "record"))
```

一つの要素だけを持つときは `,`を必ず付けないといけない！ 



### 取得する

```python
>>> t = ("play", "pause", "record")
>>> print(t[3])
"pause"
```



### 抽出する

```python
>>> t = ("play", "pause", "record", "next")
>>> print(t[3:])
("record", "next")
```



### 連結する

```
>>> t1 = (1, 2, 3)
>>> t2 = ("a", "b", "c")
>>> print(t1 + t2)
(1, 2, 3, "a", "b", "c")
```



### 特定の値が含まれているか確認する

```python
>>> t = ("play", "pause", "record")
>>> print("play" in t)
true
```

