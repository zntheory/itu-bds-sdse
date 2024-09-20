---
description: "Basics of Git."
title: "Branches"
keywords:
  - Software engineering
  - Git
---

## Branches

Truth is that you are not likely going to be working on the `main` branch all the time. Especially if working in a team.

Normally you will branch out from the main line of development to work on a new feature or fix a bug. When you are done, you merge the branch back into the main line.

</br>

When you see `main` in the terminal, this _also_ refers to a branch. The main branch.

</br>
</br>

> We will be talking more about branching strategies later, which builds on the foundation covered in this section.
> 
> For now, we focus on the git commands necessary to work with branches.

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

Branches are very _cheap_ to create. A branch is essentially a **pointer**.

There are some performance considerations if you have a repository with a lot of branches, but generally this is only going to be a problem when the volume grows large or the repository itself takes up a lot of storage space.

</br>

> **Rule of thumb:** When you are done with a branch, delete it.

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

### Exercise: Create a new repository and initial commit

> * Create a new repository `learn-git`.
> * Create a new file `README.md`.
> * Add a line of text to it that says `A`.
> * Commit the file with the message also saying `A`.

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

### Solution: Create a new repository and initial commit

```plaintext
git log

commit 0ad5c13d0496e517e66aad45ccf4cc75b09340df (HEAD -> main)
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Wed Sep 18 00:34:58 2024 +0200

    A
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

## Creating branches

Branching is easy and is done with the `branch` command.

```bash
git branch feature
```

This creates a new branch called `feature`.

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

### What happened?

- A new branch `feature` was created pointing to the **same commit** as `main`.
- We are still on `main`.

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

## Listing branches

We can see this by listing the branches. The command `git branch` displays all our local branches.

```bash
git branch
```

**Output:**

```plaintext
  feature
* main
```

The current working branch is marked with an asterisk `*`.

</br>
</br>

Furthermore, we can see more information when using `git log`.

```bash
git log
```

**Output:**

```plaintext
commit 0ad5c13d0496e517e66aad45ccf4cc75b09340df (HEAD -> main, feature)
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Wed Sep 18 00:34:58 2024 +0200

    A
```

Specifically, the `HEAD -> main, feature` part tells us that both `main` and `feature` are pointing to the same commit.

`HEAD` always points to the tip of the branch.

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

## Switching branches

To switch to the `feature` branch, we can use either the `checkout` or `switch` command.

```bash
git checkout feature
git switch feature
```

`checkout` is supposedly a more versatile command, but both commands can be used to switch branches. In this context they do the same.

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

### Exercise: Create a new branch and switch to it

> * Create a new branch called `feature`.
> * Switch to the `feature` branch.

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

### Solution: Create a new branch and switch to it

```plaintext
git branch feature
git switch feature # or git checkout feature
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

### Exercise: Create a document.md file with changes on the `feature` branch

> * Create a new file called `document.md`.
> * Add a line of text to the `document.md` file that says `B`.
> * Commit the file with the message also saying `B`.

> * Do it again, except replace `B` with `C` in the above.

</br>
</br>

When done use `git log` to see the history.

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

### Solution: Create a document.md file with changes on the `feature` branch

```bash
echo "B" >> document.md
git add document.md
git commit -m "B"

echo "C" >> document.md
git add document.md
git commit -m "C"
```

</br>

**Output:**

```plaintext
commit 787200cb8e96c3e830a3e5fbb0ec127278655325 (HEAD -> feature)
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Wed Sep 18 01:11:05 2024 +0200

    C

commit cae02f432e63ec51c87c2a1faf944b602189dc57
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Wed Sep 18 01:10:47 2024 +0200

    B

commit 0ad5c13d0496e517e66aad45ccf4cc75b09340df (main)
Author: Lasse Lund Sten Jensen <lajl@itu.dk>
Date:   Wed Sep 18 00:34:58 2024 +0200

    A
```

</br>

We can see that `B` and `C` are on the `feature` branch, while `A` is on the `main` branch.

</br>

It should look something like this:

![Branch feature](../../images/lessons/git/branch-a-b-c.svg)

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

## Deleting branches

You can delete branches with the `branch` command and the options `-d` and `-D`.

Read up on it in the documentation, `man git-branch`.

</br>

```bash
git branch -d feature
```

> Do not delete the branch yet!

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

## What do we do next?

So, we have made some changes on the `feature` branch and that is a job well done. Amazing code right there...

What do we do with them?

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

Merge them back into `main` !

</br>
</br>
