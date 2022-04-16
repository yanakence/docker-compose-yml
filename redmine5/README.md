# redmine5

## Get started

同時に立ち上げると MySQL の立ち上がりが遅いため、**初回のみ Redmine がコネクションエラー**となります。

```
$ docker compose up -d mysql
$ docker compose up -d redmine
```

次回以降は同時起動が可能です。

```
$ docker compose up -d
```

## Images

- [redmine](https://hub.docker.com/_/redmine)
- [mysql](https://hub.docker.com/_/mysql)
