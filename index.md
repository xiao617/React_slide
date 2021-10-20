---

theme : "night"
transition: "slide"
highlightTheme: "monokai"
# logoImg: "logo.png"
slideNumber: true
title: "React overview"

---

### React


<style>
pre {
  background: #303030;
  padding: 10px 16px;
  border-radius: 0.3em;
  counter-reset: line;
}
pre code[class*="="] .line {
  display: block;
  line-height: 1.8rem;
  font-size: 1em;
}
pre code[class*="="] .line:before {
  counter-increment: line;
  content: counter(line);
  display: inline-block;
  border-right: 3px solid #6ce26c !important;
  padding: 0 .5em;
  margin-right: .5em;
  color: #afafaf !important;
  width: 24px;
  text-align: right;
}

.reveal .slides > section > section {
  text-align:left; 
}

h1,h2,h3,h4 {
  text-align: center
}

p {
  text-align: center;
}
</style>

---

## History
![](./media/javascript_logo.png =100x)
![](./media/fb_logo.png =100x)

---

### How does React work

--

### Virtual DOM
![](./media/vdom.png =400x)

---

### JavaScript & TypeScript

---

## Async & sync

--

### Async & sync
![](./media/async_sync.jpeg =400x)

---

## Start with React

--

### Install by npx tool


```javascript=
//Create a new React project with Redux & TypeScript
npx create-react-app [APP_NAME] --template redux-typescript
```

--

### Initial File Structure
```
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── tsconfig.json
├── public
│   ├── favicon.ico
│   ├── index.html
│   ├── logo192.png
│   ├── logo512.png
│   ├── robots.txt
│   └── manifest.json
└── src
    ├── app
    │   ├── hooks.ts
    │   └── store.ts
    ├── features/counter
    │   ├── Counter.module.css
    │   ├── Counter.tsx
    │   ├── counterAPI.ts
    │   ├── counterSlice.spec.ts
    │   └── counterSlice.ts
    ├── App.css
    ├── App.tsx
    ├── App.test.tsx
    ├── index.css
    ├── index.tsx
    ├── logo.svg
    ├── react-app-env.d.ts
    ├── setupTests.ts
    └── serviceWorker.ts
```

--

### Entrance of React

--

#### public/index.html
```html=
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.
      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
    <title>React Redux App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.
      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.
      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
</html>
```

--

### Change title

```html=
<title>React Redux App</title>
```

--

### Chango logo

```html=
<link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
```

--

### src/index.tsx
```typescript=
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import { store } from './app/store';
import { Provider } from 'react-redux';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(
  <React.StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();
```

--

#### public/index.html
```html=
<div id="root"></div>
```
#### src/index.tsx
```javascript
document.getElementById('root')
```

---

### Project Structure

```
├── README.md
├── node_modules
├── package.json
├── .gitignore
├── tsconfig.json
├── public
└── src
    ├── app
    ├── features/counter
    ├── *components
    ├── *pages
    ├── *services
    └── *types
```

---

### JSX


```typescript=
const element = (
  <h1 className="greeting">
    Hello, World!
  </h1>
);
```

```typescript=
const element = React.createElement(
  'h1',
  {
    className: 'greeting',
    'Hello, World!'
  },
);
```

---

### React Hook

--

### useState
```typescript=
//const [value,setStateFunction] = useState<Type>(defaultValue)
const [name,setName] = useState<string>("")
```

--

### useEffect
```typescript=
const getTodos = async() =>{
        await nodeService.getTodo().then((res)=>(setTodolist(res.data.todos)));
} 
useEffect(()=>{
  getTodos();
})
```

---

### Q&A


