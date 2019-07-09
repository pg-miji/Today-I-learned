## 버그가 발생하기 어려운 코드를 작성하자

・코드를 작성할 때에는, 되도록 변수에 의존하지 않도록 짜기

```php
public function execute($command, $value1, $value2)
{
    if($command === 'add'){
        return $value1 + $value2;
    } else if ($command === 'substract'){
        return $value1 - $value2;
    } else if ($command === 'multiply'){
       return $value1 * $value2;
    } else {
       throw new Exception('$command invalid.');
    }
}
```

위의 코드에서 $command에 `addd`라는 잘못 쓴 문자열을 들어오게 되면,  바로 에러가 나지 않고 else까지 가서 에러가 발생하게 된다.  만약 else에서 다른 메소드를 부르기라도 한다면, 에러의 발화점은 더욱 더 파악하기 어려워진다. 

→ 변수에 의존하게 되면, 버그를 발견하더라도 에러의 원인을 찾기 어려워져서 조사하는 데에도 보수하는 데에도 시간이 더 걸린다. 



### 그렇다면 이상적인 코드란？

변수를 메소드화하자！

```php
public function add($value1, $value2){
    return $value + $value2;
}

public function substract($value1, $value2){
    return $value1 - $value2;
}

public function multiply($value1, $value2){
    return $value1 * $value2;
}
```

이 코드가 더 직관적으로 알기 쉽고 원시성이 높다. 불필요한 IF 문도 사라졌기 때문에、버그에도 강하다💪

