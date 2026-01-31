# Maccabi Pharmacy Stock Check

> **[Agent Skills](https://agentskills.io) format** · Works with OpenClaw and other compatible clients

Search for medications and check real-time stock availability at Maccabi Pharm locations in Israel.

> **Disclaimer**: This is an unofficial tool, not affiliated with or endorsed by Maccabi Healthcare Services. Stock information queries APIs that power the website and may not reflect actual availability. Always call the pharmacy to confirm stock before visiting. This tool is provided "as is" without warranty of any kind. Use at your own risk.

## Why this exists

Check medication stock at nearby pharmacies in one search instead of searching and browsing on Maccabi's website. Designed to work as part of agentic workflows.

## Installation

### Via skills.sh

```bash
npx skills add alexpolonsky/agent-skills --skill pharmacy-search
```

### Agent skills client
```bash
# Clone to your skills directory
git clone https://github.com/alexpolonsky/agent-skills ~/skills/pharmacy-search

# Or to workspace
git clone https://github.com/alexpolonsky/agent-skills ./skills/pharmacy-search
cd pharmacy-search
```

### Standalone CLI
No installation required - just run with Node.js:
```bash
node scripts/pharmacy-search.js <command>
```

## Requirements

- Node.js 16.0.0 or higher
- No external dependencies (uses only built-in Node.js modules)

## Quick start

```bash
# Search for medication
node scripts/pharmacy-search.js search "nurofen"

# Check stock (use Largo code from search)
node scripts/pharmacy-search.js stock 58299

# List all city codes
node scripts/pharmacy-search.js cities

# Run tests
node scripts/pharmacy-search.js test
```

## Commands

| Command | Description |
|---------|-------------|
| `search <query>` | Search drug catalog, get Largo codes |
| `stock <largo_code> [city]` | Check real-time stock at pharmacies |
| `branches maccabi [city]` | List Maccabi Pharm locations |
| `cities` | List all 51 available city codes |
| `test` | Run functionality test |

## City codes

Common examples (51 cities supported):
- Tel Aviv: 5000 (default)
- Jerusalem: 3000
- Haifa: 4000
- Beer Sheva: 9000
- Bat Yam: 6200
- Netanya: 7400

Run `cities` command to see all 51 available city codes.

## Example

```bash
# Find Nurofen
$ node scripts/pharmacy-search.js search "nurofen"
NUROFEN LIQUID 20 CAP
  Largo Code: 58299
  Prescription: No

# Check stock in Tel Aviv
$ node scripts/pharmacy-search.js stock 58299
=== Pharmacies with Stock ===
מכבי פארם-ת"א-בלפור 10
   בלפור 10, תל אביב - יפו
   03-9193013
```

## Programmatic use

```javascript
import { MaccabiAdapter } from './scripts/pharmacy-search.js';

const maccabi = new MaccabiAdapter();
const results = await maccabi.searchDrug('nurofen');
const stock = await maccabi.checkStock('58299', '5000');
```

## How it works

Queries the same endpoints that power Maccabi Pharm's website.

## Limitations

- Only supports Maccabi Pharm locations (not other pharmacy chains)
- Stock data may be delayed or inaccurate
- Requires internet connection
- City codes are region-specific (not street-level)

## License

MIT

---

**Important**: This tool queries publicly available APIs. The maintainers are not responsible for any decisions made based on this data. Stock availability should always be confirmed directly with the pharmacy.

## Author

Vibe coded by [Alex Polonsky](https://alexpolonsky.com) · [LinkedIn](https://www.linkedin.com/in/alexpolonsky/) · [GitHub](https://github.com/alexpolonsky) · [Twitter/X](https://x.com/alexpo)

## References

- [Agent Skills Specification](https://agentskills.io/specification)
- [OpenClaw Skills Documentation](https://docs.openclaw.ai/tools/skills)
