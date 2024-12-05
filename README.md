# React useEffect Cleanup Function Memory Leak

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include a return statement in the cleanup function. This can lead to memory leaks and unexpected behavior.

## Bug
The `bug.js` file contains a `useEffect` hook that fetches data from an API. However, it's missing a `return` statement in the effect function that would clean up the fetch operation if the component unmounts before the fetch completes. This can lead to memory leaks if the component is unmounted before the API call completes.

## Solution
The `bugSolution.js` file demonstrates the correct way to use a cleanup function in `useEffect`.  The `return` statement inside the `useEffect` function returns a cleanup function, which is called by React before the component is unmounted.  This ensures that any ongoing API calls or other side effects are properly cleaned up.

## How to reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs and inspect the component's behavior.