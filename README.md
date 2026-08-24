# EVE Map Assistant

Use **EVE Static Map Planner** with AI agents through MCP.

EVE Map Assistant is a collection of lightweight integrations for different AI clients.

All integrations connect to the same local MCP server provided by EVE Static Map Planner:

`eve-map-mcp.exe`

## Choose your AI client

### Codex

**EVE Map Assistant Plugin**

For OpenAI Codex.

- Native Codex Plugin / Skill integration
- Automatically connects to `eve-map-mcp.exe`
- Provides access to the EVE Map MCP tools

Repository:

https://github.com/zx0003147/EVE-Map-Assistant-Plugin

---

### DeepSeek Harness

**EVE Map Assistant DSH Bundle**

For DeepSeek Harness (DSH).

- Uses DSH's bundle/plugin mechanism
- Supports global `dsh` and npx-only environments
- Includes install, verification, migration, rollback, and uninstall tooling

Repository:

https://github.com/zx0003147/EVE-Map-Assistant-DSH

---

## Core application

### EVE Static Map Planner

The desktop application that provides the actual map, routing engine, mission layer, and MCP server.

The Windows installer includes:

- `EVE Static Map Planner.exe`
- `EVE Map MCP Bridge.exe`
- `eve-map-mcp.exe`

Repository and Windows releases:

https://github.com/zx0003147/EVE-Static-Map-Planner

## Architecture

```text
EVE Static Map Planner
        │
        └── eve-map-mcp.exe
               │
        ┌──────┴──────┐
        │             │
      Codex          DSH
      Plugin         Bundle
        │             │
        └──── AI agents ────
```

The adapters do **not** contain separate copies of the map application or MCP server.

They are lightweight client-specific integrations for the same `eve-map-mcp.exe`.

## Current integrations

| AI client | Integration | Status |
|---|---|---|
| Codex | EVE Map Assistant Plugin | Available |
| DeepSeek Harness | EVE Map Assistant DSH Bundle | Available |

More AI-client integrations may be added in the future.

## Getting started

1. Install the latest compatible **EVE Static Map Planner**.
2. Enable **AI Control** in the application.
3. Choose your AI client above.
4. Follow the installation instructions in that integration's repository.
5. Restart your AI client if required.
6. Start using the EVE Map MCP tools.

## MCP

All supported integrations ultimately communicate through the same local MCP entrypoint:

```text
eve-map-mcp.exe
```

This keeps the map logic, security model, routing engine, and MCP tool implementation centralized in EVE Static Map Planner.
