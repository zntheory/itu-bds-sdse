---
description: "Basics of Git."
title: "Stashing changes"
keywords:
  - Software engineering
  - Git
---

## Stash

Git stash will take all changes tracked by git—i.e. changes to index and change to work tree—and store them into the "stash". It is a special commit not part of the repository history.

We can think of stash as a stack of temporary changes. We may use them later. We may not.

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
git stash
```

</br>

We can provide a message to the stash:

```bash
git stash -m "a message"
```

</br>

Stashes can be listed:

```bash
git stash list
git stash show
```

</br>

We can pop the latest stash:

```bash
git stash pop
git stash pop --index <index>
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

### Exercise: Stashing changes

> * In the upstream repository `learn-git`, add and commit a change to a new file.
> * In the downstream repository `remote-git`, make a change to the `README.md` file, ***but do not commit it***.
> * In this example we pretend we need to put our temporary changes aside, because something came up, and we need to work on something else. So stash the changes.

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

### Solution: Stashing changes

Navigate to the `learn-git` repository.

```bash
echo "upstream change" >> upstream.md
git add upstream.md
git commit -m "upstream change"
```

Navigate to the `remote-git` repository.

```bash
echo "downstream change" >> README.md
```

Stash the changes:

```bash
git stash
```

</br>

**Output:**

```plaintext
Saved working directory and index state WIP on feature: 58dab59 upstream change
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

### Exercise: Playing around with stashes

> * List the stashes.
> * Show the latest stash.
> * Pop the latest stash.
> * Stash again with a custom message.
> * List the stashes again.

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

### Solution: Playing around with stashes

```bash
git stash list
git stash show
git stash pop
git stash -m "custom changes"
git stash list
```

</br>
</br>
