## Printing in groovy

- `println()` adds a new line after the text is printed.

```groovy
println "Hello World"
println("Hello World")

print("hello world")
```

## Comments

```groovy
// Single line comment

/*
    Multi
    Line
    Comment
*/

/**
* GroovyDoc comment
* It is used for documentation
* @param a is the first number
* @param b is the second number
* @return sum of a and b
*/
```

## Variables

- No need to explicitly specify the type as it is a dynamically typed language.
- However, we can still explicitly specify the type.

### Dynamically typed variables

```groovy
// Syntax
def variableName = value

def name = "Parth" // Dynamically typed string
def age = 26 // Dynamically typed integer
def isSingle = true // Dynamically typed boolean
def height = 6.0 // Dynamically typed BigInteger
```

### Explicitly typed variables

```groovy
// Syntax
Type variableName = value

String name = "parth" // Explicitly typed string
int age = 26 // Explicitly typed integer
boolean isSingle = true // Explicitly typed boolean
double height = 6.0 // Explicitly typed double
```

### Variable scope

- Defines accessibility/ visibility of a variable.
- _Local scope:_ Within methods or closures.
- _Instance scope:_ Defined at class level which is accessible by all methods in that class.
- _Global scope:_ Specifically in script, the variables defined outside a class or a method have global scope.

```groovy
def myFunction() {
    int age = 26 // Local variable
}

println(age) // Throw an exception MissingPropertyException as variable age is out of the scope
```

### Multiple assignments

```groovy
def (x, y, z) = [1,2,3]
println x // 1
println y // 2
println z // 3
```

### Default values

- Reference types -> null
- Primitive types -> Native default value

### Duck typing

- Provides more flexibility as compared to statically typed language like Java.

```groovy
def value = 69
value = "Oh yeah" // Re-initialized value

println value // Oh yeah
```
