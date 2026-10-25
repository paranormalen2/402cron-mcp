# 402cron MCP server

Remote MCP server for **402cron** (https://402cron.com). Paid cron for AI agents: you register an HTTPS URL and a schedule, we call it on time, signed, and bill one prepaid delivery per attempt. No account, no password, no card, no human in the loop — the only identity is the wallet that paid.

This repository holds the listing metadata for MCP catalogs. The server itself is hosted; there is nothing to
install or run locally.

## Connect

- Endpoint (Streamable HTTP): `https://402cron.com/mcp`
- No account, no API key.

Claude Code:

```bash
claude mcp add --transport http 402cron https://402cron.com/mcp
```

Any other client: add a remote (Streamable HTTP) server with the URL above.

## Tools

| Tool | What it does |
|---|---|
| `get_pricing` | What a delivery costs, which packs exist, and the exact x402 payment requirements for each. |
| `get_docs` | One section of the machine documentation: quickstart, headers, signature, notice, errors, billing or limits. |
| `get_service_status` | Whether the service is currently selling, on which network, and if not — why not. |
| `list_tasks` | Your tasks and their state. |
| `get_task` | A single task: schedule, destination, state, next run, and how many failures in a row it carries. |
| `create_task` | Register a schedule against a destination you have already verified. |
| `update_task` | Change the schedule, destination, method, timeout, headers or body of an existing task. |
| `pause_task` | Stop firing until you resume. |
| `resume_task` | Start firing again on the schedule. |
| `run_task_now` | Deliver immediately, outside the schedule. |
| `delete_task` | Move the task to the recycle bin. |
| `restore_task` | Bring a task back from the recycle bin within 30 days. |
| `register_destination` | Claim an https:// URL you control. |
| `verify_destination` | Prove you control a claimed URL: we send it one POST with the challenge, and it answers with the same value. |
| `list_destinations` | The URLs you have claimed and whether each is verified. |
| `delete_destination` | Remove a claimed URL. |

## Links

- Website: https://402cron.com
- For language models: https://402cron.com/llms.txt
- Official MCP Registry entry: `com.402cron/402cron`
