Implemented the dashboard polish in [index.html](/workspaces/task-51/repo/index.html).

What changed:
- Task cards now clamp long titles and summaries, truncate chips/action links, and wrap full prompt text safely.
- `Details` disclosures are now labeled `View details` and keep full prompts in a scrollable collapsible block.
- Recent Tasks, Status Board, Needs Review, and Deployment Links use compact card structure with task number, title, status, repo/source metadata, summary, details, and action links.
- Needs Review now uses compact link actions instead of wide disabled button rows.
- Existing fallback sample data and the remote `tasks.json` fetch behavior are preserved.

Verification:
- `git diff --check`
- Inline dashboard script parsed successfully with Node.

I left the untracked `.launchpilot/...` files untouched.