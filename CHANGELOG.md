# Changelog

Changes to this profile itself — the README, the repository description, and the supporting documents. Not a project changelog (MedIntelOS and the other repositories keep their own); this one tracks the profile as a document.

Format: newest first. Each entry states what changed and, where it matters, why.

---

## [ fill in date ]

- Added `GLOSSARY.md` — plain-language definitions for terms used across the cryptography and healthcare-interoperability projects.

## [ fill in date ]

- Added `.well-known/security.txt` (RFC 9116) on agentflow-enterprise.com, referencing `SECURITY.md` as policy.

## [ fill in date ]

- Added `CITATION.cff` to MedIntelOS, enabling GitHub's native "Cite this repository" button. ORCID iD added: 0009-0006-1340-0232.

## [ fill in date ]

- Added `ARCHITECTURE.md` — documents the Veritas Mesh / Umbra Exchange relationship and the Groth16 vs. Plonk/Halo2 decision.
- Added `DECISIONS.md` — first three ADRs: Ed25519 for internal signatures, FastAPI for telemetry services, in-memory hash-chain for audit logs.

## [ fill in date ]

- Added `FUNDING.yml`, `SECURITY.md`, and `BIBLIOGRAPHY.md` at the profile level.

## [ fill in date ]

- Added `MANIFESTO.md` and `now.md`.

## [ fill in date ]

- Rewrote the profile README: replaced marketing language ("Sovereign AI Architect," "Tier-2 Banks," NDA framing) with a maturity-labeled project table and honest scope statements. Restored the original dark visual identity (capsule banner, ASCII mission log, typing animation) alongside the honest content, plus mermaid diagrams for the systems map and the Digital Legacy Protocol state machine.

## [ fill in date ]

- **Still pending:** repository description and topics on `Ciprian-LocalPulse/Ciprian-LocalPulse` still read "Lead Enterprise Architect... Sovereign AI, Zero-Trust... DORA/PSD2... Tier-2 Banks... NDA protocols," with topics `air-gapped`, `b2b-fintech`, `financial-infrastructure`, `dora-compliance`, `enterprise-security`, `gdpr`. This contradicts the README above it and is the single highest-priority fix remaining. Replace with the shorter description and topics already drafted; remove this line once done.

---

*This file is itself an example of the principle in `MANIFESTO.md`: an unresolved item stays visible here until it's actually fixed, not quietly dropped.*
