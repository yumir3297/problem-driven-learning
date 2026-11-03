# Validation Status — v0.1.0

## Completed in this authoring pass

- Confirmed the agreed scope and interaction model.
- Checked the official Codex and OpenCode documentation for the shared personal skill directory.
- Reviewed primary and review literature relevant to retrieval practice, self-explanation, and worked examples.
- Created the core skill and three focused reference documents.
- Added a sample lesson and six acceptance scenarios.
- Performed structural checks on frontmatter, directory naming, relative references, and required files.
- Reviewed the sample lesson against the six-stage teaching spine.

## Not yet verified

- Independent no-skill baseline run.
- Independent skill-enabled pressure tests.
- Actual discovery and loading on the user's local Codex installation.
- Actual discovery and loading on the user's local OpenCode installation.
- Cross-model behavioral consistency.

## Why these remain pending

The current authoring environment does not expose a general-purpose independent subagent runner or direct access to the user's local agent installations. Do not describe these tests as passed until they are run in those environments.

## Next validation cycle

1. Install the ZIP in Codex and OpenCode.
2. Run the six scenarios in \`acceptance-tests.md\` in fresh conversations.
3. Record the actual output and score each dimension.
4. Fix only demonstrated failures.
5. Rerun the same scenarios after each material change.
