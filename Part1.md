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
   ```js
   let name = "Nick";
   `Hello, ${name}!`;
   ("Hello, Nick!");
   ```
1. In JavaScript, the values **undefined** and **null** have a same special meaning: they represent nothing.
1. Boolean:
   1. `true && true` is true
   2. `false || true ` is true
   3. `5===5` is true, `"hello" === "goodbye"`is false. the === or “triple equals” operator checks if two values are equal.
   4. `8!==8` is false. This operator checks if two values are not equal.
1. Type Coercion:
   1. `"Current score: " + 10; -->> "Current score: 10" `
   2. `100 + true;  -->> 101`
   3. double equals (==), that applies coercion to its operands before checking for equality. `"1" == 1;-> true `, `
undefined == null; ->true`, `
undefined == false; ->false`,`"" == 0; ->true`,`
"" == false; ->true`
   4. `0 !== false; ->true`; ` 0 != false;->false` Without coercion, 0 is not equal to false, so 0 !== false is true. With coercion, however, false becomes 0, so 0 != false is false.
   5. Use of Truthiness: `let name;
name = name || "No name provided";`, used to give a variable a default value if one isn't provided.

## 3-Compound Data Types

### 1. Arrays:

1. they have the flexibility to grow and shrink as values are added or removed.
2. `let primes = [2, 3, 5, 7, 11, 13, 17, 19];`
3. These multidimensional arrays are often used to represent two-dimensional grids of points, or tables. `
let ticTacToe = [
  ["", "", ""],
  ["", "", ""],
  ["", "", ""]
];` --> (3)[Array(3), Array(3), Array(3)]
4. Adding an Element to an array: `let languages = [];
languages.push("Python");` also the .push() method returns num of elements in the array.
5. To add an element to the beginning of the array rather than the end : `languages.unshift("Erlang");`
6. To mutate an array by removing its last element: `languages.pop();` The method returns the value of the element being removed.
7. To remove the first element from an array, rather than the last: `let worstLanguage = languages.shift();`, Like pop, the shift method returns the removed element.
   ![alt text](./MarkdownResouces/push,pop,ushshift,shift%20to%20graphic.png)
8. Combining arrays: `let fish = ["Salmon", "Cod", "Trout"];
let mammals = ["Sheep", "Cat", "Tiger"];
let animals = fish.concat(mammals); let animals2  fish.concat(mamals, mamals)`
9. Finding the Index of an Element in an Array: `let sizes = ["Small", "Medium", "Large"];
sizes.indexOf("Medium"); -->> 1 ;;;
sizes.indexOf("Huge"); -->>-1(if the element is not found in the array)`
10. Turning an Array into a string: `let beatles = ["John", "Paul", "George", "Ringo"];
beatles.join(); -->>
'John,Paul,George,Ringo'`
11. Other useful method: `.include(element); .reverse(); .sort(); .slice(start,end); .splice(index, count);`

### 2. Objects ('Key'-Value pair):

object literal consistes of `{ "" : , }`

```js
let casablanca = {
  title: "Casablanca",
  released: 1942,
  director: "Michael Curtiz",
};

casablanca["title"];
casablanca.title-- >> "Casablanca"; //like accessing the property of an object.

let dictionary = {};
dictionary.mouse = "A small rodent";
```

1. To return all the keys, why we need to call it with Object.keys(cats) rather than with cats.keys()? it is said the language designer wanted to avoid naming conflicts because you may have a key 'keys'.
2. **Object to array**: `let chromosomes = {
  koala: 16,
  snail: 24,
  giraffe: 30,
  cat: 38
};
Object.entries(chromosomes);` -->> `(4) [Array(2), Array(2), Array(2), Array(2)]
  0: (2) ['koala', 16]
  1: (2) ['snail', 24]
  2: (2) ['giraffe', 30]
  3: (2) ['cat', 38]`
3. **Combining Objects**: `let book = {};
Object.assign(book, physical, contents);
book; -->> {pages: 208, binding: 'Hardcover', genre: 'Fiction', subgenre: 'Mystery'} ` with object.assign, you can consolidate these separate objects into one.
4. **Nesting Objects and Arrays**:

```js
let trilogies = [
❶ {
    title: "His Dark Materials",
    author: "Philip Pullman",
    books: ["Northern Lights", "The Subtle Knife", "The Amber Spyglass"]
  },
❷ {
    title: "Broken Earth",
    author: "N. K. Jemisin",
    books: ["The Fifth Season", "The Obelisk Gate", "The Stone Sky"]
  }
];

trilogies[1].books[0];  -->> 'The Fifth Season'
```

