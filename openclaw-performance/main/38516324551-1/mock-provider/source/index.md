# OpenClaw Source Performance

Generated: 2026-10-14T05:35:07.712Z

## Gateway Boot

| case | name | readyz p50 | readyz p95 | healthz p50 | http listen p50 | gateway ready p50 | first output p50 | RSS p95 | CPU core p95 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| default | gateway default | 6718.5ms | 7155.3ms | 4739.7ms | 5781.1ms | 6556.1ms | 330.1ms | 1516.6MB | 1.537 |
| skipChannels | gateway, skip channels | 6046.8ms | 7194.8ms | 4185.6ms | 5337.5ms | 6025.0ms | 293.2ms | 1865.3MB | 1.529 |
| preparedRuntimeCatalogStall | gateway, prepared runtime with CPU-stalling live catalog | 5759.4ms | 6201.8ms | 4194.0ms | 5054.1ms | 5736.5ms | 340.5ms | 1801.9MB | 1.451 |
| preparedRuntimeScaleOne | gateway, prepared runtime scale with one agent | 5999.2ms | 6646.6ms | 4108.1ms | 5107.0ms | 5953.7ms | 320.9ms | 1795.5MB | 1.505 |
| preparedRuntimeScaleMany | gateway, prepared runtime scale with 11 shared-workspace agents and one distinct | 6365.9ms | 6451.5ms | 4151.5ms | 5225.2ms | 6306.5ms | 290.1ms | 2035.5MB | 1.571 |
| oneInternalHook | gateway, one configured internal hook | 6334.9ms | 6339.8ms | 4149.0ms | 5457.6ms | 6304.2ms | 272.3ms | 1937.2MB | 1.453 |
| allInternalHooks | gateway, all internal hooks | 5458.6ms | 6291.7ms | 3770.6ms | 4766.8ms | 5428.2ms | 285.6ms | 1891.2MB | 1.466 |
| fiftyPlugins | gateway, 50 manifest plugins | 5835.3ms | 6137.0ms | 3451.5ms | 4364.9ms | 5807.2ms | 267.6ms | 1890.5MB | 1.542 |
| fiftyStartupLazyPlugins | gateway, 50 startup-lazy manifest plugins | 4669.9ms | 4832.1ms | 3371.8ms | 4106.3ms | 4638.3ms | 253.1ms | 2079.8MB | 1.499 |

## Memory Trend

Compared with the latest published mock-provider source probe for this tested ref.

| surface | case | baseline RSS p95 | current RSS p95 | RSS delta | heap delta | state |
| --- | --- | --- | --- | --- | --- | --- |
| gateway boot | default | 1618.1MB | 1516.6MB | -101.5MB (-6.3%) | -48.8MB (-14.6%) | stable |
| gateway boot | skipChannels | 1918.0MB | 1865.3MB | -52.6MB (-2.7%) | -0.7MB (-0.3%) | stable |
| gateway boot | preparedRuntimeCatalogStall | 1871.6MB | 1801.9MB | -69.7MB (-3.7%) | +15.3MB (+6.6%) | stable |
| gateway boot | preparedRuntimeScaleOne | 1882.0MB | 1795.5MB | -86.5MB (-4.6%) | -5.7MB (-2.3%) | stable |
| gateway boot | preparedRuntimeScaleMany | 2210.3MB | 2035.5MB | -174.7MB (-7.9%) | -45.5MB (-16.7%) | stable |
| gateway boot | oneInternalHook | 1974.3MB | 1937.2MB | -37.1MB (-1.9%) | +19.3MB (+8.5%) | stable |
| gateway boot | allInternalHooks | 1922.3MB | 1891.2MB | -31.1MB (-1.6%) | +7.8MB (+3.3%) | stable |
| gateway boot | fiftyPlugins | 1852.9MB | 1890.5MB | +37.6MB (+2.0%) | -7.9MB (-3.1%) | stable |
| gateway boot | fiftyStartupLazyPlugins | 1961.5MB | 2079.8MB | +118.4MB (+6.0%) | -8.0MB (-3.2%) | stable |
| cli | gatewayHealthJsonWarmState | 82.1MiB | 73.6MiB | -8.5MiB (-10.3%) | n/a | stable |
| cli | gatewayHealthJsonFreshState | 82.0MiB | 73.7MiB | -8.3MiB (-10.1%) | n/a | stable |
| cli | configGetGatewayPort | 82.8MiB | 73.6MiB | -9.2MiB (-11.1%) | n/a | stable |
| mock hello | gateway RSS delta avg | 771.3MB | 744.5MB | -26.8MB (-3.5%) | n/a | stable |

