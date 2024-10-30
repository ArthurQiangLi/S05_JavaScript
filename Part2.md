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

````css
//rullset for styling h1 elements
h1 { //here 'h1' is the 'selector' to match in the webpage.
  color: red;
  font-style: italic;
}

#main-heading {  //an ID selector
  font-size: 48px;
}

strong {   //matches any strong element <strong>
  color: blue;
}

p strong {  //a descendant selector, which means “match any strong element that’s a descendant of a p element.”  <p> <strong> xxxx  </strong> </p>
  font-size: 24px;
}

.highlight {  // a class selector, will match any element with class="highlight"
  background-color: yellow;
}

.highlight strong {//“match any strong element that’s a descendant of an element with the highlight class.”
  background-color: orange;
}

```
Additionally, for a class or ID selector:
`p.highlight` means “select any p elements with the highlight class,”


## 8-Event-Based Programming

Event Handler
Event Bubbing
Event Delegation
Mouse Movement Events
Keyboard Events

## 9-The Canvas Element

Creating a Canvas
Making Static Drawings
````
