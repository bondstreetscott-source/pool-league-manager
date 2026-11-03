# Pool League Manager — Phase 1

This build connects to the Pool League Manager Supabase project and uses the existing schema and `is_league_admin()` RPC created in the previous setup steps.

## Included
- Supabase email/password sign-in
- League administrator check through `is_league_admin()`
- Administrator creation of venues and teams
- Per-season venue table capacity
- Team assignment to season, division, and venue
- Read-only division and team views (currently accessible only to admins under existing RLS policies)

## Deploy
1. Create a new GitHub repository, e.g. `pool-league-manager`.
2. Upload `index.html` to the repository root.
3. Import the repository into Vercel as a static site (Framework Preset: Other, no build command).
4. Open the deployed site, select Administration and sign in with the Supabase Authentication user created earlier.

## Important limitations
- Public users will not yet see league data: existing RLS policies allow only administrators to read core tables. This is intentional until publication rules are implemented.
- No fixtures, live scoring, cups, messages, sponsors, hall of fame, or rules sections are implemented in this phase.
- The website's publishable key is safe to expose; never put a secret/service-role key in frontend code.
- The existing administrator function must exist and be executable by authenticated users.
- Supabase Auth URL settings may need updating after deployment, depending on login flow.
