# EPISODE 07 - FINDING THE PATH

## Q1: What are various ways to `add images` into our App? Explain with `code` examples.
Ans: 
### **Various Ways to Add Images into a React App**
In React, images can be added in multiple ways depending on their source and usage. Below are some common approaches with examples:

---

### **1. Importing Images Locally (Static Assets)**
This method is used for images stored in the `src` folder.

**Example:**
```javascript
import React from "react";
import myImage from "./assets/image.jpg"; // Importing an image

function App() {
  return (
    <div>
      <h2>Local Image</h2>
      <img src={myImage} alt="Local Asset" width="300" />
    </div>
  );
}

export default App;
```

✅ Best for: Static images bundled with the app.

❌ Not ideal for: Dynamic or user-uploaded images.

---

### **2. Using Images from the `public` Folder**

The `public` folder is not processed by Webpack, so images can be referenced directly with a relative URL.

**Example:**
```javascript
function App() {
  return (
    <div>
      <h2>Public Folder Image</h2>
      <img src="/images/example.jpg" alt="Public Asset" width="300" />
    </div>
  );
}

export default App;
```

✅ Best for: Static images that don't change frequently.

❌ Not optimized: Webpack doesn’t process these images.

---

### **3. Using an Image URL (External Source)**
You can use an image hosted on a CDN, API, or any external URL.

**Example:**
```javascript
function App() {
  return (
    <div>
      <h2>External Image</h2>
      <img src="https://via.placeholder.com/300" alt="External Asset" width="300" />
    </div>
  );
}

export default App;
```

✅ Best for: Remote images, user-uploaded content, and dynamic content.

❌ Requires internet: Cannot be used offline.

---

### **4. Using Images from State or Props (Dynamic URLs)**
If image URLs are stored in state or passed as props, they can be dynamically rendered.

**Example:**
```javascript
import React, { useState } from "react";

function App() {
  const [imageUrl, setImageUrl] = useState("https://via.placeholder.com/300");

  return (
    <div>
      <h2>Dynamic Image</h2>
      <img src={imageUrl} alt="Dynamic Asset" width="300" />
    </div>
  );
}

export default App;
```

✅ Best for: Dynamic content, such as images from APIs or user uploads.

---

### **5. Using `require()` (CommonJS Syntax)**
Instead of `import`, you can use `require()` to dynamically load images.

**Example:**
```javascript
function App() {
  return (
    <div>
      <h2>Require Image</h2>
      <img src={require("./assets/image.jpg")} alt="Require Asset" width="300" />
    </div>
  );
}

export default App;
```

✅ Best for: When dynamic imports are needed.

❌ Less commonly used: import is preferred in modern React.

---

### **Conclusion**

| **Method**           | **Best For**                            | **Drawback**                     |
|----------------------|----------------------------------------|----------------------------------|
| **Importing Images** | Static assets bundled with the app    | Not for dynamic content         |
| **Public Folder**    | Global assets accessible by URL       | No Webpack optimization         |
| **External URLs**    | Remote/CDN images, user-generated content | Requires internet          |
| **State/Props**      | Dynamically changing images           | Needs state management          |
| **Require()**        | Dynamically loading local images      | Less flexible than `import`     |
 
Each method has its use case, and the choice depends on whether the image is static, dynamic, or remotely hosted.

## Q2: What would happen if we do `console.log(useState())`?
Ans: If you execute `console.log(useState())` without passing an initial value, React will throw an error because hooks **must be called inside a functional component or a custom hook**, not directly in the global scope or outside a component.  

However, if used correctly inside a functional component like `console.log(useState(0))`, it will log an **array with two elements**:  
1. **Current state value** (e.g., `0` if initialized as `useState(0)`).  
2. **State setter function** (a function to update the state).  

### **Example Output:**
```javascript
[0, ƒ] // [state value, state updater function]
```
Calling `useState()` without an initial value (`useState()`) will return `[undefined, ƒ]`. 

## Q3: How will `useEffect` behave if we `don't add` a `dependency array`?
Ans: If you **do not** add a dependency array (`[]`) to `useEffect`, the effect **runs after every render**, including **initial mount** and **every re-render**. This means:  

1. **Runs on Component Mount** – Executes once when the component is first rendered.  
2. **Runs on Every Re-Render** – Any state or prop change that triggers a re-render will re-execute the `useEffect` callback.  

### **Example: `useEffect` without a Dependency Array**
```javascript
import React, { useState, useEffect } from "react";

function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Effect is running...");
  });

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase Count</button>
    </div>
  );
}

export default App;
```

### **Behavior in This Example**
- The `console.log("Effect is running...")` will be executed on the initial render.
- Every time `count` is updated (by clicking the button), `useEffect` runs again since there is no dependency array to control execution.

### **When to Avoid Missing the Dependency Array?**

❌ If the effect performs expensive operations (e.g., API calls, event listeners), it can cause performance issues due to frequent executions.

✅ To control execution, you should use a dependency array:

- Run once on mount → `useEffect(() => { ... }, [])`
- Run only when specific dependencies change → `useEffect(() => { ... }, [dependency])`

Thus, not adding a dependency array makes `useEffect` behave like a function that executes on every render, which may not always be desirable.

## Q4: What is `SPA`?
Ans: A `Single Page Application (SPA)` is a web application that dynamically updates the content of a single HTML page without requiring full-page reloads. Instead of loading new pages from the server, `SPAs` fetch data asynchronously and update the user interface using JavaScript.

### **How SPAs Work?**
- When a user visits a `SPA`, the browser loads an initial HTML, CSS, and JavaScript bundle.
- Navigation between `pages` happens `without reloading`, as JavaScript manipulates the DOM and fetches necessary data via `APIs` (typically using fetch or Axios).
- The browser updates only `specific parts` of the UI dynamically, leading to a faster and smoother user experience.

### **Examples of SPAs**
- Gmail
- Facebook
- Twitter
- Netflix
- Trello
- React, Angular, Vue-based applications


## Q5: What is the difference between `Client Side Routing` and `Server Side Routing`?
Ans:
### **Difference Between Client-Side Routing and Server-Side Routing in Web Development**

| Feature              | **Client-Side Routing (CSR)**                                  | **Server-Side Routing (SSR)**                                  |
|----------------------|---------------------------------------------------------------|----------------------------------------------------------------|
| **Definition**       | Handles routing within the browser without refreshing the page. | Routes are handled by the server, requiring a full page reload. |
| **Navigation Speed** | Faster, as only necessary content is updated.                 | Slower, as the server processes each request before rendering. |
| **Performance**      | Faster user experience after the initial load.                | Faster initial load, but slower subsequent navigations.        |
| **SEO Friendliness** | Poorer SEO (unless using SSR techniques like Next.js).        | Better SEO, as search engines can easily crawl server-rendered pages. |
| **Page Load Type**   | Loads once and updates dynamically without full refresh.       | Fetches a new HTML page for every request.                    |
| **Example**         | React with React Router (`react-router-dom`).                  | Traditional PHP, ASP.NET, or frameworks like Express.js.       |
| **Best For**        | Single Page Applications (SPAs) where fast navigation is needed. | Multi-page applications (MPAs) where SEO and content indexing are crucial. |
