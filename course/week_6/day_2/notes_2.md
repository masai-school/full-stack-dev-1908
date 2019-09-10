# Week 6 - Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY_2_B-green)

<img src="https://cdn.pixabay.com/photo/2015/04/23/17/41/javascript-736400_960_720.png" width="100" height="100" /> 

## `localStorage` 


`localStorage` property allows you to access a Storage object for the Document's origin; the stored data is saved across browser sessions. `localStorage` is similar to `sessionStorage`, except that while data stored in `localStorage` has no expiration time, data stored in `sessionStorage` gets cleared when the page session ends — that is, when the page is closed.

The keys and the values stored in localStorage are always `strings` (note that, as with objects, integer keys will be automatically converted to strings).


`Syntax`
```javascript

myStorage = window.localStorage;

A Storage object which can be used to access the current origin's local storage space.
```

`Example`
```javascript
// The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().
localStorage.setItem('myCat', 'Tom');

// The syntax for reading the localStorage item is as follows:
var cat = localStorage.getItem('myCat');

// The syntax for removing the localStorage item is as follows:
localStorage.removeItem('myCat');

// Clear all items
localStorage.clear();

// use JSON.parse() to convert the string to an object
loadVal = JSON.parse(localStorage.getItem('name'))

// use JSON.stringify() to convert an object to a string.
localStorage.setItem('name',JSON.stringify(users))
```


[localStorage - MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)

Also read on [Session Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)
