# Lab Exercise 11: History-Preserving Undo via `git revert`

> **Objective**: Reverse the effects of a prior commit safely using `git revert`, ensuring a forward-moving audit trail suitable for public collaborative branches without rewriting history.

---

### Key Difference: `git revert` vs `git reset`

| Characteristic | `git revert` | `git reset` |
|---|---|---|
| **Mechanism** | Creates a new inverse commit | Moves branch pointer backwards |
| **History Effect** | Preserves all previous commits | Erases or alters public history |
| **Collaboration** | Safe for shared remotes (`main`) | Dangerous; requires forced push |

### Execution Workflow

1. Identify offending commit hash via `git log --oneline`.
2. Apply `git revert --no-edit <commit_hash>`.
3. Inspect commit tree to verify that both the original commit and the revert commit exist in the audit log.

- Detailed output recorded in [`output.txt`](output.txt).
