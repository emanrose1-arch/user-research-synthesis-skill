# User Research Synthesis Assistant

A Claude skill that helps product managers extract structured signal from raw user interviews and synthesise it into defensible insights, ranked themes, and actionable design opportunities. Works across single interviews and multi-interview synthesis sessions.

---

## The Problem

Most PM synthesis is fast and biased. You finish 8 interviews, spend an afternoon in a doc, and produce an insight brief that largely reflects the hypotheses you walked in with. The quotes that confirmed your thinking made it in. The contradictions got smoothed over. The emotional signals never made it to paper, like the resignation in someone's voice when they described their workaround.

Worse: a theme that appeared in 2 of 8 interviews gets equal weight to one that appeared in 7, because there's no structured way to track cross-interview frequency when you're working manually.

This skill is designed to fix both problems.

---

## How It Works

The skill runs across four phases with explicit checkpoints between each.

**Step 0: Mode Selection**
Single interview or multi-interview. Multi-interview mode runs Phase 1 extraction on each interview separately before any cross-interview synthesis begins. Themes are then weighted by how many distinct interviews they appear in. A theme from 7 of 8 interviews is structurally different from one that appears in 2.

**Phase 0: Context + Calibration**
Four calibrating questions before any transcript is touched: research objective, user segment, product stage, and existing hypotheses. Based on the answers, the skill runs a calibration step that explicitly states which extraction dimensions it will prioritise and why.

Three calibration modes:
- Pre-build with open hypotheses → weight unmet needs and emotional signals
- Post-launch with strong hypotheses → weight contradictions and observed vs stated behavior gaps
- Scaling or mature product with a specific problem → weight pain points anchored to evidence

The calibration is stated explicitly and confirmed before extraction begins. The PM knows exactly what lens the skill is applying before it touches the data.

**Phase 1: Extraction**
Six dimensions, kept strictly separate:
- Direct quotes (verbatim, tagged by topic)
- Observed behaviors (separated from stated behaviors)
- Pain points (anchored to evidence, not generalised)
- Unmet needs (derived from behavior, not feature requests)
- Emotional signals (frustration, delight, confusion, resignation — with intensity)
- Contradictions (where what the user says conflicts with what they do)

The PM reviews and confirms or corrects Phase 1 before synthesis runs. In multi-interview mode, each interview is extracted and confirmed separately.

**Phase 2: Synthesis**
Runs only on confirmed extraction. Produces:

- Themes ranked by evidence frequency and severity. In multi-interview mode, each theme shows interview coverage (e.g. "6 of 8 interviews : Strong signal").
- Insight statements in a strict three-part structure: "Users [X] because [Y], which means [Z]."
- How Might We statements framed as design opportunities.
- Theme Type Classification — what the research actually tells you about the nature of the change needed: product change, positioning change, process change, or strategic question. No effort estimation. Only what the research can answer.
- Open questions for the next research round.
- A confirmation bias check against the hypotheses declared in Phase 0.

---

## Why Theme Type Classification Instead of Impact vs Effort

Most synthesis tools try to estimate effort. Claude has no basis for that. it doesn't know your team size, tech stack, or quarterly capacity. Effort estimates from a synthesis tool are noise.

What research can tell you is the type of change a theme demands. A theme pointing to a positioning change needs a different conversation than one pointing to a product change — even if both are "high severity." Getting that classification right before walking into a roadmap meeting is worth more than a guess at effort.

---

## Why the Phased Design with Checkpoints

Single-pass synthesis tools produce outputs that feel structured but aren't trustworthy. extraction and interpretation happen simultaneously, with no checkpoint for the PM to catch errors. The three-phase design forces a separation between observation and interpretation that mirrors how rigorous researchers actually work.

The confirmation bias check exists because the most dangerous insight brief is one that's well-formatted and wrong.

---

## Input Formats

- Full verbatim transcript
- Bullet-point or prose notes
- Mixed (partial transcript + notes)
- Up to 10 interviews per multi-interview synthesis session

---

## What This Skill Does Not Do

- Conduct interviews or generate interview questions
- Estimate engineering effort or team capacity
- Produce quantitative claims or statistical significance
- Replace researcher judgment. it structures and surfaces, not decides

---

## Usage

1. Load SKILL.md into a Claude Project or paste as a system prompt
2. State whether you're doing single or multi-interview synthesis
3. Answer the four context questions in Phase 0
4. Review the calibration the skill proposes — confirm or adjust
5. Submit your transcript or notes (one interview at a time in multi-interview mode)
6. Review and confirm Phase 1 extraction before synthesis runs
7. Use Phase 2 output directly in your insight brief or roadmap prep
