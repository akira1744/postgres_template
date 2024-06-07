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


```sql
CREATE DATABASE sampledb;
```

## サンプルデータ

```sql
-- もし存在したら DROP TABLE
DROP TABLE IF EXISTS sampletable;

-- CREATE TABEL
CREATE TABLE sampletable
(shohin_id     CHAR(4) NOT NULL,
 shohin_mei    VARCHAR(100) NOT NULL,
 shohin_bunrui VARCHAR(32) NOT NULL,
 hanbai_tanka  INTEGER ,
 shiire_tanka  INTEGER ,
 torokubi      DATE ,
     PRIMARY KEY (shohin_id));

--SQL Server PostgreSQL
-- DML：データ登録
BEGIN TRANSACTION;
INSERT INTO sampletable VALUES ('0001', 'Tシャツ', '衣服', 1000, 500, '2009-09-20');
INSERT INTO sampletable VALUES ('0002', '穴あけパンチ', '事務用品', 500, 320, '2009-09-11');
INSERT INTO sampletable VALUES ('0003', 'カッターシャツ', '衣服', 4000, 2800, NULL);
INSERT INTO sampletable VALUES ('0004', '包丁', 'キッチン用品', 3000, 2800, '2009-09-20');
INSERT INTO sampletable VALUES ('0005', '圧力鍋', 'キッチン用品', 6800, 5000, '2009-01-15');
INSERT INTO sampletable VALUES ('0006', 'フォーク', 'キッチン用品', 500, NULL, '2009-09-20');
INSERT INTO sampletable VALUES ('0007', 'おろしがね', 'キッチン用品', 880, 790, '2008-04-28');
INSERT INTO sampletable VALUES ('0008', 'ボールペン', '事務用品', 100, NULL, '2009-11-11');
COMMIT;

-- 確認
SELECT * FROM sampletable LIMIT 5;
```

## docker-comopse.ymlを作成した時に参考にしたlink

https://qiita.com/satodoc/items/188a387f7439e4ec394f
