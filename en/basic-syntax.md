#Basic Syntax

##Defining packages

Package specification should be at the top of the source file:

```kotlin
package my.demo

import java.util.*

// ...
```
It is not required to match directories and packages: source files can be placed arbitrarily in the file system.

See [Packages](packages.md).

##Defining functions

Function having two Int parameters with Int return type:

```kotlin
fun sum(a: Int, b: Int): Int {
    return a + b
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

Function with an expression body and inferred return type:

```kotlin
fun sum(a: Int, b: Int) = a + b
```
Target platform: JVMRunning on kotlin v. 1.1.2

Function returning no meaningful value:

```kotlin
fun printSum(a: Int, b: Int): Unit {
    println("sum of $a and $b is ${a + b}")
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

Unit return type can be omitted:

```kotlin
fun printSum(a: Int, b: Int) {
    println("sum of $a and $b is ${a + b}")
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [Functions](functions.md).

##Defining local variables

Assign-once (read-only) local variable:

```kotlin
val a: Int = 1  // immediate assignment
val b = 2   // `Int` type is inferred
val c: Int  // Type required when no initializer is provided
c = 3       // deferred assignment
```
Target platform: JVMRunning on kotlin v. 1.1.2

Mutable variable:

```kotlin
var x = 5 // `Int` type is inferred
x += 1
```
Target platform: JVMRunning on kotlin v. 1.1.2

See also [Properties And Fields](properties.md).

##Comments

Just like Java and JavaScript, Kotlin supports end-of-line and block comments.

```kotlin
// This is an end-of-line comment

/* This is a block comment
   on multiple lines. */
```
Unlike Java, block comments in Kotlin can be nested.

See [Documenting Kotlin Code](kotlin-doc.md) for information on the documentation comment syntax.

##Using string templates

```kotlin
var a = 1
// simple name in template:
val s1 = "a is $a" 
​
a = 2
// arbitrary expression in template:
val s2 = "${s1.replace("is", "was")}, but now is $a"
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [String templates](basic-types.md).

##Using conditional expressions

```kotlin
fun maxOf(a: Int, b: Int): Int {
    if (a > b) {
        return a
    } else {
        return b
    }
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

##Using if as an expression:

```kotlin
fun maxOf(a: Int, b: Int) = if (a > b) a else b
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [if-expressions](control-flow.md).

##Using nullable values and checking for null

A reference must be explicitly marked as nullable when null value is possible.

Return null if str does not hold an integer:

```kotlin
fun parseInt(str: String): Int? {
    // ...
}
```
Use a function returning nullable value:

```kotlin
fun printProduct(arg1: String, arg2: String) {
    val x = parseInt(arg1)
    val y = parseInt(arg2)
​
    // Using `x * y` yields error because they may hold nulls.
    if (x != null && y != null) {
        // x and y are automatically cast to non-nullable after null check
        println(x * y)
    }
    else {
        println("either '$arg1' or '$arg2' is not a number")
    }    
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

or

```kotlin
// ...
if (x == null) {
    println("Wrong number format in arg1: '${arg1}'")
    return
}
if (y == null) {
    println("Wrong number format in arg2: '${arg2}'")
    return
}
​
// x and y are automatically cast to non-nullable after null check
println(x * y)
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [Null-safety](null-safety.md).

##Using type checks and automatic casts

The is operator checks if an expression is an instance of a type. If an immutable local variable or property is checked for a specific type, there's no need to cast it explicitly:

```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj is String) {
        // `obj` is automatically cast to `String` in this branch
        return obj.length
    }
​
    // `obj` is still of type `Any` outside of the type-checked branch
    return null
}
```
Target platform: JVMRunning on kotlin v. 1.1.2
or

```kotlin
fun getStringLength(obj: Any): Int? {
    if (obj !is String) return null
​
    // `obj` is automatically cast to `String` in this branch
    return obj.length
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

or even

```kotlin
fun getStringLength(obj: Any): Int? {
    // `obj` is automatically cast to `String` on the right-hand side of `&&`
    if (obj is String && obj.length > 0) {
        return obj.length
    }
​
    return null
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [Classes](classes.md) and [Type casts](typecasts.md).

##Using a for loop

```kotlin
val items = listOf("apple", "banana", "kiwi")
for (item in items) {
    println(item)
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

or

```kotlin
val items = listOf("apple", "banana", "kiwi")
for (index in items.indices) {
    println("item at $index is ${items[index]}")
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See for loop.

##Using a while loop

```kotlin
val items = listOf("apple", "banana", "kiwi")
var index = 0
while (index < items.size) {
    println("item at $index is ${items[index]}")
    index++
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [while loop](control-flow.md).

##Using when expression

```kotlin
fun describe(obj: Any): String =
when (obj) {
    1          -> "One"
    "Hello"    -> "Greeting"
    is Long    -> "Long"
    !is String -> "Not a string"
    else       -> "Unknown"
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [when expression](control-flow.md).

##Using ranges

Check if a number is within a range using in operator:


val x = 10
val y = 9
if (x in 1..y+1) {
    println("fits in range")
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

Check if a number is out of range:

```kotlin
val list = listOf("a", "b", "c")
​
if (-1 !in 0..list.lastIndex) {
    println("-1 is out of range")
}
if (list.size !in list.indices) {
    println("list size is out of valid list indices range too")
}
```Target platform: JVMRunning on kotlin v. 1.1.2

Iterating over a range:

```kotlin
for (x in 1..5) {
    print(x)
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

or over a progression:

```kotlin
for (x in 1..10 step 2) {
    print(x)
}
for (x in 9 downTo 0 step 3) {
    print(x)
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [Ranges](ranges.md).

##Using collections

Iterating over a collection:

```kotlin
for (item in items) {
    println(item)
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

Checking if a collection contains an object using in operator:

```kotlin
when {
    "orange" in items -> println("juicy")
    "apple" in items -> println("apple is fine too")
}
```
Target platform: JVMRunning on kotlin v. 1.1.2

Using lambda expressions to filter and map collections:

```kotlin
fruits
.filter { it.startsWith("a") }
.sortedBy { it }
.map { it.toUpperCase() }
.forEach { println(it) }
```
Target platform: JVMRunning on kotlin v. 1.1.2

See [Higher-order functions and Lambdas](lambdas.md).