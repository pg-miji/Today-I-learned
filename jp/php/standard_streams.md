# 標準ストリーム

UNIXでプログラムとその環境の間で事前に連結されている入出力の通路。実行されたら、３つのストリームが自動に開かれる。

UNIX 以前のプログラムは適切な入力デバイス・出力デバイスを連結したり、システムの環境設定をするなどいろいろ気にすることがたくさんあった。しかし UNIXでこのような手間をかけなくても、コマンドラインで簡単に値を渡したり出力したりすることができるようになった！



### 標準入力

プログラムに入ってくるデータ。定数`stdin`を利用

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



### 標準出力

プログラムが書き出すデータのストリーム。定数`stdout`を利用

```php
$message = 'standard output!';
fwrite(STDOUT, $message);
```



### 標準エラー出力

エラーメッセージや診断メッセージを出力するための出力ストリーム。定数`stderr`を利用

```php
$message = 'standard error!';
fwrite(STDERR, $message);
```

