# Codebase Structure

## High-Level Architecture
RAG system with FastAPI backend serving both API and static frontend.

## Core Backend Components (`backend/`)
- **app.py**: FastAPI application, routes, static file serving
- **rag_system.py**: Main orchestrator coordinating all components
- **vector_store.py**: ChromaDB integration with dual collections
- **ai_generator.py**: Anthropic Claude API integration with tool calling
- **search_tools.py**: Tool-based search system (CourseSearchTool, ToolManager)
- **document_processor.py**: Document ingestion and text chunking
- **session_manager.py**: Conversation history management
- **config.py**: Application configuration and constants
- **models.py**: Data models and schemas

## Frontend (`frontend/`)
Vanilla JavaScript single-page application served by FastAPI as static files.

## Data Flow Pattern
1. Documents (PDF, DOCX, TXT) → `docs/` directory
2. DocumentProcessor → chunks and metadata extraction
3. VectorStore → dual ChromaDB collections:
   - `course_catalog`: course metadata and lesson structure
   - `course_content`: searchable text chunks
4. User queries → AI with CourseSearchTool → contextual responses

## Key Configuration (config.py)
- Chunk size: 800 chars, 100 overlap
- Embedding: all-MiniLM-L6-v2
- Max search results: 5
- Conversation history: 2 message pairs
- Model: claude-sonnet-4-20250514

## Testing Structure (`backend/tests/`)
- Comprehensive test coverage for all core components
- Pytest markers: unit, integration, api, slow
- Test configuration in pyproject.toml