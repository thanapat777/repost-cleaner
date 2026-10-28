# Repost Cleaner — Starter Project

A responsive Thai-language prototype for a TikTok repost-management product.

## Current status
- Frontend demo only. All content is sample data.
- No TikTok login, API calls, token storage, payments, or real repost actions.
- Do not market this prototype as an automatic repost remover yet.

## Why real automation is not included
TikTok's official developer documentation describes Login Kit/OAuth and scopes such as `user.info.basic` and `video.list`. These do not themselves grant permission to manage reposts. Before implementing an automatic removal feature, verify with TikTok that an approved API/permission exists for listing and undoing reposts. Do not use password collection, copied session cookies, or automation designed to bypass platform controls.

Official docs:
- Login Kit overview: https://developers.tiktok.com/docs/en/login-kit-overview
- Login Kit web: https://developers.tiktok.com/docs/en/login-kit-web
- Scopes overview: https://developers.tiktok.com/docs/en/scopes-overview
- Scopes reference: https://developers.tiktok.com/docs/en/tiktok-api-scopes

## Run locally
1. Download and unzip this folder.
2. Open `index.html` in a browser.
3. Try selecting sample rows. The action buttons only show demo messages.

No installation or API key is needed for the frontend demo.

## Safe implementation plan
1. **Feasibility gate:** confirm in writing from TikTok developer documentation/support that an API for reading and undoing reposts is available to your app and permitted for this use case.
2. Register the app and request only approved scopes.
3. Build OAuth on a backend over HTTPS. Validate an unpredictable `state` value; exchange authorization codes server-side; keep client secret and tokens server-side; encrypt tokens at rest; never expose secrets in browser code or logs.
4. Use a secure session cookie, CSRF protection, rate limiting, audit-safe logs, deletion/withdrawal flows, and a privacy policy.
5. Only report actions as successful after a real API success response. Require a confirmation step before destructive actions.
6. Get required TikTok review/approval and test with a small invited group before public launch.
7. Add payments only after the core feature works and policy/legal requirements are checked.

## Early budget (planning estimates, not live quotes)
- Local prototype: ฿0
- Domain: roughly ฿300–฿800/year depending on provider and domain extension
- Early hosting: use a reputable free tier while testing; upgrade only after measuring actual traffic
- Database/authentication: begin on a free tier with strict access controls; account for provider limits
- Payments: no payment integration in this prototype; expect provider fees and extra compliance work
- Do not spend on ads or paid subscriptions until the core feature is confirmed feasible.

## Pricing hypothesis (not enabled)
- FREE: ฿0, planned 50 clips/day
- EXPRESS: ฿50, planned 200 clips per one-time order
- WEEKLY PRO: ฿200, planned 1,000 clips per 7 days
- MONTHLY PRO: ฿579, planned 3,000 clips per 30 days
These are planning assumptions, not active offers. Do not charge users until the promised feature is functional, authorized, and transparently described.

## Next step
Verify whether TikTok supports the exact repost operations required. If it does not, pivot to a compliant helper that guides users to manage reposts manually, rather than promising automatic removal.


## Payment UI
See `PAYMENT_SETUP.md`. The checkout section is a visual demo only and does not accept money.


## Pricing plan (not live)

- FREE: planned 50 clips/day.
- EXPRESS: planned 200 clips per one-time order for ฿50.
- WEEKLY PRO: planned 1,000 clips per 7 days for ฿200.
- MONTHLY PRO: planned 3,000 clips per 30 days for ฿579.

These are proposed limits only. TikTok integration, actual repost removal, account authentication, checkout, payment verification, and subscription entitlements are not implemented. Do not collect payment until the core capability is confirmed, permitted, and tested.


## Publishing the frontend
See `DEPLOY_GUIDE.md` for a static-site publishing checklist and the limitations that remain. Publishing the frontend does not enable TikTok integration or real payments.
