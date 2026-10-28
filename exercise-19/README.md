# Lab Exercise 19: Non-Fast-Forward Push Rejection Handling

> **Objective**: Handle concurrent remote branch divergence causing a non-fast-forward push rejection, inspect history using branch graph logs, and safely reconcile without destructive force-pushing.

---

### Challenge Scenario & Root Cause

```
Remote origin/main:   C0 ────> C_A (pushed by Collaborator A)
                                ▲
Local main:           C0 ────> C_B (committed by Collaborator B)
```

When Collaborator B runs `git push origin main`, Git rejects the push with:
```
! [rejected]        main -> main (fetch first)
error: failed to push some refs ...
hint: Updates were rejected because the remote contains work that you do not have locally.
```

### The 4-Step Professional Recovery Process

```bash
# Step 1: Download upstream commits without overwriting local files
git fetch origin

# Step 2: Visualize topology divergence
git log --oneline --graph --all

# Step 3: Reconcile diverged branches via three-way merge
git merge origin/main

# Step 4: Complete clean push with combined history
git push origin main
```

> **Critical Safety Note**: Never use `git push --force` or `--force-with-lease` on shared public branches, as this silently deletes teammates' work. Always reconcile through `fetch` followed by `merge` or `rebase`.

- Full step-by-step transcript captured in [`output.txt`](output.txt).
