# `Learn React Js`

## 1. What is a CDN?

- **A Content Delivery Network or Content Distribution Network**: "(CDN) is a distributed network of servers that helps deliver content faster by serving it from the nearest location to the user. It improves performance, reduces server load, enhances security, and ensures better availability of web applications."

## 2. Why do we use a CDN?

- **Faster Load Times:** Since the content is served from the nearest server, it reduces latency and improves page speed.
- **Reduced Server Load:** CDN distributes traffic across multiple servers, preventing overloading of the origin server.
- **Better Availability & Reliability:** Even if one server goes down, another server in the network can serve the content.
- **Improved Security:** CDNs provide DDoS protection, secure data transfer, and reduce the risk of cyberattacks.
- **SEO Benefits:** Faster load times improve user experience, which can positively impact search engine rankings.

---

## 2. What is crossorigin and why do we use it in React CDN ?

### crossorigin

The crossorigin attribute is used in HTML <script> and <link> tags to handle cross-origin requests (i.e., requests made to a different domain). It tells the browser how to handle CORS (Cross-Origin Resource Sharing) when loading external resources like scripts, stylesheets, and images.

### Why do we use crossorigin in React CDN

#### When using React via a CDN (e.g., loading React from a public URL like "https://unpkg.com/react"), the crossorigin attribute ensures:

- **Proper Error Handling in DevTools:** Without crossorigin="anonymous", if there's an error in a React script loaded from a CDN, the browser may block the error details due to security policies.With crossorigin="anonymous", the browser allows detailed error messages, helping in debugging.
- **Optimized Performance with Caching:** If multiple websites load React from the same CDN with crossorigin="anonymous", browsers can reuse the cached version instead of downloading it again.
- **Security & CORS Compliance:** It ensures that external scripts follow CORS policies, preventing unauthorized access to user data.

---

## 4. What is react.development.js and react-dom.development.js?

### When using React via a CDN, you will find two main JavaScript files:

- **react.development.js:** This file is the core React library for development mode, This file contains the whole code of React which is written in JavaScript
- **react-dom.development.js:** The library responsible for rendering React components in the browser DOM (for web applications).

---

## 5. What is the difference between react.development.js and react.production.js via CDN ?

- **react.development.js:** Used for development (debugging-friendly).
- **react.production.js:** Used for production (optimized for performance).

### Example: Using React via CDN
```
<!-- Development Mode (for debugging) -->
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

<!-- Production Mode (for performance) -->
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>

```
---

## 6. What is the difference between a framework and a library ?

### framework

- **Definition**: A collection of functions and utilities that developers can call when needed.
- **Control**: Developer controls when and how to use the library.
- **Flexibility**: More flexible; can be used with different frameworks.
- **Examples**: ReactJS (Library), jQuery, Axios

### Library

- **Definition**: A complete structure that provides rules, architecture, and tools to build applications.
- **Control**: Framework controls the flow; the developer follows its structure.
- **Flexibility**: Less flexible; enforces a specific way of building apps.
- **Examples**: Angular, Next.js, Django, Spring Boot

---

## 7. Why is React named “React” ?

- React is named "React" because it is designed to react efficiently to changes in data and update the UI dynamically.

### Reason Behind the Name

- Efficient UI Updates
- Virtual DOM Optimization
- Reactive Programming Approach: meaning the UI updates in response to state changes.

---

## 8. What is the difference between React and React-dom ?

-**React** (react) is the core library used for building UI components and handling state. -**React-DOM** (react-dom) is specifically for rendering React components into the browser’s DOM.

- React can be used in different environments (like React Native), but React-DOM is specific to web applications.

---

## 9. Explain the difference between Real DOM and Virtual DOM ?

- The **Real DOM** is the actual structure of the webpage, but modifying it directly is slow.
- React uses a **Virtual DOM**, which is a lightweight copy of the Real DOM, to optimize performance.
- When changes occur, React compares the new Virtual DOM with the previous one **(using a diffing algorithm)**
- and updates only the necessary parts in the Real DOM instead of reloading the entire page.

---

## 10. When does React sync the changes of Virtual DOM with Real DOM ?

