# [Submodule](https://git-scm.com/book/ja/v1/Git-のさまざまなツール-サブモジュール)

외부의 프로젝트를 자신의 프로젝트 안에서 사용하고 싶을 때 쓴다.



### 등록해보자！

```
git submodule add git@XXXXXX:hoge-project/other-library.git test
```

소스가 자동으로 최신 버젼으로 업데이트되려면 이하 명령도 실행할 필요가 있다

```
git submodule update --remote
```

그러면  리포지터리 하위에  `.gitmodules`라는 파일이 만들어져 있는 것을 확인할 수 있다

내용은 이런 느낌👇

```
[submodule "test"]
	path = test
	url = git@XXXXXX:hoge-project/other-library.git
```



### 에러가 발생하면…

```
'test' already exists in the index
```

```
'test' already exists and is not a valid git repo
```

위와 같은 에러가 발생한다면, 지정한 폴더가 cache에 등록되어 있는지 확인할 필요가 있다

```
git ls-files --stage 
```

↑의 명령으로 리스트에 그 폴더가 존재하는지 확인하고, 존재한다면 그 cache를 지우자

```
git rm -r --cached test
```

그리고, 다시 한번 등록하는 명령을 시도해볼 것



### 다른 사람과 리포지터리를 공유하고 있을 때

리포지터리를 새로 clone하면 정상적으로 Submodule의 소스를 볼 수 있다

하지만 기존의 clone에서는 텅 빈 폴더로 보이는 경우가 있다고 한다🙊

그럴 때는 이하를 실행해보자

```
git submodule init
git submodule update
```