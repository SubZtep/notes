Build only one service from compose

```sh
docker compose up -d --no-deps --build web 
```

Start database only:

```sh
docker compose up -d db
```
