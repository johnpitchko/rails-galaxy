---
title: Git Rebase
layout: article
permalink: /git/rebase
toc: true
---

## Rebase vs Merge

* Both integrate changes from one branch to another.
* Merging is non-destructive; existing branches are unchanged.
* Consequences for the future - impacts future commits because of extraneous merge commit - can be a challenge if there is lots of activity in master; history can look goofy
* Rebase moves entire feature branch to tip of master, creating a cleaner project history.
* Golden rule of rebase: DO NOT USE ON PUBLIC BRANCHES!!


## Resolving merge conflicts
Source: [Resolving conflicts during a Git rebase](https://codeinthehole.com/guides/resolving-conflicts-during-a-git-rebase/)

If you know that either the target branch or your working branch contains all the valid code, you can choose to automatically accept the changes from those branches. This is useful if you are doing a rebase after many commits occurred on the target branch required requiring a large number of merge conflicts that would otherwise be manually resolved.

To accept the changes from the target branch, use:

```
git checkout --ours -- $FILEPATH
```

To accept the changes made on your working branch, use:
```
git checkout --theirs -- $FILEPATH
```

Even more sweepingly, you can auto-resolve conflicts using a specified strategy when doing the rebase. Eg:

```
git rebase -Xtheirs origin/master
```
