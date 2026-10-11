# OpenClaw Source Performance

Generated: 2026-10-11T05:34:34.444Z

## Gateway Boot

| case | name | readyz p50 | readyz p95 | healthz p50 | http listen p50 | gateway ready p50 | first output p50 | RSS p95 | CPU core p95 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| default | gateway default | 4379.5ms | 4415.8ms | 3720.7ms | 3901.6ms | 4327.1ms | 224.9ms | 1440.6MB | 1.192 |
| skipChannels | gateway, skip channels | 4351.7ms | 4374.1ms | 3857.0ms | 4032.5ms | 4342.5ms | 222.2ms | 1645.4MB | 1.160 |
| preparedRuntimeCatalogStall | gateway, prepared runtime with CPU-stalling live catalog | 4067.1ms | 4156.6ms | 3662.8ms | 3844.4ms | 4059.0ms | 221.2ms | 1583.2MB | 1.230 |
| preparedRuntimeScaleOne | gateway, prepared runtime scale with one agent | 4246.2ms | 4276.7ms | 3736.5ms | 3916.2ms | 4236.3ms | 223.0ms | 1525.2MB | 1.192 |
| preparedRuntimeScaleMany | gateway, prepared runtime scale with 11 shared-workspace agents and one distinct | 4430.7ms | 4438.3ms | 3756.8ms | 3947.2ms | 4423.2ms | 228.5ms | 1540.8MB | 1.167 |
| oneInternalHook | gateway, one configured internal hook | 4422.6ms | 4448.8ms | 3889.7ms | 4064.3ms | 4412.5ms | 230.3ms | 1629.5MB | 1.144 |
| allInternalHooks | gateway, all internal hooks | 4384.8ms | 4427.1ms | 3859.0ms | 4031.8ms | 4362.9ms | 228.8ms | 1603.0MB | 1.142 |
| fiftyPlugins | gateway, 50 manifest plugins | 4606.7ms | 4624.1ms | 3879.1ms | 4070.8ms | 4591.5ms | 225.1ms | 1567.2MB | 1.317 |
| fiftyStartupLazyPlugins | gateway, 50 startup-lazy manifest plugins | 4143.8ms | 4203.8ms | 3709.7ms | 3901.5ms | 4127.8ms | 229.8ms | 1513.1MB | 1.212 |

## Memory Trend

Compared with the latest published mock-provider source probe for this tested ref.

| surface | case | baseline RSS p95 | current RSS p95 | RSS delta | heap delta | state |
| --- | --- | --- | --- | --- | --- | --- |
| gateway boot | default | 1396.9MB | 1440.6MB | +43.7MB (+3.1%) | +19.0MB (+6.1%) | stable |
| gateway boot | skipChannels | 1565.9MB | 1645.4MB | +79.5MB (+5.1%) | -0.2MB (-0.1%) | stable |
| gateway boot | preparedRuntimeCatalogStall | 1429.3MB | 1583.2MB | +153.9MB (+10.8%) | -39.4MB (-16.9%) | stable |
| gateway boot | preparedRuntimeScaleOne | 1420.3MB | 1525.2MB | +104.9MB (+7.4%) | -38.5MB (-16.6%) | stable |
| gateway boot | preparedRuntimeScaleMany | 1444.9MB | 1540.8MB | +95.9MB (+6.6%) | +55.9MB (+30.6%) | stable |
| gateway boot | oneInternalHook | 1490.2MB | 1629.5MB | +139.2MB (+9.3%) | +18.2MB (+7.8%) | stable |
| gateway boot | allInternalHooks | 1468.1MB | 1603.0MB | +134.9MB (+9.2%) | +9.4MB (+4.0%) | stable |
| gateway boot | fiftyPlugins | 1461.7MB | 1567.2MB | +105.5MB (+7.2%) | -39.3MB (-16.8%) | stable |
| gateway boot | fiftyStartupLazyPlugins | 1401.6MB | 1513.1MB | +111.5MB (+8.0%) | -38.6MB (-16.5%) | stable |
| cli | gatewayHealthJsonWarmState | 73.6MiB | 73.8MiB | +0.2MiB (+0.3%) | n/a | stable |
| cli | gatewayHealthJsonFreshState | 73.4MiB | 73.7MiB | +0.3MiB (+0.4%) | n/a | stable |
| cli | configGetGatewayPort | 73.4MiB | 73.9MiB | +0.5MiB (+0.6%) | n/a | stable |
| mock hello | gateway RSS delta avg | 614.6MB | 705.1MB | +90.4MB (+14.7%) | n/a | stable |

## Bundled Plugin Import Memory

Per-plugin rows are isolated cold imports and are not additive. The combined row measures all selected bundled-plugin entrypoints in one process.

