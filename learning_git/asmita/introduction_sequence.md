# Introduction Sequence

## LEVEL 1: INTRODUCTION TO GIT COMMITS

The first level teaches about the `git commit` command. Commits are snapshots of the changes in your project, allowing you to track progress and revert to previous states if needed.\
To progress from commit C1 to C2, use `git commit`. Another `git commit` takes you to C3, which is our goal.\


Commands:

```sh
    git commit
    git commit
```

## LEVEL 2: BRANCHING IN GIT

Branching in Git allows developers to create separate lines of development to work on different features or fixes without affecting the main codebase until they're ready to merge changes back.\
**Branch early, and branch often**\
The commands for this level are:\


```sh
    git checkout -b bugFix
```

This command creates a new branch named ‘bugFix’ and switched to it.

## LEVEL 3: MERGING IN GIT

The command is\
'git merge branchName'\
The branchName here is bugFix\
The command to checkout and merge is\
'git checkout bugFix;git merge main'

Stepwise commands are

```sh
    git checkout -b bugFix
    git commit
    git checkout main
    git commit
    git merge bugFix
```

## LEVEL 4 : REBASE INTRODUCTION

The second way of combining work between branches is _rebasing._ Rebasing essentially takes a set of commits, "copies" them, and plops them down somewhere else.\
To complete this level, do the following\
\- Checkout a new branch named `bugFix` - Commit once - Go back to main and commit again - Check out bugFix again and rebase onto main

The commands are\


```sh
    git checkout -b bugFix
    git commit
    git checkout main
    git commit
    git checkout bugFix
    git rebase main
```
