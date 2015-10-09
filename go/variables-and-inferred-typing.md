The var statement declared a list of variables with the type declared last.

```go
var(
	name string
	age int
	location string
)
```

Or even

```go
var(
	name, location string
	age int
)
```

Variable can also be declared one by one

```go
var name string
var age int
var location string
```

A var declaration can include initializers, one per variable

```go
var(
	name string = "Mayra"
	age int = 27
	location string = "MTY"
)
```

If an initializer is present, the type can be omitted, the variable will take the type of the initializer (*inferred typing*)

```go
var(
	name = "Mayra"
	age = 27
	location = "MTY"
)
```

You can also initialize variables on the same line:

```go
var(
	name, location, age = "Mayra", 27, "MTY"
)
```

Inside a function, the `:=` short assignment statement can be used in place of var declaration with implicit type

```go
func main(){
	name, location := "Mayra", "MTY"
	age := 32
	fmt.Printf("%s (%d) of %s", name, age, location)
}