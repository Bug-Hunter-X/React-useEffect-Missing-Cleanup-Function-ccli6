# React useEffect Missing Cleanup Function

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a cleanup function when making asynchronous calls or subscriptions.

## The Problem

The `bug.js` file contains a `useEffect` hook that fetches data from an API.  However, it's missing a return function. This means that if the component unmounts before the fetch completes, the promise might still resolve, causing `setCount` to update even after the component is no longer mounted, leading to unexpected behavior or memory leaks.

## The Solution

The `bugSolution.js` file shows the correct implementation. A cleanup function is returned, ensuring that any pending operations are canceled when the component is unmounted, preventing potential issues. 