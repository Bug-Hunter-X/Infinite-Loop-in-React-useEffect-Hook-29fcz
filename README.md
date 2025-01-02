# React useEffect Infinite Loop Bug
This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The issue arises from an incorrectly defined dependency array, leading to an infinite rendering loop.

## Bug Description
The `MyComponent` function uses `useEffect` to log the current `count` value to the console.  However, the dependency array `[count]` is incorrectly defined, causing the effect to re-run every time the `count` changes. Since clicking the button updates `count`, this creates an infinite loop of renders and updates.

## Solution
The solution is to optimize the dependency array to include only the relevant values that should trigger the effect. In this case, no dependencies are needed, as the effect's only purpose is to log a message after every render.  An empty array indicates the effect runs only once after the initial render. If the effect requires the count, it needs to be optimized to only trigger on specific changes. 