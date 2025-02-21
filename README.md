# `Learn React Js`

## 1. What is a CDN?

- **A Content Delivery Network or Content Distribution Network**: "(CDN) is a distributed network of servers that helps deliver content faster by serving it from the nearest location to the user. It improves performance, reduces server load, enhances security, and ensures better availability of web applications."

---

## 2. Why do we use a CDN?

- **Faster Load Times:** Since the content is served from the nearest server, it reduces latency and improves page speed.
- **Reduced Server Load:** CDN distributes traffic across multiple servers, preventing overloading of the origin server.
- **Better Availability & Reliability:** Even if one server goes down, another server in the network can serve the content.
- **Improved Security:** CDNs provide DDoS protection, secure data transfer, and reduce the risk of cyberattacks.
- **SEO Benefits:** Faster load times improve user experience, which can positively impact search engine rankings.

---

## 3. What is crossorigin and why do we use it in React CDN ?

### crossorigin

The crossorigin attribute is used in HTML \<script\> and &lt;link&gt; tags to handle cross-origin requests (i.e., requests made to a different domain). It tells the browser how to handle CORS (Cross-Origin Resource Sharing) when loading external resources like scripts, stylesheets, and images.

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

### Library

- **Definition**: A collection of functions and utilities that developers can call when needed.
- **Control**: Developer controls when and how to use the library.
- **Flexibility**: More flexible; can be used with different frameworks.
- **Examples**: ReactJS (Library), jQuery, Axios

### Framework

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

| Command                    | Description                                        |
| -------------------------- | -------------------------------------------------- |
| `npm init`                 | Initializes a new project (creates `package.json`) |
| `npm install <package>`    | Installs a package locally                         |
| `npm install -g <package>` | Installs a package globally                        |
| `npm update <package>`     | Updates an installed package                       |
| `npm uninstall <package>`  | Removes a package                                  |
| `npm start`                | Runs the project’s start script                    |
| `npm run build`            | Builds the project for production                  |

---

## 12. What is NPX ?

**NPX (Node Package eXecute)** is a tool that comes with NPM (5.2+) and allows you to run Node.js packages without installing them globally. It ensures you're using the latest version and helps execute one-time commands efficiently.

#### Using NPM (Old Method):

```javascript
npm install -g create-react-app
create-react-app my-app
```

#### Using NPX (Better Way):

```
npx create-react-app my-app
```

- No global install needed
- Always runs the latest version

## 13. What is a package.json file ?

- The package.json file is the heart of the node.js system.
- This file is a configuration file that stores important metadata about a project, including its dependencies, scripts, and project details
- It is automatically created when you initialize a project using npm init or yarn init.

### Why Do We Use package.json?

- Manages dependencies (like React, Express, etc.)
- Tracks project metadata (name, version, author, etc.)
- Defines scripts (npm start, npm run build, etc.)
- Ensures consistency in package versions across teams

### Important Fields in package.json

| Key                 | Description                                            |
| ------------------- | ------------------------------------------------------ |
| `"name"`            | Project name                                           |
| `"version"`         | Project version                                        |
| `"description"`     | Short project description                              |
| `"main"`            | Entry point of the app (default: `index.js`)           |
| `"scripts"`         | Custom commands to run the project                     |
| `"dependencies"`    | Required libraries (React, Express, etc.)              |
| `"devDependencies"` | Development-only dependencies (testing, linting, etc.) |

---

## 14. What is the role of the package-lock.json file ?

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

| Feature                      | `package.json`                | `package-lock.json`         |
| ---------------------------- | ----------------------------- | --------------------------- |
| **Purpose**                  | Lists dependencies & versions | Locks exact dependency tree |
| **Contains Version Ranges?** | Yes (`^`, `~`)                | No (Exact versions)         |
| **Editable by Developer?**   | Yes                           | No (Auto-generated)         |
| **Tracks Subdependencies?**  | No                            | Yes                         |

---

## 15. Types of Dependencies in package.json ?

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

## 16. What are Transitive Dependencies ?

