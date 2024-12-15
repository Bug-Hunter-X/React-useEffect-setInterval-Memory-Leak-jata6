# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React `useEffect` hook: creating memory leaks due to improper closure management.

The `bug.js` file contains the problematic code.  The `bugSolution.js` shows the corrected implementation.

## Problem
The original code creates a new closure for `setInterval`'s callback function on each render. This results in multiple `setInterval` instances running concurrently, preventing proper cleanup and leading to memory leaks.

## Solution
The solution involves using a useRef hook to store the interval ID, ensuring the correct interval is cleared when the component unmounts or changes.