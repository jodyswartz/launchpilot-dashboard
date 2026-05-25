Implemented the static read-only Mission Control dashboard in [docs/index.html](/workspaces/task-28/repo/docs/index.html:671).

Changes include:
- Recent tasks and task status sample data.
- PR and merge status with disabled read-only actions.
- GitHub Pages and Vercel sample deployment links.
- Latest logs table.
- Workspace cleanup queue.
- Updated dashboard nav anchors.

Validation: ran `git diff --check` successfully and confirmed the requested section headings are present. I left the existing untracked `.launchpilot` task files untouched.