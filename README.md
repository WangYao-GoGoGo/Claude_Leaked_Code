<div align="center">

# Claude Code — Leaked Source

**The full source code of Anthropic's Claude Code CLI, leaked on March 31, 2026**

[![TypeScript](https://img.shields.io/badge/TypeScript-512K%2B_lines-3178C6?logo=typescript&logoColor=white)](#tech-stack)
[![Bun](https://img.shields.io/badge/Runtime-Bun-f472b6?logo=bun&logoColor=white)](#tech-stack)
[![React + Ink](https://img.shields.io/badge/UI-React_%2B_Ink-61DAFB?logo=react&logoColor=black)](#tech-stack)
[![Files](https://img.shields.io/badge/~1,900_files-source_only-grey)](#directory-structure)
[![MCP Server](https://img.shields.io/badge/MCP-Explorer_Server-blueviolet)](#-explore-with-mcp-server)
[![npm](https://img.shields.io/npm/v/claude-code-explorer-mcp?label=npm&color=cb3837&logo=npm)](https://www.npmjs.com/package/claude-code-explorer-mcp)

> The original unmodified leaked source is preserved in the [`backup` branch](https://github.com/WangYao-GoGoGo/Leaked-Claude-Code/tree/backup).

</div>

---

## Table of Contents

- [How It Leaked](#how-it-leaked)
- [What Is Claude Code?](#what-is-claude-code)
- [Documentation](#-documentation)
- [Explore with MCP Server](#-explore-with-mcp-server)
- [Directory Structure](#directory-structure)
- [Architecture](#architecture)
  - [Tool System](#1-tool-system)
  - [Command System](#2-command-system)
  - [Service Layer](#3-service-layer)
  - [Bridge System](#4-bridge-system)
  - [Permission System](#5-permission-system)
  - [Feature Flags](#6-feature-flags)
- [Key Files](#key-files)
- [Tech Stack](#tech-stack)
- [Design Patterns](#design-patterns)
- [GitPretty Setup](#gitpretty-setup)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## How It Leaked

[Chaofan Shou (@Fried_rice)](https://x.com/Fried_rice) discovered that the published npm package for Claude Code included a `.map` file referencing the full, unobfuscated TypeScript source — downloadable as a zip from Anthropic's R2 storage bucket.

> **"Claude code source code has been leaked via a map file in their npm registry!"**
>
> — [@Fried_rice, March 31, 2026](https://x.com/Fried_rice/status/2038894956459290963)

---

## What Is Claude Code?

Claude Code is Anthropic's official CLI tool for interacting with Claude directly from the terminal — editing files, running commands, searching codebases, managing git workflows, and more. This repository contains the leaked `src/` directory.

| | |
|---|---|
| **Leaked** | 2026-03-31 |
| **Language** | TypeScript (strict) |
| **Runtime** | [Bun](https://bun.sh) |
| **Terminal UI** | [React](https://react.dev) + [Ink](https://github.com/vadimdemedes/ink) |
| **Scale** | ~1,900 files · 512,000+ lines of code |

---

## � Documentation

For in-depth guides, see the [`docs/`](docs/) directory:

| Guide | Description |
|-------|-------------|
| **[Architecture](docs/architecture.md)** | Core pipeline, startup sequence, state management, rendering, data flow |
| **[Tools Reference](docs/tools.md)** | Complete catalog of all ~40 agent tools with categories and permission model |
| **[Commands Reference](docs/commands.md)** | All ~85 slash commands organized by category |
| **[Subsystems Guide](docs/subsystems.md)** | Deep dives into Bridge, MCP, Permissions, Plugins, Skills, Tasks, Memory, Voice |
| **[Exploration Guide](docs/exploration-guide.md)** | How to navigate the codebase — study paths, grep patterns, key files |

Also see: [CONTRIBUTING.md](CONTRIBUTING.md) · [MCP Server README](mcp-server/README.md)

---

## �🔍 Explore with MCP Server

This repo ships an [MCP server](https://modelcontextprotocol.io/) that lets any MCP-compatible client (Claude Code, Claude Desktop, VS Code Copilot, Cursor) explore the full source interactively.

### Install from npm

The MCP server is published as [`claude-code-explorer-mcp`](https://www.npmjs.com/package/claude-code-explorer-mcp) on npm — no need to clone the repo:

```bash
# Claude Code
claude mcp add claude-code-explorer -- npx -y claude-code-explorer-mcp