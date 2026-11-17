# BhuGrid 1.0 — Datasets, Provenance, Citations & Validation

**Project:** BhuGrid 1.0  
**Problem Statement:** PS-143  
**Dataset Status:** Provisional, preliminary and unverified GIS data for controlled prototype demonstration and exploration

---

## 1. Purpose and Data Governance

BhuGrid 1.0 is a GIS-based Religious Institution and Asset Management Platform designed to support geographic visualization, institutional record management, linked property and asset information, inspection workflows and administrative review across Odisha.

The prototype uses publicly sourced geographic information alongside separately maintained fictional demonstration records.

Its documented geographic inventory covers three Odisha districts:

- Cuttack
- Puri
- Khordha

The platform distinguishes between:

1. **Provisional geographic institution candidates** derived from publicly available geographic sources.
2. **Fictional DEMO institution, property and asset records** maintained for controlled application workflow demonstrations.
3. **Administrative boundary datasets** used for GIS visualization and geographic grouping.
4. **Supplementary research sources** used for geographic or cultural reference where applicable.
5. **External nearby-facility information** retrieved through Geoapify.

**Data governance principle:** The presence of a geographic feature on the BhuGrid map does not establish that an institution, property, ownership claim, boundary, land classification or heritage status has been officially verified.

Publicly sourced GIS records must not be treated as government-certified institutional records, cadastral information, legal property evidence or proof of encroachment.

Official operational use would require authoritative source partnerships, appropriate permissions, data validation and independent verification.

### Repository and Source Data Separation

