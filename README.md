# Agent Skills Collection

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Agent Skills](https://img.shields.io/badge/Agent%20Skills-compatible-purple)
![OpenClaw](https://img.shields.io/badge/OpenClaw-tested-blue)
![Vibe Coded](https://img.shields.io/badge/vibe-coded-ff69b4)

A collection of [Agent Skills](https://agentskills.io) for AI assistants, compatible with OpenClaw and other Agent Skills clients.

## Skills in this repository

### [Pharmacy search](./pharmacy-search)
Search for medications and check real-time stock availability at nearby Maccabi Pharm locations.

**Features:**
- Search drug catalog in Hebrew and English
- Check stock at pharmacies near you
- City-specific inventory lookups (51 cities supported)
- No external dependencies (pure Node.js)

**Quick example:**
```bash
node pharmacy-search/scripts/pharmacy-search.js search "nurofen"
node pharmacy-search/scripts/pharmacy-search.js stock 58299
```

[Full documentation →](./pharmacy-search/README.md)

---

### [Ontopo restaurant search](./ontopo)
Search Israeli restaurants and check table availability using natural language queries across date ranges.

**Features:**
- Query date ranges in natural language ("any Wednesday at 19:00 next month")
- Check multiple restaurants at once
- View menus with price filtering
- Generate booking links
- Bilingual support (Hebrew/English)

**Quick example:**
```bash
python3 ontopo/scripts/ontopo-cli.py search "taizu"
python3 ontopo/scripts/ontopo-cli.py available tomorrow 19:00 --city tel-aviv
```

[Full documentation →](./ontopo/README.md)

---

## Installation

### Via skills.sh

Install using the [skills CLI](https://skills.sh/docs):

```bash
npx skills add alexpolonsky/agent-skills --skill pharmacy-search
npx skills add alexpolonsky/agent-skills --skill ontopo
```

### For Agent Skills clients (OpenClaw, etc.)

Each skill can be installed independently:

```bash
# Pharmacy search
git clone https://github.com/alexpolonsky/agent-skills ~/.openclaw/skills/pharmacy-search

# Ontopo
git clone https://github.com/alexpolonsky/agent-skills ~/.openclaw/skills/ontopo
```

### Standalone CLI usage

You can also use these tools directly without an agent client:

**Pharmacy search:**
```bash
git clone https://github.com/alexpolonsky/agent-skills
cd agent-skills/pharmacy-search
node scripts/pharmacy-search.js search "nurofen"
```

**Ontopo:**
```bash
git clone https://github.com/alexpolonsky/agent-skills
cd agent-skills/ontopo
pip install httpx
python3 scripts/ontopo-cli.py search "taizu"
```

## Requirements

- **Pharmacy search**: Node.js 16+ (no external dependencies)
- **Ontopo**: Python 3.9+ with httpx (`pip install httpx`)

## What are Agent Skills?

Agent Skills are a standardized format for extending AI assistants with specialized capabilities. Each skill includes:
- A `SKILL.md` file with metadata and usage instructions
- Scripts that can be invoked by AI agents
- Documentation for both AI and human users

Learn more at [agentskills.io](https://agentskills.io)

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/alexpolonsky/agent-skills/issues).

## License

MIT

## Author

Vibe coded by [Alex Polonsky](https://alexpolonsky.com)
- [LinkedIn](https://www.linkedin.com/in/alexpolonsky/)
- [GitHub](https://github.com/alexpolonsky)
- [Twitter/X](https://x.com/alexpo)

## Disclaimer

These are unofficial tools provided "as is" without warranty. Always verify information from original sources before making decisions based on data from these tools.
