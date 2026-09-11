# Test Strategy

- **Unit tests:** scanners, parsers, normalizers, contract validators.
- **Integration tests:** PostgreSQL/Redis persistence, Graphify and MCP adapters.
- **Contract tests:** API schemas, evidence payloads, model alias routing.
- **Agent output tests:** prompt templates, unsupported-claim detection, review gates.
- **MCP adapter tests:** Context7, Graphify, Linear error handling and retries.
- **API tests:** intake, scan lifecycle, findings, documents, Q&A.
- **Frontend tests:** dashboard flows, evidence explorer, diagram rendering.
- **Security tests:** path traversal, prompt injection, secret redaction, sandbox enforcement.
- **End-to-end tests:** add repository → scan → graph → agents → docs → diagrams → review → UI → grounded question.
