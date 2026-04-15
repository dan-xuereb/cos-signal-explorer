# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Status

This repository is a fresh scaffold — only `README.md` exists. No source code, build configuration, tests, or deployment artifacts have been added yet. When that changes, update this file with concrete commands and architectural notes instead of leaving the placeholders below.

## Workspace Context

`cos-signal-explorer` lives under `/home/btc/github/` alongside the rest of the Xuer Capital quant stack. The workspace-level `/home/btc/github/CLAUDE.md` documents the full project map, tech stack, and conventions that apply here — read it before adding code so this repo aligns with sibling repos (`COS-SDL`, `COS-SGL`, `COS-CIE`, `COS-BTE`, `cos-signal-bridge`, etc.).

Relevant sibling repos if this becomes a signal-exploration UI/tool:
- `COS-SDL` — factor algebra IR and `FactorRecord` registry
- `COS-SGL` — `SignalFrame` computation
- `COS-CIE` — composite indicator scoring
- `cos-signal-bridge` — SDL↔SGL↔BTE glue (registry, evaluator, feedback)

## Conventions Inherited from the Workspace

- Python 3.11+, `ruff` + `black` + `mypy`, `pytest`; TypeScript 5 + React 18 + Vite for any frontend.
- Pydantic v2 for all data validation; reuse `COS-Core` schemas rather than redefining them.
- One K8s namespace per service; Talos cluster at `10.70.0.102`; private registry at `10.70.0.30:5000`.
- GSD workflow is enforced at the workspace level — route non-trivial edits through `/gsd-quick`, `/gsd-debug`, or `/gsd-execute-phase` rather than editing directly.

## TODO for the Next Contributor

Once the repo gains real code, replace this file's Status section with:
1. Build / lint / test / run commands (including how to run a single test).
2. The big-picture architecture — what this explorer explores, which services it talks to, and where it sits in the SDL→CIE→SGL→BTE pipeline.
