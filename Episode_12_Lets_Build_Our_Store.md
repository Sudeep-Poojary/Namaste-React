# EPISODE 12 - LET'S BUILD OUR STORE

## Q1: `useContext` vs `Redux`.
Ans:
| Feature                  | `useContext`                             | Redux                                             |
|--------------------------|-------------------------------------------|---------------------------------------------------|
| **Purpose**              | Share state between components            | Centralized global state management               |
| **Setup**                | Simple, minimal boilerplate               | Requires additional setup and configuration       |
| **Scalability**          | Best for small to medium apps             | Suitable for large-scale applications             |
| **Performance**          | May cause re-renders of all consumers     | Offers more granular control over state slices    |
| **Middleware Support**   | Not built-in                              | Supports middleware like redux-thunk, redux-saga  |
| **Dev Tools**            | No dedicated tools                        | Powerful Redux DevTools available                 |
| **Learning Curve**       | Easy to learn and use                     | Steeper learning curve                            |
| **Code Structure**       | Simple and less structured                | Enforces structured code and separation of concerns |
| **State Persistence**    | Not built-in                              | Can be easily integrated                          |

## Q2: Advantage of using `Redux Toolkit` over `Redux`.
Ans: **Advantages of Using Redux Toolkit over Redux**

1. **Less Boilerplate** – Redux Toolkit reduces the amount of code needed for actions, reducers, and store setup.  
2. **Built-in Best Practices** – Encourages best practices like using `immer` for immutability and `createSlice` for logic organization.  
3. **Simplified Store Configuration** – Provides a preconfigured `configureStore` with sensible defaults.  
4. **Integrated Middleware** – Automatically includes middleware like `redux-thunk` for async logic.  
5. **Improved Code Organization** – `createSlice` groups actions and reducers together for better structure.  
6. **Developer Experience** – Better TypeScript support and integration with Redux DevTools.  
7. **Better Performance Patterns** – Encourages efficient update patterns and memoization strategies.  

> **In Summary:** Redux Toolkit makes Redux development faster, cleaner, and easier—especially for larger or more complex applications.

## Q3: Explain `Dispatcher`.
Ans: In **Redux Toolkit**, the concept of a **dispatcher** still exists but is more streamlined and abstracted compared to classic Redux.

- A **dispatcher** is essentially the function that **sends (or dispatches) an action to the Redux store**.
- In Redux Toolkit, this is typically done using the `dispatch()` method provided by the store or made available via hooks like `useDispatch()` in React-Redux.

### **Key Points:**
- You don’t manually deal with dispatcher logic; RTK handles most of it for you.
- When you use an action like `dispatch(increment())`, Redux Toolkit automatically:
  - Sends the action to the store
  - Runs the appropriate reducer
  - Updates the state accordingly

### **Example:**
```js
import { useDispatch } from "react-redux";
import { addItem } from "../utils/cartSlice";

const ItemList = ({ items }) => {
  const dispatch = useDispatch();

  const handleAddItem = (item) => {
    // Dispatch an action
    dispatch(addItem(item));
  };

  return (
    <div>Item List</div>
  );
};

export default ItemList;
```

> **In Summary:** In Redux Toolkit, the dispatcher is still used to trigger state changes, but the boilerplate is reduced and the API is more intuitive—usually accessed via `useDispatch()` in components.

## Q4: Explain `Reducer`.
Ans: In **Redux Toolkit (RTK)**, a **reducer** works the same as in Redux — it determines how the state should change in response to actions — but Redux Toolkit makes creating reducers **simpler, cleaner, and more efficient**.

### **Key Enhancements in RTK Reducers:**
- Uses `createSlice()` to automatically generate **reducers and action creators**.
- Can **mutate state directly** inside reducers using **Immer.js**, which handles immutability under the hood.
- Reduces **boilerplate** code by bundling actions and reducers together.

### **Example:**
```js
import { createSlice } from "@reduxjs/toolkit";

const cartSlice = createSlice({
  name: "cart",

  initialState: {
    items: [],
  },

  reducers: {
    addItem: (state, action) => {
      state.items.push(action.payload);
    },

    removeItem: (state, action) => {
      state.items.pop();
    },

    clearCart: (state, action) => {
      state.items.length = 0;
    },
  },
});

export const { addItem, removeItem, clearCart } = cartSlice.actions;

export default cartSlice.reducer;

```

