---
description: "Fundamentals of the Go programming language."
title: "Goroutines"
keywords:
  - Software engineering
  - Go
---

## Goroutines

* **goroutines** are lightweight threads.
* A **goroutine** is created by invoking any function with a `go` prefix.
* `go functionName()`

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

## Creating a **goroutine**

To turn any function into a "thread", e.g. a goroutine, add the `go` keyword before the function call.

```go
func PrintMessage(message string) {
    fmt.Println(message)
}

func main() {
    go PrintMessage("Learning Go!")
    fmt.Println("Goodbye!")
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

## TRY IT OUT

![Rob Pike](../../images/rob-pike.png)

</br>

### Exercise: Explore goroutines

> Change the `PrintMessage` function to print a message 5 times.

> Print two additional messages in the `main` function using the `PrintMessage` function.

> Turn the calls to `PrintMessage` into goroutines.

</br>

> **Question:** What is the output?

> **Consider:** How do you know when each goroutine has finished?

</br>
</br>
