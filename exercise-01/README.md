# Exercise 01: Configure Git

## Objective
Verify Git installation and set repository-local user identity (name and email), then verify the configured values.

## Commands Executed
```bash
git --version
git config user.name "Satvik Rastogi"
git config user.email "satvik.rastogi@example.com"
git config --get user.name
git config --get user.email
```

## Observation & Output
Git version 2.55.0.windows.5 was detected. The local configuration parameters `user.name` and `user.email` were successfully saved into `.git/config` and retrieved.
