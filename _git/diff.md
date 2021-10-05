---
title: Git Diff
layout: article
permalink: /git/diff
toc: true
---

Compare two files and highlight differences.

## Compare files between two branches.

```
$ git diff <branch> <other branch> -- <filename>
```

## Squashing commits

1. Determine how many commits to squash. Run this command to generate a pretty graph of your commit history:

```
git log --graph --decorate --pretty=oneline --abbrev-commit
```

You will want to find the SHA for the commit before the one you want to squash to. This will usually be the most recent merge/branch, or HEAD.

2. Run an interactive rebase command specifying the SHA of the commit identified in the above step.

```
git rebase -i <SHA>
```

Running the command will open your default text editor listing the commit hashes and messages for the commits you will be squashing. Review to ensure you will squash all the commits that you intend to.

3. Change the word pick to squash for all the commits that need to get squashed. The squash command informs git to combine that commit with the one above. The first commit should retain the pick command. Save and close your editor. The editor will open again showing all the commit messages.

4. Input the message for the squashed commit.
