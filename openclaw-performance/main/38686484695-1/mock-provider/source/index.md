# OpenClaw Source Performance

Generated: 2026-10-15T05:34:14.399Z

## Gateway Boot

| case | name | readyz p50 | readyz p95 | healthz p50 | http listen p50 | gateway ready p50 | first output p50 | RSS p95 | CPU core p95 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| default | gateway default | 4707.2ms | 4850.3ms | 3250.5ms | 4104.9ms | 4658.7ms | 258.0ms | 1625.5MB | 1.506 |
| skipChannels | gateway, skip channels | 4769.5ms | 4808.7ms | 3320.1ms | 4232.4ms | 4754.3ms | 262.4ms | 1953.7MB | 1.469 |
| preparedRuntimeCatalogStall | gateway, prepared runtime with CPU-stalling live catalog | 4527.6ms | 4565.0ms | 3300.8ms | 4047.3ms | 4521.0ms | 251.1ms | 2041.5MB | 1.349 |
| preparedRuntimeScaleOne | gateway, prepared runtime scale with one agent | 4593.5ms | 4864.7ms | 3301.1ms | 4024.1ms | 4570.3ms | 251.3ms | 2050.6MB | 1.439 |
| preparedRuntimeScaleMany | gateway, prepared runtime scale with 11 shared-workspace agents and one distinct | 5230.0ms | 5279.6ms | 3591.0ms | 4454.7ms | 5204.4ms | 266.2ms | 2177.7MB | 1.540 |
| oneInternalHook | gateway, one configured internal hook | 5106.0ms | 5111.3ms | 3527.2ms | 4511.7ms | 5086.8ms | 256.4ms | 1985.0MB | 1.385 |
| allInternalHooks | gateway, all internal hooks | 5157.4ms | 5171.2ms | 3548.0ms | 4537.6ms | 5142.1ms | 267.0ms | 1917.5MB | 1.364 |
| fiftyPlugins | gateway, 50 manifest plugins | 4985.3ms | 4989.0ms | 3458.1ms | 4365.1ms | 4962.2ms | 262.7ms | 1935.5MB | 1.430 |
| fiftyStartupLazyPlugins | gateway, 50 startup-lazy manifest plugins | 4619.4ms | 4648.1ms | 3380.0ms | 4101.7ms | 4609.7ms | 256.8ms | 2071.9MB | 1.366 |

## Memory Trend

Compared with the latest published mock-provider source probe for this tested ref.

| surface | case | baseline RSS p95 | current RSS p95 | RSS delta | heap delta | state |
| --- | --- | --- | --- | --- | --- | --- |
| gateway boot | default | 1516.6MB | 1625.5MB | +108.9MB (+7.2%) | +38.7MB (+13.6%) | stable |
| gateway boot | skipChannels | 1865.3MB | 1953.7MB | +88.4MB (+4.7%) | -2.9MB (-1.2%) | stable |
| gateway boot | preparedRuntimeCatalogStall | 1801.9MB | 2041.5MB | +239.7MB (+13.3%) | -20.0MB (-8.1%) | stable |
| gateway boot | preparedRuntimeScaleOne | 1795.5MB | 2050.6MB | +255.1MB (+14.2%) | +3.5MB (+1.4%) | stable |
| gateway boot | preparedRuntimeScaleMany | 2035.5MB | 2177.7MB | +142.2MB (+7.0%) | +4.3MB (+1.9%) | stable |
| gateway boot | oneInternalHook | 1937.2MB | 1985.0MB | +47.8MB (+2.5%) | -3.9MB (-1.6%) | stable |
| gateway boot | allInternalHooks | 1891.2MB | 1917.5MB | +26.4MB (+1.4%) | -2.1MB (-0.9%) | stable |
| gateway boot | fiftyPlugins | 1890.5MB | 1935.5MB | +45.0MB (+2.4%) | -5.9MB (-2.4%) | stable |
| gateway boot | fiftyStartupLazyPlugins | 2079.8MB | 2071.9MB | -8.0MB (-0.4%) | -5.1MB (-2.1%) | stable |
| cli | gatewayHealthJsonWarmState | 73.6MiB | 73.5MiB | -0.1MiB (-0.1%) | n/a | stable |
| cli | gatewayHealthJsonFreshState | 73.7MiB | 73.6MiB | -0.1MiB (-0.2%) | n/a | stable |
| cli | configGetGatewayPort | 73.6MiB | 73.7MiB | +0.2MiB (+0.2%) | n/a | stable |
| mock hello | gateway RSS delta avg | 744.5MB | 821.2MB | +76.7MB (+10.3%) | n/a | stable |

