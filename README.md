# React useEffect Dependency Array Issue

This example demonstrates a common error in React's `useEffect` hook where the dependency array is not correctly specified, leading to unexpected behavior.

## The Bug

The `useEffect` hook is intended to perform side effects based on changes in specified dependencies.  In this case, the effect should only run when `count` changes and is greater than 0. However, due to incorrect dependency handling, the effect runs on the initial render even when `count` is 0.

## The Solution

The problem is the condition `if (count > 0)` inside the `useEffect` callback.  This condition alone is not enough to prevent the effect from executing on the first render when count is 0. The solution is to check the count value within the useEffect callback and return early if the condition is not met.  Alternatively, you can refactor the logic within the useEffect hook to explicitly check if the count is greater than 0 before performing the side effect.