First, create a `.gitignore` file for your global rules. Eg: home directory:

```bash
touch ~/.gitignore
```

Add your rules, eg: `*.local.*`.

Finally, configure `git` to use it:

```bash
git config --global core.excludesfile ~/.gitignore
```