# BhuGrid 1.0 — Features, Novelty, Roles, Security & Future Implementation

**Project:** BhuGrid 1.0  
**Scope:** Controlled Prototype / DEMO  
**Problem Statement:** PS-143

> **BhuGrid — The single secure vault for every sacred legacy across Odisha.**

> **Repository Notice — Documentation Only**
>
> This repository provides public documentation and project information for BhuGrid 1.0. It is not an open-source software repository and does not contain or license the private application source code, backend implementation, credentials or deployment configuration.

## 1. Project Vision

BhuGrid 1.0 is a **GIS-based Religious Institution and Asset Management Platform** designed to support the geographic visualization, structured management, monitoring and preservation of religious institutions and their associated properties and assets across Odisha.

The platform connects geographic institution information with linked property and asset records, inspection observations, supporting evidence and administrative review workflows. Its objective is to improve information organization, geographic accessibility, institutional coordination and accountable administrative follow-up.

BhuGrid 1.0 provides five user categories through three primary application workspaces:

1. **Institutional Stakeholder Portal**
   - Local Bodies
   - Trustees / Institutional Management
   - Government Agencies
2. **Inspector Workspace**
3. **Administrator Workspace**

The Institutional Stakeholder Portal replaces the earlier Public/Tourist-oriented interface as the primary stakeholder-facing direction of the platform.

**Prototype status:** The Institutional Stakeholder Portal has completed the documented frontend functional and backend authorization checks as of 16 November 2026. This does not establish production readiness or comprehensive security certification.

**Important limitation:** BhuGrid remains an educational and competition-oriented prototype. Geographic markers, community-sourced institution candidates and fictional DEMO records do not establish official institutional status, land ownership, legal boundaries, encroachment or government verification.

## 2. Current Functional Components

The following table distinguishes implemented and tested prototype functionality from capabilities requiring further validation.

| Component | Functionality | Status |
|---|---|---|
| Odisha GIS Explorer | Interactive geographic visualization, district exploration and institution markers | Implemented — prototype |
| Institution Discovery | Search, selection and geographic exploration of available institution records | Implemented — prototype |
| Institutional Stakeholder Portal | Authorized access for Local Bodies, Trustees / Institutional Management and Government Agencies | Implemented — prototype tests passed |
| Stakeholder Institution Assignments | Restricts stakeholder access to approved institution-linked records | Backend and functional checks passed |
| Linked Property Records | Institution-associated property information using fictional DEMO records | Implemented — DEMO |
| Asset Management | Linked illustrative institutional asset records | Implemented — DEMO |
| Inspector Workflow | Field observations, inspection submissions and supporting evidence | Implemented — prototype |
| Location Capture | GPS-assisted or manual location selection in inspection workflows | Implemented — prototype |
| Administrator Review | Review of inspection information, administrative actions and record history | Implemented — prototype |
| DEMO Prioritization | Deterministic rule-based review-priority indicators | Implemented — advisory |
| Record Output | Print-oriented record presentation and available export workflows | Implemented — prototype |
| Authentication | Supabase Auth with administrator-provisioned stakeholder accounts | Verified within prototype scope |
| Role-Based Authorization | Approved memberships and institution-specific record restrictions | Backend checks passed |
| Nearby Essentials Finder | Geoapify-based hospitals, restaurants and petrol-pump discovery | Integrated and functionally tested |
| Smart Trip Planner | Groq-powered AI-assisted visit-planning suggestions | Integrated and functionally tested |
| AI Administrative Review | Groq-powered advisory inspection analysis | Integrated and functionally tested |

**Status interpretation:** “Implemented” refers to functionality available in the documented prototype. “Tested” refers to the reported project-team verification, not independent certification or exhaustive testing.

The availability of specific features depends on the deployed version, authenticated permissions, available DEMO records and external service availability.

## 3. AI and External Service Integrations

### 3.1 AI-Assisted Administrative Review

**Technology:** Supabase Edge Functions and Groq API.

**Purpose:** Support authorized Administrators by generating preliminary analysis and advisory recommendations based on inspection-related information.

**Prototype capabilities:**

- AI-assisted summaries of inspection information.
- Preliminary risk-related observations.
- Suggested administrative follow-up actions.
- Advisory recommendations for human review.

**Verification status:** The Groq-powered Administrative Review feature has been reported as functionally tested in the deployed prototype.

