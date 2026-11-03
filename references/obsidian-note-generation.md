# Obsidian Note Generation

## Purpose

Turn each completed teaching unit into a complete, independently readable Markdown note inside the learner's Obsidian Vault. The note is the durable learning artifact; the conversation is only the teaching process.

The note must preserve the six-stage problem-driven logic where useful and integrate the learner's own substantive questions into the relevant sections. It must not become a raw transcript, a short summary, a separate question log, or a detached FAQ.

## 1. When to create or update a note

Create or update a note when:

- A self-contained concept explanation or mini-lesson has been completed.
- A planned teaching unit reaches a natural stopping point.
- The learner says “总结”, “记笔记”, “先到这里”, or otherwise asks to end and consolidate the current lesson.

Do not create a separate note after every conversational turn:

- A clarification question asked during an active lesson is answered immediately and incorporated into that lesson's note.
- A sequence of related clarifications remains part of the same teaching unit.
- A short, standalone question that itself forms a complete mini-lesson (for example, “Python 的 title() 是干什么的？”) does produce a proportionate note.
- If the learner explicitly says not to create a note, follow that instruction.

## 2. Capture the lesson content while teaching

Keep a temporary working outline for the active teaching unit. It should contain:

- The central problem and its constraints.
- The reasoning that reveals why the problem is difficult.
- The role of the target knowledge in solving the problem.
- Definitions, mechanisms, formulas, assumptions, derivations, and technical terminology.
- Worked examples, code, diagrams, applications, limitations, and edge cases actually discussed.
- Source material locations (chapter, page, slide, section) and external references used.
- The learner's substantive questions, preserved in their original wording, plus the explanation that resolved each one.
- Any unresolved question, misconception, or prerequisite gap that remains at the end.

This is temporary lesson context, not a second document or a persistent question bank. Do not interrupt the lesson to ask the learner to fill in a form or approve each captured question.

## 3. Integrate learner questions at the correct point

This is a mandatory part of the note.

For every meaningful question the learner raises about the subject:

1. Preserve the original wording. Do not replace it with an AI-written paraphrase.
2. Identify the concept, assumption, formula, example, or inference that prompted it.
3. Place the question immediately after or beside the relevant explanation in the note.
4. Include the answer that was actually given, refined for clarity and correctness.
5. If the question exposed a misconception or prerequisite gap, explain that gap explicitly.
6. If the answer introduces a useful missing concept, add the minimum necessary explanation in that same section.
7. If a later explanation corrects an earlier answer, retain only the corrected explanation in the main body and, where useful, state that the earlier explanation was corrected.
8. If the question remains unresolved, preserve it in the relevant section with a clear unresolved marker and the reason it could not yet be answered.

Use an Obsidian callout to distinguish the learner's own question from the main explanation, for example:

~~~markdown
> [!question] 你的问题
> 为什么两个 NOT Gate 连接起来就能保存状态？两次取反不就是恢复原值吗？
>
> **解答：** 两次取反的逻辑关系确实会恢复原值，但存储能力来自反馈回路的状态稳定性，而不是单独的双重取反恒等式。两个反相器构成的环路具有两个稳定状态；实际电路还需要考虑器件特性和稳定性条件。
~~~

Place this callout inside the relevant section, such as “Feedback 的工作机制” or “双稳态状态保持”. Do not collect all question callouts at the end of the note.

For an unresolved question:

~~~markdown
> [!warning] 尚未解决
> **原始问题：** ...
>
> **当前状态：** 现有材料不足以确定答案；需要核对指定教材章节或权威资料。
~~~

Do not invent an answer merely to make the note look complete.

## 4. Note structure

Use this as the default structure, adapting it to the subject and size of the lesson:

~~~markdown
---
type: learning-note
topic: "主题名称"
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags:
  - learning
---

# 主题名称

## 1. 经典问题 / 代表性场景

问题、目标、约束，以及为什么值得解决。

## 2. 问题分析

已知条件、未知量、关键障碍，以及直觉方法为什么不足。

## 3. 知识如何解决问题

核心思想如何对应并解决前面的障碍。

## 4. 核心知识与原理

定义、机制、符号、公式、推导、例子。将 learner-question callouts 插入它们实际对应的位置。

## 5. 应用、延伸与边界

