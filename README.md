# Plugin VemCon

Catálogo de plugins da VemCon para Claude, ChatGPT e Codex. O plugin fica em
[`plugins/vemcon`](plugins/vemcon); o README dele explica o que faz, quais dados
usa e como instalar.

| Arquivo | Quem lê |
|---|---|
| `.claude-plugin/marketplace.json` | Claude Code |
| `.agents/plugins/marketplace.json` | Codex / ChatGPT |
| `plugins/vemcon/.claude-plugin/plugin.json`, `.mcp.json` | Claude |
| `plugins/vemcon/plugin.json`, `mcp.json` | ChatGPT e Codex |
| `plugins/vemcon/skills/` | os dois |

As tools vêm do servidor MCP da VemCon (`supabase/functions/mcp` no repositório
`vemcon`). Ao renomear uma tool lá, atualize a skill aqui, suba `version` nos
dois `plugin.json` e gere o zip de novo:

```bash
(cd plugins && rm -f vemcon.zip && zip -r vemcon.zip vemcon)
```

Licença MIT.
