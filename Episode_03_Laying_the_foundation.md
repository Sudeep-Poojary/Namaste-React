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
Ans: `JSX`, a syntax extension for JavaScript often used with React, offers several superpowers that enhance web development. First, JSX provides a more expressive and intuitive way to write UI components by allowing developers to embed HTML-like syntax directly within JavaScript code. This simplifies the creation and manipulation of complex UI structures, improving readability and maintainability. Additionally, JSX facilitates seamless integration of JavaScript expressions and logic within the UI, enabling dynamic content generation and conditional rendering. Furthermore, JSX offers performance benefits by enabling the use of tools like Babel to efficiently compile JSX code into regular JavaScript, reducing runtime overhead. Its familiarity and ease of use make JSX a powerful tool for building modern, interactive web applications.

## Q3: Role of `type` attribute in script tag? What options can I use there?
Ans:

## Q4: `{TitleComponent}` vs `{<TitleComponent/>}` vs `{<TitleComponent></TitleComponent>}` in `JSX`
Ans: