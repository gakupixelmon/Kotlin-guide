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
