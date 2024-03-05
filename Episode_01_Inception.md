# EPISODE 01 - INCEPTION

## Q1: What is `Emmet`?
Ans: Emmet is a web development tool that allows for faster and more efficient HTML and CSS coding. It uses abbreviations and shortcuts to generate complex code snippets quickly. Originally known as Zen Coding, Emmet is widely used in various code editors and IDEs, providing developers with a streamlined workflow for creating and editing markup and styling in web projects.


## Q2: Difference between a `Library and Framework`?
Ans: A library is a collection of pre-written code that developers can use for specific tasks, while a framework is a more comprehensive architecture that provides a structure for building applications. With a library, developers call specific functions when needed, while a framework dictates the overall flow of the application and may require developers to adhere to its conventions.

## Q3: What is `CDN`? Why do we use it?
Ans: A Content Delivery Network (CDN) is a network of distributed servers that deliver web content, such as images, stylesheets, and scripts, to users based on their geographic location. CDNs enhance website performance by reducing latency and speeding up content delivery, resulting in faster page load times. This helps improve user experience, SEO rankings, and overall website reliability by distributing content across multiple servers globally.

## Q4: Why is `React known as React`?
Ans: React, a JavaScript library for building user interfaces, is named "React" because of its focus on efficiently updating and rendering user interface components in response to changes in application state. The name reflects the library's core philosophy of reacting to state changes and updating the UI accordingly, providing a declarative and efficient way to build interactive and dynamic web applications.

## Q5: What is `crossorigin in script tag`?
Ans: The crossorigin attribute in a script tag is used to specify how the browser should handle cross-origin requests when fetching the script file. It is commonly used with external scripts loaded from different domains. Setting crossorigin="anonymous" allows the browser to make requests without including credentials, improving security, while crossorigin="use-credentials" includes credentials in the requests. This attribute helps prevent security issues related to cross-origin resource sharing (CORS).

## Q6: What is difference between `React and ReactDOM`?
Ans: React is a JavaScript library for building user interfaces, while ReactDOM is a specific package within the React ecosystem responsible for interacting with the DOM (Document Object Model). React provides the core functionality for defining and managing components, state, and props, while ReactDOM handles the rendering of these components in the browser by updating the DOM efficiently. In summary, React focuses on the UI components and their logic, while ReactDOM deals with the integration of React with the actual HTML DOM.

## Q7: What is difference between `react.development.js` and `react.production.js` files via `CDN`?
Ans: The react.development.js file is intended for development purposes and includes additional warnings and debugging information to aid developers. On the other hand, the react.production.js file is optimized for production environments, with minimized code size and removed debugging information to improve performance. When using React via CDN in a production setting, it is recommended to include react.production.js for a more efficient and smaller bundle size.

## Q8: What is `async and defer`?
Ans: async and defer are attributes used with the `<script>` tag in HTML.

Async: When the async attribute is present, the script is executed asynchronously, allowing it to load in the background while the HTML parsing continues. The script is executed as soon as it's downloaded, which may not maintain the order in which scripts appear in the HTML.

Defer: The defer attribute also allows scripts to load asynchronously, but they will only execute after the HTML parsing is complete. Multiple scripts with defer will execute in the order they appear in the HTML, ensuring proper dependency handling.

Both attributes are used to improve page loading performance by allowing the browser to continue parsing HTML without waiting for the scripts to download and execute.
