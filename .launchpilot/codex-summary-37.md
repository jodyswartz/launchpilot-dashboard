Updated [index.html](/workspaces/task-37/repo/index.html) with the current LaunchPilot workflow:

- LaunchPilot lane now has five steps: Telegram idea, Codex build, GitHub PR, Approve and merge, Open website.
- Read-only/Telegram action copy is clearer across hero, workflow, review buttons, and safety notes.
- Added cancelled tasks to the top metrics.
- Replaced `sage:ready` references with `sage-fix` and `sage-small`.
- Updated merge/deployment copy to reflect LaunchPilot merging PRs and sharing Vercel or GitHub Pages links.
- Kept changes scoped to the existing static design and responsive CSS.

Verified with `git diff --check`. Note: `.launchpilot/codex-prompt-37.md` and `.launchpilot/tasks/task-37.md` were already untracked; I did not edit them.