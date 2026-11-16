# Notes

**Plan:** Planned first in plan mode, then added `PUT /users/:id`. It has a new `updateUser` helper in `db/store.js` and a route in `routes/users.js`. The route validates the body first (400), then looks up the user (404), then returns the updated user (200).

**Model:** Claude Sonnet 5.5 in Claude Code.

**Commit split:** One commit for the endpoint (store helper and route), and one for this `NOTES.md`.

**Review:** The code review flagged six things. I checked each against the running app:
- Real: validation was a truthiness check, so `{"name":123,"email":{"a":1}}` returned 200 and was stored. Fixed with a shared `isValidUserInput` (non-empty strings, basic email shape), used by POST and PUT.
- Real: `PUT /users/abc` returned 404. It now returns 400 for a non-integer id.
- Not real: a missing or non-JSON body does not crash. Express 4 sets `req.body` to `{}`, so it already returned 400.
- Left alone: in-place mutation in `updateUser` (fine for an in-memory store) and the GET id parsing, which is out of scope.

What was in the plan you approved, and did you edit anything before approving?
add PUT /user/:id
a new updateUser helper
a route in routes/user.js

Which model did you choose, and why?
sonnet because it eccicient for this kind of small job

How did you split your commits, and why that way?
One commit for the endpoint and one commit for the notes.md

What did your review catch — or confirm was already fine?
It was fine
