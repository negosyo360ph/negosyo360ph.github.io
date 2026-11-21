# Negosyo360

**Your business. Your numbers. Your growth.**
An all-in-one business app for Philippine small businesses (sari-sari stores, retail shops, food businesses, online sellers, resellers, freelancers) by Jessie Cajandab.

## What's in this repo

| Path | What it is |
|---|---|
| `docs/index.html` | Landing page (GitHub Pages) with the APK download |
| `docs/app/` | The app itself (HTML/JS, works offline). Also usable in a browser at `/app/` |
| `app/` | Android shell (WebView) that packages `docs/app` as an APK, with camera access for barcode scanning, saving backups to Downloads, and the share sheet |
| `.github/workflows/build-apk.yml` | Builds `Negosyo360.apk` on every push to `main` and publishes it as a GitHub Release |

## Phase 1 (this version), offline-first pilot
- Business setup on first open, optional 4-digit PIN, sample store for demos
- Sales / POS: tap or scan items, discount, Cash (with change), GCash, Maya, Bank (with reference no.), Utang; receipts; refunds
- Products: add / edit / delete, barcode (camera or typed), stock in with suggested quantity, stock forecast from daily sales, low-stock and slow-moving filters
- Expenses by category; stock purchases are tracked as cash out but not double-counted against profit (cost is counted when items sell)
- Cash drawer per day: opening cash, cash sales, cash utang payments, cash expenses, withdrawals, count and short/over
- Utang: from sales or added manually, due dates, partial payments, reminder via share sheet
- Reports: P&L (today / yesterday / 7 days / this month), 8-day chart, sales by payment, top and slow products, staff sales and commission, attendance
- Business health score and alerts; "Ask Negosyo" answers computed from the store's own data
- Backup / restore (JSON) and sales export (CSV)

Data is stored on the device (localStorage). Back up regularly.

## Next phases
- Phase 2: Supabase accounts and cloud sync (offline queue + sync without duplicates), multi-user and multi-branch, suppliers and purchase orders, printable receipts
- Phase 3: AI assistant via an AI API, sales and stock forecasting, automated insights
- Phase 4: online ordering, loyalty, payments (PayMongo/Xendit for GCash/Maya QR), financing referrals

## Install the APK
Open the latest release on an Android phone, download `Negosyo360.apk`, and allow "Install unknown apps" when asked.

The signing key in `app/` is a pilot key. Create a private key and move it to GitHub Secrets before a Google Play release.
