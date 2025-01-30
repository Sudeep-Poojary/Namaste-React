# EPISODE 06 - EXPLORING THE WORLD

## Q1: What is `Microservice`?
Ans:  `Microservice` is an architectural style where an application is divided into small, independent services database, server or a UI of the application, that communicate through APIs. Each service focuses on a specific business function, operates autonomously, and can be developed, deployed, and scaled independently.

### Benefits of Microservices:
- `Scalability`: Individual services can be scaled independently based on demand.
- `Flexibility`: Teams can use different technologies or languages for each service.
- `Fault Isolation`: Failures in one service do not impact the entire system.
- `Faster Development`: Teams can work on separate services simultaneously, speeding up development.
- `Easier Maintenance`: Smaller, focused services are easier to debug and update.
- `Continuous Deployment`: Independent services allow for more frequent and isolated updates.

## Q2: What is `Monolith Architecture`?
Ans: `Monolith` architecture is a traditional software design where an entire application is built as a single, unified unit. All components such as the user interface, business logic, and data layer are tightly coupled and run as a single codebase and process. While it is simpler to develop and deploy initially, monoliths can become challenging to scale, maintain, and update as the application grows, since changes often impact the entire system. This architecture suits small, straightforward applications but can hinder agility and scalability in larger systems.

## Q3: What is the difference between `Monolith` and `Microservice`?
Ans:

| **Aspect**               | **Monolith Architecture**                          | **Microservices Architecture**                     |
|--------------------------|--------------------------------------------------|--------------------------------------------------|
| **Structure**            | Single, unified codebase and application.        | Divided into small, independent services.        |
| **Deployment**           | Entire application is deployed as a single unit. | Each service is deployed independently.          |
| **Scalability**          | Scales as a whole, leading to inefficiencies.    | Individual services can be scaled independently. |
| **Flexibility**          | Limited flexibility; tied to one tech stack.     | Each service can use different technologies.     |
| **Fault Isolation**      | A failure in one part can impact the whole system.| Failures are isolated to specific services.      |
| **Development Speed**    | Slower for large teams due to tight coupling.    | Faster, as teams can work on separate services.  |
| **Maintenance**          | Challenging as the application grows.            | Easier due to smaller, focused services.         |
| **Complexity**           | Simpler to develop initially.                    | More complex due to service communication.       |
| **Performance**          | Can perform better initially for small apps.     | Better for large-scale apps with targeted scaling.|
| **Use Case**             | Suitable for small or simple applications.       | Ideal for large, complex, and scalable systems.  |


## Q4: Why do we need a `useEffect` Hook?
Ans: The `useEffect` Hook in React is used to handle side effects in functional components, such as `data fetching through API`, `subscriptions`, `timers`, or `directly manipulating the DOM`. It allows you to run code after the component renders and keeps your code synchronized with external systems or APIs. The hook ensures that effects are properly cleaned up to avoid memory leaks.

### **Syntax**:

```javascript
useEffect(() => {}, [])
```

The `() => {}` is `callback function` and `[]` is called a `empty dependency array`. If anything that we pass (suppose currentState) inside the `[]` it trigger the callback function and changes the state of the application.

```javascript
useEffect(() => {
  // Side effect logic here (e.g., API call, event listener)
  
  return () => {
    // Cleanup logic here (e.g., remove event listener)
  };
}, [dependencies]); // Array of dependencies to control when the effect runs
```
The dependency array determines when the effect re-runs:

- `Empty array ([])`: Runs only once after the initial render.
- `Dependencies specified`: Runs whenever the specified dependencies change.
- `No array`: Runs after every render.

## Q5: What is `Optional Chaining`?
Ans: Optional chaining (`?.`) is a feature in JavaScript that allows you to safely access deeply nested properties of an object without having to check each level for `null` or `undefined`. It prevents runtime errors by returning `undefined` if any part of the chain is `null` or `undefined`, instead of throwing an error.

### **Syntax**:
```javascript
obj?.property
obj?.[expression]
obj?.method()
```

### **Example**:
```javascript
const user = {
  name: "John",
  address: {
    city: "New York",
    postalCode: "10001"
  }
};

console.log(user?.address?.city); // "New York"
console.log(user?.profile?.age); // undefined (safe access, no error)
```

### **Use Cases**:
- Accessing deeply nested object properties.
- Checking for the existence of optional methods before calling them.
- Handling cases where a property or object might not exist.

### **Benefits**:

- Reduces boilerplate code for null/undefined checks.
- Prevents runtime errors in cases of missing properties or methods.

## Q6: What is `Shimmer UI`?
Ans: `Shimmer UI` in React refers to a placeholder loading effect that mimics the appearance of content while it's being fetched or processed. It creates a `shimmering` or `skeleton-like animation` to indicate where the actual content (like text, images, or lists) will appear, improving the perceived performance and user experience. Shimmer UI is commonly used in modern applications to give users a visual clue that content is `loading`, making the interface feel more interactive and responsive.

## Q7: What is the difference between `JS expression` and `JS statement`?
Ans: Here’s the difference between JavaScript expressions and statements:

| **Aspect**          | **JavaScript Expression**                                      | **JavaScript Statement**                                       |
|----------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| **Definition**       | Produces a value (evaluates to a result).                     | Performs an action or task but does not produce a value.       |
| **Usage**            | Can be used wherever a value is expected (e.g., in variables).| Used to define the flow or structure of the program.          |
| **Examples**         | `5 + 3`, `"Hello"`, `x * y`, `function call()`.               | `if`, `for`, `while`, `return`, `let x = 5;`.                 |
| **Return Value**     | Always has a return value.                                    | Does not directly return a value, but may include expressions.|
| **Purpose**          | To compute and return a result.                               | To control program execution or define logic.                 |

