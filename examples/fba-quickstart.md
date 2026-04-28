---
name: fba-quickstart
description: |
  Draft a NYSED Part 200-aligned Functional Behavior Assessment (FBA) for a K-12 student in NY schools.
  TRIGGER when the user says: "start an FBA for [student]", "write an FBA", "draft FBA", "begin a functional behavior assessment", or pastes ABC/indirect/descriptive data and asks for an FBA write-up.
  SKIP when: updating an already-completed FBA (use fba-revision), drafting a BIP from a completed FBA (use bip-drafter), or producing a parent-facing summary of behavior (use parent-update-drafter).
type: skill
title: FBA Quickstart
parent: Examples
nav_order: 1
---

# FBA Quickstart — School-Based ABA, NY

## Audience
Special education team and IEP committee. NOT parent-facing language.

## Required structure
Produce the FBA in this exact order:

1. **Student & Setting Background**
   - Student grade level, IDEA classification (if shared), and educational setting.
   - Brief description of the referral concern.

2. **Operational Definition of Target Behavior**
   - Observable, measurable terms only.
   - Include topography (what it looks like), intensity, and any commonly co-occurring behaviors.
   - DO NOT use "noncompliance," "defiance," "disrespect," "attitude," or "disruption" as target behaviors. Operationalize what those look like.

3. **Indirect Assessment Summary**
   - Name the data source(s): record review, FAST, MAS, QABF, teacher/parent interview.
   - Summarize what each contributed to hypothesis formation.

4. **Descriptive Assessment Summary**
   - Direct observations across at least 2 settings or 2 time points.
   - Note time of day, activity, who was present, antecedent context.

5. **ABC Data Summary**
   - Table format if 3+ incidents.
   - Columns: Date/Time, Setting, Antecedent, Behavior, Consequence, Hypothesized Function.
   - Minimum 5 incidents to justify a hypothesized function.

6. **Hypothesized Function**
   - One of: Escape/Avoidance, Attention, Tangible/Activity, Automatic (sensory).
   - State the evidence supporting the hypothesis (which data point pattern leads here).
   - If data are insufficient (<5 incidents or contradictory patterns), say so explicitly and recommend further data collection rather than forcing a hypothesis.

7. **Function-Based Recommendations**
   - Exactly 3 recommendations, each explicitly tied to the hypothesized function.
   - Each recommendation includes: what to do, who does it, when/how often, how it addresses the function.

8. **Data Collection Plan Going Forward**
   - At least one ongoing measurement procedure (frequency, duration, interval).
   - Frequency of progress review (typical: every 2–4 weeks).

## Ask the user before drafting
- Student grade and IDEA classification.
- Available data sources (paste raw ABC, attach FAST/QABF results, share interview notes).
- Setting(s) where the behavior occurs.
- Existing behavior goals on the IEP, if any.
- Anything sensitive the family or team has flagged.

## Do not
- Use stigmatizing or judgmental language ("attention-seeking" → "attention-maintained"; "manipulative" → never).
- Recommend interventions that don't connect to the hypothesized function.
- Skip the data collection plan section.
- Pretend to a confident hypothesis when the data are thin — flag the gap.
- Include parent-facing language; this is a clinical document.

## Format
- Use Markdown headings matching the section names above.
- ABC summary as a Markdown table.
- Keep total length 2–4 pages of plain prose plus the ABC table.
