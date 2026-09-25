# Semantic Search / Retrieval Demo with ChromaDB

A small demo showing semantic search and document retrieval using vector embeddings — built while learning the retrieval component of RAG (Retrieval-Augmented Generation) systems.

## What it does

1. Stores a small set of documents in a ChromaDB vector collection
2. Embeds documents using `sentence-transformers` (all-MiniLM-L6-v2)
3. Given a natural language query, retrieves the most semantically relevant document(s) using vector similarity search
4. Concatenates the retrieved context into a response

## Tech Stack

- Python
- ChromaDB (vector database)
- sentence-transformers (embeddings)

## Example

```python
query = "What is the main idea of transformers?"

results = collection.query(
    query_texts=[query],
    n_results=2
)
# Retrieves: "Transformers allow parallel processing and faster training."
#            "Transformers use attention mechanisms instead of RNNs."
```

## Note

This project demonstrates the **retrieval** half of a RAG pipeline — semantic search over embedded documents. It does not yet include a generation step (an LLM call over the retrieved context), so it's a retrieval/semantic-search demo rather than a full RAG system.

## Possible Next Step

Add an LLM call (e.g. OpenAI, Gemini, or a local Hugging Face model) that takes the retrieved context and generates a natural-language answer — completing the "Generation" half of RAG.
