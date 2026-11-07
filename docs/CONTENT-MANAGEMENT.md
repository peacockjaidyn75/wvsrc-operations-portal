# Content management

All seeded policy and rule content is DRAFT. The owner must approve the actual wording, authority, dates, and publication scope before adoption. No content is marked Approved or Published by default.

## Files

- policies.json: add unique id, number, title, version, effectiveDate, status, owner, approvingAuthority, lastUpdated, and full text. Multi-paragraph strings may use escaped newline characters.
- ranks.json: arrays are ordered highest to lowest. Keep management above Administrator. Department titles may change; Major must retain the Administration-only restriction everywhere.
- training.json: edit module titles, topics, exercise, and completion criteria. Major is excluded from all training and promotional paths.
- rules.json: public-facing rules only; never include restricted enforcement procedures here.
- templates.json: fields define both copy output and the editable local form. Keep IDs stable. Editing field order can make older local form drafts incompatible; export before changing and clear incompatible drafts afterward.
- discord.json: edit channel plan, warnings, and checklist. Checklist changes can invalidate saved checkbox positions; reset local checklists after changes.
- roles.json and navigation.json: role scope and intended audience labels. Labels never enforce access.

Interface-level operational summaries, Major notices, precedence, search index generation, and form schemas live in assets/js/app.js. Styling lives in assets/css/style.css. Use text only in JSON fields; all content is HTML-escaped. No raw HTML is rendered from content files.

## Review and approval

1. Draft the change and keep explicit TBDs for unresolved decisions.
2. Obtain independent review and confirm policy precedence.
3. Record the actual approving authority, approval reference, effective date, and version in an authorized records system.
4. Only after authorization, update the repository status and metadata. Valid statuses: DRAFT, UNDER REVIEW, PENDING COMMAND APPROVAL, PENDING ADMINISTRATION APPROVAL, APPROVED, PUBLISHED, SUPERSEDED, REJECTED.
5. Publish prospectively after authorized adoption. Keep an appropriate authorized archive and changelog.

Local change tracker statuses are practice labels. They do not modify policy JSON, create real approvals, or publish documents.

## Checks

Run node tools/check.cjs. Review search deep links, mobile layout, copy output, and print preview after changes. Expand details to review full draft text. Search is derived from JSON at page load, so no separate index build is necessary.

## Storage adapter

Local keys use wvsrc:v1: plus drafts, evidence, changes, or deployment. The store.read/store.write adapter centralizes persistence for a future API. Draft data is not uploaded and there is no automatic retention, backup, sync, import, or authentication. Evidence and change records can export JSON. Form drafts can be copied individually. Do not store actual private records.
