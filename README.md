# React useEffect without dependencies causing unnecessary re-renders

This repository demonstrates a common React performance issue caused by using the `useEffect` hook without specifying dependencies.  The `useEffect` hook, without dependencies, runs after every render, leading to unnecessary calculations and potential performance problems.

## Problem
The provided `MyComponent` uses `useEffect` to log the current count after every render.  This is inefficient because the log occurs even when the count hasn't changed.

## Solution
To fix this, specify an empty dependency array (`[]`) to ensure the `useEffect` runs only once after the initial render:

```javascript
useEffect(() => {
    console.log('Component mounted:', count);
}, []);
```
This approach optimizes performance by preventing unnecessary re-renders and makes the code more predictable.