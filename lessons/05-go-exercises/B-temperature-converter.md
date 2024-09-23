---
description: "Fundamentals of the Go programming language."
title: "Temperature converter"
keywords:
  - Software engineering
  - Go
---

## Exercise: Temperature converter

*Build a temperature converter CLI tool in Go using structs and pointers*

**Objective:**

Create a command-line interface (CLI) tool in Go that converts temperatures between Celsius and Fahrenheit. The idea is to build a tool that can be embedded as a call in a script or similar. See the example outputs below.

Try and use structs and pointers to acomplish this.

**Requirements:**

1. **Use a Temperature struct**

   - Create a `Temperature` struct that contains:
     - A `Value` field representing the numerical temperature.
     - A `Unit` field representing the unit of the temperature ("C" for Celsius or "F" for Fahrenheit).

2. **Implement conversion functions using pointers**

   - Write two functions:
     - `celsiusToFahrenheit`
     - `fahrenheitToCelsius`
   - Each function should:
     - Accept a pointer to a `Temperature` struct.
     - Perform the appropriate conversion using the temperature value from the given struct.
     - Return a pointer to a new `Temperature` struct containing the converted temperature value and the new unit.

3. **Accept arguments from command-line**

   - The program should accept two command-line arguments when executed:
     - The temperature value (e.g., "100")
     - The unit of the temperature ("C" or "F")
   - **Example usage:**
     ```
     <binary> 230 F
     ```
     > The `<binary>` placeholder represents the name of the compiled binary file.

4. **Perform conversion based on input**

   - In the `main` function, create a pointer to a `Temperature` struct using the input arguments.
   - Determine the unit provided and call the appropriate conversion function.
     > **Hint:** Consider which control structure could be used to determine this.
   - Output the converted temperature value and unit to the console.
   - Format the output to display the temperature value without decimal places.
     > **Hint:** Use `fmt.Printf` with format specifiers to control the number type and number of decimal places displayed.
   - **Example output:**
     ```
     110 C
     ```

</br>

**Expected outputs:**

> We use `tempconverter` as an example for the binary and `$` indicates the command prompt.

* **Converting Fahrenheit to Celsius:**

   ```bash
   $ tempconverter 230 F
   110 C
   ```

* **Converting Celsius to Fahrenheit:**

   ```bash
   $ tempconverter 100 C
   212 F
   ```

</br>
</br>

### Hints

> Use the `os` package to access command-line arguments.
> 
> ```go
> os.Args[0] // binary name
> os.Args[1] // first argument
> os.Args[2] // second argument
> ```

> Use the `strconv` package to convert string arguments to numerical values. Like for example converting a string to a float64.
>
> ```go
> value, err := strconv.ParseFloat(os.Args[1], 64)
> ```

> Force an exit if an error occurs with the `os.Exit` function. You can also use `panic`, but `os.Exit` is more appropriate for CLI tools.
>
> ```go
> os.Exit(1)
> ```

</br>
</br>

### Extra (optional) — Implement additional error handling

* Handle invalid input of value.

   ```bash
   $ tempconverter abc F
   Invalid temperature value. Please enter a numeric value.
   ```

* Handle invalid input of unit.

   ```bash
   $ tempconverter 100 K
   Invalid unit. Please provide 'C' for Celsius or 'F' for Fahrenheit.
   ```

</br>
</br>
