# ADR-0002: Model Alias Strategy

## Status
Accepted

## Decision
All agent/model access will use aliases (`fast`, `code`, `reasoning`, `documentation`, `reviewer`) rather than provider-specific IDs.

## Consequences
Provider changes are isolated from agent logic and operational controls like fallbacks and budgeting are centralized.
