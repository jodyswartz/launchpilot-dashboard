Updated the README and dashboard copy only.

Changes:
- [README.md](/workspaces/task-54/repo/README.md:7) now states `tasks.json` is sanitized public data and private repo tasks are filtered by LaunchPilot before publish.
- [index.html](/workspaces/task-54/repo/index.html:801) now explains the visible task/log data comes from public JSON after LaunchPilot filters private repo tasks.

I did not change the dashboard JavaScript, so fallback sample data behavior remains intact. No secrets/env/deployment files were touched.