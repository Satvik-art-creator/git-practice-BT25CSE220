# Lab Exercise 08: Branch Lifecycle, Documentation & Pruning

> **Objective**: Implement user documentation (`help.txt`) on a dedicated documentation branch (`feature/help`), merge cleanly via `--ff-only`, prune the temporary branch, and inspect the unified commit history.

---

### Step-by-Step Workflow

1. Spawn branch: `git switch -c feature/help`.
2. Write comprehensive user manual in `help.txt` describing menu options and execution steps.
3. Commit documentation updates to the branch.
4. Switch to `main` and enforce a fast-forward merge using `git merge --ff-only feature/help`.
5. Prune merged branch: `git branch -d feature/help`.
6. Inspect the resulting topology using `git log --oneline --graph --all`.

### Key Commands

```bash
git switch -c feature/help
git add help.txt exercise-08/
git commit -m "Add usage instructions and documentation for menu script"

git switch main
git merge --ff-only feature/help
git branch -d feature/help
```

### Artifacts in this Directory

- Documentation source: [`help.txt`](help.txt) (mirrored at root [`help.txt`](../help.txt))
- Full merge & cleanup transcript: [`output.txt`](output.txt)
