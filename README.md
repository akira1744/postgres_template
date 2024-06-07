# docker_postgres_template

## .envの設定変更

- postgres_templateの部分を変更。
- フォルダ名を一致させるのがわかりやすい。

### 例

```
CONTAINER_NAME=postgres_projectname
HOST_NAME=postgres_projectname
NETWORK_NAME=postgres_projectname
DB_VOLUME_NAME=postgres_projectname_pgdata
WORKSPACE_VOLUME_NAME=postgres_projectname_workspace
HOST_PORT=15432 
USER_NAME=postgres
USER_PASSWORD=postgres
```

## containerを起動

```bash
docker comopse up -d --build
```

## データベースの作成(containerのbashに入ってpsqlに接続する場合)

```bash
docker compose exec -it postgres bash
psql
```


```bash

```


## docker-comopse.ymlを作成した時に参考にしたlink

https://qiita.com/satodoc/items/188a387f7439e4ec394f
