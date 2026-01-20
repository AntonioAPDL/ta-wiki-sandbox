# Lab: Your First PR

## Goal
Make a small docs fix and submit a PR.

## File to edit
`docs/ta-essentials.md`

## Required change (choose one)
Option A: Fix 1 typo AND fix 1 link.  
Option B: Improve 1 bullet list for clarity.

## Commands (copy-paste, in order)
Replace `<branch>` with your value.

```bash
git clone https://github.com/AntonioAPDL/ta-wiki-sandbox.git
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

## Open the PR on GitHub
1) Click "Compare & pull request" for your branch.
2) Fill out the PR template.
3) Preview Markdown one last time and submit.

Optional: add a label (typo/link, structure, template, resource, graphics).
