---
name: abc-analyzer
description: |
  Analyze raw ABC (Antecedent-Behavior-Consequence) data and produce a clinical interpretation with a hypothesized function and next-step recommendations.
  TRIGGER when the user says: "analyze this ABC data", "what's the function here", "interpret these ABC incidents", "what does this trend tell us", or pastes a list of ABC incidents and asks for analysis.
  SKIP when: the user wants a full FBA write-up (use fba-quickstart), wants graphing of frequency/duration data only with no ABC content (use data-graph), or wants a parent-facing summary (use parent-update-drafter).
type: skill
title: ABC Analyzer
parent: Examples
nav_order: 2
---

# ABC Data Analyzer

## Audience
Clinical team — BCBA, school psych, special ed teacher. Use clinical language.

## Output structure

1. **Data summary** — number of incidents, date range, settings represented. Flag any gaps (e.g., "all incidents from morning, none from afternoon").

2. **Patterns by Antecedent**
   - Group incidents by antecedent type (transition, demand, denied access, unstructured, peer interaction, etc.).
   - Note frequency of each.

3. **Patterns by Consequence**
   - Group by what followed the behavior (escape from task, adult attention, peer attention, tangible access, sensory regulation, etc.).
   - Note frequency of each.

4. **Hypothesized function**
   - One of: Escape/Avoidance, Attention, Tangible/Activity, Automatic.
   - State explicitly which antecedent + consequence pattern supports the hypothesis.
   - If multiple functions appear, name them and note which is dominant.
   - **If <5 incidents OR contradictory patterns:** state that the data are insufficient for a confident hypothesis. Recommend specific additional data collection rather than guessing.

5. **Recommendations**
   - 2–3 recommendations tied directly to the hypothesized function.
   - Each is a single concrete action — not a category ("teach replacement behavior" is not a recommendation; "teach a hand-raise to request a break during math demands" is).

6. **What to watch for**
   - Specific patterns that would change the hypothesis (e.g., "if behavior decreases when peer is removed but not when demand is removed, function may be peer attention rather than escape").

## Hard constraints

- Never claim a confident function with fewer than 5 incidents. Say so explicitly.
- Never include recommendations disconnected from the function you hypothesized.
- Never describe behavior in inference-laden language ("was being defiant"). Quote/paraphrase the topography.
- Never minimize when data show a behavior is intensifying — flag it directly.

## Ask the user before analyzing
- Date range of the data.
- Settings represented (and any setting NOT represented).
- Any other context the user thinks matters (recent transitions, medication changes, schedule shifts).

## Format
Markdown headings for each section. Use a small table if grouping by antecedent or consequence makes the patterns clearer.
