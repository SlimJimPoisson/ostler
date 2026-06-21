# Concepts

This is a narrative introduction to Ostler. It does not add anything to the
specification; it walks through the model in `docs/spec.md` in plain language so a
new reader can build a mental picture before reading the formal spec.

> Ostler is a specification, not software. Nothing here describes running code.

## The problem in one paragraph

AI workers are good at bursts of work and bad at continuity. A long task spread
across many sessions tends to lose its thread: what was decided, what is blocked,
what could still move, and why. Ostler is a way of organizing that work so it
survives the end of any single session, operator, or agent.

## Work is an estate, not a conversation

The central move is to stop treating progress as something remembered in a chat
and start treating it as a durable **estate**: missions, the evidence behind
them, the gates blocking them, the people or systems that can clear those gates,
and the decisions already made. The estate is the source of truth. A conversation
is just one way of touching it.

## The roles

- **Cockpit** — the thin coordinator. It classifies incoming work, prioritizes
  it, dispatches it, reviews returned evidence, and integrates results. It is
  deliberately kept *thin*: the moment it starts doing the deep work itself, it
  stops being able to coordinate.
- **Workers** — bounded agents or processes. A worker is handed a packet, does a
  scoped piece of work, and returns **evidence** — not just an assertion that it
  is done.
- **Actors** — whoever (or whatever) must act to clear a gate: a person, a
  system, or a particular runtime seat.

## The units of work

- **Mission** — a durable workstream that outlives sessions.
- **Packet** — a bounded assignment with an owner, an expected return artifact,
  and a review path. Packets are how the cockpit moves work off its own desk.
- **Evidence** — the concrete support for a conclusion: diffs, test output,
  commands, paths, notes, review artifacts.

## Gates: the part most people get wrong

A **gate** is a *specific blocked action* — not a person, and not a place.

Ostler insists on two separate axes:

- **Gate type** answers *what kind of action is blocked?* (e.g. credential,
  acceptance, authority).
- **Actor** answers *who must act?* (e.g. a specific operator).

These are independent. "A credential must be placed" is the gate; "the operator
places it" is the actor. Naming a gate after a person ("the operator gate") hides
the actual blocked action and makes the work harder to reason about. See
`doctrine/gate-taxonomy.md` and `doctrine/actor-gate-separation.md`.

## Gate absorption: don't stop at the first "blocked"

A gate is not a stop sign. Before declaring work blocked, the cockpit should
**absorb** as much of the gate as possible: do every safe precursor step,
separate gate-free prep from the gated action, and reduce the human ask to the
smallest irreducible atom. A downstream acceptance gate must not freeze the
upstream diagnosis, fix, and testing that need no permission at all. The worked
example shows this in full.

## The board and its lifecycle

The estate is made visible through a **board**. Conceptually, each item on the
board carries things like: the mission it belongs to, its current status, its
owner, the gate (if any) blocking it, the evidence path, and — if parked — the
condition that should wake it.

An item moves through states such as:

```
active  →  blocked  →  (gate absorbed / cleared)  →  active  →  done
   └──────────────→  parked (owner + reason + wake condition)  ─┘
```

A **parked** item is not forgotten work; it is deferred work with an explicit
owner, reason, and wake condition. A **snapshot** is a readable view of the board
safe to share with lower-privilege readers, without exposing private ledger
detail.

## What Ostler is *not*

It is tempting to map Ostler onto something familiar — a task queue, a kanban
board, a multi-agent framework. It is none of those. Those tools move tickets;
Ostler is a discipline for **continuity, gate absorption, and accountable
review** of AI-assisted work. The vocabulary overlaps; the purpose does not.

## Where to go next

- `docs/spec.md` for the authoritative detail.
- `examples/worked-example.md` to see gate absorption applied.
- `doctrine/` for the individual operating rules.
