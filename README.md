# DateAnalyze feedback assets

Storage-only repo for photos users attach to in-app **Send feedback** in the
[Us date tracker](https://github.com/tzoororg/DateAnalyze).

The `dateanalyze-feedback` Cloudflare Worker commits each validated JPEG to
`feedback-assets/<uuid>.jpg` and embeds the raw URL in the feedback GitHub issue
it opens on the app repo.

## Why this repo exists separately

The worker's write token used to have Contents write access on the app repo —
which is also the GitHub Pages deployment, so anyone who extracted the client-side
feedback key could have published arbitrary files to the app's own domain.
Photos were moved here so that token can no longer touch the deployed site.
(PRODUCTION_PLAN.md §1.2.)

## Why it is public

Images embedded in a GitHub issue only render if their raw URL is publicly
readable. Filenames are random UUIDs, so they are unguessable — but they are
**not access-controlled**. Anyone given a URL can view that photo.

Users are told this in the app's [privacy policy](https://tzoororg.github.io/DateAnalyze/privacy.html)
("Feedback" section): feedback content is not end-to-end encrypted and is
readable by the operator.

## Contents

Nothing here is written by hand. Do not host anything else in this repo.
