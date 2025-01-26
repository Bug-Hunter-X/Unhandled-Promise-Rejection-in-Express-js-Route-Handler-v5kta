# Unhandled Promise Rejection in Express.js Route Handler

This repository demonstrates a common error in Express.js applications: unhandled promise rejections within route handlers.  Asynchronous operations, if not handled correctly, can lead to unexpected crashes or silent failures.

## Bug Description

The `bug.js` file contains an Express.js server with a route that performs an asynchronous operation.  This operation has a 50% chance of throwing an error. However, the route handler lacks proper error handling, causing the server to crash if the asynchronous operation fails.

## Solution

The `bugSolution.js` file shows the corrected code.  The solution includes a `.catch` block within the asynchronous operation's `.then` chain, enabling proper error handling and preventing server crashes.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node bug.js`. Observe that the server may crash after a few requests. 
4. Run `node bugSolution.js`. The server should now gracefully handle errors from the asynchronous operation.