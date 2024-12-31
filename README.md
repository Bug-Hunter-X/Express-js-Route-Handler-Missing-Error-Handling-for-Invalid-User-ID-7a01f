# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the provided code attempts to parse a user ID from a request parameter but doesn't handle cases where the ID is not a valid integer.

The `bug.js` file shows the erroneous code. The `bugSolution.js` file provides a corrected version with appropriate error handling.

## Bug

The original code attempts to convert the user ID (obtained from `req.params.id`) to an integer using `parseInt()`.  However, if the user ID is not a valid integer (e.g., a string or a floating-point number), `parseInt()` returns `NaN`, leading to a potential runtime error or unexpected behavior.  The corrected code addresses this shortcoming.

## Solution

The solution includes a check for `isNaN()` to verify if `parseInt(userId)` returned a valid number. If not, it sends a proper error response (e.g., 400 Bad Request).