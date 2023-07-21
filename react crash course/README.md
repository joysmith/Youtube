# React crash course

- How to install & run React.js app

```sh
npx create-react-app my-app
cd my-app
npm start
```

<br>

## Clean-up process

- remove files - App.test.js, reportWebVitals.js, logo.svg, setupTest.js, App.css <br>
- remove import- webVital, webVital function, react.StrictMode from index.js <br>
- remove import- logo, App.css from App.js <br>
- In src-folder, open App.js and perform "sanity check"

<br>

## Component & style with css<a id='27'></a>

- In src/App.js create functional component

```js
function App() {
  return (
    <div>
      <h1>My Wish list</h1>
      <div className="card">
        <h2>TITLE</h2>
        <div className="actions">
          <button className="btn">Delete</button>
        </div>
      </div>
    </div>
  );
}

export default App;
```

- Copy css code from resource, In src/index.css-file, remove everything then paste

```css
* {
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  margin: 3rem;
  background-color: #dfdfdf;
}

h1,
h2 {
  color: #333333;
}

.btn {
  font: inherit;
  padding: 0.5rem 1.5rem;
  cursor: pointer;
  border-radius: 4px;
  background-color: #1f6e8c;
  color: white;
  border: 1px solid #0e2954;
  margin: 0 1rem;
}

.btn:hover {
  background-color: #84a7a1;
  border-color: #84a7a1;
}

.btn--alt {
  background-color: transparent;
  color: #84a7a1;
}

.btn--alt:hover {
  background-color: #f8dae9;
}

.card {
  background-color: white;
  border-radius: 4px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
  padding: 1rem;
  width: 20rem;
}

.actions {
  text-align: right;
}

.modal {
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.2);
  border-radius: 6px;
  background-color: white;
  padding: 1rem;
  text-align: center;
  width: 30rem;
  z-index: 10;
  position: fixed;
  top: 20vh;
  left: calc(50% - 15rem);
}

.backdrop {
  position: fixed;
  z-index: 1;
  background-color: rgba(0, 0, 0, 0.75);
  width: 100%;
  height: 100vh;
  top: 0;
  left: 0;
}
```

<br>

## Building reusable component <a id='27'></a>

- In src-folder create component-subfolder, and in it create Wish.js
- In Wish.js, create functional component (rfce)
- Cut markup from App.js and paste to Wish.js

```js
function Wish() {
  return (
    <div className="card">
      <h2>TITLE</h2>
      <div className="actions">
        <button className="btn">Delete</button>
      </div>
    </div>
  );
}

export default Wish;
```

- In src/App.js import Wish.js component and use

```js
import Wish from "./component/Wish";
function App() {
  return (
    <div>
      <h1>My Wish list</h1>
      <Todo />
      <Todo />
    </div>
  );
}

export default App;
```

<br>
