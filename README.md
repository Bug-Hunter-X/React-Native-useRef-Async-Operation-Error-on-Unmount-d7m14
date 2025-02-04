# React Native useRef Async Operation Error on Unmount

This repository demonstrates a common error in React Native when using the `useRef` hook with asynchronous operations. The error occurs when a component unmounts before an asynchronous operation within a `useEffect` hook that uses `useRef` completes.  This leads to attempts to access and update `useRef`'s `current` property after the component has been unmounted, resulting in the error `Cannot read properties of undefined (reading 'current')`.

## Problem
The provided `bug.js` shows a component making an asynchronous API call. If the component unmounts before the API call returns, attempting to update the ref will throw the error.

## Solution
The `bugSolution.js` provides a solution using the cleanup function in the `useEffect` hook to prevent the error. This function is called when the component unmounts and cancels any ongoing asynchronous operations.

## How to Run
1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install`.
4. Run `npx react-native run-android` or `npx react-native run-ios` (depending on your platform).

This example highlights a crucial consideration when handling asynchronous operations within React components.