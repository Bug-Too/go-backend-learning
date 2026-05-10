# Lab 3: Data Structures (Arrays, Slices, Maps)

Go provides a few core data structures. Slices (dynamic arrays) and Maps (key-value dictionaries) will be your most used tools.

## Objective
Manage a list of courses and a registry of student scores.

## Setup
```bash
mkdir -p cmd/lab03
touch cmd/lab03/main.go
```

## Instructions

1.  **Arrays vs Slices:** 
    *   Create an array of 3 strings for fixed course categories (e.g., "Programming", "Math", "Science").
    *   Create a slice of strings for dynamic course names. Use the `append()` function to add "Go Basics" and "Advanced Go" to the slice.
2.  **Iterating over Slices:** Use a `for` loop with the `range` keyword to iterate over your slice of courses and print their index and name.
3.  **Maps:**
    *   Create a map where the key is a student's name (string) and the value is their score (int).
    *   Add 3 students to the map.
    *   Retrieve and print a specific student's score.
    *   Delete a student from the map using the `delete()` function.
    *   Use `range` to print all remaining students and scores.

## Running
```bash
go run cmd/lab03/main.go
```
