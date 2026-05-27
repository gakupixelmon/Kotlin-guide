# Kotlin Standard Library Basics (Collections & Utils)
Kotlin’s standard library is powerful and can be used immediately without any additional installation.  
This section explains especially important topics: collections (lists and maps), string manipulation, mathematical functions, and input handling.  
### 1. List
This corresponds to std::vector in C++ and list in Python.  
In Kotlin, read-only and mutable collections are clearly separated.  
##### A. Read-only List (listOf)  
Once created, elements cannot be added, removed, or modified. This is the default choice in most cases.
```
// Immutable List
val numbers = listOf(1, 2, 3, 4, 5)

println(numbers[0])   // 1 (access is allowed)
println(numbers.size) // 5 (get size)

// numbers.add(6)     // Error! Cannot add
// numbers[0] = 10    // Error! Cannot modify
```
##### B. Mutable List (mutableListOf)
Use this only when modifications are needed later.  
```
// Mutable List
val fruits = mutableListOf("Apple", "Banana")

fruits.add("Orange")  // Add element
fruits[0] = "Peach"   // Overwrite
fruits.removeAt(1)    // Remove element (removes Banana)

println(fruits) // [Peach, Orange]
```
Note: Even if the variable itself is declared with val (fixed reference), the contents can still be modified if the object is mutable.
Questions  
What will happen when the following code is executed? Will it produce output or an error?  
Question 1: Modifying a List
```
fun main() {
    val list = listOf(10, 20, 30)
    // list.add(40) // What happens if this comment is removed?
    println(list.size)
}
Question 2:
Kotlin
fun main() {
    val numbers = mutableListOf(1, 2)
    numbers.add(3)
    numbers[0] = 99
    println(numbers)
}
```
Answers  
Question 1: Error (compile-time error)  
A list created with listOf is immutable. The add method does not exist.
Question 2: [99, 2, 3]
Since mutableListOf creates a mutable list:
Starts as 1, 2
add(3) makes it 1, 2, 3
numbers[0] = 99 replaces the first element, resulting in 99, 2, 3
### 2. Map (Associative Array)
A Map manages data as key-value pairs.
This corresponds to Python’s dict and C++’s std::map.
Pairs are created using the to keyword.
```
// Read-only map
// Uses "key" to "value" syntax
val scores = mapOf(
    "Math" to 90,
    "English" to 80,
    "Physics" to 95
)

println(scores["Math"]) // 90
// scores["Math"] = 100 // Error! Cannot modify

// Mutable map
val user = mutableMapOf(
    "id" to 1,
    "name" to "Tanaka"
)

user["name"] = "Suzuki" // Overwrite
user["age"] = 20        // Add new key
```
Question 3: Map Operations
```
fun main() {
    val dict = mapOf("A" to 1, "B" to 2)
    println(dict["B"])
}
```
Question 3 Answer: 2
dict["B"] retrieves the value 2 associated with key "B".
### 3. String Manipulation
The String class provides many useful methods.
```
val text = "Kotlin is Fun"

println(text.length)        // Number of characters: 13
println(text.uppercase())   // Convert to uppercase: "KOTLIN IS FUN"
println(text.lowercase())   // Convert to lowercase: "kotlin is fun"

// Check whether a string contains text
if (text.contains("Fun")) {
    println("Looks fun")
}

// Replace text
val newText = text.replace("Fun", "Great")
println(newText) // "Kotlin is Great"
```
### 4. Mathematical Functions (Math)
Basic mathematical functions are available in the kotlin.math package.
You can either import them manually or let your IDE auto-complete them.
```
import kotlin.math.* // Import all math functions

fun main() {
    val x = 2.0
    val y = 3.0

    println(max(x, y))  // Maximum: 3.0
    println(min(x, y))  // Minimum: 2.0
    println(sqrt(16.0)) // Square root: 4.0
    println(x.pow(3))   // Power (2³): 8.0
    
    println(PI)         // Pi: 3.14159...
}
```
### 5. Standard Input
To receive user input, use readln().
Since the input is always received as a String, you need to convert it if you want to use it as a number.
```
fun main() {
    print("Please enter your name: ")
    val name = readln() // Receive as a string
    
    print("Please enter your age: ")
    
    // Receive as a string, then convert to Int (.toInt())
    val ageString = readln()
    val age = ageString.toInt()

    println("${name}, next year you will be ${age + 1} years old.")
}
```
Questions  
What will happen when the following code is executed? Will it produce output or an error?  
Question 4: String Manipulation  
```
fun main() {
    val s = "Robot"
    println(s.uppercase())
}
```
Question 5: Input and Conversion
```
fun main() {
    // Assume the user enters "10"
    val input = "10"
    val number = input.toInt()
    println(number + 5)
}
```
Answers
Question 4: ROBOT
.uppercase() converts all characters to uppercase.
Question 5: 15
The string "10" is converted into the numeric value 10 using .toInt().
Therefore, 10 + 5 is calculated, resulting in 15.
(Without conversion, it would become string concatenation and result in "105".)
