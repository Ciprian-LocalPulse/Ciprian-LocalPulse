# Glossary

Plain-language definitions for terms used across these projects. Written for someone who understands software architecture generally but isn't a cryptography or clinical-informatics specialist — accurate, not dumbed down.

## Cryptography

**Zero-knowledge proof (ZKP)**
A method for proving a statement is true without revealing why it's true. Example: proving "I observed a malicious IP address" without revealing which IP, or proving "this transaction is compliant" without revealing the transaction's contents.

**Threshold secret sharing (Shamir's Secret Sharing)**
A way to split a secret into *n* pieces such that any *t* of them (the threshold) can reconstruct it, but *t-1* pieces reveal nothing. Used in Digital Legacy Protocol so no single key holder can unilaterally trigger release, and no single point of failure can lose it either.

**Trusted setup**
A one-time ceremony required by some zero-knowledge proof systems (including Groth16) to generate public parameters. If the ceremony's private randomness isn't fully destroyed, the security guarantee can be undermined — which is why trusted-setup ceremonies (Powers of Tau) are typically run as multi-party computations where trust is distributed across participants.

**Groth16**
A zero-knowledge proof system (a specific "SNARK" construction) known for very small proof sizes and cheap verification, at the cost of requiring a trusted setup per circuit. See `ARCHITECTURE.md` for why it was chosen over Plonk or Halo2.

**BN254**
An elliptic curve used as the mathematical foundation for the Groth16 proofs in these projects — chosen for compatibility with the Ethereum Virtual Machine's precompiled pairing operations, which keeps on-chain verification cheap where relevant.

**Ed25519**
A digital signature scheme (a specific elliptic-curve construction) used here for signing and verifying things like release authorizations. Chosen for speed, small signature size, and resistance to timing-based side-channel attacks.

**Hash-chain**
A sequence of records where each entry cryptographically incorporates the hash of the previous one (`H_n = Hash(H_{n-1} ‖ Data)`). Tampering with any past entry breaks every hash after it, making tampering detectable — but only within the system holding the chain; it doesn't by itself provide durability or independent verification.

## Healthcare interoperability

**FHIR (Fast Healthcare Interoperability Resources)**
An HL7 standard for exchanging healthcare data electronically, structured as discrete "resources" (Patient, Observation, Condition, etc.) with defined formats. MedIntelOS implements a subset of FHIR R5.

**CDS Hooks**
A specification for integrating clinical decision-support logic directly into a clinician's workflow (e.g., an EHR triggers a "hook" at a patient encounter, and a service returns advisory cards). Distinct from being a certified clinical tool — it's an integration pattern, not a guarantee of clinical validity.

**Federated learning**
A machine-learning approach where a model is trained across multiple data sources (e.g., hospitals) without the raw data ever leaving its source — only model updates are shared and aggregated centrally.

**Differential privacy**
A mathematical framework for adding calibrated noise to data or model updates so that no individual record can be reliably identified from the output, while preserving overall statistical usefulness. Referenced in MedIntelOS's federated learning experiment — see that project's own README for exactly how much of this is implemented versus planned.

## Formal methods

**TLA+**
A formal specification language (created by Leslie Lamport) for describing and mathematically checking the behavior of concurrent and distributed systems, used here to model compliance-circuit logic in Veritas Mesh before implementation.

---

*If a term you needed isn't here, that's a gap worth reporting — open an issue.*
