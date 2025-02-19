# React Router v6 Catch-all Route Bug

This repository demonstrates a subtle bug in React Router v6 related to the catch-all route ("/*") when used in conjunction with nested routes. The catch-all route unexpectedly intercepts routes that should be matched before it.

## Bug Description

The issue arises when a catch-all route (`path="/*"`) is placed after more specific routes.  Even if a route matches, the catch-all route takes precedence, resulting in unexpected rendering.  This behavior is especially troublesome when working with nested routes.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that navigating to any route, including those defined before the catch-all route, always shows the 404 Not Found component.

## Solution

The solution involves carefully ordering routes, placing more specific routes *after* the catch-all route, and using the `useLocation` hook for more advanced scenarios.  See `bugSolution.js` for a working example.