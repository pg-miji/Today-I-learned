## バグになりにくいコードを書こう

・コードを書くときは、なるべく変数に依存しないように書くこと。

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

上記のコードで$commandに`addd`というタイポした文字列を渡したら、すぐエラーにならず先のelseでエラーになってしまう。もしelseで他のmethodを呼んでいたとすれば、エラーの発火点はもっと探しにくくなる。

→変数に依存してしまうと、バグになったときにエラーの原因を探しにくくなり保守の時間がかかる。



### 理想のコードとは？

変数を関数化しよう！

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

こちらのコードのほうが直観的でアトミック性がある。無駄なIF文も無くなったので、バグにも強い💪

