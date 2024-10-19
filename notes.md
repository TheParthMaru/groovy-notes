# Groovy Language Notes

- Object oriented, dynamic programming language for Java platform.
- Created to simplify and enchance Java dev by providing flexible and concise syntax.
- Integrates easily with existing Java code allowing devs to use existing libraries and frameworks with concise and dynamic syntax.
- Also a scripting language where we can write quick scripts and execute it without the need of compilation.
- Provides functional programming support with closures and higher order functions.
- Groovy code gets compiled to Java bytecode, so it is compatible with JVM.

## Use cases of groovy

- Most useful scenario is when devs want to use the power of Java but need more concise and expressive code.
- Scripting and automation: Automating build task in Jenkins or Gradle.
- Build automation (gradle): Defining dependencies in `build.gradle`
- Writing unit test for test automation.
- Web deb: Building RESTful web services with Grails.
- Domail specific language (DSLs)
- Scripting in CI: Scripting Jenkins pipelines.

## Comparison with Java

![Java vs groovy table](/images/java_vs_groovy.png)

## Programming with groovy

- We can download the groovy SDK from [official download page](https://groovy.apache.org/download.html)
- Groovy scripts are created with `.groovy` extension.
- If creating a groovy class, make sure the file name and the class name is same following PascalCase.
- If creating a groovy script, the file name can be either PascalCase or snake_case.
- Execute a groovy script with the command `groovy fileName.groovy`.

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

## String interpolation

- The `$` symbol is used for string interpolation which allows us to embed variables or expression directly in a string.
- Makes it easy to concatenate string with variables without having to use the + operator.

```groovy
def name = "parth"
def age = 26

println("Hi, I am $name. I am $age years old")

// Output:
// Hi, I am parth. I am 26 years old
```

## Data types in groovy

- Groovy is a dynamic programming language but also supports static declarations with the below data types:

### Primitive data types

![Primitive data types table](images/primitive_data_types_table.png)

### Object data types

![Object data types](images/object_data_types.png)

### Collection types

![Collection data types](images/collection_data_type.png)

### Special data types

![Special data types](images/special_data_type.png)

### Primitive vs wrapper types

![Primitive vs wrapper types](images/primitive_vs_wrapper.png)

- When a variable is declared but not explicitly initialized, it generally defaults to `null`, except for primitive types that have their default values.

### How to know a data type of a variable

#### Using `getClass()`

```groovy
def a = 123
println(a.getClass()) // Output: class java.lang.Integer
```

#### Using `instanceof`

```groovy
def a = 123
println(a instanceof Byte) // false
println(a instanceof Short) // false
println(a instanceof Integer) // true
```
