# Lab Exercise 02: Repository Bootstrap & Initial Snapshot

> **Objective**: Initialize an empty Git version-controlled workspace using the `main` branch convention and anchor the root documentation commit.

---

### Step-by-Step Workflow

1. Initialize repository with explicit primary branch identifier (`-b main`).
2. Draft root-level `README.md` defining project metadata, student info, and assignment scope.
3. Stage the file into Git's index and record the initial repository commit.

### Terminal Commands

```bash
# Initialize repo with primary branch set to main
git init -b main

# Stage documentation
git add README.md

# Commit initial snapshot
git commit -m "Initialize project repository with README"

# Verify repository log and status
git status
git log --oneline
```

### Lab Findings & Results

- Clean repository initialized at `D:/bt25cse220/BT25CSE220_lab_assignment/.git/`.
- Root commit successfully registered with clean working tree.
- Full output logged in [`output.txt`](output.txt).
