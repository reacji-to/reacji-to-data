# reacji-to data

Public emoji reactions for [reacji.to](https://reacji.to), stored as Git commits.

The [extension](https://github.com/reacji-to/reacji-to) and [website / Cloudflare Worker](https://github.com/reacji-to/reacji-to-web) each have their own source repository. All three repositories use the MIT license.

- `data/<uuid>.json`: one dev-null post.
- `data/x/<id>.json` and `data/linkedin/<id>.json`: one social post.
- `data/web/<sha256-url>.json`: one webpage, including DOM placements and reactions at each placement.
- `profiles/<github-id>.json`: an account's current public reaction index.

The GitHub App commits only validated reaction data and profiles. Private reactions live in each user's own private repository and never enter this repository. Deleted reactions disappear from current views but remain in Git history.

## Public mirrors for personal automations

Starting with extension v0.4.3, **Mirror my public reactions to this private repo** is enabled by default. Once a user selects their own private repository in extension settings, public saves also copy that user's current reactions for the affected post/page into `public/data/` there. Private reactions remain in the private repository's separate `data/` folder. Copies contain only the owner's public reactions, and include `visibility: "public"`; their originals remain public here.

Automations in the personal repository can watch `data/**` for private reactions and `public/data/**` for public copies. Edits, moves, and removals reconcile the affected post/page. There is no historical import or background retry. A failed mirror does not undo the public save; after correcting repository/app access, the next public save on that post/page retries its current state. Turning mirroring off leaves existing copies and Git history in place.

See the [agent setup walkthrough](https://github.com/reacji-to/reacji-to/blob/main/SETUP.md#7-offer-automations-with-github-actions) for workflow triggers and automation guidance. This public data repository does not receive private reactions, automation code, or automation output.

Clone or pull this repository to fetch the data. No GitHub Pages or Issues queue is used.

MIT license; see [LICENSE](LICENSE).