- A Transitive Dependency is a dependency that your project does not directly install, but it gets installed automatically because another package (that you installed) depends on it.
- **In Simple Terms:**
  - You install Package A → Package A requires Package B → Package B is a transitive dependency

---

## 17. difference between Caret (^) and Tilde (~) in package.json ?

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

## 18. What is a bundler ?

- A bundler is a tool that takes your project's JavaScript, CSS, images, and other assets, combines them into optimized files, and makes them ready for the browser.
- It improves performance by reducing the number of requests and optimizing code.

### Why Do We Need a Bundler?

- **Optimizes Performance –** Combines multiple files into a single file (reduces HTTP requests).
- **Manages Dependencies –** Resolves import and require statements.
- **Removes Unused Code (Tree Shaking) –** Eliminates unnecessary code.
- **Minifies Code –** Compresses files for faster loading.
- **Supports Modern JavaScript Features –** Transpiles ES6+ code for browser compatibility.

### Popular Bundlers in JavaScript

- Webpack
- Vite
- Parcel
- Rollup
- ESBuild

---

## 19. What is HMR (Hot Module Replacement)?

**HMR (Hot Module Replacement)** is a feature in modern JavaScript bundlers (like Webpack, Vite, and Parcel) that allows you to update modules in a running application without a full page reload.

### Why is HMR Important?

- **Faster Development –** No need to refresh the page manually.
- **Retains State –** Doesn't reset UI state (useful in React).
- **Efficient Debugging –** Instantly sees changes without reloading.
- **Live Updates –** CSS, JS, and even React components update instantly.

### How HMR Works?

- **Listens for Changes –** Watches files in the project.
- **Recompiles Changed Modules –** Instead of rebuilding everything, it updates only the changed parts.
- **Injects Updates into the Running Application –** No full reload, just a partial update.

---

## 20. How to Make a React App Compatible with Older Browsers?

### 1. Use Babel for Transpilation

- **Why? :** Older browsers may not support ES6+ syntax like let, const, arrow functions, and async/await.
- **Solution :** Babel converts modern JavaScript into ES5, which is supported by most browsers.

### 2. Use Polyfills for Missing Features

- **Why? :** Older browsers lack modern JavaScript APIs like fetch, Promise, and Object.assign.
- **Solution :** Use polyfills (extra JavaScript code that mimics missing features).

### 3. Use CSS Prefixes for Older Browsers

- **Why? :** Some CSS properties (like grid, flexbox) need prefixes in old browsers.
- **Solution :** Use Autoprefixer to add vendor prefixes automatically.

### 4. Use a Browserlist Configuration

- **Why? :** Ensures Babel & Autoprefixer only target necessary browsers.
- **Solution :** Add browserslist in package.json:

### 5. Test in Older Browsers

- Use BrowserStack, Sauce Labs, or local VM to test in IE11, Edge Legacy, and old Chrome versions.

---

## 30. What is JSX?

**JSX (JavaScript XML)** is a syntax extension for JavaScript that allows you to write HTML-like code inside JavaScript.

### Why Do We Use JSX?

- **Makes Code More Readable –** Looks like HTML but has JavaScript power.
- **Faster Performance –** Transpiled into optimized JavaScript (React.createElement).
- **Prevents XSS Attacks –** Automatically escapes malicious scripts.
- **JavaScript Inside HTML –** You can use expressions inside JSX ({} syntax).

### How JSX Works Internally? JSX is not valid JavaScript! It gets converted to React.createElement()

#### JSX Code:

```
const element = <h1>Hello, World!</h1>;
```

#### Babel Converts it to JavaScript:

```
const element = React.createElement("h1", null, "Hello, World!");
```

#### Which Finally Becomes:

```
{
  type: "h1",
  props: { children: "Hello, World!" }
}
```

- React then renders this virtual structure into the real DOM.

---

## 31. What is Babel?

- Babel is a JavaScript compiler that converts modern JavaScript (ES6+) into older versions (ES5) so that it can run on older browsers.

### Why Do We Need Babel?

