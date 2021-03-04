# Git

## Show which files have changed between two branches

```
git diff --name-status featurebranch..main
```

## Rename master branch to main

Rename local branch:

```
git branch -m master main
```

Push newly created branch and make it track the remote:

```
git push -u origin main
```

Delete old remote branch:

```
git push origin --delete master
```

h/t [How to rename the "master" branch to "main" in Git](https://www.git-tower.com/learn/git/faq/git-rename-master-to-main/)
