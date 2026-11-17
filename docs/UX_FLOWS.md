# BhuGrid 1.0 — User Workflows

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Platform:** GIS-based Religious Institution and Asset Management Platform  
**Development Stage:** Functional Prototype / Controlled DEMO  

---

## 1. Overview

This document describes the principal user journeys supported by BhuGrid 1.0, including institutional stakeholder access, geographic exploration, institution-linked information, inspection submission and administrative review.

The platform provides three primary workspaces:

1. **Institutional Stakeholder Portal** — for Local Bodies, Trustees / Institutional Management and Government Agencies.
2. **Inspector Interface** — for authorized inspection observations and supporting evidence.
3. **Administrator Interface** — for authorized inspection review and administrative decisions.

The workflows distinguish implemented prototype functionality from intended user-experience requirements. They do not imply official institutional deployment or legal verification of property information.

## 2. Authorized Stakeholder Sign-In

**User:** Administrator-approved institutional stakeholder.

**Objective:** Access the stakeholder workspace through an approved account.

**User journey:**

1. Open the BhuGrid web application.
2. Navigate to the Institutional Stakeholder Portal.
3. Enter the approved account credentials.
4. Submit the sign-in request.
5. The system authenticates the account through Supabase Auth.
6. The application checks the relevant stakeholder authorization.
7. The user enters the permitted stakeholder workspace.

**Expected success state:** The approved stakeholder can access their authorized workspace.

**Denied-access state:** Invalid, unapproved or unauthorized accounts cannot access protected institutional records.

**Loading state:** Authentication and authorization checks are in progress.

**Error state:** Authentication or connectivity failures prevent access and should be communicated without exposing sensitive details.

**Important:** Public self-registration is not part of the intended stakeholder workflow. Stakeholder accounts are administrator-provisioned.

## 3. Stakeholder Category Verification

**User:** Authenticated institutional stakeholder.

**Objective:** Confirm the stakeholder's approved category and institutional permissions.

**Supported categories:**

- Local Bodies.
- Trustees / Institutional Management.
- Government Agencies.

**User journey:**

1. The stakeholder completes authentication.
2. The application checks the approved stakeholder membership.
3. The user's authorized category is identified.
4. Institution assignments are evaluated.
5. The workspace presents permitted institutional information.

**Expected success state:** The stakeholder accesses the correct authorized institutional scope.

**Denied-access state:** Missing approval, invalid membership or unauthorized assignment prevents access to restricted records.

**Loading state:** Membership and institution-assignment checks are pending.

**Error state:** Authorization data cannot be retrieved or validated.

The user cannot gain additional institutional access simply by selecting a different stakeholder category in the interface.

## 4. GIS Map Exploration

**User:** User with access to the relevant GIS interface.

**Objective:** Explore available religious institution locations geographically.

**User journey:**

1. Open the GIS explorer.
2. Wait for the geographic map and available location data to load.
3. Navigate the map using zoom and pan controls.
4. Explore supported district locations.
5. Select available geographic markers to examine their information.

**Expected success state:** The map displays available geographic records and responds to navigation and selection.

**Loading state:** Map tiles or geographic data are still loading.

**Error state:** Map resources, network requests or geographic records fail to load.

**Data boundary:** The documented geographic inventory contains 239 provisional OpenStreetMap-derived features across Cuttack, Puri and Khordha. These are not department-verified institutional records or legally authenticated properties.

## 5. Institution Selection

**User:** Authorized application user.

**Objective:** Select an institution and examine its available information.

**User journey:**

1. Open the relevant institution discovery interface.
2. Search or browse available institution information.
3. Select an institution or geographic marker.
4. The application retrieves the relevant available details.
5. The user examines the displayed information.

**Expected success state:** Available information for the selected institution or geographic feature is displayed.

**Loading state:** The selected record is being retrieved.

**Denied-access state:** Protected institutional information is not displayed when the user lacks permission.

**Error state:** The selected record is unavailable or cannot be retrieved.

**Important distinction:** Selecting a provisional OSM geographic marker does not automatically provide access to an authenticated institutional property record.

## 6. Authorized Property and Asset Viewing

**User:** Approved institutional stakeholder.

**Objective:** View properties and assets linked to an assigned institution.

**User journey:**

1. Sign in using an approved stakeholder account.
2. Open an institution assigned to the stakeholder.
3. Request its linked property information.
4. The application checks the user's institutional authorization.
5. Permitted property and asset information is displayed.
6. The stakeholder examines the available records.

**Expected success state:** Only authorized institution-linked records are accessible.

**Denied-access state:** Attempts to access an unassigned institution or its protected records are rejected.

**Loading state:** Linked property or asset information is being retrieved.

**Error state:** The record cannot be retrieved because of a service, data or authorization-processing failure.

The project team reported successful prototype checks for assigned institution visibility and cross-institution access denial on 16 November 2026.

The linked records currently used for management demonstrations are fictional DEMO data.

## 7. Nearby Essentials Finder

**User:** Authorized stakeholder using the supported geographic assistance feature.

**Objective:** Explore essential facilities near a selected religious institution location.

**User journey:**

1. Open the Nearby Essentials Finder.
2. Select or provide the relevant institution location.
3. Choose an available facility category.
4. The application requests nearby information through its Geoapify integration.
5. Available facility results are displayed.
6. The stakeholder examines nearby services for geographic context.

**Supported categories:**

- Hospitals.
- Restaurants.
- Petrol pumps.

**Expected success state:** Available nearby-place information is displayed.

