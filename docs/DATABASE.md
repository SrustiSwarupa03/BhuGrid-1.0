# BhuGrid 1.0 — Data Model Overview

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Database Platform:** Supabase / PostgreSQL  
**Development Stage:** Functional Prototype / Controlled DEMO  
---

## 1. Database Overview

BhuGrid 1.0 uses **Supabase**, built on PostgreSQL, to support structured institutional records, authenticated access and role-specific application workflows.

The database supports the platform's primary objective of connecting religious institutions with associated properties, assets, inspection information and administrative review activities.

The conceptual data model covers:

- Religious institutions and their associated information.
- Institution-linked property records.
- Property-related asset records.
- Inspection observations and supporting evidence.
- Possible-change observations and administrative review.
- Authorized user roles and institutional assignments.

The database architecture is designed to demonstrate organized institutional information management within a controlled prototype.

**Important:** This document describes logical relationships and responsibilities. It does not disclose the exact production database schema, SQL definitions, private policies or internal configuration.

## 2. Conceptual Data Model

The central relationship is between an institution, its associated properties and the assets linked to those properties.

### 2.1 High-Level Relationship Diagram

```text
                 Religious Institution
                          |
                Linked Property Records
                          |
                 Associated Assets


                 Religious Institution
                          |
                  Inspection Records
                          |
              Possible-Change Observations
                          |
                 Administrative Review


                 Authorized Stakeholder
                          |
               Approved Institution
                    Assignment
                          |
                 Permitted Records
```

This diagram illustrates the logical data relationships used in the BhuGrid prototype.

It is not a representation of exact database tables, foreign keys or implementation-specific constraints.

### 2.2 Core Data Entities

| Conceptual entity | Purpose |
|---|---|
| Institution | Represents an institution within the structured DEMO workflow |
| Property | Represents property information associated with an institution |
| Asset | Represents assets associated with institutional property records |
| Inspection | Records field observations and supporting inspection information |
| Possible-Change Observation | Represents a reported or suspected change requiring review |
| Administrative Review | Records review findings, decisions or follow-up information |
| User Profile / Role | Represents an authenticated user's permitted application role |
| Stakeholder Assignment | Associates an approved stakeholder with authorized institutions |

These are conceptual entity categories, not a disclosure or confirmation of exact internal table names.

## 3. Institution–Property–Asset Relationships

### 3.1 Institution Records

An institution is the primary organizational entity for structured institutional management.

Conceptually, institution information may include:

- Institution identification.
- Name and descriptive information.
- Geographic location.
- Administrative district.
- Verification or DEMO status.
- Associated property references.

### 3.2 Property Records

Property records represent information associated with an institution.

Conceptually, they may contain:

- Property identification.
- Associated institution.
- Descriptive property information.
- Available geographic references.
- Record status and supporting references.

A property record is linked to its relevant institution within the DEMO workflow.

### 3.3 Asset Records

Asset records represent institutional assets associated with available property information.

Conceptually, they may contain:

- Asset identification.
- Linked property or institution reference.
- Asset description.
- Available condition or observation information.
- Supporting inspection references.

**Relationship principle:** Institutions provide the organizational context, properties represent associated holdings, and assets provide more detailed information about items or resources linked to those holdings.

These relationships are demonstrated using fictional records. They do not establish legal ownership or property rights.

## 4. Inspection, Possible-Change and Review Records

BhuGrid includes inspection-oriented and administrative workflows to support structured monitoring.

### 4.1 Inspection Records

Inspection information may include:

- Associated institution or property.
- Inspector observations.
- Inspection date and available location information.
- Supporting photographic evidence references.
- Inspection status.

Inspectors submit observations through authorized workflows.

Inspection information is subsequently available for permitted administrative review.

### 4.2 Possible-Change Observations

A possible-change observation represents a reported or suspected condition requiring additional assessment.

Examples may include:

- Reported physical changes.
- Observed property or asset conditions.
- Inspection-related concerns.
- Follow-up requirements.

A possible-change observation is not a confirmed legal violation or verified encroachment.

The conceptual model allows these observations to be associated with inspection information and administrative review.

**Implementation boundary:** This section describes a logical record category and does not assert that a separate `possible_change` database table exists.

### 4.3 Administrative Review Records

Administrative review information conceptually includes:

- Related inspection or observation.
- Review findings.
- Administrative status.
- Human-reviewed decisions.
- Available follow-up or history information.

The application also supports advisory AI Administrative Review.

AI-generated observations must remain distinguishable from decisions made by authorized administrators.

Rule-based DEMO prioritization indicators are similarly advisory and do not establish official risk classifications.

## 5. Fictional DEMO Data

BhuGrid 1.0 uses **three fictional Supabase DEMO institutions** for controlled testing and demonstration.

These institutions support examples of:

- Institution records.
- Linked properties.
- Associated assets.
- Inspection submissions.
- Administrative review workflows.
- Role-specific access.

The DEMO records are not real government property records and must not be treated as verified institutional information.

### 5.1 Separation from Geographic Inventory

The GIS explorer also documents 239 provisional and unverified geographic features.

| Data category | Scope | Purpose |
|---|---|---|
| Provisional GIS inventory | 239 OSM-derived features across Cuttack, Puri and Khordha | Geographic exploration |
| Fictional institutional DEMO records | 3 separate Supabase institutions | Structured management and workflow testing |

The 239 geographic features are not automatically equivalent to legally verified institutional database records.

The fictional DEMO institutions are not included in the 239-feature inventory.

## 6. Stakeholder-to-Institution Assignment Model

BhuGrid's Institutional Stakeholder Portal supports three stakeholder categories:

1. Local Bodies.
2. Trustees / Institutional Management.
3. Government Agencies.

