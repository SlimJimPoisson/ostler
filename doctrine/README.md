# Doctrine

These are Ostler's standalone operating rules. Each file is short and stands on
its own; read them individually. They expand on principles stated in
`../docs/spec.md` and are not a substitute for it.

- [`actor-gate-separation.md`](actor-gate-separation.md) — actor (who must act)
  and gate type (what is blocked) are separate axes.
- [`gate-taxonomy.md`](gate-taxonomy.md) — the canonical gate types, and why
  gates are named by blocking action rather than by person.
- [`prepare-dont-apply.md`](prepare-dont-apply.md) — for risky changes, stage and
  review before live mutation.
- [`thin-cockpit.md`](thin-cockpit.md) — the cockpit coordinates; it should not
  become the worker.
- [`diagnostic-maturity.md`](diagnostic-maturity.md) — detect, interpret,
  correct, re-diagnose; a diagnosis is not complete until it produces a
  correction.
