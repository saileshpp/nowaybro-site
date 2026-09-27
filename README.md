# NoWayBro public site

This is the standalone local `nowaybro-site` repository for a **separate public GitHub Pages website**. It contains no FastAPI worker, n8n workflow, credential, environment file, production log, video, or job artifact. It has no build step, visitor form, analytics script, or external JavaScript. The `.gitignore` allowlists only the reviewed public files.

## Review before publishing

Review `terms.html`, `privacy.html`, and `data-deletion.html` with the NoWayBro operator. The operator name, public email, GitHub account and YouTube URL were provided by the owner. The operator is confirmed; the effective date must be set to the actual launch date before publication. Review the retention limitations and deletion workflow below before publication. Do not add TikTok or Facebook links until those accounts are verified. Check the exact Google OAuth scopes shown by the live credential's consent screen without copying tokens or secrets. This draft is not a substitute for jurisdiction-specific legal review.

The current private application has no automatic data-retention cleanup or general-purpose platform-deletion workflow. The 90-day contact, 30-day temporary-asset, and 30-day routine-backup periods are approved policy. Cleanup is operator-controlled and not automatically scheduled. The 17 historical backup directories are now classified and held; none is a routine backup eligible for automatic deletion. The first daily read-only retention review is recorded in the private operational handoff. The inactive live YouTube analytics workflow now sends the returned video ID and is prepared to read seven previously uploaded videos, but its first authenticated readback awaits separate approval. **Before using this site for YouTube developer registration, review that readback and continue the documented daily operator reviews.** The local deletion tool covers completed batch jobs; account-wide requests also require manual review of legacy jobs, n8n execution history, mailbox data and backups. In particular, review the [YouTube API Services developer policies](https://developers.google.com/youtube/terms/developer-policies). This website does not supply a server-side data-deletion callback; if a platform requires a callback instead of an instructions URL, that is a separate integration to build and review.

## Publish to GitHub Pages after review

1. In the GitHub account, verify whether the separate repository `saileshpp/nowaybro-site` exists and whether it has commits. An unauthenticated public check returned 404; this does not distinguish an absent repository from a private one. The local `origin` is already set to `https://github.com/saileshpp/nowaybro-site.git`. If the remote already has commits, fetch and review them before combining histories. Never force-push or make the private production repository public.
2. On the actual launch day, replace “Effective date: on first publication of this website.” in `terms.html` and `privacy.html` with that day’s YYYY-MM-DD date. Review the five pages and retention/deletion limitations. Inspect `git status --short --untracked-files=all`. The upload set should be only `index.html`, `terms.html`, `privacy.html`, `contact.html`, `data-deletion.html`, `assets/style.css`, `assets/favicon.svg`, `assets/logo.png`, `.nojekyll`, `.gitignore`, and `README.md`.
3. After review and approval, from this `nowaybro-site` directory, confirm the preconfigured remote, ensure the target repository is empty or its existing history has been reviewed, then commit and push without force:

   ```bash
   git add .
   git diff --cached --name-only
   git commit -m "Publish NoWayBro public site"
   git remote -v
   git push -u origin main
   ```

4. In the separate site repository, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then select **main** and **/(root)**. Save. GitHub will show the published URL, normally `https://saileshpp.github.io/nowaybro-site/`.
5. Visit all five pages and check the navigation, YouTube channel URL, contact information and mobile layout. Publishing may take several minutes. Keep the public site and private NoWayBro dashboard on separate hosts and repositories.

For a repository named `nowaybro-site`, the expected URLs are:

| Purpose | URL |
| --- | --- |
| Homepage | `https://saileshpp.github.io/nowaybro-site/` |
| Privacy Policy | `https://saileshpp.github.io/nowaybro-site/privacy.html` |
| Terms of Service | `https://saileshpp.github.io/nowaybro-site/terms.html` |
| Contact | `https://saileshpp.github.io/nowaybro-site/contact.html` |
| Data deletion instructions | `https://saileshpp.github.io/nowaybro-site/data-deletion.html` |

For a future Meta developer registration, the site supplies public Privacy,
Terms, Contact and Data Deletion Instructions pages at the URLs above. No Meta
account integration is active, so the policy says so. Check the actual Meta App
Dashboard fields before submission; this static site does not provide a data
deletion callback endpoint. If Meta requires a callback for the selected product,
build and test that separate endpoint before enabling the integration.

GitHub's current instructions: [GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart) and [creating a Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

If this site will be used as the homepage for a production Google OAuth app, review [Google's OAuth homepage policy](https://developers.google.com/identity/protocols/oauth2/policies) before submitting it. Google says that homepage must be on a verified domain under the app operator's ownership; a default `github.io` project URL may not satisfy that requirement. GitHub Pages can serve a custom domain, but domain ownership and verification are separate steps.
