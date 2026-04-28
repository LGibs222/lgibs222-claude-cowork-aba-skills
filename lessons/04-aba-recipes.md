---
title: 4. ABA recipes
parent: Lessons
nav_order: 4
---

# Lesson 4 — ABA-specific patterns and recipes

This lesson is the payoff: concrete patterns for the recurring tasks of school-based ABA practice. Each section gives you a **pattern** (what the skill should look like in shape) and a pointer to a complete working example in the [`examples/`](../examples/) folder.

---

## Pattern 1 — The "framework-aligned document drafter"

**When to use:** any document with a fixed structure or compliance requirement. FBAs, BIPs, manifestation determinations, reevaluation reports.

**Shape of the skill:**
- Trigger phrases include the document name AND common shortenings ("FBA," "behavior plan," "MD review").
- Body lists the **required sections in order**.
- Body includes "Do not" guardrails for the failure modes you've seen in practice.
- Body lists what to ask the user before drafting (so it doesn't make up details).

**See:** [`examples/fba-quickstart.md`](../examples/fba-quickstart.md)

---

## Pattern 2 — The "data-to-clinical-judgment translator"

**When to use:** when you have raw data (ABC logs, frequency counts, interval recordings) and need a *clinical interpretation*, not a re-statement.

**Shape of the skill:**
- Trigger phrases match what you'd say when you've already done the data collection ("analyze this ABC data," "what does this trend tell us," "interpret this data sheet").
- Body insists on **hypothesis generation tied to function**, not just description.
- Body requires Claude to flag when data is insufficient — never paper over thin evidence.
- Body bans confident claims from <5 data points.

**See:** [`examples/abc-analyzer.md`](../examples/abc-analyzer.md)

---

## Pattern 3 — The "translator across audiences"

**When to use:** the same case content needs to land differently for parents, teachers, the IEP team, and your own files. One source, multiple audiences.

**Shape of the skill:**
- One skill per audience (parent-update-drafter, teacher-coaching-note, iep-team-summary).
- Each skill states its audience in the first section of the body.
- Each skill has its own list of banned jargon and required tone.
- Each skill names the *one thing* the audience needs to leave with.

**See:** [`examples/parent-update.md`](../examples/parent-update.md) and [`examples/teacher-coaching-note.md`](../examples/teacher-coaching-note.md)

---

## Pattern 4 — The "IEP goal generator"

**When to use:** behavioral IEP goals get rewritten every annual review. They have a strict grammar (condition, behavior, criterion) and need to be measurable.

**Shape of the skill:**
- Trigger phrases include "write a goal for [student]," "draft IEP goals," "annual goal for behavior."
- Body enforces **the IEP goal grammar**: Given [condition], [student] will [observable behavior] [criterion] across [number] of [opportunities] for [duration].
- Body requires baseline data referenced in the goal (otherwise the goal is unmeasurable).
- Body produces 2–3 short-term objectives that scaffold to the annual goal.

**See:** [`examples/iep-behavioral-goal.md`](../examples/iep-behavioral-goal.md)

---

## Pattern 5 — The "treatment integrity / fidelity check"

**When to use:** when you're verifying whether an intervention is being implemented as designed, especially during teacher coaching.

**Shape of the skill:**
- Trigger phrases include "fidelity check," "treatment integrity," "is the BIP being implemented."
- Body builds a **simple checklist from the intervention's documented steps**.
- Body produces a single coaching point — not a list of 12 corrections — based on what's most likely to move outcomes.
- Body keeps the tone collaborative ("Let's try X next time"), never punitive.

**See:** [`examples/teacher-coaching-note.md`](../examples/teacher-coaching-note.md) (this example combines fidelity check + coaching note)

---

## Pattern 6 — The "case file orchestrator"

**When to use:** for ongoing cases where you want Claude to *find and load the right case folder* before doing anything else.

**Shape of the skill:**
- Trigger phrases include the per-client folder convention you use (e.g., "for J.M.'s case," "case file for Jordan").
- Body tells Claude: "before drafting, read these files in the case folder: latest FBA, current BIP, last 3 session notes." (Names of files match your folder convention.)
- This pattern stacks with the others — the case-file orchestrator runs first, then a content skill (FBA, parent update) runs second.

**Note:** this depends on your client folder convention. If you already have one, build the orchestrator around it.

---

## Quick anti-patterns to avoid

- **Skill explosion.** Don't write 40 micro-skills. Aim for ~8–12 that cover most of your weekly work.
- **One skill per student.** No. One skill per *type of task*. Student-specific info goes in their case folder.
- **The "smart" mega-skill.** No skill should branch on "if the user wants A, do this; if they want B, do that." Split it.
- **Skipping the description rewrite.** Names and bodies are easy. Descriptions are where skills live or die. Spend the time.

---

## A starter portfolio — which 8 should you build first?

If you want a starter set that covers ~80% of school-based ABA consultation, build these:

1. `fba-quickstart` — start a new FBA.
2. `bip-drafter` — turn a completed FBA into a BIP.
3. `iep-behavioral-goal` — draft annual goals + objectives.
4. `abc-analyzer` — interpret ABC data into a hypothesis.
5. `parent-update-drafter` — biweekly family communication.
6. `teacher-coaching-note` — post-observation feedback note.
7. `manifestation-determination-helper` — for disciplinary referrals.
8. `progress-monitoring-summary` — quarterly data summary for the team.

The five examples in this repo cover the most-used four. The others follow the same patterns.

---

**Next:** [Lesson 5 — Installing and sharing skills](05-installing-skills.md)
