# Kotlin Cheatsheet
Kotlin is a modern, multi-paradigm programming language that runs on the Java Virtual Machine (JVM) and is designed to be more concise and safer than Java. A Kotlin cheat sheet is a quick reference guide that provides a concise summary of the most important Kotlin syntax and features. If you'd like to support me, please give a star to this repository.⭐🙏

![Kotlin logotype](https://github.com/alidehkhodaei/kotlin-cheatsheet/blob/add-cheatsheet/images/kotlin_logotype.jpg)

# Table of Contents


- [Introduction](#introduction)
- [Variables and Types](#variables-types)
  - [Var vs Val](#var-vs-val)
  - [Type Inference](#type-inference)
  - [Type Conversion](#type-conversion)
  - [Lazy and lateinit](#lazy-and-lateinit)
  - [Types](#types)
- [Control Flow](#control-flow)
  - [If-else](#if-else)
  - [When](#when)
  - [For loop](#for-loop)
  - [While](#while)
  - [Do while](#do-while)
  - [Break and Continue](#break-and-continue)
- [Functions](#functions)
  - [Function Declaration](#function-declaration)
  - [Function Parameters](#function-parameters)
  - [Function Return Types](#function-return-type)
  - [Lambda Expressions](#lambda-expressions)
  
## Introduction <a name="introduction"></a>
Kotlin is a modern, open-source programming language that is used for building multi-platform applications. It is concise, expressive, and powerful, with features such as null safety, extension functions, lambdas, and many others. This cheat sheet will cover some of the essential Kotlin concepts.

## Variables and Types <a name="variables-types"></a>


### Var vs Val <a name="var-vs-val"></a>
In Kotlin, variables can be declared using either the var or val keyword.

var variables are mutable, meaning their value can be changed after they are initialized.

```kotlin
var x = 5
x = 10
```
val variables, on the other hand, are immutable, meaning their value cannot be changed after they are initialized.

```kotlin
val y = 5
y = 10 // This will result in a compilation error
```

### Type Inference <a name="type-inference"></a>

Kotlin supports type inference, which means the compiler can infer the type of a variable from its initial value.

```kotlin
val x = 5 // The type of x is inferred to be Int
val y = "hello" // The type of y is inferred to be String
```

Variables in Kotlin can also be declared without an initial value, but in that case, the type must be explicitly specified:

```kotlin
var z: Double // Valid, z has no initial value
// println(z) // Invalid, z is not initialized and has no value yet
z = 3.14 // Valid, z is initialized with a value
```
### Type Conversion <a name="type-conversion"></a>

Kotlin provides several methods for converting between data types.

```kotlin
val x = "5"
val y = x.toInt() // y is now an Int with value 5

val a = 5
val b = a.toString() // b is now a String with value "5"
```

 Here are some of the most commonly used methods:

| Name | Description     | 
| :-------- | :------- | 
| toByte() | converts a value to Byte type
|toShort() | converts a value to Short type
|toInt()   | converts a value to Int type
|toLong()  | converts a value to Long type
|toFloat() | converts a value to Float type
|toDouble()| converts a value to Double type
|toChar()  | converts a value to Char type
|toString()| converts a value to String type

### Lazy and lateinit  <a name="lazy-and-lateinit"></a>

A lazy variable is initialized only when it is first accessed.

```kotlin
val myLazyVar: String by lazy {
    // Perform some expensive operation to initialize the variable
    "Hello World"
}

// The variable is not initialized until it is first accessed
println(myLazyVar) // Prints "Hello World"
```
A lateinit variable is used when you know that a variable will be initialized before it is used, but you don't want to assign an initial value at the time of declaration.

```kotlin
lateinit var myLateInitVar: String

// The variable is not initialized yet, so trying to access it will throw an exception
// println(myLateInitVar) // This line would throw a "lateinit property has not been initialized" exception

// Sometime later, the variable is initialized
myLateInitVar = "Hello World"

// Now we can access the variable without an exception
println(myLateInitVar) // Prints "Hello World"
```
### Types <a name="types"></a>
Here's a brief overview of the most commonly used types:

| Name | Description     | Example
| :-------- | :------- |:---------
Byte	| 8-bit signed integer |	val myByte: Byte = 10
Short |	16-bit signed integer	| val myShort: Short = 100
Int |	32-bit signed integer	| val myInt: Int = 1000
Long	| 64-bit signed integer	| val myLong: Long = 1000000
Float	| 32-bit floating point number	| val myFloat: Float = 3.14F
Double |	64-bit floating point number	| val myDouble: Double = 3.14159
Char	| A single Unicode character	| val myChar: Char = 'A'
String	| A sequence of characters	| val myString: String = "Hello, world!"
Boolean |	A logical value of true or false	| val myBool: Boolean = true
Array |	A collection of elements of a particular type	| val myArray: Array<Int> = arrayOf(1, 2, 3)
List	| A read-only collection that supports accessing elements by index	| val myList: List<String> = listOf("apple", "banana", "orange")
Set	| A collection that contains no duplicate elements | val mySet: Set<Int> = setOf(1, 2, 3)
Map |	A collection of key-value pairs |	val myMap: Map<String, Int> = mapOf("one" to 1, "two" to 2, "three" to 3)

## Control flow  <a name="control-flow"></a>

### If-else <a name="if-else"></a>

```kotlin
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```
### When <a name="when"></a>

```kotlin
when (value) {
    condition1 -> // Code to execute if value matches condition1
    condition2 -> // Code to execute if value matches condition2
    else -> // Code to execute if value does not match any condition
}
```
### For loop <a name="for-loop"></a>
```kotlin
for (item in collection) {
    // Code to execute for each item in collection
}
```

### While <a name="while"></a>
```kotlin  
while (condition) {
    // Code to execute as long as condition is true
}
```

### Do While <a name="do-while"></a>

```kotlin
do {
    // Code to execute at least once
} while (condition)
```

### Break and Continue <a name="break-and-continue"></a>

```kotlin
for (i in 1..10) {
    if (i == 5) {
        break // Exit loop when i is equal to 5
    }
    if (i % 2 == 0) {
        continue // Skip even numbers and continue to the next iteration
    }
    // Code to execute for each odd number between 1 and 10
}
```

## Functions <a name="functions"></a>

### Function Declaration  <a name="function-declaration"></a>

```kotlin
fun sayHello() {
    println("Hello!")
}

fun greet(name: String) {
    println("Hello, $name!")
}
```

### Function Parameters  <a name="function-parameters"></a>

  ```kotlin
  fun greet(name: String, age: Int) {
    println("Hello, $name! You are $age years old.")
}

fun greet(name: String = "Ali", age: Int = 24) {
    println("Hello, $name! You are $age years old.")
}

  ```
### Function Return Types  <a name="function-return-type"></a>

```kotlin
fun add(a: Int, b: Int): Int {
    return a + b
}

fun multiply(a: Int, b: Int) = a * b
```
### Lambda Expressions  <a name="lambda-expressions"></a>

```kotlin
val sum = { a: Int, b: Int -> a + b }

val square: (Int) -> Int = { it * it }
```
