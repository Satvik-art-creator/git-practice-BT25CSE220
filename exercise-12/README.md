# Lab Exercise 12: Work-in-Progress Preservation with `git stash`

> **Objective**: Temporarily shelve uncommitted dirty working-tree changes using `git stash push`, verify a pristine working directory to allow context switching or emergency fixes, and subsequently reapply stashed edits via `git stash pop`.

---

### Step-by-Step Workflow

1. Introduce unfinished modifications to `README.md`.
2. Inspect `git status --short` to confirm dirty state (` M`).
3. Shelve changes to the LIFO stash stack:
   ```bash
   git stash push -m "WIP: new feature notes"
   ```
4. Confirm working directory is clean (`nothing to commit, working tree clean`).
5. Query stored stashes with `git stash list`.
6. Restore uncommitted changes and pop the stash:
   ```bash
   git stash pop
   ```

- Full terminal transcript preserved in [`output.txt`](output.txt).
