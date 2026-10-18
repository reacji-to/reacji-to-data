# reacji-to data

Public emoji reactions for [reacji.to](https://reacji.to), stored as Git commits.

The extension and Cloudflare Worker source live separately in [reacji-to/reacji-to](https://github.com/reacji-to/reacji-to).

- `data/<uuid>.json`: one dev-null post.
- `data/x/<id>.json` and `data/linkedin/<id>.json`: one social post.
- `data/web/<sha256-url>.json`: one webpage, including DOM placements and reactions at each placement.
- `profiles/<github-id>.json`: an account's current public reaction index.

The GitHub App commits only validated reaction data and profiles. Private reactions live in each user's own private repository and never enter this repository. Deleted reactions disappear from current views but remain in Git history.

Clone or pull this repository to fetch the data. No GitHub Pages or Issues queue is used.

MIT license; see [LICENSE](LICENSE).
