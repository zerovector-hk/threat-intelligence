# Contributing to MerkleClaw Threat Intelligence Feeds

Thank you for helping improve this dataset. Community contributions are essential for keeping this intelligence current.

---

## What We Accept

✅ **Addresses with verifiable public sources**
- OFAC/government sanctions
- Publicly disclosed exchange hacks (post-incident reports)
- Security firm reports (SlowMist, PeckShield, CertiK, etc.)
- Court documents or law enforcement press releases

✅ **Corrections to existing entries**
- Updated labels
- Additional references
- Confidence level adjustments with evidence

✅ **New attack pattern documentation**
- Documented incidents with on-chain evidence
- Behavioral patterns with detection logic

---

## What We Do NOT Accept

❌ Unverified personal accusations against individuals
❌ Addresses without a public, verifiable source
❌ Any content that could identify private individuals without legal process
❌ Speculative attributions without evidence

---

## How to Contribute

### Option 1: Open an Issue (Easiest)

1. Go to Issues → New Issue
2. Select template: "New Address Submission" or "Correction"
3. Fill in:
   - Address
   - Chain
   - Suggested label
   - Source URL (must be public)
   - Confidence level

### Option 2: Submit a Pull Request

1. Fork this repository
2. Add entries following the JSON schema in README
3. All entries require:
   - `address` (checksummed where applicable)
   - `chain`
   - `label`
   - `confidence` (confirmed/high/medium/low)
   - At least one `reference` URL
4. Submit PR with description of source

---

## Review Process

- All submissions reviewed within 7 days
- Confirmed OFAC entries: fast-tracked (usually 48 hours)
- Research-based entries: peer reviewed by ZeroVector team
- Rejected submissions receive explanation

---

## Questions?

Open a Discussion or email: intelligence@merkleclaw.com
