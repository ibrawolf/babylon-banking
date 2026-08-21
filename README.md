# Babylon Banking Corporation

A secure, live CFO command center for Babylon Banking Corporation in Politics & War.

## What is included

- Cash, deposit, loan, payment, customer, journal, trial-balance, reporting, governance, and close-control views
- Supabase Auth magic-link sign-in
- PostgreSQL constraints and row-level security for approved bank staff
- Atomic transaction posting through `bank_action`, so every financial batch succeeds or rolls back as one unit
- Realtime dashboard refresh when authorized users post new activity
- GitHub Actions workflow for GitHub Pages
- Opening books: $8 billion founder capital and the $50 million Emrys Federation deposit at 1.5% monthly from 17 August to 17 September 2026

## Local builds

```bash
npm install
npm run build:pages
```

The static artifact is written to `pages-dist/`. The existing Sites version still builds with `npm run build`.

## Supabase setup

1. Create a new Supabase project.
2. Replace `__BANK_OWNER_EMAIL__` in `supabase/migrations/202608210001_babylon_bank.sql` with the CFO sign-in email.
3. Apply the migration.
4. Add the deployed GitHub Pages URL to Supabase Auth redirect URLs.
5. Add these GitHub repository variables:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_PUBLISHABLE_KEY`

Only use a Supabase `sb_publishable_...` key in the website. Never expose a secret or `service_role` key.

## Publishing

Set GitHub Pages **Source** to **GitHub Actions**. Every push to `main` builds and deploys the static site with `.github/workflows/pages.yml`.
