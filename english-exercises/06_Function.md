##Function Definitions (Functions)
​Functions are defined using the fun keyword. In Kotlin, functions can also be written as "expressions," allowing them to be kept concise.
​#### A. Basic Functions
​You must specify the parameter types and the return type. As shown below, main is also a function.  
```
// fun functionName(parameterName: Type): ReturnType { ... }
fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val result = add(10, 20)
    println(result)
}
```
#### B. Single-Expression Functions
​This is an important point. When a function body consists of just a single expression that returns a value, you can omit the { } curly braces and the return keyword by using the = assignment operator. This style is highly preferred in Kotlin.
```
// This has the exact same meaning as the add function above
fun addSimple(a: Int, b: Int): Int = a + b

// Since type inference works here, you can even omit the return type
fun multiply(a: Int, b: Int) = a * b
```
#### C. Named Arguments and Default Arguments
​You can call functions using convenient features similar to Python.
```
// Setting a default value for the message parameter
fun greet(name: String, message: String = "Hello") {
    println("$message, $name!")
}

fun main() {
    greet("Tanaka")                  // Hello, Tanaka!
    greet("Suzuki", "Good morning")  // Good morning, Suzuki!
    
    // You can also pass arguments by specifying their names in any order
    greet(message = "Hi", name = "Sato") 
```

## Qestion
Predict what will be displayed on the console when you run the following code blocks.
### ​Question 1: Single-Expression Functions
```
// Does this function work correctly? If so, what is the result?
fun square(x: Int) = x * x

fun main() {
    println(square(4))
}
```
### Question 2: Default Arguments
```
fun power(base: Int, exponent: Int = 2): Int {
    // Math.pow uses Double, so we use a simple loop calculation here instead
    var result = 1
    for (i in 1..exponent) {
        result *= base
    }
    return result
}

fun main() {
    println(power(3)) // Omitting the second argument
}
```
## Answers
​### Question 1: 16
​It works correctly. The : Int return type in fun square(x: Int): Int = x * x is omitted thanks to type inference. The calculation is 4 \times 4 = 16.
### ​Question 2: 9
​The default value for exponent is set to 2. Since it was omitted in the function call, it calculates 3 to the power of 2 (3^2), resulting in 9.
