## React Notes

### What is React?
What exactly is React? It's not an MVC like .NET or Rails. At its core, it's a library for developing the view layer. A library focuses on one piece of functionality and that's exactly what React does. It isn't concerned with the back-end of an application. Instead, it manages how user interfaces look and behave.

React is also highly dynamic. This means it can handle views that need to change a lot. React allows us to quickly and dynamically update the UI without reloading pages. Any application or site that requires frequent updates is a great candidate for React.

### Functional Programming with JavaScript
--------------------

### `Immutability `
* The variable cannot change (const instead of let).

### `Pure Function`
* Given a specific input, a pure function always returns the same output. It will always return something. It does not alter anything else in the application. It cannot rely on external variables or state.

`example:`
```JS
function addOne(num) {
return num + 1;
}
```
* A result isn't pure if you can get different results from the same input. 

### `First Class Citizens (Functions)`
* Very loosely, this just means we can use a function in the same way we use a variable.

### `Functions returning functions`
* A function that returns yet another function is known as a higher order function. Functions that take other functions as arguments are also higher order functions as well.
```JS
function doAThing() {
  return function() {
    return "A thing was done."
  }
}
```
```JS
> doAThing()()
'A thing was done.'
```

### `Closures`
[Lesson](https://www.learnhowtoprogram.com/react/functional-programming-with-javascript/closures)

* A closure is an inner function that has access to variables from an outer function. In JavaScript, closures are created every time a function is created. A callback function is an example of a closure `only if` it has access to the outer function's variables.

* Examples:
```JS
function welcome(salutation) {
  return function(yourName) {
    return `${salutation}! Nice to meet you, ${yourName}!`
  }
}
```
* A closure needs to be assigned to a variable so it can be used elsewhere.
```JS
const heyThere = welcome ("Hey there!");
```
```JS
> heyThere("Joe")
"Hey there! Nice to meet you Joe!"
```
```JS
> const spanishGreeting = welcome("Buenos días!");
> spanishGreeting("Joe");
"Buenos días! Nice to meet you, Joe!"
```

```JS
function howManyEvenNumbers(userInputArray) {
  let instances = 0;
  userInputArray.forEach(function(element) {
    if (element % 2 === 0) { 
      instances++; // we have access to `instances` thanks to closures
    }
  });
  return instances;
}

howManyEvenNumbers([2,3,4,5,6,7]);
// returns 3
```


### `Currying`
* When we curry a function, we take a function with multiple arguments and then rewrite it as a series of functions, each with one argument. A function eith only one argument is also known as a `unary function``.
```JS
function aThingIMaybeLike(howMuchILikeIt) {
  return function(thing) {
    return function(reason) {
      return `I ${howMuchILikeIt} ${thing} because ${reason}.`;
    }
  }
}

> aThingIMaybeLike("really like")("functional programming") ("it's cool")
"I really like functional programming because it's cool."
```

### `map()`
* Use Array.prototype.map() whenever you want to modify every element in an array.
```JS
const doubledArray = numArray.map(e => e * 2);
```
### `reduce()`
* We can use Array.prototype.reduce() to reduce an array to a single element. One of the most common usages is to sum an array:
```JS
const numArray = [3, 7, 5];

const summedArray = numArray.reduce(function(currentValue, element) {
  return element + currentValue;
}, 0);
```
### `sort()`

### `filter()`
* Use Array.prototype.filter() whenever you want to filter an array based on certain conditions.
```JS
const numArray = [7, 14, 32, 8];
const filteredArray = numArray.filter(e => e > 10);
```
* filters the array for number greater than 10.

### `Recursion`
* Functions that call themselves. Great way to replace a for or forEach loop in a problem and impress during whiteboard interviews. They shoudl always include a `base case` and `termination case`.
* Make sure to always `return` the recursive function after each branch.

### `Testing`
* Using Jest and Babel for testing.
* Importing multiple functions to one test suite.
  * [link](https://www.softwaretestinghelp.com/jest-testing-tutorial/)   

### `JSX`
React uses a special syntax called JSX that allows developers to mix HTML with JavaScript. While not mandatory, developers report that JSX makes developing in React much easier. Nearly all React applications use JSX syntax. We'll use JSX, too.

### `create-react-app`

* Creates a boilerplate React app 
* $ npx create-react-app [File Name]

### `React Components`
Components are the building blocks for React. Everything in a React app is a component.

* A Functional component is a function that returns code stored inside the div.








