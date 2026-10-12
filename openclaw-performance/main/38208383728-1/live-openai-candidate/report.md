# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — agent-process peak RSS 1458.6 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1559.9 MB, agent-process 1458.6 MB, status-cli 910.3 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | agent-process peak RSS 1458.6 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1559.9 MB, agent-process 1458.6 MB, status-cli 910.3 MB |
| Blocking findings | 5 |
| Warnings | 0 |
| Records | 1 (FAIL:1) |

## Proof Completeness

- Completeness: complete: 1
- Required obligations: 23 total, 0 missing, 0 failed
- Categories: command: 8, invariant: 12, artifact: 1, cleanup: 1, collector: 1

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261012-053422-2a132e` |
| Generated | 2026-10-12T05:37:00.899Z |
| Mode | execution |
| Target | `local-build:/home/runner/_work/openclaw/openclaw` |
| Platform | linux 6.6.141 (x64) · v24.19.0 |
| Repeat / parallel | 1 / 1 |
| Auth | live (openai) |
| Network frontage | port |

## Coverage

| Field | Value |
|---|---:|
| Records | 1 |
| Scenarios | 1 |
| States | 1 |
| FAIL | 1 |

## Findings

| Severity | Area | Scenario | Finding | Evidence |
|---|---|---|---|---|
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1458.6 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1559.9 MB, agent-process 1458.6 MB, status-cli 910.3 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1458.6 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1559.9 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1458.6 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold agent spent 10385ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1458.6 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold pre-provider latency was 10385ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1458.6 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (1309ms), but OpenClaw spent 10385ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1458.6 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 167.2% | 12063ms | 11681ms | 10385ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1559.9 MB | 12063ms | 11681ms | agent-process peak RSS 1458.6 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1559.9 MB, agent-process 1458.6 MB, status-cli 910.3 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 1559.9 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 177.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1458.6 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 167.2% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 910.3 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 177.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 102.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 118.5% (scenario agent-cold-warm-message/mock-openai-provider)

## Selected Sample Details

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261012-053422-2a132e/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053422-2a132e
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1458.6 MB; tracked total 1559.9 MB; max CPU 167.2%; samples 34; roles command-tree 1559.9MB/177.7%, agent-process 1458.6MB/167.2%, status-cli 910.3MB/177.7%, agent-cli 102.4MB/118.5%
- agent: turn 12063ms; cold/warm 12063ms/11681ms; cold-warm delta 382ms; pre-provider 10385ms; provider 1309ms; metadata scans 12 (357.41ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 12043.9ms; max 12063ms; pre-provider p95 10360.35ms
- agent CLI attribution: cold known 5496ms / unattributed 4889ms; warm known 5420ms / unattributed 4472ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span cli.command-startup 2041.13ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1458.6 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1559.9 MB, agent-process 1458.6 MB, status-cli 910.3 MB
  - command-tree peak RSS 1559.9 MB exceeded threshold 1400 MB
  - cold agent spent 10385ms before provider work, over threshold 10000ms
  - cold pre-provider latency was 10385ms, over threshold 10000ms
  - cold provider was fast (1309ms), but OpenClaw spent 10385ms before provider work.
- Agent turns:
  - cold: total 12063ms; pre-provider 10385ms; provider 1309ms; post-provider 369ms; response true
    - active window: metadata scans 6 (181.42ms total, max 76.38ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 10385ms; provider 1309ms; post-provider 369ms; unknown 6619.13ms; source agent.prepare 2970.99ms; plugins.metadata.scan 794.88ms
  - warm: total 11681ms; pre-provider 9892ms; provider 1419ms; post-provider 370ms; response true
    - active window: metadata scans 6 (175.99ms total, max 72.6ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 9892ms; provider 1419ms; post-provider 370ms; unknown 6126.13ms; source agent.prepare 2970.99ms; plugins.metadata.scan 794.88ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 10385 ms | 5496 ms | 4889 ms | 1309 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261012-053422-2a132e/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053422-2a132e/openclaw/timeline.jsonl |
  | warm | 9892 ms | 5420 ms | 4472 ms | 1419 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261012-053422-2a132e/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053422-2a132e/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x10 | 10 | 0 | 5797 ms | 2041 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 1939 ms | 1297 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1109 ms | 413 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 182 ms | 76 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 18 ms | 18 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 12 ms | 4 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 4337 ms | 1571 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2380 ms | 1519 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1863 ms | 796 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 175 ms | 72 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 9 ms | 3 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261012-053422-2a132e-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261012-053422-2a132e-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261012-053422-2a132e-diagnostic.summary.json
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261012-053422-2a132e/kova-agent-cold-warm-message-2c26dd1d-kova-261012-053422-2a132e

## Target Cleanup

- Runtime: `kova-local-mv4thpdj-3tr-669cb1d5`
- Result: removed
- Duration: 550ms

