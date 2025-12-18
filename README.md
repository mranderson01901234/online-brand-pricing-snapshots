# Online Brand Pricing Snapshots

Weekly snapshots of online brand pricing and discount behavior.

Built for research, analysis, and benchmarking.

---

This repository exists to make pricing behavior observable.

Every week, we capture a structured snapshot of how online brands price their products—what's discounted, by how much, and how that changes over time. The result is a consistent, comparable record of pricing signals that would otherwise be lost.

This is not a product feed. It's a behavioral record.

## Why pricing snapshots exist

Continuous pricing data is noisy. Prices change hourly. Products appear and disappear. Promotions stack in unpredictable ways. Trying to reason about pricing behavior from a live feed is like trying to measure a river by watching it flow.

Snapshots solve this by freezing the state at regular intervals.

Weekly cadence is intentional. It's frequent enough to capture meaningful patterns—seasonal shifts, promotional cycles, competitive responses—but not so frequent that the data becomes exhaust. Each snapshot represents a clean, comparable slice of pricing behavior.

This repo publishes summaries, not raw inventory. The goal is insight, not completeness.

## What's included

- **Weekly snapshots** — Consistent, structured captures of pricing behavior across online brands
- **Historical comparability** — Each snapshot uses the same schema, so you can track changes over time
- **Discount behavior** — Not just prices, but how discounts are applied and how they shift
- **Documentation** — Methodology, schema, and usage guidance in `/docs`

What's *not* included: raw product listings, full catalog exports, or real-time feeds. This repo focuses on behavior, not inventory.

## Downloads (Coming Soon)

Snapshots will be published to:

```
snapshots/weekly/YYYY-MM-DD.csv   # Immutable weekly snapshot
snapshots/latest/weekly.csv       # Stable alias to most recent
```

Historical snapshots are never modified after publication. The `latest/` alias always points to the most recent complete snapshot.

First data release is in progress.

## Intended use

- Market research
- Pricing analysis
- Discount benchmarking
- Trend observation
- Academic research on e-commerce pricing

## Methodology

Data is collected from publicly accessible storefronts at consistent weekly intervals. Prices are normalized to a common schema, verified for format consistency, and aggregated to the snapshot level.

Collection captures pricing as it appears to a standard visitor—no login, no regional manipulation, no account-specific pricing.

For details, see [docs/methodology-summary.md](docs/methodology-summary.md).

## Limitations

This dataset reflects publicly visible pricing from the brands in scope. It does not capture:

- Member-only or loyalty pricing
- Prices behind logins or account walls
- Regional variations (unless explicitly collected)
- Flash sales or promotions that fall outside the weekly collection window
- Bundle pricing or conditional discounts that require cart interaction

Coverage may change as brands are added or removed. Historical snapshots remain unchanged.

## Citation

If you use this dataset, please cite it as:

```
Online Brand Pricing Snapshots. Project Blueprint.
Available at: https://github.com/mranderson01901234/online-brand-pricing-snapshots
```

See [CITATION.cff](CITATION.cff) for machine-readable citation information.

## Source

Source: https://getblueprint.io/datasets  
Methodology: https://getblueprint.io/methodology
