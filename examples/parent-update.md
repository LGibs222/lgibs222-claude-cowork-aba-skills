---
name: parent-update-drafter
description: |
  Draft a 1-2 week parent/caregiver update for a school-based ABA case. Translates clinical progress into plain language, leads with strengths, and ends with a clear suggestion the family can try.
  TRIGGER when the user says: "parent update", "weekly note for the family", "summary for [child]'s parents", "biweekly update for caregivers", or asks to translate progress notes into something parent-friendly.
  SKIP when: writing internal clinical notes (use session-note), drafting a formal IEP progress report (use iep-progress-report), or composing a difficult-conversation document about regression or major incidents (use family-incident-letter).
type: skill
---

# Parent Update Drafter

## Audience
Parent / primary caregiver. Reading level: 6th–8th grade.

## Output structure

1. **Greeting** — by first name, warm but professional.
2. **What we worked on this period** — 1–2 sentences. Plain language, no jargon.
3. **What went well** — at least one specific moment or data point. Strengths-first.
4. **What's still hard** — honest, not alarming. Frame as "what we're working on next."
5. **One thing to try at home** — exactly ONE strategy, concrete and short.
6. **Close** — invite questions, give a check-in date or next-meeting time.

## Tone rules
- Reading level: 6th–8th grade. Sentences average 15 words or fewer.
- Strengths-first: the first content sentence after the greeting is positive.
- Replace clinical jargon with everyday equivalents:
  - "aggression" → "hitting and pushing"
  - "elopement" → "leaving the area without permission"
  - "DRA / DRO" → "rewarding the helpful behavior we want to see more of"
  - "extinction" → "not giving the behavior the response it usually gets"
  - "antecedent intervention" → "changing what we set up before the activity"
  - "first/then board" → keep as is, parents typically know it
- Never use the words "noncompliance," "manipulative," "attention-seeking," or "extinction" in this document.
- Do not include data points without a plain-language interpretation ("Jordan was on-task for 47% of math intervals" → "Jordan stayed focused during about half of his math time, which is up from a third last month").

## Ask before drafting
- Child's first name (or initials if confidentiality is preferred).
- Date range covered.
- 1–2 specific things that happened this period (a moment of progress, a tough day).
- Anything sensitive the family already knows — or DOESN'T know — about.
- Date of next check-in or IEP meeting.

## Do not
- Lead with what's hard.
- Recommend more than one home strategy in a single update — families don't have bandwidth for three things.
- Use percentages or rates without a plain-language interpretation.
- Reference clinical frameworks the family hasn't been oriented to (don't drop "function-based intervention" or "differential reinforcement" into the body without explanation).
- Make promises about timelines ("Jordan will be hitting goals by spring" is not appropriate).

## Format
Plain prose, no Markdown headings unless explicitly requested. 1 page maximum. If the update is going by email, format it as the email body — no extra signoff beyond the close.
