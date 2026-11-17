# BhuGrid 1.0 — Functional Web Application

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Release Status:** Controlled DEMO Prototype  
**Document Type:** Public Web Application Documentation

> **Repository Notice — Documentation Only**
>
> This repository provides public project documentation for BhuGrid 1.0. It is not an open-source software repository and does not contain or license the private application source code, backend implementation, credentials or deployment configuration.

---

## 1. Access and Project Links

**Functional GIS Web Application:**  
https://bhugrid-web-app.onrender.com/

**Project Showcase Website:**  
https://bhugrid-website.onrender.com/

**Public Documentation Repository:**  
https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Original Development Repository (Private):**  
https://github.com/SrustiSwarupa03/BhuGrid

The BhuGrid web application is the project's functional, interactive GIS-based prototype. It is separate from the informational project showcase website.

The web application demonstrates geographic institution discovery, linked property and asset records, authenticated institutional workflows, inspection submissions, administrative review and AI-assisted stakeholder-support features.

**Access requirements:**

- The web application's public entry point may be accessible without authentication.
- Restricted institutional workspaces require approved user accounts.
- Stakeholder accounts are provisioned through authorized administrative processes.
- Public self-registration and anonymous sign-ins are disabled in the documented stakeholder configuration.
- Role-specific functionality depends on the authenticated user's permissions and assigned institutions.

The deployed application is a development prototype. Public availability does not imply production readiness, continuous uptime or official government deployment.

---

## 2. Application Purpose

BhuGrid 1.0 is a **GIS-based Religious Institution and Asset Management Platform** designed to support geographic visualization, structured management, monitoring and preservation of religious institutions and their associated properties and assets across Odisha.

The platform connects geographic information with institution-linked records, digital inspections, supporting evidence and administrative review.

### 2.1 Problem Context — PS-143

Religious institution information, property records and asset-management activities may be distributed across separate systems or administrative processes.

This creates challenges involving:

- Geographic discovery and institutional record organization.
- Linking institutions with associated properties and assets.
- Inspection documentation and evidence management.
- Administrative monitoring and review.
- Coordination among authorized institutional stakeholders.

BhuGrid demonstrates how these activities can be organized through a centralized GIS-based application.

### 2.2 Primary User Workspaces

The prototype supports three principal application workspaces.

**A. Institutional Stakeholder Portal**

Designed for:

1. Local Bodies.
2. Trustees / Institutional Management.
3. Government Agencies.

Stakeholders access institution-linked information according to administrator-approved memberships and institution assignments.

**B. Inspector Workspace**

Supports authorized field inspection activities, observations, location capture and evidence submission.

**C. Administrator Workspace**

Supports administrative record review, inspection assessment, human-controlled decisions and available review-history functions.

### 2.3 Institutional Stakeholder Portal Status

The former Public/Tourist-oriented interface has been repositioned as the **Institutional Stakeholder Portal**.

As of 16 November 2026, the project team reported completion of the documented stakeholder portal functional and backend authorization verification.

The verification included:

- Stakeholder login interface.
- Three stakeholder categories.
- Administrator-controlled access.
- Assigned institution visibility.
- Cross-institution restrictions.
- Linked property and asset permissions.
- Updated stakeholder-oriented Nearby Essentials descriptions.
- Updated stakeholder-oriented Smart Trip Planner descriptions.

**Frontend verification: 8/8 checks passed.**

The backend team also confirmed approved memberships, institution assignments, authenticated authorization-controlled data retrieval and cross-institution access restrictions.

These results apply to the controlled prototype testing scope. They do not establish comprehensive production security certification.

---

## 3. Main Application Capabilities

