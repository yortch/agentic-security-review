---
name: repository-mapping
description: Inventory a source repository and prioritize its security-relevant components, entry points, dependencies, and privileged operations.
---

# Repository Mapping

Use this skill before vulnerability hunting.

## Procedure

1. Read repository-level instructions and architecture documentation.
2. Inventory languages, frameworks, package managers, build systems, and deployable components.
3. Exclude vendored, generated, fixture, and build-output directories unless they are shipped or executed.
4. Locate:
   - Network and user-input entry points
   - Parsers and deserializers
   - Authentication and authorization decisions
   - Privileged operations
   - Database and filesystem access
   - Cryptographic and secret-handling code
   - Native or memory-unsafe code
5. Identify security tooling already configured in CI.
6. Rank targets using exposure, privilege, input complexity, sensitive assets, implementation language, and change frequency.

## Output

Return a concise repository map with evidence-backed priorities. Mark assumptions separately from repository facts.
