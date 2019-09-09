# Week 6 - Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY1-green)

<img src="https://cdn.pixabay.com/photo/2015/04/23/17/41/javascript-736400_960_720.png" width="100" height="100" /> <img src="https://miro.medium.com/max/1200/1*aeFzjKB-7Y804GicKxk5Rg.jpeg" height="100" />


JavaScript Basics notes:

# Introduction to ES6 and Beyond

JavaScript is an ever growing languages and new features are introduced all the time. 

The ES6 or ECMAScript 2015 introduced tons of new useful features. All modern JavaScript frameworks use many features from from ES6 and you will have to write in ES6 to be able to use them. 

A lot of this tutorial and examples are taken from Luke Hoban's ES6 features repository, [https://github.com/lukehoban/es6features#readme](https://github.com/lukehoban/es6features#readme), please give it a star if you liked it!

By the end of the ES6, you should be understand the following topics:

Part I
1. Tempelate Literals
2. Object Literals
3. Arrow function
4. let/const

Part II

5. Class
    3.A. Inheritance  
    3.B. super
6. Spread, Rest, Default operator
7. Destructuring

Although there are more features/changes made in `ES6` (ES2016) or even `ES20` (ES2020), these should be sufficient for now. 

# 1. `Template literals`

<img src="https://i.imgur.com/Vly3m4o.png" height="300"/>


Template literals are string literals that allow you to embed expressions and values within strings.

Template literals are enclosed by the back-tick (` `) or grave accent
character instead of double or single quotes. 

**Example:**

```javascript

let x = "Hello world!" //This is a regular string literal
let y = `Hello World!` //This is a template literal

```

**Some Cool features of template literals:**

Makes it really easy to write Multi-line strings:

```javascript
`This is the first line
and this is the second line.`
```
**Output:**

```javascript
'This is the first line\nand this is the second line.'
```
Notice how the `\n` newline character is automatically inserted.

The key feature is expression interpolation or the ability to embed expressions within strings. 

```javascript
var a = 5;
var b = 10;
console.log(`Fifteen is ${a + b} and not ${2 * a + b}.`);
```
This saves time on writing and managing a lot of `+` operators within strings.

You can also call functions within these expressions.

There are a few more cool features that you can read about on MDN [Template Literals MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) 


# 2. `Object literals`
A cleaner way to assign to objects

[Template Literals - Object Literals](https://codepen.io/albseb511/pen/gOYvKzV?editors=1111)
```javascript

function Car(model,make,year) {
  const details = {
    model,
    make,
    year // Instead of year:yar
  }
  var km = 0
  console.log(details)
}

```

# 3. `Arrow Function`

Arrow functions are a simpler and more compact way of writing functions in JavaScript.
Two factors influenced the introduction of arrow functions: 
the need for shorter functions and the behavior of the this keyword.

### `ES5 Syntax`
```javascript
function (argument) {
    ...
    do something
    ...
}
```

### `ES6 Syntax`
```javascript
(args) => {
    do something
}
```
or...
```
(arg) => {} 
// the parantheses () are sometimes optionsal depending on no of arguments you have
// The curly brackets {} are also sometimes optional 
```

```javascript
double = (x) => {
    return x*2
    }
//or
double = x => x*2
//or
double
//is the same as

function double(x){
    return x*2
}
```
<img src="https://miro.medium.com/max/1200/1*o-wasL_EjWk4g8velrI8bg.jpeg" height="300" />

`Codepen Examples:`

[Arrow Functions](https://codepen.io/albseb511/pen/mdbOmPa?editors=0112)

[MDN example](https://codepen.io/albseb511/pen/wvwovbm?editors=1112)

[this example](https://codepen.io/albseb511/pen/MWgbmpb?editors=0012)

The new arrow functions also ensures that 'this.' is handled better

### Example taken from MDN
[Link to MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#Shorter_functions)

```javascript
var elements = [
    'Hydrogen',
    'Helium',
    'Lithium',
    'Beryllium'
  ];
  
  var a,b,c,d,e,f,g;

  // This statement returns the array: [8, 6, 7, 9]
  a = elements.map(function(element) {
    return element.length;
  });
  
  // The regular function above can be written as the arrow function below
  b = elements.map((element) => {
    return element.length;
  }); // [8, 6, 7, 9]
  
  // When there is only one parameter, we can remove the surrounding parentheses
  c = elements.map(element => {
    return element.length;
  }); // [8, 6, 7, 9]
  
  // When the only statement in an arrow function is `return`, we can remove `return` and remove
  // the surrounding curly brackets
  d = elements.map(element => element.length); // [8, 6, 7, 9]
  
  // This destructuring parameter assignment can also be written as seen below. However, note that in
  // this example we are not assigning `length` value to the made up property. Instead, the literal name
  // itself of the variable `length` is used as the property we want to retrieve from the object.
  e = elements.map(({ length }) => length); // [8, 6, 7, 9]

  console.log(a);
  console.log(b);
  console.log(c);
  console.log(d);
  console.log(e);

```
# 4. `let/const`

<img src="https://i.imgur.com/VMB4uJs.png" height="300" />


var is scoped to the nearest function block and let is scoped to the nearest enclosing block, which can be smaller than a function block. Both are global if outside any block.
variables declared with let are not accessible before they are declared in their enclosing block.

`Syntax`
```javascript
let name_of_your_variable;
const name_of_your_variable;

let a = 'this is a let variable';
const b = 'this is a constant';
```

`Example of definition`: [Codepen Example](https://codepen.io/pen/?editors=1112)
```javascript
// let and const
// Definitions examples and differences
// var is a global scope, and the compiler 

console.log(firstname) // --> Error as firstname is a let


console.log(fullname)
// variables declared with let are not accessible before they are declared in their enclosing block.

let firstname = 'Masai'


var fullname= 'Masai School'


const lastname = 'School'

lastname= 'Seb' // --> Error as const cannot be set twice

console.log(firstname)
//expects Masai

console.log(fullname)
//expects Masai School

console.log(lastname)
//expects School


```

`Example of scope`: [Codepen Example](https://codepen.io/albseb511/pen/gOYLobG?editors=0011)

```javascript
// let and const
// Scope Example


function varTest() {
    var x = 1;
    if (true) {
      var x = 2;  // same variable!
      console.log(x);  // 2
    }
    console.log(x);  // 2
  }

  function letTest() {
    let y = 1;
    if (true) {
      let y = 2;  // same variable!
      console.log(y);  // 2
    }
    console.log(y);  // 1
  }

  function test(){
      {
        var a=100;
        let b =200;
        const c=300;

        if(true){
            console.log(a);
            console.log(b);
            console.log(c);
            }
        }
      if(true){
          console.log(a);
          console.log(b);//error b is not defined
          console.log(c);//error c is not defined
      }
  }


  
  varTest(); // Check varTest() function. 

  letTest();  // Check letTest() function. 

  test();   
  // Check letTest() function. 
  // First if statement will give no errors
  // Second if statement will give you an errors
  // console.log(`Value of x`,x)

```
