# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — gateway peak RSS 2226.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2431.9 MB, gateway 2226.7 MB, command-tree 911.8 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | gateway peak RSS 2226.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2431.9 MB, gateway 2226.7 MB, command-tree 911.8 MB |
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
| Run ID | `kova-261015-052436-6c06b0` |
| Generated | 2026-10-15T05:47:35.740Z |
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
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2226.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2431.9 MB, gateway 2226.7 MB, command-tree 911.8 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 22 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2431.9 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 22 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | status-cli peak RSS 911.8 MB exceeded threshold 900 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 22 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 341ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 22 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2136.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2347.4 MB, gateway 2136.7 MB, command-tree 673.5 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 2 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2347.4 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 2 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway peak RSS 2107.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2312.6 MB, gateway 2107.6 MB, command-tree 669 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 36 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | gateway-tree peak RSS 2312.6 MB exceeded threshold 1440 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 36 |
| fail | OpenClaw | gateway-performance/many-bundled-plugins | 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 256ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; readinessHealthReadyMs: 36 |
| incomplete | OpenClaw | gateway-performance/many-bundled-plugins | cleanup proof failed: disposable Kova env cleanup completed or was explicitly accounted for | env destroy command failed |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1492.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1688.7 MB, agent-process 1492.7 MB, status-cli 972.1 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1492.7 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1688.7 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1492.7 |
| info | Kova | report | 4 additional finding(s) omitted from Markdown | see summary JSON |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| gateway-performance/many-bundled-plugins | 3 | FAIL:3 | 22ms | 2136.7MB | n/a | 275.9% | n/a | n/a | n/a |
| agent-cold-warm-message/mock-openai-provider | 3 | FAIL:3 | n/a | 0MB | n/a | 229.1% | 7746ms | 8410ms | 7391ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | gateway-performance/many-bundled-plugins |  | 22ms | 2226.7 MB | 3122.4 MB | n/a | n/a | gateway peak RSS 2226.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2431.9 MB, gateway 2226.7 MB, command-tree 911.8 MB |
| 2 | FAIL | gateway-performance/many-bundled-plugins |  | 2ms | 2136.7 MB | 2933 MB | n/a | n/a | gateway peak RSS 2136.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2347.4 MB, gateway 2136.7 MB, command-tree 673.5 MB |
| 3 | FAIL | gateway-performance/many-bundled-plugins |  | 36ms | 2107.6 MB | 2895.7 MB | n/a | n/a | gateway peak RSS 2107.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2312.6 MB, gateway 2107.6 MB, command-tree 669 MB |
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1760.9 MB | 7746ms | 8627ms | agent-process peak RSS 1492.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1688.7 MB, agent-process 1492.7 MB, status-cli 972.1 MB |
| 2 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1732.9 MB | 7922ms | 8410ms | agent-process peak RSS 1459.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1659.2 MB, agent-process 1459.5 MB, status-cli 877.6 MB |
| 3 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1836.3 MB | 7302ms | 7779ms | agent-process peak RSS 1569 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1764.5 MB, agent-process 1569 MB, status-cli 949.7 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- gateway-tree: RSS 2431.9 MB (scenario gateway-performance/many-bundled-plugins); CPU 291.8% (scenario gateway-performance/many-bundled-plugins)
- gateway: RSS 2226.7 MB (scenario gateway-performance/many-bundled-plugins); CPU 276.3% (scenario gateway-performance/many-bundled-plugins)
- command-tree: RSS 1764.5 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 254.8% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1569 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 239.7% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 972.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 191.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 277.8 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 200.8% (scenario agent-cold-warm-message/mock-openai-provider)
- uncategorized: RSS 607.1 MB (scenario gateway-performance/many-bundled-plugins); CPU 148.9% (scenario gateway-performance/many-bundled-plugins)
- model-cli: RSS 368.6 MB (scenario gateway-performance/many-bundled-plugins); CPU 141% (scenario gateway-performance/many-bundled-plugins)

## Selected Sample Details

