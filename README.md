# Ostler

> The King's Horses could have put Humpty together if they had an *Ostler*.

Ostler is an operating model for keeping AI-assisted work moving across time.

**This is a specification seed, not software you can install.** There is no code
in this repository yet. It publishes a vocabulary, a doctrine set, and a worked
example for building durable mission continuity around AI workers. A reference
implementation may follow once the model is stable.

## What is Ostler?

Ostler treats long-running work as a durable *estate*: a collection of missions,
evidence, gates, roles, tasks, decisions, and operating memory. Its job is to
keep that estate moving — across sessions, across operators, and across any
single AI agent.

## Why does it exist?

AI workers are useful in bursts, but long-running work often fails because:

- context disappears between sessions;
- humans become the dispatcher for every small decision;
- work is remembered conversationally instead of operationally;
- blockers are mislabeled as vague "gates";
- agents stop when gate-free work still exists;
- no durable board says what is active, blocked, parked, or done.

Ostler exists to make AI-assisted work durable, inspectable, reviewable, and
resumable.

## The core model

Ostler separates:

- **the cockpit** — the thin coordinating role;
- **workers** — bounded agents or processes that perform work and return evidence;
- **missions** — durable workstreams;
- **packets** — bounded work assignments;
- **gates** — specific blocking actions;
- **actors** — the person, system, or seat required to clear a gate;
- **evidence** — paths, results, tests, notes, or artifacts that support a conclusion.

The cockpit should classify, prioritize, dispatch, review, and integrate.
It should not become the worker.

## What is in this repository?

- `docs/spec.md` — the authoritative public specification.
- `docs/concepts.md` — a narrative walkthrough of the model (start here).
- `docs/quickstart.md` — a 10-minute reading path.
- `docs/glossary.md` — short definitions for the public vocabulary.
- `docs/reference-shape.md` — an *illustrative, non-normative* sketch of what an
  implementation might contain. No real code or paths.
- `doctrine/` — standalone operating rules.
- `examples/worked-example.md` — one end-to-end example.

There is **no implementation, schema, prompt, or script** here. That is intentional
for v0.1.

## What v0.1 does

Ostler v0.1 is a modest, documentation-only target. It defines:

- a durable board of missions, packets, gates, owners, and evidence;
- a published snapshot suitable for lower-privilege readers;
- typed gates named by blocking action;
- actor/gate separation;
- gate absorption before human interruption;
- thin cockpit discipline;
- evidence-returning worker packets;
- second-set-of-eyes review for nontrivial work;
- diagnostic maturity when work stalls.

Everything above is described as a **target model**, not as running behavior.

## What v0.1 does not do

Ostler v0.1 is not yet:

- a packaged application;
- a task queue;
- a multi-agent framework;
- a scheduler;
- a replacement for human authority;
- a system that hides uncertainty.

The public seed describes the operating model first. A reference implementation
can follow after the vocabulary, schema, and examples are stable.

## Where to start

1. `docs/concepts.md` — the narrative overview.
2. `docs/spec.md` — the full specification.
3. `docs/glossary.md` — the vocabulary.
4. `examples/worked-example.md` — the model applied end to end.
5. `doctrine/` — the operating rules, read individually.

`docs/quickstart.md` lays out this same path with time estimates.

## Status

Early public seed. The model has been validated in private use, but this
repository intentionally starts with the specification and doctrine rather than a
premature implementation.

## License

MIT — see [`LICENSE`](LICENSE).
