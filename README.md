# LaunchPilot Mission Control

LaunchPilot Mission Control is a beginner-friendly dashboard for watching
AI-assisted repository work move from request to pull request. It is a static
site served from `index.html`, so there is no app server to run.

## What it tracks

- **LaunchPilot Telegram tasks**: ideas sent through Telegram become focused
  tasks, branches, and pull requests.
- **S.A.G.E. GitHub issue automation**: labeled GitHub issues can be picked up
  by S.A.G.E., implemented on a branch, and opened as pull requests for review.
- **Review status**: work stays visible while it is queued, running, waiting for
  review, cancelled, merged, or ready for cleanup.

## Operator actions

- `/logs` shows the task prompt, branch, changed files, command output, and
  current status.
- `/cancel` stops queued or active automation before it continues.
- `/cleanup` removes or archives temporary task resources after a run is done.
- **Approve-and-merge** means a human reviews the pull request, approves it, and
  merges it only when the changes and checks look good.

## Deployment links

- GitHub Pages: `https://jodyswartz.github.io/launchpilot-dashboard/`
- Vercel: `https://launchpilot-dashboard.vercel.app/`

GitHub Pages serves the dashboard from the repository root through
`index.html`. Vercel can serve the same static page as a preview or production
deployment.

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
6. After merge, check the GitHub Pages or Vercel deployment link to confirm the
   dashboard updated.
