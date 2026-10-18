# PhaseKit Legacy Support Site (redirects)

The old GitHub Pages site (`https://client23.github.io/sequence-timer-support/`) was retired with
PhaseKit 3.0. Each page now only redirects to its domtelier.com equivalent:

- `index.html` -> https://domtelier.com/apps/phasekit
- `support.html` -> https://domtelier.com/apps/phasekit/support
- `privacy-policy.html` -> https://domtelier.com/apps/phasekit/privacy
- `terms.html` -> https://domtelier.com/apps/phasekit/terms
- `404.html` (any other path) -> https://domtelier.com/apps/phasekit

Keep it online: App Store listings of older versions, caches and external links still use these
URLs. Content changes belong in `site/domtelier` (`app/lib/legal.ts`), not here.
Deploy with `zsh scripts/deploy_support_site.sh` (`SUPPORT_SITE_DRY_RUN=1` first).
