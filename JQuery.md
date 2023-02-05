## JQuery Notes

### Set-up
1. $ npm i jquery
2. import * as $ from "jquery"

* Reference [link](https://github.com/ChrisKLoveless/plants)
* Use to create DOM elements 
```JS
export function createPlantElements(plantObject) {
  const thisPlant = $(
  <div>
  <button>
  <h1>
  )
}
```
* Query the DOM (use back-ticks)
```
$(`Here is a string with an ${element/value}`)
```
Useful Methods
* .on("click")
* .text("some text")