# Evidence Standard

Every important repository finding must include:
- finding type
- title
- summary
- confidence
- classification
- evidence spans
- external context references when used

```json
{
  "finding_type": "business_logic",
  "title": "Order validation occurs before persistence",
  "summary": "Validation happens before repository writes.",
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
