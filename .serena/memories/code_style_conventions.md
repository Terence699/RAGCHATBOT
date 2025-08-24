# Code Style and Conventions

## Python Style (Enforced by Tools)
- **Line length**: 88 characters (Black standard)
- **Python version**: 3.13+
- **Type hints**: Required for all functions (mypy enforces)
- **Import sorting**: isort with black profile
- **Formatting**: Black formatter

## Code Quality Rules
- **No untyped functions**: mypy requires type annotations
- **Import organization**: First party imports use "backend" namespace
- **Docstrings**: Not explicitly enforced but recommended
- **Testing**: pytest with markers (unit, integration, api, slow)

## File Organization
- Tests in `backend/tests/` with `test_*.py` naming
- Main application code in `backend/`
- Static frontend files served by FastAPI
- Documents for ingestion in `docs/`
- ChromaDB persistence in `backend/chroma_db/`

## Configuration Details
- Black profile for isort (consistent formatting)
- Flake8 ignores E203, W503 (Black compatibility)
- mypy strict mode enabled for type safety
- pytest with verbose output and colored results

## Key Patterns
- Use uv for all Python execution (not direct python)
- FastAPI serves both API routes (/api/*) and static files
- Vector store uses dual ChromaDB collections pattern
- AI tool calling pattern for search functionality