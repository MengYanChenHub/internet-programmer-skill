# Screenshots

These screenshots show the skill being used in a real Hermes debugging workflow.

## 1. Root-cause diagnosis

This capture shows the skill turning a vague `npm run dev` failure into a concrete diagnosis: macOS quarantine blocked the `rolldown` native binding inside a WeChat-downloaded project.

![Root-cause diagnosis screenshot](../assets/screenshots/01-diagnosis.png)

## 2. Distinguishing the old failed process from the new healthy one

This capture shows Hermes separating stale background-process noise from the current valid state, so the user can focus on the new working dev server.

![Old failed process vs new healthy process screenshot](../assets/screenshots/02-old-vs-new-process.png)

## 3. Verified fix and runnable result

This capture shows the finished state: dependencies reinstalled, quarantine removed, build passed, and the dev server started successfully on `http://localhost:5176/`.

![Verified fix and runnable result screenshot](../assets/screenshots/03-fixed-and-running.png)
