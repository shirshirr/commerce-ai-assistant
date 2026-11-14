# CommerceAI — LLM-Powered Conversational Commerce Assistant

An AI-powered conversational shopping assistant that helps customers discover, compare, and evaluate products through natural-language conversations.

CommerceAI combines **Retrieval-Augmented Generation (RAG), hybrid search, reciprocal rank fusion, cross-encoder reranking, and conversational context management** to deliver relevant, context-aware product recommendations grounded in a product catalog.

**Status:** In Development

---

## Key Features

- **Semantic Search:** Retrieves relevant products using vector embeddings and ChromaDB.
- **Keyword Search:** Uses BM25 to identify products based on keyword relevance.
- **Hybrid Retrieval:** Combines semantic and keyword search using Reciprocal Rank Fusion (RRF).
- **Cross-Encoder Reranking:** Refines retrieved results to improve relevance.
- **Context-Aware Conversations:** Uses conversation history and query rewriting to understand follow-up questions.
- **Grounded Product Recommendations:** Generates recommendations using retrieved product information rather than inventing specifications.
- **Conversational Memory:** Maintains context across multiple customer interactions.
- **Retrieval Evaluation:** Includes Precision@K, Recall@K, and Mean Reciprocal Rank (MRR).

## System Architecture

```text
             Customer Query
                    |
                    v
          Contextual Query Rewriting
                 (Gemini)
                    |
                    v
             Hybrid Retrieval
              /           \
             v             v
       Vector Search    BM25 Search
        (ChromaDB)      (Keyword)
              \           /
               v         v
          Reciprocal Rank Fusion
                  (RRF)
                    |
                    v
           Cross-Encoder Reranking
                    |
                    v
           Retrieved Product Context
                    |
                    v
           LLM Response Generation
                 (Gemini)
                    |
                    v
       Context-Aware Product Recommendation
```

## Technology Stack

| Component | Technology |
|---|---|
| Programming Language | Python |
| LLM | Google Gemini API |
| Embeddings | Sentence Transformers |
| Vector Database | ChromaDB |
| Keyword Retrieval | BM25 |
| Hybrid Retrieval | Reciprocal Rank Fusion |
| Reranking | Cross-Encoder |
| Data Processing | Pandas, NumPy |
| Evaluation | Precision@K, Recall@K, MRR |
| Environment Management | Python Virtual Environment |

## Project Structure

```text
commerce-ai-assistant/
│
├── backend/
├── data/
│   └── products/
│       └── products.csv
│
├── evaluation/
├── frontend/
├── ingestion/
├── llm/
├── memory/
├── notebooks/
├── retrieval/
├── tests/
│
├── chroma_db/              # Generated locally
├── 01_rag_pipeline.ipynb
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/shirshirr/commerce-ai-assistant.git
cd commerce-ai-assistant
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**macOS / Linux**

```bash
source .venv/bin/activate
```

**Windows**

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the Gemini API key

Create a `.env` file in the project root using `.env.example` as a reference.

```env
GEMINI_API_KEY=your_gemini_api_key
```

Never commit your actual API key or `.env` file.

### 5. Run the notebook

```bash
jupyter lab
```

Open `01_rag_pipeline.ipynb` and execute the notebook cells in order.

## Product Dataset

CommerceAI currently uses a sample electronics product catalog containing product information such as:

- Product name and category
- Brand and price
- Product description
- Technical specifications
- Warranty information
- Availability

The catalog supports product discovery, comparison, and recommendation experiments.

## Evaluation

The retrieval pipeline includes the following evaluation metrics:

| Metric | Purpose |
|---|---|
| Precision@K | Measures the relevance of retrieved products |
| Recall@K | Measures how many relevant products are retrieved |
| MRR | Measures the ranking position of the first relevant result |

## Future Improvements

- Develop a dedicated conversational web interface.
- Integrate product catalog ingestion and indexing into modular services.
- Implement persistent conversation memory.
- Add advanced retrieval evaluation and experimentation.
- Improve recommendation personalization.
- Add API endpoints for integration with commerce platforms.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---

**Built as an exploration of LLM applications, RAG architectures, hybrid information retrieval, and conversational AI for e-commerce.**
