# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 1954 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2218.1 MB, gateway 1954 MB, command-tree 861.7 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 1954 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2218.1 MB, gateway 1954 MB, command-tree 861.7 MB |
| Blocking findings | 16 |
| Warnings | 0 |
| Records | 6 (FAIL:6) |

## Proof Completeness

- Completeness: complete: 6
- Required obligations: 358 total, 0 missing, 1 failed
- Categories: command: 304, artifact: 6, cleanup: 6, collector: 6, invariant: 36

| Scenario | Obligation | Status | Reason |
|---|---|---|---|
| gateway-performance | cleanup:env-cleanup | failed | env destroy command failed |

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261014-052432-3ccdcd` |
| Generated | 2026-10-14T05:47:54.797Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1954 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2218.1 MB, gateway 1954 MB, command-tree 861.7 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2218.1 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 726ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 19 |
| incomplete | OpenClaw | gateway-performance/many-bundled-plugins | cleanup proof failed: disposable Kova env cleanup completed or was explicitly accounted for | env destroy command failed |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2097.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2359.4 MB, gateway 2097.7 MB, command-tree 813 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 57 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2359.4 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 57 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 99ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 57 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 1974.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2228.1 MB, gateway 1974.7 MB, command-tree 772.2 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2228.1 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 785ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 3 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1470.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1666.2 MB, agent-process 1470.1 MB, status-cli 882.4 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1470.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1666.2 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1470.1 |
| info | Kova | report | 4 additional finding(s) omitted from Markdown | see summary JSON |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 3 | FAIL:3 | 19ms | 1974.7MB | n/a | 266.1% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 3 | FAIL:3 | n/a | 0MB | n/a | 210.3% | 8516ms | 8236ms | 7961ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 19ms | 1954 MB | 2930.2 MB | n/a | n/a | gateway peak RSS 1954 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2218.1 MB, gateway 1954 MB, command-tree 861.7 MB |
| 2 | FAIL | gateway-performance/many-bundled-plugins |  | 57ms | 2097.7 MB | 2918.1 MB | n/a | n/a | gateway peak RSS 2097.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2359.4 MB, gateway 2097.7 MB, command-tree 813 MB |
| 3 | FAIL | gateway-performance/many-bundled-plugins |  | 3ms | 1974.7 MB | 3003.2 MB | n/a | n/a | gateway peak RSS 1974.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2228.1 MB, gateway 1974.7 MB, command-tree 772.2 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1737.3 MB | 8766ms | 8189ms | agent-process peak RSS 1470.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1666.2 MB, agent-process 1470.1 MB, status-cli 882.4 MB |
| 2 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1692.5 MB | 7771ms | 8263ms | agent-process peak RSS 1418.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1618.4 MB, agent-process 1418.2 MB, status-cli 880.9 MB |
| 3 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1736 MB | 8516ms | 8236ms | agent-process peak RSS 1468.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1664.4 MB, agent-process 1468.4 MB, status-cli 995.5 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2359.4 MB (scenario gateway-performance/many-bundled-plugins); CPU 295.1% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 2097.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 277.2% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1666.2 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 232.4% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1470.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 212.9% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 995.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 198.4% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 203.8 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 211.2% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 572.4 MB (scenario gateway-performance/many-bundled-plugins); CPU 144.7% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 373.8 MB (scenario gateway-performance/many-bundled-plugins); CPU 142.2% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroy-failed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-005107f3-kova-261014-052432-3ccdcd
Measurements:
- startup: listening 1ms; health 19ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 18ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 153ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1954 MB; tracked total 2930.2 MB; max CPU 266.1%; samples 41; roles gateway-tree 2218.1MB/278.4%, gateway 1954MB/266.1%, command-tree 861.7MB/170.4%, status-cli 861.7MB/170.4%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 1779.02ms; embedded traces 0; liveness warnings 0; open spans 4 (1 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1954 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2218.1 MB, gateway 1954 MB, command-tree 861.7 MB
  - gateway-tree peak RSS 2218.1 MB exceeded threshold 1440 MB
  - 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 726ms
- Failed command: `ocm env destroy 'kova-gateway-performance-man-005107f3-kova-261014-052432-3ccdcd' --yes`
- Failure: ocm: environment process state changed during inspection; retry the command

### gateway-performance sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-1e8be6a8-kova-261014-052432-3ccdcd
Measurements:
- startup: listening 0ms; health 57ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 57ms; post-ready p95 3ms; failures 0; final failures 0; slowest startup-sample/cold-start 57ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2097.7 MB; tracked total 2918.1 MB; max CPU 277.2%; samples 41; roles gateway-tree 2359.4MB/295.1%, gateway 2097.7MB/277.2%, command-tree 813MB/171.3%, status-cli 813MB/171.3%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 1803.06ms; embedded traces 0; liveness warnings 0; open spans 4 (1 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2097.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2359.4 MB, gateway 2097.7 MB, command-tree 813 MB
  - gateway-tree peak RSS 2359.4 MB exceeded threshold 1440 MB
  - 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 99ms

### gateway-performance sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-958fde53-kova-261014-052432-3ccdcd
Measurements:
- startup: listening 0ms; health 3ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 3ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 114ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 1974.7 MB; tracked total 3003.2 MB; max CPU 252.8%; samples 39; roles gateway-tree 2228.1MB/275.7%, gateway 1974.7MB/252.8%, command-tree 772.2MB/141.1%, status-cli 772.2MB/138%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 1662.31ms; embedded traces 0; liveness warnings 0; open spans 3 (1 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 1974.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2228.1 MB, gateway 1974.7 MB, command-tree 772.2 MB
  - gateway-tree peak RSS 2228.1 MB exceeded threshold 1440 MB
  - 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 785ms

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-8e2a29af-kova-261014-052432-3ccdcd
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1470.1 MB; tracked total 1737.3 MB; max CPU 210.3%; samples 29; roles command-tree 1666.2MB/224.4%, agent-process 1470.1MB/210.3%, agent-cli 198.6MB/211.2%, status-cli 882.4MB/186.6%
- agent: turn 8766ms; cold/warm 8766ms/8189ms; cold-warm delta 577ms; pre-provider 8238ms; provider 2ms; metadata scans 14 (350.23ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8737.15ms; max 8766ms; pre-provider p95 8213ms
- agent CLI attribution: cold known 4973ms / unattributed 3265ms; warm known 5114ms / unattributed 2624ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1595.93ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1470.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1666.2 MB, agent-process 1470.1 MB, status-cli 882.4 MB
  - command-tree peak RSS 1666.2 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 8766ms; pre-provider 8238ms; provider 2ms; post-provider 526ms; response true
    - active window: metadata scans 7 (190.77ms total, max 75.6ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 8238ms; provider 2ms; post-provider 526ms; unknown 3951.6ms; source agent.prepare 3765.07ms; plugins.metadata.scan 521.33ms
  - warm: total 8189ms; pre-provider 7738ms; provider 57ms; post-provider 394ms; response true
    - active window: metadata scans 7 (159.46ms total, max 59.05ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7738ms; provider 57ms; post-provider 394ms; unknown 3451.6ms; source agent.prepare 3765.07ms; plugins.metadata.scan 521.33ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 8238 ms | 4973 ms | 3265 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-8e2a29af-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |
  | warm | 7738 ms | 5114 ms | 2624 ms | 57 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-8e2a29af-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2544 ms | 1359 ms |
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2408 ms | 719 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1805 ms | 703 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 139 ms | 76 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 26 ms | 26 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 14 ms | 8 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2590 ms | 1596 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2176 ms | 644 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1961 ms | 689 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 159 ms | 59 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 19 ms | 19 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 13 ms | 10 ms |

### agent-cold-warm-message sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-2ab680e0-kova-261014-052432-3ccdcd
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1418.2 MB; tracked total 1692.5 MB; max CPU 200.7%; samples 28; roles command-tree 1618.4MB/216.5%, agent-process 1418.2MB/200.7%, status-cli 880.9MB/185.7%, agent-cli 203.8MB/120%
- agent: turn 8263ms; cold/warm 7771ms/8263ms; cold-warm delta 0ms; pre-provider 7923ms; provider 7ms; metadata scans 11 (262.03ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8238.4ms; max 8263ms; pre-provider p95 7901.85ms
- agent CLI attribution: cold known 4491ms / unattributed 3009ms; warm known 5218ms / unattributed 2705ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1767.58ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1418.2 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1618.4 MB, agent-process 1418.2 MB, status-cli 880.9 MB
  - command-tree peak RSS 1618.4 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7771ms; pre-provider 7500ms; provider 2ms; post-provider 269ms; response true
    - active window: metadata scans 4 (107.98ms total, max 61.77ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7500ms; provider 2ms; post-provider 269ms; unknown 3495.3ms; source agent.prepare 3597.64ms; plugins.metadata.scan 407.06ms
  - warm: total 8263ms; pre-provider 7923ms; provider 7ms; post-provider 333ms; response true
    - active window: metadata scans 7 (154.05ms total, max 54.82ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7923ms; provider 7ms; post-provider 333ms; unknown 3918.3ms; source agent.prepare 3597.64ms; plugins.metadata.scan 407.06ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7500 ms | 4491 ms | 3009 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-2ab680e0-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |
  | warm | 7923 ms | 5218 ms | 2705 ms | 7 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-2ab680e0-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2356 ms | 674 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2148 ms | 1053 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1651 ms | 660 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 108 ms | 62 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 16 ms | 8 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2746 ms | 1768 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2093 ms | 622 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1948 ms | 694 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 155 ms | 55 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 8 ms | 4 ms |

### agent-cold-warm-message sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-67b331a3-kova-261014-052432-3ccdcd
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1468.4 MB; tracked total 1736 MB; max CPU 212.9%; samples 29; roles command-tree 1664.4MB/232.4%, agent-process 1468.4MB/212.9%, status-cli 995.5MB/198.4%, agent-cli 200.3MB/105.4%
- agent: turn 8516ms; cold/warm 8516ms/8236ms; cold-warm delta 280ms; pre-provider 7961ms; provider 2ms; metadata scans 14 (329.03ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8502ms; max 8516ms; pre-provider p95 7958.15ms
- agent CLI attribution: cold known 4620ms / unattributed 3341ms; warm known 5263ms / unattributed 2641ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1671.45ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1468.4 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1664.4 MB, agent-process 1468.4 MB, status-cli 995.5 MB
  - command-tree peak RSS 1664.4 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 8516ms; pre-provider 7961ms; provider 2ms; post-provider 553ms; response true
    - active window: metadata scans 7 (154.22ms total, max 59.63ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7961ms; provider 2ms; post-provider 553ms; unknown 3592.87ms; source agent.prepare 3858.89ms; plugins.metadata.scan 509.24ms
  - warm: total 8236ms; pre-provider 7904ms; provider 11ms; post-provider 321ms; response true
    - active window: metadata scans 7 (174.81ms total, max 60.76ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7904ms; provider 11ms; post-provider 321ms; unknown 3535.87ms; source agent.prepare 3858.89ms; plugins.metadata.scan 509.24ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7961 ms | 4620 ms | 3341 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-67b331a3-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |
  | warm | 7904 ms | 5263 ms | 2641 ms | 11 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-67b331a3-kova-261014-052432-3ccdcd/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2171 ms | 1165 ms |
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 2145 ms | 631 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1907 ms | 770 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 105 ms | 60 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 14 ms | 7 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2709 ms | 1671 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2285 ms | 669 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1953 ms | 634 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 175 ms | 61 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 20 ms | 20 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 15 ms | 11 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261014-052432-3ccdcd-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261014-052432-3ccdcd-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261014-052432-3ccdcd-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-005107f3-kova-261014-052432-3ccdcd
- collector-root gateway-performance#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-1e8be6a8-kova-261014-052432-3ccdcd
- collector-root gateway-performance#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-gateway-performance-man-958fde53-kova-261014-052432-3ccdcd
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-8e2a29af-kova-261014-052432-3ccdcd
- collector-root agent-cold-warm-message#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-2ab680e0-kova-261014-052432-3ccdcd
- collector-root agent-cold-warm-message#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261014-052432-3ccdcd/kova-agent-cold-warm-message-67b331a3-kova-261014-052432-3ccdcd

## Target Cleanup

- Runtime: `kova-local-mv7o0s0b-3tc-9c4842f5`
- Result: remove-failed
- Duration: 2ms

