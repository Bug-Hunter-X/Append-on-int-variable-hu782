# Append on int variable
This bug demonstrates an attempt to append to an integer variable in Go, which is invalid. Go's append function only works with slices.

## Bug
The `bug.go` file contains the following code:
```go
func main() {
    var x int
    fmt.Println(x)
    x = append(x,1)
}
```
This code attempts to append the integer 1 to the integer variable `x`. This is a type error because `append` works on slices, not integers.

## Solution
The `bugSolution.go` file provides a corrected version:
```go
func main() {
    var x []int
    fmt.Println(x)
    x = append(x, 1)
    fmt.Println(x)
}
```
In this corrected version, `x` is declared as a slice of integers (`[]int`), which allows the use of the `append` function.