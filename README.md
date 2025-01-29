# Express.js Route Handler Error Handling Bug

This repository demonstrates a common bug in Express.js route handlers: missing error handling for invalid input.  The `bug.js` file shows a route that's vulnerable to crashing if the user ID is not a valid integer.  The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug Description

The buggy code attempts to parse a user ID from a route parameter and uses it to find a user in an array.  If the ID is not a number, `parseInt()` will return `NaN`, and the `find()` method will not work as expected, potentially leading to unexpected behavior or a server crash.

## Solution

The solution adds input validation to ensure the user ID is a valid number.  If it's not, a proper HTTP error response (400 Bad Request) is returned.