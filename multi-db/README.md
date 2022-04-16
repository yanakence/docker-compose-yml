# multi-db

## Get started

```bash
$ docker compose up -d
```

## Manual

### Password

コンテナの環境変数に`MYSQL_RANDOM_ROOT_PASSWORD=yes`を使用しているため、初めてコンテナを起動したときに root ユーザーのパスワードがランダムな文字列で生成されます。
そのパスワードはコンテナを初めて起動したときのログに出力されているため、以下のような方法でパスワードを確認することができます。

```bash
$ docker compose logs | grep -i generate

multi-db-db1-1  | xxxx-xx-xx xx:xx:xx+xx:xx [Note] [Entrypoint]: GENERATED ROOT PASSWORD: THISISPASSWORD
multi-db-db2-1  | xxxx-xx-xx xx:xx:xx+xx:xx [Note] [Entrypoint]: GENERATED ROOT PASSWORD: THISISPASSWORD
```

※ MySQL のバージョンが古い場合`grep -i generate`ではなく `grep -i password`でヒットする場合があります。

### Adding or changing databases

[docker-compose.yml](./blob/main/multi-db/docker-compose.yml)の MySQL コンテナを編集した場合、合わせて[config/phpmyadmin/config.user.inc.php](./blob/main/multi-db/config/phpmyadmin/config.user.inc.php)も修正しなければ phpMyAdmin が正常に動作しない場合があります。

## Images

- [mysql](https://hub.docker.com/_/mysql)
- [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)
