# Task: Finish the Git + GitHub setup 🐙

**From:** Leader · Wailan (洄瀾)
**To:** Member · Taroko (太魯閣)
**Date:** 2026-10-12
**Mode:** Manual relay

## Background / 背景

The captain wants git + GitHub handled by CLI from this folder. I got partway and stopped here — **you take it from this point.** Do not redo what's already done.

**Already done (verify, don't repeat):**
- Git **2.55.0** and GitHub CLI **2.102.0** installed at `C:\Program Files\Git\cmd\git.exe` and `C:\Program Files\GitHub CLI\gh.exe` (both added to the **user** PATH — a *new* terminal picks them up automatically; in this session call them by full path).
- `git init` done → `C:\Users\NDHU CSIE\Downloads\ai-team-starter\my-team\.git` exists, branch `master`, **no commits yet**.
- `.gitignore` created at the folder root (OS junk, `node_modules/`, `.env*`, `*.log`).
- Nothing staged, nothing committed, nothing pushed.
- My `gh auth login` attempt is dead — its one-time code expired. Start your own.

## What to do / 做什麼

Work from the project folder:
`C:\Users\NDHU CSIE\Downloads\ai-team-starter\my-team`

1. **Authenticate GitHub.** Run `gh auth login` → **GitHub.com** → **HTTPS** → **Login with a web browser**. The captain is already logged into GitHub with Google in their own browser, so when the code appears, tell the captain: open `https://github.com/login/device` and paste the code. **Never enter the captain's password yourself.**
2. **Set git identity** from the logged-in account:
   `git config user.name` → from `gh api user --jq .name` (fall back to `.login` if name is empty)
   `git config user.email` → from `gh api user --jq .email` (fall back to `<login>@users.noreply.github.com` if null)
   Set them **locally** for this repo (`git config user.name "..."`), not `--global`.
3. **Sanity-check the repo**: `git status`, `git log` should say "No commits yet".
4. **First commit** — stage everything the `.gitignore` doesn't exclude, including `workspace/` (our notes are meant to be tracked):
   `git add -A` then commit with message `Initial commit: team charter, personas, and workspace notes`.
   Confirm with `git status` (clean) and `git log --stat -1` (files listed).
5. **Create the public repo and push:**
   `gh repo create my-team --public --source=. --remote=origin --push`
   Then `git remote -v` and `gh repo view my-team --json url,visibility` to prove it landed.

## Format / 格式

- Everything via **CLI only** — no GitHub web UI for creating the repo, no GUI clients.
- Save your report as a **new file** in `workspace/outbox/`:
  `workspace/outbox/20261012-github-setup.md`

## What "done" looks like / 怎樣算做完

- `gh auth status` → logged in as the captain's account.
- `git config user.name` and `user.email` are set locally and non-empty.
- `git log` shows exactly one commit, working tree clean.
- `git remote -v` shows `origin` over HTTPS.
- `gh repo view my-team` → **public**, URL reported in your handoff note.
- The report ends with a one-line handoff: what you did, anything to watch, ready to use or not.

## Rules / 規矩

- Stay inside this project folder. Never delete files.
- Never ask for or handle the captain's password — browser login only.
- Don't touch `shared/`, don't modify existing files (`.gitignore` only if it's actually broken — say why in your report).
- If `gh auth login` fails or the repo already exists on GitHub, **stop and report** instead of forcing it.