其他用途、条件变化、限制和容易混淆的相邻概念。

## 6. 练习与思考

记录本次教学中实际布置的练习。没有讲解答案的题目标记为“待练习”，不要擅自补出答案。

## 学习状态

已掌握 / 基本掌握 / 待巩固；只依据本次教学中观察到的证据。
~~~

Rules:

- Do not force all six headings into a tiny concept. Keep the note proportionate without losing the core explanation.
- The question callouts belong inside sections 1–5 where they make conceptual sense. Do not add a generic “问题汇总” or “FAQ” section merely to collect them.
- Include a final “未解决问题” section only when unresolved questions cannot be placed clearly in the relevant section; prefer an inline warning callout.
- Include the learner's answers to practice questions only when they were actually discussed. Do not convert tutor-generated quiz questions into learner questions.
- Use concise prose, but preserve the complete reasoning needed to understand the topic without reopening the chat.
- Do not include filler dialogue, greetings, repeated praise, or the full chat transcript.

## 5. Obsidian-compatible formatting

Prefer standard Markdown and Obsidian-supported extensions:

- Use headings, lists, tables, fenced code blocks, and blockquotes.
- Use question callouts for the learner's own questions and warning callouts for unresolved items.
- Use LaTeX for mathematical expressions when appropriate.
- Use Obsidian wikilinks only when the target note is known to exist or is deliberately being created in the same operation.
- Use embeds only for files that were actually created or already exist in the Vault.
- Use YAML frontmatter with unique property names. Keep metadata minimal: type, topic, created, updated, and tags are sufficient defaults. Follow an existing Vault convention when one is already established.
- Avoid raw HTML wrappers and unsupported renderer-specific syntax. Do not invent attachment paths, wikilinks, page numbers, or citations.

For supplied materials, record the actual chapter/page/slide references used. For external research, preserve working source links in the note and distinguish source claims from the tutor's synthesis.

## 6. Find the Vault and choose the note path

Use available filesystem tools and the current project context:

1. Check whether the current working directory is inside the Vault. Look for an .obsidian directory in the current directory or its ancestors; use an explicitly configured Vault path if the environment exposes one.
2. Do not scan the entire disk or guess a Vault path.
3. Search the Vault for an existing note on the same topic before creating a new file.
4. If one clear topic note exists, update it. If multiple plausible notes exist and choosing one could merge unrelated material, ask one concise clarification.
5. If no matching note exists, follow the Vault's existing subject/folder naming conventions.
6. If the Vault has no established learning-note convention, use 学习笔记/<safe-topic-name>.md as the default and create the folder if necessary.
7. Sanitize the filename for the filesystem while keeping the readable topic in the note title and topic property.

If the current working directory is not in the Vault and no explicit Vault path is available, do not guess. Ask for the Vault path only if the user expects an actual file write; otherwise provide the complete Markdown in the response and say it has not been saved.

## 7. Update existing notes safely

Before changing an existing note:

- Read the entire relevant note, not just its title or first section.
- Preserve user-authored content, metadata, custom headings, links, embeds, and formatting.
- Merge the new explanation into the appropriate sections. Do not replace the whole note with a generated template.
- Avoid duplicate explanations and duplicate question callouts. If a question is already represented, add only genuinely new clarification.
- Update the updated property when present; add minimal metadata only when compatible with the existing note.
- Do not delete, rename, move, or reorganize existing notes without explicit instruction.
- If the best merge would require removing or substantially rewriting user-authored material, preserve the original and add a clearly dated “学习补充” section instead.

For a new note, create the complete note in one file. Keep related clarifications from the same lesson in that same note.

## 8. Verify and report the result

After writing:

1. Read the saved file back.
2. Verify that the note contains the main explanation, key definitions and examples, and all meaningful learner questions with answers in their relevant sections.
3. Verify that formulas, code fences, callouts, YAML frontmatter, and wikilinks are syntactically intact.
4. Verify that every embedded file and internal link points to a real Vault item or was created in the same operation.
5. Report the exact Vault-relative path and a brief statement of what was included.

If writing fails or is unavailable:

- Do not claim that the note was saved.
- Provide the complete Markdown content in the response so the learner can save it.
- State the specific limitation plainly, without implying that a local file was created.