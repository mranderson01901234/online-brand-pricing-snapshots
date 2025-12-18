# Schema

This document describes the structure of pricing snapshot files.

## Design principles

The schema is designed for stability and comparability:

- **Consistent across snapshots** — The same fields appear in every snapshot, so you can join or compare across time periods without mapping
- **Explicit over inferred** — Missing data is marked as missing, not filled with defaults
- **Behavior-focused** — Fields capture pricing signals, not product attributes

## Field categories

Snapshot files include fields in the following categories:

### Identifiers

- Snapshot date (ISO 8601)
- Brand identifier
- Product identifier (brand-specific, stable across snapshots where possible)
- Source URL

### Category groupings

- Primary category (as presented by brand)
- Normalized category (standardized across brands where applicable)

### Pricing

- Current listed price
- Currency code (ISO 4217)
- Original/comparison price (if discounted)
- Discount percentage (calculated)

### Discount indicators

- Is discounted (boolean)
- Discount type (sale, clearance, promotion—where distinguishable)
- Discount badge text (raw, as displayed)

### Temporal markers

- Snapshot timestamp
- Collection window identifier

## Schema stability

The schema is versioned. When fields are added, they're added to all future snapshots. Fields are never removed or renamed without a major version bump.

This means you can write code against the schema once and expect it to work across historical and future snapshots.

## Field availability

Not all fields are populated for all brands. Some brands don't expose original prices. Some don't categorize products consistently. The schema accommodates this with explicit nulls rather than omissions.

Field-level documentation is published with each snapshot release, noting any brand-specific gaps or caveats.

## Sample structure

Detailed field definitions will be published with the first data release. The structure above reflects the planned schema.
