---
description: "Basics of Git."
title: "Basic commands and commit"
keywords:
  - Software engineering
  - Git
---

## Basic commands

These are basically the commands you will use to interact with git the majority of the time. In general git is easy, but it is the more advanced commands that can land you in trouble if not careful. Again, read the `man` for each command when in doubt.

</br>

- `git add <path-to-file | pattern>` adds zero or more files to the staging area.
- `git commit -m "<message>"` commits what changes are in the staging area.
- `git status` shows the status of the working directory and staging area, which includes overview of tracked, staged and untracked files.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Exercise: Tracing state of changes

> Trace the state of changes in git from untracked to tracked.

</br>

**Command overview**

```bash
git add <path-to-file | pattern>
git commit -m "<message>"
git status
```

</br>

> * In the git repo `my-git-repo`, create a new file `README.md`.
> * Check the status of git to see that it is untracked.
> * Add `README.md` to the staging area.
> * Check the status of git to see that it is now tracked in the staging area.
> * Commit with a message.
> * Check the status of git to see there are no changes waiting or untracked.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Changes in a repository

When working with a repo, we will eventually need to look into the history of changes. Anything committed and shared with others is in the history, so beware of committing sensitive information.

As mentioned earlier, the act of "blaming" is to find out who made a change. This is done with the `git blame` command.

Another command to traverse the history is `git log`. This command shows the history of changes in the repo. It can be styled in several ways, but the default is a simple list of commits.

</br>

- `git log` shows the history of changes.
- `git blame <file>` shows who made the changes to a file.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

Try look up the `man` page for `git log` and search for the `--graph` and `--decorate` options.

</br>

> **Hint:** `man git-log`, and searching is done with `/` with `n` and `N` to go to the next and previous search result.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Exercise: Display the history

> Display the history of the git repo with the `--graph` and `--decorate` option.

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

### Solution: Display the history

```bash
git log --graph --decorate
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

## Internal representations

### SHAs

Short for "Secure Hash Algorithm", SHA is a cryptographic hash function that produces a fixed-size hash value. In git, the SHA is used to identify objects, such as commits, trees, and blobs.

</br>

Git commits are all identified by a SHA, which is a 40-character hexadecimal string comprised of `0-9a-f` characters. The SHA is unique to the commit and is used to reference the commit in the history.

</br>

You can get away with specifying only the first 7 characters of a SHA when referencing a commit. This is because the first 7 characters are usually unique enough to identify the commit.

</br>

Main way to get SHAs is with `git log`.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Exercise: Identify a commit

> Find the commit SHA of the first commit and copy it.

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

### Solution: Identify a commit

```bash
git log
```

**Output:**

```plaintext
commit 486f1898821ee74a59ca154e0785f0f589ccb6e2 (HEAD -> main)
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Tue Sep 17 22:11:03 2024 +0200

    batman
```

```plaintext
commit 486f1898821ee74a59ca154e0785f0f589ccb6e2
---------^ this is the SHA
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

### Question

Why is your commit SHA different than mine?

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
</br>
</br>
</br>
</br>
</br>
