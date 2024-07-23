# Day 10: Event Handling in Javascript

Welcome to Day 10 of JavaScript Basics! Today, we'll explore Event Handling. We'll cover various types of events such as mouse events, keyboard events, form events, and event delegation. This session will help you understand how to interact with user actions and make your web pages more interactive and dynamic using JavaScript.

## Table of Contents

1. [Activity 1: Basic Event Handling](#activity-1-basic-event-handling)
   - Task 1: Click Event Listener
   - Task 2: Double-Click Event Listener
2. [Activity 2: Mouse Events](#activity-2-mouse-events)
   - Task 3: Mouseover Event Listener
   - Task 4: Mouseout Event Listener
3. [Activity 3: Keyboard Events](#activity-3-keyboard-events)
   - Task 5: Keydown Event Listener
   - Task 6: Keyup Event Listener
4. [Activity 4: Form Events](#activity-4-form-events)
   - Task 7: Submit Event Listener
   - Task 8: Change Event Listener
5. [Activity 5: Event Delegation](#activity-5-event-delegation)
   - Task 9: Click Event Delegation
   - Task 10: Event Listener for Dynamically Added Elements
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

## Activity 1: Basic Event Handling

**Task 1:** Add a click event listener to a button that changes the text content of a paragraph.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <p id="paragraph">This is a paragraph.</p>
    <button id="changeTextBtn">Change Text</button>

    <script>
      document
        .getElementById("changeTextBtn")
        .addEventListener("click", function () {
          document.getElementById("paragraph").textContent =
            "Text has been changed!";
        });
    </script>
  </body>
</html>
```

**Task 2:** Add a double-click event listener to an image that toggles its visibility.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <img
      id="image"
      src="image.jpg"
      alt="Chai Aur Code Image"
      style="display: block;"
    />

    <script>
      document
        .getElementById("image")
        .addEventListener("dblclick", function () {
          this.style.display = this.style.display === "none" ? "block" : "none";
        });
    </script>
  </body>
</html>
```

## Activity 2: Mouse Events

**Task 3:** Add a mouseover event listener to an element that changes its background color.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
    <style>
      #hoverElement {
        width: 200px;
        height: 200px;
        background-color: lightblue;
      }
    </style>
  </head>
  <body>
    <div id="hoverElement">Hover over me!</div>

    <script>
      document
        .getElementById("hoverElement")
        .addEventListener("mouseover", function () {
          this.style.backgroundColor = "yellow";
        });
    </script>
  </body>
</html>
```

**Task 4:** Add a mouseout event listener to an element that resets its background color.

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Handling</title>
    <style>
        #hoverElement {
            width: 200px;
            height: 200px;
            background-color: lightblue;
        }
    </style>
</head>
<body>
    <div id="hoverElement">Hover over me!</div>

    <script>
        const hoverElement = document.getElementById('hoverElement');

        hoverElement.addEventListener('mouseover', function() {
            this.style.backgroundColor = 'yellow';
        });

        hoverElement.addEventListener('mouseout', function() {
            this.style.backgroundColor = 'lightblue';
        });
    </script>
</body>
</html>
```

## Activity 3: Keyboard Events

**Task 5:** Add a keydown event listener to an input field that logs the key pressed to the console.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <input type="text" id="inputField" placeholder="Type something..." />

    <script>
      document
        .getElementById("inputField")
        .addEventListener("keydown", function (event) {
          console.log("Key pressed:", event.key);
        });
    </script>
  </body>
</html>
```

**Task 6:** Add a keyup event listener to an input field that displays the current value in a paragraph.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <input type="text" id="inputField" placeholder="Type something..." />
    <p id="displayText"></p>

    <script>
      document
        .getElementById("inputField")
        .addEventListener("keyup", function () {
          document.getElementById("displayText").textContent = this.value;
        });
    </script>
  </body>
</html>
```

## Activity 4: Form Events

**Task 7:** Add a submit event listener to a form that prevents the default submission and logs the form data to the console.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <form id="form">
      <input type="text" name="username" placeholder="Username" />
      <button type="submit">Submit</button>
    </form>

    <script>
      document
        .getElementById("form")
        .addEventListener("submit", function (event) {
          event.preventDefault();
          console.log("Form data:", new FormData(this));
        });
    </script>
  </body>
</html>
```

**Task 8:** Add a change event listener to a select dropdown that displays the selected value in a paragraph.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <select id="dropdown">
      <option value="Option 1">Option 1</option>
      <option value="Option 2">Option 2</option>
      <option value="Option 3">Option 3</option>
    </select>
    <p id="selectedValue"></p>

    <script>
      document
        .getElementById("dropdown")
        .addEventListener("change", function () {
          document.getElementById(
            "selectedValue"
          ).textContent = `Selected: ${this.value}`;
        });
    </script>
  </body>
</html>
```

## Activity 5: Event Delegation

**Task 9:** Add a click event listener to a list that logs the text content of the clicked list item using event delegation.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>
  <body>
    <ul id="list">
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>

    <script>
      document
        .getElementById("list")
        .addEventListener("click", function (event) {
          if (event.target.tagName === "LI") {
            console.log("Clicked item:", event.target.textContent);
          }
        });
    </script>
  </body>
</html>
```

**Task 10:** Add an event listener to a parent element that listens for events from dynamically added child elements.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Event Handling</title>
  </head>

  <body>
    <div id="parentElement">Parent Element</div>
    <button id="addElementBtn">Add Child Element</button>

    <script>
      document
        .getElementById("parentElement")
        .addEventListener("click", function (event) {
          if (event.target.classList.contains("childElement")) {
            console.log("Clicked child element:", event.target.textContent);
          }
        });

      let count = 0;
      document
        .getElementById("addElementBtn")
        .addEventListener("click", function () {
          const newElement = document.createElement("div");
          newElement.className = "childElement";
          newElement.textContent = `New Child Element ${count++}`;
          document.getElementById("parentElement").appendChild(newElement);
        });
    </script>
  </body>
</html>
```

## Feature Request

1. **Click Event Script:** Add a click event listener to a button to change the text content of a paragraph. (Already covered in Activity 1, Task 1)

2. **Mouse Events Script:** Handle mouseover and mouseout events to change the background color of an element. (Already covered in Activity 2, Tasks 3 and 4)

3. **Keyboard Events Script:** Log key presses and display input field values using keydown and keyup event listeners. (Already covered in Activity 3, Tasks 5 and 6)

4. **Form Events Script:** Handle form submission and change events on a select dropdown. (Already covered in Activity 4, Tasks 7 and 8)

5. **Event Delegation Script:** Demonstrate event delegation by handling events on dynamically added child elements. (Already covered in Activity 5, Task 10)

## Achievements

By completing these activities, students will:

- Add and handle basic events like click, double-click, mouseover, mouseout, keydown, and keyup.
- Understand and handle form events.
- Implement event delegation to manage events on dynamically added elements.
- Make web pages interactive by responding to various user actions.
