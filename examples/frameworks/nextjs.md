# Next.js example

## Typical pain points
- project runs on one machine but fails on another
- `npm install` / `pnpm install` behaves differently across environments
- hot reload is slow or inconsistent
- environment variables are missing or undocumented
- build errors are only caught in CI

## Common pain buckets
- environment/setup drift
- feedback-loop latency
- docs/discoverability gap
- tooling fragmentation

## Example Hermes prompt
```text
Use internet-programmer-painkiller.
My Next.js app works on one laptop but not another. Dependency installation and local startup fail in slightly different ways. Diagnose the pain buckets, give me the immediate shortest-path fix, suggest one prevention artifact, and tell me what to measure next.
```

## Likely shortest-path fixes
- pin Node and package-manager versions
- add one known-good bootstrap command
- add a minimal local smoke path: install + dev start or build
- make required env vars explicit in `.env.example`
- reduce guesswork with one troubleshooting section

## Good prevention artifacts
- verified quickstart doc
- bootstrap script
- `.nvmrc` / version pinning
- `.env.example`
- local smoke command mirrored in CI

## Metrics
- time to first successful startup
- number of setup steps
- number of install-related CI failures
- number of repeated setup questions
