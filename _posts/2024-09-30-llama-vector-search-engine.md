---
title: "LLaMA Vector Search Engine"
date: 2024-09-30
categories: [Projects, Machine Learning, NLP]
tags: [llama, langchain, rag, faiss, vector-search, semantic-search, nlp]
---

<!-- ## Overview

The LLaMA Vector Search Engine is an AI-powered research assistant that enables semantic search across machine learning research papers. Built using LangChain and LLaMA 3.2, this system provides researchers with an efficient way to discover and retrieve relevant academic literature through natural language queries.

## Problem Statement

Researchers and practitioners in machine learning face several challenges when working with academic literature:
- **Information Overload**: Thousands of papers are published annually, making it difficult to find relevant work
- **Keyword Limitations**: Traditional keyword-based search misses semantically similar but differently worded content
- **Time Constraints**: Manually sifting through papers is time-consuming
- **Context Understanding**: Need for systems that understand research context and relationships

This vector search engine addresses these challenges by enabling semantic understanding of research content and providing fast, relevant retrieval.

## Methodology

### Architecture

The system implements a Retrieval-Augmented Generation (RAG) architecture:

1. **Document Processing**: Research papers are chunked and processed for embedding
2. **Vector Embedding**: Documents are embedded using OllamaEmbeddings
3. **Vector Store**: FAISS (Facebook AI Similarity Search) indexes embeddings for fast retrieval
4. **Retrieval**: Maximal Marginal Relevance (MMR) algorithm selects diverse, relevant chunks
5. **Generation**: LLaMA 3.2 generates contextual responses based on retrieved content

### Key Innovations

- **MMR-based Retrieval**: Balances relevance and diversity, preventing redundant results
- **FAISS Vector Store**: Enables fast similarity search across large document collections
- **Parallel Query Processing**: Supports concurrent queries for improved throughput
- **Semantic Understanding**: Leverages LLaMA 3.2's capabilities for context-aware retrieval

### Performance Optimizations

- Optimized chunking strategy for research papers
- Efficient embedding generation pipeline
- Fast vector similarity search with FAISS
- Parallel processing capabilities

## Results

- **Mean Reciprocal Rank (MRR)**: Achieved 86% MRR on 30+ ML research papers, indicating highly relevant search results
- **Latency Reduction**: Reduced search latency by 56% compared to baseline approaches
- **Processing Speed**: Processes 5-6 chunks per second
- **Relevance Improvement**: MMR-based retrieval improved result relevance by 27% compared to standard similarity search
- **Scalability**: Successfully handles parallel query processing
- **Documentation**: Comprehensive technical documentation for reproducibility

## Technologies Used

- **LangChain**: Framework for building LLM applications and RAG systems
- **LLaMA 3.2**: Large language model for understanding and generation
- **FAISS**: Efficient similarity search and clustering of dense vectors
- **OllamaEmbeddings**: Embedding generation for document representation
- **RAG (Retrieval-Augmented Generation)**: Architecture pattern combining retrieval and generation
- **Python**: Primary programming language

## Repository

