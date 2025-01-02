# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to clear the interval when the component unmounts. This can lead to memory leaks and unexpected behavior.

## Problem

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it fails to clear the interval when the component is unmounted, resulting in the interval continuing to run even after the component is no longer in the DOM.  This causes a memory leak, as the interval keeps referencing the component's state.

## Solution

The `bugSolution.js` file provides a corrected version.  It stores the interval ID in a variable and uses the cleanup function in `useEffect` to clear the interval using `clearInterval` before the component unmounts.