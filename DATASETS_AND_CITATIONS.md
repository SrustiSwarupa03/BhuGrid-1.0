# BhuGrid 1.0 — Datasets, Provenance, Citations & Validation

**Last Updated:** 16 November 2026  
**Project:** BhuGrid 1.0  
**Document Status:** Updated for Public Documentation Repository  
**Dataset Status:** Provisional, preliminary and unverified GIS data for controlled prototype demonstration and exploration

---

## 1. Purpose and Data Governance

BhuGrid 1.0 uses geographic administrative boundaries and community-contributed geographic point records to support GIS-based exploration of religious institutions across Odisha.

The current documented geographic coverage includes:

- Cuttack district
- Puri district
- Khordha district

The platform distinguishes between publicly sourced geographic discovery records and separately maintained fictional demonstration records.

**Important data governance principle:** The presence of a geographic feature on the BhuGrid map does not establish that the institution, property, ownership, boundary, land classification or heritage status has been officially verified.

OpenStreetMap (OSM) records and other exploratory geographic candidates are provisional reference information. They must not be treated as government-certified institutional records, cadastral information, legal property evidence or proof of encroachment.

BhuGrid is intended to support institutional information management and GIS-based administrative workflows. Official operational use requires authoritative source partnerships, appropriate permissions and independent verification.

### Repository and Source Data Separation

