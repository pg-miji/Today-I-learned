# [Submodule](https://git-scm.com/book/ja/v1/Git-のさまざまなツール-サブモジュール)

外部のプロジェクトを自分のプロジェクト内に取り込みたいときに使う。



### 登録しよう！

```
git submodule add git@XXXXXX:hoge-project/other-library.git test
```

ソースの自動更新が必要な場合は、以下も実行。

```
git submodule update --remote
```

すると、リポジトリの直下に `.gitmodules`というファイルが生成されたはず！

中身はこういう感じ👇

```
[submodule "test"]
	path = test
	url = git@XXXXXX:hoge-project/other-library.git
```



### エラーが出たら…

```
'test' already exists in the index
```

```
'test' already exists and is not a valid git repo
```

上記のようなエラーが出たら、指定したフォルダがcacheに登録してあるか確認する必要がある。

```
git ls-files --stage 
```

↑のコマンドで、リストにそのフォルダが存在するか確認。

存在したら、そのcacheを消そう！

```
git rm -r --cached test
```

それから、もう一度登録のコマンドをトライしてみる。



### 他の人とリポジトリを共有している場合

リポジトリを再cloneすると正常にSubmoduleのソースが見える。

しかし、既存のcloneだと空に見える場合があるらしい🙊

その時は、以下を実行する。

```
git submodule init
git submodule update
```