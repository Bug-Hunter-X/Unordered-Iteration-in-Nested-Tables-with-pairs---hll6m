# Lua Nested Table Iteration Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when dealing with deeply nested tables. The `pairs` function doesn't guarantee a specific iteration order, which can lead to unexpected behavior if you modify the table during iteration.

## The Bug
The `bug.lua` file contains a function that recursively iterates over a nested table. However, because `pairs` doesn't provide a consistent order, elements in nested tables might be missed.

## The Solution
The `bugSolution.lua` file provides a corrected version.  It uses a different approach, such as a depth-first traversal or iterative solution to guarantee a consistent and complete iteration, even when modifying the table during the process.

## How to Reproduce
1. Clone this repository.
2. Run `lua bug.lua`.
3. Observe the output (it will not always print all nested values in the same order).
4. Run `lua bugSolution.lua`.
5. Compare the outputs; the solution ensures complete iteration.