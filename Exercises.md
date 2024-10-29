## 5-2.  

You’ve now seen three different ways of creating functions: function declarations, function expressions, and arrow functions. Write each of the following in all three styles:

- A function that takes a number from 0 to 5 and returns the English word for that number. For example, 1 should return "one". Hint: use an array to define the mapping from numbers to strings.
- A function with no parameters that prints how many times it’s been called. Hint: define a variable outside of the function to keep track of the number of calls, like we did in the “Side Effects” section on page 77.
- A function that prints the current date and time. Hint: you can get the current date and time with new Date().

## 5-3

5-3.  Write a function called makeWrapper that takes a prefix and a suffix, and returns a new function that adds the prefix and suffix to a provided string. For example, you could enter let bracketWrapper = makeWrapper("[", "]"); and then call bracketWrapper("Bracket me!"); to get the string "[Bracket me!]". Likewise, you could enter let bracesWrapper = makeWrapper("{", "}"); and then call bracesWrapper("Brace Me!"); to get the string "{Brace me!}".