| Component | Functionality | Prototype status |
|---|---|---|
| GIS Map Explorer | Interactive geographic exploration of Odisha and institution locations | Implemented |
| District Exploration | District-level map interaction and geographic discovery | Implemented |
| Institution Discovery | Search and selection of available institution records | Implemented |
| Institutional Information | Geographic and descriptive institution information | Implemented |
| Linked Property Records | Institution-associated fictional DEMO property information | Implemented — DEMO |
| Asset Information | Illustrative linked institutional asset records | Implemented — DEMO |
| Institutional Stakeholder Portal | Authorized stakeholder access for three institutional categories | Functionally verified |
| Institution-Specific Access | Approved assignments and restrictions on linked records | Backend checks passed |
| Inspector Workflows | Inspection observations and evidence submissions | Implemented |
| Location Capture | GPS-assisted or manual location selection | Implemented |
| Administrative Review | Inspection review, permitted actions and record history | Implemented |
| DEMO Prioritization | Deterministic rule-based review-priority indicators | Implemented — advisory |
| Record Output | Print-oriented presentation and available export workflows | Implemented |
| AI Administrative Review | Groq-powered advisory inspection analysis | Integrated and tested |
| Nearby Essentials Finder | Geoapify-powered nearby hospital, restaurant and petrol-pump discovery | Integrated and tested |
| Smart Trip Planner | Groq-powered AI-assisted visit-planning suggestions | Integrated and tested |

**Status clarification:** Implemented and tested features are part of the documented prototype. Their operation may depend on the deployed version, approved account permissions, available DEMO records and external API availability.

The application does not claim automated legal decision-making or official property verification.

---

## 4. Geographic Data Scope

BhuGrid 1.0's documented geographic inventory covers three Odisha districts.

| District | Geographic features | Data status |
|---|---:|---|
| Cuttack | 72 | Provisional OpenStreetMap-derived points |
| Puri | 60 | Preliminary OpenStreetMap-derived candidates |
| Khordha | 107 | Preliminary OpenStreetMap-derived candidates |
| **Total** | **239** | **Provisional and unverified GIS features** |

The prototype also maintains **three separate fictional Supabase DEMO institutions** for controlled institutional management workflows.

These DEMO institutions are separate from the 239 geographic candidates.

### 4.1 Geographic Sources

The documented geographic information ecosystem includes:

- **OpenStreetMap / Overpass:** Provisional geographic institution discovery.
- **GeoJSON / geoBoundaries:** Administrative geographic boundary visualization.
- **Wikidata:** Supplementary exploratory institution-related research.
- **Wikipedia:** Supplementary historical and cultural references, where actually used.
- **Geoapify Places API:** External nearby-facility discovery.

Wikidata and Wikipedia should not be interpreted as independently verified institutional registries.

### 4.2 Verification Boundaries

The geographic inventory is not an official religious institution register.

A mapped feature does not establish:

- Official institutional recognition.
- Property ownership.
- Legally verified land boundaries.
- Government registration.
- Heritage certification.
- Encroachment or land-use violations.

The fictional DEMO property and asset records are illustrative and do not constitute legal or administrative evidence.

For dataset details, see [Datasets, Provenance, Citations and Validation](DATASETS_AND_CITATIONS.md).

---

## 5. AI and External Service Integrations

### 5.1 AI-Assisted Administrative Review — Groq API

BhuGrid includes a Groq-powered AI Administrative Review feature for authorized administrators.

**Technology:**

- Supabase Edge Functions.
- Groq API.

**Purpose:**

Generate preliminary analysis and advisory recommendations from inspection-related information to support human administrative review.

**Prototype capabilities:**

- Inspection-related summaries.
- Preliminary observations.
- Risk-related advisory analysis.
- Suggested administrative follow-up actions.

**Verification status:** The feature was reported as functionally tested in the deployed BhuGrid prototype.

**Important limitations:**

- AI-generated results are advisory only.
- Administrators retain responsibility for decisions.
- The AI does not independently approve or reject records.
- The AI does not certify ownership, property boundaries or encroachment.
- Real-world deployment would require stronger evidence-provenance controls and additional validation.

### 5.2 Nearby Essentials Finder — Geoapify

**External service:** Geoapify Places API.  
**Integration:** Supabase Edge Function.

The Nearby Essentials Finder provides geographic context around religious institution locations.

**Tested categories:**

- Hospitals.
- Restaurants.
- Petrol pumps.

**Institutional stakeholder purpose:**

- Understanding nearby essential facilities.
- Supporting awareness of local accessibility.
- Providing context for visitor-support infrastructure.
- Assisting institutional planning and coordination.

**Integration history:**

