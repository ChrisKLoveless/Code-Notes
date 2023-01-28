## React Notes

### Functional Programming with JavaScript
--------------------

### ```Immutability ```
* The variable cannot change (const instead of let).

### ```Pure Function```
* Given a specific input, a pure function always returns the same output. It will always return something. It does not alter anything else in the application. It cannot rely on external variables or state.

```example:```
```
function addOne(num) {
return num + 1;
}
```
* A result isn't pure if you can get different results from the same input. 

### ```First Class Citizens (Functions)```
* Very loosely, this just means we can use a function in the same way we use a variable.

### ```Functions returning functions```
* A function that returns yet another function is known as a higher order function. Functions that take other functions as arguments are also higher order functions as well.
```
function doAThing() {
  return function() {
    return "A thing was done."
  }
}
```
```
> doAThing()()
'A thing was done.'
```

### ```Closures```
[Lesson](https://www.learnhowtoprogram.com/react/functional-programming-with-javascript/closures)

* A closure is an inner function that has access to variables from an outer function. In JavaScript, closures are created every time a function is created. A callback function is an example of a closure ```only if``` it has access to the outer function's variables.

* Examples:
```
function welcome(salutation) {
  return function(yourName) {
    return `${salutation}! Nice to meet you, ${yourName}!`
  }
}
```
* A closure needs to be assigned to a variable so it can be used elsewhere.
```
const heyThere = welcome ("Hey there!");
```
```
> heyThere("Joe")
"Hey there! Nice to meet you Joe!"
```
```
> const spanishGreeting = welcome("Buenos días!");
> spanishGreeting("Joe");
"Buenos días! Nice to meet you, Joe!"
```

```
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


### ```Currying```
* When we curry a function, we take a function with multiple arguments and then rewrite it as a series of functions, each with one argument. A function eith only one argument is also known as a ```unary function``.
```
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

### ```map()```
* Use Array.prototype.map() whenever you want to modify every element in an array.
```
const doubledArray = numArray.map(e => e * 2);
```
### ```reduce()```
* We can use Array.prototype.reduce() to reduce an array to a single element. One of the most common usages is to sum an array:
```
const numArray = [3, 7, 5];

const summedArray = numArray.reduce(function(currentValue, element) {
  return element + currentValue;
}, 0);
```
### ```sort()```

### ```filter()```
* Use Array.prototype.filter() whenever you want to filter an array based on certain conditions.
```
const numArray = [7, 14, 32, 8];
const filteredArray = numArray.filter(e => e > 10);
```
* filters the array for number greater than 10.

### ```Recursion```
* Functions that call themselves. Great way to replace a for or forEach loop in a problem and impress during whiteboard interviews. They shoudl always include a `base case` and `termination case`.







