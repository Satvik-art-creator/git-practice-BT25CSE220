# git-practice-BT25CSE220

> IT Workshop – I Lab Assignment | IIIT Nagpur | Semester 3 (2026–27)

---

**Satvik Rastogi** · Roll No. `BT25CSE220` · Section CSE-C  
🔗 GitHub → [satvikrastogi/git-practice-BT25CSE220](https://github.com/satvikrastogi/git-practice-BT25CSE220)

---

## What this repo is about

This is my hands-on Git lab record for IT Workshop – I. Over 19 exercises I worked through everything from the very basics of `git init` right up to handling tricky push rejections and tagging a release. The goal was to get comfortable with Git the way it's actually used — not just memorising commands, but understanding *why* each one exists.

Topics covered across the exercises:

- **Foundations** — repo setup, staging index, atomic commits, reading diffs
- **Ignoring noise** — `.gitignore` patterns for logs, build artifacts, secrets
- **Branching & merging** — fast-forward, three-way merges, feature branches
- **Conflict resolution** — reproducing, reading markers, and resolving manually
- **Undo toolkit** — `restore`, `restore --staged`, `revert`, `stash`
- **Collaboration** — remote tracking, clone, fetch, pull, push, non-ff rejection
- **VS Code integration** — Source Control view, 3-way Merge Editor
- **Releases** — annotated tags and pushing them to remote

---

## Exercise Index

| # | What I did | Folder |
|---|---|---|
| 01 | Git install check + identity setup | [exercise-01/](exercise-01/) |
| 02 | Init repo, first commit, project README | [exercise-02/](exercise-02/) |
| 03 | `greet.sh` — prompt script with empty-input guard | [exercise-03/](exercise-03/) |
| 04 | Stage one file, leave another untracked intentionally | [exercise-04/](exercise-04/) |
| 05 | `MM` state — diff working tree vs index vs HEAD | [exercise-05/](exercise-05/) |
| 06 | `.gitignore` — keep logs, tmp, build dirs, `.env` out | [exercise-06/](exercise-06/) |
| 07 | `menu.sh` built on a feature branch, merged to main | [exercise-07/](exercise-07/) |
| 08 | `feature/help` branch → fast-forward merge → delete branch | [exercise-08/](exercise-08/) |
| 09 | Intentional conflict in `mode.txt` → resolved to `hybrid` | [exercise-09/](exercise-09/) |
| 10 | `git restore --staged` and `git restore` recovery workflow | [exercise-10/](exercise-10/) |
| 11 | `git revert` — undo without destroying history | [exercise-11/](exercise-11/) |
| 12 | `git stash push / pop` — shelve WIP, fix, resume | [exercise-12/](exercise-12/) |
| 13 | Push to remote origin, verify with a fresh clone | [exercise-13/](exercise-13/) |
| 14 | Feature branch PR + `CONTRIBUTING.md` peer review flow | [exercise-14/](exercise-14/) |
| 15 | `git fetch` → inspect log range → `git pull --ff-only` | [exercise-15/](exercise-15/) |
| 16 | VS Code Source Control panel mapped to CLI equivalents | [exercise-16/](exercise-16/) |
| 17 | Merge conflict resolved visually inside VS Code | [exercise-17/](exercise-17/) |
| 18 | Annotated tag `v1.0` created and pushed | [exercise-18/](exercise-18/) |
| 19 | Non-fast-forward rejection → fetch → merge → clean push | [exercise-19/](exercise-19/) |

All 19 exercises completed ✓

---

## Running the scripts

> Requires **Git Bash** on Windows, or any POSIX terminal on Linux / macOS.  
> Git 2.23 or newer recommended.

### `greet.sh` — Exercise 03

```bash
chmod +x greet.sh
./greet.sh
```

Sample runs:

```
Enter your name: Satvik
Hello, Satvik! Welcome to Git Version Control Lab.

Enter your name:
Error: Name cannot be empty! Please provide a valid name.
```

### `menu.sh` — Exercise 07

```bash
chmod +x menu.sh
./menu.sh
```

Four options inside the menu:

| Option | What it does |
|---|---|
| 1 – Greet User | Asks for a name, prints a welcome line |
| 2 – Add Two Integers | Takes two numbers, returns the sum |
| 3 – Check Even / Odd | Tells you the parity of an integer |
| 4 – Exit | Quits cleanly |

---

## GitHub Activity

### Issues

| # | Title | Status |
|---|---|---|
| [#1](https://github.com/satvikrastogi/git-practice-BT25CSE220/issues/1) | Add input validation to greeting script | Closed — fixed in commit `3b8d1e2` |
| [#2](https://github.com/satvikrastogi/git-practice-BT25CSE220/issues/2) | Implement interactive CLI menu utility | Closed — completed via `feature/menu` |

### Pull Requests

| # | Title | Branch flow | Outcome |
|---|---|---|---|
| [#3](https://github.com/satvikrastogi/git-practice-BT25CSE220/pull/3) | Feature: arithmetic & utility menu | `feature/menu-enhancement` → `main` | Merged (fast-forward) |
| [#4](https://github.com/satvikrastogi/git-practice-BT25CSE220/pull/4) | Docs: peer review checklist in CONTRIBUTING | `feature/collaboration-docs` → `main` | Merged after peer review |

---
