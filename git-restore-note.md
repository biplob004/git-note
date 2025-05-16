
# 🧼 `git restore`: Undo Changes in Working Directory or Staging Area

## 🔍 What is `git restore`?

It's a command used to:
- **Discard changes in the working directory**
- **Unstage files from the staging area**

It’s designed to simplify what previously required confusing uses of `git checkout` and `git reset`.

---

## 📋 Syntax Overview

```bash
git restore <options> <file(s)>
```

---

## 🧹 Common Uses of `git restore`

### ✅ 1. Discard Changes in Working Directory (Back to Last Commit)

```bash
git restore <filename>
```

This reverts the file in your working directory to match the **last committed version** (HEAD), **discarding local edits**.

#### Example:
```bash
echo "Oops, I made a mistake" > index.html
git restore index.html
```

Now `index.html` will have the content from the last commit.

---

### 🚫 2. Unstage a File (Remove from Staging Area)

```bash
git restore --staged <filename>
```

This removes the file from the **staging area**, but keeps your working directory changes.

> This is equivalent to: `git reset HEAD <filename>`

#### Example:
```bash
git add index.html
git restore --staged index.html
```

Now `index.html` is no longer staged, but still exists with your changes.

---

### 💥 3. Discard Changes in Working Directory AND Unstage

If you want to completely discard all changes and unstage:

```bash
git restore --staged --worktree <filename>
```

Or simply:

```bash
git restore -s -w <filename>
```

> `-s` = `--staged`, `-w` = `--worktree`

---

### 📁 4. Restore a File from a Specific Commit

You can restore a file as it was in a previous commit:

```bash
git restore --source=<commit-hash> <filename>
```

#### Example:
```bash
git restore --source=abc1234 index.html
```

This replaces the current `index.html` with the version from commit `abc1234`.

---

## 🧩 Bonus Tip: Restore Multiple Files or All Files

To restore multiple files:

```bash
git restore file1.txt file2.txt
```

To restore all files:

```bash
git restore .
```

Or to unstage all files:

```bash
git restore --staged .
```

---

## 🆚 Comparison: `git reset` vs `git restore`

| Task | `git reset` | `git restore` |
|------|-------------|----------------|
| Discard changes in working directory | ❌ Not recommended | ✅ `git restore <file>` |
| Unstage a file | ✅ `git reset HEAD <file>` | ✅ `git restore --staged <file>` |
| Restore file from another commit | ✅ `git checkout <hash> <file>` | ✅ `git restore --source=<hash> <file>` |
| Clear intent | ❗ Can be confusing | ✅ More readable & specific |

So, `git restore` is preferred when you just want to **discard changes** or **unstage files**.

---

## 🛠 Practice Exercise

Let’s try a hands-on example:

### Step-by-step:

```bash
mkdir git-restore-demo
cd git-restore-demo
git init

echo "Hello World" > hello.txt
git add .
git commit -m "First commit"

echo "Some change" >> hello.txt
git add hello.txt
git restore --staged hello.txt   # Unstage the file

git restore hello.txt            # Discard local changes

git status                       # Should show nothing staged or modified
```

Try different combinations!

---

## 📝 Summary Table

| Command | Effect |
|--------|--------|
| `git restore <file>` | Discards changes in working directory |
| `git restore --staged <file>` | Unstages the file |
| `git restore --staged --worktree <file>` | Unstage + discard changes |
| `git restore --source=<hash> <file>` | Restore file from a specific commit |
| `git restore .` | Restore all files in working directory |
| `git restore --staged .` | Unstage all files |

---

## 🎯 When to Use `git restore`?

Use `git restore` when you want to:
- **Throw away local changes**
- **Unstage files before committing**
- **Restore older versions of files**

Avoid using it if you need to:
- **Rewrite history** (use `git reset`)
- **Revert an already-pushed commit** (use `git revert`)
