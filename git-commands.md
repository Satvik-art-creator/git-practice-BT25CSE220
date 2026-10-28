# Git Command Reference Manual & Conflict Resolution Log

```
Student       : Satvik Rastogi
Roll Number   : BT25CSE220
Section       : CSE - C
Course        : IT Workshop - I (CSP 201)
Institution   : Indian Institute of Information Technology, Nagpur
Academic Year : 2026–2027 (Semester III)
```

---

## Overview

This document serves as an exhaustive command reference and technical log for the 19 practical exercises completed during the Git Version Control laboratory. It details the operational mechanics, key flags, real-world utility of each command, followed by an in-depth case study of the merge conflict produced and resolved during Exercise 09.

---

## 1. Git Command Reference Directory

### Part I: Environment Setup & Local Configuration

| Command | Key Flags | Practical Purpose & Lab Context |
|---|---|---|
| `git --version` | *None* | Verifies Git binary presence and confirms version compatibility (detected `git version 2.55.0.windows.5`). |
| `git config` | `--global`, `--local`, `--get` | Configures repository identity. Used `--local` to assign `user.name "Satvik Rastogi"` and `user.email "satvik.rastogi@example.com"`. |
| `git init` | `-b <initial_branch>` | Initializes the `.git` directory structure. Initialized with `-b main` to avoid outdated default branch conventions. |

> **Key Rule**: Local configuration (`.git/config`) overrides global settings (`~/.gitconfig`), ensuring work from this repository attributes properly to university credentials.

---

### Part II: The Two-Stage Commit Pipeline (Working Tree ➔ Index ➔ HEAD)

| Command | Syntax / Flags | What It Does Under the Hood |
|---|---|---|
| `git status` | `-s`, `--short` | Queries current working directory state against the staging index. Summarizes untracked (`??`), staged (`A `), unstaged edits (` M`), and both-modified (`MM`). |
| `git add` | `<pathspec>`, `.` | Moves content snapshots from the working tree into the staging area (index), preparing changes for commit. |
| `git commit` | `-m "<message>"` | Freezes the staged index into a persistent commit object with author info, timestamp, parent pointer, and cryptographic SHA-1/SHA-256 hash. |
| `git diff` | *None* | Compares unstaged modifications in the working tree directly against the index. |
| `git diff` | `--staged` / `--cached` | Evaluates differences between the current staged changes in the index and the latest commit (`HEAD`). |
| `git diff` | `HEAD` | Comprehensive diff showing all combined modifications (staged + unstaged) relative to `HEAD`. |

---

### Part III: Exclusion & Pattern Filtering

| Mechanism | Command / File | Application |
|---|---|---|
| Pattern File | `.gitignore` | Lists globbing patterns for files Git must ignore (e.g., `*.log`, `*.tmp`, `build/`, `.env`). |
| Pattern Debugging | `git check-ignore -v <target>` | Troubleshoots which line in `.gitignore` causes a file to be omitted. |
| Untrack Staged File | `git rm --cached <target>` | Strips files out of the staging index while safely keeping them on the physical filesystem. |

---

### Part IV: Branch Operations, Merging & Topology Inspection

| Command | Arguments | Operation & Mechanics |
|---|---|---|
| `git branch` | *None*, `-d <name>` | Lists local branches or safely removes a merged branch (`-d`). |
| `git switch` | `-c <branch_name>` | Modern alternative to `git checkout -b`. Creates a branch pointer and switches `HEAD` to point to it. |
| `git switch` | `<branch_name>` | Updates the working tree to the state of the target branch. |
| `git merge` | `<branch_name>` | Integrates changes from the target branch into the currently checked-out branch. |
| `git merge` | `--ff-only <branch_name>` | Performs a fast-forward pointer update only. Refuses execution if divergence necessitates a merge commit. |
| `git log` | `--oneline --graph --all` | Produces an ASCII visualization of branch lineages, diverged histories, and merge commits. |

---

### Part V: Recovery, Rollbacks & Stash Operations

