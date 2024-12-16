# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript closure issue related to the use of `setTimeout` within a loop.  The issue arises because the variable `i` is not captured correctly for each iteration of the loop, resulting in unexpected behavior.

## Bug Description
The code uses `setTimeout` to log the value of `i` after a delay. However, due to the closure behavior, by the time `setTimeout` executes, the loop has already completed, and `i` will hold its final value (10).  Therefore, instead of printing 0 through 9, it prints 10 ten times.

## Solution
The solution utilizes an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, ensuring that each timeout captures its own value of `i`.