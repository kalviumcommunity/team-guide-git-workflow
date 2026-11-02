# CAT-2: Publish a Team Guide Through Git

**Total marks: 20 | Submission: one PDF**

## Problem statement

Your team needs a small onboarding guide update. Work on a feature branch, keep local demo files out of Git, open a pull request, review your own change and merge an improvement. Use plain text files; no application coding required.

## Starter repository and preparation

https://github.com/kalviumcommunity/team-guide-git-workflow

Use free GitHub and Git Bash, or Bash with Git on Linux/macOS. Before assessment, sign in to GitHub, check Git author name/email and test push authentication. Never include passwords/tokens in screenshots. No paid tools, partner or administrator permissions required.

On starter page select **Use this template > Create a new repository**, choose your account, a new repository name and public visibility. This creates your independent copy, not a fork. Clone YOUR repository, enter its folder and start on `main`. Do not clone the shared template and try to push to it. Ask instructor to resolve setup/authentication problems before starting tasks. A private reference may be used by instructor; visibility and ownership are not graded criteria.

Starter contains README.md and team-guide.txt. It is a working workflow starting point, not broken application code. Preserve starter files and initial commit. Use GitHub website for PR actions; GitHub CLI is an optional equivalent, not a required installation.

## Task 1: Prepare clean changes

1. Create and switch to `feature/team-guide` using `git switch -c feature/team-guide`. Show `git branch`.
2. Append exactly `Run git status before committing.` as a new line in `team-guide.txt`. Show `git diff` before staging.
3. Create `.gitignore` at repository root with exactly these two patterns, each on its own line:
   ```text
   .env
   *.log
   ```
4. Create disposable local `.env` containing `DEMO_MODE=local` and `debug.log` containing `Demo log only`. These are test files, not real secrets. Display their contents and `.gitignore`.
5. Run `git status --short --ignored` and `git ls-files`. Show `.env` and `debug.log` ignored (`!!`) and absent from tracked files. They must stay on disk and must never be committed.

**Evidence label: Task 1 - Branch and ignore rules.** Show branch, unstaged guide diff, displayed files/rules and ignore/tracked-file results. README may contain starter instructions; do not edit it.

## Task 2: Commit, push and open a pull request

1. Stage only `team-guide.txt` and `.gitignore`. Show `git diff --staged` and `git status` before committing; confirm demo files are not staged.
2. Commit using a meaningful message describing the guide and ignore-rule update. Show `git log --oneline` and clean `git status` after commit. Ignored local files do not make a working tree dirty.
3. Push your feature branch: `git push -u origin feature/team-guide`. Show successful push.
4. Open a pull request from `feature/team-guide` into `main` in YOUR repository. Give it a useful title and a short description stating what changed, why it helps onboarding and how you checked the guide/ignore rules. Capture PR while open, before Task 3 merge.

**Evidence label: Task 2 - Commit and open PR.** Show staged changes/status, commit/history/clean status, successful push and open PR title, description and branch direction. Website screenshots or equivalent real GitHub CLI output accepted.

## Task 3: Review, improve and merge

1. Leave one actionable self-review comment on your PR requesting a small onboarding improvement. Use this request or an equivalent specific request: `Please add a reminder to pull main before starting a new feature.` An ordinary PR conversation comment counts. Do not try to approve your own PR; no second reviewer required.
2. On the same feature branch, make the matching improvement. For the example request, append `Pull main before starting a new feature.` to `team-guide.txt`. Preserve earlier guide lines. Stage the guide, commit with a meaningful improvement message and push. Show improvement diff or commit content, commit and successful push.
3. Merge the PR into `main` on GitHub. Any available standard merge method accepted; no conflict or protected-branch setup required. Capture merged state and target branch. Do not delete feature branch until evidence is captured.
4. Locally run `git switch main`, then `git pull origin main`. Show `cat team-guide.txt` and clean `git status` on `main`. Both requested guide additions must be present if using the supplied review example; equivalent additions must match your own review request.
5. Below screenshots, write one sentence explaining how feature branches let changes be reviewed before reaching `main`.

**Evidence label: Task 3 - Review, improve and merge.** Show comment, matching improvement/commit/push, merged PR, updated local main/content/clean status and explanation. Self-review is a simulation of teammate review, not a claim that another person approved it.

## Submission guidelines

Upload **one PDF** with three task headings, labelled genuine screenshots and Task 3 explanation. Use as many readable screenshots as needed; capture intermediate states before moving on. Show all requested commands/results. PR evidence may use website or equivalent GitHub CLI output showing actual PR data. Do not submit fabricated output or expose authentication secrets.

No separate repository URL submission, code archive, video or filename requirement. URLs, usernames and hashes may appear naturally in evidence; no separate marks for their format, ownership, PDF styling or screenshot count. Required branch direction and actual workflow states remain technical evidence.

## Rubric: 20 marks

| Task | Criteria explicitly requested above | Marks |
|---|---|---:|
| 1 | Feature branch created and shown (1); correct guide addition shown in unstaged diff (1); both correct ignore patterns displayed (2); demo files exist and are shown ignored, not tracked (2) | 6 |
| 2 | Only intended files staged with staged diff/status evidence (2); meaningful commit/history and clean status (2); successful feature push (1); open PR with correct direction, useful title and what/why/check description (2) | 7 |
| 3 | Actionable self-review comment (1); matching improvement preserved/committed and pushed (2); PR merged into main (2); local main pulled, final guide content and clean status (1); correct feature-branch explanation (1) | 7 |
| **Total** | **Only stated task work and evidence are graded.** | **20** |

Award partial credit within each criterion. Missing evidence affects only its corresponding part; do not apply duplicate deductions or automatic whole-assessment zero. Accept equivalent commands, correct review improvements, merge methods and normal OS/path/hash differences. No extra presentation, account identity, repository-name, exact commit-message or peer-approval requirements. No conflict resolution, rebase, undo rescue, package installation, virtual environment, remote SSH or CI configuration required.