| measurement | max RSS | delta from empty process | status |
| --- | --- | --- | --- |
| empty Node process | 46.4MB | 0.0MB | ok |
| all 162 bundled plugins | 544.3MB | 497.9MB | ok |

| plugin | isolated max RSS | isolated delta from empty process | status |
| --- | --- | --- | --- |
| workboard | 380.5MB | 334.1MB | ok |
| active-memory | 366.8MB | 320.4MB | ok |
| agentsapi | 335.5MB | 289.2MB | ok |
| policy | 328.8MB | 282.4MB | ok |
| canvas | 319.0MB | 272.7MB | ok |
| deepinfra | 318.8MB | 272.5MB | ok |
| llama-cpp | 318.0MB | 271.6MB | ok |
| voice-call | 317.8MB | 271.4MB | ok |
| clickclack | 316.9MB | 270.6MB | ok |
| xai | 314.8MB | 268.4MB | ok |

## Startup Hotspots

| case | phase | p50 | p95 |
| --- | --- | --- | --- |
| default | cli.main.gateway-run-parse | 5577.3ms | 5644.8ms |
| default | process.bootstrap | 1659.0ms | 1691.6ms |
| default | runtime.post-attach | 923.7ms | 943.8ms |
| default | cli.main.gateway-run-bootstrap | 709.4ms | 714.9ms |
| default | process.bootstrap.cli.main.gateway-run-bootstrap | 709.4ms | 714.9ms |
| skipChannels | cli.main.gateway-run-parse | 5753.1ms | 5758.2ms |
| skipChannels | process.bootstrap | 1647.0ms | 1658.4ms |
| skipChannels | cli.main.gateway-run-bootstrap | 700.3ms | 703.1ms |
| skipChannels | process.bootstrap.cli.main.gateway-run-bootstrap | 700.3ms | 703.1ms |
| skipChannels | cli.command.config-ready | 698.7ms | 701.6ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-parse | 5400.7ms | 5510.7ms |
| preparedRuntimeCatalogStall | process.bootstrap | 1637.8ms | 1686.2ms |
| preparedRuntimeCatalogStall | cli.main.gateway-run-bootstrap | 696.8ms | 713.6ms |
| preparedRuntimeCatalogStall | process.bootstrap.cli.main.gateway-run-bootstrap | 696.8ms | 713.6ms |
| preparedRuntimeCatalogStall | cli.command.config-ready | 695.5ms | 712.2ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-parse | 5580.2ms | 5747.5ms |
| preparedRuntimeScaleOne | process.bootstrap | 1666.6ms | 1699.6ms |
| preparedRuntimeScaleOne | cli.main.gateway-run-bootstrap | 723.1ms | 732.8ms |
| preparedRuntimeScaleOne | process.bootstrap.cli.main.gateway-run-bootstrap | 723.1ms | 732.8ms |
| preparedRuntimeScaleOne | cli.command.config-ready | 721.6ms | 731.5ms |
| preparedRuntimeScaleMany | process.bootstrap | 1709.4ms | 1711.2ms |
| preparedRuntimeScaleMany | cli.main.gateway-run-bootstrap | 737.6ms | 740.8ms |
| preparedRuntimeScaleMany | process.bootstrap.cli.main.gateway-run-bootstrap | 737.6ms | 740.8ms |
| preparedRuntimeScaleMany | cli.command.config-ready | 736.3ms | 739.4ms |
| preparedRuntimeScaleMany | process.bootstrap.cli.command.config-ready | 736.3ms | 739.4ms |
| oneInternalHook | cli.main.gateway-run-parse | 5816.5ms | 5870.7ms |
| oneInternalHook | process.bootstrap | 1671.7ms | 1700.5ms |
| oneInternalHook | cli.main.gateway-run-bootstrap | 715.0ms | 734.4ms |
| oneInternalHook | process.bootstrap.cli.main.gateway-run-bootstrap | 715.0ms | 734.4ms |
| oneInternalHook | cli.command.config-ready | 713.6ms | 733.3ms |
| allInternalHooks | cli.main.gateway-run-parse | 5241.4ms | 5749.5ms |
| allInternalHooks | process.bootstrap | 1660.4ms | 1663.9ms |
| allInternalHooks | cli.main.gateway-run-bootstrap | 703.3ms | 704.4ms |
| allInternalHooks | process.bootstrap.cli.main.gateway-run-bootstrap | 703.3ms | 704.4ms |
| allInternalHooks | cli.command.config-ready | 701.9ms | 703.1ms |
| fiftyPlugins | cli.main.gateway-run-parse | 6079.7ms | 6104.6ms |
| fiftyPlugins | process.bootstrap | 1688.3ms | 1694.3ms |
| fiftyPlugins | cli.main.gateway-run-bootstrap | 727.8ms | 728.2ms |
| fiftyPlugins | process.bootstrap.cli.main.gateway-run-bootstrap | 727.8ms | 728.2ms |
| fiftyPlugins | cli.command.config-ready | 726.5ms | 726.9ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-parse | 4926.2ms | 4996.0ms |
| fiftyStartupLazyPlugins | process.bootstrap | 1705.6ms | 1713.6ms |
| fiftyStartupLazyPlugins | cli.main.gateway-run-bootstrap | 738.7ms | 747.7ms |
| fiftyStartupLazyPlugins | process.bootstrap.cli.main.gateway-run-bootstrap | 738.7ms | 747.7ms |
| fiftyStartupLazyPlugins | cli.command.config-ready | 737.3ms | 746.1ms |

