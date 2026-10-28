# Lab Exercise 07: Feature Branch Isolation & Interactive CLI Utility

> **Objective**: Create an isolated feature branch (`feature/menu`), develop a modular interactive arithmetic menu script (`menu.sh`), validate each option, and merge it back into `main`.

---

### Step-by-Step Workflow

1. Spin up a new branch: `git switch -c feature/menu`.
2. Construct `menu.sh` supporting 4 operations:
   - **Option 1**: Personalized greeting with fallback default (`Student`).
   - **Option 2**: Two-integer addition with regex input validation (`^-?[0-9]+$`).
   - **Option 3**: Integer parity calculation (Even vs Odd).
   - **Option 4**: Clean exit.
3. Verify all options thoroughly with interactive input.
4. Commit changes on the feature branch.
5. Return to `main` and execute a fast-forward merge.

### Execution Record

```bash
# Branch creation and switch
git switch -c feature/menu

# Execute menu utility
./menu.sh

# Commit and integrate
git add menu.sh
git commit -m "Implement interactive arithmetic and utility menu script"
git switch main
git merge feature/menu
```

### Artifacts in this Directory

- Script source: [`menu.sh`](menu.sh) (mirrored at root [`menu.sh`](../menu.sh))
- Sample inputs: [`sample_input.txt`](sample_input.txt)
- Terminal execution logs: [`output.txt`](output.txt)
