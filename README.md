# React useEffect setInterval Memory Leak

This repository demonstrates a common React bug: a memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The example component uses `setInterval` to update a counter every second. However, it lacks a cleanup function to clear the interval when the component unmounts, leading to a memory leak.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides the corrected code with a cleanup function to prevent the memory leak.

## Bug Description
The `setInterval` function continues to execute even after the component is unmounted, resulting in a memory leak.  This is because the `useEffect` hook's cleanup function is not used to stop the interval.

## Solution
The solution involves adding a return statement to the `useEffect` callback to clear the interval using `clearInterval` before the component unmounts.