## Day 7: Objects in JavaScript

Welcome to Day 7 of JavaScript Basics! Today, we'll be focusing on objects in JavaScript. This includes object creation, object methods, nested objects, the this keyword, and object iteration.

## Table of Contents

1. [Activity 1: Object Creation and Access](#activity-1-object-creation-and-access)
   - Task 1: Create an object representing a book with properties like title, author, and year, and log the object to the console.
   - Task 2: Access and log the title and author properties of the book object.
2. [Activity 2: Object Methods](#activity-2-object-methods)
   - Task 3: Add a method to the book object that returns a string with the book’s title and author, and log the result of calling this method.
   - Task 4: Add a method to the book object that takes a parameter (year) and updates the book’s year property, then log the updated object.
3. [Activity 3: Nested Objects](#activity-3-nested-objects)
   - Task 5: Create a nested object representing a library with properties like name and books (an array of book objects), and log the library object to the console.
   - Task 6: Access and log the name of the library and the titles of all the books in the library.
4. [Activity 4: The `this` Keyword](#activity-4-the-this-keyword)
   - Task 7: Add a method to the book object that uses the `this` keyword to return a string with the book’s title and year, and log the result of calling this method.
5. [Activity 5: Object Iteration](#activity-5-object-iteration)
   - Task 8: Use a `for...in` loop to iterate over the properties of the book object and log each property and its value.
   - Task 9: Use `Object.keys(obj)` and `Object.values(obj)` methods to log all the keys and values of the book object.
6. [Feature Request](#feature-request)
   - Book Object Script
   - Library Object Script
   - Object Iteration Script
7. [Achievements](#achievements)

## Activity 1: Object Creation and Access

**Task 1:** Create an object representing a book with properties like title, author, and year, and log the object to the console.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

console.log(book);
// Output: { title: 'Chai Aur Code', author: 'HC', year: 2024 }
```

**Task 2:** Access and log the title and author properties of the book object.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

console.log(book.title); // Output: Chai Aur Code
console.log(book.author); // Output: HC
```

## Activity 2: Object Methods

**Task 3:** Add a method to the book object that returns a string with the book’s title and author, and log the result of calling this method.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

book.getInfo = function () {
  return `${this.title} by ${this.author}`;
};

console.log(book.getInfo());
// Output: Chai Aur Code by HC
```

**Task 4:** Add a method to the book object that takes a parameter (year) and updates the book’s year property, then log the updated object.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

book.getInfo = function () {
  return `${this.title} by ${this.author}`;
};

book.updateYear = function (newYear) {
  this.year = newYear;
};
book.updateYear(2020);

console.log(book);
/*
Output:
{
  title: 'Chai Aur Code',
  author: 'HC',
  year: 2020,
  getInfo: [Function (anonymous)],
  updateYear: [Function (anonymous)]
}
*/
```

## Activity 3: Nested Objects

**Task 5:** Create a nested object representing a library with properties like name and books (an array of book objects), and log the library object to the console.

```javascript
let library = {
  name: "City Library",
  books: [
    { title: "Console Busters", author: "MJ", year: 2024 },
    { title: "Chai Aur Code", author: "HC", year: 2024 },
  ],
};

console.log(library);
/*
Output:
{
  name: 'City Library',
  books: [
    { title: 'Console Busters', author: 'MJ', year: 2024 },
    { title: 'Chai Aur Code', author: 'HC', year: 2024 }
  ]
}
*/
```

**Task 6:** Access and log the name of the library and the titles of all the books in the library.

```javascript
let library = {
  name: "City Library",
  books: [
    { title: "Console Busters", author: "MJ", year: 2024 },
    { title: "Chai Aur Code", author: "HC", year: 2024 },
  ],
};

console.log(library.name); // Output: City Library
library.books.forEach((book) => {
  console.log(book.title);
});
// Output:
// Console Busters
// Chai Aur Code
```

## Activity 4: The `this` Keyword

**Task 7:** Add a method to the book object that uses the `this` keyword to return a string with the book’s title and year, and log the result of calling this method.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

book.getTitleAndYear = function () {
  return `${this.title} (${this.year})`;
};

console.log(book.getTitleAndYear());
// Output: Chai Aur Code (2024)
```

## Activity 5: Object Iteration

**Task 8:** Use a `for...in` loop to iterate over the properties of the book object and log each property and its value.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

book.getInfo = function () {
  return `${this.title} by ${this.author}`;
};

book.updateYear = function (newYear) {
  this.year = newYear;
};
book.updateYear(2020);

for (let key in book) {
  if (book.hasOwnProperty(key)) {
    console.log(`${key}: ${book[key]}`);
  }
}
/*
Output:
title: Chai Aur Code
author: HC
year: 2020
getInfo: function () {

  return `${this.title} by ${this.author}`;

}
updateYear: function (newYear) {

  this.year = newYear;

}
*/
```

**Task 9:** Use `Object.keys(obj)` and `Object.values(obj)` methods to log all the keys and values of the book object.

```javascript
let book = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

book.getInfo = function () {
  return `${this.title} by ${this.author}`;
};

book.updateYear = function (newYear) {
  this.year = newYear;
};
book.updateYear(2020);

console.log(Object.keys(book));
// Output: [ 'title', 'author', 'year', 'getInfo', 'updateYear' ]
console.log(Object.values(book));
/* 
Output:
[
  'Chai Aur Code',
  'HC',
  2020,
  [Function (anonymous)],
  [Function (anonymous)]
]
*/
```

## Feature Request

1. **Book Object Script:** Write a script that creates a book object, adds methods to it, and logs its properties and method results.

```javascript
let newBook = {
  title: "Chai Aur Javascript",
  author: "HC",
  year: 2024,
  getInfo: function () {
    return `${this.title} by ${this.author}`;
  },
  updateYear: function (newYear) {
    this.year = newYear;
  },
  getTitleAndYear: function () {
    return `${this.title} (${this.year})`;
  },
};

console.log(newBook.getInfo());
// Output: Chai Aur Javascript by HC
newBook.updateYear(2021);
console.log(newBook.getTitleAndYear());
// Output: Chai Aur Javascript (2021)
```

2. **Library Object Script:** Create a script that defines a library object containing an array of book objects and logs the library’s details.

```javascript
let libraryExample = {
  name: "Town Library",
  books: [
    { title: "Book1", author: "A1", year: 2020 },
    { title: "Book2", author: "B1", year: 2024 },
  ],
};

console.log(libraryExample.name); // Output: Town Library
libraryExample.books.forEach((book) => {
  console.log(`${book.title} by ${book.author} (${book.year})`);
});
// Output:
// Book1 by A1 (2020)
// Book2 by B1 (2024)
```

3. **Object Iteration Script:** Write a script that demonstrates iterating over an object’s properties using `for...in` loop and `Object.keys`/`Object.values`.

```javascript
let sampleBook = {
  title: "Chai Aur Code",
  author: "HC",
  year: 2024,
};

console.log("Using for...in loop:");
for (let key in sampleBook) {
  console.log(`${key}: ${sampleBook[key]}`);
}
/*
Output: Using for...in loop:
title: Chai Aur Code
author: HC
year: 2024
*/

console.log("Using Object.keys and Object.values:");
Object.keys(sampleBook).forEach((key) => {
  console.log(`${key}: ${sampleBook[key]}`);
});

/*
Output: Using Object.keys and Object.values:
title: Chai Aur Code
author: HC
year: 2024
*/
```

## Achievements

By the end of these activities, students will:

- Create and manipulate objects with properties and methods.
- Understand and use the this keyword in object methods.
- Work with nested objects and arrays of objects.
- Iterate over an object’s properties using loops and built-in methods.
