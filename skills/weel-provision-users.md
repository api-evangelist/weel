---
name: Provision and manage Weel users
description: Invite a new employee to a Weel business, confirm they became an active user, and manage or offboard them.
api: openapi/weel-openapi.yml
operations: [createInvite, listInvites, cancelInvite, listUsers, getUser, updateUser, deleteUser, listRoles]
---

# Provision and manage Weel users

Use the Weel Open API to onboard, update, and offboard the people in a business.

## Auth
Send `Authorization: Bearer <token>` on every request (create the key in-app under Settings > API). All paths are scoped to a business via `{client_id}`. API access is an Enterprise-plan capability.

## Steps
1. Discover assignable roles with `listRoles` (`GET /v1/businesses/{client_id}/roles`) so you can pick a valid role for the new person.
2. Invite the employee with `createInvite` (`POST /v1/businesses/{client_id}/invites`). The invite exists until the recipient accepts it.
3. Track pending invitations with `listInvites`; if an invite was sent in error, revoke it with `cancelInvite` (`DELETE .../invites/{invite_id}`).
4. Once accepted, the person appears via `listUsers` and `getUser` (`GET .../users/{user_id}`).
5. Update a user's details with `updateUser`; offboard with `deleteUser`.

## Conventions & errors
- List endpoints paginate with `offset`/`limit` (default 50, max 500) and return `{count, next, previous, results}`.
- No idempotency key is supported — do not blind-retry `createInvite`; check `listInvites` first.
- `401` = bad/missing token, `403` = key lacks permission or API access not enabled, `404` = unknown id. See `errors/weel-problem-types.yml`.
