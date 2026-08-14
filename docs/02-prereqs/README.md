# Prerequisites and Setup

Before you begin the labs, make sure you have the following:

1) A GitHub account (free)
   - Sign up at https://github.com if you do not have one.

2) Git installed on your machine (optional: you can use the GitHub web UI instead)
   - Check with: `git --version`
   - macOS: Git is often preinstalled. If not, install Xcode Command Line Tools: `xcode-select --install`
   - Windows: Install Git for Windows: https://gitforwindows.org/
   - Linux: Install using your package manager, e.g., `sudo apt install git` or `sudo dnf install git`

3) A terminal where you can run commands
   - macOS: Terminal or iTerm
   - Windows: Windows Terminal, PowerShell, or Git Bash
   - Linux: any terminal

4) A text editor for small edits
   - VS Code, Notepad++, or the GitHub web editor are fine

5) (Recommended) Configure git with your name and email
   - git config --global user.name "Your Name"
   - git config --global user.email "you@example.com"

Cloning this repository (two options)

A) Use the GitHub web UI (beginner-friendly)
   - Open https://github.com/nkydigitech/cicd-blueprint
   - Click Fork to copy the repo to your account (optional but recommended for practice)
   - Use the green Code button to copy the clone URL and clone locally if you want

B) Use the terminal

- git clone https://github.com/your-username/cicd-blueprint.git
- cd cicd-blueprint

Where to type commands

- All `git` commands go into your terminal. When instructions say "open this file" you may edit it in the GitHub web editor or your local editor.

Cost and safety notes

- The labs in Module 01 use GitHub Actions and a public repo; there is no cloud cost.
- If later modules use cloud providers (AWS, Azure), the lab will provide explicit cost estimates and cleanup commands.

If something is missing

- If a command fails, copy the error message and open an issue in this repo. Start the issue title with `lab: ` so we can triage it quickly.