This repository, [BhuGrid-1.0](https://github.com/SrustiSwarupa03/BhuGrid-1.0), is the public documentation and project-information repository.

It does not contain the original application's source code, private backend implementation, database credentials, unrestricted internal datasets or deployment configuration.

The detailed dataset inventory, working source register and processing records are maintained separately in the private development repository, particularly:

- `data/sources.csv`
- `data/processed/`
- Associated dataset collection and validation records

These source files are not automatically included in this public documentation repository.

---

## 2. Current GIS Dataset Inventory

The current BhuGrid 1.0 GIS inventory covers three districts of Odisha.

### 2.1 Geographic Dataset Summary

| Geographic coverage | Dataset | Recorded features | Current status |
|---|---|---:|---|
| Cuttack | OpenStreetMap institution points | 72 | Provisional and unverified |
| Puri | Preliminary OpenStreetMap institution candidates | 60 | Preliminary and unverified |
| Khordha | Preliminary OpenStreetMap institution candidates | 107 | Preliminary and unverified |
| **Total** | **Combined geographic features** | **239** | **Unverified GIS records** |

**Total documented geographic features: 239.**

These records are intended for prototype-level geographic discovery and visualization. Their inclusion does not establish that every feature is an eligible religious institution or an officially recognized institutional entity.

### 2.2 Dataset Details

**A. Cuttack — 72 Provisional OSM Records**

- Source: OpenStreetMap.
- Collection date recorded in the earlier source register: 21 October 2026.
- Original retrieval: 75 raw elements.
- Three unnamed records were excluded during processing.
- Seventy-two named records were retained.
- Processed records were matched against the saved raw export using stable OSM identifiers.
- Records were marked as unverified.
- Original processing metadata recorded `is_demo=false`.
- Institution classification and individual record verification remain pending.

**B. Puri — 60 Preliminary OSM Candidates**

- Source: OpenStreetMap.
- Recorded inventory: 60 preliminary geographic candidates.
- Intended use: Geographic discovery and preliminary institutional mapping.
- Records remain unverified.
- Eligibility, classification, naming and location accuracy require further review.

The earlier Puri exploratory extraction recorded 101 raw elements, including seven without names. However, that historical extraction should not automatically be treated as the processing lineage of the current 60-record inventory.

The updated collection snapshot, retrieval date, filtering rules and retained OSM identifiers must be confirmed against the latest private source register.

**C. Khordha — 107 Preliminary OSM Candidates**

- Source: OpenStreetMap.
- Recorded inventory: 107 preliminary geographic candidates.
- Intended use: Geographic discovery and preliminary institutional mapping.
- Records remain unverified.
- Individual institution identity, geographic accuracy and classification require further validation.

The precise retrieval date, original raw element count, filtering criteria and OSM identifier reconciliation details should be confirmed from the latest source register before publication of more detailed collection statistics.

### 2.3 Important Dataset Interpretation

The combined count of 239 represents the current documented geographic inventory.

It does not represent:

- 239 government-verified religious institutions.
- 239 legally recognized institutional entities.
- 239 verified properties or land parcels.
- 239 officially registered assets.
- 239 completed administrative records.

The dataset should therefore consistently be described as **239 provisional and unverified GIS features**.

---

## 3. Separate Fictional DEMO Institution Records

In addition to the geographic discovery datasets, BhuGrid maintains three separate fictional demonstration institutions in its Supabase-backed prototype environment.

These records are intended to demonstrate the application's institutional information-management workflows.

They are not part of the 239 public geographic candidate count.

### 3.1 Purpose of DEMO Records

The three fictional institutions support controlled demonstrations of:

- Institution information management.
- Linked property records.
- Asset registration and management.
- Institutional record navigation.
- Inspector workflows.
- Inspection evidence submission.
- Administrative review and approval workflows.
- Historical record management.

### 3.2 Separation from Public GIS Data

| Characteristic | Public geographic records | DEMO institution records |
|---|---|---|
| Origin | Community-contributed geographic sources | Fictional demonstration data |
| Primary purpose | GIS discovery and visualization | Application workflow demonstration |
| Verification | Provisional and unverified | Explicitly fictional |
| Property ownership evidence | Not established | Not legally representative |
| Administrative status | Not government-certified | Demonstration only |
| Storage | Source-controlled GIS datasets | Supabase application environment |

**Important:** Public OSM geographic candidates must not be silently converted into verified institutional, property or asset records.

Likewise, fictional DEMO records must never be represented as actual government institutions, registered properties or genuine ownership information.

---

## 4. Data Sources, Provenance and Citations

BhuGrid uses third-party geographic information sources and external service integrations.

The following register documents the principal sources and their known attribution requirements.

### 4.1 Geographic Data Sources

| Source ID | Dataset / Source | Recorded retrieval date | Licence recorded in source metadata |
|---|---|---|---|
| `OSM_CUTTACK_001` | Cuttack places of worship | 21 October 2026 | Open Database License (ODbL) 1.0 |
| `OSM-PURI-2026-10-22` | Puri places of worship exploratory extraction | 22 October 2026 | ODbL 1.0 |
| `OSM_KHORDHA_001` | Khordha preliminary institution candidates | To be confirmed | To be confirmed |
| `GEO_ADM1_001` | India ADM1 / Odisha state boundary | 21 October 2026 | CC BY 2.5 IN |
| `GEO_ADM2_001` | India ADM2 / Odisha district geometries | 21 October 2026 | ODbL 1.0 |
| `WIKIDATA-ODISHA-2026-10-22` | Exploratory Odisha Wikidata sample | 22 October 2026 | CC0 1.0 |

The Khordha source identifier and licence information must be reconciled with the latest source register before final publication.

### 4.2 OpenStreetMap Attribution

Cuttack, Puri and Khordha geographic discovery records are associated with OpenStreetMap community-contributed geographic information.

The required attribution is:

**© OpenStreetMap contributors**

Official attribution and copyright information:

https://www.openstreetmap.org/copyright

OpenStreetMap data is made available under the Open Database License (ODbL).

https://opendatacommons.org/licenses/odbl/1-0/

Original geographic queries and exploratory extraction can be performed through:

https://overpass-turbo.eu/

Where OSM-derived data is displayed or redistributed, applicable attribution and share-alike requirements must be respected.

### 4.3 Administrative Boundary Sources

The administrative boundary datasets were obtained through geoBoundaries and associated source metadata.

**Odisha State Boundary — ADM1**

- Source: geoBoundaries.
- Associated source attribution: DataMeet India community and Election Commission of India.
- Recorded licence: CC BY 2.5 IN.
- Reference:

https://www.geoboundaries.org/api/current/gbOpen/IND/ADM1/

Underlying source repository:

https://github.com/datameet/maps

**Odisha District Boundaries — ADM2**

- Source: geoBoundaries.
- Associated source metadata: Pathways Data Pvt. Ltd. and Local Government Directory.
- Recorded licence: ODbL 1.0.
- Reference:

https://www.geoboundaries.org/api/current/gbOpen/IND/ADM2/

Associated source:

https://geonode.pathwaysdata.com/layers/geonode

These boundary datasets support geographic visualization and administrative grouping. Their appearance in BhuGrid does not establish official legal boundary verification.

### 4.4 Wikidata Exploratory Source

An earlier exploratory Odisha dataset was collected from Wikidata.

- Source: Wikidata.
- Recorded retrieval date: 22 October 2026.
- Original exploratory result: 100 rows.
- Selected institution-name candidates: 17.
- Recorded licence: CC0 1.0.
- Query service:

https://query.wikidata.org/

Source website:

https://www.wikidata.org/

The 17 selected records remain research candidates and must not be represented as verified institutions.

They are not included in the current 239-feature geographic inventory unless separately reconciled with the latest district datasets.

---

## 5. External Service Integration — Geoapify

BhuGrid's Nearby Essentials functionality uses the Geoapify Places API as an alternative nearby-place retrieval service.

This integration supports the discovery of relevant nearby facilities, including categories such as:

- Hospitals and healthcare facilities.
- Restaurants.
- Petrol pumps and fuel stations.
- Other supported nearby essential-place categories.

The integration was introduced to address recurring OpenStreetMap Overpass API availability and retrieval failures affecting Nearby Essentials.

### 5.1 Role of Geoapify

Geoapify is an external location and places service integration. It is not the authoritative source of BhuGrid's religious institution inventory.

Its role is distinct from the three-district geographic dataset inventory.

| Component | Purpose |
|---|---|
| OpenStreetMap | Geographic discovery records and mapped features |
| geoBoundaries | Administrative boundary geometries |
| Wikidata | Exploratory research candidates |
| Geoapify Places API | Nearby Essentials retrieval |
| Supabase | Application database and demonstration record management |

### 5.2 Attribution and Usage Requirements

Geoapify attribution must be displayed wherever required by the applicable service plan, API terms and attribution conditions.

Official references:

- Geoapify: https://www.geoapify.com/
- Geoapify Documentation: https://apidocs.geoapify.com/

API credentials must remain protected in the application's approved backend configuration and must not be included in this public documentation repository.

Geoapify results are external place-discovery information and must not automatically be interpreted as verified institutional or property records.

---

## 6. Collection, Filtering and Transformation Lineage

The geographic inventory has been assembled from external geographic information sources and processed for prototype visualization.

The available historical processing records establish the following details.

| Processing activity | Recorded information |
|---|---|
| Cuttack OSM extraction | 75 raw elements retrieved |
| Cuttack filtering | 3 unnamed records excluded |
| Cuttack processed inventory | 72 records retained |
| Cuttack identity reconciliation | 72 records matched using stable OSM identifiers |
| Puri earlier extraction | 101 raw elements retrieved |
| Puri earlier filtering | 7 unnamed records identified |
| Puri current documented inventory | 60 preliminary candidates |
| Khordha current documented inventory | 107 preliminary candidates |
| Wikidata exploration | 100 exploratory rows; 17 candidates selected |
| Administrative boundary processing | State and district GeoJSON datasets extracted |

The earlier Puri extraction statistics are historical processing information and should not be used to infer the exact lineage of the current 60-record inventory.

The latest collection and filtering details for Puri and Khordha must be confirmed from the private source project's `data/sources.csv` and associated processing records.

### 6.1 General Processing Principles

The processing workflow should preserve:

1. Original source attribution.
2. Stable source identifiers wherever available.
3. Original source tags and relevant metadata.
4. Collection and retrieval dates.
5. Filtering and exclusion information.
6. Verification status.
7. Separation of source data from fictional DEMO records.

Where source information is incomplete, the resulting record must remain provisional rather than being silently classified as verified.

---

## 7. Technical Validation and Data Quality

Earlier validation activities were performed on the available Cuttack institution and administrative boundary datasets.

The following results were recorded during the 29 October 2026 validation checks.

### 7.1 Historical Validation Results

| Validation check | Recorded result |
|---|---|
| GeoJSON FeatureCollection parsing | PASS |
| Total mapped features reviewed | 103 |
| Missing geometries / coordinates | 0 |
| Institution coordinates within approximate Odisha geographic range | 72/72 |
| Duplicate institution coordinate groups | 0 |
| District polygon geometry validity | 30 passed |
| State polygon geometry validity | 1 passed |
| Geometry validation library | Shapely 2.1.2 |

These results relate to the datasets examined during the original validation exercise.

**They must not be interpreted as validation results for all 239 current geographic features.**

The expanded Puri and Khordha inventory requires corresponding validation evidence before the same checks can be reported as completed for the full dataset.

### 7.2 What These Checks Establish

The historical checks assess:

- GeoJSON structural consistency.
- Geometry parsing.
- Coordinate availability.
- Approximate geographic plausibility.
- Polygon geometry validity.
- Duplicate coordinate groups within the reviewed dataset.

They do not independently establish:

- Correct institution identity.
- Official religious classification.
- Property ownership.
- Legal administrative boundaries.
- Cadastral accuracy.
- Government registration.
- Heritage status.
- Encroachment or land-use violations.

Geometric validity and authoritative geographic correctness are different concepts.

---

## 8. Known Data Quality Issues and Limitations

The following issues were identified in earlier dataset review activities and should remain visible in the project's documentation until resolved.

### 8.1 Institution Classification

- Twelve previously reviewed Cuttack institutions had no religion tag in the original OSM records.
- All 72 processed Cuttack institutions were provisionally assigned `institution_type=other` in the earlier processing record.
- One `religion=jewish` mapping tag associated with Satsang Vihar Narasinghpur requires further verification.
- MS LAW UNIVERSITY was returned with `amenity=place_of_worship`; its inclusion eligibility remains under review.

### 8.2 Geographic and Naming Issues

- Two provisional Cuttack district labels differed from the processed district polygon overlay: Baneshwar Temple and Maa Bhatarika Mandir.
- Four repeated-name groups were flagged for investigation.
- Fourteen close institution pairs were flagged for investigation.
- These groups are potential data-quality issues, not confirmed duplicate institutions.

### 8.3 Administrative Boundary Limitations

Earlier source metadata recorded:

- 36 ADM1 administrative units.
- 736 ADM2 administrative units.

However, the downloaded ADM2 GeoJSON was recorded as containing 735 units.

This discrepancy remains unresolved in the historical source documentation.

The administrative boundary datasets therefore require further source-level reconciliation before being used for authoritative administrative reporting.

### 8.4 Expanded District Dataset Limitations

The expanded inventory of Puri and Khordha introduces additional geographic candidates.

Their individual identity, naming, classification, coordinates and administrative alignment require validation.

The historical Cuttack validation results must not be generalized to the expanded inventory without additional evidence.

---

## 9. Data Reuse, Licensing and Ethical Considerations

BhuGrid follows a separation-based approach to geographic information management.

### 9.1 Dataset Licensing

Before redistributing any source or derived geographic dataset:

- Preserve applicable attribution notices.
- Review the source licence.
- Respect ODbL share-alike obligations where applicable.
- Respect CC BY attribution requirements where applicable.
- Review third-party API terms and usage restrictions.
- Verify the licensing status of each dataset independently.

The licence information in this document reflects the earlier working source register and recorded source metadata. It is not an independent legal opinion or confirmation of redistribution clearance.

### 9.2 Protection of Property and Institutional Information

The application may contain institution-linked property and asset information.

Such records must be handled separately from public geographic discovery datasets.

The following principles apply:

- Do not publish private property evidence.
- Do not expose sensitive person-identifying information.
- Do not publish private institutional records without authorization.
- Do not treat OSM points as proof of ownership.
- Do not infer encroachment from mapped boundaries alone.
- Maintain separation between fictional demonstration records and genuine institutional information.
- Restrict institution-linked records according to approved access-control policies.

### 9.3 Responsible Geographic Information Use

Geographic records must be presented with clear verification labels.

Recommended terminology:

- `Provisional`
- `Preliminary`
- `Unverified`
- `Candidate`
- `DEMO — Fictional`
- `Pending Authoritative Verification`

Avoid terms such as `Government Verified`, `Legally Confirmed` or `Officially Registered` unless supported by appropriate authoritative evidence.

---

## 10. Future Data Improvement and Verification

The following activities are recommended for improving BhuGrid's geographic data quality.

| Priority | Proposed activity | Expected outcome |
|---|---|---|
| NOW | Reconcile Cuttack, Puri and Khordha source inventories | Consistent geographic inventory |
| NOW | Confirm collection dates and filtering details for Puri and Khordha | Complete provenance records |
| NOW | Validate all 239 geographic features | Expanded structural and geographic validation evidence |
| NEXT | Review institution names and classification | Improved institutional data quality |
| NEXT | Resolve potential duplicate and district-alignment issues | More reliable GIS records |
| NEXT | Establish authoritative source partnerships | Better-supported institutional information |
| LATER | Integrate authorized administrative and institutional datasets | Improved administrative reliability |
| LATER | Establish a repeatable data-update and verification process | Sustainable data governance |

These are proposed improvement activities, not claims of completed implementation.

---

## 11. Public Documentation and Source Code Availability

This document belongs to the public BhuGrid-1.0 documentation repository.

**Repository Notice — Documentation Only**

This repository provides project documentation, dataset provenance information, citations, feature descriptions and technical overviews.

It is not an open-source software repository.

The original BhuGrid application source code, private backend implementation, database credentials, sensitive records and deployment configuration are maintained separately and are not released through this repository.

Public documentation does not grant permission to reproduce, modify or redistribute the underlying application source code.

### Project Links

- **Public Documentation Repository:** https://github.com/SrustiSwarupa03/BhuGrid-1.0
- **Original Development Repository:** https://github.com/SrustiSwarupa03/BhuGrid
- **Live Web Application:** https://bhugrid-web-app.onrender.com/
- **BhuGrid Showcase Website:** https://bhugrid-website.onrender.com/

---

## 12. References

1. OpenStreetMap Copyright and Attribution: https://www.openstreetmap.org/copyright
2. Open Database License 1.0: https://opendatacommons.org/licenses/odbl/1-0/
3. Overpass Turbo: https://overpass-turbo.eu/
4. geoBoundaries ADM1 — India: https://www.geoboundaries.org/api/current/gbOpen/IND/ADM1/
5. geoBoundaries ADM2 — India: https://www.geoboundaries.org/api/current/gbOpen/IND/ADM2/
6. DataMeet Maps Repository: https://github.com/datameet/maps
7. Wikidata: https://www.wikidata.org/
8. Wikidata Query Service: https://query.wikidata.org/
9. Geoapify: https://www.geoapify.com/
10. Geoapify API Documentation: https://apidocs.geoapify.com/

---

**Document Maintenance**

This document should be updated whenever the underlying geographic dataset inventory, collection methodology, attribution requirements, validation results or external data integrations change.

Dataset counts and validation claims must always reflect the latest confirmed source records.

**Final Data Governance Statement:** BhuGrid 1.0 currently documents 239 provisional and unverified geographic features across Cuttack, Puri and Khordha, alongside three separate fictional Supabase DEMO institutions. These datasets support prototype-level GIS exploration and institutional asset-management demonstrations. They do not constitute an authoritative government database or legally verified property information.
