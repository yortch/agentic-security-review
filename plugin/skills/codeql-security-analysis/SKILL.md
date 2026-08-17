---
name: codeql-security-analysis
description: Use existing CodeQL configuration and results, run appropriate security suites, and author narrowly scoped custom queries when repository-specific analysis is required.
---

# CodeQL Security Analysis

## Procedure

1. Detect existing CodeQL workflows, configuration, packs, and databases.
2. Prefer the repository's existing configuration and supported query suites.
3. Run the smallest query scope that answers the security question.
4. Trace sources, sinks, sanitizers, barriers, and path explanations.
5. Use custom queries only when built-in queries cannot express the repository-specific rule.
6. Validate custom queries with positive and negative test cases.
7. Export or preserve results in SARIF when the existing workflow supports it.

## Rules

- Treat CodeQL alerts as evidence, not automatic proof of exploitability.
- Do not reduce precision by removing valid sanitizers or barriers.
- Do not change production code while investigating a query.
- Document query-suite versions and relevant configuration.

## Output

For each result include the query, source, sink, path, relevant sanitizer behavior, and remaining uncertainty.
