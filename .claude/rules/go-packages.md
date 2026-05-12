---
paths:
  - "**/*.go"
---

# Preferred Go packages
Use these packages for common patterns. Do not reimplement what they provide.

- HTTP JSON responses: `github.com/matryer/respond`
- Environment variables: `github.com/caarlos0/env`
- CLI flags and commands: `github.com/alecthomas/kong`


## `caarlos0/env` or `alecthomas/kong`
- Use kong for cli tools
- Use env for servers
- Do not use both in the same binary
- Only import these packages in `main()`, avoid using them elsewhere unless there's a very good reason to do so