This repository, [BhuGrid-1.0](https://github.com/SrustiSwarupa03/BhuGrid-1.0), is the public documentation and project-information repository.

It is **not an open-source software repository**.

The original application source code, backend implementation, private database configuration, credentials and restricted operational records are not released through this repository.

The detailed geographic source register and working processing records are maintained separately in the private development project.

The documented source inventory includes:

- `data/sources.csv`
- `data/processed/`
- Associated dataset collection and validation records

These private development records are not automatically included in this public documentation repository.

---

## 2. Current GIS Dataset Inventory

### 2.1 Geographic Dataset Summary

| Geographic coverage | Dataset | Recorded features | Verification status |
|---|---|---:|---|
| Cuttack | OSM institution points | 72 | Provisional and unverified |
| Puri | Preliminary OSM institution candidates | 60 | Preliminary and unverified |
| Khordha | Preliminary OSM institution candidates | 107 | Preliminary and unverified |
| **Total** | **Combined geographic inventory** | **239** | **Unverified GIS features** |

**Total documented geographic features: 239.**

These features support prototype-level geographic discovery and visualization.

The count does not establish that all 239 records represent officially recognized religious institutions or legally authenticated institutional properties.

### 2.2 Dataset Details

#### A. Cuttack — 72 Provisional OSM Records

- **Source:** OpenStreetMap.
- **Recorded collection date:** 21 October 2026.
- **Original retrieval:** 75 raw elements.
- **Filtering:** Three unnamed records excluded.
- **Retained records:** 72 named geographic features.
- **Identity reconciliation:** Processed records matched to saved raw exports using stable OSM identifiers.
- **Verification:** Unverified.
- **Original processing metadata:** `is_demo=false`.

Institution classification and individual record verification remain pending.

#### B. Puri — 60 Preliminary OSM Candidates

- **Source:** OpenStreetMap.
- **Current recorded inventory:** 60 preliminary geographic candidates.
- **Purpose:** Geographic discovery and preliminary institutional mapping.
- **Verification:** Unverified.

An earlier exploratory Puri extraction recorded 101 raw elements, including seven unnamed entries.

However, the historical 101-element extraction must not automatically be treated as the confirmed processing lineage of the current 60-record inventory.

The latest retrieval date, filtering rules and retained OSM identifiers require confirmation against the private source register.

#### C. Khordha — 107 Preliminary OSM Candidates

- **Source:** OpenStreetMap.
- **Current recorded inventory:** 107 preliminary geographic candidates.
- **Purpose:** Geographic discovery and preliminary institutional mapping.
- **Verification:** Unverified.

The exact retrieval date, original raw element count, filtering rules and stable OSM identifier reconciliation details remain subject to confirmation from the latest source register.

### 2.3 Interpretation of the 239-Feature Inventory

The combined inventory represents **239 provisional and unverified GIS features**.

It does not represent:

- 239 government-verified religious institutions.
- 239 legally recognized institutional entities.
- 239 authenticated land parcels or properties.
- 239 officially registered institutional assets.
- 239 completed administrative verification records.

Geographic discovery and legal or administrative verification are separate processes.

---

## 3. Separate Fictional DEMO Institution Records

BhuGrid 1.0 maintains **three separate fictional DEMO institutions** in its Supabase-backed prototype environment.

These records demonstrate institution-linked management and administrative workflows.

They are not included in the 239-feature public geographic inventory.

### 3.1 Purpose of the DEMO Dataset

The fictional records support demonstration of:

- Institution information management.
- Linked property records.
- Linked asset records.
- Institution-specific stakeholder access.
- Inspector observations and evidence submissions.
- Administrative review and follow-up.
- Record history and management workflows.

The DEMO records are illustrative and do not represent actual institutional ownership, revenue records or officially surveyed assets.

### 3.2 Public GIS Features versus DEMO Records

| Characteristic | Public GIS features | Supabase DEMO records |
|---|---|---|
| Origin | Community-contributed geographic information | Fictional demonstration data |
| Purpose | GIS discovery and visualization | Application workflow demonstration |
| Verification | Provisional and unverified | Explicitly fictional |
| Institution identity | Candidate geographic information | Illustrative DEMO identities |
| Property ownership | Not established | Not legally representative |
| Linked assets | Not authenticated | Synthetic illustrative records |
| Primary environment | Processed GIS datasets | Supabase application environment |

Public geographic candidates must not be silently converted into officially verified institutions or property records.

Fictional DEMO records must not be presented as actual government-registered institutions, genuine ownership information or verified institutional assets.

### 3.3 Institutional Stakeholder Access

The Institutional Stakeholder Portal supports three stakeholder categories:

1. Local Bodies.
2. Trustees / Institutional Management.
3. Government Agencies.

The documented prototype uses administrator-approved memberships and institution-specific assignments to restrict access to permitted institutional records.

As of 16 November 2026, the team reported successful frontend functional and backend authorization checks for the stakeholder portal.

These checks concern access control within the DEMO environment. They do not verify the legal or factual accuracy of the underlying fictional records.

---

## 4. Data Sources, Provenance and Citations

The following register summarizes the documented geographic sources and associated attribution information.

### 4.1 Geographic Source Register

| Source ID | Dataset / source | Recorded retrieval date | Recorded licence |
|---|---|---|---|
| `OSM_CUTTACK_001` | Cuttack places of worship | 21 October 2026 | ODbL 1.0 |
| `OSM-PURI-2026-10-22` | Puri exploratory extraction | 22 October 2026 | ODbL 1.0 |
| `OSM_KHORDHA_001` | Khordha preliminary institution candidates | To be confirmed | To be confirmed in source register |
| `GEO_ADM1_001` | India ADM1 / Odisha state boundary | 21 October 2026 | CC BY 2.5 IN |
| `GEO_ADM2_001` | India ADM2 / Odisha district geometries | 21 October 2026 | ODbL 1.0 |
| `WIKIDATA-ODISHA-2026-10-22` | Exploratory Odisha Wikidata sample | 22 October 2026 | CC0 1.0 |

The Khordha collection details and dataset-specific source metadata require reconciliation with the latest private source register.

The licence of OpenStreetMap data is generally ODbL 1.0; the unconfirmed entry above concerns the completeness of the Khordha source-register metadata, not a claim that OpenStreetMap uses a different licence.

### 4.2 OpenStreetMap and Overpass

**Source:** OpenStreetMap (OSM).

OpenStreetMap provides community-contributed geographic information used for preliminary institution discovery.

Overpass and Overpass Turbo are query and retrieval mechanisms for OSM data rather than separate authoritative institutional databases.

**Required attribution:**

© OpenStreetMap contributors

**References:**

- https://www.openstreetmap.org/copyright
- https://opendatacommons.org/licenses/odbl/1-0/
- https://overpass-turbo.eu/

Where OSM-derived data is displayed or redistributed, applicable attribution and database licence obligations must be respected.

Stable OSM identifiers should be retained in the private source register wherever available.

### 4.3 Administrative Boundary Sources

Administrative boundaries support GIS visualization, geographic grouping and district-level navigation.

They are not official cadastral or land-parcel boundaries.

#### Odisha State Boundary — ADM1

- **Source:** geoBoundaries.
- **Associated source attribution:** DataMeet India community and Election Commission of India.
- **Recorded licence:** CC BY 2.5 IN.
- **Recorded retrieval date:** 21 October 2026.

**References:**

- https://www.geoboundaries.org/api/current/gbOpen/IND/ADM1/
- https://github.com/datameet/maps

#### Odisha District Boundaries — ADM2

- **Source:** geoBoundaries.
- **Associated source metadata:** Pathways Data Pvt. Ltd. and Local Government Directory.
- **Recorded licence:** ODbL 1.0.
- **Recorded retrieval date:** 21 October 2026.

**References:**

- https://www.geoboundaries.org/api/current/gbOpen/IND/ADM2/
- https://geonode.pathwaysdata.com/layers/geonode

The above licensing and attribution information reflects the historical source register and must be reconciled with the exact downloaded dataset versions before redistribution.

### 4.4 Wikidata — Supplementary Exploratory Source

Wikidata was documented as a supplementary research source for geographic and institution-related information.

The earlier exploratory Odisha extraction recorded:

- **Retrieval date:** 22 October 2026.
- **Original exploratory result:** 100 rows.
- **Selected institution-name candidates:** 17.
- **Recorded licence:** CC0 1.0.

**References:**

- https://www.wikidata.org/
- https://query.wikidata.org/

The 17 selected candidates are not officially verified institutions.

They must not be added to the current 239-feature inventory unless their identities and inclusion are explicitly reconciled with the accepted district datasets.

Wikidata's documented use for exploratory research does not establish that all retrieved information is integrated into the deployed application.

### 4.5 Wikipedia — Supplementary Cultural Reference

Wikipedia may be referenced for historical, cultural or descriptive information relating to religious institutions where such information was actually consulted.

Wikipedia is not an authoritative source for:

- Institutional land ownership.
- Cadastral boundaries.
- Property registration.
- Legal encroachment determinations.
- Government institutional certification.

**Reference:**

https://www.wikipedia.org/

Wikipedia's role should be described as supplementary reference material, not as a confirmed primary source of the 239 GIS features.

If Wikipedia content is reused, the applicable page-specific attribution and licensing requirements must be checked.

---

## 5. External Service Integration — Geoapify

BhuGrid 1.0 uses the **Geoapify Places API** for its Nearby Essentials Finder.

The integration provides externally sourced geographic information about facilities around religious institution locations.

### 5.1 Supported Nearby Facilities

The documented and tested categories include:

- Hospitals.
- Restaurants.
- Petrol pumps.

These categories support institutional stakeholders in understanding surrounding facilities, local accessibility and visitor-support infrastructure.

### 5.2 Integration History

An earlier Nearby Essentials implementation depended on OpenStreetMap Overpass-based nearby-place retrieval.

Recurring service failures affected the reliability of this workflow.

Geoapify Places API was subsequently integrated through a Supabase Edge Function as an alternative retrieval service.

The team reported successful deployed functionality testing on 9 November 2026.

### 5.3 Separation of Source Responsibilities

| Source or service | Role in BhuGrid |
|---|---|
| OpenStreetMap / Overpass | Provisional geographic institution discovery |
| geoBoundaries / GeoJSON | Administrative geographic boundaries |
| Wikidata | Supplementary exploratory research |
| Wikipedia | Supplementary cultural references, where used |
| Geoapify Places API | Nearby Essentials retrieval |
| Supabase | Fictional DEMO institutional and linked record storage |

Geoapify is not the authoritative source of BhuGrid's religious institution inventory.

### 5.4 Attribution and Limitations

Geoapify attribution must be provided according to the applicable service plan and API conditions.

**Official references:**

- https://www.geoapify.com/
- https://apidocs.geoapify.com/

Geoapify results are externally sourced and may be incomplete, outdated or inaccurate.

Facility names, distances, opening hours and service availability require independent verification.

API credentials must remain protected and must not be published in this repository.

---

## 6. Collection, Filtering and Transformation Lineage

The current geographic inventory was assembled from public geographic information sources and processed for prototype-level visualization.

### 6.1 Recorded Processing History

| Activity | Recorded information |
|---|---|
| Cuttack original OSM extraction | 75 raw elements |
| Cuttack unnamed-record exclusion | 3 elements |
| Cuttack retained inventory | 72 records |
| Cuttack OSM identifier reconciliation | 72 records matched |
| Puri historical exploratory extraction | 101 raw elements |
| Puri historical unnamed records | 7 elements |
| Puri current inventory | 60 preliminary candidates |
| Khordha current inventory | 107 preliminary candidates |
| Wikidata exploratory extraction | 100 rows |
| Wikidata selected candidates | 17 |
| Administrative boundary processing | State and district GeoJSON datasets |

The earlier Puri extraction statistics are historical and should not be treated as the confirmed filtering lineage of the current 60-record inventory.

The latest Puri and Khordha retrieval snapshots, source identifiers and filtering criteria require confirmation from the private dataset register.

### 6.2 Processing and Provenance Principles

Geographic data processing should preserve:

1. Source attribution and licence information.
2. Stable OSM identifiers where available.
3. Original geographic coordinates and relevant source tags.
4. Retrieval dates and processing history.
5. Filtering and exclusion decisions.
6. Record verification status.
7. Separation between public geographic data and fictional DEMO records.

Where information is incomplete, records must remain marked as provisional or unverified.

### 6.3 Dataset Validation Boundaries

Data processing and structural validation do not establish legal or administrative authenticity.

A geographically plausible marker can still represent an incorrectly classified, duplicated, outdated or otherwise unsuitable institution candidate.

---

## 7. Technical Validation and Data Quality

Historical validation was performed on the available Cuttack and administrative boundary datasets.

### 7.1 Recorded Validation Results — 29 October 2026

| Validation check | Recorded result |
|---|---|
| GeoJSON FeatureCollection parsing | PASS |
| Total mapped features reviewed | 103 |
| Missing geometries / coordinates | 0 |
| Cuttack institution coordinates within approximate Odisha range | 72/72 |
| Duplicate institution coordinate groups | 0 |
| District polygon geometry validity | 30 passed |
| State polygon geometry validity | 1 passed |
| Geometry validation library | Shapely 2.1.2 |

These checks relate to the historical datasets reviewed at that time.

**They do not constitute completed validation of all 239 current geographic features.**

The expanded Puri and Khordha inventory requires corresponding structural, coordinate, classification and identity checks before full-dataset validation can be claimed.

### 7.2 What the Historical Checks Establish

The recorded validation activities assessed:

- GeoJSON structural consistency.
- Geometry parsing.
- Coordinate availability.
- Approximate geographic plausibility.
- Polygon geometry validity.
- Duplicate coordinate groups within the reviewed data.

They do not establish:

- Correct institution identity.
- Official institutional classification.
- Legal property ownership.
- Government registration.
- Cadastral accuracy.
- Legally certified administrative boundaries.
- Heritage certification.
- Encroachment or land-use violations.

Geometric validity and authoritative verification are separate requirements.

---

## 8. Known Data Quality Issues and Limitations

### 8.1 Institution Classification

Historical Cuttack dataset review identified the following issues:

- Twelve records lacked a religion tag in the original OSM data.
- All 72 processed records were provisionally assigned `institution_type=other` in the earlier processing record.
- A `religion=jewish` tag associated with Satsang Vihar Narasinghpur requires verification.
- MS LAW UNIVERSITY was returned with `amenity=place_of_worship`; its inclusion eligibility requires review.

These are source-data quality issues, not verified conclusions about the institutions.

### 8.2 Geographic and Naming Issues

The earlier review also flagged:

- Two Cuttack district-label mismatches involving Baneshwar Temple and Maa Bhatarika Mandir.
- Four repeated-name groups.
- Fourteen geographically close institution pairs.

These observations require further investigation.

Repeated names or close coordinates do not automatically establish duplicate institutions.

### 8.3 Administrative Boundary Limitations

Earlier source metadata recorded:

- 36 ADM1 administrative units.
- 736 ADM2 administrative units.

However, the downloaded ADM2 GeoJSON was recorded as containing 735 units.

This historical discrepancy remains unresolved in the source documentation.

Boundary metadata should be reconciled before the dataset is used for authoritative administrative reporting.

### 8.4 Puri and Khordha Dataset Limitations

The current Puri and Khordha inventories contain preliminary geographic candidates.

Their individual:

- Names and identifiers.
- Geographic coordinates.
- Religious institution classification.
- District alignment.
- Potential duplicates.
- Eligibility for inclusion.

require further validation.

Historical Cuttack validation results must not be generalized to these expanded district datasets.

---

## 9. Data Reuse, Licensing and Ethical Considerations

### 9.1 Geographic Data Licensing

Before redistributing source or derived geographic datasets:

- Preserve applicable source attribution.
- Confirm the licence of the exact dataset version.
- Respect ODbL attribution and share-alike obligations where applicable.
- Respect CC BY attribution requirements where applicable.
- Review CC0 status for Wikidata-sourced material.
- Review applicable Wikipedia content licensing before reuse.
- Follow Geoapify's service and attribution terms.
- Review restrictions applicable to combined or derived datasets.

The licensing information in this document reflects the historical working source register.

It is not an independent legal opinion or confirmation of redistribution clearance.

### 9.2 Institutional and Property Data Protection

Institution-linked property and asset records must remain separate from public geographic discovery information.

Responsible handling principles include:

- Do not publish private property evidence.
- Do not expose sensitive personal or account information.
- Do not publish restricted institutional records without authorization.
- Do not treat OSM points as proof of ownership.
- Do not infer encroachment from map positions alone.
- Maintain clear identification of fictional DEMO records.
- Apply approved institution-specific access restrictions to protected records.

### 9.3 Responsible Verification Labels

Recommended data labels include:

- `Provisional`
- `Preliminary`
- `Unverified`
- `Candidate`
- `DEMO — Fictional`
- `Pending Authoritative Verification`

Avoid terms such as `Government Verified`, `Legally Confirmed` or `Officially Registered` without appropriate authoritative evidence.

---

## 10. Future Data Improvement and Verification

The following activities are proposed improvements, not completed BhuGrid 1.0 capabilities.

| Priority | Proposed activity | Intended outcome |
|---|---|---|
| NOW | Reconcile Cuttack, Puri and Khordha inventories | Consistent geographic source records |
| NOW | Confirm Puri and Khordha collection dates and filtering rules | Complete provenance information |
| NOW | Validate all 239 geographic features | Expanded technical validation evidence |
| NEXT | Review institution identity and classification | Improved data reliability |
| NEXT | Investigate possible duplicates and district-alignment issues | More accurate GIS inventory |
| NEXT | Establish authoritative institutional data partnerships | Access to verified information |
| NEXT | Strengthen dataset update and review procedures | Improved data governance |
| LATER | Integrate authorized institutional and administrative datasets | More reliable institutional workflows |
| LATER | Establish repeatable data-refresh and verification procedures | Sustainable dataset maintenance |

Official verification depends on appropriate institutional access, permissions and authoritative evidence.

---

## 11. Public Documentation and Source Code Availability

**Repository Notice — Documentation Only**

This repository provides public project documentation, dataset provenance, citations, feature descriptions and high-level technical information for BhuGrid 1.0.

It is **not an open-source software repository**.

The original BhuGrid application source code, private backend implementation, credentials, restricted institutional information and deployment configuration are maintained separately.

Public access to this documentation does not grant a licence to use, reproduce, modify or redistribute the underlying application source code.

### Project Links

- **Public Documentation Repository:** https://github.com/SrustiSwarupa03/BhuGrid-1.0
- **Functional Web Application:** https://bhugrid-web-app.onrender.com/
- **Project Showcase Website:** https://bhugrid-website.onrender.com/

### Related Documentation

- [Project Overview](README.md)
- [Features, Novelty, Roles and Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Functional Web Application](WEB_APP.md)
- [Project Showcase Website](WEBSITE.md)

---

## 12. References

1. **OpenStreetMap Copyright and Attribution:** https://www.openstreetmap.org/copyright
2. **Open Database License 1.0:** https://opendatacommons.org/licenses/odbl/1-0/
3. **Overpass Turbo:** https://overpass-turbo.eu/
4. **geoBoundaries ADM1 — India:** https://www.geoboundaries.org/api/current/gbOpen/IND/ADM1/
5. **geoBoundaries ADM2 — India:** https://www.geoboundaries.org/api/current/gbOpen/IND/ADM2/
6. **DataMeet Maps Repository:** https://github.com/datameet/maps
7. **Pathways Data GeoNode:** https://geonode.pathwaysdata.com/layers/geonode
8. **Wikidata:** https://www.wikidata.org/
9. **Wikidata Query Service:** https://query.wikidata.org/
10. **Wikipedia:** https://www.wikipedia.org/
11. **Geoapify:** https://www.geoapify.com/
12. **Geoapify API Documentation:** https://apidocs.geoapify.com/

---

## Document Maintenance

This document should be updated whenever the geographic inventory, source register, collection methodology, validation results, licensing information or external service integrations change.

Dataset counts and verification claims must reflect the latest confirmed source records.

**Final Data Governance Statement:** BhuGrid 1.0 documents 239 provisional and unverified GIS features across Cuttack, Puri and Khordha, alongside three separate fictional Supabase DEMO institutions with illustrative property and asset records. These datasets support prototype-level geographic exploration and institutional management demonstrations. They do not constitute an authoritative government database, legally verified property information or proof of ownership.
