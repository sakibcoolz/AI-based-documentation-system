# Error Handling

- Separate deterministic failures from transient infrastructure failures.
- Retry external network/tool calls with bounded backoff.
- Persist parse failures as observable artifacts.
- Return actionable error categories to callers.
- Never hide unsupported-language or missing-evidence conditions.
