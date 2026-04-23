# CI/CD example

## Typical pain points
- CI is much slower than local checks
- flaky jobs keep getting re-run
- developers do not know which failure matters first
- review catches the same repeated issues
- security or policy checks fail late in the pipeline

## Common pain buckets
- feedback-loop latency
- review/security/compliance drag
- maintenance/operational overload
- tooling fragmentation

## Example Hermes prompt
```text
Use internet-programmer-painkiller.
Our team waits too long for CI, we keep re-running flaky jobs, and review often repeats issues that should have been automated. Rank the pain points, suggest the smallest high-leverage fixes, and tell me which prevention artifacts to add.
```

## Likely shortest-path fixes
- split fast gating jobs from slow full-suite jobs
- add a local smoke command matching the most useful CI subset
- improve failure summaries so the first important error is obvious
- quarantine flaky checks with an owner and deadline
- move repetitive policy and security checks earlier

## Good prevention artifacts
- CI friction checklist
- PR template with risk prompts
- flaky-test owner list
- smaller mandatory smoke pipeline
- clearer runbook for failed pipeline diagnosis

## Metrics
- average CI runtime
- flaky failure count per week
- number of re-runs per PR
- review comments spent on repeatable issues
