# Lab: Your First PR

## Goal
Make a small docs fix and submit a PR.

## File to edit
`docs/ta-essentials.md`

## Required change (choose one)
Option A: Fix 1 typo AND fix 1 link.  
Option B: Improve 1 bullet list for clarity.

## Step 0: Fork the repo on GitHub
Click "Fork" to create a copy under your account.

## Commands (copy-paste, in order)
Replace `<your-username>` and `<branch>` with your values.

```bash
git clone https://github.com/<your-username>/ta-wiki-sandbox.git
cd ta-wiki-sandbox
git checkout -b <branch>
code .
```

Make your edit in VS Code, then:

```bash
git status
git add docs/ta-essentials.md
git commit -m "docs: fix typos and link"
git push -u origin <branch>
```

Note: this pushes your branch to your fork (your `origin`), not to the original repo.

## Open the PR on GitHub
1) Open your fork on GitHub and click "Compare & pull request."
2) Make sure the base repo is `AntonioAPDL/ta-wiki-sandbox` and the base branch is `main`.
3) Fill out the PR template, preview Markdown, and submit.

Optional: add a label (typo/link, structure, template, resource, graphics).
