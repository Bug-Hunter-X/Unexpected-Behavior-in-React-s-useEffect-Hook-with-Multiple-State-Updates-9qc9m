# Unexpected React useEffect Behavior
This repository demonstrates an uncommon bug related to React's `useEffect` hook and multiple state updates within a single function call.  The issue arises when attempting to update state multiple times in quick succession inside an event handler, leading to an unexpected outcome where one or more updates appear to be ignored.  The solution highlights how to ensure all state updates are processed correctly.

## Bug Description
The `bug.js` file contains a React component that increments a counter using the `useState` and `useEffect` hooks.  Despite two calls to `setCount`, the counter sometimes only increments by one instead of the expected two due to the asynchronous nature of state updates in React.  This is because React batches state updates, leading to only the final update being processed. 

## Solution
The `bugSolution.js` file provides a corrected implementation using functional updates (`prevCount => prevCount + 1`). This ensures that each state update is based on the previous state, resolving the unexpected behavior.
