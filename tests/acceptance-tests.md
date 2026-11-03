# Acceptance Tests

Use these scenarios to evaluate the skill in a fresh agent session. Compare the agent's actual teaching behavior with the criteria below; do not score it by whether it merely repeats the six-stage outline.

## Test 1 — Beginner, no supplied material

**Prompt:** “教我 Python 的变量命名规则，我刚开始学编程。”

**Must pass:**
- Starts with a concrete programming problem, not a dictionary definition.
- Labels the case as illustrative if it is not historically canonical.
- Separates syntax validity from naming readability.
- Gives precise rules and examples.
- Uses a checkpoint only when it adds diagnostic value.
- Ends with a progressively harder question, not a full answer dump.

## Test 2 — Supplied textbook or slides

**Prompt:** “根据我上传的教材教我 DQN。可以调整讲解顺序，但不要丢教材重点。”

**Must pass:**
- Inspects the supplied material before teaching.
- Preserves definitions, notation, equations, assumptions, and important examples.
- Reorders material to establish the problem before formal definitions.
- Identifies added explanations as supplements.
- Does not invent content or cite unseen pages.
- Offers a compact source-to-lesson map if the material is substantial.

## Test 3 — Abstract mathematical concept

**Prompt:** “从一个经典问题开始教我拉格朗日乘数法，最后让我能独立解题。”

**Must pass:**
- Uses a genuine motivating or canonical constrained-optimization problem, or labels a teaching example accurately.
- Explains the constraint and why ordinary unconstrained optimization is insufficient.
- Defines differentiability and constraint assumptions accurately.
- Explains the multiplier condition and its limitations.
- Moves from a worked example to independent problems.
- Does not remove proof conditions for the sake of simplicity.

## Test 4 — Learner gives a wrong answer

**Prompt sequence:** The learner gives an incorrect explanation of a central concept, then asks “所以我这样理解对吗？”

**Must pass:**
- Identifies the exact misconception.
- Does not falsely validate the answer.
- Gives a concise explanation and a useful hint.
- Allows a retry before revealing the entire solution, unless the learner asks for direct explanation.
- Uses a nearby variation to check whether the gap is repaired.

## Test 5 — Advanced learner

**Prompt:** “我已经会基本的 Q-learning，直接带我理解 DQN 为什么要用经验回放和目标网络。”

**Must pass:**
- Does not restart with elementary reinforcement-learning definitions.
- Uses a problem that exposes instability or correlated samples.
- Explains each mechanism's role and trade-offs.
- Uses a checkpoint around the central reasoning, not after every paragraph.
- Moves to a changed-condition or diagnostic question.

## Test 6 — Very small concept

**Prompt:** “Python 的 \`title()\` 是干什么的？简短讲一下。”

**Must pass:**
- Keeps the answer proportionate.
- Does not manufacture a lengthy historical problem or a six-section lecture.
- Still explains purpose, mechanism, and a small example.
- Offers one concise check only if useful.

## Scoring rubric

Score each dimension 0–2:

- Problem relevance and accuracy.
- Conceptual explanation and causal chain.
- Formal precision and source fidelity.
- Concision and pacing.
- Adaptive interaction.
- Progressive application and transfer.

Interpretation:
- **10–12:** strong pass.
- **7–9:** usable, revise weak dimensions.
- **0–6:** fail; revise the skill and rerun the same scenario.

A scenario fails regardless of total score if it fabricates a historical origin, misstates a definition or formula, ignores supplied material, or claims mastery without evidence.

## Validation status for this package

The package can be structurally checked and its example lesson reviewed, but this authoring environment does not expose an independent Codex/OpenCode subagent runner or the user's local installation. Therefore, the pressure scenarios have not yet been independently run against a no-skill control and a skill-enabled target agent. Treat cross-model behavioral validation as pending until these tests are run in Codex and OpenCode.
