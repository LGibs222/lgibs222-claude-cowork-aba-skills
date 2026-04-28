# Lesson 5 — Installing and sharing skills

You have a `.md` skill file. Now: where does it go, how do you test it, and how do you share it with a team?

---

## Where skills live

Claude Code (the engine behind Claude Cowork) looks for skills in a few standard locations. The most common:

### Per-user skills
```
~/.claude/skills/
```
On Windows, that's:
```
C:\Users\<your-username>\.claude\skills\
```

Drop a `.md` file in that folder and it becomes available in every Claude Code session you start, on any project.

> Tip: each skill goes in its own subfolder named after the skill. So `parent-update-drafter` lives at:
> ```
> ~/.claude/skills/parent-update-drafter/SKILL.md
> ```
> The file is named `SKILL.md` (or sometimes just the skill name + `.md`). Check your existing skills — match the convention you find there.

### Per-project skills
```
.claude/skills/
```
inside the root of a project folder. Useful when a skill should only fire when you're working in a specific project (e.g., a district contract folder).

### Shared / team skills
For a team, the cleanest pattern is:
1. Put all your skills in a Git repo (like the one you're reading right now).
2. Have each team member clone it into their `~/.claude/skills/` folder.
3. Use `git pull` to get updates.

That way, when one consultant improves the FBA skill, the whole team benefits the next time they pull.

---

## Installing the examples in this module

From this folder:

```bash
# Copy a single skill into your user skills directory
cp examples/parent-update.md ~/.claude/skills/parent-update-drafter/SKILL.md
```

On Windows (PowerShell):

```powershell
New-Item -Path "$env:USERPROFILE\.claude\skills\parent-update-drafter" -ItemType Directory -Force
Copy-Item "examples\parent-update.md" "$env:USERPROFILE\.claude\skills\parent-update-drafter\SKILL.md"
```

After copying, restart Claude Cowork (close and reopen the session). Skills are scanned at session start.

---

## Testing a skill

Three quick checks every time you write or modify a skill:

### 1. The "wrong-words" test
Try a request that uses *different words* than the ones in your description. If your skill is for parent updates and you say "write a note for the family," does it still fire? If not, your description is too narrow — add more trigger phrases.

### 2. The "off-topic" test
Try a request that should *not* fire the skill. Ask Claude to "rename a variable in this Python file." Does the parent-update skill fire by mistake? If yes, your description is too broad — add SKIP conditions.

### 3. The "first draft" test
Run the skill on a real (or sanitized) case. Read the first draft. Note every place you had to fix something by hand. Add a guardrail in the body for each fix. Re-run on the next case. By the third case the skill should be producing minimal-edit output.

---

## Versioning and updating

Skills live in `.md` files, which means:

- You can use Git to track changes (`git diff`, `git log` show the evolution).
- You can roll back to a previous version if a "fix" makes the skill worse.
- You can branch — try a new version of a skill in a branch, only merge once it's better than the current one.

If you don't use Git, at least keep a `CHANGELOG.md` next to your skills. Date every change. Future-you will thank present-you.

---

## Sharing with a team

### Option A — Git repo (recommended)
- Skills repo on GitHub (private or public).
- Each consultant clones into their `~/.claude/skills/` folder (or symlinks).
- Team improvements flow via PRs.

### Option B — Shared drive
- Skills in OneDrive / Google Drive folder.
- Each consultant manually copies into their `~/.claude/skills/`.
- Less version control, but works.

### Option C — Send-and-paste
- Slack a colleague the `.md` file.
- They paste it into their skills folder.
- Fine for ad-hoc collaboration, not great for a 10-person team.

Whichever option, the principle is: **the source of truth is the file**, not someone's memory of how the skill should work.

---

## Common installation pitfalls

- **Skill not firing after install.** → You probably need to restart the Claude Cowork session. Skills are loaded at session start.
- **Skill firing on wrong tasks.** → Description is too broad. Add SKIP conditions and tighten the trigger phrases.
- **Skill firing but ignoring its body.** → Body is too long, too vague, or contradicts itself. Trim it. Aim for under 200 lines.
- **Two skills compete for the same request.** → Add explicit SKIP conditions in both descriptions naming the other skill ("SKIP when: writing a BIP — use bip-drafter").

---

## What to do next

You've finished the module. Here's a 30-day plan to actually get value:

| Week | Action |
|---|---|
| 1 | Copy the 5 example skills into `~/.claude/skills/`. Use them on real cases. Note rough edges. |
| 2 | Pick the 1 skill you used most. Edit it based on what you noticed. |
| 3 | Write 1 brand-new skill from scratch for a recurring task none of the examples cover. |
| 4 | Set up a Git repo for your skills. Share with one trusted colleague. Iterate together. |

By day 30, you should have a small, sharp portfolio of skills you actually use — and the habit of writing a new one whenever you notice yourself repeating instructions.

---

**Module complete.** If you build something useful, send it back to the repo as a PR. The whole point of this work is reach.
