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

- **commit**: A snapshot of the repository at a specific point in time.

> Represented by a **SHA**, which is a unique identifier generated from the contents of the change, author, time, and more.
> </br>
> </br>
> Example: `61ddb117f38022913c17aa069fecc3013b38dd9d`

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>