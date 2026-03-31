<div align="center">

# Claude Code — Leaked Source

**Archived source tree exposed through a sourcemap-related npm publishing incident on March 31, 2026**

[![TypeScript](https://img.shields.io/badge/TypeScript-512K%2B_lines-3178C6?logo=typescript&logoColor=white)](#tech-stack)
[![Bun](https://img.shields.io/badge/Runtime-Bun-f472b6?logo=bun&logoColor=white)](#tech-stack)
[![React + Ink](https://img.shields.io/badge/UI-React_%2B_Ink-61DAFB?logo=react&logoColor=black)](#tech-stack)
[![Files](https://img.shields.io/badge/~1,900_files-source_only-grey)](#directory-structure)
[![MCP Server](https://img.shields.io/badge/MCP-Explorer_Server-blueviolet)](#-explore-with-mcp-server)
[![npm](https://img.shields.io/npm/v/claude-code-explorer-mcp?label=npm&color=cb3837&logo=npm)](https://www.npmjs.com/package/claude-code-explorer-mcp)

> The original unmodified leaked source is preserved in the [`backup` branch](https://github.com/nirholas/claude-code/tree/backup).

</div>

---

## Table of Contents

- [How It Leaked](#how-it-leaked)
- [What Is Claude Code?](#what-is-claude-code)
- [Why This Repository Exists](#why-this-repository-exists)
- [Documentation](#documentation)
- [Explore with MCP Server](#explore-with-mcp-server)
- [Directory Structure](#directory-structure)
- [Architecture](#architecture)
  - [1. Tool System](#1-tool-system)
  - [2. Command System](#2-command-system)
  - [3. Service Layer](#3-service-layer)
  - [4. Bridge System](#4-bridge-system)
  - [5. Permission System](#5-permission-system)
  - [6. Feature Flags](#6-feature-flags)
- [Key Files](#key-files)
- [Tech Stack](#tech-stack)
- [Design Patterns](#design-patterns)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## How It Leaked

Claude Code's published npm package was found to include a `.map` file that referenced the original TypeScript source.

In JavaScript/TypeScript build pipelines, source maps are generated to map bundled code back to the original source for debugging. A source map may contain a `sourcesContent` field, which can embed the full original contents of source files directly inside the `.map` artifact.

A simplified structure looks like this:

```json
{
  "version": 3,
  "sources": ["../src/main.tsx", "../src/tools/BashTool.ts"],
  "sourcesContent": ["// original source code...", "..."],
  "mappings": "AAAA,..."
}