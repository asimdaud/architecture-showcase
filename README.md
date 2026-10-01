# Architecture Showcase

Engineering write-ups of four systems I have designed and shipped. The source repositories are private (client work, live business data, or unreleased); each write-up here describes the architecture, the integrations, the decisions and trade-offs, how it was tested, and its known limits.

Each one follows the same structure: summary, constraints, architecture, integrations, data model, design decisions (with alternatives rejected), one integration or data-quality problem told as a Situation / Task / Action / Result story, testing, security and deployment, one code excerpt, and limitations.

| System | What it is | Backend / integration focus |
|---|---|---|
| [Recepto: AI receptionist backend](recepto-ai-receptionist-backend/) ([live](https://receptio-v3.vercel.app)) | Multi-tenant FastAPI service where a business configures an agent that answers, books, takes orders and escalates | Tool-calling agent loop, multi-provider LLM chain with circuit breaker, hybrid retrieval, import pipeline (JSON/CSV/PDF/URL), output guards, Postgres/SQLAlchemy |
| [Wholesale sourcing pipeline](wholesale-sourcing-integration-pipeline/) | Tool that decides which wholesale products are safe to buy for Amazon FBA | Multiple supplier connectors behind one sync pipeline, Amazon SP-API enrichment, reconciling contradictory upstream data, rule-based decision engine, audit log, RBAC |
| [Floorplan Takeoff: estimating engine](floorplan-takeoff-estimating-engine/) ([live](https://floorplan-takeoff.vercel.app)) | Browser-based construction takeoff and estimating tool, no backend | Client-side architecture, IndexedDB persistence, pure-logic pricing and geometry layer, config-driven trade packs, unit plus Playwright testing |
| [Travel agency CMS platform](travel-agency-cms-platform/) ([live](https://travelways.pk/)) | Production Next.js site with an owner-run admin panel, live in production | Admin publish pipeline via GitHub Contents API, signed stateless sessions, third-party data integrations, CI jobs (IndexNow, weekly SEO report) |

## Reading order for a backend / integration role

1. **Recepto**: API design, orchestration, and failure handling.
2. **Wholesale sourcing pipeline**: integrating disparate external systems and reconciling data that disagrees.
3. Floorplan Takeoff and the CMS platform for breadth.

## About

Muhammad Asim, full-stack software engineer (Python/FastAPI, React/Next.js, AWS), based in Greater Manchester.
[Portfolio](https://asimdaud-portfolio.web.app) · [LinkedIn](https://linkedin.com/in/asim9) · asim.scorpio9@gmail.com

All content is © Muhammad Asim, all rights reserved. Shared for review; please don't reuse without permission.
