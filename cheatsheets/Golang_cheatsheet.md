# Golang Cheatsheet

## Introduction

Golang (or Go) is an open-source programming language developed by Google. Here are some of its key features and benefits:

- Statically typed, compiled language
- Simplicity - easy to learn with a small set of keywords
- Fast compile times
- Built-in concurrency features (goroutines, channels)
- Garbage collected 
- Excellent community support

Go is well-suited for:

- Building fast, efficient networked services and microservices
- Cloud-native development
- Command line tools and utilities
- Web development (with frameworks like Gin)

Compared to other languages, Go provides faster development cycles, better performance, built-in concurrency, and portability across platforms. It's a great alternative to C, C++, Java or Python for many use cases.

## Getting Started

Here are some free resources to learn Go:

- [Official Go Tour](https://tour.golang.org/) - Interactive introduction tour
- [Official Documentation](https://golang.org/doc/) - Complete language docs
- [Go By Example](https://gobyexample.com/) - Handy code examples

Paid courses:

- [Ultimate Go Programming](https://www.udemy.com/course/ultimate-go/) on Udemy
- [Learn How To Code: Google's Go (golang) Programming Language](https://www.udemy.com/course/learn-how-to-code/) on Udemy

## Syntax Basics

- Go is a compiled, statically-typed language with syntax similar to C
- File extensions: `.go` 
- Code is organized into `packages` 
- Semi-colons optional (added automatically)
- Curly braces required for grouping

### Variables

Declare variables with `var` keyword:

```go
var name string = "John"
var age int = 25
```

Other options:

```go
name := "John" //shorthand declaration
const PI float64 = 3.14 //constant
```

### Data Types

- `bool` 
- `string`
- `int` / `int8` / `int16` / `int32` / `int64` 
- `uint` / `uint8` / `uint16` / `uint32` / `uint64`  
- `byte` - alias for `uint8`
- `rune` - alias for `int32`, represents Unicode code point
- `float32` / `float64`
- `complex64` / `complex128`

### Functions

```go
func add(x int, y int) int {
  return x + y
}
```

- Arguments and return types required
- Multiple return values allowed

### Control Flow

```go
if x > 10 {
  // do something
} else if x < 5 {
  // something else
} else {
  // fallback
}

for i := 0; i < 5; i++ {
  // loop 5 times
}

switch color {
  case "red": 
     // do something
  case "blue":
     // do something else
  default:
     // fallback
}
```

### Pointers

```go 
x := 10
p := &x // p points to x

*p = 20 //dereference p to change x
```

### Arrays

```go
var nums [5]int //fixed length

countries := [2]string{"USA", "Canada"} 

stdents := [...]string{"John", "Mary"} //determines length
```

- Use `len` function to get length
- Access with `myArray[index]` syntax 

### Slices (Dynamic Arrays)

```go
nums := []int{1, 2, 3} //slice - dynamic length

nums = append(nums, 4) //add element

nums = nums[1:] //slice from index 1 to end 
```

### Maps (Key-Value Store)

```go
lookup := make(map[string]int)

lookup["goku"] = 9001

powerLevel := lookup["goku"]
``` 

- Built-in hash table implementation
- Use `make()` to create map
- Add with `name[key] = val`
- Get with `val := name[key]`
- Check for presence with `val, ok := name[key]`
- Delete key with `delete(name, key)`

### Structs (Custom Data Types) 

```go
type User struct {
  ID        int
  FirstName string
  LastName  string
  Email     string
}

var u User 
u.ID = 1
u.FirstName = "John"
```

### Interfaces

```go
type Shape interface {
  Area() float64
}

type Circle struct {
  x, y, radius float64
}

func (c *Circle) Area() float64 {
  return math.Pi * c.radius * c.radius
}

func getArea(s Shape) float64 {
  return s.Area()
}

c := Circle{x: 0, y: 0, radius: 5}
getArea(&c) 
```

- Interface defines a set of methods signature
- Types implement interfaces by implementing interface methods
- Interfaces allow for abstraction and loose coupling

## Concurrency in Go

Go makes writing concurrent code easy with goroutines and channels.

### Goroutines 

```go
func doWork(ch chan string) {
  ch <- "Work done" //send message
}

ch := make(chan string)
go doWork(ch) //run asynchronously
msg := <- ch //receive message
```

- Functions run concurrently when invoked with `go`
- Lightweight "threads" managed by Go runtime

### Channels

```go 
ch := make(chan int) 

ch <- 10 //send
x := <- ch //receive

close(ch) //close channel
```

- Typed conduits for communication between goroutines
- Send/receive data with channel operators `<-` and `->`

## Packages and Imports

- Code organized into packages 
- `package main` - executable package
- Import packages with `import "pkg"` 
- Dot imports `import . "pkg"`
- Aliasing `import f "fmt"`

## Project Structure

```
./project
|- main.go  
|- go.mod
|- pkg/
   |- helpers.go
|- internal/
   |- handlers.go
```

- `main.go` contains `package main`
- Libraries and helpers in `pkg` and `internal` folders
- Minimal dependencies and clean architecture

## Testing

```go
func TestAdd(t *testing.T) {

  expected := 10
  actual := Add(5, 5)

  if actual != expected {
    t.Errorf("Expected %d but got %d", expected, actual) 
  }
}
```

- Test files end with `_test.go`
- Use `go test` to run tests 
- `testing` pkg provides framework
- Test table-driven tests also common

## Debugging

- Use `fmt.Println()` to log/print output
- `go build` flags:
  - `-race` detect data race conditions
  - `-gcflags "-N -l"` disable optimizations and inlining
- Delve debugger `dlv debug ./program`
- VSCode Go extension

## Deployment

- `go build` compiles executable
- `go install` compiles and installs into `GOBIN`
- Cross-compile with `GOOS` and `GOARCH` 
  - Ex: `GOOS=linux GOARCH=amd64 go build`
- Dockerize apps easily

## Best Practices 

- Use `gofmt`/`goimports` for formatting
- Group related code into packages 
- Use lower-case abbreviated names 
- Use PascalCase for exportable identifiers
- Comment documentation above functions/structs 
- Error handling - return errors, don't panic/exit
- Favor composition over inheritance 
- Avoid globals where possible

## Common Mistakes

- Forgetting to handle errors
- Goroutine leaks - don't start goroutines without waiting on them
- Array/slice out of bounds
- Misusing reference and values (pointers)
- Poorly structured code/packages
- Uncontrolled goroutine access to shared memory

## Resources

- [Go By Example](https://gobyexample.com/)
- [An Introduction to Programming in Go](https://www.golang-book.com/)
- [Effective Go](https://golang.org/doc/effective_go.html)
- [Go Bootcamp Course](http://www.golangbootcamp.com/)
- [Golang Tutorial](https://golangbot.com/learn-golang-series/)
