# コミットしたけど、ユーザー間違えた！

```zsh
$ git config --list
```

まず、このコマンドでリポジトリの設定が確認する。

直接 `~/.gitconfig` ファイルを修正してもOK



```zsh
$ git config user.name "myname"
$ git config user.email myname@test.com
```

によりユーザ情報を変更。これでこれからは指定したユーザーでコミットできるはず👍



```zsh
$ git commit --amend --reset-author
```

```zsh
$ git commit --amend --author="myname <myname@test.com>"
```

上記の二つの中で一つを実行し、

```zsh
$ git rebase --continue
```

を行うと、直前のコミットを修正される



```zsh
$ git log --pretty=full
commit XXXXXXXXXXXXXXXXXX
Author: myname <myname@test.com>
Date: Thu July 9 16:18:20 2019 +0900
```

きちんと修正されたか、Gitのログを確認

問題なければ、pushしよう！

```zsh
$ git push -f
```

