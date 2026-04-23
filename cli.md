---
title: CLI Snippets
tags: [cli, git, docker]
aliases: [bash-tips]
created: 2026-04-23
source: personal
---

Bash commands

## GIT

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

## Docker

Build only one service from compose

```sh
docker compose up -d --no-deps --build web 
```

## LLM

Basic chat


```sh
curl https://hazai.kaja.io/api/generate -d '{
  "model": "smollm2",
  "prompt":"Why is the sky blue?"
}'
```

POST message

```sh
curl -k -N -X POST https://static.249.244.62.46.clients.your-server.de/api/chat/stream -H "Content-Type: application/json" -d '{"message":"continue"}'
```

# Misc.

Keep audio on to prevent static noise.

```sh
ffplay -nodisp -autoexit -loglevel quiet -f lavfi "anullsrc=r=44100:cl=stereo"
```

