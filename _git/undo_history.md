---
title: Undoing History (git revert, git reset)
layout: article
permalink: /git/undoing_history
toc: true
---

## Revert vs Reset
`git revert` calculates what portions of files need to be changed in order to revert them to the previous version.

`git reset` wipes out changed files completely and restores the previous version.

## Undoing a pushed commit

```
git reset --hard HEAD~1
git push -f <remote> <branch>
```

## Undoing a rebase

Source [Undoing a git rebase](https://stackoverflow.com/questions/134882/undoing-a-git-rebase)

```
git reset --hard ORIG_HEAD
```

## Remove a file from a remote repo

Source: [StackOverflow](https://stackoverflow.com/questions/18357511/git-remove-committed-file-after-push)

Say you included a file in a pushed commit that you didn't intend to. Run the below command to remove that file from the commit. This is helpful if you accidently included a bunch of files unnecessary to a pull request you plan on merging.

```
git rm --cache /path/to/file
git commit -am "Remove file"
git push
```
