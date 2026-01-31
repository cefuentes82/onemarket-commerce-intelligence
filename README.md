# OneMarket Commerce Intelligence

Commerce intelligence for international trade. HTS classification, duty calculation, PGA requirements, entry type selection, and complete landed cost analysis.

Built for [Claude Code](https://claude.ai/code) and [Claude Cowork](https://claude.ai/cowork).

## Install

```bash
claude plugin install onemarket-world/commerce-intelligence
```

## Skills

| Command | Description |
|---------|-------------|
| `/onemarket-commerce-intelligence:classify` | Classify a product to its HTS code |
| `/onemarket-commerce-intelligence:duty` | Calculate customs duty and fees |
| `/onemarket-commerce-intelligence:pga` | Check Partner Government Agency requirements |
| `/onemarket-commerce-intelligence:entry-type` | Select the right CBP entry type |
| `/onemarket-commerce-intelligence:landed-cost` | Full landed cost analysis |

### Examples

```
/onemarket-commerce-intelligence:classify women's cotton t-shirt from Vietnam

/onemarket-commerce-intelligence:duty 6109.10.0012 $5000 China

/onemarket-commerce-intelligence:pga stainless steel food container

/onemarket-commerce-intelligence:entry-type $15000 ocean commercial

/onemarket-commerce-intelligence:landed-cost 1000 cotton t-shirts from Vietnam to Los Angeles
```

## What It Does

This plugin gives Claude deep expertise in customs and international trade:

- **HTS Classification**: Follows the General Rules of Interpretation (GRI 1-6) to determine the correct tariff code for any product
- **Duty Calculation**: Breaks down all import costs — duty, MPF, HMF, Section 301, AD/CVD
- **PGA Requirements**: Identifies which government agencies (FDA, EPA, USDA, CPSC, FWS, TTB, DOT) need to clear your product
- **Entry Type Selection**: Recommends informal, formal, Section 321, FTZ, TIB, or warehouse entry
- **Landed Cost**: Complete factory-to-warehouse cost analysis including freight, insurance, duties, brokerage, and domestic transport

## Enhanced Mode (Optional)

For Oracle-grade accuracy, connect the [C8 Memory MCP server](https://github.com/onemarket-world/c8-memory) which provides specialized AI reasoning networks (Oracle INNs):

- `classify_hts` — Opus 4.1 for complex classification reasoning
- `calculate_duty` — Sonnet 4.5 for fast, precise calculations
- `determine_pga_requirements` — Opus 4.1 for regulatory expertise
- `select_entry_type` — Opus 4.1 for entry type rules

The plugin works standalone with Claude's built-in knowledge. The MCP tools add verified, real-time accuracy.

## Who It's For

- E-commerce sellers importing products
- Customs brokers and freight forwarders
- Logistics and supply chain teams
- Procurement officers
- Trade compliance professionals
- Anyone importing goods into the United States

## Architecture

This plugin follows the **source-of-truth pattern**: skills teach Claude *when* and *how* to reason about customs topics. They never hardcode rates, thresholds, or regulatory data that could go stale. When Oracle tools are available, the skills delegate to them for current, verified answers.

## License

MIT

---

Built by [OneMarket World](https://onemarket.world) — the platform for borderless commerce.
