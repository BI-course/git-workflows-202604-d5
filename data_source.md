
* **Member 2:** Issue #2 - 50% Complete Milestone - Title: feature/lab-1/research-on-data-sources. Description: Create a `data_source.md` file reviewing sources of data in a business.

# Data Governance for Data Sources

## Overview
This section summarizes how data governance applies specifically to data sources in this project, ensuring compliance with PII (Personally Identifiable Information) rules and legal standards.

## What Counts as PII in Data Sources
PII includes any data that can identify a customer, employee, or user, such as names, email addresses, phone numbers, national/customer IDs, addresses, and IP addresses. Only collect PII from data sources if there is a defined, approved purpose.

## Governance Rules for Data Sources
- Only approved data sources are allowed (internal systems, external APIs, etc.)
- PII collection must have a defined purpose and be minimized
- All PII from sources must be classified as Restricted and handled securely
- PII should be cleaned, masked, or anonymized as early as possible in the pipeline

## Compliance
All data source activities must comply with the Kenya Data Protection Act (2019):
- Obtain consent for collecting personal data
- Ensure secure storage and processing
- Respect the right to privacy and data protection

## Key Recommendations for Data Sources
- Minimize PII collection from sources
- Never expose raw PII in analytics
- Use IDs instead of names wherever possible
- Regularly review and approve data sources
- Keep governance aligned with overall system design

---
*This section is aligned with the overall project governance model. See governance.md for full details.*