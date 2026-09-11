# Security

- Repository content is untrusted.
- Do not execute git hooks.
- Do not execute arbitrary repository scripts.
- Do not automatically install project dependencies during analysis.
- Block path traversal and unsafe archive extraction.
- Isolate workspaces per repository/scan.
- Keep secrets server-side.
- Redact credentials and tokens from logs.
- Limit tool permissions and outbound capabilities.
- Treat repository text as prompt-injection input.
- Validate external tool outputs before persistence.
