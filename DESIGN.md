# Problem-Driven Learning — Design

## Purpose

Create a reusable personal teaching skill that helps the learner understand and independently use a topic by reorganizing instruction around problems, while retaining the rigor and useful structure of supplied learning materials. Every completed teaching unit also produces a durable Obsidian learning note that preserves the learner's own questions in context.

## Confirmed product decisions

- Name: problem-driven-learning.
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
- Note output: after each completed self-contained teaching unit, create or update one complete Obsidian-ready Markdown note.
- Learner questions: preserve meaningful questions in their original wording and integrate each question with its answer into the relevant knowledge section of that same note. Do not create a separate question log or detached FAQ.
- Vault safety: inspect the existing Vault structure, merge into a matching note when appropriate, preserve user-authored content, verify writes, and never claim a save that did not occur.
- Packaging: one core SKILL.md plus focused references and examples.
- Target runtimes: Codex and OpenCode through the shared personal ~/.agents/skills/ directory; Obsidian note writes require the runtime to have access to the Vault.

## Learner defaults

- Problem-oriented and question-led.
- Concise explanations; no filler.
- Explain a concept in the micro-order purpose / role → mechanism / principle → example.
- Do not force unrelated connections to past projects.
- Use evidence from the learner's answers to adjust difficulty and pacing.
- Preserve learner-generated questions as part of the knowledge explanation, not as an independent question collection.

## Non-goals

- Replacing a textbook or course syllabus.
- Simplifying away formal assumptions, proof obligations, or technical terminology.
- Turning every answer into a long lesson.
- Asking a fixed number of questions after every paragraph.
- Claiming mastery from passive agreement.
- Automatically creating flashcards, study schedules, or persistent learner records.
- Saving a separate question bank or raw chat transcript.
- Overwriting or reorganizing the learner's existing Vault notes without permission.

## Architecture

SKILL.md contains discovery metadata, the core teaching workflow, question-capture rules, and the output contract. Supporting references separate teaching method, source-material processing, assessment, and Obsidian note generation. The Obsidian reference defines note structure, question placement, Vault discovery, safe updates, and post-write verification. A sample note demonstrates the expected output. Acceptance tests cover teaching behavior and note-generation edge cases.

## Evidence-informed design

- Retrieval practice and distributed practice support retention, but their effects depend on the knowledge type, assessment format, and timing.
- Self-explanation can help learners integrate new information and build more coherent mental models.
- Generating and answering conceptual questions can benefit memory for conceptual information in some study conditions; the effect is not universal across all question types or materials.
- Worked examples are useful during early skill acquisition; support should gradually fade as the learner becomes capable of independent problem solving.
- These findings inform the teaching design but do not justify a rigid universal schedule or a fixed checkpoint after every concept.

## Success criteria

A successful lesson starts from a well-chosen problem, makes the problem-solving role of the knowledge explicit, preserves formal accuracy, adapts interaction timing, and gives the learner a chance to apply and transfer the idea independently.

A successful learning note is independently understandable without the original chat, contains the complete core explanation, and places the learner's meaningful questions and their answers at the relevant points in the knowledge structure. Existing Vault content remains intact.