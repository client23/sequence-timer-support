# PhaseKit Support Site

This folder contains the static public support website for PhaseKit.

Contents:

- `index.html`
- `support.html`
- `privacy-policy.html`
- `terms.html`
- `404.html`
- `styles.css`
- `.well-known/apple-app-site-association.sample.json`

Purpose:

- App Store support URL
- App Store privacy policy URL
- public legal and support contact pages
- source of truth for the dedicated GitHub Pages repository

Note: the migration to domtelier.com is now done. `https://domtelier.com/apps/phasekit`
is the primary marketing/company page, and `https://domtelier.com/apps/phasekit/privacy`
and `/support` are the Privacy Policy and Support URLs configured in App Store
Connect metadata (see `AppStoreMetadata.md`). Those pages are built from the separate
`site/domtelier` repository (`app/lib/legal.ts`), so privacy or terms changes
must be made there too. The GitHub Pages site below is legacy — keep it live as
a fallback, but it's no longer the URL App Store Connect metadata or in-app
links point to.

Public URLs (legacy, still deployed):

- Main support page: `https://client23.github.io/sequence-timer-support/index.html`
- Privacy policy: `https://client23.github.io/sequence-timer-support/privacy-policy.html`
- Support page: `https://client23.github.io/sequence-timer-support/support.html`
- Terms of use: `https://client23.github.io/sequence-timer-support/terms.html`

Deployment:

- deployment is manual: `zsh scripts/deploy_support_site.sh`
  (there is intentionally no CI workflow; see `scripts/README.md`)
- the script syncs this folder into the dedicated support repository
  `git@github.com:client23/sequence-timer-support.git` using your local SSH access
- `SUPPORT_SITE_DRY_RUN=1` shows the changes it would deploy (committed in a
  throwaway clone) without pushing

Local preview:

```sh
cd SupportSite
python3 -m http.server 8000
```

Then open:

- `http://localhost:8000`

Notes:

- `404.html` keeps GitHub Pages fallback behavior clean
- `.well-known/apple-app-site-association.sample.json` is a placeholder template only; it is not active until renamed and populated with real app identifiers
- update these pages together with App Store pricing, in-app purchase, or privacy-impacting feature changes
