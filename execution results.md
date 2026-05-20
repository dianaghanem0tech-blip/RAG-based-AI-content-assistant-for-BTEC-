# Execution Results

## What happens when the app runs

1. `main.py` starts the Streamlit application and sets the page layout.
2. The app loads the embedding model `all-MiniLM-L6-v2` using `sentence-transformers`.
3. A persistent ChromaDB client is created at `chroma_db` and the `btec_lms` collection is initialized.
4. The app builds the local database on first run by scanning the `data` folder and approved BTEC URL sources.
5. Supported documents are processed:
   - PDF files via `pypdf`
   - DOCX files via `python-docx`
   - TXT files via standard file reading
6. Text is chunked, embedded, and stored with metadata (source, page, unit).
7. The database is initialized once per Streamlit cache lifecycle.

## Query and response flow

- User submits a question in the Streamlit UI.
- The app retrieves relevant chunks using semantic similarity.
- If the similarity score is below the threshold, the app will not return unsupported context.
- Ollama generates the final answer using only the retrieved approved context.

## Output behavior

- `Text`: displays the response in the app
- `PDF`: generates `btec_output.pdf` and triggers a download
- `PowerPoint`: generates `output.pptx` and triggers a download

## Example console logs

- During database build, the app prints a short review of sample chunks:
  - total document chunks
  - sample source
  - sample page
  - sample unit

- During retrieval, the app prints similarity scores for each candidate result.

## Known behavior

- If no approved content matches the question, the model returns:
  - `Cannot answer based on the available approved sources.`
- The app enforces strict context-based response generation to minimize hallucination.
