# Quickstart (Before the Workshop)

Complete this before the live session so the hour focuses on Git workflow, not setup.

## Choose your path
Pick one workflow and stick to it:
- Browser + Git: fork in GitHub UI, then use `git` locally.
- Terminal-first: use GitHub CLI (`gh`) for fork and PR from terminal.

Both paths work on Windows, macOS, and Linux.

## 1) Install VS Code
Windows:
- Download and install: https://code.visualstudio.com/
- Launch VS Code once so setup completes.

macOS:
- Download: https://code.visualstudio.com/
- Drag "Visual Studio Code" to Applications and open it once.

Linux:
- Download from https://code.visualstudio.com/ or use a package manager.
- Examples:

```bash
sudo snap install code --classic
```

```bash
flatpak install flathub com.visualstudio.code
```

## 2) Install Git
Windows:
- Install Git for Windows: https://git-scm.com/download/win

macOS:

```bash
xcode-select --install
```

or

```bash
brew install git
```

Linux:

```bash
sudo apt update && sudo apt install git
```

```bash
sudo dnf install git
```

```bash
sudo pacman -S git
```

Verify:

```bash
git --version
```

## 3) Install GitHub CLI (`gh`) if you want terminal-first flow
Windows (winget):

```powershell
winget install --id GitHub.cli
```

macOS:

```bash
brew install gh
```

Ubuntu/Debian:

```bash
sudo apt install gh
```

Verify:

```bash
gh --version
```

## 4) Open VS Code terminal and verify tools
- VS Code -> Terminal -> New Terminal

```bash
git --version
```

If you use terminal-first flow:

```bash
gh --version
```

Optional but recommended:
- Ensure `code .` works.
- If it fails, use Command Palette -> "Shell Command: Install 'code' command in PATH".

## 5) Set your Git identity (one time)
Why: this name and email appear on commits and PRs.

```bash
git config --global user.name "YOUR GITHUB USERNAME"
git config --global user.email "YOUR_GITHUB_EMAIL"
git config --global --get user.name
git config --global --get user.email
```

## 6) Authenticate
If using Git-only (browser + git), you can use HTTPS + PAT when prompted by `git push`.

If using `gh`, sign in:

```bash
gh auth login --hostname github.com --git-protocol https --web
gh auth status
gh api user -q .login
```

### WSL/Ubuntu note: browser may not auto-open
You may see errors like `xdg-open: no method available`. This is normal on headless terminals.
- Copy the one-time code printed by `gh`.
- Open `https://github.com/login/device` manually in any browser.
- Paste the code and continue.

If you need to log out:

```bash
gh auth logout -h github.com
```

## 7) GitHub fork access check
- Open `https://github.com/AntonioAPDL/ta-wiki-sandbox`.
- Confirm you can see the "Fork" button.

## Ready check
- `git --version` works.
- `gh --version` works (if using terminal-first flow).
- Git name and email are set correctly.
- You can log in to GitHub and confirm your account.
- You can see the "Fork" button on the sandbox repo.

## If you get stuck, paste this debug bundle
- Exact error text
- `git status`
- `git remote -v`
- `gh auth status` (if using `gh`)
