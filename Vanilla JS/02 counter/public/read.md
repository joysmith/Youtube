# Counter

- Create a folder, name it "public", open with vs-code
- In public-folder create index.html, app.js, style.css files
- Go to bootstrap, copy starter template in public/index.html-file

  - change title
  - link app.js, styles.css files

  ```html
  <!-- styles -->
  <link rel="stylesheet" href="styles.css" />

  <!-- Place this just above body ending tag -->
  <script src="app.js"></script>
  ```

  - In body-tag create mark up

  ```html
  <main>
    <div class="container-counter">
      <h1>Counter</h1>
      <span id="value">0</span>
      <div class="button-container">
        <!-- bootstrap button -->
      </div>
    </div>
  </main>
  ```

<br>

- Go to bootstap in component-> Buttons => variants

  - select secondary,success,danger button
  - perform the tweaking

  ```html
  <button type="button" class="btn btn-danger decrease">decrease</button>
  <button type="button" class="btn btn-secondary reset">reset</button>
  <button type="button" class="btn btn-outline-success increase">
    increase
  </button>
  ```

<br>

- In public/style.css-file, style code

```css
.container-counter {
  width: auto;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}
```

<br>

- Go to bootstap in content-> typography => Display heading

  - copy class="display-1" and place it in span to increase the size of font

<br>

- In public/app.js-file build logic

```js
// set inital value to zero
let count = 0;
// select value and buttons
const value = document.querySelector("#value");
const btns = document.querySelectorAll(".btn");

btns.forEach(function (btn) {
  btn.addEventListener("click", function (e) {
    const styles = e.currentTarget.classList;
    if (styles.contains("decrease")) {
      count--;
    } else if (styles.contains("increase")) {
      count++;
    } else {
      count = 0;
    }

    if (count > 0) {
      value.style.color = "green";
    }
    if (count < 0) {
      value.style.color = "red";
    }
    if (count === 0) {
      value.style.color = "#222";
    }
    value.textContent = count;
  });
});
```
