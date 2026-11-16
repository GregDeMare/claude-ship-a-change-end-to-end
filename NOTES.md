# Notes

**Plan:** Planned first in plan mode, then added `PUT /users/:id`. It has a new `updateUser` helper in `db/store.js` and a route in `routes/users.js`. The route validates the body first (400), then looks up the user (404), then returns the updated user (200).

**Model:** Claude Sonnet 5.5 in Claude Code.

**Commit split:** One commit for the endpoint (store helper and route), and one for this `NOTES.md`.

**Review:** Still to do. Fill this in with what the review caught.
