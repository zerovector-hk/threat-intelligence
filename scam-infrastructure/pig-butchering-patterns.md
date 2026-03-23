# Pig Butchering / Romance Scam On-Chain Infrastructure Patterns

> **Last Updated:** 2026-03-22
> **Source:** ZeroVector case analysis + public research
> **Note:** Specific scam addresses are not listed here due to ongoing investigations. Contact intelligence@merkleclaw.com for case-specific data.

---

## Infrastructure Patterns

### Collection Address Characteristics

Pig butchering scams typically use a hierarchical fund collection structure:

```
Victim deposits (USDT/ETH)
    ↓
Collection addresses (often 1–5, receive from many victims)
    ↓
Aggregation wallets (consolidate across collection addresses)
    ↓
Bridge to Tron (TRC-20 USDT preferred for lower fees)
    ↓
Exchange deposits (often multiple, including some licensed)
```

### Detection Signals

1. **Many-to-one inflow pattern**: Single address receives from 10+ unique addresses within 7 days
2. **Consistent amounts**: Victim deposits often follow coached amounts ($500, $1000, $5000)
3. **Rapid consolidation**: Funds moved within 1–4 hours of receipt
4. **Tron bridge preference**: ETH USDT → Tron TRC-20 USDT via bridge (lower fees, faster)
5. **Exchange deposit clustering**: Multiple scam addresses feeding same exchange deposit address

### Common Chains

- **Ethereum**: Initial victim deposits (USDT ERC-20)
- **Tron**: Preferred consolidation chain (USDT TRC-20)
- **BNB Chain**: Secondary route

### Typical Scale

- Single scam operation: 20–200 victim addresses
- Revenue per operation: $500k–$50M
- Estimated global scale: Billions USD annually (Interpol data)

---

## If You're Investigating a Pig Butchering Case

1. Start with victim's deposit transaction hash
2. Trace to collection address — look for other inflows (other victims)
3. Follow consolidation path to Tron bridge
4. Identify exchange deposit addresses (potential freeze targets)
5. Cross-reference with known scam syndicate addresses in MerkleClaw database

**For case-specific intelligence:** contact@zerovector.hk
**For MerkleClaw beta access:** merkleclaw.com/beta

---

## References

- UNODC Report on Scam Centres: https://www.unodc.org/roseap/en/2023/10/transnational-crime-southeast-asia/story.html
- FBI IC3 2023 Annual Report: https://www.ic3.gov/Media/PDF/AnnualReport/2023_IC3Report.pdf
