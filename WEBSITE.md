# BhuGrid 1.0 — Project Showcase Website

## 1. Access and Project Links

**Live public showcase website:** https://bhugrid-website.onrender.com/

**Website source (original project):** https://github.com/SrustiSwarupa03/BhuGrid/tree/website

*Access to the source repository depends on repository permissions.*

**Functional GIS web application:** https://bhugrid-web-app.onrender.com/

**Public documentation repository:** https://github.com/SrustiSwarupa03/BhuGrid-1.0

The showcase website and functional GIS application serve different purposes and should be described separately.

## 2. Purpose

The BhuGrid showcase website is the project's **public-facing explanatory and presentation platform**.

Its purpose is to communicate the problem addressed by BhuGrid, its proposed solution, intended stakeholders, principal capabilities, technical approach and controlled prototype scope.

The website introduces BhuGrid as a GIS-based Religious Institution and Asset Management Platform designed to support the organization and geographic visualization of religious institutions and their associated properties and assets.

It also directs visitors to the functional GIS application and relevant project documentation.

The showcase website is not the operational database or the secured institutional management application. Actual application workflows and access-controlled functions are provided through the functional web application.

## 3. Intended Audience and Project Positioning

The website should communicate BhuGrid's institutional purpose and intended stakeholder groups:

1. **Local Bodies** — access to relevant institutional information and associated property and asset records.
2. **Trustees / Institutional Management** — organization and review of information relating to their assigned institutions.
3. **Government Agencies** — access to authorized institutional information for relevant administrative and governance purposes.

The platform also includes Inspector and Administrator workflows within its broader operational design.

The showcase must explain that access to operational information is intended to be restricted to administrator-authorized users and their permitted institutional assignments.

## 4. Website Content and Implementation

The original `website` branch contains a `showcase/` directory with HTML pages, stylesheets and visual assets.

The documented page structure includes:

| Page | Documented purpose |
|---|---|
| `index.html` | Main project introduction and navigation |
| `about.html` | Project background and overview |
| `problem.html` | Problem statement and challenges |
| `solution.html` | Proposed BhuGrid solution |
| `features.html` | Platform capabilities and features |
| `map.html` | Geographic and GIS-related presentation |
| `tourist.html` | Earlier tourist-oriented information |
| `admin.html` | Administrative functionality and presentation |
| `handbook.html` | User guidance and documentation |

The source structure reflects the earlier showcase organization. As the project transitions towards an institutional stakeholder model, page content, navigation and terminology should be reviewed and updated accordingly.

In particular:

- The former tourist-oriented presentation should not define the platform's primary purpose.
- Institutional stakeholder use cases should receive priority.
- Property, asset, inspection and administrative workflows should be explained accurately.
- The showcase should distinguish proposed functionality from capabilities demonstrated in the current prototype.
- Links to the functional GIS application and public documentation should remain clear and accessible.

The homepage source includes a link to the functional web application.

## 5. Presentation and Credibility Guidelines

The showcase website and its visual content should follow these guidelines:

### 5.1 Accurate Project Description

- Present BhuGrid 1.0 as a **GIS-based Religious Institution and Asset Management Platform**.
- Explain its focus on geographic institution information, linked property and asset records, inspection workflows and administrative review.
- Describe the Institutional Stakeholder Portal as the redesigned direction of the former Public/Tourist interface.
- Identify Local Bodies, Trustees / Institutional Management and Government Agencies as the intended stakeholder groups.

### 5.2 Geographic Data Transparency

- Clearly identify the current inventory of 239 geographic features as unverified GIS candidates.
- Distinguish the 72 Cuttack, 60 Puri and 107 Khordha provisional or preliminary candidates.
- Keep the three fictional Supabase DEMO institutions separate from the geographic inventory.
- Do not describe community-sourced OpenStreetMap information as an officially certified institutional register.
- Include appropriate source attribution and licensing information where geographic data is displayed.

### 5.3 Property and Asset Information

- Describe fictional property and asset records as controlled DEMO information.
- Do not portray illustrative records as actual government land or property records.
- Do not imply that mapped locations establish ownership, legal boundaries, heritage status or property rights.
- Explain that real institutional records require authorized sources and verification.

### 5.4 AI and External Services

- Present AI-assisted administrative review as preliminary and advisory.
- Make clear that administrative decisions require authorized human review.
- Describe Geoapify as the integrated provider for Nearby Essentials retrieval.
- Do not imply that Geoapify supplies BhuGrid's religious-institution inventory.
- Do not claim automated, legally valid encroachment detection or verified boundary-change identification.
- Do not publish API credentials or private integration configuration.

### 5.5 Prototype Status

- Clearly identify BhuGrid 1.0 as a controlled educational and competition prototype.
- Avoid claims of government endorsement, official land-record certification or statewide operational deployment.
- Do not present planned roadmap capabilities as completed features.
- Ensure screenshots, videos and demonstrations reflect the current application direction.

## 6. Relationship Between the Showcase Website and Functional Application

| Aspect | Showcase Website | Functional GIS Web Application |
|---|---|---|
| Primary purpose | Project explanation and presentation | GIS-based institutional information and management workflows |
| Main audience | Public visitors, evaluators and project stakeholders | Administrator-authorized users and permitted institutional stakeholders |
| Content | Project overview, problem, solution, features and guidance | Geographic information, linked records, inspections and administrative functions |
| Access | Public-facing explanatory content | Controlled authentication and authorization |
| Data handling | Presentation-oriented information | Application records and associated operational workflows |
| Main role | Communicate the project | Demonstrate and support the platform's functional capabilities |

The showcase website complements the functional application. It does not replace authentication, database access controls or secured institutional workflows.

## 7. Maintenance and Future Improvements

Future website maintenance should focus on:

- Updating the homepage and project overview to reflect the institutional GIS and asset-management direction.
- Revising earlier tourist-oriented content and navigation where appropriate.
- Highlighting Local Bodies, Trustees / Institutional Management and Government Agencies as intended stakeholders.
- Explaining Inspector and Administrator workflows accurately.
- Keeping feature descriptions consistent with the deployed functional application.
- Updating geographic dataset counts and verification labels when the underlying data changes.
- Maintaining appropriate attribution and source references.
- Reviewing screenshots, diagrams, visual assets and user guidance after significant application changes.
- Checking application and documentation links periodically.
- Avoiding the publication of private implementation details, credentials or sensitive operational information.

## 8. Maintainer Responsibility

**Maintainer area:** Project showcase website, visual content, presentation materials and user-facing documentation.

**Team contribution:** Smruti.

Website content and presentation should remain consistent with the approved BhuGrid 1.0 project scope and the latest functional application changes.

## 9. Related Public Documentation

- [Features, Novelty, Roles, Security & Future Implementation](FEATURES_AND_FUTURE_IMPLEMENTATION.md)
- [Datasets and Citations](DATASETS_AND_CITATIONS.md)
- [Web Application](WEB_APP.md)

**Project links:**

- Showcase Website: https://bhugrid-website.onrender.com/
- Functional GIS Web Application: https://bhugrid-web-app.onrender.com/
- Public Documentation Repository: https://github.com/SrustiSwarupa03/BhuGrid-1.0

**Documentation note:** The public documentation repository is intended for project documentation. It does not publish or license the private application source code, backend implementation, credentials or private deployment configuration.
