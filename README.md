# railsアプリ作成のためのbasicな雛形です。
DBにはpostgreSQLを使用しています。
---

## 設定する必要がある事項
- rubyのバージョン Dockerfile内のイメージ:tagで記述
- railsのバージョン Gemfileの中に記述
- appのディレクトリ名 Dockerfile内の`ARG APP_NAME`で編集可能
  - entrypoint.shとdocker-compose.ymlでもプロジェクトのディレクトリ名をパスとして使用するため、依存関係にある。修正を忘れないようにすること。

### docker-compose upするたびに、ローカルのサーバーは起動するようになっている。


# コマンドととして実行するもの
1. railsプロジェクトの雛形作成
```
$ docker-compose run --rm rails new . --force --database=postgresql
```

2. 作成されたので必要になるgemをインストールするように
```
$ docker-compose build
```
?これってrunのコマンドで&& で繋げれば良くないか?

3. db.yamlを編集して、rails:db:createをする必要がありそう。

