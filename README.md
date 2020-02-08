```sh
# Up
docker-compose -f [yml-file-name] up -d

# Login: (基本 mount するので、使わない.)
docker exec -it [container-name] /bin/bash
# Login: to Mysql image
docker exec -it コンテナID mysql -u root -p
```

## 📖 [Docker-compose.yml リファレンス](http://docs.docker.jp/compose/compose-file.html#container-name)

- [単一ホスト上で複数の環境を分離する](http://docs.docker.jp/compose/overview.html#multiple-isolated-environments-on-a-single-host)
- [コンテナ作成時にボリューム・データの保持](http://docs.docker.jp/compose/overview.html#preserve-volume-data-when-containers-are-created)
  > 以前に実行済みのコンテナが見つかれば、古いコンテナから新しいコンテナにボリュームをコピーします。この処理により、ボリューム内で作成したデータを失わないように守ります。

# Docker install

- [docker-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- [docker-win](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

# DB data

docker-compose.yml があるプロジェクトのディレクトリ内に  
`./.data/db` ディレクトリを自動的に作成します。  
wordpress がデータベースに対して更新したあらゆるデータは、  
このディレクトリで保持します。