| Command | Usage | Safety Profile & Behavior |
|---|---|---|
| `git restore --staged` | `<file>` | **Safe**: Copies version from HEAD into index; does not overwrite file edits in the working tree. |
| `git restore` | `<file>` | **Destructive**: Overwrites local unstaged file changes with index content. Discarded edits cannot be undone. |
| `git revert` | `[--no-edit] <hash>` | **Safe & History-Preserving**: Generates a forward-moving commit that applies the inverse diff of the target commit. Essential for shared branches. |
| `git stash push` | `-m "<message>"` | Saves dirty state (working tree and index) onto the LIFO stash stack and reverts to a clean HEAD state. |
| `git stash pop` | *None* | Restores the top stashed patchset back to the working tree and prunes it from the stash stack. |
| `git stash list` | *None* | Displays all active stashes in storage (`stash@{0}`, etc.). |

---

### Part VI: Remote Repository Interaction & Distributed Workflows

| Command | Arguments | Operational Function |
|---|---|---|
| `git remote` | `add <name> <url>`, `-v` | Links a local repository to a remote server endpoint and lists configured fetch/push addresses. |
| `git push` | `-u <remote> <branch>` | Uploads commits to the remote and registers an upstream tracking relationship for subsequent streamlined `git push`/`git pull`. |
| `git clone` | `<url> [target_dir]` | Clones an entire remote repository: pulls all commits, historical branches, and creates a local tracking branch. |
| `git fetch` | `<remote>` | Updates remote-tracking pointers (`origin/main`) and downloads objects without touching working tree files. |
| `git log` | `<branch>..<remote>/<branch>` | Visualizes incoming commits that exist on the remote branch but haven't been merged locally yet. |
| `git pull` | `--ff-only <remote> <branch>` | Combines `git fetch` + `git merge --ff-only` to guarantee divergence-free remote updates. |

---

### Part VII: Tagging & Release Verification

| Command | Arguments | Function |
|---|---|---|
| `git tag` | `-a <tag_name> -m "<annotation>"` | Generates an annotated release tag object with creator signature, timestamp, and message. |
| `git show` | `<tag_name>` | Displays tag metadata, tagger credentials, and the attached commit snapshot. |
| `git push` | `<remote> <tag_name>` | Explicitly synchronizes the created tag ref to remote storage. |

---

## 2. Merge Conflict Case Study & Resolution Record (Exercise 09)

### 2.1 The Conflict Scenario

A deliberate merge conflict was staged on the file `mode.txt` to master Git's three-way resolution process:

1. **Base Commit on `main`**:
   ```
   Lab mode: pending
   ```
2. **Feature Branch (`feature/mode`)**:
   - Branched off from base.
   - Updated content:
     ```
     Lab mode: online
     ```
   - Committed with: `"Set lab delivery mode to online"`.
3. **Simultaneous Divergence on `main`**:
   - Switched back to `main`.
   - Updated the identical line:
     ```
     Lab mode: classroom
     ```
   - Committed with: `"Set lab delivery mode to classroom"`.

When executing `git merge feature/mode` while on `main`, Git detected conflicting updates to the exact same line originating from the common ancestor. The automatic merge was suspended.

---

### 2.2 Conflict Output & Inspection

Git signaled the conflict in terminal and updated `mode.txt` with standard conflict markers:

```text
<<<<<<< HEAD
Lab mode: classroom
=======
Lab mode: online
>>>>>>> feature/mode
```

- **`<<<<<<< HEAD`**: Start of current branch content (`main`).
- **`=======`**: Boundary separating divergent changes.
- **`>>>>>>> feature/mode`**: End of incoming branch content.
- **Index State**: `git status` flagged `mode.txt` as `both modified` (`UU`).

---

### 2.3 Step-by-Step Resolution Walkthrough

1. **Evaluation**:
   The team agreed upon a unified delivery model: blending physical campus labs with remote virtual participation.
2. **Manual Reconciliation**:
   All marker lines (`<<<<<<<`, `=======`, `>>>>>>>`) were deleted and replaced with the consolidated consensus text:
   ```text
   Lab mode: hybrid
   ```
3. **Marking Resolved**:
   ```bash
   git add mode.txt
   ```
   Staging `mode.txt` informed Git's index that conflict reconciliation was complete.
4. **Finalizing the Merge**:
   ```bash
   git commit -m "Resolve merge conflict in mode.txt with hybrid delivery mode"
   ```
   This created a two-parent merge commit integrating the histories of both branches.
5. **Clean-up & Graph Inspection**:
   - `git branch -d feature/mode` was executed safely.
   - `git log --oneline --graph` verified the converged branch structure.
