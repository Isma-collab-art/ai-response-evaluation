# AI Response Evaluation: Customer Support

## Overview
A practice evaluation project assessing AI-generated customer support responses
against a custom rubric, simulating real-world LLM QA / evaluation work.

## What I Did
- Designed a 4-criteria scoring rubric (accuracy, completeness, tone, escalation handling)
- Wrote 8 test prompts covering easy, ambiguous, policy-edge, and out-of-scope scenarios
- Generated responses using Claude acting as a customer support agent
- Scored each response with documented reasoning
- Identified failure patterns and improvement recommendations

## Key Findings
Across the responses tested, the AI was strong on tone and factual accuracy for
straightforward policy questions, but showed two notable weak points: (1) it
sometimes invented unstated exception categories when a request fell outside
policy (a mild hallucination risk), and (2) it occasionally over-helped on
out-of-scope requests — such as walking a customer through legal case
withdrawal steps — instead of escalating to a human, even when the response
itself was well-written and factually reasonable. This highlighted an
important insight: **a high rubric score does not automatically mean a
response is safe to send.** A confident, polite, accurate-sounding response
can still violate scope boundaries, which matters more than surface quality
in customer-facing AI deployments.

## Files
- `rubric.md` — scoring criteria and thresholds
- `test-prompts.md` — the 8 test cases used
- `evaluations.md` — full scored evaluations with reasoning
