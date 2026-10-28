# Contributor Handbook & Collaboration Standard

Welcome to the **Git Version Control Lab** repository (`git-practice-BT25CSE220`).  
Please follow these engineering practices when proposing changes or submitting pull requests:

---

## 1. Branching Protocol

- Never commit untested changes directly to `main`.
- Branch naming convention:
  - `feature/<name>` for new functionality or scripts
  - `docs/<name>` for documentation updates
  - `fix/<name>` for bug fixes or edge-case handling

```bash
# Branch creation example
git switch -c feature/menu-enhancement
```

---

## 2. Commit Message Rules

- Use the present-tense imperative style (e.g., `Add input validation to greet.sh`).
- Keep the first line under 72 characters.
- Avoid vague messages like `update file` or `fixed stuff`.

---

## 3. Pull Request & Review Standards

1. Push your branch to the remote: `git push -u origin <branch-name>`.
2. Open a Pull Request on GitHub against `main`.
3. Provide a concise description of the motivation and execution evidence.
4. Request review from at least one lab peer before merging.
5. Merge using fast-forward when linear history is desired.

---

## 4. Script Quality & Verification

All shell scripts must:
- Include a shebang line (`#!/bin/bash`).
- Be executable (`chmod +x <script>.sh`).
- Handle empty or non-numeric arguments gracefully with informative error messages.

---

## Peer Review Checklist (Exercise 14)

Before signing off on any PR:
- [x] Shell scripts tested across positive and negative edge cases in Git Bash
- [x] Commit history is clean, descriptive, and atomic
- [x] No secrets, private credentials, or runtime artifacts (`.env`, `*.log`, `build/`) included
- [x] Documentation and sample outputs accurately updated
