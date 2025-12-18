# Frequently Asked Questions

## How often does this update?

Weekly. Every snapshot covers a consistent collection window, same time each week. This isn't a real-time feed—it's a structured historical record.

## What does the dataset cover?

Publicly visible pricing from online brand storefronts. Current prices, original prices, discount indicators, and category context. The specific brands in scope are documented in each snapshot release.

## Is this data complete?

No, and it's not trying to be.

This dataset captures pricing *behavior*, not full product catalogs. If a brand sells 10,000 SKUs and we capture 2,000 of them, that's fine—as long as the sample is consistent week over week.

Completeness is not the goal. Comparability is.

## Can I use this commercially?

Yes. The dataset is released under the MIT license.

That said, you're responsible for ensuring your use complies with applicable laws and any terms of service from the original sources. We're publishing aggregated snapshots of publicly visible data, but downstream use is on you.

## What's excluded?

- Member or loyalty pricing
- Prices behind logins
- Cart-only discounts
- Regional price variations (unless explicitly collected)
- Flash sales that happen outside the collection window

If it's not visible to a standard visitor at the time of collection, it's not in the snapshot.

## Why weekly instead of daily?

Daily snapshots would capture more noise than signal. Prices don't change meaningfully every day for most products. Weekly cadence is frequent enough to catch trends and promotions, but not so frequent that you're drowning in redundant data.

## Can I request a specific brand?

Coverage decisions are made based on data quality, relevance, and feasibility. We don't take requests, but the scope is documented transparently.

## How should I cite this dataset?

Use the citation block in the README, or reference the [CITATION.cff](../CITATION.cff) file for machine-readable formats.

If you're publishing research, a citation helps others find the source. If you're building a product, attribution is appreciated but not required.
