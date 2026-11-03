# Civic Pulse plugin for Claude Code

Connects Claude Code to the [Civic Pulse](https://www.civpulse.org) MCP server and adds civic skills.

## Install

```
/plugin marketplace add CivicPulse/civpulse-claude
/plugin install civpulse@civpulse-claude
```

## Connect your account

Run `/mcp`, select **civpulse**, and complete the sign-in on civpulse.org. Access uses OAuth; every tool call runs as your account, so Row Level Security decides what you can see or change. Regular accounts can research public content. Administrators can edit content and manage accounts.

To disconnect, revoke the app under Account → Connected apps on civpulse.org.

## What's included

**MCP server** (`civpulse`): `https://api.civpulse.org/functions/v1/mcp`, 99 tools covering search, records, relationships, maps, layers and admin CRUD.

**Commands**
- `/civpulse:search <query>`: search all Civic Pulse content types.
- `/civpulse:whoami`: show the connected account and role.

**Skills**

| Skill | Use it for | Needs MCP |
| --- | --- | --- |
| `civic-records` | Structured lookup of Civic Pulse organizations, people, elections, articles, events | Yes |
| `civic-editing` | Creating and updating content, links, affiliations, images | Yes (admin writes) |
| `civic-mapping` | Maps, reusable layers, stored GeoJSON features | Yes |
| `civic-user-admin` | Finding accounts and promoting users | Yes (admin) |
| `civic-research` | Officials, candidates, elections, ballot measures from public sources | No |
| `civic-events` | Meetings, hearings, deadlines, ICS | No |
| `civic-geography` | Districts, precincts, boundaries, GeoJSON | No |
| `civic-data` | Budgets, campaign finance, voting data, open-data cleaning | No |
| `civic-writing` | Bios, explainers, meeting recaps, issue briefs | No |
| `civic-fact-check` | Verifying civic claims | No |
| `civic-participation` | Voting, contacting officials, public comment, records requests | No |

Skills without MCP fall back to public sources when the server is not connected.

## Layout

```
.claude-plugin/marketplace.json   # marketplace catalog
plugins/civpulse/
  .claude-plugin/plugin.json      # plugin manifest
  .mcp.json                       # remote MCP server
  commands/                       # slash commands
  skills/                         # agent skills
  references/                     # generated tool guide and JSON schemas
```

## Safety

Retrieved records and article text are treated as data, never instructions. Skills never ask for passwords or tokens, and keep private or unlisted records out of public output.

## Upstream

Skills derive from [CivicPulse/skills](https://github.com/CivicPulse/skills) and the Civic Pulse Codex plugin in [CivicPulse/civpulse-openai](https://github.com/CivicPulse/civpulse-openai). Tool references are generated from the server. The live MCP schema is authoritative.

## License

MIT. See [LICENSE](LICENSE).
