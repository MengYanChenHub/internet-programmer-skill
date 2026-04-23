# Python backend example

## Typical pain points
- backend behavior is hard to inspect during debugging
- local environment differs from CI or production
- dependency versions drift
- logs are noisy but still unhelpful
- incidents repeat because fixes are not turned into runbooks

## Common pain buckets
- invisible state
- environment/setup drift
- maintenance/operational overload
- docs/discoverability gap

## Example Hermes prompt
```text
Use internet-programmer-painkiller.
I am debugging a Python backend and I keep guessing. Requests enter the service, but I cannot clearly see where state diverges before the database write. Diagnose the pain buckets, give me the immediate fix, the system fix, and what to measure next.
```

## Likely shortest-path fixes
- add structured logs around request lifecycle
- add request or correlation IDs
- compare expected vs actual payloads
- capture one reproducible failing case
- narrow the loop to one smoke test or one request path

## Good prevention artifacts
- debugging runbook
- incident-to-runbook conversion
- request tracing checklist
- smoke test for the failing path
- log field conventions

## Metrics
- time to reproduce
- time to isolate root cause
- repeated incident frequency
- number of manual debugging steps
