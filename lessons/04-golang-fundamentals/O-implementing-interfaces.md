---
description: "Fundamentals of the Go programming language."
title: "Implementing interfaces"
keywords:
  - Software engineering
  - Go
---

## Implementing interfaces

Often we want to print a struct in a specific way.

Let's go back to the course and instructor exercise from earlier.

If we just print the course instance, we will get something that looks like JSON, but not quite.

We want to print the course information in a specific way.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## The stringer interface

The way to do it is to implement the `Stringer` interface.

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

### Exercise: Implement the `Stringer` interface on the `Course` struct

> Attach a `String()` method to the course struct that prints the course information in a "nicer" way.

</br>

More information on [go.dev](https://go.dev/tour/methods/17).

</br>
</br>

<!-- 
```go
// Something like:
func (c Course) String() string {
    return fmt.Sprintf("Course: %s, Instructor: %s", c.Name, c.Instructor)
}
```
-->
