# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code. The `serverSolution.js` file shows the solution using asynchronous operations.

## Bug Description

The server hangs because the `while` loop in the request handler blocks the event loop.  This prevents the server from accepting and processing new requests while the loop runs.  This is a classic example of how synchronous code can bring down a Node.js server.

## Solution

The solution involves using asynchronous operations to avoid blocking the event loop. Asynchronous techniques are crucial for Node.js's non-blocking I/O model.  The corrected code is in `serverSolution.js`.