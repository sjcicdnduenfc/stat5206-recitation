# STAT 5206 — Friday recitation (Ringo's section)

Demo repository for the Git/GitHub sessions. Everyone forks this repo, adds a file under `students/`, and opens a pull request.

## Setup (10 min, before Friday)
1. Get a GitHub account (github.com).
2. GitHub CLI for logging in: Mac `brew install gh`; Windows `winget install GitHub.cli`. Then `gh auth login` → GitHub.com → HTTPS → Yes → Login with a web browser. Check: `gh auth status`.
3. `git config --global user.name "Your Name"` and `git config --global user.email "you@email.edu"` (the email on your GitHub account).
4. Fork this repo (button top right) and `git clone https://github.com/<you>/stat5206-recitation.git`.

## Contribute
1. Fork this repo (button top right).
2. `git clone https://github.com/<you>/stat5206-recitation.git`
3. `git switch -c add-<you>`
4. Create `students/<you>.md` (see `students/README.md`).
5. `git add students/<you>.md && git commit -m "Add <you> to students"`
6. `git push -u origin add-<you>`
7. On GitHub: **Compare & pull request** → base `main` here → **Create pull request**. Put `Closes #1` in the description.

## Data
`data/mpg.csv` — ggplot2's mpg dataset (234 cars), used in the visualization recitation.
`pd.read_csv('data/mpg.csv')` if `from plotnine.data import mpg` doesn't work on your machine.

## Cheat sheet
| Want to… | Command |
|---|---|
| What's going on? | `git status` |
| See my edits | `git diff` |
| Stage / snapshot | `git add <file>` · `git commit -m "message"` |
| History | `git log --oneline --graph --all` |
| New branch / switch | `git switch -c <name>` · `git switch <name>` |
| Send / get commits | `git push` (first time: `git push -u origin <name>`) · `git pull upstream main` |
| Bail out of a merge | `git merge --abort` |
| Discard a file's edits | `git restore <file>` |
| Undo last commit, keep edits | `git reset --soft HEAD~1` |

## Troubleshooting
- `Permission denied to <you>` → you cloned this repo instead of your fork: `git remote set-url origin https://github.com/<you>/stat5206-recitation.git`
- `git push` asks for a password → passwords don't work; run `gh auth login` and push again.
- `! [rejected] (fetch first)` → `git pull`, then `git push`.
- Committed on `main` by mistake → `git switch -c my-branch` (commits come along), then `git switch main && git reset --hard upstream/main`.
