---
description: "Basics of Git."
title: "Pull"
keywords:
  - Software engineering
  - Git
---

## Pull

When fetching we keep the local repository's remotes updated. Fetching does, as we have seen, not alter the local repository state.

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

We can use the `git pull` command to fetch and merge changes from the remote repository.

This is the same as running `git fetch` followed by `git merge` as we just did before.

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

### Exercise: Add a change in the remote repository and pull it

> * Navigate to the `learn-git` repository.
> * Make sure you are on the `main` branch.
> * Append some text, e.g. `A remote change`, to the `README.md` file in the remote repository.
> * Commit the change.
> * Navigate to the `remote-git` repository.
> * Pull the changes from the remote repository.

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

### Solution: Add a change in the remote repository and pull it

```bash
# navigate to the "learn-git" repository
git checkout main
echo "A remote change" >> README.md
git add README.md
git commit -m "remote change"

# navigate to the "remote-git" repository
git pull
```

</br>

**Output:**

```plaintext
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 327 bytes | 327.00 KiB/s, done.
From ../learn-git
   058f2b5..d8df0e5  feature-delete-test -> origin/feature-delete-test
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> main
```

</br>

We got an error. Why?

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

This is because we have not set up a tracking branch.

We can do this by running the command:

```bash
git branch --set-upstream-to=origin/main main
```

</br>

**Output:**

```plaintext
Branch 'main' set up to track remote branch 'main' from 'origin'.
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

If we run `git pull` again, we will see that the changes are pulled from the remote repository.

</br>

**Output:**

```plaintext
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 297 bytes | 148.00 KiB/s, done.
From ../learn-git
   1bfa0c5..7142285  main       -> origin/main
Updating 1bfa0c5..7142285
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)
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

## Pull with rebase

We can also use the `--rebase` flag with the `git pull` command.

This will rebase the local changes on top of the remote changes. Again, useful for keeping a clean history. The software developers on your team will love this.

</br>

```bash
git pull --rebase
```

</br>
</br>
