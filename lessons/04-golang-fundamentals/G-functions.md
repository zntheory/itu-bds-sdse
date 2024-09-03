---
description: "Fundamentals of the Go programming language."
title: "Functions"
keywords:
  - Software engineering
  - Go
---

## Functions

Go functions are similar to functions in other programming languages.

- A function can take zero or more arguments.
- Arguments can have default values.
- The last argument can be variadic (variable lenght).

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### **Some things to be aware of**

- Functions can return more than one value.
- Functions can return labeled variables.
- Functions always receive arguments by value.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

**Syntax and use:**

```go
func load() {}
func load(file string) {}

func add(a int, b int) int {
    return a + b
}

func substract(a, b int) int {
    return a - b
}

func addAndSubstract(a int, b int) (int, int) {
    return a + b, a - b
}
```

Labelled return values, but try and avoid this as it is considered a bad practice.

```go
func multiply(a, b int) (result int) {
    result = a * b
    return
}
```

</br>
</br>
