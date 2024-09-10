---
description: "Fundamentals of the Go programming language."
title: "Interfaces"
keywords:
  - Software engineering
  - Go
---

## Interfaces

Interfaces are a way to define a set of methods that a type must implement.

They are a powerful feature of Go, and they are used to define contracts between types.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Why do we need interfaces?

Well, let's say we want to create an array of Courses and Workshops, so we can iterate and print them.

We run into a problem.

</br>

```go
var courses [2]Course
courses[0] = goCourse
courses[1] = goWorkshop // error

for _, c := range courses {
    fmt.Println(c)
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

The same type problem occurs when we want to create a function that can receive both Courses and Workshops. Like for instance a function `SignUp()`.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

To get around this, we create an interface. Let's call it `Signable`.

</br>

```go
type Signable interface {
    SignUp() string
}
```

</br>

Interfaces define a set of methods that a type must implement in order to fulfil the contract.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

This is how the `Course` and `Workshop` method implementations would look like:

</br>

```go
func (c Course) SignUp() string {
    return fmt.Sprintf("Signed up for the course %s", c.Name)
}

func (w Workshop) SignUp() string {
    return fmt.Sprintf("Signed up for the workshop %s", w.Name)
}
```

</br>

And this this would work, since both `Course` and `Workshop` implement the `Signable` interface:

</br>

```go
var courses [2]Signable
courses[0] = goCourse
courses[1] = goWorkshop

for _, c := range courses {
    fmt.Println(c)
}
```

</br>

This may seem confusing, since we are not explicitly saying that `Course` and `Workshop` implement the `Signable` interface.

</br>

> In Go, implementation is **implicit**. If a type has the methods defined in the interface, it implements the interface.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

What we have just done is also known as polymorphism.

</br>
</br>
