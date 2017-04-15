# Git basics

Git is a version control system (VCS) for tracking changes in computer files and coordinating work on those files among multiple people. It is primarily used for software development, but it can be used to keep track of changes in any files. (Extracted from [Wikipedia](https://en.wikipedia.org/wiki/Git))

It let us save a snapshot of our complete project at any time we want.

_Version control_ is independent of the kind of project / technology / framework we're working with.

![VCS](https://www.git-tower.com/learn/content/01-git/01-ebook/en/01-command-line/02-basics/01-what-is-version-control/what-is-vcs.png)

With a VCS, everybody on the team is able to **work** absolutely **freely** on **any file at any time**. Allows to **restore older versions** of a file. We can see what exactly was changed in the file's content; and can act as a **backup**.

A **repository** is a kind of database where our VCS stores all the versions and metadata that accumulate in the course of our project.

**commit** is a wrapper for a specific set of changes. Every set of changes implicitly creates a new, different version of your project. Therefore, every commit also marks a specific version.

## Init a Repository

To inicialize a repository we have to use the command `git init`.

This command will create a hidden `.git` sub-folder in the project folder.

At this moment, we can use the _git commands_.

## Track first changes

First time our files are *untracked*.

To start tracking our files we have to `commit` them.

For example, if we have an `index.html` created we can start tracking it by doing in the root folder:

```
git init
git add index.html
git commit -m "first commit"
```

### git add

We use `git add` before committing a file/folder. This will add the files and folders into the **staging area**.

`git add --all` will add the folder with all files inside.

### git commit -m

We use `git commit -m` to commit our files and folders. `-m` means message, and the message has to be written between `""`.

### git log

Think of `git log` as a journal that remembers all the changes we've committed so far, in the order we committed them.

```
git log
commit 2c1d85d41ab4477d8fec775f55fad6de6ec4e5d1
Author: Sergio MT <sergio.mt88@gmail.com>
Date:   Tue Apr 11 09:26:47 2017 +0200

    git_basics.md created
```

`git log --stat` show changes on a simple form.

### git status

We use `git status` to verify the condition and changes of the repository. It allow us to get a list of all the changes we performed since the last commit.

```
git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   git_basics.md

no changes added to commit (use "git add" and/or "git commit -a")
```

### git config

`git config` will show us commands. And if we write `git config -l` we can add our personal information.

```
$ git config --global user.name "John Doe"
$ git config --global user.email "john@doe.org"
$ git config --global color.ui auto
```

### git push

We use `git push` to save our data in a remote _repository_.

```
git push origin master
```

## Updating a repository

```
git add fileOrFolder
git commit -m "Update"
git push
```

## Starting with an existing project

```
$ cd your/development/folder/
$ git clone https://github.com/misan7/pasapalabra_8bits.git
```
