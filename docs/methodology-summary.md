# Methodology Summary

This document provides a high-level overview of how pricing snapshots are collected and processed. This is a summary, not a complete methodology specification.

## Collection

Pricing data is collected from publicly accessible product pages on online storefronts. Collection occurs at regular weekly intervals to maintain consistency across snapshots.

Data is retrieved as it would appear to a standard visitor without account-specific pricing or regional overrides where possible.

## Verification

Collected data undergoes verification to ensure accuracy:

- Price values are validated against expected formats
- Currency and unit consistency is checked
- Obvious collection errors are flagged and excluded

## Normalization

Raw data is normalized to a consistent schema:

- Prices are recorded in their original currency
- Discount indicators are standardized
- Product identifiers are mapped where possible

## Limitations

This methodology captures publicly visible pricing only. It does not account for:

- Member-only or loyalty pricing
- Regional price variations (unless explicitly collected)
- Flash sales or time-limited promotions that fall outside collection windows
- Prices that require interaction beyond page load

## Full methodology

A complete methodology document may be published separately. This summary is intended to provide sufficient context for understanding the dataset's scope and constraints.

