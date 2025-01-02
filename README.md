# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications where the `useEffect` hook causes an infinite loop due to improper dependency management.

## Bug Description

The `useEffect` hook is designed to perform side effects after a component renders. However, if the effect's dependency array is missing or incorrectly specified, the effect can run repeatedly, leading to performance issues or even an infinite loop.

In this example, the `useEffect` hook inside `MyComponent` runs on every render because its dependency array is empty (`[]`). This means that even a simple click that updates the `count` state will trigger the effect again, creating an infinite loop of console logs and re-renders.

## Solution

The solution is to correctly specify the dependencies in the `useEffect` hook's dependency array. In this case, we only want the effect to run when the `count` state changes, so the dependency array should include `count`.

## How to reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the infinite console logs and the continuously incrementing count in the browser.  The browser may even freeze or crash.

## How to fix

1. Open `bugSolution.js` to see the corrected code.
2. Run `npm start` again. You should see that the console logs now only appear when the count is updated and the infinite loop is gone.