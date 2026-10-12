# OpenClaw Source Performance

Generated: 2026-10-12T05:44:37.463Z

## Gateway Boot

| case | name | readyz p50 | readyz p95 | healthz p50 | http listen p50 | gateway ready p50 | first output p50 | RSS p95 | CPU core p95 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| default | gateway default | 5316.3ms | 5509.1ms | 4413.9ms | 4741.9ms | 5243.4ms | 236.8ms | 1435.5MB | 1.321 |
| skipChannels | gateway, skip channels | 5250.9ms | 5364.5ms | 4744.1ms | 4858.3ms | 5232.7ms | 255.7ms | 1682.0MB | 1.305 |
| preparedRuntimeCatalogStall | gateway, prepared runtime with CPU-stalling live catalog | 5176.7ms | 5848.2ms | 4813.5ms | 4788.2ms | 5146.7ms | 239.7ms | 1603.3MB | 1.368 |
| preparedRuntimeScaleOne | gateway, prepared runtime scale with one agent | 5574.1ms | 5684.9ms | 5090.7ms | 5055.4ms | 5543.0ms | 245.2ms | 1616.7MB | 1.321 |
| preparedRuntimeScaleMany | gateway, prepared runtime scale with 11 shared-workspace agents and one distinct | 5841.6ms | 5863.3ms | 5221.6ms | 5193.6ms | 5825.0ms | 271.0ms | 1530.7MB | 1.369 |
| oneInternalHook | gateway, one configured internal hook | 6093.2ms | 6452.6ms | 5521.6ms | 5647.0ms | 6065.1ms | 288.9ms | 1689.3MB | 1.314 |
| allInternalHooks | gateway, all internal hooks | 5786.4ms | 5989.0ms | 5185.6ms | 5288.9ms | 5762.4ms | 268.6ms | 1689.7MB | 1.336 |
| fiftyPlugins | gateway, 50 manifest plugins | 5871.8ms | 6131.3ms | 5036.7ms | 5227.9ms | 5848.7ms | 261.8ms | 1585.9MB | 1.362 |
| fiftyStartupLazyPlugins | gateway, 50 startup-lazy manifest plugins | 5056.6ms | 5148.9ms | 4765.0ms | 4729.5ms | 5040.5ms | 241.6ms | 1652.6MB | 1.214 |

## Memory Trend

Compared with the latest published mock-provider source probe for this tested ref.

| surface | case | baseline RSS p95 | current RSS p95 | RSS delta | heap delta | state |
| --- | --- | --- | --- | --- | --- | --- |
| gateway boot | default | 1440.6MB | 1435.5MB | -5.1MB (-0.4%) | +9.7MB (+3.0%) | stable |
| gateway boot | skipChannels | 1645.4MB | 1682.0MB | +36.5MB (+2.2%) | -4.9MB (-2.1%) | stable |
| gateway boot | preparedRuntimeCatalogStall | 1583.2MB | 1603.3MB | +20.1MB (+1.3%) | +41.7MB (+21.5%) | stable |
| gateway boot | preparedRuntimeScaleOne | 1525.2MB | 1616.7MB | +91.5MB (+6.0%) | +32.0MB (+16.5%) | stable |
| gateway boot | preparedRuntimeScaleMany | 1540.8MB | 1530.7MB | -10.1MB (-0.7%) | -12.0MB (-5.0%) | stable |
| gateway boot | oneInternalHook | 1629.5MB | 1689.3MB | +59.9MB (+3.7%) | -3.9MB (-1.6%) | stable |
| gateway boot | allInternalHooks | 1603.0MB | 1689.7MB | +86.7MB (+5.4%) | -20.0MB (-8.3%) | stable |
| gateway boot | fiftyPlugins | 1567.2MB | 1585.9MB | +18.7MB (+1.2%) | +34.9MB (+17.9%) | stable |
| gateway boot | fiftyStartupLazyPlugins | 1513.1MB | 1652.6MB | +139.4MB (+9.2%) | +34.1MB (+17.5%) | stable |
| cli | gatewayHealthJsonWarmState | 73.8MiB | 74.0MiB | +0.2MiB (+0.3%) | n/a | stable |
| cli | gatewayHealthJsonFreshState | 73.7MiB | 73.5MiB | -0.2MiB (-0.3%) | n/a | stable |
| cli | configGetGatewayPort | 73.9MiB | 73.5MiB | -0.3MiB (-0.4%) | n/a | stable |
| mock hello | gateway RSS delta avg | 705.1MB | 677.0MB | -28.1MB (-4.0%) | n/a | stable |

