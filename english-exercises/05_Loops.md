## Kotlin Essential Syntax: Loops
​This section explains "loops" used to write programs efficiently. Note that the concept is slightly different from for loops in languages like C/C++.  
### ​1. Loops
​In Kotlin, a for loop is written to iterate through a "Range" or "Collection" using an iterator. It does not use the C-style syntax like for(int i=0; i<10; i++).
#### ​A. Repeating a Specific Number of Times (.. and until)  
​This is the most common pattern.
```
// From 1 to 5 (1, 2, 3, 4, 5)
// ".." is inclusive
for (i in 1..5) {
    println(i)
}

// From 0 to 4 (0, 1, 2, 3, 4)
// "until" is exclusive. Often used for array indices.
for (i in 0 until 5) {
    println(i)
}

```

#### B. Reverse Order and Steps (downTo, step)
```
// From 10 down to 0, decreasing by 2 (10, 8, 6, 4, 2, 0)
for (i in 10 downTo 0 step 2) {
    println("Count: $i")
}
```

#### C. Iterating Through a List
​This is the same as the range-based for loop in C++ (for(auto x : list)) or Python (for x in list:).
```
val robots = listOf("Drone", "Arm", "Rover")

for (robot in robots) {
    println("Robot name: $robot")
}

// If you also need the index (position)
for ((index, value) in robots.withIndex()) {
    println("Robot at index $index: $value")
}

```
#### D. While Loops
​This is exactly the same as in C/C++.
```
var x = 5
while (x > 0) {
    println(x)
    x--
}
```
### Practice Problems
​Predict what will be displayed on the console when the following code is executed.
#### ​Question 1: Loop Range
```
fun main() {
    // Since it's "0 until 3", is 3 included or excluded?
    for (i in 0 until 3) {
        print(i)
    }
}

```

#### Question 2: Step Execution
```
fun main() {
    var sum = 0
    // Adds 1, 3, and 5
    for (i in 1..5 step 2) {
        sum += i
    }
    println(sum)
}

```
### Answers
​#### Question 1: 012
​Since until means "exclusive", 3 is not included. It is commonly used when iterating up to the size of an array.
​#### Question 2: 9  
​1..5 step 2 results in 1, 3, and 5. 1 + 3 + 5 = 9.
