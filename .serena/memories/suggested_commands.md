# Essential Development Commands

## Application Management
```bash
# Quick start (recommended)
./run.sh

# Manual start
cd backend && uv run uvicorn app:app --reload --port 8000
```

## Environment Setup
```bash
# Install all dependencies
uv sync

# Install with dev dependencies for linting/formatting
uv sync --group dev

# Add new package
uv add package_name
```

## Code Quality (IMPORTANT - Run Before Commits)
```bash
# Format and fix code (modifies files)
./scripts/format.sh

# Check code quality without changes (CI-safe)
./scripts/lint.sh

# Make scripts executable if needed
chmod +x scripts/*.sh
```

## Testing
```bash
# Run all tests
uv run pytest

# Run specific test markers
uv run pytest -m "unit"
uv run pytest -m "integration"
uv run pytest -m "api"

# Run single test file
uv run pytest backend/tests/test_vector_store.py

# Verbose output
uv run pytest -v
```

## Python Execution
Always use `uv run` prefix for Python commands:
```bash
uv run python script.py
uv run mypy backend/
uv run black backend/
```

## Application Access
- Web Interface: http://localhost:8000
- API Docs: http://localhost:8000/docs