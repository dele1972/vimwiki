# Docker - clean up

## First Try

```bash
docker-compose build --no-cache
```

no new dump required

## last one - rebuild very new and delete all old ones

### 1 - show some disc usages of current docker

```bash
docker system df
```

### 2 - reduce files to currently used

```bash
docker system prune
```

### 3 - rebuild

```bash
docker-compose build --no-cache --pull
```

