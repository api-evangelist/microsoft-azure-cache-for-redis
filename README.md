# Microsoft Azure Cache For Redis

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Azure Cache for Redis is Microsoft's managed in-memory data store built on the open-source Redis software, used to put a low-latency cache, session store or message broker in front of a slower backing store. This record covers the management (control-plane) REST API — the Microsoft.Cache/redis resource provider on Azure Resource Manager — which creates, scales, secures, backs up and deletes caches across the Basic, Standard, Premium, Enterprise and Enterprise Flash tiers. The Redis data plane itself is plain Redis, spoken with an ordinary Redis client and not described by an OpenAPI. Microsoft announced in October 2025 that every Azure Cache for Redis SKU is retiring: Enterprise and Enterprise Flash on 2027-03-31, Basic, Standard and Premium on 2028-09-30, with Azure Managed Redis as the successor.

**Areas:** Microsoft Azure · Cache · Cloud Infrastructure · Datastore · In-Memory Database · Managed Service · Microsoft · Redis

## Microsoft Azure Cache For Redis on APIs.io

Everything profiled for Microsoft Azure Cache For Redis is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/microsoft-azure-cache-for-redis/](https://apis.io/providers/microsoft-azure-cache-for-redis/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [microsoft-azure-cache-for-redis Operations API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-operations-api/) — Operations operations
- [Microsoft Azure Cache For Redis Linked Server API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-linkedserver-api/) — The LinkedServer API from Microsoft Azure Cache For Redis — 2 operation(s) for linkedserver.
- [Microsoft Azure Cache For Redis Redis Cache Access Policies API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicies-api/) — The RedisCacheAccessPolicies API from Microsoft Azure Cache For Redis — 2 operation(s) for rediscacheaccesspolicies.
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Assignments API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicyassignments-api/) — The RedisCacheAccessPolicyAssignments API from Microsoft Azure Cache For Redis — 2 operation(s) for rediscacheaccesspolicyassignments.
- [Microsoft Azure Cache For Redis Redis Firewall Rules API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisfirewallrules-api/) — The RedisFirewallRules API from Microsoft Azure Cache For Redis — 2 operation(s) for redisfirewallrules.
- [Microsoft Azure Cache For Redis Redis Patch Schedules API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redispatchschedules-api/) — The RedisPatchSchedules API from Microsoft Azure Cache For Redis — 2 operation(s) for redispatchschedules.
- [Microsoft Azure Cache For Redis Redis Resources API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisresources-api/) — The RedisResources API from Microsoft Azure Cache For Redis — 11 operation(s) for redisresources.
- [Microsoft Azure Cache For Redis Subscriptions API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-subscriptions-api/) — The Subscriptions API from Microsoft Azure Cache For Redis — 2 operation(s) for subscriptions.
- [Microsoft Azure Cache For Redis Private Endpoint Connections API](https://apis.io/apis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-private-endpoint-connections-api/) — The Private Endpoint Connections API from Microsoft Azure Cache For Redis — 2 operation(s) for private endpoint connections.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (2)

Event-driven and webhook contracts.

- [Azure Cache for Redis — Event Grid events](https://apis.io/asyncapis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-events-asyncapi/)
- [Microsoft Azure Cache For Redis Webhooks](https://apis.io/asyncapis/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-webhooks/)

#### Event channels (1)

Individual events and webhooks the provider emits.

- [/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.Cache/Redis/{cacheName}](https://apis.io/channels/microsoft-azure-cache-for-redis/subscriptions-subscriptionid-resourcegroups-resourcegroupname-providers-microsof/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Azure MCP Server](https://apis.io/servers/microsoft-azure-cache-for-redis/azure-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Microsoft Azure Cache For Redis Agentic Access](https://apis.io/agentic-access/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-agentic-access/)

#### Examples (46)

Example requests and responses.

- [Microsoft Azure Cache For Redis Redis Cache Access Policy Assignment Create Update Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-assignment-create-update-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Assignment Delete Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-assignment-delete-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Assignment Get Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-assignment-get-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Assignment List Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-assignment-list-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Create Update Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-create-update-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Delete Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-delete-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy Get Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-get-example/)
- [Microsoft Azure Cache For Redis Redis Cache Access Policy List Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-access-policy-list-example/)
- [Microsoft Azure Cache For Redis Redis Cache Async Operation Status Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-async-operation-status-example/)
- [Microsoft Azure Cache For Redis Redis Cache Check Name Availability Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-check-name-availability-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create Automatic Zonal Allocation Policy Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-automatic-zonal-allocation-policy-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create Default Version Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-default-version-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create Latest Version Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-latest-version-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create No Zones Zonal Allocation Policy Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-no-zones-zonal-allocation-policy-example/)
- [Microsoft Azure Cache For Redis Redis Cache Create User Defined Zonal Allocation Policy Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-create-user-defined-zonal-allocation-policy-example/)
- [Microsoft Azure Cache For Redis Redis Cache Delete Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-delete-example/)
- [Microsoft Azure Cache For Redis Redis Cache Delete Private Endpoint Connection Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-delete-private-endpoint-connection-example/)
- [Microsoft Azure Cache For Redis Redis Cache Export Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-export-example/)
- [Microsoft Azure Cache For Redis Redis Cache Firewall Rule Create Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-firewall-rule-create-example/)
- [Microsoft Azure Cache For Redis Redis Cache Firewall Rule Delete Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-firewall-rule-delete-example/)
- [Microsoft Azure Cache For Redis Redis Cache Firewall Rule Get Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-firewall-rule-get-example/)
- [Microsoft Azure Cache For Redis Redis Cache Firewall Rules List Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-firewall-rules-list-example/)
- [Microsoft Azure Cache For Redis Redis Cache Flush Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-flush-example/)
- [Microsoft Azure Cache For Redis Redis Cache Force Reboot Example](https://apis.io/examples/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redis-cache-force-reboot-example/)
- …and 21 more published on APIs.io

#### Collections (3)

Postman and Open Collection request collections.

- [Azure Cache for Redis REST API](https://apis.io/collections/microsoft-azure-cache-for-redis/open-microsoft-azure-cache-for-redis/)
- [Azure Cache for Redis REST Operations API](https://apis.io/collections/microsoft-azure-cache-for-redis/open-microsoft-azure-cache-for-redis-operations-api/)
- [Azure Cache for REST Operations Redis API](https://apis.io/collections/microsoft-azure-cache-for-redis/open-microsoft-azure-cache-for-redis-redis-api/)

#### Overlays (18)

OpenAPI overlays, including conversational phrasing for each operation.

- [Microsoft Azure Cache For Redis Linkedserver Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-linkedserver-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Linkedserver Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-linkedserver-overlay/)
- [Microsoft Azure Cache For Redis Operations Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-operations-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Operations Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-operations-overlay/)
- [Microsoft Azure Cache For Redis Private Endpoint Connections Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-private-endpoint-connections-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Privateendpointconnections Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-privateendpointconnections-overlay/)
- [Microsoft Azure Cache For Redis Rediscacheaccesspolicies Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicies-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Rediscacheaccesspolicies Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicies-overlay/)
- [Microsoft Azure Cache For Redis Rediscacheaccesspolicyassignments Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicyassignments-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Rediscacheaccesspolicyassignments Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rediscacheaccesspolicyassignments-overlay/)
- [Microsoft Azure Cache For Redis Redisfirewallrules Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisfirewallrules-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Redisfirewallrules Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisfirewallrules-overlay/)
- [Microsoft Azure Cache For Redis Redispatchschedules Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redispatchschedules-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Redispatchschedules Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redispatchschedules-overlay/)
- [Microsoft Azure Cache For Redis Redisresources Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisresources-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Redisresources Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-redisresources-overlay/)
- [Microsoft Azure Cache For Redis Subscriptions Api Phrasing Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-subscriptions-api-phrasing-overlay/)
- [Microsoft Azure Cache For Redis Subscriptions Overlay](https://apis.io/overlays/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-subscriptions-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Microsoft Azure Cache For Redis Authentication](https://apis.io/security/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-authentication/)
- [Microsoft Azure Cache For Redis Domain Security](https://apis.io/security/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-domain-security/)
- [Microsoft Azure Cache For Redis Trust Center](https://apis.io/security/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-trust-center/)
- [Microsoft Azure Cache For Redis Vulnerability Disclosure](https://apis.io/security/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Microsoft Azure Cache For Redis Scopes](https://apis.io/scopes/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Microsoft Azure Cache For Redis Plans Pricing](https://apis.io/plans/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Microsoft Azure Cache For Redis Rate Limits](https://apis.io/rate-limits/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Microsoft Azure Cache For Redis Finops](https://apis.io/finops/microsoft-azure-cache-for-redis/microsoft-azure-cache-for-redis-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.microsoft.com/)
- [Documentation](https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/)
- [Getting started](https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/quickstart-create-redis)
- [API reference](https://learn.microsoft.com/en-us/rest/api/redis/)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/cache/)
- [Sign up](https://azure.microsoft.com/en-us/free/)
- [Support](https://azure.microsoft.com/en-us/support/options/)
- [Blog](https://azure.microsoft.com/en-us/blog/feed/)
- [Terms of service](https://www.microsoft.com/en-us/legal/terms-of-use)
- [Privacy policy](https://privacy.microsoft.com/en-us/privacystatement)
- [GitHub](https://github.com/Azure)
- [Status](https://azure.status.microsoft/en-us/status)

## API Evangelist rating

**Kin Score 73.6** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.7 |
| Contract quality | 52.6 |
| Contract governance | 18.2 |
| Operational transparency | 92.1 |
| Developer ergonomics | 73.2 |
| Access clarity | 92.1 |

**Agent readiness 41.4** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/microsoft-azure-cache-for-redis/](https://apis.io/providers/microsoft-azure-cache-for-redis/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Microsoft Azure Cache For Redis: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/microsoft-azure-cache-for-redis/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
