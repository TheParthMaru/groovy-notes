# Collections in groovy

- They provide powerful data structures to store and manipulate groups of related objects.

## Lists

- Ordered collection of homogenous or heterogenous elements that can contain duplicates.
- Groovy uses the `ArrayList` implementation by default.

```groovy
// Creating a list
def list = [1,2,3,4,5]

// Accessing elements
println list[0] // 1

// Adding elements
list.add(6)
list << 7
println list // [1,2,3,4,5,6,7]

// Removing elements
list.remove(0) // removes the element at index 0

// Iterating over list
for(element in list) {
    print (element + " ") // 1 2 3
}
```
