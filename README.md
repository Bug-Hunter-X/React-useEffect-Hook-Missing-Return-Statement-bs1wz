# React useEffect Hook Missing Return Statement

This example demonstrates a common mistake when using the `useEffect` hook in React: omitting the return statement for cleanup functions.

## Problem

The `useEffect` hook in the provided `MyComponent` is missing a return statement.  This can lead to memory leaks if the component unmounts, especially if the effect performs actions like setting event listeners or intervals. Without a return statement, the cleanup function won't execute to remove these listeners and stop intervals.

## Solution

The solution includes adding a return statement to the `useEffect` hook that cleans up any side effects. In this case, we don't have any side effects, but if the effect function was doing something like setting an event listener, this function would return a cleanup function to remove that event listener when the component is unmounted.