---
description: "Fundamentals of the Go programming language."
title: "Factories"
keywords:
  - Software engineering
  - Go
---

## Factories

* Remember: No constructors in Go.

Instead we use the **design pattern**: Factory

```go
func NewPerson(name string, age int) Person {
    return Person{name, age}
}
```

</br>

> With some clever naming, we could name a package `person` and the function `New` to make it look like a constructor, i.e. `person.New("John", 30)`.

</br>
</br>
