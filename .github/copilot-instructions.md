# Copilot Workspace Instructions

## Development Checklist

Before committing any changes, ensure:

- [ ] `uv run ruff check .` passes with no errors
- [ ] `uv run pytest` passes
- [ ] Code follows Python conventions (snake_case, type hints)
- [ ] No unused variables or imports

## Project Overview

**Soc Ops** is a Social Bingo game built with Python (FastAPI + Jinja2 + HTMX). Players find people who match questions to mark squares and get 5 in a row.

## Architecture

```text
app/
|- templates/       # Jinja2 HTML templates
|  |- base.html
|  |- home.html
|  '- components/   # bingo_board, bingo_modal, game_screen, start_screen
|- static/          # CSS and JS assets
|- models.py        # Pydantic models (GameState, BingoSquare)
|- game_logic.py    # Board generation and bingo detection
|- game_service.py  # Session management (GameSession)
|- data.py          # Question bank
'- main.py          # FastAPI routes and HTMX endpoints
tests/
|- test_api.py         # API endpoint tests (httpx + TestClient)
'- test_game_logic.py  # Game logic unit tests
```

## Key Commands

```bash
uv run uvicorn app.main:app --reload --port 8000  # Run dev server
uv run pytest                                       # Run tests
uv run ruff check .                                 # Lint
```

## Styling

Uses custom CSS utility classes and component styles in `app/static/css/app.css`.

## Design Guide

When redesigning or adding UI, follow these principles:

- Visual direction: clean premium minimal. Avoid neon, cyberpunk, or generic default templates.
- Typography: use expressive but readable pairings. Prefer `Plus Jakarta Sans` for UI text and `DM Mono` for numeric/system accents.
- Color system: define and reuse CSS variables in `:root`. Keep a focused palette with one primary brand color, one warm accent, and strong neutral contrast.
- Surfaces: use layered backgrounds, subtle gradients, and restrained shadows to create depth without visual noise.
- Motion: use purposeful transitions and one or two meaningful entrance animations. Keep animations short and calm.
- Component shape language: consistent radii, spacing rhythm, and border treatment across cards, buttons, and controls.
- Responsiveness: design mobile first for bingo board legibility and tap targets; then scale up for desktop.
- Accessibility: preserve readable contrast, clear focus/hover states, and semantic labels/roles for interactive UI.

App-specific guidance:

- Keep game flow and HTMX wiring unchanged (`hx-post`, `hx-target`, `hx-swap`).
- Preserve state-based styling semantics for squares: default, marked, winning, and free-space states must remain visually distinct.
- Keep copy mostly stable unless explicitly requested.

Docs-specific guidance:

- Keep locale support intact across `docs/`, `docs/es/`, and `docs/pt_BR/`.
- Keep docs theme toggle support (dark and light parity) using shared variables in `docs/light-theme.css`.
- Avoid inline styles when a reusable class can be added to shared stylesheets.

## State Management

- `GameSession` manages game state server-side
- State persisted via signed cookies (itsdangerous)
- HTMX handles partial page updates without full reloads
