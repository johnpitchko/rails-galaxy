---
title: Git Branch
layout: article
permalink: /git/branch
toc: true
---

## Delete branches

To delete a local branch:

```
git branch -d <branch name>
```

To delete a remote branch:

```
git push -d <remote_name> <branch_name>
```

## Rename a branch
Source: [StackOverflow](https://stackoverflow.com/questions/30590083/how-do-i-rename-both-a-git-local-and-remote-branch-name)

### Rename your local branch:

1. If you are on the branch you want to rename:

```
git branch -m new-name
```

If you are on a different branch:

```
git branch -m old-name new-name
```

2. Delete the old-name remote branch and push the new-name local branch:

```
git push origin :old-name new-name
```

3. Reset the upstream branch for the new-name local branch: Switch to the branch and then:

```
git push origin -u new-name
```
