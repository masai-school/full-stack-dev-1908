# Week 7 - Day 2

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK7-DAY2-green)

<img src="https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png" width="100" height="100" /> 

## Introduction to ReactJS Part 2 -B

[Documentation](https://reactjs.org/docs/lists-and-keys.html)

First, let’s review how you transform lists in JavaScript.
```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);
console.log(doubled);

//This code logs [2, 4, 6, 8, 10] to the console.
```
## `Rendering Multiple Components`

You can build collections of elements and include them in JSX using curly braces {}.

Below, we loop through the numbers array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to listItems:

```javascript
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
```

We include the entire listItems array inside a ul element, and render it to the DOM:


```javascript
ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```

[Codepen](https://codepen.io/gaearon/pen/GjPyQr?editors=0011)

When you run this code, you’ll be given a warning that a key should be provided for list items. A `“key”` is a special string attribute you need to include when creating lists of elements.

## `Keys`

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:


```javascript
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);
```
