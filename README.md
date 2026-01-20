# Welcome to the TA Wiki Git Workshop

This is a safe practice sandbox for students preparing to maintain the TA Resources wiki at https://github.com/UCSC-Statistics/TA-resources/wiki. It is an introduction to Git for wiki contributions. In one hour, you will make a small docs change and open a pull request (PR) using Git (CLI) and VS Code.

This repo is for practice only. Your PRs are reviewed here before you contribute to the real wiki.

## Start here (before the workshop)
- Complete `workshop/quickstart.md` so Git, VS Code, and authentication are ready.

## What you will do in 60 minutes
- [ ] Clone the repo to your laptop.
- [ ] Create a branch for your change.
- [ ] Edit a Markdown file in VS Code.
- [ ] Stage and commit the change with a clear message.
- [ ] Push your branch and open a PR on GitHub.
- [ ] Preview Markdown and check any links you touch.

End state: one PR open on GitHub and ready for review.

## Workshop materials
- `workshop/quickstart.md`
- `workshop/lab.md`
- `workshop/troubleshooting.md`

## Workshop flow (what we will use)
- Start in `workshop/lab.md` for the exact commands.
- Make your edits in `docs/ta-essentials.md`.
- Use `workshop/troubleshooting.md` if you get stuck.

## Pre-work checklist
- [ ] Git is installed (`git --version` works).
- [ ] GitHub account is ready and you can log in.
- [ ] VS Code is installed.

## Git mental model (one minute)
Git keeps three layers of state. You move changes forward one step at a time so you can review what you are about to share.

```
Working tree (your files)
  | git add
Staging area (what will be committed)
  | git commit
Local history (on your laptop)
  | git push
Remote branch on GitHub
  | open PR
Pull request (review + merge)
```

Branch = an isolated line of work. A PR is the reviewable bundle of that work.

## Standard workflow (one path only)
1) `git clone <repo-url>` (then `cd ta-wiki-sandbox`)
2) `git checkout -b <branch>`
3) Edit files in VS Code
4) `git status`
5) `git add ...`
6) `git commit -m "docs: ..."`
7) `git push -u origin <branch>`
8) Open a PR on GitHub

## Hygiene for a strong PR
- Keep the change single purpose.
- Use a clear, scoped commit message.
- Preview Markdown before you push.
- Check any links you touch.