1. **JSON (JavaScript Object Notation)**. The `JSON.stringify` method converts a JavaScrip object into a JSON string.

## 4-Conditionals and Loops

> The control structs

### If Statements

```js
<html><body><script>
let speed = 20;
console.log(`Your current speed is ${speed} mph.`);
if (speed > 25) {
❶ console.log("Slow down!");
} else {
❷ console.log("You're obeying the speed limit.");
}
</script></body></html>


//Write the boolean expression separately
let tooFastForSchool = speed > 25 && hour > 7 && hour < 16;
if (tooFastForSchool) {...}
```

### While Loops

### For Loops

> 4 kinds of loops: while loops, for loops, for…in loops, and for…of loops. Let’s start with while loops.

```html
<html>
  <body>
    <script>
      for (let speed = 30; speed > 25; speed--) {
        console.log(`Your current speed is ${speed} mph.`);
      }
    </script>
  </body>
</html>
```

A `for…of` loop cycles through the items in an **array**, strings are arrays, too.

```html
<html>
  <body>
    <script>
      let colors = ["Red", "Green", "Blue"];

      for (let color of colors) {
        console.log(`${color} is a color.`);
      }

      for (let [index, item] of colors.entries()) {
        //with entries to access the indices in an array.
        console.log(`${index}: ${item} is a color.`);
      }
    </script>
  </body>
</html>
```

A `for…in` loop cycles through the keys in an **object**.

```html
<html>
  <body>
    <script>
      let me = {
        "first name": "Nick",
        "last name": "Morgan",
        age: 39,
      };

      for (let key in me) {
        console.log(`My ${key} is ${me[key]}.`);
      }
      //You could achieve the same result using Object.entries(me) to get an array of pairs of keys and values
    </script>
  </body>
</html>
```

## 5-Functions

### Declaring and Calling Functions

```js
//Declaring functions:
function sayHello(name) {
  console.log(`Hello, ${name}!`);
  return 0;
}
//Calling functions:
sayHello("Nick");

//Calling from within the template literal:
`I walked ${add(500, 500)} miles`;
("I walked 1000 miles");
```

> JavaScript is a **dynamically typed** programming language, in which the types of a variables can change while the program is running.

```js
add("Hello, ", "world!");
("Hello, world!");
add(true, false);
1;
add(1, "1");
("11");
```

> In JavaScript, functions are first-class citizens, which means they **can be used like any other value**, such as a number or a string. For example, you can store a function in a variable or pass a function as an argument to another function.

#### Passing a Function as an Argument

> When a function is passed as an argument, it's often refferred as a callback, because the fucntion it's passed to is said to 'call it back' by executing it.

```js
function sayHi() {
  console.log("Hi!");
}
setTimeout(sayHi, 2000);
1 //this is timeout ID
Hi!
```

### Function Expressions

> is an expression that evaluates to (returens) a function.

```js
//[1]a function expression can’t be written at the start of a line of code
let addExpression = function (x, y) {
  //[2], a function expression doesn’t have to include a name, it's called a anonymous function
  return x + y;
}; //a semicolon after the closing brace is needed

addExpression(1, 2); //the funcion is bound to the addExpression variable now
3;
```

> Function expression and function declarations are interchangeable, choosing between the two approaches is a matter of style.

### Arrow Functions

> a.k.a Arrow Function Expression.

```js
let addArrow = (x, y) => {
  return x + y;
};

addArrow(2, 2);
4;

let addArrowConcise = (x, y) => x + y; //concise body: if the body consists of just a single statement.

let squared = (x) => x * x;
squared(3);
9;

setInterval(() => {
  //arrow function takes no arguments, so it begins with an empty set of parentheses
  console.log("Beep");
}, 1000);
3;
Beep;
```

### Rest Parameters

> Sometimes you want your function to accept a variable number of arguments.

```js
let myColors = (name, …favoriteColors) => {  //A rest parameter looks like an ordinary parameter preceded by three periods, and it always has to be the last parameter listed in the function definition. The rest parameter bundles the '...favoriteColors' into an arry.
  let colorString = favoriteColors.join(", ");
  console.log(`My name is ${name} and my favorite colors are ${colorString}.`);
};
myColors("Nick", "blue", "green", "orange");
My name is Nick and my favorite colors are blue, green, orange.

//another example
function sum(…numbers) {
  let total = 0;
  for (let number of numbers) {
    total += number;
  }
  return total;
}
sum(1, 2, 3, 4, 5);
15
sum(6, 7, 8, 9, 10, 11, 12, 13);
76
```

### Higher-Order Functions

> A higher-order function is a function that takes another function as an argument, or that outputs another function as its return value.

