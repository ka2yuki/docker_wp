# Start
- docker stop
- docker restart
```sh
docker-compose -f docker-compose.yml up -d 
# check 
docker ps
```
[ブラウザ確認する↗️](http://localhost:8080)
Sample: [docker-compose.yml](https://docs.docker.jp/compose/wordpress.html)
[env_file](https://docs.docker.jp/compose/compose-file.html#env-file)
# Error
##### `Error establishing a database connection`
- Docker リスタート。✅
- docker-composeの環境設定が間違えてた。`WORDPRESS_DB_HOST=[services-db-name]:3306` ✅
- MysqlがRestart中な可能性がある。`docker ps`待機。ガチ遅いabout 3min。（docker-compose.ymlで restart: always だとなる）
1. PHP7系では「caching_sha2_password」をサポートする接続ライブラリがなく、****
2. MySQL8.0では、新たな認証プラグイン「caching_sha2_password」が導入されてる。
##### `WordPress データベースエラー: [Unknown database 'wordpress']`

# その他
- STATSU が UP か 確認。
  - `docker-compose ps [cmd]`
  - `docker stop [name]`
  - `docker rm [name]`
  - `docker images -a`
  - `docker rmi [mysql IMAGE ID]`
  - `docker stop wp mysql && docker rm wp mysql`

# Tips
##### Mysqlログイン(image)
```sh
docker exec -it [コンテナID] mysql -u root -p
```
##### WPサーバーログイン(image)
(基本ローカルに Mount するので、使わない.)
```sh
docker exec -it [container-name] /bin/bash
```

## 📖 [Docker-compose.yml リファレンス](http://docs.docker.jp/compose/compose-file.html#container-name)

- [単一ホスト上で複数の環境を分離する](http://docs.docker.jp/compose/overview.html#multiple-isolated-environments-on-a-single-host)
- [コンテナ作成時にボリューム・データの保持](http://docs.docker.jp/compose/overview.html#preserve-volume-data-when-containers-are-created)
  > 以前に、実行済みのコンテナが見つかれば、古いコンテナから新しいコンテナにボリュームを **コピー**~~ します。この処理により、ボリューム内で作成したデータを失わないように守ります。

# Docker install

- [docker-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- [docker-win](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

# DataBase: DATA

`./.data/db`：自動的に、作成。  
