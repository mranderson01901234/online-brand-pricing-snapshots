# FAQ

---

**How often does this update?**

Weekly. Same collection window each week. This is a structured historical record, not a real-time feed.

**What does the dataset cover?**

Publicly visible pricing from online brand storefronts: current prices, original prices, discount indicators, and category context. Brands in scope are documented in each release.

**Is this data complete?**

No.

This captures pricing behavior, not full product catalogs. A consistent sample that's comparable week over week is more useful than exhaustive coverage that varies. Completeness is not the goal. Comparability is.

**Can I use this commercially?**

Yes. MIT license.

You're responsible for ensuring your use complies with applicable laws and any terms of service from original sources. We publish aggregated snapshots of publicly visible data. Downstream use is on you.

**What's excluded?**

- Member or loyalty pricing
- Prices behind logins
- Cart-only discounts
- Regional price variations (unless explicitly collected)
- Flash sales outside the collection window

If it's not visible to a standard visitor at collection time, it's not in the snapshot.

**Why weekly?**

Daily captures noise. Prices don't change meaningfully every day for most products. Weekly is frequent enough to catch trends and promotions without drowning in redundant data.

**Can I request a brand?**

No. Coverage is based on data quality, relevance, and feasibility. Scope is documented transparently.

**How do I cite this?**

```
Online Brand Pricing Snapshots. Project Blueprint.
https://github.com/mranderson01901234/online-brand-pricing-snapshots
```

See [CITATION.cff](../CITATION.cff) for machine-readable format.

**What if I find an error?**

Open an issue. Include the snapshot date, brand, and specific problem. We'll investigate.

**Will historical snapshots change?**

No. Published snapshots are immutable. If we find a collection error, it's documented in release notes but the original snapshot is not modified.
