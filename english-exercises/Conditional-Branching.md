# Conditional Branching

Kotlin's conditional branching is similar to C or Python, but it comes with more powerful and safer features (such as being able to be **treated as expressions**).

This document will carefully explain everything from the basic `if` to `when`, which is one of Kotlin's most powerful syntactic constructs.

---

## 1. if Expression

The basic syntax is the same as C or Java, but the biggest feature of Kotlin's `if` is that it can "return a value".

### Basic Syntax
It is exactly the same as C/C++.

```kotlin
var a = 10
var b = 20

if (a > b) {
    println("a is larger")
} else {
    println("b is larger")
}

[Important] if as an Expression (Returning a value)
This is a major feature of Kotlin.
The "ternary operator (a > b) ? a : b" (an operator that evaluates to a if a>b, otherwise b) found in C does not exist in Kotlin. Instead, you use if to assign a value directly to a variable.

```
val a = 10
val b = 20

// Assign the result of if directly to the variable max
// The last evaluated value becomes the "return value"
val max = if (a > b) {
    println("Selected a")
    a // This goes into max
} else {
    println("Selected b")
    b // This goes into max
}

println("The maximum value is $max")
```

2. when Expression
It is equivalent to the switch statement in C/C++, but is far more functional.
You do not need to write break statements. It automatically exits once a condition is matched.

Basic Syntax (Matching Values)
```
val x = 1

when (x) {
    1 -> println("x is 1")
    2 -> println("x is 2")
    else -> { // Equivalent to default in switch
        println("x is neither 1 nor 2")
    }
}
```

Grouping Multiple Conditions
By separating with a comma ,, you can write multiple conditions on a single line.
```
val x = 1

when (x) {
    0, 1 -> println("It is 0 or 1")
    else -> println("It is something else")
}
```
[Powerful] Branching by Range or Type
You can use not only constants but also ranges (in) and type checks (is). This is the decisive difference from switch.
```
val score = 85

when (score) {
    in 0..59 -> println("Failing grade")       // 0 to 59 inclusive
    in 60..79 -> println("Pass")               // 60 to 79 inclusive
    in 80..100 -> println("Excellent!")        // 80 to 100 inclusive
    else -> println("Invalid score")
}
```

[Important] when as an Expression (Returning a value)
Similar to if, you can assign the result of when to a variable.
```
val color = "Red"

val message = when (color) {
    "Red" -> "Stop"
    "Yellow" -> "Caution"
    "Green" -> "Go"
    else -> "Out of order" // else is mandatory when used as an expression
}

println(message) // Prints "Stop"
```

3. Smart Casts
If you use is (type check) inside a conditional branch, Kotlin automatically casts (type-converts) the variable to that type.
```
val x: Any = "Hello" // Any is the parent of "all types" (similar to void* in C, but safe)

if (x is String) {
    // Inside this block, x is automatically treated as a String
    println(x.length) // You can use .length!
}
```

###Gemini の回答
Markdown
# Conditional Branching

Kotlin's conditional branching is similar to C or Python, but it comes with more powerful and safer features (such as being able to be **treated as expressions**).

This document will carefully explain everything from the basic `if` to `when`, which is one of Kotlin's most powerful syntactic constructs.

---

## 1. if Expression

The basic syntax is the same as C or Java, but the biggest feature of Kotlin's `if` is that it can "return a value".

### Basic Syntax
It is exactly the same as C/C++.

```kotlin
var a = 10
var b = 20

if (a > b) {
    println("a is larger")
} else {
    println("b is larger")
}
[Important] if as an Expression (Returning a value)
This is a major feature of Kotlin.
The "ternary operator (a > b) ? a : b" (an operator that evaluates to a if a>b, otherwise b) found in C does not exist in Kotlin. Instead, you use if to assign a value directly to a variable.

Kotlin
val a = 10
val b = 20

// Assign the result of if directly to the variable max
// The last evaluated value becomes the "return value"
val max = if (a > b) {
    println("Selected a")
    a // This goes into max
} else {
    println("Selected b")
    b // This goes into max
}

println("The maximum value is $max")
2. when Expression
It is equivalent to the switch statement in C/C++, but is far more functional.
You do not need to write break statements. It automatically exits once a condition is matched.

Basic Syntax (Matching Values)

Kotlin
val x = 1

when (x) {
    1 -> println("x is 1")
    2 -> println("x is 2")
    else -> { // Equivalent to default in switch
        println("x is neither 1 nor 2")
    }
}
Grouping Multiple Conditions
By separating with a comma ,, you can write multiple conditions on a single line.

Kotlin
val x = 1

when (x) {
    0, 1 -> println("It is 0 or 1")
    else -> println("It is something else")
}
[Powerful] Branching by Range or Type
You can use not only constants but also ranges (in) and type checks (is). This is the decisive difference from switch.

Kotlin
val score = 85

when (score) {
    in 0..59 -> println("Failing grade")       // 0 to 59 inclusive
    in 60..79 -> println("Pass")               // 60 to 79 inclusive
    in 80..100 -> println("Excellent!")        // 80 to 100 inclusive
    else -> println("Invalid score")
}
[Important] when as an Expression (Returning a value)
Similar to if, you can assign the result of when to a variable.

Kotlin
val color = "Red"

val message = when (color) {
    "Red" -> "Stop"
    "Yellow" -> "Caution"
    "Green" -> "Go"
    else -> "Out of order" // else is mandatory when used as an expression
}

println(message) // Prints "Stop"
3. Smart Casts
If you use is (type check) inside a conditional branch, Kotlin automatically casts (type-converts) the variable to that type.

Kotlin
val x: Any = "Hello" // Any is the parent of "all types" (similar to void* in C, but safe)

if (x is String) {
    // Inside this block, x is automatically treated as a String
    println(x.length) // You can use .length!
}

## Exercises
Predict what will be printed to the console when the following code is executed.

Problem 1
```
fun main() {
    val a = 5
    val b = 10
    
    // Put the result of if into a variable
    val result = if (a < b) "Small" else "Big"
    
    println(result)
}
```

Problem 2
```
fun main() {
    val x = 2
    
    when (x) {
        1 -> println("One")
        2 -> println("Two")
        3 -> println("Three")
        else -> println("Other")
    }
}
```

Problem 3
```
fun main() {
    val y = 15
    
    when (y) {
        in 1..10 -> println("Low")
        in 11..20 -> println("Middle")
        else -> println("High")
    }
}
```

Problem 4
```
fun main() {
    val signal = "Blue"
    
    // Put the result of when into the variable action
    val action = when (signal) {
        "Red" -> "Stop"
        "Yellow" -> "Caution"
        else -> "Go"
    }
    
    println(action)
}
```

Problem 5
```
fun main() {
    val obj: Any = 100 // Put Int type data in
    
    when (obj) {
        is String -> println("It is a String")
        is Int -> println("It is an Integer")
        else -> println("Unknown")
    }
}
```

Answers
Problem 1: Small Since a (5) < b (10) is true, "Small" in the first block is assigned to result.

Problem 2: Two Since x is 2, the line 2 -> ... is executed. No break is needed.

Problem 3: Middle
Since 15 is included in the 11..20 range, the line in 11..20 matches.

Problem 4: Go
signal is "Blue", but since "Blue" is not among the conditions, it proceeds to else, and "Go" is returned.

Problem 5: It is an Integer
obj contains 100 (Int). The type check is Int succeeds, and that line is executed.
