---
description: Audit Go code against Mat Ryer and Karpathy principles
allowed-tools: Read, Bash(grep *)
---

Review the code for violations of these principles. Quote offending lines and suggest the fix. Only flag real problems — don't praise what's fine.

**Mat Ryer checks:**
- Happy path buried inside an if block instead of early return
- Functions longer than ~30 lines
- Nesting deeper than 2 levels
- Interface defined in the producing package
- Abstraction with only one caller
- Named return values
- init() or package-level mutable globals
- Error logged AND returned

**Karpathy checks:**
- Helper or wrapper used exactly once
- Dependency that could be replaced with stdlib
- Complex data structure where a simple one would do
- Deep call stack hiding what's actually happening
- Stateful code where stateless would work
- Abstraction introduced before the pattern appears twice