### gateway-performance sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-005107f3-kova-261015-052436-6c06b0
Measurements:
- startup: listening 1ms; health 22ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 21ms; post-ready p95 3ms; failures 0; final failures 0; slowest startup-sample/cold-start 21ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2226.7 MB; tracked total 3122.4 MB; max CPU 276.3%; samples 43; roles gateway-tree 2431.9MB/284.3%, gateway 2226.7MB/276.3%, command-tree 911.8MB/168.8%, status-cli 911.8MB/168.8%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 2050.43ms; embedded traces 0; liveness warnings 0; open spans 3 (1 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2226.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2431.9 MB, gateway 2226.7 MB, command-tree 911.8 MB
  - gateway-tree peak RSS 2431.9 MB exceeded threshold 1440 MB
  - status-cli peak RSS 911.8 MB exceeded threshold 900 MB
  - 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 341ms

### gateway-performance sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-1e8be6a8-kova-261015-052436-6c06b0
Measurements:
- startup: listening 0ms; health 2ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 2ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 59ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2136.7 MB; tracked total 2933 MB; max CPU 272.8%; samples 41; roles gateway-tree 2347.4MB/291.8%, gateway 2136.7MB/272.8%, command-tree 673.5MB/157.8%, status-cli 673.5MB/157.8%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 1725.5ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2136.7 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2347.4 MB, gateway 2136.7 MB, command-tree 673.5 MB
  - gateway-tree peak RSS 2347.4 MB exceeded threshold 1440 MB

### gateway-performance sample 3

- Status: FAIL
- Cleanup: destroy-failed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-958fde53-kova-261015-052436-6c06b0
Measurements:
- startup: listening 0ms; health 36ms; readiness ready (gateway became healthy within the readiness threshold); gateway running; restarts 4
- health: startup p95 36ms; post-ready p95 3ms; failures 0; final failures 0; slowest final/final 39ms
- resources: scope product; contract primary-role-product-scope-v4; gateway RSS 2107.6 MB; tracked total 2895.7 MB; max CPU 275.9%; samples 40; roles gateway-tree 2312.6MB/285.9%, gateway 2107.6MB/275.9%, command-tree 669MB/152.5%, status-cli 669MB/152.5%
- agent: not-run
- Agent turn stats: count 0; p95 n/a; max n/a; pre-provider p95 n/a
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages 0; warm reuse true
- diagnostics: timeline available; slowest span post-ready.maintenance 1476.15ms; embedded traces 0; liveness warnings 0; open spans 3 (1 required); node CPU/heap/trace 0/0/0
- Violations:
  - gateway peak RSS 2107.6 MB exceeded threshold 1177 MB; observed role gateway; top RSS roles: gateway-tree 2312.6 MB, gateway 2107.6 MB, command-tree 669 MB
  - gateway-tree peak RSS 2312.6 MB exceeded threshold 1440 MB
  - 1 required OpenClaw diagnostics span(s) were left open; slowest gateway.ready age 256ms
- Failed command: `ocm env destroy 'kova-gateway-performance-man-958fde53-kova-261015-052436-6c06b0' --yes`
- Failure: ocm: environment process state changed during inspection; retry the command

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-8e2a29af-kova-261015-052436-6c06b0
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1492.7 MB; tracked total 1760.9 MB; max CPU 239.7%; samples 27; roles command-tree 1688.7MB/254.8%, agent-process 1492.7MB/239.7%, status-cli 972.1MB/184.3%, agent-cli 196MB/119.4%
- agent: turn 8627ms; cold/warm 7746ms/8627ms; cold-warm delta 0ms; pre-provider 8277ms; provider 47ms; metadata scans 11 (306.54ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8582.95ms; max 8627ms; pre-provider p95 8236.35ms
- agent CLI attribution: cold known 4454ms / unattributed 3010ms; warm known 5661ms / unattributed 2616ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1856.28ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1492.7 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1688.7 MB, agent-process 1492.7 MB, status-cli 972.1 MB
  - command-tree peak RSS 1688.7 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7746ms; pre-provider 7464ms; provider 2ms; post-provider 280ms; response true
    - active window: metadata scans 4 (123.23ms total, max 58.72ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7464ms; provider 2ms; post-provider 280ms; unknown 3458.34ms; source agent.prepare 3567.88ms; plugins.metadata.scan 437.78ms
  - warm: total 8627ms; pre-provider 8277ms; provider 47ms; post-provider 303ms; response true
    - active window: metadata scans 7 (183.31ms total, max 65.57ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 8277ms; provider 47ms; post-provider 303ms; unknown 4271.34ms; source agent.prepare 3567.88ms; plugins.metadata.scan 437.78ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7464 ms | 4454 ms | 3010 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-8e2a29af-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |
  | warm | 8277 ms | 5661 ms | 2616 ms | 47 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-8e2a29af-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2395 ms | 671 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2106 ms | 1026 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1613 ms | 707 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 122 ms | 58 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 8 ms | 4 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2970 ms | 1856 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2280 ms | 638 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1955 ms | 759 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 183 ms | 65 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 23 ms | 23 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 7 ms | 7 ms |

### agent-cold-warm-message sample 2

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-2ab680e0-kova-261015-052436-6c06b0
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1459.5 MB; tracked total 1732.9 MB; max CPU 229.1%; samples 27; roles command-tree 1659.2MB/243.1%, agent-process 1459.5MB/229.1%, status-cli 877.6MB/191.7%, agent-cli 232.1MB/149.7%
- agent: turn 8410ms; cold/warm 7922ms/8410ms; cold-warm delta 0ms; pre-provider 8062ms; provider 8ms; metadata scans 14 (347.69ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 8385.6ms; max 8410ms; pre-provider p95 8028.45ms
- agent CLI attribution: cold known 4372ms / unattributed 3019ms; warm known 5490ms / unattributed 2572ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1764.24ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1459.5 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1659.2 MB, agent-process 1459.5 MB, status-cli 877.6 MB
  - command-tree peak RSS 1659.2 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7922ms; pre-provider 7391ms; provider 2ms; post-provider 529ms; response true
    - active window: metadata scans 7 (168.44ms total, max 55.7ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7391ms; provider 2ms; post-provider 529ms; unknown 3240.37ms; source agent.prepare 3669.42ms; plugins.metadata.scan 481.21ms
  - warm: total 8410ms; pre-provider 8062ms; provider 8ms; post-provider 340ms; response true
    - active window: metadata scans 7 (179.25ms total, max 63.55ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 8062ms; provider 8ms; post-provider 340ms; unknown 3911.37ms; source agent.prepare 3669.42ms; plugins.metadata.scan 481.21ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7391 ms | 4372 ms | 3019 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-2ab680e0-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |
  | warm | 8062 ms | 5490 ms | 2572 ms | 8 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-2ab680e0-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2146 ms | 616 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2065 ms | 970 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1745 ms | 701 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 118 ms | 56 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | cold | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 6 ms | 6 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2803 ms | 1764 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2324 ms | 641 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1925 ms | 690 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 181 ms | 64 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 21 ms | 21 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 8 ms | 4 ms |

### agent-cold-warm-message sample 3

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-67b331a3-kova-261015-052436-6c06b0
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1569 MB; tracked total 1836.3 MB; max CPU 214.6%; samples 26; roles command-tree 1764.5MB/228.6%, agent-process 1569MB/214.6%, status-cli 949.7MB/188.1%, agent-cli 277.8MB/200.8%
- agent: turn 7779ms; cold/warm 7302ms/7779ms; cold-warm delta 0ms; pre-provider 7429ms; provider 115ms; metadata scans 11 (295.67ms); event-loop n/a; polls 0; cleanup n/a; diagnosis agent-latency-attributed; leaks 0
- Agent turn stats: count 2; p95 7755.15ms; max 7779ms; pre-provider p95 7409.2ms
- agent CLI attribution: cold known 4211ms / unattributed 2822ms; warm known 5103ms / unattributed 2326ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span agent.startup 1634.28ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1569 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1764.5 MB, agent-process 1569 MB, status-cli 949.7 MB
  - command-tree peak RSS 1764.5 MB exceeded threshold 1400 MB
- Agent turns:
  - cold: total 7302ms; pre-provider 7033ms; provider 2ms; post-provider 267ms; response true
    - active window: metadata scans 4 (114.1ms total, max 55.59ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7033ms; provider 2ms; post-provider 267ms; unknown 3144.56ms; source agent.prepare 3454.33ms; plugins.metadata.scan 434.11ms
  - warm: total 7779ms; pre-provider 7429ms; provider 115ms; post-provider 235ms; response true
    - active window: metadata scans 7 (181.57ms total, max 64.65ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 7429ms; provider 115ms; post-provider 235ms; unknown 3540.56ms; source agent.prepare 3454.33ms; plugins.metadata.scan 434.11ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 7033 ms | 4211 ms | 2822 ms | 2 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-67b331a3-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |
  | warm | 7429 ms | 5103 ms | 2326 ms | 115 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-67b331a3-kova-261015-052436-6c06b0/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x8 | 8 | 0 | 2127 ms | 628 ms |
  | cold | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2043 ms | 975 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1621 ms | 657 ms |
  | cold | `plugins.metadata.scan` | `startup`, `cli.command-startup` x3 | 4 | 0 | 115 ms | 56 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3 | 3 | 0 | 7 ms | 3 ms |
  | warm | `agent.startup` | `agent.startup` x9 | 9 | 0 | 2595 ms | 1634 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 2148 ms | 592 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1831 ms | 675 ms |
  | warm | `plugins.metadata.scan` | `startup` x4, `cli.command-startup` x3 | 7 | 0 | 180 ms | 65 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 22 ms | 22 ms |
  | warm | `cli.main.core-imports` | `cli.startup` | 1 | 0 | 6 ms | 6 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261015-052436-6c06b0-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261015-052436-6c06b0-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/mock-provider/kova-261015-052436-6c06b0-diagnostic.summary.json
- collector-root gateway-performance#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-005107f3-kova-261015-052436-6c06b0
- collector-root gateway-performance#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-1e8be6a8-kova-261015-052436-6c06b0
- collector-root gateway-performance#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-gateway-performance-man-958fde53-kova-261015-052436-6c06b0
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-8e2a29af-kova-261015-052436-6c06b0
- collector-root agent-cold-warm-message#2: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-2ab680e0-kova-261015-052436-6c06b0
- collector-root agent-cold-warm-message#3: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/mock-provider/artifacts/kova-261015-052436-6c06b0/kova-agent-cold-warm-message-67b331a3-kova-261015-052436-6c06b0

## Target Cleanup

- Runtime: `kova-local-mv93gp3b-3ta-413b2b64`
- Result: remove-failed
- Duration: 2ms

