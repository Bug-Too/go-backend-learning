# Lab 4: Functions & Error Handling

Go functions can return multiple values, which is commonly used for error handling. Go does not have exceptions (`try/catch`).

## Objective
Write a function that calculates an average score, handling cases where the input is invalid.

## Setup
```bash
mkdir -p cmd/lab04
touch cmd/lab04/main.go
```

## Instructions

1.  **Multiple Returns:** Create a function named `calculateAverage` that takes a slice of integers (scores) as input. It should return two values: the average (float64) and an error (`error`).
2.  **Error Handling:** 
    *   Inside the function, if the slice is empty, return `0` and a custom error using `errors.New("cannot calculate average of empty slice")`. (You will need to import the `"errors"` package).
    *   If valid, calculate and return the average and `nil` for the error.
3.  **Calling the Function:** In `main()`, call your function.
4.  **Checking Errors:** Always check if the returned error is `nil` before using the successful result. If it's not `nil`, print the error message and exit early or handle it.

## Running
```bash
go run cmd/lab04/main.go
```
