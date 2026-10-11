# Cobra Lab Pro Admin

Arabic RTL administration dashboard for the existing Cobra Lab VPN Supabase project.

## Hosting

The GitHub Actions workflow `.github/workflows/deploy-pages.yml` publishes the existing Cobra Lab static homepage and the admin dashboard together. Once GitHub Pages is enabled with **GitHub Actions** as the build/deployment source, the admin dashboard will be available at:

`https://ali1994-wq.github.io/Cobra-Lab/admin/`

## Supabase integration

- Project URL: `https://tjifhqgcmfukxjznmoqf.supabase.co`
- Browser key: Supabase publishable key only, in `config.js`
- Admin API: Edge Function `cobra-vpn-payments`
- Login: Supabase Auth email/password. The signed-in account must already be listed in `public.cobra_vpn_payment_admins` (or have `profiles.role = 'admin'`).
- No service-role or secret key is included in browser files.

## Implemented admin actions

- Load payment requests through the authenticated Edge Function.
- Record manual review decisions and append review events.
- Edit plan names, prices, duration, and active status.
- Update the exchange rate manually.
- Read the payment review audit log.

**Approving a request records the decision only. It does not transfer funds or create/activate a VPN subscription.** Verify the payment externally before recording an approval.

## Important security notes

The publishable key is not a secret; database access must remain protected by RLS and server-side authorization. Never place a Supabase secret or service-role key in `config.js` or any browser bundle.

No database schema was changed as part of the dashboard integration. The existing review RPC was adjusted to record the decision only and not create a subscription.
