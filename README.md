
# Retrieval Augmented Generation with Advanced techniques

A brief description of what this project does and who it's for

# 📘 Setup

1. Install dependencies:
pip install datasets sentence-transformers faiss-cpu rank-bm25 anthropic

2. Set your API key:
export ANTHROPIC_API_KEY=your_key_here

3. Run the notebook:
colab notebook

---

# 📘 Brief documentation of the implementation

- The project implements a Retrieval-Augmented Generation (RAG) system using the PopQA dataset and a Wikipedia subset.

- The pipeline includes:
  - Dense Retrieval (FAISS + embeddings)
  - Query Expansion
  - Hybrid Retrieval (Dense + BM25)
  - Reranking (Cross-Encoder)
  - Citation-Grounded Generation
  - Self-Reflective RAG

- The system retrieves top-k passages, generates answers using a grounded prompt, and applies a reflection step to validate outputs.

---

# 📘 Analysis

- Dense retrieval provides semantic matching but struggles with exact factual queries.  
- Query expansion increases recall but introduces noise.  
- Hybrid retrieval improves diversity, while reranking improves ordering.  
- The reflection step improves reliability by preventing unsupported answers.  

---

# 📘 Challenges

- Mismatch between PopQA and the Wikipedia subset leading to missing answers.  
- Retrieval of incorrect entities due to ambiguous names.  
- BM25 bias toward frequent keywords.  
- Ensuring grounded generation without hallucination.  