- **Browser Compatibility –** Converts ES6+ to ES5 for older browsers like IE11.
- **Supports JSX –** Converts JSX into JavaScript (React.createElement).
- **Allows Latest JS Features –** Enables features like async/await, optional chaining (?.), and nullish coalescing (??).
- **Works with Webpack & Bundlers –** Optimizes and compiles JS for production.

### How Babel Works? Babel takes modern JavaScript and transpiles it into older JavaScript.

#### Modern JavaScript (ES6+):

```
const greet = () => console.log("Hello, World!");
```

#### Babel Transpiles to ES5:

```
var greet = function () {
  console.log("Hello, World!");
};
```

- This makes it compatible with older browsers that don’t support ES6.

---

## 32. Difference Between { Title } vs { \<Title \/\> } vs { \<Title\>\<\/Title\> }

| Syntax                       | Meaning                                                                                    |
| ---------------------------- | ------------------------------------------------------------------------------------------ |
| **{ Title }**                | This value describes the Title as a JavaScript expression or a variable.                   |
| **{ \<Title \/\> }**         | This value represents a component that is basically returning some JSX value.(Recommended) |
| **{ \<Title\>\<\/Title\> }** | <Title> and <Title></Title> are equivalent only when \<Title\> has no child components.    |

---

## 33. What is Reconciliation in React?

- Reconciliation is the process in React that updates the Real DOM efficiently by comparing it with the Virtual DOM and applying only the necessary changes.
- This helps improve performance and avoid unnecessary re-renders.

### How Does Reconciliation Work?

**Render Phase:**

- React creates a Virtual DOM tree based on the component’s JSX.
- It compares the new Virtual DOM with the previous one (Diffing).

**Commit Phase:**

- React calculates the minimal number of changes (using the Fiber algorithm).
- It applies only the necessary updates to the Real DOM.

### The Diffing Algorithm in Reconciliation

- React uses a Diffing Algorithm to efficiently update the DOM.

**Rules of Diffing Algorithm:**

- If the element type is the same, React updates only its attributes.
- If the element type changes, React destroys the old element and creates a new one.
- If the list items change, React uses keys to identify and update them efficiently.

---

## 34. What is React Fiber?

- React Fiber is the re-implementation of React’s core algorithm introduced in React 16.
- It improves rendering performance by enabling asynchronous rendering, better handling of animations, and prioritization of updates.

### Why Was React Fiber Introduced?

- Before React Fiber, React used a recursive rendering approach that was synchronous and blocked the main thread until rendering was complete. This caused:
- Slow UI updates in large applications.
- Animations & transitions lagging due to blocking renders.
- Performance issues when handling complex components.

### How Does React Fiber Work?

- React Fiber splits the rendering process into small units called fibers, allowing React to pause, prioritize, and resume rendering when needed.

#### Before Fiber (Old React Reconciliation)

- React would render the entire component tree in one go, blocking the UI.
- If an update took too long, the page could freeze.

#### With Fiber (New Reconciliation Algorithm)

- Rendering is broken into smaller chunks.
- React can pause rendering if needed (e.g., for high-priority updates like user input).
- Improves handling of animations, transitions, and responsiveness.

---

## 35. Why and When Do We Need Keys in React?

- Keys in React help identify which elements in a list have changed, been added, or removed. They improve performance and prevent unnecessary re-renders by ensuring React can efficiently update the UI.
- **In Simple Terms:**
  - Keys help React track which items changed, added, or removed, improving performance.

**Why Are Keys Important?**

- React needs a way to track changes when rendering lists.
- Without keys, React re-renders everything, even if only one item changes.
- Keys help React identify elements uniquely and optimize updates.

**When Do We Need Keys?**

- We must use keys when rendering lists dynamically using .map(), such as:

```
{users.map((user) => (
  <li key={user.id}>{user.name}</li>  // ✅ Using unique "id" as key
))}
```

**Can We Use Indexes as Keys in React?**

- Yes, we can use indexes as keys in React.
- but it is not recommended in most cases because it can lead to unexpected bugs and performance issues when list items are added, removed, or reordered.

## 36. What is React?

