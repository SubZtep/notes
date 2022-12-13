Get Git hash

```sh
git rev-parse --short HEAD
```

Undo last Git commit

```sh
git reset --hard HEAD~1
```

Find and delete node_module folders in monorepo

```sh
find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
```

Current timestamp in nanoseconds

```sh
date +%s%N
```

Directory sizes in current folder

```sh
du -sh *
```

