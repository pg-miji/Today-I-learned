# 기본 명령어

- JVM 옵션・힙사이즈

```zsh
cat /etc/elasticsearch/jvm.options
```

- 기본정보・상태 확인

```zsh
curl -X GET http://localhost:9200/
```

- 헬스체크

```zsh
curl -X GET http://localhost:9200/_cluster/health?pretty
```

- Index 리스트

```zsh
curl -X GET http://localhost:9200/_cat/indices
```

- 도큐먼트 확인

```zsh
curl -X GET http://localhost:9200/shop/item/1?pretty
```

- 색인별명 확인

```zsh
curl -X GET http://localhost:9200/_aliases?pretty
```

