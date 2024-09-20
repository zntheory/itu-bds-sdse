---
description: "Basics of Git."
title: "Introduction"
keywords:
  - Software engineering
  - Git
---

## Introduction to <i class="fab fa-git"></i>

### The goal

Not all the commands, but enough that you _git_ it.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## But—before we git we man

If you are not familiar with `man`, it is a command-line utility for reading the manual pages (documentation) of the Unix and Unix-like operating systems.

</br>
</br>

**Try it out:**

```bash
man man
```

> **Hint:** Use `q` to exit.

</br>
</br>

We will only cover a fraction of git commands, but you can always read the manual pages for more information. Now you know how.

```bash
man git- # Press tab for auto complete (if you are using zsh or similar)
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

## What is Git?

Git is a distributed version control system (VCS).

Traditionally VCSs were centralized, which came with some downsides—but Git is distributed. This means that every developer has a full copy of the repository on their local machine.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Commands

In Git, commands are divided into high-level ("porcelain") commands and low-level ("plumbing") commands.

We will be using a bit of both.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Some terminology

- **repo**: A project tracked by Git.

</br>

- **commit**: A snapshot of the repository in its entirety at a specific point in time.

> Represented by a **SHA**, which is a unique identifier generated from the contents of the change, author, time, and more.
> </br>
> </br>
> Example: `61ddb117f38022913c17aa069fecc3013b38dd9d`

</br>

- **git index**: The Git index is an essential data structure in Git, and it serves as the temporary staging area for changes before committing them to the project history.

> When you run `git add`, you are adding changes to the index. The files from your working directory are hashed and stored as objects in the index, leading them to be "staged changes".
>
> More info: [Git Index](https://graphite.dev/guides/git-index)

</br>

- **work tree**, **working tree**, **main working tree**: This is the directory and set of files that you are currently working on. The git repo. A working tree is setup by `git init` or `git clone`.

</br>

- **squash**: Combining multiple commits into one.

> A squash would be taking N commits and turning it into 1 commit (most commonly). Great for cleaning up your commit history.

</br>

- **untracked**, **staged**, and **tracked**: The state of a file in the working tree.

</br>

![Git states](../../images/lessons/git/untracked-staged-tracked.svg)

</br>

> **untracked**: A file that is not being tracked by Git. These files are easier to accidentally lose work on since Git is not tracking them.
> 
> **indexed/staged**: A file that has been added to the index. You must stage before you commit and you stage changes by using the `git add` command.
> 
> **tracked**: A file that is being tracked by Git. This means that Git is aware of the file and its changes and they will be included in the next commit.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Some facts

- Git is an acyclic graph

</br>

- In git, each commit is a node in the graph, and each node has a parent (except the first commit), and each pointer is a child to parent relationship

</br>

- If *untracked* files are deleted they are lost forever, **so commit early and often**—you can always change history to turn it into one commit (squashing)

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

For many people their experience with git can be summed up in these 5 commands:

* `status`
* `add`
* `commit`
* `push`
* `pull`

</br>
</br>

Anything beyond that can feel _very advanced_.

We will go a bit beyond these.

For now, we assume you have zero knowledge and experience with **git**. This part of the course is about making you practically comfortable using git for daily work and forming some good habits.

</br>
</br>
