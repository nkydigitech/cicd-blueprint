# Hello CI — Run your first GitHub Actions workflow

Goal

- Add and run a simple GitHub Actions workflow that prints messages and shows you the build logs.

Why you need this

- This lab teaches the minimal steps: add a workflow file, push it, and inspect a run. These are the foundational skills for all CI/CD work.

Prerequisites

- A GitHub account
- Either cloned fork of this repo or permission to push to a repo
- A terminal (or you can use the GitHub web editor)

Quick overview

- We will add `.github/workflows/hello-ci.yml`, commit it, push it, and then look at the Actions tab.

Step-by-step (copy-paste friendly)

1) Fork the repo (recommended)

- In your browser, open: https://github.com/nkydigitech/cicd-blueprint
- Click "Fork" (top-right) and fork to your personal account.

2) Clone your fork (or clone the repo if you will work directly in this repo)

- git clone https://github.com/<your-username>/cicd-blueprint.git
- cd cicd-blueprint

3) Create a branch for the lab (this keeps `main` clean)

- git checkout -b learn/hello-ci

4) Create the workflow file

Create a new file at `.github/workflows/hello-ci.yml` with the exact content below.

```yaml
name: Hello CI

on:
  push:
    branches:
      - '**'
  pull_request:

jobs:
  say-hello:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run a tiny test script
        run: |
          echo "Hello CI — this is a simple test job"
          echo "Runner: $(uname -a)"
          echo "Current dir: $(pwd)"
          echo "Files in workspace:"
          ls -la
```

Where to type

- Create this file in your local editor under the repository folder and save it, or use the GitHub web UI: Add file → Create new file → paste content → Commit to branch `learn/hello-ci`.

5) Commit and push (local instructions)

- git add .github/workflows/hello-ci.yml
- git commit -m "chore(lab): add Hello CI workflow"
- git push -u origin learn/hello-ci

6) View the run

- In your forked repo on GitHub: Actions tab → select "Hello CI" → click the most recent run → click the job `say-hello` → expand the step `Run a tiny test script` to see the echo and `ls` output.

What you should see

- The job should complete successfully (green checkmark).
- Log output will include the "Hello CI — this is a simple test job" line and a directory listing of the repository workspace.

What the result means

- The GitHub hosted runner checked out your repository and executed the commands. You have successfully run a CI job.

Troubleshooting — common problems and fixes

- No run appears after pushing
  - Confirm you pushed the branch that contains the workflow file.
  - Confirm the workflow `on` events include `push` and `pull_request` (the example above does).

- YAML parsing error or workflow did not start
  - The workflow file must be valid YAML and located under `.github/workflows/`.
  - Use an online YAML validator if unsure.

- Job fails on checkout
  - If the job cannot check out the code, confirm the repo is public or the runner has permission.

Cleanup

- Delete the branch when done to keep your repo tidy:
  - git checkout main
  - git branch -D learn/hello-ci
  - git push origin --delete learn/hello-ci

No cloud costs were incurred in this lab — GitHub Actions runs on public repos are free.

Checkpoint quiz (quick)

1) Where do GitHub Actions workflow files live in a repository?
2) What command did we use to create a branch locally?
3) What does a green checkmark next to an Actions run mean?

Answers

1) .github/workflows/
2) git checkout -b <branch-name>
3) The run's jobs finished successfully

What next

- Module 02: run a simple unit test in CI (Node or Python). See docs/03-roadmap/README.md for the roadmap.

