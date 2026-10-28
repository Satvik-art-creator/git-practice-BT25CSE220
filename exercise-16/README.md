# Lab Exercise 16: VS Code Graphical Source Control Integration

> **Objective**: Explore Visual Studio Code's native Source Control interface (`Ctrl+Shift+G`), mapping GUI buttons directly to underlying Git CLI operations.

---

### GUI to CLI Operation Mapping

| Visual Studio Code Action | Underlying Git CLI Command | Architectural Operation |
|---|---|---|
| Click `+` on modified file | `git add <file>` | Stages file content into index |
| Click `-` on staged file | `git restore --staged <file>` | Unstages while retaining disk changes |
| Type message & hit `Ctrl+Enter` | `git commit -m "<message>"` | Records snapshot of staged changes |
| Click file under Changes | `git diff` | Opens side-by-side visual diff |
| Click branch name in status bar | `git switch <branch>` / `-c` | Switches or creates a branch pointer |
| Context Menu `...` ➔ Branch ➔ Merge | `git merge <target>` | Merges specified branch into active branch |

- Detailed command equivalence reference recorded in [`output.txt`](output.txt).