## Bundled Plugin Import Memory

Per-plugin rows are isolated cold imports and are not additive. The combined row measures all selected bundled-plugin entrypoints in one process.

| measurement | max RSS | delta from empty process | status |
| --- | --- | --- | --- |
| empty Node process | 46.3MB | 0.0MB | ok |
| all 166 bundled plugins | 550.0MB | 503.6MB | ok |

| plugin | isolated max RSS | isolated delta from empty process | status |
| --- | --- | --- | --- |
| workboard | 393.1MB | 346.8MB | ok |
| active-memory | 384.7MB | 338.3MB | ok |
| agentsapi | 336.3MB | 289.9MB | ok |
| policy | 332.7MB | 286.3MB | ok |
| muse | 330.7MB | 284.3MB | ok |
| opencode | 327.5MB | 281.1MB | ok |
| deepinfra | 324.6MB | 278.2MB | ok |
| voice-call | 324.3MB | 278.0MB | ok |
| xai | 321.5MB | 275.2MB | ok |
| clickclack | 320.9MB | 274.6MB | ok |

## Startup Hotspots

| case | phase | p50 | p95 |
| --- | --- | --- | --- |
| default | cli.main.gateway-run-parse | 5702.5ms | 5730.5ms |
| default | process.bootstrap | 1873.7ms | 1923.0ms |
| default | runtime.post-attach | 814.4ms | 834.1ms |
| default | sessions.projection | 612.1ms | 615.1ms |
| default | cli.main.gateway-run-bootstrap | 486.9ms | 503.2ms |
| skipChannels | cli.main.gateway-run-parse | 5967.4ms | 6080.3ms |
| skipChannels | process.bootstrap | 1889.7ms | 1907.5ms |
| skipChannels | post-ready.maintenance | 767.7ms | 821.0ms |
| skipChannels | sessions.projection | 619.0ms | 621.3ms |
| skipChannels | cli.main.gateway-run-bootstrap | 492.3ms | 501.1ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-parse | 5656.0ms | 5668.7ms |
| preparedRuntimeCatalogStall | process.bootstrap | 1859.5ms | 1875.4ms |
| preparedRuntimeCatalogStall | post-ready.maintenance | 788.8ms | 861.7ms |
| preparedRuntimeCatalogStall | sessions.projection | 616.9ms | 656.8ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-bootstrap | 478.2ms | 504.1ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-parse | 6156.9ms | 6156.9ms |
| preparedRuntimeScaleOne | process.bootstrap | 1912.5ms | 1973.8ms |
| preparedRuntimeScaleOne | post-ready.maintenance | 852.0ms | 868.8ms |
| preparedRuntimeScaleOne | sessions.projection | 623.8ms | 653.7ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-bootstrap | 485.4ms | 498.7ms |
| preparedRuntimeScaleMany | process.bootstrap | 1998.7ms | 2023.9ms |
| preparedRuntimeScaleMany | post-ready.maintenance | 1319.1ms | 1338.7ms |
| preparedRuntimeScaleMany | sessions.projection | 782.4ms | 798.2ms |
| preparedRuntimeScaleMany | sidecars.model-runtime | 545.4ms | 548.3ms |
| preparedRuntimeScaleMany | cli.main.gateway-run-bootstrap | 524.6ms | 536.2ms |
| oneInternalHook | cli.main.gateway-run-parse | 6217.4ms | 6223.5ms |
| oneInternalHook | process.bootstrap | 2005.7ms | 2010.6ms |
| oneInternalHook | post-ready.maintenance | 803.1ms | 826.1ms |
| oneInternalHook | sessions.projection | 649.1ms | 675.4ms |
| oneInternalHook | cli.main.gateway-run-bootstrap | 522.1ms | 535.4ms |
| allInternalHooks | cli.main.gateway-run-parse | 6259.3ms | 6286.7ms |
| allInternalHooks | process.bootstrap | 2037.8ms | 2080.8ms |
| allInternalHooks | post-ready.maintenance | 750.5ms | 786.6ms |
| allInternalHooks | sessions.projection | 654.3ms | 673.3ms |
| allInternalHooks | cli.main.gateway-run-bootstrap | 549.0ms | 552.3ms |
| fiftyPlugins | cli.main.gateway-run-parse | 6084.4ms | 6160.4ms |
| fiftyPlugins | process.bootstrap | 1981.2ms | 2032.6ms |
| fiftyPlugins | post-ready.maintenance | 786.1ms | 835.7ms |
| fiftyPlugins | sessions.projection | 647.0ms | 668.0ms |
| fiftyPlugins | cli.main.gateway-run-bootstrap | 524.2ms | 540.5ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-parse | 5649.4ms | 5979.7ms |
| fiftyStartupLazyPlugins | process.bootstrap | 1949.9ms | 2004.8ms |
| fiftyStartupLazyPlugins | post-ready.maintenance | 750.2ms | 785.7ms |
| fiftyStartupLazyPlugins | sessions.projection | 617.5ms | 617.8ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-bootstrap | 514.7ms | 594.3ms |

