# Bibliography

The primary sources behind the design decisions across these projects — not a reading list assembled for appearance, but what each system is actually built on. Organized by the project that draws on it.

## Digital Legacy Protocol

- Shamir, A. (1979). "How to Share a Secret." *Communications of the ACM*, 22(11), 612–613. — the threshold secret-sharing scheme the protocol is built on.
- Bernstein, D. J., Duif, N., Lange, T., Schwabe, P., & Yang, B.-Y. (2012). "High-speed high-security signatures." *Journal of Cryptographic Engineering*, 2(2), 77–89. — Ed25519, used for release-signature verification.

## Veritas Mesh / Umbra Exchange

- Groth, J. (2016). "On the Size of Pairing-Based Non-interactive Arguments." *EUROCRYPT 2016*. — Groth16, the proving system used across both protocols.
- [arkworks](https://github.com/arkworks-rs) — the Rust zkSNARK ecosystem (BN254 curve implementation, constraint-system tooling) both protocols are built against.
- Lamport, L. (2002). *Specifying Systems: The TLA+ Language and Tools for Hardware and Software Engineers*. Addison-Wesley. — formal modeling approach used for Veritas Mesh's compliance circuits.
- [MISP Project](https://www.misp-project.org/) — the existing threat-intelligence-sharing landscape Umbra Exchange positions itself against; understanding what MISP does (and requires participants to reveal) is the baseline for the zero-knowledge gap the project targets.

## MedIntelOS

- HL7 FHIR R5 Specification — [hl7.org/fhir/R5](https://hl7.org/fhir/R5/) — the interoperability standard the FHIR resource layer implements.
- CDS Hooks Specification — [cds-hooks.hl7.org](https://cds-hooks.hl7.org/) — the clinical decision-support integration pattern used for the hooks service.
- McMahan, H. B., Moore, E., Ramage, D., Hampson, S., & y Arcas, B. A. (2017). "Communication-Efficient Learning of Deep Networks from Decentralized Data." *AISTATS 2017*. — the federated averaging approach behind the aggregation coordinator.
- Dwork, C., & Roth, A. (2014). "The Algorithmic Foundations of Differential Privacy." *Foundations and Trends in Theoretical Computer Science*, 9(3–4), 211–407. — the differential-privacy framing used (and, honestly, not yet fully implemented — see the project's own scope table) in the federated learning experiment.

## A note on how this list is used

Citing a source here doesn't mean the corresponding implementation matches the paper's guarantees exactly — several of these (particularly the differential-privacy component in MedIntelOS) are explicitly marked as experimental in the relevant repository's own README. This list exists so a reader can check the gap between the reference design and the current implementation themselves, not to imply the gap doesn't exist.