An earlier implementation used OpenStreetMap Overpass-based nearby-place retrieval.

Recurring API failures affected that workflow.

Geoapify was integrated as the alternative nearby-place retrieval service, and the team reported successful deployed functionality testing on 9 November 2026.

**Limitations:**

Geoapify information is externally sourced and provisional. Facility names, distances, operating hours and availability require independent verification.

Geoapify is not the authoritative source of the BhuGrid religious institution inventory or property records.

### 5.3 Smart Trip Planner — Groq API

The Smart Trip Planner uses Groq-powered AI to generate suggested institution-related visit plans.

**Purpose:**

Help institutional stakeholders understand possible visitor itineraries, surrounding attractions and potential visitor-oriented planning opportunities.

**Prototype capabilities:**

- Suggested visit itineraries.
- Institution-related attractions.
- Potential visitor routes and activities.
- AI-assisted planning information.

**Verification status:** The team reported successful functionality testing of the deployed Smart Trip Planner.

**Limitations:**

AI-generated itineraries are suggestions, not official travel recommendations.

Route suitability, opening hours, travel conditions, accessibility and other details must be independently verified.

The Smart Trip Planner is a supplementary stakeholder-support tool rather than the primary purpose of the platform.

### 5.4 Rule-Based Review Prioritization

BhuGrid also includes deterministic rule-based review-priority indicators.

These indicators are separate from the Groq-powered AI Administrative Review feature.

They support administrative triage within the DEMO workflow and are not trained real-world encroachment predictions or official risk classifications.

---

## 6. Technical Overview

The documented prototype uses the following technologies.

| Layer | Technology |
|---|---|
| Frontend | React 19, TypeScript |
| Development and build tooling | Vite |
| GIS visualization | MapLibre GL |
| Geographic data formats | GeoJSON |
| Backend services | Supabase |
| Database | PostgreSQL |
| Authentication | Supabase Auth |
| Access control | Row-Level Security and authorization-controlled database functions |
| Server-side integrations | Supabase Edge Functions |
| AI integrations | Groq API |
| Nearby-place retrieval | Geoapify Places API |
| Deployment | Render |
| Version control | Git and GitHub |

### 6.1 High-Level Application Architecture

The application follows a frontend-to-backend architecture:

1. The React-based interface provides GIS visualization and role-specific workspaces.
2. Supabase Auth manages authenticated access.
3. Supabase PostgreSQL stores the fictional DEMO institution, property, asset and workflow records.
4. Database authorization and Row-Level Security restrict protected information.
5. Supabase Edge Functions support selected server-side integrations.
6. Groq provides AI-generated advisory output.
7. Geoapify supplies nearby-place information.
8. Render hosts the deployed web application.

This is a conceptual overview, not a disclosure of private implementation files, credentials or internal security configurations.

---

## 7. Authentication and Access Control

BhuGrid uses Supabase Authentication and role-specific access controls.

### 7.1 Institutional Stakeholder Access

The Institutional Stakeholder Portal supports:

- Local Bodies.
- Trustees / Institutional Management.
- Government Agencies.

The documented configuration requires administrator-provisioned stakeholder accounts and approved, active memberships.

Stakeholders can access only the institutional records authorized through their assignments.

Public self-registration and anonymous sign-ins are disabled in the documented stakeholder configuration.

### 7.2 Institution-Specific Record Restrictions

The prototype uses:

- Authenticated stakeholder sessions.
- Approved stakeholder memberships.
- Institution-specific assignments.
- Row-Level Security for relevant tables.
- Authorization-controlled database functions for protected records.
- Restrictions against cross-institution record retrieval.

These controls were reported as successfully verified through the backend team's documented tests on 16 November 2026.

### 7.3 Inspector and Administrator Separation

Inspector and Administrator workspaces retain their separate approved-role permissions.

Inspectors perform authorized inspection-related activities.

Administrators perform permitted review and decision-making activities.

Institutional stakeholder access does not automatically grant Inspector or Administrator permissions.

### 7.4 Security Verification Status

**Documented verification results:**

- Frontend stakeholder functional checks: 8/8 PASS.
- Backend authentication and authorization checks: PASS.
- Approved stakeholder membership checks: PASS.
- Institution-assignment restrictions: PASS.
- Cross-institution access restrictions: PASS.
- Separation from Inspector and Administrator workspaces: PASS.

