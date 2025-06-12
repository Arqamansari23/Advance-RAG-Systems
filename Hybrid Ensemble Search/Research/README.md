# Hybrid Ensemble RAG System with BM25 and Semantic Retrievers

This project implements a **Hybrid Ensemble Retrieval-Augmented Generation (RAG) System** that combines both BM25 (keyword-based) and semantic (embedding-based) retrievers for robust document search and question answering.

## Key Features

- **PDF Ingestion:** Load and process PDF documents for analysis.
- **Text Chunking:** Split documents into manageable chunks for efficient retrieval.
- **BM25 Retriever:** Classic keyword-based search for precise term matching.
- **Semantic Retriever:** Embedding-based vector search for semantic similarity.
- **Ensemble Retriever:** Combines BM25 and semantic retrievers for hybrid search, leveraging the strengths of both.
- **Google Generative AI Integration:** Uses Gemini models for embeddings and LLM-based answers.
- **Retrieval-Augmented Generation:** Answers questions using retrieved context and LLM reasoning.

## How It Works

1. **Load PDF:** The system reads a PDF and converts it into text chunks.
2. **Build Retrievers:** 
    - BM25Retriever indexes chunks for keyword search.
    - Vector retriever indexes chunks using embeddings for semantic search.
3. **Hybrid Search:** EnsembleRetriever combines results from both retrievers.
4. **RAG Pipeline:** Retrieved chunks are passed to a language model to generate answers.

## Example Usage

```python
query = "What is the revenue of the company in 2024?"
response = rag_chain.invoke({"input": query})
print(response["answer"])
```

## Requirements

- Python 3.9+
- `langchain`, `langchain-community`, `langchain-google-genai`, `chromadb`, `faiss-cpu`
- Google API key for Gemini models

## Getting Started

1. Install dependencies:
    ```
    pip install langchain langchain-community langchain-google-genai chromadb faiss-cpu
    ```
2. Place your PDF in the project folder.
3. Run the Jupyter notebook `research.ipynb` to build the hybrid RAG pipeline and ask questions.

## Notes

- If you see protobuf errors, run: `pip install protobuf==3.20.3`
- Update your Google API key in the notebook before running.

---

*This project demonstrates advanced hybrid retrieval for RAG systems using both BM25 and semantic search.*