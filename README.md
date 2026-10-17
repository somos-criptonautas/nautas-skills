# nautas-skills

**ENGLISH** | [ESPAÑOL](README.es.md)

Skills and a connection to [comunidad.criptonautas.co](https://comunidad.criptonautas.co) for writing, editing and publishing from an AI agent in the community's voice. The skills themselves are in Spanish, like the forum.

> [!NOTE]
> The agent works with **your own forum account**. It can do what your user can, no more and no less: Discourse decides by trust level and groups. It never publishes without first showing the draft and waiting for a yes.

## What's included

| Skill | For |
|---|---|
| `voz-del-foro` | The community's tone and format. Before writing, it reads your latest replies to pick up your personal style, plus the shared rules from the Voz del foro topic, the same ones the forum's bots follow. |
| `glosario` | Create or edit glossary terms without duplicates, with the basic conventions applied for consistency. |
| `wikis` | Co-authored wikis using the forum's templates (Concepts, Guide, Resources, Experience). |
| `curso` | Propose or apply edits to the course, keeping numbering, TL;DR and navigation. |

The connection uses our Discourse's official MCP server (`https://comunidad.criptonautas.co/mcp`). Each person signs in with their own account through OAuth, from a link: this repo holds no keys or access, everything is managed on the forum.

## Before you start

- An active forum account.
- One of these agents: Claude Code, Claude Desktop, opencode or pi.

The first time the agent uses the forum, it opens a link to authorize your account. Access is revoked on the forum: Preferences → Security → Apps.

## Install

### Claude Code

Inside Claude Code:

```text
/plugin marketplace add somos-criptonautas/nautas-skills
/plugin install comunidad@criptonautas
```

Restart Claude Code, type `/mcp`, choose `comunidad` and authorize in the link. Skills and connection are ready.

### Claude Desktop

1. **Connection:** Settings → Connectors → Add custom connector → URL `https://comunidad.criptonautas.co/mcp` → Connect and authorize.
2. **Skills:** download this repo, zip each folder in `plugins/comunidad/skills/` and upload it in Settings → Capabilities → Skills.

### opencode

```bash
git clone https://github.com/somos-criptonautas/nautas-skills ~/nautas-skills
```

```bash
mkdir -p ~/.config/opencode/skills && ln -s ~/nautas-skills/plugins/comunidad/skills/* ~/.config/opencode/skills/
```

Add the connection to `~/.config/opencode/opencode.json`:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "comunidad": {
      "type": "remote",
      "url": "https://comunidad.criptonautas.co/mcp",
      "oauth": {}
    }
  }
}
```

Authorize:

```bash
opencode mcp auth comunidad
```

### pi

pi has no built-in MCP; add it with [`pi-mcp-adapter`](https://github.com/nicobailon/pi-mcp-adapter), which also loads this repo's skills.

```bash
pi install npm:pi-mcp-adapter
```

```bash
git clone https://github.com/somos-criptonautas/nautas-skills ~/nautas-skills
```

Add to `~/.config/mcp/mcp.json`, with the full path (replace `USER`). If the file exists, add only `claudePlugins`:

```json
{
  "claudePlugins": [
    { "path": "/home/USER/nautas-skills/plugins/comunidad", "mcp": true, "skills": true }
  ],
  "mcpServers": {}
}
```

Restart pi and authorize with `/mcp-auth comunidad`.

## Usage

Ask in plain language, in Spanish. For example:

- *"Sumá al glosario el término slippage."* (add slippage to the glossary)
- *"Revisá la wiki de redes de transferencia y proponé qué actualizar."* (review a wiki and propose updates)
- *"Pasá este borrador a la voz del foro."* (rewrite this draft in the forum's voice)

The flow is always the same:

1. **Reads your voice and the shared rules:** your latest replies and the Voz del foro topic.
2. **Searches the community** for anything that already covers it.
3. **Shows the draft** (or the diff, for an edit), with category and tags.
4. **Waits for an explicit yes.**
5. **Publishes** and returns the link to check.

We ALWAYS check what gets published: the tool is there to speed us up, not to replace us. We are a community of humans who use tools, and using AI does not change that.

If your user cannot edit something (the course, for example), the agent offers to leave the proposal as a reply in the same topic for the team to apply.

## Updating

- **Claude Code:** `/plugin marketplace update criptonautas`
- **opencode:** `git -C ~/nautas-skills pull`
- **Claude Desktop:** upload again the `.zip` of the skills that changed
- **pi:** `git -C ~/nautas-skills pull`

## Proposing changes

The skills are text in `plugins/comunidad/skills/*/SKILL.md`. To improve them: fork, change and pull request, or a topic on the forum with the proposal. Rule of thumb: less is more, and every new rule comes with a real example from the forum.

## Credits

Thanks to [KONVO](https://github.com/kirupa/KONVO), by Kirupa Chinnathambi. We adapted these ideas in our own words, without copying its text:

- **`voz-del-foro`:** review without rewriting (a report by severity, with the exact quote and what to keep), list observations before rewriting, the boring-version and transplant tests, and the idea of a list of filler phrases (the Spanish list is ours).
- **`wikis`:** ask before drafting a new wiki (who it is for, what they should be able to do, own experience, length).

## License

[CC BY-SA 4.0](LICENSE): free to copy, adapt and share, for any purpose, crediting Criptonautas and **under the same license**. Whoever modifies it has to release their changes the same way: what is free is shared and nobody can close it.
