---
name: lock-down-azure-cache-for-redis-network
description: >-
  Restrict who can reach an Azure Cache for Redis instance — firewall rules for IP allowlisting
  and private endpoint connections for VNet-only access. Use when asked to secure or isolate a
  cache.
api: microsoft-azure-cache-for-redis
api_version: '2024-11-01'
base_url: https://management.azure.com
operations:
  - FirewallRules_List
  - FirewallRules_Get
  - FirewallRules_CreateOrUpdate
  - FirewallRules_Delete
  - PrivateLinkResources_ListByRedisCache
  - PrivateEndpointConnections_List
  - PrivateEndpointConnections_Get
  - PrivateEndpointConnections_Put
  - PrivateEndpointConnections_Delete
  - Redis_Update
generated: '2026-09-17'
method: generated
source: openapi/microsoft-azure-cache-for-redis-redisfirewallrules-api-openapi.yml, openapi/microsoft-azure-cache-for-redis-privateendpointconnections-api-openapi.yml, conventions/
---

# Lock down network access to a cache

## Two mechanisms, different blast radius

- **Firewall rules** allowlist public client IP ranges. The cache is still reachable from the
  internet, just from fewer addresses.
- **Private endpoints** put the cache on a VNet. Combined with
  `properties.publicNetworkAccess: Disabled` (via `Redis_Update`), the public endpoint is gone.

## Firewall rules

1. `FirewallRules_List` — `GET .../redis/{cacheName}/firewallRules` to see what exists.
   **Read before you write.** A rule is addressed by name, so writing a rule whose name already
   exists silently replaces its IP range.
2. `FirewallRules_CreateOrUpdate` — `PUT .../redis/{cacheName}/firewallRules/{ruleName}` with
   `{"properties":{"startIP":"...","endIP":"..."}}`. Idempotent; not long-running.
3. `FirewallRules_Delete` — `DELETE .../firewallRules/{ruleName}`. Returns 204 if it was already
   gone. **There is no undo and no restore window** — recreate the rule from your own record if
   you remove the wrong one. Deleting the rule that carries the caller's own IP will lock them
   out of the data plane immediately.

## Private endpoints

1. `PrivateLinkResources_ListByRedisCache` — what the cache exposes for Private Link.
2. `PrivateEndpointConnections_List` / `_Get` — the pending and approved connections.
3. `PrivateEndpointConnections_Put` — approve or reject a connection by setting
   `properties.privateLinkServiceConnectionState.status` to `Approved` or `Rejected`.
   This one IS long-running: poll `Azure-AsyncOperation` until `provisioningState` is
   `Succeeded`.
4. `PrivateEndpointConnections_Delete` — removes the connection. Returns 204 when absent.

## Order of operations

Approve the private endpoint and confirm the caller can reach the cache over it **before**
setting `publicNetworkAccess: Disabled` with `Redis_Update`. Doing it the other way round cuts
off every existing client, and there is no reversal window — only another `Redis_Update` to turn
public access back on, which itself takes minutes.
