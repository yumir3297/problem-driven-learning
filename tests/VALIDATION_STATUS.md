# Validation Status — v0.2.0

## Completed in this repository update

- Preserved the original problem-driven six-stage teaching spine.
- Added an explicit end-of-unit Obsidian note-generation requirement.
- Added a dedicated reference for Vault discovery, note structure, learner-question integration, safe merging, and write verification.
- Specified that learner questions must retain their original wording and appear beside the relevant concept, not in a separate question log or detached FAQ.
- Updated the sample lesson to demonstrate an Obsidian note with a learner-question callout embedded in the correct section.
- Added acceptance scenarios for note creation, question placement, multiple questions, existing-note preservation, unresolved questions, missing Vault access, and short concept lessons.
- Updated README, design decisions, and research/documentation sources.
- Checked that the Skill frontmatter, directory name, relative reference paths, and repository file references are consistent.

## Not yet verified

- Actual discovery and loading on the user's local OpenCode installation.
- Actual file creation in the user's Obsidian Vault.
- Safe merge behavior against a real existing Vault note.
- Correct rendering of YAML properties, callouts, LaTeX, and wikilinks in the user's Obsidian theme/plugins.
- Independent behavioral runs of the acceptance tests.
- Cross-model behavioral consistency.

## Why these remain pending

This repository authoring environment can update GitHub content but does not expose the user's local Obsidian Vault or a live OpenCode session. Repository synchronization and static consistency do not prove that local file writes or rendering work.

## Next validation cycle

1. Pull the updated repository into the installed Skill directory.
2. Open the Obsidian Vault as the OpenCode working project or grant the OpenCode process access to the Vault.
3. Run acceptance tests 7–13, especially the in-context learner-question case and the existing-note preservation case.
4. Inspect the actual generated note in Obsidian.
5. Fix only demonstrated failures, then rerun the same cases.
6. Record real test evidence here; do not mark unexecuted tests as passed.