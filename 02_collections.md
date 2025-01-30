# Collections in groovy

- They provide powerful data structures to store and manipulate groups of related objects.

## Lists

- Ordered collection of homogenous or heterogenous elements that can contain duplicates.
- Groovy uses the `ArrayList` implementation by default.

```groovy
// Creating a list
def list = [1,2,3,4,5]
println list.getClass() // class java.util.ArrayList

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

## Maps

- A map is an unordered collection of key-value pairs, where each key is unique.
- Groovy uses the HashMap implementation by default.

### Syntax

```groovy
// Syntax
def map = [key1: "value1", key2: "value2", key3: "value3"]
```

### Creating a map

```groovy
// Creating a map
def map = [name: "parth", age: 26] // Using key-value pairs
println map.getClass() // class java.util.LinkedHashMap

// Creating using constructor
def map2 = new HashMap()
map.put("key1", "value1")
map.put("key2", "value2")

// Creating an empty map
def map3 = [:]
```

### Accessing elements

#### Dot notation

- Works when the key is an identifier (no special chars, stars with a letter)

```groovy
def map = [name: "parth", age: 26]
println(map.name) // "parth"
```

#### Subscript or bracket notation

- Useful when key contains special chars or spaces.

```groovy
println(map["age"]) // 26
```

#### Using `get()` method

```groovy
println(map.get("name")) // parth
```

### Adding and modifying map entries

#### Using dot notation

```groovy
map.isEmployed = false
println(map) // [name:parth, age:26, isEmployed:false]
```

#### Using Subscript notation

```groovy
map["relationship status"] = "single"
println(map) // [name:parth, age:26, isEmployed:false, relationship status:single]
```

#### Using `put()` method

```groovy
map.put("industry", "IT")
println map // [name:parth, age:26, isEmployed:false, relationship status:single, industry:IT]
```

### Removing key-value

```groovy
map.remove("industry") // Also, it will return the value of the key which can be stored in a variable
println(map) // [name:parth, age:26, isEmployed:false, relationship status:single]
```

### Iterating over map

#### Iterating over keys and values using `each`

```groovy
def map = [name: "parth", age: 26, isEmployed: false, industry: "IT"]

map.each{
	key, value -> println "$key: $value"
}

/*
Output:
    name: parth
    age: 26
    isEmployed: false
    industry: IT
*/
```

#### Iterating over only keys

```groovy
map.each{
	key, value -> println key
}
```

#### Iterating over only values

```groovy
map.each{
	key, value -> println value
}
```

### Useful map methods

1. `containsKey()` - Checks if the map contains a specific key.

```groovy
def map = [name: "parth", age: 26, isEmployed: false, industry: "IT"]

println(map.containsKey("name")) // true
```

2. `containsValue()` - Checks if the map contains a specific value.

```groovy
println(map.containsValue("69")) // false
```

3. `size()` - Returns the number of key-value pairs in the map.

```groovy
println(map.size()) // 4
```

4. `isEmpty()` - Checks if the map is empty.

```groovy
println map.isEmpty()  // Output: false
```

5. `keySet()` - Returns a set of all the keys in the map.

```groovy
println(map.keySet()) // [name, age, isEmployed, industry]
```

6. `values()` - Returns a collection of all the values in the map

```groovy
println(map.values()) // [parth, 26, false, IT]
```

7. `clear()` - Removes all the entries from the map.

```groovy
map.clear()
println map  // Output: [:]
```

8. `putAll()` - Used to merge two Maps

```groovy
def map1 = [name: "parth", age: 26, isEmployed: false, industry: "IT"]
def map2 = [relationshipStatus: "single"]

map1.putAll(map2)

println map1 // [name:parth, age:26, isEmployed:false, industry:IT, relationshipStatus:single]
```



