# Week 7 - Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK7-DAY1-green)

<img src="https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png" width="100" height="100" /> 

## Introduction to ReactJS Part 1

**What is React Js?**

In short, `React` is a JavaScript library for building web interfaces. A library is a group of files that contains objects and functions/methods that collectively accomplish a useful task. 

You have already been using in-built libraries in JavaScript and React is just a library written by a third-party. 

React is a declarative, efficient, and flexible JavaScript library for building user interfaces.

We will be closely following the ReactJS official docs available on [https://reactjs.org/](https://reactjs.org/)


## Getting started  

We will be doing most of our development on local JS files but all the examples will be on codepen.io

Lets write a simple hello world program. 

[https://codepen.io/steviekong/pen/PrrMXE?editors=1010](https://codepen.io/steviekong/pen/PrrMXE?editors=1010)

You might already recognize most of the html code.

Lets look at what is new:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.26.0/babel.min.js"></script>
 <script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
```
Here we import the ReactJS libraries over the Internet through something called a CDN. 

Make sure you have these three lines in your `body` tag when you write any react applications in HTML files. 

```javascript
ReactDOM.render(
  <h1>Hello, world!</h1>,
  document.getElementById('root')
);
```
`ReactDOM` is a global object provided by the React JS library. It contains a `render` functions that accepts 2 arguments.

The first argument is a **JSX** object and the second is the `HTML` container element onto which we are rendering the the `JSX` as a child.

When the `render` function is called it renders a react object into the DOM as a child of the `container` element. In this case the `container` is a `div` element with the `id` ***root***. 

## `JSX`

**What is JSX?**

In formal terms JSX is a preprocessor that adds XML or HTML syntax to Javascript. 
There are other preprocessors you could use but JSX and React go hand in hand so it is very easy to use the two of them. 

You could also write react without JSX but JSX makes react much more readable as it is visually similar to HTML and much easier to write. For more about react without JSX, read this [https://reactjs.org/docs/react-without-jsx.html](https://reactjs.org/docs/react-without-jsx.html).

JSX produces "Elements" which you can then render to the DOM.


**Lets try writing some JSX**

```javascript
const welcome = <h1>Welcome to Masai School</h1>
```
This is a simple JSX element store in the constant called `welcome`.

You can then render it by calling `ReactDOM.render`.

Take a look at the following example. 

[https://codepen.io/steviekong/pen/qzeEZe](https://codepen.io/steviekong/pen/qzeEZe)

**Lets write some larger JSX elements:**

[https://codepen.io/steviekong/pen/LKwxPd?editors=1000](https://codepen.io/steviekong/pen/LKwxPd?editors=1000)

Notice how we wrapped all the elements in a `div` tag. This is because JSX must return a single element. Several JSX elements who are siblings with no parent are invalid JSX and will not transpile. 

**Valid JSX:**

```html
<div>
<h1>Shopping Cart</h1>
<ul>
  <li>Apples</li>
  <li>Oranges</li>
  <li>Banana</li>
</ul>
</div>
```

**Invalid JSX:**

```html
<h1>Shopping Cart</h1>
<ul>
  <li>Apples</li>
  <li>Oranges</li>
  <li>Banana</li>
</ul>
```

**Embedding Expressions within JSX:**

You can also embed JavaScript expressions within JSX. We do this by wrapping the expressions within `{}` curly brackets. 

[https://codepen.io/steviekong/pen/pXMpqQ](https://codepen.io/steviekong/pen/pXMpqQ)

[https://codepen.io/steviekong/pen/pXMaJY?editors=1000](https://codepen.io/steviekong/pen/pXMaJY?editors=1000)

**JSX evaluates to a JavaScript Object:**

After the code compiles, JSX expressions become regular javascript objects. This means just like any other other object, you can store it inside variables, return it from functions, use it within if statements, for loops etc. 

[https://codepen.io/steviekong/pen/orKqXd?editors=1010](https://codepen.io/steviekong/pen/orKqXd?editors=1010)

**Updating Rendered Elements:**

React elements are immutable which means that once you create an element it cannot be changed in any way. However you can render element again to get different results. 

Here is an example from the react docs given here [https://reactjs.org/docs/rendering-elements.html](https://reactjs.org/docs/rendering-elements.html)

Here is that same example on codepen [https://codepen.io/steviekong/pen/bPXMPM](https://codepen.io/steviekong/pen/bPXMPM)

As you can see it calls the function to re-ender the `h2` element with new values each second.

If you inspect the element within the developer console, you can see that only that time string value within the `h2` element is being updated, not the whole DOM and not even the other text within the `h2` element. 

This is because React is smart and uses a [**Virtual DOM**](https://reactjs.org/docs/faq-internals.html) and a smart [**Reconciliation Algorithm**](https://reactjs.org/docs/reconciliation.html) to compare the difference and only perform the necessary changes to the DOM.

Lets look at a simple example with a pre-defined button. The DOM will render after the button is clicked.

[https://codepen.io/steviekong/pen/OeKENZ](https://codepen.io/steviekong/pen/OeKENZ)

**Note:** Most react applications will only call render once. In the next few classes we will learn about components and state which we will use to render the DOM in a much more powerful way.





### Setting up a React app using NPM and nodeJS

While writing react apps into HTML isn't incorrect, it can be tedious.

Most react apps are developed as standalone front-end apps which can then interact with an API backend. 

Instead we use the `create-react-app` NPM package developed by Facebook to give us some starter files with `boilerplate` code along with a basic file structure into which we can develop our own ReactJS app.

To read more about the `create-react-app` package you can visit their official github repository [https://github.com/facebook/create-react-app](https://github.com/facebook/create-react-app).

Follow these steps to setup and run a react app locally:

1. Make a directory where you would want to create a react app and `cd` in to the directory. 
2. Make sure you have NPM installed by running `npm --version`. This should show you the version number of NPM you have installed.
3. Then run `npm install -g create-react-app`. 

**Breaking down this command:**

`npm install <package_name>` is how you install any package in NPM. 
The `-g` flag tells NPM to install that package globally rather than locally. This allows us to use this package from the command-line.
(Note: Some of you might need to run `sudo` before the command, dependent on your systems write permissions.)

If all goes well you should see something like `added 91 packages from 45 contributors in 15.389s` in your terminal. 
`
4. Now run `create-react-app <name_of_your_app>`. This will take a bit of time since this is building a lot of files so be patient!

If all goes well you should get a message that says `Happy Hacking!`. 

You will observe that a folder with the name of you app has been created.
This contains all the files necessary for your react app. All new files you create will be within this folder.

Before we start creating our app lets understand why we had to go through this process.

**Why did we have do to all of this??**

If you run `sudo du -sh <folder_name>` on the project folder you created you might notice it is around `200`+ MegaBytes!

An obvious question might be, why? What is in this folder? Do I need all of this? Why is it so large? My HTML file was very small!

A large portion of this is taken up by NPM `packages`. These are libraries which contain code that other programmers wrote and have hosted on NPM which is a package manager for NodeJS. 

`create-react-app` dependents on these libraries to work correctly so these packages are also called **dependencies**. In many cases these ***dependencies** also dependent on other dependencies and so on..

You can visualize these dependencies here [http://npm.broofa.com/?q=create-react-app](http://npm.broofa.com/?q=create-react-app)

As you can see, `create-react-app` depends on 83 different dependencies. 

You can also use `npm ls` to see all the dependencies on your terminal. 

Note:

Please make sure that you do not add node_modules folder to your git repository.



**`Babel`:**

While there are many dependencies I want to draw you attention to `Babel`. We have used this before by linking it through a script tag. 

But, what is `Babel` and what does it do?

Anyone who has read the **HitchHikers Guide to the Galaxy** will know of the Babel fish which can translate between any language in the universe.

Similarly the `Babel` package is used to translate from ES6  and above back to ES5. In our case, Babel also performs the necessary translations from `JSX` syntax to regular JavaScript. This is useful since this allows our code to run on virtually any browser that supports ES5 features. 

For this reason `Babel` is often called a Transpiler as it does both translation as well as compilation of Javascript code. 

To learn more about `Babel` visit their website `https://babeljs.io/docs/en/`.

**Learning more about the files and folders in the app:**

This should give you a short overview of all the important files and folders in the project/app directory. We will discuss each of these in detail at a later time. 

1. `src`: This is where we will put all the JS code we write.
2. `public`: This folder is used to store static files like images, text files, html files, icons etc. 
3. `node_modules`: This is the folder where NPM stores all the dependencies for our project. If you LS into that folder you can see all of them. 
4.`package.json`: This file contains the configuration for our project including the dependencies as well as some starter scripts. 
5. `package-lock.json`: This file contains the exact version numbers for all the dependencies we are using.
6. `README.md`: This file is used to tell any developers or users about your project. It should include information about your project, as well as instructions on how to set it up and run it. Github natively displays this file at the homepage of a repository and you might have seen before. 



## Starting and stopping your project

To start your app use `npm start`.

You should see your project running on your browser at the url `localhost:3000`.

To stop your app return to the terminal and press `Control+c`.

When you look at your browser you should get a page with the react logo and a prompt `Edit src/App.js and save to reload`.

Once we change some code in `App.js` we should see the result here. 



## Writing a simple Hello World App

Open up the src folder and delete all the files within. We want to start fresh so delete everything in there.

Now create a file called `index.js`. 

**Import statements:**

Add these two lines to your code

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
```

What are these statements?

`import` statements allow us to use objects and functions from dependencies or modules. 

Lets break down each part of the import statement:

`React` is the variable we want to assign to this import. 

We write `from` before we specify the name of the dependency or path to the file we want to include.

`react` is the name of the dependency that we are importing. 

You can use `import` statements to import any dependency that you include in your project. 

You can also use `import` statements to import JS files that you create.

You can read more about it here [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)

**Creating and displaying a simple component:**

Open up `public/index.html`. This is a fairly normal HTML file. 

Notice there is a div with the `id="root` we will use this as the parent element for our react app to which we will attach all our components to. 

Now go back to index.js and create a simple component and render it to the DOM. 

```jsx
//Create a React Compoenent
const App = () =>{
    return <h1>Hello world</h1>;
};

//Render it to the DOM
ReactDOM.render(
    <App />, 
    document.getElementById('root')
);
```

The example covered here can be seen at [https://github.com/masai-school/full-stack-dev/tree/master/course/week_7/day_1/session1/hello_world](https://github.com/masai-school/full-stack-dev/tree/master/course/week_7/day_1/session1/hello_world). 

If you want to run the above app locally, you must clone the repository and run `npm install` within the project folder to install all the required dependencies. 




## Creating multiple components in different files

When you start working on larger projects you want to structure your project folder in a meaningful way. 

Usually a react project will have a separate components folder where all your components are stored. 

The task of `index.js` will be to simply call `ReactDOM.render`.

I'm going to create a new project called `multiple_test`.

To start out, I create a folder called `components` within the `src` folder. 

In here I'm going to write create a file called `SimpleList.js` which will be a basic list component which will render an ordered list. 

Here is the code for the SimpleList component: 

```jsx
import React from 'react';

class SimpleList extends React.Component{
    render(){
        return (
            <ol>
                <li>Apple</li>
                <li>Banana</li>
                <li>Watermelon</li>
            </ol>
        );
    }
}

export default SimpleList
```




Here I created a component called `SimpleList`. In the last line I used the `export` statement so that any import statements used in other JS files could have access to the `SimpleList` class that I created here. 

For more on import statements check out the MDN documentation [https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export](https://developer.mozilla.org/en-US/docs/web/javascript/reference/statements/export)

I will also create an `App` component which will render multiple `SimpleList` components. 

Here is the code for the App component. 

```jsx
import React from 'react';
import SimpleList from './SimpleList.js'

class App extends React.Component{
    render(){
        return (
            <div>
                <h1>Shopping List</h1>
                <SimpleList />
                <SimpleList />
                <SimpleList />
            </div>
        );
    }
}

export default App
```

Finally I use `ReactDOM.render` in my `index.js` file to render the `App` component.

Here is the `index.js` code:
```jsx
import React from 'react';
import ReactDOM from 'react-dom';
import App from "./components/App.js"


ReactDOM.render(<App />, document.getElementById('root'));
```

You can check the source code out for this app here [https://github.com/masai-school/full-stack-dev/tree/master/course/week_7/day_1/session1/multiple_test](https://github.com/masai-school/full-stack-dev/tree/master/course/week_7/day_1/session1/multiple_test).





## Adding styles and CSS modules

It is commonplace in react to have a style-sheet for each component as this can help you retain a lot of modularity. 

You can add styles in many ways, including including inline styles, style object literals.

Here we will be using CSS Modules which offer many advantages including local scoping and class composition.  

Lets add some CSS to the `multiple_test` app. 

For the `App` component, I make a new css file called `app.module.css` in my components folder.

Any new CSS modules must follow the syntax `<name>.module.css`.

Here is the code for `app.module.css`:

```css
.header{
    color: blue;
    border: 1px groove black;
    background-color: lightgrey;
}
```
**Note:** Since this is not JSX you can use regular CSS syntax.

Now I have to import these styles from my `App` component. 

Updated code in app component:

```jsx
import React from 'react';
import SimpleList from './SimpleList.js'
import styles from './app.module.css'

class App extends React.Component{
    render(){
        return (
            <div>
                <h1 className = {styles.header} >Shopping List</h1>
                <SimpleList />
                <SimpleList />
            </div>
        );
    }
}

export default App
```

The only changes are `import styles from './app.module.css'` which imports the styles and `className = {styles.header}` which adds the header style to the `H1` tag. 

Lets also add styles to the `SimpleList` component. 

I create a file called `simpleList.module.css` and add the following css into it. 

```css
.list{
    font-family: monospace;
    font-size: 2em;
    margin: 2em;
    padding: 0;
    list-style-type: '> ';
}
```
Then I add a few lines of code to add the styles to my component. 

```jsx
import React from 'react';
import styles from './simpleList.module.css'

class SimpleList extends React.Component{
    render(){
        return (
            <ol className = {styles.list}>
                <li>Apple</li>
                <li>Banana</li>
                <li>Watermelon</li>
            </ol>
        );
    }
}

export default SimpleList
```

This is the basics of using CSS modules. For a deeper look visit [https://programmingwithmosh.com/react/css-modules-react/](https://programmingwithmosh.com/react/css-modules-react/)




## Adding images

Adding images is very simple. 

Any images you want to must be included in the `public` folder. 

I have added an image called `computer.jpg`.

Now I can render it in the App component with an image tag. 

```jsx
<img src = "/computer.jpg" height = "50%" width = "50%" />
```

React automatically knows the image is in the public directory so you don't need to include the entire path. 