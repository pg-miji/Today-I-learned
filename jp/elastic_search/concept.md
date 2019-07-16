# Elastic Search

Elastic社が開発している, Lucene ベースの オープンソース全文検索エンジン

リアルタイムで膨大なデータを検索・分析できる。ログを収集するLogstash、データを可視化するKibanaなどと一緒に使われることが多い



（参照 : https://docs.bonsai.io/article/122-shard-primer ）

![img](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5bd08cb42c7d3a01757a5894/images/5c6c66f2042863543ccd30ac/file-M9aMzgYZ9s.jpg)

- Cluster

  Nodeの集合

  

- Node

  サーバーと同じ概念で、１つのサーバーに1つのNodeが存在する

  Master Node / Data Node に分けられる

  検索トラフィックが増加するときにNodeも増加され、処理速度の分散が可能になっている。

  

- Index

  RDBのDatabaseにが該当する概念

  １つのClusterに複数のIndexを作成できる

  

- Type

  RDBのTableに該当する概念

  1つのIndexに複数のTypeを作成できる

  

- Document

  RDBのRowに該当する概念

  DocumentはTypeの中で識別可能なIDを持つ

  複数のFieldを持ち、ネストされた情報も表現できる

  

- Shard

  Indexを作成すると、パフォーマンスの分散のために複数のShardになっている

  データはいくつのShardに分割して保存される

  基本的に５つのPrimary Shard（書き込み可能な Shard）と同じ数のReplica Shard（読み込み専用）が作成される