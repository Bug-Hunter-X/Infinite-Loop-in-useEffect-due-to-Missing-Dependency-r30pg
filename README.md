# React useEffect Infinite Loop Bug
This repository demonstrates a common React bug caused by an incorrectly used `useEffect` hook. The bug leads to an infinite rendering loop because the dependency array is missing a crucial dependency, causing the effect to run on every render.

## Bug Description
The `useEffect` hook is used to perform side effects after every render. However, if a value used within the effect is not included in the dependency array, React will rerun the effect on every render, even if that value hasn't changed. In this example, the missing dependency is the `count` state variable.  The log statement will run on every render causing the loop and a performance bottleneck.

## Bug Solution
The solution involves adding the `count` state variable to the dependency array. This ensures that the effect only runs when the `count` value changes.

## How to reproduce the bug
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs and see that they repeat endlessly.