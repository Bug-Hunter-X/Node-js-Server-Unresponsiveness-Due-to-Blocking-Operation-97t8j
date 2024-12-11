# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a corrected version using asynchronous operations.

**Problem:** The original code performs a 5-second CPU-bound operation within the request handler. During this time, the server cannot process any other requests, leading to unresponsiveness and potentially a timeout for clients.

**Solution:** The solution uses asynchronous operations or offloads the long-running task to a worker thread to avoid blocking the main event loop. This ensures that the server remains responsive to other requests even while handling long-running tasks.