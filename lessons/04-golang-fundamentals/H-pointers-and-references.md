---
description: "Fundamentals of the Go programming language."
title: "Pointers and references"
keywords:
  - Software engineering
  - Go
---

## Functions receiving references

By default, Go functions receive arguments **by value**.

But you can pass a **reference to a variable** to a function. In this case, we need to receive a **pointer** instead of the value.

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
func increment(a *int) {
    *a++
}

func main() {
    var a = 1
    increment(&a)
    fmt.Println(a)
}
```

```go
func main() {
    var a = 1
    var b = &a
    increment(b)
    increment(&a)
    fmt.Println(a)
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

We need to use the `*` operator to access the value of the pointer.

To get the address of a variable, use the `&` operator.

> We need to use pointers when functions need to modify the value of the argument.

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

> Let's try and print the address of the pointer and the value of the pointer.

<!-- fmt.Println("The the pointer is %v and the value is %v", pointer, *pointer) -->

</br>
</br>
