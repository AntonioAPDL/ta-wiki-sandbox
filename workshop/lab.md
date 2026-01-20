# Lab: Your First PR

## Goal
Make a small docs fix and submit a PR.

## File to edit
`docs/ta-essentials.md`

## Required change (choose ONE small edit)
Pick one easy change so your PR stays small.

Option A: Fix 1 typo (one word).  
Option B: Fix 1 formatting issue (a small Markdown change).  
Option C: Fix 1 link (correct an obvious typo in the URL).  
Option D: Improve 1 bullet for clarity (rewrite one line).

Examples (choose one):
- Fix "reserced" -> "reserved".
- Turn "Office hours flow" into a heading.
- Fix ".../academic-integrty" -> ".../academic-integrity".
- Rewrite "Make sure announcements are sent maybe."

Do only one change in this file.

## Step 0 (GitHub, browser): fork the repo
Click "Fork" to create a copy under your account.

Why: you do not have write access to the original repo, so you push to your fork.

## Step 1 (VS Code terminal, local): clone your fork and create a branch
Branch naming standard: `your-username/<short-topic>`  
Examples: `aguirredleonis/fix-typo`, `lee/link-fix`

Commands (copy-paste, in order). Replace `<your-username>` and `<branch>` with your values.

```bash
git clone https://github.com/<your-username>/ta-wiki-sandbox.git
cd ta-wiki-sandbox
git checkout -b <branch>
code .
```

## Step 2 (VS Code, editor): make your change
- Open `docs/ta-essentials.md`.
- Make one small, clean change (choose Option A or Option B).
- Preview Markdown in VS Code (top right preview icon).

## Step 3 (VS Code terminal, local): commit and push
Make your edit in VS Code, then:

```bash
git status
git add docs/ta-essentials.md
git commit -m "docs: fix typos and link"
git push -u origin <branch>
```

Note: this pushes your branch to your fork (your `origin`), not to the original repo.

## Step 4 (GitHub, browser): open the PR
1) Open your fork on GitHub and click "Compare & pull request."
2) Make sure the base repo is `AntonioAPDL/ta-wiki-sandbox` and the base branch is `main`.
3) Fill out the PR template, preview Markdown, and submit.

Optional: add a label (typo/link, structure, template, resource, graphics).
