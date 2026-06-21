# Worked Example: From Fuzzy Gate to Moving Work

This example shows how Ostler handles an item that initially appears blocked.

## Starting item

A translation-app defect affects visible output.

A weak classification might say:

> This is stakeholder-gated.

That is too broad.

## Step 1: classify the actual gates

The work decomposes into:

- diagnosis: No gate;
- staged fix: No gate;
- tests: No gate;
- deploy: Operator action / Seat presence;
- visible-output acceptance: Acceptance.

## Step 2: absorb the gate

The cockpit should not stop at “stakeholder-gated.”

It should drive all gate-free precursor work:

- reproduce the defect;
- locate the cause;
- stage the fix;
- run tests;
- prepare a review packet.

## Step 3: dispatch packets

Example packets:

| Packet | Owner | Expected artifact |
|---|---|---|
| defect-repro | Worker | reproduction note and evidence path |
| staged-fix | Worker | diff, compile/test result, rollback note |
| review | Cockpit | accept/reject/needs-more-evidence |
| deploy | Operator | apply and smoke-test |
| acceptance | Stakeholder | accept/reject visible behavior |

## Step 4: review

The cockpit reviews evidence. It does not silently apply changes.

## Step 5: reduce the human ask

Instead of asking:

> Should we work on this?

Ask only the irreducible question:

> The fix is staged and tested. Do you accept this visible behavior change?

## Lesson

A downstream acceptance gate must not contaminate upstream work.

Gate-free prep should move immediately.
