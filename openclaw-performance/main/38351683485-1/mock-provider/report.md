# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 2093.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2409.8 MB, gateway 2093.6 MB, command-tree 978.5 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 2093.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2409.8 MB, gateway 2093.6 MB, command-tree 978.5 MB |
| Blocking findings | 15 |
| Warnings | 0 |
| Records | 6 (FAIL:6) |

## Proof Completeness

- Completeness: complete: 6
- Required obligations: 358 total, 0 missing, 0 failed
- Categories: command: 304, artifact: 6, cleanup: 6, collector: 6, invariant: 36

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261013-053147-79131b` |
| Generated | 2026-10-13T05:53:29.341Z |
| Mode | execution |
| Target | `local-build:/home/runner/_work/openclaw/openclaw` |
| Platform | linux 6.6.141 (x64) · v24.19.0 |
| Repeat / parallel | 3 / 1 |
| Auth | mock (openai) |
| Network frontage | port |

## Coverage

| Field | Value |
|---|---:|
| Records | 6 |
| Scenarios | 2 |
| States | 2 |
| FAIL | 6 |

## Findings

| Severity | Area | Scenario | Finding | Evidence |
|---|---|---|---|---|
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2093.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2409.8 MB, gateway 2093.6 MB, command-tree 978.5 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 37 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2409.8 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 37 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 978.5 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 37 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2082.1 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2399.2 MB, gateway 2082.1 MB, command-tree 926 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2399.2 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 926 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1992 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2307.9 MB, gateway 1992 MB, command-tree 1101.7 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 5 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2307.9 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 5 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 1101.7 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 5 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1449 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1550.1 MB, agent-process 1449 MB, status-cli 1011.2 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1449 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1550.1 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1449 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1504.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1606.7 MB, agent-process 1504.8 MB, status-cli 907.5 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1504.8 |
| info | Kova | report | 3 additional finding(s) omitted from Markdown | see summary JSON |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 3 | FAIL:3 | 5ms | 2082.1MB | n/a | 269.6% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 3 | FAIL:3 | n/a | 0MB | n/a | 193% | 7629ms | 8238ms | 7355ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 37ms | 2093.6 MB | 3461 MB | n/a | n/a | gateway peak RSS 2093.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2409.8 MB, gateway 2093.6 MB, command-tree 978.5 MB |
| 2 | FAIL | gateway-performance/many-bundled-plugins |  | 3ms | 2082.1 MB | 3397.8 MB | n/a | n/a | gateway peak RSS 2082.1 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2399.2 MB, gateway 2082.1 MB, command-tree 926 MB |
| 3 | FAIL | gateway-performance/many-bundled-plugins |  | 5ms | 1992 MB | 3284.3 MB | n/a | n/a | gateway peak RSS 1992 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2307.9 MB, gateway 1992 MB, command-tree 1101.7 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1621.4 MB | 7570ms | 10259ms | agent-process peak RSS 1449 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1550.1 MB, agent-process 1449 MB, status-cli 1011.2 MB |
| 2 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1679.1 MB | 7829ms | 8238ms | agent-process peak RSS 1504.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1606.7 MB, agent-process 1504.8 MB, status-cli 907.5 MB |
| 3 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1612.9 MB | 7629ms | 8163ms | agent-process peak RSS 1440.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1541.4 MB, agent-process 1440.4 MB, status-cli 981.4 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2409.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 327.7% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 2093.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 292.2% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1606.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 209.6% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1504.8 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 199.8% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1101.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 195% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 782.3 MB (scenario gateway-performance/many-bundled-plugins); CPU 147.7% (scenario gateway-performance/many-bundled-plugins)
- agent-cli: RSS 201.7 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 162.1% (scenario agent-cold-warm-message/mock-openai-provider)
- model-cli: RSS 448.9 MB (scenario gateway-performance/many-bundled-plugins); CPU 149.1% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-005107f3-kova-261013-053147-79131b
Measurements:
- startup: listening 1ms; health 37ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 36ms; post-ready p95 2ms; failures 0; final failures 0; slowest final/final 83ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2093.6 MB; tracked total 3461 MB; max CPU 269.6%; samples 43; roles gateway-tree 2409.8MB/295.6%, gateway 2093.6MB/269.6%, command-tree 978.5MB/159.3%, status-cli 978.5MB/159.3%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1679.06ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2093.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2409.8 MB, gateway 2093.6 MB, command-tree 978.5 MB
  - gateway-tree peak RSS 2409.8 MB exceeded threshold 1440 MB
  - status-cli peak RSS 978.5 MB exceeded threshold 900 MB

### gateway-performance sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-1e8be6a8-kova-261013-053147-79131b
Measurements:
- startup: listening 1ms; health 3ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 3ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 56ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2082.1 MB; tracked total 3397.8 MB; max CPU 266.6%; samples 43; roles gateway-tree 2399.2MB/290.7%, gateway 2082.1MB/266.6%, command-tree 926MB/160.5%, status-cli 926MB/160.5%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span sidecars.subagent-recovery 1695.11ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2082.1 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2399.2 MB, gateway 2082.1 MB, command-tree 926 MB
  - gateway-tree peak RSS 2399.2 MB exceeded threshold 1440 MB
  - status-cli peak RSS 926 MB exceeded threshold 900 MB

### gateway-performance sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-958fde53-kova-261013-053147-79131b
Measurements:
- startup: listening 0ms; health 5ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 5ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 115ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1992 MB; tracked total 3284.3 MB; max CPU 292.2%; samples 44; roles gateway-tree 2307.9MB/327.7%, gateway 1992MB/292.2%, command-tree 1101.7MB/150.9%, status-cli 1101.7MB/150.9%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span cli.command-startup 2391.09ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1992 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2307.9 MB, gateway 1992 MB, command-tree 1101.7 MB
  - gateway-tree peak RSS 2307.9 MB exceeded threshold 1440 MB
  - status-cli peak RSS 1101.7 MB exceeded threshold 900 MB

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-8e2a29af-kova-261013-053147-79131b
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1449 MB; tracked total 1621.4 MB; max CPU 199.8%; samples 30; roles command-tree 1550.1MB/209.6%, agent-process 1449MB/199.8%, status-cli 1011.2MB/195%, agent-cli 198.5MB/112.4%
- agent: turn 10259ms; cold/warm 7570ms/10259ms; cold-warm delta 0ms; pre-provider 9661ms; provider 135ms; metadata scans 11 (266.45ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 10124.55ms; max 10259ms; pre-provider p95 9543.05ms
- agent CLI attribution: cold known 3729ms / unattributed 3573ms; warm known 4735ms / unattributed 4926ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1402.48ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1449 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1550.1 MB, agent-process 1449 MB, status-cli 1011.2 MB
  - command-tree peak RSS 1550.1 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7570ms; pre-provider 7302ms; provider 2ms; post-provider 266ms; response true
    - active window: metadata scans 4 (103.7ms total, max 54.38ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7302ms; provider 2ms; post-provider 266ms; unknown 3635.61ms; source agent.prepare 3247.9ms; plugins.metadata.scan 418.49ms
  - warm: total 10259ms; pre-provider 9661ms; provider 135ms; post-provider 463ms; response true
    - active window: metadata scans 7 (162.75ms total, max 55.26ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 9661ms; provider 135ms; post-provider 463ms; unknown 5994.61ms; source agent.prepare 3247.9ms; plugins.metadata.scan 418.49ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7302 ms | 3729 ms | 3573 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-8e2a29af-kova-261013-053147-79131b/openclaw/timeline.jsonl |
  | warm | 9661 ms | 4735 ms | 4926 ms | 135 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-8e2a29af-kova-261013-053147-79131b/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1902 ms | 543 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1594 ms | 643 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1469 ms | 688 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 104 ms | 55 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 8 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2453 ms | 1402 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1770 ms | 514 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1654 ms | 862 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 163 ms | 56 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 5 ms | 5 ms |

### agent-cold-warm-message sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-2ab680e0-kova-261013-053147-79131b
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1504.8 MB; tracked total 1679.1 MB; max CPU 188.5%; samples 27; roles command-tree 1606.7MB/198.4%, agent-process 1504.8MB/188.5%, status-cli 907.5MB/184.5%, agent-cli 201.7MB/125.8%
- agent: turn 8238ms; cold/warm 7829ms/8238ms; cold-warm delta 0ms; pre-provider 7969ms; provider 0ms; metadata scans 8 (215.61ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8217.55ms; max 8238ms; pre-provider p95 7948.4ms
- agent CLI attribution: cold known 3809ms / unattributed 3748ms; warm known 4204ms / unattributed 3765ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1351.51ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1504.8 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1606.7 MB, agent-process 1504.8 MB, status-cli 907.5 MB
  - command-tree peak RSS 1606.7 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7829ms; pre-provider 7557ms; provider 2ms; post-provider 270ms; response true
    - active window: metadata scans 4 (105.45ms total, max 56.47ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7557ms; provider 2ms; post-provider 270ms; unknown 4209.26ms; source agent.prepare 3011.64ms; plugins.metadata.scan 336.1ms
  - warm: total 8238ms; pre-provider 7969ms; provider 0ms; post-provider 269ms; response true
    - active window: metadata scans 4 (110.16ms total, max 56.2ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7969ms; provider 0ms; post-provider 269ms; unknown 4621.26ms; source agent.prepare 3011.64ms; plugins.metadata.scan 336.1ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7557 ms | 3809 ms | 3748 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-2ab680e0-kova-261013-053147-79131b/openclaw/timeline.jsonl |
  | warm | 7969 ms | 4204 ms | 3765 ms | 0 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-2ab680e0-kova-261013-053147-79131b/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 1871 ms | 538 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1723 ms | 664 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1481 ms | 688 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 106 ms | 57 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2272 ms | 1351 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1827 ms | 531 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1289 ms | 640 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 111 ms | 56 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 6 ms | 3 ms |

### agent-cold-warm-message sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-67b331a3-kova-261013-053147-79131b
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1440.4 MB; tracked total 1612.9 MB; max CPU 193%; samples 27; roles command-tree 1541.4MB/203%, agent-process 1440.4MB/193%, status-cli 981.4MB/178.9%, agent-cli 189.1MB/162.1%
- agent: turn 8163ms; cold/warm 7629ms/8163ms; cold-warm delta 0ms; pre-provider 7893ms; provider 1ms; metadata scans 8 (212.67ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8136.3ms; max 8163ms; pre-provider p95 7866.1ms
- agent CLI attribution: cold known 3679ms / unattributed 3676ms; warm known 4105ms / unattributed 3788ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1316.68ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1440.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1541.4 MB, agent-process 1440.4 MB, status-cli 981.4 MB
  - command-tree peak RSS 1541.4 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7629ms; pre-provider 7355ms; provider 2ms; post-provider 272ms; response true
    - active window: metadata scans 4 (104.8ms total, max 56.09ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7355ms; provider 2ms; post-provider 272ms; unknown 4194.84ms; source agent.prepare 2830.81ms; plugins.metadata.scan 329.35ms
  - warm: total 8163ms; pre-provider 7893ms; provider 1ms; post-provider 269ms; response true
    - active window: metadata scans 4 (107.87ms total, max 58.73ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7893ms; provider 1ms; post-provider 269ms; unknown 4732.84ms; source agent.prepare 2830.81ms; plugins.metadata.scan 329.35ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7355 ms | 3679 ms | 3676 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-67b331a3-kova-261013-053147-79131b/openclaw/timeline.jsonl |
  | warm | 7893 ms | 4105 ms | 3788 ms | 1 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-67b331a3-kova-261013-053147-79131b/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 1833 ms | 505 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1550 ms | 626 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 1483 ms | 723 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 104 ms | 56 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2217 ms | 1317 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x11 | 11 | 0 | 1767 ms | 504 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1280 ms | 651 ms |
  | warm | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 107 ms | 59 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 3 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261013-053147-79131b-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261013-053147-79131b-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261013-053147-79131b-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-005107f3-kova-261013-053147-79131b
- collector-root gateway-performance#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-1e8be6a8-kova-261013-053147-79131b
- collector-root gateway-performance#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-gateway-performance-man-958fde53-kova-261013-053147-79131b
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-8e2a29af-kova-261013-053147-79131b
- collector-root agent-cold-warm-message#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-2ab680e0-kova-261013-053147-79131b
- collector-root agent-cold-warm-message#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261013-053147-79131b/kova-agent-cold-warm-message-67b331a3-kova-261013-053147-79131b

## Target Cleanup

- Runtime: `kova-local-mv68u91n-3tf-96f86026`
- Result: removed
- Duration: 540ms

