# 01 — Client AI Governance Audit (Served Review AI)

## Executive Summary
Served Review AI operates in a **medium-high trust environment** where generated text can materially impact business reputation, customer trust, and platform integrity. Governance must prioritize factual grounding, neutrality, and privacy-safe interactions.

## Business Context
- Domain: Restaurant reviews and customer feedback
- Interfaces: QR table journey, WordPress landing pages, embedded chat
- AI Role: Draft assistant for review clarity and structure
- Human Expectation: Honest, useful, non-coercive review support

## Governance Objectives
1. Improve review quality without changing sentiment intent.
2. Prevent fabricated details and unverifiable claims.
3. Block defamation, abuse, and targeted harassment.
4. Minimize exposure of personal/sensitive data.
5. Provide clear escalation path for risky interactions.

## Risk Profile

| Risk Category | Probability | Impact | Governance Control |
|---|---:|---:|---|
| Fabricated review details | Medium | High | Truthfulness rule + explicit uncertainty handling |
| Defamation of business/staff | Medium | High | Defamation boundary + neutral rewrite flow |
| Privacy leakage (names, contacts, payment data) | Medium | High | PII redaction prompts + refusal policy |
| Coerced positive sentiment | Low-Medium | High | Neutrality and no-pressure constitutional rule |
| Prompt abuse/toxicity | Medium | Medium | Moderation layer + safe reframe |
| Legal complaint exposure | Low-Medium | High | Escalation to human moderation and logs |

## AI Constitution (Applied)
1. **Truth First:** Never invent events, identities, or outcomes.
2. **User Intent Integrity:** Preserve user sentiment and experience.
3. **Harm Minimization:** Prevent abusive, discriminatory, or defamatory output.
4. **Privacy by Default:** Remove personal identifiers unless strictly required.
5. **Transparent Limits:** Clearly state when refusing or escalating.
6. **Human Override:** Route edge cases to support/moderation.

## Governance Maturity Snapshot
- Policy coverage: Strong foundational baseline
- Technical enforcement: Requires Flowise node-level moderation and logging
- Compliance readiness: Moderate; improve with audit trails and retention policy
- Incident response readiness: Moderate; define SLA and reviewer workflow

## Recommended Controls (Priority)
- P0: System message lock + boundary tests
- P0: Defamation/privacy detection and refusal branches
- P1: Structured escalation queue for moderation team
- P1: Prompt injection resilience checks
- P2: Quarterly policy refresh with incident review

## Success Metrics
- <2% sessions requiring moderation escalation
- 0 confirmed fabricated facts emitted post-launch
- >85% user satisfaction for “helpfulness” without sentiment coercion
- 100% refusal on direct requests to include private personal data
