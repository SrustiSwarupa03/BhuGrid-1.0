# BhuGrid 1.0 — System Architecture

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**System Type:** GIS-based Religious Institution and Asset Management Platform  
**Development Stage:** Functional Prototype / Controlled DEMO  
---

## 1. Architecture Overview

BhuGrid 1.0 follows a web-based architecture integrating geographic visualization, structured institutional records, authenticated workflows and AI-assisted services.

The system combines a React and Vite frontend with MapLibre GL for GIS visualization, Supabase for backend services, Groq for AI assistance, Geoapify for nearby-place discovery and Render for web application hosting.

The architecture supports three principal workspaces:

1. **Institutional Stakeholder Portal:** Authorized access to assigned institutions and linked records.
2. **Inspector Interface:** Field observations, location capture and inspection evidence submission.
3. **Administrator Interface:** Institutional monitoring, inspection review and administrative assessment.

The system separates provisional geographic information from fictional institutional DEMO records.

This document presents a conceptual architecture without disclosing private source code, credentials, internal security policies or deployment configurations.

## 2. High-Level Architecture Diagram

The following diagram illustrates the main components of BhuGrid 1.0.

```text
                    BHUGRID 1.0
                         |
                  Authorized Users
                         |
              React + TypeScript + Vite
                  (Render Hosting)
                         |
        +----------------+----------------+
        |                |                |
   MapLibre GL       Supabase         Application
    GIS Map          Services         Interfaces
        |                |                |
   OSM Geographic        |          Stakeholder Portal
   Data + GeoJSON        |          Inspector Interface
   Boundaries            |          Administrator Interface
                         |
             +-----------+-----------+
             |           |           |
        Supabase     PostgreSQL    Supabase
          Auth        Database   Edge Functions
             |           |           |
         Role and    Fictional   +---+---+
        Institution  DEMO Records |       |
       Authorization             Groq   Geoapify
                                  AI    Places API
```

**Architecture components:**

- **Render:** Hosts the deployed frontend.
- **React, TypeScript and Vite:** Provide the application interface and build environment.
- **MapLibre GL:** Visualizes geographic institution locations.
- **Supabase Auth:** Manages authenticated user sessions.
- **Supabase PostgreSQL:** Stores structured DEMO institutional and workflow records.
- **Supabase Edge Functions:** Support external AI and nearby-place integrations.
- **Groq:** Provides advisory AI functionality.
- **Geoapify:** Retrieves nearby essential facilities.
- **OpenStreetMap and GeoJSON:** Supply provisional geographic data and administrative boundary information.

The diagram is conceptual. It does not represent every internal request, database relationship or security control.

## 3. Frontend Architecture

### 3.1 React and Vite

The frontend uses:

- **React:** Component-based application interfaces.
- **TypeScript:** Typed application development.
- **Vite:** Development and production build tooling.

The frontend provides the GIS explorer, institutional information views, stakeholder portal, inspection interface and administrative workspace.

### 3.2 MapLibre GL

MapLibre GL provides interactive geographic visualization, including:

- Religious institution location markers.
- Geographic navigation and exploration.
- District-level geographic context.
- Institution selection and information display.

The map uses provisional geographic records and available administrative boundary data.

Mapped locations do not establish legal property ownership, official institutional recognition or verified boundaries.

## 4. Backend and Database Architecture

### 4.1 Supabase PostgreSQL

Supabase provides PostgreSQL-backed structured data services.

The conceptual database includes information relating to:

- Institutions.
- Institution-linked properties.
- Associated assets.
- Inspection observations and evidence.
- Administrative review records.
- User roles and institution assignments.

The controlled prototype contains **three fictional Supabase DEMO institutions** with illustrative linked records.

These records are not official government or institutional property records.

### 4.2 Supabase Authentication

Supabase Auth provides authenticated access to protected application workflows.

The documented stakeholder configuration uses administrator-provisioned accounts rather than public self-registration.

Authentication identifies users, while authorization controls determine their permitted institutional records and operations.

### 4.3 Supabase Edge Functions

Supabase Edge Functions support server-side application integrations.

Their documented responsibilities include:

- Groq-powered AI Administrative Review.
- Groq-powered Smart Trip Planner.
- Geoapify-powered Nearby Essentials Finder.
- Server-side handling of external service credentials.

Private function implementations, API credentials and deployment secrets are excluded from this public documentation.

## 5. AI and External Service Integrations

### 5.1 Groq — AI Administrative Review

Groq supports preliminary AI-assisted administrative observations and recommendations.

**Conceptual workflow:**

1. An authorized administrator accesses an inspection-related review.
2. Relevant permitted information is processed through the application integration.
3. A Supabase Edge Function communicates with Groq.
4. Advisory AI output is returned for human assessment.

AI-generated results do not independently approve, reject or legally certify institutional records.

### 5.2 Groq — Smart Trip Planner

The Smart Trip Planner generates AI-assisted institution-related visit suggestions.

It supports institutional stakeholders in understanding potential visitor itineraries, nearby attractions and visitor-oriented planning opportunities.

Generated itineraries are advisory and require independent verification.

### 5.3 Geoapify — Nearby Essentials Finder

The Nearby Essentials Finder uses the **Geoapify Places API** to retrieve nearby:

- Hospitals.
- Restaurants.
- Petrol pumps.

