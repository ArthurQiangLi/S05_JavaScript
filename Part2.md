# Part 2

This part is about how to use JavaScript to interface with a web browser.

## 7-HTML, DOM and CSS

### HTML

> HTML (HyperText Markup Language), is text that links to other text or documents, and markup is a system for annotating text in documents.

![Alt text](./MarkdownResouces/f71%20the%20anatomy%20of%20an%20HTML%20element.png)

1.  all other elements are nested within the only 'html' element in a file.
2.  The title 'hello, world' will display as the tab title at the top of your browser, not on the page itself.

```html
❶ <!DOCTYPE html> ❷
<html>
  ❸
  <head>
    <title>Hello, World!</title>
  </head>
  ❹
  <body>
    <h1>Hello!</h1>
    <p>Welcome to my document.</p>
  </body>
</html>
```

> DOM (Document Object Model), remember 'document' = 'webpage'. In your browser's 'Elements' tab. Document Object Model, or DOM. (Remember, document is just another word for a web page.)

<br>

> Web browsers allow you to modify the DOM using JavaScript with the DOM API

```js
document.title;
("Hello, World!");
document.title = "Hello, JavaScript!";
("Hello, JavaScript!");
```

#### Adding an id attribute

![Alt text](./MarkdownResouces/f74%20h1%20with%20an%20id.png)
<br>

Now that the h1 element has an ID, we can easily refer to it using Java script.

```
let heading = document.getElementById("main-heading");
heading;
<h1 id="main-heading">Hello!</h1>;
heading.innerText;
'Hello!'
heading.innerText = "Hi there…";
'Hi there…'

```

`<p class="highlight">This is my third <strong>paragraph</strong>.</p>` the `class` attribute is similar to the `id` attribute, but whereas IDs should be unique, you can apply the same class name to multiple elements. We use `class` when we want to treat a set of elements in the same way.

#### script Elements

> If you want to include JavaScript in an HTML document.

Here shows how to create a page with HTML file that includes a script element, and have that element point to a separate JavaScript.

```js
<!DOCTYPE html>
<html>
  <head>
    <title>Hello, JavaScript!</title>
 ❶ <script src="script.js"></script>
  </head>
  <body>
    <h1 id="main-heading">Hello, JavaScript!</h1>
  </body>
</html>
```

### CSS

> Modern web pages are made with three languages: HTML, JavaScript, and CSS. At a basic level, HTML defines the content of the page, JavaScript defines the behavior of the page, and CSS, short for Cascading Style Sheets, defines the appearance of the page.

<br>

#### link Elements

> The 'link' element is a generic way of including an external resource on a page.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello, JavaScript!</title>
    <script src="script.js"></script>
    <link href="style.css" rel="stylesheet" />
  </head>
  <body>
    <h1 id="main-heading">Hello, JavaScript!</h1>
  </body>
</html>
```

Here We set two attributes on the link element: href, short for hypertext reference (similar to 'src' for js files), and rel, short for relationship (here the linked file should be interpreted as a stylesheet for the page, about how elements should appear). Also, there is not closing bracket for this because a link element never contains content.

#### Rulesets

```css
//rullset for styling h1 elements
h1 {
  //here 'h1' is the 'selector' to match in the webpage.
  color: red;
  font-style: italic;
}

#main-heading {
  //an ID selector
  font-size: 48px;
}

strong {
  //matches any strong element <strong>
  color: blue;
}

p strong {
  //a descendant selector, which means “match any strong element that’s a descendant of a p element.”  <p> <strong> xxxx  </strong> </p>
  font-size: 24px;
}

.highlight {
  // a class selector, will match any element with class="highlight"
  background-color: yellow;
}

.highlight strong {
  //“match any strong element that’s a descendant of an element with the highlight class.”
  background-color: orange;
}
```

<br>

Additionally, for a class or ID selector:
`p.highlight` means “select any p elements with the highlight class,”

## 8-Event-Based Programming

### Event Handler

> Events are how the browser tells JavaScript that something has occurred in the DOM.

<br>

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Event Handlers</title>
  </head>
  <body>
    <h1 id="main-heading">Hello <em>World!</em></h1>
    <script src="script.js"></script>
  </body>
</html>
```

The browser builds a model of the page called the DOM. It builds the DOM incrementally by reading through the HTML file from top to bottom. Anytime the browser reaches a script element, it executes the whole script before continuing. That means that if we had our script element in the head, and we looked up the h1 element in that script, the h1 element wouldn’t be in the DOM yet! By placing the script element at the end of the body, we can be sure that all the page content has been loaded into the DOM before we run our JavaScript.
<br>

