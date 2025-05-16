##  📝  **hands-on guide** covering:
- Initializing and cloning repos
- Adding and committing changes
- Working with remotes (`origin`)
- Pushing, pulling, and merging

Let’s go step by step!

---

# 🧾 Basic Git Commands (With Examples)

## 1. 🔧 Initialize a New Git Repository

```bash
git init
```

> Starts a new Git repository in the current folder.

### Example:
```bash
mkdir my-project
cd my-project
git init
```

---

## 2. 📄 Check Status of Your Repo

```bash
git status
```

> Shows which files are staged, modified, or untracked.

---

## 3. ✏️ Add Files to Staging Area

```bash
git add <filename>
```
> Stage one file

```bash
git add .
```
> Stage all files in the current directory

---

## 4. 💾 Commit Changes Locally

```bash
git commit -m "Your message"
```

> Saves your changes locally with a message.

### Example:
```bash
git add index.html
git commit -m "Add homepage HTML"
```

---

## 5. 🌐 Connect to Remote Repository (GitHub)

```bash
git remote add origin <repository-url>
```

> Links your local repo to a remote one (usually named `origin`).

### Example:
```bash
git remote add origin https://github.com/yourname/yourrepo.git
```

---

## 6. 🚀 Push Local Commits to Remote

```bash
git push -u origin main
```

> Uploads your commits to the remote repository.  
> `-u` sets the **upstream tracking**, so future pushes can be done with just `git push`.

> Use `main`, `master`, or whatever your default branch is on your remote.

---

## 7. 📥 Pull Latest Changes from Remote

```bash
git pull origin main
```

> Fetches and merges the latest changes from the remote branch into your current branch.

---

## 8. 📦 Clone an Existing Remote Repo

```bash
git clone <repository-url>
```

> Downloads a full copy of the remote repository to your machine.

### Example:
```bash
git clone https://github.com/octocat/Hello-World.git
```

---

## 9. 🌿 Create and Switch Branches

```bash
git branch <branch-name>
```
> Creates a new branch

```bash
git checkout <branch-name>
```
> Switches to a different branch

Or in one command:

```bash
git checkout -b <branch-name>
```

> Creates and switches to a new branch

---

## 10. 🔀 Merge One Branch into Another

```bash
git checkout main
git merge dev
```

> Merges the `dev` branch into `main`.

---

## 11. 🔄 Sync with Remote After Merge

After merging branches locally:

```bash
git push
```

> Pushes merged changes to remote.

---

## 📝 Summary Table: Basic Git Workflow

| Command | Description |
|--------|-------------|
| `git init` | Start a new Git repo |
| `git status` | Show current state |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Commit changes locally |
| `git remote add origin <url>` | Link remote repo |
| `git push -u origin main` | Push first commit |
| `git pull origin main` | Get latest updates |
| `git clone <url>` | Copy remote repo |
| `git checkout -b dev` | Create and switch to `dev` branch |
| `git checkout main && git merge dev` | Merge `dev` into `main` |
| `git push` | Push updated branch to remote |

---

## 🛠 Practice Exercise: Full Git Workflow

Try this step-by-step practice:

### Step 1: Set Up
```bash
mkdir git-basics
cd git-basics
git init
git remote add origin https://github.com/yourname/yourrepo.git
```

### Step 2: Make a File & Commit
```bash
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
```

### Step 3: Push to Remote
```bash
git push -u origin main
```

### Step 4: Create a New Branch
```bash
git checkout -b feature/about
```

### Step 5: Make a Change
```bash
echo "## About Us" >> README.md
git add README.md
git commit -m "Add about section"
git push -u origin feature/about
```

### Step 6: Merge Back to Main
```bash
git checkout main
git pull origin main
git merge feature/about
git push
```

---

## 📎 Bonus Tips

- **Check connected remotes**:  
  ```bash
  git remote -v
  ```

- **See log of commits**:  
  ```bash
  git log
  ```

- **View differences between commits**:  
  ```bash
  git diff
  ```


