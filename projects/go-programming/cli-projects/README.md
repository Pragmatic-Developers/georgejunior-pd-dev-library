# Go CLI Projects

A collection of **real-world beginner-friendly CLI applications built with Go**.

The goal of this repository is to learn Go by building practical command-line tools rather than isolated syntax exercises.

## Projects

| # | Project             | Description                               | Difficulty |
| - | ------------------- | ----------------------------------------- | ---------- |
| 1 | 💰 Expense Tracker  | Track and manage personal expenses        | ⭐          |
| 2 | 📁 File Organizer   | Automatically organize files into folders | ⭐⭐         |
| 3 | 📝 Developer Notes  | Create, search, and manage personal notes | ⭐⭐         |
| 4 | 🔐 Secret Manager   | Store and retrieve secrets locally        | ⭐⭐⭐        |
| 5 | 🏢 Employee Manager | Manage employees and basic HR operations  | ⭐⭐⭐        |

---

# 1. 💰 Expense Tracker

A CLI application for managing personal expenses.

### Example

```bash
expense add 50 food "Lunch"
expense add 20 transport "Uber"
expense list
expense total
expense delete 2
```

### Features

* [ ] Add expense
* [ ] List expenses
* [ ] View expense details
* [ ] Edit expense
* [ ] Delete expense
* [ ] Calculate total expenses
* [ ] Filter by category
* [ ] Filter by date
* [ ] Monthly expense summary
* [ ] Save expenses to JSON
* [ ] Load expenses when the application starts

### Concepts

* Variables
* Functions
* Structs
* Slices
* Maps
* JSON
* File I/O
* Error handling
* CLI arguments
* Date and time

---

# 2. 📁 File Organizer

A CLI utility that automatically organizes files into folders based on their file types.

### Example

```bash
organizer ~/Downloads
```

Before:

```text
Downloads/
├── image.png
├── report.pdf
├── music.mp3
├── document.docx
└── video.mp4
```

After:

```text
Downloads/
├── Images/
│   └── image.png
├── Documents/
│   ├── report.pdf
│   └── document.docx
├── Music/
│   └── music.mp3
└── Videos/
    └── video.mp4
```

### Features

* [ ] Scan directory
* [ ] Detect file extensions
* [ ] Create folders automatically
* [ ] Move files
* [ ] Support images
* [ ] Support documents
* [ ] Support videos
* [ ] Support audio
* [ ] Add `--dry-run`
* [ ] Add recursive organization
* [ ] Handle duplicate filenames

### Concepts

* `os`
* `path/filepath`
* Files
* Directories
* File extensions
* Command-line arguments
* Error handling

---

# 3. 📝 Developer Notes

A personal knowledge-base CLI for storing programming notes.

### Example

```bash
notes add "goroutines" "Goroutines are lightweight concurrent functions"
notes list
notes search "goroutine"
notes get 12
notes delete 12
```

### Features

* [ ] Create note
* [ ] List notes
* [ ] View note
* [ ] Edit note
* [ ] Delete note
* [ ] Search notes
* [ ] Add tags
* [ ] Filter by tag
* [ ] Favorite notes
* [ ] Sort notes
* [ ] Export notes to Markdown
* [ ] Save notes locally

### Example

```text
$ notes get 12

Title: goroutines

Goroutines are lightweight concurrent functions
managed by the Go runtime.

Tags:
go, concurrency, programming

Created:
2026-09-29
```

### Concepts

* Structs
* Slices
* Maps
* Strings
* Searching
* Sorting
* JSON
* File handling
* Packages

---

# 4. 🔐 Secret Manager

A local CLI application for storing credentials and other secrets.

> **Learning project:** Do not use this as a production password manager until the security implementation has been properly reviewed and tested.

### Example

```bash
vault add github
vault list
vault get github
vault delete github
```

### Features

* [ ] Add secret
* [ ] Get secret
* [ ] List secrets
* [ ] Delete secret
* [ ] Search secrets
* [ ] Master password
* [ ] Password generation
* [ ] Secure password input
* [ ] Encrypt stored data
* [ ] Use environment variables where appropriate

### Example

```text
$ vault get github

Service:  GitHub
Username: george
Password: ********
```

### Concepts

* Structs
* Maps
* Files
* JSON
* Hashing
* Encryption
* Secure input
* Environment variables
* Error handling

---

# 5. 🏢 Employee Manager

A CLI application for managing employee records and basic HR operations.

### Example

```bash
hr employee add
hr employee list
hr employee get EMP002
hr employee update EMP002
hr employee delete EMP002
```

### Example output

```text
$ hr employee list

ID       NAME              DEPARTMENT
EMP001   John Mensah       Finance
EMP002   Ama Boateng      HR
EMP003   Daniel Owusu     IT
```

