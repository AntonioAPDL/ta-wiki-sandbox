# Quickstart

This page gets you ready for the lab in the shortest, clearest path.

## 1) Verify Git
Why: if Git is not installed, the rest of the steps will fail.

```bash
git --version
```

## 2) Set your Git identity (one time)
Why: Git records who made each commit, and that name shows in the PR.

```bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR@EMAIL"
```

## 3) Authentication (HTTPS + PAT)
GitHub no longer accepts account passwords for Git operations over HTTPS. When Git prompts for a password, paste a personal access token (PAT) instead.

Minimal steps to create a PAT:
1) GitHub -> Settings -> Developer settings -> Personal access tokens.
2) Create a token (classic or fine-grained) with access to this repo.
3) Copy the token and treat it like a password.

## If you get stuck, paste this
Include this bundle when asking for help so we can diagnose quickly:
- Exact error text
- `git status`
- `git remote -v`
