---
description: "Fundamentals of the Go programming language."
title: "Packages"
keywords:
  - Software engineering
  - Go
---

## Packages

In Go, a package is a collection of Go source files that are in the same directory.

A package can be imported into another package. The package name is the same as the last element of the import path. For example, the package name for the import path `fmt` is `fmt`.

</br>
</br>

```go
package main    // package declaration

import "fmt"    // import statement

func main() {   // Main app's entry point
    fmt.Println("Hello from Go!")
}
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

Files in a package must be in the same folder.

The package name is the same as the folder name.

When importing packages from the internet, the import path is the URL of the package.

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

The Go compiler will actually group all files that belong to the same package at compile time.

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

## TRY IT OUT

![Rob Pike](../../images/rob-pike.png)

</br>

- Multiple files in a package
- Importing from the same package
- Referencing from the same package
- Creating a new package
- Referencing from another package
- Unsafe `print` and `println` functions and safe alternatives
- Comments
- Linting on save only (VSCode)

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

## Visibility

Convention in Go is that the first letter of an identifier determines its visibility.

</br>

```go
package main

import "fmt"

func PrintData() {
    fmt.Println("Hello from PrintData!")
}
```

</br>

```go
package main

func main() {
    PrintData()
}
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

## Other notes

- Imports are per file, not per package.
- Importing a package in the same module is done with the project name (in the `go.mod` file) as prefix to the package name—think of it as a path.
- Imported packages can be aliased.
- Referencing a package is done with the package name as prefix to the identifier.

</br>
</br>
