Hide your local changes from Git:
```bash
git update-index --skip-worktree path/to/config.file
```

What it does:
- ✅ Keeps your local modifications.
- ✅ `git status` won't show the file.
- ✅ `git add .` won't stage it.
- ✅ You won't accidentally commit it.

To make Git track the file again:
```bash
git update-index --no-skip-worktree path/to/config.file
```

To see all files marked this way:
```bash
git ls-files -v | grep '^S'
```

**Good for:** Local config files (API keys, ports, personal settings) that are tracked by Git but you want to customise on your own machine without committing those changes.