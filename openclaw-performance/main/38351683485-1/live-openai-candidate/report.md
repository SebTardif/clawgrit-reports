# Kova OpenClaw Runtime Report

> **❌ [FAIL]** — agent-process peak RSS 1609.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1709.9 MB, agent-process 1609.1 MB, status-cli 1219.3 MB

## Verdict

| Field | Value |
|---|---|
| Verdict | FAIL |
| Reason | agent-process peak RSS 1609.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1709.9 MB, agent-process 1609.1 MB, status-cli 1219.3 MB |
| Blocking findings | 7 |
| Warnings | 0 |
| Records | 1 (FAIL:1) |

## Proof Completeness

- Completeness: complete: 1
- Required obligations: 23 total, 0 missing, 0 failed
- Categories: command: 8, invariant: 12, artifact: 1, cleanup: 1, collector: 1

## Run

| Field | Value |
|---|---|
| Run ID | `kova-261013-053125-3c64f0` |
| Generated | 2026-10-13T05:34:17.100Z |
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
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | agent-process peak RSS 1609.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1709.9 MB, agent-process 1609.1 MB, status-cli 1219.3 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | command-tree peak RSS 1709.9 MB exceeded threshold 1400 MB | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold agent spent 11309ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm agent spent 10535ms before provider work, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold pre-provider latency was 11309ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | warm pre-provider latency was 10535ms, over threshold 10000ms | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |
| fail | OpenClaw | agent-cold-warm-message/mock-openai-provider | cold provider was fast (1345ms), but OpenClaw spent 11309ms before provider work. | resourceScope: product; resourceContract: primary-role-product-scope-v4; agent-processRssMb: 1609.1 |

## Performance Summary

- Resource measurement scope: product
- Resource headline contract: `primary-role-product-scope-v4`

| Scenario | Samples | Status | Health Ready | Gateway RSS | Tracked RSS | CPU | Cold Turn | Warm Turn | Cold Pre-Provider |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| agent-cold-warm-message/mock-openai-provider | 1 | FAIL:1 | n/a | 0MB | n/a | 177.7% | 13016ms | 12463ms | 11309ms |

## Samples

| Sample | Status | Scenario | Upgrade From | Health Ready | Gateway RSS | Tracked RSS | Cold Turn | Warm Turn | Blocker |
|---:|---|---|---|---:|---:|---:|---:|---:|---|
| 1 | FAIL | agent-cold-warm-message/mock-openai-provider |  | unknown | 0 MB | 1709.9 MB | 13016ms | 12463ms | agent-process peak RSS 1609.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1709.9 MB, agent-process 1609.1 MB, status-cli 1219.3 MB |

## Resource Roles

- Measurement scope: product
- Headline contract: `primary-role-product-scope-v4`
- command-tree: RSS 1709.9 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 188.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-process: RSS 1609.1 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 177.7% (scenario agent-cold-warm-message/mock-openai-provider)
- status-cli: RSS 1219.3 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 188.7% (scenario agent-cold-warm-message/mock-openai-provider)
- agent-cli: RSS 201.4 MB (scenario agent-cold-warm-message/mock-openai-provider); CPU 107.4% (scenario agent-cold-warm-message/mock-openai-provider)

## Selected Sample Details

### agent-cold-warm-message sample 1

- Status: FAIL
- Cleanup: destroyed
- Artifact root: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261013-053125-3c64f0/kova-agent-cold-warm-message-2c26dd1d-kova-261013-053125-3c64f0
Measurements:
- startup: listening unknown; health unknown; readiness unknown; gateway disabled; restarts 0
- health: startup p95 not-collected; post-ready p95 not-collected; failures at least 0; final failures not-collected
- resources: scope product; contract primary-role-product-scope-v4; agent-process RSS 1609.1 MB; tracked total 1709.9 MB; max CPU 177.7%; samples 36; roles command-tree 1709.9MB/188.7%, agent-process 1609.1MB/177.7%, status-cli 1219.3MB/188.7%, agent-cli 201.4MB/107.4%
- agent: turn 13016ms; cold/warm 13016ms/12463ms; cold-warm delta 553ms; pre-provider 11309ms; provider 1345ms; metadata scans 12 (378.7ms); event-loop n/a; polls 0; cleanup n/a; diagnosis pre-provider-stall; leaks 0
- Agent turn stats: count 2; p95 12988.35ms; max 13016ms; pre-provider p95 11270.3ms
- agent CLI attribution: cold known 6192ms / unattributed 5117ms; warm known 5590ms / unattributed 4945ms
- plugins/runtime: missing deps 0; plugin failures 0; runtime deps not-observed; warm restages n/a; warm reuse n/a
- diagnostics: timeline available; slowest span cli.command-startup 2039.6ms; embedded traces 0; liveness warnings 0; open spans 0 (0 required); node CPU/heap/trace 0/0/0
- Violations:
  - agent-process peak RSS 1609.1 MB exceeded threshold 1150 MB; observed role agent-process; top RSS roles: command-tree 1709.9 MB, agent-process 1609.1 MB, status-cli 1219.3 MB
  - command-tree peak RSS 1709.9 MB exceeded threshold 1400 MB
  - cold agent spent 11309ms before provider work, over threshold 10000ms
  - warm agent spent 10535ms before provider work, over threshold 10000ms
  - cold pre-provider latency was 11309ms, over threshold 10000ms
  - warm pre-provider latency was 10535ms, over threshold 10000ms
  - cold provider was fast (1345ms), but OpenClaw spent 11309ms before provider work.