- React is an open-source JavaScript library developed by Facebook (Meta) for building fast, interactive, and reusable UI components. - - It follows a component-based architecture and uses a Virtual DOM for efficient updates.

### Key Features of React

- **Component-Based Architecture**
  - Everything in React is a component (e.g., buttons, forms, headers).
- **Virtual DOM (VDOM)**
  - React doesn’t update the Real DOM directly (which is slow).
- **JSX**
  - JSX is a syntax extension that allows writing HTML-like code inside JavaScript.
- **State Management**
  - React uses state to manage component-specific data dynamically.
- **Props (Properties)**
  - Props allow passing data between components.
- **React Hooks**
  - Hooks (introduced in React 16.8) allow functional components to use state and lifecycle methods.
- **React Router (For Navigation)**
  - React doesn’t have built-in routing, so React Router is used to navigate between pages in a Single Page Application (SPA).
- **One-Way Data Binding**
  - React follows one-way data binding, meaning data flows from parent to child components.
- **Fast Performance with React Fiber**
  - React Fiber (React 16+) improves rendering with asynchronous updates, time-slicing, and prioritization of tasks.

---

## 37. What are Props in React, and How Are They Used?

### What Are Props?

- **Props (short for "Properties")** in React are used to pass data from a parent component to a child component. They make components reusable and allow them to be configured dynamically.

### Key Characteristics of Props:

- **Immutable -** Cannot be changed inside the child component.
- **One-way data flow -** Data flows from parent to child only.
- **Reusable -** Props allow components to work with different data values.

### How Are Props Used?

**1. Passing Props from Parent to Child**

```
    function Greeting(props) {
      return <h1>Hello, {props.name}!</h1>;
    }

    function App() {
      return <Greeting name="John" />;
    }
```

**2. Using Destructuring for Props**

```
    function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}

function App() {
  return <Greeting name="Alice" />;
}
```

- Destructuring makes the code more readable.

**3. Passing Multiple Props**

```
function User({ name, age, hobbies }) {
  return (
    <div>
      <h2>Name: {name}</h2>
      <p>Age: {age}</p>
      <p>Hobbies: {hobbies.join(", ")}</p>
    </div>
  );
}

function App() {
  return <User name="John" age={25} hobbies={["Reading", "Gaming"]} />;
}

```

**4. Passing Functions as Props (Callback Functions)**

```
function Button({ onClick }) {
  return <button onClick={onClick}>Click Me</button>;
}

function App() {
  const handleClick = () => alert("Button Clicked!");

  return <Button onClick={handleClick} />;
}


```

- The handleClick function is passed as a prop and executed inside the child component.

**5. Default Props (Setting Default Values)**

```
function Greeting({ name = "Guest" }) {
  return <h1>Hello, {name}!</h1>;
}

function App() {
  return <Greeting />; // No name passed, so "Guest" is used
}


```

- If name is missing, "Guest" is displayed instead of undefined.

**6. PropTypes (Type Checking for Props)**

```
import PropTypes from "prop-types";

function User({ name, age }) {
  return (
    <div>
      <h2>Name: {name}</h2>
      <p>Age: {age}</p>
    </div>
  );
}

User.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
};


```

- This ensures name is a string and age is a number.
- If the wrong type is passed, React will show a warning in the console.

---

## 38. What is State in React, and How Is It Different from Props?

### What is State in React?

- State is a built-in feature in React that allows components to store and manage dynamic data.
- It controls the component’s behavior and re-renders the UI whenever it changes.

### Key Features of State:

- **Mutable -** State can be updated inside the component.
- **Private -** State belongs to the component and cannot be accessed by other components directly.
- **Triggers Re-renders -** When state changes, React automatically re-renders the component.

### How is State Used?

**1. Declaring State Using useState()**

```
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0); // State variable

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;



```

- Here, count is a state variable, and setCount is a function to update state.
- Clicking the button updates the state (count), causing a re-render.

**2. Updating State Based on Previous State**

```
const [count, setCount] = useState(0);

const increment = () => {
  setCount(prevCount => prevCount + 1);
};



```

