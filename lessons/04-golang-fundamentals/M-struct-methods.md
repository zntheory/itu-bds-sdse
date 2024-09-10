---
description: "Fundamentals of the Go programming language."
title: "Struct methods"
keywords:
  - Software engineering
  - Go
---

## Type: Struct with methods

Like with simple types, we can add methods to structs.

Struct methods are functions that are attached to a type delcared outside of the structure.

</br>

```go
func (p Person) Greet() string {
    return "Hello, my name is" + p.Name
}

func main() {
    p := Person{"John", 30}
    msg := (p.Greet())
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

## TRY IT OUT

![Rob Pike](../../images/rob-pike.png)

</br>

### Exercise: Create a data structure for a course with instructor

> Create structs for a course with an instructor.

> The instructor should have a first name, last name.

> Implement a method that prints the first name and last name of an instructor.

</br>

Note: The struct method can be defined in any file within the package.

</br>
</br>
