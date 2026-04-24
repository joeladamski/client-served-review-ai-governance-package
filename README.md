# Served Review AI Governance Package

A GitHub-ready, client-facing AI governance deliverable for **Served Review AI** (demo Fiverr client), built for a restaurant feedback ecosystem that combines:
- **Flowise chatflows** for guided review writing
- **WordPress landing pages** for public interactions
- **QR-code table flows** for in-restaurant review capture

This package follows an **AI Constitution governance model** focused on trustworthy, safe, and useful outputs.

---

## 1) Architecture Plan (System-Level)

### Objective
Enable customers to write honest, actionable restaurant reviews while preventing harmful, fabricated, coercive, or privacy-violating content.

### Core Components
1. **Entry Layer (WordPress + QR Pages)**
   - Hosts chat widget and policy notice
   - Collects explicit consent for AI-assisted drafting
2. **Conversation Layer (Flowise)**
   - Orchestrates prompts, memory windows, guardrails, and fallbacks
   - Applies moderation and escalation paths
3. **Governance Layer (AI Constitution Rules)**
   - Defines non-negotiable boundaries
   - Enforces escalation and refusal policies
4. **Human Oversight Layer**
   - Handles legal-risk, defamation, self-harm, or privacy incidents
   - Receives traceable logs (without unnecessary personal data)

### Data & Safety Principles
- Data minimization first
- No forced positivity or sentiment bias
- No fabrication of events, names, or outcomes
- No doxxing, no private data exposure
- Controlled escalation for high-risk requests

---

## 2) Repository File Structure

```text
README.md
01-client-ai-governance-audit.md
02-system-message.md
03-assistant-role-definition.md
04-boundaries-and-escalation.md
05-response-format-rules.md
06-implementation-notes.md
07-future-upgrade-path.md
optional-flowise/flowise-chatflow-plan.md
wordpress-embed-plan.md
```

---

## 3) Key Logic Explanation

### Why AI Constitution for Served Review AI
The AI Constitution model is ideal for customer-feedback systems because it creates explicit, testable policy behavior around truthfulness, harm prevention, and user autonomy.

### Operating Logic
- **Assist, don’t author reality:** The assistant helps users express experience clearly, but does not invent facts.
- **Protect all parties:** Prevents harassment/defamation against businesses and protects customer privacy.
- **Escalate uncertainty/risk:** When legal, safety, or privacy thresholds are crossed, route to a safer flow or human review.
- **Maintain neutrality:** Never pressure users to leave positive reviews.

---

## Included Deliverables
- Governance audit + risk profile
- Production-style system message
- Assistant role definition and behavior scope
- Hard boundaries and escalation policy
- Response formatting rules for consistency
- Flowise implementation blueprint
- WordPress embed integration plan
- Future roadmap with upgrade phases

---

## Recommended Usage
1. Review `01-client-ai-governance-audit.md` with stakeholders.
2. Implement the system message and role definition in Flowise.
3. Configure WordPress embed controls and policy disclosure.
4. Run acceptance tests from implementation notes before launch.
5. Use the upgrade path for multilingual, analytics, and compliance maturity.
