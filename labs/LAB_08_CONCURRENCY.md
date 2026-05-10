# Lab 8: Concurrency (Goroutines & Channels)

Go handles concurrency beautifully using lightweight threads called goroutines, and channels for them to communicate.

## Objective
Run tasks simultaneously and collect their results safely.

## Setup
```bash
mkdir -p cmd/lab08
touch cmd/lab08/main.go
```

## Instructions

1.  **Goroutines:** Write a function `processData(id int)` that prints a message, sleeps for a random amount of time (using `time.Sleep`), and prints a completion message. In `main()`, call this function 3 times normally. Then, add the `go` keyword before the function calls to run them concurrently. Add a `time.Sleep` at the end of `main` so the program doesn't exit before the goroutines finish.
2.  **Channels:** `time.Sleep` is a bad way to wait. Let's use channels.
    *   Create a channel of strings: `ch := make(chan string)`.
    *   Update `processData` to take the channel as an argument: `processData(id int, ch chan string)`.
    *   Instead of printing the completion message, send it to the channel: `ch <- fmt.Sprintf("Task %d done", id)`.
    *   In `main`, launch the 3 goroutines passing the channel.
    *   Read from the channel 3 times and print the results: `msg := <-ch`. This inherently blocks and waits, eliminating the need for `time.Sleep` in `main`.

## Running
```bash
go run cmd/lab08/main.go
```
