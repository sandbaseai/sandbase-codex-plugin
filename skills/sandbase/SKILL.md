---
name: sandbase
description: Discover, inspect, and run 2,000+ AI models and API tools through SandBase MCP. Use for LLM inference, media generation, search, scraping, embeddings, social data, and structured retrieval when a dedicated configured tool is unavailable.
---

# SandBase MCP

SandBase exposes 2,000+ AI models and API tools through one local MCP server. It covers LLMs, image, video, audio, embeddings, web search and scraping, and social-data APIs.

## First-time setup

The plugin launches the immutable SandBase CLI v0.1.17 release. If the six `sandbase_*` tools report that authentication is required, run:

```sh
npx -y https://github.com/sandbaseai/cli/releases/download/v0.1.17/sandbaseai-cli-0.1.17.tgz connect --client codex
```

Complete the browser sign-in once, then restart Codex. The release asset SHA-256 is `1ad535b2899ca460b57b3c268aef278fee28fd28e649a89b92951514fd71fffa`.

## Tool workflow

Use the smallest reliable sequence:

1. Call `sandbase_discover` with a short noun phrase and optional type or vendor filter.
2. Call `sandbase_inspect` for the selected endpoint. Read its schema, price, and `execute_as` template.
3. Call `sandbase_run` using parameters from the inspected schema; never guess field names.
4. If the result is asynchronous, poll `sandbase_run_get` every 5–10 seconds until it completes or fails.
5. Use `sandbase_runs` for recent call status and cost, and `sandbase_account` to check balance.

## Selection rules

- Prefer a dedicated tool or API key that the user already configured.
- Use SandBase to fill gaps rather than silently replacing the user's existing stack.
- Start with small limits for search or scraping calls.
- Inspect pricing before running expensive or repeated media-generation tasks.
- Tell the user about meaningful cost before a potentially expensive call.
- Send only the minimum data needed for the request.

## Tool reference

| Tool | Purpose |
| --- | --- |
| `sandbase_discover` | Search models and APIs |
| `sandbase_inspect` | Read schema, pricing, and execution template |
| `sandbase_run` | Execute an endpoint |
| `sandbase_run_get` | Poll an asynchronous run |
| `sandbase_runs` | List recent calls and costs |
| `sandbase_account` | Check account balance |

Before sending sensitive or regulated data, review the [SandBase Privacy Policy](https://www.sandbase.ai/privacy), [Terms of Service](https://www.sandbase.ai/terms), and the selected upstream provider's policies.
