# Day 13: JavaScript Module Activities

Welcome to JavaScript Module Activities! In these activities, we will explore creating, exporting, and importing modules in JavaScript. We'll also cover using third-party modules, named and default exports, and importing entire modules. By the end of these activities, you'll have a strong understanding of how to work with modules in JavaScript.

## Table of Contents

1. [Activity 1: Creating and Exporting Modules](#activity-1-creating-and-exporting-modules)
2. [Activity 2: Named and Default Exports](#activity-2-named-and-default-exports)
3. [Activity 3: Importing Entire Modules](#activity-3-importing-entire-modules)
4. [Activity 4: Using Third-Party Modules](#activity-4-using-third-party-modules)
5. [Feature Request](#feature-request)
6. [Achievements](#achievements)

## Activity 1: Creating and Exporting Modules

**Task 1:** Create a module that exports a function to add two numbers. Import and use this module in another script.

```JS
// -------------- mathModule.js

// Exporting a function to add two numbers
function add(a, b) {
    return a + b;
}

export {add};
```

```JS
// -------------- app.js

// Importing the add function from mathModule.js
import { add } from "./mathModule";

const result = add(5, 3);
console.log(`The sum is: ${result}`); // The sum is: 8
```

**Task 2:** Create a module that exports an object representing a person with properties and methods. Import and use this module in another script.

```JS
// -------------- personModule.js

// Exporting an object representing a person with properties and methods
export const person = {
  name: 'manoj',
  age: 25,
  greet() {
    return `Hello, my name is ${this.name}`;
  }
};
```

```JS
// -------------- app.js

// Importing the person object from personModule.js
import { person } from './personModule';

console.log(person.greet()); // Hello, my name is manoj
console.log(`Age: ${person.age}`); // Age: 25
```

## Activity 2: Named and Default Exports

**Task 3:** Create a module that exports multiple functions using named exports. Import and use these functions in another script.

```JS
// -------------- utilsModule.js

// Exporting multiple functions using named exports
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}

```

```JS
// -------------- app.js

// Importing the add and subtract functions from utilsModule.js
import { add, subtract } from './utilsModule';

console.log(`The sum is: ${add(5, 3)}`); // The sum is: 8
console.log(`The difference is: ${subtract(5, 3)}`); // The difference is: 2
```

**Task 4:** Create a module that exports a single function using default export. Import and use this function in another script.

```JS
// -------------- defaultExportModule.js

// Exporting a function using default export
export default function multiply(a, b) {
  return a * b;
}
```

```JS
// -------------- app.js

// Importing the multiply function from defaultExportModule.js
import multiply from './defaultExportModule';

console.log(`The product is: ${multiply(5, 3)}`); // The product is: 15
```

## Activity 3: Importing Entire Modules

**Task 5:** Create a module that exports multiple constants and functions. Import the entire module as an object in another script and use its properties.

```JS
// -------------- constantsModule.js

// Exporting multiple constants and functions
export const PI = 3.14;
export const E = 2.71;

export function square(x) {
  return x * x;
}
```

```JS
// -------------- app.js

// Importing the entire constantsModule.js as an object
import * as constants from './constantsModule';

console.log(`PI: ${constants.PI}`); // PI: 3.14
console.log(`E: ${constants.E}`); // E: 2.71
console.log(`Square of 4: ${constants.square(4)}`); // Square of 4: 16
```

## Activity 4: Using Third-Party Modules

**Task 6:** Install a third-party module (e.g., lodash) using npm. Import and use a function from this module in a script.

```BASH
npm install lodash
```

```JS
// -------------- app.js

import _ from 'lodash';

const array = [1, 2, 3, 4, 5];
const reversedArray = _.reverse([...array]); // Using spread operator to create a copy

console.log(`Reversed array: ${reversedArray}`); // Reversed array: [5, 4, 3, 2, 1]
```

**Task 7:** Install a third-party module (e.g., axios) using npm. Import and use this module to make a network request in a script.

```BASH
npm install axios
```

```JS
// -------------- app.js

// Importing axios
import axios from 'axios';

axios.get('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(error);
  });


/*
{
  userId: 1,
  id: 1,
  title: "CHAI AUR CODE",
  completed: false
}
*/
```

## Feature Request

1. **Basic Module Script:** Write a script that creates a module exporting a function and imports it in another script.
2. **Named and Default Exports Script:** Create a script demonstrating both named and default exports and their usage.
3. **Third-Party Module Script:** Write a script that installs, imports, and uses functions from third-party modules like lodash and axios.
4. **Module Bundling Script:** Create a script demonstrating how to bundle JavaScript files using a module bundler (optional).

## Achievements

By the end of these activities, students will:

- Create and export functions, objects, and constants using modules.
- Import modules using named and default imports.
- Use third-party modules installed via npm.
- Understand the basics of module bundling (optional).
