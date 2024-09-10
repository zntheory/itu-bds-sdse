---
description: "Fundamentals of the Go programming language."
title: "Type definitions"
keywords:
  - Software engineering
  - Go
---

## Type definitions

We already know that packages can include variables, constants, and functions.

But they can also include types:

* **New types**
* **Aliases**

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
// Type alias
type customString = string

// New type based on an existing type
type customString string

// A type has constructor and conversion functions
cs := customString("Hello")
```

> You can add methods to a new type, but not to an alias.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

Methods are extensions to types and are defined with a special syntax on functions.

```go
func (cs customString) PrintInChinese() string {
    // ...
}

cs.PrintInChinese()
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

> Create a new type 'distance'.

> 

</br>
</br>
