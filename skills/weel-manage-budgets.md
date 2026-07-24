---
name: Create and fund Weel budgets
description: Create a spend budget, add members and owners, and top it up at the budget or member level.
api: openapi/weel-openapi.yml
operations: [createBudget, getBudget, updateBudget, listBudgets, createBudgetMember, listBudgetMembers, createBudgetOwner, createBudgetTopup, createBudgetMemberTopup, deleteBudget]
---

# Create and fund Weel budgets

Provision a budget in Weel, staff it, and allocate funds.

## Auth
`Authorization: Bearer <token>`; paths scoped to `{client_id}`. Enterprise-plan gated.

## Steps
1. Create the budget with `createBudget` (`POST /v1/businesses/{client_id}/budgets`). Set `has_member_limits` when funds should be allocated per member rather than at the budget level.
2. Add members with `createBudgetMember` (`POST .../budgets/{budget_id}/members`); each member is associated with a user. Review with `listBudgetMembers`.
3. Assign an approver/owner with `createBudgetOwner` (`POST .../budgets/{budget_id}/owners`).
4. Fund the budget with `createBudgetTopup` (`POST .../budgets/{budget_id}/topups`), or fund an individual member with `createBudgetMemberTopup` when `has_member_limits` is set.
5. Inspect state with `getBudget` / `listBudgets`; adjust with `updateBudget`; remove with `deleteBudget`.

## Conventions & errors
- Budgets are hierarchical: budget → members (each tied to a user) → optional per-member limits.
- No `Idempotency-Key` is available; retries of top-up creation can double-fund — verify before retrying.
- Standard HTTP errors: `400` validation, `401/403` auth, `404` missing budget/member, `429` rate limited. See `errors/weel-problem-types.yml`.
