# Lab Exercise 03: Script Development & Defensive Validation

> **Objective**: Implement a POSIX Bash interactive greeting script (`greet.sh`), establish an initial commit, and incrementally enhance it with input validation for blank strings.

---

### Step-by-Step Workflow

1. Create `greet.sh` prompting the user for an interactive string input.
2. Commit the base version into version control history.
3. Enhance the script with an empty-input boundary check (`-z "$name"`), returning an informative error and exit code `1`.
4. Create a secondary, focused commit capturing the defensive validation fix.

### Script Execution & Testing

```bash
# Executing script with valid input
./greet.sh
# Input: Satvik -> Output: Hello, Satvik! Welcome to Git Version Control Lab.

# Testing validation guard
./greet.sh
# Input: [Enter] -> Output: Error: Name cannot be empty! Please provide a valid name.
```

### Artifacts in this Directory

- Script implementation: [`greet.sh`](greet.sh) (also mirrored at root [`greet.sh`](../greet.sh))
- Test input vectors: [`sample_input.txt`](sample_input.txt)
- Execution log and commit trail: [`output.txt`](output.txt)
