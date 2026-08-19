# Writing standards

This repository's prose — `README.md`, `GetStarted.md`, `PATTERNS.md`, every
lab's `RESULTS.md`, and any other explanatory Markdown — follows one house
style: **STE100 discipline, ISO 24495 latitude.** Apply it whenever you write
or edit documentation here, human or AI.

## Why a hybrid, not a single standard

| Standard | Main purpose | Fit for this repo |
|---|---|---|
| ASD-STE100 (Issue 9, Jan 2025) | Controlled English for technical documentation — a restricted vocabulary plus grammar rules | Baseline discipline |
| ISO 24495-1:2023 | Plain-language principles: make text relevant, findable, understandable, usable | Very relevant |
| ISO 24495-3:2026 | Plain language for science writing | Relevant for architecture/technique explanations |
| IEC/IEEE 82079-1 | How to prepare instructions for use | Relevant for setup/quickstart docs |
| S1000D | Structured technical-publication lifecycle management | Out of scope — too broad for this repo |
| ISO/IEC Directives Part 2 | Rules for normative/requirements text | Out of scope — this repo has no normative requirements text |

STE100 is a *controlled language*: a restricted vocabulary plus grammar
rules, not just a style guide. Followed strictly, it reads mechanical — like
an aircraft maintenance manual — which is wrong for a course that also has
to build intuition. ISO 24495 is looser: readable, audience-oriented,
concise, without a locked vocabulary. The house style keeps STE100's
sentence- and grammar-level discipline and ISO 24495's freedom to use normal
technical vocabulary where it helps the reader.

Quick mental model:

- **ASD-STE100** → simple sentences + controlled vocabulary + low ambiguity
- **ISO 24495** → readable + audience-oriented + concise
- **IEC 82079-1** → usable instructions/setup docs

## Rules

1. **One idea per sentence.** Split compound sentences that carry two claims.
2. **Explicit subjects.** Say who or what does the action; avoid dangling
   "this" / "it" referring back across a paragraph break.
3. **Short sentences.** Target ≤ 20–25 words. Long enumerations become lists.
4. **Active voice.** "The benchmark measures X," not "X is measured by the
   benchmark." Passive is acceptable only when the actor is genuinely
   unknown or irrelevant.
5. **Consistent terminology.** One term per concept, repeated verbatim
   (e.g. always "baseline," never alternating with "unoptimized version" or
   "reference build"). Do not vary word choice for style.
6. **Limited noun stacks.** Break up chains like "cache line false sharing
   detection method" into a phrase with prepositions: "a method to detect
   false sharing on a cache line."
7. **No acronym in an opening sentence** without having introduced it, and
   spell out an acronym on first use per document.
8. **Normal technical vocabulary is allowed** (unlike strict STE100's
   approved-word dictionary) when it is the term a reader of this material
   already knows — e.g. "vectorization," "branch misprediction," "LLC miss."
   Do not force plain-English paraphrases of established technical terms.
9. **Lead with the reader-relevant fact**, not the mechanism. State what
   happens/what to do before explaining why, per ISO 24495's
   relevant-findable-understandable-usable ordering.
10. **Concrete over abstract.** Prefer a number, an example, or a named file
    over a general claim.

## Reusable prompt

Paste this block into any prompt (human instructions or an LLM system/task
prompt) that asks for documentation, comments, or RESULTS.md-style
explanations in this repository, to enforce the house style:

```
Write in the ARAMAS/perf-ninja house style: a hybrid of ASD-STE100 and
ISO 24495-1. Rules:
- One idea per sentence. Explicit subject. Active voice by default.
- Target 20-25 words per sentence; split anything longer.
- Use one consistent term per concept throughout — never vary word choice
  for style.
- Avoid noun stacks; use prepositional phrases instead.
- Spell out acronyms on first use; never open a sentence or section with an
  unintroduced acronym.
- Use normal technical vocabulary the reader already knows (e.g.
  vectorization, cache miss, branch misprediction) — do not force plain-
  English substitutes for established terms.
- Lead with the fact the reader needs, then explain the mechanism.
- Prefer a concrete number, example, or file reference over an abstract
  claim.
Do not sound like a restricted-vocabulary manual: normal technical English
is fine as long as every sentence obeys the rules above.
```

## Where this applies

- `SKILL.md`'s `RESULTS.md` template (see "RESULTS.md template
  (intuition-first)") and the `PATTERNS.md` aggregation step both write
  under this standard.
- `README.md`, `GetStarted.md`, `Contributing.md`, and the `Quickstart*.md`
  files.
- Any new lab `README.md` contributed to `labs/`.

Code comments and commit messages are out of scope — this standard governs
prose documentation only.
