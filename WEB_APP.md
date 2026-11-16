# BhuGrid 1.0 — Functional Web Application

## 1. Access and Project Links

**Functional GIS Web Application:** https://bhugrid-web-app.onrender.com/

**Source Code (original project):** https://github.com/SrustiSwarupa03/BhuGrid/tree/web-app

*Access to the source repository depends on repository permissions.*

**Project Showcase Website:** https://bhugrid-website.onrender.com/

**Public Documentation Repository:** https://github.com/SrustiSwarupa03/BhuGrid-1.0

The BhuGrid web application is the project's **functional interactive GIS prototype**, separate from the informational project showcase website.

The application demonstrates geographic institution discovery, linked property and asset information, inspection-oriented workflows and administrative functionality.

Deployment availability may vary. No uptime guarantee or production-service commitment is implied.

## 2. Application Purpose

BhuGrid 1.0 is a GIS-based Religious Institution and Asset Management Platform designed to organize and visualize information about religious institutions and their associated properties and assets across Odisha.

The application connects geographic institution information with linked records and prototype workflows for inspection, evidence submission and administrative review.

The former Public/Tourist interface is being redesigned as the **Institutional Stakeholder Portal**, intended to serve:

1. Local Bodies
2. Trustees / Institutional Management
3. Government Agencies

The broader application design also includes Inspector and Administrator workflows.

Only administrator-authorized users should be permitted to sign in. Stakeholders should be able to access only their assigned institutions and the properties and assets linked to those institutions. Full implementation and end-to-end verification of stakeholder-specific access isolation must be confirmed before it is described as production-ready.

## 3. Main Application Capabilities

| Component | Description |
|---|---|
| GIS Map Explorer | Interactive geographic exploration of Odisha and available institution locations |
| District Exploration | Geographic discovery through district-level map interaction |
| Institution Discovery | Search and selection of available institution records |
| Institutional Information | Display of available institution details and geographic information |
| Linked Property Records | Presentation of institution-associated fictional DEMO property records |
| Asset Information | Display of illustrative institution-related asset information |
| Institutional Stakeholder Portal | Redesigned interface intended for Local Bodies, Trustees / Institutional Management and Government Agencies |
| Inspector Workflows | Field-oriented observation and evidence-submission interfaces |
| Location Capture | GPS-assisted or manual location selection in inspection-oriented workflows |
| Administrative Review | Interfaces for reviewing available institutional and inspection information |
| DEMO Prioritization | Prototype scoring and prioritization functionality, not an official determination |
| Record Printing | Print-oriented presentation of available prototype records |
| AI-Assisted Administrative Review | Preliminary AI-generated review drafts, subject to human verification |
| Nearby Essentials | Retrieval of nearby essential services through the Geoapify Places API integration |

The availability of individual functions depends on the deployed version, user permissions, integration status and available data.

## 4. Geographic Data Scope

The current geographic inventory covers three districts:

| District | Geographic features | Data status |
|---|---:|---|
| Cuttack | 72 | Provisional OpenStreetMap-derived points |
| Puri | 60 | Preliminary OpenStreetMap-derived candidates |
| Khordha | 107 | Preliminary OpenStreetMap-derived candidates |
| **Total** | **239** | **Unverified GIS features** |

In addition, the prototype contains **3 separate fictional Supabase DEMO institutions** for controlled testing and demonstration.

These DEMO institutions are separate from the 239 geographic candidates.

The geographic inventory is not an officially verified institutional register. Community-sourced locations may require further validation, classification and correction against authoritative sources.

A mapped location does not establish legal ownership, heritage status, property boundaries or administrative recognition.

## 5. AI and External Service Integrations

### 5.1 AI-Assisted Administrative Review

The application includes an AI-assisted administrative review workflow intended to support preliminary examination of available inspection-related information.

- **Backend:** Supabase Edge Function integration.
- **Function:** `admin-review-ai`.
- **AI service:** Groq integration, as recorded in the prototype implementation.
- **Intended user:** Approved administrator.
- **Input:** Accessible institution/property-related inspection information.
- **Output:** Preliminary summary, risk classification, observations and recommended actions.

**Important limitations:**

- AI-generated content is advisory.
- Human verification and authorized administrative judgment remain necessary.
- The AI workflow must not independently approve, reject or modify administrative decisions.
- Inspection evidence and property-record provenance require reliable server-side validation before production use.

### 5.2 Nearby Essentials Finder — Geoapify

The Nearby Essentials Finder retrieves nearby service locations around a selected geographic location.

- **External service:** Geoapify Places API.
- **Backend:** Supabase Edge Function integration.
- **Verified categories during integration:** Hospitals, restaurants and petrol pumps.
- **Purpose:** Provide supplementary nearby-service information.

Geoapify was integrated as an alternative to recurring OpenStreetMap Overpass API retrieval failures.

