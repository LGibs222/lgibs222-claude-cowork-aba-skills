# Lesson 3 — Writing skills that actually fire

Most skills that fail don't fail because of bad content. They fail because Claude never picked them in the first place. This lesson is about making sure your skill triggers when it should — and *doesn't* trigger when it shouldn't.

---

## The trigger problem

Claude has many skills available at any moment. When you send a message, Claude scans the **descriptions** and picks the best match. Three things go wrong:

1. **Description too vague** → skill never gets picked.
2. **Description too broad** → skill gets picked for unrelated tasks and produces weird output.
3. **Description doesn't use the words your user actually says** → skill gets picked at random.

The fix for all three is the same: write descriptions that include the *exact phrases* your real users (you, your team) say when they want this kind of work.

---

## The TRIGGER / SKIP pattern

Borrowed from Anthropic's own skill style. Add explicit trigger and skip language:

```yaml
description: |
  Draft a Behavior Intervention Plan (BIP) aligned to NYSED Part 200 from a completed FBA.

  TRIGGER when the user says: "draft a BIP," "write the BIP for [student]," "BIP from this FBA," "behavior plan for [student]," or pastes an FBA and asks for the corresponding plan.

  SKIP when: the user is asking general questions about what a BIP is, requesting a parent-facing version of a plan, or asking to update an already-drafted BIP (use bip-revision skill instead).
```

This makes Claude's decision much sharper. Use it for any skill that overlaps in topic with another.

---

## The five-test checklist for a description

Before you save a skill, run its description through these questions:

1. **Could a stranger read this and explain in one sentence what the skill does?** If not, rewrite.
2. **Are at least 3 specific user phrases in there?** ("parent update," "weekly note," "summary for the family.")
3. **Is there at least one SKIP condition?** Especially important if you have multiple skills in the same domain.
4. **Are the trigger phrases the words *you actually say*** when working — not formal task names you'd never type? ("write the BIP" beats "produce a behavior intervention plan document.")
5. **Is it under ~400 characters?** Long descriptions get diluted. Tight is better.

---

## Body craft — what makes a body actually useful

Once a skill fires, Claude follows the body. The body is doing two jobs:

### Job 1 — Tell Claude the structure of the output

This is concrete: headings, sections, what comes first.

```markdown
## Structure
1. Operational definition of target behavior (observable, measurable, no inference).
2. Setting and context.
3. ABC summary (table format if 3+ incidents).
4. Hypothesized function (one of: escape, attention, tangible, automatic).
5. Function-based recommendations (3 max, all tied to hypothesized function).
6. Data collection plan going forward.
```

### Job 2 — Tell Claude what *not* to do

Constraints punch above their weight. They prevent the most common drift.

```markdown
## Do not
- Use "noncompliance" as a target behavior — operationally define what the behavior looks like.
- Recommend interventions that don't connect to the hypothesized function.
- Skip the data collection plan — even a single sentence is required.
- Use the phrase "attention-seeking." Use "attention-maintained" instead.
```

You'll be surprised how much these "do not" lines steady the output across cases.

### Job 3 — Tell Claude what to ask the user

If the task needs information up front, list it. Otherwise Claude makes assumptions and you spend more time correcting than you saved.

```markdown
## Ask before drafting
- Student's grade level and disability classification (IDEA category).
- 3–5 ABC incidents (or paste raw ABC data).
- Existing IEP goals related to behavior, if any.
- Setting(s) where the behavior occurs.
```

---

## Common mistakes I see

### Mistake 1 — One skill trying to do five things
A skill called `aba-helper` that handles FBAs, BIPs, parent updates, and IEP goals will fire for everything and do all of them poorly.
**Fix:** one skill, one job.

### Mistake 2 — Body so long it becomes a textbook
If your body is 4+ pages of background, Claude does worse — not better. The body is an SOP, not a reference book.
**Fix:** if you need reference material, *link* to it from the body or put it in a separate file. The skill itself stays under ~300 lines.

### Mistake 3 — Forgetting the audience constraint
"Write an FBA" is different depending on whether the audience is a special ed teacher, a parent, an IEP committee, or a court. State the audience.
**Fix:** add an `## Audience` section.

### Mistake 4 — Putting case-specific info in the skill
The skill is the *template*, not the case. Names, dates, and details belong in the prompt or in the case folder.
**Fix:** if you find yourself writing "for J.M.'s case" in the skill, stop — move that to a per-client file.

### Mistake 5 — Never updating the skill
Skills get better the second and third time you use them. The first version always has rough edges. Edit them.
**Fix:** after each use, ask yourself "what did I have to fix by hand?" and put a guardrail for it in the body.

---

## A worked example: from blob to skill

Here's how I'd refine a weak first draft.

**v1 (weak):**
```markdown
---
name: fba-helper
description: Helps with FBAs.
---
Write a good FBA.
```

**v2 (clearer trigger, but still weak body):**
```markdown
---
name: fba-quickstart
description: Start a new functional behavior assessment for a K-12 student in NY.
---
Produce an FBA covering the student's behavior, function, and recommendations.
```

**v3 (production-ready):**
```markdown
---
name: fba-quickstart
description: |
  Draft a NYSED Part 200-aligned Functional Behavior Assessment (FBA) for a K-12 student in NY.
  TRIGGER when the user says: "start an FBA for [student]," "write an FBA," "draft FBA," or pastes ABC/indirect/descriptive data and asks for an FBA.
  SKIP when: updating an existing FBA (use fba-revision), or doing a BIP (use bip-drafter).
---

# FBA Quickstart

## Audience
Special ed teacher + IEP team (not parent-facing).

## Required structure
1. **Background** — student grade, disability classification, setting.
2. **Operational definition** of target behavior (observable, measurable, no inference).
3. **Indirect data summary** (interviews, scales — name the source).
4. **Descriptive data summary** (observations).
5. **ABC summary table** (minimum 5 incidents).
6. **Hypothesized function** — one of: escape, attention, tangible, automatic. State the evidence.
7. **Function-based recommendations** — exactly 3, each linked to the hypothesized function.
8. **Data collection plan going forward.**

## Ask before drafting
- Student grade and IDEA classification.
- ABC data (paste raw or attach).
- Existing behavior goals from IEP, if any.
- Setting(s) — classroom, hallway, cafeteria, etc.

## Do not
- Use "noncompliance" or "defiance" as a target behavior.
- Recommend interventions disconnected from the hypothesized function.
- Skip the data collection plan.
- Produce parent-facing language in this skill (use parent-update-drafter for that).
```

v3 will fire reliably and produce consistent output. v1 and v2 will not.

---

**Next:** [Lesson 4 — ABA-specific patterns and recipes](04-aba-recipes.md)
