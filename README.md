# Express.js Asynchronous Request Handler Bug

This repository demonstrates a common issue in Express.js applications where asynchronous request handlers can cause the application to appear unresponsive. The bug arises from not handling asynchronous operations appropriately within the request handler, leading to potential timeouts and connection issues.

## Bug Description

The `bug.js` file contains an Express.js application with a simple GET route.  The route includes a `setTimeout` function simulating a long-running asynchronous task.  Because the `res.send()` method is placed inside the `setTimeout` callback, the response might not be sent back to the client before the connection times out if the delay is too long.  This makes the application appear to hang.

## Solution

The `bugSolution.js` file provides a corrected version of the application. It resolves the issue by properly handling the asynchronous operation and ensuring that the response is sent to the client even if the asynchronous task takes some time to complete. 

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install` to install the necessary dependencies.
4. Execute `node bug.js` to run the buggy version of the application.
5. Execute `node bugSolution.js` to run the corrected version of the application.