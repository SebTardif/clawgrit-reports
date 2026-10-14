# OpenClaw Performance Report

- Lane: live-openai-candidate
- Run: kova-261014-052433-c1163a
- Generated: 2026-10-14T05:27:20.410Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 1
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,354 MB | 1,354 MB | 1,354 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 168 % | 168 % | 168 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 12,035 ms | 12,035 ms | 12,035 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 12,042 ms | 12,042 ms | 12,042 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 11,900 ms | 11,900 ms | 11,900 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 10,383 ms | 10,383 ms | 10,383 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,354 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,556 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,402 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,025 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,402 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | 10,025 | <= 10000 |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | pre-provider-stall | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 30fb4feba23f4afe6e29065dc69a9b756f821e87
- Workflow ref: main
- Workflow SHA: 30fb4feba23f4afe6e29065dc69a9b756f821e87
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: live
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11871667744](https://github.com/openclaw/openclaw/actions/runs/38516324551/artifacts/11871667744); its checksum is published under the bundles directory.
