# Repost Cleaner — deployment guide

## What this release can do
- Display the landing page, planned pricing, sample dashboard, and demo checkout UI.
- Work as a static website on a static host.
- Use no API keys or secrets in the browser.

## What this release cannot do yet
- It does not log in to TikTok or read a user's real reposts.
- It cannot remove reposts.
- It does not create real orders, accept payments, or activate entitlements.
- The displayed prices and quotas are proposed plans only, not a service currently available for purchase.

## Before publishing
1. Keep the wording that says this is a demo and not accepting payment. Do not advertise automatic removal as available.
2. Confirm the TikTok API and policy situation in writing. The Research API's repost query is read-only research access and is not a user-facing repost-removal permission.
3. If the removal capability cannot be approved, change the product into a compliant helper that guides users through TikTok's own interface instead of automating private endpoints or collecting passwords/cookies.
4. Do not add payment collection until the promised service works and is authorized. Payment accounts may require an eligible adult or registered business representative; follow provider requirements and involve a parent/guardian as needed.

## Publish as a static website
This folder contains a single `index.html`, so no build command is required.

1. Create a repository in a Git hosting account you are allowed to use.
2. Upload `index.html`, `README.md`, `SECURITY_CHECKLIST.md`, `PAYMENT_SETUP.md`, and this guide.
3. In the repository's Pages/Static site settings, enable deployment from the main branch and the root folder (the exact UI wording may vary).
4. Wait for the host to provide the public URL, then open it on a phone and computer and test all links and the demo controls.
5. Keep the checkout button labeled as a demo. Do not accept money or claim the real removal feature is live.

A public static URL only publishes the frontend. It does not create a backend or enable TikTok integration/payments.

## Requirements for a real paid service
- Approved and documented TikTok capability for the exact actions promised.
- Secure backend and database, authentication/session management, rate limits, audit logs, privacy policy, terms, support and refund policy.
- Payment provider account approved for the business and age/legal status; server-side payment verification via signed webhooks.
- Server-side subscription/credit entitlements that update only after verified payment, plus refund and dispute handling.
- Security and end-to-end tests before inviting customers.

Never put API keys, payment secrets, or TikTok access tokens into `index.html`, a public repository, screenshots, or chat messages.
