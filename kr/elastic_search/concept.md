# Elastic Search

Elastic사가 개발하고 있는, Lucene 기반의 오픈소스 분산 전문 검색 엔진

실시간으로 방대한 양의 데이터를 검색, 분석할 수 있다. 로그를 수집하는 Logstash, 데이터를 시각화하는 Kibana 등과 같이 사용되는 경우가 많다



( 참조 : https://docs.bonsai.io/article/122-shard-primer )

![img](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5bd08cb42c7d3a01757a5894/images/5c6c66f2042863543ccd30ac/file-M9aMzgYZ9s.jpg)

- Cluster

  Node의 집합

  

- Node

  서버와 같은 개념으로, 1개의 서버에 1개의 Node가 존재한다

  Master Node / Data Node 으로 나뉜다

  검색 트래픽이 증가할 때 Node도 증가시켜서, 처리속도의 분산이 가능하게 만들었다

  

- Index

  RDB의 Database에 해당하는 개념

  1개의 Cluster에 복수의 Index를 작성할 수 있다

  

- Type

  RDB의 Table에 해당하는 개념

  1개의 Index에 복수의 Type을 작성할 수 있다

  

- Document

  RDB의 Row에 해당하는 개념

  Document는 Type 안에서 식별가능한 ID를 가진다

  복수의 Field를 가지고, 네스트된 정보도 표현가능하다

  

- Shard

  Index를 작성하면, 퍼포먼스 분산을 위해 복수의 Shard으로 구성된다

  데이터는 여러 개의 Shard로 분할되어 저장된다

  기본적으로 5개의 Primary Shard과 동일한 수의 복사본 Replica Shard (읽기전용) 가 작성된다

  