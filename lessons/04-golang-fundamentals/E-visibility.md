---
description: "Fundamentals of the Go programming language."
title: "Visibility"
keywords:
  - Software engineering
  - Go
---

# Visibility

In a module:

- If it is TitleCase, it is **public**
- If it is camelCase, it is **private**

Variables and lambda functions (??) can be:

- **Module** scoped
- **Function** scoped
- **Block** scoped

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

**Example:**

```go
package main

var PublicVariable = "I am public"      // Module scoped
var privateVariable = "I am private"    // Module scoped

func main() {
    var functionScoped = "I am function scoped"
    {
        blockScoped := "I am block scoped"
    }
}

func notExported() {
    // This function is not exported; only visible within this package
}

func Exported() {
    // This function is exported; visible outside this package
}
```

</br>
</br>
