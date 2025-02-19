# Next.js Overview

## What is Next.js?

- **React-based Open-Source Full-Stack Framework**: For building fast, production-ready web.
- **Hybrid Rendering**: SSR, SSG, ISR, CSR support.
- **Developer-friendly**: Simplified routing, built-in optimizations.
- **Developed By**: Vercel

---

## Key Features

- **File-based Routing**: Routes match file structure.
- **Image Optimization**: Lazy loading, resizing, WebP support.
- **API Routes**: Backend capabilities within the app.
- **SSR**: Server-rendered pages for SEO and speed.
- **SSG**: Static content at build time.
- **ISR**: Update static pages without full rebuilds.
- **CSR**: UI interaction
- **CSS/Sass Support**: Global styles, CSS modules.
- **TypeScript**: Built-in support.
- **Middleware**: Pre-render logic.
- **Edge/Serverless Deployment**: Scalable, fast.

---

## Benefits

- **SEO Optimized**: Pre-rendered pages for better indexing.
- **Fast Performance**: Faster TTFB, lazy loading.
- **Better UX**: Seamless navigation, Fast Refresh.
- **Scalable**: Hybrid rendering, serverless-ready.
- **Developer Productivity**: Easy setup, rich ecosystem.
- **Flexibility**: Custom configs, headless CMS support.
- **Rich Ecosystem**: Large community, React compatibility.

---

## Use Cases

- **E-commerce**: SEO, fast loading boosts conversions.
- **Content Sites**: Blogs, docs with SSG/ISR.
- **Enterprise Apps**: Scalable with APIs and hybrid rendering.
- **Real-time Apps**: SSR + CSR for interactivity.

---

## Conclusion

Next.js = Fast, flexible, production-ready React framework. Ideal for SEO, performance, and scalable web apps.








# `Learn React With Harshi 👩🏻‍💻 Series`
   Documenting my learning journey of [Namaste React Live Course](https://learn.namastedev.com/) conducted by Akshay Saini


## Namaste React Project Setup Cheatsheet
Following are the steps that we followed (in namaste react course) while developing a React App. You don't have to jump to multiple websites to copy setup command. Simply, you can refer to this cheatsheet for commands & configuration steps and easily create any new React Application. 

### Important Note
You can follow these steps when you want to learn React in depth and want to know what happens behind the scene of create-react-app. But when you are in time constraint to develop a react app in situations like machine coding round of interview, it's advisable to use create-react-app package which does most of the below steps in less time. If you want to know how to setup the react application with create-react-app, check out [Setting Up React Application using CRA](https://github.com/Learn-React-With-Harshi/chapter-14-machine-coding-interview/blob/main/setup.md)


Let's set up the project in quick time by following the steps below & spend all the time that we have for developing the features. 

### Tech Stack:
- UI Framwork         : React 
- CSS Framework       : Tailwind CSS 
- Routing             : React Router DOM
- State Management    : React-Redux & Redux Toolkit
- Web Bundler         : Parcel
- Testing Frameowrk   : React Testing Library & Jest

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