# Agent skills for everyday tasks

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Agent Skills](https://img.shields.io/badge/Agent%20Skills-format-purple)

Skills that give AI agents practical abilities - restaurant reservations, pharmacy stock checks, library tracking. Each skill is a standalone repo you install in one command.

## The skills

### [Ontopo restaurant search](https://github.com/alexpolonsky/agent-skill-ontopo)

Search Israeli restaurants, check availability across date ranges, and get booking links.

> "Find me a table for 2 at Taizu this Friday or Saturday evening"

```bash
npx skills add alexpolonsky/agent-skill-ontopo
```

---

### [Maccabi pharmacy stock check](https://github.com/alexpolonsky/agent-skill-maccabi-pharm-search)

Check prescription medication stock at Maccabi pharmacies before you go. Search all nearby branches in one query.

> "Is Nurofen in stock at any Maccabi pharmacy in Tel Aviv?"

```bash
npx skills add alexpolonsky/agent-skill-maccabi-pharm-search
```

---

### [Libby book monitor](https://github.com/alexpolonsky/agent-skill-libby-book-monitor)

Track when books get added to your Libby/OverDrive library. Watchlists, multi-library profiles, cron-ready notifications.

> "Watch for 'The Travelling Cat Chronicles' by Hiro Arikawa at my library"

```bash
npx skills add alexpolonsky/agent-skill-libby-book-monitor
```

## What are Agent Skills?

[Agent Skills](https://agentskills.io) are folders of instructions, scripts, and resources that agents can discover and use automatically. Think of them as apps for your AI agent - install one, and your agent gains an ability it didn't have before.

Each skill contains a `SKILL.md` manifest that describes what the skill does and how to use it. When your agent loads a skill, it reads this manifest and knows what commands are available.

The format is an [open standard](https://github.com/agentskills/agentskills) supported by Claude Code, Cursor, Codex, VS Code, Gemini CLI, Roo Code, Goose, and [many more](https://agentskills.io).

## Install any skill

```bash
npx skills add alexpolonsky/agent-skill-<name>
```

<details>
<summary>Manual install</summary>

Clone into your agent's skills directory:

```bash
# OpenClaw
git clone https://github.com/alexpolonsky/agent-skill-<name> ~/.openclaw/skills/<name>

# Claude
git clone https://github.com/alexpolonsky/agent-skill-<name> ~/.claude/skills/<name>

# Cursor
git clone https://github.com/alexpolonsky/agent-skill-<name> ~/.cursor/skills/<name>
```

</details>

## Author

[Alex Polonsky](https://alexpolonsky.com) - [GitHub](https://github.com/alexpolonsky) - [LinkedIn](https://www.linkedin.com/in/alexpolonsky/) - [Twitter/X](https://x.com/alexpo)

## License

MIT - see individual skill repos for details. These are unofficial, independent tools provided as-is. Verify information from original sources before acting on data from these skills.
