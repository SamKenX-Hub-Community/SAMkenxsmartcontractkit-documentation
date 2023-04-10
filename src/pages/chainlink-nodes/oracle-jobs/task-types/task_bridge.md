---
layout: ../../../../layouts/MainLayout.astro
section: nodeOperator
date: Last Modified
title: "Bridge Task"
permalink: "docs/jobs/task-types/bridge/"
---

Bridge tasks make HTTP POST requests to pre-configured URLs. Bridges can be configured via the UI or the CLI, and are referred to by a simple user-specified name. This is the way that most jobs interact with [External Adapters](/chainlink-nodes/external-adapters/external-adapters/).

**Parameters**

- `name`: an arbitrary name given to the bridge by the node operator.
- `requestData` (optional): a statically-defined payload to be sent to the external adapter.
- `cacheTTL` (optional): a duration-formatted string indicating the maximum acceptable staleness for cached bridge responses in case of intermittent failures. This is disabled by default.
- `headers` (optional): an array of strings. The number of strings must be even. Example: `foo [type="bridge" name="foo" headers="[\\"X-Header-1\\", \\"value1\\", \\"X-Header-2\\", \\"value2\\"]"]`

**Outputs**

A string containing the response body.

**Example**

```toml
my_bridge_task [type="bridge"
                name="some_bridge"
                requestData="{\\"data\\":{\\"foo\\": $(foo), \\"bar\\": $(bar)}}"
                ]
```
