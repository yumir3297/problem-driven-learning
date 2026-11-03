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

**Prompt:** “Python 的 title() 是干什么的？简短讲一下。”

**Must pass:**
- Keeps the explanation proportionate.
- Does not manufacture a lengthy historical problem or a six-section lecture.
- Still explains purpose, mechanism, and a small example.
- Produces a proportionate note after the mini-lesson is complete.
- Does not turn the short concept into an unnecessarily long document.

## Test 7 — Create a note after a completed lesson

**Prompt:** “教我 D Flip-Flop。讲完后整理成 Obsidian 笔记。”

**Must pass:**
- Completes the problem-driven explanation before consolidating it.
- Produces a complete, independently readable note, not a transcript or a short summary.
- Preserves definitions, state-update behavior, timing assumptions, examples, and any caveats actually taught.
- Uses Obsidian-compatible Markdown and valid YAML frontmatter.
- Writes the note to the accessible Vault and reports the exact Vault-relative path.
- Reads the file back to verify the write.
- If Vault access is unavailable, provides the complete Markdown and explicitly says it was not saved.

## Test 8 — Integrate the learner's question into the right section

**Prompt sequence:**
1. “教我 Feedback 为什么能实现状态保持。”
2. During the lesson: “为什么两个 NOT Gate 连接起来就能保存状态？两次取反不就是恢复原值吗？”
3. After the explanation: “继续，最后整理成笔记。”

**Must pass:**
- Answers the learner's question immediately before continuing the lesson.
- Preserves the original question wording in the note.
- Places the question callout inside the section explaining the feedback loop / bistable state, not in a detached FAQ at the end.
- Includes the actual explanation, including why the double-inversion identity alone is not the full storage explanation.
- Does not create a separate question-log file.

## Test 9 — Multiple questions across different concepts

**Prompt:** During one lesson, the learner asks one question about the motivation for the concept and another about a formula's assumptions.

**Must pass:**
- Preserves both original questions.
- Places each beside the relevant problem-analysis or formal-knowledge section.
- Does not merge distinct questions into a vague summary.
- Does not duplicate the same question in multiple places.
- The note remains coherent when read without the chat.

## Test 10 — Existing note and user-authored content

**Setup:** The Vault contains an existing note on the same topic with user-written examples, links, and custom headings.

**Prompt:** “继续学习这个知识点，讲完更新原来的笔记。”

**Must pass:**
- Finds and reads the existing note before editing.
- Preserves user-authored content, properties, links, and formatting.
- Merges new explanations and question callouts into appropriate sections.
- Avoids duplicate content.
- Does not replace the whole file with a generated template or create an unnecessary duplicate note.
- Reads back and verifies the updated note.

## Test 11 — Unresolved learner question

**Prompt sequence:** The learner asks a meaningful question that cannot be resolved from the supplied material and available reliable sources.

**Must pass:**
- Says clearly that the answer is not yet established.
- Preserves the original question in the relevant note section.
- Marks it as unresolved and explains what evidence or source is needed.
- Does not invent an answer to make the note appear complete.

## Test 12 — No Vault access

**Setup:** The agent is running outside the Vault and has no configured Vault path or write permission.

**Prompt:** “讲完后保存到 Obsidian。”

**Must pass:**
- Does not guess a local Vault path or scan the entire disk.
- Does not claim the file was saved.
- Provides the complete Markdown note in the response.
- Clearly states that the note has not been saved and identifies the missing access/path.

## Test 13 — Distinguish learner questions from tutor exercises

**Prompt:** The tutor asks a practice question; the learner answers it. Separately, the learner asks a spontaneous “why” question.

**Must pass:**
- Does not label tutor-generated exercises as learner questions.
- Records the learner's spontaneous question in the relevant concept section.
- Records the practice question and the learner's answer only as exercise/learning evidence when useful.
- Does not create an artificial FAQ.

## Scoring rubric

Score each dimension 0–2:

- Problem relevance and accuracy.
- Conceptual explanation and causal chain.
- Formal precision and source fidelity.
- Concision and pacing.
- Adaptive interaction.
- Progressive application and transfer.
- Note completeness and standalone readability.
- Fidelity and placement of learner questions.
- Safe Vault update and truthful write verification.

Interpretation:
- **15–18:** strong pass.
- **11–14:** usable, revise weak dimensions.
- **0–10:** fail; revise the skill and rerun the same scenario.

A scenario fails regardless of total score if it fabricates a historical origin, misstates a definition or formula, ignores supplied material, overwrites user-authored notes, misplaces or drops a meaningful learner question, or claims mastery / a successful file write without evidence.

## Validation status for this package

The package can be structurally checked and its example note reviewed, but independent behavioral tests in the user's local Codex/OpenCode and Obsidian Vault remain pending. Do not describe those tests as passed until they are run in those environments.