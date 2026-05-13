## openwork-hub

Shared automation hub for office workers using OpenWork/OpenCode.

### Contents

| Directory | Description |
|-----------|-------------|
| `skills/` | Reusable skills (workflows + scripts) |
| `agents/` | Agent definitions |
| `commands/` | Custom commands |
| `plugins/` | Plugin documentation and local plugin files |

### Vendoring into a project

To use these assets in a project that uses `.opencode/`:

```bash
mkdir -p .opencode
cp -R skills   .opencode/skills
cp -R agents   .opencode/agents
cp -R commands .opencode/commands
cp -R plugins  .opencode/plugins

# Merge plugin/MCP config
cp opencode.json .opencode/opencode.json
```

### Plugin/MCP setup

The `opencode.json` file contains recommended plugins and MCP servers:

- **Plugins**: context management, extended agents, notifications, LLM tracing
- **MCP**: Playwright (headless browser automation)

When vendoring, copy `opencode.json` to `.opencode/opencode.json`. Plugins are auto-installed by Bun at startup — no `node_modules` or `package.json` needed.

### Environment variables

Copy `.env.example` to `.env` and fill in values if using Langfuse tracing:

```bash
cp .env.example .env
```

### Installing skills via OpenWork UI

OpenWork can also browse and install individual skills from this hub through the UI
without full vendoring. Only the `skills/` directory is used by the skill hub API.
