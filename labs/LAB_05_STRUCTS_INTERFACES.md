# Lab 5: Structs & Interfaces

Go is not a traditional Object-Oriented language. It uses Structs for data and Interfaces for behavior.

## Objective
Model LMS entities (User, Course) and define common behaviors.

## Setup
```bash
mkdir -p cmd/lab05
touch cmd/lab05/main.go
```

## Instructions

1.  **Structs:** Define a `Course` struct with fields: `ID` (int), `Title` (string), and `Price` (float64).
2.  **Methods:** Add a method to the `Course` struct called `Display()` that prints the course details beautifully. A method is just a function with a receiver argument.
3.  **Interfaces:** 
    *   Define an interface called `Printable` with a single method signature: `Display()`.
    *   Since `Course` has a `Display()` method, it automatically satisfies the `Printable` interface (implicit implementation).
4.  **Using Interfaces:** Write a function `PrintDetails(p Printable)` that accepts any type satisfying the interface and calls `p.Display()`. Pass your `Course` instance to this function.

## Running
```bash
go run cmd/lab05/main.go
```
