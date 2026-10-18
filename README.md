# PocketLedger v1 — Android + Windows

Local-first personal money manager, installable as a PWA on Android and Windows.

## Features
- Accounts with opening balances (bank, cash, credit card, wallet, investment, other)
- Income, expense and transfer transactions
- Current-month overview, account balances, recent entries, category/month reports
- Search, edit and delete entries
- Excel workbook export (Transactions, Accounts, Categories sheets)
- Excel/CSV transaction import
- Full JSON backup and restore
- Responsive installable PWA

## Install on Android and Windows
1. Upload the contents of this folder to a static HTTPS host (GitHub Pages is one free option).
2. Android: open the HTTPS URL in Chrome → menu → Install app/Add to Home screen.
3. Windows: open the URL in Edge or Chrome → menu/app icon → Install this site as an app.
4. For local testing only, run `python -m http.server 8080` and open `http://localhost:8080`.

## Google Drive backup
In v1, use Data & backup → Download JSON backup, then upload the file to Google Drive. To restore, download it from Drive and select Restore JSON backup. This is manual backup, not automatic sync. Direct Drive integration requires Google OAuth configuration and further development.

## Excel
SheetJS is loaded from jsDelivr, so Excel import/export needs internet access unless you bundle a licensed local copy. Import headers: Date, Type, Account, Amount, Category, Description; transfers also need To Account. Account names must match existing accounts. Import does not deduplicate. Back up before bulk imports.

## Important limitations
- Prototype, not audited double-entry accounting, tax software, or bank-sync software.
- Data is in localStorage for this prototype. Clearing site/browser data can erase it.
- Android and Windows instances do not automatically share data; transfer backups manually.
- No server receives your financial records through this app itself, but the Excel library is fetched from a CDN.
- INR base currency; no live bank connection.