The integration provides supplementary geographic context around religious institution locations.

Geoapify replaced the earlier Overpass-based nearby-service retrieval approach following recurring API failures.

**Important:** OpenStreetMap-derived data remains part of the provisional institution GIS inventory. Geoapify is used for nearby-service discovery, not official institutional property verification.

## 6. GIS Dataset Flow

BhuGrid maintains a clear separation between provisional geographic reference data and structured fictional DEMO institutional records.

### 6.1 Provisional Geographic Inventory

| District | Geographic features | Status |
|---|---:|---|
| Cuttack | 72 | Provisional OSM-derived points |
| Puri | 60 | Preliminary OSM-derived candidates |
| Khordha | 107 | Preliminary OSM-derived candidates |
| **Total** | **239** | **Unverified GIS features** |

**Conceptual GIS data flow:**

```text
OpenStreetMap / Overpass
          |
Collection and Filtering
          |
Provisional GIS Records
          |
GeoJSON / Geographic Data
          |
MapLibre GIS Explorer
          |
Interactive Geographic Visualization

Administrative Boundary Data
          |
MapLibre GIS Explorer
```

The 239 geographic features are provisional candidates, not an officially verified register of religious institutions or legally recognized properties.

### 6.2 Fictional DEMO Institutional Records

The prototype separately maintains three fictional Supabase DEMO institutions.

**Conceptual record relationships:**

```text
Fictional DEMO Institution
          |
    Linked Properties
          |
    Associated Assets

Fictional DEMO Institution
          |
    Inspection Records
          |
    Administrative Review
```

These records demonstrate institution–property–asset relationships and inspection workflows.

They are illustrative and must not be interpreted as legal ownership evidence.

### 6.3 Data Separation Principle

| Geographic inventory | Institutional DEMO records |
|---|---|
| OpenStreetMap-derived candidates | Fictional Supabase records |
| 239 provisional GIS features | 3 fictional institutions |
| Geographic discovery | Management workflow demonstration |
| Requires authoritative validation | Illustrative, not legally authoritative |
| No automatic verified property linkage | Controlled property and asset relationships |

No legally authoritative relationship between provisional OSM map features and official property records is claimed.

## 7. Role-Based Access Architecture

BhuGrid uses authenticated, role-aware access to protected institutional workflows.

| Role | Conceptual access |
|---|---|
| Local Bodies | Assigned institutions and permitted linked records |
| Trustees / Institutional Management | Authorized institution-specific property and asset information |
| Government Agencies | Assigned institutional information for approved administrative purposes |
| Inspector | Permitted inspection and evidence-submission workflows |
| Administrator | Authorized review, monitoring and administrative operations |

### 7.1 Authorization Principles

The documented prototype incorporates:

- Supabase authentication.
- Administrator-approved stakeholder accounts.
- Approved stakeholder memberships.
- Institution-specific assignments.
- Row-Level Security for relevant database records.
- Authorization-controlled database operations.
- Cross-institution access restrictions.
- Separation of stakeholder, Inspector and Administrator permissions.

### 7.2 Verification Status

On 16 November 2026, the project team reported:

- **Frontend stakeholder verification:** 8/8 checks PASS.
- **Backend authorization verification:** PASS.
- **Assigned institution restrictions:** PASS.
- **Cross-institution access denial:** PASS.
- **Inspector/Administrator separation:** PASS.

These results apply to controlled prototype testing.

They do not establish independent penetration-test certification or comprehensive production security assurance.

## 8. Deployment Architecture

The functional BhuGrid web application is deployed through **Render**.

**Conceptual deployment flow:**

```text
                  Web Browser
                       |
              Render-Hosted Frontend
                       |
                Supabase Services
                       |
          +------------+------------+
          |            |            |
     Supabase Auth  PostgreSQL   Edge Functions
                       |            |
                  DEMO Records   +--+--+
                                 |     |
                               Groq  Geoapify
                                AI   Places API
```

Render hosts the frontend, while Supabase provides managed authentication, database and server-side integration capabilities.

Groq and Geoapify are accessed through the documented backend integrations.

Deployment availability depends on the hosting environment and external service availability.

No continuous uptime guarantee or production service-level commitment is claimed.

## 9. Architecture Constraints and Limitations

The current architecture supports controlled prototype demonstration.

Key limitations include:

- Provisional and unverified geographic datasets.
- Fictional institutional property and asset records.
- Dependence on external AI and nearby-place services.
- Prototype-scope authorization verification.
- No official cadastral or government land-record integration.
- No validated automatic encroachment detection.
- No independent production security certification.
- No confirmed statewide operational deployment.

Future deployment using real institutional information would require authorized datasets, stronger security assessment, privacy governance, operational monitoring and institutional approval.

## 10. Related Documentation

- [Project Overview](../README.md)
- [Product Requirements Document](PRD.md)
- [Features and Future Implementation](../FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets and Citations](../DATASETS_AND_CITATIONS.md)
- [Functional Web Application](../WEB_APP.md)

---

**Repository Notice — Documentation Only**

This public repository documents the BhuGrid 1.0 prototype. It does not publish or license the original application source code, private backend implementation, internal database policies, API credentials or deployment configuration.

**Architecture Status:** Implemented prototype components and reported functional integrations are documented conceptually. Production architecture and independent security validation remain outside the completed BhuGrid 1.0 scope.