- This ensures that React uses the latest state value.

**6. State Can Hold Objects & Arrays**

```
const [user, setUser] = useState({ name: "John", age: 25 });

const updateAge = () => {
  setUser(prevUser => ({ ...prevUser, age: prevUser.age + 1 }));
};



```

- The spread operator (...prevUser) ensures that other properties remain unchanged.

### Difference Between Props and State

| Feature          | Props                         | State                            |
| ---------------- | ----------------------------- | -------------------------------- |
| **Mutability**   | Immutable (cannot be changed) | Mutable (can be updated)         |
| **Ownership**    | Passed from parent to child   | Managed within the component     |
| **Re-rendering** | Does not cause re-renders     | Triggers re-renders              |
| **Usage**        | Used for data transfer        | Used for component behavior      |
| **Access**       | Read-only                     | Can be modified using `setState` |

---

## 39. What Are React Hooks, and Why Were They Introduced?

### What Are React Hooks?

- React Hooks are functions that allow functional components to use state and lifecycle features without writing class components. - - - Hooks were introduced in React 16.8 to simplify component logic and improve reusability.

### Key Features of Hooks:

- Allow state management in functional components (useState)
- Enable side effects like API calls (useEffect)
- Provide performance optimizations (useMemo, useCallback)
- Facilitate global state management (useContext, useReducer)

### Why Were Hooks Introduced?

Before hooks, state and lifecycle methods were only available in class components. This led to several problems:

**1. Complex Component Logic**

- In class components, logic was often split across multiple lifecycle methods (componentDidMount, componentDidUpdate, componentWillUnmount).
- Hooks allow us to group related logic together inside functions.

**2. No State in Functional Components**

- Before hooks, only class components could manage state.
- useState made state available inside functional components, reducing boilerplate code.

**3. Code Reusability Issues**

- React HOCs (Higher-Order Components) and Render Props were used to share logic, but they made the code hard to read.
- Hooks like useContext, useReducer, and custom hooks allow better code reusability.

### Before Hooks: Using Class Components

```
class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}

```

#### Problems:

- Boilerplate code (constructor, this.state, this.setState)
- Complex syntax (this binding)

### After Hooks: Using Functional Components

```
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}


```

#### Advantages of Hooks:

- Less code, easier to read
- No need for classes or this keyword
- Simplifies state management

---

## 40. Fetching data from an API

- There are two approaches.
  - First Approach
    - Page Loads -> Make API call -> Render UI
    - In this approach, as soon as the page loads, we will make an API call.
    - As soon as we get the API response, we will populate the data and render the UI.
  - Second Approach
    - Page Loads -> Render UI -> Make API call -> Render
    - In this approach, as soon as the page loads, we will render the skeleton of the UI.
    - Then we will make an API call.
    - Once we get the API response, then we will populate the data and render the UI.
    - In React, we are always going to follow the second approach.

### Fetching Data with useEffect and useState (Best Practices)

- Always handle errors (try/catch or .catch()).
- Use useEffect with an empty dependency array ([]) to fetch data only once on mount.
- Use a loading state to avoid showing blank UI while fetching.
- Use a key prop when rendering lists from API data (\<li key={user.id}\>).

---

## 41. How Can We Change a State Variable Even If It Is Defined as a Constant?

- In React, when we declare a state variable using useState, we define it as a constant using const.
- However, React provides a special function (setState) to update the state, even though it is declared as a constant.

### Example: Behind the Scenes

**Let's assume the component renders for the first time:**

```
const [count, setCount] = useState(0);
```

- count is initialized as 0.

**When setCount(1) is called:**

- React creates a new state value (1).
- React re-renders the component, and now count = 1.

#### Thus, React does not modify the existing constant but assigns a new value when the component re-renders.

---

## 42. Key Differences Between Expression and Statement

| Feature         | Expression                    | Statement               |
| --------------- | ----------------------------- | ----------------------- |
| **Definition**  | Returns a value               | Performs an action      |
| **Usage**       | Can be assigned to a variable | Cannot be assigned      |
| **Inside JSX?** | ✅ Yes                        | ❌ No                   |
| **Examples**    | `5 + 5`, `"Hello"`, `x > y`   | `if`, `for`, `function` |

