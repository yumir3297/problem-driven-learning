# problem-driven-learning

A personal, problem-driven, interactive teaching skill for Codex and OpenCode.

## Install (macOS / Linux)

1. Download `problem-driven-learning.zip`.
2. Open Terminal in the download folder.
3. Run:

```bash
mkdir -p ~/.agents/skills
unzip -o problem-driven-learning.zip -d ~/.agents/skills/
```

Confirm this file exists:

```bash
~/.agents/skills/problem-driven-learning/SKILL.md
```

## Install (Windows PowerShell)

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills"
Expand-Archive -Path "$HOME\Downloads\problem-driven-learning.zip" -DestinationPath "$HOME\.agents\skills" -Force
```

Confirm:

```powershell
Test-Path "$HOME\.agents\skills\problem-driven-learning\SKILL.md"
```

If your ZIP is saved somewhere else, change the archive path accordingly.

## Use it

In a new Codex or OpenCode conversation, ask the agent to use `problem-driven-learning` and state what you want to learn. For example:

> 请使用 problem-driven-learning 教我 DQN。我会提供教材，请先分析教材，再从一个经典问题开始，按互动式教学带我学会。

You can also use short controls during a lesson: “继续”, “慢一点”, “直接讲”, “举例”, “再难一点”, “先做题”, or “总结”.

## Compatibility

The package uses the standard `SKILL.md` directory format. Codex and OpenCode both document support for the shared personal directory `~/.agents/skills/`.

- Codex: personal skills are discovered from `~/.agents/skills/`.
- OpenCode: global agent-compatible skills are discovered from `~/.agents/skills/`.

If the skill is not listed:
- Verify the directory is named exactly `problem-driven-learning`.
- Verify the entry file is named exactly `SKILL.md`.
- Check whether your agent configuration permits loading skills.
- Start a new session or refresh the agent after installation.

## Package contents

- `SKILL.md` — core teaching behavior.
- `references/teaching-method.md` — adaptive teaching and subject-specific guidance.
- `references/material-processing.md` — how to inspect and reorganize supplied materials.
- `references/assessment-rubric.md` — question progression, feedback, and mastery criteria.
- `examples/sample-lesson.md` — a short example lesson.
- `tests/acceptance-tests.md` — scenarios and evaluation criteria.
- `DESIGN.md` — confirmed design decisions.
- `SOURCES.md` — documentation and research basis.

## Version and validation

Version: 0.1.0 — first usable draft.

The package structure and internal references are included for review. Independent behavioral tests in the user's local Codex and OpenCode environments remain pending; see `tests/acceptance-tests.md`.
