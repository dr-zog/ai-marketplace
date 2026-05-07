# dr-zog marketplace

A [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) for Dr Zog's public AI plugins.

## Add the marketplace

From inside a Claude Code session:

```
/plugin marketplace add dr-zog/ai-marketplace
```

Or with the non-interactive CLI:

```bash
claude plugin marketplace add dr-zog/ai-marketplace
```

## Plugins

### jfdi-agents

An architect-led agent team for autonomous software development. Product Owner + Architect scope the system, then the Architect mints per-layer developer agents (backend, frontend, middleware, shared) tailored to the chosen stack. The team walks the stack sequentially to build a walking skeleton, then parallelises refinement with each developer owning its own folder.

```
/plugin install jfdi-agents@dr-zog
```

Source: [`dr-zog/jfdi-agents`](https://github.com/dr-zog/jfdi-agents) (subdir `plugins/jfdi-agents`)

### thinking-partner

A deterministic thinking partner that challenges assumptions and applies 150+ mental models to sharpen decisions, solve problems, and think more clearly. Features orientation detection, a cognitive operations framework, and structured diagnostic workflows.

```
/plugin install thinking-partner@dr-zog
```

Source: [`dr-zog/thinking-partner`](https://github.com/dr-zog/thinking-partner)

## Updating

Plugins use the `version` declared in each plugin's own `plugin.json`. Bump the upstream version (or omit `version` and rely on commit SHA) to ship updates. Users refresh with:

```
/plugin marketplace update dr-zog
```

## Adding a new plugin

1. Add a new entry to the `plugins` array in `.claude-plugin/marketplace.json`.
2. Pick the right `source` shape:
   - **Whole-repo plugin** (`.claude-plugin/plugin.json` at repo root): `github` with `repo: "owner/name"`.
   - **Plugin in a subdirectory**: `git-subdir` with `url` + `path`.
3. Commit and push. Users pick up the new plugin on their next `/plugin marketplace update`.

## Validate locally

```bash
claude plugin validate .
```
