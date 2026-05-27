# LaunchPilot Task #50

Repo: jodyswartz/launchpilot-dashboard
Base branch: main
Branch: launchpilot/task-50-1779907850094

## Idea

Polish the LaunchPilot dashboard task display so it is legible for end users. Long task descriptions should be converted into compact cards with: task number, short title, status badge, repo, source agent, one-sentence summary, and action links. Move the full original task prompt into a collapsible Details section. Apply this improvement to Recent Tasks, Task Status, Status Board, Needs Review, and Deployment Links. On mobile, replace wide tables with stacked cards. Ensure long text wraps cleanly, is truncated where appropriate, and never breaks the layout. Keep fallback sample data and the existing tasks.json fetch behavior.