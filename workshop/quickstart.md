# Quickstart (Before the Workshop)

Complete this before the live session so the hour focuses on Git workflow, not setup. Use your OS terminal or the VS Code terminal.

## 1) Install VS Code
Windows:
- Download and install: https://code.visualstudio.com/
- Launch VS Code once so it finishes setup.

macOS:
- Download: https://code.visualstudio.com/
- Drag "Visual Studio Code" to Applications and open it once.

Linux:
- Download the .deb or .rpm from https://code.visualstudio.com/ and install it, or use a package manager.
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
- Accept defaults so Git works from the command line.
- Verify in a terminal:

```bash
git --version
```

macOS:
- Run:

```bash
xcode-select --install
```

- Or if you use Homebrew:

```bash
brew install git
```

- Verify:

```bash
git --version
```

Linux:
- Install Git from your package manager.
- Examples:

```bash
sudo apt update
sudo apt install git
```

```bash
sudo dnf install git
```

```bash
sudo pacman -S git
```

- Verify:

```bash
git --version
```

## 3) Open a terminal in VS Code
- In VS Code: Terminal -> New Terminal.
- Verify Git works:

```bash
git --version
```

Optional but recommended for the lab:
- Make sure `code .` works.
- If it fails, open Command Palette and run "Shell Command: Install 'code' command in PATH".
- You can always open the folder manually via File -> Open Folder.

## 4) Set your Git identity (one time)
Why: Git records who made each commit, and that name shows in the PR.

```bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR@EMAIL"
```

## 5) Authentication (HTTPS + PAT)
GitHub no longer accepts account passwords for Git operations over HTTPS. When Git prompts for a password, paste a personal access token (PAT) instead.

Create a PAT:
1) GitHub -> Settings -> Developer settings -> Personal access tokens.
2) Create a fine-grained token with access to this repo and "Contents: Read and write".
3) Copy the token and store it safely.

When prompted by Git:
- Username: your GitHub username
- Password: paste the token

If your terminal opens a browser login (Git Credential Manager), follow the prompts and approve access.

## 6) GitHub check (fork access)
- Log in to GitHub in a browser.
- Open https://github.com/AntonioAPDL/ta-wiki-sandbox and confirm you can see the "Fork" button.

## Ready check
- `git --version` works in the VS Code terminal.
- Your Git name and email are set.
- You can log in to GitHub in a browser.
- You have a PAT ready for HTTPS pushes.
- You can see the "Fork" button on the sandbox repo.

## If you get stuck, paste this
Include this bundle when asking for help so we can diagnose quickly:
- Exact error text
- `git status`
- `git remote -v`
