---
description: "Basics of Git."
title: "Push"
keywords:
  - Software engineering
  - Git
---

## Push

Git push is used to push commits made on your local branch to a remote repository.

</br>

```bash
git push <remote> <branch>
```

</br>

As with the `git pull` command, it is a prerequisite that "tracking" is configured for a remote branch.

We will get an error, if that is the case.

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

### Exercise: Push a change to the remote repository

> * Navigate to the `remote-git` repository.
> * Checkout the `feature` branch.
> * Append `Change from remote` to the `README.md` file.
> * Commit the change with message `Change from remote`.
> * Push the changes to the remote repository.
> * Validate the change made in the remote repository.

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

### Solution: Push a change to the remote repository

Navigate to the `remote-git` repository.

```bash
git checkout feature
echo "Change from remote" >> README.md
git add README.md
git commit -m "Change from remote"
git push
```

Validate the change made in the remote repository. First navigate to the `learn-git` repository.

```bash
git checkout feature
git log --oneline --graph
```

</br>
</br>
