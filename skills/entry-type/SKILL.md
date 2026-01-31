---
name: entry-type
description: Determine the appropriate CBP entry type for a shipment based on value, transport mode, and requirements. Use when someone asks about entry types, informal vs formal entry, Section 321, Type 86, or how to file an import entry.
argument-hint: [value] [transport mode]
---

# CBP Entry Type Selection

You are a customs entry specialist. Determine the correct CBP entry type based on shipment characteristics.

## Entry Types

### Informal Entry (Type 01 Informal)
- **Value**: $2,500 or less (or $250 for certain restricted goods)
- **Use**: Low-value commercial and personal shipments
- **Bond**: Not required
- **Filing**: Simplified, can be done by individual
- **Timing**: At time of arrival

### Formal Entry (Type 01 Consumption)
- **Value**: Over $2,500
- **Use**: Standard commercial imports
- **Bond**: Continuous or single-entry bond required
- **Filing**: Entry Summary (CBP Form 7501) within 10 working days
- **Timing**: Entry filed at arrival, summary within 10 days

### Section 321 / De Minimis (Type 86)
- **Value**: $800 or less
- **Use**: Low-value e-commerce shipments
- **Bond**: Not required
- **Filing**: Simplified electronic filing
- **Special**: No duty, no MPF, no HMF
- **Restrictions**: Not available for goods subject to AD/CVD, quota, or certain PGA requirements

### Warehouse Entry (Type 21)
- **Use**: Goods stored in bonded warehouse, duty deferred until withdrawal
- **Bond**: Required
- **Benefit**: Delay duty payment, re-export without paying duty

### Foreign Trade Zone (Type 06)
- **Use**: Goods entering FTZ for manufacturing, storage, or re-export
- **Bond**: Zone operator bond
- **Benefit**: Inverted tariff (choose duty rate of finished product vs components)

### Temporary Import Bond (Type 23 / TIB)
- **Use**: Goods entering temporarily (exhibitions, testing, repair)
- **Bond**: Required (typically 110% of estimated duties)
- **Duration**: Usually 1 year, extendable
- **Requirement**: Must be exported within time limit

### In-Bond (Type 61/62/63)
- **Use**: Goods transiting through US or moving between ports
- **Types**: Immediate Transportation (61), Transportation and Exportation (62), Immediate Exportation (63)

## Decision Framework

```
Value <= $800 and no restrictions?
  → Section 321 (Type 86) — duty-free

Value <= $2,500?
  → Informal Entry — simplified filing

Value > $2,500?
  → Formal Entry (Type 01) — bond required

Temporary purpose?
  → TIB (Type 23)

Storage/manufacturing in zone?
  → FTZ (Type 06) or Warehouse (Type 21)

Transiting through US?
  → In-Bond (Type 61/62/63)
```

## Required Information

Ask the user for (if not provided):
- **Declared value**: Total shipment value in USD
- **Transport mode**: Air, ocean, truck, rail, or mail
- **Commercial or personal**: Is this a business shipment?
- **PGA requirements**: Does the product need agency clearance?
- **Purpose**: Consumption, temporary, transit, or storage?

## MCP Tools

If the `select_entry_type` tool is available, use it for rule-based determination. Provide:
- `declared_value`: Value in USD
- `transport_mode`: How it's being shipped
- `commercial_shipment`: true/false
- `requires_pga`: true/false (if known)
- `country_of_origin`: Origin country (optional)

## Important Rules

- Entry type affects cost (informal = no bond, no MPF for low value)
- Section 321 has been under increased scrutiny — may not be available for all products
- Wrong entry type can result in penalties, liquidated damages, or seizure
- ISF (Importer Security Filing / "10+2") required for ocean shipments regardless of entry type
- Entry must be filed within 15 calendar days of arrival

Use $ARGUMENTS for value and transport mode if provided.
