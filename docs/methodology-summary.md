# Methodology Summary

High-level summary of how pricing snapshots are collected and processed.

For complete methodology details: https://getblueprint.io/methodology

---

## What a snapshot represents

A snapshot is a point-in-time capture of pricing behavior from online storefronts.

Each snapshot includes:
- Current listed prices (what a visitor sees on product pages)
- Original/comparison prices (reference prices shown alongside discounted items)
- Discount indicators (sale, clearance, promotion markers)
- Category context (product categorization as presented by brand)

A snapshot is not a complete product catalog. It's a consistent sample of observable pricing signals.

## Collection approach

- **Timing**: Weekly, same collection window each week to minimize day-of-week effects
- **Perspective**: Standard visitor view (no authentication, no account history, no regional targeting)
- **Scope**: Publicly accessible storefronts only
- **Consistency**: Same brands, same collection method, same schema across snapshots

## Price normalization

Raw pricing varies across brands. Normalization ensures comparability:

- Prices recorded in original currency with explicit ISO 4217 currency codes
- Percentage discounts calculated consistently: `(original - current) / original`
- Price formats standardized (decimals normalized, currency symbols stripped)
- Missing original prices on non-discounted items left null, not inferred

## Discount interpretation

A product is marked discounted if the source page presents it that way: sale badge, strikethrough price, or explicit discount callout.

Discounts are not inferred from price changes over time. If a price drops but the brand doesn't mark it as a sale, it's recorded as a regular price.

The dataset reflects **presented** discount behavior, not **detected** price changes.

## Verification

Before inclusion, data passes through:

- **Format validation**: Prices must be parseable and within reasonable bounds
- **Consistency checks**: Currency codes, discount math, category mappings verified
- **Anomaly flagging**: Outliers (e.g., $0.01 prices, 99% discounts) reviewed
- **Source confirmation**: Spot checks against live pages during collection window

Verification catches collection errors. It does not guarantee business accuracy.

## Exclusions

Certain pricing signals are intentionally excluded:

- **Authenticated prices**: Login or account required
- **Cart-dependent pricing**: Discounts only visible after add-to-cart
- **Regional variations**: Unless explicitly targeted
- **Bundle pricing**: "Buy 2 get 1 free" style promotions
- **Mid-collection changes**: First observed value used if price changes during window

## Cadence rationale

Weekly balances signal quality against data volume.

More frequent: captures noise, not signal. Prices don't change meaningfully daily for most products.

Less frequent: misses promotional cycles, seasonal patterns, competitive responses.

Weekly is the sweet spot for behavioral analysis.

---

Full methodology: https://getblueprint.io/methodology