## Fake Model Hello Loops

| run | status | pass | wall | gateway CPU core | RSS start | RSS end | RSS delta | model |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| run-001 | pass | 1/1 | 11368.0ms | 0.880 | 1864.2MB | 2594.8MB | 730.6MB | mock-openai/gpt-5.6-luna |
| run-002 | pass | 1/1 | 11734.0ms | 0.937 | 1795.1MB | 2620.1MB | 825.0MB | mock-openai/gpt-5.6-luna |
| run-003 | pass | 1/1 | 11286.0ms | 0.975 | 1853.3MB | 2761.2MB | 907.9MB | mock-openai/gpt-5.6-luna |

## CLI Against Booted Gateway

RSS metric: legacy-last-marker; values are MiB.

| case | command | duration p50 | duration p95 | RSS p95 | exits |
| --- | --- | --- | --- | --- | --- |
| gatewayHealthJsonWarmState | gateway health --json (warm state) | 581.3ms | 926.7ms | 73.5MiB | code:0 x3 |
| gatewayHealthJsonFreshState | gateway health --json (fresh state) | 538.7ms | 587.1ms | 73.6MiB | code:0 x3 |
| configGetGatewayPort | config get gateway.port | 595.1ms | 599.8ms | 73.7MiB | code:0 x3 |

## SQLite State Smoke

| run | format | profile | SQLite | state schema | agent schema | state rows | agent rows | integrity | WAL before | WAL after | total |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| current | v2 | smoke | 3.53.3 | 22 | 27 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 305.9ms |
| baseline | v2 | smoke | 3.53.3 | 22 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 303.9ms |

| scenario | database | rows | runs | p50 | p95 | baseline rows | baseline runs | baseline p95 | delta | plan/index |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cron.store.load | state | 13 | 20 | 0.0ms | 0.0ms | 13 | 20 | 0.0ms | -8.7% | indexes: idx_cron_jobs_store_order; full scans: none; temp sorts: none |
| task-runs.cron.list | state | 1000 | 20 | 1.6ms | 1.7ms | 1000 | 20 | 1.8ms | -9.0% | indexes: idx_task_runs_runtime_status; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| task-runs.cron-source.list | state | 250 | 20 | 0.4ms | 0.4ms | 250 | 20 | 0.4ms | -0.9% | indexes: idx_task_runs_runtime_source_ended; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| delivery.pending.load | state | 696 | 20 | 0.3ms | 0.3ms | 696 | 20 | 0.3ms | +9.6% | indexes: idx_delivery_queue_pending; full scans: none; temp sorts: none |
| ingress.pending.first-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | -4.5% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +4.2% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.id-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +4.9% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| ingress.pending.id-seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +4.0% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| plugin-state.namespace.live | state | 675 | 20 | 0.3ms | 0.3ms | 675 | 20 | 0.3ms | -5.0% | indexes: idx_plugin_state_listing; full scans: none; temp sorts: none |
| agent-cache.plugin-model-catalog.list | agent | 64 | 20 | 0.0ms | 0.0ms | 64 | 20 | 0.0ms | 0.0% | indexes: sqlite_autoindex_cache_entries_1; full scans: none; temp sorts: none |
| transcript.tail.metadata | agent | 256 | 20 | 0.1ms | 0.1ms | 256 | 20 | 0.2ms | -18.6% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |
| transcript.tail.payload | agent | 256 | 20 | 1.9ms | 2.4ms | 256 | 20 | 2.3ms | +3.7% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |

## Observations

No data.

