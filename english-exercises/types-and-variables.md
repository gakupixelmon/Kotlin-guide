# Hello World!

Most programming textbooks begin by displaying **Hello World**.

Click **New Project**, choose any name you like, and keep the default location.  
A Git repository is used to track changes in your program, but it is not necessary for learning purposes.

For this tutorial, we will use IntelliJ as the build system unless otherwise specified.

For the JDK, select **Download JDK** from the dropdown menu on the right.  
Choose version **21**, and select **Amazon Corretto** as the vendor (any vendor is fine).  
You can keep the default installation location.

Uncheck **Add sample code**.

If a message such as “Free trial” appears, close it by clicking the **×** button near the top where it says “Trial Version”.

On the left side, find the **src** folder under “Project.”  
Right-click it and select:

New → Kotlin Class/File

Choose any name, select **File**, and press Enter.

---

## Problem 1

① `fun` is used to define a function.  
(For now, ignore return types and parameters.)

In programming, a function is a collection of instructions grouped together to perform a specific task.  
```
fun functionName(parameter1, parameter2, …) : ReturnType { }
```

② Every Kotlin program starts from a function named `main`.  
The `main` function does not require parameters or a return value, so we write it as: ```main()```  
  
③ The `print` function is used like this: ```print(something)```  
If you want to display `"abc"`, then *something* should be `"abc"`.

Change the `???` parts in the code below so that it prints:

Hello World!

Copy and paste the code below. After replacing `???`, click the green triangle next to `fun` to run the program.  
```
fun ???(){
???
}
```

# Variables and Types
```
fun main(){
val a = 100
var b = 100
b = 200
}
```
In Kotlin, there are two ways to declare variables.

① A variable whose value cannot be changed after it is assigned.  
Write `val` before the variable name.  
(`val` stands for value.)

② A variable whose value can be changed after assignment.  
Write `var` before the variable name.  
(`var` stands for variation.)

If you try to assign a different value to a `val` variable later, an error will occur.

Since using `val` helps prevent bugs, you should use `val` whenever possible.

Variables can also store strings.  
For example, `"Hello, World!"` is a string.  
Strings are surrounded by double quotation marks `" "`.

In Python and JavaScript, strings can also use single quotes `' '`,  
but in Kotlin, only double quotes are used for strings.

`val` and `var` function as keywords, similar to `fun`.

There are also words like `Int` and `String`.  
These are used to declare types.

- Integers use the `Int` type.
- Strings use the `String` type.

Below is a table of common types:

| 32-bit Integer | 64-bit Integer | 32-bit Decimal | 64-bit Decimal | Character (single) | String |
|---------------|---------------|---------------|---------------|--------------------|--------|
| Int | Long | Float | Double | Char | String |

There are many more types, so feel free to research them on your own.

The part `: ReturnType` after a function’s parentheses refers to types like `Int` or `String`.  
We will discuss return values more when learning about functions.

When creating a variable, you can explicitly specify its type:
```val a : String = “abc123”```  
However, Kotlin can automatically infer the type, so writing it is often unnecessary.

In other languages:
- Python also performs type inference.
- C requires explicit type declarations.

Requiring types has advantages — programs can run faster and are suitable even for simple computers.

---

## Problem 2

If you pass a variable into `print()`, it displays the value of that variable.

Create a variable named `five`, and use `print(five)` to display the number `5`.  
```
fun main(){
}
```


# Answers

## Problem 1
```
fun main(){
print(“Hello, World!”)
}
```

## Problem 2
```
fun main(){
val five = 5
print(five)
}
```
