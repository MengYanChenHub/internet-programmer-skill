---
name: internet
description: Alias skill for internet-programmer-painkiller so typing /internet in Hermes can surface the workflow quickly.
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [developer-experience, debugging, workflow, docs, focus, devops, internet]
    canonical_skill: internet-programmer-painkiller
---

# Internet

This is a short alias for `internet-programmer-painkiller`.

Use this skill when an internet programmer is blocked by workflow chaos rather than pure lack of coding knowledge.

Typical triggers:
- repeated debugging thrash
- local setup pain
- slow test/build/reload cycles
- too many tools and handoffs
- unclear runtime behavior
- stale docs or missing runbooks
- context-switch fatigue
- recurring CI/review/security friction

## Outcome

By the end of the workflow, produce these outputs when relevant:
1. A ranked list of the user's top friction points
2. One shortest-path fix for today
3. One system fix that prevents recurrence
4. A lightweight runbook or checklist update
5. A verification step with a measurable improvement

## Workflow

### Phase 1: Friction intake
Ask or infer the smallest possible set of facts:
- What task is failing?
- What is the shortest reproducible loop?
- Where is the delay?
- What repeats weekly?

Classify the pain into one or more buckets:
- feedback-loop latency
- invisible state
- environment/setup drift
- tooling fragmentation
- docs/discoverability gap
- review/security/compliance drag
- maintenance/operational overload

### Phase 2: Stabilize the loop
Before suggesting big redesigns, reduce immediate thrash:
1. Reproduce the issue in the smallest loop possible
2. Remove unrelated tools/tabs/steps
3. Capture exact commands, inputs, logs, and expected vs actual behavior
4. Add one visible probe

Rule: if the programmer says "I'm guessing," stop and add visibility first.

### Phase 3: Pick the shortest-path fix
Select only one immediate fix from this order:
1. Make the behavior visible
2. Shorten the feedback loop
3. Reduce moving parts
4. Document the known-good path
5. Automate the repeated check

### Phase 4: Produce a system fix
After the immediate fix works, choose one prevention artifact:
- troubleshooting note
- setup script
- make/task command
- runbook
- checklist
- test case
- CI guardrail
- docs example

### Phase 5: Verify improvement
Measure at least one of these:
- time to reproduce
- time to first useful feedback
- number of steps to local setup
- number of tools/tabs needed
- number of manual checks replaced
- frequency of the recurring failure

## Output format

When applying this skill, respond with:
1. Pain buckets detected
2. Immediate shortest-path fix
3. System fix to prevent recurrence
4. What to measure next

## Discoverability in Hermes

Install this folder alongside `skill/internet-programmer-painkiller/` if you want `/internet` to show an obvious skill suggestion in Hermes.

## Example invocation

- "Use internet. My local environment only works on one machine. Diagnose the pain buckets and give me the shortest-path fix."
- "Use internet. CI is slow and flaky. Rank the top friction points and propose the smallest high-leverage fixes."
- "Use internet. I keep guessing during debugging because the runtime state is unclear. Give me the immediate fix, system fix, and what to measure."
