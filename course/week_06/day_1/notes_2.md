# Week 6 - Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY1-green)

<img src="https://cdn.pixabay.com/photo/2015/04/23/17/41/javascript-736400_960_720.png" width="100" height="100" /> <img src="https://miro.medium.com/max/1200/1*aeFzjKB-7Y804GicKxk5Rg.jpeg" height="100" />

Part II

5. Class

    3.A. Inheritance  
    3.B. super

6. Spread, Rest, Default operator

7. Destructuring

# 5. `Class`

Classes are syntactical sugar over the existing object oriented model in JavaScript. This means that it does not introduced any new features but improves upon old features. 

They are similar to function constructors that you have already studied but give you much more functionality with less code. 

**Example:**

```javascript
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
}

let box = new Rectangle(12, 13);
```


The `constructor` is a special function for initializing objects created with `class`. They work similar to function constructors.


They also support simple instance methods/functions with short declaration syntax. 

```javascript
class Rectangle {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }

  area(){
    return this.height * this.width;
  }

}

let box = new Rectangle(12, 13);
box.area();
```

## 5.A. `Inheritance`

Classes also support inheritance which means they can take properties and functions from other classes. 

For example lets say we have two classes `Car` and `Sedan`. 

`Car:`

```javascript
class Car{
  constructor(horsePower){
    this.horsePower = horsePower;
    this.fuel = 100;
  }

  consumeFuel(amount){
    this.fuel -= amount;
  }
}
let myCar = new Car(102);
```

`Sedan`
```javascript
class Sedan{
  constructor(name){
    this.name = name;
  }
  printName(){
    console.log(this.name);
  }
}
var mySedan = new Sedan('Civic');
```

Right now they are independent. Lets say we want `Sedan` to inherit or get the properties and functions of the `Car` object.

We can use the `extends` keyword to make `Sedan` a child of the `Car` class. This will allow `Sedan` to get properties and methods/functions of the parent class `Car`.

```javascript
class Car{
  constructor(horsePower, name){
    this.horsePower = horsePower;
    this.fuel = 100;
    this.name = name;
  }

  consumeFuel(amount){
    this.fuel -= amount;
  }
}

class Sedan extends Car{
  printName(){
    console.log(this.name)
  }
}

let mySedan = new Sedan(150, 'Civic');
mySedan.consumeFuel(10);
console.log(mySedan.fuel);
mySedan.printName();
```
MDN documentation [Classes MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)


## 5.B. `super`

Now what if we need to access the parent class's properties or functions in the child class? 

Also what if we want to declare a constructor for our child class?

The `super` keyword is used to access and call functions on an object's parent.

Lets update our above example with the super keyword. 
```javascript
class Car{
  constructor(horsePower, name){
    this.horsePower = horsePower;
    this.fuel = 100;
    this.name = name;
  }

  consumeFuel(amount){
    this.fuel -= amount;
  }
}

class Sedan extends Car{
  constructor(horsePower, name, numSeats){
    super(horsePower, name);
    this.numSeats = numSeats;
  }
  printName(){
    console.log(this.name);
  }

  updateHorsePower(input){
    super.horsePower = input;
  }
}

let mySedan = new Sedan(150, 'Civic', 4);

mySedan.updateHorsePower(300);

mySedan
```

It is important to note that when used in a constructor, the super keyword appears alone and must be used before the this keyword is used. 


[Codepen Example](https://codepen.io/albseb511/pen/MWgQPbe?editors=0011)
MDN documentation [super MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)



# 6. `Default, Spread, Rest Operators`

## `Default`
Pass in a default value if a proper value is not passed in the arguments or if it is undefined.
```javascript
function f(x, y=12) {
  // y is 12 if not passed (or passed as undefined)
  return x + y;
}
f(3) == 15
```
### Example

[Codepen Example](https://codepen.io/albseb511/pen/VwZmgNR)

![Code](https://i.imgur.com/wUPQGvu.png)
![Output](https://i.imgur.com/L5l8F8m.png)

## `Spread`

```javascript
function sum(x, y, z) {
  return x + y + z; 
}
// Pass each elem of array as argument
sum(...[1,2,3]) == 6

// x = 1
// y = 2
// z = 3
```
In the example below the var abc and contains 3 values each.
The spread operator basically lays out the entire array into seperate elements.
alpha contains 6 elements.

```javascript
var abc = ['a', 'b', 'c'];
var def = ['d', 'e', 'f'];
var alpha = [ ...abc, ...def ];
console.log(alpha)// alpha == ['a', 'b', 'c', 'd', 'e', 'f'];
```

## `Rest`
The example below shows how the arguments after the first is combined into an array.
```javascript
function f(x, ...y) {
  // y is an Array
  return x * y.length;
}
f(3, "hello", true) == 6
```

In the example below, the arguments 2, 3 & 4 are taken into an array others.
```javascript
function sum( first, ...others ) {
    for ( var i = 0; i < others.length; i++ )
        first += others[i];
    return first;
}
console.log(sum(1,2,3,4))// sum(1, 2, 3, 4) == 10;
```

# 7. `Destructuring`

The destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
This has been shown in the Rest and Spread operators. 

## Syntax
```javascript
var first, second, rest
[first,second,...rest]=[1,2,3,4,5,6,7,8,9,10]
console.log(first); // 1
console.log(second);// 2
console.log(rest);  // [3,4,5,6,7,8,9,10]
```
Destructuring can be applied to Arrays, Objects.

[Codepen - Destructuring](https://codepen.io/albseb511/pen/mdbXKBo)
```javascript
const contactDetails = {
    firstName: 'Masai',
    lastName: 'School',
    phone: '1234567890',
    city: 'Bangalore',
    state: 'Karnataka',
}

const {firstName,lastName} = contactDetails
const {firstName:fname,lastName:lname} = contactDetails


console.log(`${firstName} ${lastName}`)
console.log(`${fname} ${lname}`)

let [name, make, country] = ['Baleno', 'Maruti', 'Japan'];

console.log(country)
//Japan
```
Refer to [Destructuring MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)


# `Comments & References`

There are many more features we have yet to discuss but we will get to them at a later time. 

We really encourage you read a few if not all the extra links and documentation given to you.

If you feel like you are an intermediate to advanced level to understand Javascript, check this out.

[ES6 in Depth](https://hacks.mozilla.org/category/es6-in-depth/)

[https://github.com/lukehoban/es6features#readme](https://github.com/lukehoban/es6features#readme)