# Lab: Your First PR

## Goal
Make a small docs fix and submit a PR.

If you prefer one command-driven path from login to PR, see:
- `workshop/student-copy-paste-script.md`

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

## Step 0: choose one path
Path A (recommended): fork in GitHub UI, then clone with `git`.

Path B (terminal-first): use GitHub CLI:

```bash
gh repo view <your-username>/ta-wiki-sandbox >/dev/null 2>&1 || gh repo fork AntonioAPDL/ta-wiki-sandbox --remote=false
git clone https://github.com/<your-username>/ta-wiki-sandbox.git
cd ta-wiki-sandbox
```

If you use Path A:
1) Open `https://github.com/AntonioAPDL/ta-wiki-sandbox`.
2) Click "Fork".
3) Clone your fork:

```bash
git clone https://github.com/<your-username>/ta-wiki-sandbox.git
cd ta-wiki-sandbox
```

Why this step matters:
- You need your own fork so you can push changes without write access to the upstream repo.

## Step 1 (terminal): create your branch
Branch naming standard: `your-username/<short-topic>`  
Examples: `aguirrepdeleon-beep/fix-typo`, `lee/link-fix`

```bash
git switch -c <your-username>/<short-topic>
```

Why this step matters:
- A branch isolates your work and keeps your PR focused.

## Step 2 (VS Code editor): make one small change
```bash
code .
```

- Open `docs/ta-essentials.md`.
- Make exactly one small change.
- Preview Markdown in VS Code.

Why this step matters:
- Small single-purpose edits are easier to review and less likely to conflict.

## Step 3 (terminal): verify you really changed a file
Run this before committing:

```bash
git status
git diff -- docs/ta-essentials.md
```

If you see `nothing to commit, working tree clean`, you did not save any change yet. Go back to Step 2.

Why this step matters:
- It prevents empty commits and the "No commits between ..." PR error.

## Step 4 (terminal): commit and push
```bash
git add docs/ta-essentials.md
git commit -m "docs: <short description>"
git push -u origin <your-username>/<short-topic>
```

Note: `origin` must be your fork, not `AntonioAPDL/ta-wiki-sandbox`.
Check:

```bash
git remote -v
```

Why this step matters:
- `git add` selects what goes into the commit.
- `git commit` creates a reviewable snapshot.
- `git push` publishes your branch so GitHub can open a PR.

## Step 5: open the PR
Browser path:
1) Open your fork and click "Compare & pull request".
2) Confirm base repo is `AntonioAPDL/ta-wiki-sandbox` and base branch is `main`.
3) Fill the PR template and submit.

Terminal path:

```bash
gh pr create \
  --repo AntonioAPDL/ta-wiki-sandbox \
  --base main \
  --head <your-username>:<your-username>/<short-topic> \
  --title "docs: <short description>"
```

If `gh pr create` says `No commits between ...`, your branch has no new commit. Return to Step 2 and Step 4.

Optional: add a label (`typo/link`, `structure`, `template`, `resource`, `graphics`).

Why this step matters:
- The PR is where review happens before merge into `main`.
