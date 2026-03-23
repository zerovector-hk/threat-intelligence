# MerkleClaw Threat Intelligence Feeds

> **Maintained by [MerkleClaw](https://merkleclaw.com) / [ZeroVector](https://zerovector.hk)**
> Public blockchain threat intelligence — free for researchers, investigators, and compliance teams.

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Data Updated](https://img.shields.io/badge/Updated-Weekly-green.svg)](https://github.com/zerovector-hk/threat-intelligence/commits/main)
[![Addresses](https://img.shields.io/badge/Addresses-3289%2B-blue.svg)](./sanctions/)

---

## What's in this repository

| Directory | Contents | Records | Updated |
|-----------|----------|---------|---------|
| [`/sanctions`](./sanctions/) | OFAC-sanctioned crypto addresses | 3,000+ | Weekly |
| [`/dprk`](./dprk/) | DPRK / Lazarus Group attributed addresses & patterns | 50+ | Monthly |
| [`/scam-infrastructure`](./scam-infrastructure/) | Known scam aggregation addresses | 200+ | Weekly |
| [`/attack-patterns`](./attack-patterns/) | Documented on-chain attack patterns | 30 | Monthly |
| [`/threat-actors`](./threat-actors/) | Threat actor profiles (structured) | 6 | Monthly |

---

## Quick Start

### Check an address against the full blacklist

```python
import json

with open('sanctions/ofac-crypto-addresses.json') as f:
    ofac = json.load(f)

address = "0x098b716b8aaf21512996dc57eb0615e2383e2f96"
matches = [e for e in ofac['entries'] if e['address'].lower() == address.lower()]
print(matches)  # Returns Lazarus Group entry
```

### Load all blacklisted addresses (CSV)

```python
import pandas as pd
df = pd.read_csv('sanctions/blacklist_combined.csv')
print(f"Total blacklisted addresses: {len(df)}")
```

---

## Data Schema

### Address Entry Format

```json
{
  "address": "0x098b716b8aaf21512996dc57eb0615e2383e2f96",
  "chain": "ethereum",
  "label": "Lazarus Group — Ronin Bridge Attacker",
  "category": "sanctions",
  "source": "OFAC SDN List",
  "confidence": "confirmed",
  "sanctioned_date": "2022-04-14",
  "last_updated": "2026-03-22",
  "references": [
    "https://home.treasury.gov/news/press-releases/jy0768"
  ]
}
```

### Confidence Levels

| Level | Meaning |
|-------|---------|
| `confirmed` | Multi-source cross-verified or official OFAC/government attribution |
| `high` | Single authoritative source (SlowMist, PeckShield, CISA) |
| `medium` | Research-based attribution, circumstantial evidence |
| `low` | Preliminary intelligence, unverified — use with caution |

---

## Data Sources

- **OFAC SDN List** — US Treasury Office of Foreign Assets Control
- **SlowMist Hacked** — slowmist.io/en/hacked.html
- **PeckShield Alert** — @PeckShieldAlert
- **Rekt.news** — rekt.news
- **CertiK Skynet** — certik.com
- **Beosin Security** — beosin.com
- **DeFiHackLabs** — github.com/SunWeb3Sec/DeFiHackLabs
- **ZeroVector Original Research** — zerovector.hk

---

## Coverage Statistics

| Chain | Addresses | Notes |
|-------|-----------|-------|
| Ethereum (ETH) | 2,100+ | Including ERC-20 |
| Bitcoin (BTC) | 800+ | |
| Tron (TRX) | 300+ | TRC-20 scam corridors |
| BNB Chain | 150+ | |
| Others | 50+ | SOL, MATIC, etc. |

---

## Updates

- **Sanctions (OFAC)**: Synced weekly from official OFAC SDN XML
- **DPRK addresses**: Updated within 48 hours of new OFAC designations
- **Scam infrastructure**: Community contributions + ZeroVector case analysis
- **Attack patterns**: Updated monthly with new documented incidents

---

## Using This Data

This data is released under **CC BY 4.0**. You are free to:
- Use it in your research, tools, or products
- Share and redistribute with attribution
- Adapt and build upon it

**Attribution:** Please credit `MerkleClaw / ZeroVector (zerovector.hk)` when using this data.

### Integration Examples

**Compliance screening (Python):**
```python
# pip install merkleclaw-intel (coming soon)
# Or use directly:
import requests
data = requests.get(
  'https://raw.githubusercontent.com/zerovector-hk/threat-intelligence/main/sanctions/blacklist_combined.csv'
).text
```

**SIEM/SOC integration:** CSV format compatible with most SIEM platforms for alert rule creation.

---

## Contributing

Found an address that should be here? Have a correction?

1. **Open an issue** with the address, evidence/source, and suggested label
2. **Submit a PR** following the [contribution guidelines](./contributing/CONTRIBUTING.md)

We review contributions weekly. All submissions require a verifiable public source.

**We do NOT accept:**
- Unverified personal accusations
- Addresses without public evidence
- Any content that could identify individuals without legal process

---

## Related Projects

- **[MerkleClaw](https://merkleclaw.com)** — Desktop on-chain intelligence platform using this data (apply for beta access)
- **[ThreatLedger](https://zerovector.hk)** — Coming soon: community threat intelligence platform
- **[Sealr](https://sealr.io)** — Web3 asset monitoring terminal

---

## Disclaimer

This data is compiled from public sources for research and compliance purposes. It does not constitute legal advice. OFAC data is sourced from the US Treasury's official SDN list. Users are responsible for compliance with applicable laws and regulations in their jurisdiction.

ZeroVector makes no warranties regarding the completeness or accuracy of this data. For legal proceedings, always verify against primary sources and consult qualified legal counsel.

---

*⭐ Star this repo to stay updated | 🦞 [merkleclaw.com/beta](https://merkleclaw.com/beta)*
