# REACT NATIVE


#### Create native apps for Android and iOS using React

`https://facebook.github.io/react-native/`

By using React Native, you are able to build hybrid apps which can be deployed for android and iOS.

React is something you are already comfortable with, so conceptually there wouldnt be challenges on React.

Getting used to the environment 

### Getting Started

You have two options to get started:

#### Expo 
    
    If you are new to mobile development, the easiest way to get started is with Expo CLI. Expo is a set of tools built around React Native and, while it has many features, the most relevant feature for us right now is that it can get you writing a React Native app within minutes. You will only need a recent version of Node.js and a phone or emulator. If you'd like to try out React Native directly in your web browser before installing any tools, you can try out Snack.

(https://expo.io/)[https://expo.io/]

#### React Native CLI

    If you are already familiar with mobile development, you may want to use React Native CLI. It requires Xcode or Android Studio to get started. If you already have one of these tools installed, you should be able to get up and running within a few minutes. If they are not installed, you should expect to spend about an hour installing and configuring them.

You will need to follow instructions on setting up the environment. This can take a few hours to get everything right.

(https://facebook.github.io/react-native/docs/getting-started)[https://facebook.github.io/react-native/docs/getting-started]

For simplicity sake we will be using expo

You can install Expo CLI 

```
npm install -g expo-cli
```

Then run the following commands to create a new React Native project called "myApp"

```
expo init myApp

cd myApp

npm start
```

There are a few templates to choose from with expo.
- You can start with a blank slate
- expo has already setup a few templates with react-navigation with a bottom drawer and routing pre-built

![expo init](https://i.imgur.com/y1pNkJe.png)


- Install the Expo client app from your app store on your iOS or Android phone 
- Connect to the same wireless network as your computer. [Make sure this is done]
- On Android, use the Expo app to scan the QR code from your terminal to open your project. 
- On iOS, follow on-screen instructions to get a link.

#### Running your app on a simulator or virtual device

Expo CLI allows you to run your React Native app on a physical device without setting up a development environment. If you want to run your app on the iOS Simulator or an Android Virtual Device, please refer to the instructions for "React Native CLI Quickstart" to learn how to install Xcode or set up your Android development environment.

Once you've set these up, you can launch your app on an Android Virtual Device by running npm run android, or on the iOS Simulator by running npm run ios (macOS only).

#### Limitations

Because you don't build any native code when using Expo to create a project, it's not possible to include custom native modules beyond the React Native APIs and components that are available in the Expo client app.

If you know that you'll eventually need to include your own native code, Expo is still a good way to get started. In that case you'll need to "eject" eventually to create your own native builds. If you do eject, the "React Native CLI Quickstart" instructions will be required to continue working on your project.

### App.js

Lets start coding!

If you goto your App.js you will notice the import statements like this

```javascript
import React, { Component } from 'react';
import { Text, View } from 'react-native';
```

Wait, isnt that `react` module that we were using for building web applications?s

Well, yes.

So You would have notice that we imported `react-dom` for our web applications.

The React team did a great job of seperating the core React code such that it was possible to render the UI in any environment.
- For web we can use `react-dom`
- For native apps, we can use `react-native`

This is a simple hello world app

```javascript
import React, { Component } from 'react';
import { Text, View } from 'react-native';

export default class HelloWorldApp extends Component {
  render() {
    return (
      <View style={{ flex: 1, justifyContent: "center", alignItems: "center" }}>
        <Text>Hello, world!</Text>
      </View>
    );
  }
}
```

- Now everything seems familiar except the Components. 
- Well since you do not have a browser, we cannot use html elements.
- Hence we have to use Components which are available in the framework.
- This is similar to to using any UI framework on React.js like Material UI

You can have a look at the API docs in react native

(https://facebook.github.io/react-native/docs/text)[https://facebook.github.io/react-native/docs/text]

- All your text has to be wrapped around the Text component

(https://facebook.github.io/react-native/docs/view)[https://facebook.github.io/react-native/docs/view]

- The most fundamental component for building a UI, View is a container
- View is designed to be nested inside other views and can have 0 to many children of any type.
- View is like a div

Lets look at a button

(https://facebook.github.io/react-native/docs/button)[https://facebook.github.io/react-native/docs/button]

There are a few differences when building web applications

You would have used the event `onClick` to trigger an event on the web.

When building apps for your mobile, we have to use the event `onPress`

If this button doesn't look right for your app, you can build your own button using the components
- `TouchableOpacity` 
- `TouchableNativeFeedback`

Lets get to styling,

We can use JavaScript objects to handle styling for your components.

We can do inline styling or use the StyleSheet API as well

```javascript
const App = ()=>(
    <Text style={{color:'red', fontSize:24}}>
        All interaction for the component are disabled.
    </Text>
    )

    // Or with StyleSheet - recommended
const styles = StyleSheet.create({
  title: {
    textAlign: 'center',
    marginVertical: 8,
  }
});

const App = ()=>(
    <Text style={styles.title}>
        All interaction for the component are disabled.
    </Text>
    )

```

- Other things you will notice is that your app renders onto your notification / status bar.
- We can use StatusBar component and use currentHeight from it