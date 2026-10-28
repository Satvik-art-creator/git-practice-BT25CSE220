# Lab Exercise 09: Three-Way Merge Conflict Simulation & Manual Resolution

> **Objective**: Stage a deterministic merge conflict on `mode.txt` between `main` and a divergent branch, analyze standard conflict markers, and execute a verified hybrid resolution commit.

---

### Conflict Mechanics

```
Base Commit (C0):
"Lab mode: pending"
        │
        ├───> main (C1):           "Lab mode: classroom"
        │
        └───> feature/mode (C2):   "Lab mode: online"
```

When attempting to merge `feature/mode` into `main`, Git encounters conflicting modifications on the exact same line.

### Conflict Marker Anatomy

```text
<<<<<<< HEAD
Lab mode: classroom
=======
Lab mode: online
>>>>>>> feature/mode
```

- `<<<<<<< HEAD` denotes current branch changes (`classroom`).
- `=======` marks the division boundary.
- `>>>>>>> feature/mode` marks incoming branch changes (`online`).

### Resolution Procedure

1. Open `mode.txt` and replace conflicting lines with agreed consensus: `Lab mode: hybrid`.
2. Stage file: `git add mode.txt`.
3. Commit merge: `git commit -m "Resolve merge conflict in mode.txt with hybrid delivery mode"`.
4. Delete branch: `git branch -d feature/mode`.

### Artifacts in this Directory

- Final resolved file: [`mode.txt`](mode.txt) (mirrored at root [`mode.txt`](../mode.txt))
- Step-by-step logs: [`output.txt`](output.txt)