## Bundled Plugin Import Memory

Per-plugin rows are isolated cold imports and are not additive. The combined row measures all selected bundled-plugin entrypoints in one process.

| measurement | max RSS | delta from empty process | status |
| --- | --- | --- | --- |
| empty Node process | 46.3MB | 0.0MB | ok |
| all 162 bundled plugins | 560.6MB | 514.3MB | ok |

| plugin | isolated max RSS | isolated delta from empty process | status |
| --- | --- | --- | --- |
| active-memory | 383.6MB | 337.4MB | ok |
| workboard | 374.9MB | 328.6MB | ok |
| agentsapi | 336.5MB | 290.3MB | ok |
| voice-call | 332.1MB | 285.8MB | ok |
| policy | 328.9MB | 282.6MB | ok |
| copilot | 322.3MB | 276.0MB | ok |
| canvas | 319.6MB | 273.3MB | ok |
| deepinfra | 319.4MB | 273.2MB | ok |
| tencent | 317.7MB | 271.4MB | ok |
| clickclack | 316.9MB | 270.6MB | ok |

## Startup Hotspots

| case | phase | p50 | p95 |
| --- | --- | --- | --- |
| default | cli.main.gateway-run-parse | 6450.8ms | 6518.1ms |
| default | process.bootstrap | 2085.7ms | 2105.9ms |
| default | gateway.request-runtime | 909.6ms | 989.8ms |
| default | runtime.post-attach | 897.7ms | 901.6ms |
| default | sessions.projection | 860.9ms | 942.9ms |
| skipChannels | cli.main.gateway-run-parse | 6619.3ms | 6645.7ms |
| skipChannels | process.bootstrap | 2028.7ms | 2137.3ms |
| skipChannels | gateway.request-runtime | 903.6ms | 942.3ms |
| skipChannels | sessions.projection | 866.9ms | 900.8ms |
| skipChannels | cli.main.gateway-run-bootstrap | 668.4ms | 697.9ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-parse | 6548.2ms | 7409.2ms |
| preparedRuntimeCatalogStall | process.bootstrap | 2021.5ms | 2345.1ms |
| preparedRuntimeCatalogStall | gateway.request-runtime | 1000.9ms | 1123.8ms |
| preparedRuntimeCatalogStall | sessions.projection | 953.3ms | 1060.1ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-bootstrap | 662.2ms | 797.3ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-parse | 6943.2ms | 7192.5ms |
| preparedRuntimeScaleOne | process.bootstrap | 2243.2ms | 2262.9ms |
| preparedRuntimeScaleOne | gateway.request-runtime | 972.5ms | 987.8ms |
| preparedRuntimeScaleOne | sessions.projection | 933.7ms | 942.0ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-bootstrap | 721.8ms | 727.3ms |
| preparedRuntimeScaleMany | process.bootstrap | 2288.9ms | 2323.7ms |
| preparedRuntimeScaleMany | gateway.request-runtime | 1021.3ms | 1024.2ms |
| preparedRuntimeScaleMany | sessions.projection | 967.1ms | 975.8ms |
| preparedRuntimeScaleMany | cli.main.gateway-run-bootstrap | 780.8ms | 788.1ms |
| preparedRuntimeScaleMany | process.bootstrap.cli.main.gateway-run-bootstrap | 780.8ms | 788.1ms |
| oneInternalHook | cli.main.gateway-run-parse | 7593.6ms | 7622.7ms |
| oneInternalHook | process.bootstrap | 2503.7ms | 2534.6ms |
| oneInternalHook | gateway.request-runtime | 1046.8ms | 1139.0ms |
| oneInternalHook | sessions.projection | 999.6ms | 1075.0ms |
| oneInternalHook | cli.main.gateway-run-bootstrap | 877.1ms | 887.0ms |
| allInternalHooks | cli.main.gateway-run-parse | 7151.1ms | 7414.7ms |
| allInternalHooks | process.bootstrap | 2176.6ms | 2249.4ms |
| allInternalHooks | gateway.request-runtime | 1009.9ms | 1060.3ms |
| allInternalHooks | sessions.projection | 958.4ms | 996.5ms |
| allInternalHooks | cli.main.gateway-run-bootstrap | 729.5ms | 739.5ms |
| fiftyPlugins | cli.main.gateway-run-parse | 7283.1ms | 7376.6ms |
| fiftyPlugins | process.bootstrap | 2192.0ms | 2346.4ms |
| fiftyPlugins | gateway.request-runtime | 1004.7ms | 1057.2ms |
| fiftyPlugins | sessions.projection | 955.8ms | 1009.0ms |
| fiftyPlugins | cli.main.gateway-run-bootstrap | 745.8ms | 833.4ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-parse | 6296.6ms | 6527.3ms |
| fiftyStartupLazyPlugins | process.bootstrap | 2076.5ms | 2082.8ms |
| fiftyStartupLazyPlugins | gateway.request-runtime | 924.2ms | 925.4ms |
| fiftyStartupLazyPlugins | sessions.projection | 882.7ms | 886.4ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-bootstrap | 703.2ms | 714.2ms |

