# OpenClaw Performance Report

- Lane: mock-provider
- Run: kova-261013-053147-79131b
- Generated: 2026-10-13T05:53:29.339Z
- Target: local-build:/home/runner/_work/openclaw/openclaw
- Statuses: FAIL: 6
- Repeat: 3

## Key metrics

| Scenario | State | Metric | Median | p95 | Max |
| --- | --- | --- | ---: | ---: | ---: |
| gateway-performance | many-bundled-plugins | Primary RSS | 2,082 MB | 2,092 MB | 2,094 MB |
| gateway-performance | many-bundled-plugins | Gateway RSS | 2,082 MB | 2,092 MB | 2,094 MB |
| gateway-performance | many-bundled-plugins | Max CPU | 270 % | 290 % | 292 % |
| gateway-performance | many-bundled-plugins | Event Loop Max | 38 ms | 39.5 ms | 39.7 ms |
| agent-cold-warm-message | mock-openai-provider | Primary RSS | 1,449 MB | 1,499 MB | 1,505 MB |
| agent-cold-warm-message | mock-openai-provider | Gateway RSS | 0 MB | 0 MB | 0 MB |
| agent-cold-warm-message | mock-openai-provider | Max CPU | 193 % | 199 % | 200 % |
| agent-cold-warm-message | mock-openai-provider | Agent Turn p95 | 8,218 ms | 9,934 ms | 10,125 ms |
| agent-cold-warm-message | mock-openai-provider | Cold Agent Turn | 7,629 ms | 7,809 ms | 7,829 ms |
| agent-cold-warm-message | mock-openai-provider | Warm Agent Turn | 8,238 ms | 10,057 ms | 10,259 ms |
| agent-cold-warm-message | mock-openai-provider | Pre-Provider p95 | 7,948 ms | 9,384 ms | 9,543 ms |

## Threshold violations

| Scenario | State | Metric | Actual | Threshold |
| --- | --- | --- | ---: | ---: |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,094 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,410 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 979 | <= 900 |
| gateway-performance | many-bundled-plugins | peakRssMb | 2,082 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,399 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 926 | <= 900 |
| gateway-performance | many-bundled-plugins | peakRssMb | 1,992 | <= 1177 |
| gateway-performance | many-bundled-plugins | resourceByRole.gateway-tree.peakRssMb | 2,308 | <= 1440 |
| gateway-performance | many-bundled-plugins | resourceByRole.status-cli.peakRssMb | 1,102 | <= 900 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,449 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,550 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,505 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,607 | <= 1400 |
| agent-cold-warm-message | mock-openai-provider | peakRssMb | 1,440 | <= 1150 |
| agent-cold-warm-message | mock-openai-provider | resourceByRole.command-tree.peakRssMb | 1,541 | <= 1400 |

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
- Tested SHA: 869ceef2c25f9c966bfb574b6f5206d1fc685039
- Workflow ref: main
- Workflow SHA: 869ceef2c25f9c966bfb574b6f5206d1fc685039
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

The complete Kova bundle remains in [Actions artifact 11791743429](https://github.com/openclaw/openclaw/actions/runs/38351683485/artifacts/11791743429); its checksum is published under the bundles directory.