The documented prototype uses administrator-approved access and institution-specific assignments.

### 6.1 Conceptual Authorization Relationship

```text
          Authenticated Stakeholder
                     |
            Approved Membership
                     |
          Institution Assignment
                     |
             Assigned Institution
                     |
          +----------+----------+
          |                     |
    Linked Properties     Linked Assets
          |                     |
          +----------+----------+
                     |
            Authorized Viewing
```

### 6.2 Access-Control Principles

The conceptual assignment model requires:

- Authentication through Supabase Auth.
- Administrator-approved stakeholder accounts.
- Active and authorized memberships.
- Institution-specific assignments.
- Access only to permitted institution-linked records.
- Restrictions against cross-institution access.
- Separation from Inspector and Administrator permissions.

Relevant database operations use authorization controls, including Row-Level Security and protected database functions.

### 6.3 Verification Status

The project team reported successful backend authorization checks on **16 November 2026**.

The reported checks covered:

- Approved stakeholder membership.
- Assigned institution visibility.
- Institution-linked property and asset restrictions.
- Cross-institution access denial.
- Separation of stakeholder, Inspector and Administrator roles.

**Status: PASS within the documented controlled prototype scope.**

These results do not establish comprehensive independent security certification.

## 7. Data Provenance and Source Classification

Data provenance describes where information originates and how its reliability should be interpreted.

BhuGrid distinguishes geographic source information from fictional operational records.

| Data source | Information type | Verification boundary |
|---|---|---|
| OpenStreetMap / Overpass | Provisional religious institution geographic candidates | Community-sourced; requires authoritative verification |
| GeoJSON / Administrative Boundaries | Geographic boundary visualization | Source accuracy and licensing must be preserved |
| Supabase DEMO Records | Fictional institutions, properties and assets | Illustrative; not legally authoritative |
| Inspector Submissions | Prototype observations and supporting evidence | Requires authorized review and evidence validation |
| Groq AI | Advisory administrative analysis | Generated output; not authoritative evidence |
| Geoapify Places API | Nearby essential-service information | External and provisional; not institutional property data |

### 7.1 Provenance Principles

The data model should support:

- Clear identification of source categories.
- Separation of DEMO and externally sourced records.
- Appropriate geographic attribution.
- Traceability of inspection and review information.
- Verification status where available.
- Human review before treating observations as authoritative.

### 7.2 Geographic Source Attribution

The documented GIS inventory includes:

- **Cuttack:** 72 provisional OSM-derived features.
- **Puri:** 60 preliminary OSM-derived candidates.
- **Khordha:** 107 preliminary OSM-derived candidates.
- **Total:** 239 unverified GIS features.

OpenStreetMap data is subject to the Open Database License (ODbL). Attribution and applicable reuse obligations must be preserved.

For collection details, citations and validation limitations, refer to the project's dataset documentation.

## 8. Data Integrity and Verification Boundaries

Data integrity is essential for maintaining reliable relationships between institutions, properties, assets and inspection records.

### 8.1 Conceptual Integrity Requirements

The database design should support:

- Consistent institution–property relationships.
- Appropriate property–asset linkage.
- Valid references between inspection and review information.
- Role-aware access to protected records.
- Prevention of unauthorized cross-institution access.
- Clear distinction between fictional and verified information.
- Appropriate handling of incomplete or invalid submissions.

These are conceptual design requirements. This document does not claim that every possible integrity constraint has been independently audited.

### 8.2 Verification Boundaries

BhuGrid 1.0 does not establish:

- Official property ownership.
- Legally certified land boundaries.
- Government-verified institutional registration.
- Automatic encroachment detection.
- Legally conclusive possible-change findings.
- Production-grade database security certification.

Real-world institutional data integration would require authorized sources, verification procedures, governance approvals and additional security testing.

### 8.3 Privacy and Sensitive Information

Protected information may include institutional records, inspection evidence, user details and administrative observations.

Public documentation must not disclose:

- Real institutional property records without authorization.
- Private user account information.
- Authentication credentials or API secrets.
- Internal access-control policies.
- Unrestricted database exports.
- Sensitive inspection evidence or private operational records.

## 9. Current Status and Future Data Improvements

**Current status:** Conceptual documentation of an implemented Supabase-backed DEMO prototype.

The documented prototype includes fictional institution-linked records, authenticated workflows, inspection information and administrative review.

Future priorities include:

- Stronger provenance and verification metadata.
- Improved record-history traceability.
- Additional data-integrity validation.
- More comprehensive authorization testing.
- Approved institutional dataset onboarding.
- Formal backup, recovery and retention procedures.
- Independent security and privacy review.

These improvements should not be presented as completed production capabilities.

## 10. Related Documentation

- [Project Overview](../README.md)
- [Product Requirements Document](PRD.md)
- [System Architecture](ARCHITECTURE.md)
- [Datasets and Citations](../DATASETS_AND_CITATIONS.md)
- [Functional Web Application](../WEB_APP.md)

---

## Publication and Security Review

**Required Reviewer:** Shakti Saranjana Pradhan — Backend, Database and Security.

**Review Status:** Pending explicit approval.

Before publication, the reviewer must confirm that:

- Conceptual relationships accurately reflect the accepted prototype.
- No unverified database implementation details are presented as confirmed.
- Stakeholder assignment descriptions match the verified backend behavior.
- No sensitive schema details, private policies or credentials are disclosed.
- DEMO records and provisional geographic data remain clearly distinguished.

**Repository Notice — Documentation Only**

This repository provides public documentation for BhuGrid 1.0. It does not publish or license the private application source code, backend implementation, internal database configuration, credentials or unrestricted institutional records.

**Data Model Status:** Conceptual documentation of the controlled prototype, subject to backend and security approval before public release.
