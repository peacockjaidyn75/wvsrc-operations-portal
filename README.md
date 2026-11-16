# WVSRC Operations Portal

[Open the live portal](https://peacockjaidyn75.github.io/wvsrc-operations-portal/) · [GitHub repository](https://github.com/peacockjaidyn75/wvsrc-operations-portal)

The existing live build is served over HTTPS. Repository documentation records **main / (root)** as the publishing source. Version 1.2 is the public member release.

A buildless operations portal for the West Virginia State Roleplay Community. Version 1.2 gives the six effective v5.0 member documents dedicated reading pages with section links, search and print layouts. The reading pages summarize the authorized member editions.

## Features

- Responsive navy, white, and muted gold dashboard with 12 quick-access areas.
- 30 navigation destinations, public/Staff/Command/Administration audience labels, keyboard focus, mobile menu, and print styles.
- Global multi-word search with category filters and direct links to individual policies, ranks, training modules, rules, and templates.
- 20 expandable draft staff policies with version, owner, effective date, approving authority, status, number, and last-updated fields.
- Editable Staff and LEO ranks; management sits above Administrator. Major is always an Administration-only appointment, excluded from training and normal promotion.
- Seven Staff training modules and eight ER:LC / Roblox LEO modules. These are fictional roleplay resources, not professional certification.
- Public rule summaries, onboarding, FAQs, supervisor roles, policy precedence, and a read-only document status and version register.
- 15 copyable report/form templates, editable local form drafts, evidence-reference and change trackers with JSON export, saved deployment checklist, and deletion confirmations.
- No runtime dependencies, external fonts, analytics, credentials, or build pipeline.

## Run locally

Install Node.js, then run from the repository root:

```sh
node tools/serve.cjs
```

Open http://localhost:4173. Stop with Ctrl+C. The server binds only to the local computer. Do not open index.html by double-clicking: browsers block JSON fetches on file URLs. A Python alternative is `python -m http.server 4173 --bind 127.0.0.1`.

## Project structure

```text
index.html                 Semantic application shell
.nojekyll                  Serve static files directly
.gitignore                 Excludes common private/local artifacts
LICENSE                    Rights reserved pending leadership decision
assets/css/style.css       Responsive, accessible and print styling
assets/js/app.js           Routing, search, rendering and local tools
assets/images/mark.svg     Original mountain/shield mark
data/navigation.json       Navigation groups and audience labels
data/policies.json         Draft staff policies and metadata
data/ranks.json            Editable Staff and LEO hierarchies
data/training.json         Staff and LEO curricula
data/rules.json            Summaries of the 20 effective v5.0 member rules
data/documents.json        Public-safe document status and version metadata
data/member-guides.json    On-site sections for the five member companion guides
data/templates.json        Report and deployment form fields
data/discord.json          Channel placeholders and manager checklist
data/roles.json            Supervisor and command descriptions
docs/DEPLOYMENT.md          Exact GitHub Pages instructions
docs/CONTENT-MANAGEMENT.md  Editing and approval workflow
docs/DECISIONS-NEEDED.md    Full visible TBD inventory
docs/SECURITY.md            Public hosting and restricted-data limits
docs/CONTRIBUTING.md        Contribution requirements
docs/QA.md                 Verification results and limitations
docs/SOURCE-STATUS.md      Verified references and publication gaps
tools/serve.cjs             Dependency-free local server
tools/check.cjs             Structural and content checks
```

## Edit content and placeholders

Edit UTF-8 JSON under data/. Preserve stable IDs so search deep links continue working. Update member summaries and document statuses against authorized sources. The sample staff policies remain draft. Resolve bracketed TBD values only after leadership records a decision. See [content management](docs/CONTENT-MANAGEMENT.md), [source status](docs/SOURCE-STATUS.md), and [decisions needed](docs/DECISIONS-NEEDED.md).

## Deploy to GitHub Pages

Review updates on a separate branch. Merging or pushing to the configured publishing branch can publish the update automatically. Obtain deployment authorization before merging to main or changing Pages settings. See [deployment](docs/DEPLOYMENT.md) for verification and rollback.

## Security and storage

**GitHub Pages serves all files publicly. Audience labels do not authenticate users.** Do not commit confidential procedures, private disciplinary evidence, passwords, bot tokens, API keys, member data, or administration records. This edition ships only generic draft content. WVSRC must decide which staff-facing guidance is safe for public release before publishing.

**localStorage is not a shared database and should not be treated as WVSRC's permanent official records system.** Use fictional examples only. Records live in this browser profile and origin, are not synced, and may be cleared, modified, or read by others. Exports are manual snapshots. No approval, discipline, ban, or Discord action is actually issued by the portal. Copying a template is not submitting it.

## Future authentication and database

Replace the small storage adapter in assets/js/app.js with an authenticated API. Enforce server-side role and object-level permissions before storing real records. Candidate backends include Supabase, Firebase, or PostgreSQL behind an API. Add immutable audit events, retention/deletion policies, backups and restore tests, confidential file storage, verified approvals, and access reviews. Frontend role labels alone must never authorize access. Keep secrets on the server.

## Validation

Run `node tools/check.cjs` for structural, JSON, route, template, draft-status, and Major-rule checks. See [QA](docs/QA.md) for browser verification and [source status](docs/SOURCE-STATUS.md) for publication gaps.