- React syncs the Virtual DOM with the Real DOM whenever the state or props change, causing a component to re-render.
- **It follows a two-phase process**:
  - React updates the Virtual DOM and finds the differences "Reconciliation" (Render Phase),
  - then it applies the minimal necessary changes to the Real DOM (Commit Phase). This makes React efficient and avoids unnecessary updates.

### React Update Lifecycle: Render Phase vs. Commit Phase

#### Render Phase (Reconciliation Phase)

- React creates a new Virtual DOM when state or props change.
- It compares the new Virtual DOM with the previous one (Diffing Algorithm).
- React does not touch the Real DOM in this phase.
- This phase is pure (no side effects like DOM updates or API calls).

#### Commit Phase

- React applies the necessary updates to the Real DOM.
- Runs side effects (useEffect, componentDidMount, componentDidUpdate).
- Updates UI and triggers re-renders if required.

---

## 11. What is NPM ?
- NPM is a package manager.
- It is the world’s largest software registry.

### Why Do We Use NPM?
- Install JavaScript libraries (like React, Express, Lodash, etc.)
- Manage dependencies in a project **(package.json)**
- Run scripts (start, build, test, etc.)
- Publish & share packages with the community

### Key Features of NPM
- NPM Registry – A public database of JavaScript packages.
- Package Management – Helps install, update, and remove dependencies.
- Version Control – Supports semantic versioning to avoid breaking changes.
- Script Execution – Can run commands like npm start and npm run build.

### Basic NPM Commands

| Command                        | Description                                       |
|--------------------------------|---------------------------------------------------|
| `npm init`                     | Initializes a new project (creates `package.json`) |
| `npm install <package>`        | Installs a package locally                        |
| `npm install -g <package>`     | Installs a package globally                      |
| `npm update <package>`         | Updates an installed package                     |
| `npm uninstall <package>`      | Removes a package                                |
| `npm start`                    | Runs the project’s start script                  |
| `npm run build`                | Builds the project for production               |

---

## 12. What is a package.json file ?
- The package.json file is the heart of the node.js system.
- This file is a configuration file that stores important metadata about a project, including its dependencies, scripts, and project details
- It is automatically created when you initialize a project using npm init or yarn init.

### Why Do We Use package.json?
- Manages dependencies (like React, Express, etc.)
- Tracks project metadata (name, version, author, etc.)
- Defines scripts (npm start, npm run build, etc.)
- Ensures consistency in package versions across teams

### Important Fields in package.json

| Key               | Description                                      |
|------------------|--------------------------------------------------|
| `"name"`         | Project name                                     |
| `"version"`      | Project version                                  |
| `"description"`  | Short project description                        |
| `"main"`         | Entry point of the app (default: `index.js`)     |
| `"scripts"`      | Custom commands to run the project               |
| `"dependencies"` | Required libraries (React, Express, etc.)        |
| `"devDependencies"` | Development-only dependencies (testing, linting, etc.) |

--- 

## 13. What is the role of the package-lock.json file ?
- The **package-lock.json** file is automatically generated when you run npm install. 
- It locks the exact versions of installed dependencies to ensure consistency across different environments.

### Role of package-lock.json
- Locks Dependency Versions – Ensures that the same package versions are installed for every developer in the team.
- Improves Install Speed – Speeds up npm install by caching resolved package versions.
- Ensures Reproducibility – Guarantees that the project will work the same way across all environments (development, testing, production).

```
{
  "name": "my-app",
  "version": "1.0.0",
  "dependencies": {
    "react": {
      "version": "18.2.0",
      "resolved": "https://registry.npmjs.org/react/-/react-18.2.0.tgz",
      "integrity": "sha512-abc123..."
    }
  }
}

```
- **version –** The exact version installed (18.2.0)
- **resolved –** The URL where the package was downloaded from
- **integrity –** Security hash to verify package integrity

### Difference Between package.json and package-lock.json

| Feature                 | `package.json`                          | `package-lock.json`                     |
|-------------------------|----------------------------------------|-----------------------------------------|
| **Purpose**            | Lists dependencies & versions          | Locks exact dependency tree           |
| **Contains Version Ranges?** | Yes (`^`, `~`)                     | No (Exact versions)                   |
| **Editable by Developer?** | Yes                                  | No (Auto-generated)                   |
| **Tracks Subdependencies?** | No                                  | Yes                                   |


