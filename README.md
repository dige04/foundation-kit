# OpenCode Foundation Kit

![OpenCode](https://img.shields.io/badge/OpenCode-foundation-0A84FF)
![Hive](https://img.shields.io/badge/Hive-plan--first-2F855A)
![Beads](https://img.shields.io/badge/Beads-execution-F59E0B)
![Tilth](https://img.shields.io/badge/Tilth-code--perception-0F766E)
![NotebookLM](https://img.shields.io/badge/NotebookLM-retrieval-7C3AED)

A public starter for teams that want `OpenCode` to ship with a real operating
model, not just a config file.

This starter bakes in:
- `OpenCode` as the coding-agent environment
- `Beads` as the default engineering execution layer
- optional `Hive` scaffolding for plan-first feature handoff
- optional `Tilth` integration for stronger code perception
- `NotebookLM` as retrieval only
- `docs/` and pod files as durable project memory

## Why This Starter Exists

Most AI-agent setups stop at local prompts and personal config. This starter is
meant to be cloned by a team and used as a shared foundation.

It gives you:
- a minimal root `opencode.json`
- a richer optional OpenCode profile in `examples/opencode/`
- Beads and Hive standards that do not fight each other
- optional Tilth integration and setup guidance
- pod templates for execution memory and handoff
- OpenCode role specs for planning, docs, research, review, and integration

## Install And Setup

### 1. Install OpenCode

```bash
curl -fsSL https://opencode.ai/install | bash
```

### 2. Optional: install Beads

```bash
curl -fsSL https://raw.githubusercontent.com/steveyegge/beads/main/scripts/install.sh | bash
```

Or use the helper in this repo:

```bash
bash scripts/setup-beads.sh
```

### 3. Optional: install Tilth

```bash
bash scripts/setup-tilth.sh
```

Or wire it to OpenCode user config directly after installing Tilth:

```bash
tilth install opencode
```

### 4. Launch OpenCode

```bash
opencode
```

### 5. Read the starter docs first

1. `docs/opencode-standard.md`
2. `docs/beads-standard.md`
3. `docs/tilth-integration.md`
4. `docs/agent-hive-standard.md`
5. `docs/integration-model.md`
6. `docs/code-standards.md`
7. `docs/opencode-agents/README.md`

## Usage Modes

### Minimal mode

Use the root config only:
- `opencode.json`

This keeps the repo simple and is the default recommendation.

### Foundation mode

Adapt from:
- `examples/opencode/opencode.foundation.jsonc`
- `examples/opencode/opencode.tilth.jsonc`

Use this when you want more explicit agent shaping, MCP examples, and tighter
role boundaries.

### Team-stack mode

Adapt from:
- `examples/opencode/opencode.team-stack.jsonc`

Use this when your team wants one example that shows where `Linear`,
`NotebookLM`, `Tilth`, `Context7`, and `fetch` fit into the broader stack.

Treat this file as a placeholder example, not a mandatory default.

## Working Model

```text
Linear / Figma / NotebookLM
            |
            v
      Hive + Beads runtime
            |
            v
   OpenCode agents + Tilth MCP
            |
            v
 docs/ + pods/ + .hive/
```

## Repository Layout

- `docs/` - durable standards and operating guidance
- `docs/opencode-agents/` - standardized OpenCode role specs
- `examples/opencode/` - optional advanced OpenCode config examples
- `.hive/` - optional Hive planning templates and workflow scaffolding
- `pods/` - default pod-local context, dependencies, decisions, and task memory
- `scripts/` - optional helper scripts such as Beads bootstrap

## Included Standards

- `docs/opencode-standard.md`
- `docs/beads-standard.md`
- `docs/tilth-integration.md`
- `docs/team-stack-pattern.md`
- `docs/agent-hive-standard.md`
- `docs/integration-model.md`
- `docs/code-standards.md`
- `docs/codebase-summary.md`

## Included Templates

- `.hive/templates/plan.md`
- `.hive/templates/task-spec.md`
- `.hive/templates/task-report.md`
- `pods/candidate-experience/tasks/_template.md`
- `pods/content-cms-strapi/tasks/_template.md`

## Public Starter Notes

- keep `opencode.json` minimal by default
- treat NotebookLM as retrieval only
- let Beads own engineering execution when used
- treat Tilth as optional code perception, not as memory or orchestration
- use Hive only when extra plan/report scaffolding is worth it
- promote durable knowledge into `docs/` or pod files

## Next Steps After Clone

1. keep or rename the default pods in `pods/`
2. choose whether your team is Beads-first or OpenCode-minimal first
3. decide whether to add optional Tilth integration
4. adapt `examples/opencode/opencode.foundation.jsonc` or
   `examples/opencode/opencode.tilth.jsonc` or
   `examples/opencode/opencode.team-stack.jsonc` if you need richer setup
5. replace starter wording in docs with your project-specific sources of truth
