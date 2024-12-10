# Express.js Route Handler Missing Return Statement

This repository demonstrates a common error in Express.js route handlers: a missing `return` statement within a conditional block.  This can lead to unexpected behavior and potentially allow subsequent code to execute even when a proper response has been sent, causing errors or incorrect data handling.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Bug

The issue is within the `/users/:id` route handler. If a user is not found (`!user`), a 404 response is sent. However, the lack of a `return` statement allows the `res.send(user)` line to execute regardless, potentially causing an error or unexpected output if `user` is undefined.