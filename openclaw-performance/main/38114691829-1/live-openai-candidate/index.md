# OpenClaw Performance Report

- Lane: live-openai-candidate
- Run: kova-261011-052630-b2f590
- Generated: 2026-10-11T05:29:07.706Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 1
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,303 MB | 1,303 MB | 1,303 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 169 % | 169 % | 169 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 13,145 ms | 13,145 ms | 13,145 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 13,154 ms | 13,154 ms | 13,154 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 12,968 ms | 12,968 ms | 12,968 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 11,100 ms | 11,100 ms | 11,100 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,303 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,405 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 11,113 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,848 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 11,113 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,848 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
- Workflow ref: main
- Workflow SHA: 9a62c5b5cd2eb98a47e7091dfa1484cfe8dd7809
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: live
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11692458680](https://github.com/openclaw/openclaw/actions/runs/38114691829/artifacts/11692458680); its checksum is published under the bundles directory.
