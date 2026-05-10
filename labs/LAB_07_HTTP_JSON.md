# Lab 7: Standard Library - HTTP & JSON

Let's build our first web server using only Go's standard library.

## Objective
Create an API endpoint that returns a list of courses in JSON format.

## Setup
```bash
mkdir -p cmd/lab07
touch cmd/lab07/main.go
```

## Instructions

1.  **The Struct:** Define a `Course` struct. To make it serialize properly to JSON, add struct tags: 
    `` `json:"id"` `` and `` `json:"title"` ``. Note: Struct fields MUST start with a capital letter to be exported and visible to the `encoding/json` package.
2.  **The Handler:** Create an HTTP handler function matching the signature `func(w http.ResponseWriter, r *http.Request)`.
3.  **JSON Encoding:** Inside the handler, create a slice of `Course`. Use `json.NewEncoder(w).Encode(courses)` to convert the slice to JSON and write it directly to the HTTP response. Don't forget to set the `Content-Type` header to `application/json`.
4.  **The Server:** In `main()`, use `http.HandleFunc("/courses", yourHandlerFunc)` to register the route. Then, start the server using `http.ListenAndServe(":8080", nil)`.

## Testing
Run the server:
```bash
go run cmd/lab07/main.go
```
In another terminal (or your browser), test the endpoint:
```bash
curl http://localhost:8080/courses
```
