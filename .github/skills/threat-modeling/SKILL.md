---
name: threat-modeling
description: Create a repository-grounded threat model covering assets, actors, trust boundaries, entry points, privileged operations, and concrete abuse cases.
---

# Threat Modeling

## Procedure

1. Identify protected assets and security objectives.
2. Define realistic attacker capabilities from repository and deployment evidence.
3. Map trust boundaries and identity transitions.
4. Enumerate entry points and privileged operations.
5. Create concrete abuse cases for each high-risk flow.
6. Connect abuse cases to the components and symbols that implement the flow.

## Rules

- Do not assume internet exposure, privilege, or deployment topology without evidence.
- Prioritize concrete misuse paths over generic threat lists.
- Record unknown deployment assumptions for validation.

## Output

Return assets, actors, boundaries, entry points, abuse cases, mitigations, and unresolved assumptions.
