# DAY 1: JavaScript Variables and Data Types

## Table of Contents

- [What is a Variable?](#what-is-a-variable)
- [Why Use Variables?](#why-use-variables)
- [What are Data Types?](#what-are-data-types)
- [Why Use Data Types?](#why-use-data-types)
- [Rules for Declaring Variables](#rules-for-declaring-variables)
- [`var`, `let`, and `const`](#var-let-and-const)
  - [Declare variable using var](#declare-variable-using-var)
  - [Declare variable using let](#declare-variable-using-let)
  - [Declare variable using const](#declare-variable-using-const)
- [Data Types in JavaScript](#data-types-in-javascript)
  - [1. undefined type](#1-undefined-type)
  - [2. null type](#2-null-type)
  - [3. number type](#3-number-type)
  - [4. Big Integers type](#4-big-integers-type)
  - [5. string type](#5-string-type)
  - [6. boolean type](#6-boolean-type)
  - [7. symbol type](#7-symbol-type)
  - [8. object type](#8-object-type)
- [Data Type Conversion](#data-type-conversion)
  - [STRING TO NUMBER](#string-to-number)
  - [STRING TO BOOLEAN](#string-to-boolean)
  - [NUMBER TO STRING](#number-to-string)
  - [NUMBER TO BOOLEAN](#number-to-boolean)
  - [BOOLEAN TO STRING](#boolean-to-string)

## What is a Variable?

A variable is a named storage that programmers can use to store data and retrieve it later using the variable name.

## Why Use Variables?

1. Variable can store some information.
2. We can use that information later.
3. We can change that information later.

## What are Data Types?

Data types specify the kind of data that can be stored and manipulated within a program. JavaScript supports various data types, each serving a unique purpose.

## Why Use Data Types?

1. The data is stored appropriately for its type.
2. Data is retrieved correctly according to its type.
3. Data is manipulated in ways suitable for its type.

## Rules for Declaring Variables

1. Variable names must start with a letter, underscore (\_), or dollar sign ($).
2. Variable names cannot start with a number.
3. Variable names are case-sensitive.
4. Reserved words (like JavaScript keywords) cannot be used as variable names.

```javascript
// 1. You cannot start with number
var value1 = 10;
console.log(value1);

// 2. You can use only underscore _ or dollar symbol $
var first_name = "Manoj";
var _lastname = "Kumar";
console.log(first_name + " " + _lastname);

var first$name = "Rohit";
var $firstname = "Jain";
console.log(first$name + " " + $firstname);

// Convention 1. Use camelCase writing
var firstName = "camelCase";
console.log(firstName);

// Convention 2. Use snake_case writing
var first_name = "snake_case";
console.log(first_name);
```

## `var`, `let`, and `const`

### Declare variable using var

```javascript
// Declare a variable
var firstName = "MANOJ KUMAR";

// Use a variable
console.log(firstName);

// Change value
firstName = "BCA PATHSHALA";
console.log(firstName);

/*
Expected Output:
MANOJ KUMAR
BCA PATHSHALA
*/
```

### Declare variable using let

```javascript
// Declare a variable
let value = 10;

// Use a variable
console.log(value);

// Change value
value = 11;
console.log(value);

/*
Expected Output:
10
11
*/
```

### Declare variable using const

```javascript
// Declare a variable
const value = 10;

// Use a variable
console.log(value);

/*
Expected Output:
10
*/
```

## Data Types in JavaScript

JavaScript is a dynamically typed language, meaning that a variable isn’t associated with a specific type. In other words, a variable can hold a value of different types. For example:

> To determine the current type of the value stored in a variable, you use the `typeof `operator

```javascript
let x = 120;
console.log(typeof x); // "number"

x = false;
console.log(typeof x); // "boolean"

x = "Hi";
console.log(typeof x); // "string"
```

### 1. undefined type

It has only one value `null`

```javascript
let x;
console.log(x); // undefined
console.log(typeof x); // undefined
```

**Note 1:** When a variable is declared but not initialized, it defaults to undefined.

### 2. null type

It has only one value `null`

```javascript
let x = null;
console.log(typeof x); // object

console.log(null == undefined); // true
```

**Note 1:** The `typeof null` returns `object` is a known bug in JavaScript. A proposal to fix was rejected due to the potential to break many existing sites.

**Note 2:** JavaScript defines that `null` is equal to `undefined`

### 3. number type

JavaScript uses the number type to represent both integer and floating-point numbers.

```javascript
let num = 100; // interpreted as an integer 100
let price = 12.5; // interpreted as floating 12.5
let discount = 0.05; // interpreted as floating 0.05
let offer = 200.0; // interpreted as an integer 200
```

### 4. Big Integers type

To make a `BigInt`, you append n to the end of the number literal

```javascript
let bigInt = 9007199254740991n;
// OR
let bigInt = BigInt(9007199254740991);
```

### 5. string type

A string that begins with a double quote must end with a double quote, and a string that begins with a single quote must also end with a single quote. For example:

```javascript
let greeting = "Hi";
let message = "Bye";
```

### 6. boolean type

The boolean type has two literal values: `true` and `false` in lowercase.

```javascript
let inProgress = true;
let completed = false;

console.log(typeof completed); // boolean

// Important values to know about falsy and truely value
console.log(Boolean("Hi")); // true
console.log(Boolean("")); // false

console.log(Boolean(20)); // true
console.log(Boolean(Infinity)); // true
console.log(Boolean(0)); // false

console.log(Boolean({ foo: 100 })); // true on non-empty object
console.log(Boolean(null)); // false
```

### 7. symbol type

The Symbol function creates a new unique value every time you call it.

```javascript
console.log(Symbol() == Symbol()); // false
```

### 8. object type

In JavaScript, an object is a collection of properties, where each property is defined as a key-value pair.

```javascript
// Defines an empty object
let obj = {};

// Defines the person object with two properties: firstName and lastName.
let person = {
  firstName: "John",
  lastName: "Doe",
};
```

## Data Type Conversion

**Warning:** Whenever you are doing type conversion, check both value and type.

### STRING TO NUMBER

```javascript
//* EXAMPLE 1 (NaN)
let fullName = "MANOJ";
console.log("Type: ", typeof fullName, " Value: ", fullName);
// OUTPUT: Type:  string  Value:  MANOJ

let num = Number(fullName);
console.log("Type: ", typeof num, " Value: ", num);
// OUTPUT: Type:  number  Value:  NaN

//* EXAMPLE 2 (Integer)
let str1 = "123";
console.log("Type: ", typeof str1, " Value: ", str1);
// OUTPUT: Type:  string  Value:  123

let num1 = Number(str1);
console.log("Type: ", typeof num1, " Value: ", num1);
// OUTPUT: Type:  number  Value:  123
```

### STRING TO BOOLEAN

```javascript
//* EXAMPLE 1 (true)
let str2 = "123";
console.log("Type: ", typeof str2, " Value: ", str2);
// OUTPUT: Type:  string  Value:  123

let flag1 = Boolean(str2);
console.log("Type: ", typeof flag1, " Value: ", flag1);
// OUTPUT: Type:  boolean  Value:  true

//* EXAMPLE 1 (false)
let str3 = "";
console.log("Type: ", typeof str3, " Value: ", str3);
// OUTPUT: Type:  string  Value:

let flag2 = Boolean(str3);
console.log("Type: ", typeof flag2, " Value: ", flag2);
// OUTPUT: Type:  boolean  Value:  false
```

### NUMBER TO STRING

```javascript
//* EXAMPLE 1
let count1 = 786;
console.log("Type: ", typeof count1, " Value: ", count1);
// OUTPUT: Type:  number  Value:  786

let word1 = String(count1);
console.log("Type: ", typeof word1, " Value: ", word1);
// OUTPUT: Type:  string  Value:  786
```

### NUMBER TO BOOLEAN

```javascript
//* EXAMPLE 1 (false)
let count2 = NaN;
console.log("Type: ", typeof count2, " Value: ", count2);
// OUTPUT: Type:  number  Value:  NaN

let word2 = Boolean(count2);
console.log("Type: ", typeof word2, " Value: ", word2);
// OUTPUT: Type:  boolean  Value:  false

//* EXAMPLE 2 (false)
let count3 = 0;
console.log("Type: ", typeof count3, " Value: ", count3);
// OUTPUT: Type:  number  Value:  0

let word3 = Boolean(count3);
console.log("Type: ", typeof word3, " Value: ", word3);
// OUTPUT: Type:  boolean  Value:  false

//* EXAMPLE 3 (true)
let count4 = 7867;
console.log("Type: ", typeof count4, " Value: ", count4);
// OUTPUT: Type:  number  Value:  7867

let word4 = Boolean(count4);
console.log("Type: ", typeof word4, " Value: ", word4);
// OUTPUT: Type:  boolean  Value:  true
```

### BOOLEAN TO STRING

```javascript
//* EXAMPLE 1 (false->false)
let flag5 = false;
console.log("Type: ", typeof flag5, " Value: ", flag5);
// OUTPUT: Type:  boolean  Value:  false

let str4 = String(flag5);
console.log("Type: ", typeof str4, " Value: ", str4);
// OUTPUT: Type:  string  Value:  false
```
