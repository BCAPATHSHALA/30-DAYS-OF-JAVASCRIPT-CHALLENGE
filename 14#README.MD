# Day 14: Classes in JavaScript

Welcome to JavaScript Classes Activities! In these activities, we will explore defining classes, using inheritance, implementing static methods and properties, and working with getters, setters, and private fields. By the end of these activities, you'll have a solid understanding of how to use classes in JavaScript.

## Table of Contents

1. [Activity 1: Class Definition](#activity-1-class-definition)
2. [Activity 2: Class Inheritance](#activity-2-class-inheritance)
3. [Activity 3: Static Methods and Properties](#activity-3-static-methods-and-properties)
4. [Activity 4: Getters and Setters](#activity-4-getters-and-setters)
5. [Activity 5: Private Fields (Optional)](#activity-5-private-fields-optional)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Class Definition

**Task 1:** Define a class `Person` with properties `name` and `age`, and a method to return a greeting message. Create an instance of the class and log the greeting message.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

const person1 = new Person("MANOJ", 25);
console.log(person1.greet()); // Hello, my name is MANOJ and I am 25 years old.
```

**Task 2:** Add a method to the `Person` class that updates the `age` property and logs the updated age.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }

  updateAge(newAge) {
    this.age = newAge;
    console.log(`Updated age: ${this.age}`);
  }
}

const person1 = new Person("MANOJ", 25);
console.log(person1.greet()); // Hello, my name is MANOJ and I am 25 years old.
person1.updateAge(26); // Updated age: 26
console.log(person1.greet()); // Hello, my name is MANOJ and I am 26 years old.
```

## Activity 2: Class Inheritance

**Task 3:** Define a class `Student` that extends the `Person` class. Add a property `studentId` and a method to return the student ID. Create an instance of the `Student` class and log the student ID.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

class Student extends Person {
  constructor(name, age, studentId) {
    super(name, age);
    this.studentId = studentId;
  }

  getStudentId() {
    return `Student ID: ${this.studentId}`;
  }
}

const student1 = new Student("UMESH", 22, "S12345");
console.log(student1.getStudentId()); // Student ID: S12345
```

**Task 4:** Override the greeting method in the `Student` class to include the student ID in the message. Log the overridden greeting message.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

class Student extends Person {
  constructor(name, age, studentId) {
    super(name, age);
    this.studentId = studentId;
  }

  // Override the greet method of person class
  greet() {
    return `Hello, my name is ${this.name}, I am ${this.age} years old, and my student ID is ${this.studentId}.`;
  }
}

const student1 = new Student("UMESH", 22, "S12345");
console.log(student1.greet()); // Hello, my name is UMESH, I am 22 years old, and my student ID is S12345.
```

## Activity 3: Static Methods and Properties

**Task 5:** Add a static method to the `Person` class that returns a generic greeting message. Call this static method without creating an instance of the class and log the message.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Static method: we can call it without creating the instance of person class
  static genericGreet() {
    return "Hello, welcome to our community!";
  }
}

console.log(Person.genericGreet()); // Hello, welcome to our community!
```

**Task 6:** Add a static property to the `Student` class to keep track of the number of students created. Increment this property in the constructor and log the total number of students.

```js
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  // Static method: we can call it without creating the instance of person class
  static genericGreet() {
    return "Hello, welcome to our community!";
  }

  greet() {
    return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
  }
}

class Student extends Person {
  // Static variable
  static studentCount = 0;

  constructor(name, age, studentId) {
    // super method call a constructor of our parent class person to initialize the name and age fields
    super(name, age);
    this.studentId = studentId;
    Student.studentCount++;
  }

  // Override the greet method of person class
  greet() {
    return `Hello, my name is ${this.name}, I am ${this.age} years old, and my student ID is ${this.studentId}.`;
  }
}

const student1 = new Student("RAKESH", 22, "S12345");
const student2 = new Student("SAMAR", 23, "S12346");
console.log(`Total number of students: ${Student.studentCount}`); // Total number of students: 2
```

## Activity 4: Getters and Setters

**Task 7:** Add a getter method to the `Person` class to return the full name (assume a `firstName` and `lastName` property). Create an instance and log the full name using the getter.

```js
class Person {
  constructor(firstName, lastName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  }
}

const person1 = new Person("SAMAR", "SARKAR", 25);
console.log(person1.fullName); // SAMAR SARKAR
```

**Task 8:** Add a setter method to the `Person` class to update the name properties (`firstName` and `lastName`). Update the name using the setter and log the updated full name.

```js
class Person {
  constructor(firstName, lastName, age) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  }

  set fullName(name) {
    console.log("Hello " + name); // Hello Umesh Chaurasiya
    const [firstName, lastName] = name.split(" "); // ["Umesh", "Chaurasiya"]
    this.firstName = firstName; // Umesh
    this.lastName = lastName; // Chaurasiya
  }
}

const person1 = new Person("Samar", "Sarkar", 25);
console.log(person1.fullName); // Samar Sarkar
person1.fullName = "Umesh Chaurasiya";
console.log(person1.fullName); // Umesh Chaurasiya
```

## Activity 5: Private Fields (Optional)

**Task 9:** Define a class `Account` with private fields for `balance` and a method to deposit and withdraw money. Ensure that the balance can only be updated through these methods.

**Task 10:** Create an instance of the `Account` class and test the deposit and withdraw methods, logging the balance after each operation.

```js
// Task 1:
class Account {
  // Private Instance Variable Of Account
  _balance;

  constructor(initialBalance) {
    this._balance = initialBalance;
  }

  deposit(amount) {
    this._balance += amount;
    this.logBalance();
  }

  withdraw(amount) {
    if (amount <= this._balance) {
      this._balance -= amount;
    } else {
      console.log("Insufficient balance");
    }
    this.logBalance();
  }

  logBalance() {
    console.log(`Current balance: ${this._balance}`);
  }
}

// Task 10:
const instanceOfAccount = new Account(1000);
console.log(instanceOfAccount._balance); // 1000
instanceOfAccount.deposit(1000); // Current balance: 2000
instanceOfAccount.withdraw(150); // Current balance: 1850
```

## Feature Request

1. **Basic Class Script:** Write a script that defines a `Person` class with properties and methods, creates instances, and logs messages.
2. **Class Inheritance Script:** Create a script that defines a `Student` class extending `Person`, overrides methods, and logs the results.
3. **Static Methods and Properties Script:** Write a script that demonstrates static methods and properties in classes.
4. **Getters and Setters Script:** Create a script that uses getters and setters in a class.
5. **Private Fields Script:** Write a script that defines a class with private fields and methods to manipulate these fields (optional).

## Achievements

By the end of these activities, students will:

- Define and use classes with properties and methods.
- Implement inheritance to extend classes.
- Utilize static methods and properties.
- Apply getters and setters for encapsulation.
- Understand and use private fields in classes (optional).
