Done in [index.html](/workspaces/task-48/repo/index.html:1123).

The dashboard already had the `fetch()` loader and static fallback in place, so I kept the change small: I adjusted the real-data normalization to show `Task #id: idea` from the live feed and changed the generated metric set to include completed tasks instead of weekly PRs.

Verified:
- Embedded dashboard script passes `node --check`.
- Live `tasks.json` loads successfully: 47 tasks, 2 active, 2 review, 40 completed, 2 cancelled, 3 failed, 467 logs, 69 deployment links.
- Static fallback remains untouched if fetch fails.