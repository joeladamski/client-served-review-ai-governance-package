# WordPress Embed Plan

## Objective
Embed Served Review AI safely on WordPress landing pages for restaurant guests arriving via QR code or direct page access.

## Embed Pattern
1. Create dedicated page template (`/leave-feedback/`).
2. Insert Flowise widget/script with environment-based endpoint.
3. Display governance disclosure above widget.
4. Add consent checkbox for AI-assisted drafting.
5. Route final user-approved text to review destination.

## UX Requirements
- Mobile-first layout for table scanning flows.
- Clear “AI draft assistant, not auto-publisher” message.
- One-tap switch: short / balanced / detailed draft.
- Accessible typography and contrast compliance.

## Security & Privacy
- Enforce HTTPS only.
- Use nonce/CSRF protections on feedback submission actions.
- Minimize client-side data retention.
- Do not expose API keys in frontend code.

## Suggested Content Block (Disclosure)
“Served Review AI helps you draft feedback based on your experience. Please review and edit before submitting. Avoid including private personal information.”

## Launch Checklist
- Widget loads reliably across devices.
- Consent + disclosure visible before first prompt.
- Boundary refusal text tested end-to-end.
- Escalation path tested for high-risk prompts.
