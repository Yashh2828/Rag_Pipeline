# RAG PDF Q&A Notebook

A Jupyter Notebook that builds a Retrieval-Augmented Generation (RAG) pipeline for PDF documents using FAISS, Sentence Transformers, and Google Gemini. It covers ingestion, chunking, vectorization, persistence, and an interactive Q&A interface.

## Features

- PDF loading with metadata preservation
- Recursive text splitting with overlap
- Local embeddings using Sentence Transformers
- FAISS index creation and persistence
- Index rehydration for fast reuse
- Google Gemini-powered summarization and Q&A
- Interactive widget-based Q&A interface

## Project Structure

- `Rag.ipynb`: Main notebook with the full RAG pipeline
- `requirements.txt`: Python dependencies
- `faiss_index/`: Persisted FAISS index artifacts
  - `documents.json`: Stored document chunks and metadata
  - `embeddings.npy`: Numpy array of document embeddings

## Prerequisites

- Python 3.9+
- A Google Gemini API key

## Setup

1. Create a virtual environment (optional but recommended).
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file in the project root:

   ```bash
   GOOGLE_API_KEY=your_api_key_here
   PDF_DATA_PATH=./data/sample.pdf
   FAISS_INDEX_PATH=./faiss_index
   CHUNK_SIZE=1000
   CHUNK_OVERLAP=100
   TOP_K_RESULTS=3
   EMBEDDING_MODEL=all-MiniLM-L6-v2
   ```

## Usage

Open and run the notebook:

```bash
jupyter notebook Rag.ipynb
```

Run the cells in order to:

1. Install dependencies
2. Load environment variables
3. Load and split the PDF
4. Create embeddings and build the FAISS index
5. Rehydrate the index (optional)
6. Ask questions through the widget interface

## Notes

- If your PDF is large, embedding generation can take time.
- The FAISS index artifacts in `faiss_index/` can be reused in future sessions.

## Troubleshooting

- If `GOOGLE_API_KEY` is missing, the notebook will raise a `ValueError`.
- Ensure the PDF path in `.env` points to an existing file.

## License

Add your license here (e.g., MIT).
