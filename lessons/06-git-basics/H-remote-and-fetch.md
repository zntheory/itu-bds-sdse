---
description: "Basics of Git."
title: "Remote and Fetch"
keywords:
  - Software engineering
  - Git
---

## Remote git

While you can totally use a git repository for your own personal use, git is really built for collaboration with others.


</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## So here is a shocker

A remote git repository does not actually have to ***be*** remote. A bit misleading, yes. A remote git repository is ***just a copy*** of the local repository ***somewhere else***.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Exercise: Create a new repo `remote-git` and initialize it

> * Create a new directory `remote-git` and navigate into it. **Do not do this inside an existing git repository.**
> * Initialize the repository.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Solution: Create a new repo `remote-git` and initialize it

```bash
mkdir remote-git
cd remote-git
git init
```

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## This is distributed version control

So, a remote is just another git repository that is of the same project and has changes we may need or may need to share our changes with.

To manage remotes, we have the `git remote` command. Read more with `man git-remote`.

To add a remote, we use the `git remote add <name> <uri>` command.

The URI can be a path to a directory or a URL, like SSH or HTTPS.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Exercise: Add `learn-git` as a remote to the `remote-git` repository

> * Add a remote called `learn-git` to the `remote-git` repository.
> * The URI for the remote is `<path-to-your-learn-git-directory>`.
> * Use `origin` as the name of the remote. This is good practice for the *authority* repo.
> * Verify that the remote has been added.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Solution: Add `learn-git` as a remote to the `remote-git` repository

> Here `<path-to-your-learn-git-directory>` is the path to the `learn-git` directory on your system. We use `../learn-git` as path in this example.

```bash
git remote add origin ../learn-git
```

We can check the remotes by using the `git remote -v` command.

```bash
git remote -v
```

</br>

**Output:**

```plaintext
origin  ../learn-git (fetch)
origin  ../learn-git (push)
```

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Good practices with remotes

</br>

### Remote is a project repository

There is a *single source of truth*, which is the remote project repository. This should be named `origin`.

</br>

### Remote is a fork

In this case the fork remote repository should be named `origin` and the project repository should be named `upstream`.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

Now we will need to merge our changes from `learn-git` into `remote-git`.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Fetch

All state can be fetched from a remote repository. We use the `git fetch` command for this.

This operation does not affect currently checked out branches—just the history about them that is in `origin/*`.

</br>
</br>

(you should do that now)

</br>
</br>

```bash
git fetch
```

</br>

The output will look something like this. We got all the information about branches from `learn-git`.

**Output:**

```plaintext
remote: Enumerating objects: 28, done.
remote: Counting objects: 100% (28/28), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 28 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (28/28), 2.12 KiB | 57.00 KiB/s, done.
From ../learn-git
 * [new branch]      feature             -> origin/feature
 * [new branch]      feature-delete-test -> origin/feature-delete-test
 * [new branch]      feature-rebase-main -> origin/feature-rebase-main
 * [new branch]      feature-two         -> origin/feature-two
 * [new branch]      main                -> origin/main
```

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

So now we are up to date, right?

```bash
git log
```

</br>
</br>

(try it now)

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

> We can use `git log origin/main` to see the log of the `main` branch in the remote repository.

> We can also use `git branch -a` to see all the branches, including the remote branches.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

> **Question:** Can you think of a way to get the changes from the remote?

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

We can do a merge.

```bash
git merge origin/main
```

</br>
</br>

But there is also `git pull`, which we will cover next.

</br>
</br>