---

## 14. Types of Dependencies in package.json ?

#### When installing packages using NPM , dependencies are categorized into two main types:
- dependencies 
    - These are the core libraries required for the application to run in production.
    - We install production dependencies with
    ```
    npm install <package>
    ``` 
- devDependencies
    - These packages are required only during development (not needed in production).
    - We install development dependencies with
    ```
    npm install <package> --save-dev
    ```
```    
"dependencies": {
  "react": "^18.0.0",
  "express": "^4.17.1"
}
"devDependencies": {
  "react": "^18.0.0",
  "express": "^4.17.1"
}

```
---

## 15. What are Transitive Dependencies ?
- A Transitive Dependency is a dependency that your project does not directly install, but it gets installed automatically because another package (that you installed) depends on it.
- **In Simple Terms:**
    - You install Package A → Package A requires Package B → Package B is a transitive dependency

---

## 16. difference between Caret (^) and Tilde (~) in package.json ?

#### Example: 2.3.4
- Major (2.x.x) → Breaking changes
- Minor (x.3.x) → New features, no breaking changes
- Patch (x.x.4) → Bug fixes, no breaking changes

### Caret (^) – Allows Minor & Patch Updates

```
"dependencies": {
  "react": "^18.2.0"
}

```
- This means React version 18.2.0 or any newer minor/patch version (18.x.x) will be installed
- It allows updates as long as the major version (18.x.x) remains the same
- Example versions that can be installed: 18.2.1, 18.3.0, 18.4.5
- **Won't install:** 19.0.0 (Because 19 is a major update)
- Use **^** when you want new features but no breaking changes **(Safe, default for most libraries)**

### Tilde (~) – Allows Only Patch Updates

```
"dependencies": {
  "react": "~18.2.0"
}

```
- This means React version 18.2.0 or any newer patch version (18.2.x) will be installed
- It allows only patch updates, but not minor updates
- Example versions that can be installed: 18.2.1, 18.2.2
- **Won't install:** 18.3.0 (Because 3 is a minor update)
- Use **~** when you want only bug fixes but no new features **(Strict, for stability (like testing tools))**

### No Symbol ^ or ~
```
"dependencies": {
  "react": "18.2.0"
}
```
- Only React version 18.2.0 will be installed
- No updates will be installed automatically (even if 18.2.1 or 18.3.0 is available)
- Use **No Symbol** when you want When you want a fixed version

---

## 17. What is a bundler ?
- A bundler is a tool that takes your project's JavaScript, CSS, images, and other assets, combines them into optimized files, and makes them ready for the browser. 
- It improves performance by reducing the number of requests and optimizing code.

### Why Do We Need a Bundler?
- **Optimizes Performance –** Combines multiple files into a single file (reduces HTTP requests).
- **Manages Dependencies –** Resolves import and require statements.
- **Removes Unused Code (Tree Shaking) –** Eliminates unnecessary code.
- **Minifies Code –** Compresses files for faster loading.
- **Supports Modern JavaScript Features –** Transpiles ES6+ code for browser compatibility.

#### Popular Bundlers in JavaScript
- Webpack
- Vite
- Parcel
- Rollup
- ESBuild



# `Learn React With Harshi 👩🏻‍💻 Series`

