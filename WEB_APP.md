# BhuGrid 1.0 — Functional Web Application

## Access

**Web application:** https://bhugrid-web-app.onrender.com/

**Source code (original project):** https://github.com/SrustiSwarupa03/BhuGrid/tree/web-app (access depends on source repository permissions).

The web application is the **functional interactive prototype**, separate from the informational showcase website. Deployment availability can vary; no uptime guarantee is implied.

## What the application does

- Explores Odisha using an interactive GIS map with district and institution discovery.
- Displays available institution information and linked fictional DEMO property/asset records.
- Provides role-specific public/tourist, inspector and administrator interfaces.
- Supports inspection observation/evidence submission and GPS/manual location selection interfaces.
- Includes review, DEMO priority/scoring and record-print workflows.
- Integrates a Groq-powered Smart Trip Planner with suggested DEMO activities and durations.
- Integrates a Nearby Essentials Finder for provisional OSM hospitals, restaurants and fuel locations, but live Overpass retrieval has encountered HTTP 429/503 errors.
- Provides an administrator-only, read-only AI review draft from linked DEMO inspection observations; **human authorization and verification remain necessary**.

## Technical notes

- **UI:** React 19, Vite, MapLibre GL.
- **Data/auth:** Supabase JavaScript client, Supabase Auth and PostgreSQL-backed records.
- **AI integration:** Supabase Edge Functions `tourist-assist` and `admin-review-ai`.
- **Authorization:** Role-sensitive frontend views; administrative AI endpoint performs authenticated approved-admin validation.

## Safety and limitations

Records marked `DEMO` are fictional. Community geographic coordinates are not official verification. Tourist itineraries are suggestions, not verified travel routes. AI administrative drafts are advisory and do not modify official decisions. Prototype security controls are not a completed production security audit.

See [Features and Roadmap](FEATURES_AND_FUTURE_IMPLEMENTATION.md) for detailed architecture, status, novelty and future work.