- Agent turns:
  - cold: total 13016ms; pre-provider 11309ms; provider 1345ms; post-provider 362ms; response true
    - active window: metadata scans 6 (193.02ms total, max 78.12ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 11309ms; provider 1345ms; post-provider 362ms; unknown 7657.21ms; source agent.prepare 2806.63ms; plugins.metadata.scan 845.16ms
  - warm: total 12463ms; pre-provider 10535ms; provider 1543ms; post-provider 385ms; response true
    - active window: metadata scans 6 (185.68ms total, max 76.98ms); event-loop samples 0 max unknown
    - breakdown: pre-provider 10535ms; provider 1543ms; post-provider 385ms; unknown 6883.21ms; source agent.prepare 2806.63ms; plugins.metadata.scan 845.16ms
- Agent CLI pre-provider attribution:
  - Spans are clipped to the active turn timestamp window; collector-specific name and phase rules select attributed work.

  | turn | pre-provider | known | unattributed | provider | timeline |
  |---|---:|---:|---:|---:|---|
  | cold | 11309 ms | 6192 ms | 5117 ms | 1345 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261013-053125-3c64f0/kova-agent-cold-warm-message-2c26dd1d-kova-261013-053125-3c64f0/openclaw/timeline.jsonl |
  | warm | 10535 ms | 5590 ms | 4945 ms | 1543 ms | /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261013-053125-3c64f0/kova-agent-cold-warm-message-2c26dd1d-kova-261013-053125-3c64f0/openclaw/timeline.jsonl |

  | turn | span | phase(s) | count | errors | clipped | max |
  |---|---|---|---:|---:|---:|---:|
  | cold | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 5717 ms | 2040 ms |
  | cold | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2831 ms | 1574 ms |
  | cold | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1116 ms | 404 ms |
  | cold | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 194 ms | 78 ms |
  | cold | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | cold | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 10 ms | 3 ms |
  | warm | `cli.command-startup` | `cli.command-startup` x9 | 9 | 0 | 4197 ms | 1588 ms |
  | warm | `agent.startup` | `agent.startup` x8 | 8 | 0 | 2702 ms | 1499 ms |
  | warm | `agent.prepare` | `agent.prepare` x13 | 13 | 0 | 1689 ms | 702 ms |
  | warm | `plugins.metadata.scan` | `cli.command-startup` x3, `startup`, `agent.startup` x2 | 6 | 0 | 187 ms | 77 ms |
  | warm | `entry.run-main-import` | `cli.startup` | 1 | 0 | 17 ms | 17 ms |
  | warm | `plugins.metadata.freeze` | `cli.command-startup` x3, `agent.startup` x2 | 5 | 0 | 12 ms | 4 ms |

## Artifacts

- markdown-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261013-053125-3c64f0-diagnostic.md
- json-report: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261013-053125-3c64f0-diagnostic.json
- summary-json: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/reports/live-openai-candidate/kova-261013-053125-3c64f0-diagnostic.summary.json
- collector-root agent-cold-warm-message#1: /home/runner/\_work/openclaw/openclaw/.artifacts/kova/home/live-openai-candidate/artifacts/kova-261013-053125-3c64f0/kova-agent-cold-warm-message-2c26dd1d-kova-261013-053125-3c64f0

## Target Cleanup

- Runtime: `kova-local-mv68trtd-3sx-acc5986b`
- Result: removed
- Duration: 579ms

