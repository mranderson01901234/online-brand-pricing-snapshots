# Schema

Structure of pricing snapshot files.

---

## Design principles

- **Stable**: Same fields across all snapshots. Schema is versioned.
- **Explicit**: Missing data is null, not inferred or defaulted.
- **Behavior-focused**: Fields capture pricing signals, not product attributes.

## Field definitions

### Identifiers

| Field | Type | Description |
|-------|------|-------------|
| `snapshot_date` | date | ISO 8601 date of snapshot (YYYY-MM-DD) |
| `brand` | string | Brand identifier, stable across snapshots |
| `product_id` | string | Brand-specific product identifier |
| `source_url` | string | URL where pricing was observed |

### Pricing

| Field | Type | Description |
|-------|------|-------------|
| `price` | decimal | Current listed price |
| `currency` | string | ISO 4217 currency code (USD, EUR, etc.) |
| `original_price` | decimal | Comparison/original price if discounted; null otherwise |
| `discount_pct` | decimal | Calculated discount percentage (0-100); null if not discounted |

### Discount indicators

| Field | Type | Description |
|-------|------|-------------|
| `is_discounted` | boolean | True if presented as on sale |
| `discount_type` | string | Category: sale, clearance, promotion; null if not distinguishable |
| `discount_badge` | string | Raw badge text as displayed; null if none |

### Category

| Field | Type | Description |
|-------|------|-------------|
| `category` | string | Primary category as presented by brand |
| `category_normalized` | string | Standardized category for cross-brand comparison; may be null |

### Temporal

| Field | Type | Description |
|-------|------|-------------|
| `snapshot_timestamp` | timestamp | ISO 8601 timestamp of collection |
| `collection_window` | string | Identifier for the collection batch |

## Stability promise

- **Fields are never removed** without a major version bump
- **Fields may be added** in any release; added fields appear in all future snapshots
- **Field types are stable**; a string stays a string, a decimal stays a decimal
- **Nulls are explicit**; missing data is null, not empty string or zero

Code written against this schema will work across historical and future snapshots.

## Nullability

| Field | Can be null? |
|-------|--------------|
| `snapshot_date` | No |
| `brand` | No |
| `product_id` | No |
| `source_url` | No |
| `price` | No |
| `currency` | No |
| `original_price` | Yes (null if not discounted) |
| `discount_pct` | Yes (null if not discounted) |
| `is_discounted` | No |
| `discount_type` | Yes (null if not distinguishable) |
| `discount_badge` | Yes (null if none displayed) |
| `category` | Yes (some brands don't categorize) |
| `category_normalized` | Yes (not all categories map) |
| `snapshot_timestamp` | No |
| `collection_window` | No |

## File format

- CSV with header row
- UTF-8 encoding
- Fields quoted when containing commas or quotes
- Newlines: LF (Unix-style)

---

Field-level notes for specific brands are documented in snapshot release notes.
