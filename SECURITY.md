# Security Policy

This file covers vulnerability reporting across every public repository under this account. Individual repositories may carry their own `SECURITY.md` with project-specific detail (MedIntelOS does); this one is the fallback and the single point of contact when a project doesn't have its own.

## Reporting a vulnerability

**Do not open a public issue for a security finding.**

Report privately via:

- [ your preferred channel — GitHub Security Advisories on the specific repo is the standard mechanism: repo → Security → Advisories → "Report a vulnerability" ]
- Email: [ fill in a contact address you actually monitor ]

Please include:

- The repository and, if applicable, the commit or version affected
- Steps to reproduce, or a proof of concept
- The potential impact as you understand it

## What to expect

- **Acknowledgment:** [ fill in — e.g. within 5 business days. State a number you can actually meet, not an aspirational one. ]
- **Status updates:** as the investigation progresses, not on a fixed cadence I can't guarantee alone.
- **Disclosure:** coordinated — I'll agree on a timeline with you before any public writeup, and credit you unless you prefer otherwise.

## Scope

This covers code and infrastructure I maintain and publish under this account. It does not cover:

- Third-party dependencies (report those upstream — I'll help identify the right place if you're unsure)
- Social engineering, physical security, or denial-of-service testing against any live services
- Findings in repositories explicitly marked as proof-of-concept or UI-kit-only, where the README already states there's no backend or real data path

## A note on solo maintenance

There is no security team behind this account — there's one person. That means response times are honest-effort, not SLA-backed. If something is urgent (active exploitation, data exposure), say so explicitly in the first line of your report.
