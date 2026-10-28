# Lab Exercise 15: Safe Remote Synchronization via Fetch & FF-Pull

> **Objective**: Decouple remote download from local integration using `git fetch`, inspect incoming commits with revision ranges, and safely integrate upstream updates via `git pull --ff-only`.

---

### Two-Step Safe Pull Workflow

```
1. Download objects:      git fetch origin
                                │
2. Inspect log range:     git log --oneline main..origin/main
                                │
3. Integrate safely:      git pull --ff-only origin main
```

### Why Use `--ff-only`?

Executing a bare `git pull` risks creating unintended merge commits if the local branch has diverged unexpectedly. Using `--ff-only` guarantees that Git fast-forwards the pointer or fails with an explicit notification, preserving linear project history.

- Full terminal transcript recorded in [`output.txt`](output.txt).
