# Ontopo Restaurant Search

> **[Agent Skills](https://agentskills.io) format** · Works with OpenClaw and other compatible clients

Search Israeli restaurants, check table availability, view menus, and get booking links via Ontopo.

> **Disclaimer**: This is an unofficial tool, not affiliated with or endorsed by Ontopo. Availability data queries APIs that power the website and may not reflect actual availability. This tool does NOT place reservations - it generates booking links for manual confirmation on Ontopo's website. Provided "as is" without warranty of any kind.

## Why this exists

Ontopo's website makes you browse availability day by day, manually clicking through calendars. This tool lets you search across date ranges in natural language, then provides direct booking links:

- Query "any Wednesday at 19:00 in the next month"
- Check multiple restaurants for the same time slot
- Search patterns like "every Friday evening" or "weekdays only"
- Get direct booking links (complete reservation on Ontopo's website)

## Installation

### Via skills.sh

```bash
npx skills add alexpolonsky/agent-skills --skill ontopo
```

### Agent skills client
```bash
# Clone to your skills directory
git clone https://github.com/alexpolonsky/agent-skills ~/skills/ontopo

# Or to workspace
git clone https://github.com/alexpolonsky/agent-skills ./skills/ontopo
cd ontopo
```

### Standalone CLI
```bash
# Install dependency
pip install httpx

# Run directly
python3 scripts/ontopo-cli.py <command>
```

## Requirements

- Python 3.9+
- httpx library (`pip install httpx`)

## Quick start

```bash
# Search for a restaurant
python3 scripts/ontopo-cli.py search "taizu"

# Find available restaurants for tonight
python3 scripts/ontopo-cli.py available tomorrow 19:00 --city tel-aviv

# Check specific venue availability
python3 scripts/ontopo-cli.py check taizu tomorrow 19:00

# Get booking link
python3 scripts/ontopo-cli.py url taizu
```

## Commands

| Command | Description |
|---------|-------------|
| `cities` | List supported Israeli cities |
| `categories` | List venue categories |
| `search <query>` | Search venues by name |
| `available <date> <time>` | Find venues with availability |
| `check <venue> <date> [time]` | Check specific venue availability |
| `range <venue> <start> <end>` | Check availability over date range |
| `menu <venue>` | View venue menu |
| `info <venue>` | Get venue details |
| `url <venue>` | Get booking URL |

## Options

| Option | Commands | Description |
|--------|----------|-------------|
| `--json` | all | Output in JSON format |
| `--locale en\|he` | search, info, url | Language (English or Hebrew) |
| `--city` | available, search | City filter |
| `--party-size` | available, check, range | Number of guests (default: 2) |

## Date/time formats

- **Dates**: `YYYY-MM-DD`, `today`, `tomorrow`, `+N` (days from now)
- **Times**: `HH:MM`, `HHMM`, `7pm`, `19:30`

## Supported cities

tel-aviv, jerusalem, haifa, herzliya, raanana, ramat-gan, netanya, ashdod, ashkelon, beer-sheva, eilat, modiin, rehovot, rishon-lezion, petah-tikva, holon, kfar-saba, hod-hasharon, caesarea

## Example workflow

```bash
# 1. Search for restaurant
python3 scripts/ontopo-cli.py search "taizu"

# 2. Check availability
python3 scripts/ontopo-cli.py check taizu tomorrow 19:00

# 3. View menu
python3 scripts/ontopo-cli.py menu taizu

# 4. Get booking link
python3 scripts/ontopo-cli.py url taizu
```

## Output example

```bash
$ python3 scripts/ontopo-cli.py search "taizu"
taizu-tel-aviv-jaffa
  Taizu · Asian Fusion
  Tel Aviv · $$$$

$ python3 scripts/ontopo-cli.py check taizu tomorrow 19:00
Checking taizu-tel-aviv-jaffa for 2025-02-01...
19:00 - Available
19:15 - Available
19:30 - Available
20:00 - Not available
```

## Testing

```bash
cd tests/
./test_commands.sh        # Integration tests
./test_edge_cases.sh      # Error handling tests
./test_skill_selection.sh # Trigger word tests
```

## How it works

Queries the same endpoints that power Ontopo's website.

## Limitations

- Does NOT place reservations automatically
- Booking links redirect to Ontopo's website for confirmation
- Availability data may be delayed or inaccurate
- Requires internet connection

## License

MIT

## Author

Vibe coded by [Alex Polonsky](https://alexpolonsky.com) · [LinkedIn](https://www.linkedin.com/in/alexpolonsky/) · [GitHub](https://github.com/alexpolonsky) · [Twitter/X](https://x.com/alexpo)

## References

- [Agent Skills Specification](https://agentskills.io/specification)
- [OpenClaw Skills Documentation](https://docs.openclaw.ai/tools/skills)
