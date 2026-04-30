1. Overview

This document defines how data will be governed within our project, including how Personally Identifiable Information (PII) is collected, stored, processed, and accessed. It aligns with the system we are building (data pipeline + warehouse + analytics) and ensures compliance with legal and ethical standards.

This governance model supports:

Data ingestion from business data sources
ETL/ELT processing pipelines
A star schema data warehouse
Controlled access for users and analytics
2. What Counts as PII in This Project

In our system, PII includes any data that can identify a customer, employee, or user. Examples relevant to our dataset:

Names (first name, last name)
Email addresses
Phone numbers
National ID / customer ID
Location or address data
IP addresses (if collected)

PII will not be used directly in analytics tables unless necessary.

3. Data Flow and Governance Points

Our governance applies at each stage of the pipeline:

3.1 Data Sources
Internal systems (e.g., sales, CRM)
External APIs or datasets

Governance Rule:

Only approved sources are allowed
PII collection must have a defined purpose
3.2 Data Pipeline (ETL / ELT)
Data is extracted, transformed, and loaded into staging/warehouse

Governance Rule:

PII should be cleaned, masked, or anonymized during transformation
Raw PII should remain in secure staging layers only
3.3 Data Warehouse (Star Schema)
Fact and dimension tables used for analytics

Governance Rule:

Avoid storing direct PII in fact tables
Use surrogate keys instead of real identifiers
Sensitive attributes should be removed or generalized
4. Data Classification

We classify data in this project as:

Public – Safe for sharing
Internal – Business-only data
Confidential – Sensitive business data
Restricted (PII) – Personal data requiring strict protection

All PII is Restricted.

5. Access Control Model

We implement Role-Based Access Control (RBAC):

Roles in This Project
Admin / Data Owner
Full access to all datasets including raw PII
Data Engineer
Access to pipelines and staging data
Limited access to raw PII (only when necessary)
Analyst
Access to warehouse tables (no raw PII)
End User / Viewer
Access to dashboards only (aggregated data)
Rules
Least privilege principle applies
Access must be approved
Authentication (password + MFA if possible)
6. PII Protection Techniques

To secure PII, we apply:

Encryption (at rest and in transit)
Masking (e.g., showing only last 4 digits)
Anonymization (removing identifiers)
Pseudonymization (replacing with IDs)

Example:

Replace customer name with customer_id
7. Data Storage
Raw data stored in secure staging area
Cleaned data stored in warehouse
Access to storage systems is restricted

Rule: PII must never be stored in unsecured files (e.g., local CSVs without protection).

8. Data Sharing
No sharing of raw PII outside the system
Only aggregated or anonymized data can be shared
Any sharing must be approved by the Data Owner
9. Compliance (Kenya Context)

This project aligns with:

Kenya Data Protection Act (2019)

Key requirements:

Consent for collecting personal data
Secure storage and processing
Right to privacy and data protection
10. Logging and Monitoring
Track who accesses data
Monitor unusual access patterns
Maintain audit logs
11. Incident Management

If a data breach occurs:

Identify affected data
Restrict access immediately
Notify relevant authorities (if required)
Fix vulnerabilities
12. Team Responsibilities 
Member 1 (README) → Documents roles and governance overview
Member 2 (Data Sources) → Ensures sources comply with PII rules
Member 3 (Star Schema) → Designs schema avoiding PII exposure
Member 4 (Pipeline) → Implements masking/anonymization in ETL/ELT
Member 5 (Governance) → Defines and enforces all policies in this file
13. Key Recommendations
Minimize PII collection
Never expose raw PII in analytics
Use IDs instead of names
Regularly review access permissions
Keep governance aligned with system design