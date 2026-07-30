# AGENTS.md — rfp

## Project summary

Claude Code Skill that facilitates the RFP (planning) process for new
nlink-jp projects — interactive Q&A against CONVENTIONS.md Phase 1,
producing a structured RFP document. Invoked as `/rfp [tool-name]`.

## Key commands

| Command | Purpose |
|---------|---------|
| `make install` | Copy the skill to `~/.claude/skills/rfp` |
| `make install DEST=<path>` | Copy to a custom skills directory |
| `make uninstall` | Remove the installed copy |
| `make check` (= `make test`) | Structural validation (frontmatter, relative links) |
| `make package` | Build `dist/rfp-vX.Y.Z.zip` (zip root = skill folder) |
| `make clean` | Remove `dist/` |

## Directory structure

```
rfp/
├── rfp/                   The skill — the only thing that ships
│   └── SKILL.md           Frontmatter + instructions
├── tests/
│   └── validate-skill.sh
├── Makefile
├── README.md / README.ja.md
├── CHANGELOG.md
├── CLAUDE.md / AGENTS.md
└── LICENSE
```

## Gotchas

- The skill is Markdown — no build, no behaviour tests. Structure *is*
  tested: `make check` verifies frontmatter and relative links.
- The `rfp/` subdirectory is the distribution boundary (ADR-004): `make
  package` zips exactly that directory, so the zip root is the skill folder —
  the layout claude.ai accepts. Never add repo-level files inside it, and
  never bundle README.md into the zip.
- The directory name is the slash command; frontmatter `name` must match it
  (lowercase letters, digits, hyphens only). `make check` enforces this.
- After editing SKILL.md, run `make install` to refresh the deployed copy.
- Releases follow the org checklist with `make package` in place of a binary
  build; before uploading, unzip the artifact and confirm `rfp/SKILL.md`
  sits directly under the zip root.

## Module path

Repository: `github.com/nlink-jp/rfp`
