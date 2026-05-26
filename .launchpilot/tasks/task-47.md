# LaunchPilot Task #47

Repo: jodyswartz/launchpilot-dashboard
Base branch: main
Branch: launchpilot/task-47-1779805811958

## Idea

Improve the LaunchPilot Dashboard README so it accurately describes the production dashboard. Explain that this repo is a static GitHub Pages dashboard, not the bot backend. It fetches sanitized LaunchPilot task data from jodyswartz/launchpilot-data/tasks.json and renders metrics, recent tasks, needs-review items, logs, deployment links, cancelled tasks, failed tasks, and cleanup status. Document the three-repo architecture: launchpilot, launchpilot-data, and launchpilot-dashboard. Add quickstart steps for opening index.html locally, enabling GitHub Pages, updating the DATA_URL, and troubleshooting when tasks.json cannot be loaded. Mention that the page should keep fallback sample data if the fetch fails.