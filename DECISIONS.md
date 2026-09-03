# Architecture Decision Records

Short, dated records of specific technical choices — what was picked, what was rejected, and why. The point of an ADR is not to justify the decision after the fact; it's to leave the reasoning visible for whoever (including future me) has to revisit it.

Format follows the standard ADR shape: Context, Decision, Rejected alternatives, Consequences.

---

## ADR-001: Ed25519 for internal cryptographic signatures

**Status:** Accepted

**Context:** Internal microservices and protocol components need signature verification for authentication and integrity — independent of any EVM-compatible chain requirement.

**Decision:** Ed25519 (Edwards-curve Digital Signature Algorithm).

**Rejected alternatives:**
- *secp256k1* — the Bitcoin/Ethereum standard curve. Rejected because it introduces EVM-oriented overhead and complexity with no benefit for components that have no direct on-chain requirement.
- *RSA* — rejected on verification speed and key/signature size, both materially worse than Ed25519 for the same security margin.

**Consequences:** Faster signature verification, smaller memory footprint, and native resistance to timing side-channel attacks. Trade-off: Ed25519 is not the native curve of EVM-based chains, so any future component requiring direct on-chain signature verification against Ethereum-style infrastructure will need a separate scheme or a bridging layer.

---

## ADR-002: FastAPI for data-analysis and telemetry microservices

**Status:** Accepted

**Context:** Services handling data analysis and telemetry need input validation, async support for real-time sensor/collector streams, and documentation suitable for audit and compliance review.

**Decision:** FastAPI (Python).

**Rejected alternatives:**
- *Django* — rejected as too monolithic for microservice-scale components; brings structure and tooling that isn't needed at this granularity.
- *Flask* — rejected for lacking native async support and strict type validation out of the box; both would need to be bolted on rather than provided by the framework.

**Consequences:** Automatic input validation via Pydantic, native OpenAPI documentation generation (directly useful for auditability), and native `asyncio` support for real-time data streams. Trade-off: smaller ecosystem of batteries-included extensions than Django, so some functionality (admin interfaces, ORM tooling) requires explicit third-party choices rather than framework defaults.

---

## ADR-003: In-memory hash-chain for audit log integrity

**Status:** Accepted

**Context:** Audit entries need tamper-evidence during critical execution paths, without I/O latency blocking the operation being audited.

**Decision:** Cryptographic hash-chain, held in memory, with periodic snapshot persistence to disk.

Each entry is chained to the previous one: `H_n = Hash(H_{n-1} ‖ Data)`.

**Rejected alternatives:**
- *Synchronous writes to a distributed append-only store* (PostgreSQL append-only tables, TimescaleDB) — rejected for introducing I/O latency directly into the critical execution path.

**Consequences:** Tamper-evidence and immutability are guaranteed within a single running process before the asynchronous disk write occurs — and only within that process. This is explicitly **not** durable audit storage: a process crash between chain updates and the next snapshot loses unpersisted entries, and there is no independent, cross-process anchoring of the chain. Any deployment requiring durable, court-admissible audit trails needs an additional persistence layer on top of this — this hash-chain solves tamper-evidence, not durability.

---

*New entries append to this file; existing entries are not rewritten after the fact. If a decision is later reversed, that's ADR-00N (Superseded by ADR-00M), not a silent edit — see `MANIFESTO.md` on why numbers and claims here need to stay checkable.*