**Loading state:** The nearby-place request is being processed.

**Empty-result state:** No matching facilities are returned for the requested location or category.

**Error state:** External service, connectivity or request-processing failures prevent retrieval.

**Data boundary:** Nearby-place names, distances and other details are externally sourced and provisional. They require independent verification.

The feature supports institutional planning and surrounding infrastructure awareness, rather than official facility certification.

## 8. Smart Trip Planner

**User:** Authorized stakeholder using the supported planning feature.

**Objective:** Generate advisory institution-related visit suggestions.

**User journey:**

1. Open the Smart Trip Planner.
2. Provide the available visit-planning inputs.
3. Submit the planning request.
4. The application processes the request through its Groq integration.
5. AI-assisted itinerary suggestions are returned.
6. The stakeholder reviews the suggestions for visitor-related planning context.

**Expected success state:** A relevant advisory itinerary or planning suggestion is displayed.

**Loading state:** The AI request is being processed.

**Error state:** Invalid input, service unavailability or request failure prevents generation.

**Output boundary:** AI-generated itineraries are suggestions, not confirmed travel arrangements. Travel times, availability, routes and facility information require independent verification.

The feature supports understanding of potential visitor movement and institution-related tourism opportunities.

## 9. Inspector Evidence Submission

**User:** Authorized Inspector.

**Objective:** Submit structured inspection observations and supporting evidence.

**User journey:**

1. Sign in through the authorized Inspector workflow.
2. Open the relevant institution or inspection record.
3. Enter available inspection observations.
4. Provide location information where supported.
5. Attach permitted supporting evidence.
6. Review the submission details.
7. Submit the inspection record.
8. The application processes and stores the permitted submission.

**Expected success state:** The inspection submission is accepted and becomes available through the relevant authorized workflow.

**Loading state:** Evidence or inspection information is being submitted.

**Denied-access state:** Users without Inspector permissions cannot perform restricted inspection submissions.

**Validation state:** Missing required information or unsupported evidence prevents submission until corrected.

**Error state:** Upload, database or connectivity failures interrupt submission.

**Evidence boundary:** Inspector observations and photographs are submitted evidence, not automatic confirmation of encroachment, ownership or legal violations.

## 10. Administrator Review

**User:** Authorized Administrator.

**Objective:** Review inspection information and record permitted administrative assessments.

**User journey:**

1. Sign in through the Administrator interface.
2. Open available inspection or possible-change information.
3. Examine submitted observations and supporting evidence.
4. Review any available rule-based DEMO priority indicators.
5. Optionally request AI Administrative Review.
6. Evaluate the information using human judgment.
7. Record an authorized review outcome or follow-up action.
8. Access available review history where supported.

**Expected success state:** The permitted administrative review action is recorded.

**Loading state:** Inspection information, advisory analysis or review operations are being processed.

**Denied-access state:** Users without appropriate administrative authorization cannot perform restricted review actions.

**Error state:** Record retrieval, AI generation or review submission fails.

**Decision boundary:** Groq-generated administrative observations and DEMO priority indicators are advisory. Final administrative decisions remain under authorized human control.

Possible-change observations do not independently establish legally verified encroachment or property violations.

## 11. Common Interface States

The following states apply conceptually across BhuGrid's user workflows.

| State | Expected application behavior |
|---|---|
| Success | Display the requested permitted information or confirm a completed operation |
| Loading | Indicate that authentication, retrieval, submission or external processing is in progress |
| Denied Access | Prevent unauthorized access to protected records or operations |
| Validation Error | Identify missing or invalid input without exposing sensitive implementation details |
| Empty Result | Communicate when no matching data is available |
| Service Error | Communicate request or service failure and allow appropriate retry |
| Session Expired | Require renewed authentication before protected operations continue |

These are expected UX behaviors. The table is not a claim that every state has been independently tested across every workflow.

## 12. Workflow Verification and Limitations

### 12.1 Documented Prototype Status

| Workflow | Documented status |
|---|---|
| Stakeholder sign-in and category-based access | Implemented; prototype-tested |
| Assigned institution and linked-record restrictions | Backend verification reported PASS |
| GIS map exploration | Implemented |
| Institution discovery and selection | Implemented |
| Nearby Essentials Finder | Integrated and functionally tested |
| Smart Trip Planner | Integrated and functionally tested |
| Inspector inspection/evidence workflow | Implemented |
| Administrator review workflow | Implemented |
| AI Administrative Review | Integrated and functionally tested |
| Comprehensive UX and accessibility certification | Not established |

### 12.2 Known Limitations

- Geographic information is provisional and unverified.
- Institution-linked management records are fictional DEMO data.
- External API availability is not guaranteed.
- AI outputs are advisory and require human assessment.
- Workflow testing does not constitute independent production security certification.
- Real institutional deployment requires authoritative datasets, formal permissions and additional validation.

## 13. Related Documentation

- [Project Overview](../README.md)
- [Product Requirements Document](PRD.md)
- [System Architecture](ARCHITECTURE.md)
- [Data Model Overview](DATABASE.md)
- [Security and Access Control](SECURITY.md)
- [Functional Web Application](../WEB_APP.md)

---

**Repository Notice — Documentation Only**

This public repository contains BhuGrid 1.0 project documentation only. It does not publish or license the original application source code, private backend implementation, credentials or sensitive institutional records.

**Workflow Status:** The documented journeys describe implemented prototype functions and expected interface behavior. They do not represent official institutional deployment or independently certified production workflows.
