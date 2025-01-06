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
Ans:

## Q3: What are `React Hooks`?
Ans:

## Q4: Why do we need `useState` Hook?
Ans: