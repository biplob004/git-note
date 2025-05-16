
# 📚 Git Commands Table – Updated for Latest Version (2025)

## 🔧 Setup & Configuration

| Command | Description |
|--------|-------------|
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone an existing repository |
| `git config --global user.name "Name"` | Set global username |
| `git config --global user.email "email@example.com"` | Set global email |
| `git config --list` | View all configuration settings |
| `git config color.ui auto` | Enable colored output |

---

## 📁 Working with Files

| Command | Description |
|--------|-------------|
| `git status` | Show current status of working directory |
| `git add <file>` | Add a specific file to staging area |
| `git add .` | Add all files in current directory to staging |
| `git diff` | Show changes in working directory vs staging |
| `git diff --cached` | Show changes staged for next commit |
| `git restore <file>` | Discard changes in working directory |
| `git restore --staged <file>` | Unstage a file (keep changes) |
| `git checkout -- <file>` | Older way to discard local changes (deprecated) |

---

## 💾 Committing Changes

| Command | Description |
|--------|-------------|
| `git commit -m "message"` | Commit staged changes with message |
| `git commit --amend` | Modify last commit (add forgotten changes or edit message) |
| `git reset HEAD~1` | Undo last commit but keep changes unstaged |
| `git reset --hard HEAD~1` | Discard last commit and changes |
| `git revert HEAD` | Create a new commit that undoes the last commit |

---

## 🌿 Branching & Merging

| Command | Description |
|--------|-------------|
| `git branch` | List all branches |
| `git branch <name>` | Create a new branch |
| `git checkout <branch>` | Switch to another branch (legacy) |
| `git switch <branch>` | Modern command to switch branches |
| `git switch -c <name>` | Create and switch to a new branch |
| `git merge <branch>` | Merge another branch into current one |
| `git branch -d <name>` | Delete a branch safely |
| `git branch -D <name>` | Force delete a branch |
| `git log --graph --oneline --all` | Visualize branch history |

---

## 🌐 Remote Repositories

| Command | Description |
|--------|-------------|
| `git remote -v` | List connected remote repositories |
| `git remote add origin <url>` | Add a remote named `origin` |
| `git fetch` | Download commits from remote (no merge) |
| `git pull` | Fetch + merge changes from remote |
| `git pull origin main` | Pull changes from specific remote branch |
| `git push` | Upload local commits to remote |
| `git push -u origin main` | Push and set upstream tracking |
| `git fetch --prune` | Remove stale remote-tracking branches |

---

## 🔄 Syncing & Updating

| Command | Description |
|--------|-------------|
| `git fetch` | Get latest changes without merging |
| `git pull` | Fetch and merge changes |
| `git push` | Upload your commits |
| `git push --force` | Overwrite remote history (use with caution) |
| `git reflog` | See where HEAD has pointed (helps recover lost commits) |

---

## 🧹 Cleaning & Maintenance

| Command | Description |
|--------|-------------|
| `git clean -n` | Show files that would be removed |
| `git clean -f` | Remove untracked files |
| `git gc` | Garbage collect unnecessary files |
| `git fsck` | Check integrity of Git database |

---

## 🧪 Advanced Tools

| Command | Description |
|--------|-------------|
| `git stash` | Temporarily save changes |
| `git stash apply` | Reapply stashed changes |
| `git stash list` | List saved stashes |
| `git cherry-pick <commit>` | Apply a specific commit |
| `git bisect start` | Binary search through commits to find bugs |
| `git blame <file>` | Show who changed each line of a file |
| `git tag v1.0.0` | Create a tag for release |
| `git archive` | Export a repo snapshot as ZIP/TAR |

---

## 🧩 Miscellaneous Useful Commands

| Command | Description |
|--------|-------------|
| `git log` | View commit history |
| `git log --oneline` | Compact log view |
| `git show <commit>` | Show details of a commit |
| `git submodule add <url>` | Add a Git submodule |
| `git worktree add ../new-branch dev` | Work on multiple branches at once |

---

## 🆕 Modern Git Commands (Safer Alternatives)

| Legacy Command | Modern Alternative | Purpose |
|----------------|--------------------|---------|
| `git checkout -- <file>` | `git restore <file>` | Discard changes |
| `git reset HEAD <file>` | `git restore --staged <file>` | Unstage file |
| `git checkout <branch>` | `git switch <branch>` | Switch branches |
| `git checkout -b <branch>` | `git switch -c <branch>` | Create + switch |

