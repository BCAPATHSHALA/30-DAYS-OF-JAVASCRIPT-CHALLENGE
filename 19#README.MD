# Day 19: Regular Expressions in JavaScript

Welcome to Regular Expression Activities! In these activities, we will delve into the world of regular expressions, exploring their fundamentals and applications through hands-on tasks and practical examples. By the end of these activities, you'll have a solid understanding of how to create and use regular expressions effectively in programming, enabling you to tackle complex text processing and validation challenges with confidence.

💡 Regexs can be used to find and match all sort of things, from urls to filenames

💡 HOWEVER! be careful if you try to use regexs for really complex tasks, such as parsing emails (which get really confusing, really fast), or HTML (which is not a regular language, and so can't be fully parsed by a regular expression)

- [Basic Understanding of Regexs](#)
- [Regexs Website for Developer](https://regexr.com/)
- 🙋🏻‍♂️ This is a hard task: Use tools like AI, or any other regex generator for generating Regex but you have a basic understanding of regex.

## Table of Contents

1. [Activity 1: Basic Regular Expressions](#activity-1-basic-regular-expressions)
2. [Activity 2: Character Classes and Quantifiers](#activity-2-character-classes-and-quantifiers)
3. [Activity 3: Grouping and Capturing](#activity-3-grouping-and-capturing)
4. [Activity 4: Assertions and Boundaries](#activity-4-assertions-and-boundaries)
5. [Activity 5: Practical Applications](#activity-5-practical-applications)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Basic Regular Expressions

**Task 1:** Write a regular expression to match a simple pattern (e.g., match all occurrences of the word "JavaScript" in a string). Log the matches.

```js
const str =
  "JavaScript is a programming language. Many developers love JavaScript.";
const regex = /JavaScript/g;
const matches = str.match(regex);
console.log(matches); // Output: ["JavaScript", "JavaScript"]
```

**Task 2:** Write a regular expression to match all digits in a string. Log the matches.

```js
const str = "There are 123 apples and 456 oranges.";
const regex = /\d+/g;
const matches = str.match(regex);
console.log(matches); // Output: ["123", "456"]
```

## Activity 2: Character Classes and Quantifiers

**Task 3:** Write a regular expression to match all words in a string that start with a capital letter. Log the matches.

```js
const str = "JavaScript is a programming language. Many developers love it.";
const regex = /\b[A-Z][a-z]*\b/g;
const matches = str.match(regex);
console.log(matches); // Output: ["JavaScript", "Many"]
```

**Task 4:** Write a regular expression to match all sequences of one or more digits in a string. Log the matches.

```js
const str = "The numbers are 123, 4567, and 89.";
const regex = /\d+/g;
const matches = str.match(regex);
console.log(matches); // Output: ["123", "4567", "89"]
```

## Activity 3: Grouping and Capturing

**Task 5:** Write a regular expression to capture the area code, central office code, and line number from a US phone number format (e.g., (123) 456-7890). Log the captures.

```js
const str = "(123) 456-7890";
const regex = /\((\d{3})\)\s(\d{3})-(\d{4})/;
const matches = str.match(regex);
console.log(matches); // Output: ["(123) 456-7890", "123", "456", "7890"]
```

**Task 6:** Write a regular expression to capture the username and domain from an email address. Log the captures.

```js
const str = "example@domain.com";
const regex = /(\w+)@([\w.]+)/;
const matches = str.match(regex);
console.log(matches); // Output: ["example@domain.com", "example", "domain.com"]
```

## Activity 4: Assertions and Boundaries

**Task 7:** Write a regular expression to match a word only if it is at the beginning of a string. Log the matches.

```js
const str = "JavaScript is great. JavaScript is fun.";
const regex = /^\w+/;
const matches = str.match(regex);
console.log(matches); // Output: ["JavaScript"]
```

**Task 8:** Write a regular expression to match a word only if it is at the end of a string. Log the matches.

```js
const str = "I love JavaScript";
const regex = /\w+$/;
const matches = str.match(regex);
console.log(matches); // Output: ["JavaScript"]
```

## Activity 5: Practical Applications

Task 9: Write a regular expression to validate a simple password (must include at least one uppercase letter, one lowercase letter, one digit, and one special character). Log whether the password is valid.

```js
const password = "P@ssw0rd";
const regex =
  /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/;
const isValid = regex.test(password);
console.log(isValid); // Output: true
```

**Task 10:** Write a regular expression to validate a URL. Log whether the URL is valid.

```js
const url = "https://www.example.com";
const regex = /^(https?:\/\/)?([\w.-]+)+(:\d+)?(\/[\w.-]*)*\/?$/;
const isValid = regex.test(url);
console.log(isValid); // Output: true
```

## Feature Request:

1. **Basic Regex Script:** Write a script that uses regular expressions to match simple patterns and log the matches.
2. **Character Classes and Quantifiers Script:** Create a script that uses regular expressions to match words with specific characteristics and log the matches.
3. **Grouping and Capturing Script:** Write a script that uses regular expressions to capture parts of a string, such as phone numbers and email addresses, and log the captures.
4. **Assertions and Boundaries Script:** Create a script that uses regular expressions to match words at specific positions in a string and log the matches.
5. **Validation Script:** Write a script that uses regular expressions to validate passwords and URLs and log whether they are valid.

## Achievements:

By the end of these activities, students will:

- Understand and create basic regular expressions.
- Use character classes and quantifiers in regular expressions.
- Implement grouping and capturing in regular expressions.
- Apply assertions and boundaries in regular expressions.
- Use regular expressions for practical applications like validating passwords and URLs.
