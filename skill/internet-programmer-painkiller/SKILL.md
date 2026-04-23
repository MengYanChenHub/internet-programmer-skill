---
name: internet-programmer-painkiller
description: Reduce common pain points for internet programmers by diagnosing friction, shortening feedback loops, making runtime state visible, simplifying tooling, and producing concrete workflow fixes.
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [developer-experience, debugging, workflow, docs, focus, devops, internet]
    aliases: [internet]
---

# Internet Programmer Painkiller

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

## Guiding assumptions

- Most programmer pain is not lack of intelligence; it is feedback latency, hidden state, or fragmented tools.
- The first goal is not elegance. The first goal is to restore visibility and momentum.
- Fix the highest-frequency pain first, not the loudest opinion.
- Prefer defaults, templates, and golden paths over optional complexity.

## Workflow

### Phase 1: Friction intake
Ask or infer the smallest possible set of facts:
- What task is failing? build, debug, deploy, review, setup, docs, onboarding
- What is the shortest reproducible loop?
- Where is the delay? waiting, guessing, searching, switching, approval, flaky tooling
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
4. Add one visible probe:
   - structured log
   - timestamp
   - request ID
   - failing test
   - state dump
   - screenshot or trace

Rule: if the programmer says "I'm guessing," stop and add visibility first.

### Phase 3: Pick the shortest-path fix
Select only one immediate fix from this order:
1. Make the behavior visible
2. Shorten the feedback loop
3. Reduce moving parts
4. Document the known-good path
5. Automate the repeated check

Examples:
- Add a minimal repro test instead of discussing theories
- Use watch mode / hot reload / narrower test selection
- Replace a 5-step setup with one script
- Add a troubleshooting doc for the top recurring failure
- Add pre-commit or CI validation for a repeat mistake

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

Use the smallest artifact that future-you will actually maintain.

### Phase 5: Verify improvement
Measure at least one of these:
- time to reproduce
- time to first useful feedback
- number of steps to local setup
- number of tools/tabs needed
- number of manual checks replaced
- frequency of the recurring failure

If nothing measurable improved, the fix is incomplete.

## Default interventions by pain bucket

### 1. Feedback-loop latency
Symptoms:
- slow build/test/reload
- waiting before each learning cycle

Interventions:
- isolate the smallest failing test
- use watch mode
- cache dependencies/build artifacts
- split slow suites from smoke checks
- create a one-command dev start path

### 2. Invisible runtime state
Symptoms:
- "it should work"
- guessing about inputs/state/network calls

Interventions:
- add structured logs
- print or inspect intermediate state
- attach correlation IDs
- compare expected vs actual payloads
- capture traces or reproducible snapshots

### 3. Environment/setup drift
Symptoms:
- works on one machine only
- onboarding is fragile
- version mismatch pain

Interventions:
- pin versions
- create a bootstrap script
- add preflight checks
- document one golden path
- prefer devcontainers/Nix/Docker only if they reduce total complexity

### 4. Tooling fragmentation
Symptoms:
- too many tabs/apps/CLI handoffs
- task ownership unclear

Interventions:
- collapse common flows into one task runner
- define one source of truth per workflow
- remove duplicate dashboards and scripts
- create a clear escalation path

### 5. Docs/discoverability gap
Symptoms:
- stale setup docs
- tribal knowledge
- repeated Slack/chat questions

Interventions:
- example-first docs
- last-verified date
- troubleshooting section
- copy-paste-safe commands
- link docs directly from errors/CI where possible

### 6. Review/security/compliance drag
Symptoms:
- late-stage surprises
- review bottlenecks
- manual repetitive checks

Interventions:
- lightweight pre-commit checks
- dependency scanning in CI
- PR templates with risk prompts
- secure-by-default templates
- automate policy checks early

### 7. Maintenance/operational overload
Symptoms:
- fixes crowd out feature work
- same flaky failure keeps returning

Interventions:
- maintain a friction log
- rank by recurrence x severity
- reserve explicit debt budget
- quarantine flaky tests with owners and deadlines
- convert incidents into runbooks

## Anti-patterns

Avoid these traps:
- prescribing a new platform before shrinking the current problem
- adding observability that no one reads
- building a giant process document instead of one usable checklist
- optimizing edge cases before fixing the common path
- treating all friction as a people problem

## Output format

When applying this skill, respond with:
1. Pain buckets detected
2. Immediate shortest-path fix
3. System fix to prevent recurrence
4. What to measure next

## Recommended companion artifacts

- `templates/friction-log.md`
- `templates/debugging-runbook.md`
- `templates/golden-path-checklist.md`
- `templates/incident-to-runbook.md`
- `templates/ci-friction-checklist.md`

## Discoverability in Hermes

If you install the optional alias skill folder `skill/internet/`, typing `/internet` in Hermes can surface this skill faster in command suggestions while keeping the full canonical skill name `internet-programmer-painkiller` available.

## Example invocation

Use this skill with prompts like:
- "Use internet-programmer-painkiller. My local environment only works on one machine. Diagnose the pain buckets and give me the shortest-path fix."
- "Use internet. My local environment only works on one machine. Diagnose the pain buckets and give me the shortest-path fix."
- "Use internet-programmer-painkiller. CI is slow and flaky. Rank the top friction points and propose the smallest high-leverage fixes."
- "Use internet-programmer-painkiller. I keep guessing during debugging because the runtime state is unclear. Give me the immediate fix, system fix, and what to measure."
