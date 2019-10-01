# Week 9 Day 2

![](https://img.shields.io/badge/MASAI-SPARTANS-red?logo=&style=for-the-badge)

![](https://img.shields.io/badge/WEEK9-DAY2-green)

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1280px-React-icon.svg.png" height="100" /> 
<img src="https://redux.js.org/img/redux.svg" width="100" height="100" /> 

## `Scaling complexity`

Over the last few weeks you have started to build larger applications, and you have started to work on state management. The complexity of building these apps will increase as the apps become bigger. 

Larger the app gets, the complexity of state and props have increased. Some bugs like:

        Forgetting to pass a prop 
        Managing deeply nested states
        Duplication of state objects
        Not Updating all dependant props
        Components with large no of props
        Understanding where the data is going


## Facebook and `MVC`
<img src="https://www.tutorialsleader.com/Images/c-sharp-tutorials/asp-net-mvc-architecture.png" width="200" height="200" /> 


- The MVC architecture became too complex for facebook
- The complexity manifested into bugs
- Facebook rearchitectured into one-way data flow

Watch this video:
The birth of `React`

[Rethinking Web App Development at Facebook](https://www.youtube.com/watch?v=nYkdrAPrdcw&feature=youtu.be&t=10m22s)


## `Flux`

An application architecture for React utilising a unidirectional data flow.
    Views react to changes in stores
    Stores can only get updated through dipatchers
    Dispatchers can only be triggerred by actions
    Actions can only get triggered by Views

Flux is the application architecture that Facebook uses for building client-side web applications. It complements React's composable view components by utilizing a unidirectional data flow. It's more of a pattern rather than a formal framework, and you can start using Flux immediately without a lot of new code.

Flux applications have three major parts: the dispatcher, the stores, and the views (React components). These should not be confused with Model-View-Controller. Controllers do exist in a Flux application, but they are controller-views — views often found at the top of the hierarchy that retrieve data from the stores and pass this data down to their children. Additionally, action creators — dispatcher helper methods — are used to support a semantic API that describes all changes that are possible in the application. It can be useful to think of them as a fourth part of the Flux update cycle.

### `Structure and Data Flow`

![](https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-1300w.png)

Data in a Flux application flows in a single direction:

A unidirectional data flow is central to the Flux pattern, and the above diagram should be the primary mental model for the Flux programmer. The dispatcher, stores and views are independent nodes with distinct inputs and outputs. The actions are simple objects containing the new data and an identifying type property.

The views may cause a new action to be propagated through the system in response to user interactions:

![](https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-with-client-action-1300w.png)

All data flows through the dispatcher as a central hub. Actions are provided to the dispatcher in an action creator method, and most often originate from user interactions with the views. The dispatcher then invokes the callbacks that the stores have registered with it, dispatching actions to all stores. Within their registered callbacks, stores respond to whichever actions are relevant to the state they maintain. The stores then emit a change event to alert the controller-views that a change to the data layer has occurred. Controller-views listen for these events and retrieve data from the stores in an event handler. The controller-views call their own setState() method, causing a re-rendering of themselves and all of their descendants in the component tree.

![](https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-explained-1300w.png)

This structure allows us to reason easily about our application in a way that is reminiscent of functional reactive programming, or more specifically data-flow programming or flow-based programming, where data flows through the application in a single direction — there are no two-way bindings. Application state is maintained only in the stores, allowing the different parts of the application to remain highly decoupled. Where dependencies do occur between stores, they are kept in a strict hierarchy, with synchronous updates managed by the dispatcher.

We found that two-way data bindings led to cascading updates, where changing one object led to another object changing, which could also trigger more updates. As applications grew, these cascading updates made it very difficult to predict what would change as the result of one user interaction. When updates can only change data within a single round, the system as a whole becomes more predictable.


## `Dispatcher`

The dispatcher is the central hub that manages all data flow in a Flux application. It is essentially a registry of callbacks into the stores and has no real intelligence of its own — it is a simple mechanism for distributing the actions to the stores. Each store registers itself and provides a callback. When an action creator provides the dispatcher with a new action, all stores in the application receive the action via the callbacks in the registry.

As an application grows, the dispatcher becomes more vital, as it can be used to manage dependencies between the stores by invoking the registered callbacks in a specific order. Stores can declaratively wait for other stores to finish updating, and then update themselves accordingly.

The same dispatcher that Facebook uses in production is available through npm, Bower, or GitHub.

## `Stores`

Stores contain the application state and logic. Their role is somewhat similar to a model in a traditional MVC, but they manage the state of many objects — they do not represent a single record of data like ORM models do. Nor are they the same as Backbone's collections. More than simply managing a collection of ORM-style objects, stores manage the application state for a particular domain within the application.

For example, Facebook's Lookback Video Editor utilized a TimeStore that kept track of the playback time position and the playback state. On the other hand, the same application's ImageStore kept track of a collection of images. The TodoStore in our TodoMVC example is similar in that it manages a collection of to-do items. A store exhibits characteristics of both a collection of models and a singleton model of a logical domain.

As mentioned above, a store registers itself with the dispatcher and provides it with a callback. This callback receives the action as a parameter. Within the store's registered callback, a switch statement based on the action's type is used to interpret the action and to provide the proper hooks into the store's internal methods. This allows an action to result in an update to the state of the store, via the dispatcher. After the stores are updated, they broadcast an event declaring that their state has changed, so the views may query the new state and update themselves.

## `Views` and Controller-Views

React provides the kind of composable and freely re-renderable views we need for the view layer. Close to the top of the nested view hierarchy, a special kind of view listens for events that are broadcast by the stores that it depends on. We call this a controller-view, as it provides the glue code to get the data from the stores and to pass this data down the chain of its descendants. We might have one of these controller-views governing any significant section of the page.

When it receives the event from the store, it first requests the new data it needs via the stores' public getter methods. It then calls its own setState() or forceUpdate() methods, causing its render() method and the render() method of all its descendants to run.

We often pass the entire state of the store down the chain of views in a single object, allowing different descendants to use what they need. In addition to keeping the controller-like behavior at the top of the hierarchy, and thus keeping our descendant views as functionally pure as possible, passing down the entire state of the store in a single object also has the effect of reducing the number of props we need to manage.

Occasionally we may need to add additional controller-views deeper in the hierarchy to keep components simple. This might help us to better encapsulate a section of the hierarchy related to a specific data domain. Be aware, however, that controller-views deeper in the hierarchy can violate the singular flow of data by introducing a new, potentially conflicting entry point for the data flow. In making the decision of whether to add a deep controller-view, balance the gain of simpler components against the complexity of multiple data updates flowing into the hierarchy at different points. These multiple data updates can lead to odd effects, with React's render method getting invoked repeatedly by updates from different controller-views, potentially increasing the difficulty of debugging.

## `Actions`

The dispatcher exposes a method that allows us to trigger a dispatch to the stores, and to include a payload of data, which we call an action. The action's creation may be wrapped into a semantic helper method which sends the action to the dispatcher. For example, we may want to change the text of a to-do item in a to-do list application. We would create an action with a function signature like updateText(todoId, newText) in our TodoActions module. This method may be invoked from within our views' event handlers, so we can call it in response to a user interaction. This action creator method also adds a type to the action, so that when the action is interpreted in the store, it can respond appropriately. In our example, this type might be named something like TODO_UPDATE_TEXT.

Actions may also come from other places, such as the server. This happens, for example, during data initialization. It may also happen when the server returns an error code or when the server has updates to provide to the application.

[Documentation](https://facebook.github.io/flux/docs/in-depth-overview)


## [Redux](https://redux.js.org/) - Alternative State Management

As Flux is not a framework per se, developers have tried to come up with many implementations of the Flux pattern. Eventually, a clear winner emerged, which was Redux. Redux combines the ideas from Flux, Command pattern and Elm architecture and is the de facto state management library developers use with React these days. Its core concepts are:

    App state is described by a single plain old JavaScript object (POJO).
    Dispatch an action (also a POJO) to modify the state.
    Reducer is a pure function that takes in current state and action to produce a new state.

The concepts sound simple, but they are really powerful as they enable apps to:

    Have their state rendered on the server, booted up on the client.
    Trace, log and backtrack changes in the whole app.
    Implement undo/redo functionality easily.


## `Redux`

### What is redux?

Redux is a predictable state container for any JavaScript application. For our purpose we are going to use Redux to manage a React Application.

However, Redux has nothing to do with React JS, you can write applications that use Redux in plain JavaScript and direct DOM updates. Redux can also be used with any Front End or Backend framework like AngularJS, EmberJS, VueJS etc.

## The three core principles of Redux

**Single Source of Truth:**

The store in redux is known as the single source of truth. This is because there is only one store in redux and it holds all the application state. Any state that need to be read in redux can only be done from the store.

**State is READ only**

You cannot modify state directly in Redux like you do within a React application using `setState()`.

According to the Redux Docs, "The only way to change the state is to emit an action, an object describing what happened."

Only modify state in Redux using actions and reducers!

**Changes in Redux are made with pure functions:**

Pure functions are functions that **do not** modify their arguments. Instead they create copies of the arguments and modify and change those copies to be returned later. 

Moreover for any given input, pure functions will always return the same value.


```
Action -> Reducer -> Update Store
```

`pure function` - 
Pure functions take an input value (a parameter or argument) and depending on that input, produce an output value, that's all. They do one thing only, but they do it well. It should be that whenever you give a pure function the same input it will return the same output every single time.


![](https://raw.githubusercontent.com/masai-school/full-stack-dev/master/course/week_10/day_1/redux_basic.gif)


[Cartoon guide to Flux](https://code-cartoons.com/a-cartoon-guide-to-flux-6157355ab207)
[Cartoon guide to Redux](https://code-cartoons.com/a-cartoon-intro-to-redux-3afb775501a6)