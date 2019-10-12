# Week 7 - Day 3

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK7-DAY2-green)

<img src="https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png" width="100" height="100" /> 

## Introduction to ReactJS Part 2 -B

`Imperative vs Declarative:`

A declarative style, like what react has, allows you to control flow and state in your application by saying "It should look like this". An imperative style turns that around and allows you to control your application by saying "This is what you should do".

The benefit of declarative is that you don't get bogged down in the implementation details of representing the state. You're delegating the organizational component of keeping your application views consistent so you just have to worry about state.

React:
```javascript
// Guitar component will create the rest for you
// Declarative approach
<Guitar string={6} size='large' neck={19}>


//Imperative

//Create head - psuedo code
head = createElemend('head')
if size large
    create largebody

//Create neck - psuedo code
createElementNeck
for no of necks
    createElement fret
    append fret to head
    
//Create body and strings - psuedo code
createElementString
for no of strings
    createElement strings
    append strings to head
    
So you can see that this is a long process to write the code for imperative programming

```
React library will take care of DOM manipulation for us, so its faster and easier to write programs
with lesser bugs.

### PERFORMANCE ADVANTAGES

- We write what we want and React will do the hard work for us
- React uses a virtual DOM. [Reconcilliation](https://reactjs.org/docs/reconciliation.html) 


## [`State and Lifecycle`](https://reactjs.org/docs/state-and-lifecycle.html)


State is an internally managed configuration for any component. 
Component can be made with classes, and this.state is part of 
Let us take this example of creating a simple timer

```javascript
function App(props) {
  return <div className="App">{props.count}</div>;
}
//  count is defined here
var count = 0;

const rootElement = document.getElementById("root");

// ReactDOM.render is called every 1000ms, and with that
// count value is incremented by 1
// count is passed as prop into the Component App as well
setInterval(() => {
  ReactDOM.render(<App count={count++} />, rootElement);
}, 1000);
```


[Codesanbox State Example](https://codesandbox.io/s/47wzj)

[Event Handling Example](https://codesandbox.io/s/zdcf9)


## `LifeCycle` of a Component

Any react component that extends `React.Component` almost like a living organism will go through the following phases in its lifetime:

1. Mounting
2. Updating
3. Unmounting


Lets go though each phase in-depth:

1. Mounting: This is the phase when a component is created and inserted into the DOM.
When this happens the following methods are called in same order as below:

    - `constructor`: [https://reactjs.org/docs/react-component.html#constructor](https://reactjs.org/docs/react-component.html#constructor)
    - `getDerivedStateFromProps`: [https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)
    - `render`:  [https://reactjs.org/docs/react-component.html#render](https://reactjs.org/docs/react-component.html#render)
    - `componentDidMount()`: This is a `lifecycle` method that is called right after a component is **mounted** or rendered. We can use this method to modify state right after a component is rendered to the DOM using `setState`. [https://reactjs.org/docs/react-component.html#componentdidmount](https://reactjs.org/docs/react-component.html#componentdidmount)
2. Updating: After the react component has been mounted, it can then recieve new updates through new props being sent by parents or from updating the state.
When this happens the following methods are called in the same order as below:

    - `static getDerivedStateFromProps()`: [https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)
    - `shouldComponentUpdate()`: [https://reactjs.org/docs/react-component.html#shouldcomponentupdate](https://reactjs.org/docs/react-component.html#shouldcomponentupdate)
    - `render()`: This is the same render method as before.
    - `getSnapshotBeforeUpdate()`: [https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate](https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate)
    - `componentDidUpdate()`: This method is called right after a component updates. This method is usually used to perform DOM operations when a component has been updated. [https://reactjs.org/docs/react-component.html#componentdidupdate](https://reactjs.org/docs/react-component.html#componentdidupdate)
3. Unmounting: This is the pahse when a component is not needed anymore and has been unmounted from the DOM. It only contains one method:
    - `componentWillUnmount()`: This method is called right before a component is unmounted or destroyed. [https://reactjs.org/docs/react-component.html#componentwillunmount](https://reactjs.org/docs/react-component.html#componentwillunmount)

If that was too confusing, here is a simple graphic:

[http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)

While there are many lifecycle methods the most important one's you should be focusing on are:

- `constructor()`
- `render()`
- `componentDidMount()`
- `componentDidUpdate()`
- `componentWillUnmount()`

The rest are not as commonly used but can provide additional functionality when required.


Lets take a look at a simple example to see how these methods are executed during the lifecycle of a component:

**CodePen Link:** [https://codepen.io/steviekong/pen/LwbvoY?editors=0011](https://codepen.io/steviekong/pen/LwbvoY?editors=0011)

Lets better understand these lifecycle methods by doing an example:

Remember in the first tutorial we made a `Clock` that called `ReactDOM.render` multiple times? 

We are going to rewrite that code using the lifecycle methods we learned above. 

**CodePen Link:** [https://codepen.io/steviekong/pen/wVoZJz?editors=1010](https://codepen.io/steviekong/pen/wVoZJz?editors=1010)

## `Conditional Rendering`:

Often you will want to render components based on a condition. This can easily be done in react by using a conditional `if` within the render function.

```javascript
class App(){
render(){
    if(condition){
        return(
            <Component if true />
        )
    }
    else 
        return( <Component if false>)
}
}

```


[Codesandbox example](https://codesandbox.io/s/qidhd)

**Example:** 

[https://codepen.io/steviekong/pen/RXozRB?editors=1011](https://codepen.io/steviekong/pen/RXozRB?editors=1011)

You can also embed javascript expressions within JSX to perform conditional rendering.

**Example:**
[https://codepen.io/gaearon/pen/ozJddz?editors=0010](https://codepen.io/gaearon/pen/ozJddz?editors=0010)

**Using the conditional(ternary) operator:**

The conditional operator is often used as a shorthand for the if statement. 

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

This can be really useful in react for in-line conditional rendering.
Here is the login button example with the conditional operator.

**Example:**
[https://codepen.io/steviekong/pen/MNbMPJ](https://codepen.io/steviekong/pen/MNbMPJ)

**Preventing components from rendering:**

Sometimes you may want to hide or delete components after rendering it. 

To do this return `null` instead of any JSX in the render function. 

**Example:**

[https://codepen.io/gaearon/pen/Xjoqwm?editors=0010](https://codepen.io/gaearon/pen/Xjoqwm?editors=0010)

## Using setInterval the right way using `componentWillUnmount`

An great use-case for `componentWillUnmount` is the following example.

Here's the right way to do this:

[https://codepen.io/peterbe/pen/LNxmRp?editors=0010](https://codepen.io/peterbe/pen/LNxmRp?editors=0010)

Here's the wrong way to do this:

[https://codepen.io/peterbe/pen/VaPXNL?editors=1010](https://codepen.io/peterbe/pen/VaPXNL?editors=1010)


