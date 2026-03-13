# Tilth Integration

## Purpose

This document explains how to add `Tilth` to the OpenCode foundation starter as
an optional code-perception layer.

Tilth complements the existing stack:
- `OpenCode` stays the runtime and coding-agent environment
- `Hive` stays the orchestration layer when plan-first work is needed
- `Beads` stays the engineering execution memory layer
- `Tilth` improves code reading, definition lookup, callers/callees tracing, and
  large-file navigation

## What Tilth Adds

Based on the upstream `jahala/tilth` project, the most useful additions are:

- adaptive file reading for small vs large files
- definition-first search using tree-sitter
- callee expansion and callers search for impact analysis
- session dedup for repeated symbol reads in MCP mode
- optional hash-anchored edit mode with `--edit`

## When To Use It

Use Tilth when:
- the codebase is large enough that repeated `read` / `grep` loops waste time
- the team wants better symbol navigation in one call
- smaller models need stronger structure for code perception
- review and impact analysis need callers/callees context

Do not treat Tilth as:
- persistent memory
- orchestration
- the durable documentation system

## Install

Preferred local install:

```bash
cargo install tilth
```

Alternative ad hoc usage:

```bash
npx tilth
```

## OpenCode Integration Paths

### User-scope install

Tilth supports writing directly to the OpenCode user config:

```bash
tilth install opencode
```

Enable hash-anchored edit mode:

```bash
tilth install opencode --edit
```

The upstream project writes this at user scope in `~/.opencode.json`, making it
available across all projects.

### Project-scope example

This starter keeps the root `opencode.json` minimal on purpose.

If you want a project-level example instead, use:
- `examples/opencode/opencode.tilth.jsonc`
- `examples/opencode/opencode.foundation.jsonc`

## Guardrails

- keep Tilth optional by default
- do not replace the minimal root `opencode.json`
- do not present Tilth as a substitute for Hive or Beads
- do not assume every builder has Rust or Cargo installed

## References

- `https://github.com/jahala/tilth`
- `docs/opencode-standard.md`
- `docs/beads-standard.md`
- `docs/agent-hive-standard.md`
