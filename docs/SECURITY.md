# Security and data handling

This is a public static documentation and fictional local-practice portal. It has no authentication, access enforcement, backend, shared database, private upload storage, Discord integration, or official approval capability. Intended audience badges are informational only; hiding a link cannot protect data.

Do not put private disciplinary evidence, confidential Staff procedures, passwords, Discord bot tokens, API keys, private member information, or confidential administration records in source files, commits, local tools, exports, screenshots, or bug reports. The .gitignore is only a convenience and does not detect secrets or erase Git history. Review files and commit history before public hosting.

localStorage is not a shared database and should not be treated as WVSRC's permanent official records system. It has no integrity guarantee or confidentiality protection. Use fictional data only. Exported JSON is a local snapshot and must be handled appropriately. There are no uploads: evidence fields are plain text references, not clickable user-supplied links.

Before real use: add an authenticated backend with server-side authorization, private object storage, audit logs, retention, appeals access controls, reviewed permissions, backups, deletion workflows, and a breach-response plan. Keep provider service keys and Discord credentials server-side. Public policies and private procedures should have distinct publication pipelines.

If a secret is committed, revoke/rotate it promptly and follow the provider's remediation guidance; deleting the current file does not remove history. [SECURITY CONTACT TBD] [INCIDENT RESPONSE OWNER TBD]
