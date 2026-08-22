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

## Customer access

Chairman, CEO, and CFO users provision permanent customer credentials from **Client Service → Access administration**. Customers sign in with a bank username such as `emrys`; the app securely maps it to an internal `@clients.bbc.com` authentication identity, so no real email inbox is required.

- Initial passwords are created or reset through a protected server-side function.
- Passwords are never stored in the banking tables or returned after provisioning.
- Staff can require a password change at first sign-in and suspend or restore access.
- Row-level security limits each customer to their own deposits, loans, payment schedules, statements, requests, holdings, IPO orders, and dividends.

## Banking workspace

The staff portal includes:

- Executive dashboard with six KPI cards and four analytical graphics for liquidity trend, capital structure, depositor concentration, and operating controls
- Balance sheet and account balances derived from posted journal entries
- Customer and officer records
- Client Service credential administration, account controls, relationship directory, and transaction-request queue
- Deposit register with working account details, principal, monthly interest, maturity, accrued interest, and status
- Loan register with approval controls, payment schedules, balances, and delinquency tracking
- Double-entry journal and trial balance
- Reporting center with management summary, financial statements, trial balance, risk analytics, export center, and CSV downloads
- Capital markets center with ownership analytics, share transactions, IPO order book, and dividend administration
- Governance control center with authority matrix, decision queue, charter register, audit trail, and evidence-backed month-end close
- Officer profile with security, device preferences, notifications, session controls, and bank configuration
- Real-time refresh when authorized staff post activity

The customer portal includes current deposit balances, accrued interest, maturity dates, loan balances, payment schedules, downloadable statements, transaction requests, share holdings, IPO subscriptions, and dividends.

## Accounting controls

- Every posted batch must balance: total debits equal total credits.
- Financial actions run atomically, so a partial posting cannot be saved.
- Loan activation requires Chairman approval.
- Posted entries are retained as an audit trail rather than silently overwritten.
- Database constraints validate dates, positive amounts, allowed statuses, and payment splits.
- Supabase Row Level Security protects every exposed banking table.
- Anonymous requests receive no customer or financial records.
- The charter's 40% ownership cap is enforced for every shareholder except Richard, whose founder exemption is explicitly recorded and audited.

## Current officers

- Chairman: Richard — Rich Land, Nation ID 774545
- Chief Executive Officer: Prosper
- Chief Financial Officer: Ibrawolf — Republic of Krandia, Nation ID 337443
- Chief Operations Officer: Yusuf

## Deployment

GitHub Pages serves the production files in the repository root from the `main` branch over enforced HTTPS. Supabase provides authentication, PostgreSQL storage, transaction functions, row-level security, and Realtime updates. Only the browser-safe Supabase publishable key is embedded in the site; privileged secret keys are never published.
