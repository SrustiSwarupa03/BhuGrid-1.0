# BhuGrid 1.0 — Features, Novelty, Roles, Security & Future Implementation

**Project:** BhuGrid 1.0  
**Scope:** Controlled prototype / DEMO  
**Updated:** 16 November 2026

> **BhuGrid — A GIS-based Religious Institution and Asset Management Platform for Odisha.**

## 1. Project Vision

BhuGrid 1.0 is a GIS-based platform designed to organize, visualize and manage information related to religious institutions, their associated properties and assets across Odisha.

The platform connects geographic institution records with linked property and asset information, inspection observations, evidence records and administrative review workflows. It aims to support structured institutional information management, spatial exploration and transparent administrative follow-up.

The former Public/Tourist interface is being redesigned as an **Institutional Stakeholder Portal**, intended for authorized stakeholders, including:

1. Local Bodies
2. Trustees / Institutional Management
3. Government Agencies

The platform also incorporates Inspector and Administrator workflows to support field-level information collection, record review and authorized administrative activities.

**Important limitation:** BhuGrid is currently an educational and competition-oriented prototype. A mapped location, community-sourced institution candidate or fictional DEMO record does not establish official heritage status, property ownership, land boundaries, encroachment, legal rights or government verification.

## 2. Current Functional Components

| Component | Prototype capability / current scope |
|---|---|
| Odisha GIS Explorer | Interactive geographic visualization, district-level exploration and institution markers |
| Institution Discovery | Search and selection of available institution records with geographic information and verification labels |
| Institutional Stakeholder Portal | Redesigned interface intended for Local Bodies, Trustees / Institutional Management and Government Agencies |
| Linked Property Records | Display of institution-associated property information using controlled fictional DEMO records |
| Asset Management | Organization and presentation of illustrative institution-related asset information |
| Inspector Workflow | Field-oriented observation, location information and evidence-submission workflows |
| Location Capture | GPS-assisted or manual location selection in inspection-oriented workflows |
| Administrative Tools | Administrative record review and existing decision-oriented prototype workflows |
| DEMO Prioritization | Prototype scoring and prioritization interfaces; not official assessments |
| Record Output | Print-oriented record presentation for prototype information |
| Authentication and Access Control | Supabase authentication and implemented role-aware application/database permission mechanisms |
| Nearby Essentials | Geoapify Places API integration for retrieving nearby categories such as hospitals, restaurants and petrol pumps |
| AI-Assisted Review | Preliminary AI-generated administrative review drafts, subject to human verification |

**Access principle:** Only administrator-authorized users should be permitted to sign in. Stakeholders should be restricted to their assigned institutions and the properties and assets linked to those institutions.

The implementation and end-to-end verification of stakeholder-specific data isolation must be confirmed before claiming that this requirement has been fully validated.

The availability of individual functions depends on the deployed version, permissions, integration status and available data. BhuGrid is not yet a certified government records or property-management system.

## 3. AI and External Service Integrations

### 3.1 AI-Assisted Administrative Review

- **Backend:** Supabase Edge Function-based AI review workflow.
- **AI service:** Groq integration, as recorded in the prototype implementation.
- **Purpose:** Assist authorized administrative users by preparing preliminary summaries and review suggestions from available inspection-related information.
- **Intended output:** Summary, preliminary risk classification, observations, recommended actions and an explicit requirement for human review.
- **Decision boundary:** AI-generated content is advisory. It must not independently approve, reject, establish ownership, determine encroachment or replace an authorized administrative decision.

**Known limitation:** Inspection evidence and property-record provenance must be validated through reliable server-side checks before the workflow is considered suitable for real institutional records. AI-generated outputs require human verification.

### 3.2 Nearby Essentials Finder — Geoapify Integration

- **Backend:** Supabase Edge Function-based nearby-place retrieval workflow.
- **External service:** Geoapify Places API.
- **Purpose:** Retrieve nearby essential services around a selected geographic location.
- **Supported categories verified during integration:** Hospitals, restaurants and petrol pumps.
- **Configuration:** Geoapify API credentials are maintained through secure server-side Supabase Edge Function secrets.
- **Integration status:** Geoapify has been integrated as an alternative to recurring OpenStreetMap Overpass API failures, and the supported categories have been verified.

**Important distinction:** Geoapify is used for nearby-place retrieval. It is not the source of BhuGrid's religious-institution inventory or official property records.