**Decision boundary:** AI-generated analysis is advisory only. It cannot independently approve or reject inspection submissions, establish ownership, determine encroachment, certify land boundaries or replace an authorized Administrator's decision.

Before using real institutional information, additional evidence-provenance validation, data governance and operational assurance would be required.

### 3.2 Nearby Essentials Finder — Geoapify Integration

**Technology:** Geoapify Places API through a Supabase Edge Function.

**Purpose:** Help authorized institutional stakeholders understand essential services surrounding religious institution locations.

**Supported categories:**

- Hospitals
- Restaurants
- Petrol pumps

**Institutional relevance:**

- Understanding accessibility around institution locations.
- Identifying surrounding visitor-support infrastructure.
- Supporting local coordination and institutional planning.
- Providing geographical context for stakeholders.

**Integration status:** Geoapify was integrated following recurring availability problems with the earlier OpenStreetMap Overpass-based nearby-place retrieval approach. The supported categories and deployed functionality were reported as successfully tested.

**Data limitation:** Geoapify results are externally sourced and provisional. Facility details, distances, operating hours, service availability and accessibility require independent verification.

Geoapify is not the source of BhuGrid's institution inventory or legally authenticated property records.

### 3.3 Smart Trip Planner — AI-Assisted Visit Planning

**Technology:** Groq API integration.

**Purpose:** Generate AI-assisted visit-planning suggestions that help institutional stakeholders understand possible visitor itineraries involving religious institutions.

**Prototype capabilities:**

- Suggested institution-related visit itineraries.
- Potential visitor routes and attractions.
- AI-generated contextual planning information.
- Insights into visitor-oriented opportunities around institutions.

**Institutional relevance:** The feature supports stakeholder awareness of potential visitor movement, surrounding attractions and tourism-related planning opportunities.

**Verification status:** The deployed Groq-powered Smart Trip Planner was reported as functionally tested.

**Limitations:** Generated itineraries are suggestions, not official travel plans. Travel conditions, opening hours, route suitability and other factual details require independent verification.

The Smart Trip Planner is a supplementary stakeholder-support capability, not the primary purpose of BhuGrid.

### 3.4 Deterministic Review Prioritization

BhuGrid also demonstrates rule-based review-priority indicators.

These indicators are separate from the Groq-powered AI Administrative Review feature.

Priority scores support administrative triage within the DEMO workflow. They are not trained encroachment predictions, official risk classifications or legal findings.

## 4. User Roles and Security Model

BhuGrid uses authenticated and role-specific workflows to separate institutional stakeholder access from Inspector and Administrator responsibilities.

| Role | Prototype responsibility |
|---|---|
| Local Bodies | View assigned institutional information and permitted linked property and asset records |
| Trustees / Institutional Management | Access authorized records associated with assigned institutions |
| Government Agencies | View institution-specific information permitted by approved assignments |
| Inspector | Submit authorized field observations, location information and supporting evidence |
| Administrator | Perform authorized review activities and permitted administrative decisions |

### 4.1 Authentication and Authorization

The documented prototype uses:

- Supabase Authentication.
- Administrator-provisioned stakeholder accounts.
- Approved and active stakeholder membership requirements.
- Role-based and institution-specific authorization.
- Row-Level Security for relevant database tables.
- Authorization-controlled database functions for protected institution-linked information.
- Separation of stakeholder, Inspector and Administrator workspaces.

Public self-registration and anonymous sign-in are disabled in the reported stakeholder configuration.

### 4.2 Stakeholder Access Verification — 16 November 2026

The project team reported successful verification of the Institutional Stakeholder Portal.

**Frontend functional verification:**

- Stakeholder login interface — PASS.
- Three stakeholder categories — PASS.
- Administrator-controlled access — PASS.
- Assigned institution visibility — PASS.
- Cross-institution access restrictions — PASS.
- Property and asset permissions — PASS.
- Nearby Essentials stakeholder wording — PASS.
- Smart Trip Planner stakeholder wording — PASS.

**Result: 8/8 frontend functional checks passed.**

**Backend verification confirmed by the database/security team:**

- Supabase Authentication restrictions — PASS.
- Approved stakeholder membership and institution assignments — PASS.
- Role-based authorization checks — PASS.
- Authenticated access to protected records through authorization-controlled database functions — PASS.
- Cross-institution access restrictions — PASS.
- Separation of stakeholder access from existing Inspector and Administrator permissions — PASS.

