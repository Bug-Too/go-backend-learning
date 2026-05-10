# Lab 6: Pointers and Memory

Understanding pointers is crucial for performance and modifying data in place.

## Objective
Learn the difference between passing by value and passing by reference.

## Setup
```bash
mkdir -p cmd/lab06
touch cmd/lab06/main.go
```

## Instructions

1.  **Pointers Basics:** Declare an integer variable `x`. Declare a pointer variable `p` that points to `x` (using `&x`). Print the value of `x`, the memory address `p`, and the dereferenced value `*p`.
2.  **Pass by Value:** Create a function `updateNameValue(name string)` that modifies the string. Call it in `main`. Notice that the original string in `main` does not change.
3.  **Pass by Reference (Pointer):** Create a function `updateNamePointer(name *string)` that modifies the string at the pointer's address. Call it from `main` by passing the memory address (`&`). Notice that the original string is now updated.
4.  **Struct Pointers:** It's common to pass pointers to structs to avoid copying large amounts of data. Create a method on a struct that uses a pointer receiver (e.g., `func (c *Course) UpdatePrice(newPrice float64)`) to modify the struct's state.

## Running
```bash
go run cmd/lab06/main.go
```
