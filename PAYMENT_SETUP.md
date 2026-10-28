# Payment setup plan (Thailand)

## Current state
The payment section in `index.html` is a UI demo only. It does not accept payments, create orders, collect payment details, or start subscriptions.

## Suggested rollout
1. **Validate the product first.** Do not charge until the core repost-management feature is technically possible and permitted by TikTok.
2. **Choose a payment provider.** Compare a Thai provider such as Opn Payments (formerly Omise) with other providers available to your registered business. Confirm current eligibility, supported methods (PromptPay/QR, cards), fees, settlement schedule, refunds, recurring billing, and required business documents directly with the provider.
3. **Use hosted checkout.** The backend creates a checkout session; the browser redirects to the provider-hosted payment page. Never collect or store card numbers/CVV in this project.
4. **Confirm payment on the server.** Verify provider-signed webhooks and payment status server-side. Do not grant paid features based only on a browser redirect or a screenshot/QR scan.
5. **Use explicit order states.** `pending`, `paid`, `failed`, `refunded`, `cancelled`. Make webhook handling idempotent to avoid duplicate fulfilment.
6. **Recurring subscriptions are a separate phase.** Show renewal amount and schedule, cancellation process, and refund terms before purchase. Keep a user-visible cancellation route.
7. **Security basics.** Store provider secret keys only in server environment variables; never put them in HTML/JavaScript or commit them to Git. Use HTTPS, CSRF protection for app sessions, rate limiting, and minimal logs.
8. **Policies.** Publish accurate terms of service, privacy policy, contact details, refund/cancellation terms, and invoice/receipt details as applicable.
9. **Account eligibility.** Payment providers may require a legally eligible account holder and business/identity verification. Since eligibility varies by provider and age, check the current terms; a parent/guardian or registered business may need to be the account holder. Do not misstate age or identity.

## Budget approach
- Prototype UI: ฿0
- Payment integration: no payment transaction fee can be quoted until the provider and business profile are selected; providers may charge transaction fees and/or other fees.
- Start with one-time payments or free beta. Add recurring billing only after validating demand and confirming provider support.
- Do not promise that ฿29/฿59 monthly tiers unlock real automatic repost removal until that feature is authorized and working.

## Important
This project currently has no backend and must not be used to take real payments. Use the provider's current official documentation and merchant onboarding team before production integration.


## Proposed Repost Cleaner pricing

| Plan | Proposed price | Proposed quota | Billing |
|---|---:|---:|---|
| FREE | ฿0 | 50 clips/day | Free |
| EXPRESS | ฿50 | 200 clips/order | One-time |
| WEEKLY PRO | ฿200 | 1,000 clips/7 days | One-time weekly pass |
| MONTHLY PRO | ฿579 | 3,000 clips/30 days | One-time 30-day pass |

These prices and quotas are planning assumptions, not live offers. Before enabling checkout, confirm that the service can lawfully and reliably perform the advertised action. Do not represent the frontend demo as an active paid service.
