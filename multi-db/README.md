# multi-db

## Get started

```bash
$ docker compose up -d
```

## Manual

### Password

環境変数の`MYSQL_RANDOM_ROOT_PASSWORD=yes`により、MySQL のログにパスワードが記載されています。
初回起動時に以下のコマンドで確認することができます。

```
$ docker compose logs | grep -i generate

multi-db-db1-1  | xxxx-xx-xx xx:xx:xx+xx:xx [Note] [Entrypoint]: GENERATED ROOT PASSWORD: THISISPASSWORD
multi-db-db2-1  | xxxx-xx-xx xx:xx:xx+xx:xx [Note] [Entrypoint]: GENERATED ROOT PASSWORD: THISISPASSWORD
```

※ MySQL のバージョンが想定よりも古い場合`grep -i password`でヒットする場合があります。

### Adding or changing databases

[compose.yml](../../../blob/main/multi-db/compose.yml)の MySQL コンテナに変更を加えた場合、合わせて[config/phpmyadmin/config.user.inc.php](../../../blob/main/multi-db/config/phpmyadmin/config.user.inc.php)も修正します。

## Images

- [mysql](https://hub.docker.com/_/mysql)
- [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)