Nearby-place results are external geographic information and should not be interpreted as verified operating status, service quality, accessibility or official institutional recommendations. API credentials must not be exposed in public documentation or frontend code.

### 3.3 Earlier Tourist-Oriented AI Features

The earlier prototype included a Smart Trip Planner and tourist-oriented discovery workflows. These belonged to the previous public/tourist-facing direction of the application.

They should not be presented as the primary purpose of the current BhuGrid 1.0 platform. Any retention, removal or future reuse of these features should be documented according to the approved application scope and deployed implementation.

## 4. User Roles and Security Model

BhuGrid follows an authorization-oriented model in which users should access only the institutional information relevant to their approved responsibilities.

| Role | Intended responsibilities |
|---|---|
| Local Bodies | Access assigned institutional information and associated property and asset records |
| Trustees / Institutional Management | Review and manage permitted information relating to their assigned institutions |
| Government Agencies | Access authorized institutional information for relevant administrative and governance purposes |
| Inspector | Submit authorized field observations, location information and supporting photographic evidence |
| Administrator | Manage authorized access, review institutional records and perform permitted administrative workflows |

### 4.1 Authentication and Authorization

- Supabase Auth is used for user authentication.
- Sign-in is intended for administrator-authorized users.
- Role-aware access is intended to restrict users to their assigned institutional records.
- Database permissions and Row Level Security (RLS) are important parts of the access-control model.
- Frontend visibility alone must never be treated as proof of authorization.
- Server-side authorization must protect sensitive operations and record access.

### 4.2 Security and Privacy Considerations

The prototype includes authentication and permission-related mechanisms. However, a complete independent security audit, penetration test and comprehensive negative-path authorization assessment have not been established by this document.

Before production deployment, the project requires:

- Verification of stakeholder-specific data isolation.
- Comprehensive authentication and authorization testing.
- Review of database RLS policies and server-side access checks.
- Secure handling of API keys and service credentials.
- Protection of inspection evidence and sensitive institutional information.
- Appropriate audit trails, backup and recovery procedures.
- Documented data retention and access-revocation policies.

**Security boundary:** Public documentation must not contain private credentials, API keys, unredacted inspection evidence, private user information or sensitive database configuration.

## 5. Novelty and Integration Value

BhuGrid's novelty is its prototype-level combination of geographic visualization, institutional information management, linked records and evidence-oriented administrative workflows. It is not a claim of patented or globally unique invention.

The key integration aspects are:

1. **GIS-to-Institution Linkage:** Connect geographic institution locations with associated property and asset information.
2. **Institutional Record Organization:** Provide a structured way to organize information related to religious institutions and their associated assets.
3. **Evidence-Oriented Inspection:** Support field observations and evidence submission to help create a traceable administrative review process.
4. **Role-Based Stakeholder Access:** Design separate access workflows for Local Bodies, Trustees / Institutional Management, Government Agencies, Inspectors and Administrators.
5. **Human-in-the-Loop AI:** Explore AI-assisted administrative summaries and preliminary review suggestions while retaining human responsibility for decisions.
6. **External Geographic Service Integration:** Use Geoapify for nearby essential-service discovery without treating external place results as official institutional records.
7. **Source Transparency:** Distinguish provisional community-mapped geographic candidates from fictional DEMO records and future verified institutional information.
8. **Integrated Project Communication:** Maintain a separate showcase website to explain the project, alongside the functional React web application.

An exploratory synthetic image-difference experiment exists in the development project. However, no trained real-world encroachment detector, legally valid boundary-detection system or verified automated property-change detection capability has been demonstrated.

## 6. Geographic Data and DEMO Scope

The current geographic inventory covers three districts:

| Geographic dataset | Number of features | Status |
|---|---:|---|
| Cuttack | 72 | Provisional OpenStreetMap-derived points |
| Puri | 60 | Preliminary OpenStreetMap-derived candidates |
| Khordha | 107 | Preliminary OpenStreetMap-derived candidates |
| **Total** | **239** | **Unverified GIS features** |

In addition, the prototype contains **3 separate fictional Supabase DEMO institutions** for controlled testing and demonstration.

These DEMO institutions are separate from the 239 geographic candidates. They must not be presented as verified real institutions or official property records.

The geographic inventory is subject to data-quality review, source attribution, duplicate checks and authoritative verification. Its presence on the map does not establish legal or administrative status.

## 7. Team Responsibilities

