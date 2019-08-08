# 표준 스트림

UNIX에서 컴퓨터 프로그램과 그 환경 사이에 미리 연결된 입출력 통로. 실행 시 세 개의 스트림이 자동으로 열린다. 

UNIX 이전의 프로그램들은 적절한 입력 장치, 출력 장치를 연결하거나 시스템의 환경설정을 해야 하는 등 여러 가지 신경 써야 할 것들이 많았다. 하지만 UNIX로 이러한 번거로운 것들을 하지 않아도 커맨드라인에서 간단하게 값을 주고받는 것이 가능해졌다!



### 표준입력

프로그램이 입력받는 데이터.  정수 `stdin`를 사용한다

```php
<?php
echo "Do you want to continue this? (yes/no):"
$input = fopen('php://stdin', 'r');
if(trim(fgets($input)) != 'yes'){
    echo 'Game Over!\n';
    exit;
}
echo 'OK!';
```

```zsh
$ php sample.php
Do you want to continue this? (yes/no)
yes
OK!
```



### 표준출력

프로그램이 실행결과를 기록하는 스트림. 정수 `stdout`를 사용한다

```php
$message = 'standard output!';
fwrite(STDOUT, $message);
```



### 표준에러출력

에러메세지나 진단 메세지를 기록하기 위한 스트림. 정수 `stderr`를 사용한다

```php
$message = 'standard error!';
fwrite(STDERR, $message);
```

