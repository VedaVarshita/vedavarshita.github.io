---
# the default layout is 'page'
icon: fas fa-file-lines
order: 1
---

[**Download CV (PDF)**](/assets/Vedavarshita_Nunna_Resume.pdf){: target="_blank" }

# Highlights

- **≈10% → 74%** pre-gradient-update accuracy on MNIST (65% on CIFAR-10) via a novel Bayesian-inspired initialization
- **−20% perplexity** (31.64 → 25.42) and **+17%** task performance aligning a 1.5B-parameter LM with DPO/RLHF
- **86% MRR** semantic retrieval over 30+ ML papers; **94%** query success with DSPy-optimized RAG
- **98% cost reduction** ($15K → $300) on corpus-scale LLM reprocessing at BioNTech

# Education

_Drexel University_ Philadelphia, PA **Master of Science, Artificial Intelligence & Machine Learning** (CGPA: 3.9) Sep 2023 – June 2025

**Coursework**: Intro to Cloud Computing, Data Analysis and Interpretation, Machine Learning.

_Lovely Professional University_ Punjab, India **Bachelor of Technology, Electronics & Communication Engineering (Hons.)** July 2018 – May 2022 _Minor in Data Science_

**Coursework**: Intro to Data Management, Data Science Toolbox: R Programming, Data Visualization.

# Experience

**Gen AI Researcher – Contract** **_BioNTech_** | Python, Databricks | Berkeley Heights, NJ | Jan 2026 – present
- Designed a query-adaptive retrieval fusion strategy for an agentic RAG + knowledge graph system over a 3,285-document oncology corpus, dynamically weighting vector, graph, and keyword signals based on inferred query intent to handle heterogeneous unstructured biomedical data
- Developed a two-pass LLM entity extraction pipeline with windowed cross-chunk deduplication and content-addressed entity identity (18.5K entities, 82K+ edges on Amazon Neptune), enabling idempotent, replayable knowledge graph construction at corpus scale
- Evaluated infrastructure tradeoffs (Neptune over ArangoDB, custom async orchestration over LangGraph) under production constraints; reduced full-corpus LLM reprocessing cost by 98% ($15K → $300) via prompt-version-aware extraction caching with automated cross-store integrity verification (Postgres, Databricks Delta, Neptune)

**AI/ML Research Assistant** **_CODED Lab**, Drexel University_ | Advisor: Dr. Jake Williams | PyTorch, LLM | Philadelphia, PA | July 2024 – Dec 2025
- Expanded a novel Bayesian inspired neural network initialization algorithm leveraging co-occurrence and Product Quantization, improving pre-gradient update accuracy from ≈10% (random) to 74% on MNIST and 65% on CIFAR-10
- Validated the approach through weight evolution analysis, showing 75% cosine similarity between initialized and fully trained kernels, demonstrating its effectiveness as an informative warm-start for neural networks
- Integrated RLHF with 1.5B parameter Language Model via preference-based fine-tuning with DPO and adaptive training, improving performance by 17% and reducing perplexity by 20% (31.64 to 25.42) on the HHH dataset

**Associate Software Engineer** _Location Intelligence R&D dept._ | **PRECISELY** | Python, SQL | Bangalore, India | July 2022 – June 2023 
- Enhanced Geocoded Master Location Data pipeline, expanding coverage to Sweden and France while optimizing data processing for 1M+ geographic locations
- Productionized World Fabric Data automation pipeline by integrating UPU postal data, reducing processing time by 67%, improving cross-country data consistency and reducing manual validation effort
- Automated QA framework, streamlining test case execution, identifying potential discrepancies and rectifying issues within the Alternate Language Data over various countries, resulting in a 28% improvement in accuracy

**Intern** _Location Intelligence R&D dept._ | **PRECISELY** | TensorFlow, SQL, Python | Bangalore, India | Jan 2022 – June 2022 
- Debugged and optimized 50+ SQL queries and validation pipelines across multiple international postal systems (Finland, India, China/HK), improving ETL accuracy by 6% and reducing validation time by 14%
- Implemented address deduplication PoC using Bi-LSTM with GloVe embeddings, achieving 86% accuracy in identifying duplicate addresses across diverse formats
- Contributed to a large-scale data cleaning and transformation pipeline processing 1M+ addresses, reducing duplicates by 40%, and collaborating with data science teams to ensure data consistency and reliability at scale

