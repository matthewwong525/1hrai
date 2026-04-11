---
name: ship
description: Push the current branch, create a PR against main, resolve any merge conflicts, and merge. Run the full flow without asking for confirmation at each step.
---

# Ship

Push the current branch, create a PR against main, resolve any merge conflicts, and merge. Run the full flow without asking for confirmation at each step.

## Steps

1. **Prepare the branch**: Run `git status` to check for uncommitted changes. If there are uncommitted changes, create a commit with an auto-generated message summarizing the changes (use `git diff` to understand what changed). Use the format: `Co-Authored-By: Claude Opus 4.6 (1M context) <noreply@anthropic.com>` at the end of the commit message.

2. **Ensure branch is not main**: If on `main`, create a new branch named after the changes (e.g., `feat/add-login`, `fix/header-bug`) and switch to it before proceeding.

3. **Push to remote**: Run `git push -u origin HEAD`. If the push is rejected due to diverged history, first pull with `git pull origin <branch> --no-rebase` and resolve any merge conflicts by preferring the local (current branch) version using `git checkout --theirs` for conflicting files, then commit the merge and push again.

4. **Sync with main**: Before creating the PR, fetch the latest main and check if there are conflicts between the current branch and main:
   - Run `git fetch origin main`
   - Run `git merge origin/main` to bring main's changes into the branch
   - If there are merge conflicts, resolve them by keeping the current branch's changes (`git checkout --ours <file>` for each conflicting file), then `git add` the resolved files and `git commit`
   - Push the merged result

5. **Create the PR**: Use `gh pr create --fill --base main`. If a PR already exists for this branch, skip creation and use the existing one. Capture the PR number/URL.

6. **Merge the PR**: Use `gh pr merge <number> --merge --delete-branch` to merge and clean up the remote branch. If merge fails due to conflicts or checks, report the error.

7. **Clean up locally**: Switch back to `main` and pull the latest: `git checkout main && git pull origin main`. Delete the local feature branch.

8. **Report**: Print a short summary with the PR URL and confirm the merge succeeded.
