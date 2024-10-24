## 1-Getting Started

1. Strl+shift+J : open Chrome javascript console.
   1. try `alert("Hello, world!");` in the console
   2. JavaScript can run in the html file

```html
<html>
  <body>
    <script>
      alert("Hello from hello.html!");
    </script>
  </body>
</html>
```

## 2-The Basic

1. Expressions, have values, but don't let computer do anything
1. statements, tells computer to perform tasks, but don't have values
1. JavaScript statements end with a semicolon.
1. Compound expression,
1. literal,
1. var, let(preferred): two keywords for declaring variables.
   1. `let cats = 2;` `const PI = 3.141592653589793;`
1. naming convention: both **camelCase** and **snake_case** are ok.
1. Strings: `let greeting = 'hello';`
   1. `"abc".length; ` =3
   2. `greeting[0]` = 'h' , `greeting[10]` is `undefined   `
   3. String operation: getting multiple characters from a string
   4. Trimming whitespace from a string
   5. `.toLowerCase() `, `.includes(sss)`, `.padStart(num, char)`, `.repeat(count)`.
   6. Template Literals:
   ```
   let name = "Nick";
    `Hello, ${name}!`;
    'Hello, Nick!'
   ```
1. In JavaScript, the values **undefined** and **null** have a same special meaning: they represent nothing.
1. Boolean:
   1. `true && true` is true
   2. `false || true ` is true
   3. `5===5` is true, `"hello" === "goodbye"`is false. the === or “triple equals” operator checks if two values are equal.
   4. `8!==8` is false. This operator checks if two values are not equal.
