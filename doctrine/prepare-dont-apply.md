# Prepare, Don't Apply

For risky changes, prefer staged preparation before live mutation.

A worker packet may produce:

- staged diffs;
- dry-run output;
- test results;
- rollback notes;
- decision cards.

Live application should be separated from preparation unless the system has explicit authority and safety bounds.

This allows review before irreversible or high-blast-radius action.
