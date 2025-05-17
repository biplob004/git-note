

## Git Essentials: Amending, History, and Stashing

This note covers some useful Git commands for managing your commit history, handling untracked files, and temporarily saving your work.

### Amending Your Last Commit

Need to fix a typo in your last commit message or add/remove a file you forgot? Use `git commit --amend`. This command doesn't create a new commit on top; instead, it rewrites the most recent commit.

  * **Edit commit message:** If you want to change the commit message, use:
    ```bash
    git commit --amend -m "Your new, improved commit message"
    ```
  * **Fix code/add files and keep the current message:** If you've made changes (staged them with `git add`) and want to include them in the last commit without changing the message:
    ```bash
    git commit --amend --no-edit
    ```
    **Important:** Amending rewrites history. If you've already pushed the commit you're amending, you'll need to use `git push --force` (or `git push --force-with-lease`), which can be disruptive for collaborators. Use with caution on shared branches.

-----

### Viewing All Commit History

To see a complete history of your Git repository, including commits that might have been "hidden" by operations like `git commit --amend`, use `git reflog`:

```bash
git reflog
```

This command shows a log of where your `HEAD` has been, making it invaluable for recovering lost commits or understanding your repository's movement.

-----

### Git Garbage Collection

Over time, your Git repository can accumulate unused objects. `git gc` (garbage collect) helps clean up unnecessary files and optimize your repository's size:

```bash
git gc
```

This command is usually run automatically by Git, but you can run it manually if you notice your repository growing unusually large.

-----

### Staging and Committing in One Go

For quickly committing changes to **already tracked files**, you can combine staging and committing into one command:

```bash
git commit -a -m "Your concise commit message"
```

The `-a` flag automatically stages all changes to files that Git is already tracking. This command **will not** stage new, untracked files.

-----

### Filtering `git status`

Sometimes you only want to see changes to tracked files, ignoring new, untracked ones. Use these options with `git status`:

```bash
git status --untracked-files=no
# Or the shorthand:
git status -uno
```

This can help keep your `git status` output cleaner when you have many temporary or new files.

-----

### Git Stash: Temporarily Saving Work

`git stash` is a lifesaver when you need to switch branches or pull updates but aren't ready to commit your current work. It takes your uncommitted changes (both staged and unstaged for **tracked files**) and saves them in a temporary "stash" area, reverting your working directory to a clean state.

  * **Stash your changes:**
    ```bash
    git stash
    ```
    This saves your changes and cleans your working directory.
  * **View your stashes:**
    ```bash
    git stash list
    ```
    This shows a list of all your saved stashes.
  * **Apply the most recent stash:**
    ```bash
    git stash apply
    ```
    This applies the changes from the most recent stash, leaving the stash in the list.
  * **Apply a specific stash:**
    ```bash
    git stash apply stash@{<id>}
    ```
    Replace `<id>` with the index from `git stash list` (e.g., `git stash apply stash@{2}`).
  * **Apply and remove the most recent stash:**
    ```bash
    git stash pop
    ```
    This applies the changes from the most recent stash and then removes it from the list.
  * **Apply and remove a specific stash:**
    ```bash
    git stash pop stash@{<id>}
    ```
  * **Clear all stashes:**
    ```bash
    git stash clear
    ```
    Use with caution, as this removes all your saved stashes permanently.



---

| Task                                  | Command                    |
| ------------------------------------- | -------------------------- |
| Undo a commit, keep changes staged    | `git reset --soft HEAD~1`  |
| Undo a commit, keep changes unstaged  | `git reset --mixed HEAD~1` |
| Undo a commit and discard all changes | `git reset --hard HEAD~1`  |
