```sh
# Up
docker-compose -f [yml-file-name] up -d
```
[ブラウザ確認する↗️](http://localhost:8080)
# Error
##### `Error establishing a database connection`
- Docker リスタート。✅

# その他
- STATSU が UP か 確認。
- docker containers stop rm など

```sh
# Login: to Mysql image
docker exec -it コンテナID mysql -u root -p

# Login: WP Server
# (基本ローカルに Mount するので、使わない.)
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
