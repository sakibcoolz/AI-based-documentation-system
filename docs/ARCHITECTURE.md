# Architecture

## 1. High-Level System Architecture
The platform ingests a repository, performs deterministic analysis, builds a repository knowledge model, routes contextual evidence to specialist AI agents, and produces reviewable documentation and Q&A outputs.

### System Context Diagram
```mermaid
flowchart LR
  USER[Developer / Reviewer] --> UI[Next.js UI]
  UI --> API[FastAPI API]
  API --> MODELS[OpenRouter]
  API --> LINEAR[Linear MCP]
  API --> CTX[Context7 MCP]
  API --> GRAPH[Graphify]
  API --> DATA[(PostgreSQL / Redis / Object Storage)]
```

## 2. Frontend Layer
Next.js + TypeScript dashboard for repository intake, architecture exploration, evidence inspection, documentation browsing, and grounded Q&A.

## 3. API Layer
FastAPI exposes repository intake, scan control, findings retrieval, document generation, Q&A, and task/status endpoints.

## 4. Google ADK Orchestration Layer
ADK coordinates the orchestrator and specialist agents, but only after deterministic extraction and evidence packaging.

## 5. Deterministic Analysis Layer
Python services handle file scanning, hashing, stack detection, AST parsing, symbol extraction, dependency discovery, Graphify invocation, and git metadata collection.

## 6. Repository Knowledge Layer
PostgreSQL stores repositories, scans, findings, evidence, tasks, and generated documents. Redis supports caching, queues, and ephemeral session state.

## 7. Graphify Integration
Graphify provides graph-backed structural context for modules, relationships, and change impact; repository evidence remains the governing source.

## 8. Context7 Integration
Context7 provides current external framework documentation to support design and implementation guidance.

## 9. Linear Integration
Linear is optional and is used only for MVP/phase/task planning and delivery-state tracking.

## 10. OpenRouter Model Gateway
Model access is abstracted behind aliases: `fast`, `code`, `reasoning`, `documentation`, and `reviewer`.

## 11. Database / Cache / Object Storage
PostgreSQL is the system of record, Redis backs async workflows, and object storage is reserved for large generated artifacts.

## 12. Observability
OpenTelemetry spans repository ingestion, parsing, graph enrichment, agent execution, and document generation.

## 13. Security Boundaries
Repository content is untrusted, execution is sandboxed, credentials remain server-side, and prompt-injection defenses treat repository text as hostile input.

## 14. Deployment Architecture
Docker Compose is the MVP deployment target; Kubernetes is deferred until scale and operational requirements justify it.

### Container Architecture
```mermaid
flowchart TB
  subgraph Client
    UI[Next.js]
  end
  subgraph Platform
    API[FastAPI]
    WORKER[Analysis / Agent Workers]
    REDIS[(Redis)]
    POSTGRES[(PostgreSQL)]
    OBJ[(Object Storage)]
  end
  subgraph External
    OPENROUTER[OpenRouter]
    GRAPHIFY[Graphify]
    CONTEXT7[Context7]
    LINEAR[Linear MCP]
  end
  UI --> API
  API --> WORKER
  API --> REDIS
  API --> POSTGRES
  API --> OBJ
  WORKER --> OPENROUTER
  WORKER --> GRAPHIFY
  WORKER --> CONTEXT7
  API --> LINEAR
```

### Deployment Diagram
```mermaid
flowchart LR
  DEV[Developer Browser] --> INGRESS[Ingress / Reverse Proxy]
  INGRESS --> WEB[Next.js Service]
  INGRESS --> APP[FastAPI Service]
  APP --> JOBS[Worker Deployment]
  APP --> PG[(PostgreSQL)]
  APP --> R[(Redis)]
  JOBS --> STORE[(Object Storage)]
  JOBS --> EXT[OpenRouter / Graphify / Context7]
```

## 15. Mermaid Diagram
```mermaid
flowchart LR
  UI[Next.js UI] --> API[FastAPI API]
  API --> ANALYSIS[Deterministic Analysis Services]
  ANALYSIS --> GRAPH[Graphify]
  ANALYSIS --> DB[(PostgreSQL)]
  API --> CACHE[(Redis)]
  API --> ORCH[ADK Orchestrator]
  ORCH --> MODELS[OpenRouter Aliases]
  ORCH --> DOCS[Documentation & Diagram Generation]
  DOCS --> DB
  API --> OBS[OpenTelemetry]
```

## Architecture Principle
`Parse -> Structure -> Build Relationships -> Retrieve Relevant Context -> AI Reasoning -> Evidence Validation -> Documentation`
