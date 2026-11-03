# Problem-Driven Learning — Design

## Purpose

Create a reusable personal teaching skill that helps the learner understand and independently use a topic by reorganizing instruction around problems, while retaining the rigor and useful structure of supplied learning materials.

## Confirmed product decisions

- Name: `problem-driven-learning`.
- Teaching interaction: interactive tutor.
- Pause timing: adaptive to topic difficulty, learner responses, and conceptual bottlenecks.
- Teaching sequence:
  1. Classic or representative problem.
  2. Problem analysis.
  3. How the target knowledge solves the problem.
  4. Formal definitions, principles, notation, formulas, and derivations.
  5. Extensions, applications, and boundaries.
  6. Progressive questions from simple recognition or formula use to a complete open-ended problem.
- Style: concise and precise without losing essential reasoning.
- Material handling: preserve accurate definitions, formulas, notation, proofs, and valuable original examples; reorder or supplement the teaching sequence where useful.
- Packaging: one core `SKILL.md` plus focused references and an example.
- Target runtimes: Codex and OpenCode through the shared personal `~/.agents/skills/` directory.

## Learner defaults

- Problem-oriented and question-led.
- Concise explanations; no filler.
- Explain a concept in the micro-order purpose / role → mechanism / principle → example.
- Do not force unrelated connections to past projects.
- Use evidence from the learner's answers to adjust difficulty and pacing.

## Non-goals

- Replacing a textbook or course syllabus.
- Simplifying away formal assumptions, proof obligations, or technical terminology.
- Turning every answer into a long lesson.
- Asking a fixed number of questions after every paragraph.
- Claiming mastery from passive agreement.
- Automatically creating flashcards, study schedules, or persistent learner records.

## Architecture

`SKILL.md` contains discovery metadata and the core workflow. Supporting references separate teaching method, source-material processing, and assessment. A sample lesson demonstrates the expected teaching shape. Acceptance tests cover beginner, advanced, material-based, abstract, corrective-feedback, and small-question cases.

## Evidence-informed design

- Retrieval practice and distributed practice support retention, but their effects depend on the knowledge type, assessment format, and timing.
- Self-explanation can help learners integrate new information and build more coherent mental models.
- Worked examples are useful during early skill acquisition; support should gradually fade as the learner becomes capable of independent problem solving.
- These findings inform the teaching design but do not justify a rigid universal schedule or a fixed checkpoint after every concept.

## Success criteria

A successful lesson starts from a well-chosen problem, makes the problem-solving role of the knowledge explicit, preserves formal accuracy, adapts interaction timing, and gives the learner a chance to apply and transfer the idea independently.