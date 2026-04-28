# Tests

Integration tests for ida-mcp using a minimal `mini.c` fixture.

## Prerequisites

- `curl` (for HTTP tests)
- `jq` (for elicitation, DSC, and crash-guard tests)

## Build the fixture

```bash
just fixture
```

Compiles `fixtures/mini.c` to `fixtures/mini`. IDA analyzes raw binaries directly on first open.

## Run tests

```bash
just test       # Stdio JSONL test
just test-http  # HTTP/SSE test
just test-bootstrap # Generate fixtures/mini.i64 once via the MCP server
just test-script # IDAPython script test
just test-observability # Foreground progress/recent_operations test
just test-elicitation # open_idb auto-background elicitation test
```

## Clean

```bash
just clean
```
