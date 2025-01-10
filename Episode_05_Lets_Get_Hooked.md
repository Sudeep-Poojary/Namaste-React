# EPISODE 05 - LETS GET HOOKED!

## Q1: What is the difference between `Named export`, `Default export`, and `* as export`?

Ans:

1. **Named Export/Import**:

   - You export specific variables, functions, or objects by name.
   - Syntax:
     ```javascript
     export const Component1 = () => {};
     export const Component2 = () => {};
     ```
   - Import must match the exact names:
     ```javascript
     import { Component1, Component2 } from "./module";
     ```

2. **Default Export/Import**:

   - You export a single default value (e.g., function, class, object).
   - Syntax:
     ```javascript
     const Component = () => {};
     export default Component;
     ```
   - Import can use any name:
     ```javascript
     import Component from "./module";
     ```

3. **`* as` Export/Import**:

   - You export specific variables, functions, or objects by name.

     ```javascript
     export const Component1 = () => {};
     export const Component2 = () => {};
     ```

   - Imports all named exports from a module under a namespace.
   - Syntax:
     ```javascript
     import * as AllComponents from "./module";
     ```
   - Access exports with:
     ```javascript
     <AllComponents.Component1 />
     <AllComponents.Component2 />
     ```

## Q2: What is the importance of `config.js` file?

Ans: A `config.js` file is important for managing configuration settings centrally. It typically contains environment-specific values such as API endpoints, feature flags, or keys for external services. This approach improves maintainability by separating configuration from code logic, making it easier to update settings without modifying the core codebase. It also supports scalability by allowing you to define different configurations for development, testing, and production environments.

### Example of `config.js`

```javascript
const config = {
  API_BASE_URL: process.env.REACT_APP_API_BASE_URL || "http://localhost:3000",
  TIMEOUT: 5000,
  FEATURE_FLAG: true,
};

export default config;
```

### Usage of `config.js`

```javascript
import config from "./config";

fetch(`${config.API_BASE_URL}/endpoint`)
  .then((response) => response.json())
  .catch((error) => console.error("Error:", error));
```

## Q3: What are `React Hooks`?

Ans: It's simply a regular JavaScript function. However, it
becomes powerful when used within React, as it's provided to us
by React itself. These pre-built functions have underlying logic
developed by React developers. When we install React via npm, we
gain access to these superpowers.

**Here are some of the most utilized Hooks:**

- `useState`: To manage states. Returns a stateful value and an updater function to update it.
- `useEffect`: To manage side-effects like API calls, subscriptions, timers, mutations, and more.
- `useContext`: To return the current value for a context.
- `useReducer`: A useState alternative to help with complex state management.
- `useCallback`: It returns a memorized version of a callback to help a child component not re-render unnecessarily.
- `useMemo`: It returns a memoized value that helps in performance optimizations.
- `useRef`: It returns a ref object with a current property. The ref object is mutable. It is mainly used to access a child component imperatively.
- `useLayoutEffect`: It fires at the end of all DOM mutations. It's best to use useEffect as much as possible over this one as the useLayoutEffect fires synchronously.
- `useDebugValue`: Helps to display a label in React DevTools for custom hooks.

## Q4: Why do we need `useState` Hook?

Ans: The `useState` Hook in React is essential for managing state in functional components. It allows components to store and update `dynamic` data, enabling them to reactively render changes in response to user interactions or other events. Without useState, functional components would remain stateless, limiting their ability to handle dynamic behaviors. By using useState, developers can create interactive and responsive UIs, as it provides a straightforward way to initialize state, update it through setter functions, and trigger re-renders whenever the state changes. This Hook is a cornerstone of React's functional programming paradigm, replacing the need for class-based components to manage state.

### Example Workflow of `useState` Hook:

- `Initial Render`: A component is rendered for the first time, generating an initial Virtual DOM.
- `State Update`: The useState setter function is called (e.g., in response to a button click), updating the component’s state.
- `Re-render and Diffing`: React re-runs the component function, creates a new Virtual DOM, and uses the diffing algorithm to compare it with the previous Virtual DOM.
- `Minimal Updates`: React efficiently updates only the parts of the real DOM that need to change.

### Implementation of `useState` Hook:

```javascript
const [listOfRestaurants, setListOfRestaurants] = useState(resList);
```
