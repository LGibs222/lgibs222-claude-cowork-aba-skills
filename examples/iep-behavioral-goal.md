---
name: iep-behavioral-goal
description: |
  Draft a measurable annual IEP goal and 2-3 short-term objectives for a behavioral or social-emotional concern, aligned to NY IEP grammar (condition / behavior / criterion).
  TRIGGER when the user says: "write a behavior goal for [student]", "draft an IEP goal", "annual goal for [target behavior]", "behavioral goal", "social-emotional goal", or asks to convert an FBA hypothesis into an IEP goal.
  SKIP when: writing academic goals (this skill is for behavior/SEL only), drafting a full BIP (use bip-drafter), or rewriting a goal that already exists in compliant form (use goal-revision).
type: skill
title: IEP Behavioral Goal
parent: Examples
nav_order: 3
---

# IEP Behavioral Goal Drafter

## Audience
IEP team, parent committee, district compliance reviewers.

## Required grammar
Every annual goal MUST contain all four parts in this order:

1. **Condition** — "Given [setting/support/prompt]…"
2. **Student** — "[student name or 'the student'] will…"
3. **Observable behavior** — operationalized, no inference verbs.
4. **Criterion** — measurable accuracy / frequency / duration AND across how many opportunities, sessions, or settings.

Example template:
> Given [condition], [student] will [observable behavior] [criterion] across [N] of [M] [opportunities/sessions/settings] as measured by [data source].

## Output structure
Produce:

1. **Baseline statement** — current performance in observable terms, with date and source. If user didn't provide baseline, ask for it before drafting.
2. **Annual goal** — one paragraph using the grammar above.
3. **2–3 short-term objectives** — scaffolded steps that build to the annual goal. Each follows the same grammar with a lower criterion.
4. **Measurement plan** — what data, how often, by whom.

## Required guardrails
- Behavior must be **observable**: replace "will be respectful" with "will use a quiet voice," "will keep hands to self," etc.
- Criterion must be **measurable** with a number.
- The goal must be reachable within one academic year given the baseline (don't write goals so ambitious they set the student up to fail).
- Short-term objectives should reflect a logical progression — not three identical goals at slightly different criteria.

## Ask the user before drafting
- Student grade and IDEA classification.
- The target behavior (observable, not "is disrespectful").
- Current baseline data (frequency, duration, percent accuracy — whatever fits).
- Setting(s) the goal applies to.
- Whether this is replacing an existing goal (so you can match its data conventions).
- Whether there's an FBA on file with a hypothesized function (so the replacement behavior can be function-based).

## Do not
- Use vague verbs: be, understand, know, appreciate, demonstrate awareness of, show respect.
- Write criteria without a number ("will improve").
- Omit the data source.
- Combine two distinct behaviors in one goal — split into two goals.
- Write a goal whose replacement behavior doesn't match the FBA hypothesis (if an FBA exists).

## Format
Plain prose. Use a Markdown heading for each of the four output sections (Baseline, Annual Goal, Short-Term Objectives, Measurement Plan).
