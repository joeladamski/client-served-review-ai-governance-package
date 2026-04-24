# Flowise Chatflow Plan (Optional)

## Goal
Create a policy-enforced chatflow that helps users draft factual restaurant reviews while preventing harmful or non-compliant outputs.

## Chatflow Stages
1. **Session Start**
   - Show short disclosure: “AI helps draft your feedback; you control final submission.”
2. **Intent Capture**
   - Draft new review / refine existing / shorten / translate
3. **Risk Screening**
   - Detect PII, abuse, defamation, coercion, illegal content
4. **Compliant Generation**
   - Apply system message + role + format constraints
5. **Post-Generation Review**
   - Secondary policy scan
6. **Output or Escalation**
   - Return draft, refusal, or moderation flag

## Suggested Variables
- `session_id`
- `entry_channel` (qr_table, wordpress_page)
- `risk_label` (none, low, medium, high)
- `escalation_required` (true/false)
- `output_mode` (quick/balanced/detailed)

## Suggested Webhooks
- `POST /moderation/events`
- `POST /analytics/review-session`
- `POST /safety/incidents`

## Operational Notes
- Keep prompts versioned and checksum-tracked.
- Set timeout and fallback response for model/API failures.
- Use idempotent webhook calls to avoid duplicate escalation tickets.