## Bundled Plugin Import Memory

Per-plugin rows are isolated cold imports and are not additive. The combined row measures all selected bundled-plugin entrypoints in one process.

| measurement | max RSS | delta from empty process | status |
| --- | --- | --- | --- |
| empty Node process | 46.3MB | 0.0MB | ok |
| all 164 bundled plugins | 544.9MB | 498.6MB | ok |

| plugin | isolated max RSS | isolated delta from empty process | status |
| --- | --- | --- | --- |
| active-memory | 388.0MB | 341.8MB | ok |
| workboard | 387.9MB | 341.6MB | ok |
| policy | 334.6MB | 288.4MB | ok |
| agentsapi | 332.6MB | 286.4MB | ok |
| voice-call | 320.3MB | 274.1MB | ok |
| xai | 316.7MB | 270.4MB | ok |
| cloudflare-ai-gateway | 315.0MB | 268.7MB | ok |
| clickclack | 312.2MB | 266.0MB | ok |
| opencode | 311.2MB | 265.0MB | ok |
| deepinfra | 308.1MB | 261.8MB | ok |

## Startup Hotspots

| case | phase | p50 | p95 |
| --- | --- | --- | --- |
| default | cli.main.gateway-run-parse | 7712.9ms | 8164.8ms |
| default | process.bootstrap | 2744.4ms | 2979.1ms |
| default | runtime.post-attach | 1268.8ms | 1370.9ms |
| default | cli.main.gateway-run-bootstrap | 853.5ms | 911.1ms |
| default | process.bootstrap.cli.main.gateway-run-bootstrap | 853.5ms | 911.1ms |
| skipChannels | cli.main.gateway-run-parse | 7545.6ms | 7556.1ms |
| skipChannels | process.bootstrap | 2409.1ms | 2557.8ms |
| skipChannels | post-ready.maintenance | 1037.0ms | 1119.2ms |
| skipChannels | sessions.projection | 748.8ms | 859.9ms |
| skipChannels | cli.main.gateway-run-bootstrap | 689.6ms | 712.5ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-parse | 7032.2ms | 7032.2ms |
| preparedRuntimeCatalogStall | process.bootstrap | 2465.0ms | 2578.7ms |
| preparedRuntimeCatalogStall | post-ready.maintenance | 994.7ms | 1071.8ms |
| preparedRuntimeCatalogStall | sessions.projection | 742.4ms | 803.7ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-bootstrap | 715.4ms | 727.2ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-parse | 7505.0ms | 7990.3ms |
| preparedRuntimeScaleOne | process.bootstrap | 2322.5ms | 2610.9ms |
| preparedRuntimeScaleOne | post-ready.maintenance | 952.9ms | 993.1ms |
| preparedRuntimeScaleOne | sessions.projection | 893.5ms | 949.3ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-bootstrap | 623.3ms | 735.2ms |
| preparedRuntimeScaleMany | process.bootstrap | 2373.7ms | 2481.5ms |
| preparedRuntimeScaleMany | post-ready.maintenance | 1477.0ms | 1530.2ms |
| preparedRuntimeScaleMany | sessions.projection | 865.2ms | 896.8ms |
| preparedRuntimeScaleMany | cli.main.gateway-run-bootstrap | 725.8ms | 745.8ms |
| preparedRuntimeScaleMany | process.bootstrap.cli.main.gateway-run-bootstrap | 725.8ms | 745.8ms |
| oneInternalHook | cli.main.gateway-run-parse | 7461.0ms | 7879.0ms |
| oneInternalHook | process.bootstrap | 2379.3ms | 2444.3ms |
| oneInternalHook | post-ready.maintenance | 963.9ms | 1022.2ms |
| oneInternalHook | sessions.projection | 721.4ms | 829.1ms |
| oneInternalHook | cli.main.gateway-run-bootstrap | 605.5ms | 627.4ms |
| allInternalHooks | cli.main.gateway-run-parse | 6425.8ms | 6559.1ms |
| allInternalHooks | process.bootstrap | 2316.8ms | 2344.1ms |
| allInternalHooks | post-ready.maintenance | 758.7ms | 874.9ms |
| allInternalHooks | sessions.projection | 671.5ms | 875.1ms |
| allInternalHooks | cli.main.gateway-run-bootstrap | 633.3ms | 682.9ms |
| fiftyPlugins | cli.main.gateway-run-parse | 7227.1ms | 7241.7ms |
| fiftyPlugins | process.bootstrap | 2043.1ms | 2133.4ms |
| fiftyPlugins | sidecars.model-runtime | 1104.8ms | 1221.1ms |
| fiftyPlugins | sidecars.reply-runtime | 990.6ms | 1104.1ms |
| fiftyPlugins | post-ready.maintenance | 685.6ms | 693.1ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-parse | 6199.4ms | 6369.6ms |
| fiftyStartupLazyPlugins | process.bootstrap | 2007.7ms | 2106.6ms |
| fiftyStartupLazyPlugins | post-ready.maintenance | 769.6ms | 822.6ms |
| fiftyStartupLazyPlugins | sessions.projection | 630.3ms | 661.1ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-bootstrap | 599.1ms | 631.6ms |

