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
  Outputs two Markdown files next to the manuscript: an English evaluation report
  and a student-facing summary (Korean by default, telegraphic style).
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

This skill produces **two deliverables**, both saved as Markdown files (see
"Output format"):

1. **Evaluation report** — always written in **English**, regardless of the language
   the user is communicating in.
2. **Student summary** — a short hand-off version for the author. Written in
   **Korean** unless the user explicitly specifies another language, in the
   telegraphic style described under "Student summary style".

In both files keep the priority tags `[CRITICAL]/[MAJOR]/[MINOR]` and technical terms
in English. Chat replies to the user follow the user's own language.

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

Always produce **both** files below and save them next to the manuscript (same folder
as the input file). Do not merely print them in chat; after saving, give the user a
brief summary of the verdict and the file paths.

| Deliverable | File name | Language |
|---|---|---|
| Evaluation report | `<manuscript-name>_evaluation.md` | English (always) |
| Student summary | `<manuscript-name>_evaluation_student_summary.md` | Korean by default; another language only if the user specifies one |

If the user asks to regenerate or translate one of the files, overwrite that file
only and leave the other untouched.

### 1. Evaluation report (English)

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
[Recommendation + 1-2 sentence justification tied to the findings,
 followed by a recommended revision order]
```

Start the file with a short metadata list (manuscript file name, evaluation framework,
and any caveats such as "venue page limit/template not verified"). If numbers in the
manuscript were cross-checked, say so. Number the Major/Minor items continuously
(1, 2, 3, …) so the student summary can refer to them as `#n`.

### 2. Student summary (Korean by default)

A one-page hand-off for the student, derived from the evaluation report. It must not
introduce findings that are absent from the report; item numbers (`#n`) must match
the report.

```markdown
# <Venue/Year> 원고 피드백 요약 (학생 전달용)

**논문**: [title]
**상세 평가**: `<manuscript-name>_evaluation.md` (번호는 상세 평가서의 항목 번호와 동일)

## 한 줄 총평
[Verdict (Major Revision etc.), the main reason, and expected effort — as 3-4 bullets]

## 잘한 점 (유지할 것)
[Strengths, one bullet each]

## 반드시 고칠 것 (Major, 우선순위 순)
[Numbered; each item: bold topic + (#n), then sub-bullets for the problem and the action]

## 다듬을 것 (Minor)
[One bullet per item with (#n)]

## 수정 일정 (제안)
[Table: week | tasks — sized to the actual amount of work]

## 다음 미팅 논의 사항
[Decisions the student and advisor must make together]
```

#### Student summary style (telegraphic / 개조식)

Write every sentence in the telegraphic style — noun-ending or short "~함/~됨/~임"
and "~할 것" endings — instead of polite or imperative sentence endings.

- Actions and requests: end with **"~할 것"** (e.g., "그래프 작성할 것",
  "차단주파수를 명시할 것").
- Observations and facts: end with **"~함", "~됨", "~임"** or a noun (e.g.,
  "서사가 일관됨", "재현성이 높음", "비교가 불공정할 수 있음").
- Do **not** use "~하세요", "~합니다", "~입니다", "~좋습니다", "~바랍니다",
  "~해 주세요" or similar polite/imperative endings anywhere in the file.
- Prefer short bullets over long sentences; split a sentence rather than chaining
  clauses.
- If the user requests another language, apply the same terse, list-style tone in
  that language.

Before saving, scan the summary once for forbidden endings and fix any that remain.
