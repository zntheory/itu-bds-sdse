---
description: "Fundamentals of the Go programming language."
title: "Variables, Types, and Constants"
keywords:
  - Software engineering
  - Go
---

## Defining variables

Using the `var` keyword, you can define a variable in Go. The syntax is as follows:

```go
var x int
var name string
const pi = 3.14
```

</br>
</br>

> Data types come after the variable identifer and are mandatory in this form.

> Variables value is **nil** by default.

> Constants can only be bool, string or numbers. Always need a value.

> In Go constants are ***true* constants** and not immutable variables—unlike in Python, JavaScript and others. This means less runtime overhead.

</br>
</br>

Generally, you can expect Go to infer the type of a variable based on the value you assign to it. 

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

```go
var z int = 42

var text string
text = "Hello!"

lastName := "Doe"
```

</br>
</br>

> Variables can be created with initialization.

> Strings use double quotes.

> Initialization shortcut. Only valid inside functions.

</br>
</br>

Backticks `` ` `` are used for raw string literals.

<!-- Semicolon?

![Semicolon](../../images/lessons/golang-fundamentals/we-dont-do-that-here.png)
 -->

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

Consider: When might we want to specify a type for numbers?

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

## Scope

> Variables are scoped to the block in which they are declared.

```go
package main

// global-scoped (within package) variables
...

func main() {
    // function-scoped variables
    ...
    {
        // block-scoped variables
    }
}
```
