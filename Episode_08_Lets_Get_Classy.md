# EPISODE 08 - LET'S GET CLASSY

## Q1: How do you create `Nested Routes` react-router-dom configuration?
Ans: We can create a `Nested Routes` inside a react router configuration as follows:
first call createBrowserRouter for routing different pages
```javascript
const router = createBrowserRouter([
   {
      path: "/", // show path for routing
      element: <Parent />, // show component for particular path
      errorElement: <Error />, // show error component for path is different
      children: [ // show children component for routing
         {
            path: "/path",
            element: <Child />
         }
      ],
   }
])
```
Now we can create a nested routing for `/path` using `children` again as follows:

```javascript
const router = createBrowserRouter([
   {
      path: "/",
      element: <Parent />,
      errorElement: <Error />,
      children: [
         {
            path: "/path",
            element: <Child />,
            children: [ // nested routing for subchild
               {
                  path: "/child",
                  element: <SubChild />,
               }
            ],
         }
      ],
   }
])
```

## Q2: Read about `createHashRouter`, `createMemoryRouter` from React Router docs.
Ans: `createHashRouter` is useful if you are unable to configure your web server to direct all traffic to your React Router application. Instead of using normal URLs, it will use the `hash (#)` portion of the URL to manage the "application URL".
Other than that, it is functionally the same as `createBrowserRouter`.
For more reference [Read more](https://reactrouter.com/en/main/routers/create-hash-router)

`createMemoryRouter` Instead of using the browsers history a memory router manages it's own history stack in memory. It's primarily useful for testing and component development tools like Storybook, but can also be used for running React Router in any non-browser environment.
For more reference [Read more](https://reactrouter.com/en/main/routers/create-memory-router)

## Q3: What is the order of life cycle method calls in `Class Based Components`?
Ans: Following is the order of lifecycle methods calls in `Class Based Components`:
1. constructor()
2. render ()
3. componentDidMount()
4. componentDidUpdate()
5. componentWillUnmount()

![React Lifecycle Methods Diagram](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/ogimage.png)


## Q4: Why do we use `componentDidMount`?
Ans: `componentDidMount()` is a lifecycle method in React class components that runs **once**, after the component is mounted to the DOM. It is commonly used for **fetching API data, setting up event listeners, manipulating the DOM, or starting timers**. Since it executes after the initial render, it ensures that side effects do not block the rendering process. 

For ex. It's the best place to `make API calls`.

> **In functional components, the equivalent method is `useEffect(() => {}, [])`.**  


## Q5: Why do we use `componentWillUnmount`? Show with example.
Ans:

## Q6: (Read) Why do we use `super(props)` in constructor?
Ans:

## Q7: (Read) Why can't we have the `callback function` of `useEffect async`?
Ans: