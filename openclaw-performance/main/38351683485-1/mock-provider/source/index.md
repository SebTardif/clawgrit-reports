# OpenClaw Source Performance

Generated: 2026-10-13T05:41:31.396Z

## Gateway Boot

| case | name | readyz p50 | readyz p95 | healthz p50 | http listen p50 | gateway ready p50 | first output p50 | RSS p95 | CPU core p95 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| default | gateway default | 5598.0ms | 5872.7ms | 3590.1ms | 4928.1ms | 5496.6ms | 204.7ms | 1618.1MB | 1.701 |
| skipChannels | gateway, skip channels | 4992.3ms | 5489.0ms | 3472.0ms | 4602.5ms | 4971.2ms | 215.1ms | 1918.0MB | 1.640 |
| preparedRuntimeCatalogStall | gateway, prepared runtime with CPU-stalling live catalog | 5423.1ms | 5812.4ms | 3775.8ms | 5024.8ms | 5395.0ms | 218.2ms | 1871.6MB | 1.720 |
| preparedRuntimeScaleOne | gateway, prepared runtime scale with one agent | 5051.8ms | 5639.1ms | 3540.4ms | 4650.2ms | 5023.3ms | 205.9ms | 1882.0MB | 1.596 |
| preparedRuntimeScaleMany | gateway, prepared runtime scale with 11 shared-workspace agents and one distinct | 6832.0ms | 7487.3ms | 3419.9ms | 6257.2ms | 6812.0ms | 212.4ms | 2210.3MB | 1.620 |
| oneInternalHook | gateway, one configured internal hook | 5107.7ms | 5184.5ms | 3509.6ms | 4686.0ms | 5086.7ms | 199.2ms | 1974.3MB | 1.566 |
| allInternalHooks | gateway, all internal hooks | 4780.3ms | 5505.4ms | 3264.3ms | 4357.4ms | 4763.8ms | 189.2ms | 1922.3MB | 1.635 |
| fiftyPlugins | gateway, 50 manifest plugins | 4877.6ms | 4901.0ms | 3208.6ms | 4261.9ms | 4839.3ms | 189.1ms | 1852.9MB | 1.640 |
| fiftyStartupLazyPlugins | gateway, 50 startup-lazy manifest plugins | 4803.8ms | 4848.6ms | 3433.4ms | 4510.5ms | 4780.1ms | 196.6ms | 1961.5MB | 1.526 |

## Memory Trend

Compared with the latest published mock-provider source probe for this tested ref.

| surface | case | baseline RSS p95 | current RSS p95 | RSS delta | heap delta | state |
| --- | --- | --- | --- | --- | --- | --- |
| gateway boot | default | 1435.5MB | 1618.1MB | +182.6MB (+12.7%) | -4.1MB (-1.2%) | stable |
| gateway boot | skipChannels | 1682.0MB | 1918.0MB | +236.0MB (+14.0%) | +17.7MB (+7.8%) | stable |
| gateway boot | preparedRuntimeCatalogStall | 1603.3MB | 1871.6MB | +268.3MB (+16.7%) | -5.8MB (-2.5%) | stable |
| gateway boot | preparedRuntimeScaleOne | 1616.7MB | 1882.0MB | +265.3MB (+16.4%) | +26.2MB (+11.6%) | stable |
| gateway boot | preparedRuntimeScaleMany | 1530.7MB | 2210.3MB | +679.5MB (+44.4%) | +44.9MB (+19.8%) | watch |
| gateway boot | oneInternalHook | 1689.3MB | 1974.3MB | +284.9MB (+16.9%) | -21.2MB (-8.6%) | stable |
| gateway boot | allInternalHooks | 1689.7MB | 1922.3MB | +232.6MB (+13.8%) | +15.9MB (+7.2%) | stable |
| gateway boot | fiftyPlugins | 1585.9MB | 1852.9MB | +267.0MB (+16.8%) | +24.0MB (+10.4%) | stable |
| gateway boot | fiftyStartupLazyPlugins | 1652.6MB | 1961.5MB | +308.9MB (+18.7%) | +24.7MB (+10.8%) | stable |
| cli | gatewayHealthJsonWarmState | 74.0MiB | 82.1MiB | +8.1MiB (+10.9%) | n/a | stable |
| cli | gatewayHealthJsonFreshState | 73.5MiB | 82.0MiB | +8.5MiB (+11.6%) | n/a | stable |
| cli | configGetGatewayPort | 73.5MiB | 82.8MiB | +9.2MiB (+12.5%) | n/a | stable |
| mock hello | gateway RSS delta avg | 677.0MB | 771.3MB | +94.3MB (+13.9%) | n/a | stable |

## Bundled Plugin Import Memory

Per-plugin rows are isolated cold imports and are not additive. The combined row measures all selected bundled-plugin entrypoints in one process.

| measurement | max RSS | delta from empty process | status |
| --- | --- | --- | --- |
| empty Node process | 46.3MB | 0.0MB | ok |
| all 162 bundled plugins | 544.6MB | 498.4MB | ok |

| plugin | isolated max RSS | isolated delta from empty process | status |
| --- | --- | --- | --- |
| active-memory | 382.4MB | 336.1MB | ok |
| workboard | 375.5MB | 329.2MB | ok |
| agentsapi | 334.7MB | 288.4MB | ok |
| policy | 328.2MB | 282.0MB | ok |
| clickclack | 326.3MB | 280.0MB | ok |
| deepinfra | 323.3MB | 277.1MB | ok |
| canvas | 321.2MB | 274.9MB | ok |
| voice-call | 320.6MB | 274.3MB | ok |
| cloudflare-ai-gateway | 317.1MB | 270.9MB | ok |
| copilot | 314.2MB | 268.0MB | ok |

## Startup Hotspots

| case | phase | p50 | p95 |
| --- | --- | --- | --- |
| default | cli.main.gateway-run-parse | 6813.6ms | 7126.0ms |
| default | process.bootstrap | 2058.5ms | 2187.0ms |
| default | runtime.post-attach | 1106.0ms | 1165.9ms |
| default | runtime.early | 782.9ms | 876.0ms |
| default | runtime.early.skills-listener | 762.2ms | 851.7ms |
| skipChannels | cli.main.gateway-run-parse | 6144.2ms | 6565.1ms |
| skipChannels | process.bootstrap | 2122.7ms | 2132.1ms |
| skipChannels | runtime.early | 737.8ms | 782.6ms |
| skipChannels | runtime.early.skills-listener | 718.4ms | 763.1ms |
| skipChannels | sessions.projection | 675.8ms | 741.9ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-parse | 6456.0ms | 6869.4ms |
| preparedRuntimeCatalogStall | process.bootstrap | 2242.9ms | 2430.2ms |
| preparedRuntimeCatalogStall | runtime.early | 793.8ms | 1006.1ms |
| preparedRuntimeCatalogStall | sessions.projection | 778.3ms | 963.7ms |
| preparedRuntimeCatalogStall | runtime.early.skills-listener | 778.1ms | 982.8ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-parse | 6063.1ms | 6668.1ms |
| preparedRuntimeScaleOne | process.bootstrap | 2160.9ms | 2572.3ms |
| preparedRuntimeScaleOne | runtime.early | 696.3ms | 711.8ms |
| preparedRuntimeScaleOne | runtime.early.skills-listener | 668.7ms | 694.6ms |
| preparedRuntimeScaleOne | sessions.projection | 643.8ms | 668.4ms |
| preparedRuntimeScaleMany | runtime.early | 2601.8ms | 2990.9ms |
| preparedRuntimeScaleMany | runtime.early.skills-listener | 2587.7ms | 2957.2ms |
| preparedRuntimeScaleMany | process.bootstrap | 2076.5ms | 2147.6ms |
| preparedRuntimeScaleMany | sessions.projection | 661.2ms | 739.4ms |
| preparedRuntimeScaleMany | cli.main.gateway-run-bootstrap | 595.2ms | 605.6ms |
| oneInternalHook | cli.main.gateway-run-parse | 6113.1ms | 6271.7ms |
| oneInternalHook | process.bootstrap | 2106.2ms | 2176.5ms |
| oneInternalHook | runtime.early | 682.0ms | 734.1ms |
| oneInternalHook | runtime.early.skills-listener | 666.0ms | 716.7ms |
| oneInternalHook | sessions.projection | 642.8ms | 680.0ms |
| allInternalHooks | cli.main.gateway-run-parse | 5870.4ms | 6554.7ms |
| allInternalHooks | process.bootstrap | 1981.5ms | 1986.3ms |
| allInternalHooks | runtime.early | 679.0ms | 828.1ms |
| allInternalHooks | runtime.early.skills-listener | 661.5ms | 811.7ms |
| allInternalHooks | sessions.projection | 661.2ms | 770.8ms |
| fiftyPlugins | cli.main.gateway-run-parse | 6000.5ms | 6053.6ms |
| fiftyPlugins | process.bootstrap | 1961.1ms | 1967.3ms |
| fiftyPlugins | runtime.early | 688.6ms | 692.3ms |
| fiftyPlugins | runtime.early.skills-listener | 674.7ms | 677.8ms |
| fiftyPlugins | sessions.projection | 608.5ms | 612.8ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-parse | 5758.2ms | 5897.6ms |
| fiftyStartupLazyPlugins | process.bootstrap | 2077.3ms | 2090.5ms |
| fiftyStartupLazyPlugins | runtime.early | 704.4ms | 746.5ms |
| fiftyStartupLazyPlugins | runtime.early.skills-listener | 686.9ms | 728.7ms |
| fiftyStartupLazyPlugins | sessions.projection | 630.7ms | 643.0ms |

