# Troubleshooting

## Forgot `git add`
Symptoms: `git commit` says "nothing to commit" or your file is still listed as "not staged."

```bash
git status
git add docs/ta-essentials.md
git commit -m "docs: add my change"
```

If you already committed without a file and have NOT pushed yet:

```bash
git add docs/ta-essentials.md
git commit --amend --no-edit
```

## Committed to main by accident (local fix)
If the commit is local and not pushed, move it to a new branch.

```bash
git switch -c username/<short-topic>
git switch main
git reset --hard origin/main
```

This resets your local `main` to match `origin/main` after your commit is safely on a new branch.

If you already pushed to `main`, stop and call the organizer.

## Wrong branch
Check where you are and switch:

```bash
git branch
git switch <correct-branch>
```

If the correct branch does not exist yet:

```bash
git switch -c username/<short-topic>
```

## Auth failed (token vs password)
GitHub requires a token for HTTPS pushes.

```bash
git remote -v
```

If you are prompted for a password, paste your PAT. If you do not have one, create it first (see `workshop/quickstart.md`).

## Merge conflict
A merge conflict happens when Git cannot automatically combine changes to the same lines.

Do this:
1) Open the conflicted file in VS Code.
2) Choose the correct lines and remove conflict markers.
3) `git add <file>` and `git commit`.

If this is your first conflict, call the organizer and resolve together.
