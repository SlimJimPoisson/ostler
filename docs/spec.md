# Ostler Specification

## Purpose

Ostler is a mission-continuity operating model for AI-assisted work.

Its purpose is to prevent long-running work from disappearing, stalling, or becoming dependent on one chat, one operator, or one moment of attention.

Ostler treats work as an estate: a durable collection of missions, evidence, gates, roles, tasks, decisions, and operating memory. Its job is to keep that estate moving.

## Core problem

AI-assisted work often fails when:

- context is lost between sessions;
- work is remembered conversationally but not operationally;
- blockers are mislabeled as vague gates;
- agents wait for humans when gate-free work remains;
- humans become dispatchers for every small task;
- decisions are not separated from implementation;
- no durable board explains what is active, parked, blocked, or complete.

## Core idea

Ostler separates:

- work from conversation;
- actors from gate types;
- authority from implementation;
- diagnosis from correction;
- mission continuity from any single agent session.

A running Ostler system maintains a durable board of work, records operating doctrine, tracks evidence paths, and keeps missions moving through bounded work packets.

## v0.1 target

Ostler v0.1 should support the following.

### Durable board

A board should track:

- active missions;
- findings;
- packets;
- gates;
- owners;
- status;
- evidence paths;
- wake conditions.

### Published snapshot

The system should be able to publish a readable board snapshot for lower-privilege readers or observers while keeping private ledger details protected.

### Gate taxonomy

Gates are typed by blocking action, not by person.

Canonical gate types:

- Authority
- Credential
- Operator action
- Seat presence
- Acceptance
- External dependency
- No gate

### Actor/gate separation

Actor means who must act.

Gate type means what kind of action is blocked.

Example:

- `needs_operator = true` means a specific human operator is the required actor.
- `gate:credential` means the blocked action is credential placement.

Those are separate axes.

### Gate absorption

A gate is not a stop sign.

Before declaring work blocked, the system should attempt to:

- resolve the issue from existing evidence;
- split gate-free prep from gated action;
- reduce the gate to the smallest human atom;
- prepare scripts, dry-runs, review packets, or decision cards;
- dispatch bounded work that does not require human authority.

### Thin cockpit

The cockpit coordinates. It does not become the worker.

The cockpit should:

- classify;
- prioritize;
- dispatch;
- review;
- integrate;
- preserve continuity.

Deep research, implementation, testing, and evidence-building should become bounded work packets.

### Second set of eyes

Nontrivial work requires review.

The system should prefer evidence-returning work packets and explicit review chains over silent implementation.

### Diagnostic maturity

Ostler should learn from stalls.

Diagnostic stages:

1. Detect — notice a stall, loop, false gate, retention problem, bad label, or queue paralysis.
2. Interpret — identify the actual mechanism, not merely the symptom.
3. Correct — create doctrine, board, schema, packet, test, or migration changes that prevent recurrence.
4. Re-diagnose — run the diagnostic loop again when a stall recurs or a new fuzzy category appears.

A diagnosis is not complete until it produces one of:

- a tested correction;
- a dispatched correction packet;
- a decision card;
- a parked item with owner, reason, and wake condition.

## v1.0 direction

Ostler v1.0 aims to become a general-purpose AI mission-continuity operating layer.

Future work may include:

- multiple concurrent workstreams;
- durable mission state;
- structured role handoff;
- evidence-linked decisions;
- gate classification and reduction;
- resumable context for new agents;
- audit trails;
- public/private board separation;
- safe deployment and operator-action workflows;
- self-diagnosis of stalls and recurring failure modes.

The goal is not unsafe autonomy.

The goal is accountable, inspectable, recoverable AI-assisted work.

## Design principle

Ostler should not hide uncertainty.

It should expose:

- what is known;
- what is assumed;
- what is blocked;
- who must act;
- what can proceed now;
- what evidence supports the current state.
