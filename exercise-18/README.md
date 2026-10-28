# Lab Exercise 18: Release Tagging & Production Milestones

> **Objective**: Perform pre-release script verification, create an annotated release tag (`v1.0`) with cryptographic authorship details, and publish the release pointer to the remote repository.

---

### Step-by-Step Workflow

1. Execute test runs for all interactive utilities (`greet.sh`, `menu.sh`) to confirm stability.
2. Mint an annotated Git tag with full release notes:
   ```bash
   git tag -a v1.0 -m "Release version 1.0 - All lab exercises verified"
   ```
3. Inspect tag object metadata and commit association:
   ```bash
   git show v1.0
   ```
4. Push tag object to GitHub remote:
   ```bash
   git push origin v1.0
   ```

- Terminal execution evidence and tag output in [`output.txt`](output.txt).
