# EPISODE 11 - DATA IS THE NEW OIL

## Q1: What is `prop drilling`?
Ans: `Prop drilling` is the process of **passing data (props)** from a parent component to deeply nested child components. This happens when intermediate components pass props that they **don’t directly need** just to get the data to a deeply nested component.  

### **Issues with Prop Drilling:**  
- Increases **complexity** and makes the code harder to maintain.  
- Causes **performance issues** if too many components re-render unnecessarily.  

> **Solution:** Context API or state management libraries (like Redux or Zustand) can help avoid prop drilling.  


## Q2: What is `lifting the state up`?
Ans: **Lifting the state up** is a pattern in React where **state** is moved from child components to their **closest common parent** to allow multiple child components to share and modify the same state.  

### **When to Use It:**  
- When two or more child components need to **synchronize data**.  
- To **avoid prop drilling** and manage state in a centralized location.  

> **Key Benefit:** It improves **state management** and ensures data consistency between related components. 


## Q3: What is `Context Provider` and `Context Consumer`?
Ans: 
- **Context Provider** – Provides a **context value** to all the child components, allowing them to access the shared state or data without prop drilling. It is defined using `<MyContext.Provider value={data}>`.  
- **Context Consumer** – Consumes the **context value** provided by the `Provider`, allowing child components to use the shared data. It is used with `<MyContext.Consumer>` or the `useContext` hook.  

> **Key Benefit:** Context Provider and Consumer simplify **state management** and avoid the need for passing props through multiple components.


## Q4: If you don’t pass a value to the `provider` does it take the default value?
Ans: Yes, if no value is passed to the `Context.Provider`, the **default value** specified during `createContext()` is used. The default value is provided as an argument to `createContext(defaultValue)` and is only used when a component consumes the context **without a matching provider** in the component tree.  

> **Note:** If a `Provider` is present but no value is passed, the context value will be `undefined` or the fallback value depending on the implementation.

