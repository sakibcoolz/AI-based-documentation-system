# Technology Stack

| Technology | Purpose | Why Selected | Where Used | Alternatives Considered | Limitations | Version Guidance |
|---|---|---|---|---|---|---|
| Python | Backend and analysis services | Strong ecosystem for parsing and orchestration | API, workers, scanners | Go, Node.js | Single-process CPU work needs care | 3.12+ |
| FastAPI | HTTP API | Async support and typed contracts | Service layer | Flask, Django Ninja | Requires discipline around app boundaries | Current stable |
| Google ADK | Agent orchestration | Structured agent execution | Multi-agent layer | LangGraph, custom orchestration | External dependency maturity | Current stable |
| OpenRouter | Model gateway | Multi-model abstraction | LLM access | Direct vendor SDKs | Provider variability | Alias-based configuration |
| Next.js | Frontend app | Full-stack React tooling | Dashboard and explorers | Remix, Vite SPA | Server/client boundary complexity | Current LTS/stable |
| TypeScript | Frontend typing | Improves maintainability | UI and contracts | JavaScript | Build tooling overhead | Current stable |
| PostgreSQL | System of record | Strong relational and JSON support | Findings, tasks, docs | MySQL, SQLite | Requires schema management | Current stable |
| Redis | Cache and queues | Fast ephemeral state | Caching and job coordination | RabbitMQ, Valkey | Data durability tradeoffs | Current stable |
| Graphify | Repository graph context | Structural analysis focus | Graph enrichment | Custom graph builder | External tool dependency | Current compatible release |
| Context7 MCP | Framework documentation | Current external docs | Design assistance | Manual web lookup | Not repository truth | Current compatible release |
| Linear MCP | Task planning | Delivery workflow alignment | Optional task sync | GitHub Issues, Jira | Optional integration | Current compatible release |
| Tree-sitter | Parsing | Multi-language AST coverage | Static analysis | Regex, bespoke parsers | Grammar coverage varies | Current stable |
| Mermaid | Diagrams | Text-based diagrams in docs | Architecture docs | PlantUML, draw.io | Large diagrams can become noisy | Current stable |
| React Flow | Graph UI | Interactive node/edge visualization | Architecture explorer | Cytoscape, d3 | Complex state management | Current stable |
| OpenTelemetry | Observability | Vendor-neutral tracing | API and pipeline telemetry | Proprietary SDKs | Setup complexity | Current stable |
| Docker Compose | Local deployment | Fast MVP composition | Dev and preview envs | Helm, Tilt | Not long-term orchestration | Current stable |
