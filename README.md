# SandBase for Codex

[![SandBase CLI](https://img.shields.io/badge/powered%20by-sandbaseai%2Fcli-20B884)](https://github.com/sandbaseai/cli)
[![License](https://img.shields.io/badge/license-Apache--2.0-blue)](./LICENSE)

The official Codex plugin for [SandBase CLI](https://github.com/sandbaseai/cli). It gives Codex a local MCP server and Agent Skill for discovering, inspecting, and running 2,000+ AI models and APIs through one account.

## What it adds

- Six MCP tools: discover, inspect, run, poll, history, and account balance.
- One guided Agent Skill that enforces discover → inspect → run.
- An immutable v0.1.17 launcher with a published SHA-256 checksum.
- Browser-based SandBase authentication; no provider API keys are stored in this repository.

## First-time authentication

```sh
npx -y https://github.com/sandbaseai/cli/releases/download/v0.1.17/sandbaseai-cli-0.1.17.tgz connect --client codex
```

Complete browser sign-in once and restart Codex. To inspect or remove only SandBase-managed state, replace `connect` with `doctor` or `unregister`.

## Security

The MCP launcher uses the immutable GitHub release asset for v0.1.17. Its SHA-256 is:

```text
1ad535b2899ca460b57b3c268aef278fee28fd28e649a89b92951514fd71fffa
```

See [SECURITY.md](./SECURITY.md) before reporting vulnerabilities or credential issues.

## Source

The CLI, MCP implementation, tests, releases, and full documentation live in [sandbaseai/cli](https://github.com/sandbaseai/cli). This repository contains only the Codex plugin packaging needed by plugin marketplaces.
