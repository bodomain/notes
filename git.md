
---

| Command                                             | Short Explanation                                                                                        |
| --------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| `git init`                                          | Creates a new Git repository in the current folder.                                                      |
| `git clone <url>`                                   | Downloads an existing repository from a server (e.g., GitHub) to your computer.                          |
| **--- Basic Workflow ---**                          |                                                                                                          |
| `git status`                                        | Shows the current state: which files are changed, staged, or untracked.                                  |
| `git add <file>`                                    | Stages a file – marks it for the next commit.                                                            |
| `git add .`                                         | Stages **all** changed files in the current folder.                                                      |
| `git commit -m "message"`                           | Saves all staged changes as a new snapshot (commit) with a descriptive message.                          |
| `git log`                                           | Shows the commit history of the current branch.                                                          |
| `git log --oneline`                                 | Compact version – each commit on one line.                                                               |
| **--- Branches (the core of your observation) ---** |                                                                                                          |
| `git branch`                                        | Lists all local branches. The current one is marked with `*`.                                            |
| `git branch <name>`                                 | Creates a new branch (but does NOT switch to it).                                                        |
| `git switch <branch>`                               | Switches to an existing branch. **Uncommitted changes come with you!** (as you discovered)               |
| `git switch -c <branch>`                            | Creates a new branch AND switches to it (shortcut for `branch` + `switch`).                              |
| `git branch -d <branch>`                            | Deletes a branch (only if its changes are already merged).                                               |
| **--- Differences & Compare ---**                   |                                                                                                          |
| `git diff`                                          | Shows uncommitted changes in your working directory.                                                     |
| `git diff <branch1>..<branch2>`                     | Shows all differences between two branches.                                                              |
| `git diff --stat <branch1>..<branch2>`              | Summary: only which files changed, not the full code.                                                    |
| **--- Working with remotes (server) ---**           |                                                                                                          |
| `git remote -v`                                     | Shows which remote servers are configured (e.g., origin).                                                |
| `git fetch`                                         | Downloads all new commits from the remote, but does NOT merge them into your branches.                   |
| `git pull`                                          | Downloads AND merges the remote changes into your current branch (`fetch` + `merge`).                    |
| `git push`                                          | Uploads your local commits to the remote server.                                                         |
| `git push -u origin <branch>`                       | Pushes a new branch to the remote and sets up tracking (so future `push`/`pull` work without arguments). |
| **--- Fixing mistakes ---**                         |                                                                                                          |
| `git stash`                                         | Temporarily saves uncommitted changes aside – cleans your working directory.                             |
| `git stash pop`                                     | Restores the last stashed changes back into your working directory.                                      |
| `git reset <file>`                                  | Unstages a file (removes it from the staging area, but keeps the changes).                               |
| `git reset --hard`                                  | **DANGER:** Discards ALL uncommitted changes permanently.                                                |
| `git revert <commit>`                               | Creates a new commit that undoes the changes of a specific commit (safe for shared branches).            |
| **--- Help ---**                                    |                                                                                                          |
| `git help <command>`                                | Opens the official manual for any command (e.g., `git help switch`).                                     |

---

## Bonus: The commands you used in your observation

| Your Situation                    | Command                              |
| --------------------------------- | ------------------------------------ |
| See all branches (local + remote) | `git branch -a`                      |
| Switch to the feature branch      | `git switch feature/neues-login`     |
| Back to main                      | `git switch main`                    |
| See if there are differences      | `git diff main..feature/neues-login` |
| Check for uncommitted changes     | `git status`                         |

---

## One rule of thumb for you

> **`git status` is your best friend.**  
> Run it before and after every `switch` – it tells you exactly what's going on.