> **In Summary:** Reducers in Redux Toolkit are more concise, easier to write, and leverage Immer for safe state mutation.

## Q5: Explain `slice`.
Ans: In **Redux Toolkit**, a **slice** is a collection of Redux **reducer logic** and **actions** for a specific feature or part of the application state.

A slice is created using the `createSlice()` function, which automatically:
- Generates **action creators**
- Defines **reducer functions**
- Assigns a **slice name**
- Sets an **initial state**

### **Key Features of a Slice:**
- Combines actions and reducers in one place for better code organization.
- Uses **Immer** under the hood, so you can write “mutating” code that’s actually immutable.
- Reduces boilerplate code significantly compared to traditional Redux.

### **Example:**
```js
import { createSlice } from "@reduxjs/toolkit";

const cartSlice = createSlice({
  name: "cart",

  initialState: {
    items: [],
  },

  reducers: {
    addItem: (state, action) => {
      state.items.push(action.payload);
    },

    removeItem: (state, action) => {
      state.items.pop();
    },

    clearCart: (state, action) => {
      state.items.length = 0;
    },
  },
});

export const { addItem, removeItem, clearCart } = cartSlice.actions;

export default cartSlice.reducer;
```

> **In Summary:** A slice in Redux Toolkit is an all-in-one structure that includes the reducer logic and actions for a specific part of your state, making state management more efficient and organized.

## Q6: Explain `selector`.
Ans: A **selector** in Redux Toolkit (and Redux in general) is a **function** that **extracts and returns a specific piece of state** from the Redux store. It helps **decouple component logic from the structure of the state**, making your code more modular, readable, and easier to maintain.


### **Why Use Selectors?**

- Avoids repetitive state access logic in components  
- Improves readability and reusability  
- Makes it easier to refactor state shape  
- Can be memoized for performance optimization (e.g., using `reselect`)

### **Example:**

```js
import { useDispatch, useSelector } from "react-redux";
import ItemList from "./ItemList";
import { clearCart } from "../utils/cartSlice";

const Cart = () => {
  const cartItems = useSelector((store) => store.cart.items);
  console.log(cartItems);

  const dispatch = useDispatch();

  const handleClearCart = () => {
    dispatch(clearCart());
  };

  return (
    <div>
        <h1>Cart</h1>
        <button onClick={handleClearCart}>Clear Cart</button>
      </div>

      <div>
        {cartItems.length === 0 && (<h1>Your Cart is Empty!!!</h1>)}
        <ItemList items={cartItems} />
      </div>
  );
};

export default Cart;
```

> **In Summary:** A selector is a helper function used to read values from the Redux state, helping to keep components clean and focused on rendering.

## Q7: Explain `createSlice` and the configuration it takes.
Ans: `createSlice` is a function provided by **Redux Toolkit** that simplifies the process of creating **Redux reducers, actions**, and **action creators**. It groups them into a single "slice" of the state.

### **Why Use `createSlice`?**

- Reduces boilerplate code  
- Automatically generates action types and creators  
- Integrates **Immer** to allow writing mutable-style logic safely  
- Organizes state logic in a modular way

### **Configuration Object (`createSlice({...})`)**

The `createSlice` function takes a configuration object with the following properties:

| Key                | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `name`              | A string that defines the slice name. Used in generated action type.        |
| `initialState`      | The initial state for the slice.                                             |
| `reducers`          | An object of reducer functions that define how the state is updated.        |
| `extraReducers` *(optional)* | To handle actions from other slices or async actions like `createAsyncThunk`. |

### **Example:**

```js
import { createSlice } from "@reduxjs/toolkit";

const cartSlice = createSlice({
  name: "cart",

  initialState: {
    items: [],
  },

  reducers: {
    addItem: (state, action) => {
      state.items.push(action.payload);
    },

    removeItem: (state, action) => {
      state.items.pop();
    },

    clearCart: (state, action) => {
      state.items.length = 0;
    },
  },
});

export const { addItem, removeItem, clearCart } = cartSlice.actions;

export default cartSlice.reducer;
```

> **In Summary:** `createSlice` is a powerful abstraction in Redux Toolkit that combines state, reducers, and actions into a single, manageable module—streamlining **Redux development**.