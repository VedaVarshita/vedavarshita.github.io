---
title: "LLaMA Vector Search Engine"
date: 2024-09-30
categories: [Projects, Machine Learning, NLP]
tags: [llama, langchain, rag, faiss, vector-search, semantic-search, nlp]
---

<!--  -->

<!-- # Building a High-Performance RAG System with LLaMA 3.2

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
 -->

 





## Overview
This project implements a sophisticated RAG research assistant that combines:

- Dense vector retrieval using FAISS for semantic search
- Local LLM inference with LLaMA 3.2 via Ollama
- Three operational modes: Standard RAG, LangGraph workflow, and DSPy optimization
- Interactive web interface built with Gradio

The system is designed for researchers and practitioners who need to quickly search and understand large collections of academic papers while maintaining full control over their data.

This RAG system addresses these challenges through semantic search, intelligent retrieval strategies, and contextual answer generation.

## Features
### Core Capabilities

- Semantic Search: Understanding query intent beyond keyword matching
- Multi-Document Support: Process and index entire research paper collections
- Three RAG Modes:

    - Standard RAG: Direct retrieval and generation pipeline
    - LangGraph: Workflow with document grading and conditional routing
    - DSPy: Optimized prompting and structured generation


- Interactive Web UI: User-friendly Gradio interface with real-time responses
- Performance Analytics: Track query statistics, latency, and mode effectiveness
- Source Attribution: Automatic citation of source documents

### Technical Features

Maximal Marginal Relevance (MMR) for diverse retrieval results
Configurable chunk sizes and overlap for optimal retrieval
FAISS-based vector indexing for fast similarity search
Streaming responses for better user experience
Session statistics and performance tracking
Example questions for quick exploration

## System Architecture
┌─────────────────────────────────────────────────────────────┐
│                     Document Processing                     │
├─────────────────────────────────────────────────────────────┤
│  PDF Loading → Text Splitting → Embedding → Vector Storage  │
│  (PyMuPDF)     (Recursive)      (Nomic)     (FAISS)         │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│                    Query Processing                         │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  ┌─────────────┐  ┌──────────────┐  ┌─────────────┐         │
│  │ Standard    │  │  LangGraph   │  │    DSPy     │         │
│  │    RAG      │  │   Workflow   │  │ Optimized   │         │
│  └─────────────┘  └──────────────┘  └─────────────┘         │
│         ↓                 ↓                  ↓              │
│         └─────────────────┴──────────────────┘              │
│                           ↓                                 │
│              MMR Retrieval (k=3, fetch_k=100)               │
│                           ↓                                 │
│              LLaMA 3.2 Generation (Ollama)                  │
└─────────────────────────────────────────────────────────────┘
                            ↓
┌─────────────────────────────────────────────────────────────┐
│                      Gradio Web UI                          │
│  Chat Interface | Mode Selection | Statistics | Examples    │
└─────────────────────────────────────────────────────────────┘



## ⚙️ Configuration

### Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `EMBEDDING_MODEL` | `nomic-embed-text` | Ollama embedding model name |
| `CHAT_MODEL` | `llama3.2:1b` | Ollama chat model name |
| `BASE_URL` | `http://localhost:11434` | Ollama API endpoint |
| `CHUNK_SIZE` | `1024` | Document chunk size in characters |
| `CHUNK_OVERLAP` | `128` | Overlap between chunks |

These parameters control model selection, document chunking behavior, and backend connectivity.


## 📊 Performance Metrics

### Overall Results

| Metric | Standard RAG | LangGraph | DSPy |
|--------|-------------|-----------|------|
| **Quality Score** | 74% | 63% | 76% |
| **Average Latency** | 1.79s | 1.31s | 1.06s |
| **Success Rate** | 88% | 60% | 94% |
| **MRR** | 0.82 | 0.71 | 0.86 |

Key observations:
- DSPy achieves the strongest overall performance  
- LangGraph offers lower latency with stricter filtering  
- Standard RAG provides a stable and reliable baseline  



## Repository

