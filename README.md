<p align="center">
  <img src="BhuGrid Logo.png"
       alt="BhuGrid Official Logo"
       width="130">
</p>
<p align="center">
  <img src="BhuGrid Word.png"
       alt="The single secure vault for every sacred legacy across Odisha."
       width="380">
</p>

# BhuGrid 1.0

**The single secure vault for every sacred legacy across Odisha.**

**A GIS-based Religious Institution and Asset Management Platform | PS-143**

BhuGrid 1.0 is an initial GIS-based prototype designed to support the geographic visualization, structured management, monitoring and preservation of religious institutions and their associated properties and assets across Odisha.

The platform connects geographic information with institution-linked property and asset records, digital inspections, administrative review and authorized stakeholder access.

> **Repository Notice — Documentation Only**
>
> This repository is the official public documentation and project-information repository for BhuGrid 1.0, an initial GIS-based religious institution and asset-management prototype.
>
> It is **not an open-source software repository** and does not contain the application's source code, backend implementation or private deployment configuration.
>
> The repository is intended to explain the project's objectives, architecture, features, datasets, development status and limitations, and to provide access to the deployed initial prototype and its accompanying showcase website.
>
> **Explore the initial web-application prototype:** https://bhugrid-web-app.onrender.com/
>
> **Visit the BhuGrid showcase website:** https://bhugrid-website.onrender.com/
>
> Public availability of this documentation does not grant a licence to use, reproduce, modify or redistribute the underlying BhuGrid application source code.

---

## 1. Problem Statement — PS-143

Religious institutions and their associated properties and assets require organized geographic records, reliable documentation, inspection mechanisms and administrative coordination.

Existing challenges may include:

- Fragmented institutional, property and asset information.
- Limited integration between geographic maps and administrative records.
- Difficulty tracking inspections, reported changes and review history.
- Challenges coordinating field-level verification and administrative decisions.
- Limited structured access for institutional stakeholders.

**BhuGrid's proposed solution** is a centralized GIS-based platform connecting institution locations with linked property and asset information, digital inspection records and role-specific administrative workflows.

BhuGrid 1.0 demonstrates this approach through a controlled prototype. It does not claim to replace official government land records or institutional verification processes.

## 2. Objectives

- Visualize religious institution locations through an interactive Odisha GIS map.
- Organize institution-linked property and asset records.
- Support structured field inspection and evidence documentation.
- Assist administrators with review, monitoring and record history.
- Provide authorized stakeholders with institution-specific information access.
- Demonstrate how geographic and administrative information can be integrated into one platform.

## 3. User Groups

### Administrators

Authorized Administrators manage relevant review workflows, inspect submitted information, maintain administrative records and make human-controlled decisions.

### Inspectors

Authorized Inspectors can participate in field inspection workflows, document observations and submit inspection information for administrative review.

### Institutional Stakeholders

The Institutional Stakeholder Portal supports three categories:

1. **Local Bodies** — Access to assigned institutional information relevant to local coordination.
2. **Trustees / Institutional Management** — Access to authorized institution-linked property and asset information.
3. **Government Agencies** — Access to assigned institutional records for authorized administrative purposes.

Stakeholder access is restricted to administrator-provisioned, approved accounts and assigned institutional records.

## 4. Major Prototype Features

### Interactive GIS Mapping

- Odisha-focused interactive GIS visualization.
- District-level geographic exploration.
- Institution location discovery and map markers.
- Geographic context for institution-related information.

### Institution, Property and Asset Management

- Three separate fictional DEMO institutions.
- Institution-linked illustrative property records.
- Associated DEMO asset records.
- Structured relationships between institutions, properties and assets.

### Institutional Stakeholder Portal

- Administrator-approved stakeholder accounts.
- Three stakeholder categories.
- Institution-specific authorized record access.
- Role-based restrictions and cross-institution access controls.

### Inspector Workflows

- Digital inspection submissions.
- Inspection observations and supporting evidence.
- Structured information for administrative follow-up.

### Administrator Review

- Inspection review workflows.
- Review history and administrative record management.
- Deterministic rule-based priority indicators.
- Human-controlled administrative decisions.

### AI-Assisted Administrative Review

- Groq API integration for AI-generated advisory analysis.
- Inspection-related review assistance.
- Recommendations intended to support human administrators.

AI-generated output does not constitute an official decision, legal finding or verified property determination.

### Nearby Essentials Finder

- Geoapify Places API integration.
- Nearby hospitals, restaurants and petrol pumps.
- Geographic context supporting institutional accessibility and surrounding visitor infrastructure assessment.

External facility information remains provisional and requires independent verification.

### Smart Trip Planner

- Groq-powered AI-assisted visit-planning suggestions.
- Potential itinerary and route-planning insights.
- Stakeholder-support context for understanding visitor-oriented opportunities around institutions.

Generated suggestions are advisory and must not be treated as verified travel information.

## 5. GIS Datasets and Verification

BhuGrid 1.0 maintains a clear distinction between publicly sourced geographic features and fictional institutional management records.

