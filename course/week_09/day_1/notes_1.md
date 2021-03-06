# Week 9 Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK9-DAY1-green)

## Introduction to Routing with React III

### Authentication and `Redirect`

While the front end is not used for authentication we might still want some routes to be protected. 

If a user visits once of these routes, they should be redirected to the login page or the home page, if they are not authenticated. 

To do this we can use the `<Redirect>` component from react router.  

You can read the documentaiton here [https://reacttraining.com/react-router/web/api/Redirect](https://reacttraining.com/react-router/web/api/Redirect)

To start out with lets create a `<Login>` component and a `/admin` route. 

If the user is not logged in, they will be redirected to the login page. If the are logged in, they can access the admin page. 

First lets create a `fakeAuth` object literal which will tell the application is a user is logged in or not. In a real application this information would be coming from the backend API. 

**Do not use this kind of function/login for security in a production environment!** 

```jsx
const fakeAuth = {
  isAuthenticated: false,
  authenticate(cb) {
    this.isAuthenticated = true;
    setTimeout(cb, 100); // fake async
  },
  signout(cb) {
    this.isAuthenticated = false;
    setTimeout(cb, 100);
  }
};
```

Next we can make components for `Admin` and `Login`.

```jsx
const Admin = (props) => {
    return (
        <React.Fragment>
            <h1> This is the admin page with some confedential information </h1>
            <p> Number of sales : 2 </p>
            <p> Number of users : 100 </p>
            <button onClick = {() => fakeAuth.signout()} > Sign Out </button>
        </React.Fragment>
    );
}

const Login = (props) =>{
    return (
        <React.Fragment>
            <h1> This is the login page </h1>
            <button onClick = {() => fakeAuth.authenticate()} > Sign In </button>
        </React.Fragment>
    );
}
```

Finally in the App component we can write the logic for the sign in and sign out.

```jsx
<Route path = "/admin" render = {props =>{
                        return fakeAuth.isAuthenticated ? 
                            <Admin {...props} /> :
                            <Redirect to = {{pathname : "/login", state: {from :props.location}}} />
                    }} />
                    <Route path = "/login" component = {Login} />
```


##### `push`:bool
The attribute push on Redirect when true, redirecting will push a new entry onto the history instead of replacing the current one.
```javascript
<Redirect push to='/location'>
```

#### `history`

[history Docs](https://reacttraining.com/react-router/web/api/history)

The term “history” and "history object" in this documentation refers to the history package, which is one of only 2 major dependencies of React Router (besides React itself), and which provides several different implementations for managing session history in JavaScript in various environments.

The following terms are also used:

    “browser history” - A DOM-specific implementation, useful in web browsers that support the HTML5 history API
    “hash history” - A DOM-specific implementation for legacy web browsers
    “memory history” - An in-memory history implementation, useful in testing and non-DOM environments like React Native

history objects typically have the following properties and methods:

    length - (number) The number of entries in the history stack
    action - (string) The current action (PUSH, REPLACE, or POP)
    location - (object) The current location. May have the following properties:
        pathname - (string) The path of the URL
        search - (string) The URL query string
        hash - (string) The URL hash fragment
        state - (object) location-specific state that was provided to e.g. push(path, state) when this location was pushed onto the stack. Only available in browser and memory history.
    push(path, [state]) - (function) Pushes a new entry onto the history stack
    replace(path, [state]) - (function) Replaces the current entry on the history stack
    go(n) - (function) Moves the pointer in the history stack by n entries
    goBack() - (function) Equivalent to go(-1)
    goForward() - (function) Equivalent to go(1)
    block(prompt) - (function) Prevents navigation (see the history docs)



### Using `Regular Expressions` for `dynamic routing`

The `path` property of the `<Route>` component can accept regular expressions for dynamic routing. 

For this tutroial we will not be diving deep into Regular Expressions or regex. However, if you are curious and want to learn more [https://regexone.com/](https://regexone.com/) provides a great tutorial on this subject. 

For example lets say we have an array of items that are sold on our website, users may want to order these items by price, color etc. 

We can assign dynamic routes for each of these in a single line and render components accordingly. 

In our application we might want to order the products within the `/products` route by both ascending and descending price. 

An easy way to do this might be a `/products/asc` route and a `/products/desc` route. This is fine for 2 different routes but often we must have many more routes which makes our code needlessly complicated. 

Instead we can modify the existing `/products` route with a Regular Expression.

```jsx
<Route path = "/products/:orderBy(asc|desc)" component = {AllProducts} />
```
We also have to modify the `AllProducts` component to account for this change. 

```jsx
const AllProducts = (props) =>{
    let arr = [...props.productArr];
    if(props.match.params.orderBy == "asc"){
        arr.sort((a, b) => a.price - b.price);
    }
    else if(props.match.params.orderBy == "desc"){
        arr.sort((a, b) => b.price - a.price);
    }
    return (
        <React.Fragment>
            <h2> Products </h2>
            {props.match.params.orderBy == "asc" ?
                <Link to = "desc"> Order By Descending Price</Link>:
                <Link to = "asc"> Order By Ascending Price</Link>
            }
            <div style = {{border : "1px solid black"}}>
                {arr.map(element =>{
                    return (
                        <div key = {element.id} style = {{border : "1px solid black"}}>
                            <p> Name : {element.name} </p>
                            <p> Price : {element.price} </p>
                            <Link to = {`product/${element.id}`}>Click to see product </Link>
                        </div>
                    );
                })}
            </div>
        </React.Fragment>
    );
}
```

Now users can easily order by price, either ascending or descending. The default value is left as ascending. 

 
 [CodeSandbox Example](https://codesandbox.io/s/redirect-dynamic-d1qin)


## Deploying a React App to `Netlify`

After making our apps look amazing we want to show it off to the world!

Lets host our React App using Netlify. 

Follow these steps:

1. First go to [https://www.netlify.com/](https://www.netlify.com/) and create an account using Github. 
2. Next go to your React App folder in the command line and run the command `npm run build`. This will do all the work necessary to have your app ready for deployment. 
3. Install the netlify CLI using `npm install netlify-cli -g`.
4. Now type `netlify deploy` and visit the link it provides to verify your account. 
5. Once you are done verifying, it should give you some options, select `+  Create & configure a new site `.
6. Select a team, this would usually be the same as your Netlify-ID.
7. Then give your website some unique name. 
8. In the deploy path option type `build`. 
9. Your draft should be live on the `Live Draft URL:`. Visit the lin kand make sure your application is working correctly.
10. If you application is working, type `netlify deploy --prod` to deploy the application. The deploy path should be `build`.
11. Visit the live URL to see your website live on the Internet for anyone to visit.

Alternatively you can run `npm build` and deploy the optimised build folder to your domain

other docs that you should visit in Routing:

[location](https://reacttraining.com/react-router/web/api/location)
[match](https://reacttraining.com/react-router/web/api/match)

But do go through all eventually