---
paths:
  - "**/*.go"
---

# Boring Go (Mat Ryer)

## Boring code
- Obvious beats clever. If it needs a comment to explain what it does, rewrite it.
- Consistent beats smart. Do the same thing the same way every time.
- Use the standard library. Add a dependency only when the problem genuinely warrants it.
- No init(). No package-level mutable globals. Be explicit about dependencies.

## Glancability
- A function should be understandable in 2 seconds. If not, split it.
- Target ~30 lines per function. If it doesn't fit on screen, it's doing too much.
- No named return values — they obscure what a function actually returns.
- Flat is readable. Nested is not.

## Line of sight
- Handle errors and guards first. Let the happy path flow down the left margin.
- Use early returns. Never bury the happy path inside an if block.

  Good:
    if err != nil {
        return err
    }
    // happy path here

  Bad:
    if err == nil {
        // happy path buried here
    }

## Interfaces and structs
- Accept interfaces, return structs.
- Define interfaces in the consuming package, not the producing package.
- Keep interfaces small. One or two methods is ideal.

## Errors
- Handle every error explicitly. No `_` on errors.
- Wrap with context: `fmt.Errorf("doing X: %w", err)`
- Don't log and return — do one or the other.

