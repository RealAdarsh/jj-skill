# Git to Jujutsu Quick Cheat Sheet

Use this file when a user describes Git commands and needs practical `jj` equivalents.

| Intent | Git | Jujutsu |
|---|---|---|
| Show working state | `git status` | `jj status` |
| View history graph | `git log --graph` | `jj log` |
| Show current diff | `git show HEAD` | `jj show` |
| Start new work on current state | `git checkout -b feature` | `jj new` then `jj describe -m "..."` |
| Create commit with message | `git commit -m "msg"` | `jj commit -m "msg"` |
| Update current commit message | `git commit --amend -m "msg"` | `jj describe -m "msg"` |
| Rebase change | `git rebase <base>` | `jj rebase -r <revision> -d <destination>` |
| Drop commit/change | `git rebase -i` (drop) | `jj abandon <revision>` |
| Discard file edits | `git restore <path>` | `jj restore <path>` |
| Recover from bad operation | `git reflog` + reset | `jj undo`, `jj op log`, `jj op restore <op-id>` |
| Fetch remote updates | `git fetch` | `jj git fetch` |
| Push one line of work | `git push origin feature` | `jj git push --change @-` or bookmark workflow |
| View diff of working copy | `git diff` | `jj diff` |
| Diff a specific revision | `git show <commit>` | `jj diff -r <revision>` |
| Blame/annotate a file | `git blame <file>` | `jj file annotate <file>` |
| Split a commit | `git rebase -i` (edit) | `jj split <paths>... -m "split: ..."` |
| Navigate to parent | `git checkout HEAD~1` | `jj prev -e` |
| Navigate to child | — | `jj next -e` |
| Copy a commit onto target | `git cherry-pick <commit>` | `jj duplicate <revision> --destination <target>` |
| View change evolution | `git reflog` (approximate) | `jj evolog` |
| Clean up merge parents | — | `jj simplify-parents` |
| Parallel working copies | `git worktree add <path>` | `jj workspace add <path>` |
| List working copies | `git worktree list` | `jj workspace list` |
| Auto-format code | — | `jj fix` |

## Notes

1. Prefer `jj` commands for repository mutations in colocated repos.
2. Use `jj help <subcommand>` when flags differ by version.
3. In non-interactive environments, pass `-m` for commands that can open an editor.
4. For `duplicate`, choose a destination that is not a descendant of the source commit.
