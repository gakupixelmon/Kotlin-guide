# Operators

You might feel overwhelmed by the amount of things to memorize in this chapter. There's no need to memorize everything at once; aim to just vaguely know that they exist at first. That way, you can search for them when you need them.

## Arithmetic Operators
There is nothing in particular to be careful about other than division and remainder.
| Operator | Meaning | Differences from C/C++ / Notes |
| :---: | :--- | :--- |
| `+` | Addition | Can also be used for string concatenation |
| `-` | Subtraction | |
| `*` | Multiplication | |
| `/` | Division | **Truncated for integers** (e.g., `5 / 2` → `2`) |
| `%` | Remainder (Modulo) | |

Truncation in integer division simply means dropping the decimal part; in other words, rather than being the largest integer not exceeding the quotient (floor), it is the integer with the same sign as the quotient and the largest absolute value that does not exceed the quotient's absolute value.
As a supplementary note on the remainder, if the dividend is negative, the result will also be negative. (e.g., `-7 % 3` is `-1`)
Kotlin has a function that expresses the remainder as a positive number. (e.g., `(-7).mod(3)` is `2`. This can also be expressed as `3 + (-7 % 3)`.)
Also, when calculating the remainder with decimals, the result is `(dividend) - (divisor) × (integer part of the quotient)`. The integer part of the quotient is found simply by dropping the decimal part; in other words, rather than being the largest integer not exceeding the quotient, it is the integer with the same sign as the quotient and the largest absolute value that does not exceed the quotient's absolute value.
(e.g., `-3.14 % -1.41` becomes `-3.14 - (-1.41) × 2`, which is `-0.32`)

## Increment and Decrement
As a way to assign the next integer to `x`, like `x = x + 1`, there are increment and decrement operators.
| Operator | Meaning | Differences from C/C++ / Notes |
| :---: | :--- | :--- |
| `++` | Increment | Cannot be used with `val` variables |
| `--` | Decrement | Cannot be used with `val` variables |

Example
```kotlin
var count = 0
count++  // Same as count = count + 1
println(count) // 1

count--  // Same as count = count - 1
println(count) // 0

Comparison Operators
​A characteristic of Kotlin is the presence of === and !==.
| Operator | Meaning | Differences from C/C++ / Notes |
| :---: | :--- | :--- |
| == | Equal in value (Structural equality) | Equivalent to Java's .equals(). Normally, use this one. |
| != | Not equal in value | |
| === | Equal in reference (Referential equality) | Compares if the location in memory is the same (similar to pointer comparison in C++) |
