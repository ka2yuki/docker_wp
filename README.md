[進捗：Private](https://github.com/users/ka2yuki/projects/10)  
- [x] コンテナ内の/var/www/html/wp-content/theme/:作業ディレクトリ を同期させたい

# 📦アプリInstall DockerDesktop
- Windows: [Docker Desktop](https://docs.docker.com/desktop/setup/install/windows-install/)

## 開発環境をインストール
1. 🐋DockerDessktop🐋 の 検索窓に「wordpress」と入力
2. 「Pull」ボタンを押す
3. Imagesタブ > 「➡️」Runボタンを押す

Docker Official Image: [Wordpress](https://hub.docker.com/_/wordpress) | hub.docker.com

# 実行
```sh
docker-compose -f docker-compose.yml up --watch # also use -w
# check 
docker ps
```
[http://localhost:8080](http://localhost:8080)

# Restart
```sh
# Containers
docker container stop wp mysql && docker container rm wp mysql
# Volumes
docker volume rm [hoge hoge] # nead to specify id
```


## :pencil: memo
## files

| file/dir name | meaning |
| :- | :- |
|`.env`|passwordなど|

### Docker Desktopのめも

-  Tab: Containers
   -  
   -  Exec: コンテナ内の　CLI
   -  Files: コンテナ内の ファイルを表しているみたい
   -  Stats: ながめる

### wordpress CLI
[WP-CLI Commands](https://developer.wordpress.org/cli/commands/)
| Command | 概要 |
| :--- | :--- |
| [wp admin](https://developer.wordpress.org/cli/commands/admin/) | ブラウザで `/wp-admin/`を開く |
| wp cache | WPオブジェクトのCacheObjectの 操作 |
| wp cap | ユーザー権限の操作 |
| wp cli | ... |
| wp comment | |
| wp config |  |
| wp core |  |
| wp db |  |
| wp dist-archive |  |
| wp embed | |
| wp eval | |
| wp eval-file | |
| wp export | |
| wp find | |
| wp help | |
| wp i18n | |
| wp import | |
| wp language | |
| wp maintenance-mode | |
| wp media | |
| wp menu | |
| wp network | |
| wp option | |
| wp package | |
| wp plugin ||
| wp post ||
| wp post-type||
| wp profile ||
| wp rewrite ||
| wp role ||
| wp scaffold ||
| wp search-replace ||
| wp server ||
| wp shell ||
| wp sidebar ||
| wp site ||
| wp super-admin ||
| wp taxonomy ||
| wp term ||
| wp theme ||
| wp transient ||
| wp user ||
| wp widget ||

more: [WP-CLI Commands](https://developer.wordpress.org/cli/commands/)

---
[History](https://github.com/ka2yuki/docker_wp/commits/master/)
