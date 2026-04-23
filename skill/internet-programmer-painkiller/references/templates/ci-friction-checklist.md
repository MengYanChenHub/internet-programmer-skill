# CI friction checklist

Use this when CI/review is slowing the team down.

## Signals of friction
- [ ] CI is much slower than the local smoke path
- [ ] The same flaky check fails repeatedly
- [ ] Developers merge without understanding failing jobs
- [ ] Reviewers spend time pointing out repeatable issues
- [ ] Security checks only fail late in the pipeline
- [ ] Logs are noisy and hard to scan
- [ ] One failure blocks unrelated work

## Diagnosis
- Slowest job:
- Average CI runtime:
- Fastest useful local check:
- Most repeated failure:
- Flaky owner:
- Time lost per week:

## Smallest high-leverage fixes
- [ ] Add a local smoke command matching the most valuable CI subset
- [ ] Split slow jobs from fast gating jobs
- [ ] Cache dependencies and build artifacts
- [ ] Quarantine flaky tests with an owner and deadline
- [ ] Improve failure summaries so the first error is obvious
- [ ] Move security or policy checks earlier
- [ ] Add PR template prompts for risky changes

## Verification
- Before CI runtime:
- After CI runtime:
- Before manual review comments on repeat issues:
- After:
- Before flaky failure count per week:
- After:
