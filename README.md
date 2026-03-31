# Claude_Leaked_Code

## Overview

This repository is an archived copy of source files that were publicly exposed through an npm sourcemap incident involving Claude Code on March 31, 2026.

It is kept here for research, documentation, and software supply-chain security discussion purposes only.

## Purpose

This repository is intended to support:

- security analysis of accidental source exposure through sourcemaps
- research on software packaging and release engineering risks
- documentation of a real-world case of build artifact leakage
- educational discussion about secure publishing practices

## Important Notice

- This repository does **not** claim ownership of the original code.
- The original code belongs to its respective rights holder.
- This archive is provided strictly for **research, archival, and educational reference**.
- If you are the rights holder and would like this repository removed or modified, please open an issue or contact me.

## Background

The incident discussed here involves a published package that appears to have included a source map file containing original source content. Source maps can embed full source code inside the `sourcesContent` field, which may unintentionally expose internal implementation details if they are shipped in production artifacts.

This repository exists as a case study in:

- why production packages should be checked for `.map` files
- why release pipelines need explicit artifact filtering
- how debugging metadata can unintentionally leak sensitive internals

## Repository Contents

This repository contains archived source files and directory structure associated with the exposed package contents.

Examples of included modules/directories:

- `assistant/`
- `bridge/`
- `buddy/`
- `coordinator/`
- `services/`
- `tools/`
- `upstreamproxy/`
- `utils/`

## Why This Matters

This case is useful because it highlights a broader engineering issue rather than a single product-specific mistake:

1. sourcemaps may contain far more than stack-trace metadata
2. package publishing pipelines often leak files unintentionally
3. secure release engineering requires artifact review before publish
4. AI tooling products are also subject to ordinary software supply-chain risks

## Ethical Use

Please do **not** use this repository for harassment, abuse, unauthorized redistribution, or harmful exploitation.

Recommended use cases:

- academic/security discussion
- reproducible documentation of the incident
- defensive analysis of packaging mistakes
- learning how to prevent similar leaks in your own projects

## Takedown / Rights Holder Requests

If you are the copyright owner or an authorized representative and believe this content should not remain available, please contact me and I will handle the request promptly.

## Disclaimer

All trademarks, product names, and source code rights belong to their respective owners.
This repository is provided without warranty of any kind.

## Related Topic

This repository may also be useful for discussions around:

- npm package hygiene
- sourcemap handling in production builds
- build system defaults
- secure software release workflows

## Current Status

This repository is maintained as an archive/reference snapshot.
