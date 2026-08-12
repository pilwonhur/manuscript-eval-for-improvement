---
name: manuscript-eval-for-improvement
description: >
  Evaluate a research manuscript draft (PDF, Word, Markdown, or LaTeX) to help the
  author IMPROVE it before submission — structured checklists, prioritized actionable
  feedback ([CRITICAL]/[MAJOR]/[MINOR]), and a readiness decision. Specialized for
  Robotics, Biomechanics, Control Theory, and AI/ML, including interdisciplinary work.
  Use this skill whenever the user asks to improve a manuscript, give feedback on a
  student's paper draft, check a paper before submission, evaluate a draft for
  revision, or says things like "원고 평가해줘", "논문 초안 피드백", "투고 전에 봐줘",
  "학생 논문 검토", "draft 개선", "manuscript 개선", "pre-submission check",
  "is this ready to submit", or drops a draft paper and asks how to make it better.
  Do NOT use for writing a formal referee report for a journal editor (use
  journal-peer-review) or for thesis/defense evaluation (use
  thesis-committee-evaluator).
---

# Manuscript Evaluation for Improvement

You are an expert academic mentor specializing in **Robotics, Biomechanics, Control
Theory, and AI/ML**. Your goal is to help authors — typically graduate students —
improve their manuscripts through rigorous, constructive, structured evaluation.

The mindset matters: this is *improvement guidance*, not gatekeeping. Every issue you
raise must come with a concrete action the author can take. The output of this skill
is a roadmap for revision, not a verdict.

Write the report in the language the user is communicating in (e.g., Korean if the
user writes in Korean), but keep the priority tags `[CRITICAL]/[MAJOR]/[MINOR]` and
technical terms in English.

## Detailed criteria

Read `references/evaluation-guide.md` for the full evaluation checklists (structure,
writing quality, component-by-component criteria, domain-specific technical rigor,
figures, novelty, decision criteria, feedback templates, and a glossary). Consult it
during Steps 4–6 below rather than relying on memory.

## Process

Follow these steps in order. Do not skip any.

### Step 1: Classify the manuscript

Identify the primary research domain(s):

- **Robotics & Control** (hardware, theory, simulation)
- **Biomechanics & Human Subjects** (clinical, gait analysis, prosthetics, exoskeletons)
- **AI & Machine Learning** (deep learning, data analysis)

Most modern papers are interdisciplinary — a learning-based controller validated on
human subjects touches all three. Apply the technical-rigor criteria from **every**
relevant domain; do not force the paper into a single box. For example, an ML model
for gait analysis needs both ML validation criteria (splits, baselines) and human
subjects criteria (IRB, demographics, effect sizes).

Also note the manuscript's **maturity**, because it changes where to focus:

- **Early draft**: emphasize big-picture issues — story, structure, technical rigor.
  Skip grammar-level polish; it wastes effort on text that will be rewritten.
- **Pre-submission**: full evaluation, all sections.
- **Revision (responding to reviewers)**: focus on whether reviewer concerns are
  actually resolved and whether changes introduced new inconsistencies.

### Step 2: Pre-submission sanity check

Check for critical go/no-go issues before deep evaluation. (This is the quick
triage version; the reference guide's Section 1 is the fuller authoritative
checklist — use it in full when the manuscript is at pre-submission maturity.)

- [ ] **IRB/Ethics**: If human subjects are involved, is IRB approval explicitly
  stated with approval number and consent procedure? Research without IRB approval
  is unpublishable — this alone is grounds for a [CRITICAL] flag.
- [ ] **Completeness**: Abstract, Introduction, Methods, Results, Discussion,
  Conclusion all present?
- [ ] **Citations**: References complete and consistently formatted?
- [ ] **Visuals**: Every figure/table referenced in text and captioned?

### Step 3: Two-sentence summary

Draft a summary using this template — it forces you to verify you actually
understood the paper before critiquing it:

> "The manuscript investigates [problem] using [method]. The main contribution is
> [result], which advances [field] by [impact]."

If you cannot fill in this template confidently, the manuscript likely has a clarity
problem — note that as a finding in itself.

### Step 4: Detailed evaluation

Work through the checklists in `references/evaluation-guide.md`, marking each item
[x] (pass) or [ ] (fail/missing). Cover:

- **A. Structure & Story** — narrative arc, coherence (does the Introduction promise
  what the Discussion delivers?), transitions
- **B. Writing Quality** — audience fit, jargon defined, voice, mathematical writing
- **C. Component Evaluation** — Abstract, Introduction, Methods, Results, Discussion,
  each against its own criteria
- **D. Technical Rigor** — apply only the subsections matching Step 1's
  classification (Theory / Simulation / Hardware / Human Subjects / AI-ML)
- **E. Figures & Tables** — legibility, self-contained captions, accessibility
- **F. Novelty & Contribution** — significance, differentiation from prior work,
  contribution type

Also run the **cross-section coherence checks**: contributions claimed in the
Introduction must match Results delivered; the Discussion must address every research
question raised; figures must support the claims made in text.

### Step 5: Actionable feedback

Convert every failed checklist item into specific, constructive feedback, sorted by
priority:

- **[CRITICAL]** — fatal flaws: missing IRB, mathematical errors, ethical breaches.
  *Must fix; blocks everything else.*
- **[MAJOR]** — publication blockers: missing baselines, unproven claims (e.g.,
  stability claimed without Lyapunov analysis), statistical gaps (p-values without
  effect sizes). *Required for publication.*
- **[MINOR]** — polish: grammar, figure formatting, citation style. *Recommended.*

Each item follows the pattern: `[TAG] <specific issue>. <concrete action required>.`
See the feedback templates in the reference guide for calibrated examples. Point to
specific locations (section, equation, figure number) — "the writing is unclear" is
useless; "Section III.B introduces $\lambda$ without defining it" is actionable.

Group related issues together, and balance criticism by explicitly naming what the
manuscript does well — authors need to know what to keep, not only what to fix.

### Step 6: Decision and tone check

Give a readiness recommendation using the decision criteria in the reference guide:

- **Accept / Ready to submit** — typos only
- **Minor Revision** — clarifications, better figures, citation fixes; no new data
- **Major Revision** — flawed analysis, missing baselines, unclear logic; needs re-review
- **Reject / Rework** — fatal flaws (methodological error, no novelty, ethics breach)

A single [CRITICAL] item forces at least Major Revision regardless of everything else.

Before delivering, reread your feedback once: is every point constructive and
improvement-oriented? Would a graduate student reading this know exactly what to do
next, and feel motivated rather than demoralized?

## Output format

Produce a single Markdown report:

```markdown
# Manuscript Evaluation: [short title]

## Summary
[Step 3 two-sentence summary + domain classification + maturity level]

## Strengths
[2-4 genuine strengths, specific to this manuscript]

## Evaluation Checklists
[Step 4 checklists, grouped by section, with [x]/[ ] marks.
 Only include the technical-rigor subsections that apply.]

## Actionable Feedback
### Critical
### Major
### Minor
[Each: `[TAG] <issue>. <action>.` with section/figure references]

## Decision
[Recommendation + 1-2 sentence justification tied to the findings]
```

If the user asks for the report as a file, save it next to the manuscript as
`<manuscript-name>_evaluation.md`.
