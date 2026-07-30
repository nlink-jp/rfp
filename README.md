# rfp

A Claude Code Skill that facilitates the RFP (planning) process for new
[nlink-jp](https://github.com/nlink-jp) projects. It collects requirements
through interactive Q&A, validates completeness against
[CONVENTIONS.md](https://github.com/nlink-jp/.github/blob/main/CONVENTIONS.md)
Phase 1, and generates a structured RFP document.

## Installation

### From a release zip (recommended)

Download `rfp-vX.Y.Z.zip` from
[Releases](https://github.com/nlink-jp/rfp/releases) and unzip it into your
skills directory:

```bash
unzip rfp-vX.Y.Z.zip -d ~/.claude/skills/
```

Use `.claude/skills/` inside a project instead for project-scoped installs.

On claude.ai, Claude Desktop, or mobile: upload the zip as-is under
**Settings → Skills**.

### From source

```bash
git clone https://github.com/nlink-jp/rfp.git
cd rfp
make install
```

`make install DEST=/path/to/project/.claude/skills` installs to a specific
project. `make uninstall` removes the installed copy.

## Usage

```
/rfp
/rfp my-new-tool
```

The skill walks through problem statement, feature specification, design
decisions, series placement, and development plan, then writes the RFP
document once the required information is complete.

## Development

```bash
make check     # structural validation (frontmatter, relative links)
make package   # build dist/rfp-vX.Y.Z.zip (zip root = skill folder)
```

The skill content lives in [`rfp/`](rfp/) — that directory is exactly what
`make package` ships and `make install` copies. Repository scaffolding
(README, Makefile, tests) never enters the artifact.

## History

Before v0.1.0 this skill lived in
[skills-series](https://github.com/nlink-jp/skills-series); the split is
recorded in
[ADR-004](https://github.com/nlink-jp/.github/blob/main/adr/004-skills-series-umbrella.md).

## Documentation

- [English](README.md)
- [Japanese](README.ja.md)

## License

[MIT](LICENSE)
