# Manifesto

I work alone. Everything published under this account — code, documentation, the README you're reading now — is written, tested, and maintained by one person. No team, no editorial layer smoothing out claims before they ship. That has a cost and a benefit, and I'd rather state both than let either go unsaid.

## What I believe about technical writing

Most engineering writing fails before the code does. A README that oversells creates a debt the software then has to pay down — in trust, in wasted evaluation time, in the eventual, avoidable moment someone discovers the gap between the pitch and the repository. I've written that kind of README before. I don't anymore.

So: every project here states its maturity level in plain terms — *prototype*, *alpha*, *production* — and the project name is never allowed to promise more than the code delivers. If something is untested, it says so. If something is a proof of concept with no backend, it says so on the first line, not buried in a FAQ.

## What I believe about scope

A system that claims to do everything usually does nothing well enough to trust. Every repository here ships with an explicit scope table: what's implemented, what's deliberately out of bounds, and what a reader shouldn't assume from the project's name alone. MedIntelOS says, in its own README, that it is not a certified EHR. That sentence cost nothing to write and would have cost a great deal to discover the hard way, in someone else's production environment.

## What I believe about numbers

If I state a figure — a test count, a coverage percentage, a version number — it's a number I can point to in CI, not one chosen because it sounds credible. I'd rather publish fewer claims and have all of them hold up than publish an impressive-sounding profile that doesn't survive a second look from someone who knows the domain.

## What I believe about being solo

Working alone means no second reviewer catches my blind spots before the world does. I try to compensate for that with tests, threat-model documents, and explicit disclaimers rather than with confidence. If you find something wrong — a claim that doesn't hold, a diagram that doesn't match the code, a gap in the threat model — I want to know. Open an issue. That's not a courtesy line; it's the actual mechanism I rely on in place of a team.

## What this is not

This is not a pitch. If you're evaluating whether to collaborate, hire, or fund something here, the README tables and the repository scope docs are the actual evidence — read those, not this page. This page exists to explain the standard I'm holding myself to, so that when a claim here turns out to be wrong, you know exactly what kind of failure that is: a mistake to fix, not a pattern to expect.

---

*Last revised: check the commit history of this file — that date is more honest than one written by hand and left to go stale.*