| Member | Main area of responsibility |
|---|---|
| Srusti | GIS data preparation and validation, AI/ML backend, external service integration and technical documentation |
| Pratikshya | React web application UI, application integration, testing and presentation |
| Shakti | Supabase database, schema, access rules and institutional record / decision workflows |
| Smruti | Project showcase website, visual content and user documentation |

Responsibilities may overlap during integration, testing and documentation.

## 8. Prototype Workflow

The intended institutional workflow is:

`Authorized user sign-in → assigned institution access → linked property and asset records → inspection / evidence submission → administrative review → authorized follow-up`

Supporting workflows include:

- **Institutional stakeholder access:** An authorized stakeholder views only the institutions and associated records permitted by their assigned access.
- **Inspector workflow:** An authorized inspector submits field observations and supporting location or photographic information.
- **Administrative workflow:** An authorized administrator reviews available records and inspection information and performs permitted administrative actions.
- **AI-assisted review:** An authorized administrator may use an AI-generated preliminary review draft where the relevant integration is available. Human verification remains mandatory.
- **Nearby essentials:** The application can retrieve nearby essential-service information through the Geoapify integration.

These workflows describe the intended prototype structure. Their complete production readiness and end-to-end authorization behaviour require further testing.

## 9. Future Implementation Roadmap

### 9.1 Near-Term Reliability and Verification

- Complete the redesign of the former Public/Tourist interface into the Institutional Stakeholder Portal.
- Verify administrator-authorized sign-in and stakeholder-specific access.
- Confirm that Local Bodies, Trustees / Institutional Management and Government Agencies can access only their assigned institutions and linked properties and assets.
- Independently validate institution locations and geographic information against authoritative sources.
- Review the 239 unverified GIS features for duplicates, classification issues and geographic accuracy.
- Conduct end-to-end browser testing of map interactions, record views, location capture and responsive layouts.
- Continue testing Geoapify integration, category retrieval, error handling and service reliability.
- Strengthen server-side inspection-record retrieval and evidence/property provenance checks for AI-assisted review.

### 9.2 Production Security and Governance

- Complete role-based access and RLS testing.
- Conduct independent security review and penetration testing.
- Introduce appropriate audit trails and administrative activity tracking.
- Establish backup, recovery and data-retention procedures.
- Define authorized onboarding and verification procedures for real institutional records.
- Establish data-sharing and approval arrangements with relevant government agencies and institutional authorities.
- Maintain clear source provenance, licence notices and attribution on geographic outputs.
- Ensure that sensitive property, inspection and user information is handled under appropriate access restrictions.

### 9.3 Advanced Roadmap — Not Implemented as Complete Capabilities in Version 1.0

- Verified religious-institution and property onboarding through authorized sources.
- Integration with relevant government and institutional information systems, subject to formal approval.
- Historical evidence tracking and geospatial change-review workflows.
- Human-reviewed identification and escalation of potential property or boundary changes.
- Explainable risk triage using validated data and accountable administrative decisions.
- Improved GIS analytics and institutional asset reporting.
- Offline-capable field inspection workflows.
- Accessibility and multilingual support.
- Monitoring dashboards and administrative analytics.

These items represent future development directions and must not be presented as completed Version 1.0 capabilities.

## 10. Current Limitations

BhuGrid 1.0 remains a controlled educational and competition prototype.

- The three Supabase DEMO institutions and their associated illustrative records are fictional.
- The 239 geographic features are unverified GIS candidates, not an official institutional register.
- Community-sourced geographic information may be incomplete, inaccurate or outdated.
- Administrative access isolation requires comprehensive verification before production claims.
- Geoapify nearby-place results do not establish that a business or service is currently operating or accessible.
- AI-generated administrative content is advisory and requires human review.
- No legally valid ownership verification or automated encroachment determination is claimed.
- No government endorsement, official land-record certification or statewide operational deployment is claimed.
- Structural GIS validation does not establish authoritative geographic or legal correctness.
- Production deployment requires further security, governance, data-quality and operational validation.

## 11. Related Public Documentation

- [Datasets and Citations](DATASETS_AND_CITATIONS.md)
- [Web App](WEB_APP.md)
- [Website](WEBSITE.md)

**Project links:**

- Web Application: https://bhugrid-web-app.onrender.com/
- Showcase Website: https://bhugrid-website.onrender.com/
- Public Documentation Repository: https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Documentation note:** The public repository is intended for project documentation. It does not constitute publication or licensing of the private application source code, backend implementation, credentials or private deployment configuration.
