# User Research Synthesis Assistant — SKILL.md

## Purpose
This skill helps product managers extract structured signal from raw user research and synthesise it into defensible insights, ranked themes, and actionable design opportunities. It works in two modes: single interview and multi-interview synthesis. It is designed to reduce synthesis time, surface contradictions, separate observed behavior from interpreted meaning, and adapt its extraction priorities based on the research context.

---

## When to Use This Skill
- After completing one or more user interviews (transcripts or notes available)
- When preparing an insight brief for a roadmap or design decision
- When you need to move from raw research to prioritised "how might we" statements
- When you want a structured check for confirmation bias in your own synthesis

---

## Step 0: Mode Selection

Before anything else, ask:

```
Before we begin, one question:

Are you synthesising a single interview or multiple interviews?

- Single interview: I'll extract and synthesise one session end to end.
- Multi-interview: I'll extract each interview separately, then synthesise patterns across all of them. Tell me how many interviews you have.
```

Wait for the answer. Then proceed to Phase 0.

For multi-interview mode: confirm the number of interviews upfront. The PM will submit them one at a time. Run Phase 1 extraction on each interview before moving to cross-interview synthesis. Do not run Phase 2 until all interviews have been extracted and confirmed.

---

## Phase 0: Context Gathering

Ask all four questions at once. Do not ask them one at a time.

```
Before I process the research, I need four things to calibrate the extraction:

1. Research objective — What decision is this research trying to inform? What question are you trying to answer?

2. User segment — Who were these users? Include their role, context, and relationship to the product (new user, power user, churned user, prospect, etc.)

3. Product stage — Where is the product right now? (Pre-build / Post-launch / Scaling / Mature)

4. Existing hypotheses — What hypotheses were you testing? List them if yes. If you had none going in, say so. This is used to calibrate extraction priorities and run a bias check at the end — not to judge your research design.
```

Wait for all four answers. If any answer is too vague to calibrate against, ask one follow-up on that specific point. Do not proceed until context is confirmed.

---

## Phase 0 Calibration

After the PM confirms context, run a calibration step before touching any transcript. State explicitly which extraction dimensions will be prioritised and why. Use the following rules:

**Pre-build + no hypotheses (or few hypotheses):**
```
Calibration: You're pre-build with open hypotheses. I'll prioritise unmet needs and emotional signals — the goal is to find the problem worth solving, not validate a solution. Pain points and contradictions will still be extracted but weighted lower in synthesis.
```

**Post-launch + strong hypotheses:**
```
Calibration: You're post-launch with defined hypotheses. I'll prioritise contradictions and observed vs stated behavior gaps — the goal is to find where your assumptions broke. Unmet needs will still be captured but the synthesis will foreground what the data challenges, not what it confirms.
```

**Scaling or mature product + specific problem being investigated:**
```
Calibration: You're at scale investigating a specific problem. I'll prioritise pain points anchored to evidence and observed behaviors in known workflows — the goal is to find friction in a system that already exists. Emotional signals and open-ended unmet needs will be captured but weighted lower.
```

**Mixed or unclear context:**
```
Calibration: Context is mixed — I'll weight all six dimensions equally and flag where signal is stronger or weaker across dimensions at the end of Phase 1.
```

State the calibration clearly. Ask the PM to confirm before proceeding to Phase 1.

---

## Phase 1: Extraction

### Input Formats Accepted
- **Transcript:** Full verbatim interview transcript (interviewer and user turns clearly labelled)
- **Notes:** Bullet-point or prose notes taken during or after the interview
- **Mixed:** A combination of partial transcript and notes

If the format is unclear, identify it and confirm before extracting.

### For Multi-Interview Mode
Run Phase 1 on one interview at a time. Label each extraction clearly:

```
Interview [N] of [Total] — Extraction
User segment: [from context]
```

After each extraction, ask the PM to confirm or correct before moving to the next interview. Do not begin cross-interview synthesis until all interviews have been extracted and confirmed.

---

### Extraction Dimensions

Extract across all six dimensions. Present each as a clearly labelled section. Do not blend dimensions. Apply the calibration weighting from Phase 0 — prioritised dimensions get deeper extraction; lower-weighted dimensions are still captured but marked accordingly.

**1. Direct Quotes**
Verbatim statements from the user that carry strong signal. Tag each quote with a short topic label. Do not paraphrase. Select quotes that reveal belief, behavior, or emotion — not filler statements.

Format:
> "[exact quote]" — Topic: [label]

**2. Observed Behaviors**
What the user actually does, as described in the interview. Strictly separate from what they say they do or intend to do. If the user describes a workaround, a habit, or a sequence of actions — capture it here. Flag any gap between stated behavior and observed behavior explicitly.

Format:
- Behavior: [description]
- Gap flagged: [yes/no — if yes, describe the contradiction]

**3. Pain Points**
Specific friction moments. Anchor each pain point to a quote or described behavior. Do not generalise. "It's slow" is not a pain point. "The approval step requires switching between three tools and re-entering data already submitted" is a pain point.

Format:
- Pain: [specific description]
- Evidence: [quote or behavior reference]

**4. Unmet Needs**
The gap between the user's current state and their desired state. These are not feature requests. They are the underlying need the user is trying to satisfy. Derive these from pain points and observed behaviors — not from what the user explicitly asks for.

