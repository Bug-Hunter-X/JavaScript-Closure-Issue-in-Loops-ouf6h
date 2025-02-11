# JavaScript Closure Issue in Loops

This repository demonstrates a common JavaScript error related to closures within loops using `setTimeout`. The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version.

## Bug Description

The issue arises because the `setTimeout` callback functions don't capture the value of `i` at the time they're created. Instead, they capture the reference to `i`, which is updated in each iteration of the loop.  By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` holds its final value (10).  Therefore, all callbacks log 10.

## Solution

The solution involves using an Immediately Invoked Function Expression (IIFE) to create a new scope for each iteration. This ensures that each callback captures its own unique copy of `i`. The corrected code is available in `bugSolution.js`.