# API Contract

## Planned Domains
- Repository intake
- Scan orchestration
- Findings and evidence retrieval
- Documentation generation
- Diagram generation
- Grounded repository Q&A
- Task and phase status

## Proposed Endpoints
- `POST /repositories`
- `POST /repositories/{id}/scans`
- `GET /repositories/{id}/scans/{scan_id}`
- `GET /repositories/{id}/findings`
- `GET /repositories/{id}/documents`
- `POST /repositories/{id}/questions`
- `GET /roadmap/phases`

## Example Finding Payload
```json
{
  "finding_type": "business_logic",
  "title": "Order validation occurs before persistence",
  "summary": "Validation is performed before repository writes.",
  "confidence": "high",
  "classification": "extracted",
  "evidence": [
    {
      "path": "src/orders/service.py",
      "symbol": "OrderService.create",
      "start_line": 20,
      "end_line": 75
    }
  ],
  "external_context": []
}
```