| Dataset | Prototype scope | Verification |
|---|---|---|
| Cuttack institution GIS features | 72 provisional points | Unverified |
| Puri institution GIS features | 60 preliminary candidates | Unverified |
| Khordha institution GIS features | 107 preliminary candidates | Unverified |
| **Total geographic features** | **239 provisional GIS features** | **Not department-certified** |
| Supabase DEMO institutions | 3 fictional institutions | Synthetic DEMO records |
| Property and asset records | Institution-linked illustrative records | Synthetic DEMO data |

The geographic inventory uses documented OpenStreetMap/Overpass sourcing. Wikidata and Wikipedia are documented supplementary reference sources where applicable. GeoJSON boundary data supports district-level visualization, with geoBoundaries referenced in geographic research documentation.

Geoapify provides external nearby-facility information.

**Important:** The 239 provisional geographic features are not equivalent to 239 officially verified religious institutions or legally authenticated institutional properties.

For further information, see [Datasets, Provenance, Licences and Citations](DATASETS_AND_CITATIONS.md).

## 6. Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React, TypeScript, Vite |
| GIS visualization | MapLibre GL JS, GeoJSON |
| Database | Supabase PostgreSQL |
| Authentication and access control | Supabase Auth, Row-Level Security, authorization-controlled database functions |
| Backend services | Supabase Edge Functions |
| AI-assisted features | Groq API |
| Nearby facilities | Geoapify Places API |
| Deployment | Render |
| Geographic data | OpenStreetMap/Overpass and documented supplementary sources |
| Version control | Git and GitHub |

This is a high-level architectural overview. Private implementation details and credentials are not included in this repository.

## 7. Security and Access Control

BhuGrid 1.0 uses authenticated, role-specific access for its institutional workflows.

The documented prototype verification completed on 16 November 2026 confirmed:

- Administrator-provisioned stakeholder access.
- Restrictions on public self-registration and anonymous sign-ins.
- Approved and active stakeholder membership requirements.
- Role-specific institution assignments.
- Authorization-controlled access to linked property and asset records.
- Cross-institution access restrictions.
- Separation of stakeholder, Inspector and Administrator permissions.

**Verification status:** Eight stakeholder portal frontend functional checks passed, and the team confirmed backend authorization and database security tests within the documented prototype scope.

These checks do not constitute a comprehensive security audit, penetration test or certification of production readiness.

## 8. Live Project Links

**Functional Web Application**

https://bhugrid-web-app.onrender.com/

The functional prototype demonstrates GIS mapping, linked records, authorized workflows and AI-assisted features. Restricted functionality requires approved accounts.

**Project Showcase Website**

https://bhugrid-website.onrender.com/

The informational website presents the project's objectives, problem, solution, interfaces, novelty, demonstrations and supporting information.

**Public Documentation Repository**

https://github.com/SrustiSwarupa03/BhuGrid-1.0

This repository is intended for project documentation and information only.

## 9. Project Documentation

### Core Documentation

- [Features, Novelty, User Roles and Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets, Provenance, Licences and Citations](DATASETS_AND_CITATIONS.md)
- [Functional Web Application](WEB_APP.md)
- [Project Showcase Website](WEBSITE.md)

### Detailed Documentation

- [Product Requirements Document](docs/PRD.md)
- [System Architecture](docs/ARCHITECTURE.md)
- [Data Model Overview](docs/DATABASE.md)
- [Security and Access Control](docs/SECURITY.md)
- [User Workflows](docs/UX_FLOWS.md)
- [Testing and Validation](docs/TESTING.md)
- [Future Implementation Roadmap](docs/ROADMAP.md)
- [Development History](docs/CHANGELOG.md)
- [Design System and Branding](docs/DESIGN_SYSTEM.md)


## 10. Project Status and Limitations

**Project status: BhuGrid 1.0 — Controlled DEMO Prototype**

The prototype demonstrates implemented GIS, institutional record management, inspection, administrative and stakeholder-support workflows.
- Geographic institution data remains provisional, while linked property and asset records are fictional DEMO data without official cadastral or legal verification.

- AI outputs are advisory, external service information requires verification, and automated encroachment detection, comprehensive security certification and statewide operational deployment are not established.
  
## 11. Team Contributions

| Team member | Primary contribution |
|---|---|
| **Srusti Swarupa Mohapatra** | Team leadership, geographic datasets, GIS data research and AI-assisted feature integration |
| **Pratikshya Muduli** | React/GIS frontend, web application integration, deployment and submission coordination |
| **Shakti Saranjana Pradhan** | Supabase backend, database design, authentication, access control and institutional workflows |
| **Smruti Rekha Behera** | Project showcase website, frontend presentation and supporting documentation |

## 12. Acknowledgments

The team acknowledges the open geographic data and technology ecosystems supporting prototype development, including OpenStreetMap contributors, documented geographic reference providers and the relevant software and service platforms.

Public data attribution, licences and usage limitations are detailed in [DATASETS_AND_CITATIONS.md](DATASETS_AND_CITATIONS.md).

## 13. Repository Scope and Source Code Availability

This repository contains public documentation for the BhuGrid 1.0 prototype.

It does **not** contain or provide an open-source licence for:

- The original application source code.
- Backend implementation files.
- Private database configurations.
- Credentials, access tokens or API secrets.
- Restricted operational or security information.

The underlying application source code remains separate from this documentation repository.

**BhuGrid 1.0 is a demonstration platform, not an official land-record authority, ownership-verification system or certified government deployment.**
