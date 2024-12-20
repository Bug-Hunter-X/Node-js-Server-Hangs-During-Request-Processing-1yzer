# Node.js Server Hang Issue

This repository demonstrates a common Node.js issue where a server hangs during request processing due to a long-running synchronous operation.  The server simulates a 5-second delay before responding, which can negatively impact performance and responsiveness.

## Problem

The `server.js` file contains a simple HTTP server that performs a synchronous wait for 5 seconds within the request handler. This blocks the event loop, preventing other requests from being processed.  This leads to significant performance degradation under load, as each request will hold up the whole system for 5 seconds.

## Solution

The `serverSolution.js` file demonstrates a solution using asynchronous operations and promises to prevent blocking the event loop.  This allows the server to handle multiple requests concurrently without significant performance issues.