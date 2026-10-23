Ignore my current changes and makes the branch looks like in remote

```bash
git reset --hard
```

Get Git hash

```sh
git rev-parse --short HEAD
```

Redo last push

```sh
git push -f origin HEAD^:main
```

Undo last local commit

```sh
git reset --soft HEAD~
```

Undo last Git commit

```sh
git reset --hard HEAD~1
```

Delete file from git

```sh
git rm --cached apps/cli/.env
```

List remotes

```sh
git remote -v
```
