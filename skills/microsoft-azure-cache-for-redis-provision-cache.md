---
name: provision-azure-cache-for-redis
description: >-
  Create an Azure Cache for Redis instance and wait for it to become usable, then hand back its
  hostname, SSL port and connection secret. Use when a caller asks to stand up a new cache.
api: microsoft-azure-cache-for-redis
api_version: '2024-11-01'
base_url: https://management.azure.com
operations:
  - Redis_CheckNameAvailability
  - Redis_Create
  - AsyncOperationStatus_Get
  - Redis_Get
  - Redis_ListKeys
generated: '2026-09-17'
method: generated
source: openapi/microsoft-azure-cache-for-redis-*-openapi.yml, conventions/, errors/
---

# Provision an Azure Cache for Redis instance

**Before you start.** This product is retiring — Basic/Standard/Premium on 2028-09-30,
Enterprise/Enterprise Flash on 2027-03-31 — and creating a new cache is blocked for any tenant
that had none before 2026-04-01. If the caller has no existing cache in the tenant, the create
will fail and the right answer is Azure Managed Redis, not a workaround. Say so before acting.

## Auth

Every call needs an Entra bearer token for the `https://management.azure.com/` audience
(securityScheme `azure_auth`, scope `user_impersonation`). Discovery document:
`https://login.microsoftonline.com/common/v2.0/.well-known/openid-configuration`.
Every request also needs `?api-version=2024-11-01` — without it you get
`400 MissingApiVersionParameter`.

## Steps

1. **Check the name is free.** `Redis_CheckNameAvailability` —
   `POST /subscriptions/{subscriptionId}/providers/Microsoft.Cache/checkNameAvailability`
   with `{"name": "<cacheName>", "type": "Microsoft.Cache/redis"}`.
   This is the only dry-run this API offers. Do it; a failed create costs minutes.

2. **Create the cache.** `Redis_Create` —
   `PUT /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Cache/redis/{name}`
   with `location` and `properties.sku` (`{name, family, capacity}` — e.g. Standard/C/1).
   This is a PUT addressed by name, so it is **idempotent**: a retry after a lost response
   converges on the same cache. It is also long-running.

3. **Poll until it is real.** The response is 201/202. Follow the `Azure-AsyncOperation`
   header (fall back to `Location`), honour `Retry-After`, and use `AsyncOperationStatus_Get`
   or `Redis_Get` until `properties.provisioningState` is `Succeeded`. `Failed` and `Canceled`
   are the other terminal values. Do not report success on the 202.

4. **Read the connection facts.** `Redis_Get` returns `properties.hostName`,
   `properties.sslPort` (6380) and `properties.port`.

5. **Fetch the key only if you need it.** `Redis_ListKeys` —
   `POST .../redis/{name}/listKeys`. **This returns a live credential.** Never log it, never
   echo it into a transcript, never store it outside the caller's secret store. Prefer Entra ID
   authentication with an access policy assignment (see the access-control skill) so no key is
   handled at all.

## Failure handling

- `403 AuthorizationFailed` — the principal lacks an Azure RBAC role on the resource group, or
  the `Microsoft.Cache` provider is not registered. Do not retry; report it.
- `409 Conflict` / `AnotherOperationInProgress` — a write is already running on this resource.
  Wait for the in-flight operation, then retry.
- `429` — read `Retry-After` and the `x-ms-ratelimit-remaining-subscription-writes` header.
  Writes are 200 burst, 10 per second per subscription per region.
- Error bodies are `{"error":{"code","message","target","details","additionalInfo"}}`, not
  RFC 9457. The actionable code is usually inside `details[]`.
