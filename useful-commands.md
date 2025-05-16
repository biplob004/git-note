
# 🧰 Useful Git Commands You Should Know

## 🔁 Undo Changes

| Command | Description |
|--------|-------------|
| `git restore <file>` | Discard changes in working directory (reset file to last commit) |
| `git restore --staged <file>` | Unstage a file (remove from staging area) |
| `git restore --source=HEAD~1 <file>` | Restore file from previous commit |
| `git checkout -- <file>` | Older alternative to `git restore <file>` |
| `git reset` | Unstage all staged files |
| `git reset --hard` | Discard all local changes (working directory + staging area) |
| `git revert HEAD` | Revert the last commit by creating a new commit that undoes it |

---

## 🌿 Branch Management

| Command | Description |
|--------|-------------|
| `git branch` | List all local branches |
| `git branch <name>` | Create a new branch |
| `git checkout <branch>` | Switch to an existing branch |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git switch <branch>` | Modern way to switch branches (cleaner than `checkout`) |
| `git switch -c <name>` | Create and switch to a new branch |
| `git merge <branch>` | Merge another branch into current branch |
| `git branch -d <name>` | Delete a local branch (safe delete) |
| `git branch -D <name>` | Force delete a branch even if not merged |

---

## 🚨 Stash Local Changes

When you want to save changes temporarily without committing:

| Command | Description |
|--------|-------------|
| `git stash` | Save modified and staged changes to a stack |
| `git stash push -m "message"` | Stash with a descriptive message |
| `git stash list` | See all saved stashes |
| `git stash apply` | Apply the most recent stashed changes |
| `git stash apply stash@{2}` | Apply a specific stash |
| `git stash drop stash@{0}` | Delete a specific stash |
| `git stash clear` | Delete all stashes |

---

## 🔍 View History & Differences

| Command | Description |
|--------|-------------|
| `git log` | Show commit history |
| `git log --oneline` | Compact view of commit history |
| `git log --graph --all --oneline` | Visualize branch history as ASCII graph |
| `git diff` | Show differences between working directory and staging area |
| `git diff --cached` | Show what is staged for the next commit |
| `git blame <file>` | Show who changed each line of a file and when |
| `git show <commit>` | Show details of a specific commit |

---

## 💾 Remote Repository Interaction

| Command | Description |
|--------|-------------|
| `git remote -v` | Show connected remote repositories |
| `git remote add origin <url>` | Add a remote named `origin` |
| `git fetch` | Download commits, files, and refs from remote |
| `git pull` | Fetch and merge changes from remote branch |
| `git push` | Upload local commits to remote repository |
| `git push -u origin main` | Push and set upstream tracking |
| `git push --set-upstream-to=origin/dev dev` | Set upstream for an existing branch |
| `git fetch --prune` | Remove remote-tracking branches that no longer exist on remote |

---

## 🧪 Advanced / Utility Commands

| Command | Description |
|--------|-------------|
| `git gc` | Clean up unnecessary files and optimize local repository |
| `git fsck` | Check database integrity |
| `git reflog` | Show a log of where HEAD has pointed (useful for recovering lost commits) |
| `git cherry-pick <commit>` | Apply a specific commit from another branch |
| `git bisect` | Binary search through commits to find regression bugs |
| `git submodule` | Work with submodules (nested repos inside a repo) |
| `git archive` | Export a snapshot of a repo as a tar/zip |

---

## 📦 Bonus: Git Configuration

| Command | Description |
|--------|-------------|
| `git config --global user.name "Your Name"` | Set global username |
| `git config --global user.email "you@example.com"` | Set global email |
| `git config --list` | View all Git configurations |
| `git config core.editor "code --wait"` | Set default editor (e.g., VS Code) |
| `git config color.ui auto` | Enable colorful output |
| `git config --global alias.co checkout` | Create command aliases (e.g., `git co` instead of `git checkout`) |

---

## ✅ Example: Setting Up Aliases

Make Git faster with custom shortcuts:

```bash
git config --global alias.br branch
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
```

Now you can do:
```bash
git co dev      # switch to dev branch
git br feature  # create feature branch
git st          # check status
```

---

## 📝 Summary Table: Modern vs Legacy Commands

| Task | Legacy | Modern |
|------|--------|--------|
| Unstage file | `git reset HEAD <file>` | `git restore --staged <file>` |
| Discard changes | `git checkout -- <file>` | `git restore <file>` |
| Switch branch | `git checkout <branch>` | `git switch <branch>` |
| Create + switch | `git checkout -b <branch>` | `git switch -c <branch>` |

---

## 📄 Want a Cheat Sheet?

I can generate a printable **Git cheat sheet PDF** summarizing these commands. Just let me know!

Or I can give you:
- A **visual diagram** of Git areas (`Working Directory`, `Staging Area`, `HEAD`)
- A **flowchart** for undoing changes (`restore`, `reset`, `revert`)
- Or a **practice lab script** to try all these commands step-by-step

