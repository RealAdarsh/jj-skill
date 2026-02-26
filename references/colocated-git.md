# Colocated Workflow (`.jj` + `.git`)

Use this workflow when teammates still use Git while you work with Jujutsu locally.

## Daily Sync

```bash
jj git fetch
jj rebase -d main@origin
```

## Prepare and Push a Change

Fast path:

```bash
jj git push --change @-
```

Bookmark path:

```bash
jj bookmark create feat/my-change -r @-
jj git push -b feat/my-change
```

## Pull Request Feedback

```bash
jj edit <change-id>
# apply requested edits
jj describe -m "Address PR feedback"
jj new
jj git fetch
jj rebase -d main@origin
jj git push -b feat/my-change
```

## Parallel Workspaces

Use workspaces to work on multiple changes at the same time without stashing:

```bash
jj workspace add ../hotfix        # separate directory for a hotfix
jj workspace list
jj workspace forget hotfix        # clean up when done
```

Each workspace shares the same repo state, so bookmarks and history stay in sync.

## Interop Rules

1. Prefer `jj` for local mutations.
2. If another tool creates Git commits directly, run:

```bash
jj git import
```

3. Keep bookmark names stable across pushes so PR branches remain predictable.
