# A1: Git & GitHub Workflow

Learning the real-world Git workflow from the terminal: branch → pull request → review → merge.

## Steps
| Step | What I did | Key commands | PR |
|---|---|---|---|
| 1 | Created this repository from the terminal | `git init -b main`, `gh repo create --push` | (first commit) |
| 2 | First PR on the GitHub website: added `.gitignore` | `git switch -c`, `git push -u origin` | [#1](https://github.com/maehoo/Cloud-labs/pull/1) |
| 3 | Created and merged a PR from the terminal: added the lab list to README | `gh pr create --fill`, `gh pr merge` | [#2](https://github.com/maehoo/Cloud-labs/pull/2) |
| 4 | Made a merge conflict on purpose and resolved it | `git fetch`, `git merge origin/main` | [#3](https://github.com/maehoo/Cloud-labs/pull/3), [#4](https://github.com/maehoo/Cloud-labs/pull/4) |
| 5 | Stopped tracking an already-committed file | `git rm --cached` | [#5](https://github.com/maehoo/Cloud-labs/pull/5) |
| 6 | Added a PR template and closed an issue from a PR | `.github/pull_request_template.md`, `closes #7` | [#6](https://github.com/maehoo/Cloud-labs/pull/6), [#8](https://github.com/maehoo/Cloud-labs/pull/8) |
| + | Wrote this note and moved labs into phase folders | `git mv`, `git commit --amend` | [#10](https://github.com/maehoo/Cloud-labs/pull/10) |

## What I learned
- `git commit` saves changes only on my computer. `git push` sends them to GitHub, and `git pull` brings GitHub's changes back.
- Keep `main` stable: work on a branch, review the changes in a PR, then merge.
- A conflict happens when two branches change the same line differently. Git stops and lets a person decide, so no one's work is silently lost.
- Git does not track a new file until `git add`, so it does not show up in `git diff` or `git commit -am`.
- If a secret key is pushed to a public repository, revoke the key first. Cleaning up the Git history comes after.

## Troubleshooting log
| Problem | Cause | Fix |
|---|---|---|
| `git diff` showed nothing | A filename typo created a new untracked file (`READEME.md`) | Renamed it with `mv` |
| `error: src refspec ... does not match any` | Typo in the branch name when pushing | Pushed with the real name, or `git push -u origin HEAD` |
| Every git command failed with `bad config line` | Accidentally saved stray text into `~/.gitconfig` from vim | Removed the bad lines, set `core.editor` to nano |
