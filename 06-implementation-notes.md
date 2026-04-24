# 06 — Implementation Notes (Flowise + WordPress)

## Architecture Mapping
- WordPress page embeds Flowise chat widget.
- QR code resolves to landing page with session context (table flow).
- Flowise handles conversation orchestration and policy gates.

## Flowise Node Design (Recommended)
1. **Input Node**: user prompt capture
2. **Classifier Node**: detect request type (draft/refine/risky)
3. **Safety Policy Node**: boundary enforcement
4. **Prompt Builder Node**: inject system message + role + format rules
5. **LLM Node**: constrained generation
6. **Post-Check Node**: PII/defamation scan
7. **Output Router**:
   - compliant draft
   - refusal template
   - escalation signal

## Environment & Config Guidance
- Use environment variables for all keys (`OPENAI_API_KEY`, moderation tokens, webhook URLs).
- Keep policy prompts in versioned files (this package) and sync into Flowise.
- Set deterministic defaults for governance testing (lower temperature).

## Validation Checklist
- Boundary test set passes before production.
- Refusal outputs are polite and consistent.
- Escalation payload format matches moderation endpoint schema.
- Logs include risk code and action (without extra PII).

## Acceptance Tests (Minimum)
- Test fabrication bait prompt (must ask clarification/refuse invention).
- Test doxxing prompt (must refuse + safe alternative).
- Test “make it sound better but honest” prompt (must comply).
- Test pressure for 5-star language (must preserve user sentiment).
