---
name: azure-cache-for-redis-entra-access-control
description: >-
  Replace shared access keys with Microsoft Entra ID identities on an Azure Cache for Redis
  instance — create access policies and assign them to principals. Use when asked to stop using
  cache keys, grant a service principal access, or rotate credentials.
api: microsoft-azure-cache-for-redis
api_version: '2024-11-01'
base_url: https://management.azure.com
operations:
  - AccessPolicy_List
  - AccessPolicy_Get
  - AccessPolicy_CreateUpdate
  - AccessPolicy_Delete
  - AccessPolicyAssignment_List
  - AccessPolicyAssignment_Get
  - AccessPolicyAssignment_CreateUpdate
  - AccessPolicyAssignment_Delete
  - Redis_ListKeys
  - Redis_RegenerateKey
generated: '2026-09-17'
method: generated
source: openapi/microsoft-azure-cache-for-redis-rediscacheaccesspolicies-api-openapi.yml, openapi/microsoft-azure-cache-for-redis-rediscacheaccesspolicyassignments-api-openapi.yml, conventions/
---

# Grant access with Entra ID instead of a shared key

Entra ID authentication for Azure Cache for Redis went GA in May 2024. It is the reason to stop
passing `Redis_ListKeys` output around.

## Model

- An **access policy** (`RedisCacheAccessPolicy`) is a named permission set — built-in
  (`Data Owner`, `Data Contributor`, `Data Reader`) or custom, expressed as Redis ACL
  permissions in `properties.permissions`.
- An **access policy assignment** binds one policy to one Entra object ID
  (`properties.objectId` plus a human-readable `properties.objectIdAlias`).

## Steps

1. `AccessPolicy_List` — `GET .../redis/{cacheName}/accessPolicies`. Prefer a built-in policy;
   only create a custom one if the built-ins are too broad.
2. `AccessPolicy_CreateUpdate` — `PUT .../accessPolicies/{accessPolicyName}` with
   `{"properties":{"permissions":"<redis ACL string>"}}`. Long-running: poll
   `Azure-AsyncOperation` to `Succeeded`.
3. `AccessPolicyAssignment_CreateUpdate` — `PUT .../accessPolicyAssignments/{name}` with
   `objectId`, `objectIdAlias` and `accessPolicyName`. Also long-running.
4. Verify with `AccessPolicyAssignment_List` before you take anything away.

## Retiring the shared keys

Only after every consumer is authenticating with Entra:

- `Redis_RegenerateKey` — `POST .../redis/{name}/regenerateKey` with
  `{"keyType":"Primary"}` or `"Secondary"`.
- **This is not idempotent and not reversible.** It is a POST action with no Idempotency-Key
  support: firing it twice rotates twice. The old key stops working the moment it is replaced,
  and regenerating the other key does not bring it back. Rotate one key, let clients move,
  then rotate the other.
- Set `properties.disableAccessKeyAuthentication: true` via `Redis_Update` to turn key auth off
  entirely.

## Never do

- Do not call `Redis_ListKeys` "to check" — it returns live secrets into your context. Use
  `AccessPolicyAssignment_List` to verify access instead.
- Do not delete an access policy that still has assignments; remove the assignments first.
