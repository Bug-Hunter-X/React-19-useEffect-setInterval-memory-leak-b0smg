# React 19 useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React 19.  Forgetting to return a cleanup function from `useEffect` leads to a memory leak because the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file contains the erroneous code.  The `setInterval` function is started in the `useEffect` hook, but there's no way to stop it when the component is unmounted, resulting in a memory leak.

## Solution
The `bugSolution.js` file provides the correct implementation. A cleanup function is returned from `useEffect`, which uses `clearInterval` to stop the interval before the component unmounts. This prevents the memory leak.