API credentials are maintained through secure server-side Supabase Edge Function secrets and must not be exposed in public documentation or frontend code.

**Important distinction:** Geoapify provides nearby-place information. It is not the source of BhuGrid's religious-institution inventory or official property records.

Retrieved places should not automatically be interpreted as verified businesses, currently operating establishments, accessible facilities or officially recommended services.

### 5.3 Earlier Smart Trip Planner

The earlier prototype included a Groq-powered Smart Trip Planner that generated suggested activities and durations for fictional DEMO starting institutions.

This functionality belongs to the previous tourist-oriented application direction. It should not be presented as the primary capability or purpose of the current institutional GIS platform.

Any continued availability or future integration of this feature should be described according to the current deployed application.

## 6. Technical Notes

The following technologies are documented as part of the original application implementation:

| Layer | Technology |
|---|---|
| Frontend | React 19 |
| Development and build tooling | Vite |
| GIS visualization | MapLibre GL |
| Backend and database services | Supabase |
| Authentication | Supabase Auth |
| Database | PostgreSQL-backed Supabase records |
| Server-side integrations | Supabase Edge Functions |
| AI integration | Groq |
| Nearby-place retrieval | Geoapify Places API |
| Deployment | Render |

The application uses a React-based frontend with Supabase services for authentication, database-related operations and server-side integrations.

Implementation details and deployed versions should be checked against the current source code before being treated as a complete technical inventory.

## 7. Authentication and Access Control

BhuGrid uses Supabase Auth for authentication and incorporates role-aware application workflows.

The intended access model is:

- Only administrator-authorized users can sign in.
- Local Bodies, Trustees / Institutional Management and Government Agencies should access only their assigned institutions.
- Inspectors should perform permitted inspection and evidence-submission activities.
- Administrators should access authorized institutional and administrative workflows.
- Sensitive operations must be protected by server-side authorization and database access policies.

Frontend role-based visibility alone is not sufficient to establish secure access.

Database RLS policies, server-side validation and stakeholder-specific data isolation require comprehensive testing before production deployment.

## 8. Safety, Privacy and Limitations

The functional application is a controlled educational and competition prototype.

- Records marked DEMO are fictional.
- The three fictional Supabase DEMO institutions are separate from the 239 unverified geographic candidates.
- Community-mapped geographic coordinates are not official verification.
- Property and asset information must not be interpreted as proof of legal ownership or government registration.
- AI administrative review drafts are advisory and require human verification.
- Nearby Essentials results are externally retrieved geographic information and may be incomplete or outdated.
- API keys, service credentials and sensitive implementation details must remain private.
- Inspection photographs, personal information and sensitive institutional records require appropriate access protection.
- Prototype security controls do not constitute a completed independent production security audit.
- No validated real-world encroachment detector or legally authoritative boundary-detection system is claimed.
- No government endorsement, official land-record certification or statewide operational deployment is claimed.

## 9. Future Application Improvements

The following areas represent future development and verification priorities rather than claims of completed production capabilities.

### 9.1 Institutional Stakeholder Portal

- Complete the transition from the former Public/Tourist interface.
- Implement and verify access for Local Bodies, Trustees / Institutional Management and Government Agencies.
- Enforce institution-specific access restrictions.
- Ensure stakeholders can view only their assigned institutions and linked properties and assets.

### 9.2 GIS and Data Reliability

- Validate geographic institution records against authoritative sources.
- Review duplicates, classification exceptions and geographic inconsistencies.
- Improve geographic data provenance and verification labels.
- Strengthen map usability and responsive behaviour.

### 9.3 Inspection and Asset Management

- Improve inspection evidence management and record traceability.
- Strengthen property and asset linkage.
- Introduce appropriate historical inspection records and administrative tracking.
- Improve field-oriented workflows and location capture.

### 9.4 Security and Governance

- Complete role-based access and RLS testing.
- Conduct independent security review and negative-path authorization testing.
- Strengthen server-side validation and audit trails.
- Establish suitable backup, recovery and data-retention procedures.
- Define authorized onboarding and verification procedures for real institutional records.

### 9.5 AI and Geographic Assistance

- Strengthen inspection-record provenance validation for AI-assisted review.
- Improve reliability and error handling of nearby-place retrieval.
- Explore explainable, human-reviewed administrative prioritization.
- Evaluate future GIS change-review capabilities using validated data and authorized evidence.

## 10. Related Public Documentation

- [Features, Novelty, Roles, Security & Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets and Citations](DATASETS_AND_CITATIONS.md)
- [Project Showcase Website](WEBSITE.md)

**Project links:**

- Functional GIS Web Application: https://bhugrid-web-app.onrender.com/
- Showcase Website: https://bhugrid-website.onrender.com/
- Public Documentation Repository: https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Documentation note:** The public documentation repository is intended for project documentation. It does not publish or license the private application source code, backend implementation, credentials, private database information or deployment configuration.