## Fake Model Hello Loops

| run | status | pass | wall | gateway CPU core | RSS start | RSS end | RSS delta | model |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| run-001 | pass | 1/1 | 11808.0ms | 0.593 | 1866.4MB | 2455.4MB | 589.0MB | mock-openai/gpt-5.6-luna |
| run-002 | pass | 1/1 | 11450.0ms | 0.611 | 1807.6MB | 2570.6MB | 763.0MB | mock-openai/gpt-5.6-luna |
| run-003 | pass | 1/1 | 11396.0ms | 0.527 | 1807.6MB | 2570.8MB | 763.3MB | mock-openai/gpt-5.6-luna |

## CLI Against Booted Gateway

RSS metric: legacy-last-marker; values are MiB.

| case | command | duration p50 | duration p95 | RSS p95 | exits |
| --- | --- | --- | --- | --- | --- |
| gatewayHealthJsonWarmState | gateway health --json (warm state) | 509.3ms | 533.6ms | 73.8MiB | code:0 x3 |
| gatewayHealthJsonFreshState | gateway health --json (fresh state) | 463.7ms | 465.1ms | 73.7MiB | code:0 x3 |
| configGetGatewayPort | config get gateway.port | 868.5ms | 897.9ms | 73.9MiB | code:0 x3 |

## SQLite State Smoke

| run | format | profile | SQLite | state schema | agent schema | state rows | agent rows | integrity | WAL before | WAL after | total |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| current | v2 | smoke | 3.53.3 | 20 | 25 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 396.4ms |
| baseline | v2 | smoke | 3.53.3 | 20 | 25 | 4100 | 1000 | ok | 3.5MB | 0.0MB | 336.8ms |

| scenario | database | rows | runs | p50 | p95 | baseline rows | baseline runs | baseline p95 | delta | plan/index |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cron.store.load | state | 13 | 20 | 0.0ms | 0.0ms | 13 | 20 | 0.0ms | 0.0% | indexes: idx_cron_jobs_store_order; full scans: none; temp sorts: none |
| task-runs.cron.list | state | 1000 | 20 | 1.7ms | 1.7ms | 1000 | 20 | 1.7ms | -0.7% | indexes: idx_task_runs_runtime_status; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| task-runs.cron-source.list | state | 250 | 20 | 0.4ms | 0.4ms | 250 | 20 | 0.4ms | 0.0% | indexes: idx_task_runs_runtime_source_ended; full scans: none; temp sorts: USE TEMP B-TREE FOR ORDER BY |
| delivery.pending.load | state | 696 | 20 | 0.3ms | 0.3ms | 696 | 20 | 0.3ms | +6.3% | indexes: idx_delivery_queue_pending; full scans: none; temp sorts: none |
| ingress.pending.first-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +7.5% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | -3.7% | indexes: idx_channel_ingress_pending; full scans: none; temp sorts: none |
| ingress.pending.id-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | +6.6% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| ingress.pending.id-seek-page | state | 100 | 20 | 0.1ms | 0.1ms | 100 | 20 | 0.1ms | -18.5% | indexes: sqlite_autoindex_channel_ingress_events_1; full scans: none; temp sorts: none |
| plugin-state.namespace.live | state | 675 | 20 | 0.3ms | 0.3ms | 675 | 20 | 0.3ms | +7.5% | indexes: idx_plugin_state_listing; full scans: none; temp sorts: none |
| agent-cache.plugin-model-catalog.list | agent | 64 | 20 | 0.0ms | 0.0ms | 64 | 20 | 0.0ms | +21.1% | indexes: sqlite_autoindex_cache_entries_1; full scans: none; temp sorts: none |
| transcript.tail.metadata | agent | 256 | 20 | 0.1ms | 0.1ms | 256 | 20 | 0.1ms | +5.9% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |
| transcript.tail.payload | agent | 256 | 20 | 1.9ms | 2.5ms | 256 | 20 | 2.3ms | +12.4% | indexes: idx_agent_transcript_active_messages, sqlite_autoindex_transcript_events_1; full scans: none; temp sorts: none |

## Observations

No data.

