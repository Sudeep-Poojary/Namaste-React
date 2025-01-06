# EPISODE 02 - IGNITING OUR APP

## Q1: What is `NPM`?
Ans: It is a tool used for package management and the default package manager for Node projects. `NPM is installed when NodeJS` is installed on a machine. It comes with a command-line interface (CLI) used to interact with the online database of NPM. This database is called the NPM Registry, and it hosts public and private 'packages.' To add or update packages, we use the NPM CLI to interact with this database. 
- `npm` alternative is `yarn`

- Initialation of `npm`
```javascript
npm init
```
`npm init -y` can be used to skip the setup step, `npm` takes care of it and creates the `package.json` json file automatically , but without configurations.

## Q2: What is `Parcel/Webpack`? Why do we need it?
Ans: Parcel/Webpack is type of a web application bundler used for development and productions purposes or power our application with different type functionalities and features. It offers blazing fast performance utilizing multicore processing, and requires zero configuration. Parcel can take any type of file as an entry point, but an HTML or JavaScript file is a good place to start. Parcel/Webpack are type of bundlers that we use to power our application with different type functionalities and features.

### `Parcel Features`:
* HMR (Hot Module Replacement) - parcel keeps track of file changes via file watcher algorithm and renders the changes in the files
* File watcher algorithm - made with C++
* Minification
* Cleaning our code
* DEV and production Build
* Super fast building algorithm
* Image optimization
* Caching while development
* Compresses
* Compatible with older version of browser
* HTTPS in dev
* Port Number
* Consistent hashing algorithm
* Zero Configuration
* Automatic code splitting

### Installation Commands:
- Install:
```javascript
npm install -D parcel
```
`-D` is used for development and as a development dependency.

- Parcel Commands :
    - For development build:
    ```javascript
    npx parcel <entry_point> 
    ```
    - For production build :
    ```javascript
    npx parcel build <entry_point> 
    ```

## Q3: What is `.parcel-cache`?
Ans: The `.parcel-cache` directory is created by Parcel, a web application bundler, to store cached data and intermediate build artifacts. It helps improve build performance by avoiding unnecessary reprocessing of files. The cache directory allows Parcel to quickly reuse previously computed results during subsequent builds, reducing the time it takes to generate the final bundled output for a web application.

## Q4: What is `npx` ?
Ans: `npx` is a tool that is used to execute the packages. It comes with the `npm`, when you installed npm above 5.2.0 version then automatically `npx` will installed. It is an npm package runner that can execute any package that you want from the `npm` registry without even installing that package.

## Q5: What is difference between `dependencies` vs `devDependencies`?
Ans: In the context of a `Node.js` project's `package.json` file:

`Dependencies`: These are packages required for the application to run in production. They are installed with the command `npm install` and include modules necessary for the actual functionality of the application.

`devDependencies`: These are packages needed only during development, such as testing frameworks or build tools. They are installed with the command `npm install --save-dev` and are not necessary for the production runtime of the application. Including these ensures that developers have the required tools to work on the project, but they don't contribute to the application's production footprint.

## Q6: What is `Tree Shaking`?
Ans: `Tree shaking` is a technique used in JavaScript bundlers like Webpack to eliminate dead or unused code during the bundling process. It involves analyzing the code's dependency tree and removing unreachable or unreferenced modules and functions. This helps reduce the size of the bundled JavaScript file, improving application performance by eliminating unnecessary code that would otherwise be sent to the browser. Tree shaking is particularly effective in optimizing the production build of applications and libraries.

## Q7: What is `Hot Module Replacement`?
Ans: `Hot Module Replacement (HMR)` is a feature in JavaScript bundlers like Webpack that allows developers to update modules in an application without requiring a full page reload. It enables real-time code updates and preserves the application state, making development more efficient by reducing the need for manual page refreshes.

## Q8: List down your favourite `5 superpowers of Parcel and describe any 3` of them in your own words.
Ans: 5 superpowers of Parcel:

- `HMR (Hot Module Replacement)` - adds, or removes modules while an application is running, without a full reload.
- `File watcher algorithm` - File Watchers monitor directories on the file system and perform specific actions when desired files appear.
- `Minification` - Minification is the process of minimizing code and markup in your web pages and script files.
- `Image optimization`
- `Caching while development`

## Q9: What is `.gitignore`? What should we add and not add into it?
Ans: The `.gitignore file` is a text file that tells `Git` which files or folders to `ignore` in a project during `commit to the repository`.
The types of files you should consider adding to a .gitignore file are any files that do not need to get committed. for example, For security, the security key files and API keys should get added to the gitignore.
`package-lock.json` should `not add` into your `.gitignore` file.

The entries in this file can also follow a matching pattern.
```javascript
* is used as a wildcard match
/ is used to ignore pathnames relative to the .gitignore file
# is used to add comments to a .gitignore file
```
This is an example of what the .gitignore file could look like:
```javascript
# Ignore Mac system files
.DS_store

# Ignore node_modules folder
node_modules

# Ignore all text files
*.txt

# Ignore files related to API keys
.env

# Ignore SASS config files
.sass-cache
```

## Q10: What is the difference between `package.json` and `package-lock.json`?
Ans: `package.json` contains metadata about a Node.js project, including its dependencies and scripts. `package-lock.json` is an automatically generated file that provides specific version information for each dependency, ensuring consistent installations across different environments. While `package.json` describes the project, `package-lock.json` locks down the exact versions of dependencies to maintain reproducibility in installations.

## Q11: Read about: ^ - caret and ~ - tilda
Ans: **~** or **^** in `package.json` file :
These are used with the versions of the package installed.

For example  in `package.json` file:
```javascript
"dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  }
```

* **~** : `Approximately equivalent to version`, will update you to all future patch versions, without incrementing the minor version.
* **^** : `Compatible with version`, will update you to all future minor/patch versions, without incrementing the major version.

> If none of them is present, that means only the version specified in `package.json` file is used in the development.

## Q12: Why should I not modify `package-lock.json`?
Ans: Modifying `package-lock.json` is generally discouraged because it's an automatically generated file that records the specific versions of dependencies installed. Altering it manually may lead to inconsistencies in dependency versions, potentially causing issues with collaboration and deployment. It's best to let npm manage and update the `package-lock.json` file to ensure accurate and reproducible installations across different environments.

## Q13: What is `node_modules` ? Is it a good idea to push that on git?
Ans: `node_modules` is a directory where Node.js stores project dependencies. It is not recommended to push the `node_modules` folder to Git as it can be large and contains files that can be regenerated using the project's `package.json` and `package-lock.json` files. Instead, it's common practice to include a `.gitignore` file to exclude `node_modules` from version control, and developers can install dependencies locally using `npm install` or `yarn install` based on the project's package manager.

## Q14: What is the `dist` folder?
Ans: The `/dist` folder contains the minimized version of the source code. The code present in the `/dist` folder is actually the code which is used on production web applications. Along with the minified code, the `/dist` folder also comprises of all the compiled modules that may or may not be used with other systems.

## Q15: What is `browserlists`? (Read about dif bundlers: vite, webpack, parcel)
Ans: `Browserslist` is a tool that allows specifying which browsers should be supported in your frontend app by specifying "queries" in a config file. It's used by frameworks/libraries such as React, Angular and Vue, but it's not limited to them.