## Fake Model Hello Loops

| run | status | pass | wall | gateway CPU core | RSS start | RSS end | RSS delta | model |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| run-001 | pass | 1/1 | 11517.0ms | 0.955 | 1660.8MB | 2533.5MB | 872.7MB | mock-openai/gpt-5.6-luna |
| run-002 | pass | 1/1 | 11530.0ms | 0.867 | 1792.9MB | 2472.4MB | 679.6MB | mock-openai/gpt-5.6-luna |
| run-003 | pass | 1/1 | 10814.0ms | 0.925 | 1857.5MB | 2538.7MB | 681.2MB | mock-openai/gpt-5.6-luna |

## CLI Against Booted Gateway

RSS metric: legacy-last-marker; values are MiB.

| case | command | duration p50 | duration p95 | RSS p95 | exits |
| --- | --- | --- | --- | --- | --- |
| gatewayHealthJsonWarmState | gateway health --json (warm state) | 581.3ms | 957.9ms | 73.6MiB | code:0 x3 |
| gatewayHealthJsonFreshState | gateway health --json (fresh state) | 554.3ms | 559.9ms | 73.7MiB | code:0 x3 |
| configGetGatewayPort | config get gateway.port | 594.2ms | 613.7ms | 73.6MiB | code:0 x3 |

## SQLite State Smoke

| run | format | profile | SQLite | state schema | agent schema | state rows | agent rows | integrity | WAL before | WAL after | total |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| current | v2 | smoke | 3.53.3 | 22 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 303.9ms |
| baseline | v2 | smoke | 3.53.3 | 21 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 610.7ms |

| scenario | database | rows | runs | p50 | p95 | baseline rows | baseline runs | baseline p95 | delta | plan/index |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cron.store.load | state | 13 | 20 | 0.0ms | 0.0ms | 13 | 20 | 0.0ms | -17.9% | indexes: idx_cron_jobs_store_order; full scans: none; temp sorts: none |
| task-runs.cron.list | state | 1000 | 20 | 1.5ms | 1.8ms | 1000 | 20 | 2.3ms | -18.4% | indexes: idx_task_runs_runtime_status; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| task-runs.cron-source.list | state | 250 | 20 | 0.4ms | 0.4ms | 250 | 20 | 0.7ms | -38.4% | indexes: idx_task_runs_runtime_source_ended; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| delivery.pending.load | state | 696 | 20 | 0.3ms | 0.3ms | 696 | 20 | 0.6ms | -53.7% | indexes: idx_delivery_queue_pending; full scans: none; temp sorts: none |
| ingress.pending.first-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | -24.3% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.2ms | -39.9% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.id-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | -19.0% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| ingress.pending.id-seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.2ms | -53.7% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| plugin-state.namespace.live | state | 675 | 20 | 0.3ms | 0.3ms | 675 | 20 | 0.5ms | -38.7% | indexes: idx_plugin_state_listing; full scans: none; temp sorts: none |
| agent-cache.plugin-model-catalog.list | agent | 64 | 20 | 0.0ms | 0.0ms | 64 | 20 | 0.0ms | -53.5% | indexes: sqlite_autoindex_cache_entries_1; full scans: none; temp sorts: none |
| transcript.tail.metadata | agent | 256 | 20 | 0.1ms | 0.2ms | 256 | 20 | 0.3ms | -41.1% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |
| transcript.tail.payload | agent | 256 | 20 | 1.8ms | 2.3ms | 256 | 20 | 3.4ms | -31.0% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |

## Observations

No data.

