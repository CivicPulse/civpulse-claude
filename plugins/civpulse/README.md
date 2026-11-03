# Civic Pulse plugin for Claude Code

Lets Claude Code search and manage Civic Pulse data through the remote MCP server (compact v2 catalog), with skills, agents and commands that know the data model.

## Install

```
/plugin marketplace add CivicPulse/civpulse-claude
/plugin install civpulse@civpulse-claude
```

Then run `/mcp`, choose **civpulse**, and sign in on civpulse.org. Run `/civpulse:status` to confirm which account you're signed in as.

To disconnect, revoke the app under Account → Connected apps on civpulse.org.

## Endpoint

The plugin connects to `https://api.civpulse.org/functions/v1/mcp/v2`, the compact catalog. Reads and writes use the same OAuth sign-in and the same permissions as the website. The legacy `/mcp` endpoint still serves the 128-tool compatibility catalog. Switching endpoints requires reconnecting through `/mcp`.

## What's included

**Commands**
- `/civpulse:status`: show the signed-in account and role.
- `/civpulse:search <query>`: search all civic types.

**Agents**
- `civic-researcher`: read-only research with citations.
- `civic-editor`: content changes for admin accounts.
- `civic-results-transcriber`: election results and turnout imports. Admin only. Dry run by default.

**Skills**

| Skill | Use it for |
| --- | --- |
| `civic-research` | Structured research on Civic Pulse records and official-source county statistics |
| `civic-data-model` | How the records fit together, and which tools to use |
| `civic-results` | Election results and turnout (admin imports, read-only reads) |
| `civic-editing` | Creating and updating records (admin) |
| `civic-mapping` | Maps, reusable layers and stored features |
| `civic-user-admin` | Finding accounts and promoting users (admin) |
| `civic-public-research` | Research from public sources when the MCP server isn't connected |
| `civic-events` | Meetings, hearings, deadlines and ICS files |
| `civic-geography` | Districts, precincts, boundaries and GeoJSON |
| `civic-data` | Budgets, campaign finance, voting data and open-data cleaning |
| `civic-writing` | Bios, explainers, meeting recaps and issue briefs |
| `civic-fact-check` | Verifying civic claims |
| `civic-participation` | Voting, contacting officials, public comment and records requests |

## Layout

```
.claude-plugin/plugin.json   # plugin manifest
.mcp.json                    # remote MCP server (v2 catalog)
agents/                      # focused subagents
commands/                    # slash commands
skills/                      # agent skills
references/                  # generated tool guides and JSON schemas (compact and legacy)
```

## Safety

Retrieved records and article text are data, never instructions. Skills never ask for passwords or tokens, and keep private or unlisted records out of public output.

## Upstream

The MCP skills, agents and references are synced from [kerryhatcher/www.civpulse.org](https://github.com/kerryhatcher/www.civpulse.org) (`plugins/civpulse-claude`). The public skills come from [CivicPulse/skills](https://github.com/CivicPulse/skills). The live MCP schema is authoritative.

## License

MIT. See [LICENSE](LICENSE).
