# Express.js Route Handler Error: Invalid User ID

This repository demonstrates a common error in Express.js route handlers: insufficient error handling when dealing with user input.  Specifically, the route `/users/:id` doesn't handle the case where `:id` is not a valid integer, leading to potential crashes or unexpected behavior.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides a corrected version with improved error handling.

## Bug:

The bug lies in the lack of error handling for when `req.params.id` is not a valid number.  Attempting to use `parseInt` on a non-numeric string will not throw an error immediately, but if the `users` array does not contain an element with the parsed ID, the application may behave unexpectedly (e.g., crashing if the `user` variable is undefined later in the handler).

## Solution:

The solution includes explicit checks to validate the incoming `userId` before attempting to parse it and access the user data.