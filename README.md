# SpeedyDrone MCP server

[![SpeedyDrone MCP connector](https://glama.ai/mcp/connectors/ca.speedydrone.agr/site/badges/score.svg)](https://glama.ai/mcp/connectors/ca.speedydrone.agr/site)

**Answers Canadian growers, custom applicators and research buyers on spray drones, drone spraying rules, spreading, Mavic 3M mapping, job costs and buy-vs-hire.**

A free, public [MCP](https://modelcontextprotocol.io) server from [SpeedyDrone](https://agr.speedydrone.ca?utm_source=github&utm_medium=readme&utm_campaign=mcp): **SpeedyDrone Canadian Agricultural Drone Library**. Connect it to ChatGPT, Claude or another AI assistant and it answers from SpeedyDrone's published guides and articles, and runs the same calculators as the website, so the numbers match, citing the page each answer comes from.

```
https://agr.speedydrone.ca/mcp
```

No sign-in, no API key, nothing to install. Listed in the [official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=ca.speedydrone.agr%2Fsite) as `ca.speedydrone.agr/site`.

## What you can ask

- "What would it cost to hire a drone to spray 300 acres of soybeans in southern Ontario if the operator has to travel 60 km?"
- "I'm spraying 150 acres at 2 US gal/acre with a T50. What's the spray mix and how many tank loads will that take?"
- "How many acres a season do I need to spray before buying a used Agras T50 for C$22,999 beats hiring at C$20/acre?"
- "Should I get the Agras T50 or the T100 for about 2,000 acres a year, and how many batteries does each one need?"
- "Do I need a pesticide applicator licence or an SFOC from Transport Canada to spray crops by drone in Canada?"
- "Our research lab has to receive a Mavic 3M by March 31. What's the last day we can send the purchase order, and when should we request the quote?"

## Tools

| Tool | What it does |
|---|---|
| `about_site` | Start here: what agricultural drone spraying, spreading and crop mapping in Canada database covers (Choosing a spray drone: Agras T50 vs T100, Drone spraying regulations, licences and SFOCs in Canada, Cover-crop, pasture and granular fertilizer spreading, Multispectral crop scouting and mapping with Mavic 3M, Drone spraying job costs and buy-vs-hire break-even, Research and government drone purchasing, Starting a drone spraying business and pilot training, Orchard, vineyard, potato and greenhouse applications), who it is for (Canadian growers, custom applicators, and research and government buyers choosing or running agricultural drones), and its free calculators. |
| `search_site` | Search agricultural drone spraying, spreading and crop mapping in Canada library: Choosing a spray drone: Agras T50 vs T100, Drone spraying regulations, licences and SFOCs in Canada, Cover-crop, pasture and granular fertilizer spreading, Multispectral crop scouting and mapping with Mavic 3M, Drone spraying job costs and buy-vs-hire break-even, Research and government drone purchasing, Starting a drone spraying business and pilot training, Orchard, vineyard, potato and greenhouse applications. |
| `read_page` | The full text of one SpeedyDrone page: an article, guide, FAQ page or calculator page. |
| `drone_spraying_cost` | What a custom drone spraying or seeding job costs (southern Ontario hire rates, C$, before tax: spraying C$18–22/acre, seeding C$15–18/acre, C$500 minimum, C$1.5/km travel), plus the spray mix and tank loads for a T50 or T100. |
| `buy_or_hire_spray_drone` | Owning a spray drone vs hiring custom spraying per acre (Canada, C$, before tax). |
| `fiscal_year_order_planner` | For a research or public buyer who must receive goods by a date (often March 31): the last day to send the purchase order and the last day to request the quote and start approvals. |
| `ask_expert` | A question still open? With your OK, your name and email, the assistant sends it to SpeedyDrone's specialists, and a person replies by email. |

Every tool only reads SpeedyDrone's published pages, except `ask_expert`, which sends only what you approve.

## Connect it

**Claude** (claude.ai and desktop, every plan; Free allows one custom connector): Customize > Connectors > **+ Add** > **Add custom connector**. Name it, paste `https://agr.speedydrone.ca/mcp`, choose **No sign in**, then **Add**. In a chat: **+** > Connectors, switch it on. ([Claude help](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp))

**ChatGPT** (Pro, Business, Enterprise, Edu; web): **Plugins** > **+** > **Add custom MCP server**. Name it, paste the URL under Connection, accept the notice, **Create as a plugin**. In a new chat type **@** and pick it. ([OpenAI help](https://help.openai.com/en/articles/12584461))

**Claude Code**:
```bash
claude mcp add --transport http speedydrone https://agr.speedydrone.ca/mcp
```
Or clone this repo: its `.mcp.json` connects it for the project.

**Cursor** (`~/.cursor/mcp.json`):
```json
{ "mcpServers": { "speedydrone": { "url": "https://agr.speedydrone.ca/mcp" } } }
```

**VS Code (GitHub Copilot)**: Command Palette > **MCP: Add Server** > HTTP > paste the URL.

**Gemini CLI**:
```bash
gemini mcp add --transport http speedydrone https://agr.speedydrone.ca/mcp
```

## Try it without an AI

```bash
curl -s https://agr.speedydrone.ca/mcp -H 'content-type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/call","params":{"name":"search_site","arguments":{"query":"Agras T50 vs T100"}}}'
```

## More from SpeedyDrone

- Website: [agr.speedydrone.ca](https://agr.speedydrone.ca?utm_source=github&utm_medium=readme&utm_campaign=mcp)
- Questions: [agr.speedydrone.ca/contact](https://agr.speedydrone.ca/contact?utm_source=github&utm_medium=readme&utm_campaign=mcp)

Answers are general information from SpeedyDrone's published pages.

## License

This repository (README and config) is MIT licensed. The server is operated by SpeedyDrone.
