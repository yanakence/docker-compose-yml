# redmine

## Get started

初回のみ MySQL の立ち上がりが遅いため、個別に起動します。

```bash
$ docker compose up -d mysql
$ docker compose up -d redmine
```

次回以降は同時起動が可能です。

```bash
$ docker compose up -d
```

## Images

- [redmine](https://hub.docker.com/_/redmine)
- [mysql](https://hub.docker.com/_/mysql)
