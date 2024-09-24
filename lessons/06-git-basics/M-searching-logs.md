---
description: "Basics of Git."
title: "Searching git logs"
keywords:
  - Software engineering
  - Git
---

## Searching repository history

Logs are great, because we can search them. For all the details, see `man git-log`.

Here are some examples:

```bash
git log --author="John Doe"
git log --grep="bug #1234"
git log --grep bug
git log --since="2 weeks ago"
git log --until="yesterday"

# search for a commit with message and show the diff
git log --grep bug -p

# Search for a commit that changed a file
git log -- <file>

# Search for a commit that changed a file and show the diff
git log -p -- <file>
```

</br>
</br>
