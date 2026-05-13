This directory is for local plugin files (.js/.ts) used in vendoring.

## How it works

OpenCode loads plugins from two sources:

1. **npm packages** — declared in `opencode.json` under `plugin`. Auto-installed by Bun.
2. **Local files** — `.js`/`.ts` files placed in `.opencode/plugins/`.

This `plugins/` directory is for the second type. When vendoring this hub into a project,
copy the contents to `.opencode/plugins/`:

```bash
cp -R plugins/* .opencode/plugins/
```

## Current plugins (npm-based)

The following plugins are configured in `opencode.json` and auto-installed:

| Plugin | Purpose |
|--------|---------|
| `@tarquinen/opencode-dcp@latest` | Context management (compress/expand) |
| `oh-my-openagent@latest` | Extended agent capabilities |
| `@mohak34/opencode-notifier@latest` | Desktop notifications |
| `opencode-plugin-langfuse` | LLM tracing & observability |

When vendoring, also copy or merge `opencode.json` into `.opencode/opencode.json`.
