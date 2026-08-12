# Manuscript Improvement & Evaluation Guide

Detailed criteria for evaluating research manuscripts in **Robotics, Biomechanics,
Control Theory, and AI/ML**. Used by SKILL.md Steps 4–6.

## Contents

1. [Pre-Submission Checklist](#1-pre-submission-checklist)
2. [Structure & Organization](#2-structure--organization)
3. [Writing Quality](#3-writing-quality)
4. [Component Evaluation](#4-component-evaluation)
5. [Technical Rigor (Methodology-Specific)](#5-technical-rigor-methodology-specific)
6. [Figures, Tables, & Visualizations](#6-figures-tables--visualizations)
7. [References & Citations](#7-references--citations)
8. [Novelty & Contribution](#8-novelty--contribution)
9. [Cross-Section Coherence](#9-cross-section-coherence)
10. [Decision Criteria](#10-decision-criteria)
11. [Feedback Templates](#11-feedback-templates)
12. [Glossary](#12-glossary)

---

## 1. Pre-Submission Checklist

*Go/no-go items — check before deep evaluation.*

- [ ] **Formatting**: Adheres to target venue template (IEEE, ASME, etc.) and page limits.
- [ ] **Completeness**: All sections (Abstract to Conclusion) present.
- [ ] **Citations**: All references complete and consistently formatted.
- [ ] **Visuals**: All figures/tables referenced in text and captioned.
- [ ] **Ethics**: IRB/IACUC approval statements included (if applicable).
- [ ] **Authorship**: All contributors listed; author order agreed upon.
- [ ] **Integrity**: Plagiarism check passed; no inappropriate image manipulation
  (contrast adjustment is acceptable; adding/removing features is not).

---

## 2. Structure & Organization

*Ensure the manuscript tells a coherent story.*

- [ ] **Narrative Arc**: Clear "story" connecting the problem to the solution.
- [ ] **Coherence**: The Introduction promises what the Discussion delivers.
- [ ] **Transitions**: Paragraphs and sections transition logically.
- [ ] **Signposting**: Text guides the reader (e.g., "In the next section, we...").
- [ ] **Topic Sentences**: Each paragraph opens with a clear topic sentence; one idea
  per paragraph.

---

## 3. Writing Quality

*Clear communication is as important as technical rigor.*

### Clarity & Audience

- [ ] **Audience Appropriateness**: Technical level right for the target venue;
  enough background for non-specialists at interdisciplinary venues.
- [ ] **Jargon**: Technical terms defined on first use (e.g., "Lyapunov stability",
  "ablation study").
- [ ] **Conciseness**: Sentences direct (avoid "It is to be noted that...").
- [ ] **Voice**: Active voice for actions ("We designed..."); passive acceptable for
  methods ("Data were collected...").
- [ ] **Hedging**: "may/might/could" used deliberately, not as reflexive padding.

### Mathematical Writing

- [ ] **Notation**: Consistent symbols throughout (scalars $x$, vectors
  $\mathbf{x}$, matrices $\mathbf{X}$); no symbol overloading.
- [ ] **Definitions**: All variables defined immediately before or after first use.
- [ ] **Grammar**: Equations read as parts of sentences with proper punctuation.
- [ ] **Referencing**: Equations numbered and referenced as "(3)" per venue style.

---

## 4. Component Evaluation

*Evaluate the quality of each manuscript section.*

### Abstract

- [ ] **Hook**: Context/problem statement (1–2 sentences).
- [ ] **Gap**: What is missing in current knowledge?
- [ ] **Method**: High-level approach.
- [ ] **Results**: Key quantitative findings (specific numbers, not "significant improvement").
- [ ] **Conclusion**: Impact/takeaway.
- [ ] **Self-contained**: Readable without the full manuscript; no citations
  (standard in most engineering venues).

### Introduction

- [ ] **Funnel Structure**: Broad context → specific problem → proposed solution.
- [ ] **Gap Analysis**: Clearly identifies why existing solutions are insufficient.
- [ ] **Contributions**: Explicit list of contributions (bullets preferred), each
  specific and verifiable — and each actually delivered later in the paper.

### Methods

*Central question: can a peer reproduce this work?*

- [ ] **Detail**: Sufficient parameters, settings, and protocols provided.
- [ ] **Justification**: Why these specific methods/algorithms were chosen.
- [ ] **Limitations**: Honest assessment of method constraints.

### Results

- [ ] **Organization**: Logical order (chronological, or most important first).
- [ ] **Presentation**: Objective reporting of data — interpretation belongs in the
  Discussion.
- [ ] **Completeness**: Every research question addressed with data.
- [ ] **Granularity**: Not raw data dumps, not over-summarized.

### Discussion

- [ ] **Interpretation**: What the results *mean* (not a restatement of Results).
- [ ] **Context**: Comparison with prior work — support or contradict, and why.
- [ ] **Limitations**: Critical self-reflection (sample size, assumptions,
  generalizability).
- [ ] **Implications**: Theoretical or practical impact; no overreaching beyond
  what the data support.
- [ ] **Future Work**: Relevant and feasible, not a wish list.

---

## 5. Technical Rigor (Methodology-Specific)

*Apply only the subsections matching the manuscript's methodology. Interdisciplinary
papers need multiple subsections — e.g., a learned controller tested on humans needs
A or C plus D plus E.*

### A. Theoretical Work (Control/Math)

- [ ] **Correctness**: Proofs mathematically sound and complete.
- [ ] **Stability**: Lyapunov/passivity analysis provided where stability is claimed.
- [ ] **Convergence**: Convergence properties established where claimed.
- [ ] **Assumptions**: Clearly stated and physically realistic.
- [ ] **Novelty**: New theorems or frameworks, not trivial extensions.
- [ ] **Examples**: Numerical or illustrative examples provided.

### B. Simulation Studies

- [ ] **Validation**: Simulator physics matched to reality (if claiming real-world relevance).
- [ ] **Parameters**: Realistic values used — and listed.
- [ ] **Robustness**: Tested against noise, disturbances, parameter uncertainty.
- [ ] **Comparison**: Benchmarked against state-of-the-art methods.
- [ ] **Numerics**: Timestep/discretization justified; Monte Carlo runs for
  stochastic systems; sensitivity analysis for key parameters.

### C. Hardware Experiments (Robotics)

- [ ] **Setup**: Hardware described in reproducible detail (sensors, actuators, compute).
- [ ] **Repeatability**: Protocol allows others to replicate; number of trials stated.
- [ ] **Safety**: Protocols and fail-safes described — critical for human-robot
  interaction (e-stops, force limits, collision handling).
- [ ] **Metrics**: Quantitative performance measures (RMS error, energy, time).

### D. Human Subjects Research (Biomechanics)

> **Ethics first**: research without IRB approval is unpublishable. Missing IRB is
> automatically [CRITICAL].

- [ ] **IRB/Ethics**: Approval number and informed consent procedure stated.
- [ ] **Demographics**: N, age, sex, height, mass reported.
- [ ] **Protocol**: Randomization, control groups, rest periods described;
  equipment calibration and measurement validity addressed.
- [ ] **Statistics**:
    - [ ] Appropriate tests (t-test vs. ANOVA vs. non-parametric).
    - [ ] Assumptions checked (normality, homogeneity of variance).
    - [ ] **Effect sizes** reported alongside p-values.
    - [ ] Correction for multiple comparisons (Bonferroni, etc.).

**Statistical pitfalls to flag:**

- Multiple testing without correction (p-hacking pattern).
- Circular analysis — same data used for hypothesis generation and testing.
- Inappropriate pooling across subjects; pseudoreplication (treating repeated
  measures from one subject as independent samples).
- Retrospective ("post hoc") power analysis presented as justification.

### E. AI & Machine Learning

- [ ] **Data**: Dataset size, source, preprocessing, and train/val/test splits
  detailed; no test-set leakage.
- [ ] **Model**: Architecture and hyperparameters fully specified.
- [ ] **Validation**: Cross-validation or independent test set.
- [ ] **Baselines**: Comparison with simple models AND state-of-the-art.
- [ ] **Fairness/Bias**: Data balance and potential biases addressed (especially
  for human-derived data — demographic representation).
- [ ] **Interpretation**: Error analysis (where does the model fail?); feature
  importance or interpretability methods where claims depend on them.
- [ ] **Reproducibility**: Code/data availability statement; dependencies and
  environment specified if code is shared.
- [ ] **Deployment claims**: If real-time or edge deployment is claimed, inference
  time and model size reported.

---

## 6. Figures, Tables, & Visualizations

*Visuals should tell the story independently of the text.*

### General Quality

- [ ] **Legibility**: Text readable at print size (no tiny fonts).
- [ ] **Captions**: Self-contained — explain what is shown without the body text.
- [ ] **Axes**: Labels and units on every axis.
- [ ] **Accessibility**: Color-blind friendly palettes; distinct line styles/markers
  in addition to color.
- [ ] **Figure vs. Table**: Tables for exact values, figures for trends; no
  redundancy between figures, tables, and text.

### Domain-Specific Expectations

- **Control**: Block diagrams, phase portraits, step/tracking response with error bounds.
- **Biomechanics**: Stick figures, joint angle/moment profiles, EMG signals,
  gait-cycle-normalized plots.
- **ML**: Architecture diagrams, learning curves (train/val), confusion matrices,
  t-SNE/UMAP embeddings.

---

## 7. References & Citations

- [ ] **Coverage**: Foundational papers included; recent work (typically last ~5
  years for active fields) represented — but seminal older works still belong.
- [ ] **Primary sources**: Cited directly, not via second-hand citations.
- [ ] **Methods papers**: Cited when using established techniques.
- [ ] **Fairness**: Competing methods cited and characterized accurately.
- [ ] **Accuracy**: Each citation actually supports the claim it is attached to.
- [ ] **No padding**: No irrelevant citations inflating the reference count.

---

## 8. Novelty & Contribution

*What is the "delta"?*

- [ ] **Significance**: Solves a *real* problem, not a contrived one.
- [ ] **Differentiation**: Clearly distinguished from prior work — including the
  authors' own previous papers.
- [ ] **Contribution Type** (identify which; each type is evaluated on its own terms):
    - **Methodological**: New algorithm or technique.
    - **Empirical**: New data or experimental insight.
    - **Theoretical**: New proof or framework.
    - **System**: Novel hardware or software integration.
    - **Dataset/Tool**: New benchmark, data resource, or platform.

**Red flags**: incremental change presented as breakthrough; literature review that
omits the closest competing work; claims in the abstract that the results do not
support.

---

## 9. Cross-Section Coherence

*Consistency checks across the manuscript — where many drafts silently fail.*

- [ ] Contributions claimed in the Introduction match Results actually presented.
- [ ] Discussion addresses every research question raised in the Introduction.
- [ ] Limitations acknowledged in the Discussion are consistent with the Methods.
- [ ] Figures support the claims made in the text (numbers match, trends match).
- [ ] Abstract numbers match the Results section.
- [ ] Notation and terminology consistent across sections.

---

## 10. Decision Criteria

- **Accept / Ready to submit**: No changes or typos only.
- **Minor Revision**: Clarifications, better figures, citation fixes — no new data
  or analysis needed.
- **Major Revision**: Flawed analysis, missing baselines, unclear logic — requires
  re-review after substantial changes.
- **Reject / Rework**: Fatal flaws — methodological error, lack of novelty, ethical
  breach. For a student draft, frame this as "rework before considering submission"
  with a concrete recovery path.

**Weighting rules:**

- Any single [CRITICAL] item → at least Major Revision.
- Multiple [MAJOR] items in Technical Rigor → Major Revision.
- Only [MINOR] items → Minor Revision or Ready.
- Novelty problems cannot be fixed by polish — if the delta is unclear, that is
  [MAJOR] and the feedback should focus on repositioning the contribution.

**Borderline tie-breaker**: when a case sits between two levels, the deciding
question is *"does fixing the [MAJOR] items require new data, new analysis, or new
experiments?"* Yes → Major Revision; no (the fixes are additions of existing
numbers, rewrites, or reframing) → Minor Revision. State the recommendation
decisively rather than hedging between levels — the justification sentence can note
it was borderline.

---

## 11. Feedback Templates

Every item: `[TAG] <specific issue>. <concrete action required>.` — always with a
location (section, equation, figure number).

**Missing theory:**
> "[MAJOR] The stability of the proposed controller (Sec. III) is claimed but not
> proven. Provide a Lyapunov analysis or passivity proof to guarantee stability."

**Statistical issues:**
> "[MAJOR] P-values are reported (Table II) without effect sizes. Include effect
> sizes (e.g., Cohen's d) to demonstrate the practical significance of the results."

**Unclear contribution:**
> "[MAJOR] The distinction between this work and [Author, Year] is unclear.
> Explicitly state the novel contributions of this manuscript relative to prior art
> at the end of Section I."

**Missing ethics:**
> "[CRITICAL] The manuscript reports human subject experiments (Sec. IV) but does
> not state IRB approval. Add the approval number and informed consent procedure to
> the Methods; without this the manuscript cannot be submitted."

**Figure quality:**
> "[MINOR] Fig. 5 axis labels are illegible at print size and colors are not
> distinguishable in grayscale. Increase font size to ≥8pt and add distinct line
> styles."

---

## 12. Glossary

- **Ablation Study**: Systematically removing components of a model to assess their
  individual contribution.
- **Bonferroni Correction**: Statistical adjustment to prevent false positives when
  performing multiple tests.
- **Effect Size**: A measure of the magnitude of a phenomenon (e.g., difference
  between groups), independent of sample size.
- **IRB (Institutional Review Board)**: Committee that approves research involving
  human subjects.
- **Lyapunov Stability**: A method to prove that a system's state will stay near an
  equilibrium point.
- **Pseudoreplication**: Treating non-independent measurements (e.g., many trials
  from one subject) as independent samples, inflating statistical significance.
- **SOTA (State-of-the-Art)**: The current best performance/method in a specific
  field.
