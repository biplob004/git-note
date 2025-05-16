## **comprehensive markdown table** of **Git commands**, grouped by **use case sections**. Since you're already familiar with Git, this list includes both **common and advanced commands** with concise descriptions.

---

## 🧾 Navigation

- [Basics](#basics)
- [Configuration](#configuration)
- [Initialization & Cloning](#initialization--cloning)
- [Staging & Committing](#staging--committing)
- [Branching & Merging](#branching--merging)
- [Remote Repositories](#remote-repositories)
- [Status & Inspection](#status--inspection)
- [Undo Changes](#undo-changes)
- [Rebasing & Reflog](#rebasing--reflog)
- [Tags](#tags)
- [Stashing](#stashing)
- [Patching & Interactive Mode](#patching--interactive-mode)
- [Submodules](#submodules)
- [Advanced Commands](#advanced-commands)

---

## 🔹 Basics

| Command | Description |
|--------|-------------|
| `git --version` | Show installed Git version |
| `git help <command>` | Get help on a specific command |
| `git init` | Initialize a new Git repository |
| `git clone <url>` | Clone a remote repository |

---

## ⚙️ Configuration

| Command | Description |
|--------|-------------|
| `git config --global user.name "Name"` | Set global username |
| `git config --global user.email "email@example.com"` | Set global email |
| `git config --global core.editor <editor>` | Set default editor (e.g., `vim`, `code`) |
| `git config --list` | List current Git configuration |
| `git config --global color.ui auto` | Enable colored output in terminal |

---

## 🔄 Initialization & Cloning

| Command | Description |
|--------|-------------|
| `git init` | Create an empty Git repo in current directory |
| `git init <repo-name>` | Initialize a new repo in a new directory |
| `git clone <url>` | Clone a remote repo into a local directory |
| `git clone <url> <dir-name>` | Clone repo into a custom directory |
| `git clone --depth 1 <url>` | Shallow clone with limited history |

---

## 📥 Staging & Committing

| Command | Description |
|--------|-------------|
| `git add <file>` | Add file to staging area |
| `git add .` | Stage all changes in working directory |
| `git commit -m "Message"` | Commit staged changes with message |
| `git commit -a -m "Message"` | Stage modified/tracked files and commit |
| `git commit --amend` | Amend the last commit |
| `git reset <file>` | Unstage file while keeping changes |
| `git checkout -- <file>` | Discard changes in working directory |

---

## 🌿 Branching & Merging

| Command | Description |
|--------|-------------|
| `git branch` | List all branches |
| `git branch <name>` | Create a new branch |
| `git checkout <name>` | Switch to a branch |
| `git checkout -b <name>` | Create and switch to a new branch |
| `git merge <branch>` | Merge specified branch into current |
| `git branch -d <name>` | Delete a merged branch |
| `git branch -D <name>` | Force delete an unmerged branch |
| `git merge --no-ff <branch>` | Merge without fast-forward |
| `git merge --squash <branch>` | Combine changes as one commit |
| `git branch --merged` | View branches merged into current |

---

## 🌐 Remote Repositories

| Command | Description |
|--------|-------------|
| `git remote` | List remotes |
| `git remote -v` | Show remote URLs |
| `git remote add <name> <url>` | Add a new remote |
| `git fetch <remote>` | Fetch data from remote |
| `git pull` | Fetch and merge from remote tracking branch |
| `git push <remote> <branch>` | Push local commits to remote branch |
| `git push -u <remote> <branch>` | Set upstream and push |
| `git push --tags` | Push tags to remote |
| `git remote prune origin` | Remove stale remote-tracking branches |

---

## 🕵️ Status & Inspection

| Command | Description |
|--------|-------------|
| `git status` | Show working tree status |
| `git log` | Show commit history |
| `git log --oneline` | Compact one-line log |
| `git log --graph --oneline --all` | Visual branch log |
| `git diff` | Show unstaged changes |
| `git diff --cached` | Show staged changes |
| `git diff <commit> <commit>` | Compare two commits |
| `git blame <file>` | Show who last modified each line |
| `git show <commit>` | Show details about a commit |

---

## 🔁 Undo Changes

| Command | Description |
|--------|-------------|
| `git reset HEAD~1` | Uncommit last commit, keep changes |
| `git reset --soft HEAD~1` | Keep changes staged |
| `git reset --hard HEAD~1` | Discard last commit and changes |
| `git checkout <commit> -- <file>` | Restore file from a previous commit |
| `git revert <commit>` | Create a new commit that undoes changes |
| `git reflog` | See history of reference changes |
| `git fsck` | Check integrity of objects in database |

---

## 🔄 Rebasing & Reflog

| Command | Description |
|--------|-------------|
| `git rebase <branch>` | Reapply commits over another base |
| `git rebase -i HEAD~3` | Interactive rebase for last 3 commits |
| `git rebase --continue` | Continue after resolving conflicts |
| `git rebase --abort` | Abort current rebase |
| `git reflog` | Show history of HEAD changes |
| `git reflog show` | Same as `git reflog` |
| `git reflog expire --expire=now` | Clear old entries from reflog |
| `git gc` | Run garbage collection |

---

## 🏷️ Tags

| Command | Description |
|--------|-------------|
| `git tag` | List existing tags |
| `git tag v1.0` | Create lightweight tag |
| `git tag -a v1.0 -m "message"` | Create annotated tag |
| `git push origin v1.0` | Push single tag to remote |
| `git push origin --tags` | Push all tags |
| `git tag -d v1.0` | Delete local tag |
| `git push origin :refs/tags/v1.0` | Delete remote tag |

---

## 🎒 Stashing

| Command | Description |
|--------|-------------|
| `git stash` | Save modified tracked files temporarily |
| `git stash save "message"` | Stash with optional description |
| `git stash list` | List all stashes |
| `git stash apply` | Apply latest stash |
| `git stash apply stash@{2}` | Apply specific stash |
| `git stash drop` | Remove latest stash |
| `git stash pop` | Apply and remove latest stash |
| `git stash clear` | Delete all stashes |
| `git stash -u` or `--include-untracked` | Include untracked files |
| `git stash -a` or `--all` | Include ignored and untracked files |

---

## 🧩 Patching & Interactive Mode

| Command | Description |
|--------|-------------|
| `git add -p` | Interactively stage hunks of changes |
| `git checkout -p` | Interactively discard parts of changes |
| `git stash apply -p` | Apply only part of a stash |
| `git reset -p` | Unstage specific parts of files |
| `git commit -p` | Stage and commit interactively |
| `git diff --word-diff` | Highlight word-level diffs |

---

## 🧱 Submodules

| Command | Description |
|--------|-------------|
| `git submodule add <url>` | Add submodule to repo |
| `git submodule init` | Initialize submodules |
| `git submodule update` | Pull submodule content |
| `git submodule update --init --recursive` | Init and update nested submodules |
| `git submodule foreach git pull` | Update all submodules |
| `git submodule deinit <path>` | Remove submodule from `.git/config` |
| `rm -rf .git/modules/<path>` | Manually remove submodule from index |

---

## 🔍 Advanced Commands

| Command | Description |
|--------|-------------|
| `git filter-branch` | Rewrite Git history (deprecated) |
| `git filter-branch --tree-filter 'rm -f secrets.txt' HEAD` | Remove file from all commits |
| `git bisect start` | Start binary search to find bug-introducing commit |
| `git bisect good/bad` | Mark commit as good or bad during bisect |
| `git bisect reset` | End bisect session |
| `git worktree add ../new-workdir <branch>` | Use multiple working directories |
| `git archive --format zip --output file.zip HEAD` | Export current branch as zip |
| `git gc --aggressive` | Garbage collect and compress object store |
| `git verify-commit <commit>` | GPG verify a commit |
| `git rev-parse HEAD` | Get SHA-1 hash of current commit |
| `git ls-files` | List all files tracked in index |

