# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common error in React involving the use of `setInterval` within the `useEffect` hook without proper cleanup, leading to memory leaks and unexpected behavior.

## Bug Description
The `MyComponent` component utilizes `setInterval` to update a counter every second. However, the cleanup function within `useEffect` is not correctly handling the interval ID. This causes the interval to persist even after the component unmounts, resulting in a memory leak.

## Solution
The solution involves ensuring proper cleanup by storing the interval ID in a `ref` and using `useRef` to avoid unnecessary re-renders of the component.