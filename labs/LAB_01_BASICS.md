# Lab 1: Go Basics - Hello World and Variables

Welcome to your first Go lab! In this lab, we will cover the absolute basics of Go: packages, imports, the `main` function, variables, and printing to the console.

## Objective
Write a Go program that prints a customized greeting and performs a simple calculation using variables.

## Setup

1. Open your terminal and navigate to the `lms-backend` directory.
2. Inside `lms-backend/cmd`, create a new folder called `lab01`.
3. Inside `lab01`, create a file named `main.go`.

```bash
mkdir -p cmd/lab01
touch cmd/lab01/main.go
```

## Instructions

Open `cmd/lab01/main.go` in your code editor and complete the following steps:

### Step 1: Package Declaration
Every Go file starts with a package declaration. Since this is an executable program (not a library), it must be named `main`.
```go
package main
```

### Step 2: Imports
We need the `fmt` (format) package to print text to the console.
```go
import "fmt"
```

### Step 3: The Main Function
The `main()` function is the entry point of your Go program. 
```go
func main() {
    // Your code goes here
}
```

### Step 4: Variables and Printing
Inside the `main` function:
1. Declare a string variable named `courseName` and assign it the value `"Go Backend Learning"`. Use the `var` keyword.
2. Declare an integer variable named `studentCount` and assign it the value `1`. Use the short declaration syntax (`:=`).
3. Print a welcome message using `fmt.Println()`.
4. Print a formatted string using `fmt.Printf()`.

**Hint for formatted strings:**
*   `%s` is for strings.
*   `%d` is for integers.
*   `\n` adds a new line.

Example output:
```text
Welcome to Go Backend Learning!
Currently, there is 1 student enrolled.
```

## Running Your Code

To run your code, use the `go run` command in your terminal:

```bash
go run cmd/lab01/main.go
```

---

## What you learned:
*   **`package main`**: Tells the Go compiler this file should compile as an executable program.
*   **`import "fmt"`**: How to bring in standard library packages.
*   **`var` vs `:=`**: Go provides explicit (`var name string = "..."`) and implicit (`name := "..."`) ways to declare variables.
*   **`fmt.Println` vs `fmt.Printf`**: Printing with and without format specifiers.

When you have completed this lab and run it successfully, let me know, and we can review it or move on to Lab 2!