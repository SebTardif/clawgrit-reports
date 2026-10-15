# OpenClaw Performance Report

- Lane: mock-provider
- Run: kova-261015-052436-6c06b0
- Generated: 2026-10-15T05:47:35.738Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 6
- Repeat: 3

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 2,137 MB | 2,218 MB | 2,227 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 2,137 MB | 2,218 MB | 2,227 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 276 % | 276 % | 276 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 50.5 ms | 52.5 ms | 52.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,493 MB | 1,561 MB | 1,569 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 229 % | 239 % | 240 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 8,386 ms | 8,563 ms | 8,583 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 7,746 ms | 7,904 ms | 7,922 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 8,410 ms | 8,605 ms | 8,627 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 8,028 ms | 8,216 ms | 8,236 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,227 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,432 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 912 | <= 900 |
| gateway-performance | many-bundled-plugins | openclawOpenRequiredSpanCount | 1 | 0 |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,137 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,347 | <= 1440 |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,108 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,313 | <= 1440 |
| gateway-performance | many-bundled-plugins | openclawOpenRequiredSpanCount | 1 | 0 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,493 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,689 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,460 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,659 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,569 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,765 | <= 1400 |

## Records

| Scenario | State | Status | Failure |
| --- | --- | --- | --- |
| gateway-performance | many-bundled-plugins | FAIL |  |
| gateway-performance | many-bundled-plugins | FAIL |  |
| gateway-performance | many-bundled-plugins | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |
| agent-cold-warm-message | mock-openai-provider | FAIL |  |

## Test scope

- Repository: openclaw/openclaw
- Tested ref: main
- Tested SHA: 54691736d026cba16ee8623bb3729f8c2c4c5af7
- Workflow ref: main
- Workflow SHA: 54691736d026cba16ee8623bb3729f8c2c4c5af7
- Kova repository: openclaw/Kova
- Kova ref: 88d9a7efa5e6569f902bf8d298fd6a21c6be2e7b
- Kova profile: diagnostic
- Kova scenario timeout: 300000ms
- Lane auth: mock
- Lane model: gpt-5.6-luna
- Lane repeat: 3
- Include filters: scenario:fresh-install,scenario:gateway-performance,scenario:bundled-plugin-startup,scenario:agent-cold-warm-message

## Source probes

Additional gateway boot, memory, plugin pressure, mock hello-loop, CLI startup, and SQLite state smoke numbers are in [source/index.md](source/index.md).

## Full diagnostic artifact

The complete Kova bundle remains in [Actions artifact 11950229898](https://github.com/openclaw/openclaw/actions/runs/38686484695/artifacts/11950229898); its checksum is published under the bundles directory.
