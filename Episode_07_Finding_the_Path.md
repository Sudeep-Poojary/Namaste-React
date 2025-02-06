# EPISODE 07 - FINDING THE PATH

## Q1: What are various ways to `add images` into our App? Explain with `code` examples.
Ans:

## Q2: What would happen if we do `console.log(useState())`?
Ans:

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
