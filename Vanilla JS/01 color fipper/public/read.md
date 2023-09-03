# Color flipper

- Create a folder name it "public", open with vs-code
- In public-folder create index.html, app.js, style.css files
- Go to bootstrap, copy starter template in public/index.html-file

  - change title
  - link app.js, style.css files

```html
<!-- styles -->
<link rel="stylesheet" href="styles.css" />

<!-- Place this just above body ending tag -->
<script src="app.js"></script>
```

- Go to bootstap in component-> nav

  - select navigation bar template copy and paste it in index.html
  - perform the tweaking

<br>

- Go to bootstrap in component-> card => Text alignment

  - select card component copy and paste it in index.html
  - perform tweaking with adding container class in card-div

  ```html
  <h5 class="card-title">
    Background color : <span class="color">#f1f5f8</span>
  </h5>
  ```

<br>

- In public/style.css-file, style code

```css
.container {
  width: auto;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

- In public/app.js-file build logic

```js
const hex = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, "A", "B", "C", "D", "E", "F"];
const btn = document.getElementById("btn");
const color = document.querySelector(".color");

btn.addEventListener("click", function () {
  let hexColor = "#";
  for (let i = 0; i < 6; i++) {
    hexColor += hex[getRandomNumber()];
  }
  // console.log(hexColor);

  color.textContent = hexColor;
  document.body.style.backgroundColor = hexColor;
});

function getRandomNumber() {
  return Math.floor(Math.random() * hex.length);
}
```

- [Js random number generator -w3school](https://www.w3schools.com/js/js_random.asp)
