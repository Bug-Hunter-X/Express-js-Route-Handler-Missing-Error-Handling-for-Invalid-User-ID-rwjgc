# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the `/users/:id` route fails to handle cases where the `id` parameter is not a valid number. This can lead to unexpected behavior or crashes.

## Bug

The `bug.js` file contains the erroneous code. The route handler attempts to parse the `userId` as an integer using `parseInt()`, but it doesn't handle the case where `parseInt()` returns `NaN`. This results in an error if a non-numeric ID is provided.

## Solution

The `bugSolution.js` file shows how to fix the issue.  It adds error handling to check if `parseInt(userId)` is `NaN`. If it is, the handler sends a 400 Bad Request response. This ensures that the application handles invalid input gracefully and prevents crashes.