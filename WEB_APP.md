# BhuGrid 1.0 — Functional Web Application

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Status:** Functional Development Prototype / Controlled DEMO  

## 1. Live Web Application

**Access the BhuGrid 1.0 Web Application:**

https://bhugrid-web-app.onrender.com/

BhuGrid 1.0 is a functional GIS-based Religious Institution and Asset Management Platform developed to demonstrate the geographic visualization, organization and monitoring of religious institutions, linked properties and assets across Odisha.

The deployed application provides interactive GIS exploration, institutional record management, inspection workflows, administrative review and supplementary AI-assisted features.

**Access Notice:** BhuGrid 1.0 is a development prototype. Restricted institutional interfaces require administrator-authorized accounts. Public access to the application URL does not grant unrestricted access to protected institutional records.

## 2. GIS and Institutional Records

The web application provides the following GIS and record-management capabilities:

- **Interactive Odisha GIS Map:** Geographic visualization of religious institution locations and district-level exploration.
- **Institution Discovery:** Search and selection of available institution records with geographic information.
- **Institutional Information:** Display of available institution details and geographic context.
- **Linked Property Records:** Institution-associated property information using fictional DEMO records.
- **Asset Management:** Viewing and organization of illustrative assets linked to DEMO institutions.
- **Location Capture:** GPS-assisted or manual location selection for supported inspection workflows.
- **Record Output:** Print-oriented presentation of available prototype records.

The documented geographic inventory contains **239 provisional and unverified GIS features** across Cuttack (72), Puri (60) and Khordha (107).

The application also maintains **three separate fictional Supabase DEMO institutions** with illustrative linked property and asset records.

These DEMO records are distinct from the public geographic inventory and do not represent legally verified institutional properties.

## 3. Role-Specific Application Workflows

BhuGrid provides three principal role-specific interfaces.

### 3.1 Administrator Interface

The Administrator interface supports:

- Authorized institutional and inspection record review.
- Administrative assessment and permitted decision workflows.
- Review history and follow-up records.
- Rule-based DEMO prioritization.
- Optional AI-assisted administrative review.

Administrative decisions remain under authorized human control.

### 3.2 Inspector Interface

The Inspector interface supports authorized field-oriented activities, including:

- Institution-related inspection observations.
- GPS-assisted or manually selected location information.
- Supporting photographic evidence submission.
- Inspection records for subsequent administrative review.

### 3.3 Institutional Stakeholder Portal

The Institutional Stakeholder Portal serves three stakeholder categories:

1. Government Agencies.
2. Trustees / Institutional Management.
3. Local Bodies.

The portal provides authorized access to assigned institutions and their permitted linked property and asset records.

## 4. AI and External Service Features

### 4.1 AI Administrative Review

**Integration:** Groq API through Supabase Edge Functions.

The application generates preliminary AI-assisted summaries, observations and recommended follow-up actions from available inspection-related information.

**Status:** Integrated and functionally tested in the prototype.

**Limitation:** AI-generated outputs are advisory only. They do not establish legal ownership, detect encroachment conclusively or replace authorized administrative decisions.

### 4.2 Nearby Essentials Finder

**Integration:** Geoapify Places API through Supabase Edge Functions.

The feature retrieves nearby essential services around religious institution locations, including:

- Hospitals.
- Restaurants.
- Petrol pumps.

It helps institutional stakeholders understand surrounding facilities, accessibility and visitor-support infrastructure.

**Status:** Geoapify integration implemented and functionally tested.

Geoapify replaced the earlier Overpass-based nearby-service retrieval approach following recurring API failures. OpenStreetMap remains a documented source for provisional institution geographic records.

**Limitation:** Nearby information is externally sourced and provisional. Facility details, distances, operating hours and availability require independent verification.

### 4.3 Smart Trip Planner

**Integration:** Groq API.

The Smart Trip Planner generates AI-assisted visit-planning suggestions involving religious institutions, nearby attractions and potential visitor itineraries.

The feature supports institutional stakeholders in understanding visitor-oriented planning opportunities and geographic context.

**Status:** Integrated and functionally tested in the prototype.

**Limitation:** Suggested itineraries are advisory. Routes, opening hours, accessibility and travel conditions require independent verification.

The Smart Trip Planner is a supplementary stakeholder-support feature, not the primary purpose of BhuGrid.

## 5. Authentication and Access Control

The web application uses **Supabase Authentication** and role-specific authorization mechanisms.

The documented prototype includes:

- Administrator-provisioned user accounts.
- Approved stakeholder memberships and institution assignments.
- Institution-specific access restrictions.
- Supabase Row-Level Security for relevant database records.
- Authorization-controlled database functions for protected information.
- Separate stakeholder, Inspector and Administrator permissions.

Public self-registration and anonymous sign-ins are disabled in the documented stakeholder configuration.

**Verification Status:** The stakeholder access model passed the reported frontend and backend prototype checks on 16 November 2026.

Comprehensive independent security testing and production certification remain outside the completed prototype scope.

## 6. Technology Stack

| Component | Technology |
|---|---|
| Frontend | React, TypeScript, Vite |
| GIS Visualization | MapLibre GL |
| Geographic Data | GeoJSON, OpenStreetMap-derived records |
| Database | Supabase PostgreSQL |
| Authentication | Supabase Auth |
| Backend Integrations | Supabase Edge Functions |
| AI Services | Groq API |
| Nearby Places | Geoapify Places API |
| Deployment | Render |

The original application source code and private deployment configuration are maintained separately from this public documentation repository.

## 7. Current Status and Limitations

**Overall Status: Functional Prototype — PASS WITH LIMITATIONS**

BhuGrid 1.0 demonstrates implemented GIS, institutional records, role-specific workflows and AI-assisted features.

The reported stakeholder portal and selected integration tests have passed within their documented scope.

However:

- The 239 geographic features are provisional and unverified.
- The three Supabase DEMO institutions and their linked records are fictional.
- No official cadastral or government-certified property database is integrated.
- AI Administrative Review and Smart Trip Planner outputs require human verification.
- Geoapify results depend on external data and API availability.
- Prototype authorization testing does not establish comprehensive production security.
- Automatic encroachment detection and legally authoritative boundary determination are not implemented.
- The application is not an officially deployed statewide government system.

Further authoritative data validation, institutional approvals, security assessment and operational testing would be required before production use.

## 8. Related Links and Documentation

**Functional Web Application:**  
https://bhugrid-web-app.onrender.com/

**Project Showcase Website:**  
https://bhugrid-website.onrender.com/

**Public Documentation Repository:**  
https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Related Documentation:**

- [Project Overview — README](README.md)
- [Features and Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets and Citations](DATASETS_AND_CITATIONS.md)

---

**Repository Notice — Documentation Only**

The BhuGrid-1.0 repository provides public project documentation and information about the deployed prototype. It is not an open-source software repository.

The original application source code, backend implementation, private database configuration and deployment credentials are not published or licensed through this repository.
