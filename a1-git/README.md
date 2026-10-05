# A1: Git & GitHub Workflow

## What I did
- Created this repository from the terminal (`git init`, `gh repo create`)
- Practiced branch → pull request → merge (PR #1–#8)
- Made a merge conflict on purpose and resolved it (PR #3, #4)
- Stopped tracking an already-committed file with `git rm --cached` (PR #5)
- Added a PR template and closed an issue from a PR (PR #6, #8 / issue #7)

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