These are project-team verification results within the defined prototype scope.

A comprehensive independent security audit, penetration test and production-readiness certification have not been performed.

---

## 8. Safety, Privacy and Limitations

BhuGrid 1.0 is a controlled educational and competition-oriented prototype.

### 8.1 Data Limitations

- The 239 geographic features are provisional and unverified.
- Three Supabase DEMO institutions are fictional.
- Linked property and asset records are illustrative.
- Geographic markers are not legal ownership evidence.
- No official cadastral property database is integrated.
- Geographic and institutional records require authoritative verification before real-world use.

### 8.2 AI and External Data Limitations

- AI Administrative Review produces advisory output only.
- Smart Trip Planner suggestions require independent verification.
- Geoapify nearby-place information may be incomplete or outdated.
- External API availability and response quality are not guaranteed.
- Deterministic priority indicators are not official risk assessments.

### 8.3 Security and Operational Limitations

- Prototype authorization checks do not replace independent security auditing.
- Sensitive evidence and institutional information require appropriate governance.
- API keys and credentials must remain protected.
- Real institutional onboarding requires additional operational safeguards.
- Public deployment does not establish production readiness.

### 8.4 Explicit Non-Claims

BhuGrid 1.0 does not claim:

- Automatic encroachment detection.
- Legally authoritative boundary determination.
- Government-certified ownership verification.
- Trained real-world encroachment prediction.
- Statewide operational deployment.
- Official government endorsement.
- Comprehensive production security certification.

---

## 9. Future Application Improvements

The following improvements are proposed future work rather than completed BhuGrid 1.0 functionality.

### 9.1 Institutional Stakeholder Portal Enhancements

The initial stakeholder portal and its documented authorization tests have been completed within the prototype scope.

Future improvements include:

- Broader negative-path authorization testing.
- Independent security assessment.
- Improved account lifecycle and revocation procedures.
- Expanded stakeholder usability and accessibility.
- Controlled onboarding of authorized real institutional information.

### 9.2 GIS and Data Reliability

- Validate all 239 provisional geographic features.
- Review duplicate candidates and classification exceptions.
- Improve district-level geographic analytics.
- Strengthen data provenance and verification labels.
- Improve map responsiveness and accessibility.

### 9.3 Inspection and Asset Management

- Strengthen inspection evidence management.
- Improve historical record traceability.
- Expand administrative reporting.
- Improve field-oriented workflows.
- Explore offline-capable inspections.

### 9.4 Security and Governance

- Conduct independent penetration testing.
- Expand adversarial authorization tests.
- Strengthen audit, backup and recovery procedures.
- Define formal data-retention and access-revocation processes.
- Establish approved procedures for genuine institutional datasets.

### 9.5 AI and Geographic Assistance

- Improve evidence provenance for AI Administrative Review.
- Improve external-service error handling.
- Evaluate human-reviewed geographic change-screening methods.
- Explore satellite-assisted monitoring only with appropriate licensed data and validation.

No future feature should be presented as already implemented without corresponding verification evidence.

---

## 10. Related Public Documentation

- [Project Overview](README.md)
- [Features, Novelty, Roles, Security and Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets, Provenance, Citations and Validation](DATASETS_AND_CITATIONS.md)
- [Project Showcase Website](WEBSITE.md)

### Project Links

**Functional GIS Web Application:**  
https://bhugrid-web-app.onrender.com/

**Project Showcase Website:**  
https://bhugrid-website.onrender.com/

**Public Documentation Repository:**  
https://github.com/SrustiSwarupa03/BhuGrid-1.0

---

**Documentation and Source Code Notice:** This repository provides public information about BhuGrid 1.0. The original application source code, private backend implementation, credentials, restricted database information and deployment configuration are not published or licensed through this repository.

**Final Prototype Statement:** BhuGrid 1.0 demonstrates an integrated GIS-based religious institution and asset-management workflow with provisional geographic data, fictional DEMO records, authorized institutional access and advisory AI features. It is not an official property-verification authority or production-certified government system.
