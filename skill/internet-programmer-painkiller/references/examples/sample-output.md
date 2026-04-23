# Sample Hermes output

## Input scenario
A Node.js service works locally for one maintainer, but two teammates cannot start it reliably. CI also fails intermittently on dependency installation.

## Output
### 1. Pain buckets detected
- environment/setup drift
- feedback-loop latency
- docs/discoverability gap

### 2. Immediate shortest-path fix
- create one known-good bootstrap command
- pin Node and package-manager versions
- run the smallest install + startup smoke test locally and in CI

### 3. System fix to prevent recurrence
- add a checked-in bootstrap script
- add a quickstart section with verified commands
- add a preflight check for version mismatch
- add a CI job that runs the same smoke path as local setup

### 4. What to measure next
- number of setup steps
- time to first successful startup
- number of install-related CI failures per week
- number of setup questions asked in chat

## Why this is a good output
- it classifies the pain instead of treating it as random failure
- it starts with the shortest path to restore momentum
- it creates prevention artifacts, not just one-off advice
- it ends with measurable outcomes
