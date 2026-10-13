# OpenClaw Performance Report

- Lane: live-openai-candidate
- Run: kova-261013-053125-3c64f0
- Generated: 2026-10-13T05:34:17.099Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 1
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,609 MB | 1,609 MB | 1,609 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 178 % | 178 % | 178 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 12,988 ms | 12,988 ms | 12,988 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 13,016 ms | 13,016 ms | 13,016 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 12,463 ms | 12,463 ms | 12,463 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 11,270 ms | 11,270 ms | 11,270 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,609 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,710 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 11,309 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,535 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 11,309 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,535 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 869ceef2c25f9c966bfb574b6f5206d1fc685039
- Workflow ref: main
- Workflow SHA: 869ceef2c25f9c966bfb574b6f5206d1fc685039
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: live
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11791645522](https://github.com/openclaw/openclaw/actions/runs/38351683485/artifacts/11791645522); its checksum is published under the bundles directory.
