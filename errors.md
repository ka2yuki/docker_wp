ERROERs

`Error establishing a database connection`

- Docker リスタート。✅
- docker-composeの環境設定が間違えてた。`WORDPRESS_DB_HOST=[services-db-name]:3306` ✅
- MysqlがRestart中な可能性がある。`docker ps`待機。

1. PHP7系では「caching_sha2_password」をサポートする接続ライブラリがなく、****
2. MySQL8.0では、新たな認証プラグイン「caching_sha2_password」が導入されてる。

##### `WordPress データベースエラー: [Unknown database 'wordpress']`

[back to README.md](README.md)