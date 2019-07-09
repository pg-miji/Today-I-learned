# 커밋했는데、유저가 잘못됐어！

```zsh
$ git config --list
```

먼저 이 명령으로 리포지터리의 설정을 확인할 수 있다. 

직접 `~/.gitconfig` 파일을 수정해도 OK



```zsh
$ git config user.name "myname"
$ git config user.email myname@test.com
```

에 의해 유저 정보를 변경. 이것으로 앞으로의 커밋은 지정한 유저로 커밋이 가능하다👍



```zsh
$ git commit --amend --reset-author
```

```zsh
$ git commit --amend --author="myname <myname@test.com>"
```

위 두 명령 중 하나를 실행하고, 

```zsh
$ git rebase --continue
```

를 입력하면 직전의 커밋을 변경할 수 있다



```zsh
$ git log --pretty=full
commit XXXXXXXXXXXXXXXXXX
Author: myname <myname@test.com>
Date: Thu July 9 16:18:20 2019 +0900
```

제대로 수정되었는지 Git의 로그를 확인

문제 없으면 그대로 push하기！

```zsh
$ git push -f
```

