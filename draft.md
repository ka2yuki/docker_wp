> [!WARNING]
> このファイルはメモです。

# Goal
- 作業ディレクトリ上に自動マッピングできて使用できること
  - issue: Docker環境までリポジトリに含まれてしまう
- 

# TODO
- What [Docker Engine](https://docs.docker.com/engine/install) install

# check
```sh
docker-compose -f docker-compose.yml up -d 
# check 
docker ps
```
[ブラウザ確認する↗️](http://localhost:8080)：
- Sample: 
  - [docker-compose.yml](https://docs.docker.jp/compose/wordpress.html)
  - [env_file](https://docs.docker.jp/compose/compose-file.html#env-file)

# :pencil:Tips 
良く使用したCommands
```sh
# Status? Up or Down
docker-compose ps [cmd]
docker stop [name]
docker rm [name]
docker images -a
docker rmi [mysql IMAGE ID]
docker stop wp mysql 
docker rm wp mysql
```

Mysqlログイン(image)
```sh
docker exec -it [コンテナID] mysql -u root -p
```

WP local imageログイン  
(基本ローカルに 紐づけ同期 する想定なので使わない.)
```sh
docker exec -it [container-name] /bin/bash
```

## 📖 [Docker-compose.yml リファレンス](http://docs.docker.jp/compose/compose-file.html#container-name)
### 環境を分ける
- [単一ホスト上で複数の環境を分離する](http://docs.docker.jp/compose/overview.html#multiple-isolated-environments-on-a-single-host)
### 保存データ: ボリューム・データ
- [コンテナ作成時にボリューム・データの保持](http://docs.docker.jp/compose/overview.html#preserve-volume-data-when-containers-are-created)
  > 以前に、実行済みのコンテナが見つかれば、古いコンテナから新しいコンテナにボリュームを **コピー**~~ します。この処理により、ボリューム内で作成したデータを失わないように守ります。

 DataBase: DATA  
`./.data/db`：自動的に、作成。 


# Try & Errors
[errors](errors.md)
## install docker-comppose standalone by CMD  

> [!WARNING]
> This install scenario is not recommended and is only supported for backward compatibility purposes. [link](https://docs.docker.com/compose/install/#scenario-three-install-the-docker-compose-standalone)
```sh
sudo curl -SL https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
# https://github.com/docker/compose/releases
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```