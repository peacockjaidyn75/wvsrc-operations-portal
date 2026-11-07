# Recommended next version

1. Adopt the content: resolve the decision inventory, approve actual rules and policy wording, name owners, define authorization limits, and record versions/effective dates. Decide what Staff guidance may be published publicly.
2. Add authentication and enforce role permissions on the server. Separate public member information from confidential Staff, Command, and Administration systems. Keep Major an Administration-only appointment.
3. Add a shared records service using Supabase, Firebase, or an API backed by PostgreSQL. Design case IDs, validation, role/object permissions, immutable audit history, and concurrent-edit handling before importing real records.
4. Add restricted evidence storage with source and chain-of-custody metadata, reviewed retention periods, redaction tracking, backups, and tested restore/deletion procedures.
5. Implement verified approval workflows and prospective policy publication, with authorized reviewers and auditable decisions. Local status labels must not become proof of approval.
6. Track training assignments, evaluations, corrective coaching, and completion reviews. Keep all Major appointments outside automated training/promotion logic.
7. Add a controlled Discord integration only after permissions and approval requirements are finalized. Keep bot credentials on the server and require authorized publication.
8. Expand browser/device and accessibility testing, add schema validation and continuous checks, and provide secure export/import and records migration tooling.

These recommendations do not require any provider account or secret for version 1.0.
