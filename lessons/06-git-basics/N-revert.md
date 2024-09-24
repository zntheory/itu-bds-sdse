---
description: "Basics of Git."
title: "Reverting changes"
keywords:
  - Software engineering
  - Git
---

## Revert

Sometimes we end up making changes that need to be rolled back.

Git revert is a shorthand for undoing changes. It creates a new commit that undoes the changes from the previous commit.

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

**Command**

```bash
git revert <commit-ish>
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

### Exercise: Revert a commit

> * Navigate to the `learn-git` repository.
> * Revert the commit with log message `E`.
> * Check the logs to see the new revert commit.

</br>

> **Hint:** Use `git log` to find the commit hash.

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

### Solution: Revert a commit

Navigate to the `learn-git` repository.

```bash
git revert 1fef21501625d1cb1ab99318ad0fa8487d6ef5cb
```

> **Note:** We ***may*** get a revert conflict. Yes, we can get conflicts on reverts too. If so, resolve the conflict and commit the changes.

</br>

We can see the new commit in the logs.

```bash
git log --oneline --graph
```

**Output**

```plaintext
* d1a64a9 (HEAD -> main) Revert "E"
```

</br>
</br>
