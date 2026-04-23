# Internet Programmer Painkiller

A research-backed Hermes skill for internet programmers who are drowning in tool sprawl, slow feedback loops, invisible runtime state, stale docs, and constant context switching.

This project consolidates signals from YouTube talks, industry surveys, and developer-experience reports, then turns them into one reusable skill:

- skill name: `internet-programmer-painkiller`
- purpose: reduce recurring engineering friction before it turns into burnout, thrash, and technical debt

## What this skill helps with

The skill is designed for programmers who repeatedly say things like:

- "I can't see what the program is doing."
- "The edit-run-debug loop is too slow."
- "There are too many moving parts."
- "The docs are stale or scattered."
- "I spend more time stitching tools together than solving the problem."

## Core pain points consolidated from research

1. Accidental complexity
2. Slow feedback loops
3. Invisible runtime state
4. Tool fragmentation and context switching
5. Poor discoverability and stale documentation
6. Maintenance work and operational drag crowding out creation
7. Security/review/compliance friction arriving too late

## Deliverables in this repo

- `skill/internet-programmer-painkiller/SKILL.md` — the reusable skill
- `research/sources.md` — research summary with source links
- `templates/friction-log.md` — recurring pain capture template
- `templates/debugging-runbook.md` — reproducible debugging worksheet
- `templates/golden-path-checklist.md` — setup/docs/tooling checklist

## How to use

1. Copy the skill directory into your Hermes skills directory, or adapt the content for your own agent framework.
2. Load the skill whenever a programmer needs help with:
   - debugging loops
   - setup friction
   - workflow cleanup
   - DX improvements
   - taming tool sprawl
3. Follow the triage workflow in the skill.

## Design principles

- Make runtime behavior visible.
- Shorten feedback loops first.
- Prefer fewer moving parts.
- Standardize debugging.
- Write docs for the next stressed developer.
- Automate recurring safety checks.

## Source classes used

- YouTube talks on programming complexity, feedback loops, and interfaces
- Developer surveys and ecosystem reports
- DevOps / DX / DevSecOps research

See `research/sources.md` for the consolidated evidence base.

## License

MIT