### Employee details

```text
Employee

ID:          EMP002
Name:        Ama Boateng
Department:  HR
Position:    HR Officer
Email:       ama@example.com
Status:      Active
```

### Leave management

```bash
hr leave apply EMP002
hr leave list
hr leave approve 12
hr leave reject 12
```

### Features

#### Employee Management

* [ ] Add employee
* [ ] List employees
* [ ] View employee
* [ ] Update employee
* [ ] Delete employee
* [ ] Search employees
* [ ] Filter employees
* [ ] Activate/deactivate employee

#### Leave Management

* [ ] Apply for leave
* [ ] List leave requests
* [ ] View leave request
* [ ] Approve leave
* [ ] Reject leave
* [ ] Calculate leave balance

#### Persistence

* [ ] Store data locally
* [ ] Load data on startup
* [ ] Add validation
* [ ] Handle errors

### Concepts

* Structs
* Relationships between structs
* Slices
* Maps
* CRUD
* Business logic
* Validation
* Dates
* JSON
* Packages
* Application architecture

---

# Learning Roadmap

The projects should be completed progressively.

```text
Expense Tracker
       │
       ▼
File Organizer
       │
       ▼
Developer Notes
       │
       ▼
Secret Manager
       │
       ▼
Employee Manager
```

Each project should become progressively more sophisticated.

---

# Development Progression

For every project, follow these stages.

## V1 — Basic

Get the core functionality working.

```text
Input
  ↓
Processing
  ↓
Output
```

Don't worry about perfect architecture.

---

## V2 — Functions & Structs

Move functionality into functions and introduce appropriate structs.

```go
type Expense struct {
    ID          int
    Amount      float64
    Category    string
    Description string
}
```

---

## V3 — CRUD

Implement:

```text
Create
Read
Update
Delete
```

---

## V4 — Persistence

Store data so it survives when the application closes.

For example:

```text
data/
└── expenses.json
```

---

## V5 — Real CLI Commands

Move from interactive menus toward commands.

Instead of:

```text
1. Add
2. List
3. Delete
```

support:

```bash
expense add 50 food "Lunch"

expense list

expense delete 3
```

---

## V6 — Validation & Error Handling

Handle situations such as:

```text
Invalid amount
Missing argument
Unknown command
File doesn't exist
Invalid employee ID
Duplicate record
```

The program should fail gracefully rather than crash.

---

## V7 — Testing

Add unit tests for important functionality.

Example:

```text
internal/
├── expense/
│   ├── expense.go
│   └── expense_test.go
```

Test:

* Adding records
* Deleting records
* Calculations
* Validation
* Searching
* Filtering

---

## V8 — Refactoring

Once the application works, reorganize it into a maintainable structure.

Example:

```text
project/
├── cmd/
├── internal/
│   ├── service/
│   ├── repository/
│   └── model/
├── data/
├── tests/
├── go.mod
└── README.md
```

Don't start with complicated architecture. **Earn the architecture as the project grows.**

---

# General Go Skills to Learn

By the end of the five projects, you should have practiced:

* [ ] Variables
* [ ] Constants
* [ ] Data types
* [ ] Arrays
* [ ] Slices
* [ ] Maps
* [ ] Structs
* [ ] Methods
* [ ] Functions
* [ ] Pointers
* [ ] Interfaces
* [ ] Error handling
* [ ] Packages
* [ ] Modules
* [ ] JSON
* [ ] File handling
* [ ] Command-line arguments
* [ ] Environment variables
* [ ] Testing
* [ ] Goroutines
* [ ] Channels
* [ ] Basic application architecture

---

# Project Rules

To get the most learning value from these projects:

1. **Don't copy the complete solution.**
2. Build the simplest version first.
3. Use Go's standard library before adding third-party packages.
4. Read Go documentation when you get stuck.
5. Write functions instead of putting everything in `main.go`.
6. Add error handling as you go.
7. Write tests after the basic functionality works.
8. Refactor only after you understand the working solution.
9. Commit your progress with Git.
10. Document what you learned from each project.

---

# Suggested Git Workflow

Example:

```bash
git init

git add .
git commit -m "initialize expense tracker"

git commit -m "add expense model"

git commit -m "implement add expense"

git commit -m "implement expense listing"

git commit -m "add JSON persistence"

git commit -m "add expense tests"
```

---

# Goal

The goal isn't simply to build five CLI applications.

The goal is to progress from:

```text
"I know some Go syntax."
```

to:

```text
"I can identify a real problem,
design a solution,
build it in Go,
handle errors,
persist data,
write tests,
and structure a maintainable application."
```

By the end of the fifth project, you should have a small portfolio of practical Go applications and a much stronger foundation for moving into **Go APIs, backend development, concurrency, and distributed systems**.