### **Example:**
```javascript
// Expression
const sum = 5 + 3; // Produces a value (8)

// Statement
if (sum > 5) {
  console.log("Sum is greater than 5"); // Performs an action
}
```

## Q8: What is `Conditional Rendering`? explain with a code example.
Ans: `Conditional Rendering` in React refers to dynamically rendering components or elements based on certain conditions. It works similarly to conditional statements in JavaScript (`if`, `else`, `ternary operators`, etc.). This technique is commonly used to display different UI elements depending on the application's state or user interactions.

### **Example:**
```javascript
import React, { useState } from 'react';

function App() {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  return (
    <div>
      {isLoggedIn ? ( 
        // Renders when `isLoggedIn` is true
        <h1>Welcome back, User!</h1>
      ) : (
        // Renders when `isLoggedIn` is false
        <h1>Please log in</h1>
      )}

      <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
        {isLoggedIn ? "Log Out" : "Log In"}
      </button>
    </div>
  );
}

export default App;
```

### **Explanation:**
1. `Condition (isLoggedIn):` The UI depends on the isLoggedIn state.
2. `Ternary Operator:` The isLoggedIn state determines which JSX is rendered:
    - If true, it shows a welcome message.
    - If false, it asks the user to log in.
3. `Button:` Toggles the isLoggedIn state when clicked, dynamically updating the rendered content.

Conditional rendering makes the application more interactive and dynamic by showing appropriate UI based on the application's state.

## Q9: What is `CORS`?
Ans: `CORS (Cross-Origin Resource Sharing)` is a security feature in web browsers that allows or `restricts` resources (like APIs or fonts) to be accessed from a different origin (domain, protocol, or port) than the one from which the request originated. By default, browsers block such cross-origin requests to prevent potential security risks, such as cross-site scripting (XSS) or data theft.

To enable cross-origin access, the server must include specific HTTP headers (e.g., `Access-Control-Allow-Origin`) in its responses, explicitly allowing requests from trusted origins. CORS is essential for enabling safe and controlled communication between web applications hosted on different domains.

## Q10: What is `async` and `await`?
Ans: `async` and `await` are modern JavaScript features used to handle asynchronous operations in a more readable and manageable way, compared to traditional approaches like `callbacks` or `.then()` in `Promises`. They are often used in both plain JavaScript and React applications to work with asynchronous tasks, such as fetching data or performing background computations.

### `async`
- Declares a function as asynchronous.
- Ensures that the function returns a Promise.
- Inside an `async` function, you can use `await` to pause execution until a Promise resolves.

### **Syntax:**
```javascript
async function fetchData() {
  return "Data fetched";
}
fetchData().then(console.log); // Logs: "Data fetched"
```

### `await`
- Used inside an `async` function to pause execution until a Promise resolves or rejects.
- Makes asynchronous code appear synchronous, improving readability.

### **Syntax:**
```javascript
async function fetchData() {
  const data = await fetch("https://api.example.com/data");
  const json = await data.json();
  console.log(json);
}
fetchData();
```

### **Usage in React:**
In React, `async` and `await` are commonly used for:

- `Fetching Data`: To retrieve data from APIs in components, often within useEffect or event handlers.
- `Handling Asynchronous Events`: To manage tasks like submitting forms, loading resources, etc.

### **Benefits:**
1. Improves code readability compared to `.then()` chains.
2. Simplifies error handling with `try...catch`.
3. Makes asynchronous code easier to write and debug.

`async` and `await` are essential for managing asynchronous operations efficiently, especially in modern JavaScript and React development.

## Q11: What is the use of `const json = await data.json();` in `getRestaurants()`?
Ans: Use of `const json = await data.json();` in `fetchData()`

The line:

```javascript
const json = await data.json();
```
is used to parse the response from the `API` into a `JavaScript` object.

## **Detailed Explanation:**

1. **`fetch()` Makes a Network Request**
    ```javascript
    const data = await fetch("https://www.swiggy.com/dapi/restaurants/list/v5?lat=19.060587&lng=72.8251294&is-seo-homepage-enabled=true&page_type=DESKTOP_WEB_LISTING");
    ```

    - `fetch()` sends a request to the Swiggy API.

    - The response (`data`) is a ReadableStream that needs to be converted into usable JSON format.

2. **`await data.json()` Parses the Response**

    ```javascript
    const json = await data.json();
    ```
    - `.json()` is a method that extracts the response body and converts it into a JavaScript object.
    - Since `.json()` returns a Promise, `await` ensures that the function waits for the JSON conversion to complete before proceeding.

3. **Why is it Important?**

    - APIs return raw data in JSON format as a string.
    - `data.json()` converts it into a usable JavaScript object that can be accessed using dot notation (`json.data.cards[...]`).
    - Without this step, `data` would be a Response object, not an actual usable data structure.

## **Example Output Structure (Simplified JSON)**
```json
{
  "data": {
    "cards": [
      {}, {}, {}, {},
      {
        "card": {
          "card": {
            "gridElements": {
              "infoWithStyle": {
                "restaurants": [ ... ]
              }
            }
          }
        }
      }
    ]
  }
}
```

This structure is why you use:

```javascript
json?.data?.cards[4]?.card?.card?.gridElements?.infoWithStyle?.restaurants;
```

to extract the restaurant list from the response.

## **Final Purpose in `fetchData()`**
- Extracts and stores restaurant data into `setListOfRestaurants()`.
- Ensures data is available before updating state, preventing runtime errors.

This makes `await data.json();` a crucial step in handling API responses in React. 🚀