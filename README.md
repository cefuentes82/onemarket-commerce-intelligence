# OneMarket Commerce Intelligence

Commerce intelligence for international trade. Covers the full import lifecycle — from sourcing strategy to regulatory compliance to cost optimization.

Built for [Claude Code](https://claude.ai/code) and [Claude Cowork](https://claude.ai/cowork).

## Install

```bash
claude plugin install cefuentes82/onemarket-commerce-intelligence
```

## Skills

| Command | What it answers |
|---------|-----------------|
| `/onemarket-commerce-intelligence:source` | Where should I source this product? |
| `/onemarket-commerce-intelligence:classify` | What's the HTS code? |
| `/onemarket-commerce-intelligence:landed-cost` | What will it cost to import? |
| `/onemarket-commerce-intelligence:comply` | What regulations apply? |
| `/onemarket-commerce-intelligence:optimize` | How can I reduce import costs? |

### Examples

```
/onemarket-commerce-intelligence:source leather handbags

/onemarket-commerce-intelligence:classify women's cotton t-shirt from Vietnam

/onemarket-commerce-intelligence:landed-cost 1000 cotton t-shirts from Vietnam to Los Angeles

/onemarket-commerce-intelligence:comply stainless steel food container from China

/onemarket-commerce-intelligence:optimize $50K/month in apparel from China
```

## What It Does

This plugin gives Claude structured expertise across the full trade decision lifecycle:

- **Source** — Evaluate sourcing countries, compare landed costs across origins, discover suppliers. Covers FTA advantages, risk factors, and the China+1 strategy.
- **Classify** — Determine the correct HTS code using General Rules of Interpretation (GRI 1-6), validated against real customs transaction patterns.
- **Landed Cost** — Complete factory-to-warehouse cost analysis. Entry type selection, duty, Section 301 tariffs, MPF, HMF, freight, insurance, brokerage, domestic transport, and hidden costs (demurrage, detention, exam fees).
- **Comply** — Full regulatory landscape: PGA requirements (FDA, EPA, USDA, CPSC, FWS, TTB, DOT), OFAC sanctions screening, denied party lists, export controls, and documentation obligations.
- **Optimize** — Actionable strategies to reduce import costs: FTA utilization, tariff engineering, first sale valuation, Foreign Trade Zones, duty drawback, country-of-origin shifting, classification review, and Section 321 strategies.

## How It Works

The plugin works standalone — no additional setup required. Each skill teaches Claude structured reasoning frameworks for trade topics (GRI rules for classification, cost component breakdowns for landed cost, agency jurisdiction mapping for compliance).

Skills follow the **source-of-truth pattern**: they encode *methodology* (how to reason about classification, what cost components to include, which regulations apply) but never hardcode *data* (specific rates, thresholds, or fees that change). Claude applies the methodology using its training knowledge.

For production environments, the skills integrate with MCP tools when available:

| Tool | Purpose |
|------|---------|
| `classify_hts` | Oracle classification engine |
| `calculate_duty` | Duty and fee calculation |
| `determine_pga_requirements` | PGA agency analysis |
| `select_entry_type` | Entry type recommendation |
| `get_hts_info` | HTS code lookup |
| `diana_search` | Product and supplier discovery |
| `diana_hts_lookup` | Real customs transaction data |
| `search_specs` | CBP specification documents |

## Who It's For

- E-commerce sellers importing products
- Customs brokers and freight forwarders
- Logistics and supply chain teams
- Procurement and sourcing officers
- Trade compliance professionals
- Anyone importing goods into the United States

## License

MIT

---

Built by [OneMarket World](https://github.com/cefuentes82/onemarket-commerce-intelligence).
