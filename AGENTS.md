# AGENTS.md

## Project

Vanilla JS/HTML/CSS Pac-Man game. No build system. No tests. No linter.

## Architecture

- Entry point: `src/index.html` — open directly in browser (no server needed).
- Script load order (critical): `maze.js` → `game.js` → `render.js` → `main.js`.
- State is shared via globals on `window`: `createGame`, `update`, `draw`, `MAZE`, `TUNNEL_ROW`, `PACMAN_START`, `GHOST_STARTS`, `DIRS`.
- `maze.js` defines the 28×31 grid as ASCII strings parsed at load time. Do not mutate `MAZE` directly — each game copies it.
- `game.js` contains rules, movement, collision. `render.js` handles all canvas drawing. `main.js` drives the loop and input.

## Commands

- No build, test, or lint commands exist. Verify changes by opening `src/index.html` in a browser.

## Spec-Driven Workflow

This repo uses `/spec` and `/spec-impl` skills installed locally under `.agents/skills/`.

- **`/spec <description>`** — Define a new feature. Ask clarifying questions, write spec to `specs/NN-slug.md`.
- **`/spec-impl <slug>`** — Implement an approved spec. Creates branch `spec-NN-slug`, implements step by step.

Only specs in `Draft` state exist. The `specs/` directory does not exist yet.
