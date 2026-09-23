---
name: azure-cache-for-redis-backup-and-restore
description: >-
  Export an Azure Cache for Redis dataset to blob storage and import it back, with the data-loss
  rules stated. Use when asked to back up, snapshot, migrate or restore a cache's contents.
api: microsoft-azure-cache-for-redis
api_version: '2024-11-01'
base_url: https://management.azure.com
operations:
  - Redis_ExportData
  - Redis_ImportData
  - Redis_FlushCache
  - AsyncOperationStatus_Get
  - Redis_Get
generated: '2026-09-17'
method: generated
source: openapi/microsoft-azure-cache-for-redis-redisresources-api-openapi.yml, https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-how-to-import-export-data, conventions/
---

# Export and import cache data

## What is reversible here, and what is not

- **Export → Import is the only reversal path this API has.** An RDB blob written by
  `Redis_ExportData` can be loaded back by `Redis_ImportData`. No retention window is published
  — the blob lives in the customer's own storage account for exactly as long as they keep it,
  so the retention is theirs to state, not Microsoft's.
- **Import is itself destructive.** Microsoft's documentation is explicit: "Importing data
  deletes preexisting cache data, and the cache isn't accessible by cache clients during the
  import process." Treat an import as a replace, never as a merge.
- **`Redis_FlushCache` and `Redis_Delete` have no reversal at all.** There is no undelete, no
  soft delete, no restore operation in the contract. If a caller asks to flush or delete, take
  an export first unless they explicitly decline.

## Export

`Redis_ExportData` — `POST .../redis/{name}/export` with `{"prefix":"...","container":"<SAS
URL>","format":"RDB"}`. Long-running: poll `Azure-AsyncOperation` (fall back to `Location`),
honour `Retry-After`, finish at `provisioningState: Succeeded`.

Export is available on Premium, Enterprise and Enterprise Flash. On Basic and Standard it is
not offered, and the honest answer to "back up this Basic cache" is that the platform cannot —
the data must be re-populated from its source of truth.

## Import

`Redis_ImportData` — `POST .../redis/{name}/import` with `{"files":["<blob SAS URL>"],
"format":"RDB"}`. Also long-running, same polling contract.

## Safety rules for an agent

1. **Neither export nor import is idempotent.** They are POST actions and this API has no
   Idempotency-Key header. If a call times out, poll the async-operation URL to find out what
   happened — do not re-POST.
2. Confirm the destination before importing. An import aimed at the wrong cache destroys that
   cache's data with no way back.
3. The cache is unreachable to clients for the duration of an import. Say so before starting.
4. Watch for the `Microsoft.Cache.ExportRDBCompleted` and `Microsoft.Cache.ImportRDBCompleted`
   Event Grid events if the caller has a subscription — they are the authoritative completion
   signal.
