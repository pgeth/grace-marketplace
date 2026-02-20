# GRACE Framework — Claude Code Plugin

**GRACE** (Graph-RAG Anchored Code Engineering) is a methodology for AI-driven code generation with semantic markup, knowledge graphs, and contracts. Originally created by **Vladimir Ivanov** ([@turboplanner](https://t.me/turboplanner)).

GRACE provides structured scaffolding that helps LLMs generate, navigate, and maintain code with high reliability. Every module gets a contract before code exists, every code block gets semantic markers for RAG navigation, and a knowledge graph keeps the entire project map current.

This plugin packages Vladimir's methodology as a reusable Claude Code marketplace plugin so any project can adopt GRACE.

## Installation

### Via Claude Code Plugin Marketplace

```bash
# Add the marketplace
/plugin marketplace add osovv/grace-marketplace

# Install the plugin
/plugin install grace@grace-marketplace
```

### Via npx skills (Vercel Skills CLI)

```bash
# Install GRACE skill to Claude Code
npx skills add osovv/grace-marketplace

# Or install globally (available across all projects)
npx skills add osovv/grace-marketplace -g

# Install to a specific agent
npx skills add osovv/grace-marketplace -a claude-code
```

> Browse more skills at [skills.sh](https://skills.sh)

### Via Codex CLI

Inside Codex, use the built-in skill installer to add GRACE skills:

```
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-init
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-plan
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-generate
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-execute
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-add
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-fix
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-refresh
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-status
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-ask
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-explainer
$skill-installer install https://github.com/osovv/grace-marketplace/tree/main/codex-skills/grace-reviewer
```

After installation, restart Codex to activate the skills.

## Quick Start

**Claude Code:**
```bash
# Initialize GRACE structure in your project
/grace:init

# Define requirements, then plan the architecture
/grace:plan

# Generate code for a specific module
/grace:generate <module-name>

# Or execute the entire development plan
/grace:execute
```

**Codex CLI:**
```bash
# Initialize GRACE structure in your project
$grace-init

# Define requirements, then plan the architecture
$grace-plan

# Generate code for a specific module
$grace-generate <module-name>

# Or execute the entire development plan
$grace-execute
```

## Commands

| Command (Claude Code) | Command (Codex) | Description |
|---|---|---|
| `/grace:init` | `$grace-init` | Bootstrap GRACE structure |
| `/grace:plan` | `$grace-plan` | Architectural planning |
| `/grace:add <desc>` | `$grace-add <desc>` | Add a new module with contract |
| `/grace:generate <module>` | `$grace-generate <module>` | Generate code with GRACE markup |
| `/grace:execute` | `$grace-execute` | Execute full plan with validation |
| `/grace:fix <error>` | `$grace-fix <error>` | Debug via semantic navigation |
| `/grace:refresh` | `$grace-refresh` | Sync knowledge graph |
| `/grace:status` | `$grace-status` | Project health report |
| `/grace:ask <question>` | `$grace-ask <question>` | Answer questions with context |

## Skills

- **semantic-markup** — START/END block conventions, ~500 token granularity, unique block names
- **knowledge-graph** — How to maintain `docs/knowledge-graph.xml`
- **contract-driven-dev** — MODULE_CONTRACT, function contracts, governed autonomy (PCAM)
- **unique-tag-convention** — Unique ID-based XML tags that eliminate closing-tag polysemy

## Agents

- **grace-architect** (Opus) — Top-down architectural planning, module decomposition, knowledge graph design
- **grace-reviewer** (Sonnet) — Validates semantic markup integrity, contract completeness, graph consistency

## Origin

GRACE was designed and battle-tested by Vladimir Ivanov ([@turboplanner](https://t.me/turboplanner)). See the [TurboProject](https://t.me/turboproject) Telegram channel for more on the methodology. This plugin extracts GRACE into a standalone, project-agnostic format.

## License

MIT
