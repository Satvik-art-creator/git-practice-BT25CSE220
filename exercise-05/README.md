# Lab Exercise 05: Three-Tier State Inspection & Diff Analysis

> **Objective**: Explore Git's internal architecture across Working Tree, Index (Staging), and Commit (HEAD) by producing a concurrent `MM` state and analyzing targeted diff outputs.

---

### Understanding the Three-Tier Architecture

```
+------------------+         git add         +------------------+        git commit        +------------------+
|   Working Tree   |  ────────────────────>  |   Index/Stage    |  ─────────────────────>  |       HEAD       |
| (Unstaged edits) |                         |  (Staged edits)  |                          | (Latest snapshot)|
+------------------+                         +------------------+                          +------------------+
        │                                             ▲                                             ▲
        │─────────────────── git diff ────────────────│                                             │
        │                                                                                           │
        │─────────────────────────────── git diff --staged ─────────────────────────────────────────│
        │                                                                                           │
        │──────────────────────────────────── git diff HEAD ────────────────────────────────────────┘
```

### Step-by-Step Workflow

1. Modify `README.md` and stage the alteration using `git add`.
2. Introduce an additional modification to `README.md` without staging it.
3. Observe the `MM` indicator in `git status --short`.
4. Contrast the three diff perspectives:
   - `git diff`: Working Tree vs Index
   - `git diff --staged`: Index vs HEAD
   - `git diff HEAD`: Working Tree vs HEAD

### Verification

- Command outputs and exact patch diffs documented in [`output.txt`](output.txt).
