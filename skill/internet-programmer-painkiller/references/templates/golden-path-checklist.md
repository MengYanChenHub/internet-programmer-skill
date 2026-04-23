# Golden path checklist

A project passes the golden-path test if a stressed but competent developer can become productive quickly.

## Setup
- [ ] One-command local setup exists
- [ ] Required versions are pinned
- [ ] Preflight checks fail fast with useful messages
- [ ] Seed data / sample env is available

## Feedback loop
- [ ] Smallest useful test command is documented
- [ ] Watch mode or fast iteration path exists
- [ ] Common failure modes are linked from docs

## Visibility
- [ ] Logs are structured enough to inspect behavior
- [ ] Runtime state can be checked without guesswork
- [ ] Network/API failures are traceable

## Docs
- [ ] README contains a known-good quick start
- [ ] Commands are copy-paste safe
- [ ] Troubleshooting section exists
- [ ] Last verified date is recorded

## Safety
- [ ] Repeated mistakes are automated away in CI or pre-commit
- [ ] Review expectations are clear
- [ ] Security checks happen early enough to avoid late churn
