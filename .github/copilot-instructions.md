# Copilot Instructions

## Repository Rule
This repository uses a **pre-development documentation phase**. Do not start production code until documentation is generated, internally validated, and explicitly approved.

## Required Read Order
1. `PRT.md`
2. `docs/INDEX.md`
3. `prompts/MASTER_DEVELOPMENT_PROMPT.md`
4. Existing files under `docs/`

## Mandatory Workflow
1. Read existing repository files.
2. Refresh repository context with Graphify if available.
3. Use Context7 for current external framework documentation.
4. Use Linear MCP only for task planning/status if configured.
5. Generate or update the required documentation set.
6. Validate consistency across documents.
7. Stop with the documented pre-development completion message.

## Source-of-Truth Priority
1. Existing source code
2. Existing project requirements
3. Existing repository configuration
4. Graphify repository graph
5. Tests/configuration/runtime-safe evidence
6. Context7 external technical documentation
7. AI reasoning

## Evidence Rules
- Classify findings as `extracted`, `inferred`, or `ambiguous`.
- Never promote an inference to a fact without repository evidence.
- Do not treat Linear or Context7 as proof of repository behavior.

## Stop Condition
End pre-development work with:

`PRE-DEVELOPMENT DOCUMENTATION COMPLETE`

followed by the generated document list, MVP phase count, task count, architecture decisions, open questions, the recommended first implementation task, and `Waiting for development approval.`
