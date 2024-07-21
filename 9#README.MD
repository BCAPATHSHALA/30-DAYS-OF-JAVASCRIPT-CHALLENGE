# Day 9: DOM Manipulation in Javascript

Welcome to Day 9 of JavaScript Basics! Today, we'll dive into DOM Manipulation. We'll explore how to select and manipulate elements, create and append new elements, remove existing ones, modify attributes and classes, and handle events. This session will help you understand the core techniques to interact with and modify the web page dynamically using JavaScript.

## Table of Contents

1. [HTML File](#html-file)
2. [Activity 1: Selecting and Manipulating Elements](#activity-1-selecting-and-manipulating-elements)
3. [Activity 2: Creating and Appending Elements](#activity-2-creating-and-appending-elements)
4. [Activity 3: Removing Elements](#activity-3-removing-elements)
5. [Activity 4: Modifying Attributes and Classes](#activity-4-modifying-attributes-and-classes)
6. [Activity 5: Event Handling](#activity-5-event-handling)
7. [JavaScript File](#javascript-file)
8. [CSS File](#css-file)
9. [Feature Request](#feature-request)
10. [Achievements](#achievements)

## HTML File

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Day 9: DOM Manipulation</title>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <h1>Day 9: DOM Manipulation</h1>

    <!-- Task 1 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 1
    </p>
    <p id="task1">Original Text</p>

    <!-- Task 2 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 2
    </p>
    <div class="task2">Background Color Change</div>

    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 3
    </p>
    <!-- Task 3 will append here -->

    <!-- Task 4 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 4
    </p>
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>

    <!-- Task 5 and 6 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 5, 6
    </p>
    <div id="task5">
      <p>Child 1</p>
      <p>Child 2</p>
      <p>Child 3</p>
    </div>

    <!-- Task 7 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 7
    </p>
    <img id="task7" src="originalImage.jpg" alt="Original Image" />

    <!-- Task 8 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 8
    </p>
    <div id="task8" class="oldClass">Class Modification</div>

    <!-- Task 9 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 9
    </p>
    <button id="task9Button">Change Paragraph Text</button>
    <p id="task9Text">Original Paragraph Text</p>

    <!-- Task 10 -->
    <p
      style="background-color: violet; font-size: large; text-align: center; font-style:italic;"
    >
      TASK 10
    </p>
    <div
      id="task10"
      style="border: 1px solid black; width: 200px; height: 200px;"
    >
      Hover over me
    </div>

    <script src="index.js"></script>
  </body>
</html>
```

## Activity 1: Selecting and Manipulating Elements

**Task 1:** Select an HTML element by its ID and change its text content.

```javascript
document.getElementById("task1").textContent = "New text content";
```

**Task 2:** Select an HTML element by its class and change its background color.

```javascript
document.querySelector(".task2").style.backgroundColor = "green";
```

## Activity 2: Creating and Appending Elements

**Task 3:** Create a new `div` element with some text content and append it to the body.

```javascript
const newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";
document.body.appendChild(newDiv);
```

**Task 4:** Create a new `li` element and add it to an existing `ul` list.

```javascript
const newLi = document.createElement("li");
newLi.textContent = "New list item 3";
document.querySelector("ul").appendChild(newLi);
```

## Activity 3: Removing Elements

**Task 5:** Select an HTML element and remove it from the DOM.

```javascript
const elementToRemove = document.getElementById("task5");
elementToRemove.parentNode.removeChild(elementToRemove);
```

**Task 6:** Remove the last child of a specific HTML element.

```javascript
const parentElement = document.getElementById("task5");
parentElement.removeChild(parentElement.lastChild);
```

## Activity 4: Modifying Attributes and Classes

**Task 7:** Select an HTML element and change one of its attributes (e.g., `src` of an `img` tag).

```javascript
document.querySelector("img").setAttribute("src", "newImage.jpg");
```

**Task 8:** Add and remove a CSS class to/from an HTML element.

```javascript
const element = document.getElementById("task8");
element.classList.add("newClass");
element.classList.remove("oldClass");
```

## Activity 5: Event Handling

**Task 9:** Add a click event listener to a button that changes the text content of a paragraph.

```javascript
document.getElementById("task9Button").addEventListener("click", function () {
  document.getElementById("task9Text").textContent = "Text has been changed!";
});
```

**Task 10:** Add a mouseover event listener to an element that changes its border color.

```javascript
document.getElementById("task10").addEventListener("mouseover", function () {
  this.style.borderColor = "red";
});
```

## JavaScript File

```javascript
// index.js
// Task 1: Select an HTML element by its ID and change its text content.
document.getElementById("task1").textContent = "New text content";

// Task 2: Select an HTML element by its class and change its background color.
document.querySelector(".task2").style.backgroundColor = "green";

// Task 3: Create a new div element with some text content and append it to the body.
const newDiv = document.createElement("div");
newDiv.textContent = "This is a new div";
document.body.appendChild(newDiv);

// Task 4: Create a new li element and add it to an existing ul list.
const newLi = document.createElement("li");
newLi.textContent = "New list item 3";
document.querySelector("ul").appendChild(newLi);

// Task 5: Select an HTML element and remove it from the DOM.
const elementToRemove = document.getElementById("task5");
elementToRemove.parentNode.removeChild(elementToRemove);

// Task 6: Remove the last child of a specific HTML element.
const parentElement = document.getElementById("task5");
parentElement.removeChild(parentElement.lastChild);

// Task 7: Select an HTML element and change one of its attributes (e.g., src of an img tag).
document.querySelector("img").setAttribute("src", "newImage.jpg");

// Task 8: Add and remove a CSS class to/from an HTML element.
const element = document.getElementById("task8");
element.classList.add("newClass");
element.classList.remove("oldClass");

// Task 9: Add a click event listener to a button that changes the text content of a paragraph.
document.getElementById("task9Button").addEventListener("click", function () {
  document.getElementById("task9Text").textContent = "Text has been changed!";
});

// Task 10: Add a mouseover event listener to an element that changes its border color.
document.getElementById("task10").addEventListener("mouseover", function () {
  this.style.borderColor = "red";
});
```

## CSS File

```css
/* style.css */
body {
  font-family: Arial, sans-serif;
  margin: 20px;
  padding: 0;
  background-color: #f0f0f0;
}

h1 {
  color: #333;
}

p,
div,
ul,
li,
img,
button {
  margin-bottom: 20px;
}

.task2 {
  padding: 10px;
  border: 1px solid #ccc;
}

#task10 {
  display: flex;
  align-items: center;
  justify-content: center;
  transition: border-color 0.3s ease;
}

button {
  padding: 10px 20px;
  cursor: pointer;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #0056b3;
}

.newClass {
  background-color: lightblue;
}

.oldClass {
  background-color: lightcoral;
}
```

## Feature Request

1. Text Content Manipulation Script: Write a script that selects an HTML element by its ID and changes its text content.
2. Element Creation Script: Create a script that demonstrates creating a new div element and appending it to the body.
3. Element Removal Script: Write a script that selects an HTML element and removes it from the DOM.
4. Attribute Modification Script: Create a script that changes the attributes of an HTML element.
5. Event Handling Script: Write a script that adds event listeners to HTML elements to change their content or style based on user interactions.

## Achievements

By the end of these activities, students will:

- Select and manipulate DOM elements using JavaScript.
- Create and append new elements to the DOM.
- Remove elements from the DOM.
- Modify attributes and classes of HTML elements.
- Add and handle events to make web pages interactive.
