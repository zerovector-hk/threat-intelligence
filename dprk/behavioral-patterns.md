# DPRK / Lazarus Group On-Chain Behavioral Patterns

> **Last Updated:** 2026-03-22
> **Source:** ZeroVector Research + Public CISA/FBI Advisories
> **Use:** These patterns can be used to build detection rules in blockchain monitoring systems.

---

## Pre-Attack Reconnaissance

**Pattern: Small value test transactions**
- Amount: $0.01–$1.00 equivalent
- Timing: 3–30 days before main attack
- Purpose: Verify address control, test gas parameters
- Detection: Flag addresses with multiple micro-transactions followed by large outflows

---

## Post-Attack Fund Movement (within first 6 hours)

**Pattern: Rapid automated dispersion**
- Split to 20–200 intermediate wallets
- Irregular amounts (avoids round-number detection)
- All transactions within same block range or consecutive blocks
- Detection: Fan-out pattern from single source within 10 blocks

**Pattern: Immediate token conversion**
- All non-ETH/BTC tokens swapped to ETH or stablecoins via DEX
- Typically within 30 minutes of attack
- Common DEXes used: Uniswap, 1inch, Paraswap

---

## Cross-Chain Movement

**Preferred bridges (as of 2026):**
- THORChain (ETH → BTC primary route)
- RenBridge (historical, now defunct)
- Avoid: bridges with on-chain KYC or compliance layers

**Detection:** Monitor bridge contract interactions from flagged clusters

---

## Mixing Strategies

**Tornado Cash (pre-sanction, now alternative):**
- 100 ETH denominations preferred
- Multiple deposit/withdrawal cycles over 24–72 hours

**Post-TC alternatives:**
- RailGun (privacy protocol)
- Wasabi Wallet (BTC)
- Direct OTC to Chinese/Russian intermediaries

---

## Cash-Out Patterns

**Exchange targets:**
- Prefer exchanges with weaker KYC enforcement
- Known corridors: HTX (Huobi), MEXC, some smaller Southeast Asian exchanges
- P2P/OTC: Chinese OTC markets, Russian exchanges

**Timing:**
- Active hours: UTC 00:00–08:00 (Pyongyang business hours: 09:00–17:00 KST)
- Reduced activity during DPRK national holidays

---

## References

- FBI/CISA Advisory AA22-108A: https://www.cisa.gov/uscert/ncas/alerts/aa22-108a
- OFAC DPRK Sanctions: https://home.treasury.gov/policy-issues/financial-sanctions/sanctions-programs-and-country-information/north-korea-sanctions
- Chainalysis 2024 Crypto Crime Report: https://www.chainalysis.com/blog/crypto-crime-report-2024/