#### 1.Array Methods That takes Callbacks

```js
//[1]Finding an Array Element
let shoppingList = ["Milk", "Sugar", "Bananas", "Ice Cream"];
shoppingList.find((item) => item.length > 6); //pass a callback to find()
("Bananas");
shoppingList.find((item) => item[0] === "A");
undefined; //if no item is found, returns undefined.
```

```js
//[2]Filtering the elements of an Array
let shoppingList = ["Milk", "Sugar", "Bananas", "Ice Cream"];
shoppingList.filter(item => item.length > 6);
(2) ['Bananas', 'Ice Cream']
```

```js
//[3]Transforming Each Element of an Array
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let cubes = numbers.map(x => x * x * x); //this callback function to map(), takes an array element and cubes it.
cubes;
(10) [1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]

//Equals to:
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let cubes = [];
for (let x of numbers) {
  cubes.push(x * x * x);
}
cubes;
(10) [1, 8, 27, 64, 125, 216, 343, 512, 729, 1000]
//***
let stockList = [
  {name: "Cheese", price: 3},
  {name: "Bread", price: 1},
  {name: "Butter", price: 2}
];
let prices = stockList.map(item => item.price); //for each item in an array, just get the prices and form a new array with all the prices.
prices;
(3) [3, 1, 2]
```

### Custom Functions That Take Callbacks

```js
function doubler(callback) {
  callback();
  callback();
}
doubler(() => console.log("Hi there!"));
Hi there!
Hi there!

//another example
function callMultipleTimes(times, callback) {
  for (let i = 0; i < times; i++) {
    callback(i);
  }
}
callMultipleTimes(3, time => console.log(`This was time: ${time}`));  //here 'time => console...' is a arrow funciton with single 'time' parameter. In case you're confused of: why not '(3, time) ==> ...'?
This was time: 0
This was time: 1
This was time: 2
```

### Functions That Return Functions

```js
function makeAppender(suffix) {
❶ return function (text) {
  ❷ return text + suffix;
  };
}

let puzzling = makeAppender("???");
puzzling("Hello");
'Hello???'
let winking = makeAppender(" ;-)");
winking("Hello");
'Hello ;-)'
```

## 6-Classes

> Functions vs Methods: methods are always associated with an object, whereas a function stands alone.
> 'myArray.push(2)', here 'myArray' is called "receiver", because it receives the method call.

### Creating Classes and Instances

```js
class Player {
❶ constructor(startX, startY) {  //constructor() is called automatically anytime you create an instance of the class
    this.x = startX; //'this' is set to the current object(the receiver)
    this.y = startY;
  }

❷ move(dx, dy) { //don't use 'function' keyword
    this.x += dx;
    this.y += dy;
  }
}

let player1 = new Player(0, 0); //here 'this' is 'player1'

```

### Inheritance

```js
class Player extends Actor {
   //Inside a subclass’s constructor method, the super keyword refers to the constructor from the superclass
  constructor(startX, startY) {
    super(startX, startY);
  ❶ this.hp = 100;
  }
}

//
let player = new Player(1, 2);
let enemy = new Enemy(3, 4);
player.hp;
100
enemy.distanceTo(player);
2.8284271247461903
enemy.attack(player);
true
player.hp;
90
player.move(5, 5);
enemy.attack(player);
false
player.hp;
90
```

> When a subclass doesn’t define a constructor, its parent class’s constructor is called automatically when a new instance of the subclass is created

### Prototype-Based Inheritance

### Using Constructors and Prototypes

```js
function Cat(name) {
  this.name = name;
}
Cat.prototype.sayHello = function () {
  console.log(`Miaow! My name is ${this.name}.`);
};

let kiki = new Cat("Kiki");
kiki.sayHello();
Miaow! My name is Kiki.
undefined

kiki.__proto__; //to access an object's prototype property directly in code
{sayHello: f, constructor: f}
```

### Comparing Constructors and Classes

### Walking the Prototype Chain

![Alt text](./MarkdownResouces/figure6.1%20the%20prototype%20chain%20for%20kiki.png)

> all constructor functions have a prototype field.

<b>

> Understanding how JavaScript walks the prototype chain to locate an object’s methods is important because it allows us to override the definition of a method that an object would otherwise inherit from its prototype.

### Overriding a Method

```js
let moona = new Cat("Moona");
moona.sayHello = function () {
  console.log(`HELLO!!! I'M ${this.name.toUpperCase()}!`);
};
moona.sayHello();
❶ HELLO!!! I'M MOONA!
kiki.sayHello();
❷ Miaow! My name is Kiki.
```
