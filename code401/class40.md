# React native 

### Create native apps for Android and iOS using React
* React Native combines the best parts of native development with React, a best-in-class JavaScript library for building user interfaces.

* Use a little—or a lot. You can use React Native today in your existing Android and iOS projects or you can create a whole new app from scratch.

### Written in JavaScript—rendered with native code
* React primitives render to native platform UI, meaning your app uses the same native platform APIs other apps do.

* Many platforms, one React. Create platform-specific versions of components so a single codebase can share code across platforms. With React Native, one team can maintain two platforms and share a common technology—React.

### Native Development For Everyone
* React Native lets you create truly native apps and doesn't compromise your users' experiences. It provides a core set of platform agnostic native components like View, Text, and Image that map directly to the platform’s native UI building blocks.

### Seamless Cross-Platform
* React components wrap existing native code and interact with native APIs via React’s declarative UI paradigm and JavaScript. This enables native app development for whole new teams of developers, and can let existing native teams work much faster.

### Fast Refresh
* See your changes as soon as you save. With the power of JavaScript, React Native lets you iterate at lightning speed. No more waiting for native builds to finish. Save, see, repeat.


### Setting up the development environment

* If you are new to mobile development, the easiest way to get started is with Expo Go. Expo is a set of tools and services built around React Native and, while it has many features, the most relevant feature for us right now is that it can get you writing a React Native app within minutes. You will only need a recent version of Node.js and a phone or emulator. If you'd like to try out React Native directly in your web browser before installing any tools, you can try out Snack.

* If you are already familiar with mobile development, you may want to use React Native CLI. It requires Xcode or Android Studio to get started. If you already have one of these tools installed, you should be able to get up and running within a few minutes. If they are not installed, you should expect to spend about an hour installing and configuring them.

```
npx create-expo-app appName

cd AwesomeProject
npm start

```
```import React from 'react';
import { Text, View } from 'react-native';

const YourApp = () => {
  return (
    <View style={{ flex: 1, justifyContent: "center", alignItems: "center" }}>
      <Text>
        Try editing me! 🎉
      </Text>
    </View>
  );
}

export default YourApp;

```

## Expo
```
npm install --global expo-cli
expo init my-project
cd my-project
npm start
```
This will open up the Expo app runner, which allows you to run your app on a real device, or a simulator (see notes below)

Installing Tools
Mac Users - Install XCode so you can use the iOS Simulators

All Users - Install Android Studio so that you can run an Android phone simulator

Android Studio
Once installed, apply all updates and then open the AVD Manager, from the "Tools" menu.

Choose a device and the latest version of the Android OS, and then install the update (it may take > 30 minutes).

Once done, you can then re-open the AVD Manager and start an Android Virtual Device from which you can test