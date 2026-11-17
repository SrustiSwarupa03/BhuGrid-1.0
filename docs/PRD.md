# BhuGrid 1.0 — Product Requirements Document (PRD)

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Product Type:** GIS-based Religious Institution and Asset Management Platform  
**Development Stage:** Functional Prototype / Controlled DEMO  

---

## 1. Project Overview

BhuGrid 1.0 is a GIS-based Religious Institution and Asset Management Platform developed to support the geographic visualization, organization, monitoring and preservation of religious institutions and their associated properties and assets across Odisha.

Developed in response to **Problem Statement PS-143**, BhuGrid demonstrates how geographic information systems, structured institutional records, digital inspection workflows and AI-assisted administrative tools can be integrated into a unified platform.

The initial prototype includes an interactive GIS interface, institution-linked DEMO records, role-specific workflows and supplementary geographic assistance.

BhuGrid 1.0 is a controlled development prototype, not an officially deployed government property-management system.

## 2. Problem Statement and Objectives

### 2.1 Problem Statement — PS-143

Religious institutions and their associated properties and assets require organized information, geographic visibility, systematic inspection and accountable administrative monitoring.

Existing challenges may include:

- Fragmented institution, property and asset information.
- Limited integration between geographic maps and institutional records.
- Difficulty maintaining structured inspection evidence.
- Manual or disconnected administrative review processes.
- Limited coordination among institutional stakeholders.
- Inconsistent verification and provenance of geographic records.

### 2.2 Product Objectives

BhuGrid aims to:

1. Provide centralized GIS-based discovery of religious institutions.
2. Establish structured relationships between institutions, properties and assets.
3. Support authorized institutional stakeholder access.
4. Enable digital inspection and evidence-submission workflows.
5. Facilitate administrative review and record tracking.
6. Provide advisory AI-assisted analysis without replacing human decisions.
7. Improve awareness of nearby essential services and visitor-related geographic context.
8. Support future integration of verified institutional datasets and stronger governance mechanisms.

## 3. Target Stakeholders

| User group | Primary requirement |
|---|---|
| Local Bodies | View assigned institutional information and linked assets for local coordination |
| Trustees / Institutional Management | Access authorized information relating to their institutions and associated properties |
| Government Agencies | Review permitted institutional information for administrative purposes |
| Inspector | Record field observations, location information and supporting evidence |
| Administrator | Manage authorized workflows, review inspection records and perform administrative assessments |

Institutional stakeholder accounts are administrator-authorized. Access to institution-linked information is restricted according to approved assignments.

## 4. Core Product Capabilities

| Capability | Product requirement | Current status |
|---|---|---|
| Interactive GIS Map | Visualize available religious institution locations across supported Odisha districts | Implemented |
| Institution Discovery | Search and select available geographic institution records | Implemented |
| Linked Property and Asset Records | Display structured institution-associated records | Implemented with fictional DEMO data |
| Institutional Stakeholder Portal | Provide authorized access for three stakeholder categories | Implemented and prototype-tested |
| Institution-Specific Authorization | Restrict access to assigned institutions and linked records | Backend checks passed |
| Inspector Workflow | Support observations, location capture and evidence submission | Implemented |
| Administrator Workflow | Support inspection review, permitted decisions and review history | Implemented |
| Rule-Based Prioritization | Provide deterministic DEMO review-priority indicators | Implemented — advisory |
| AI Administrative Review | Generate preliminary AI-assisted administrative observations | Integrated and tested |
| Nearby Essentials Finder | Retrieve nearby essential services through Geoapify | Integrated and tested |
| Smart Trip Planner | Generate AI-assisted visit-planning suggestions | Integrated and tested |
| Record Output | Provide print-oriented presentation of available records | Implemented |

### 4.1 Geographic Data Scope

The documented geographic inventory contains:

- **Cuttack:** 72 provisional OpenStreetMap-derived features.
- **Puri:** 60 preliminary OpenStreetMap-derived candidates.
- **Khordha:** 107 preliminary OpenStreetMap-derived candidates.
- **Total:** 239 unverified GIS features.

The prototype separately contains **three fictional Supabase DEMO institutions** with illustrative property and asset records.

These two data categories must remain clearly distinguished.

## 5. User Stories

| ID | User story | Expected outcome |
|---|---|---|
| US-01 | As an authorized stakeholder, I want to sign in securely so that I can access my permitted institutional workspace. | Approved account access |
| US-02 | As a stakeholder, I want to view my assigned institutions so that I can examine relevant information. | Institution-specific visibility |
| US-03 | As a stakeholder, I want to view linked properties and assets so that I can understand the available institutional records. | Authorized linked-record access |
| US-04 | As a stakeholder, I want to explore institution locations on a GIS map so that I can understand geographic context. | Interactive geographic exploration |
| US-05 | As an Inspector, I want to submit observations and supporting evidence so that inspections can be reviewed. | Structured inspection submission |
| US-06 | As an Administrator, I want to review inspection information so that I can record appropriate administrative actions. | Human-controlled review |
| US-07 | As an Administrator, I want preliminary AI-generated observations so that I can consider additional advisory information. | AI-assisted review output |
| US-08 | As a stakeholder, I want to discover nearby essential facilities so that I can understand surrounding infrastructure. | Geoapify-powered nearby information |
| US-09 | As a stakeholder, I want suggested visit itineraries so that I can understand potential visitor movement and planning opportunities. | AI-assisted planning suggestions |
| US-10 | As an unauthorized user, I should be denied access to restricted institutional records. | Access restrictions enforced |

