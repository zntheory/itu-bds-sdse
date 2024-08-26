---
description: "Fundamentals of the Go programming language."
keywords:
  - Software engineering
  - Go
---

# Go basics

In this lesson, we will cover the fundamentals of the Go programming language.

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

- Syntax rules; use of curly braces, case-sensitivity
- Modules
- Variables, types and constants
- Data types
- Visibility
- Collections
- Numbers
- Functions
- Pointers and references
- Control structures
- panic, defer
- Error handling design pattern
- Packages to organize, share and use code

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

As a practical exercise (well, many exercises) along the way, we are going to build a command line tool that can compress and decompress bitmap images.

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

## Language types

Developers write code in | Shipped as</br>
Interpreted languages -> Source code (e.g. JS, Python)</br>
Intermediate compiled languages -> Bytecode (e.g. Java)</br>
Compiled languages -> Machine code

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

Developers write code in | Shipped as</br>
Go -> Source code (e.g. JS, Python)</br>
Go -> Bytecode (e.g. Java)</br>
Go -> Machine code

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

## Basic rules

- We use `.go` files
- Code blocks in `{}`
- No styling freedom
- We do have semi-colon to separate sentences
- They are optional though
- Case-senstive
- Strongly typed
- NOT an object-oriented language
- No classes, no inheritance
- No exceptions, no try-catch

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

- We have one file acting as the entry point with a main function
- A folder is a package
- Packages can have simple names (utilities) or URLs (github.com/username/project)
- Within one `.go` file, we can have:
  - Variables
  - Functions
  - Type declarations
  - Method declarations

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

## Modules

- A module is a group of packages
- You can think of it as a project
- Modules contain a `go.mod` file that contains the module name, configuration and metadata (about dependencies)

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

## CLI

It manipulates the module
- `go mod init` -> initializes the module
- `go build` -> builds the module
- `go test` -> tests the module
- `go run` -> builds and runs the module
- `go get` -> retrieves dependencies