These results establish successful verification within the documented prototype testing scope.

They do not represent an independent penetration test, exhaustive security assessment or production security certification.

### 4.3 Security and Privacy Limitations

Further work is required before production use, including:

- Independent security review and penetration testing.
- Broader negative-path and adversarial authorization testing.
- Secure onboarding and verification of real institutional records.
- Formal audit, backup, recovery and data-retention procedures.
- Review of evidence access and data provenance.
- Operational monitoring and access-revocation assurance.

Private credentials, internal policies, sensitive account information and implementation-specific security configurations are excluded from this public documentation repository.

## 5. Novelty and Integration Value

BhuGrid's innovation lies in its prototype-level integration of GIS visualization, institution-linked management records, inspection evidence, role-based access and human-controlled administrative review.

It does not claim patented technology or a globally unique invention.

### Key Integration Contributions

1. **GIS-Based Institutional Discovery:** Geographic visualization of provisional religious institution locations across selected Odisha districts.

2. **Institution–Property–Asset Linkage:** Structured relationships between fictional DEMO institutions and associated property and asset records.

3. **Institutional Stakeholder Access:** Approved, institution-specific access for Local Bodies, Trustees / Institutional Management and Government Agencies.

4. **Evidence-Oriented Inspection:** Digital observations and supporting evidence for structured administrative follow-up.

5. **Human-in-the-Loop Administrative Review:** Administrator-controlled review supported by rule-based prioritization and Groq-generated advisory analysis.

6. **Stakeholder-Support Geographic Services:** Geoapify Nearby Essentials and AI-assisted Smart Trip Planner functionality.

7. **Data Provenance Transparency:** Clear separation between provisional public GIS features, fictional DEMO records and future authoritative datasets.

8. **Integrated Project Communication:** A functional web application supported by a separate informational showcase website and public documentation repository.

An exploratory synthetic image-difference experiment exists in the development project. It is not evidence of a trained real-world encroachment detector or an operational satellite-based monitoring system.

## 6. Geographic Data and DEMO Scope

BhuGrid 1.0's documented geographic inventory covers three Odisha districts.

| Geographic dataset | Features | Verification status |
|---|---:|---|
| Cuttack | 72 | Provisional OSM-derived points |
| Puri | 60 | Preliminary OSM-derived candidates |
| Khordha | 107 | Preliminary OSM-derived candidates |
| **Total** | **239** | **Unverified GIS features** |

The prototype also uses **three separate fictional Supabase DEMO institutions** for controlled institutional record workflows.

These three DEMO institutions are not included as additional verified institutions in the 239-feature geographic inventory.

Their associated property and asset records are illustrative, synthetic records rather than authenticated ownership, cadastral or government survey data.

### Data Sources and Boundaries

- **OpenStreetMap / Overpass:** Documented source for geographic institution candidates.
- **Wikidata:** Supplementary institution and geographic information, where used.
- **GeoJSON / geoBoundaries:** Geographic boundary visualization and reference research.
- **Wikipedia:** Supplementary historical or cultural references, where used.
- **Geoapify Places API:** External nearby-facility information.
- **Supabase DEMO records:** Fictional institutional, property and asset information.

The presence of an institution candidate on the map does not establish official recognition, ownership, land boundaries or administrative verification.

Detailed dataset attribution, collection methods, licensing and limitations are documented in [DATASETS_AND_CITATIONS.md](DATASETS_AND_CITATIONS.md).

## 7. Team Responsibilities

| Team member | Primary contribution |
|---|---|
| Srusti Swarupa Mohapatra | Team leadership, GIS dataset research and preparation, AI integrations, external services |
| Pratikshya Muduli | React/GIS frontend, web application integration, testing, deployment |
| Shakti Saranjana Pradhan | Supabase database, authentication, authorization, record management and backend security verification |
| Smruti Rekha Behera | Informational showcase website, and visual presentation |

## 8. Prototype Workflows

### 8.1 Institutional Stakeholder Workflow

`Administrator-provisioned account → authenticated sign-in → authorized institution selection → permitted property and asset viewing → stakeholder-support features`

Stakeholders are limited to records associated with their approved institution assignments.

