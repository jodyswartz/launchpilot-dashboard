Implemented the smallest useful static update in [docs/index.html](/workspaces/task-29/repo/docs/index.html:554).

Changes:
- Renamed the PR section/navigation to explicit `Needs Review`.
- Added explicit `Whitelisted Repos`, `Supported Labels`, and `Cancelled Tasks` tables.
- Added `Cleanup` to the read-only safety controls.
- Kept everything static, responsive, GitHub Pages friendly, and consistent with the existing styling.

Verification:
- Checked anchors/content with `rg`.
- `xmllint` was not available, so no HTML validator run.
- Left `.launchpilot/*` untracked task files untouched.