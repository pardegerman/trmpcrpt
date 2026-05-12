# trmp-crpt

## Structure
- `backend/` — backend service written in go, also includes a trmpcrpt-cli tool
- `frontend/` — frontend in react/js


## Context
- Reads crypto market data along with social media posts and indicates buy/sell signals
- Backend has a pluggable market interface so that it can be extended to read from several market sources
- All code is made to be simple to read and maintain

