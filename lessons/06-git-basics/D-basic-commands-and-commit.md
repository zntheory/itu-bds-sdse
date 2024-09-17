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

### Here is another question

This is a bit harder.

Can you find your commit's SHA within the `.git` directory?

</br>

> **Hint:** You will need that SHA you copied earlier.

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

### Observation

All commits exist in the `.git/objects` directory with the first 2 characters of the SHA as the directory and the rest (38) as the file name.

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

### Remember

Everything in git is stored as a file in the `.git` directory.

What is in the file for our SHA?

</br>

```bash
cat .git/objects/48/6f1898821ee74a59ca154e0785f0f589ccb6e2

xK ]s71|
Z&+:!RxW2q:AdȠBe]
lVO*{.su48we9c_9 %
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

### Exercise: Reading the commit object

> Can you get `git cat-file -p <SHA>` to output the content of `README.md`?

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

### Solution: Reading the commit object

```bash
git cat-file -p 486f1898821ee74a59ca154e0785f0f589ccb6e2

tree f93e3a1a1525fb5b91020da86e44810c87a2d7bc
author Lasse Lund Sten Jensen <lajl@itu.dk> 1726603863 +0200
committer Lasse Lund Sten Jensen <lajl@itu.dk> 1726603863 +0200

batman
```

Not quite what we wanted, but we can look at the other SHA for tree.

```bash
git cat-file -p f93e3a1a1525fb5b91020da86e44810c87a2d7bc

100644 blob e69de29bb2d1d6434b8b29ae775ad8c2e48c5391    README.md
```

Still not the content of `README.md`, but we can see the SHA of the blob. Let us look at that.

```bash
git cat-file -p e69de29bb2d1d6434b8b29ae775ad8c2e48c5391

We are learning git!
```

So there is our content of `README.md`—assuming we set it to "We are learning git!".

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

### Observation

Tree is a directory.

Blob is a file.

> **Important:** Git does _not_ store diffs, but the entirety of the change.

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

### Exercise: A second commit

Make a second commit with a new file and content.

> * Create a new file, we call it `document.md`.
> * Add some content to the file. We will use "This is a document".
> * Add the file to the staging area.
> * Commit the file with a message.

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

### Solution: A second commit

Create the file `document.md` and add the content `This is a document`.

```bash
git add document.md
git commit -m "document"

[main ef831b9] document
 1 file changed, 1 insertion(+)
 create mode 100644 document.md
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

### Exercise: Reading the document commit object

> Can you get `git cat-file -p <SHA>` to output the content of `document.md`?

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

### Solution: Reading the document commit object

```bash
git cat-file -p ef831b9

tree 7de536eec1170876ccb1238b78a0ee4d7dbab94a
parent 486f1898821ee74a59ca154e0785f0f589ccb6e2
author Lasse Lund Sten Jensen <lajl@itu.dk> 1726606575 +0200
committer Lasse Lund Sten Jensen <lajl@itu.dk> 1726606575 +0200

document
```

Notice we have a `parent` SHA.

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

### Observation

If we do the same for the tree, we can see that git stores the entirety of the repository and not just the one change.

```bash
git cat-file -p 7de536eec1170876ccb1238b78a0ee4d7dbab94a

100644 blob e69de29bb2d1d6434b8b29ae775ad8c2e48c5391    README.md
100644 blob 9de2f7e0f0b41ff960078f4879c6e9a67ee562f4    document.md
```

</br>

In other words, git stores the entire state of the repository at each commit, and we only need a single commit SHA to recover the entire state of the repository at that commit.

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

Git commits are organized as an acyclic graph that happens to be linear. Time is the order commits follow.

</br>
</br>
