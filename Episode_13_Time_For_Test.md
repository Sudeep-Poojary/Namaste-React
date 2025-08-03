# EPISODE 11 - TIME FOR TEST

## Q1: What are different types for `testing`?
Ans:  Here are the most common types of testing used in the software development lifecycle:


| **Type of Testing**         | **Purpose**                                                                 |
|-----------------------------|------------------------------------------------------------------------------|
| **Unit Testing**            | Tests individual components or functions in isolation.                      |
| **Integration Testing**     | Ensures different modules or services work together correctly.              |
| **End-to-End (E2E) Testing**| Simulates real user scenarios from start to finish across the whole application. |
| **Functional Testing**      | Validates that the software functions according to specified requirements.  |
| **Smoke Testing**           | Basic tests to check whether the major functionalities are working.         |
| **Regression Testing**      | Ensures that new code changes haven't affected existing functionality.      |
| **Acceptance Testing**      | Confirms the system meets business requirements; often done by stakeholders.|
| **Performance Testing**     | Checks speed, responsiveness, and stability under load.                     |
| **Load Testing**            | Measures how the system behaves under heavy user or data load.              |
| **Stress Testing**          | Tests system limits by pushing it beyond its capacity.                      |
| **Usability Testing**       | Evaluates user-friendliness and overall user experience (UX).               |
| **Security Testing**        | Identifies vulnerabilities and weaknesses in the application.               |
| **UI Testing**              | Ensures user interface components render and behave correctly.              |
| **Snapshot Testing**        | Captures component rendering output and compares it to stored snapshots (common in React). |


## Q2: What is `Enzyme`?
Ans: **Enzyme** is a **JavaScript testing utility** for **React**, developed by **Airbnb**. It allows developers to **test and manipulate React components** by providing a simpler and more flexible API for **unit testing**, **shallow rendering**, **mounting**, and **interacting with component trees**.

### Key Features of Enzyme:
- Supports **shallow rendering** (to test components in isolation).
- Enables **full DOM rendering** for lifecycle and interaction testing.
- Can **traverse, manipulate, and simulate events** on components.
- Works with **testing frameworks like Jest or Mocha**.

### Common Use Cases:
- Verifying **component rendering** and **UI structure**
- Testing **props**, **state changes**, and **event handlers**
- Ensuring **component behavior** matches expected outputs

> **Note:** Enzyme is no longer actively maintained for React 18+. For modern React apps, it's recommended to use **React Testing Library** instead.


## Q3: `Enzyme` vs `React Testing Library`
Ans: 

| Feature/Aspect             | Enzyme                                      | React Testing Library (RTL)                          |
|----------------------------|---------------------------------------------|------------------------------------------------------|
| **Developer**              | Airbnb                                     | Kent C. Dodds (Community-driven)                     |
| **Testing Philosophy**     | Tests implementation details                | Tests component behavior from the user's perspective |
| **DOM Rendering**          | Shallow, mount, and full DOM rendering      | Uses real DOM rendering via `@testing-library/dom`   |
| **Ease of Setup**          | Slightly more complex                       | Simpler and lighter setup                            |
| **Event Simulation**       | `.simulate()` method                        | Uses real DOM events like `fireEvent`, `userEvent`   |
| **Selector Style**         | CSS selectors, component names              | Queries like `getByText`, `getByRole`, etc.          |
| **Component Internals**    | Can access and test internal state/methods  | Focuses only on visible UI and behavior              |
| **Learning Curve**         | Easier for class components                 | More intuitive for functional components             |
| **React 18 Support**       | Not actively maintained                   | Fully supported                                   |
| **Recommendation**         | Legacy projects                             | Modern React apps (preferred choice)                 |


>  **Best Practice:** Use **React Testing Library** for testing what the user sees and does. Avoid relying on implementation details.


## Q4: What is `Jest` and why do we use it?
Ans: **Jest** is a **JavaScript testing framework** developed and maintained by **Meta (formerly Facebook)**. It is widely used for testing **React applications**, but also supports testing any JavaScript codebase.

### Why Do We Use Jest?

- **All-in-One Framework**: Comes with test runner, assertion library, mocking support, and code coverage out of the box.
- **Zero Config Setup**: Works out of the box with minimal configuration, especially in React apps (like those created with Create React App).
- **Fast and Parallel Testing**: Runs tests in parallel for improved performance.
- **Snapshot Testing**: Captures UI snapshots and alerts you on unexpected changes.
- **Mocking Capabilities**: Allows mocking functions, modules, and timers.
- **Great Integration with React**: Often used with tools like **React Testing Library** to test React components effectively.

### Common Features:

- `describe()` — groups related tests  
- `test()` or `it()` — defines individual test cases  
- `expect()` — assertions to verify outcomes  
- `jest.fn()` — create mock functions

> Jest is the **default testing framework** for many modern front-end applications and is favored for its simplicity and power.
