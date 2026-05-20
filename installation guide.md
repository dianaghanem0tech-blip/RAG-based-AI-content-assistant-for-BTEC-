# Installation Guide

## Prerequisites

- Python 3.10+ installed on Windows
- Internet access to download Python packages and the approved Pearson BTEC PDF
- Ollama installed and running locally

## Required Python packages

Install the required packages using pip:

```bash
pip install streamlit chromadb sentence-transformers pypdf python-docx ollama fpdf python-pptx requests
```

## Setting up Ollama

1. Install Ollama if not already installed.
2. Start the model server before running the app:

```bash
ollama run llama3
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
