# Week 6 - Day 1

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK6-DAY2-green)

<img src="https://cdn.pixabay.com/photo/2015/04/23/17/41/javascript-736400_960_720.png" width="100" height="100" /> 


## JavaScript Error Handling and Asychronous functions:

Flaws in computer programs are usually called `bugs`.
The process of finding mistakes—bugs—in programs is called `debugging`.

`Exception/Error handling` is the process of responding to the occurrence, during computation, of exceptions – anomalous or exceptional conditions requiring special processing – often changing the normal flow of program execution.

Writing programs that work when everything goes as expected is a good start. Making your programs behave properly when encountering unexpected conditions is where it really gets challenging.

The problematic situations that a program can encounter fall into two categories: `Programmer mistakes` and `genuine problems`. If someone forgets to pass a required argument to a function, that is an example of the first kind of problem. On the other hand, if a program asks the user to enter a name and it gets back an empty string, that is something the programmer can not prevent.

In general, one deals with programmer errors by finding and fixing them, and with genuine errors by having the code check for them and perform some suitable action to remedy them (for example, asking for the name again), or at least fail in a well-defined and clean way.

## `try catch throw and finally`:

Handling Exceptions

The statements `try`, `catch` and `finally` can be used to handle selected exceptions. A try statement may have more than one catch clause to specify handlers for different exceptions.

    The try statement allows you to define a block of code to be tested for errors while it is being executed.

    The catch statement allows you to handle the error.

    The finally statement allows you to execute code after the try and catch statements, regardless of the result.

The `try` statement consists of a `try` block, which contains one or more statements. {} must always be used, even for single statements. At least one `catch` clause, or a `finally` clause, must be present.

try catch handles only runtime errors. 

EXAMPLE
```javascript
var a = 1;
//var p = 2;

try {
    a = 1/p;
    console.log(`New value of 'a' is ${a}`);
} catch (err) {
    console.log(err.message);
} finally {
    console.log(`Final value of 'a' is ${a}`)
}
```
OUTPUT
```
p is not defined
Final value of 'a' is 1
```

[Codepen Example](https://codepen.io/albseb511/pen/JjPLdXy)

[try...catch MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch)


**[`Error Types`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)**

- The [`EvalError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError) object indicates an error regarding the global eval() function.

- An [`InternalError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError) is thrown whenever an internal error in the JavaScript engine occurred.

    Example cases are mostly when something is too large, e.g.:

        "too many switch cases",
        "too many parentheses in regular expression",
        "array initializer too large",
        "too much recursion".

- A [`RangeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError) is thrown when trying to pass a value as an argument to a function that does not allow a range that includes the value.

- A [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError) is thrown when trying to dereference a variable that has not been declared.

- A [`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError) is thrown when the JavaScript engine encounters tokens or token order that does not conform to the syntax of the language when parsing code.

- A [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) is thrown when an operand or argument passed to a function is incompatible with the type expected by that operator or function.

- A [`URIError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/URIError) is thrown when the global URI handling functions are passed a malformed URI.


## Error Handling tips:

1. Assume your code will fail
2. Log errors to the server
3. You handle the errors, not the browser
4. Identify where errors might occur - Types of errors (type coersion, data type, communication and network, invalid urls)
5. Distinguish between fatal and non fatal errors
6. Debug or verbose mode

[More Reading](https://www.joyent.com/node-js/production/design/errors)

## `strict mode`

By using strict mode, 

Toss this at the top of a program to enable it for the whole script:
```javascript
"use strict";
x = 3.14;  

```

Or place it within a function to turn on strict mode only within that context.
```javascript
// Non-strict code...

function(){
      "use strict";

      // Define your library strictly...
    };

    // Non-strict code... 

```
strict is supported by almost all [Browsers](https://caniuse.com/#feat=use-strict)

Strict mode helps out in a couple ways:

- It catches some common coding bloopers, throwing exceptions.
- It prevents, or throws errors, when relatively "unsafe" actions are taken (such as gaining access to the global object).
- It disables features that are confusing or poorly thought out.
- Eliminates some JavaScript silent errors by changing them to throw errors.
- Fixes mistakes that make it difficult for JavaScript engines to perform optimizations: strict mode code can sometimes be made to run      faster than identical code that's not strict mode.
- Prohibits some syntax likely to be defined in future versions of ECMAScript.


[Codepen Example](https://codepen.io/albseb511/pen/jONzPmP?)

[strict - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)

## `SetTimeout`

The setTimeout() method calls a function or evaluates an expression after a specified number of milliseconds.

1000 ms = 1 second.
The function is only executed once.
Use the clearTimeout() method to prevent the function from running.

[Codepen Example](https://codepen.io/albseb511/pen/XWrEMMv)

## `SetInterval`

The setInterval() method calls a function or evaluates an expression at specified intervals (in milliseconds).

The setInterval() method will continue calling the function until clearInterval() is called, or the window is closed.

The ID value returned by setInterval() is used as the parameter for the clearInterval() method.

[Codepen Example](https://codepen.io/albseb511/pen/vYBRxWZ)
