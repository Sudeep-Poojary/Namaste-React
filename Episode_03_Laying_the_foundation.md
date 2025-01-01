# EPISODE 03 - LAYING THE FOUNDATION

## Q1: What is `JSX`?
Ans: `JSX (JavaScript XML)` is a syntax extension for JavaScript commonly used with React, a popular JavaScript library for building user interfaces. JSX allows developers to write HTML-like code within JavaScript, making it easier to create and manipulate UI elements. JSX gets compiled into regular JavaScript code, enabling seamless integration with JavaScript logic and facilitating the creation of dynamic and interactive web applications.

### Example 1 using JSX:
```
const myElement = <h1>I Love JSX!</h1>;
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```
### Example 2 Without JSX:
```
const myElement = React.createElement('h1', {}, 'I do not use JSX!');
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(myElement);
```

## Q2: Superpowers of `JSX`
Ans: `JSX`, a syntax extension for JavaScript often used with React, offers several superpowers that enhance web development. First, `JSX` provides a more expressive and intuitive way to write UI components by allowing developers to embed HTML-like syntax directly within JavaScript code. This simplifies the creation and manipulation of complex UI structures, improving readability and maintainability. Additionally, `JSX` facilitates seamless integration of JavaScript expressions and logic within the UI, enabling dynamic content generation and conditional rendering. Furthermore, `JSX` offers performance benefits by enabling the use of tools like Babel to efficiently compile `JSX` code into regular JavaScript, reducing runtime overhead. Its familiarity and ease of use make `JSX` a powerful tool for building modern, interactive web applications.

### Example
```
function greeting(user) {
//JSX
  return <h1>{user}, How are you!!!</h1>;
}
```

## Q3: Role of `type` attribute in script tag? What options can I use there?
Ans: The `type` attribute in a `<script>` tag specifies the media type of the script being referenced. It helps the browser understand how to interpret the content within the script tag.

Common options for the type attribute include:

1. `text/javascript` : It is the basic standard of writing javascript code inside the `<script>` tag.
    ### Syntax
    ```
    <script type="text/javascript"></script>
    ```
2. `text/ecmascript` : this value indicates that the script is following the `EcmaScript` standards.
3. `module`: This value tells the browser that the script is a module that can import or export other files or modules inside it.
4. `text/babel` : This value indicates that the script is a babel type and required babel to transpile it.
5. `text/typescript`: As the name suggest the script is written in `TypeScript`.

For modern JavaScript usage, specifying type="module" is recommended when using ES6 modules to take advantage of browser support and clear module separation.

## Q4: `{TitleComponent}` vs `{<TitleComponent/>}` vs `{<TitleComponent></TitleComponent>}` in `JSX`
Ans: In JSX, `{TitleComponent}` represents the usage of a component directly, `{<TitleComponent/>}` and `{<TitleComponent></TitleComponent>}` both signify the instantiation of the component. However, `{<TitleComponent/>}` is a self-closing tag syntax, while `{<TitleComponent></TitleComponent>}` uses an opening and closing tag explicitly. The choice between them depends on whether the component requires children elements.