# CommerceAI

An LLM-powered conversational commerce assistant that helps customers discover and compare products through natural-language conversations.

**Status: In Development**

## Current Features

- Product retrieval using semantic vector search.
- BM25 keyword-based retrieval.
- Hybrid retrieval combining semantic and keyword search using Reciprocal Rank Fusion (RRF).
- Cross-encoder-based product reranking.
- Context-aware conversational query rewriting using Google Gemini.
- Product recommendations grounded in retrieved catalog information.
- Conversation history for handling follow-up questions.
- Retrieval evaluation using Precision@K, Recall@K and MRR.

## Technology Stack

- Python
- Google Gemini API
- Sentence Transformers
- ChromaDB
- BM25
- Cross-Encoder Reranking
- Pandas and NumPy

## Project Structure

```text
commerce-ai-assistant/
├── backend/
├── chroma_db/
├── data/
│   └── products/
│       └── products.csv
├── evaluation/
├── frontend/
├── ingestion/
├── llm/
├── memory/
├── notebooks/
├── retrieval/
├── tests/
├── 01_rag_pipeline.ipynb
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
