# Installation Guide

## Prerequisites

- Python 3.10+ installed on Windows
- Internet access to download Python packages and the approved Pearson BTEC PDF
- A valid Groq API key configured in Streamlit secrets

## Required Python packages

Install the required packages using pip:

```bash
pip install streamlit chromadb sentence-transformers pypdf python-docx groq fpdf python-pptx requests
```

## Setting up Groq

1. Obtain a valid Groq API key.
2. Add the key to Streamlit secrets as `GROQ_API_KEY`.

Example `.streamlit/secrets.toml`:

```toml
GROQ_API_KEY = "your_groq_api_key_here"
```

## Running the app

From the project root:

```bash
streamlit run main.py
```

## Notes

- The app builds a local ChromaDB index in `chroma_db`.
- Approved external content is loaded from a fixed Pearson URL.
- `data` folder should contain locally approved materials if you want additional sources.
