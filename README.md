# Online Brand Pricing Snapshots

Weekly snapshots of online brand pricing and discount behavior.

Built for research, analysis, and benchmarking.

---

## What this is

A structured, versioned record of how online brands price their products. Each snapshot captures what's discounted, by how much, and how that changes week over week.

This is not a product feed. It's a behavioral dataset.

## Why snapshots exist

Prices change constantly. Products appear and disappear. Promotions stack unpredictably. Trying to analyze pricing behavior from continuous data is like measuring a river by watching it flow.

Snapshots freeze state at regular intervals.

Weekly cadence captures meaningful patterns (seasonal shifts, promotional cycles, competitive responses) without drowning in noise. Each snapshot is a clean, comparable slice of pricing behavior across brands.

Point-in-time beats real-time when you're tracking behavior over time.

## What's included

- **Weekly snapshots** of pricing behavior across online brand storefronts
- **Historical comparability** via consistent schema across all snapshots
- **Discount signals** including original prices, sale indicators, and calculated discount percentages
- **Documentation** covering methodology, schema, and known limitations

What's not included: complete product catalogs, inventory data, or real-time feeds.

## Downloads (Coming Soon)

Snapshots will be published to:

```
snapshots/weekly/YYYY-MM-DD.csv   # Immutable weekly snapshot
snapshots/latest/weekly.csv       # Stable alias to most recent
```

Historical snapshots are immutable. The `latest/` alias points to the most recent complete snapshot.

First data release is in progress.

## Intended use

- Pricing analysis and benchmarking
- Market research on e-commerce behavior
- Discount strategy observation
- Academic research on retail pricing dynamics
- Building models or tools that need consistent pricing signals

## Methodology

Data is collected from publicly accessible storefronts at consistent weekly intervals. Prices are normalized, validated, and aggregated to snapshot level.

Collection captures pricing as it appears to a standard visitor: no login, no account-specific pricing, no regional manipulation.

See [docs/methodology-summary.md](docs/methodology-summary.md) for details.

## Limitations

This dataset reflects publicly visible pricing. It does not capture:

- Member-only or loyalty pricing
- Prices behind authentication
- Cart-dependent discounts
- Regional price variations (unless explicitly collected)
- Flash sales outside the collection window
- Bundle or conditional promotions

Coverage may evolve as brands are added or removed. Historical snapshots remain unchanged.

## Schema

Snapshot files use a stable, versioned schema. Fields include identifiers, pricing data, discount indicators, and temporal markers.

See [docs/schema.md](docs/schema.md) for field definitions.

## Citation

```
Online Brand Pricing Snapshots. Project Blueprint.
https://github.com/mranderson01901234/online-brand-pricing-snapshots
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## Source

Source: https://getblueprint.io/datasets
Methodology: https://getblueprint.io/methodology
