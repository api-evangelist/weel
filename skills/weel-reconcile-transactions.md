---
name: Reconcile Weel transactions to the chart of accounts
description: Pull transactions, then code them against accounting codes, categories, tax rates, and custom fields for accounting-system sync.
api: openapi/weel-openapi.yml
operations: [listTransactions, getTransaction, listStatements, listAccountingCodes, upsertAccountingCode, listCategories, createCategory, listTaxRates, listCustomFields, linkCustomFieldBudget]
---

# Reconcile Weel transactions to the chart of accounts

Read spend out of Weel and align it with your accounting system's chart of accounts.

## Auth
`Authorization: Bearer <token>`; paths scoped to `{client_id}`. Enterprise-plan gated.

## Steps
1. Pull spend with `listTransactions` (`GET /v2/businesses/{client_id}/transactions`), paging with `offset`/`limit`; drill in with `getTransaction`.
2. Pull the period view with `listStatements` when reconciling by statement.
3. Load the chart of accounts with `listAccountingCodes`; create/update codes with `upsertAccountingCode` to mirror your ERP (Xero, QuickBooks, MYOB, NetSuite).
4. Load `listCategories` and `listTaxRates` for coding; add categories with `createCategory` as needed.
5. Where custom fields drive coding, load `listCustomFields` and attach them to budgets with `linkCustomFieldBudget`.

## Conventions & errors
- Transactions live under `/v2`; most other resources under `/v1`.
- Pagination envelope: `{count, next, previous, results}`; `next`/`previous` are ready-made query strings.
- No idempotency contract; `upsertAccountingCode` is upsert-semantic so re-running is safe, but `createCategory` is not — check `listCategories` first. See `errors/weel-problem-types.yml`.
