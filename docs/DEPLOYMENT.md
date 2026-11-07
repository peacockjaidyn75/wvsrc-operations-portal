# GitHub Pages deployment

Current live site: [WVSRC Operations Portal](https://peacockjaidyn75.github.io/wvsrc-operations-portal/)

Repository: [peacockjaidyn75/wvsrc-operations-portal](https://github.com/peacockjaidyn75/wvsrc-operations-portal)

Configured source: **Deploy from a branch → main → /(root)**. HTTPS is enforced. Commits to main automatically trigger publication.

1. Review docs/SECURITY.md and decide which draft material may be public. Replace only decisions leadership has finalized; preserve unresolved placeholders.
2. Create a GitHub repository, for example wvsrc-operations-portal. GitHub Pages availability for private repositories depends on your plan; published site access is a separate issue. This project assumes public static hosting.
3. Upload the contents of this folder, including index.html, assets/, data/, .nojekyll, tools/, and docs/. Do not upload a wrapping folder or the delivery ZIP as the website. Include dotfiles. Use main as the branch.
4. Open **Settings → Pages → Build and deployment**.
5. Under Source, select **Deploy from a branch**.
6. Select branch **main** and folder **/(root)**, then **Save**.
7. Wait for the Pages deployment to succeed in GitHub's Actions/Pages interface. Open the site URL GitHub displays, usually https://YOUR-ACCOUNT.github.io/wvsrc-operations-portal/.
8. Verify dashboard, search, a template copy, direct hash link, mobile navigation, and JSON loads. All asset paths are relative and routes use hashes, so repository subpaths work without rewrites.

No build command, package installation, server, API key, or Actions workflow is needed. Never select /docs: the entry point is in the repository root. A local preview server is not part of the hosted deployment.

## Updates and rollback

Edit content through reviewed commits or pull requests to main. Pages republishes after commits. Record policy adoption separately; pushing a draft does not authorize it. To roll back, revert the problematic commit and wait for deployment. Browser local drafts are not versioned by Git and do not synchronize between localhost and the Pages origin.

## Troubleshooting

- Blank/error content: verify data/ JSON files are present and valid; open over HTTP, not file://.
- Missing styling: verify assets/ was uploaded with the same case and directory names.
- 404: confirm main, /(root), index.html, deployment status, and the full repository URL.
- Old content: wait for the deploy to finish, then refresh. This portal has no service worker.
- Clipboard blocked: try HTTPS or localhost, or manually copy the displayed template.

GitHub's official setup reference: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
