# CLAUDE.md — rfp

**Organization rules (mandatory): https://github.com/nlink-jp/.github/blob/main/CONVENTIONS.md**

See [`AGENTS.md`](AGENTS.md) for commands, structure, and gotchas.

## Non-negotiable rules

- **Docs in sync** — update `README.md` and `README.ja.md` in the same commit as behaviour changes.
- **Small, typed commits** — `feat:`, `fix:`, `docs:`, `chore:`
- **`make check` before committing** — structural validation is this repo's test suite.
- **The `rfp/` subdirectory is the distribution boundary** — only skill
  content goes inside it; `make package` ships exactly that directory (ADR-004).

## Communication Language

All communication between contributors and Claude Code is conducted in **Japanese**.
