# PermitPath — legal and support pages

The hosted privacy policy, support page and terms of use for the PermitPath iOS app.

Published at **https://qadanm.github.io/permitpath-legal/**

## Why this repo exists

App Store Connect requires a publicly reachable HTTPS privacy policy URL and a
support URL, both working without a login. The app repository is private (and
should stay that way), so the pages live here in a small public repo of their own.

Plain static HTML plus one stylesheet. No dependencies, no build step — a legal
page that stops rendering because a toolchain moved is a compliance problem, not a
cosmetic one.

## Pages

| Path | Purpose |
|---|---|
| `/` | Privacy policy |
| `/support.html` | Support, corrections, purchases, data deletion |
| `/terms.html` | Terms of use, licence, no-pass-guarantee |

## Before submitting to App Review

Two owner-only placeholders remain, marked in the page as `[LIKE THIS]`:

- `[LEGAL ENTITY / INDIVIDUAL OWNER]`
- `[ADDRESS]`

Everything else is real: support address, effective date (6 November 2026),
version 1.0, and the published URL.

`index.html` states this openly in a callout so nobody mistakes a draft for a
finished policy. Remove that callout once the two fields are filled.

## What the pages claim, and why

Each statement was checked against the shipped build, not assumed:

- **No account, no advertising SDK, no third-party analytics, no developer server** —
  confirmed by source review; the app has a no-op analytics implementation.
- **Study data stays on the device** — `StudyStore` is local SQLite in the app
  container.
- **Purchases go through Apple** — StoreKit 2, verified transactions only, no
  entitlement boolean in defaults.
- **Settings → Delete local progress** — this path exists and is tested.
- **Not affiliated with the California DMV** — stated in the app, the store
  metadata and here.
- **Narration is not enabled** — recorded in the privacy policy because the
  narration feature is parked for this release, so no study content is sent to any
  speech service.

## Updating

Edit the HTML here, commit to `main`. GitHub Pages serves `main` directly.

If a future app version adds an analytics vendor, a support form, cloud sync or a
network speech service, update `index.html` **before** that build ships — the
policy currently states none of those exist.
