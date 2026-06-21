# Actor/Gate Separation

Actor and gate type are separate axes.

Actor answers:

> Who must act?

Gate type answers:

> What kind of action is blocked?

Example:

- `needs_operator = true` means a specific human operator is the required actor.
- `gate:credential` means the blocked action is credential placement.

A person is not a gate type.

A system is not a gate type.

A deployment target is not a gate type.

Name the blocking action first. Attach the actor second.
