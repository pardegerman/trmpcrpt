---
description: Read SPEC.md and produce an ordered task list in TASKS.md
allowed-tools: Read, Write, TodoWrite
---

Read specs/[spec name]/SPEC.md.

Analyze the spec and produce an ordered task list. Tasks must be:
- Atomic — one concrete thing to do
- Ordered by dependency — nothing depends on something listed after it
- Testable — it is obvious when the task is done

Use this Go-idiomatic ordering:
1. Define types and interfaces (the contract, no implementation yet)
2. Write failing tests for each behavior in the spec's Behavior section
3. Implement each behavior to make the tests pass
4. Implement error cases from the spec's Error cases section
5. Wire up / integrate (main, CLI flags, HTTP handler — whatever applies)
6. Verify each acceptance criterion from the spec manually

Write tasks/[spec name]/TASKS.md to the project root in this format:

---

# Tasks: [spec name]

Generated from specs/[spec name]/SPEC.md. Check off tasks as they are completed.

## Pending
- [ ] T01: [task description] — [which spec section this satisfies]
- [ ] T02: [task description] — [which spec section this satisfies]
...

## Completed
(tasks move here when done)

---

After writing TASKS.md, load all tasks into TodoWrite so they are tracked in this session.
Each task content should be the task description. Each activeForm should be the present
continuous form (e.g. "Define X" → "Defining X").
All tasks start as pending.

Tell the user how many tasks were created and which ones are good candidates to start with.

