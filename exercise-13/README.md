# Lab Exercise 13: Remote Origin Publishing & Independent Cloning

> **Objective**: Bind the local workspace to a remote GitHub upstream endpoint (`origin`), push the primary branch with upstream tracking (`-u`), and verify distributed cloning from another directory.

---

### Step-by-Step Workflow

1. Register remote repository URL:
   ```bash
   git remote add origin https://github.com/satvikrastogi/git-practice-BT25CSE220.git
   git remote -v
   ```
2. Push commits and establish upstream tracking:
   ```bash
   git push -u origin main
   ```
3. Simulate peer collaborator by executing a clean clone into a distinct directory:
   ```bash
   git clone https://github.com/satvikrastogi/git-practice-BT25CSE220.git git-practice-clone
   ```
4. Verify complete commit history integrity within the clone.

- Full command logs documented in [`output.txt`](output.txt).
