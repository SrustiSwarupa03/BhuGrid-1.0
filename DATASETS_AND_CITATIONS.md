# BhuGrid 1.0 — Datasets, Provenance, Citations & Validation

**Updated:** 31 October 2026 · **Status:** Provisional datasets for controlled DEMO use

## 1. Scope and data governance

BhuGrid uses geographic boundary files and community-contributed point data for prototype exploration. **A mapped record is not government-verified** and must not be used to determine ownership, legal boundaries, heritage status or encroachment.

The detailed working source register is maintained in the source project's `ai-ml` branch at `data/sources.csv`. This document records the important citations and limitations without copying raw datasets into this documentation-only repository.

## 2. Processed dataset inventory

The source project records these files under `data/processed/`:

| Dataset | Recorded contents | Current status |
|---|---|---|
| `state.geojson` | 1 Odisha Polygon | Geometry-valid in Day 10 checks; authoritative boundary not independently verified |
| `districts.geojson` | 30 districts: 28 Polygon, 2 MultiPolygon | Geometry-valid; district names/boundaries still require authoritative review |
| `institutions.geojson` | 72 Cuttack OSM Point records | Provisional and unverified |
| `institutions.csv` | Tabular Cuttack institution records | Provisional; classify and reconcile as needed |
| `wikidata_institution_candidates.csv` | 17 exploratory name-filtered candidates | Research candidates, **not** verified institutions |

The files above are documented in the original BhuGrid repository, not automatically present in this new documentation repository.

## 3. Data sources and citations

| ID | Dataset / source | Licence recorded in source metadata | Citation / attribution |
|---|---|---|---|
| `OSM_CUTTACK_001` | Cuttack places of worship; retrieved 21 Oct 2026 | Open Database License (ODbL) 1.0 | © OpenStreetMap contributors — https://www.openstreetmap.org/copyright |
| `GEO_ADM1_001` | India ADM1 / Odisha state boundary; retrieved 21 Oct 2026 | Creative Commons Attribution 2.5 India (CC BY 2.5 IN) | geoBoundaries; DataMeet India community; Election Commission of India — https://www.geoboundaries.org/api/current/gbOpen/IND/ADM1/ ; underlying source https://github.com/datameet/maps |
| `GEO_ADM2_001` | India ADM2 / Odisha district geometries; retrieved 21 Oct 2026 | ODbL 1.0 | geoBoundaries; Pathways Data Pvt. Ltd.; lgdirectory.gov.in — https://www.geoboundaries.org/api/current/gbOpen/IND/ADM2/ ; source geonode.pathwaysdata.com/layers/geonode |
| `OSM-PURI-2026-10-22` | Puri places of worship; retrieved 22 Oct 2026 | ODbL 1.0 | © OpenStreetMap contributors — https://www.openstreetmap.org/copyright ; query tool https://overpass-turbo.eu/ |
| `WIKIDATA-ODISHA-2026-10-22` | Odisha exploratory Wikidata sample; retrieved 22 Oct 2026 | Creative Commons CC0 1.0 | Wikidata contributors — https://www.wikidata.org/ ; query service https://query.wikidata.org/ |

**Licence note:** This table records what the retrieved source metadata and working register state; it does not constitute an independent legal opinion or clearance of all derived-file redistribution conditions. Preserve licence notices, source attribution and any applicable share-alike requirements. Verify the current terms before redistributing datasets.

## 4. Collection and transformation lineage

- **Cuttack OSM:** 75 raw elements retrieved on 21 Oct 2026; **3 unnamed** records excluded; **72 processed** records retained. All 72 matched back to the saved raw export by stable OSM ID; processed records are marked `unverified` and `is_demo=false`.
- **Puri OSM:** 101 raw elements; 7 lacked names. Puri records were **not automatically merged** into the 72-record Cuttack processed set.
- **Wikidata:** 100 exploratory result rows, of which 17 were selected as institution-name candidates. Candidate identity remains unverified; they were **not automatically merged**.
- **Administrative boundaries:** Odisha geometry was extracted from national ADM1/ADM2 source files. Original metadata reports 36 ADM1 units. ADM2 metadata reports 736 units whereas the downloaded GeoJSON count was recorded as **735**. That mismatch remains unresolved.

## 5. Technical validation performed (29 October 2026)

| Check | Result |
|---|---|
| GeoJSON FeatureCollection parsing | Passed for state, districts and institutions |
| Total mapped features reviewed | 103 |
| Missing geometries/coordinates | 0 |
| Institution coordinates in approximate Odisha range | 72/72 |
| Duplicate institution coordinate groups | 0 |
| Polygon validity | 30 district geometries and 1 state geometry passed |
| Geometry tool | Shapely 2.1.2 |

These tests assess structural/geometric consistency, **not authoritative correctness**.

## 6. Known quality issues

- 12 Cuttack institutions have no religion tag in original OSM data.
- All 72 processed institutions currently have provisional `institution_type=other`.
- One `religion=jewish` mapping tag (Satsang Vihar Narasinghpur) requires verification; it has **not** been silently corrected.
- MS LAW UNIVERSITY was returned with `amenity=place_of_worship`; inclusion eligibility is under review.
- Two provisional Cuttack district labels differ from the processed district polygon overlay (Baneshwar Temple and Maa Bhatarika Mandir).
- Four repeated-name groups and 14 close institution pairs were flagged for investigation, **not confirmed duplicates**.
- Individual institution locations, district names and boundary alignment require authoritative validation.

## 7. Reuse and ethics

Keep DEMO property records separate from public OSM/Wikidata records. Label public mapping as provisional/unverified. Show OpenStreetMap attribution in map or data views where required. Do not publish raw private evidence or sensitive person-identifying property data. Before extending to official use, obtain authoritative data partnerships, review data rights and validate each record.

**Reference:** Source project: https://github.com/SrustiSwarupa03/BhuGrid (access subject to repository permissions). This new repository documents the datasets; it does not itself certify or redistribute them.
