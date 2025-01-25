# React Native AsyncStorage Synchronous Access Bug

This repository demonstrates a common error in React Native applications involving asynchronous storage (AsyncStorage). The bug arises from attempting to synchronously access data stored asynchronously using AsyncStorage.getItem().

## Bug Description
The provided `bug.js` demonstrates the problem: it attempts to retrieve a value from AsyncStorage using `getItem` without awaiting the promise it returns. This causes the value to be `undefined` if `getItem` completes after the line that displays the value.  AsyncStorage is inherently asynchronous; it requires asynchronous methods to interact correctly.

## Solution
The `bugSolution.js` shows how to resolve this. We use `await` to properly wait for the asynchronous `getItem` call to complete before attempting to access the returned value.

## How to reproduce
1. Clone this repository.
2. Navigate to the project directory in your terminal.
3. Run `npx react-native run-android` or `npx react-native run-ios` to run the app.
4. Observe the error when running the app in its original state.
5. Change the code to use the solution to see the value properly printed.
