# Project Summary

This project is BTEC RAG assistant built with Streamlit. It extracts text from approved PDF, DOCX, and TXT documents, generates embeddings with `sentence-transformers`, and stores vectors in a local `ChromaDB` database.

The application retrieves relevant content based on semantic similarity and uses Groq to generate answers only from approved sources. It supports multiple task types, including normal answers, quiz questions, assignment guidance, lesson summaries, learning activities, and short explanations.

The user interface allows choosing the output format as text, PDF, or PowerPoint, while showing the source and unit of the retrieved approved content.
