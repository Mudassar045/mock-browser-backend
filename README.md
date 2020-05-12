# Browser Mock Backend

> Thinking about convert into npm package

The fake backend enables the example to run without a backend (backend-less), it contains a hardcoded collection of users and provides fake implementations for the api endpoints `authenticate`, `get user by id`, and `get all users`, these would be handled by a real api and database in a production application.

The `authenticate` endpoint is used for logging in to the application and is publicly accessible, the `get user by id` is restricted to authenticated users in any role, however regular users can only access their own user record whereas admin users can access any user record. The "get all users" endpoint is restricted to admin users only.

The fake backend is implemented by *monkey patching* the `fetch() function` to intercept certain api requests and mimic the behaviour of a real api. Any requests that aren't intercepted get passed through to the real fetch() function.
