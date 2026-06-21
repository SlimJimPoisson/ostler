# Gate Taxonomy

Gates must be named by blocking action, not by person.

Canonical gate types:

- Authority
- Credential
- Operator action
- Seat presence
- Acceptance
- External dependency
- No gate

Avoid labels such as:

- person-named gate (e.g. "Alice gate")
- role-named gate (e.g. "operator gate")
- deploy gate
- production gate
- database gate

Those labels hide the actual blocked action.

Use:

- Authority when a decision or approval is required.
- Credential when a secret, token, password, or key is required.
- Operator action when a manual or local action is required.
- Seat presence when a specific runtime or seat must be active.
- Acceptance when a stakeholder must accept the result.
- External dependency when an outside system or party must act.
- No gate when work can continue.
