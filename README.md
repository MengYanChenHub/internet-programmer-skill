# Internet Programmer Painkiller

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![Hermes Skill](https://img.shields.io/badge/Hermes-Skill-6f42c1)](./skill/internet-programmer-painkiller/SKILL.md)
[![Chinese README](https://img.shields.io/badge/README-中文-red)](./README.zh-CN.md)
[![Last Commit](https://img.shields.io/github/last-commit/MengYanChenHub/internet-programmer-skill)](https://github.com/MengYanChenHub/internet-programmer-skill/commits/main)

English | [简体中文](./README.zh-CN.md)

A research-backed Hermes skill for programmers who are losing time to tool sprawl, slow feedback loops, invisible runtime state, stale docs, and constant context switching.

This repository turns those pain points into a reusable operating playbook:
- a Hermes skill
- practical templates
- copy-paste examples
- framework-specific scenarios
- research references

## Table of Contents

- [Why this exists](#why-this-exists)
- [What is inside](#what-is-inside)
- [Who this is for](#who-this-is-for)
- [What the skill does](#what-the-skill-does)
- [Quick start](#quick-start)
- [How to use this inside Hermes](#how-to-use-this-inside-hermes)
- [Framework-specific examples](#framework-specific-examples)
- [Recommended workflow](#recommended-workflow)
- [Example use cases](#example-use-cases)
- [Design principles](#design-principles)
- [Research basis](#research-basis)
- [Repository structure](#repository-structure)
- [Contributing ideas](#contributing-ideas)
- [License](#license)

## Why this exists

Most programmer pain is not about syntax.
It is about workflow friction:
- too much accidental complexity
- slow edit-run-debug loops
- invisible runtime behavior
- fragmented tools and handoffs
- stale or scattered documentation
- review/security friction arriving too late
- maintenance toil crowding out real work

This repo turns those patterns into one reusable skill: `internet-programmer-painkiller`.

## What is inside

### Core skill
- `skill/internet-programmer-painkiller/SKILL.md`

### Research
- `research/sources.md` — consolidated YouTube + survey/report sources

### Templates
- `templates/friction-log.md` — capture recurring pain and rank what to fix first
- `templates/debugging-runbook.md` — reduce debugging guesswork
- `templates/golden-path-checklist.md` — improve setup/docs/iteration quality
- `templates/incident-to-runbook.md` — turn repeated incidents into reusable operating knowledge
- `templates/ci-friction-checklist.md` — find avoidable CI/review delays

### Examples
- `examples/example-prompts.md` — ready-to-use prompts for Hermes
- `examples/sample-output.md` — example diagnosis and improvement plan
- `examples/frameworks/nextjs.md` — Next.js setup and debugging friction examples
- `examples/frameworks/python-backend.md` — Python backend reliability and observability examples
- `examples/frameworks/ci-cd.md` — CI/CD delay and flaky pipeline examples

## Who this is for

Use this if you are a:
- solo developer drowning in setup/debugging churn
- startup engineer switching between code, infra, CI, and docs
- tech lead trying to reduce team thrash
- DX / DevOps / platform engineer improving developer workflows
- maintainer who keeps seeing the same failures repeat

## What the skill does

When loaded, the skill helps you:
1. classify the pain into buckets
2. stop guesswork by restoring visibility
3. pick the shortest-path fix for today
4. create one prevention artifact for tomorrow
5. verify measurable improvement

Pain buckets covered:
- feedback-loop latency
- invisible state
- environment/setup drift
- tooling fragmentation
- docs/discoverability gaps
- review/security/compliance drag
- maintenance/operational overload

## Quick start

### Option 1: use the repo as reference only
Read the skill and copy its workflow into your own agent or team process.

### Option 2: install it as a local Hermes skill
Copy the skill directory into your Hermes skills folder:

```bash
mkdir -p ~/.hermes/skills/
cp -R skill/internet-programmer-painkiller ~/.hermes/skills/
```

Then start Hermes and load the skill.

## How to use this inside Hermes

### 1. Start Hermes
```bash
hermes
```

### 2. Load the skill in a session
```text
/skill internet-programmer-painkiller
```

Or preload it when launching Hermes:

```bash
hermes -s internet-programmer-painkiller
```

### 3. Ask for a friction diagnosis
Example prompts:

```text
Use internet-programmer-painkiller.
My Next.js project works on one machine but not another. npm install and dev startup keep failing in slightly different ways. Diagnose the pain buckets, give me the shortest-path fix, and tell me what prevention artifact to create.
```

```text
Use internet-programmer-painkiller.
Our team loses a lot of time waiting for CI, fixing flaky checks, and re-explaining setup steps to new developers. Produce a friction audit, rank the top issues, and suggest the smallest high-leverage fixes.
```

```text
Use internet-programmer-painkiller.
I keep guessing during debugging because I cannot see what my backend is doing between request entry and database write. Give me the immediate fix, the system fix, and what to measure.
```

### 4. Expected output shape
A good response from Hermes should include:
1. pain buckets detected
2. immediate shortest-path fix
3. system fix to prevent recurrence
4. what to measure next

### 5. Useful Hermes commands
```bash
hermes skills list
hermes -s internet-programmer-painkiller
```

```text
/skill internet-programmer-painkiller
/help
```

## Framework-specific examples

If you want a faster starting point, open one of these:
- `examples/frameworks/nextjs.md`
- `examples/frameworks/python-backend.md`
- `examples/frameworks/ci-cd.md`

These files contain:
- typical pain buckets
- example Hermes prompts
- likely shortest-path fixes
- useful prevention artifacts
- suggested metrics

## Recommended workflow

1. Run one real case through the skill.
2. Save the resulting checklist, runbook, or script.
3. Add the recurring issue to `templates/friction-log.md`.
4. Reuse the skill every time the same class of friction returns.
5. Track whether time-to-feedback or setup complexity actually improves.

## Example use cases

### Case 1: slow local feedback loop
Problem:
- tests take too long
- engineers stop running them locally
- bugs escape to CI

Likely output:
- pain bucket: feedback-loop latency
- immediate fix: isolate a smoke subset + watch mode
- prevention artifact: one-command local test shortcut
- measure: time to first useful feedback

### Case 2: invisible runtime state
Problem:
- developers say “it should work” but cannot see actual payloads/state transitions

Likely output:
- pain bucket: invisible state
- immediate fix: add structured logs / request IDs / state dump
- prevention artifact: debugging runbook
- measure: time to reproduce and isolate the bug

### Case 3: onboarding/setup chaos
Problem:
- new contributors need handholding to boot the project

Likely output:
- pain bucket: environment/setup drift
- immediate fix: one known-good bootstrap command
- prevention artifact: golden path checklist + verified quickstart
- measure: number of setup steps and onboarding failure rate

## Design principles

- Make runtime behavior visible.
- Shorten feedback loops first.
- Prefer fewer moving parts.
- Standardize debugging.
- Write docs for the next stressed developer.
- Automate recurring safety checks.

## Research basis

This skill was informed by:

### YouTube
- Rich Hickey — Simple Made Easy
- Bret Victor — Inventing on Principle
- Bret Victor — The Future of Programming
- Douglas Engelbart — The Mother of All Demos

### Other sources
- Stack Overflow Developer Survey 2024
- JetBrains State of Developer Ecosystem 2024
- Stripe Developer Coefficient
- Google Cloud / DORA DevOps Research
- GitLab Developer Survey / DevSecOps Report

See `research/sources.md` for links and synthesis.

## Repository structure

```text
.
├── README.md
├── README.zh-CN.md
├── research/
│   └── sources.md
├── skill/
│   └── internet-programmer-painkiller/
│       └── SKILL.md
├── templates/
│   ├── ci-friction-checklist.md
│   ├── debugging-runbook.md
│   ├── friction-log.md
│   ├── golden-path-checklist.md
│   └── incident-to-runbook.md
└── examples/
    ├── example-prompts.md
    ├── sample-output.md
    └── frameworks/
        ├── ci-cd.md
        ├── nextjs.md
        └── python-backend.md
```

## Contributing ideas

Useful future additions:
- language/framework-specific variants
- onboarding audit checklist
- flaky-test reduction playbook
- docs freshness automation
- PR/review latency scorecard

## License

MIT
