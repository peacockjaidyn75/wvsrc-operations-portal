# Version 1.0 verification

Verified November 7, 2026. Tests used fictional local examples only. The project was uploaded to [https://github.com/peacockjaidyn75/wvsrc-operations-portal](https://github.com/peacockjaidyn75/wvsrc-operations-portal) and deployed through GitHub Pages at [https://peacockjaidyn75.github.io/wvsrc-operations-portal/](https://peacockjaidyn75.github.io/wvsrc-operations-portal/).

| Check | Result and evidence |
|---|---|
| Website load | Passed in Chrome over the included local HTTP server. JSON, CSS, JS, and shield asset loaded. |
| Main navigation | Clicked all 30 navigation links; every destination displayed the expected page heading. |
| Routes and internal links | tools/check.cjs rendered 31 pages and validated 113 generated content links, including deep-link anchors. |
| Mobile navigation | Tested a 390 × 844 viewport. Menu opened, Dashboard link navigated, menu closed and aria-expanded returned false. Document scroll width did not exceed viewport width. Temporary viewport override reset afterward. |
| Layout | Desktop dashboard visually inspected; mobile dashboard inspected. Responsive grids, form columns, and table overflow styles are supplied. No exhaustive device/browser matrix was performed. |
| Global search | Searched “evidence”, selected Policies filter, and opened Evidence Preservation directly. The target policy expanded and received focus. |
| Policy disclosure | Expand all opened 20 policies; Collapse all closed all 20. |
| Clipboard | Exercised all 15 template copy controls. Staff Training Report was separately verified against the clipboard; other template headers were verified in the batch. Filled fictional training report copy contained the entered trainee value. |
| Local form drafts | Saved a fictional training form, reloaded, reopened it for editing, and copied the filled report. |
| Evidence tracker | Created a fictional case/reference; record remained after reload. Delete opened a confirmation; cancellation preserved the record. |
| Change tracker | Created a fictional draft policy change; it appeared in the record list and dashboard recent updates. |
| Discord checklist | Checked one item, reloaded, and verified 1 of 15 remained checked. Manager and approving-authority field values survived reload after autosave refinement. |
| Status badges | Policy register and seeded policies remain DRAFT. Local change statuses are expressly informational and cannot alter repository policies. |
| Print | Print button opened Chrome print preview with all 20 policies expanded in an eight-page preview. No print job was submitted. Navigation and controls were absent from the print content. Skip link was subsequently hidden in print styles. |
| Accessibility | Semantic headings, labels, native details, focus states, skip-link focus handling, mobile Escape handling, and hidden offscreen mobile navigation provided. No formal accessibility audit or assistive-technology certification performed. |
| Major policy | Structural checks confirm prominent Administration-only notices on rank, training, FTO, field-training, supervisory, and Major pages. No promotion-award logic exists. |
| Draft metadata | All 20 policies contain visible TBD metadata and proposed-draft text. All 98 distinct TBD tokens are inventoried in DECISIONS-NEEDED.md. |
| Security | No confidential records supplied or shipped. All content was generated as generic draft material. Common private-key, GitHub token, AWS access-key, and API-key patterns scan passed. This is not a comprehensive security audit. |
| Browser errors | No captured application console errors during the final browser check. |
| Deployment | Buildless repository-root GitHub Pages instructions checked against GitHub's official publishing-source documentation. |

## Reproduce structural checks

Run `node tools/check.cjs` from the project folder. This verifies JSON parsing, JavaScript syntax, unique navigation IDs, all rendered routes and generated content deep links, content counts, draft status, management ordering, Major restrictions, template presence, asset paths, and common secret patterns.

The local preview initially required a restart with permission to serve local connections. Native confirmation and print dialogs interrupted browser automation; they were observed and closed with native keyboard input. These did not reveal an application failure.

## Live deployment verification

GitHub Pages was configured to deploy from **main / (root)** with HTTPS enforced. [Initial deployment run](https://github.com/peacockjaidyn75/wvsrc-operations-portal/actions/runs/42358805666) completed successfully for source commit 4d7ffcefe43daa049f7d236e6282c24db5ff1294. All 25 uploaded source files were compared with the tested local project; content matched, with only line-ending differences.

On the live HTTPS site: dashboard, styling, content JSON and shield asset loaded under the repository subpath; an evidence search with the Policies filter produced six results; the direct Evidence Preservation link opened its policy; Staff Training Report copied to the clipboard; a checklist item survived reload and was then unchecked; and mobile navigation at 390 × 844 opened, navigated to Dashboard, and closed without horizontal overflow. The viewport override was reset afterward.

Shared records, authentication, real approvals, Discord publishing, and confidential evidence storage remain outside this static version's capabilities. Leadership decisions and policy adoption remain unresolved as documented.
