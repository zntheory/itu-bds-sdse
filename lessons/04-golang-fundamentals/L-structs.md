---
description: "Fundamentals of the Go programming language."
title: "Structs"
keywords:
  - Software engineering
  - Go
---

## Type: Struct

A struct is a collection of fields under a single name.

Same rules for visiblity apply to structs.

```go
type Person struct {
    Name string
    Age  int
}
```

### Constructor

Go has two built-in constructors for structs—with and without field names.

```go
func main() {
    var p1 Person
    p1 = Person{Name: "John", Age: 30}  // with field names
    p2 := Person{"John", 30}            // without field names
}
```

</br>

> Can you inherit from another struct? No, Go does not support inheritance.

</br>
</br>