# Projects & Research


**LLaMA Vector Search Engine** | [Link](https://github.com/VedaVarshita/llama3.2_RAG_Application/tree/extend_langGraph) | LangChain, Retrieval-Augmented Generation | Aug 2024 – Sept 2024
- Architected an AI research assistant using LangChain and LLaMA 3.2, enabling semantic search across 30+ ML research papers with a Mean Reciprocal Rank (MRR) of 86%
- Implemented a vector-based document retrieval pipeline using FAISS and OllamaEmbeddings, reducing search latency by 56% while processing 5–6 document chunks per second
- Extended a stateful LangGraph workflow with conditional routing and automated document grading, achieving 94% success rate through multi-step query refinement and intelligent fallback mechanisms
- Optimized RAG performance using DSPy prompt learning and MMR retrieval strategy, improving answer relevance by 27% and reducing generation latency to 1.06s while maintaining 76% quality scores across 37 test queries

**Synthetic Text Data Generation Pipeline with LoRA** | [Link](https://github.com/VedaVarshita/Synthetic-text-data-generation) | PyTorch, LoRA | June 2025 – July 2025
- Designed and implemented an end-to-end, 4-stage machine learning data pipeline (ingest, validation, cleaning, monitoring) for synthetic text generation across AG News and IMDB datasets, enabling zero-shot, one-shot, few-shot, and LoRA fine-tuned text generation
- Orchestrated workflows with Prefect, containerized with Docker + CI/CD, and exposed the pipeline through RESTful APIs (FastAPI) for integration into downstream systems
- Integrated logging using MLflow and monitoring to track generation quality and diversity (ROUGE-L, Self-BLEU, VendiScore, N-gram div.), reducing perplexity by 10–15× while ensuring continuous evaluation and reproducibility across 10+ tunable hyperparameters



<!-- - Architected AI research assistant using LangChain and LLaMA 3.2, enabling semantic search across 30+ ML research papers with Mean Reciprocal Rank of 86%
- Implemented vector-based document retrieval system using FAISS and OllamaEmbeddings, reducing search latency by 56% while processing 5-6 chunks/second
- Optimized search accuracy using Maximal Marginal Relevance (MMR) based retrieval system, improving result relevance by 27%, supporting parallel query processing and documented technical details for reproducibility -->

# Technical Skills

**Programming & Dev Tools**: Python, C/C++, Java, NumPy, Pandas, SQL, Git, Docker, Spark, Databricks, AWS, Azure, Jira

**ML/AI Tools**: Scikit-Learn, PyTorch, TensorFlow, OpenCV, LlamaIndex, HuggingFace, LangChain, ONNX, MLflow, Amazon Neptune, Knowledge Graphs

**LLMs & Gen AI**: Models (LLaMA, Mistral, OpenAI, Deepseek), SLMs, Multi-modal Models, LoRA, Finetuning, RAG, Prompt Engineering, Statistical Modeling, FAISS, Pinecone

**Core competencies**: Probability, Statistics, Exploratory Data Analysis, Data Visualization, Unsupervised Learning, Reinforcement Learning, Deep Learning, Computer Vision, Natural Language Processing

# Certifications

- Introduction to Machine Learning using TensorFlow - [Udacity](https://confirm.udacity.com/4WTHAAKD) July 2021
- Data Science for Engineers - [NPTEL](https://nptel.ac.in/noc/E_Certificate/NPTEL20CS72S42500326193762) Dec 2020

# Achievements

- Location Intelligence Hackathon Runner up ([Precisely](https://drive.google.com/file/d/1_T92K4bKQzvVeFIxtTEQwMZpjhSO59dl/view?usp=sharing))
- CCI Dean's Fellowship ([Drexel](https://drive.google.com/file/d/13Z0V4Efz6xSRaqlohi9HM6jnbdQ9VdGT/view?usp=sharing))