---

## 43. What is React Router?

- React Router is a popular routing library for React applications that enables client-side navigation without refreshing the page.
- It allows us to create single-page applications (SPAs) with multiple views.

### Why Use React Router?

- Enables navigation between pages without reloading (Client-side Routing).
- Improves user experience with faster transitions.
- Supports nested routes, dynamic routes, and protected routes.
- Handles browser history and URL updates efficiently.

### Types of Router in React and Their Uses

React Router provides different types of routers for handling navigation based on the application's requirements.

1. BrowserRouter (Most Common)

- Used for:
  - Standard Single Page Applications (SPAs) with modern browsers.
- How It Works:
  - Uses the HTML5 History API (pushState, replaceState) to change the URL without reloading the page.
  - Keeps a clean URL without a hash (/home, /about).
  - Ideal for most React applications deployed on a web server.
- Best For:
  - Modern browsers.
  - SEO-friendly SPAs.

2. HashRouter

- Used for:
  - Applications that don’t have backend server support for routing (like static sites).
- How It Works:
  - Uses a hash (#) in the URL (http://example.com/#/about).
  - Works well even if the server doesn't handle route requests.
- Best For:
  - Static websites hosted on GitHub Pages, AWS S3, or Firebase.
  - Environments where server-side routing is unavailable.

3. MemoryRouter

- Used for:
  - Applications that do not use the browser’s URL (e.g., mobile apps, unit testing).
- How It Works:
  - Stores the route history in memory instead of the browser URL.Stores the route history in memory instead of the browser URL.
  - The URL does not change in the address bar.
- Best For:
  - React Native apps.
  - Unit testing with tools like Jest.

4. MemoryRouter

- Used for:
  - Server-Side Rendering (SSR) applications like Next.js.
- How It Works:
  - Prepares static routes for the server to render the initial page.
  - Does not track navigation changes (no pushState).
  - Mostly used in frameworks like Next.js that handle SSR.
- Best For:
  - Server-Side Rendering (SSR) frameworks like Next.js.
  - Pre-rendering pages for SEO.

#### Note: Two types of routing

- Client side routing
  - In client side routing, the app does not make any network calls while navigating from one page to another.
- Server side routing
  - In client side routing, the app does not make any network calls while navigating from one page to another.

---

## 44. What is createBrowserRouter?

- It is an alternative to \<BrowserRouter\> that uses a JavaScript object-based route configuration instead of JSX-based \<Routes\> and \<Route\>.
- It enables nested routing, layout components, data loading, and error handling at the route level.
- Works well with React Suspense for better performance.

### Note: createBrowserRouter is a way to define routes (introduced in React Router v6.4), but it still uses BrowserRouter internally for navigation but provides more powerful features (data fetching, layouts, etc.).

## Correct Understanding: BrowserRouter vs. createBrowserRouter

| Feature               | `BrowserRouter`                                       | `createBrowserRouter`                  |
| --------------------- | ----------------------------------------------------- | -------------------------------------- |
| **Type**              | Router (decides URL handling)                         | API to define routes                   |
| **Uses**              | `<Routes>` & `<Route>` (JSX-based routing)            | Object-based route configuration       |
| **Advanced Features** | Simple routing                                        | Nested routes, loaders, error handling |
| **Example**           | `<BrowserRouter><Routes>...</Routes></BrowserRouter>` | `createBrowserRouter([...routes])`     |

## 45. What should happen if we do console.log(useState()) ?

1. **Incorrect Usage:**
```
import { useState } from "react";

console.log(useState()); //Error: Invalid hook call. Hooks can only be called inside the body of a function component.

```

2.  **Correct Usage Inside a Functional Component:**
```
import { useState } from "react";

function Counter() {
  const state = useState(0);
  console.log(state); // ✅ Logs: [0, ƒ setState]

  return <button>Click</button>;
}

export default Counter;

```

---

## 46. 

