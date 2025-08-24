# Task Completion Workflow

## Before Starting Development
1. Ensure development dependencies installed: `uv sync --group dev`
2. Check current branch: `git status && git branch`
3. Create feature branch if needed: `git checkout -b feature/description`

## During Development
- Use `uv run` prefix for all Python commands
- Place documents for testing in `docs/` directory (auto-loaded on startup)
- ChromaDB data persists in `backend/chroma_db/` between runs

## After Code Changes (MANDATORY)
Run quality checks before committing:

```bash
# Option 1: Auto-fix issues (recommended for development)
./scripts/format.sh

# Option 2: Check without modifications (good for CI)
./scripts/lint.sh
```

Both scripts run:
- flake8 linting (style and complexity)
- mypy type checking (type safety)
- isort import sorting
- black code formatting

## Testing Requirements
```bash
# Run full test suite
uv run pytest

# Run specific test categories
uv run pytest -m "unit"      # Unit tests only
uv run pytest -m "integration"  # Integration tests
uv run pytest -m "api"      # API endpoint tests
```

## Before Committing
1. All tests must pass: `uv run pytest`
2. Code quality checks pass: `./scripts/lint.sh` (exit code 0)
3. No type errors: `uv run mypy backend/ main.py`

## Environment Notes
- System: Darwin (macOS)
- Python: 3.13+
- Package manager: uv (not pip or poetry)
- Requires ANTHROPIC_API_KEY in .env file