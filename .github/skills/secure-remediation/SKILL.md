---
name: secure-remediation
description: Fix a validated vulnerability with a minimal root-cause correction, regression coverage, and verification using the repository's existing engineering practices.
---

# Secure Remediation

## Procedure

1. Confirm the finding has an independent `confirmed` verdict.
2. Identify the root cause and all directly related variants.
3. Reuse existing validation, authorization, encoding, memory-safety, or cryptographic helpers.
4. Implement the smallest complete fix.
5. Add a regression test that exercises the validated attack path.
6. Run relevant tests, builds, linters, and security checks.
7. Document compatibility impact and residual risk.

## Rules

- Do not suppress alerts or weaken validation.
- Do not remove security tests.
- Avoid unrelated refactoring.
- Preserve public behavior unless the insecure behavior must change.
- Require human approval before opening or merging a pull request.