## Fake Model Hello Loops

| run | status | pass | wall | gateway CPU core | RSS start | RSS end | RSS delta | model |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| run-001 | pass | 1/1 | 15117.0ms | 0.728 | 2108.4MB | 2725.4MB | 616.9MB | mock-openai/gpt-5.6-luna |
| run-002 | pass | 1/1 | 15448.0ms | 0.842 | 1965.5MB | 3014.2MB | 1048.7MB | mock-openai/gpt-5.6-luna |
| run-003 | pass | 1/1 | 17219.0ms | 0.813 | 2076.9MB | 2725.0MB | 648.1MB | mock-openai/gpt-5.6-luna |

## CLI Against Booted Gateway

RSS metric: legacy-last-marker; values are MiB.

| case | command | duration p50 | duration p95 | RSS p95 | exits |
| --- | --- | --- | --- | --- | --- |
| gatewayHealthJsonWarmState | gateway health --json (warm state) | 885.3ms | 1138.5ms | 82.1MiB | code:0 x3 |
| gatewayHealthJsonFreshState | gateway health --json (fresh state) | 508.7ms | 585.7ms | 82.0MiB | code:0 x3 |
| configGetGatewayPort | config get gateway.port | 1065.5ms | 1069.5ms | 82.8MiB | code:0 x3 |

## SQLite State Smoke

| run | format | profile | SQLite | state schema | agent schema | state rows | agent rows | integrity | WAL before | WAL after | total |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| current | v2 | smoke | 3.53.3 | 21 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 610.7ms |
| baseline | v2 | smoke | 3.53.3 | 20 | 26 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 444.5ms |

| scenario | database | rows | runs | p50 | p95 | baseline rows | baseline runs | baseline p95 | delta | plan/index |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cron.store.load | state | 13 | 20 | 0.0ms | 0.0ms | 13 | 20 | 0.0ms | +33.3% | indexes: idx_cron_jobs_store_order; full scans: none; temp sorts: none |
| task-runs.cron.list | state | 1000 | 20 | 2.0ms | 2.3ms | 1000 | 20 | 1.8ms | +26.0% | indexes: idx_task_runs_runtime_status; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| task-runs.cron-source.list | state | 250 | 20 | 0.5ms | 0.7ms | 250 | 20 | 0.5ms | +45.8% | indexes: idx_task_runs_runtime_source_ended; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| delivery.pending.load | state | 696 | 20 | 0.4ms | 0.6ms | 696 | 20 | 0.3ms | +82.8% | indexes: idx_delivery_queue_pending; full scans: none; temp sorts: none |
| ingress.pending.first-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +26.5% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.seek-page | state | 100 | 20 | 0.1ms | 0.2ms | 100 | 20 | 0.1ms | +46.7% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.id-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +10.5% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| ingress.pending.id-seek-page | state | 100 | 20 | 0.1ms | 0.2ms | 100 | 20 | 0.1ms | +91.2% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| plugin-state.namespace.live | state | 675 | 20 | 0.3ms | 0.5ms | 675 | 20 | 0.4ms | +10.4% | indexes: idx_plugin_state_listing; full scans: none; temp sorts: none |
| agent-cache.plugin-model-catalog.list | agent | 64 | 20 | 0.0ms | 0.0ms | 64 | 20 | 0.0ms | +65.4% | indexes: sqlite_autoindex_cache_entries_1; full scans: none; temp sorts: none |
| transcript.tail.metadata | agent | 256 | 20 | 0.2ms | 0.3ms | 256 | 20 | 0.2ms | +90.8% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |
| transcript.tail.payload | agent | 256 | 20 | 2.3ms | 3.4ms | 256 | 20 | 2.9ms | +16.1% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |

## Observations

No data.

