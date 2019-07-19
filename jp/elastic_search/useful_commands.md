# よく使うコマンド

- JVM オプション・ヒープサイズ

```zsh
cat /etc/elasticsearch/jvm.options
```

- 基本情報・状態確認

```zsh
curl -X GET http://localhost:9200/
```

- ヘルスチェック

```zsh
curl -X GET http://localhost:9200/_cluster/health?pretty
```

- Indexの一覧

```zsh
curl -X GET http://localhost:9200/_cat/indices
```

- ドキュメント取得

```zsh
curl -X GET http://localhost:9200/shop/item/1?pretty
```

- エイリアス取得

```zsh
curl -X GET http://localhost:9200/_aliases?pretty
```

