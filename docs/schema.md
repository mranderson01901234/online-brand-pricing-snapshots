# Schema

This document describes the data schema used in pricing snapshots.

## Status

Schema documentation will be published alongside the first data snapshots. This placeholder outlines the expected structure.

## Expected fields

The following fields are anticipated in snapshot data files:

| Field | Description |
|-------|-------------|
| `snapshot_date` | Date of the snapshot (ISO 8601) |
| `brand` | Brand or retailer identifier |
| `product_id` | Unique product identifier |
| `product_name` | Product name as displayed |
| `price` | Current listed price |
| `currency` | Currency code (ISO 4217) |
| `original_price` | Original price if discounted |
| `discount_indicator` | Whether a discount is applied |
| `category` | Product category if available |
| `url` | Source URL |

## Notes

- Field availability may vary by brand
- Additional metadata fields may be included
- Schema may evolve as the dataset matures

Refer to snapshot release notes for field-level documentation specific to each release.

