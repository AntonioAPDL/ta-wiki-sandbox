# Student Copy-Paste Script (Terminal)

Use this script if you want one terminal path from login to PR.

It assumes:
- You already installed `git`, `gh`, and VS Code.
- You are running in a Bash/Zsh terminal (Linux, macOS, or WSL).

## How to use
1) Copy this full script into your terminal.
2) Replace `YOUR_GITHUB_EMAIL` only.
3) Follow prompts (especially `gh auth login`).

```bash
# 0) Set your email only (used for commit attribution)
EMAIL="YOUR_GITHUB_EMAIL"

# 1) Authenticate GitHub CLI as your student account
gh auth logout -h github.com 2>/dev/null || true
gh auth login --hostname github.com --git-protocol https --web
# If browser does not open, manually go to: https://github.com/login/device
# and enter the one-time code shown by gh.

# 2) Capture logged-in username and verify account
USERNAME=$(gh api user -q .login)
echo "Logged in as: $USERNAME"
gh auth status

# 3) Set Git identity (name/email shown on commits and PR)
git config --global user.name "$USERNAME"
git config --global user.email "$EMAIL"
git config --global --get user.name
git config --global --get user.email

# 4) Create/enter student workspace
mkdir -p ~/repos/student-dryrun
cd ~/repos/student-dryrun

# 5) Create fork if missing, then clone your fork
gh repo view "$USERNAME/ta-wiki-sandbox" >/dev/null 2>&1 || gh repo fork AntonioAPDL/ta-wiki-sandbox --remote=false
[ -d ta-wiki-sandbox ] || git clone "https://github.com/$USERNAME/ta-wiki-sandbox.git"
cd ta-wiki-sandbox

# 6) Ensure remotes are correct
# origin   -> your fork (push target)
# upstream -> AntonioAPDL repo (PR target)
git remote add upstream https://github.com/AntonioAPDL/ta-wiki-sandbox.git 2>/dev/null || true
git remote -v

# 7) Branch, edit, commit, push
# Branch keeps your change isolated and reviewable
BRANCH="$USERNAME/fix-typo-lab1"
git switch -c "$BRANCH" || git switch "$BRANCH"

code docs/ta-essentials.md
# Make one small saved change

# Check the exact change before committing
git status
git diff -- docs/ta-essentials.md

# Commit and publish branch to your fork
git add docs/ta-essentials.md
git commit -m "docs: <short description>"
git push -u origin "$BRANCH"

# 8) Open PR to upstream main
gh pr create \
  --repo AntonioAPDL/ta-wiki-sandbox \
  --base main \
  --head "$USERNAME:$BRANCH" \
  --title "docs: <short description>"
```

## Common gotcha
If `gh pr create` says `No commits between ...`, you likely did not save any file change.
Go back, edit `docs/ta-essentials.md`, save, and rerun commit/push.
