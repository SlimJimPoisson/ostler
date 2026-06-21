# Reference Shape (Illustrative Only)

> **This document is non-normative and illustrative.**
>
> No implementation is published in v0.1. The names below are *roles*, not real
> filenames, module names, or paths. They sketch the **kind** of components a
> system conforming to this specification might have, so a reader can see that
> the model is implementable — without any code being shown.
>
> Nothing here describes, fingerprints, or commits to any actual deployment. A
> real implementation may organize itself completely differently.

## Why this document exists

A common reaction to a spec-only repository is "but what would this even look
like as software?" This page answers that question at the level of *shapes*. It
is deliberately abstract. Treat every name as a placeholder.

## Notional component roles

A conforming system might be organized around components that play these roles:

| Role (illustrative) | Responsibility implied by the spec |
|---|---|
| `board_store` | Durable persistence of the estate: missions, packets, gates, owners, status, evidence paths, wake conditions. |
| `gate_classifier` | Maps an apparent blocker to a canonical gate type (Authority, Credential, Operator action, Seat presence, Acceptance, External dependency, No gate). |
| `actor_resolver` | Attaches the required actor to a gate, kept on a separate axis from gate type. |
| `gate_absorber` | Drives gate-free precursor work and reduces a gate to its smallest human atom before declaring "blocked." |
| `packet_dispatcher` | Issues bounded work packets with an owner, expected artifact, and review path. |
| `evidence_collector` | Receives and stores the artifacts a worker returns. |
| `review_chain` | Routes nontrivial work through a second set of eyes before integration. |
| `snapshot_publisher` | Renders a reader-safe view of the board for lower-privilege observers. |
| `diagnostic_loop` | Runs detect → interpret → correct → re-diagnose when work stalls. |

These are roles, not modules. One real file might cover several; one role might
span several files.

## Notional data a board item might carry

Again illustrative — field *meanings*, not a schema:

- the mission it belongs to;
- its current status (e.g. active, blocked, parked, done);
- its owner;
- its gate type, if any, and the actor required to clear it;
- an evidence path;
- a wake condition, if parked.

## What this document is not

- It is **not** a schema. See the spec for the authoritative field list.
- It is **not** an architecture or a commitment to one.
- It is **not** derived from, and does not describe, any private deployment.

When a real reference implementation is published, it will live in its own
clearly-marked directories — not here.
