# EPISODE 05 - LETS GET HOOKED!

## Q1: What is the difference between `Named export`, `Default export`, and `* as export`?
Ans: 
1. **Named Export/Import**:  
   - You export specific variables, functions, or objects by name.  
   - Syntax: 
     ```javascript
     export const Component1 = () => {}
     export const Component2 = () => {}
     ```
   - Import must match the exact names: 
     ```javascript
     import { Component1, Component2 } from './module';
     ```

2. **Default Export/Import**:  
   - You export a single default value (e.g., function, class, object).  
   - Syntax: 
     ```javascript
     const Component = () => { }
     export default Component;
     ```
   - Import can use any name: 
     ```javascript
     import Component from './module';
     ```

3. **`* as` Export/Import**:  
    - You export specific variables, functions, or objects by name.

      ```javascript
       export const Component1 = () => {}
       export const Component2 = () => {}
      ```

   - Imports all named exports from a module under a namespace.  
   - Syntax: 
     ```javascript
     import * as AllComponents from './module';
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
  API_BASE_URL: process.env.REACT_APP_API_BASE_URL || 'http://localhost:3000',
  TIMEOUT: 5000,
  FEATURE_FLAG: true,
};

export default config;
```

### Usage of `config.js`

```javascript
import config from './config';

fetch(`${config.API_BASE_URL}/endpoint`)
  .then(response => response.json())
  .catch(error => console.error('Error:', error));
```
## Q3: What are `React Hooks`?
Ans:

## Q4: Why do we need `useState` Hook?
Ans: