# Day 20: LocalStorage and SessionStorage in JavaScript

In these activities, we will explore the fundamentals of LocalStorage and SessionStorage in JavaScript. By the end of these activities, you'll have a solid understanding of how to use LocalStorage and SessionStorage for persistent and session-specific data storage.

## Table of Contents

1. [Activity 1: Understanding LocalStorage](#activity-1-understanding-localstorage)
2. [Activity 2: Using LocalStorage](#activity-2-using-localstorage)
3. [Activity 3: Understanding SessionStorage](#activity-3-understanding-sessionstorage)
4. [Activity 4: Using SessionStorage](#activity-4-using-sessionstorage)
5. [Activity 5: Comparing LocalStorage and SessionStorage](#activity-5-comparing-localstorage-and-sessionstorage)
6. [Feature Request](#feature-request)
7. [Achievements](#achievements)

🙋🏻‍♂️ [Understanding LocalStorage, SessionStorage, and Cookies](https://github.com/BCAPATHSHALA/30-DAYS-OF-JAVASCRIPT-CHALLENGE/blob/main/LSC.MD)

## Activity 1: Understanding LocalStorage

**Task 1:** Write a script to save a string value to localStorage and retrieve it. Log the retrieved value.

```js
let key = "myString";
let value = "Hello, LocalStorage!";

// Save a string to localStorage
localStorage.setItem(key, value);

// Retrieve the string from localStorage
const retrievedString = localStorage.getItem(key);
console.log(retrievedString); // Output: "Hello, LocalStorage!"
```

**Task 2:** Write a script to save an object to localStorage by converting it to a JSON string. Retrieve and parse the object, then log it.

```js
const myObject = { channel: "CHAI AUR CODE", subscribers: "1M" };

console.log("OBJECT: ", myObject); // OBJECT: {channel: 'CHAI AUR CODE', subscribers: '1M'}
console.log("OBJECT TO JSON: ", JSON.stringify(myObject)); // OBJECT TO JSON:  {"channel":"CHAI AUR CODE","subscribers":"1M"}

// Save an object to localStorage
localStorage.setItem("myObject", JSON.stringify(myObject));

console.log("JSON: ", localStorage.getItem("myObject")); // JSON: {"channel":"CHAI AUR CODE","subscribers":"1M"}
console.log("JSON TO OBJECT: ", JSON.parse(localStorage.getItem("myObject"))); // JSON TO OBJECT: {channel: 'CHAI AUR CODE', subscribers: '1M'}

// Retrieve and parse the object from localStorage
const retrievedObject = JSON.parse(localStorage.getItem("myObject"));
console.log(retrievedObject); // Output: { channel: "CHAI AUR CODE", subscribers: "1M" }
```

## Activity 2: Using LocalStorage

**Task 3:** Create a simple form that saves user input (e.g., name and email) to `localStorage` when submitted. Retrieve and display the saved data on page load.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>LocalStorage Form</title>
  </head>

  <body>
    <div class="container">
      <form id="userForm">
        <input type="text" id="name" placeholder="Name" required />
        <input type="email" id="email" placeholder="Email" required />
        <button type="submit">Save</button>
      </form>
      <div id="displayData"></div>
    </div>
    <script>
      document.addEventListener("DOMContentLoaded", () => {
        const userForm = document.getElementById("userForm");
        const displayData = document.getElementById("displayData");

        userForm.addEventListener("submit", (e) => {
          e.preventDefault();
          const name = document.getElementById("name").value;
          const email = document.getElementById("email").value;
          const userData = { name, email };

          // Add validation for email
          if (!validateEmail(email)) {
            alert("Invalid email address");
            return;
          }

          localStorage.setItem("userData", JSON.stringify(userData));
          displayUserData();
        });

        function displayUserData() {
          const userData = JSON.parse(localStorage.getItem("userData"));
          if (userData) {
            displayData.innerHTML = `Name: ${userData.name}, Email: ${userData.email}`;
          } else {
            displayData.innerHTML = "No user data found";
          }
        }

        // Add a function to validate email
        function validateEmail(email) {
          const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
          return emailRegex.test(email);
        }

        displayUserData();
      });
    </script>
  </body>
</html>
```

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722495424/LOCAL_STORAGE_nwopaw.png" alt="Local Storage in JavaScript">
</p>

**Task 4:** Write a script to remove an item from `localStorage`. Log the `localStorage` content before and after removal.

```js
let key = "myString";
let value = "Hello, LocalStorage!";

// Save a string to localStorage
localStorage.setItem(key, value);

// Log localStorage content before removal
console.log(localStorage.getItem(key)); // Output: "Hello, LocalStorage!"

// Remove an item from localStorage
localStorage.removeItem(key);

// Log localStorage content after removal
console.log(localStorage.getItem(key)); // Output: null
```

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722496039/LOCAL_STORAGE_jngcrk.png" alt="Local Storage in JavaScript">
</p>

## Activity 3: Understanding SessionStorage

**Task 5:** Write a script to save a string value to `sessionStorage` and retrieve it. Log the retrieved value.

```js
let key = "mySessionString";
let value = "Hello, SessionStorage!";

// Save a string to sessionStorage
sessionStorage.setItem(key, value);

// Retrieve the string from sessionStorage
const retrievedSessionString = sessionStorage.getItem(key);
console.log(retrievedSessionString); // Output: "Hello, SessionStorage!"
```

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722496303/Session_Storage_lz4vlk.png" alt="Session Storage in JavaScript">
</p>

**Task 6:** Write a script to save an object to `sessionStorage` by converting it to a JSON string. Retrieve and parse the object, then log it.

```js
const mySessionObject = { channel: "CHAI AUR CODE", subscribers: "1M" };

// Save an object to sessionStorage
sessionStorage.setItem("mySessionObject", JSON.stringify(mySessionObject));

// Retrieve and parse the object from sessionStorage
const retrievedSessionObject = JSON.parse(
  sessionStorage.getItem("mySessionObject")
);
console.log(retrievedSessionObject); // Output: {channel: 'CHAI AUR CODE', subscribers: '1M'}
```

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722496653/Session_Storage_tbvole.png" alt="Session Storage in JavaScript">
</p>

## Activity 4: Using SessionStorage

**Task 7:** Create a simple form that saves user input (e.g., name and email) to `sessionStorage` when submitted. Retrieve and display the saved data on page load.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>SessionStorage Form</title>
  </head>

  <body>
    <div class="container">
      <form id="sessionForm">
        <input type="text" id="sessionName" placeholder="Name" required />
        <input type="email" id="sessionEmail" placeholder="Email" required />
        <button type="submit">Save</button>
      </form>
      <div id="sessionDisplayData"></div>
    </div>
    <script>
      document.addEventListener("DOMContentLoaded", () => {
        const sessionForm = document.getElementById("sessionForm");
        const sessionDisplayData =
          document.getElementById("sessionDisplayData");

        sessionForm.addEventListener("submit", (e) => {
          e.preventDefault();
          const name = document.getElementById("sessionName").value;
          const email = document.getElementById("sessionEmail").value;
          const userData = { name, email };

          // Add validation for email
          if (!validateEmail(email)) {
            alert("Invalid email address");
            return;
          }

          sessionStorage.setItem("sessionUserData", JSON.stringify(userData));
          displaySessionUserData();
        });

        function displaySessionUserData() {
          const userData = JSON.parse(
            sessionStorage.getItem("sessionUserData")
          );
          if (userData) {
            sessionDisplayData.innerHTML = `Name: ${userData.name}, Email: ${userData.email}`;
          } else {
            sessionDisplayData.innerHTML = "No user data found";
          }
        }

        // Add a function to validate email
        function validateEmail(email) {
          const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
          return emailRegex.test(email);
        }

        displaySessionUserData();
      });
    </script>
  </body>
</html>
```

<p align="center">
    <img src="https://res.cloudinary.com/dkbtmzdtt/image/upload/v1722497047/Session_Storage_ve0iu1.png" alt="Session Storage in JavaScript">
</p>

**Task 8:** Write a script to remove an item from `sessionStorage`. Log the `sessionStorage` content before and after removal.

```js
const mySessionObject = { channel: "CHAI AUR CODE", subscribers: "1M" };

// Save an object to sessionStorage
sessionStorage.setItem("mySessionObject", JSON.stringify(mySessionObject));

// Log sessionStorage content before removal
console.log(sessionStorage.getItem("mySessionObject")); // Output: {"channel":"CHAI AUR CODE","subscribers":"1M"}

// Remove an item from sessionStorage
sessionStorage.removeItem("mySessionObject");

// Log sessionStorage content after removal
console.log(sessionStorage.getItem("mySessionObject")); // Output: null
```

## Activity 5: Comparing LocalStorage and SessionStorage

**Task 9:** Write a function that accepts a key and a value, and saves the value to both `localStorage` and `sessionStorage`. Retrieve and log the values from both storage mechanisms.

```js
function saveToBothStorages(key, value) {
  localStorage.setItem(key, value);
  sessionStorage.setItem(key, value);
  console.log("localStorage:", localStorage.getItem(key));
  console.log("sessionStorage:", sessionStorage.getItem(key));
}

saveToBothStorages("myKey", "myValue");
// Output:
// localStorage: myValue
// sessionStorage: myValue
```

**Task 10:** Write a function that clears all data from both `localStorage` and `sessionStorage`. Verify that both storages are empty.

```js
function saveToBothStorages(key, value) {
  localStorage.setItem(key, value);
  sessionStorage.setItem(key, value);
  console.log("localStorage:", localStorage.getItem(key));
  console.log("sessionStorage:", sessionStorage.getItem(key));
}

saveToBothStorages("myKey", "myValue");
// Output:
// localStorage: myValue
// sessionStorage: myValue

function clearAllStorages() {
  localStorage.clear();
  sessionStorage.clear();
  console.log("localStorage:", localStorage.length);
  console.log("sessionStorage:", sessionStorage.length);
}

clearAllStorages();

// Output:
// localStorage: 0
// sessionStorage: 0
```

## Feature Request:

1. **LocalStorage Script:** Write a script that saves, retrieves, and removes items from localStorage, and displays the saved data on page load.

```js
function localStorageScript() {
  // Save item
  localStorage.setItem("localKey", "localValue");

  // Retrieve item
  const localItem = localStorage.getItem("localKey");
  console.log("Retrieved from localStorage:", localItem);

  // Remove item
  localStorage.removeItem("localKey");
  console.log(
    "After removal from localStorage:",
    localStorage.getItem("localKey")
  );
}

localStorageScript();
// Output:
// Retrieved from localStorage: localValue
// After removal from localStorage: null
```

2. **SessionStorage Script:** Create a script that saves, retrieves, and removes items from sessionStorage, and displays the saved data on page load.

```js
function sessionStorageScript() {
  // Save item
  sessionStorage.setItem("sessionKey", "sessionValue");

  // Retrieve item
  const sessionItem = sessionStorage.getItem("sessionKey");
  console.log("Retrieved from sessionStorage:", sessionItem);

  // Remove item
  sessionStorage.removeItem("sessionKey");
  console.log(
    "After removal from sessionStorage:",
    sessionStorage.getItem("sessionKey")
  );
}

sessionStorageScript();

localStorageScript();
// Output:
// Retrieved from sessionStorage: sessionValue
// After removal from sessionStorage: null
```

3. **Storage Comparison Script:** Write a script that saves data to both localStorage and sessionStorage, retrieves the data, and compares the results.

```js
function storageComparisonScript() {
  // Save item to both storages
  localStorage.setItem("compareKey", "compareValue");
  sessionStorage.setItem("compareKey", "compareValue");

  // Retrieve items
  const localItem = localStorage.getItem("compareKey");
  const sessionItem = sessionStorage.getItem("compareKey");
  console.log("Retrieved from localStorage:", localItem);
  console.log("Retrieved from sessionStorage:", sessionItem);

  // Compare results
  console.log("Comparison result:", localItem === sessionItem);
}

storageComparisonScript();
// Output:
// Retrieved from localStorage: compareValue
// Retrieved from sessionStorage: compareValue
// Comparison result: true
```

4. **Clear Storage Script:** Create a script that clears all data from both localStorage and sessionStorage, and verifies the operation.

```js
function clearStorageScript() {
  // Clear both storages
  localStorage.clear();
  sessionStorage.clear();

  // Verify operation
  console.log("localStorage:", localStorage.length); // Output: 0
  console.log("sessionStorage:", sessionStorage.length); // Output: 0
}

clearStorageScript();
// Output:
// localStorage: 0
// sessionStorage: 0
```

## Achievements:

By the end of these activities, students will:

- Understand how to use localStorage and sessionStorage for persistent and session-specific data storage.
- Save, retrieve, and remove data from both localStorage and sessionStorage.
- Implement form data storage using localStorage and sessionStorage.
- Compare and contrast the use cases for localStorage and sessionStorage.
