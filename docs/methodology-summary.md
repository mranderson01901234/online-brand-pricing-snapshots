# Methodology Summary

This is a high-level summary of how pricing snapshots are collected and processed. For full methodology details, see the [complete documentation](https://getblueprint.io/methodology).

## What a snapshot represents

A snapshot is a point-in-time capture of pricing behavior from online storefronts. Each snapshot includes:

- **Current listed prices** — What a visitor would see on the product page
- **Original/comparison prices** — The reference price shown alongside discounted items
- **Discount indicators** — Whether the item is marked as on sale, clearance, or promotion
- **Category context** — Product categorization as presented by the brand

A snapshot does not represent a complete product catalog. It represents observable pricing signals at the moment of collection.

## How pricing is normalized

Raw pricing data varies significantly across brands. Normalization ensures comparability:

- Prices are recorded in their original currency with explicit currency codes
- Percentage discounts are calculated consistently from original and current prices
- Price formats are standardized (decimals, thousands separators, currency symbols stripped)
- Missing original prices on non-discounted items are handled explicitly, not inferred

## How discounts are interpreted

A product is marked as discounted if the source page presents it that way—sale badge, strikethrough price, or explicit discount callout.

We do not infer discounts from price changes over time. If a price drops but the brand doesn't mark it as a sale, it's recorded as a regular price.

This means the dataset reflects *presented* discount behavior, not *detected* price changes.

## What verification means

Before inclusion in a snapshot, data passes through:

- **Format validation** — Prices must be parseable and within reasonable bounds
- **Consistency checks** — Currency, discount math, and category mappings are verified
- **Anomaly flagging** — Outliers (e.g., $0.01 prices, 99% discounts) are reviewed manually
- **Source confirmation** — Spot checks against live pages during collection window

Verification is about catching collection errors, not guaranteeing business accuracy.

## What's excluded

Certain pricing signals are intentionally excluded:

- **Authenticated prices** — Anything requiring login or account creation
- **Cart-dependent pricing** — Discounts that only appear after adding to cart
- **Regional variations** — Unless a region is explicitly targeted for collection
- **Bundle or conditional pricing** — "Buy 2 get 1 free" style promotions
- **Rapidly changing prices** — If a price changes during collection, the first observed value is used

## Cadence

Snapshots are collected weekly. The specific collection window is consistent week over week to minimize day-of-week effects.

Weekly cadence balances signal quality against data volume. More frequent collection would capture noise; less frequent collection would miss meaningful patterns.

---

For the complete methodology, including technical details on collection infrastructure, see: https://getblueprint.io/methodology
