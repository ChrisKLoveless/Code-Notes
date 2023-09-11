# Big O Notation
Big O is an essential computer science concept. It is a `runtime` algorithm to determine how long a function takes to run and how much memory space is required.

Generally it is used to determine the worst case scenario or `upper bound`. This is technically the most time and memory the algorithm can possible use. Or how many operations. 

## Terms of RunTime

O(1) Time
is constant time, which means no matter how big the dataset is it will take the same amount of time.

ex:
```js
function returnFirst(array) {
  return array[0];
}
```

O(N) Time
is linear time, which means the larger the data set the longer the algorithm will take. Careful to also call this O(AB) when there is a nested loop and linear runtime. If the iterations are chained and not nested it is O(N).

ex:
```js
function doubledArray(array) {
  let doubledArray = [];
  array.forEach(function(element) {
    doubledArray.push(element * 2);
  });
return doubledArray;
}
```

O(N²)
is the squared version of O(N) and has a exponential curve instead of linear.
This runtime takes much longer as the data set gets bigger. Also known as quadratic time.

O(log(N)) Time
is known as logarithmic time. A logarithm is the `power` a number must have to be equal to another number. Log alone means powers of 10 and log with a number, like 3, means we are talking about powers of 3.

