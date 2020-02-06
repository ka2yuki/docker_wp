docker-compose -f [yml-file-name] up -d

# Docker install

- [docker-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
- [docker-win](https://hub.docker.com/editions/community/docker-ce-desktop-windows)

# DB data

`./.data/db`
docker-compose.yml があるプロジェクトのディレクトリ内に  
`./.data/db` ディレクトリを自動的に作成します。  
wordpress がデータベースに対して更新したあらゆるデータは、  
このディレクトリで保持します。
