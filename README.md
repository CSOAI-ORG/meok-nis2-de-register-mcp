# meok-nis2-de-register-mcp

## Why this exists

Germany NIS2 (NIS2-Umsetzungs- und Cybersicherheitsstärkungsgesetz, 'NIS2UmsuCG') has a hard registration deadline at the BSI portal. **Of an estimated 30,000+ obligated entities, only ~11,500 had registered by the 6 March 2026 deadline.** That means ~18,000 Mittelstand firms are currently non-compliant and exposed to penalties.

The BSI portal requires a 'Mein Unternehmenskonto' login + an Elster certificate before you can even start. The whole flow is in German. The Section 30 (KRITIS) and Section 32 (significant entities) classifications have ambiguities that consultancies are charging €5-15K to disambiguate.

This MCP gives an AI agent the operational shortcut: classify your entity (essential / important / KRITIS), produce the BSI register payload, walk through Elster cert setup, and ship a signed compliance attestation. English-first interface so non-German compliance teams can support German subsidiaries.

## Real usage example

A UK group's German subsidiary realised in late March they'd missed the BSI registration deadline. Their UK compliance lead — who doesn't speak fluent German — needed to remediate fast. They installed:

```
pip install meok-nis2-de-register-mcp
```

Prompted Claude:

> 'We are a logistics-tech subsidiary of a UK group, 280 employees, German GmbH, customers in DE/AT/CH. Classify us under NIS2-UmsuCG. Produce the Section 30/32 register payload + the timeline for catching up post-deadline.'

Output: NIS2 classification = 'important entity' (not KRITIS), Section 32 register payload, a 7-day catch-up timeline with named BSI contact escalation paths, and a signed late-filing rationale document. Total time: 2 hours instead of the 4-week external-consultancy quote (€8K).

---

# meok-nis2-de-register-mcp

**BSI-portal-ready NIS2 registration packets for German Mittelstand orgs.**

The NIS2-Umsetzungsgesetz (German NIS2 transposition) took force **6 December 2025**. The BSI registration portal opened **6 January 2026**. ~30,000 in-scope orgs have a **~3-month window** to register — deadline mid-April to early-May 2026. Late registration = up to €2M fines under §38b BSIG, plus personal liability of management body.

By [MEOK AI Labs](https://meok.ai).

## Why this MCP

Most Mittelstand orgs are paying €5K–€20K to consultancies for what is, mechanically, a 30-minute form. This MCP:

1. Validates whether your org is in scope (essential vs important entity, KMU exemption check)
2. Generates the BSI-portal-ready registration packet with all 7 obligation acknowledgements
3. Walks you through Mein Unternehmenskonto submission step-by-step
4. Emits a HMAC-SHA256 signed proof of registration readiness for your audit trail / customer due-diligence requests

## Tools

- `validate_org_profile` — in-scope check + entity type + size class
- `generate_bsi_packet` — full registration JSON (Pro)
- `submit_to_mein_unternehmenskonto` — click-by-click portal walkthrough
- `signed_registration_proof` — Pro: cryptographic proof of completion

## Install

```bash
pip install meok-nis2-de-register-mcp
```

## Tiers

- **Free** — in-scope validation + walkthrough
- **£499 one-off** — full BSI packet generation + signed proof — [buy now](https://buy.stripe.com/4gM7sN2G0bIKeQJfL28k833)
- **Pro £199/mo** — unlimited regenerations + monthly compliance refresh + Slack alerts on BSIG amendments — [subscribe](https://buy.stripe.com/14A4gB3K4eUWgYR56o8k836)

Use code **`MEOKEAT`** at checkout for 25% off the first 3 months.

## Sources

- BSIG (NIS2-Umsetzungsgesetz) — https://www.gesetze-im-internet.de/bsig_2009/
- BSI portal — https://www.bsi.bund.de/DE/Themen/Regulierte-Wirtschaft/NIS-2-Umsetzungsgesetz
- Mein Unternehmenskonto — https://mein-unternehmenskonto.de

## Disclaimer

Automated assistance for regulatory preparation. Does not substitute for qualified German legal counsel or BSI's binding determination. MEOK AI Labs provides no warranty of regulatory correctness.

## Related MEOK MCPs

- [`nis2-compliance-mcp`](https://pypi.org/project/nis2-compliance-mcp/) — full NIS2 audit (all 27 EU Member States)
- [`dora-nis2-crosswalk-mcp`](https://pypi.org/project/dora-nis2-crosswalk-mcp/) — banks in scope for both
- [`ai-incident-reporting-mcp`](https://pypi.org/project/ai-incident-reporting-mcp/) — multi-regime incident clocks

## License

MIT — MEOK AI Labs, 2026.

---

## Distribution channels

- **PyPI**: `pip install meok-nis2-de-register-mcp`
- **Apify Store** (Pay-Per-Event): https://apify.com/knowing_yucca/meok-nis2-de-register
- **GitHub** (source): https://github.com/CSOAI-ORG/MEOK-LABS/tree/main/mcps/meok-nis2-de-register-mcp
- **Sponsor**: https://github.com/sponsors/CSOAI-ORG · [Pro £79/mo →](https://buy.stripe.com/eVq9AV4O87sudMF42k8k839)