Documenting my learning journey of [Namaste React Live Course](https://learn.namastedev.com/) conducted by Akshay Saini

## Namaste React Project Setup Cheatsheet

Following are the steps that we followed (in namaste react course) while developing a React App. You don't have to jump to multiple websites to copy setup command. Simply, you can refer to this cheatsheet for commands & configuration steps and easily create any new React Application.

### Important Note

You can follow these steps when you want to learn React in depth and want to know what happens behind the scene of create-react-app. But when you are in time constraint to develop a react app in situations like machine coding round of interview, it's advisable to use create-react-app package which does most of the below steps in less time. If you want to know how to setup the react application with create-react-app, check out [Setting Up React Application using CRA](https://github.com/Learn-React-With-Harshi/chapter-14-machine-coding-interview/blob/main/setup.md)

Let's set up the project in quick time by following the steps below & spend all the time that we have for developing the features.

### Tech Stack:

- UI Framwork : React
- CSS Framework : Tailwind CSS
- Routing : React Router DOM
- State Management : React-Redux & Redux Toolkit
- Web Bundler : Parcel
- Testing Frameowrk : React Testing Library & Jest

### Table of contents:

- [GitHub Repository](#github-repository)
- [Basic Files](#basic-files)
- [NPM - Initialize and Install Packages](#npm-initialize-and-install-packages)
  - [Init](#init)
  - [Install Parcel](#install-parcel)
  - [Install React](#install-react)
  - [Install React DOM](#install-react-dom)
  - [Install React Router DOM](#install-react-router-dom)
- [.gitignore](#gitignore)
- [.babelrc](#babelrc)
- [config.js](#config.js)
- [Command Scripts](#command-scripts)
- [Tailwind CSS](#tailwind-css)
- [Redux](#redux)
- [Jest and React Testing Library](#jest-and-react-testing-library)

### GitHub Repository:

1. Create a new public Github Repository in `https://github.com/`
2. Click on `code` dropdown and copy the link to your repo.
3. Clone the repo into local machine.

```
git clone "https://github.com/Learn-React-With-Harshi/Namaste-React.git"
```

4. Go to the project directory

```
cd Namaste-React
```

### Basic Files:

1. Open Namaste-React folder in vs code and create basic files like `index.html`, `app.js` and `index.css`
2. Write basic code, add link and script (important: type="module" for app.js) in html file.

### NPM - Initialize and Install Packages:

#### Init:

```
npm init
```

#### Install Parcel:

```
npm install -D parcel
```

#### Install React:

```
npm install react
```

#### Install React DOM:

```
npm install react-dom
```

#### Install React Router DOM:

```
npm install react-router-dom
```

### .gitignore:

Create .gitignore file in the project directory and add the following

```
#Node modules
node_modules

#Parcel
.parcel-cache
/dist

.DS_Store
```

### .babelrc:

Create .gitignore file in the project directory and add the following

```
{
  "plugins": [ [
    "transform-remove-console",
    { "exclude": [ "error", "warn" , "log"] }
    ]
  ]
}
```

### config.js:

Create .gitignore file in the project directory and add the required config

### Command Scripts:

Modify the scripts in `package.json`

```json
  "scripts": {
    "test": "jest",
    "start": "parcel index.html",
    "build": "parcel build index.html"
  }
```

### Tailwind CSS:

1. Install tailwindcss via npm, and `tailwind.config.js` file will be created on executing init command.

```
npm install -D tailwindcss
npx tailwindcss init
```

2. Configure template paths

Add the paths to all of your template files in your tailwind.config.js file.

```
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

3. Add the Tailwind directives to your CSS

Add the @tailwind directives for each of Tailwind’s layers to your main CSS file.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

4. Create `.postcssrc` file in project directory and add the following

{
"plugins": {
"tailwindcss": {}
}
}

### Redux:

1. Install Redux Toolkit & React-Redux

```
npm install @reduxjs/toolkit
npm install react-redux
```

### Jest and React Testing Library:

1. Install React & Jest DOM from React Testing library

```
npm install --save-dev @testing-library/react @testing-library/jest-dom
```

2. Install Jest & JS-DOM Environment

```
npm install -D jest jest-environment-jsdom
```

3. Configure Jest & this creates `jest.config.js`

```
npx jest --init
```

- Typescript -> N
- environment -> jsdom (broswer-like)
- code coverage -> y
- provider for coverage -> babel
- automatically clear before test -> y

4. Include following scripts to package.json

```
"test" : "jest",
"watch-test" : "test --watch"
```

5. Create new folder `__tests__` under `src/components`
6. Install Babel

```
npm install --save-dev babel-jest @babel/core @babel/preset-env @babel/preset-react
```

7. Add the following to Configure babel -> .babelrc file

```

  "presets" : [["@babel/preset-env", {"targets": {"node": "current"}}],
              ["@babel/preset-react", {"runtime" : "automatic"}]]
}
```

9. Add /coverage in .gitignore file
