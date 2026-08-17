# Agentic Security Review Demo

This repository-level configuration provides five GitHub Copilot custom agents and seven Agent Skills for a staged, defensive source-code security review.

## Demo flow

Select the indicated custom agent and submit the corresponding prompt.

### 1. Start the review

**Agent:** `security-orchestrator`

> Run a defensive security review of this repository. First map the repository, then perform broad triage, deepen the most credible candidates, and independently validate them. Use only local, non-destructive testing. Stop before modifying code and summarize the results.

### 2. Map the repository

**Agent:** `repository-mapper`

> Map this repository's entry points, trust boundaries, sensitive operations, and highest-risk components. Recommend the five best targets for deeper security analysis.

### 3. Run broad hunting

**Agent:** `vulnerability-hunter`

> Perform a broad security triage of `[component or folder]`. Identify only candidates with a concrete attacker-controlled input, reachable sensitive operation, and plausible impact. Do not modify code or confirm your own findings.

Run this prompt in parallel against different components.

### 4. Deepen a candidate

**Agent:** `vulnerability-hunter`

> Investigate this candidate in depth: `[paste candidate]`. Trace the complete attack path, check relevant callers and controls, search for related variants, and return a structured candidate finding for independent validation.

### 5. Validate independently

**Agent:** `adversarial-validator`

> Independently validate this candidate: `[paste candidate]`. Attempt to disprove it, verify attacker control and reachability, identify mitigations, and use a safe local test if appropriate. Return `confirmed`, `rejected`, `duplicate`, or `needs-human-review`.

### 6. Create the remediation

**Agent:** `remediation-engineer`

> Remediate this independently confirmed finding: `[paste validated finding]`. Implement the smallest complete fix, add a regression test, and run the relevant existing checks. Do not create a pull request.

### 7. Verify and summarize

**Agent:** `security-orchestrator`

> Verify the remediation independently. Re-run the relevant security analysis and regression tests, confirm the original attack path is closed, and summarize the finding, evidence, fix, and residual risk.

## Fast single-prompt demo

**Agent:** `security-orchestrator`

> Demonstrate the complete security-review workflow against `[folder or component]`: map the attack surface, run broad triage, investigate the strongest candidate, validate it independently, and propose a remediation with a regression test. Use safe local testing only and stop before changing code.

## Included customization

Custom agents are stored under `.github/agents`.

Agent Skills are stored under `.github/skills`.
