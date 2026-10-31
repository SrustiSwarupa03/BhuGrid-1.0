# BhuGrid 1.0 — Features, Novelty, Roles, Security & Future Implementation

**Project:** BhuGrid 1.0 · **Scope:** Controlled prototype / DEMO · **Updated:** 31 October 2026

> **BhuGrid — The single secure vault for every sacred legacy across Odisha.**

## 1. Project vision

BhuGrid is a GIS-oriented prototype for organizing and exploring religious-institution information in Odisha, linking mapped institutions to illustrative property and asset records, documenting inspections, and supporting transparent review. It combines a map-centric public experience with differentiated inspector and administrator workflows and carefully labeled AI assistance.

**Important limitation:** A displayed map point or fictional DEMO record is not an official verification of heritage status, property ownership, land boundaries, encroachment, or legal rights.

## 2. Current functional components

| Component | Prototype capability |
|---|---|
| Odisha GIS explorer | Interactive state/district map, district selection, institutional markers and discovery |
| Institution discovery | Search/selection with available names, coordinates, and verification labels |
| Linked records | View institution-related DEMO property and asset information |
| Public/tourist experience | Map exploration and institution information without administrative privileges |
| Field inspection | Inspector-facing observation, evidence and potential-change reporting workflows |
| Location capture | GPS-assisted or manual location selection in inspection-oriented workflows |
| Administrative tools | Inspection/review interfaces and an existing administrative decision workflow |
| DEMO prioritization | Prototype scoring / prioritization interfaces; not official determinations |
| Record output | Print-oriented record view for prototype records |
| Access controls | Supabase authentication, role-aware frontend workflows and database access controls |
| AI tourist tools | Suggested itineraries and nearby-service discovery interface |
| AI administrator tool | Read-only preliminary review draft from inspection observations |

Exact availability depends on role, permissions, deployed version and data. The prototype is not a fully certified government records system.

## 3. AI integrations and tested status

### Smart Trip Planner — demonstrated

- **Backend:** Supabase Edge Function `tourist-assist` with `feature: "trip_planner"`.
- **AI service:** Groq; model recorded as `openai/gpt-oss-20b`.
- **Input:** Approved fictional DEMO starting institution, duration (1–8 hours), maximum stops (1–3).
- **Output:** `itinerary[]` with `stop`, `activity` and `duration_minutes`, plus a cautionary `note`.
- **Test status:** Backend returned `success: true`, `ai_generated: true`, and frontend itinerary rendering was integrated.
- **Safety:** Activities are generic suggestions, **not** verified businesses, directions, attractions, opening hours or travel times.

### Nearby Essentials Finder — integrated, live retrieval unresolved

- **Backend:** `tourist-assist` with `feature: "nearby_essentials"`.
- **Source:** OpenStreetMap via Overpass; supported types: hospital, restaurant and fuel.
- **Input:** OSM-style institution identifier, valid coordinates, categories and radius up to 10 km.
- **Output design:** Up to 30 source-attributed, unverified places and **straight-line** distances.
- **Test status:** Frontend request/error handling integrated; external Overpass HTTP 429 errors led to backend HTTP 503. Successful live result retrieval has **not** been demonstrated.
- **Safety:** This is OSM-based retrieval, not Groq-generated recommendations. It does not guarantee the establishment is operating or accessible.

### AI Administrative Review Assistant — demonstrated as advisory

- **Backend:** Supabase Edge Function `admin-review-ai` with `feature: "administrative_review"`.
- **Use:** Approved administrator selects a fictional DEMO property; frontend retrieves accessible linked inspection observations and submits them for a preliminary AI draft.
- **Output:** Summary, `risk_level` (`low`, `medium`, `high`, `unknown`), observations, recommended actions and `requires_human_review: true`.
- **Test status:** A draft was displayed using `DEMO-PROP-001`; the result recognized the evidence as fictional and displayed `unknown` risk.
- **Boundary:** The AI-review workflow is **read-only**; it does not approve, reject or overwrite administrative decisions.
- **Known gap:** The Edge Function has not independently verified the provenance of every client-supplied inspection note against a server-side property inspection. This must be strengthened before production use.

## 4. User roles and security model

