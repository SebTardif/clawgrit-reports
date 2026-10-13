# OpenClaw Performance Report

- Lane: mock-deep-profile
- Run: kova-261013-053149-bf8740
- Generated: 2026-10-13T05:41:08.311Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 2
- Repeat: 1

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 2,077 MB | 2,077 MB | 2,077 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 2,077 MB | 2,077 MB | 2,077 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 282 % | 282 % | 282 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 41.7 ms | 41.7 ms | 41.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,808 MB | 1,808 MB | 1,808 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 291 % | 291 % | 291 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 27,502 ms | 27,502 ms | 27,502 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 27,502 ms | 27,502 ms | 27,502 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,077 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,394 | <= 1440 |
| agent-cold-warm-message | mock-openai-provider | agentResponseOk | 0 | true |
| agent-cold-warm-message | mock-openai-provider | agentTurn.responseOk | none | usable assistant response |
| agent-cold-warm-message | mock-openai-provider | agentTurn.expectedTextPresent | none | KOVA_AGENT_OK |
| agent-cold-warm-message | mock-openai-provider | agentProviderRequestMissing | none | provider request during agent command |
| agent-cold-warm-message | mock-openai-provider | preProviderMs | null | finite non-negative turn measurement |
| agent-cold-warm-message | mock-openai-provider | agentLatencyDiagnosis | no-provider-request | no cold pre-provider stall |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
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
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 1
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:agent-cold-warm-message

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11791870901](https://github.com/openclaw/openclaw/actions/runs/38351683485/artifacts/11791870901); its checksum is published under the bundles directory.
