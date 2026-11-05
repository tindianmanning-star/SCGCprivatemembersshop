# Scotchmans Creek Golf Club Members Store — prototype

This is a responsive, browser-based storefront prototype. Open `index.html` in a modern browser.

## Included
- Product catalogue with sample garment SKUs, prices, colours and sizes
- Cart and delivery-detail checkout flow
- Demonstration order packet export (JSON)
- Club dashboard with sample gross sales and 5% commission calculations
- Manufacturer-ready order fields including product SKU, selected options, delivery details and artwork placeholder

## Important: not production-connected
This prototype does **not** authenticate actual club members, process payments, transmit orders to a manufacturer, send emails, or move funds. The checkout is explicitly demo-only. Do not enter real payment details or treat demo orders as accepted orders.

## Production architecture
1. Frontend: Next.js or equivalent, hosted on a managed platform.
2. Member access: club-approved identity provider or invite-only accounts; enforce authorization server-side.
3. Catalogue: admin-managed products mapped to manufacturer's confirmed SKUs, artwork files, size charts and wholesale prices.
4. Checkout: create payment intent/session server-side; never trust browser-supplied prices.
5. Payment allocation: implement Stripe Connect or an agreed marketplace settlement model only after the club, manufacturer and payment provider approve the legal/commercial structure. A 5% club fee should be calculated on a clearly defined eligible subtotal, not assumed to include GST, shipping, refunds or processing fees.
6. Fulfilment: payment-success webhook creates an idempotent manufacturer order; transmit only necessary customer/order data via authenticated API or secure email/portal. Record acceptance, production, dispatch and tracking updates.
7. Admin: role-based club and manufacturer views, audit log, order reconciliation, refunds and monthly commission statements.

## Required before launch
- Club-approved logo, brand rules and permission to operate the store
- Manufacturer identity, contact, catalogue, SKU list, production pricing, artwork specs, API/email workflow and service levels
- Agreement defining the 5% commission base, GST, shipping, refunds, chargebacks, payment fees, payout timing and responsibility for consumer guarantees
- Stripe/merchant account and verified payout details
- Domain, hosting and transactional email
- Member access method and privacy/retention policy


## Club branding update
The storefront uses the supplied Scotchmans Creek Golf Club crest and a dark-green / gold-yellow colour palette. The crest asset is `scotchmans-creek-crest.png`.