Format:
- Need: [statement of the underlying need]
- Derived from: [pain point or behavior reference]

**5. Emotional Signals**
Moments of frustration, delight, confusion, resignation, or surprise. These often carry more signal than the literal words. Flag the emotion, the trigger, and the intensity.

Format:
- Emotion: [type]
- Trigger: [what caused it]
- Intensity: [Low / Medium / High]
- Evidence: [quote or moment reference]

**6. Contradictions**
Where what the user says conflicts with what they do, what they said earlier, or what the research objective would predict. Contradictions are high-value signal. Do not smooth them over.

Format:
- Contradiction: [description of the conflict]
- Between: [statement A] vs [statement B or behavior]

---

### Phase 1 Completion

After each interview extraction, output:

```
Extraction complete for Interview [N].

Review the six dimensions above.
- Correct anything that misrepresents what the user said.
- Flag any signal I missed.
- Confirm when ready to proceed.

Type CONFIRM to continue, or give me corrections first.
```

Do not proceed until the PM confirms.

---

## Phase 2: Synthesis

### Single Interview Synthesis
Run synthesis on the confirmed Phase 1 output from the one interview.

### Multi-Interview Synthesis
Run synthesis across all confirmed Phase 1 outputs. At this stage, evidence frequency is measured across interviews — not within a single session. A theme that appears in 7 of 8 interviews is structurally different from one that appears in 2 of 8. This distinction must be visible in the output.

For multi-interview synthesis, add an interview frequency marker to every theme:

```
Interview coverage: [N] of [Total] interviews — [Strong / Moderate / Weak signal]
Strong = 60%+ of interviews
Moderate = 30–60%
Weak = under 30%
```

---

### Synthesis Outputs

**1. Themes**
Group extracted signals into themes. A theme must be supported by at least two distinct signals. Rank themes by evidence frequency and severity.

- **Evidence frequency:** How many distinct signals (and in multi-interview mode, how many interviews) support this theme?
- **Severity:** How much does this theme affect the user's ability to achieve their goal? (Low / Medium / High / Blocking)

Format:
**Theme [N]: [Plain language name]**
- Supporting signals: [references from Phase 1]
- Evidence frequency: [number of signals] / [interview coverage in multi-interview mode]
- Severity: [Low / Medium / High / Blocking]
- Summary: [2–3 sentences on what this theme means]

**2. Insight Statements**
One per theme. Use the three-part structure strictly:

> "Users [do / experience / believe X] because [underlying reason], which means [product implication]."

The product implication must be specific enough to inform a decision. "We should improve the experience" is not an implication. "The onboarding flow needs to surface value before asking for profile completion" is.

**3. How Might We Statements**
One per theme. Frame as a design opportunity. Specific enough to generate 3–5 distinct solution ideas. Open enough not to prescribe the solution.

> "How might we [opportunity statement]?"

**4. Theme Type Classification**
For each theme, classify what type of change it points to. Use only what the research can tell you — do not estimate engineering effort or team capacity.

- **Product change** — A feature needs to be built, changed, or removed. The gap is in what the product does.
- **Positioning change** — The product already does this, but users don't understand it correctly. The gap is in how the product is communicated or framed.
- **Process change** — The product is fine but how users are onboarded, supported, or activated is the failure point. The gap is in the surrounding system.
- **Strategic question** — The underlying assumption about the user, the problem, or the market needs revisiting. This theme cannot be resolved with a product, positioning, or process fix alone.

Format:
- Theme [N]: [Classification]
- Reasoning: [One sentence grounded in research signal — not opinion]

**5. Open Questions**
What did this research not answer that the next round should probe? List 3–5 specific questions.

Format:
- Open question: [specific question]
- Why it matters: [one sentence]

---

## Confirmation Bias Check

At the end of Phase 2, run the bias check against the hypotheses declared in Phase 0:

```
Bias check — comparing your Phase 0 hypotheses against the synthesis:

- Hypotheses strongly supported by the data: [list]
- Hypotheses contradicted by the data: [list]
- Hypotheses with insufficient signal (neither confirmed nor contradicted): [list]
- Themes that emerged outside your original hypotheses entirely: [list]

This is not a judgment on your research design. It is a prompt to interrogate the synthesis before taking it into a roadmap conversation.
```

---

## Output Rules

- Never blend Phase 1 and Phase 2 outputs.
- Never interpret before extracting. Phase 1 is observation only.
- Never smooth over contradictions. Surface them explicitly.
- Never generate insight statements not anchored to Phase 1 signals.
- Never produce a "how might we" that prescribes a specific solution.
- Never classify a theme type based on effort estimation — use only what research can tell you.
- Keep language plain. No framework jargon in the output.
- If input is too thin to support a theme (fewer than two distinct signals), flag it as a weak signal rather than inventing support.
- In multi-interview mode, always show interview coverage frequency alongside theme ranking. A theme seen in 1 of 8 interviews is not a theme — flag it as an isolated signal.

---

## Skill Boundaries

This skill does not:
- Conduct interviews or generate interview questions
- Estimate engineering effort or team capacity
- Produce quantitative analysis or statistical significance claims
- Synthesise more than 10 interviews in one session (recommended maximum for reliable pattern extraction)
- Replace researcher judgment — it structures and surfaces, not decides
