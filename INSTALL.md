# Instalação rápida

Buscador: Google é um servidor MCP remoto hospedado em `https://api.mcp.ai/p_buscador_google`. Você não baixa nem roda nada localmente — só aponta seu cliente pra essa URL.

A auth acontece em runtime: clientes com **OAuth 2.1** (Claude Desktop, Cursor, VS Code recentes) abrem o browser na 1ª chamada (magic-link). Clientes sem OAuth recebem a tool `authenticate` — abra `https://app.mcp.ai/agent-auth`, faça login, copie o JWT e cole no chat.

---

## Claude (Web e Desktop)

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → `Buscador: Google` / `https://api.mcp.ai/p_buscador_google`.

Config file (legado): `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) ou `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{ "mcpServers": { "buscador_google": { "type": "http", "url": "https://api.mcp.ai/p_buscador_google" } } }
```

## Cursor

[➕ Instalar no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=buscador_google&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9idXNjYWRvcl9nb29nbGUifQ==)

`.cursor/mcp.json`:
```json
{ "mcpServers": { "buscador_google": { "url": "https://api.mcp.ai/p_buscador_google" } } }
```

## VS Code (Copilot Chat)

[➕ Instalar no VS Code](vscode:mcp/install?name=buscador_google&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_buscador_google%22%7D)

`.vscode/mcp.json`:
```json
{ "servers": { "buscador_google": { "type": "http", "url": "https://api.mcp.ai/p_buscador_google" } } }
```

## Outros clientes MCP

Qualquer cliente com **MCP over HTTP**. URL fixa:

```
https://api.mcp.ai/p_buscador_google
```

Dúvidas? [buscador_google@mcp.ai](mailto:buscador_google@mcp.ai)
