Implemented in [index.html](/workspaces/task-50/repo/index.html).

What changed:
- Added reusable compact task cards with task number, short title, status badge, repo, source agent, one-sentence summary, Details, and action links.
- Applied the card format to Recent Tasks, Status Board, Needs Review, and Deployment Links.
- Replaced the Status Board table with stacked cards, with mobile-friendly wrapping/truncation.
- Preserved the existing `tasks.json` fetch behavior and updated fallback sample data to match the new display.

Verification:
- Inline dashboard script syntax: passed.
- Mock `tasks.json` render path: passed.
- `git diff --check`: passed.
- `xmllint` was unavailable in the container.