# Lesson 2 — Anatomy of a skill file

A skill is one Markdown file. Two parts: **frontmatter** at the top, **body** below.

## The whole picture

```markdown
---
name: parent-update-drafter
description: Draft a 2-week parent update for a school-based ABA case. Use when the user says "parent update," "weekly note for the family," "summary for [child]'s parents," or asks to translate progress notes into plain language for caregivers.
---

# Parent Update Drafter

When this skill fires, produce a parent update with the following structure:

## Structure
1. **Greeting** — by first name, warm but professional.
2. **What we worked on** — 1–2 sentences in plain language. No jargon ("aggression" → "hitting and pushing"; "DRA" → "rewarding the helpful behavior we want to see more of").
3. **What went well** — at least one specific moment. Quote or paraphrase if data supports it.
4. **What's still hard** — honest, never alarming. Frame as "what we're working on next."
5. **What you can try at home** — exactly ONE strategy. Concrete and short.
6. **Close** — invite questions, give a check-in date.

## Tone rules
- Reading level: 6th–8th grade.
- Strengths-based first sentence.
- Never use the words "noncompliance," "manipulative," "attention-seeking," or "extinction" in a parent-facing document.
- If the case has a BIP, refer to strategies by their everyday name (e.g., "first/then board" not "antecedent manipulation via behavioral momentum").

## What to ask the user before drafting
- Child's first name (or initials if confidentiality is preferred).
- Date range covered.
- One or two specific things that happened this period.
- Anything sensitive the family already knows about.
```

That's it. One page, complete.

---

## The frontmatter, line by line

The block at the top between the `---` lines is **YAML frontmatter**. Two fields are required:

### `name`
A short, lowercase, hyphen-separated identifier. This is how Claude internally refers to the skill.

✅ `parent-update-drafter`
✅ `fba-quickstart`
✅ `abc-analyzer`
❌ `Parent Update Drafter` (spaces, capitals)
❌ `skill_v3_final_FINAL` (underscores, ambiguous)

### `description`
**This is the most important field.** Claude reads the description of every available skill and decides which one (if any) fits the user's current request. If your description is vague, your skill won't fire when it should.

Good descriptions answer two questions:

1. **What does this skill do?** (one clause)
2. **When should it be used?** (specific phrases the user might say)

Compare:

❌ `description: Helps with parent updates.`
*Too vague. Claude doesn't know if this fires for a single sentence rewrite or a full report.*

✅ `description: Draft a 2-week parent update for a school-based ABA case. Use when the user says "parent update," "weekly note for the family," "summary for [child]'s parents," or asks to translate progress notes into plain language for caregivers.`
*Specific trigger phrases. Claude can match this to real user messages.*

### Optional: `type`
You can add `type: skill` for clarity, but it's not required by the harness.

---

## The body

Everything below the second `---` is the body. This is what Claude reads **after** it has decided to use the skill. Treat it like an internal SOP document.

### What to put in the body

- **The structure of the output** — sections, headings, format.
- **Tone, reading level, audience constraints.**
- **Compliance or framework requirements** — e.g., NYSED Part 200 elements, NYC DOE FBA template fields.
- **What to ask the user before producing output**, if anything.
- **What to avoid** — banned phrases, jargon, formats.

### What NOT to put in the body

- Long backstory about why you wrote it.
- Generic prompt engineering advice ("be helpful and accurate").
- Information Claude already has (e.g., what an FBA is in general — Claude knows; tell it what *your* FBAs need to look like).

---

## Self-check

Read this skill and predict: would it fire when a user says "Hey, can you write a quick weekly update for Jordan's mom about how this week went?"

```markdown
---
name: family-summary
description: Helps with summaries.
---

# Family Summary
Write a nice summary for the family.
```

**Probably not** — the description is too vague to match "weekly update for [child]'s mom," and the body gives no structure to follow. Compare to the parent-update-drafter at the top of this lesson.

---

**Next:** [Lesson 3 — Writing skills that actually fire](03-writing-effective-skills.md)
