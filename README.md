## 本リポジトリの環境

- Ruby(3.2.2)
- Ruby on rails(7.0.6)
- PostgreSQL(12)

## 環境構築手順

### 本リポジトリをクローンする

```
git clone https://github.com/otaki0413/rails-docker.git
```

### データベース 作成（※初回のみ）

```
docker-compose run --rm web rails:db-create
```

### マイグレーション実行（※初回と随時）

- web(rails)用のコンテナが立ち上がってることを確認して、以下コマンド実行

```
docker-compose exec web rails db:migrate
```

### コンテナ作成 & コンテナ起動

```
docker-compose up -d
```

rails コンテナと DB コンテナが起動するので、`http://localhost:3000`にアクセスできれば OK

### コンテナ停止・コンテナ削除

```
# コンテナの停止
docker-compose stop

# コンテナの削除
docker-compose down
```
