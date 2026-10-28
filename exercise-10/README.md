# Lab Exercise 10: Safe Working Tree & Staging Index Recovery

> **Objective**: Practice Git's non-destructive rollback operations to unstage files from the index and discard unwanted working tree modifications safely.

---

### Recovery Workflows

```
Working Tree (Dirty)  ◄─── git restore <file> ───  Index (Clean)
        │                                                ▲
        └─────────────── git restore --staged <file> ────┘
```

1. **Unstaging Changes (`git restore --staged <file>`)**:
   - Removes files from the staging index back to unstaged working tree.
   - Preserves all file modifications on disk.
2. **Discarding Working Tree Edits (`git restore <file>`)**:
   - Reverts modified file in working tree back to index/HEAD state.
   - Cleans working directory back to a pristine state.

### Verification Commands

```bash
# Stage edit
git add README.md
git status --short # M  README.md

# Unstage
git restore --staged README.md
git status --short #  M README.md

# Discard
git restore README.md
git status --short # Clean working tree
```

- Detailed terminal output recorded in [`output.txt`](output.txt).