| Role / surface | Intended responsibilities |
|---|---|
| Public / tourist | Explore permitted map and institution information; access appropriate tourism tools |
| Inspector | Submit authorized field observations, location information and photographic evidence |
| Administrator | Review accessible records and inspections; perform authorized administrative workflows |
| Approved administrator (AI review) | Generate preliminary, non-binding AI review drafts requiring human verification |

Authentication uses **Supabase Auth**. The administrative AI endpoint requires a bearer token, resolves the user via Supabase Auth and checks approved administrator status through the `is_approved_admin` RPC. It also restricts requests to an explicit fictional DEMO property allowlist and validates input. Frontend visibility is not a replacement for server-side authorization. Database access is subject to the project's implemented permission/RLS rules.

**Security status:** Prototype protections are implemented; an independent security audit, penetration testing and comprehensive negative-path authorization tests have **not** been completed. Store Groq secrets server-side; do not publish service credentials, private inspection documents, or unredacted user information.

## 5. Novelty and integration value

BhuGrid's key **prototype-level combination**, rather than a claim of patented or globally unique invention, is:

1. **Spatial-to-record linkage:** Move from district and institution discovery to connected DEMO property, asset and inspection records.
2. **Evidence-oriented workflow:** Capture inspector observations and support structured administrative follow-up instead of relying on disconnected documents.
3. **Role-aware separation:** Distinguish public discovery, field reporting and administrative review.
4. **Human-in-the-loop AI:** Generate tourism suggestions and read-only administrative drafts with explicit uncertainty and required human review.
5. **Source transparency:** Distinguish DEMO records, unverified community mapping and potential official records rather than presenting all data as equally trustworthy.
6. **Integrated public communication:** A separate project showcase website explains the product while the React web application provides the functional prototype.

An exploratory synthetic image-difference experiment exists in the source project; **no trained real-world encroachment detector or legally valid boundary-detection system has been demonstrated**.

## 6. Team responsibilities

| Member | Main area |
|---|---|
| Srusti | GIS data preparation/validation, AI/ML backend, integration and technical documentation |
| Pratikshya | React web-app UI, application integration, testing and presentation |
| Shakti | Supabase database, schema, access rules and record/decision workflows |
| Smruti | Project showcase website, visual content and user documentation |

## 7. Prototype workflow

`Public map discovery → institution selection → linked DEMO records → authorized inspection/evidence capture → administrative review / decision workflow`

Optional assistance: `tourist selection → AI trip suggestion or OSM nearby lookup`; `approved administrator → linked DEMO inspection → AI review draft → human verification`.

## 8. Future implementation roadmap

**Near-term reliability and verification**
- Repair or replace rate-limited Overpass retrieval with a compliant, reliable provider and/or appropriately maintained cache.
- Independently check institution and geographic data against authoritative sources; resolve duplicates and classification exceptions.
- Verify displayed datasets, GPS/manual selection and responsive views in end-to-end browser testing.
- Add server-side inspection-record retrieval and evidence/property provenance validation for AI review.

**Production security and governance**
- Complete role/RLS testing, abuse protections, audit trails, security review, backup/recovery and documented retention policies.
- Establish approval rules for real property records and evidence with authorized government/owner partners.
- Publish complete data provenance, licence notices and attribution on mapped outputs.

**Advanced roadmap — not implemented in 1.0**
- Verified heritage/property onboarding and inter-agency integrations.
- Evidence history, geospatial change review and escalation with human sign-off.
- More reliable route-aware visitor planning from verified points of interest.
- Explainable risk triage with validated datasets and accountable human decisions.
- Accessibility, multilingual support, offline-capable field inspection and monitoring analytics.

## 9. Current limitations

This is an educational/competition prototype. DEMO property and institution IDs are fictional. Community mapping may be inaccurate. Administrative decisions cannot be delegated to AI. Structural tests of GeoJSON do not establish legal or authoritative geographic correctness. No government endorsement, official land-record certification, legal ownership proof or validated encroachment-detection performance is claimed.

**Related public documents:** [Datasets and Citations](DATASETS_AND_CITATIONS.md) · [Web App](WEB_APP.md) · [Website](WEBSITE.md).
