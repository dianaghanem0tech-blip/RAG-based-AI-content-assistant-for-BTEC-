# Project Structure

```
project root/
│
├── chroma_db/                 # Local ChromaDB storage folder
│   ├── chroma.sqlite3
│   └── <collection folders>
│
├── data/                      # Expected folder for local approved source files
│   ├── *.pdf
│   ├── *.docx
│   └── *.txt
│
├── main.py                    # Main Streamlit application and RAG workflow
├── OllamaSetup.exe            # Optional installer file (project now uses Groq for LLM access)
└── project description/       # Generated documentation files
    ├── Readme.md
    ├── execution results.md
    ├── installation guide.md
    ├── project structure.md
    ├── requirments.md
    └── summary.md
```

## Important files

- `main.py`: application logic, document ingestion, embedding creation, retrieval, and UI.
- `chroma_db/`: persistent vector database used by the app.
- `data/`: local document source directory used during build.
- `project description/`: generated project documentation.
