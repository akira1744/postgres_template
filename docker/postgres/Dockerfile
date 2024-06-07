FROM postgres:16.3


# /home/postgres/workspaceディレクトリの作成
RUN mkdir -p /home/postgres/workspace

# /home/postgres/workspaceの権限をpostgres:postgresに変更
RUN chown -R postgres:postgres /home/postgres/workspace

# ユーザーをpostgresに切り替え
USER postgres

# 作業ディレクトリの設定
WORKDIR /home/postgres/workspace