## 6. Minimum Viable Product (MVP) Scope

The BhuGrid 1.0 MVP demonstrates the following integrated functions:

1. Interactive GIS-based institution discovery.
2. Provisional geographic inventory for three Odisha districts.
3. Three fictional DEMO institutions with linked property and asset information.
4. Authenticated Institutional Stakeholder, Inspector and Administrator workspaces.
5. Institution-specific stakeholder authorization.
6. Digital inspection and administrative review workflows.
7. Rule-based DEMO prioritization and advisory AI Administrative Review.
8. Geoapify-powered Nearby Essentials Finder.
9. Groq-powered Smart Trip Planner.
10. Deployed functional web application for controlled demonstration.

**MVP Verification:** The team reported successful stakeholder frontend and backend checks on 16 November 2026, including 8/8 frontend functional checks and relevant authorization restrictions.

The MVP demonstrates product feasibility. It does not establish readiness for real institutional deployment.

## 7. Non-Goals and Constraints

### 7.1 Non-Goals

BhuGrid 1.0 does not aim to provide:

- Legally authoritative property ownership certification.
- Official cadastral boundary verification.
- Automatic real-world encroachment detection.
- Autonomous administrative decisions.
- Government-certified institutional registration.
- Statewide operational deployment.
- Production-grade security certification.

### 7.2 Constraints

**Data constraints:** Geographic records are provisional; property and asset records are fictional DEMO data.

**Security constraints:** Protected workflows require authorized accounts, and the prototype's verified authorization controls do not replace independent security assessment.

**External-service constraints:** Groq and Geoapify availability, output quality and response completeness depend on external services.

**Operational constraints:** Real-world deployment requires institutional permissions, authoritative data, privacy controls, maintenance procedures and additional testing.

**AI constraints:** Generated administrative observations and visit-planning suggestions require human verification.

## 8. Acceptance Criteria

The following criteria define the expected behavior of the controlled BhuGrid 1.0 prototype.

| ID | Acceptance criterion | Documented result |
|---|---|---|
| AC-01 | GIS interface displays supported institution locations. | Implemented |
| AC-02 | Available institution records can be discovered and selected. | Implemented |
| AC-03 | Fictional DEMO institutions display linked property and asset information. | Implemented |
| AC-04 | Approved stakeholders can access their assigned institutions. | PASS — prototype checks |
| AC-05 | Stakeholders cannot access unauthorized institution-linked records. | PASS — backend checks |
| AC-06 | Inspector workflows support inspection observations and evidence. | Implemented |
| AC-07 | Administrator workflows support review and permitted actions. | Implemented |
| AC-08 | AI Administrative Review produces advisory output without autonomous decisions. | Functionally tested |
| AC-09 | Nearby Essentials retrieves supported Geoapify place categories. | PASS — functional testing |
| AC-10 | Smart Trip Planner produces AI-assisted planning suggestions. | PASS — functional testing |
| AC-11 | Public signup and anonymous sign-in are disabled in the documented stakeholder configuration. | PASS — backend checks |
| AC-12 | The application is suitable for production deployment without additional verification. | Not established |

**Overall assessment: PASS WITH LIMITATIONS.**

Acceptance results describe the team's reported prototype testing and do not imply exhaustive functional, performance or security certification.

## 9. Implemented Versus Planned Requirements

### 9.1 Implemented and Tested

- Interactive Odisha GIS map and institution discovery.
- Institution-linked fictional DEMO property and asset records.
- Inspector and Administrator workflows.
- Institutional Stakeholder Portal and assigned-record restrictions.
- Supabase authentication and relevant authorization checks.
- Groq-powered AI Administrative Review.
- Geoapify-powered Nearby Essentials Finder.
- Groq-powered Smart Trip Planner.
- Controlled web application deployment.

### 9.2 Planned Improvements

- Authoritative verification of geographic institution datasets.
- Stronger authorization and independent security testing.
- Improved inspection history and evidence provenance.
- District-level analytics and reporting.
- Regional-language support, including Odia.
- Enhanced mobile accessibility and offline field workflows.
- Controlled integration of approved real institutional records.

### 9.3 Deferred Research

Satellite-assisted geographic change screening, advanced image analysis and 3D institutional visualization may be explored in future versions, subject to appropriate datasets, permissions and technical validation.

These capabilities are not implemented or validated BhuGrid 1.0 features.

---

## 10. Product Status and Documentation Notice

**Current Product Status:** Functional Development Prototype — PASS WITH LIMITATIONS.

BhuGrid 1.0 demonstrates a unified GIS-based institutional information and asset-management approach using provisional geographic data, fictional DEMO records, authenticated workflows and advisory AI services.

It is not a production-certified government system or a source of legally authoritative property information.

**Repository Notice:** This public repository contains BhuGrid project documentation only. The original application source code, private backend implementation, credentials and deployment configurations are not released or licensed through this repository.

For the main project overview, see the [BhuGrid 1.0 README](../README.md).