```js
let heading = document.querySelector("#main-heading");

heading.addEventListener("click", () => {
  console.log("You clicked the heading!");
});
```

### Event Bubbing

> When an event is triggered on an element, it also gets triggered on all the element’s ancestors
> <br>

```js
document.querySelector("em").addEventListener("click", () => {
  console.log("You clicked the em element!");
});

document.querySelector("body").addEventListener("click", () => {
  console.log("You clicked the body element!");
});
```

### Event Delegation

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Event Handlers</title>
  </head>
  <body>
    <h1 id="main-heading">Hello <em>World!</em></h1>

    <ul id="word-list">
      <li>The</li>
      <li>Dog</li>
      <li>Cat</li>
      <li>Is</li>
      <li>Was</li>
      <li>And</li>
      <li>Hungry</li>
      <li>Green</li>
    </ul>

    <p id="sentence"></p>

    <script src="script.js"></script>
  </body>
</html>
```

`ul` = unordered list
`li` = list item

```js
let wordList = document.querySelector("#word-list");
let sentence = document.querySelector("#sentence");

wordList.addEventListener("click", ❶ event => {
❷ let word = event.target.textContent;
  sentence.textContent += word;
  sentence.textContent += " ";
});
```

❷ event.target will be the li element you clicked. not the ul (the ul element is available with the currentTarget property).

### Mouse Movement Events

These mousemove events are triggered on an element while the mouse moves over that element.

<br>
```html
--snip--
    <p id="sentence"></p>

    <div id="box"></div>

    <script src="script.js"></script>

  </body>
</html>
```
`div`, short for content division. The div element is HTML’s generic container element. This means that it’s an element that can contain other elements, but by default has no appearance and no specific meaning (unlike ul, which means a list, or h1, which means a heading).

```js
document.querySelector("html").addEventListener("mousemove", (e) => {
  box.style.left = e.clientX + "px";
  box.style.top = e.clientY + "px";
});
```

`style` property, which is an object representing the CSS applied to the element.

### Keyboard Events

> In this part, We’ll focus on one keyboard event, called keydown, which is triggered when a key is pressed down.

```js
--snip--
document.querySelector("html").addEventListener("keydown", e => {
  console.log(e);

  if (e.key == "w") {
    currentY -= 5;
  } else if (e.key == "a") {
    currentX -= 5;
  } else if (e.key == "s") {
    currentY += 5;
  } else if (e.key == "d") {
    currentX += 5;
  }

  box.style.left = currentX + "px";
  box.style.top = currentY + "px";

});
```

## 9-The Canvas Element

canvas: it provides space for you to draw images within the browser window using JavaScrip. By repeatedly erasing old images and drawing new ones, you can create animations on the canvas.

## Creating a Canvas

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Canvas</title>
  </head>
  <body>
    <canvas id="canvas" width="300" height="300"></canvas>
    <script src="script.js"></script>
  </body>
</html>
```

## Making Static Drawings

```js
let canvas = document.querySelector("#canvas");
let ctx = canvas.getContext("2d");
ctx.fillStyle = "blue";
ctx.fillRect(10, 10, 200, 100);
```

**getContext**, which we use to get the canvas’s drawing context. we pass the string "2d" to the getContext method to request the two-dimensional drawing context.

<br>

To create an outlined rectangles

```js
ctx.lineWidth = 2;
ctx.strokeStyle = "red";
ctx.strokeRect(10, 10, 200, 100);
```

Here we uses `strokeStyle` and `strokeRect` rather than `fillStyle` and `fillRect`.

```js
ctx.strokeStyle = "orange";
ctx.strokeRect(20, 20, 180, 80);

ctx.strokeStyle = "yellow";
ctx.strokeRect(30, 30, 160, 60);

ctx.strokeStyle = "green";
ctx.strokeRect(40, 40, 140, 40);

ctx.strokeStyle = "blue";
ctx.strokeRect(50, 50, 120, 20);
```

![Alt text](/MarkdownResouces/f93%20concentric%20rectangles.png)

Each line **don't retroactively** affect anything that's already been drawn. Each rectangle is a different color, indicating that the style changes didn't impact anything that had already been drawn.

### Drawing Other Shapes Using Paths

```js
let canvas = document.querySelector("#canvas");
let ctx = canvas.getContext("2d");
ctx.fillStyle = "red";
ctx.beginPath();
ctx.moveTo(100, 100);
ctx.lineTo(150, 15);
ctx.lineTo(200, 100);
ctx.lineTo(100, 100);
ctx.fill();
```

Drawing a path takes three steps. First, you declare that you want to start drawing a new path with beginPath. Then, you use various methods to define where the path will be. Finally, you use fill or stroke to fill or stroke the path