### 8.2 Inspector Workflow

`Authorized Inspector sign-in → institution/record selection → field observation → location capture → evidence submission`

Inspection records support administrative review and follow-up.

### 8.3 Administrator Workflow

`Authorized Administrator sign-in → inspection record review → priority assessment → optional AI advisory review → human administrative decision → review history`

Administrative decisions remain the responsibility of authorized human users.

### 8.4 Supporting Geographic and AI Workflows

- **Nearby Essentials:** Retrieve external nearby-facility information for institutional geographic context.
- **Smart Trip Planner:** Generate advisory visit-planning suggestions.
- **AI Administrative Review:** Generate preliminary inspection-related analysis for authorized Administrators.

All workflows operate within the controlled prototype and available data scope.

## 9. Future Implementation Roadmap

The following work represents proposed enhancements rather than completed BhuGrid 1.0 capabilities.

### 9.1 NOW — Prototype Consolidation

- Maintain the verified Institutional Stakeholder Portal.
- Address any remaining interface or accessibility issues.
- Improve error handling and external-service reliability.
- Review the 239 provisional geographic features for duplicates and classification accuracy.
- Maintain consistent documentation of feature status, data limitations and security boundaries.

### 9.2 NEXT — Validation and Institutional Readiness

- Establish authorized partnerships for verified institutional and property datasets.
- Strengthen data import, validation and provenance workflows.
- Expand security testing beyond the completed prototype authorization checks.
- Improve district-level GIS analytics and institutional reporting.
- Strengthen inspection evidence handling and administrative traceability.
- Develop more comprehensive audit, backup and recovery procedures.

### 9.3 LATER — Expanded Platform Capabilities

- Regional language support, including Odia.
- Offline-capable field inspection workflows.
- Enhanced institutional dashboards and reporting.
- Historical inspection and change-review tools.
- More advanced accessibility support.
- Approved integrations with relevant institutional information systems.

### 9.4 DEFERRED — Research-Dependent Capabilities

- Satellite-assisted geographic change screening.
- Human-reviewed potential boundary-change alerts.
- Advanced image comparison using suitable licensed datasets.
- Site-level 3D visualization or digital-twin research, subject to validated data and resources.

These capabilities require further research, permissions, reliable datasets and evaluation.

### 9.5 NOT PLANNED AS AUTOMATED AUTHORITY

BhuGrid does not propose replacing authorized legal or administrative processes with automatic AI decisions.

The prototype does not provide:

- Automated legal ownership certification.
- Autonomous encroachment determination.
- Automatic approval or rejection of administrative cases.
- Unverified changes to official government land records.

## 10. Current Limitations

BhuGrid 1.0 is a controlled educational and competition-oriented prototype.

- The 239 geographic features are provisional and unverified.
- The three Supabase DEMO institutions and their linked property and asset records are fictional.
- Public geographic information may be incomplete, outdated or inaccurate.
- No official cadastral boundaries or legally authenticated ownership database are integrated.
- Stakeholder authorization has passed the documented prototype tests, but comprehensive independent security validation has not been performed.
- Nearby Essentials depends on externally sourced Geoapify information.
- Smart Trip Planner generates suggestions that require independent factual verification.
- Groq-powered Administrative Review provides advisory output only.
- Deterministic prioritization indicators are not official risk assessments.
- No trained real-world encroachment detection or operational satellite monitoring is claimed.
- No government endorsement, statewide institutional deployment or production certification is claimed.
- Real-world deployment requires authoritative data, institutional approvals, governance and further security and operational validation.

## 11. Related Public Documentation

### Core Documentation

- [Project Overview — README](README.md)
- [Datasets, Provenance, Licences and Citations](DATASETS_AND_CITATIONS.md)
- [Functional Web Application](WEB_APP.md)
- [Project Showcase Website](WEBSITE.md)

### Detailed Documentation

Additional product, architecture, database, security, workflow, testing, roadmap and development-history documents are planned under the `docs/` directory.

### Project Links

- **Functional Web Application:** https://bhugrid-web-app.onrender.com/
- **Project Showcase Website:** https://bhugrid-website.onrender.com/
- **Documentation Repository:** https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Documentation and source-code notice:** This repository is intended for public project documentation. The original BhuGrid application source code, private backend implementation, credentials and deployment configuration are not released or licensed through this repository.
