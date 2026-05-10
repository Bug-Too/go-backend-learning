# Lab 2: Control Flow

In this lab, you will learn how to control the flow of your Go programs using `if/else`, `switch`, and `for` loops. Remember, `for` is the only loop in Go!

## Objective
Create a program that categorizes student grades and prints a class roster.

## Setup
```bash
mkdir -p cmd/lab02
touch cmd/lab02/main.go
```

## Instructions

1.  **If/Else:** Write a function that takes an integer `score` (0-100) and prints whether the student "Passed" (>= 50) or "Failed" (< 50).
2.  **Switch:** Expand the grading logic using a `switch` statement to print a letter grade:
    *   A: >= 80
    *   B: >= 70
    *   C: >= 60
    *   D: >= 50
    *   F: < 50
3.  **For Loop:** Write a standard `for` loop (initialization; condition; post) that counts from 1 to 5, printing "Processing student X".
4.  **For as a While Loop:** Write a `for` loop that acts like a `while` loop (only a condition) to simulate waiting for a task to complete.

## Running
```bash
go run cmd/lab02/main.go
```
