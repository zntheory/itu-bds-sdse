---
description: "Basics of Git."
title: "Resetting"
keywords:
  - Software engineering
  - Git
---

## Reset

It is a way to discard current changes. At least this is the most common use case. There are other uses for `git reset` but we will focus on this application only in the course.

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

### Soft reset

Git soft reset will move the HEAD to a previous commit but will keep the changes in the working directory. This is useful when you want to keep the changes and maybe put them on a branch instead.

```bash
git reset --soft <commit-ish>
```

</br>

### Example: Undo the last commit

```bash
git reset --soft HEAD~1
```

If we do a `git status` we will see that the changes that were reset are in the index (i.e. staged).

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

## Changing a previous commit

We have two options here.

1. **Amend the commit**
   ```bash
   git commit --amend
   ```
    This will open the editor with the previous commit message. We can change the message and save the file with `:wq` and then press `Enter`.

2. **Soft reset**
   ```bash
   git reset --soft <commit-ish>
   ```
   This will move the HEAD to the previous commit but keep the changes in the working directory. We can then commit the changes again.

> **Remember**
> 
> Both of these are changing history and creating new SHAs.

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

## Hard reset

This is the most dangerous reset. It will move the HEAD to a previous commit and discard all changes in the working directory.

```bash
git reset --hard <commit-ish>
```

</br>

### Example: Discard all changes

```bash
# Undo the last commit
git reset --hard HEAD~1
```

```bash
# Undo all changes and reset to latest commit on origin/main
git reset --hard origin/main
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

### Exercise: Reset a commit

> * Navigate to a repository.
> * Create a new file `reset.md`.
> * Add some text to the file and commit it with message `want to reset this`.
> * Undo the commit by hard resetting it.
> * Check the logs.

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

### Solution: Reset a commit

Navigate to a repository. Create a new change and commit it.

```bash
echo "reset" >> reset.md
git add reset.md
git commit -m "want to reset this"
```

Then we delete the change, which is the last commit, but hard resetting.

```bash
git reset --hard HEAD~1
```

Check the logs.

```bash
git log --oneline
```

</br>
</br>

### Observation

Only changes that git ***knows*** about will be deleted in the hard reset. Any untracked changes will remain.

> **Warning**
> 
> It is easy to loose changes that are staged but not committed.

</br>
</br>