## Fake Model Hello Loops

| run | status | pass | wall | gateway CPU core | RSS start | RSS end | RSS delta | model |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| run-001 | pass | 1/1 | 13830.0ms | 0.651 | 1811.1MB | 2530.2MB | 719.2MB | mock-openai/gpt-5.6-luna |
| run-002 | pass | 1/1 | 14254.0ms | 0.631 | 1804.2MB | 2535.2MB | 731.0MB | mock-openai/gpt-5.6-luna |
| run-003 | pass | 1/1 | 14257.0ms | 0.701 | 1956.6MB | 2537.4MB | 580.8MB | mock-openai/gpt-5.6-luna |

## CLI Against Booted Gateway

RSS metric: legacy-last-marker; values are MiB.

| case | command | duration p50 | duration p95 | RSS p95 | exits |
| --- | --- | --- | --- | --- | --- |
| gatewayHealthJsonWarmState | gateway health --json (warm state) | 571.3ms | 611.3ms | 74.0MiB | code:0 x3 |
| gatewayHealthJsonFreshState | gateway health --json (fresh state) | 557.2ms | 575.1ms | 73.5MiB | code:0 x3 |
| configGetGatewayPort | config get gateway.port | 958.3ms | 982.7ms | 73.5MiB | code:0 x3 |

## SQLite State Smoke

| run | format | profile | SQLite | state schema | agent schema | state rows | agent rows | integrity | WAL before | WAL after | total |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| current | v2 | smoke | 3.53.3 | 20 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 444.5ms |
| baseline | v2 | smoke | 3.53.3 | 20 | 25 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 396.4ms |

| scenario | database | rows | runs | p50 | p95 | baseline rows | baseline runs | baseline p95 | delta | plan/index |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cron.store.load | state | 13 | 20 | 0.0ms | 0.0ms | 13 | 20 | 0.0ms | +5.0% | indexes: idx_cron_jobs_store_order; full scans: none; temp sorts: none |
| task-runs.cron.list | state | 1000 | 20 | 1.8ms | 1.8ms | 1000 | 20 | 1.7ms | +6.7% | indexes: idx_task_runs_runtime_status; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| task-runs.cron-source.list | state | 250 | 20 | 0.5ms | 0.5ms | 250 | 20 | 0.4ms | +7.5% | indexes: idx_task_runs_runtime_source_ended; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| delivery.pending.load | state | 696 | 20 | 0.3ms | 0.3ms | 696 | 20 | 0.3ms | +7.2% | indexes: idx_delivery_queue_pending; full scans: none; temp sorts: none |
| ingress.pending.first-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +2.6% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +3.1% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.id-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +0.9% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| ingress.pending.id-seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +2.7% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| plugin-state.namespace.live | state | 675 | 20 | 0.3ms | 0.4ms | 675 | 20 | 0.3ms | +37.5% | indexes: idx_plugin_state_listing; full scans: none; temp sorts: none |
| agent-cache.plugin-model-catalog.list | agent | 64 | 20 | 0.0ms | 0.0ms | 64 | 20 | 0.0ms | +13.0% | indexes: sqlite_autoindex_cache_entries_1; full scans: none; temp sorts: none |
| transcript.tail.metadata | agent | 256 | 20 | 0.1ms | 0.2ms | 256 | 20 | 0.1ms | +6.3% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |
| transcript.tail.payload | agent | 256 | 20 | 2.0ms | 2.9ms | 256 | 20 | 2.5ms | +14.0% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |

## Observations

No data.

