---
description: "Fundamentals of the Go programming language."
title: "Testing"
keywords:
  - Software engineering
  - Go
---

## Testing in Go

* Go has a built-in testing framework.
* Tests should be in the same package as the code they are testing.
* Test files must have the suffix `_test.go`.
* The Go CLI `go test` command is used to run tests.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Example: Code under test

```go
func PrintMyName(name string) string {
    return fmt.Sprintf("Hello, my name is %s.", name)
}
```

</br>

### Example: Test case

```go
package main

import "testing"

func TestPrintMyName(t *testing.T) {
    testCases := []struct {
        name        string
        value       string
        expectValue string
        expectFail  bool
    }{
        {"Valid response", "John Doe", "Hello, my name is John Doe.", false},
        {"Invalid response", "John Doe", "Hello, my name is .", true},
        {"Valid lower case name", "john doe", "Hello, my name is john doe.", false},
    }

    for _, tc := range testCases {
        t.Run(tc.name, func(t *testing.T) {
            out := PrintMyName(tc.value)
            if out != tc.expectValue && !tc.expectFail {
                t.Errorf("expected value: %s, got: %s, for name: '%s'", tc.expectValue, out, tc.value)
            }
        })
    }
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

## Running tests

```bash
go test .
```

</br>

> **Note:** There are other ways to run tests, such as `go test -v .` to get more verbose output.

> **Note:** You can also get coverage reports with `go test -cover .`.

</br>
</br>
