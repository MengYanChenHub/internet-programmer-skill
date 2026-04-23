# Example prompts for Hermes

## 1. Debugging thrash
```text
Use internet-programmer-painkiller.
I am debugging a backend issue and keep guessing. Requests sometimes succeed, sometimes fail, and I cannot tell where state diverges. Identify the pain buckets, give me the immediate shortest-path fix, the system fix, and what to measure next.
```

## 2. Setup drift
```text
Use internet-programmer-painkiller.
Our project works on two senior engineers' laptops but new contributors fail during setup. Diagnose the likely friction buckets and produce a golden-path improvement plan.
```

## 3. CI drag
```text
Use internet-programmer-painkiller.
Our team waits too long for CI, and we keep re-running flaky jobs. Rank the pain points, suggest the smallest high-leverage fixes, and tell me what prevention artifacts to create.
```

## 4. Tool sprawl
```text
Use internet-programmer-painkiller.
We use too many dashboards, scripts, bots, and deployment surfaces. I want a friction audit that reduces context switching without forcing a massive platform rewrite.
```

## 5. Docs decay
```text
Use internet-programmer-painkiller.
Developers keep asking the same setup and troubleshooting questions in chat. Analyze this as a documentation/discoverability problem and propose the smallest fixes that will reduce repeat questions.
```
