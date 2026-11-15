---
name: submit-pr
description: Publish completed SharpLedger lesson documentation or code changes as a GitHub pull request for the user to review and merge. Invoke explicitly with $submit-pr.
---

# Submit a SharpLedger pull request

An explicit invocation authorizes committing in-scope changes, pushing the topic branch, and opening or reusing a PR to `main`. Leave review and merging to the user. Follow [the repository Git rules](../../../rules/git-workflow.md).

1. Inspect the current checkout, staged and unstaged diffs, untracked files, and existing commits relative to `origin/main`. Fetch `origin` to verify the base and any remote topic branch. Confirm that the checkout and remote belong to SharpLedger. Keep unrelated changes out of the commit and PR, including unrelated staged changes. Ask only when scope is ambiguous or cannot be safely isolated. If there are no publishable changes or relevant commits, stop.
2. For a completed lesson, update the local journal and relevant shared glossary entries if the work calls for it. Keep `docs/learning/`, `docs/learning-journal.md`, and `docs/learning-method.md` local and out of the PR body. Stage only reviewed publishable paths. Check the staged diff for secrets, local artifacts, and unintended changes. Never force-add ignored material.
3. Use the current topic branch if its entire PR diff is in scope. From `main`, create a `codex/<topic>` branch before committing. Reuse a matching branch when retrying. From a detached checkout, create a topic branch only after checking its starting commits. If the branch contains unrelated commits, isolate the requested changes on a clean branch from `origin/main` when safe. Preserve the original work and stop on conflicts you cannot resolve without expanding scope.
4. Run `git diff --check` and `git diff --cached --check`. For code or build-affecting changes run the repository's verification, including `dotnet build` and `dotnet test` as applicable. For docs-only changes inspect the staged document diff. Fix in-scope failures and recheck. Report unavailable verification and stop before publishing if required checks are blocked.
5. Commit only the intended files with Conventional Commit messages that explain why. Verify the branch name and the complete PR diff relative to `origin/main` before pushing. Push only the topic branch to `origin` using a normal push. After a failed or uncertain push, check remote state before retrying. Never force-push or push directly to `main`.
6. Look for an open PR with the same head and base. A normal push updates that PR. Otherwise create a review-ready PR against `main` with a concise summary and actual verification results. Use the GitHub connector or authenticated `gh`; if neither can create the PR, report the pushed branch and provide its GitHub compare URL. On retry, check for a PR again before creating one. Do not approve, merge, or enable auto-merge.
7. Return the PR link, branch, verification results, and any remaining blocker. If publishing stops partway through, state what succeeded so the next invocation can resume.
