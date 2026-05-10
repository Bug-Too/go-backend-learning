# Lab 10: Database Integration (PostgreSQL)

Mock data is nice, but real applications need a database. We'll connect our LMS to PostgreSQL using the standard `database/sql` package and a driver.

## Objective
Connect to PostgreSQL and perform basic queries for our courses.

## Setup
Install the Postgres driver:
```bash
cd lms-backend
go get -u github.com/lib/pq
```

Make sure you have a local PostgreSQL instance running.

## Instructions

1.  **Connection:** In your `main.go` (or a separate database package), import `"database/sql"` and the driver `_ "github.com/lib/pq"`.
2.  **Open DB:** Use `sql.Open("postgres", "postgres://user:password@localhost/dbname?sslmode=disable")`. (Replace with your actual DB credentials).
3.  **Ping:** Always call `db.Ping()` immediately after `Open` to verify the connection is actually alive.
4.  **Create Table (Optional setup):** You can write a raw SQL query `CREATE TABLE IF NOT EXISTS courses ...` and execute it with `db.Exec()`.
5.  **Insert (Create):** Write a function to insert a new course into the database. Use parameterized queries (`$1, $2`) to prevent SQL injection.
    *   `db.QueryRow("INSERT INTO courses (title) VALUES ($1) RETURNING id", "My Course").Scan(&id)`
6.  **Select (Read):** Write a function to fetch all courses.
    *   `rows, err := db.Query("SELECT id, title FROM courses")`
    *   Iterate over `rows.Next()` and use `rows.Scan(&id, &title)` to populate your structs.
7.  **Integrate:** Hook these database functions up to the Gin routes you created in Lab 9.

*Note: In future refactoring, we will learn Clean Architecture to separate the database logic from the HTTP handlers!*