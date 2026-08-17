---
name: finding-validation
description: Independently confirm, reject, deduplicate, or escalate candidate security findings using source evidence and explicit exploitability criteria.
---

# Finding Validation

## Procedure

1. Reproduce the claimed source-to-sink or security-decision path.
2. Verify attacker control and realistic preconditions.
3. Identify sanitizers, authorization checks, compiler behavior, runtime protections, and deployment mitigations.
4. Test alternate paths that could invalidate the claim.
5. Search for an existing finding with the same root cause.
6. Use safe static or dynamic evidence where available.

## Verdict criteria

- `confirmed`: Reachable security impact is demonstrated with sufficient evidence.
- `rejected`: A required path, precondition, or impact is disproven.
- `duplicate`: Another finding captures the same root cause.
- `needs-human-review`: Evidence is material but cannot be validated safely or completely.

Always explain the evidence supporting the verdict.
