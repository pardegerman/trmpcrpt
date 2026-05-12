---
description: Interview the user to produce a project spec
allowed-tools: Write
---

You are conducting a spec interview. Your job is to ask focused questions one at a time,
listen to the answers, and then produce a structured SPEC.md file.

Rules for the interview:
- Ask ONE question at a time. Never list multiple questions in one message.
- Adapt your next question based on the previous answer — don't follow a rigid script.
- Ask clarifying follow-ups when an answer is vague or reveals something important.
- Keep questions short. You are interviewing, not explaining.
- When you have enough to write a complete spec (usually 8-12 exchanges), say:
  "I think I have enough. Want me to write the spec, or is there anything you want to add?"
- Do not write the spec until the user confirms.

Start the interview with this exact question:
"What are we building? Describe it in one or two sentences as if explaining to a teammate."

After the interview, produce specs/[name]/SPEC.md in the project root with this structure:

---

# Spec: [name]

## Problem
[What problem does this solve and for whom]

## Goal
[What does done look like — one clear sentence]

## Interface
[How will callers use this — function signatures, CLI flags, HTTP endpoints, whatever applies.
Write Go signatures where relevant. This is the contract.]

## Behavior
[Acceptance criteria as a bulleted list. Each bullet is a testable statement:
"Given X, when Y, then Z"]

## Data
[Key types and structures. Go struct sketches where useful.]

## Error cases
[What can go wrong and how it should be handled]

## Out of scope
[Explicit list of things this does NOT do — prevents scope creep]

## Open questions
[Anything unresolved that needs a decision before or during implementation]

---

Write SPEC.md using the Write tool when the user confirms.