[GitHub Repository](https://github.com/VedaVarshita/llama3.2_RAG_Application)






<!-- Hf_Spcae branch -->
<!--
## Project Overview
This project addresses a critical challenge in modern AI research: how to efficiently extract relevant information from vast collections of academic literature. Traditional keyword search fails to capture semantic meaning, while manual review is time-intensive and doesn't scale.
Solution: A fully local, modular RAG system that combines:

Dense vector retrieval (FAISS) for semantic understanding
Maximal Marginal Relevance (MMR) for diverse, non-redundant results
Local LLM inference (LLaMA 3.2) for privacy and cost control
Agent-based orchestration (LangGraph) for complex multi-step reasoning

## Key Achievements

86% Mean Reciprocal Rank (MRR) - retrieval accuracy benchmark
56% latency reduction - optimized vector operations
27% relevance improvement - MMR vs baseline similarity search
94% success rate - with DSPy optimization mode
30+ research papers - indexed and searchable


## System Architecture
The system follows a clean, modular design where each component has a single responsibility:
┌─────────────────────────────────────────────────────────────┐
│                     User Interface Layer                    │
│              (Gradio Web UI / CLI Interface)                │
└────────────────────────┬────────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────────┐
│                   Orchestration Layer                       │
│  ┌──────────────┐  ┌──────────────┐  ┌─────────────────┐    │
│  │  Standard    │  │  LangGraph   │  │     DSPy        │    │
│  │     RAG      │  │   Workflow   │  │  Optimization   │    │
│  └──────────────┘  └──────────────┘  └─────────────────┘    │
└────────────────────────┬────────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────────┐
│                    Retrieval Layer                          │
│  ┌──────────────────┐         ┌─────────────────────────┐   │
│  │  FAISS Vector    │◄────────┤  MMR Retrieval          │   │
│  │     Store        │         │  (k=3, fetch_k=100)     │   │
│  └──────────────────┘         └─────────────────────────┘   │
└────────────────────────┬────────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────────┐
│                   Generation Layer                          │
│  ┌──────────────────────────────────────────────────────┐   │
│  │         LLaMA 3.2-3B Instruct (HuggingFace)          │   │
│  │         • Temperature: 0.1                           │   │
│  │         • Max Tokens: 512                            │   │
│  └──────────────────────────────────────────────────────┘   │
└────────────────────────┬────────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────────┐
│                  Document Processing                        │
│  ┌──────────┐  ┌──────────┐  ┌────────────┐  ┌──────────┐   │
│  │   PDF    │─►│  Text    │─►│ Embedding  │─►│  FAISS   │   │
│  │ Parsing  │  │Splitting │  │ Generation │  │ Indexing │   │
│  └──────────┘  └──────────┘  └────────────┘  └──────────┘   │
└─────────────────────────────────────────────────────────────┘
## Component Breakdown

1. Document Processing Pipeline

PDF Parsing: PyMuPDF extracts text while preserving structure
Chunking Strategy: 1024-token chunks with 128-token overlap
Why it matters: Maintains semantic coherence while optimizing retrieval granularity

2. Vector Store & Embeddings

FAISS: In-memory vector database for fast similarity search
Embeddings: sentence-transformers/all-MiniLM-L6-v2 (384 dimensions)
Indexing: L2 distance metric with flat index structure
Performance: Sub-second retrieval across 30+ documents

3. Retrieval Strategy

MMR Algorithm: Balances relevance and diversity
Parameters: k=3 (top results), fetch_k=100 (candidate pool), λ=1 (diversity weight)
Impact: +27% relevance improvement vs naive top-k search

4. Three RAG Modes
Standard RAG

Direct retrieval → generation pipeline
Fastest mode (avg 1.79s latency)
74% quality score, 88% success rate

LangGraph Workflow

Stateful execution: Multi-step reasoning with conditional branching
Document grading: Automatic relevance filtering
Fallback handling: Graceful degradation when no relevant docs found
1.31s avg latency, 60% success rate (experimental)

DSPy Optimization ⭐ Recommended

Prompt optimization: Learns from examples to refine prompts
Quality: 76% (highest)
Speed: 1.06s (fastest)
Success: 94% (most reliable)

## Technical Implementation
### LangGraph Integration
LangGraph enables sophisticated agent-based workflows with:

State management: Tracks documents, generation status, and errors
Conditional edges: Routes to generation or fallback based on document quality
Retry logic: Automatically handles failures

### DSPy Optimization
DSPy treats prompts as learnable parameters:

Automatically refines prompts based on retrieval quality
Uses meta-llama/Llama-3.2-3B-Instruct
Implements custom BaseLM wrapper for HuggingFace integration -->