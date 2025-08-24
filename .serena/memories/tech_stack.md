# Technology Stack

## Backend
- **Python 3.13+**: Core language
- **FastAPI**: Web framework and API server
- **uvicorn**: ASGI server for development
- **ChromaDB**: Vector database for embeddings
- **Anthropic Claude**: AI model (claude-sonnet-4-20250514)
- **SentenceTransformers**: Embedding model (all-MiniLM-L6-v2)

## Frontend  
- **Vanilla JavaScript**: No frameworks, native JS
- **HTML5/CSS3**: Static frontend served by FastAPI
- **Markdown rendering**: For AI response formatting

## Development Tools
- **uv**: Python package manager (replaces pip/poetry)
- **black**: Code formatting
- **isort**: Import sorting
- **flake8**: Linting
- **mypy**: Type checking
- **pytest**: Testing framework

## Key Dependencies
- chromadb==1.0.15
- anthropic==0.58.2
- sentence-transformers==5.0.0
- fastapi==0.116.1
- python-multipart, python-dotenv for utilities