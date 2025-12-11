# Architecture Overview

## System Components
- **Frontend**
  - Built with JavaScript/TypeScript (.js, .ts, .json configs).
  - Bundled and deployed using `npm run build` commands.
  - Hosted on **Google Cloud** (static hosting + CDN).
  - Provides tribe‑specific negotiation workflows and dashboards.

- **Backend**
  - Node.js/TypeScript services.
  - REST/GraphQL APIs for authentication, negotiation flows, tribe templates, and audit logs.
  - Built and deployed using `npm run` scripts.
  - Hosted on **Google Cloud** (App Engine / Cloud Run).
  - Integrates with notification services (email/SMS/push).

- **Database**
  - **MongoDB Atlas** cluster.
  - Collections: Users, Families, Tribes, Negotiations, LineItems, Invitations, Events (audit), Messages.
  - Indexed for fast retrieval of negotiation records and tribe templates.

## Data Flow
1. Groom family submits **Letter of Intent** via frontend → backend API.
2. Backend stores negotiation record in MongoDB.
3. Bride family receives notification and sets negotiation date.
4. Tribe template applied (Ndebele, Zulu, Pedi, Shona, Xhosa, Tswana).
5. Negotiation updates tracked in MongoDB with immutable event log.
6. Final agreement exported to PDF and archived not yet in place

## Deployment Pipeline
- **Build:** `npm run build` for frontend and backend.
- **Test:** Unit + integration tests run before deploy.
- **Deploy:** Google Cloud CI/CD pushes builds to hosting services.
- **Monitor:** Logs and metrics collected via Google Cloud Monitoring.

## Security
- Role‑based access control (Bride family, Groom family).
- Encrypted sensitive fields in MongoDB.
- Tokenized invitation links with expiry.
- Audit trail for all negotiation changes.

## Roadmap
- Add analytics dashboard (negotiation duration, common line items).
- Localization improvements for tribe templates.
- Enhanced PDF export with signatures.
- Accessibility and offline support.
