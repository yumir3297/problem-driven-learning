# problem-driven-learning

A personal, problem-driven, interactive teaching skill for Codex and OpenCode. Completed teaching units are turned into complete Obsidian-ready learning notes, with the learner's own questions integrated into the relevant sections.

## What it does

- Starts from a classic or representative problem.
- Analyzes the obstacle before introducing the solution.
- Explains how the target knowledge solves the problem.
- Formalizes definitions, mechanisms, formulas, assumptions, and derivations.
- Extends to applications, limitations, and boundary cases.
- Uses adaptive checkpoints and progressively harder questions.
- Creates or updates an Obsidian note after each completed teaching unit.
- Preserves the learner's original questions and places each answer beside the relevant concept—not in a separate FAQ.

## Install (macOS / Linux)

Clone the repository directly into the shared personal Agent Skills directory:

~~~bash
mkdir -p ~/.agents/skills
git clone https://github.com/yumir3297/problem-driven-learning.git \
  ~/.agents/skills/problem-driven-learning
~~~

Confirm this file exists:

~~~bash
~/.agents/skills/problem-driven-learning/SKILL.md
~~~

To update later:

~~~bash
cd ~/.agents/skills/problem-driven-learning
git pull
~~~

## Install (Windows PowerShell)

~~~powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills"
git clone https://github.com/yumir3297/problem-driven-learning.git "$HOME\.agents\skills\problem-driven-learning"
~~~

Confirm:

~~~powershell
Test-Path "$HOME\.agents\skills\problem-driven-learning\SKILL.md"
~~~

If Git is not installed, download the repository archive from the GitHub Code → Download ZIP menu, extract it, and place the problem-driven-learning folder under ~/.agents/skills/ (or $HOME\.agents\skills\ on Windows).

## Use it

In a new Codex or OpenCode conversation, ask the agent to use problem-driven-learning and state what you want to learn. For example:

> 请使用 problem-driven-learning 教我 DQN。我会提供教材，请先分析教材，再从一个经典问题开始，按互动式教学带我学会。每完成一个知识单元，请把完整讲解整理成 Obsidian 笔记，并把我提出的疑问放到对应知识章节。

You can also use short controls during a lesson: “继续”, “慢一点”, “直接讲”, “举例”, “再难一点”, “先做题”, or “总结”.

## Use with Obsidian

1. Install the Skill in a location discovered by your OpenCode installation.
2. Open the Obsidian Vault as the working project in OpenCode, or configure the runtime with access to that Vault.
3. Ask OpenCode to use problem-driven-learning.
4. After each completed teaching unit, the Skill searches for an existing note on the topic, safely updates it when appropriate, or creates a new note following the Vault's folder conventions.
5. The agent verifies the saved note and reports its Vault-relative path.

The Skill cannot write to a Vault that the active OpenCode process cannot access. In that case it must provide the complete Markdown note and clearly state that it has not been saved.

## Compatibility

The package uses the standard SKILL.md directory format. Codex and OpenCode both document support for the shared personal directory ~/.agents/skills/.

- Codex: personal skills are discovered from ~/.agents/skills/.
- OpenCode: global agent-compatible skills are discovered from ~/.agents/skills/; OpenCode also supports ~/.config/opencode/skills/.

If the skill is not listed:
- Verify the directory is named exactly problem-driven-learning.
- Verify the entry file is named exactly SKILL.md.
- Check whether your agent configuration permits loading skills.
- Start a new session or refresh the agent after installation.

## Package contents

- SKILL.md — core teaching behavior and output contract.
- references/teaching-method.md — adaptive teaching and subject-specific guidance.
- references/material-processing.md — how to inspect and reorganize supplied materials.
- references/assessment-rubric.md — question progression, feedback, and mastery criteria.
- references/obsidian-note-generation.md — note structure, inline learner-question integration, Vault writes, and safe updates.
- examples/sample-lesson.md — an example of a completed Obsidian learning note.
- tests/acceptance-tests.md — scenarios and evaluation criteria.
- DESIGN.md — confirmed design decisions.
- SOURCES.md — documentation and research basis.

## Version and validation

Version: 0.2.0 — adds Obsidian note generation and in-context learner-question integration.

Structural checks and repository consistency checks are included. Actual note creation, safe merge behavior, and Skill discovery still need to be tested in the user's local Obsidian/OpenCode environment; see tests/VALIDATION_STATUS.md.