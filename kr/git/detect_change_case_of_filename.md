# 파일명의 대소문자 변경을 적용시키기

```zsh
$ git config --list
```

먼저 이 명령으로 리포지터리의 설정을 확인할 수 있다

디폴트로 `core.ignorecase` 가 true로 되어있는데, 이것을 false로 수정할 필요가 있다



```zsh
$ git config core.ignorecase false
```

으로 간단하게 완료!

