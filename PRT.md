# Product Requirements & Technical Thesis (PRT)

## Product
AI Repository Intelligence & Documentation Platform

## Goal
Build a language-agnostic platform that analyzes repositories, extracts evidence-backed structure and business logic, generates technical documentation and diagrams, tracks delivery progress, and answers grounded repository questions.

## Core Requirements
- Evidence-driven repository understanding.
- Deterministic parsing before LLM synthesis.
- Documentation-first delivery workflow.
- Clear separation between repository facts and external framework guidance.
- Traceable findings with confidence and evidence metadata.

## Primary Stack
Python 3.12+, FastAPI, Google ADK, OpenRouter, Next.js, TypeScript, PostgreSQL, Redis, Graphify, Context7 MCP, Linear MCP, Tree-sitter, Mermaid, React Flow, OpenTelemetry, Docker Compose.

## Constraints
- Do not infer architecture from filenames alone.
- Do not execute untrusted repository scripts during analysis.
- Do not start production coding before documentation approval.

## MVP Success Criteria
- A repository can be ingested and scanned safely.
- Evidence-backed findings can be stored and retrieved.
- Documentation and diagrams can be generated and reviewed.
- Users can inspect evidence and ask grounded questions.

## Open Questions
- Object storage choice for artifacts.
- Authentication/tenant model for hosted deployment.
- Linear availability and required workflow customization.
