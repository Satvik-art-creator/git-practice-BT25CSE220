# Lab Exercise 01: Environment Configuration & Identity Setup

> **Objective**: Validate the Git installation environment and configure local repository credentials for author attribution.

---

### Step-by-Step Workflow

1. Query system environment to ensure Git is accessible via the terminal.
2. Bind local user details (`name` and `email`) specifically to this repository scope.
3. Confirm parameter retention via configuration queries.

### Terminal Commands

```bash
# Check version
git --version

# Set repository-level identity
git config user.name "Satvik Rastogi"
git config user.email "satvik.rastogi@example.com"

# Validate configuration
git config --get user.name
git config --get user.email
```

### Lab Findings & Results

- Active binary: `git version 2.55.0.windows.5`.
- Stored local identity within `.git/config` preventing global gitconfig leakage.
- Execution logs recorded in [`output.txt`](output.txt).
