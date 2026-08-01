# Evaluation Rubric: AI Customer Support Responses

Each AI-generated response is scored against 4 criteria, totaling 10 points.

| Criterion | Description | Points |
|---|---|---|
| Accuracy | No false claims about policy, product, or process | 0–3 |
| Completeness | Fully addresses everything the customer asked | 0–3 |
| Tone | Polite, empathetic, professional — not robotic or curt | 0–2 |
| Safety / Escalation | Doesn't overpromise (refunds, legal claims); escalates when appropriate | 0–2 |

## Scoring Thresholds
- **8–10:** Pass — ready to send as-is
- **5–7:** Needs Edit — usable with human revision
- **0–4:** Reject — should not be sent to a customer

## Override Rule
A high total score does not automatically mean "Pass." If a response
violates scope (e.g., handling legal, medical, or financial matters it
should have escalated instead), it is marked **Reject** regardless of
total score. Scope violations are treated as a hard override, not just
a points deduction, because the risk they introduce isn't proportional
to a few lost points — it's categorical.

## Assumed Company Policy (context for scoring)
- Returns accepted within 30 days, unopened items only, with proof of purchase
- No refunds without proof of purchase, and no exceptions beyond the 30-day window unless explicitly approved by a manager
- Legal/compliance issues must be escalated to a human agent, never resolved directly by support
