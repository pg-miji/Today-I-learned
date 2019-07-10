# ファイル名の大小文字変更を検知させる

```zsh
$ git config --list
```

まず、このコマンドでリポジトリの設定が確認する。

デフォルト設定として`core.ignorecase` がtrueになっていると思うので、これをfalseに直す必要がある。



```zsh
$ git config core.ignorecase false
```

で簡単に完了！

