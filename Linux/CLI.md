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

Find directory by name

```sh
find /home/dcr -type d -name "my_dir_name"
```

Keep audio on to prevent static noise.

```sh
ffplay -nodisp -autoexit -loglevel quiet -f lavfi "anullsrc=r=44100:cl=stereo"
```

Open test database

```sh
rainfrog -u postgresql://testuser:testpass@localhost:5433/test
```

Check for dependency updates:

```sh
bun outdated -r
```

Update depdendencies for all packages:

```sh
bunx npm-check-updates -w -u
```

Print full output with errors into a file:

```sh
bun dev > output.txt 2>&1
```

Generate Better-Auth secret:

```sh
openssl rand -base64 32
```

Find unused dependencies:

```sh
bunx knip
```

Update all packages in all monorepo workspaces:

```sh
bunx npm-check-updates -w -u
```

Debug pressed key

```sh
kitten show-key -m kitty
```
