# Git Flow

How we use branches, commits, PRs, and merges in this project.

## When to Use

- Before committing any change, determine which flow applies.

## Decision

Ask: **does this change need testing?**

| Answer | Flow | Examples |
|--------|------|----------|
| Yes | **Branch flow** | Code, scripts, config that affects runtime |
| No | **Commit on main** | Docs, typos, one-liner tweaks, README updates |

When in doubt, use branch flow.

## Branch Flow

1. **Branch** — Create a feature branch from `master` (e.g. `story-006-container-image`).
2. **Commit** — Make changes and commit to the branch.
3. **Test** — Run relevant tests / verification steps.
4. **Create PR** — Open a pull request against `master`.
5. **Review** — Review the PR (self-review or request review).
6. **Fix** — If issues are found, push fixes to the branch and re-review.
7. **Merge** — Merge the PR into `master`.
8. **Delete branch** — Remove the feature branch after merge.

## Commit on Main

For changes that don't need testing: review the diff, commit directly to `master`.
