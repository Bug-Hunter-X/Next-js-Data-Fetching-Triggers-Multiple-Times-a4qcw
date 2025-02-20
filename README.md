# Next.js Data Fetching Triggers Multiple Times

This repository demonstrates a common issue in Next.js where data fetching triggers multiple times when navigating between pages or refreshing, leading to performance issues. The issue is often exacerbated by the use of `useEffect` hooks without proper dependency management, potentially causing redundant API calls and slower loading times. This example showcases the problem and provides a solution.

## Problem

The provided example uses a custom component which contains `useEffect`.  When used within a page, this can cause unintended re-renders and multiple calls to the API due to how Next.js handles page transitions and client-side rendering. The goal is to fix this behavior without changing the overall functionality of the application. 

## Solution

The solution demonstrates how to prevent multiple data fetches by properly managing the dependencies in the `useEffect` hook. By adding the correct dependencies to the `useEffect` hook, you can ensure that the data is only fetched once per page load or transition. 

## How to reproduce the bug

1.  Clone this repository.
2.  Run `npm install`.
3.  Run `npm run dev`.
4.  Observe the console logs. You will see "MyComponent mounted" and "MyComponent unmounted" multiple times when navigating or refreshing. 

## How to see the solution

1.  Switch to the `bugSolution.js` file.
2. Run `npm run dev`.
3. Observe the console logs.  You will see "MyComponent mounted" and "MyComponent unmounted" only once when navigating or refreshing. 