# Processing Learning Materials

## Goal

Treat supplied material as the source of truth for course-specific terminology, notation, scope, and expected coverage. Reorganize its teaching order when doing so improves understanding, but do not silently replace or discard important content.

## Inspection workflow

1. Identify the material type and inspect the relevant pages, sections, examples, diagrams, formulas, and learning objectives.
2. Extract the source's:
   - learning objectives and topic boundaries;
   - definitions, symbols, assumptions, formulas, and proof steps;
   - examples, exercises, and teaching explanations;
   - stated prerequisites and dependencies.
3. Build an internal map from source order to problem-driven teaching order.
4. Identify:
   - content worth preserving as written;
   - content worth moving earlier or later;
   - gaps that require explanation;
   - content that is supplementary or outside the requested scope.
5. Teach from the reorganized map while retaining a traceable connection to the source.

## Preserve, adapt, supplement

| Material element | Default treatment |
|---|---|
| Formal definition, theorem, standard, or required formula | Preserve its meaning and conditions; clarify wording if needed. |
| Useful worked example | Keep it, or move it to the point where it best supports understanding. |
| Textbook order that delays motivation | Reorder for problem-first teaching; do not change the underlying knowledge dependency. |
| Redundant explanation | Compress without removing a necessary distinction. |
| Missing prerequisite | Add the minimum explanation needed and label it as a prerequisite. |
| Missing application or limitation | Supplement with a reliable source and identify it as an addition. |
| Ambiguous, outdated, or apparently incorrect statement | Flag it, verify it, and explain the discrepancy; do not silently “correct” the source. |

## Source-to-lesson map

For substantial materials, keep a compact map available to the learner:

| Lesson stage | Source location | Treatment |
|---|---|---|
| Opening problem | Chapter / slide / page | Preserved, adapted, or supplemented |
| Problem analysis | Chapter / slide / page | Reordered or supplemented |
| Core idea and definition | Chapter / slide / page | Preserved with clarification |
| Formal derivation | Chapter / slide / page | Preserved |
| Extension | Source or external source | Added / not covered in source |
| Exercises | Source exercise / new question | Preserved or newly designed |

Do not produce this table for every tiny request. Use it when it helps the learner see what changed.

## External research

When the material is missing, incomplete, disputed, or likely to be outdated:

- Search for the original paper, official documentation, standard, reputable textbook, or university course material.
- Prefer sources close to the original claim.
- Use recent sources for changing technologies, regulations, versions, and empirical findings.
- Distinguish the source's claim from the tutor's synthesis.
- Cite external factual claims in the lesson.
- Do not cite search snippets as if they were full-text verification.

## Historical integrity

Classify the opening problem accurately:

- **Historical motivating problem:** documented as part of the concept's development.
- **Canonical teaching problem:** widely used to explain the concept, but not necessarily its historical origin.
- **Representative scenario:** created or adapted for this lesson.

If the evidence does not establish historical origin, say so. A good teaching example does not need a fabricated origin story.

## Copyright and source fidelity

- Explain in original wording; do not reproduce long passages from textbooks or articles.
- Preserve mathematical meaning, code behavior, and technical conditions.
- Quote only short passages when necessary and cite them.
- Do not claim that a source contains a point unless it has been inspected.
