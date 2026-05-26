Implemented in [index.html](/workspaces/task-45/repo/index.html:1066).

Changed the dashboard to fetch the requested raw GitHub JSON feed, normalize its task fields, and populate metrics, recent tasks, status board, needs-review, deployment links, logs, cleanup queue, cancelled tasks, and the new failed tasks table. The existing static HTML remains in place as the fallback if fetch fails. ([raw.githubusercontent.com](https://raw.githubusercontent.com/jodyswartz/launchpilot-data/main/tasks.json))

Verification:
- Inline script parses with Node.
- Smoke-tested the live fetch with a DOM shim; all target sections populated.
- `git diff --check` passed.

I did not touch secrets, env files, deployment tokens, or the untracked `.launchpilot` task files.