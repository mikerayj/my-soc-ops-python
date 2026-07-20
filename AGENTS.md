# AGENTS

Guidance for AI coding agents working in this repository.

## Scope And Source Of Truth

- Start with [README.md](README.md) for project intent and lab flow.
- Use workshop docs for deeper context: [workshop/GUIDE.md](workshop/GUIDE.md).
- Follow repository customization rules in:
  - [.github/instructions/general.instructions.md](.github/instructions/general.instructions.md)
  - [.github/instructions/css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md)
  - [.github/instructions/frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md)

## Environment And Commands

- Python requirement is `>=3.13` (see [pyproject.toml](pyproject.toml)).
- Use `uv` for environment and dependency management.

Common commands:

- `uv sync`
- `uv run pytest`
- `uv run ruff check .`
- `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000`

## Architecture Map

- FastAPI entrypoint and routes: [app/main.py](app/main.py)
- Session orchestration: [app/game_service.py](app/game_service.py)
- Pure game logic and bingo checks: [app/game_logic.py](app/game_logic.py)
- Domain models: [app/models.py](app/models.py)
- Question data: [app/data.py](app/data.py)
- Jinja templates: [app/templates](app/templates)
- Static assets: [app/static](app/static)
- Tests: [tests](tests)

## Implementation Conventions

- Keep route handlers thin in [app/main.py](app/main.py); delegate game behavior to service/logic modules.
- Keep state transitions in [app/game_service.py](app/game_service.py), and reusable/pure board logic in [app/game_logic.py](app/game_logic.py).
- Prefer targeted template component updates in [app/templates/components](app/templates/components) for HTMX responses.
- Reuse existing CSS utility classes in [app/static/css/app.css](app/static/css/app.css). Add new utilities there when needed.

## Testing Expectations

- Add or update tests for behavior changes in:
  - [tests/test_game_logic.py](tests/test_game_logic.py) for rules/state logic
  - [tests/test_api.py](tests/test_api.py) for endpoint/template behavior
- Run `uv run pytest` before finishing changes.

## Pitfalls To Avoid

- Do not use VS Code Simple Browser for this app. Follow [.github/instructions/general.instructions.md](.github/instructions/general.instructions.md).
- Templates are under [app/templates](app/templates), not a top-level `templates/` directory.
- Session storage is in-memory (`_sessions` in [app/game_service.py](app/game_service.py)); server restarts reset active games.
- The [.solutions](.solutions) tree is reference material for workshop steps. Do not modify it unless explicitly requested.

## Existing Agent Assets

- Custom agents live in [.github/agents](.github/agents).
- Prompt shortcuts live in [.github/prompts](.github/prompts).
