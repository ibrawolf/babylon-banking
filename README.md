# Babylon Banking Corporation

Secure, real-time CFO command center and double-entry banking ledger for Babylon Banking Corporation in Politics & War.

**Live staff portal:** https://ibrawolf.github.io/babylon-banking/

## Opening books

- Bank opened: 19 August 2026
- Reporting start: 21 August 2026
- Founder capital: $8,000,000,000 cash funded by Richard
- Opening customer: The Emrys Federation, led by Emrys (Nation ID 740012; Singularity)
- Opening deposit: $50,000,000 at 1.5% monthly, 17 August–17 September 2026
- Opening bank cash after the deposit: $8,050,000,000
- Loans at opening: none

## Staff access

The public website contains no public banking data. Approved staff sign in with an assigned `@bbc.com` staff login and password. Database row-level security verifies bank membership before returning records or accepting transactions.

1. Open the live staff portal.
2. Enter an approved `@bbc.com` staff login and password.
3. On first sign-in, replace the temporary password.
4. Continue to the protected banking workspace.

Current staff logins:

- `ibrawolf@bbc.com` — CFO
- `yusuf@bbc.com` — COO

Temporary passwords must be replaced on first sign-in. New passwords require at least 10 characters with uppercase, lowercase, a number, and a symbol.

## Banking workspace

The portal includes:

- Executive dashboard with cash, deposits, loans, interest, liquidity, and portfolio analytics
- Balance sheet and account balances derived from posted journal entries
- Customer and officer records
- Deposit register with principal, monthly interest, maturity, accrued interest, and status
- Loan register with approval controls, payment schedules, balances, and delinquency tracking
- Double-entry journal and trial balance
- Income statement, capital, liquidity, and operating statistics
- Audit log and month-end close checklist
- Real-time refresh when authorized staff post activity

## Accounting controls

- Every posted batch must balance: total debits equal total credits.
- Financial actions run atomically, so a partial posting cannot be saved.
- Loan activation requires Chairman approval.
- Posted entries are retained as an audit trail rather than silently overwritten.
- Database constraints validate dates, positive amounts, allowed statuses, and payment splits.
- Supabase Row Level Security protects every exposed banking table.
- Anonymous requests receive no customer or financial records.

## Current officers

- Chairman: Richard — Rich Land, Nation ID 774545
- Chief Executive Officer: Prosper
- Chief Financial Officer: Ibrawolf — Republic of Krandia, Nation ID 337443
- Chief Operations Officer: Yusuf

## Deployment

GitHub Pages serves the production files in the repository root from the `main` branch over enforced HTTPS. Supabase provides authentication, PostgreSQL storage, transaction functions, row-level security, and Realtime updates. Only the browser-safe Supabase publishable key is embedded in the site; privileged secret keys are never published.
