---
title: 1. What is a skill?
parent: Lessons
nav_order: 1
---

# Lesson 1 — What is a skill?

## The 30-second version

A **skill** is a Markdown file (`.md`) that teaches Claude how to do one specific thing well. When your request matches what the skill is for, Claude reads the file and follows its guidance — automatically, without you reminding it.

Think of it as a **standing order** rather than a one-time instruction.

---

## Why this matters for school-based ABA

Most consultation work is repetitive in shape, even when each case is unique:

- Every FBA needs operational definitions, an ABC summary, a hypothesized function, and a function-based recommendation.
- Every parent update needs to translate clinical language into plain English, lead with progress, and end with a clear ask.
- Every teacher coaching note needs a behavior described in observable terms, a single replacement strategy, and a check-in date.

You already know the structure. The slow part is typing it out — or worse, prompting Claude to follow it correctly each time and getting drift halfway through.

A skill bakes the structure in. You ask Claude to "write a parent update for J.M. about the past two weeks," and the right format shows up.

---

## Skill vs. prompt — what's the difference?

| | Prompt | Skill |
|---|---|---|
| Lives in… | Your message, typed each time | A `.md` file Claude loads automatically |
| Reusable? | Only if you copy/paste it | Yes — fires whenever the request matches |
| Versioned? | No, it scrolls away in chat | Yes, it's a file you can edit and track |
| Shareable? | Only via screenshot/copy | Send the file to a colleague, they get the same behavior |
| Triggered by | You manually | Claude, based on the request |

A prompt is what you say once. A skill is what you say *every* time you do this kind of work.

---

## When a skill is the right tool

Write a skill when:

- You catch yourself giving Claude the same instructions on different cases.
- You want consistent output across a team (e.g., every consultant on your district team produces FBAs in the same format).
- The task has a defined structure or compliance requirement (NYSED Part 200, district FBA template, IEP goal grammar).
- You want Claude to **bring its own checklist** to a task instead of relying on you to remember every step.

Don't write a skill when:

- The task is one-off ("rename this variable," "summarize this email").
- The behavior is purely a personal preference for one moment ("be terser today").
- You haven't done the task by hand at least 2–3 times — you don't yet know the structure well enough to teach it.

---

## A quick mental model

Imagine you're orienting a new graduate student to your practice. You'd give them:

1. **A name for the task** ("FBA quickstart").
2. **A short description of when to use it** ("when starting a new functional behavior assessment for a K–12 student in NY").
3. **The actual steps and standards** ("collect indirect, descriptive, and ABC data; operationally define the target behavior; hypothesize function; tie recommendations to function").

That's a skill. Three pieces — name, description, body. The next lesson shows you exactly how that maps to a `.md` file.

---

**Next:** [Lesson 2 — Anatomy of a skill file](02-anatomy-of-a-skill.md)
