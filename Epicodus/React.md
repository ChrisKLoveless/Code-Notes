## React Notes

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

### ```Fisrt Class Citizens (Functions)```
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


