# Lab Exercise 04: Controlled Staging & Untracked File Isolation

> **Objective**: Master granular staging by selectively adding specific files to the index while preserving untracked candidate files in the working directory.

---

### Step-by-Step Workflow

1. Generate two distinct data files: `file_alpha.txt` and `file_beta.txt`.
2. Inspect `git status --short` to see both marked as untracked (`??`).
3. Stage only `file_alpha.txt` (`A `), ensuring `file_beta.txt` remains untracked.
4. Commit `file_alpha.txt`, verify repository status, then stage and commit `file_beta.txt` in a separate atomic transaction.

### Terminal Commands

```bash
# Verify both are untracked
git status --short

# Selectively stage alpha only
git add exercise-04/file_alpha.txt
git commit -m "Add first dataset file (file_alpha.txt)"

# Stage and commit beta subsequently
git add exercise-04/file_beta.txt
git commit -m "Add second dataset file (file_beta.txt)"
```

### Lab Findings & Results

- Verified that Git does not commit everything in the folder by default; staging is explicit.
- Both data files are tracked across independent commits: [`file_alpha.txt`](file_alpha.txt) and [`file_beta.txt`](file_beta.txt).
- Status transitions documented in [`output.txt`](output.txt).
