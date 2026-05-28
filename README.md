# LaunchPilot Mission Control

LaunchPilot Mission Control is the static GitHub Pages dashboard for
LaunchPilot. This repository is not the LaunchPilot bot backend and does not
run Telegram commands, GitHub automation, workers, queues, or deployment
services.

The production page is served from `index.html`. It fetches sanitized public
task data from:

```text
https://raw.githubusercontent.com/jodyswartz/launchpilot-data/main/tasks.json
```

Private repository tasks are filtered out by LaunchPilot before `tasks.json` is
published. The dashboard only renders the public data it receives; it does not
perform private-repo filtering in browser JavaScript. If that JSON cannot be
loaded, the page should keep rendering the fallback sample data already embedded
in `index.html`.

## What it tracks

- Metrics for active, review, completed, cancelled, and failed work.
- Recent LaunchPilot tasks and task status.
- Needs-review items with read-only action buttons.
- Latest logs loaded from task data when available.
- Deployment and pull request links.
- Cancelled tasks, failed tasks, and cleanup status.

Commands such as `/logs`, `/cancel`, `/cleanup`, approve, and merge are handled
by the LaunchPilot bot flow, not by this dashboard.

## Three-repo architecture

- `jodyswartz/launchpilot`: the bot and automation backend. It handles
  Telegram commands, repository work, pull requests, review flow, cancellation,
  cleanup, and publishing sanitized dashboard data.
- `jodyswartz/launchpilot-data`: the public data repository. It exposes
  `tasks.json`, which contains sanitized LaunchPilot task data for the
  dashboard.
- `jodyswartz/launchpilot-dashboard`: this static dashboard. It fetches
  `tasks.json` and renders the production GitHub Pages view.

## Quickstart

1. Open `index.html` directly in a browser to view the dashboard locally.
2. To publish it, enable GitHub Pages for this repository and serve from the
   repository root.
3. If the data source changes, update `DATA_URL` in `index.html`.
4. If `tasks.json` cannot be loaded, check the browser console, confirm the raw
   GitHub URL is reachable, verify the JSON is valid, and make sure the data
   file contains only sanitized public fields.

## Deployment links

- GitHub Pages: `https://jodyswartz.github.io/launchpilot-dashboard/`

GitHub Pages serves the dashboard from the repository root through
`index.html`.

## Example workflow

1. Send a LaunchPilot request in Telegram, such as: "Update the dashboard copy
   in `jodyswartz/launchpilot-dashboard`."
2. LaunchPilot creates a task branch, makes the smallest useful change, and
   opens a pull request.
3. Use `/logs` to inspect what happened and confirm no protected files, secrets,
   `.env` files, SSH keys, or deployment tokens were touched.
4. If the run is wrong, use `/cancel`. If it is finished but has leftover task
   resources, use `/cleanup`.
5. Review the pull request in GitHub. If the diff and checks are good, use the
   approve-and-merge flow.
6. After merge, check the GitHub Pages deployment link to confirm the dashboard
   updated.