[GitHub Repository](https://github.com/VedaVarshita/llama3.2_RAG_Application)

## Applications

- Academic research assistance
- Literature review automation
- Research paper discovery
- Knowledge base search systems
- Domain-specific information retrieval

## Future Enhancements

- Expand to additional research domains beyond ML
- Implement citation network analysis
- Add support for multi-modal content (figures, tables)
- Integrate with academic databases (arXiv, PubMed)
- Develop interactive visualization of search results -->


<!--  -->

# Building a High-Performance RAG System with LLaMA 3.2

## Project Overview

This project implements a **Retrieval-Augmented Generation (RAG) research assistant** designed to perform semantic search and question-answering over collections of research papers. The system combines **dense vector retrieval (FAISS)** with **local LLM inference (LLaMA 3.2 via Ollama)** to deliver accurate, low-latency responses while remaining fully self-hosted.

The primary goal was to **optimize retrieval relevance, latency, and system modularity**, while maintaining transparency and control over the full RAG pipeline.

---

## Problem Statement
Researchers and practitioners in machine learning face several challenges when working with academic literature:
- **Information Overload**: Thousands of papers are published annually, making it difficult to find relevant work
- **Keyword Limitations**: Traditional keyword-based search misses semantically similar but differently worded content
- **Time Constraints**: Manually sifting through papers is time-consuming
- **Context Understanding**: Need for systems that understand research context and relationships

Traditional keyword-based search struggles with:

* Semantic mismatch between queries and documents
* Long, unstructured research papers
* Redundant or low-diversity retrieval results

At the same time, cloud-based LLM solutions introduce:

* High latency
* Cost constraints
* Limited data control

This project addresses these challenges by designing a **local, modular RAG system** optimized for:

* Semantic relevance
* Retrieval diversity
* Low-latency inference
* Scalability across document collections

---

## System Architecture

The system follows a **clean, modular architecture**, where each component has a single responsibility:

* **Document Ingestion**: PDF parsing using PyMuPDF
* **Text Chunking**: Recursive splitting for semantic coherence
* **Vector Indexing**: FAISS-based dense vector store
* **Retriever**: MMR-based retrieval to balance relevance and diversity
* **Generation**: LLaMA 3.2 via LangChain LCEL pipeline
* **Interface**: Interactive command-line chat

This design enables easy experimentation with chunk sizes, retrievers, embedding models, and LLMs.

---

## Methodology

### Document Processing & Chunking

* PDFs are parsed and converted into raw text
* Text is split into overlapping chunks (1024 tokens, 128 overlap)
* Chunking strategy preserves semantic continuity while improving retrieval granularity

This step directly impacts retrieval quality—overly small chunks reduce context, while overly large chunks hurt precision.

---

### Embedding & Vector Search

* **Embeddings** generated using `nomic-embed-text` via Ollama
* **FAISS** used for fast in-memory similarity search
* L2 distance metric selected for efficient dense retrieval

FAISS was chosen for its speed and suitability for local deployments without external dependencies.

---

### Retrieval Strategy: Maximal Marginal Relevance (MMR)

Instead of naive top-k similarity search, the system uses **MMR** to:

* Reduce redundancy across retrieved chunks
* Increase topical diversity
* Improve downstream answer quality

MMR parameters (`k`, `fetch_k`, `lambda`) were tuned empirically to balance relevance and coverage.

---

### RAG Pipeline Construction

* Implemented using **LangChain Expression Language (LCEL)**
* Retrieved chunks are injected into a structured prompt
* LLaMA 3.2 generates grounded responses using retrieved context
* Streaming output improves user experience and perceived latency

---

## Evaluation & Results

The system was evaluated on real research documents using relevance and latency-focused metrics.

### Quantitative Results

* **Mean Reciprocal Rank (MRR):** 86%
* **Retrieval Relevance Improvement:** +27% with MMR vs baseline similarity search
* **Latency Reduction:** 56% through optimized vector operations
* **Processing Speed:** 5–6 chunks/second
* **Scalability:** Successfully handled 30+ documents without degradation

### Qualitative Observations

* Responses were significantly more grounded and citation-consistent
* Reduced hallucinations due to tighter retrieval context
* Improved answer diversity for broad or ambiguous queries

---
## Repository

[GitHub Repository](https://github.com/VedaVarshita/llama3.2_RAG_Application)

---

## Technologies Used

- **LangChain**: Framework for building LLM applications and RAG systems
- **LLaMA 3.2**: Large language model for understanding and generation
- **FAISS**: Efficient similarity search and clustering of dense vectors
- **OllamaEmbeddings**: Embedding generation for document representation
- **RAG (Retrieval-Augmented Generation)**: Architecture pattern combining retrieval and generation
- **Python**: Primary programming language


---

## Key Insights

* Retrieval quality dominates generation quality in RAG systems
* MMR dramatically improves answer usefulness by reducing redundancy
* Chunking strategy has a larger impact than model size
* Local LLM inference is viable for research-scale workloads
* Modular design accelerates experimentation and debugging

---

## Design Trade-offs

* **Local inference vs cloud APIs**: Lower cost and higher control, slightly lower raw model capacity
* **FAISS vs managed vector DBs**: Faster iteration locally, less operational overhead
* **CLI interface**: Faster prototyping, defers UI complexity

These decisions prioritized **system understanding and performance tuning** over production polish.

---

## Limitations

* Limited to PDF documents
* No persistent conversation memory
* Single-user, local execution
* No citation highlighting in responses

---

## Future Improvements

* Web-based UI (Streamlit or Gradio)
* Multi-format document support (HTML, DOCX, Markdown)
* Conversation memory and follow-up reasoning
* Hybrid retrieval (BM25 + dense vectors)
* Cloud-based or distributed vector storage
* Real-time document updates

---

## Conclusion

This project demonstrates an **end-to-end RAG system built from first principles**, emphasizing retrieval optimization, modular design, and measurable performance improvements. It highlights practical trade-offs in deploying local LLM-powered systems and provides a strong foundation for extending toward production-grade AI applications.

---
