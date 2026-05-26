# LaunchPilot Task #49

Repo: jodyswartz/launchpilot-dashboard
Base branch: main
Branch: launchpilot/task-49-1779816764312

## Idea

Update the Mission Control dashboard data loader to support the actual launchpilot-data/tasks.json format: { generated_at, tasks }. Do not expect counts, recentTasks, failedTasks, cancelledTasks, or recentLogs to exist. Instead, derive all dashboard data from tasks[]. Update “Today at a glance”, Recent Tasks, Status Board, Needs Review, Deployment Links, Latest Logs, Cancelled Tasks, and Failed Tasks from tasks[]. Use task.logs for the logs table, preview_url for website links, pr_url for PR links, and generated_at for the last updated timestamp. Treat codex_running tasks older than 24 hours as stale, not active, and show them as blocked/stale instead. Keep fallback sample data if the JSON cannot be loaded.