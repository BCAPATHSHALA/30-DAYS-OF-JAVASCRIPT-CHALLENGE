# Understanding LocalStorage, SessionStorage, and Cookies

LocalStorage, SessionStorage, and Cookies are all mechanisms for storing data on the client-side. Each has its own use cases, advantages, and limitations.

## LocalStorage

### Why Use LocalStorage?

- Persistent storage: Data stored in LocalStorage does not expire.
- Can store a larger amount of data compared to cookies (up to 5MB per origin).
- Ideal for saving user preferences, settings, or any information that should persist across browser sessions.

### When to Use LocalStorage?

- When you need to store data for long periods.
- For data that doesn't need to be sent to the server with every HTTP request.

### How to Use LocalStorage?

Example Code:

```JS
// Save a string to LocalStorage
localStorage.setItem('username', 'manojofficialmj');

// Retrieve the string from LocalStorage
const username = localStorage.getItem('username');
console.log(username); // Output: "manojofficialmj"

// Save an object to LocalStorage
const user = { name: 'Manoj Kumar', age: 25 };
localStorage.setItem('user', JSON.stringify(user));

// Retrieve and parse the object from LocalStorage
const retrievedUser = JSON.parse(localStorage.getItem('user'));
console.log(retrievedUser); // Output: { name: "Manoj Kumar", age: 25 }

// Remove an item from LocalStorage
localStorage.removeItem('username');

// Clear all data from LocalStorage
localStorage.clear();
```

## SessionStorage

### Why Use SessionStorage?

- Session-specific storage: Data is stored only for the duration of the page session.
- Data is deleted when the page session ends (e.g., when the tab is closed).

### When to Use SessionStorage?

- When you need to store temporary data that should only be available during a single session.
- For sensitive data that should not persist beyond the current session.

### How to Use SessionStorage?

Example Code:

```JS
// Save a string to SessionStorage
sessionStorage.setItem('sessionUsername', 'manojofficialmj');

// Retrieve the string from SessionStorage
const sessionUsername = sessionStorage.getItem('sessionUsername');
console.log(sessionUsername); // Output: "manojofficialmj"

// Save an object to SessionStorage
const sessionUser = { name: 'Manoj Kumar', age: 25 };
sessionStorage.setItem('sessionUser', JSON.stringify(sessionUser));

// Retrieve and parse the object from SessionStorage
const retrievedSessionUser = JSON.parse(sessionStorage.getItem('sessionUser'));
console.log(retrievedSessionUser); // Output: { name: "Manoj Kumar", age: 25 }

// Remove an item from SessionStorage
sessionStorage.removeItem('sessionUsername');

// Clear all data from SessionStorage
sessionStorage.clear();
```

## Cookies

### Why Use Cookies?

- Can be sent to the server with every HTTP request, making them suitable for maintaining sessions or authentication tokens.
- Expiry dates can be set to control how long data persists.
- Data can be shared across multiple pages and even across different browser sessions.

### When to Use Cookies?

- When you need to maintain session state between server and client.
- For storing authentication tokens, user preferences, and tracking information.

### How to Use Cookies?

Example Code:

```JS
// Save a cookie
document.cookie = "username=manojofficialmj; expires=Fri, 31 Dec 2024 23:59:59 GMT; path=/";

// Retrieve a cookie
function getCookie(name) {
    const value = `; ${document.cookie}`;
    const parts = value.split(`; ${name}=`);
    if (parts.length === 2) return parts.pop().split(';').shift();
}

const cookieUsername = getCookie('username');
console.log(cookieUsername); // Output: "manojofficialmj"

// Remove a cookie by setting its expiry date to the past
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";

// Clear all cookies (setting them to past date, but path and domain need to be known for each cookie)
document.cookie.split(";").forEach(function(c) {
    document.cookie = c.trim().split("=")[0] +
    "=;expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/";
});
```

# LocalStorage Vs SessionStorage Vs Cookies

| Feature                 | LocalStorage                             | SessionStorage                      | Cookies                                           |
| ----------------------- | ---------------------------------------- | ----------------------------------- | ------------------------------------------------- |
| **Storage Limit**       | ~5MB per origin                          | ~5MB per origin                     | ~4KB per cookie                                   |
| **Expiry**              | Never expires (until explicitly deleted) | Expires when the page session ends  | Can be set to expire at a specific time           |
| **Scope**               | Window/tab                               | Window/tab                          | Browser and server (via HTTP headers)             |
| **Use Cases**           | Persistent data, user preferences        | Temporary data for a single session | Session management, authentication, tracking      |
| **Accessibility**       | Accessible via JavaScript                | Accessible via JavaScript           | Accessible via JavaScript and server-side scripts |
| **Data Sent to Server** | No                                       | No                                  | Yes, with every HTTP request                      |

## Description

This table summarizes the key differences between LocalStorage, SessionStorage, and Cookies. Each storage mechanism has its own strengths and weaknesses, and this table helps to highlight the main features and use cases for each.
