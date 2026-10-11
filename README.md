# Trivolt Axis Ventures — Circular Platform Prototype

## Run the front end
Extract this ZIP and open `index.html` in a modern browser. It includes interactive demo screens for:
- Overview and circular impact dashboard
- Waste collection and pickup requests
- Farmer registration, compost batches and supply agreements
- Fresh produce marketplace and demo ordering
- Existing TAV procurement, engineering, logistics, training, mining and institutional food-supply services
- Orders/activity, CSV export and demo operations admin

Demo records are stored in the browser's localStorage only. This is not a live hosted app and data is not shared across devices.

## Backend starter
`supabase/migrations/001_trivolt_core.sql` defines PostgreSQL tables for user profiles, farmer profiles, pickups, waste records, compost batches/inventory, produce listings/orders, supply agreements, points ledger, service enquiries, payment intents and audit events. It enables RLS and provides starter policies. These policies require review and testing before production.

`supabase/functions/create-pickup/index.ts` is a starter authenticated Edge Function.

## Set up hosting/backend
1. Create a Supabase project.
2. Run the migration SQL in its SQL Editor.
3. Test customer, farmer, collector, staff and admin roles using separate accounts.
4. Deploy the Edge Function with the Supabase CLI after linking your project.
5. Add Supabase Auth and client-side API wiring to replace localStorage with shared database calls.
6. Host the front end on Vercel, Netlify or another HTTPS host.

Never put Supabase service-role keys or payment-provider secrets in browser code. Keep mobile-money credentials server-side and integrate only after provider merchant/API access is obtained.

## Not live yet
- Shared hosted database or user login
- Real mobile-money/bank payments or redeemable points
- Transactional order placement and inventory reservation
- GPS dispatch/maps, notifications, delivery proof
- Full admin permissions and audit workflows

Compost must be processed and quality checked appropriately before sale. Do not issue points with monetary value until server-side ledger controls, fraud checks and reconciliation are implemented.
