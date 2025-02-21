# Git tutorial

This is a git tutorial, keep updating while using git...

## Git repository initialization

Go to your repository, open it in the terminal, and type command line:

```bash
git init
```

## Back to last version

Check the history of update, find the commit-id:

```bash
git log  
```

Get back to the version you want:

```bash
git reset --hard commit_id
```

Push the version to origin:

```bash
git push origin
```

Quik command to get back to last version:

```bash
git reset --hard HEAD^
```

PS: **HEAD** points to the current source version, **HEAD^** points to last version, **HEAD^^** points to the version before last one.

## Delete git repository

当不需要git跟踪时,找出隐藏的.git文件删除即可

```bash
ls -a
```

```bash
rm -rf .git
```
