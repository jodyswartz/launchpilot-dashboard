Updated [index.html](/workspaces/task-49/repo/index.html:1115) so the dashboard now derives its rendered model from `{ generated_at, tasks }`.

Key changes:
- Derives metrics, Recent Tasks, Status Board, Needs Review, Deployment Links, Latest Logs, Cleanup, Cancelled Tasks, and Failed Tasks from `tasks[]`.
- Uses `task.logs`, `preview_url`, `pr_url`, and `generated_at`.
- Treats `codex_running`/running tasks older than 24 hours as `blocked/stale`, excluding them from active runs.
- Keeps the existing static sample dashboard intact if JSON loading fails.

Verification:
- Parsed the embedded script successfully with Node.
- Smoke-tested against the live `tasks.json`; it rendered `last updated` from `generated_at` and showed the old running task as `blocked/stale`.