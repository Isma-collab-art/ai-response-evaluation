# AI Response Evaluation: Customer Support

A self-directed practice project exploring AI response evaluation, built as
part of a transition from manual QA into AI/LLM QA.

## Overview
This project evaluates AI-generated customer support responses against a
custom rubric, simulating real-world LLM evaluation work: designing scoring
criteria, testing edge cases, scoring outputs with documented reasoning, and
surfacing behavioral patterns across results.

## What I Did
- Designed a 4-criteria scoring rubric (accuracy, completeness, tone, escalation handling), including an override rule for scope violations
- Wrote 8 test prompts spanning easy, ambiguous, policy-edge, multi-part, and out-of-scope scenarios
- Generated responses using Claude acting as a customer support agent
- Scored all 8 responses with documented reasoning
- Identified a specific, recurring behavioral pattern across results (see below)

## Key Finding
The model performs perfectly (10/10) at both extremes: when a request maps
cleanly onto stated policy, and when it has too little information and
simply asks clarifying questions instead of guessing. It also performs well
(9.5/10) when it correctly recognizes a case as genuinely ambiguous and
hedges accordingly, deferring to human review.

Where it consistently struggles (6–8.5/10) is the **partial-coverage zone**:
requests that are *partly* covered by policy but not fully. Rather than
flagging the gap, the model tends to quietly fill it with a confident,
invented allowance — an unstated refund exception, an unconfirmed warranty
path, an unauthorized refund commitment, an assumed store-credit policy.

A separate, more serious failure mode also appeared once: on a request that
fell entirely outside the support domain (a legal case withdrawal), the
model produced a well-written, accurate-sounding response that nonetheless
should have escalated to a human immediately. It scored 8/10 by the rubric
but was rejected under an override rule, since a confident, polite, accurate
response can still be unsafe to send if it oversteps scope.

**Takeaway:** the model doesn't need more general accuracy — it needs better
calibration for when to hedge versus when to assert, particularly in
partial-coverage and out-of-scope scenarios.

## Files
- `rubric.md` — scoring criteria, thresholds, and the override rule
- `test-prompts.md` — the 8 test cases used
- `evaluations.md` — all 8 scored evaluations with reasoning, plus a full results table and pattern analysis
