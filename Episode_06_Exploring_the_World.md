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
Ans:

## Q8: What is `Conditional Rendering`? explain with a code example.
Ans:

## Q9: What is `CORS`?
Ans:

## Q10: What is `async` and `await`?
Ans:

## Q11: What is the use of `const json = await data.json();` in `getRestaurants()`?
Ans: