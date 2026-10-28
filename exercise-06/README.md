# Lab Exercise 06: Ignore Rules & Artifact Exclusion

> **Objective**: Configure `.gitignore` to prevent transient build artifacts, debug loggers, swap files, and secret environment configurations from contaminating repository history.

---

### Configured Pattern Rules

| Rule Pattern | Description / Targeted Files |
|---|---|
| `*.log` | Runtime execution logs (e.g., `app.log`) |
| `*.tmp` | Temporary swap and cache dumps (e.g., `temp_data.tmp`) |
| `build/` | Compiled binary output directories (e.g., `build/output.bin`) |
| `.env` | Local secrets, API credentials, and runtime flags |

### Testing with `git check-ignore`

```bash
# Debug pattern matches
git check-ignore -v app.log
git check-ignore -v temp_data.tmp
git check-ignore -v build/output.bin
git check-ignore -v .env
```

### Lab Findings & Results

- All four target patterns correctly identified and discarded from untracked status.
- Configured file: [`.gitignore`](.gitignore) (mirrored at root [`.gitignore`](../.gitignore)).
- Test results documented in [`output.txt`](output.txt).
