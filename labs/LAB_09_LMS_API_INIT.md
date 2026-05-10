# Lab 9: LMS Project - Framework Initialization

Now we transition to building the actual LMS. We will use a framework (like Gin or Echo) to make routing and middleware easier. We will use `Gin` for this lab.

## Objective
Set up the LMS API structure and basic CRUD routes.

## Setup
First, install the Gin framework:
```bash
cd lms-backend
go get -u github.com/gin-gonic/gin
```

Create the application entry point:
```bash
mkdir -p cmd/api
touch cmd/api/main.go
```

## Instructions

1.  **Initialize Gin:** In `cmd/api/main.go`, initialize a default Gin router: `r := gin.Default()`.
2.  **Health Check:** Create a simple GET route `/health` that returns a JSON response `{"status": "ok"}` using `c.JSON(200, gin.H{...})`.
3.  **Group Routing:** Create a route group for API version 1: `v1 := r.Group("/api/v1")`.
4.  **Course Routes (Mock Data):** Inside the `v1` group, define routes for courses:
    *   `GET /courses` (returns a hardcoded list of courses)
    *   `GET /courses/:id` (reads the ID param using `c.Param("id")` and returns a mock course)
    *   `POST /courses` (accepts JSON body, binds it to a struct using `c.ShouldBindJSON`, and returns the created course)
5.  **Run:** Start the server on port 8080: `r.Run(":8080")`.

## Testing
Run the API:
```bash
go run cmd/api/main.go
```
Test with cURL:
```bash
curl http://localhost:8080/health
curl http://localhost:8080/api/v1/courses
```
